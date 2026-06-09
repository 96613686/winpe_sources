# dllmain_dispatch

- ea: `0x180001a54`
- end: `0x180001b7b`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180001b90`

## callees

- `0x180001870`
- `0x180001a54`
- `0x180001d20`
- `0x1800078cc`
- `0x180009010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_18000E230 <= 0 )
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
0x180001a54  mov     rax, rsp
0x180001a57  mov     [rax+20h], rbx
0x180001a5b  mov     [rax+18h], r8
0x180001a5f  mov     [rax+10h], edx
0x180001a62  mov     [rax+8], rcx
0x180001a66  push    rsi
0x180001a67  push    rdi
0x180001a68  push    r14
0x180001a6a  sub     rsp, 40h
0x180001a6e  mov     rsi, r8
0x180001a71  mov     edi, edx
0x180001a73  mov     r14, rcx
0x180001a76  test    edx, edx
0x180001a78  jnz     short loc_180001A89
0x180001a7a  cmp     cs:dword_18000E230, edx
0x180001a80  jg      short loc_180001A89
0x180001a82  xor     eax, eax
0x180001a84  jmp     loc_180001B6D
0x180001a89  lea     eax, [rdx-1]
0x180001a8c  cmp     eax, 1
0x180001a8f  ja      short loc_180001AD0
0x180001a91  mov     rax, cs:_pRawDllMain
0x180001a98  test    rax, rax
0x180001a9b  jnz     short loc_180001AA2
0x180001a9d  lea     ebx, [rax+1]
0x180001aa0  jmp     short loc_180001AA9
0x180001aa2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001aa7  mov     ebx, eax
0x180001aa9  mov     [rsp+58h+var_28], ebx
0x180001aad  test    ebx, ebx
0x180001aaf  jz      loc_180001B63
0x180001ab5  mov     r8, rsi
0x180001ab8  mov     edx, edi
0x180001aba  mov     rcx, r14
0x180001abd  call    dllmain_crt_dispatch
0x180001ac2  mov     ebx, eax
0x180001ac4  mov     [rsp+58h+var_28], eax
0x180001ac8  test    eax, eax
0x180001aca  jz      loc_180001B63
0x180001ad0  mov     r8, rsi; lpvReserved
0x180001ad3  mov     edx, edi; fdwReason
0x180001ad5  mov     rcx, r14; hinstDLL
0x180001ad8  call    DllMain
0x180001add  mov     ebx, eax
0x180001adf  mov     [rsp+58h+var_28], eax
0x180001ae3  cmp     edi, 1
0x180001ae6  jnz     short loc_180001B1F
0x180001ae8  test    eax, eax
0x180001aea  jnz     short loc_180001B1F
0x180001aec  mov     r8, rsi; lpvReserved
0x180001aef  xor     edx, edx; fdwReason
0x180001af1  mov     rcx, r14; hinstDLL
0x180001af4  call    DllMain
0x180001af9  mov     r8, rsi
0x180001afc  xor     edx, edx
0x180001afe  mov     rcx, r14
0x180001b01  call    dllmain_crt_dispatch
0x180001b06  mov     rax, cs:_pRawDllMain
0x180001b0d  test    rax, rax
0x180001b10  jz      short loc_180001B1F
0x180001b12  mov     r8, rsi
0x180001b15  xor     edx, edx
0x180001b17  mov     rcx, r14
0x180001b1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001b1f  test    edi, edi
0x180001b21  jz      short loc_180001B28
0x180001b23  cmp     edi, 3
0x180001b26  jnz     short loc_180001B63
0x180001b28  mov     r8, rsi
0x180001b2b  mov     edx, edi
0x180001b2d  mov     rcx, r14
0x180001b30  call    dllmain_crt_dispatch
0x180001b35  mov     ebx, eax
0x180001b37  mov     [rsp+58h+var_28], eax
0x180001b3b  test    eax, eax
0x180001b3d  jz      short loc_180001B63
0x180001b3f  mov     rax, cs:_pRawDllMain
0x180001b46  test    rax, rax
0x180001b49  jnz     short loc_180001B50
0x180001b4b  lea     ebx, [rax+1]
0x180001b4e  jmp     short loc_180001B5F
0x180001b50  mov     r8, rsi
0x180001b53  mov     edx, edi
0x180001b55  mov     rcx, r14
0x180001b58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001b5d  mov     ebx, eax
0x180001b5f  mov     [rsp+58h+var_28], ebx
0x180001b63  jmp     short loc_180001B6B
0x180001b65  xor     ebx, ebx
0x180001b67  mov     [rsp+58h+var_28], ebx
0x180001b6b  mov     eax, ebx
0x180001b6d  mov     rbx, [rsp+58h+arg_18]
0x180001b72  add     rsp, 40h
0x180001b76  pop     r14
0x180001b78  pop     rdi
0x180001b79  pop     rsi
0x180001b7a  retn
0x180007f8c  push    rbp
0x180007f8e  sub     rsp, 30h
0x180007f92  mov     rbp, rdx
0x180007f95  mov     rax, [rcx]
0x180007f98  mov     edx, [rax]
0x180007f9a  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x180007f9f  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x180007fa3  lea     r9, dllmain_crt_dispatch; int
0x180007faa  mov     r8, [rbp+70h]; int
0x180007fae  mov     edx, [rbp+68h]; int
0x180007fb1  mov     rcx, [rbp+60h]; int
0x180007fb5  call    __scrt_dllmain_exception_filter
0x180007fba  nop
0x180007fbb  add     rsp, 30h
0x180007fbf  pop     rbp
0x180007fc0  retn
```
