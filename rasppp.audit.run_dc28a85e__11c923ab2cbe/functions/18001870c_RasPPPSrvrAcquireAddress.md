# RasPPPSrvrAcquireAddress

- ea: `0x18001870c`
- end: `0x18001876a`
- name: `RasPPPSrvrAcquireAddress`
- size: `94`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18001fc1c`

## callees

- `0x18001870c`
- `0x180034010`

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
0x18001870c  sub     rsp, 58h
0x180018710  mov     rax, qword ptr cs:g_IpAddrMgmtFunctions
0x180018717  mov     r10, rcx
0x18001871a  test    rax, rax
0x18001871d  jnz     short loc_180018726
0x18001871f  mov     eax, 10DDh
0x180018724  jmp     short loc_180018764
0x180018726  mov     rcx, [rsp+58h+arg_28]
0x18001872e  mov     [rsp+58h+var_28], 0
0x180018736  movups  xmm0, xmmword ptr [rcx]
0x180018739  mov     rcx, [rsp+58h+arg_20]
0x180018741  mov     [rsp+58h+var_30], rcx
0x180018746  lea     rcx, [rsp+58h+var_18]
0x18001874b  mov     [rsp+58h+var_38], r9
0x180018750  mov     r9, r8
0x180018753  mov     r8d, edx
0x180018756  mov     rdx, r10
0x180018759  movdqu  [rsp+58h+var_18], xmm0
0x18001875f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018764  add     rsp, 58h
0x180018768  retn
```
