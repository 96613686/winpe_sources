# dllmain_dispatch

- ea: `0x180001a14`
- end: `0x180001b3b`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180001b50`

## callees

- `0x180001830`
- `0x180001a14`
- `0x180001c9c`
- `0x18000b11c`
- `0x18000e010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_180018590 <= 0 )
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
0x180001a14  mov     rax, rsp
0x180001a17  mov     [rax+20h], rbx
0x180001a1b  mov     [rax+18h], r8
0x180001a1f  mov     [rax+10h], edx
0x180001a22  mov     [rax+8], rcx
0x180001a26  push    rsi
0x180001a27  push    rdi
0x180001a28  push    r14
0x180001a2a  sub     rsp, 40h
0x180001a2e  mov     rsi, r8
0x180001a31  mov     edi, edx
0x180001a33  mov     r14, rcx
0x180001a36  test    edx, edx
0x180001a38  jnz     short loc_180001A49
0x180001a3a  cmp     cs:dword_180018590, edx
0x180001a40  jg      short loc_180001A49
0x180001a42  xor     eax, eax
0x180001a44  jmp     loc_180001B2D
0x180001a49  lea     eax, [rdx-1]
0x180001a4c  cmp     eax, 1
0x180001a4f  ja      short loc_180001A90
0x180001a51  mov     rax, cs:_pRawDllMain
0x180001a58  test    rax, rax
0x180001a5b  jnz     short loc_180001A62
0x180001a5d  lea     ebx, [rax+1]
0x180001a60  jmp     short loc_180001A69
0x180001a62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001a67  mov     ebx, eax
0x180001a69  mov     [rsp+58h+var_28], ebx
0x180001a6d  test    ebx, ebx
0x180001a6f  jz      loc_180001B23
0x180001a75  mov     r8, rsi
0x180001a78  mov     edx, edi
0x180001a7a  mov     rcx, r14
0x180001a7d  call    dllmain_crt_dispatch
0x180001a82  mov     ebx, eax
0x180001a84  mov     [rsp+58h+var_28], eax
0x180001a88  test    eax, eax
0x180001a8a  jz      loc_180001B23
0x180001a90  mov     r8, rsi; lpvReserved
0x180001a93  mov     edx, edi; fdwReason
0x180001a95  mov     rcx, r14; hinstDLL
0x180001a98  call    DllMain
0x180001a9d  mov     ebx, eax
0x180001a9f  mov     [rsp+58h+var_28], eax
0x180001aa3  cmp     edi, 1
0x180001aa6  jnz     short loc_180001ADF
0x180001aa8  test    eax, eax
0x180001aaa  jnz     short loc_180001ADF
0x180001aac  mov     r8, rsi; lpvReserved
0x180001aaf  xor     edx, edx; fdwReason
0x180001ab1  mov     rcx, r14; hinstDLL
0x180001ab4  call    DllMain
0x180001ab9  mov     r8, rsi
0x180001abc  xor     edx, edx
0x180001abe  mov     rcx, r14
0x180001ac1  call    dllmain_crt_dispatch
0x180001ac6  mov     rax, cs:_pRawDllMain
0x180001acd  test    rax, rax
0x180001ad0  jz      short loc_180001ADF
0x180001ad2  mov     r8, rsi
0x180001ad5  xor     edx, edx
0x180001ad7  mov     rcx, r14
0x180001ada  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001adf  test    edi, edi
0x180001ae1  jz      short loc_180001AE8
0x180001ae3  cmp     edi, 3
0x180001ae6  jnz     short loc_180001B23
0x180001ae8  mov     r8, rsi
0x180001aeb  mov     edx, edi
0x180001aed  mov     rcx, r14
0x180001af0  call    dllmain_crt_dispatch
0x180001af5  mov     ebx, eax
0x180001af7  mov     [rsp+58h+var_28], eax
0x180001afb  test    eax, eax
0x180001afd  jz      short loc_180001B23
0x180001aff  mov     rax, cs:_pRawDllMain
0x180001b06  test    rax, rax
0x180001b09  jnz     short loc_180001B10
0x180001b0b  lea     ebx, [rax+1]
0x180001b0e  jmp     short loc_180001B1F
0x180001b10  mov     r8, rsi
0x180001b13  mov     edx, edi
0x180001b15  mov     rcx, r14
0x180001b18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001b1d  mov     ebx, eax
0x180001b1f  mov     [rsp+58h+var_28], ebx
0x180001b23  jmp     short loc_180001B2B
0x180001b25  xor     ebx, ebx
0x180001b27  mov     [rsp+58h+var_28], ebx
0x180001b2b  mov     eax, ebx
0x180001b2d  mov     rbx, [rsp+58h+arg_18]
0x180001b32  add     rsp, 40h
0x180001b36  pop     r14
0x180001b38  pop     rdi
0x180001b39  pop     rsi
0x180001b3a  retn
0x18000d68c  push    rbp
0x18000d68e  sub     rsp, 30h
0x18000d692  mov     rbp, rdx
0x18000d695  mov     rax, [rcx]
0x18000d698  mov     edx, [rax]
0x18000d69a  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x18000d69f  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x18000d6a3  lea     r9, dllmain_crt_dispatch; int
0x18000d6aa  mov     r8, [rbp+70h]; int
0x18000d6ae  mov     edx, [rbp+68h]; int
0x18000d6b1  mov     rcx, [rbp+60h]; int
0x18000d6b5  call    __scrt_dllmain_exception_filter
0x18000d6ba  nop
0x18000d6bb  add     rsp, 30h
0x18000d6bf  pop     rbp
0x18000d6c0  retn
```
