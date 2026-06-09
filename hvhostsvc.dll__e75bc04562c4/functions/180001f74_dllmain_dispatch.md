# dllmain_dispatch

- ea: `0x180001f74`
- end: `0x18000209b`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x1800020b0`

## callees

- `0x180001d90`
- `0x180001f74`
- `0x1800021fc`
- `0x1800025c8`
- `0x18000a010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_1800125B0 <= 0 )
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
0x180001f74  mov     rax, rsp
0x180001f77  mov     [rax+20h], rbx
0x180001f7b  mov     [rax+18h], r8
0x180001f7f  mov     [rax+10h], edx
0x180001f82  mov     [rax+8], rcx
0x180001f86  push    rsi
0x180001f87  push    rdi
0x180001f88  push    r14
0x180001f8a  sub     rsp, 40h
0x180001f8e  mov     rsi, r8
0x180001f91  mov     edi, edx
0x180001f93  mov     r14, rcx
0x180001f96  test    edx, edx
0x180001f98  jnz     short loc_180001FA9
0x180001f9a  cmp     cs:dword_1800125B0, edx
0x180001fa0  jg      short loc_180001FA9
0x180001fa2  xor     eax, eax
0x180001fa4  jmp     loc_18000208D
0x180001fa9  lea     eax, [rdx-1]
0x180001fac  cmp     eax, 1
0x180001faf  ja      short loc_180001FF0
0x180001fb1  mov     rax, cs:_pRawDllMain
0x180001fb8  test    rax, rax
0x180001fbb  jnz     short loc_180001FC2
0x180001fbd  lea     ebx, [rax+1]
0x180001fc0  jmp     short loc_180001FC9
0x180001fc2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001fc7  mov     ebx, eax
0x180001fc9  mov     [rsp+58h+var_28], ebx
0x180001fcd  test    ebx, ebx
0x180001fcf  jz      loc_180002083
0x180001fd5  mov     r8, rsi
0x180001fd8  mov     edx, edi
0x180001fda  mov     rcx, r14
0x180001fdd  call    dllmain_crt_dispatch
0x180001fe2  mov     ebx, eax
0x180001fe4  mov     [rsp+58h+var_28], eax
0x180001fe8  test    eax, eax
0x180001fea  jz      loc_180002083
0x180001ff0  mov     r8, rsi; lpvReserved
0x180001ff3  mov     edx, edi; fdwReason
0x180001ff5  mov     rcx, r14; hinstDLL
0x180001ff8  call    DllMain
0x180001ffd  mov     ebx, eax
0x180001fff  mov     [rsp+58h+var_28], eax
0x180002003  cmp     edi, 1
0x180002006  jnz     short loc_18000203F
0x180002008  test    eax, eax
0x18000200a  jnz     short loc_18000203F
0x18000200c  mov     r8, rsi; lpvReserved
0x18000200f  xor     edx, edx; fdwReason
0x180002011  mov     rcx, r14; hinstDLL
0x180002014  call    DllMain
0x180002019  mov     r8, rsi
0x18000201c  xor     edx, edx
0x18000201e  mov     rcx, r14
0x180002021  call    dllmain_crt_dispatch
0x180002026  mov     rax, cs:_pRawDllMain
0x18000202d  test    rax, rax
0x180002030  jz      short loc_18000203F
0x180002032  mov     r8, rsi
0x180002035  xor     edx, edx
0x180002037  mov     rcx, r14
0x18000203a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000203f  test    edi, edi
0x180002041  jz      short loc_180002048
0x180002043  cmp     edi, 3
0x180002046  jnz     short loc_180002083
0x180002048  mov     r8, rsi
0x18000204b  mov     edx, edi
0x18000204d  mov     rcx, r14
0x180002050  call    dllmain_crt_dispatch
0x180002055  mov     ebx, eax
0x180002057  mov     [rsp+58h+var_28], eax
0x18000205b  test    eax, eax
0x18000205d  jz      short loc_180002083
0x18000205f  mov     rax, cs:_pRawDllMain
0x180002066  test    rax, rax
0x180002069  jnz     short loc_180002070
0x18000206b  lea     ebx, [rax+1]
0x18000206e  jmp     short loc_18000207F
0x180002070  mov     r8, rsi
0x180002073  mov     edx, edi
0x180002075  mov     rcx, r14
0x180002078  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000207d  mov     ebx, eax
0x18000207f  mov     [rsp+58h+var_28], ebx
0x180002083  jmp     short loc_18000208B
0x180002085  xor     ebx, ebx
0x180002087  mov     [rsp+58h+var_28], ebx
0x18000208b  mov     eax, ebx
0x18000208d  mov     rbx, [rsp+58h+arg_18]
0x180002092  add     rsp, 40h
0x180002096  pop     r14
0x180002098  pop     rdi
0x180002099  pop     rsi
0x18000209a  retn
0x180009194  push    rbp
0x180009196  sub     rsp, 30h
0x18000919a  mov     rbp, rdx
0x18000919d  mov     rax, [rcx]
0x1800091a0  mov     edx, [rax]
0x1800091a2  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x1800091a7  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x1800091ab  lea     r9, dllmain_crt_dispatch; int
0x1800091b2  mov     r8, [rbp+70h]; int
0x1800091b6  mov     edx, [rbp+68h]; int
0x1800091b9  mov     rcx, [rbp+60h]; int
0x1800091bd  call    __scrt_dllmain_exception_filter
0x1800091c2  nop
0x1800091c3  add     rsp, 30h
0x1800091c7  pop     rbp
0x1800091c8  retn
```
