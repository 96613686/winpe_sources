# dllmain_dispatch

- ea: `0x1800013f4`
- end: `0x18000151b`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180001530`

## callees

- `0x180001210`
- `0x1800013f4`
- `0x180001784`
- `0x1800065c8`
- `0x18001e010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_180024750 <= 0 )
    return 0;
  if ( fdwReason - 1 > 1
    || (pRawDllMain ? (v7 = ((__int64 (*)(void))pRawDllMain)()) : (v7 = 1),
        v7 && (v7 = dllmain_crt_dispatch(hinstDLL, fdwReason, lpvReserved)) != 0) )
  {
    v8 = DllMain(hinstDLL, fdwReason, lpvReserved);
    v7 = v8;
    if ( fdwReason == 1 && !v8 )
    {
      DllMain(hinstDLL, 0, lpvReserved);
      dllmain_crt_dispatch(hinstDLL, 0, lpvReserved);
      if ( pRawDllMain )
        pRawDllMain(hinstDLL, 0, lpvReserved);
    }
    if ( !fdwReason || fdwReason == 3 )
    {
      v7 = dllmain_crt_dispatch(hinstDLL, fdwReason, lpvReserved);
      if ( v7 )
      {
        if ( pRawDllMain )
          return (unsigned int)pRawDllMain(hinstDLL, fdwReason, lpvReserved);
        else
          return 1;
      }
    }
  }
  return v7;
}

```

## disassembly

```asm
0x1800013f4  mov     rax, rsp
0x1800013f7  mov     [rax+20h], rbx
0x1800013fb  mov     [rax+18h], r8
0x1800013ff  mov     [rax+10h], edx
0x180001402  mov     [rax+8], rcx
0x180001406  push    rsi
0x180001407  push    rdi
0x180001408  push    r14
0x18000140a  sub     rsp, 40h
0x18000140e  mov     rsi, r8
0x180001411  mov     edi, edx
0x180001413  mov     r14, rcx
0x180001416  test    edx, edx
0x180001418  jnz     short loc_180001429
0x18000141a  cmp     cs:dword_180024750, edx
0x180001420  jg      short loc_180001429
0x180001422  xor     eax, eax
0x180001424  jmp     loc_18000150D
0x180001429  lea     eax, [rdx-1]
0x18000142c  cmp     eax, 1
0x18000142f  ja      short loc_180001470
0x180001431  mov     rax, cs:_pRawDllMain
0x180001438  test    rax, rax
0x18000143b  jnz     short loc_180001442
0x18000143d  lea     ebx, [rax+1]
0x180001440  jmp     short loc_180001449
0x180001442  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001447  mov     ebx, eax
0x180001449  mov     [rsp+58h+var_28], ebx
0x18000144d  test    ebx, ebx
0x18000144f  jz      loc_180001503
0x180001455  mov     r8, rsi
0x180001458  mov     edx, edi
0x18000145a  mov     rcx, r14
0x18000145d  call    dllmain_crt_dispatch
0x180001462  mov     ebx, eax
0x180001464  mov     [rsp+58h+var_28], eax
0x180001468  test    eax, eax
0x18000146a  jz      loc_180001503
0x180001470  mov     r8, rsi; lpvReserved
0x180001473  mov     edx, edi; fdwReason
0x180001475  mov     rcx, r14; hinstDLL
0x180001478  call    DllMain
0x18000147d  mov     ebx, eax
0x18000147f  mov     [rsp+58h+var_28], eax
0x180001483  cmp     edi, 1
0x180001486  jnz     short loc_1800014BF
0x180001488  test    eax, eax
0x18000148a  jnz     short loc_1800014BF
0x18000148c  mov     r8, rsi; lpvReserved
0x18000148f  xor     edx, edx; fdwReason
0x180001491  mov     rcx, r14; hinstDLL
0x180001494  call    DllMain
0x180001499  mov     r8, rsi
0x18000149c  xor     edx, edx
0x18000149e  mov     rcx, r14
0x1800014a1  call    dllmain_crt_dispatch
0x1800014a6  mov     rax, cs:_pRawDllMain
0x1800014ad  test    rax, rax
0x1800014b0  jz      short loc_1800014BF
0x1800014b2  mov     r8, rsi
0x1800014b5  xor     edx, edx
0x1800014b7  mov     rcx, r14
0x1800014ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800014bf  test    edi, edi
0x1800014c1  jz      short loc_1800014C8
0x1800014c3  cmp     edi, 3
0x1800014c6  jnz     short loc_180001503
0x1800014c8  mov     r8, rsi
0x1800014cb  mov     edx, edi
0x1800014cd  mov     rcx, r14
0x1800014d0  call    dllmain_crt_dispatch
0x1800014d5  mov     ebx, eax
0x1800014d7  mov     [rsp+58h+var_28], eax
0x1800014db  test    eax, eax
0x1800014dd  jz      short loc_180001503
0x1800014df  mov     rax, cs:_pRawDllMain
0x1800014e6  test    rax, rax
0x1800014e9  jnz     short loc_1800014F0
0x1800014eb  lea     ebx, [rax+1]
0x1800014ee  jmp     short loc_1800014FF
0x1800014f0  mov     r8, rsi
0x1800014f3  mov     edx, edi
0x1800014f5  mov     rcx, r14
0x1800014f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800014fd  mov     ebx, eax
0x1800014ff  mov     [rsp+58h+var_28], ebx
0x180001503  jmp     short loc_18000150B
0x180001505  xor     ebx, ebx
0x180001507  mov     [rsp+58h+var_28], ebx
0x18000150b  mov     eax, ebx
0x18000150d  mov     rbx, [rsp+58h+arg_18]
0x180001512  add     rsp, 40h
0x180001516  pop     r14
0x180001518  pop     rdi
0x180001519  pop     rsi
0x18000151a  retn
0x18001d42c  push    rbp
0x18001d42e  sub     rsp, 30h
0x18001d432  mov     rbp, rdx
0x18001d435  mov     rax, [rcx]
0x18001d438  mov     edx, [rax]
0x18001d43a  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x18001d43f  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x18001d443  lea     r9, dllmain_crt_dispatch; int
0x18001d44a  mov     r8, [rbp+70h]; int
0x18001d44e  mov     edx, [rbp+68h]; int
0x18001d451  mov     rcx, [rbp+60h]; int
0x18001d455  call    __scrt_dllmain_exception_filter
0x18001d45a  nop
0x18001d45b  add     rsp, 30h
0x18001d45f  pop     rbp
0x18001d460  retn
```
