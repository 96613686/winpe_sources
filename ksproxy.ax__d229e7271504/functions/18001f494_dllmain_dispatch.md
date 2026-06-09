# dllmain_dispatch

- ea: `0x18001f494`
- end: `0x18001f5bb`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x18001f5d0`

## callees

- `0x18001f2b0`
- `0x18001f494`
- `0x18001f740`
- `0x180025830`
- `0x180045010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_180051310 <= 0 )
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
0x18001f494  mov     rax, rsp
0x18001f497  mov     [rax+20h], rbx
0x18001f49b  mov     [rax+18h], r8
0x18001f49f  mov     [rax+10h], edx
0x18001f4a2  mov     [rax+8], rcx
0x18001f4a6  push    rsi
0x18001f4a7  push    rdi
0x18001f4a8  push    r14
0x18001f4aa  sub     rsp, 40h
0x18001f4ae  mov     rsi, r8
0x18001f4b1  mov     edi, edx
0x18001f4b3  mov     r14, rcx
0x18001f4b6  test    edx, edx
0x18001f4b8  jnz     short loc_18001F4C9
0x18001f4ba  cmp     cs:dword_180051310, edx
0x18001f4c0  jg      short loc_18001F4C9
0x18001f4c2  xor     eax, eax
0x18001f4c4  jmp     loc_18001F5AD
0x18001f4c9  lea     eax, [rdx-1]
0x18001f4cc  cmp     eax, 1
0x18001f4cf  ja      short loc_18001F510
0x18001f4d1  mov     rax, cs:_pRawDllMain
0x18001f4d8  test    rax, rax
0x18001f4db  jnz     short loc_18001F4E2
0x18001f4dd  lea     ebx, [rax+1]
0x18001f4e0  jmp     short loc_18001F4E9
0x18001f4e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f4e7  mov     ebx, eax
0x18001f4e9  mov     [rsp+58h+var_28], ebx
0x18001f4ed  test    ebx, ebx
0x18001f4ef  jz      loc_18001F5A3
0x18001f4f5  mov     r8, rsi
0x18001f4f8  mov     edx, edi
0x18001f4fa  mov     rcx, r14
0x18001f4fd  call    dllmain_crt_dispatch
0x18001f502  mov     ebx, eax
0x18001f504  mov     [rsp+58h+var_28], eax
0x18001f508  test    eax, eax
0x18001f50a  jz      loc_18001F5A3
0x18001f510  mov     r8, rsi; lpvReserved
0x18001f513  mov     edx, edi; fdwReason
0x18001f515  mov     rcx, r14; hinstDLL
0x18001f518  call    DllMain
0x18001f51d  mov     ebx, eax
0x18001f51f  mov     [rsp+58h+var_28], eax
0x18001f523  cmp     edi, 1
0x18001f526  jnz     short loc_18001F55F
0x18001f528  test    eax, eax
0x18001f52a  jnz     short loc_18001F55F
0x18001f52c  mov     r8, rsi; lpvReserved
0x18001f52f  xor     edx, edx; fdwReason
0x18001f531  mov     rcx, r14; hinstDLL
0x18001f534  call    DllMain
0x18001f539  mov     r8, rsi
0x18001f53c  xor     edx, edx
0x18001f53e  mov     rcx, r14
0x18001f541  call    dllmain_crt_dispatch
0x18001f546  mov     rax, cs:_pRawDllMain
0x18001f54d  test    rax, rax
0x18001f550  jz      short loc_18001F55F
0x18001f552  mov     r8, rsi
0x18001f555  xor     edx, edx
0x18001f557  mov     rcx, r14
0x18001f55a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f55f  test    edi, edi
0x18001f561  jz      short loc_18001F568
0x18001f563  cmp     edi, 3
0x18001f566  jnz     short loc_18001F5A3
0x18001f568  mov     r8, rsi
0x18001f56b  mov     edx, edi
0x18001f56d  mov     rcx, r14
0x18001f570  call    dllmain_crt_dispatch
0x18001f575  mov     ebx, eax
0x18001f577  mov     [rsp+58h+var_28], eax
0x18001f57b  test    eax, eax
0x18001f57d  jz      short loc_18001F5A3
0x18001f57f  mov     rax, cs:_pRawDllMain
0x18001f586  test    rax, rax
0x18001f589  jnz     short loc_18001F590
0x18001f58b  lea     ebx, [rax+1]
0x18001f58e  jmp     short loc_18001F59F
0x18001f590  mov     r8, rsi
0x18001f593  mov     edx, edi
0x18001f595  mov     rcx, r14
0x18001f598  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f59d  mov     ebx, eax
0x18001f59f  mov     [rsp+58h+var_28], ebx
0x18001f5a3  jmp     short loc_18001F5AB
0x18001f5a5  xor     ebx, ebx
0x18001f5a7  mov     [rsp+58h+var_28], ebx
0x18001f5ab  mov     eax, ebx
0x18001f5ad  mov     rbx, [rsp+58h+arg_18]
0x18001f5b2  add     rsp, 40h
0x18001f5b6  pop     r14
0x18001f5b8  pop     rdi
0x18001f5b9  pop     rsi
0x18001f5ba  retn
0x18004492c  push    rbp
0x18004492e  sub     rsp, 30h
0x180044932  mov     rbp, rdx
0x180044935  mov     rax, [rcx]
0x180044938  mov     edx, [rax]
0x18004493a  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x18004493f  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x180044943  lea     r9, dllmain_crt_dispatch; int
0x18004494a  mov     r8, [rbp+70h]; int
0x18004494e  mov     edx, [rbp+68h]; int
0x180044951  mov     rcx, [rbp+60h]; int
0x180044955  call    __scrt_dllmain_exception_filter
0x18004495a  nop
0x18004495b  add     rsp, 30h
0x18004495f  pop     rbp
0x180044960  retn
```
