# dllmain_dispatch

- ea: `0x180015f04`
- end: `0x18001602b`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180016040`

## callees

- `0x180015d20`
- `0x180015f04`
- `0x18001632c`
- `0x180018f48`
- `0x180026010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_1800312F0 <= 0 )
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
0x180015f04  mov     rax, rsp
0x180015f07  mov     [rax+20h], rbx
0x180015f0b  mov     [rax+18h], r8
0x180015f0f  mov     [rax+10h], edx
0x180015f12  mov     [rax+8], rcx
0x180015f16  push    rsi
0x180015f17  push    rdi
0x180015f18  push    r14
0x180015f1a  sub     rsp, 40h
0x180015f1e  mov     rsi, r8
0x180015f21  mov     edi, edx
0x180015f23  mov     r14, rcx
0x180015f26  test    edx, edx
0x180015f28  jnz     short loc_180015F39
0x180015f2a  cmp     cs:dword_1800312F0, edx
0x180015f30  jg      short loc_180015F39
0x180015f32  xor     eax, eax
0x180015f34  jmp     loc_18001601D
0x180015f39  lea     eax, [rdx-1]
0x180015f3c  cmp     eax, 1
0x180015f3f  ja      short loc_180015F80
0x180015f41  mov     rax, cs:_pRawDllMain
0x180015f48  test    rax, rax
0x180015f4b  jnz     short loc_180015F52
0x180015f4d  lea     ebx, [rax+1]
0x180015f50  jmp     short loc_180015F59
0x180015f52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015f57  mov     ebx, eax
0x180015f59  mov     [rsp+58h+var_28], ebx
0x180015f5d  test    ebx, ebx
0x180015f5f  jz      loc_180016013
0x180015f65  mov     r8, rsi
0x180015f68  mov     edx, edi
0x180015f6a  mov     rcx, r14
0x180015f6d  call    dllmain_crt_dispatch
0x180015f72  mov     ebx, eax
0x180015f74  mov     [rsp+58h+var_28], eax
0x180015f78  test    eax, eax
0x180015f7a  jz      loc_180016013
0x180015f80  mov     r8, rsi; lpvReserved
0x180015f83  mov     edx, edi; fdwReason
0x180015f85  mov     rcx, r14; hinstDLL
0x180015f88  call    DllMain
0x180015f8d  mov     ebx, eax
0x180015f8f  mov     [rsp+58h+var_28], eax
0x180015f93  cmp     edi, 1
0x180015f96  jnz     short loc_180015FCF
0x180015f98  test    eax, eax
0x180015f9a  jnz     short loc_180015FCF
0x180015f9c  mov     r8, rsi; lpvReserved
0x180015f9f  xor     edx, edx; fdwReason
0x180015fa1  mov     rcx, r14; hinstDLL
0x180015fa4  call    DllMain
0x180015fa9  mov     r8, rsi
0x180015fac  xor     edx, edx
0x180015fae  mov     rcx, r14
0x180015fb1  call    dllmain_crt_dispatch
0x180015fb6  mov     rax, cs:_pRawDllMain
0x180015fbd  test    rax, rax
0x180015fc0  jz      short loc_180015FCF
0x180015fc2  mov     r8, rsi
0x180015fc5  xor     edx, edx
0x180015fc7  mov     rcx, r14
0x180015fca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015fcf  test    edi, edi
0x180015fd1  jz      short loc_180015FD8
0x180015fd3  cmp     edi, 3
0x180015fd6  jnz     short loc_180016013
0x180015fd8  mov     r8, rsi
0x180015fdb  mov     edx, edi
0x180015fdd  mov     rcx, r14
0x180015fe0  call    dllmain_crt_dispatch
0x180015fe5  mov     ebx, eax
0x180015fe7  mov     [rsp+58h+var_28], eax
0x180015feb  test    eax, eax
0x180015fed  jz      short loc_180016013
0x180015fef  mov     rax, cs:_pRawDllMain
0x180015ff6  test    rax, rax
0x180015ff9  jnz     short loc_180016000
0x180015ffb  lea     ebx, [rax+1]
0x180015ffe  jmp     short loc_18001600F
0x180016000  mov     r8, rsi
0x180016003  mov     edx, edi
0x180016005  mov     rcx, r14
0x180016008  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001600d  mov     ebx, eax
0x18001600f  mov     [rsp+58h+var_28], ebx
0x180016013  jmp     short loc_18001601B
0x180016015  xor     ebx, ebx
0x180016017  mov     [rsp+58h+var_28], ebx
0x18001601b  mov     eax, ebx
0x18001601d  mov     rbx, [rsp+58h+arg_18]
0x180016022  add     rsp, 40h
0x180016026  pop     r14
0x180016028  pop     rdi
0x180016029  pop     rsi
0x18001602a  retn
0x18002518d  push    rbp
0x18002518f  sub     rsp, 30h
0x180025193  mov     rbp, rdx
0x180025196  mov     rax, [rcx]
0x180025199  mov     edx, [rax]
0x18002519b  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x1800251a0  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x1800251a4  lea     r9, dllmain_crt_dispatch; int
0x1800251ab  mov     r8, [rbp+70h]; int
0x1800251af  mov     edx, [rbp+68h]; int
0x1800251b2  mov     rcx, [rbp+60h]; int
0x1800251b6  call    __scrt_dllmain_exception_filter
0x1800251bb  nop
0x1800251bc  add     rsp, 30h
0x1800251c0  pop     rbp
0x1800251c1  retn
```
