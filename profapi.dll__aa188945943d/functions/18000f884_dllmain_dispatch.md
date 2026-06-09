# dllmain_dispatch

- ea: `0x18000f884`
- end: `0x18000f9ab`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x18000f9c0`

## callees

- `0x18000aa48`
- `0x18000f6a0`
- `0x18000f884`
- `0x18000fb0c`
- `0x180018010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_180022230 <= 0 )
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
0x18000f884  mov     rax, rsp
0x18000f887  mov     [rax+20h], rbx
0x18000f88b  mov     [rax+18h], r8
0x18000f88f  mov     [rax+10h], edx
0x18000f892  mov     [rax+8], rcx
0x18000f896  push    rsi
0x18000f897  push    rdi
0x18000f898  push    r14
0x18000f89a  sub     rsp, 40h
0x18000f89e  mov     rsi, r8
0x18000f8a1  mov     edi, edx
0x18000f8a3  mov     r14, rcx
0x18000f8a6  test    edx, edx
0x18000f8a8  jnz     short loc_18000F8B9
0x18000f8aa  cmp     cs:dword_180022230, edx
0x18000f8b0  jg      short loc_18000F8B9
0x18000f8b2  xor     eax, eax
0x18000f8b4  jmp     loc_18000F99D
0x18000f8b9  lea     eax, [rdx-1]
0x18000f8bc  cmp     eax, 1
0x18000f8bf  ja      short loc_18000F900
0x18000f8c1  mov     rax, cs:_pRawDllMain
0x18000f8c8  test    rax, rax
0x18000f8cb  jnz     short loc_18000F8D2
0x18000f8cd  lea     ebx, [rax+1]
0x18000f8d0  jmp     short loc_18000F8D9
0x18000f8d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f8d7  mov     ebx, eax
0x18000f8d9  mov     [rsp+58h+var_28], ebx
0x18000f8dd  test    ebx, ebx
0x18000f8df  jz      loc_18000F993
0x18000f8e5  mov     r8, rsi
0x18000f8e8  mov     edx, edi
0x18000f8ea  mov     rcx, r14
0x18000f8ed  call    dllmain_crt_dispatch
0x18000f8f2  mov     ebx, eax
0x18000f8f4  mov     [rsp+58h+var_28], eax
0x18000f8f8  test    eax, eax
0x18000f8fa  jz      loc_18000F993
0x18000f900  mov     r8, rsi; lpvReserved
0x18000f903  mov     edx, edi; fdwReason
0x18000f905  mov     rcx, r14; hinstDLL
0x18000f908  call    DllMain
0x18000f90d  mov     ebx, eax
0x18000f90f  mov     [rsp+58h+var_28], eax
0x18000f913  cmp     edi, 1
0x18000f916  jnz     short loc_18000F94F
0x18000f918  test    eax, eax
0x18000f91a  jnz     short loc_18000F94F
0x18000f91c  mov     r8, rsi; lpvReserved
0x18000f91f  xor     edx, edx; fdwReason
0x18000f921  mov     rcx, r14; hinstDLL
0x18000f924  call    DllMain
0x18000f929  mov     r8, rsi
0x18000f92c  xor     edx, edx
0x18000f92e  mov     rcx, r14
0x18000f931  call    dllmain_crt_dispatch
0x18000f936  mov     rax, cs:_pRawDllMain
0x18000f93d  test    rax, rax
0x18000f940  jz      short loc_18000F94F
0x18000f942  mov     r8, rsi
0x18000f945  xor     edx, edx
0x18000f947  mov     rcx, r14
0x18000f94a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f94f  test    edi, edi
0x18000f951  jz      short loc_18000F958
0x18000f953  cmp     edi, 3
0x18000f956  jnz     short loc_18000F993
0x18000f958  mov     r8, rsi
0x18000f95b  mov     edx, edi
0x18000f95d  mov     rcx, r14
0x18000f960  call    dllmain_crt_dispatch
0x18000f965  mov     ebx, eax
0x18000f967  mov     [rsp+58h+var_28], eax
0x18000f96b  test    eax, eax
0x18000f96d  jz      short loc_18000F993
0x18000f96f  mov     rax, cs:_pRawDllMain
0x18000f976  test    rax, rax
0x18000f979  jnz     short loc_18000F980
0x18000f97b  lea     ebx, [rax+1]
0x18000f97e  jmp     short loc_18000F98F
0x18000f980  mov     r8, rsi
0x18000f983  mov     edx, edi
0x18000f985  mov     rcx, r14
0x18000f988  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f98d  mov     ebx, eax
0x18000f98f  mov     [rsp+58h+var_28], ebx
0x18000f993  jmp     short loc_18000F99B
0x18000f995  xor     ebx, ebx
0x18000f997  mov     [rsp+58h+var_28], ebx
0x18000f99b  mov     eax, ebx
0x18000f99d  mov     rbx, [rsp+58h+arg_18]
0x18000f9a2  add     rsp, 40h
0x18000f9a6  pop     r14
0x18000f9a8  pop     rdi
0x18000f9a9  pop     rsi
0x18000f9aa  retn
0x18001721e  push    rbp
0x180017220  sub     rsp, 30h
0x180017224  mov     rbp, rdx
0x180017227  mov     rax, [rcx]
0x18001722a  mov     edx, [rax]
0x18001722c  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x180017231  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x180017235  lea     r9, dllmain_crt_dispatch; int
0x18001723c  mov     r8, [rbp+70h]; int
0x180017240  mov     edx, [rbp+68h]; int
0x180017243  mov     rcx, [rbp+60h]; int
0x180017247  call    __scrt_dllmain_exception_filter
0x18001724c  nop
0x18001724d  add     rsp, 30h
0x180017251  pop     rbp
0x180017252  retn
```
