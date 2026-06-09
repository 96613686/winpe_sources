# dllmain_dispatch

- ea: `0x180001b54`
- end: `0x180001c7b`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180001c90`

## callees

- `0x180001970`
- `0x180001b54`
- `0x180001dc0`
- `0x180001f10`
- `0x18000e010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_1800131D0 <= 0 )
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
0x180001b54  mov     rax, rsp
0x180001b57  mov     [rax+20h], rbx
0x180001b5b  mov     [rax+18h], r8
0x180001b5f  mov     [rax+10h], edx
0x180001b62  mov     [rax+8], rcx
0x180001b66  push    rsi
0x180001b67  push    rdi
0x180001b68  push    r14
0x180001b6a  sub     rsp, 40h
0x180001b6e  mov     rsi, r8
0x180001b71  mov     edi, edx
0x180001b73  mov     r14, rcx
0x180001b76  test    edx, edx
0x180001b78  jnz     short loc_180001B89
0x180001b7a  cmp     cs:dword_1800131D0, edx
0x180001b80  jg      short loc_180001B89
0x180001b82  xor     eax, eax
0x180001b84  jmp     loc_180001C6D
0x180001b89  lea     eax, [rdx-1]
0x180001b8c  cmp     eax, 1
0x180001b8f  ja      short loc_180001BD0
0x180001b91  mov     rax, cs:_pRawDllMain
0x180001b98  test    rax, rax
0x180001b9b  jnz     short loc_180001BA2
0x180001b9d  lea     ebx, [rax+1]
0x180001ba0  jmp     short loc_180001BA9
0x180001ba2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001ba7  mov     ebx, eax
0x180001ba9  mov     [rsp+58h+var_28], ebx
0x180001bad  test    ebx, ebx
0x180001baf  jz      loc_180001C63
0x180001bb5  mov     r8, rsi
0x180001bb8  mov     edx, edi
0x180001bba  mov     rcx, r14
0x180001bbd  call    dllmain_crt_dispatch
0x180001bc2  mov     ebx, eax
0x180001bc4  mov     [rsp+58h+var_28], eax
0x180001bc8  test    eax, eax
0x180001bca  jz      loc_180001C63
0x180001bd0  mov     r8, rsi; lpvReserved
0x180001bd3  mov     edx, edi; fdwReason
0x180001bd5  mov     rcx, r14; hinstDLL
0x180001bd8  call    DllMain
0x180001bdd  mov     ebx, eax
0x180001bdf  mov     [rsp+58h+var_28], eax
0x180001be3  cmp     edi, 1
0x180001be6  jnz     short loc_180001C1F
0x180001be8  test    eax, eax
0x180001bea  jnz     short loc_180001C1F
0x180001bec  mov     r8, rsi; lpvReserved
0x180001bef  xor     edx, edx; fdwReason
0x180001bf1  mov     rcx, r14; hinstDLL
0x180001bf4  call    DllMain
0x180001bf9  mov     r8, rsi
0x180001bfc  xor     edx, edx
0x180001bfe  mov     rcx, r14
0x180001c01  call    dllmain_crt_dispatch
0x180001c06  mov     rax, cs:_pRawDllMain
0x180001c0d  test    rax, rax
0x180001c10  jz      short loc_180001C1F
0x180001c12  mov     r8, rsi
0x180001c15  xor     edx, edx
0x180001c17  mov     rcx, r14
0x180001c1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001c1f  test    edi, edi
0x180001c21  jz      short loc_180001C28
0x180001c23  cmp     edi, 3
0x180001c26  jnz     short loc_180001C63
0x180001c28  mov     r8, rsi
0x180001c2b  mov     edx, edi
0x180001c2d  mov     rcx, r14
0x180001c30  call    dllmain_crt_dispatch
0x180001c35  mov     ebx, eax
0x180001c37  mov     [rsp+58h+var_28], eax
0x180001c3b  test    eax, eax
0x180001c3d  jz      short loc_180001C63
0x180001c3f  mov     rax, cs:_pRawDllMain
0x180001c46  test    rax, rax
0x180001c49  jnz     short loc_180001C50
0x180001c4b  lea     ebx, [rax+1]
0x180001c4e  jmp     short loc_180001C5F
0x180001c50  mov     r8, rsi
0x180001c53  mov     edx, edi
0x180001c55  mov     rcx, r14
0x180001c58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001c5d  mov     ebx, eax
0x180001c5f  mov     [rsp+58h+var_28], ebx
0x180001c63  jmp     short loc_180001C6B
0x180001c65  xor     ebx, ebx
0x180001c67  mov     [rsp+58h+var_28], ebx
0x180001c6b  mov     eax, ebx
0x180001c6d  mov     rbx, [rsp+58h+arg_18]
0x180001c72  add     rsp, 40h
0x180001c76  pop     r14
0x180001c78  pop     rdi
0x180001c79  pop     rsi
0x180001c7a  retn
0x18000d91c  push    rbp
0x18000d91e  sub     rsp, 30h
0x18000d922  mov     rbp, rdx
0x18000d925  mov     rax, [rcx]
0x18000d928  mov     edx, [rax]
0x18000d92a  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x18000d92f  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x18000d933  lea     r9, dllmain_crt_dispatch; int
0x18000d93a  mov     r8, [rbp+70h]; int
0x18000d93e  mov     edx, [rbp+68h]; int
0x18000d941  mov     rcx, [rbp+60h]; int
0x18000d945  call    __scrt_dllmain_exception_filter
0x18000d94a  nop
0x18000d94b  add     rsp, 30h
0x18000d94f  pop     rbp
0x18000d950  retn
```
