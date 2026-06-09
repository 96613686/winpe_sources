# FIPreFSControlCallback

- ea: `0x1400149e0`
- end: `0x140014bdf`
- name: `FIPreFSControlCallback`
- size: `511`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x140003920`
- `0x140003a00`
- `0x140010cd0`
- `0x1400149e0`

## import_xrefs

- `ntoskrnl!PsGetThreadId` at `0x140014a92`
- `ntoskrnl!PsGetThreadId` at `0x140014a92`
- `ntoskrnl!IoGetTopLevelIrp` at `0x140014b27`
- `ntoskrnl!IoGetTopLevelIrp` at `0x140014b27`
- `FLTMGR!FltGetActivityIdCallbackData` at `0x140014acb`
- `FLTMGR!FltGetActivityIdCallbackData` at `0x140014acb`

## pseudocode

```c
__int64 __fastcall FIPreFSControlCallback(unsigned __int64 a1, _QWORD *a2, __int64 *a3)
{
  __int64 v3; // rdi
  __int64 v5; // rcx
  unsigned int v8; // r15d
  int v9; // esi
  void (__fastcall *v10)(_QWORD, _QWORD *, __int64, __int64, __int16, __int128 *); // r13
  struct _KTHREAD *v11; // rcx
  unsigned int ThreadId; // eax
  int ActivityIdCallbackData; // eax
  __int128 *v14; // rdx
  unsigned int v15; // ebx
  __int64 v17; // [rsp+48h] [rbp-49h] BYREF
  _QWORD v18[3]; // [rsp+50h] [rbp-41h] BYREF
  __int128 v19; // [rsp+68h] [rbp-29h] BYREF
  _BYTE v20[24]; // [rsp+78h] [rbp-19h] BYREF
  __int128 v21; // [rsp+90h] [rbp-1h] BYREF
  _QWORD v22[2]; // [rsp+A0h] [rbp+Fh] BYREF

  v3 = 0;
  v17 = 0;
  v5 = *(_QWORD *)(a1 + 16);
  v19 = 0;
  memset(v20, 0, sizeof(v20));
  v21 = 0;
  if ( (*(_BYTE *)(v5 + 5) & 0xFB) != 0 )
    return 1;
  v8 = 1;
  v18[0] = a2[2];
  v18[1] = a2[3];
  v9 = *(_DWORD *)(v5 + 40);
  v18[2] = a2[4];
  v10 = *(void (__fastcall **)(_QWORD, _QWORD *, __int64, __int64, __int16, __int128 *))(qword_140009A00 + 16);
  if ( v10 )
  {
    v11 = *(struct _KTHREAD **)(a1 + 8);
    memset(v20, 0, sizeof(v20));
    v19 = a1;
    if ( v11 )
      ThreadId = (unsigned int)PsGetThreadId(v11);
    else
      ThreadId = -1;
    *(_DWORD *)&v20[16] = ThreadId;
    *((_QWORD *)&v19 + 1) = a2[4];
    *(_QWORD *)v20 = *(_QWORD *)(*((_QWORD *)&v19 + 1) + 24LL);
    v22[0] = &v19;
    *(_DWORD *)&v20[20] = v9;
    v22[1] = 40;
    ActivityIdCallbackData = FltGetActivityIdCallbackData(a1, &v21);
    v14 = &v21;
    if ( ActivityIdCallbackData < 0 )
      v14 = 0;
    v10(*(_QWORD *)(a1 + 8), v22, 1, 0x4000000, 1099, v14);
  }
  if ( v9 == 589848 || (v15 = 1, v9 == 589856) )
  {
    _InterlockedIncrement(&dword_1400099F8);
    v15 = 0;
  }
  if ( !IoGetTopLevelIrp() )
  {
    if ( v9 != 589848 )
    {
      if ( v9 != 589856 )
      {
        if ( v9 == 589940 )
          v15 = 5;
        goto LABEL_15;
      }
      v8 = 2;
    }
    FIPfVolumeFSOpPreventConflicts((__int64)v18, v8, &v17);
    v3 = v17;
    v15 = 0;
  }
LABEL_15:
  *a3 = v3;
  if ( *(_QWORD *)(qword_140009A00 + 24) )
  {
    if ( v15 == 1 )
      return 0;
  }
  return v15;
}

