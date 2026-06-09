# dllmain_dispatch

- ea: `0x18000a9a4`
- end: `0x18000aacb`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x18000aae0`

## callees

- `0x18000a7c0`
- `0x18000a9a4`
- `0x18000ac2c`
- `0x18000f110`
- `0x18002b010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_1800338D0 <= 0 )
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
0x18000a9a4  mov     rax, rsp
0x18000a9a7  mov     [rax+20h], rbx
0x18000a9ab  mov     [rax+18h], r8
0x18000a9af  mov     [rax+10h], edx
0x18000a9b2  mov     [rax+8], rcx
0x18000a9b6  push    rsi
0x18000a9b7  push    rdi
0x18000a9b8  push    r14
0x18000a9ba  sub     rsp, 40h
0x18000a9be  mov     rsi, r8
0x18000a9c1  mov     edi, edx
0x18000a9c3  mov     r14, rcx
0x18000a9c6  test    edx, edx
0x18000a9c8  jnz     short loc_18000A9D9
0x18000a9ca  cmp     cs:dword_1800338D0, edx
0x18000a9d0  jg      short loc_18000A9D9
0x18000a9d2  xor     eax, eax
0x18000a9d4  jmp     loc_18000AABD
0x18000a9d9  lea     eax, [rdx-1]
0x18000a9dc  cmp     eax, 1
0x18000a9df  ja      short loc_18000AA20
0x18000a9e1  mov     rax, cs:_pRawDllMain
0x18000a9e8  test    rax, rax
0x18000a9eb  jnz     short loc_18000A9F2
0x18000a9ed  lea     ebx, [rax+1]
0x18000a9f0  jmp     short loc_18000A9F9
0x18000a9f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a9f7  mov     ebx, eax
0x18000a9f9  mov     [rsp+58h+var_28], ebx
0x18000a9fd  test    ebx, ebx
0x18000a9ff  jz      loc_18000AAB3
0x18000aa05  mov     r8, rsi
0x18000aa08  mov     edx, edi
0x18000aa0a  mov     rcx, r14
0x18000aa0d  call    dllmain_crt_dispatch
0x18000aa12  mov     ebx, eax
0x18000aa14  mov     [rsp+58h+var_28], eax
0x18000aa18  test    eax, eax
0x18000aa1a  jz      loc_18000AAB3
0x18000aa20  mov     r8, rsi; lpvReserved
0x18000aa23  mov     edx, edi; fdwReason
0x18000aa25  mov     rcx, r14; hinstDLL
0x18000aa28  call    DllMain
0x18000aa2d  mov     ebx, eax
0x18000aa2f  mov     [rsp+58h+var_28], eax
0x18000aa33  cmp     edi, 1
0x18000aa36  jnz     short loc_18000AA6F
0x18000aa38  test    eax, eax
0x18000aa3a  jnz     short loc_18000AA6F
0x18000aa3c  mov     r8, rsi; lpvReserved
0x18000aa3f  xor     edx, edx; fdwReason
0x18000aa41  mov     rcx, r14; hinstDLL
0x18000aa44  call    DllMain
0x18000aa49  mov     r8, rsi
0x18000aa4c  xor     edx, edx
0x18000aa4e  mov     rcx, r14
0x18000aa51  call    dllmain_crt_dispatch
0x18000aa56  mov     rax, cs:_pRawDllMain
0x18000aa5d  test    rax, rax
0x18000aa60  jz      short loc_18000AA6F
0x18000aa62  mov     r8, rsi
0x18000aa65  xor     edx, edx
0x18000aa67  mov     rcx, r14
0x18000aa6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aa6f  test    edi, edi
0x18000aa71  jz      short loc_18000AA78
0x18000aa73  cmp     edi, 3
0x18000aa76  jnz     short loc_18000AAB3
0x18000aa78  mov     r8, rsi
0x18000aa7b  mov     edx, edi
0x18000aa7d  mov     rcx, r14
0x18000aa80  call    dllmain_crt_dispatch
0x18000aa85  mov     ebx, eax
0x18000aa87  mov     [rsp+58h+var_28], eax
0x18000aa8b  test    eax, eax
0x18000aa8d  jz      short loc_18000AAB3
0x18000aa8f  mov     rax, cs:_pRawDllMain
0x18000aa96  test    rax, rax
0x18000aa99  jnz     short loc_18000AAA0
0x18000aa9b  lea     ebx, [rax+1]
0x18000aa9e  jmp     short loc_18000AAAF
0x18000aaa0  mov     r8, rsi
0x18000aaa3  mov     edx, edi
0x18000aaa5  mov     rcx, r14
0x18000aaa8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aaad  mov     ebx, eax
0x18000aaaf  mov     [rsp+58h+var_28], ebx
0x18000aab3  jmp     short loc_18000AABB
0x18000aab5  xor     ebx, ebx
0x18000aab7  mov     [rsp+58h+var_28], ebx
0x18000aabb  mov     eax, ebx
0x18000aabd  mov     rbx, [rsp+58h+arg_18]
0x18000aac2  add     rsp, 40h
0x18000aac6  pop     r14
0x18000aac8  pop     rdi
0x18000aac9  pop     rsi
0x18000aaca  retn
0x18002a08c  push    rbp
0x18002a08e  sub     rsp, 30h
0x18002a092  mov     rbp, rdx
0x18002a095  mov     rax, [rcx]
0x18002a098  mov     edx, [rax]
0x18002a09a  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x18002a09f  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x18002a0a3  lea     r9, dllmain_crt_dispatch; int
0x18002a0aa  mov     r8, [rbp+70h]; int
0x18002a0ae  mov     edx, [rbp+68h]; int
0x18002a0b1  mov     rcx, [rbp+60h]; int
0x18002a0b5  call    __scrt_dllmain_exception_filter
0x18002a0ba  nop
0x18002a0bb  add     rsp, 30h
0x18002a0bf  pop     rbp
0x18002a0c0  retn
```
