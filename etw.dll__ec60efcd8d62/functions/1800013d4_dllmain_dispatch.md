# dllmain_dispatch

- ea: `0x1800013d4`
- end: `0x1800014fb`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180001510`

## callees

- `0x1800011f0`
- `0x1800013d4`
- `0x180001764`
- `0x180002340`
- `0x180016010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_18001D1D0 <= 0 )
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
0x1800013d4  mov     rax, rsp
0x1800013d7  mov     [rax+20h], rbx
0x1800013db  mov     [rax+18h], r8
0x1800013df  mov     [rax+10h], edx
0x1800013e2  mov     [rax+8], rcx
0x1800013e6  push    rsi
0x1800013e7  push    rdi
0x1800013e8  push    r14
0x1800013ea  sub     rsp, 40h
0x1800013ee  mov     rsi, r8
0x1800013f1  mov     edi, edx
0x1800013f3  mov     r14, rcx
0x1800013f6  test    edx, edx
0x1800013f8  jnz     short loc_180001409
0x1800013fa  cmp     cs:dword_18001D1D0, edx
0x180001400  jg      short loc_180001409
0x180001402  xor     eax, eax
0x180001404  jmp     loc_1800014ED
0x180001409  lea     eax, [rdx-1]
0x18000140c  cmp     eax, 1
0x18000140f  ja      short loc_180001450
0x180001411  mov     rax, cs:_pRawDllMain
0x180001418  test    rax, rax
0x18000141b  jnz     short loc_180001422
0x18000141d  lea     ebx, [rax+1]
0x180001420  jmp     short loc_180001429
0x180001422  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001427  mov     ebx, eax
0x180001429  mov     [rsp+58h+var_28], ebx
0x18000142d  test    ebx, ebx
0x18000142f  jz      loc_1800014E3
0x180001435  mov     r8, rsi
0x180001438  mov     edx, edi
0x18000143a  mov     rcx, r14
0x18000143d  call    dllmain_crt_dispatch
0x180001442  mov     ebx, eax
0x180001444  mov     [rsp+58h+var_28], eax
0x180001448  test    eax, eax
0x18000144a  jz      loc_1800014E3
0x180001450  mov     r8, rsi; lpvReserved
0x180001453  mov     edx, edi; fdwReason
0x180001455  mov     rcx, r14; hinstDLL
0x180001458  call    DllMain
0x18000145d  mov     ebx, eax
0x18000145f  mov     [rsp+58h+var_28], eax
0x180001463  cmp     edi, 1
0x180001466  jnz     short loc_18000149F
0x180001468  test    eax, eax
0x18000146a  jnz     short loc_18000149F
0x18000146c  mov     r8, rsi; lpvReserved
0x18000146f  xor     edx, edx; fdwReason
0x180001471  mov     rcx, r14; hinstDLL
0x180001474  call    DllMain
0x180001479  mov     r8, rsi
0x18000147c  xor     edx, edx
0x18000147e  mov     rcx, r14
0x180001481  call    dllmain_crt_dispatch
0x180001486  mov     rax, cs:_pRawDllMain
0x18000148d  test    rax, rax
0x180001490  jz      short loc_18000149F
0x180001492  mov     r8, rsi
0x180001495  xor     edx, edx
0x180001497  mov     rcx, r14
0x18000149a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000149f  test    edi, edi
0x1800014a1  jz      short loc_1800014A8
0x1800014a3  cmp     edi, 3
0x1800014a6  jnz     short loc_1800014E3
0x1800014a8  mov     r8, rsi
0x1800014ab  mov     edx, edi
0x1800014ad  mov     rcx, r14
0x1800014b0  call    dllmain_crt_dispatch
0x1800014b5  mov     ebx, eax
0x1800014b7  mov     [rsp+58h+var_28], eax
0x1800014bb  test    eax, eax
0x1800014bd  jz      short loc_1800014E3
0x1800014bf  mov     rax, cs:_pRawDllMain
0x1800014c6  test    rax, rax
0x1800014c9  jnz     short loc_1800014D0
0x1800014cb  lea     ebx, [rax+1]
0x1800014ce  jmp     short loc_1800014DF
0x1800014d0  mov     r8, rsi
0x1800014d3  mov     edx, edi
0x1800014d5  mov     rcx, r14
0x1800014d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800014dd  mov     ebx, eax
0x1800014df  mov     [rsp+58h+var_28], ebx
0x1800014e3  jmp     short loc_1800014EB
0x1800014e5  xor     ebx, ebx
0x1800014e7  mov     [rsp+58h+var_28], ebx
0x1800014eb  mov     eax, ebx
0x1800014ed  mov     rbx, [rsp+58h+arg_18]
0x1800014f2  add     rsp, 40h
0x1800014f6  pop     r14
0x1800014f8  pop     rdi
0x1800014f9  pop     rsi
0x1800014fa  retn
0x18001590c  push    rbp
0x18001590e  sub     rsp, 30h
0x180015912  mov     rbp, rdx
0x180015915  mov     rax, [rcx]
0x180015918  mov     edx, [rax]
0x18001591a  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x18001591f  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x180015923  lea     r9, dllmain_crt_dispatch; int
0x18001592a  mov     r8, [rbp+70h]; int
0x18001592e  mov     edx, [rbp+68h]; int
0x180015931  mov     rcx, [rbp+60h]; int
0x180015935  call    __scrt_dllmain_exception_filter
0x18001593a  nop
0x18001593b  add     rsp, 30h
0x18001593f  pop     rbp
0x180015940  retn
```
