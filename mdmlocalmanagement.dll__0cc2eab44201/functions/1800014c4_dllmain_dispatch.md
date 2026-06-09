# dllmain_dispatch

- ea: `0x1800014c4`
- end: `0x1800015eb`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180001600`

## callees

- `0x1800012e0`
- `0x1800014c4`
- `0x18000175c`
- `0x1800059dc`
- `0x180007010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_18000B290 <= 0 )
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
0x1800014c4  mov     rax, rsp
0x1800014c7  mov     [rax+20h], rbx
0x1800014cb  mov     [rax+18h], r8
0x1800014cf  mov     [rax+10h], edx
0x1800014d2  mov     [rax+8], rcx
0x1800014d6  push    rsi
0x1800014d7  push    rdi
0x1800014d8  push    r14
0x1800014da  sub     rsp, 40h
0x1800014de  mov     rsi, r8
0x1800014e1  mov     edi, edx
0x1800014e3  mov     r14, rcx
0x1800014e6  test    edx, edx
0x1800014e8  jnz     short loc_1800014F9
0x1800014ea  cmp     cs:dword_18000B290, edx
0x1800014f0  jg      short loc_1800014F9
0x1800014f2  xor     eax, eax
0x1800014f4  jmp     loc_1800015DD
0x1800014f9  lea     eax, [rdx-1]
0x1800014fc  cmp     eax, 1
0x1800014ff  ja      short loc_180001540
0x180001501  mov     rax, cs:_pRawDllMain
0x180001508  test    rax, rax
0x18000150b  jnz     short loc_180001512
0x18000150d  lea     ebx, [rax+1]
0x180001510  jmp     short loc_180001519
0x180001512  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001517  mov     ebx, eax
0x180001519  mov     [rsp+58h+var_28], ebx
0x18000151d  test    ebx, ebx
0x18000151f  jz      loc_1800015D3
0x180001525  mov     r8, rsi
0x180001528  mov     edx, edi
0x18000152a  mov     rcx, r14
0x18000152d  call    dllmain_crt_dispatch
0x180001532  mov     ebx, eax
0x180001534  mov     [rsp+58h+var_28], eax
0x180001538  test    eax, eax
0x18000153a  jz      loc_1800015D3
0x180001540  mov     r8, rsi; lpvReserved
0x180001543  mov     edx, edi; fdwReason
0x180001545  mov     rcx, r14; hinstDLL
0x180001548  call    DllMain
0x18000154d  mov     ebx, eax
0x18000154f  mov     [rsp+58h+var_28], eax
0x180001553  cmp     edi, 1
0x180001556  jnz     short loc_18000158F
0x180001558  test    eax, eax
0x18000155a  jnz     short loc_18000158F
0x18000155c  mov     r8, rsi; lpvReserved
0x18000155f  xor     edx, edx; fdwReason
0x180001561  mov     rcx, r14; hinstDLL
0x180001564  call    DllMain
0x180001569  mov     r8, rsi
0x18000156c  xor     edx, edx
0x18000156e  mov     rcx, r14
0x180001571  call    dllmain_crt_dispatch
0x180001576  mov     rax, cs:_pRawDllMain
0x18000157d  test    rax, rax
0x180001580  jz      short loc_18000158F
0x180001582  mov     r8, rsi
0x180001585  xor     edx, edx
0x180001587  mov     rcx, r14
0x18000158a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000158f  test    edi, edi
0x180001591  jz      short loc_180001598
0x180001593  cmp     edi, 3
0x180001596  jnz     short loc_1800015D3
0x180001598  mov     r8, rsi
0x18000159b  mov     edx, edi
0x18000159d  mov     rcx, r14
0x1800015a0  call    dllmain_crt_dispatch
0x1800015a5  mov     ebx, eax
0x1800015a7  mov     [rsp+58h+var_28], eax
0x1800015ab  test    eax, eax
0x1800015ad  jz      short loc_1800015D3
0x1800015af  mov     rax, cs:_pRawDllMain
0x1800015b6  test    rax, rax
0x1800015b9  jnz     short loc_1800015C0
0x1800015bb  lea     ebx, [rax+1]
0x1800015be  jmp     short loc_1800015CF
0x1800015c0  mov     r8, rsi
0x1800015c3  mov     edx, edi
0x1800015c5  mov     rcx, r14
0x1800015c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800015cd  mov     ebx, eax
0x1800015cf  mov     [rsp+58h+var_28], ebx
0x1800015d3  jmp     short loc_1800015DB
0x1800015d5  xor     ebx, ebx
0x1800015d7  mov     [rsp+58h+var_28], ebx
0x1800015db  mov     eax, ebx
0x1800015dd  mov     rbx, [rsp+58h+arg_18]
0x1800015e2  add     rsp, 40h
0x1800015e6  pop     r14
0x1800015e8  pop     rdi
0x1800015e9  pop     rsi
0x1800015ea  retn
0x180006bcc  push    rbp
0x180006bce  sub     rsp, 30h
0x180006bd2  mov     rbp, rdx
0x180006bd5  mov     rax, [rcx]
0x180006bd8  mov     edx, [rax]
0x180006bda  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x180006bdf  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x180006be3  lea     r9, dllmain_crt_dispatch; int
0x180006bea  mov     r8, [rbp+70h]; int
0x180006bee  mov     edx, [rbp+68h]; int
0x180006bf1  mov     rcx, [rbp+60h]; int
0x180006bf5  call    __scrt_dllmain_exception_filter
0x180006bfa  nop
0x180006bfb  add     rsp, 30h
0x180006bff  pop     rbp
0x180006c00  retn
```
