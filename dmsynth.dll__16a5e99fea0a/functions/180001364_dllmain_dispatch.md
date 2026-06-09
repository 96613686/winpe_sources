# dllmain_dispatch

- ea: `0x180001364`
- end: `0x18000148b`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x1800014a0`

## callees

- `0x180001180`
- `0x180001364`
- `0x180001720`
- `0x18000ed30`
- `0x180015010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_18001E630 <= 0 )
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
0x180001364  mov     rax, rsp
0x180001367  mov     [rax+20h], rbx
0x18000136b  mov     [rax+18h], r8
0x18000136f  mov     [rax+10h], edx
0x180001372  mov     [rax+8], rcx
0x180001376  push    rsi
0x180001377  push    rdi
0x180001378  push    r14
0x18000137a  sub     rsp, 40h
0x18000137e  mov     rsi, r8
0x180001381  mov     edi, edx
0x180001383  mov     r14, rcx
0x180001386  test    edx, edx
0x180001388  jnz     short loc_180001399
0x18000138a  cmp     cs:dword_18001E630, edx
0x180001390  jg      short loc_180001399
0x180001392  xor     eax, eax
0x180001394  jmp     loc_18000147D
0x180001399  lea     eax, [rdx-1]
0x18000139c  cmp     eax, 1
0x18000139f  ja      short loc_1800013E0
0x1800013a1  mov     rax, cs:_pRawDllMain
0x1800013a8  test    rax, rax
0x1800013ab  jnz     short loc_1800013B2
0x1800013ad  lea     ebx, [rax+1]
0x1800013b0  jmp     short loc_1800013B9
0x1800013b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800013b7  mov     ebx, eax
0x1800013b9  mov     [rsp+58h+var_28], ebx
0x1800013bd  test    ebx, ebx
0x1800013bf  jz      loc_180001473
0x1800013c5  mov     r8, rsi
0x1800013c8  mov     edx, edi
0x1800013ca  mov     rcx, r14
0x1800013cd  call    dllmain_crt_dispatch
0x1800013d2  mov     ebx, eax
0x1800013d4  mov     [rsp+58h+var_28], eax
0x1800013d8  test    eax, eax
0x1800013da  jz      loc_180001473
0x1800013e0  mov     r8, rsi; lpvReserved
0x1800013e3  mov     edx, edi; fdwReason
0x1800013e5  mov     rcx, r14; hinstDLL
0x1800013e8  call    DllMain
0x1800013ed  mov     ebx, eax
0x1800013ef  mov     [rsp+58h+var_28], eax
0x1800013f3  cmp     edi, 1
0x1800013f6  jnz     short loc_18000142F
0x1800013f8  test    eax, eax
0x1800013fa  jnz     short loc_18000142F
0x1800013fc  mov     r8, rsi; lpvReserved
0x1800013ff  xor     edx, edx; fdwReason
0x180001401  mov     rcx, r14; hinstDLL
0x180001404  call    DllMain
0x180001409  mov     r8, rsi
0x18000140c  xor     edx, edx
0x18000140e  mov     rcx, r14
0x180001411  call    dllmain_crt_dispatch
0x180001416  mov     rax, cs:_pRawDllMain
0x18000141d  test    rax, rax
0x180001420  jz      short loc_18000142F
0x180001422  mov     r8, rsi
0x180001425  xor     edx, edx
0x180001427  mov     rcx, r14
0x18000142a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000142f  test    edi, edi
0x180001431  jz      short loc_180001438
0x180001433  cmp     edi, 3
0x180001436  jnz     short loc_180001473
0x180001438  mov     r8, rsi
0x18000143b  mov     edx, edi
0x18000143d  mov     rcx, r14
0x180001440  call    dllmain_crt_dispatch
0x180001445  mov     ebx, eax
0x180001447  mov     [rsp+58h+var_28], eax
0x18000144b  test    eax, eax
0x18000144d  jz      short loc_180001473
0x18000144f  mov     rax, cs:_pRawDllMain
0x180001456  test    rax, rax
0x180001459  jnz     short loc_180001460
0x18000145b  lea     ebx, [rax+1]
0x18000145e  jmp     short loc_18000146F
0x180001460  mov     r8, rsi
0x180001463  mov     edx, edi
0x180001465  mov     rcx, r14
0x180001468  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000146d  mov     ebx, eax
0x18000146f  mov     [rsp+58h+var_28], ebx
0x180001473  jmp     short loc_18000147B
0x180001475  xor     ebx, ebx
0x180001477  mov     [rsp+58h+var_28], ebx
0x18000147b  mov     eax, ebx
0x18000147d  mov     rbx, [rsp+58h+arg_18]
0x180001482  add     rsp, 40h
0x180001486  pop     r14
0x180001488  pop     rdi
0x180001489  pop     rsi
0x18000148a  retn
0x1800149a0  push    rbp
0x1800149a2  sub     rsp, 30h
0x1800149a6  mov     rbp, rdx
0x1800149a9  mov     rax, [rcx]
0x1800149ac  mov     edx, [rax]
0x1800149ae  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x1800149b3  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x1800149b7  lea     r9, dllmain_crt_dispatch; int
0x1800149be  mov     r8, [rbp+70h]; int
0x1800149c2  mov     edx, [rbp+68h]; int
0x1800149c5  mov     rcx, [rbp+60h]; int
0x1800149c9  call    __scrt_dllmain_exception_filter
0x1800149ce  nop
0x1800149cf  add     rsp, 30h
0x1800149d3  pop     rbp
0x1800149d4  retn
```
