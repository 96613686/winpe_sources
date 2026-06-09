# dllmain_dispatch

- ea: `0x180014c34`
- end: `0x180014d5b`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180014d70`

## callees

- `0x180012fdc`
- `0x180014a50`
- `0x180014c34`
- `0x180014ff0`
- `0x18001c010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_180021090 <= 0 )
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
0x180014c34  mov     rax, rsp
0x180014c37  mov     [rax+20h], rbx
0x180014c3b  mov     [rax+18h], r8
0x180014c3f  mov     [rax+10h], edx
0x180014c42  mov     [rax+8], rcx
0x180014c46  push    rsi
0x180014c47  push    rdi
0x180014c48  push    r14
0x180014c4a  sub     rsp, 40h
0x180014c4e  mov     rsi, r8
0x180014c51  mov     edi, edx
0x180014c53  mov     r14, rcx
0x180014c56  test    edx, edx
0x180014c58  jnz     short loc_180014C69
0x180014c5a  cmp     cs:dword_180021090, edx
0x180014c60  jg      short loc_180014C69
0x180014c62  xor     eax, eax
0x180014c64  jmp     loc_180014D4D
0x180014c69  lea     eax, [rdx-1]
0x180014c6c  cmp     eax, 1
0x180014c6f  ja      short loc_180014CB0
0x180014c71  mov     rax, cs:_pRawDllMain
0x180014c78  test    rax, rax
0x180014c7b  jnz     short loc_180014C82
0x180014c7d  lea     ebx, [rax+1]
0x180014c80  jmp     short loc_180014C89
0x180014c82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014c87  mov     ebx, eax
0x180014c89  mov     [rsp+58h+var_28], ebx
0x180014c8d  test    ebx, ebx
0x180014c8f  jz      loc_180014D43
0x180014c95  mov     r8, rsi
0x180014c98  mov     edx, edi
0x180014c9a  mov     rcx, r14
0x180014c9d  call    dllmain_crt_dispatch
0x180014ca2  mov     ebx, eax
0x180014ca4  mov     [rsp+58h+var_28], eax
0x180014ca8  test    eax, eax
0x180014caa  jz      loc_180014D43
0x180014cb0  mov     r8, rsi; lpvReserved
0x180014cb3  mov     edx, edi; fdwReason
0x180014cb5  mov     rcx, r14; hinstDLL
0x180014cb8  call    DllMain
0x180014cbd  mov     ebx, eax
0x180014cbf  mov     [rsp+58h+var_28], eax
0x180014cc3  cmp     edi, 1
0x180014cc6  jnz     short loc_180014CFF
0x180014cc8  test    eax, eax
0x180014cca  jnz     short loc_180014CFF
0x180014ccc  mov     r8, rsi; lpvReserved
0x180014ccf  xor     edx, edx; fdwReason
0x180014cd1  mov     rcx, r14; hinstDLL
0x180014cd4  call    DllMain
0x180014cd9  mov     r8, rsi
0x180014cdc  xor     edx, edx
0x180014cde  mov     rcx, r14
0x180014ce1  call    dllmain_crt_dispatch
0x180014ce6  mov     rax, cs:_pRawDllMain
0x180014ced  test    rax, rax
0x180014cf0  jz      short loc_180014CFF
0x180014cf2  mov     r8, rsi
0x180014cf5  xor     edx, edx
0x180014cf7  mov     rcx, r14
0x180014cfa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014cff  test    edi, edi
0x180014d01  jz      short loc_180014D08
0x180014d03  cmp     edi, 3
0x180014d06  jnz     short loc_180014D43
0x180014d08  mov     r8, rsi
0x180014d0b  mov     edx, edi
0x180014d0d  mov     rcx, r14
0x180014d10  call    dllmain_crt_dispatch
0x180014d15  mov     ebx, eax
0x180014d17  mov     [rsp+58h+var_28], eax
0x180014d1b  test    eax, eax
0x180014d1d  jz      short loc_180014D43
0x180014d1f  mov     rax, cs:_pRawDllMain
0x180014d26  test    rax, rax
0x180014d29  jnz     short loc_180014D30
0x180014d2b  lea     ebx, [rax+1]
0x180014d2e  jmp     short loc_180014D3F
0x180014d30  mov     r8, rsi
0x180014d33  mov     edx, edi
0x180014d35  mov     rcx, r14
0x180014d38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014d3d  mov     ebx, eax
0x180014d3f  mov     [rsp+58h+var_28], ebx
0x180014d43  jmp     short loc_180014D4B
0x180014d45  xor     ebx, ebx
0x180014d47  mov     [rsp+58h+var_28], ebx
0x180014d4b  mov     eax, ebx
0x180014d4d  mov     rbx, [rsp+58h+arg_18]
0x180014d52  add     rsp, 40h
0x180014d56  pop     r14
0x180014d58  pop     rdi
0x180014d59  pop     rsi
0x180014d5a  retn
0x18001b6fc  push    rbp
0x18001b6fe  sub     rsp, 30h
0x18001b702  mov     rbp, rdx
0x18001b705  mov     rax, [rcx]
0x18001b708  mov     edx, [rax]
0x18001b70a  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x18001b70f  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x18001b713  lea     r9, dllmain_crt_dispatch; int
0x18001b71a  mov     r8, [rbp+70h]; int
0x18001b71e  mov     edx, [rbp+68h]; int
0x18001b721  mov     rcx, [rbp+60h]; int
0x18001b725  call    __scrt_dllmain_exception_filter
0x18001b72a  nop
0x18001b72b  add     rsp, 30h
0x18001b72f  pop     rbp
0x18001b730  retn
```
