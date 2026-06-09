# dllmain_dispatch

- ea: `0x180009e24`
- end: `0x180009f4b`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180009f60`

## callees

- `0x180009c40`
- `0x180009e24`
- `0x18000a1e0`
- `0x18000b2b0`
- `0x180019010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_180022090 <= 0 )
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
0x180009e24  mov     rax, rsp
0x180009e27  mov     [rax+20h], rbx
0x180009e2b  mov     [rax+18h], r8
0x180009e2f  mov     [rax+10h], edx
0x180009e32  mov     [rax+8], rcx
0x180009e36  push    rsi
0x180009e37  push    rdi
0x180009e38  push    r14
0x180009e3a  sub     rsp, 40h
0x180009e3e  mov     rsi, r8
0x180009e41  mov     edi, edx
0x180009e43  mov     r14, rcx
0x180009e46  test    edx, edx
0x180009e48  jnz     short loc_180009E59
0x180009e4a  cmp     cs:dword_180022090, edx
0x180009e50  jg      short loc_180009E59
0x180009e52  xor     eax, eax
0x180009e54  jmp     loc_180009F3D
0x180009e59  lea     eax, [rdx-1]
0x180009e5c  cmp     eax, 1
0x180009e5f  ja      short loc_180009EA0
0x180009e61  mov     rax, cs:_pRawDllMain
0x180009e68  test    rax, rax
0x180009e6b  jnz     short loc_180009E72
0x180009e6d  lea     ebx, [rax+1]
0x180009e70  jmp     short loc_180009E79
0x180009e72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009e77  mov     ebx, eax
0x180009e79  mov     [rsp+58h+var_28], ebx
0x180009e7d  test    ebx, ebx
0x180009e7f  jz      loc_180009F33
0x180009e85  mov     r8, rsi
0x180009e88  mov     edx, edi
0x180009e8a  mov     rcx, r14
0x180009e8d  call    dllmain_crt_dispatch
0x180009e92  mov     ebx, eax
0x180009e94  mov     [rsp+58h+var_28], eax
0x180009e98  test    eax, eax
0x180009e9a  jz      loc_180009F33
0x180009ea0  mov     r8, rsi; lpvReserved
0x180009ea3  mov     edx, edi; fdwReason
0x180009ea5  mov     rcx, r14; hinstDLL
0x180009ea8  call    DllMain
0x180009ead  mov     ebx, eax
0x180009eaf  mov     [rsp+58h+var_28], eax
0x180009eb3  cmp     edi, 1
0x180009eb6  jnz     short loc_180009EEF
0x180009eb8  test    eax, eax
0x180009eba  jnz     short loc_180009EEF
0x180009ebc  mov     r8, rsi; lpvReserved
0x180009ebf  xor     edx, edx; fdwReason
0x180009ec1  mov     rcx, r14; hinstDLL
0x180009ec4  call    DllMain
0x180009ec9  mov     r8, rsi
0x180009ecc  xor     edx, edx
0x180009ece  mov     rcx, r14
0x180009ed1  call    dllmain_crt_dispatch
0x180009ed6  mov     rax, cs:_pRawDllMain
0x180009edd  test    rax, rax
0x180009ee0  jz      short loc_180009EEF
0x180009ee2  mov     r8, rsi
0x180009ee5  xor     edx, edx
0x180009ee7  mov     rcx, r14
0x180009eea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009eef  test    edi, edi
0x180009ef1  jz      short loc_180009EF8
0x180009ef3  cmp     edi, 3
0x180009ef6  jnz     short loc_180009F33
0x180009ef8  mov     r8, rsi
0x180009efb  mov     edx, edi
0x180009efd  mov     rcx, r14
0x180009f00  call    dllmain_crt_dispatch
0x180009f05  mov     ebx, eax
0x180009f07  mov     [rsp+58h+var_28], eax
0x180009f0b  test    eax, eax
0x180009f0d  jz      short loc_180009F33
0x180009f0f  mov     rax, cs:_pRawDllMain
0x180009f16  test    rax, rax
0x180009f19  jnz     short loc_180009F20
0x180009f1b  lea     ebx, [rax+1]
0x180009f1e  jmp     short loc_180009F2F
0x180009f20  mov     r8, rsi
0x180009f23  mov     edx, edi
0x180009f25  mov     rcx, r14
0x180009f28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009f2d  mov     ebx, eax
0x180009f2f  mov     [rsp+58h+var_28], ebx
0x180009f33  jmp     short loc_180009F3B
0x180009f35  xor     ebx, ebx
0x180009f37  mov     [rsp+58h+var_28], ebx
0x180009f3b  mov     eax, ebx
0x180009f3d  mov     rbx, [rsp+58h+arg_18]
0x180009f42  add     rsp, 40h
0x180009f46  pop     r14
0x180009f48  pop     rdi
0x180009f49  pop     rsi
0x180009f4a  retn
0x180018c0c  push    rbp
0x180018c0e  sub     rsp, 30h
0x180018c12  mov     rbp, rdx
0x180018c15  mov     rax, [rcx]
0x180018c18  mov     edx, [rax]
0x180018c1a  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x180018c1f  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x180018c23  lea     r9, dllmain_crt_dispatch; int
0x180018c2a  mov     r8, [rbp+70h]; int
0x180018c2e  mov     edx, [rbp+68h]; int
0x180018c31  mov     rcx, [rbp+60h]; int
0x180018c35  call    __scrt_dllmain_exception_filter
0x180018c3a  nop
0x180018c3b  add     rsp, 30h
0x180018c3f  pop     rbp
0x180018c40  retn
```
