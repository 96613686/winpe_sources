# dllmain_dispatch

- ea: `0x180002984`
- end: `0x180002aab`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180002ac0`

## callees

- `0x1800027a0`
- `0x180002984`
- `0x180002c0c`
- `0x180007aa8`
- `0x18001b010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_180026310 <= 0 )
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
0x180002984  mov     rax, rsp
0x180002987  mov     [rax+20h], rbx
0x18000298b  mov     [rax+18h], r8
0x18000298f  mov     [rax+10h], edx
0x180002992  mov     [rax+8], rcx
0x180002996  push    rsi
0x180002997  push    rdi
0x180002998  push    r14
0x18000299a  sub     rsp, 40h
0x18000299e  mov     rsi, r8
0x1800029a1  mov     edi, edx
0x1800029a3  mov     r14, rcx
0x1800029a6  test    edx, edx
0x1800029a8  jnz     short loc_1800029B9
0x1800029aa  cmp     cs:dword_180026310, edx
0x1800029b0  jg      short loc_1800029B9
0x1800029b2  xor     eax, eax
0x1800029b4  jmp     loc_180002A9D
0x1800029b9  lea     eax, [rdx-1]
0x1800029bc  cmp     eax, 1
0x1800029bf  ja      short loc_180002A00
0x1800029c1  mov     rax, cs:_pRawDllMain
0x1800029c8  test    rax, rax
0x1800029cb  jnz     short loc_1800029D2
0x1800029cd  lea     ebx, [rax+1]
0x1800029d0  jmp     short loc_1800029D9
0x1800029d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800029d7  mov     ebx, eax
0x1800029d9  mov     [rsp+58h+var_28], ebx
0x1800029dd  test    ebx, ebx
0x1800029df  jz      loc_180002A93
0x1800029e5  mov     r8, rsi
0x1800029e8  mov     edx, edi
0x1800029ea  mov     rcx, r14
0x1800029ed  call    dllmain_crt_dispatch
0x1800029f2  mov     ebx, eax
0x1800029f4  mov     [rsp+58h+var_28], eax
0x1800029f8  test    eax, eax
0x1800029fa  jz      loc_180002A93
0x180002a00  mov     r8, rsi; lpvReserved
0x180002a03  mov     edx, edi; fdwReason
0x180002a05  mov     rcx, r14; hinstDLL
0x180002a08  call    DllMain
0x180002a0d  mov     ebx, eax
0x180002a0f  mov     [rsp+58h+var_28], eax
0x180002a13  cmp     edi, 1
0x180002a16  jnz     short loc_180002A4F
0x180002a18  test    eax, eax
0x180002a1a  jnz     short loc_180002A4F
0x180002a1c  mov     r8, rsi; lpvReserved
0x180002a1f  xor     edx, edx; fdwReason
0x180002a21  mov     rcx, r14; hinstDLL
0x180002a24  call    DllMain
0x180002a29  mov     r8, rsi
0x180002a2c  xor     edx, edx
0x180002a2e  mov     rcx, r14
0x180002a31  call    dllmain_crt_dispatch
0x180002a36  mov     rax, cs:_pRawDllMain
0x180002a3d  test    rax, rax
0x180002a40  jz      short loc_180002A4F
0x180002a42  mov     r8, rsi
0x180002a45  xor     edx, edx
0x180002a47  mov     rcx, r14
0x180002a4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002a4f  test    edi, edi
0x180002a51  jz      short loc_180002A58
0x180002a53  cmp     edi, 3
0x180002a56  jnz     short loc_180002A93
0x180002a58  mov     r8, rsi
0x180002a5b  mov     edx, edi
0x180002a5d  mov     rcx, r14
0x180002a60  call    dllmain_crt_dispatch
0x180002a65  mov     ebx, eax
0x180002a67  mov     [rsp+58h+var_28], eax
0x180002a6b  test    eax, eax
0x180002a6d  jz      short loc_180002A93
0x180002a6f  mov     rax, cs:_pRawDllMain
0x180002a76  test    rax, rax
0x180002a79  jnz     short loc_180002A80
0x180002a7b  lea     ebx, [rax+1]
0x180002a7e  jmp     short loc_180002A8F
0x180002a80  mov     r8, rsi
0x180002a83  mov     edx, edi
0x180002a85  mov     rcx, r14
0x180002a88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002a8d  mov     ebx, eax
0x180002a8f  mov     [rsp+58h+var_28], ebx
0x180002a93  jmp     short loc_180002A9B
0x180002a95  xor     ebx, ebx
0x180002a97  mov     [rsp+58h+var_28], ebx
0x180002a9b  mov     eax, ebx
0x180002a9d  mov     rbx, [rsp+58h+arg_18]
0x180002aa2  add     rsp, 40h
0x180002aa6  pop     r14
0x180002aa8  pop     rdi
0x180002aa9  pop     rsi
0x180002aaa  retn
0x18001883c  push    rbp
0x18001883e  sub     rsp, 30h
0x180018842  mov     rbp, rdx
0x180018845  mov     rax, [rcx]
0x180018848  mov     edx, [rax]
0x18001884a  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x18001884f  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x180018853  lea     r9, dllmain_crt_dispatch; int
0x18001885a  mov     r8, [rbp+70h]; int
0x18001885e  mov     edx, [rbp+68h]; int
0x180018861  mov     rcx, [rbp+60h]; int
0x180018865  call    __scrt_dllmain_exception_filter
0x18001886a  nop
0x18001886b  add     rsp, 30h
0x18001886f  pop     rbp
0x180018870  retn
```
