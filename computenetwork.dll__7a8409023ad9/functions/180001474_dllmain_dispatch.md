# dllmain_dispatch

- ea: `0x180001474`
- end: `0x18000159b`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x1800015b0`

## callees

- `0x180001290`
- `0x180001474`
- `0x1800016fc`
- `0x180001b0c`
- `0x18000f010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_180018270 <= 0 )
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
0x180001474  mov     rax, rsp
0x180001477  mov     [rax+20h], rbx
0x18000147b  mov     [rax+18h], r8
0x18000147f  mov     [rax+10h], edx
0x180001482  mov     [rax+8], rcx
0x180001486  push    rsi
0x180001487  push    rdi
0x180001488  push    r14
0x18000148a  sub     rsp, 40h
0x18000148e  mov     rsi, r8
0x180001491  mov     edi, edx
0x180001493  mov     r14, rcx
0x180001496  test    edx, edx
0x180001498  jnz     short loc_1800014A9
0x18000149a  cmp     cs:dword_180018270, edx
0x1800014a0  jg      short loc_1800014A9
0x1800014a2  xor     eax, eax
0x1800014a4  jmp     loc_18000158D
0x1800014a9  lea     eax, [rdx-1]
0x1800014ac  cmp     eax, 1
0x1800014af  ja      short loc_1800014F0
0x1800014b1  mov     rax, cs:_pRawDllMain
0x1800014b8  test    rax, rax
0x1800014bb  jnz     short loc_1800014C2
0x1800014bd  lea     ebx, [rax+1]
0x1800014c0  jmp     short loc_1800014C9
0x1800014c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800014c7  mov     ebx, eax
0x1800014c9  mov     [rsp+58h+var_28], ebx
0x1800014cd  test    ebx, ebx
0x1800014cf  jz      loc_180001583
0x1800014d5  mov     r8, rsi
0x1800014d8  mov     edx, edi
0x1800014da  mov     rcx, r14
0x1800014dd  call    dllmain_crt_dispatch
0x1800014e2  mov     ebx, eax
0x1800014e4  mov     [rsp+58h+var_28], eax
0x1800014e8  test    eax, eax
0x1800014ea  jz      loc_180001583
0x1800014f0  mov     r8, rsi; lpvReserved
0x1800014f3  mov     edx, edi; fdwReason
0x1800014f5  mov     rcx, r14; hinstDLL
0x1800014f8  call    DllMain
0x1800014fd  mov     ebx, eax
0x1800014ff  mov     [rsp+58h+var_28], eax
0x180001503  cmp     edi, 1
0x180001506  jnz     short loc_18000153F
0x180001508  test    eax, eax
0x18000150a  jnz     short loc_18000153F
0x18000150c  mov     r8, rsi; lpvReserved
0x18000150f  xor     edx, edx; fdwReason
0x180001511  mov     rcx, r14; hinstDLL
0x180001514  call    DllMain
0x180001519  mov     r8, rsi
0x18000151c  xor     edx, edx
0x18000151e  mov     rcx, r14
0x180001521  call    dllmain_crt_dispatch
0x180001526  mov     rax, cs:_pRawDllMain
0x18000152d  test    rax, rax
0x180001530  jz      short loc_18000153F
0x180001532  mov     r8, rsi
0x180001535  xor     edx, edx
0x180001537  mov     rcx, r14
0x18000153a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000153f  test    edi, edi
0x180001541  jz      short loc_180001548
0x180001543  cmp     edi, 3
0x180001546  jnz     short loc_180001583
0x180001548  mov     r8, rsi
0x18000154b  mov     edx, edi
0x18000154d  mov     rcx, r14
0x180001550  call    dllmain_crt_dispatch
0x180001555  mov     ebx, eax
0x180001557  mov     [rsp+58h+var_28], eax
0x18000155b  test    eax, eax
0x18000155d  jz      short loc_180001583
0x18000155f  mov     rax, cs:_pRawDllMain
0x180001566  test    rax, rax
0x180001569  jnz     short loc_180001570
0x18000156b  lea     ebx, [rax+1]
0x18000156e  jmp     short loc_18000157F
0x180001570  mov     r8, rsi
0x180001573  mov     edx, edi
0x180001575  mov     rcx, r14
0x180001578  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000157d  mov     ebx, eax
0x18000157f  mov     [rsp+58h+var_28], ebx
0x180001583  jmp     short loc_18000158B
0x180001585  xor     ebx, ebx
0x180001587  mov     [rsp+58h+var_28], ebx
0x18000158b  mov     eax, ebx
0x18000158d  mov     rbx, [rsp+58h+arg_18]
0x180001592  add     rsp, 40h
0x180001596  pop     r14
0x180001598  pop     rdi
0x180001599  pop     rsi
0x18000159a  retn
0x18000cfac  push    rbp
0x18000cfae  sub     rsp, 30h
0x18000cfb2  mov     rbp, rdx
0x18000cfb5  mov     rax, [rcx]
0x18000cfb8  mov     edx, [rax]
0x18000cfba  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x18000cfbf  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x18000cfc3  lea     r9, dllmain_crt_dispatch; int
0x18000cfca  mov     r8, [rbp+70h]; int
0x18000cfce  mov     edx, [rbp+68h]; int
0x18000cfd1  mov     rcx, [rbp+60h]; int
0x18000cfd5  call    __scrt_dllmain_exception_filter
0x18000cfda  nop
0x18000cfdb  add     rsp, 30h
0x18000cfdf  pop     rbp
0x18000cfe0  retn
```
