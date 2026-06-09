# RasPPPSrvrAcquireAddress

- ea: `0x180017ea4`
- end: `0x180017f01`
- name: `RasPPPSrvrAcquireAddress`
- size: `93`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18001f06c`

## callees

- `0x180017ea4`
- `0x180033010`

## pseudocode

```c
__int64 __fastcall RasPPPSrvrAcquireAddress(
        __int64 a1,
        unsigned int a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int128 *a6)
{
  __int128 v7; // [rsp+40h] [rbp-18h] BYREF

  if ( !g_IpAddrMgmtFunctions )
    return 4317;
  v7 = *a6;
  return g_IpAddrMgmtFunctions(&v7, a1, a2, a3, a4, a5, 0);
}

```

## disassembly

```asm
0x180017ea4  sub     rsp, 58h
0x180017ea8  mov     rax, qword ptr cs:g_IpAddrMgmtFunctions
0x180017eaf  mov     r10, rcx
0x180017eb2  test    rax, rax
0x180017eb5  jnz     short loc_180017EBE
0x180017eb7  mov     eax, 10DDh
0x180017ebc  jmp     short loc_180017EFC
0x180017ebe  mov     rcx, [rsp+58h+arg_28]
0x180017ec6  mov     [rsp+58h+var_28], 0
0x180017ece  movups  xmm0, xmmword ptr [rcx]
0x180017ed1  mov     rcx, [rsp+58h+arg_20]
0x180017ed9  mov     [rsp+58h+var_30], rcx
0x180017ede  lea     rcx, [rsp+58h+var_18]
0x180017ee3  mov     [rsp+58h+var_38], r9
0x180017ee8  mov     r9, r8
0x180017eeb  mov     r8d, edx
0x180017eee  mov     rdx, r10
0x180017ef1  movdqu  [rsp+58h+var_18], xmm0
0x180017ef7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017efc  add     rsp, 58h
0x180017f00  retn
```
