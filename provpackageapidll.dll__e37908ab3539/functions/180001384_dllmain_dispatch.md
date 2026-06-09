# dllmain_dispatch

- ea: `0x180001384`
- end: `0x1800014ab`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x1800014c0`

## callees

- `0x1800011a0`
- `0x180001384`
- `0x180001714`
- `0x1800022fc`
- `0x180019010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_1800261F0 <= 0 )
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
0x180001384  mov     rax, rsp
0x180001387  mov     [rax+20h], rbx
0x18000138b  mov     [rax+18h], r8
0x18000138f  mov     [rax+10h], edx
0x180001392  mov     [rax+8], rcx
0x180001396  push    rsi
0x180001397  push    rdi
0x180001398  push    r14
0x18000139a  sub     rsp, 40h
0x18000139e  mov     rsi, r8
0x1800013a1  mov     edi, edx
0x1800013a3  mov     r14, rcx
0x1800013a6  test    edx, edx
0x1800013a8  jnz     short loc_1800013B9
0x1800013aa  cmp     cs:dword_1800261F0, edx
0x1800013b0  jg      short loc_1800013B9
0x1800013b2  xor     eax, eax
0x1800013b4  jmp     loc_18000149D
0x1800013b9  lea     eax, [rdx-1]
0x1800013bc  cmp     eax, 1
0x1800013bf  ja      short loc_180001400
0x1800013c1  mov     rax, cs:_pRawDllMain
0x1800013c8  test    rax, rax
0x1800013cb  jnz     short loc_1800013D2
0x1800013cd  lea     ebx, [rax+1]
0x1800013d0  jmp     short loc_1800013D9
0x1800013d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800013d7  mov     ebx, eax
0x1800013d9  mov     [rsp+58h+var_28], ebx
0x1800013dd  test    ebx, ebx
0x1800013df  jz      loc_180001493
0x1800013e5  mov     r8, rsi
0x1800013e8  mov     edx, edi
0x1800013ea  mov     rcx, r14
0x1800013ed  call    dllmain_crt_dispatch
0x1800013f2  mov     ebx, eax
0x1800013f4  mov     [rsp+58h+var_28], eax
0x1800013f8  test    eax, eax
0x1800013fa  jz      loc_180001493
0x180001400  mov     r8, rsi; lpvReserved
0x180001403  mov     edx, edi; fdwReason
0x180001405  mov     rcx, r14; hinstDLL
0x180001408  call    DllMain
0x18000140d  mov     ebx, eax
0x18000140f  mov     [rsp+58h+var_28], eax
0x180001413  cmp     edi, 1
0x180001416  jnz     short loc_18000144F
0x180001418  test    eax, eax
0x18000141a  jnz     short loc_18000144F
0x18000141c  mov     r8, rsi; lpvReserved
0x18000141f  xor     edx, edx; fdwReason
0x180001421  mov     rcx, r14; hinstDLL
0x180001424  call    DllMain
0x180001429  mov     r8, rsi
0x18000142c  xor     edx, edx
0x18000142e  mov     rcx, r14
0x180001431  call    dllmain_crt_dispatch
0x180001436  mov     rax, cs:_pRawDllMain
0x18000143d  test    rax, rax
0x180001440  jz      short loc_18000144F
0x180001442  mov     r8, rsi
0x180001445  xor     edx, edx
0x180001447  mov     rcx, r14
0x18000144a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000144f  test    edi, edi
0x180001451  jz      short loc_180001458
0x180001453  cmp     edi, 3
0x180001456  jnz     short loc_180001493
0x180001458  mov     r8, rsi
0x18000145b  mov     edx, edi
0x18000145d  mov     rcx, r14
0x180001460  call    dllmain_crt_dispatch
0x180001465  mov     ebx, eax
0x180001467  mov     [rsp+58h+var_28], eax
0x18000146b  test    eax, eax
0x18000146d  jz      short loc_180001493
0x18000146f  mov     rax, cs:_pRawDllMain
0x180001476  test    rax, rax
0x180001479  jnz     short loc_180001480
0x18000147b  lea     ebx, [rax+1]
0x18000147e  jmp     short loc_18000148F
0x180001480  mov     r8, rsi
0x180001483  mov     edx, edi
0x180001485  mov     rcx, r14
0x180001488  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000148d  mov     ebx, eax
0x18000148f  mov     [rsp+58h+var_28], ebx
0x180001493  jmp     short loc_18000149B
0x180001495  xor     ebx, ebx
0x180001497  mov     [rsp+58h+var_28], ebx
0x18000149b  mov     eax, ebx
0x18000149d  mov     rbx, [rsp+58h+arg_18]
0x1800014a2  add     rsp, 40h
0x1800014a6  pop     r14
0x1800014a8  pop     rdi
0x1800014a9  pop     rsi
0x1800014aa  retn
0x18001851c  push    rbp
0x18001851e  sub     rsp, 30h
0x180018522  mov     rbp, rdx
0x180018525  mov     rax, [rcx]
0x180018528  mov     edx, [rax]
0x18001852a  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x18001852f  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x180018533  lea     r9, dllmain_crt_dispatch; int
0x18001853a  mov     r8, [rbp+70h]; int
0x18001853e  mov     edx, [rbp+68h]; int
0x180018541  mov     rcx, [rbp+60h]; int
0x180018545  call    __scrt_dllmain_exception_filter
0x18001854a  nop
0x18001854b  add     rsp, 30h
0x18001854f  pop     rbp
0x180018550  retn
```
