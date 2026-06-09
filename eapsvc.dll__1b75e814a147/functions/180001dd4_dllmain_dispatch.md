# dllmain_dispatch

- ea: `0x180001dd4`
- end: `0x180001efb`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180001f10`

## callees

- `0x180001bf0`
- `0x180001dd4`
- `0x18000205c`
- `0x18000bf5c`
- `0x180017010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_180020810 <= 0 )
    return 0;
  if ( fdwReason - 1 > 1
    || (pRawDllMain ? (v7 = pRawDllMain()) : (v7 = 1),
        v7 && (v7 = dllmain_crt_dispatch((__int64)hinstDLL, fdwReason, (__int64)lpvReserved)) != 0) )
  {
    v8 = DllMain(hinstDLL, fdwReason, lpvReserved);
    v7 = v8;
    if ( fdwReason == 1 && !v8 )
    {
      DllMain(hinstDLL, 0, lpvReserved);
      dllmain_crt_dispatch((__int64)hinstDLL, 0, (__int64)lpvReserved);
      if ( pRawDllMain )
        pRawDllMain();
    }
    if ( !fdwReason || fdwReason == 3 )
    {
      v7 = dllmain_crt_dispatch((__int64)hinstDLL, fdwReason, (__int64)lpvReserved);
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
0x180001dd4  mov     rax, rsp
0x180001dd7  mov     [rax+20h], rbx
0x180001ddb  mov     [rax+18h], r8
0x180001ddf  mov     [rax+10h], edx
0x180001de2  mov     [rax+8], rcx
0x180001de6  push    rsi
0x180001de7  push    rdi
0x180001de8  push    r14
0x180001dea  sub     rsp, 40h
0x180001dee  mov     rsi, r8
0x180001df1  mov     edi, edx
0x180001df3  mov     r14, rcx
0x180001df6  test    edx, edx
0x180001df8  jnz     short loc_180001E09
0x180001dfa  cmp     cs:dword_180020810, edx
0x180001e00  jg      short loc_180001E09
0x180001e02  xor     eax, eax
0x180001e04  jmp     loc_180001EED
0x180001e09  lea     eax, [rdx-1]
0x180001e0c  cmp     eax, 1
0x180001e0f  ja      short loc_180001E50
0x180001e11  mov     rax, cs:_pRawDllMain
0x180001e18  test    rax, rax
0x180001e1b  jnz     short loc_180001E22
0x180001e1d  lea     ebx, [rax+1]
0x180001e20  jmp     short loc_180001E29
0x180001e22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001e27  mov     ebx, eax
0x180001e29  mov     [rsp+58h+var_28], ebx
0x180001e2d  test    ebx, ebx
0x180001e2f  jz      loc_180001EE3
0x180001e35  mov     r8, rsi
0x180001e38  mov     edx, edi
0x180001e3a  mov     rcx, r14
0x180001e3d  call    dllmain_crt_dispatch
0x180001e42  mov     ebx, eax
0x180001e44  mov     [rsp+58h+var_28], eax
0x180001e48  test    eax, eax
0x180001e4a  jz      loc_180001EE3
0x180001e50  mov     r8, rsi; lpvReserved
0x180001e53  mov     edx, edi; fdwReason
0x180001e55  mov     rcx, r14; hinstDLL
0x180001e58  call    DllMain
0x180001e5d  mov     ebx, eax
0x180001e5f  mov     [rsp+58h+var_28], eax
0x180001e63  cmp     edi, 1
0x180001e66  jnz     short loc_180001E9F
0x180001e68  test    eax, eax
0x180001e6a  jnz     short loc_180001E9F
0x180001e6c  mov     r8, rsi; lpvReserved
0x180001e6f  xor     edx, edx; fdwReason
0x180001e71  mov     rcx, r14; hinstDLL
0x180001e74  call    DllMain
0x180001e79  mov     r8, rsi
0x180001e7c  xor     edx, edx
0x180001e7e  mov     rcx, r14
0x180001e81  call    dllmain_crt_dispatch
0x180001e86  mov     rax, cs:_pRawDllMain
0x180001e8d  test    rax, rax
0x180001e90  jz      short loc_180001E9F
0x180001e92  mov     r8, rsi
0x180001e95  xor     edx, edx
0x180001e97  mov     rcx, r14
0x180001e9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001e9f  test    edi, edi
0x180001ea1  jz      short loc_180001EA8
0x180001ea3  cmp     edi, 3
0x180001ea6  jnz     short loc_180001EE3
0x180001ea8  mov     r8, rsi
0x180001eab  mov     edx, edi
0x180001ead  mov     rcx, r14
0x180001eb0  call    dllmain_crt_dispatch
0x180001eb5  mov     ebx, eax
0x180001eb7  mov     [rsp+58h+var_28], eax
0x180001ebb  test    eax, eax
0x180001ebd  jz      short loc_180001EE3
0x180001ebf  mov     rax, cs:_pRawDllMain
0x180001ec6  test    rax, rax
0x180001ec9  jnz     short loc_180001ED0
0x180001ecb  lea     ebx, [rax+1]
0x180001ece  jmp     short loc_180001EDF
0x180001ed0  mov     r8, rsi
0x180001ed3  mov     edx, edi
0x180001ed5  mov     rcx, r14
0x180001ed8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001edd  mov     ebx, eax
0x180001edf  mov     [rsp+58h+var_28], ebx
0x180001ee3  jmp     short loc_180001EEB
0x180001ee5  xor     ebx, ebx
0x180001ee7  mov     [rsp+58h+var_28], ebx
0x180001eeb  mov     eax, ebx
0x180001eed  mov     rbx, [rsp+58h+arg_18]
0x180001ef2  add     rsp, 40h
0x180001ef6  pop     r14
0x180001ef8  pop     rdi
0x180001ef9  pop     rsi
0x180001efa  retn
0x180014f5c  push    rbp
0x180014f5e  sub     rsp, 30h
0x180014f62  mov     rbp, rdx
0x180014f65  mov     rax, [rcx]
0x180014f68  mov     edx, [rax]
0x180014f6a  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x180014f6f  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x180014f73  lea     r9, dllmain_crt_dispatch; int
0x180014f7a  mov     r8, [rbp+70h]; int
0x180014f7e  mov     edx, [rbp+68h]; int
0x180014f81  mov     rcx, [rbp+60h]; int
0x180014f85  call    __scrt_dllmain_exception_filter
0x180014f8a  nop
0x180014f8b  add     rsp, 30h
0x180014f8f  pop     rbp
0x180014f90  retn
```
