# dllmain_dispatch

- ea: `0x180001a24`
- end: `0x180001b4b`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180001b60`

## callees

- `0x180001840`
- `0x180001a24`
- `0x180001d54`
- `0x1800033a8`
- `0x18002d010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_18003DD90 <= 0 )
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
0x180001a24  mov     rax, rsp
0x180001a27  mov     [rax+20h], rbx
0x180001a2b  mov     [rax+18h], r8
0x180001a2f  mov     [rax+10h], edx
0x180001a32  mov     [rax+8], rcx
0x180001a36  push    rsi
0x180001a37  push    rdi
0x180001a38  push    r14
0x180001a3a  sub     rsp, 40h
0x180001a3e  mov     rsi, r8
0x180001a41  mov     edi, edx
0x180001a43  mov     r14, rcx
0x180001a46  test    edx, edx
0x180001a48  jnz     short loc_180001A59
0x180001a4a  cmp     cs:dword_18003DD90, edx
0x180001a50  jg      short loc_180001A59
0x180001a52  xor     eax, eax
0x180001a54  jmp     loc_180001B3D
0x180001a59  lea     eax, [rdx-1]
0x180001a5c  cmp     eax, 1
0x180001a5f  ja      short loc_180001AA0
0x180001a61  mov     rax, cs:_pRawDllMain
0x180001a68  test    rax, rax
0x180001a6b  jnz     short loc_180001A72
0x180001a6d  lea     ebx, [rax+1]
0x180001a70  jmp     short loc_180001A79
0x180001a72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001a77  mov     ebx, eax
0x180001a79  mov     [rsp+58h+var_28], ebx
0x180001a7d  test    ebx, ebx
0x180001a7f  jz      loc_180001B33
0x180001a85  mov     r8, rsi
0x180001a88  mov     edx, edi
0x180001a8a  mov     rcx, r14
0x180001a8d  call    dllmain_crt_dispatch
0x180001a92  mov     ebx, eax
0x180001a94  mov     [rsp+58h+var_28], eax
0x180001a98  test    eax, eax
0x180001a9a  jz      loc_180001B33
0x180001aa0  mov     r8, rsi; lpvReserved
0x180001aa3  mov     edx, edi; fdwReason
0x180001aa5  mov     rcx, r14; hinstDLL
0x180001aa8  call    DllMain
0x180001aad  mov     ebx, eax
0x180001aaf  mov     [rsp+58h+var_28], eax
0x180001ab3  cmp     edi, 1
0x180001ab6  jnz     short loc_180001AEF
0x180001ab8  test    eax, eax
0x180001aba  jnz     short loc_180001AEF
0x180001abc  mov     r8, rsi; lpvReserved
0x180001abf  xor     edx, edx; fdwReason
0x180001ac1  mov     rcx, r14; hinstDLL
0x180001ac4  call    DllMain
0x180001ac9  mov     r8, rsi
0x180001acc  xor     edx, edx
0x180001ace  mov     rcx, r14
0x180001ad1  call    dllmain_crt_dispatch
0x180001ad6  mov     rax, cs:_pRawDllMain
0x180001add  test    rax, rax
0x180001ae0  jz      short loc_180001AEF
0x180001ae2  mov     r8, rsi
0x180001ae5  xor     edx, edx
0x180001ae7  mov     rcx, r14
0x180001aea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001aef  test    edi, edi
0x180001af1  jz      short loc_180001AF8
0x180001af3  cmp     edi, 3
0x180001af6  jnz     short loc_180001B33
0x180001af8  mov     r8, rsi
0x180001afb  mov     edx, edi
0x180001afd  mov     rcx, r14
0x180001b00  call    dllmain_crt_dispatch
0x180001b05  mov     ebx, eax
0x180001b07  mov     [rsp+58h+var_28], eax
0x180001b0b  test    eax, eax
0x180001b0d  jz      short loc_180001B33
0x180001b0f  mov     rax, cs:_pRawDllMain
0x180001b16  test    rax, rax
0x180001b19  jnz     short loc_180001B20
0x180001b1b  lea     ebx, [rax+1]
0x180001b1e  jmp     short loc_180001B2F
0x180001b20  mov     r8, rsi
0x180001b23  mov     edx, edi
0x180001b25  mov     rcx, r14
0x180001b28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001b2d  mov     ebx, eax
0x180001b2f  mov     [rsp+58h+var_28], ebx
0x180001b33  jmp     short loc_180001B3B
0x180001b35  xor     ebx, ebx
0x180001b37  mov     [rsp+58h+var_28], ebx
0x180001b3b  mov     eax, ebx
0x180001b3d  mov     rbx, [rsp+58h+arg_18]
0x180001b42  add     rsp, 40h
0x180001b46  pop     r14
0x180001b48  pop     rdi
0x180001b49  pop     rsi
0x180001b4a  retn
0x18002c30c  push    rbp
0x18002c30e  sub     rsp, 30h
0x18002c312  mov     rbp, rdx
0x18002c315  mov     rax, [rcx]
0x18002c318  mov     edx, [rax]
0x18002c31a  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x18002c31f  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x18002c323  lea     r9, dllmain_crt_dispatch; int
0x18002c32a  mov     r8, [rbp+70h]; int
0x18002c32e  mov     edx, [rbp+68h]; int
0x18002c331  mov     rcx, [rbp+60h]; int
0x18002c335  call    __scrt_dllmain_exception_filter
0x18002c33a  nop
0x18002c33b  add     rsp, 30h
0x18002c33f  pop     rbp
0x18002c340  retn
```
