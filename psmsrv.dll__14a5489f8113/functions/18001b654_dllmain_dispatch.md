# dllmain_dispatch

- ea: `0x18001b654`
- end: `0x18001b77b`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x18001b790`

## callees

- `0x18001b470`
- `0x18001b654`
- `0x18001b8c0`
- `0x18001ba10`
- `0x18002f010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_18003F310 <= 0 )
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
0x18001b654  mov     rax, rsp
0x18001b657  mov     [rax+20h], rbx
0x18001b65b  mov     [rax+18h], r8
0x18001b65f  mov     [rax+10h], edx
0x18001b662  mov     [rax+8], rcx
0x18001b666  push    rsi
0x18001b667  push    rdi
0x18001b668  push    r14
0x18001b66a  sub     rsp, 40h
0x18001b66e  mov     rsi, r8
0x18001b671  mov     edi, edx
0x18001b673  mov     r14, rcx
0x18001b676  test    edx, edx
0x18001b678  jnz     short loc_18001B689
0x18001b67a  cmp     cs:dword_18003F310, edx
0x18001b680  jg      short loc_18001B689
0x18001b682  xor     eax, eax
0x18001b684  jmp     loc_18001B76D
0x18001b689  lea     eax, [rdx-1]
0x18001b68c  cmp     eax, 1
0x18001b68f  ja      short loc_18001B6D0
0x18001b691  mov     rax, cs:_pRawDllMain
0x18001b698  test    rax, rax
0x18001b69b  jnz     short loc_18001B6A2
0x18001b69d  lea     ebx, [rax+1]
0x18001b6a0  jmp     short loc_18001B6A9
0x18001b6a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b6a7  mov     ebx, eax
0x18001b6a9  mov     [rsp+58h+var_28], ebx
0x18001b6ad  test    ebx, ebx
0x18001b6af  jz      loc_18001B763
0x18001b6b5  mov     r8, rsi
0x18001b6b8  mov     edx, edi
0x18001b6ba  mov     rcx, r14
0x18001b6bd  call    dllmain_crt_dispatch
0x18001b6c2  mov     ebx, eax
0x18001b6c4  mov     [rsp+58h+var_28], eax
0x18001b6c8  test    eax, eax
0x18001b6ca  jz      loc_18001B763
0x18001b6d0  mov     r8, rsi; lpvReserved
0x18001b6d3  mov     edx, edi; fdwReason
0x18001b6d5  mov     rcx, r14; hinstDLL
0x18001b6d8  call    DllMain
0x18001b6dd  mov     ebx, eax
0x18001b6df  mov     [rsp+58h+var_28], eax
0x18001b6e3  cmp     edi, 1
0x18001b6e6  jnz     short loc_18001B71F
0x18001b6e8  test    eax, eax
0x18001b6ea  jnz     short loc_18001B71F
0x18001b6ec  mov     r8, rsi; lpvReserved
0x18001b6ef  xor     edx, edx; fdwReason
0x18001b6f1  mov     rcx, r14; hinstDLL
0x18001b6f4  call    DllMain
0x18001b6f9  mov     r8, rsi
0x18001b6fc  xor     edx, edx
0x18001b6fe  mov     rcx, r14
0x18001b701  call    dllmain_crt_dispatch
0x18001b706  mov     rax, cs:_pRawDllMain
0x18001b70d  test    rax, rax
0x18001b710  jz      short loc_18001B71F
0x18001b712  mov     r8, rsi
0x18001b715  xor     edx, edx
0x18001b717  mov     rcx, r14
0x18001b71a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b71f  test    edi, edi
0x18001b721  jz      short loc_18001B728
0x18001b723  cmp     edi, 3
0x18001b726  jnz     short loc_18001B763
0x18001b728  mov     r8, rsi
0x18001b72b  mov     edx, edi
0x18001b72d  mov     rcx, r14
0x18001b730  call    dllmain_crt_dispatch
0x18001b735  mov     ebx, eax
0x18001b737  mov     [rsp+58h+var_28], eax
0x18001b73b  test    eax, eax
0x18001b73d  jz      short loc_18001B763
0x18001b73f  mov     rax, cs:_pRawDllMain
0x18001b746  test    rax, rax
0x18001b749  jnz     short loc_18001B750
0x18001b74b  lea     ebx, [rax+1]
0x18001b74e  jmp     short loc_18001B75F
0x18001b750  mov     r8, rsi
0x18001b753  mov     edx, edi
0x18001b755  mov     rcx, r14
0x18001b758  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b75d  mov     ebx, eax
0x18001b75f  mov     [rsp+58h+var_28], ebx
0x18001b763  jmp     short loc_18001B76B
0x18001b765  xor     ebx, ebx
0x18001b767  mov     [rsp+58h+var_28], ebx
0x18001b76b  mov     eax, ebx
0x18001b76d  mov     rbx, [rsp+58h+arg_18]
0x18001b772  add     rsp, 40h
0x18001b776  pop     r14
0x18001b778  pop     rdi
0x18001b779  pop     rsi
0x18001b77a  retn
0x18002e24c  push    rbp
0x18002e24e  sub     rsp, 30h
0x18002e252  mov     rbp, rdx
0x18002e255  mov     rax, [rcx]
0x18002e258  mov     edx, [rax]
0x18002e25a  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x18002e25f  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x18002e263  lea     r9, dllmain_crt_dispatch; int
0x18002e26a  mov     r8, [rbp+70h]; int
0x18002e26e  mov     edx, [rbp+68h]; int
0x18002e271  mov     rcx, [rbp+60h]; int
0x18002e275  call    __scrt_dllmain_exception_filter
0x18002e27a  nop
0x18002e27b  add     rsp, 30h
0x18002e27f  pop     rbp
0x18002e280  retn
```
