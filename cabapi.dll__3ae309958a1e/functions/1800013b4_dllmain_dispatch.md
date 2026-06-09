# dllmain_dispatch

- ea: `0x1800013b4`
- end: `0x1800014db`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x1800014f0`

## callees

- `0x1800011d0`
- `0x1800013b4`
- `0x18000168c`
- `0x180001a58`
- `0x180015010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_18001F270 <= 0 )
    return 0;
  if ( fdwReason - 1 > 1
    || (pRawDllMain ? (v7 = ((__int64 (*)(void))pRawDllMain)()) : (v7 = 1),
        v7 && (v7 = dllmain_crt_dispatch((__int64)hinstDLL, fdwReason, (__int64)lpvReserved)) != 0) )
  {
    v8 = DllMain(hinstDLL, fdwReason, lpvReserved);
    v7 = v8;
    if ( fdwReason == 1 && !v8 )
    {
      DllMain(hinstDLL, 0, lpvReserved);
      dllmain_crt_dispatch((__int64)hinstDLL, 0, (__int64)lpvReserved);
      if ( pRawDllMain )
        pRawDllMain(hinstDLL, 0, lpvReserved);
    }
    if ( !fdwReason || fdwReason == 3 )
    {
      v7 = dllmain_crt_dispatch((__int64)hinstDLL, fdwReason, (__int64)lpvReserved);
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
0x1800013b4  mov     rax, rsp
0x1800013b7  mov     [rax+20h], rbx
0x1800013bb  mov     [rax+18h], r8
0x1800013bf  mov     [rax+10h], edx
0x1800013c2  mov     [rax+8], rcx
0x1800013c6  push    rsi
0x1800013c7  push    rdi
0x1800013c8  push    r14
0x1800013ca  sub     rsp, 40h
0x1800013ce  mov     rsi, r8
0x1800013d1  mov     edi, edx
0x1800013d3  mov     r14, rcx
0x1800013d6  test    edx, edx
0x1800013d8  jnz     short loc_1800013E9
0x1800013da  cmp     cs:dword_18001F270, edx
0x1800013e0  jg      short loc_1800013E9
0x1800013e2  xor     eax, eax
0x1800013e4  jmp     loc_1800014CD
0x1800013e9  lea     eax, [rdx-1]
0x1800013ec  cmp     eax, 1
0x1800013ef  ja      short loc_180001430
0x1800013f1  mov     rax, cs:_pRawDllMain
0x1800013f8  test    rax, rax
0x1800013fb  jnz     short loc_180001402
0x1800013fd  lea     ebx, [rax+1]
0x180001400  jmp     short loc_180001409
0x180001402  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001407  mov     ebx, eax
0x180001409  mov     [rsp+58h+var_28], ebx
0x18000140d  test    ebx, ebx
0x18000140f  jz      loc_1800014C3
0x180001415  mov     r8, rsi
0x180001418  mov     edx, edi
0x18000141a  mov     rcx, r14
0x18000141d  call    dllmain_crt_dispatch
0x180001422  mov     ebx, eax
0x180001424  mov     [rsp+58h+var_28], eax
0x180001428  test    eax, eax
0x18000142a  jz      loc_1800014C3
0x180001430  mov     r8, rsi; lpvReserved
0x180001433  mov     edx, edi; fdwReason
0x180001435  mov     rcx, r14; hinstDLL
0x180001438  call    DllMain
0x18000143d  mov     ebx, eax
0x18000143f  mov     [rsp+58h+var_28], eax
0x180001443  cmp     edi, 1
0x180001446  jnz     short loc_18000147F
0x180001448  test    eax, eax
0x18000144a  jnz     short loc_18000147F
0x18000144c  mov     r8, rsi; lpvReserved
0x18000144f  xor     edx, edx; fdwReason
0x180001451  mov     rcx, r14; hinstDLL
0x180001454  call    DllMain
0x180001459  mov     r8, rsi
0x18000145c  xor     edx, edx
0x18000145e  mov     rcx, r14
0x180001461  call    dllmain_crt_dispatch
0x180001466  mov     rax, cs:_pRawDllMain
0x18000146d  test    rax, rax
0x180001470  jz      short loc_18000147F
0x180001472  mov     r8, rsi
0x180001475  xor     edx, edx
0x180001477  mov     rcx, r14
0x18000147a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000147f  test    edi, edi
0x180001481  jz      short loc_180001488
0x180001483  cmp     edi, 3
0x180001486  jnz     short loc_1800014C3
0x180001488  mov     r8, rsi
0x18000148b  mov     edx, edi
0x18000148d  mov     rcx, r14
0x180001490  call    dllmain_crt_dispatch
0x180001495  mov     ebx, eax
0x180001497  mov     [rsp+58h+var_28], eax
0x18000149b  test    eax, eax
0x18000149d  jz      short loc_1800014C3
0x18000149f  mov     rax, cs:_pRawDllMain
0x1800014a6  test    rax, rax
0x1800014a9  jnz     short loc_1800014B0
0x1800014ab  lea     ebx, [rax+1]
0x1800014ae  jmp     short loc_1800014BF
0x1800014b0  mov     r8, rsi
0x1800014b3  mov     edx, edi
0x1800014b5  mov     rcx, r14
0x1800014b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800014bd  mov     ebx, eax
0x1800014bf  mov     [rsp+58h+var_28], ebx
0x1800014c3  jmp     short loc_1800014CB
0x1800014c5  xor     ebx, ebx
0x1800014c7  mov     [rsp+58h+var_28], ebx
0x1800014cb  mov     eax, ebx
0x1800014cd  mov     rbx, [rsp+58h+arg_18]
0x1800014d2  add     rsp, 40h
0x1800014d6  pop     r14
0x1800014d8  pop     rdi
0x1800014d9  pop     rsi
0x1800014da  retn
0x180013ecc  push    rbp
0x180013ece  sub     rsp, 30h
0x180013ed2  mov     rbp, rdx
0x180013ed5  mov     rax, [rcx]
0x180013ed8  mov     edx, [rax]
0x180013eda  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x180013edf  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x180013ee3  lea     r9, dllmain_crt_dispatch; int
0x180013eea  mov     r8, [rbp+70h]; int
0x180013eee  mov     edx, [rbp+68h]; int
0x180013ef1  mov     rcx, [rbp+60h]; int
0x180013ef5  call    __scrt_dllmain_exception_filter
0x180013efa  nop
0x180013efb  add     rsp, 30h
0x180013eff  pop     rbp
0x180013f00  retn
```
