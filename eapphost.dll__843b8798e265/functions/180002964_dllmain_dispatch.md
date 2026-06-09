# dllmain_dispatch

- ea: `0x180002964`
- end: `0x180002a8b`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180002aa0`

## callees

- `0x180002780`
- `0x180002964`
- `0x180002c24`
- `0x18000df6c`
- `0x180039010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_18004F1D0 <= 0 )
    return 0;
  if ( fdwReason - 1 > 1
    || (pRawDllMain ? (v7 = pRawDllMain()) : (v7 = 1),
        v7 && (v7 = dllmain_crt_dispatch(hinstDLL, fdwReason, lpvReserved)) != 0) )
  {
    v8 = DllMain(hinstDLL, fdwReason, lpvReserved);
    v7 = v8;
    if ( fdwReason == 1 && !v8 )
    {
      DllMain(hinstDLL, 0, lpvReserved);
      dllmain_crt_dispatch(hinstDLL, 0, lpvReserved);
      if ( pRawDllMain )
        pRawDllMain();
    }
    if ( !fdwReason || fdwReason == 3 )
    {
      v7 = dllmain_crt_dispatch(hinstDLL, fdwReason, lpvReserved);
      if ( v7 )
      {
        if ( pRawDllMain )
          return (unsigned int)pRawDllMain();
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
0x180002964  mov     rax, rsp
0x180002967  mov     [rax+20h], rbx
0x18000296b  mov     [rax+18h], r8
0x18000296f  mov     [rax+10h], edx
0x180002972  mov     [rax+8], rcx
0x180002976  push    rsi
0x180002977  push    rdi
0x180002978  push    r14
0x18000297a  sub     rsp, 40h
0x18000297e  mov     rsi, r8
0x180002981  mov     edi, edx
0x180002983  mov     r14, rcx
0x180002986  test    edx, edx
0x180002988  jnz     short loc_180002999
0x18000298a  cmp     cs:dword_18004F1D0, edx
0x180002990  jg      short loc_180002999
0x180002992  xor     eax, eax
0x180002994  jmp     loc_180002A7D
0x180002999  lea     eax, [rdx-1]
0x18000299c  cmp     eax, 1
0x18000299f  ja      short loc_1800029E0
0x1800029a1  mov     rax, cs:_pRawDllMain
0x1800029a8  test    rax, rax
0x1800029ab  jnz     short loc_1800029B2
0x1800029ad  lea     ebx, [rax+1]
0x1800029b0  jmp     short loc_1800029B9
0x1800029b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800029b7  mov     ebx, eax
0x1800029b9  mov     [rsp+58h+var_28], ebx
0x1800029bd  test    ebx, ebx
0x1800029bf  jz      loc_180002A73
0x1800029c5  mov     r8, rsi
0x1800029c8  mov     edx, edi
0x1800029ca  mov     rcx, r14
0x1800029cd  call    dllmain_crt_dispatch
0x1800029d2  mov     ebx, eax
0x1800029d4  mov     [rsp+58h+var_28], eax
0x1800029d8  test    eax, eax
0x1800029da  jz      loc_180002A73
0x1800029e0  mov     r8, rsi; lpvReserved
0x1800029e3  mov     edx, edi; fdwReason
0x1800029e5  mov     rcx, r14; hinstDLL
0x1800029e8  call    DllMain
0x1800029ed  mov     ebx, eax
0x1800029ef  mov     [rsp+58h+var_28], eax
0x1800029f3  cmp     edi, 1
0x1800029f6  jnz     short loc_180002A2F
0x1800029f8  test    eax, eax
0x1800029fa  jnz     short loc_180002A2F
0x1800029fc  mov     r8, rsi; lpvReserved
0x1800029ff  xor     edx, edx; fdwReason
0x180002a01  mov     rcx, r14; hinstDLL
0x180002a04  call    DllMain
0x180002a09  mov     r8, rsi
0x180002a0c  xor     edx, edx
0x180002a0e  mov     rcx, r14
0x180002a11  call    dllmain_crt_dispatch
0x180002a16  mov     rax, cs:_pRawDllMain
0x180002a1d  test    rax, rax
0x180002a20  jz      short loc_180002A2F
0x180002a22  mov     r8, rsi
0x180002a25  xor     edx, edx
0x180002a27  mov     rcx, r14
0x180002a2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002a2f  test    edi, edi
0x180002a31  jz      short loc_180002A38
0x180002a33  cmp     edi, 3
0x180002a36  jnz     short loc_180002A73
0x180002a38  mov     r8, rsi
0x180002a3b  mov     edx, edi
0x180002a3d  mov     rcx, r14
0x180002a40  call    dllmain_crt_dispatch
0x180002a45  mov     ebx, eax
0x180002a47  mov     [rsp+58h+var_28], eax
0x180002a4b  test    eax, eax
0x180002a4d  jz      short loc_180002A73
0x180002a4f  mov     rax, cs:_pRawDllMain
0x180002a56  test    rax, rax
0x180002a59  jnz     short loc_180002A60
0x180002a5b  lea     ebx, [rax+1]
0x180002a5e  jmp     short loc_180002A6F
0x180002a60  mov     r8, rsi
0x180002a63  mov     edx, edi
0x180002a65  mov     rcx, r14
0x180002a68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002a6d  mov     ebx, eax
0x180002a6f  mov     [rsp+58h+var_28], ebx
0x180002a73  jmp     short loc_180002A7B
0x180002a75  xor     ebx, ebx
0x180002a77  mov     [rsp+58h+var_28], ebx
0x180002a7b  mov     eax, ebx
0x180002a7d  mov     rbx, [rsp+58h+arg_18]
0x180002a82  add     rsp, 40h
0x180002a86  pop     r14
0x180002a88  pop     rdi
0x180002a89  pop     rsi
0x180002a8a  retn
0x18003520c  push    rbp
0x18003520e  sub     rsp, 30h
0x180035212  mov     rbp, rdx
0x180035215  mov     rax, [rcx]
0x180035218  mov     edx, [rax]
0x18003521a  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x18003521f  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x180035223  lea     r9, dllmain_crt_dispatch; int
0x18003522a  mov     r8, [rbp+70h]; int
0x18003522e  mov     edx, [rbp+68h]; int
0x180035231  mov     rcx, [rbp+60h]; int
0x180035235  call    __scrt_dllmain_exception_filter
0x18003523a  nop
0x18003523b  add     rsp, 30h
0x18003523f  pop     rbp
0x180035240  retn
```
