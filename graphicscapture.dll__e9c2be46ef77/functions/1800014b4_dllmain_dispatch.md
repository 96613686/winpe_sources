# dllmain_dispatch

- ea: `0x1800014b4`
- end: `0x1800015db`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x1800015f0`

## callees

- `0x1800012d0`
- `0x1800014b4`
- `0x180001844`
- `0x18000257c`
- `0x180028010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_180035610 <= 0 )
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
0x1800014b4  mov     rax, rsp
0x1800014b7  mov     [rax+20h], rbx
0x1800014bb  mov     [rax+18h], r8
0x1800014bf  mov     [rax+10h], edx
0x1800014c2  mov     [rax+8], rcx
0x1800014c6  push    rsi
0x1800014c7  push    rdi
0x1800014c8  push    r14
0x1800014ca  sub     rsp, 40h
0x1800014ce  mov     rsi, r8
0x1800014d1  mov     edi, edx
0x1800014d3  mov     r14, rcx
0x1800014d6  test    edx, edx
0x1800014d8  jnz     short loc_1800014E9
0x1800014da  cmp     cs:dword_180035610, edx
0x1800014e0  jg      short loc_1800014E9
0x1800014e2  xor     eax, eax
0x1800014e4  jmp     loc_1800015CD
0x1800014e9  lea     eax, [rdx-1]
0x1800014ec  cmp     eax, 1
0x1800014ef  ja      short loc_180001530
0x1800014f1  mov     rax, cs:_pRawDllMain
0x1800014f8  test    rax, rax
0x1800014fb  jnz     short loc_180001502
0x1800014fd  lea     ebx, [rax+1]
0x180001500  jmp     short loc_180001509
0x180001502  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001507  mov     ebx, eax
0x180001509  mov     [rsp+58h+var_28], ebx
0x18000150d  test    ebx, ebx
0x18000150f  jz      loc_1800015C3
0x180001515  mov     r8, rsi
0x180001518  mov     edx, edi
0x18000151a  mov     rcx, r14
0x18000151d  call    dllmain_crt_dispatch
0x180001522  mov     ebx, eax
0x180001524  mov     [rsp+58h+var_28], eax
0x180001528  test    eax, eax
0x18000152a  jz      loc_1800015C3
0x180001530  mov     r8, rsi; lpvReserved
0x180001533  mov     edx, edi; fdwReason
0x180001535  mov     rcx, r14; hinstDLL
0x180001538  call    DllMain
0x18000153d  mov     ebx, eax
0x18000153f  mov     [rsp+58h+var_28], eax
0x180001543  cmp     edi, 1
0x180001546  jnz     short loc_18000157F
0x180001548  test    eax, eax
0x18000154a  jnz     short loc_18000157F
0x18000154c  mov     r8, rsi; lpvReserved
0x18000154f  xor     edx, edx; fdwReason
0x180001551  mov     rcx, r14; hinstDLL
0x180001554  call    DllMain
0x180001559  mov     r8, rsi
0x18000155c  xor     edx, edx
0x18000155e  mov     rcx, r14
0x180001561  call    dllmain_crt_dispatch
0x180001566  mov     rax, cs:_pRawDllMain
0x18000156d  test    rax, rax
0x180001570  jz      short loc_18000157F
0x180001572  mov     r8, rsi
0x180001575  xor     edx, edx
0x180001577  mov     rcx, r14
0x18000157a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000157f  test    edi, edi
0x180001581  jz      short loc_180001588
0x180001583  cmp     edi, 3
0x180001586  jnz     short loc_1800015C3
0x180001588  mov     r8, rsi
0x18000158b  mov     edx, edi
0x18000158d  mov     rcx, r14
0x180001590  call    dllmain_crt_dispatch
0x180001595  mov     ebx, eax
0x180001597  mov     [rsp+58h+var_28], eax
0x18000159b  test    eax, eax
0x18000159d  jz      short loc_1800015C3
0x18000159f  mov     rax, cs:_pRawDllMain
0x1800015a6  test    rax, rax
0x1800015a9  jnz     short loc_1800015B0
0x1800015ab  lea     ebx, [rax+1]
0x1800015ae  jmp     short loc_1800015BF
0x1800015b0  mov     r8, rsi
0x1800015b3  mov     edx, edi
0x1800015b5  mov     rcx, r14
0x1800015b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800015bd  mov     ebx, eax
0x1800015bf  mov     [rsp+58h+var_28], ebx
0x1800015c3  jmp     short loc_1800015CB
0x1800015c5  xor     ebx, ebx
0x1800015c7  mov     [rsp+58h+var_28], ebx
0x1800015cb  mov     eax, ebx
0x1800015cd  mov     rbx, [rsp+58h+arg_18]
0x1800015d2  add     rsp, 40h
0x1800015d6  pop     r14
0x1800015d8  pop     rdi
0x1800015d9  pop     rsi
0x1800015da  retn
0x18002543c  push    rbp
0x18002543e  sub     rsp, 30h
0x180025442  mov     rbp, rdx
0x180025445  mov     rax, [rcx]
0x180025448  mov     edx, [rax]
0x18002544a  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x18002544f  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x180025453  lea     r9, dllmain_crt_dispatch; int
0x18002545a  mov     r8, [rbp+70h]; int
0x18002545e  mov     edx, [rbp+68h]; int
0x180025461  mov     rcx, [rbp+60h]; int
0x180025465  call    __scrt_dllmain_exception_filter
0x18002546a  nop
0x18002546b  add     rsp, 30h
0x18002546f  pop     rbp
0x180025470  retn
```
