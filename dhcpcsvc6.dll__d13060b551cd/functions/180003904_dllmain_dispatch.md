# dllmain_dispatch

- ea: `0x180003904`
- end: `0x180003a2b`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180003a40`

## callees

- `0x180003720`
- `0x180003904`
- `0x180003c94`
- `0x18000456c`
- `0x180009010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_18000F090 <= 0 )
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
0x180003904  mov     rax, rsp
0x180003907  mov     [rax+20h], rbx
0x18000390b  mov     [rax+18h], r8
0x18000390f  mov     [rax+10h], edx
0x180003912  mov     [rax+8], rcx
0x180003916  push    rsi
0x180003917  push    rdi
0x180003918  push    r14
0x18000391a  sub     rsp, 40h
0x18000391e  mov     rsi, r8
0x180003921  mov     edi, edx
0x180003923  mov     r14, rcx
0x180003926  test    edx, edx
0x180003928  jnz     short loc_180003939
0x18000392a  cmp     cs:dword_18000F090, edx
0x180003930  jg      short loc_180003939
0x180003932  xor     eax, eax
0x180003934  jmp     loc_180003A1D
0x180003939  lea     eax, [rdx-1]
0x18000393c  cmp     eax, 1
0x18000393f  ja      short loc_180003980
0x180003941  mov     rax, cs:_pRawDllMain
0x180003948  test    rax, rax
0x18000394b  jnz     short loc_180003952
0x18000394d  lea     ebx, [rax+1]
0x180003950  jmp     short loc_180003959
0x180003952  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003957  mov     ebx, eax
0x180003959  mov     [rsp+58h+var_28], ebx
0x18000395d  test    ebx, ebx
0x18000395f  jz      loc_180003A13
0x180003965  mov     r8, rsi
0x180003968  mov     edx, edi
0x18000396a  mov     rcx, r14
0x18000396d  call    dllmain_crt_dispatch
0x180003972  mov     ebx, eax
0x180003974  mov     [rsp+58h+var_28], eax
0x180003978  test    eax, eax
0x18000397a  jz      loc_180003A13
0x180003980  mov     r8, rsi; lpvReserved
0x180003983  mov     edx, edi; fdwReason
0x180003985  mov     rcx, r14; hinstDLL
0x180003988  call    DllMain
0x18000398d  mov     ebx, eax
0x18000398f  mov     [rsp+58h+var_28], eax
0x180003993  cmp     edi, 1
0x180003996  jnz     short loc_1800039CF
0x180003998  test    eax, eax
0x18000399a  jnz     short loc_1800039CF
0x18000399c  mov     r8, rsi; lpvReserved
0x18000399f  xor     edx, edx; fdwReason
0x1800039a1  mov     rcx, r14; hinstDLL
0x1800039a4  call    DllMain
0x1800039a9  mov     r8, rsi
0x1800039ac  xor     edx, edx
0x1800039ae  mov     rcx, r14
0x1800039b1  call    dllmain_crt_dispatch
0x1800039b6  mov     rax, cs:_pRawDllMain
0x1800039bd  test    rax, rax
0x1800039c0  jz      short loc_1800039CF
0x1800039c2  mov     r8, rsi
0x1800039c5  xor     edx, edx
0x1800039c7  mov     rcx, r14
0x1800039ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800039cf  test    edi, edi
0x1800039d1  jz      short loc_1800039D8
0x1800039d3  cmp     edi, 3
0x1800039d6  jnz     short loc_180003A13
0x1800039d8  mov     r8, rsi
0x1800039db  mov     edx, edi
0x1800039dd  mov     rcx, r14
0x1800039e0  call    dllmain_crt_dispatch
0x1800039e5  mov     ebx, eax
0x1800039e7  mov     [rsp+58h+var_28], eax
0x1800039eb  test    eax, eax
0x1800039ed  jz      short loc_180003A13
0x1800039ef  mov     rax, cs:_pRawDllMain
0x1800039f6  test    rax, rax
0x1800039f9  jnz     short loc_180003A00
0x1800039fb  lea     ebx, [rax+1]
0x1800039fe  jmp     short loc_180003A0F
0x180003a00  mov     r8, rsi
0x180003a03  mov     edx, edi
0x180003a05  mov     rcx, r14
0x180003a08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a0d  mov     ebx, eax
0x180003a0f  mov     [rsp+58h+var_28], ebx
0x180003a13  jmp     short loc_180003A1B
0x180003a15  xor     ebx, ebx
0x180003a17  mov     [rsp+58h+var_28], ebx
0x180003a1b  mov     eax, ebx
0x180003a1d  mov     rbx, [rsp+58h+arg_18]
0x180003a22  add     rsp, 40h
0x180003a26  pop     r14
0x180003a28  pop     rdi
0x180003a29  pop     rsi
0x180003a2a  retn
0x1800079b2  push    rbp
0x1800079b4  sub     rsp, 30h
0x1800079b8  mov     rbp, rdx
0x1800079bb  mov     rax, [rcx]
0x1800079be  mov     edx, [rax]
0x1800079c0  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x1800079c5  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x1800079c9  lea     r9, dllmain_crt_dispatch; int
0x1800079d0  mov     r8, [rbp+70h]; int
0x1800079d4  mov     edx, [rbp+68h]; int
0x1800079d7  mov     rcx, [rbp+60h]; int
0x1800079db  call    __scrt_dllmain_exception_filter
0x1800079e0  nop
0x1800079e1  add     rsp, 30h
0x1800079e5  pop     rbp
0x1800079e6  retn
```