```

## disassembly

```asm
0x1400149e0  mov     r11, rsp
0x1400149e3  push    rbp
0x1400149e4  push    rbx
0x1400149e5  push    rdi
0x1400149e6  push    r12
0x1400149e8  push    r14
0x1400149ea  push    r15
0x1400149ec  lea     rbp, [r11-5Fh]
0x1400149f0  sub     rsp, 0B8h
0x1400149f7  mov     rax, cs:__security_cookie
0x1400149fe  xor     rax, rsp
0x140014a01  mov     [rbp+57h+var_38], rax
0x140014a05  xorps   xmm0, xmm0
0x140014a08  xor     eax, eax
0x140014a0a  xor     edi, edi
0x140014a0c  mov     [rbp+57h+var_60], rax
0x140014a10  mov     rbx, rcx
0x140014a13  mov     [rbp+57h+var_A0], rdi
0x140014a17  mov     rcx, [rcx+10h]
0x140014a1b  mov     r12, r8
0x140014a1e  movups  [rbp+57h+var_80], xmm0
0x140014a22  mov     r14, rdx
0x140014a25  movups  [rbp+57h+var_70], xmm0
0x140014a29  movups  [rbp+57h+var_58], xmm0
0x140014a2d  test    byte ptr [rcx+5], 0FBh
0x140014a31  jnz     loc_140014B96
0x140014a37  mov     rax, [rdx+10h]
0x140014a3b  mov     r15d, 1
0x140014a41  mov     [rbp+57h+var_98], rax
0x140014a45  mov     rax, [rdx+18h]
0x140014a49  mov     [rbp+57h+var_90], rax
0x140014a4d  mov     rax, [rdx+20h]
0x140014a51  mov     [r11+10h], rsi
0x140014a55  mov     esi, [rcx+28h]
0x140014a58  mov     [rbp+57h+var_88], rax
0x140014a5c  mov     rax, cs:qword_140009A00
0x140014a63  mov     [r11-38h], r13
0x140014a67  mov     r13, [rax+10h]
0x140014a6b  test    r13, r13
0x140014a6e  jz      loc_140014B08
0x140014a74  mov     rcx, [rbx+8]; Thread
0x140014a78  mov     qword ptr [rbp+57h+var_80+8], rdi
0x140014a7c  mov     qword ptr [rbp+57h+var_70], rdi
0x140014a80  mov     qword ptr [rbp+57h+var_80], rbx
0x140014a84  movdqu  [rbp+57h+var_70+8], xmm0
0x140014a89  test    rcx, rcx
0x140014a8c  jz      loc_140014BB4
0x140014a92  call    cs:__imp_PsGetThreadId
0x140014a99  nop     dword ptr [rax+rax+00h]
0x140014a9e  mov     dword ptr [rbp+57h+var_60], eax
0x140014aa1  lea     rdx, [rbp+57h+var_58]
0x140014aa5  mov     rax, [r14+20h]
0x140014aa9  mov     rcx, rbx
0x140014aac  mov     qword ptr [rbp+57h+var_80+8], rax
0x140014ab0  mov     rax, [rax+18h]
0x140014ab4  mov     qword ptr [rbp+57h+var_70], rax
0x140014ab8  lea     rax, [rbp+57h+var_80]
0x140014abc  mov     [rbp+57h+var_48], rax
0x140014ac0  mov     dword ptr [rbp+57h+var_60+4], esi
0x140014ac3  mov     [rbp+57h+var_40], 28h ; '('
0x140014acb  call    cs:__imp_FltGetActivityIdCallbackData
0x140014ad2  nop     dword ptr [rax+rax+00h]
0x140014ad7  xor     ecx, ecx
0x140014ad9  lea     rdx, [rbp+57h+var_58]
0x140014add  test    eax, eax
0x140014adf  mov     r9d, 4000000h
0x140014ae5  mov     r8d, r15d
0x140014ae8  mov     rax, r13
0x140014aeb  cmovs   rdx, rcx
0x140014aef  mov     rcx, [rbx+8]
0x140014af3  mov     [rsp+28h], rdx
0x140014af8  lea     rdx, [rbp+57h+var_48]
0x140014afc  mov     word ptr [rsp+0E0h+var_C0], 44Bh
0x140014b03  call    _guard_dispatch_icall
0x140014b08  mov     r13, [rsp+0B0h]
0x140014b10  cmp     esi, 90018h
0x140014b16  jz      loc_140014BA6
0x140014b1c  mov     ebx, r15d
0x140014b1f  cmp     esi, 90020h
0x140014b25  jz      short loc_140014BA6
0x140014b27  call    cs:__imp_IoGetTopLevelIrp
0x140014b2e  nop     dword ptr [rax+rax+00h]
0x140014b33  test    rax, rax
0x140014b36  jnz     short loc_140014B5A
0x140014b38  cmp     esi, 90018h
0x140014b3e  jz      loc_140014BC4
0x140014b44  cmp     esi, 90020h
0x140014b4a  jz      short loc_140014BBE
0x140014b4c  cmp     esi, 90074h
0x140014b52  mov     eax, 5
0x140014b57  cmovz   ebx, eax
0x140014b5a  mov     rsi, [rsp+0E0h+arg_8]
0x140014b62  mov     [r12], rdi
0x140014b66  mov     rax, cs:qword_140009A00
0x140014b6d  mov     rcx, [rax+18h]
0x140014b71  test    rcx, rcx
0x140014b74  jnz     short loc_140014B9D
0x140014b76  mov     eax, ebx
0x140014b78  mov     rcx, [rbp+57h+var_38]
0x140014b7c  xor     rcx, rsp; StackCookie
0x140014b7f  call    __security_check_cookie
0x140014b84  add     rsp, 0B8h
0x140014b8b  pop     r15
0x140014b8d  pop     r14
0x140014b8f  pop     r12
0x140014b91  pop     rdi
0x140014b92  pop     rbx
0x140014b93  pop     rbp
0x140014b94  retn
0x140014b96  mov     eax, 1
0x140014b9b  jmp     short loc_140014B78
0x140014b9d  cmp     ebx, 1
0x140014ba0  jnz     short loc_140014B76
0x140014ba2  xor     ebx, ebx
0x140014ba4  jmp     short loc_140014B76
0x140014ba6  lock inc cs:dword_1400099F8
0x140014bad  xor     ebx, ebx
0x140014baf  jmp     loc_140014B27
0x140014bb4  mov     eax, 0FFFFFFFFh
0x140014bb9  jmp     loc_140014A9E
0x140014bbe  mov     r15d, 2
0x140014bc4  lea     r8, [rbp+57h+var_A0]
0x140014bc8  mov     edx, r15d
0x140014bcb  lea     rcx, [rbp+57h+var_98]
0x140014bcf  call    FIPfVolumeFSOpPreventConflicts
0x140014bd4  mov     rdi, [rbp+57h+var_A0]
0x140014bd8  xor     ebx, ebx
0x140014bda  jmp     loc_140014B5A
```
