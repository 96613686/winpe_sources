# dllmain_dispatch

- ea: `0x180002904`
- end: `0x180002a2b`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180002a40`

## callees

- `0x180002720`
- `0x180002904`
- `0x180002bc4`
- `0x18000d9f4`
- `0x180038010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_18004E090 <= 0 )
    return 0;
  if ( fdwReason - 1 > 1
    || (pRawDllMain ? (v7 = pRawDllMain()) : (v7 = 1),
        v7 && (v7 = dllmain_crt_dispatch(hinstDLL, fdwReason, lpvReserved)) != 0) )
  {
    v8 = DllMain(hinstDLL, fdwReason, lpvReserved);
    v7 = v8;
    if ( fdwReason == 1 && !v8 )
    {
      DllMain(hinstDLL, 0, lpvReserved);
      dllmain_crt_dispatch(hinstDLL, 0, lpvReserved);
      if ( pRawDllMain )
        pRawDllMain();
    }
    if ( !fdwReason || fdwReason == 3 )
    {
      v7 = dllmain_crt_dispatch(hinstDLL, fdwReason, lpvReserved);
      if ( v7 )
      {
        if ( pRawDllMain )
          return (unsigned int)pRawDllMain();
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
0x180002904  mov     rax, rsp
0x180002907  mov     [rax+20h], rbx
0x18000290b  mov     [rax+18h], r8
0x18000290f  mov     [rax+10h], edx
0x180002912  mov     [rax+8], rcx
0x180002916  push    rsi
0x180002917  push    rdi
0x180002918  push    r14
0x18000291a  sub     rsp, 40h
0x18000291e  mov     rsi, r8
0x180002921  mov     edi, edx
0x180002923  mov     r14, rcx
0x180002926  test    edx, edx
0x180002928  jnz     short loc_180002939
0x18000292a  cmp     cs:dword_18004E090, edx
0x180002930  jg      short loc_180002939
0x180002932  xor     eax, eax
0x180002934  jmp     loc_180002A1D
0x180002939  lea     eax, [rdx-1]
0x18000293c  cmp     eax, 1
0x18000293f  ja      short loc_180002980
0x180002941  mov     rax, cs:_pRawDllMain
0x180002948  test    rax, rax
0x18000294b  jnz     short loc_180002952
0x18000294d  lea     ebx, [rax+1]
0x180002950  jmp     short loc_180002959
0x180002952  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002957  mov     ebx, eax
0x180002959  mov     [rsp+58h+var_28], ebx
0x18000295d  test    ebx, ebx
0x18000295f  jz      loc_180002A13
0x180002965  mov     r8, rsi
0x180002968  mov     edx, edi
0x18000296a  mov     rcx, r14
0x18000296d  call    dllmain_crt_dispatch
0x180002972  mov     ebx, eax
0x180002974  mov     [rsp+58h+var_28], eax
0x180002978  test    eax, eax
0x18000297a  jz      loc_180002A13
0x180002980  mov     r8, rsi; lpvReserved
0x180002983  mov     edx, edi; fdwReason
0x180002985  mov     rcx, r14; hinstDLL
0x180002988  call    DllMain
0x18000298d  mov     ebx, eax
0x18000298f  mov     [rsp+58h+var_28], eax
0x180002993  cmp     edi, 1
0x180002996  jnz     short loc_1800029CF
0x180002998  test    eax, eax
0x18000299a  jnz     short loc_1800029CF
0x18000299c  mov     r8, rsi; lpvReserved
0x18000299f  xor     edx, edx; fdwReason
0x1800029a1  mov     rcx, r14; hinstDLL
0x1800029a4  call    DllMain
0x1800029a9  mov     r8, rsi
0x1800029ac  xor     edx, edx
0x1800029ae  mov     rcx, r14
0x1800029b1  call    dllmain_crt_dispatch
0x1800029b6  mov     rax, cs:_pRawDllMain
0x1800029bd  test    rax, rax
0x1800029c0  jz      short loc_1800029CF
0x1800029c2  mov     r8, rsi
0x1800029c5  xor     edx, edx
0x1800029c7  mov     rcx, r14
0x1800029ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800029cf  test    edi, edi
0x1800029d1  jz      short loc_1800029D8
0x1800029d3  cmp     edi, 3
0x1800029d6  jnz     short loc_180002A13
0x1800029d8  mov     r8, rsi
0x1800029db  mov     edx, edi
0x1800029dd  mov     rcx, r14
0x1800029e0  call    dllmain_crt_dispatch
0x1800029e5  mov     ebx, eax
0x1800029e7  mov     [rsp+58h+var_28], eax
0x1800029eb  test    eax, eax
0x1800029ed  jz      short loc_180002A13
0x1800029ef  mov     rax, cs:_pRawDllMain
0x1800029f6  test    rax, rax
0x1800029f9  jnz     short loc_180002A00
0x1800029fb  lea     ebx, [rax+1]
0x1800029fe  jmp     short loc_180002A0F
0x180002a00  mov     r8, rsi
0x180002a03  mov     edx, edi
0x180002a05  mov     rcx, r14
0x180002a08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002a0d  mov     ebx, eax
0x180002a0f  mov     [rsp+58h+var_28], ebx
0x180002a13  jmp     short loc_180002A1B
0x180002a15  xor     ebx, ebx
0x180002a17  mov     [rsp+58h+var_28], ebx
0x180002a1b  mov     eax, ebx
0x180002a1d  mov     rbx, [rsp+58h+arg_18]
0x180002a22  add     rsp, 40h
0x180002a26  pop     r14
0x180002a28  pop     rdi
0x180002a29  pop     rsi
0x180002a2a  retn
0x180033e4c  push    rbp
0x180033e4e  sub     rsp, 30h
0x180033e52  mov     rbp, rdx
0x180033e55  mov     rax, [rcx]
0x180033e58  mov     edx, [rax]
0x180033e5a  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x180033e5f  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x180033e63  lea     r9, dllmain_crt_dispatch; int
0x180033e6a  mov     r8, [rbp+70h]; int
0x180033e6e  mov     edx, [rbp+68h]; int
0x180033e71  mov     rcx, [rbp+60h]; int
0x180033e75  call    __scrt_dllmain_exception_filter
0x180033e7a  nop
0x180033e7b  add     rsp, 30h
0x180033e7f  pop     rbp
0x180033e80  retn
```
