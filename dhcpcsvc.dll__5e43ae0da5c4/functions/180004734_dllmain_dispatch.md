# dllmain_dispatch

- ea: `0x180004734`
- end: `0x18000485b`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180004870`

## callees

- `0x180002f40`
- `0x180004550`
- `0x180004734`
- `0x180004ac4`
- `0x180014010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_18001E0D0 <= 0 )
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
0x180004734  mov     rax, rsp
0x180004737  mov     [rax+20h], rbx
0x18000473b  mov     [rax+18h], r8
0x18000473f  mov     [rax+10h], edx
0x180004742  mov     [rax+8], rcx
0x180004746  push    rsi
0x180004747  push    rdi
0x180004748  push    r14
0x18000474a  sub     rsp, 40h
0x18000474e  mov     rsi, r8
0x180004751  mov     edi, edx
0x180004753  mov     r14, rcx
0x180004756  test    edx, edx
0x180004758  jnz     short loc_180004769
0x18000475a  cmp     cs:dword_18001E0D0, edx
0x180004760  jg      short loc_180004769
0x180004762  xor     eax, eax
0x180004764  jmp     loc_18000484D
0x180004769  lea     eax, [rdx-1]
0x18000476c  cmp     eax, 1
0x18000476f  ja      short loc_1800047B0
0x180004771  mov     rax, cs:_pRawDllMain
0x180004778  test    rax, rax
0x18000477b  jnz     short loc_180004782
0x18000477d  lea     ebx, [rax+1]
0x180004780  jmp     short loc_180004789
0x180004782  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004787  mov     ebx, eax
0x180004789  mov     [rsp+58h+var_28], ebx
0x18000478d  test    ebx, ebx
0x18000478f  jz      loc_180004843
0x180004795  mov     r8, rsi
0x180004798  mov     edx, edi
0x18000479a  mov     rcx, r14
0x18000479d  call    dllmain_crt_dispatch
0x1800047a2  mov     ebx, eax
0x1800047a4  mov     [rsp+58h+var_28], eax
0x1800047a8  test    eax, eax
0x1800047aa  jz      loc_180004843
0x1800047b0  mov     r8, rsi; lpvReserved
0x1800047b3  mov     edx, edi; fdwReason
0x1800047b5  mov     rcx, r14; hinstDLL
0x1800047b8  call    DllMain
0x1800047bd  mov     ebx, eax
0x1800047bf  mov     [rsp+58h+var_28], eax
0x1800047c3  cmp     edi, 1
0x1800047c6  jnz     short loc_1800047FF
0x1800047c8  test    eax, eax
0x1800047ca  jnz     short loc_1800047FF
0x1800047cc  mov     r8, rsi; lpvReserved
0x1800047cf  xor     edx, edx; fdwReason
0x1800047d1  mov     rcx, r14; hinstDLL
0x1800047d4  call    DllMain
0x1800047d9  mov     r8, rsi
0x1800047dc  xor     edx, edx
0x1800047de  mov     rcx, r14
0x1800047e1  call    dllmain_crt_dispatch
0x1800047e6  mov     rax, cs:_pRawDllMain
0x1800047ed  test    rax, rax
0x1800047f0  jz      short loc_1800047FF
0x1800047f2  mov     r8, rsi
0x1800047f5  xor     edx, edx
0x1800047f7  mov     rcx, r14
0x1800047fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800047ff  test    edi, edi
0x180004801  jz      short loc_180004808
0x180004803  cmp     edi, 3
0x180004806  jnz     short loc_180004843
0x180004808  mov     r8, rsi
0x18000480b  mov     edx, edi
0x18000480d  mov     rcx, r14
0x180004810  call    dllmain_crt_dispatch
0x180004815  mov     ebx, eax
0x180004817  mov     [rsp+58h+var_28], eax
0x18000481b  test    eax, eax
0x18000481d  jz      short loc_180004843
0x18000481f  mov     rax, cs:_pRawDllMain
0x180004826  test    rax, rax
0x180004829  jnz     short loc_180004830
0x18000482b  lea     ebx, [rax+1]
0x18000482e  jmp     short loc_18000483F
0x180004830  mov     r8, rsi
0x180004833  mov     edx, edi
0x180004835  mov     rcx, r14
0x180004838  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000483d  mov     ebx, eax
0x18000483f  mov     [rsp+58h+var_28], ebx
0x180004843  jmp     short loc_18000484B
0x180004845  xor     ebx, ebx
0x180004847  mov     [rsp+58h+var_28], ebx
0x18000484b  mov     eax, ebx
0x18000484d  mov     rbx, [rsp+58h+arg_18]
0x180004852  add     rsp, 40h
0x180004856  pop     r14
0x180004858  pop     rdi
0x180004859  pop     rsi
0x18000485a  retn
0x180010c92  push    rbp
0x180010c94  sub     rsp, 30h
0x180010c98  mov     rbp, rdx
0x180010c9b  mov     rax, [rcx]
0x180010c9e  mov     edx, [rax]
0x180010ca0  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x180010ca5  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x180010ca9  lea     r9, dllmain_crt_dispatch; int
0x180010cb0  mov     r8, [rbp+70h]; int
0x180010cb4  mov     edx, [rbp+68h]; int
0x180010cb7  mov     rcx, [rbp+60h]; int
0x180010cbb  call    __scrt_dllmain_exception_filter
0x180010cc0  nop
0x180010cc1  add     rsp, 30h
0x180010cc5  pop     rbp
0x180010cc6  retn
```
