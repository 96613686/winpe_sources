# dllmain_dispatch

- ea: `0x18000a394`
- end: `0x18000a4bb`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x18000a4d0`

## callees

- `0x180003e90`
- `0x18000a1b0`
- `0x18000a394`
- `0x18000a61c`
- `0x180020010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_18002DAD0 <= 0 )
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
0x18000a394  mov     rax, rsp
0x18000a397  mov     [rax+20h], rbx
0x18000a39b  mov     [rax+18h], r8
0x18000a39f  mov     [rax+10h], edx
0x18000a3a2  mov     [rax+8], rcx
0x18000a3a6  push    rsi
0x18000a3a7  push    rdi
0x18000a3a8  push    r14
0x18000a3aa  sub     rsp, 40h
0x18000a3ae  mov     rsi, r8
0x18000a3b1  mov     edi, edx
0x18000a3b3  mov     r14, rcx
0x18000a3b6  test    edx, edx
0x18000a3b8  jnz     short loc_18000A3C9
0x18000a3ba  cmp     cs:dword_18002DAD0, edx
0x18000a3c0  jg      short loc_18000A3C9
0x18000a3c2  xor     eax, eax
0x18000a3c4  jmp     loc_18000A4AD
0x18000a3c9  lea     eax, [rdx-1]
0x18000a3cc  cmp     eax, 1
0x18000a3cf  ja      short loc_18000A410
0x18000a3d1  mov     rax, cs:_pRawDllMain
0x18000a3d8  test    rax, rax
0x18000a3db  jnz     short loc_18000A3E2
0x18000a3dd  lea     ebx, [rax+1]
0x18000a3e0  jmp     short loc_18000A3E9
0x18000a3e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a3e7  mov     ebx, eax
0x18000a3e9  mov     [rsp+58h+var_28], ebx
0x18000a3ed  test    ebx, ebx
0x18000a3ef  jz      loc_18000A4A3
0x18000a3f5  mov     r8, rsi
0x18000a3f8  mov     edx, edi
0x18000a3fa  mov     rcx, r14
0x18000a3fd  call    dllmain_crt_dispatch
0x18000a402  mov     ebx, eax
0x18000a404  mov     [rsp+58h+var_28], eax
0x18000a408  test    eax, eax
0x18000a40a  jz      loc_18000A4A3
0x18000a410  mov     r8, rsi; lpvReserved
0x18000a413  mov     edx, edi; fdwReason
0x18000a415  mov     rcx, r14; hinstDLL
0x18000a418  call    DllMain
0x18000a41d  mov     ebx, eax
0x18000a41f  mov     [rsp+58h+var_28], eax
0x18000a423  cmp     edi, 1
0x18000a426  jnz     short loc_18000A45F
0x18000a428  test    eax, eax
0x18000a42a  jnz     short loc_18000A45F
0x18000a42c  mov     r8, rsi; lpvReserved
0x18000a42f  xor     edx, edx; fdwReason
0x18000a431  mov     rcx, r14; hinstDLL
0x18000a434  call    DllMain
0x18000a439  mov     r8, rsi
0x18000a43c  xor     edx, edx
0x18000a43e  mov     rcx, r14
0x18000a441  call    dllmain_crt_dispatch
0x18000a446  mov     rax, cs:_pRawDllMain
0x18000a44d  test    rax, rax
0x18000a450  jz      short loc_18000A45F
0x18000a452  mov     r8, rsi
0x18000a455  xor     edx, edx
0x18000a457  mov     rcx, r14
0x18000a45a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a45f  test    edi, edi
0x18000a461  jz      short loc_18000A468
0x18000a463  cmp     edi, 3
0x18000a466  jnz     short loc_18000A4A3
0x18000a468  mov     r8, rsi
0x18000a46b  mov     edx, edi
0x18000a46d  mov     rcx, r14
0x18000a470  call    dllmain_crt_dispatch
0x18000a475  mov     ebx, eax
0x18000a477  mov     [rsp+58h+var_28], eax
0x18000a47b  test    eax, eax
0x18000a47d  jz      short loc_18000A4A3
0x18000a47f  mov     rax, cs:_pRawDllMain
0x18000a486  test    rax, rax
0x18000a489  jnz     short loc_18000A490
0x18000a48b  lea     ebx, [rax+1]
0x18000a48e  jmp     short loc_18000A49F
0x18000a490  mov     r8, rsi
0x18000a493  mov     edx, edi
0x18000a495  mov     rcx, r14
0x18000a498  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a49d  mov     ebx, eax
0x18000a49f  mov     [rsp+58h+var_28], ebx
0x18000a4a3  jmp     short loc_18000A4AB
0x18000a4a5  xor     ebx, ebx
0x18000a4a7  mov     [rsp+58h+var_28], ebx
0x18000a4ab  mov     eax, ebx
0x18000a4ad  mov     rbx, [rsp+58h+arg_18]
0x18000a4b2  add     rsp, 40h
0x18000a4b6  pop     r14
0x18000a4b8  pop     rdi
0x18000a4b9  pop     rsi
0x18000a4ba  retn
0x18001e998  push    rbp
0x18001e99a  sub     rsp, 30h
0x18001e99e  mov     rbp, rdx
0x18001e9a1  mov     rax, [rcx]
0x18001e9a4  mov     edx, [rax]
0x18001e9a6  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x18001e9ab  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x18001e9af  lea     r9, dllmain_crt_dispatch; int
0x18001e9b6  mov     r8, [rbp+70h]; int
0x18001e9ba  mov     edx, [rbp+68h]; int
0x18001e9bd  mov     rcx, [rbp+60h]; int
0x18001e9c1  call    __scrt_dllmain_exception_filter
0x18001e9c6  nop
0x18001e9c7  add     rsp, 30h
0x18001e9cb  pop     rbp
0x18001e9cc  retn
```
