# dllmain_dispatch

- ea: `0x180004e94`
- end: `0x180004fbb`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180004fd0`

## callees

- `0x180002a80`
- `0x180004cb0`
- `0x180004e94`
- `0x18000511c`
- `0x18000b010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_180012BF0 <= 0 )
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
0x180004e94  mov     rax, rsp
0x180004e97  mov     [rax+20h], rbx
0x180004e9b  mov     [rax+18h], r8
0x180004e9f  mov     [rax+10h], edx
0x180004ea2  mov     [rax+8], rcx
0x180004ea6  push    rsi
0x180004ea7  push    rdi
0x180004ea8  push    r14
0x180004eaa  sub     rsp, 40h
0x180004eae  mov     rsi, r8
0x180004eb1  mov     edi, edx
0x180004eb3  mov     r14, rcx
0x180004eb6  test    edx, edx
0x180004eb8  jnz     short loc_180004EC9
0x180004eba  cmp     cs:dword_180012BF0, edx
0x180004ec0  jg      short loc_180004EC9
0x180004ec2  xor     eax, eax
0x180004ec4  jmp     loc_180004FAD
0x180004ec9  lea     eax, [rdx-1]
0x180004ecc  cmp     eax, 1
0x180004ecf  ja      short loc_180004F10
0x180004ed1  mov     rax, cs:_pRawDllMain
0x180004ed8  test    rax, rax
0x180004edb  jnz     short loc_180004EE2
0x180004edd  lea     ebx, [rax+1]
0x180004ee0  jmp     short loc_180004EE9
0x180004ee2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004ee7  mov     ebx, eax
0x180004ee9  mov     [rsp+58h+var_28], ebx
0x180004eed  test    ebx, ebx
0x180004eef  jz      loc_180004FA3
0x180004ef5  mov     r8, rsi
0x180004ef8  mov     edx, edi
0x180004efa  mov     rcx, r14
0x180004efd  call    dllmain_crt_dispatch
0x180004f02  mov     ebx, eax
0x180004f04  mov     [rsp+58h+var_28], eax
0x180004f08  test    eax, eax
0x180004f0a  jz      loc_180004FA3
0x180004f10  mov     r8, rsi; lpvReserved
0x180004f13  mov     edx, edi; fdwReason
0x180004f15  mov     rcx, r14; hinstDLL
0x180004f18  call    DllMain
0x180004f1d  mov     ebx, eax
0x180004f1f  mov     [rsp+58h+var_28], eax
0x180004f23  cmp     edi, 1
0x180004f26  jnz     short loc_180004F5F
0x180004f28  test    eax, eax
0x180004f2a  jnz     short loc_180004F5F
0x180004f2c  mov     r8, rsi; lpvReserved
0x180004f2f  xor     edx, edx; fdwReason
0x180004f31  mov     rcx, r14; hinstDLL
0x180004f34  call    DllMain
0x180004f39  mov     r8, rsi
0x180004f3c  xor     edx, edx
0x180004f3e  mov     rcx, r14
0x180004f41  call    dllmain_crt_dispatch
0x180004f46  mov     rax, cs:_pRawDllMain
0x180004f4d  test    rax, rax
0x180004f50  jz      short loc_180004F5F
0x180004f52  mov     r8, rsi
0x180004f55  xor     edx, edx
0x180004f57  mov     rcx, r14
0x180004f5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004f5f  test    edi, edi
0x180004f61  jz      short loc_180004F68
0x180004f63  cmp     edi, 3
0x180004f66  jnz     short loc_180004FA3
0x180004f68  mov     r8, rsi
0x180004f6b  mov     edx, edi
0x180004f6d  mov     rcx, r14
0x180004f70  call    dllmain_crt_dispatch
0x180004f75  mov     ebx, eax
0x180004f77  mov     [rsp+58h+var_28], eax
0x180004f7b  test    eax, eax
0x180004f7d  jz      short loc_180004FA3
0x180004f7f  mov     rax, cs:_pRawDllMain
0x180004f86  test    rax, rax
0x180004f89  jnz     short loc_180004F90
0x180004f8b  lea     ebx, [rax+1]
0x180004f8e  jmp     short loc_180004F9F
0x180004f90  mov     r8, rsi
0x180004f93  mov     edx, edi
0x180004f95  mov     rcx, r14
0x180004f98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004f9d  mov     ebx, eax
0x180004f9f  mov     [rsp+58h+var_28], ebx
0x180004fa3  jmp     short loc_180004FAB
0x180004fa5  xor     ebx, ebx
0x180004fa7  mov     [rsp+58h+var_28], ebx
0x180004fab  mov     eax, ebx
0x180004fad  mov     rbx, [rsp+58h+arg_18]
0x180004fb2  add     rsp, 40h
0x180004fb6  pop     r14
0x180004fb8  pop     rdi
0x180004fb9  pop     rsi
0x180004fba  retn
0x18000aaa4  push    rbp
0x18000aaa6  sub     rsp, 30h
0x18000aaaa  mov     rbp, rdx
0x18000aaad  mov     rax, [rcx]
0x18000aab0  mov     edx, [rax]
0x18000aab2  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x18000aab7  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x18000aabb  lea     r9, dllmain_crt_dispatch; int
0x18000aac2  mov     r8, [rbp+70h]; int
0x18000aac6  mov     edx, [rbp+68h]; int
0x18000aac9  mov     rcx, [rbp+60h]; int
0x18000aacd  call    __scrt_dllmain_exception_filter
0x18000aad2  nop
0x18000aad3  add     rsp, 30h
0x18000aad7  pop     rbp
0x18000aad8  retn
```
