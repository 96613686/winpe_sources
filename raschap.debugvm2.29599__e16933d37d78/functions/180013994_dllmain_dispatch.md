# dllmain_dispatch

- ea: `0x180013994`
- end: `0x180013abb`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180013ad0`

## callees

- `0x18000ae60`
- `0x1800137b0`
- `0x180013994`
- `0x180013cb4`
- `0x180027010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_1800335D0 <= 0 )
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
0x180013994  mov     rax, rsp
0x180013997  mov     [rax+20h], rbx
0x18001399b  mov     [rax+18h], r8
0x18001399f  mov     [rax+10h], edx
0x1800139a2  mov     [rax+8], rcx
0x1800139a6  push    rsi
0x1800139a7  push    rdi
0x1800139a8  push    r14
0x1800139aa  sub     rsp, 40h
0x1800139ae  mov     rsi, r8
0x1800139b1  mov     edi, edx
0x1800139b3  mov     r14, rcx
0x1800139b6  test    edx, edx
0x1800139b8  jnz     short loc_1800139C9
0x1800139ba  cmp     cs:dword_1800335D0, edx
0x1800139c0  jg      short loc_1800139C9
0x1800139c2  xor     eax, eax
0x1800139c4  jmp     loc_180013AAD
0x1800139c9  lea     eax, [rdx-1]
0x1800139cc  cmp     eax, 1
0x1800139cf  ja      short loc_180013A10
0x1800139d1  mov     rax, cs:_pRawDllMain
0x1800139d8  test    rax, rax
0x1800139db  jnz     short loc_1800139E2
0x1800139dd  lea     ebx, [rax+1]
0x1800139e0  jmp     short loc_1800139E9
0x1800139e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800139e7  mov     ebx, eax
0x1800139e9  mov     [rsp+58h+var_28], ebx
0x1800139ed  test    ebx, ebx
0x1800139ef  jz      loc_180013AA3
0x1800139f5  mov     r8, rsi
0x1800139f8  mov     edx, edi
0x1800139fa  mov     rcx, r14
0x1800139fd  call    dllmain_crt_dispatch
0x180013a02  mov     ebx, eax
0x180013a04  mov     [rsp+58h+var_28], eax
0x180013a08  test    eax, eax
0x180013a0a  jz      loc_180013AA3
0x180013a10  mov     r8, rsi; lpvReserved
0x180013a13  mov     edx, edi; fdwReason
0x180013a15  mov     rcx, r14; hinstDLL
0x180013a18  call    DllMain
0x180013a1d  mov     ebx, eax
0x180013a1f  mov     [rsp+58h+var_28], eax
0x180013a23  cmp     edi, 1
0x180013a26  jnz     short loc_180013A5F
0x180013a28  test    eax, eax
0x180013a2a  jnz     short loc_180013A5F
0x180013a2c  mov     r8, rsi; lpvReserved
0x180013a2f  xor     edx, edx; fdwReason
0x180013a31  mov     rcx, r14; hinstDLL
0x180013a34  call    DllMain
0x180013a39  mov     r8, rsi
0x180013a3c  xor     edx, edx
0x180013a3e  mov     rcx, r14
0x180013a41  call    dllmain_crt_dispatch
0x180013a46  mov     rax, cs:_pRawDllMain
0x180013a4d  test    rax, rax
0x180013a50  jz      short loc_180013A5F
0x180013a52  mov     r8, rsi
0x180013a55  xor     edx, edx
0x180013a57  mov     rcx, r14
0x180013a5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013a5f  test    edi, edi
0x180013a61  jz      short loc_180013A68
0x180013a63  cmp     edi, 3
0x180013a66  jnz     short loc_180013AA3
0x180013a68  mov     r8, rsi
0x180013a6b  mov     edx, edi
0x180013a6d  mov     rcx, r14
0x180013a70  call    dllmain_crt_dispatch
0x180013a75  mov     ebx, eax
0x180013a77  mov     [rsp+58h+var_28], eax
0x180013a7b  test    eax, eax
0x180013a7d  jz      short loc_180013AA3
0x180013a7f  mov     rax, cs:_pRawDllMain
0x180013a86  test    rax, rax
0x180013a89  jnz     short loc_180013A90
0x180013a8b  lea     ebx, [rax+1]
0x180013a8e  jmp     short loc_180013A9F
0x180013a90  mov     r8, rsi
0x180013a93  mov     edx, edi
0x180013a95  mov     rcx, r14
0x180013a98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013a9d  mov     ebx, eax
0x180013a9f  mov     [rsp+58h+var_28], ebx
0x180013aa3  jmp     short loc_180013AAB
0x180013aa5  xor     ebx, ebx
0x180013aa7  mov     [rsp+58h+var_28], ebx
0x180013aab  mov     eax, ebx
0x180013aad  mov     rbx, [rsp+58h+arg_18]
0x180013ab2  add     rsp, 40h
0x180013ab6  pop     r14
0x180013ab8  pop     rdi
0x180013ab9  pop     rsi
0x180013aba  retn
0x1800261c2  push    rbp
0x1800261c4  sub     rsp, 30h
0x1800261c8  mov     rbp, rdx
0x1800261cb  mov     rax, [rcx]
0x1800261ce  mov     edx, [rax]
0x1800261d0  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x1800261d5  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x1800261d9  lea     r9, dllmain_crt_dispatch; int
0x1800261e0  mov     r8, [rbp+70h]; int
0x1800261e4  mov     edx, [rbp+68h]; int
0x1800261e7  mov     rcx, [rbp+60h]; int
0x1800261eb  call    __scrt_dllmain_exception_filter
0x1800261f0  nop
0x1800261f1  add     rsp, 30h
0x1800261f5  pop     rbp
0x1800261f6  retn
```
