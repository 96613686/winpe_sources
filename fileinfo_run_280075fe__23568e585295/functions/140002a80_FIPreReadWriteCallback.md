# FIPreReadWriteCallback

- ea: `0x140002a80`
- end: `0x140002cb3`
- name: `FIPreReadWriteCallback`
- size: `563`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: ``

## callees

- `0x1400024e0`
- `0x140002708`
- `0x140002a80`
- `0x140002ec0`
- `0x140003920`
- `0x140003a00`
- `0x14000e148`
- `0x1400138d4`

## import_xrefs

- `ntoskrnl!PsGetThreadId` at `0x140002b28`
- `ntoskrnl!PsGetThreadId` at `0x140002b28`
- `ntoskrnl!FsRtlIsPagingFile` at `0x140002bc7`
- `ntoskrnl!FsRtlIsPagingFile` at `0x140002bc7`
- `FLTMGR!FltGetActivityIdCallbackData` at `0x140002b88`
- `FLTMGR!FltGetActivityIdCallbackData` at `0x140002b88`
- `FLTMGR!FltReleaseContext` at `0x140002c06`
- `FLTMGR!FltReleaseContext` at `0x140002c06`

## pseudocode

```c
__int64 __fastcall FIPreReadWriteCallback(__int64 a1, _QWORD *a2, _QWORD *a3)
{
  struct _FILE_OBJECT *v3; // r14
  void *v4; // rsi
  void (__fastcall *v8)(_QWORD, _QWORD *, __int64, __int64, __int16, __int128 *); // r15
  struct _KTHREAD *v9; // rcx
  unsigned int ThreadId; // eax
  __int64 v11; // rcx
  bool v12; // zf
  __int16 v13; // bx
  int ActivityIdCallbackData; // eax
  __int128 *v15; // rdx
  unsigned int v16; // ebx
  int v18; // eax
  int v19; // ecx
  _DWORD *v20; // [rsp+40h] [rbp-59h] BYREF
  _QWORD v21[2]; // [rsp+48h] [rbp-51h] BYREF
  struct _FILE_OBJECT *v22; // [rsp+58h] [rbp-41h]
  __int128 v23; // [rsp+60h] [rbp-39h] BYREF
  __int128 v24; // [rsp+70h] [rbp-29h]
  __int128 v25; // [rsp+80h] [rbp-19h]
  __int128 v26; // [rsp+90h] [rbp-9h] BYREF
  _QWORD v27[2]; // [rsp+A0h] [rbp+7h] BYREF

  v3 = (struct _FILE_OBJECT *)a2[4];
  v4 = 0;
  v21[0] = a2[2];
  v21[1] = a2[3];
  v23 = 0;
  v24 = 0;
  v20 = 0;
  v25 = 0;
  v22 = v3;
  v26 = 0;
  v8 = *(void (__fastcall **)(_QWORD, _QWORD *, __int64, __int64, __int16, __int128 *))(qword_140009A00 + 16);
  if ( v8 )
  {
    if ( (*(_BYTE *)(*(_QWORD *)(a1 + 16) + 5LL) & 2) != 0 )
    {
      FIETWLogMdlReadWrite();
    }
    else
    {
      v9 = *(struct _KTHREAD **)(a1 + 8);
      *(_QWORD *)&v23 = 0;
      *((_QWORD *)&v23 + 1) = a1;
      v24 = 0;
      v25 = 0;
      if ( v9 )
        ThreadId = (unsigned int)PsGetThreadId(v9);
      else
        ThreadId = -1;
      v11 = *(_QWORD *)(a1 + 16);
      LODWORD(v25) = ThreadId;
      *(_QWORD *)&v24 = a2[4];
      *((_QWORD *)&v24 + 1) = *(_QWORD *)(v24 + 24);
      *(_QWORD *)&v23 = *(_QWORD *)(v11 + 40);
      DWORD1(v25) = *(_DWORD *)(v11 + 24);
      DWORD2(v25) = *(_DWORD *)v11;
      v12 = *(_BYTE *)(v11 + 4) == 3;
      v27[0] = &v23;
      v27[1] = 48;
      v13 = !v12 + 1091;
      ActivityIdCallbackData = FltGetActivityIdCallbackData(a1, &v26);
      v15 = &v26;
      if ( ActivityIdCallbackData < 0 )
        v15 = 0;
      v8(*(_QWORD *)(a1 + 8), v27, 1, 0x4000000, v13, v15);
    }
  }
  if ( FsRtlIsPagingFile(v3) )
  {
    if ( !(unsigned int)FIFindPagefile(v3->FsContext, &v20) )
      FIPagefileQueueQuery(v21);
LABEL_13:
    v16 = 1;
    goto LABEL_14;
  }
  v18 = FIStreamGet(a1, v21, &v20, 0);
  v4 = v20;
  if ( v18 >= 0 && dword_140009A70 == 1 && (v20[14] & 3) == 1 )
    FIStreamQueueQuery(v21, v20);
  v19 = **(_DWORD **)(a1 + 16);
  if ( (v19 & 2) != 0 || (v19 & 1) != 0 || (v22->Flags & 8) != 0 )
    goto LABEL_13;
  v16 = 0;
LABEL_14:
  *a3 = 0;
  if ( v4 )
    FltReleaseContext(v4);
  if ( *(_QWORD *)(qword_140009A00 + 24) && v16 == 1 )
    return 0;
  return v16;
}

```

