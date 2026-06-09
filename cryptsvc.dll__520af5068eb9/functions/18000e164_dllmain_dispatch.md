# dllmain_dispatch

- ea: `0x18000e164`
- end: `0x18000e28b`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x18000e2a0`

## callees

- `0x18000df80`
- `0x18000e164`
- `0x18000e4f4`
- `0x18000f60c`
- `0x180018010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_180020170 <= 0 )
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
0x18000e164  mov     rax, rsp
0x18000e167  mov     [rax+20h], rbx
0x18000e16b  mov     [rax+18h], r8
0x18000e16f  mov     [rax+10h], edx
0x18000e172  mov     [rax+8], rcx
0x18000e176  push    rsi
0x18000e177  push    rdi
0x18000e178  push    r14
0x18000e17a  sub     rsp, 40h
0x18000e17e  mov     rsi, r8
0x18000e181  mov     edi, edx
0x18000e183  mov     r14, rcx
0x18000e186  test    edx, edx
0x18000e188  jnz     short loc_18000E199
0x18000e18a  cmp     cs:dword_180020170, edx
0x18000e190  jg      short loc_18000E199
0x18000e192  xor     eax, eax
0x18000e194  jmp     loc_18000E27D
0x18000e199  lea     eax, [rdx-1]
0x18000e19c  cmp     eax, 1
0x18000e19f  ja      short loc_18000E1E0
0x18000e1a1  mov     rax, cs:_pRawDllMain
0x18000e1a8  test    rax, rax
0x18000e1ab  jnz     short loc_18000E1B2
0x18000e1ad  lea     ebx, [rax+1]
0x18000e1b0  jmp     short loc_18000E1B9
0x18000e1b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e1b7  mov     ebx, eax
0x18000e1b9  mov     [rsp+58h+var_28], ebx
0x18000e1bd  test    ebx, ebx
0x18000e1bf  jz      loc_18000E273
0x18000e1c5  mov     r8, rsi
0x18000e1c8  mov     edx, edi
0x18000e1ca  mov     rcx, r14
0x18000e1cd  call    dllmain_crt_dispatch
0x18000e1d2  mov     ebx, eax
0x18000e1d4  mov     [rsp+58h+var_28], eax
0x18000e1d8  test    eax, eax
0x18000e1da  jz      loc_18000E273
0x18000e1e0  mov     r8, rsi; lpvReserved
0x18000e1e3  mov     edx, edi; fdwReason
0x18000e1e5  mov     rcx, r14; hinstDLL
0x18000e1e8  call    DllMain
0x18000e1ed  mov     ebx, eax
0x18000e1ef  mov     [rsp+58h+var_28], eax
0x18000e1f3  cmp     edi, 1
0x18000e1f6  jnz     short loc_18000E22F
0x18000e1f8  test    eax, eax
0x18000e1fa  jnz     short loc_18000E22F
0x18000e1fc  mov     r8, rsi; lpvReserved
0x18000e1ff  xor     edx, edx; fdwReason
0x18000e201  mov     rcx, r14; hinstDLL
0x18000e204  call    DllMain
0x18000e209  mov     r8, rsi
0x18000e20c  xor     edx, edx
0x18000e20e  mov     rcx, r14
0x18000e211  call    dllmain_crt_dispatch
0x18000e216  mov     rax, cs:_pRawDllMain
0x18000e21d  test    rax, rax
0x18000e220  jz      short loc_18000E22F
0x18000e222  mov     r8, rsi
0x18000e225  xor     edx, edx
0x18000e227  mov     rcx, r14
0x18000e22a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e22f  test    edi, edi
0x18000e231  jz      short loc_18000E238
0x18000e233  cmp     edi, 3
0x18000e236  jnz     short loc_18000E273
0x18000e238  mov     r8, rsi
0x18000e23b  mov     edx, edi
0x18000e23d  mov     rcx, r14
0x18000e240  call    dllmain_crt_dispatch
0x18000e245  mov     ebx, eax
0x18000e247  mov     [rsp+58h+var_28], eax
0x18000e24b  test    eax, eax
0x18000e24d  jz      short loc_18000E273
0x18000e24f  mov     rax, cs:_pRawDllMain
0x18000e256  test    rax, rax
0x18000e259  jnz     short loc_18000E260
0x18000e25b  lea     ebx, [rax+1]
0x18000e25e  jmp     short loc_18000E26F
0x18000e260  mov     r8, rsi
0x18000e263  mov     edx, edi
0x18000e265  mov     rcx, r14
0x18000e268  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e26d  mov     ebx, eax
0x18000e26f  mov     [rsp+58h+var_28], ebx
0x18000e273  jmp     short loc_18000E27B
0x18000e275  xor     ebx, ebx
0x18000e277  mov     [rsp+58h+var_28], ebx
0x18000e27b  mov     eax, ebx
0x18000e27d  mov     rbx, [rsp+58h+arg_18]
0x18000e282  add     rsp, 40h
0x18000e286  pop     r14
0x18000e288  pop     rdi
0x18000e289  pop     rsi
0x18000e28a  retn
0x1800175cc  push    rbp
0x1800175ce  sub     rsp, 30h
0x1800175d2  mov     rbp, rdx
0x1800175d5  mov     rax, [rcx]
0x1800175d8  mov     edx, [rax]
0x1800175da  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x1800175df  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x1800175e3  lea     r9, dllmain_crt_dispatch; int
0x1800175ea  mov     r8, [rbp+70h]; int
0x1800175ee  mov     edx, [rbp+68h]; int
0x1800175f1  mov     rcx, [rbp+60h]; int
0x1800175f5  call    __scrt_dllmain_exception_filter
0x1800175fa  nop
0x1800175fb  add     rsp, 30h
0x1800175ff  pop     rbp
0x180017600  retn
```
