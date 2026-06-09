# FveConfigManageGet

- ea: `0x140081b24`
- end: `0x140081c37`
- name: `FveConfigManageGet`
- size: `275`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x1400520f8`

## callees

- `0x1400218c0`
- `0x140021d00`
- `0x140081b24`
- `0x1400da590`
- `0x1400da8d4`

## import_xrefs

- `ntoskrnl!ProbeForWrite` at `0x140081b85`
- `ntoskrnl!ProbeForWrite` at `0x140081b9e`
- `ntoskrnl!ProbeForWrite` at `0x140081b85`
- `ntoskrnl!ProbeForWrite` at `0x140081b9e`
- `ntoskrnl!KeUnstackDetachProcess` at `0x140081c04`
- `ntoskrnl!KeUnstackDetachProcess` at `0x140081c04`
- `ntoskrnl!KeStackAttachProcess` at `0x140081b6e`
- `ntoskrnl!KeStackAttachProcess` at `0x140081b6e`

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
0x140081b24  mov     r11, rsp
0x140081b27  mov     [r11+8], rbx
0x140081b2b  push    rsi
0x140081b2c  push    rdi
0x140081b2d  push    r14
0x140081b2f  sub     rsp, 0F0h
0x140081b36  mov     rax, cs:__security_cookie
0x140081b3d  xor     rax, rsp
0x140081b40  mov     [rsp+108h+var_28], rax
0x140081b48  mov     rsi, rdx
0x140081b4b  xor     ebx, ebx
0x140081b4d  mov     rdi, [r9+8]
0x140081b51  mov     r14, [r9+18h]
0x140081b55  xorps   xmm0, xmm0
0x140081b58  movups  xmmword ptr [r11-58h], xmm0
0x140081b5d  movups  xmmword ptr [r11-48h], xmm0
0x140081b62  movups  xmmword ptr [r11-38h], xmm0
0x140081b67  lea     rdx, [r11-58h]; ApcState
0x140081b6b  mov     rcx, r8; PROCESS
0x140081b6e  call    cs:__imp_KeStackAttachProcess
0x140081b75  nop     dword ptr [rax+rax+00h]
0x140081b7a  nop
0x140081b7b  lea     edx, [rbx+8]; Length
0x140081b7e  lea     r8d, [rbx+4]; Alignment
0x140081b82  mov     rcx, r14; Address
0x140081b85  call    cs:__imp_ProbeForWrite
0x140081b8c  nop     dword ptr [rax+rax+00h]
0x140081b91  mov     [r14], rbx
0x140081b94  lea     edx, [rbx+10h]; Length
0x140081b97  lea     r8d, [rbx+4]; Alignment
0x140081b9b  mov     rcx, rdi; Address
0x140081b9e  call    cs:__imp_ProbeForWrite
0x140081ba5  nop     dword ptr [rax+rax+00h]
0x140081baa  xorps   xmm0, xmm0
0x140081bad  movups  xmmword ptr [rdi], xmm0
0x140081bb0  test    rsi, rsi
0x140081bb3  jz      short loc_140081BF5
0x140081bb5  xor     edx, edx; Val
0x140081bb7  mov     r8d, 90h; Size
0x140081bbd  lea     rcx, [rsp+108h+var_E8]; void *
0x140081bc2  call    memset
0x140081bc7  xor     r8d, r8d
0x140081bca  lea     rdx, [rsp+108h+var_E8]
0x140081bcf  mov     rcx, rsi
0x140081bd2  call    FvepAcquireDevFveLock
0x140081bd7  mov     rax, [rsi+3D0h]
0x140081bde  test    rax, rax
0x140081be1  jz      short loc_140081BEB
0x140081be3  movups  xmm0, xmmword ptr [rax+50h]
0x140081be7  movdqu  xmmword ptr [rdi], xmm0
0x140081beb  lea     rcx, [rsp+108h+var_E8]
0x140081bf0  call    FvepReleaseDevFveLock
0x140081bf5  jmp     short loc_140081BFC
0x140081bf7  mov     ebx, 0C000000Dh
0x140081bfc  lea     rcx, [rsp+108h+ApcState]; ApcState
0x140081c04  call    cs:__imp_KeUnstackDetachProcess
0x140081c0b  nop     dword ptr [rax+rax+00h]
0x140081c10  mov     eax, ebx
0x140081c12  mov     rcx, [rsp+108h+var_28]
0x140081c1a  xor     rcx, rsp; StackCookie
0x140081c1d  call    __security_check_cookie
0x140081c22  mov     rbx, [rsp+108h+arg_0]
0x140081c2a  add     rsp, 0F0h
0x140081c31  pop     r14
0x140081c33  pop     rdi
0x140081c34  pop     rsi
0x140081c35  retn
```