## disassembly

```asm
0x140002a80  push    rbp
0x140002a82  push    rbx
0x140002a83  push    rsi
0x140002a84  push    rdi
0x140002a85  push    r12
0x140002a87  push    r14
0x140002a89  push    r15
0x140002a8b  lea     rbp, [rsp-27h]
0x140002a90  sub     rsp, 0C0h
0x140002a97  mov     rax, cs:__security_cookie
0x140002a9e  xor     rax, rsp
0x140002aa1  mov     [rbp+57h+var_40], rax
0x140002aa5  mov     rax, [rdx+10h]
0x140002aa9  xorps   xmm0, xmm0
0x140002aac  mov     r14, [rdx+20h]
0x140002ab0  xor     esi, esi
0x140002ab2  mov     [rbp+57h+var_A8], rax
0x140002ab6  mov     r12, r8
0x140002ab9  mov     rax, [rdx+18h]
0x140002abd  mov     rbx, rdx
0x140002ac0  mov     [rbp+57h+var_A0], rax
0x140002ac4  mov     rdi, rcx
0x140002ac7  mov     rax, cs:qword_140009A00
0x140002ace  movups  [rbp+57h+var_90], xmm0
0x140002ad2  mov     [rbp+57h+var_98], 0
0x140002ada  movups  [rbp+57h+var_80], xmm0
0x140002ade  mov     [rbp+57h+var_B0], rsi
0x140002ae2  movups  [rbp+57h+var_70], xmm0
0x140002ae6  mov     [rbp+57h+var_98], r14
0x140002aea  movups  [rbp+57h+var_60], xmm0
0x140002aee  mov     r15, [rax+10h]
0x140002af2  test    r15, r15
0x140002af5  jz      loc_140002BC4
0x140002afb  mov     rax, [rcx+10h]
0x140002aff  test    byte ptr [rax+5], 2
0x140002b03  jz      short loc_140002B0F
0x140002b05  call    FIETWLogMdlReadWrite
0x140002b0a  jmp     loc_140002BC4
0x140002b0f  mov     rcx, [rcx+8]; Thread
0x140002b13  movups  [rbp+57h+var_90], xmm0
0x140002b17  mov     qword ptr [rbp+57h+var_90+8], rdi
0x140002b1b  movups  [rbp+57h+var_80], xmm0
0x140002b1f  movups  [rbp+57h+var_70], xmm0
0x140002b23  test    rcx, rcx
0x140002b26  jz      short loc_140002B36
0x140002b28  call    cs:__imp_PsGetThreadId
0x140002b2f  nop     dword ptr [rax+rax+00h]
0x140002b34  jmp     short loc_140002B39
0x140002b36  or      eax, 0FFFFFFFFh
0x140002b39  mov     rcx, [rdi+10h]
0x140002b3d  lea     rdx, [rbp+57h+var_60]
0x140002b41  mov     dword ptr [rbp+57h+var_70], eax
0x140002b44  mov     rax, [rbx+20h]
0x140002b48  xor     ebx, ebx
0x140002b4a  mov     qword ptr [rbp+57h+var_80], rax
0x140002b4e  mov     rax, [rax+18h]
0x140002b52  mov     qword ptr [rbp+57h+var_80+8], rax
0x140002b56  mov     rax, [rcx+28h]
0x140002b5a  mov     qword ptr [rbp+57h+var_90], rax
0x140002b5e  mov     eax, [rcx+18h]
0x140002b61  mov     dword ptr [rbp+57h+var_70+4], eax
0x140002b64  mov     eax, [rcx]
0x140002b66  mov     dword ptr [rbp+57h+var_70+8], eax
0x140002b69  lea     rax, [rbp+57h+var_90]
0x140002b6d  cmp     byte ptr [rcx+4], 3
0x140002b71  mov     rcx, rdi
0x140002b74  mov     [rbp+57h+var_50], rax
0x140002b78  setnz   bl
0x140002b7b  mov     [rbp+57h+var_48], 30h ; '0'
0x140002b83  add     bx, 443h
0x140002b88  call    cs:__imp_FltGetActivityIdCallbackData
0x140002b8f  nop     dword ptr [rax+rax+00h]
0x140002b94  xor     ecx, ecx
0x140002b96  lea     rdx, [rbp+57h+var_60]
0x140002b9a  test    eax, eax
0x140002b9c  mov     r9d, 4000000h
0x140002ba2  mov     rax, r15
0x140002ba5  cmovs   rdx, rcx
0x140002ba9  mov     [rsp+0F0h+var_C8], rdx
0x140002bae  lea     r8d, [rcx+1]
0x140002bb2  mov     rcx, [rdi+8]
0x140002bb6  lea     rdx, [rbp+57h+var_50]
0x140002bba  mov     [rsp+0F0h+var_D0], bx
0x140002bbf  call    _guard_dispatch_icall
0x140002bc4  mov     rcx, r14; FileObject
0x140002bc7  call    cs:__imp_FsRtlIsPagingFile
0x140002bce  nop     dword ptr [rax+rax+00h]
0x140002bd3  test    eax, eax
0x140002bd5  jz      short loc_140002C4B
0x140002bd7  mov     rcx, [r14+18h]
0x140002bdb  lea     rdx, [rbp+57h+var_B0]
0x140002bdf  call    FIFindPagefile
0x140002be4  test    eax, eax
0x140002be6  jnz     short loc_140002BF1
0x140002be8  lea     rcx, [rbp+57h+var_A8]
0x140002bec  call    FIPagefileQueueQuery
0x140002bf1  mov     ebx, 1
0x140002bf6  mov     qword ptr [r12], 0
0x140002bfe  test    rsi, rsi
0x140002c01  jz      short loc_140002C12
0x140002c03  mov     rcx, rsi; Context
0x140002c06  call    cs:__imp_FltReleaseContext
0x140002c0d  nop     dword ptr [rax+rax+00h]
0x140002c12  mov     rcx, cs:qword_140009A00
0x140002c19  mov     rdx, [rcx+18h]
0x140002c1d  test    rdx, rdx
0x140002c20  jz      short loc_140002C2A
0x140002c22  xor     ecx, ecx
0x140002c24  cmp     ebx, 1
0x140002c27  cmovz   ebx, ecx
0x140002c2a  mov     eax, ebx
0x140002c2c  mov     rcx, [rbp+57h+var_40]
0x140002c30  xor     rcx, rsp; StackCookie
0x140002c33  call    __security_check_cookie
0x140002c38  add     rsp, 0C0h
0x140002c3f  pop     r15
0x140002c41  pop     r14
0x140002c43  pop     r12
0x140002c45  pop     rdi
0x140002c46  pop     rsi
0x140002c47  pop     rbx
0x140002c48  pop     rbp
0x140002c49  retn
0x140002c4b  xor     r9d, r9d
0x140002c4e  lea     r8, [rbp+57h+var_B0]
0x140002c52  lea     rdx, [rbp+57h+var_A8]
0x140002c56  mov     rcx, rdi
0x140002c59  call    FIStreamGet
0x140002c5e  mov     rsi, [rbp+57h+var_B0]
0x140002c62  test    eax, eax
0x140002c64  js      short loc_140002C84
0x140002c66  mov     eax, [rsi+38h]
0x140002c69  cmp     cs:dword_140009A70, 1
0x140002c70  jnz     short loc_140002C84
0x140002c72  and     al, 3
0x140002c74  cmp     al, 1
0x140002c76  jnz     short loc_140002C84
0x140002c78  mov     rdx, rsi
0x140002c7b  lea     rcx, [rbp+57h+var_A8]
0x140002c7f  call    FIStreamQueueQuery
0x140002c84  mov     rax, [rdi+10h]
0x140002c88  mov     ecx, [rax]
0x140002c8a  test    cl, 2
0x140002c8d  jnz     loc_140002BF1
0x140002c93  test    cl, 1
0x140002c96  jnz     loc_140002BF1
0x140002c9c  mov     rax, [rbp+57h+var_98]
0x140002ca0  mov     ecx, [rax+50h]
0x140002ca3  test    cl, 8
0x140002ca6  jnz     loc_140002BF1
0x140002cac  xor     ebx, ebx
0x140002cae  jmp     loc_140002BF6
```
