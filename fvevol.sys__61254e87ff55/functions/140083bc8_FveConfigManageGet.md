# FveConfigManageGet

- ea: `0x140083bc8`
- end: `0x140083cdb`
- name: `FveConfigManageGet`
- size: `275`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x1400540f8`

## callees

- `0x140022bf0`
- `0x140023040`
- `0x140083bc8`
- `0x1400dce00`
- `0x1400dd144`

## import_xrefs

- `ntoskrnl!ProbeForWrite` at `0x140083c29`
- `ntoskrnl!ProbeForWrite` at `0x140083c42`
- `ntoskrnl!ProbeForWrite` at `0x140083c29`
- `ntoskrnl!ProbeForWrite` at `0x140083c42`
- `ntoskrnl!KeUnstackDetachProcess` at `0x140083ca8`
- `ntoskrnl!KeUnstackDetachProcess` at `0x140083ca8`
- `ntoskrnl!KeStackAttachProcess` at `0x140083c12`
- `ntoskrnl!KeStackAttachProcess` at `0x140083c12`

## pseudocode

```c
__int64 __fastcall FveConfigManageGet(__int64 a1, __int64 a2, struct _KPROCESS *a3, __int64 a4)
{
  _OWORD *v5; // rdi
  _QWORD *v6; // r14
  __int64 v7; // rax
  _BYTE v9[144]; // [rsp+20h] [rbp-E8h] BYREF
  struct _KAPC_STATE ApcState; // [rsp+B0h] [rbp-58h] BYREF

  v5 = *(_OWORD **)(a4 + 8);
  v6 = *(_QWORD **)(a4 + 24);
  memset(&ApcState, 0, sizeof(ApcState));
  KeStackAttachProcess(a3, &ApcState);
  ProbeForWrite(v6, 8u, 4u);
  *v6 = 0;
  ProbeForWrite(v5, 0x10u, 4u);
  *v5 = 0;
  if ( a2 )
  {
    memset(v9, 0, sizeof(v9));
    FvepAcquireDevFveLock(a2, v9, 0);
    v7 = *(_QWORD *)(a2 + 976);
    if ( v7 )
      *v5 = *(_OWORD *)(v7 + 80);
    FvepReleaseDevFveLock(v9);
  }
  KeUnstackDetachProcess(&ApcState);
  return 0;
}

```

## disassembly

```asm
0x140083bc8  mov     r11, rsp
0x140083bcb  mov     [r11+8], rbx
0x140083bcf  push    rsi
0x140083bd0  push    rdi
0x140083bd1  push    r14
0x140083bd3  sub     rsp, 0F0h
0x140083bda  mov     rax, cs:__security_cookie
0x140083be1  xor     rax, rsp
0x140083be4  mov     [rsp+108h+var_28], rax
0x140083bec  mov     rsi, rdx
0x140083bef  xor     ebx, ebx
0x140083bf1  mov     rdi, [r9+8]
0x140083bf5  mov     r14, [r9+18h]
0x140083bf9  xorps   xmm0, xmm0
0x140083bfc  movups  xmmword ptr [r11-58h], xmm0
0x140083c01  movups  xmmword ptr [r11-48h], xmm0
0x140083c06  movups  xmmword ptr [r11-38h], xmm0
0x140083c0b  lea     rdx, [r11-58h]; ApcState
0x140083c0f  mov     rcx, r8; PROCESS
0x140083c12  call    cs:__imp_KeStackAttachProcess
0x140083c19  nop     dword ptr [rax+rax+00h]
0x140083c1e  nop
0x140083c1f  lea     edx, [rbx+8]; Length
0x140083c22  lea     r8d, [rbx+4]; Alignment
0x140083c26  mov     rcx, r14; Address
0x140083c29  call    cs:__imp_ProbeForWrite
0x140083c30  nop     dword ptr [rax+rax+00h]
0x140083c35  mov     [r14], rbx
0x140083c38  lea     edx, [rbx+10h]; Length
0x140083c3b  lea     r8d, [rbx+4]; Alignment
0x140083c3f  mov     rcx, rdi; Address
0x140083c42  call    cs:__imp_ProbeForWrite
0x140083c49  nop     dword ptr [rax+rax+00h]
0x140083c4e  xorps   xmm0, xmm0
0x140083c51  movups  xmmword ptr [rdi], xmm0
0x140083c54  test    rsi, rsi
0x140083c57  jz      short loc_140083C99
0x140083c59  xor     edx, edx; Val
0x140083c5b  mov     r8d, 90h; Size
0x140083c61  lea     rcx, [rsp+108h+var_E8]; void *
0x140083c66  call    memset
0x140083c6b  xor     r8d, r8d
0x140083c6e  lea     rdx, [rsp+108h+var_E8]
0x140083c73  mov     rcx, rsi
0x140083c76  call    FvepAcquireDevFveLock
0x140083c7b  mov     rax, [rsi+3D0h]
0x140083c82  test    rax, rax
0x140083c85  jz      short loc_140083C8F
0x140083c87  movups  xmm0, xmmword ptr [rax+50h]
0x140083c8b  movdqu  xmmword ptr [rdi], xmm0
0x140083c8f  lea     rcx, [rsp+108h+var_E8]
0x140083c94  call    FvepReleaseDevFveLock
0x140083c99  jmp     short loc_140083CA0
0x140083c9b  mov     ebx, 0C000000Dh
0x140083ca0  lea     rcx, [rsp+108h+ApcState]; ApcState
0x140083ca8  call    cs:__imp_KeUnstackDetachProcess
0x140083caf  nop     dword ptr [rax+rax+00h]
0x140083cb4  mov     eax, ebx
0x140083cb6  mov     rcx, [rsp+108h+var_28]
0x140083cbe  xor     rcx, rsp; StackCookie
0x140083cc1  call    __security_check_cookie
0x140083cc6  mov     rbx, [rsp+108h+arg_0]
0x140083cce  add     rsp, 0F0h
0x140083cd5  pop     r14
0x140083cd7  pop     rdi
0x140083cd8  pop     rsi
0x140083cd9  retn
```
