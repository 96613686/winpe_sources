# WPP_SF_SSSS

- ea: `0x180010e68`
- end: `0x180010f89`
- name: `WPP_SF_SSSS`
- size: `289`
- prototype: `__int64 __fastcall(__int64, unsigned __int16, __int64, const wchar_t *, __int64, __int64, __int64)`
- caller_count: `6`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180001600`
- `0x180002970`
- `0x180004340`
- `0x180006c50`
- `0x1800070c0`
- `0x18000bda0`

## callees

- `0x180010e68`

## import_xrefs

- `ntdll!EtwTraceMessage` at `0x180010f76`
- `ntdll!EtwTraceMessage` at `0x180010f76`

## pseudocode

```c
__int64 __fastcall WPP_SF_SSSS(
        __int64 a1,
        unsigned __int16 a2,
        __int64 a3,
        const wchar_t *a4,
        __int64 a5,
        __int64 a6,
        __int64 a7)
{
  __int64 v7; // r8
  __int64 v8; // rax
  __int64 v9; // rax
  __int64 v10; // rax
  bool v11; // zf

  v7 = -1;
  if ( a7 )
  {
    v8 = -1;
    do
      ++v8;
    while ( *(_WORD *)(a7 + 2 * v8) );
  }
  if ( a6 )
  {
    v9 = -1;
    do
      ++v9;
    while ( *(_WORD *)(a6 + 2 * v9) );
  }
  if ( a5 )
  {
    v10 = -1;
    do
      ++v10;
    while ( *(_WORD *)(a5 + 2 * v10) );
  }
  v11 = a4 == 0;
  if ( a4 )
  {
    do
      ++v7;
    while ( a4[v7] );
    v11 = a4 == 0;
  }
  if ( v11 )
    a4 = L"NULL";
  return EtwTraceMessage(a1, 43, WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids, a2, a4);
}

```

## disassembly

```asm
0x180010e68  push    rbx
0x180010e6a  push    rbp
0x180010e6b  push    rsi
0x180010e6c  push    rdi
0x180010e6d  push    r14
0x180010e6f  push    r15
0x180010e71  sub     rsp, 78h
0x180010e75  mov     r11, [rsp+0A8h+arg_30]
0x180010e7d  or      r8, 0FFFFFFFFFFFFFFFFh
0x180010e81  xor     r14d, r14d
0x180010e84  movzx   esi, dx
0x180010e87  mov     rbp, rcx
0x180010e8a  mov     r10d, 0Ah
0x180010e90  test    r11, r11
0x180010e93  jz      short loc_180010EAC
0x180010e95  mov     rax, r8
0x180010e98  inc     rax
0x180010e9b  cmp     [r11+rax*2], r14w
0x180010ea0  jnz     short loc_180010E98
0x180010ea2  lea     rdi, ds:2[rax*2]
0x180010eaa  jmp     short loc_180010EAF
0x180010eac  mov     rdi, r10
0x180010eaf  mov     rdx, [rsp+0A8h+arg_28]
0x180010eb7  lea     r15, aNull_0; "NULL"
0x180010ebe  test    r11, r11
0x180010ec1  cmovz   r11, r15
0x180010ec5  test    rdx, rdx
0x180010ec8  jz      short loc_180010EE1
0x180010eca  mov     rax, r8
0x180010ecd  inc     rax
0x180010ed0  cmp     [rdx+rax*2], r14w
0x180010ed5  jnz     short loc_180010ECD
0x180010ed7  lea     rbx, ds:2[rax*2]
0x180010edf  jmp     short loc_180010EE4
0x180010ee1  mov     rbx, r10
0x180010ee4  mov     rcx, [rsp+0A8h+arg_20]
0x180010eec  test    rdx, rdx
0x180010eef  cmovz   rdx, r15
0x180010ef3  test    rcx, rcx
0x180010ef6  jz      short loc_180010F0F
0x180010ef8  mov     rax, r8
0x180010efb  inc     rax
0x180010efe  cmp     [rcx+rax*2], r14w
0x180010f03  jnz     short loc_180010EFB
0x180010f05  lea     rax, ds:2[rax*2]
0x180010f0d  jmp     short loc_180010F12
0x180010f0f  mov     rax, r10
0x180010f12  test    rcx, rcx
0x180010f15  cmovz   rcx, r15
0x180010f19  test    r9, r9
0x180010f1c  jz      short loc_180010F33
0x180010f1e  inc     r8
0x180010f21  cmp     [r9+r8*2], r14w
0x180010f26  jnz     short loc_180010F1E
0x180010f28  lea     r10, ds:2[r8*2]
0x180010f30  test    r9, r9
0x180010f33  mov     [rsp+0A8h+var_48], r14
0x180010f38  lea     r8, WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids
0x180010f3f  mov     [rsp+0A8h+var_50], rdi
0x180010f44  cmovz   r9, r15
0x180010f48  mov     [rsp+0A8h+var_58], r11
0x180010f4d  mov     [rsp+0A8h+var_60], rbx
0x180010f52  mov     [rsp+0A8h+var_68], rdx
0x180010f57  mov     edx, 2Bh ; '+'
0x180010f5c  mov     [rsp+0A8h+var_70], rax
0x180010f61  mov     [rsp+0A8h+var_78], rcx
0x180010f66  mov     rcx, rbp
0x180010f69  mov     [rsp+0A8h+var_80], r10
0x180010f6e  mov     [rsp+0A8h+var_88], r9
0x180010f73  mov     r9d, esi
0x180010f76  call    cs:__imp_EtwTraceMessage
0x180010f7c  add     rsp, 78h
0x180010f80  pop     r15
0x180010f82  pop     r14
0x180010f84  pop     rdi
0x180010f85  pop     rsi
0x180010f86  pop     rbp
0x180010f87  pop     rbx
0x180010f88  retn
```
