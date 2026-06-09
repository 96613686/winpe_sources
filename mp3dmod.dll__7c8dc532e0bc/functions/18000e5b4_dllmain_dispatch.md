# dllmain_dispatch

- ea: `0x18000e5b4`
- end: `0x18000e6db`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x18000e6e4`

## callees

- `0x18000e3d0`
- `0x18000e5b4`
- `0x18000e920`
- `0x1800101d0`
- `0x180012010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_18001B110 <= 0 )
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
0x18000e5b4  mov     rax, rsp
0x18000e5b7  mov     [rax+20h], rbx
0x18000e5bb  mov     [rax+18h], r8
0x18000e5bf  mov     [rax+10h], edx
0x18000e5c2  mov     [rax+8], rcx
0x18000e5c6  push    rsi
0x18000e5c7  push    rdi
0x18000e5c8  push    r14
0x18000e5ca  sub     rsp, 40h
0x18000e5ce  mov     rsi, r8
0x18000e5d1  mov     edi, edx
0x18000e5d3  mov     r14, rcx
0x18000e5d6  test    edx, edx
0x18000e5d8  jnz     short loc_18000E5E9
0x18000e5da  cmp     cs:dword_18001B110, edx
0x18000e5e0  jg      short loc_18000E5E9
0x18000e5e2  xor     eax, eax
0x18000e5e4  jmp     loc_18000E6CD
0x18000e5e9  lea     eax, [rdx-1]
0x18000e5ec  cmp     eax, 1
0x18000e5ef  ja      short loc_18000E630
0x18000e5f1  mov     rax, cs:_pRawDllMain
0x18000e5f8  test    rax, rax
0x18000e5fb  jnz     short loc_18000E602
0x18000e5fd  lea     ebx, [rax+1]
0x18000e600  jmp     short loc_18000E609
0x18000e602  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e607  mov     ebx, eax
0x18000e609  mov     [rsp+58h+var_28], ebx
0x18000e60d  test    ebx, ebx
0x18000e60f  jz      loc_18000E6C3
0x18000e615  mov     r8, rsi
0x18000e618  mov     edx, edi
0x18000e61a  mov     rcx, r14
0x18000e61d  call    dllmain_crt_dispatch
0x18000e622  mov     ebx, eax
0x18000e624  mov     [rsp+58h+var_28], eax
0x18000e628  test    eax, eax
0x18000e62a  jz      loc_18000E6C3
0x18000e630  mov     r8, rsi; lpvReserved
0x18000e633  mov     edx, edi; fdwReason
0x18000e635  mov     rcx, r14; hinstDLL
0x18000e638  call    DllMain
0x18000e63d  mov     ebx, eax
0x18000e63f  mov     [rsp+58h+var_28], eax
0x18000e643  cmp     edi, 1
0x18000e646  jnz     short loc_18000E67F
0x18000e648  test    eax, eax
0x18000e64a  jnz     short loc_18000E67F
0x18000e64c  mov     r8, rsi; lpvReserved
0x18000e64f  xor     edx, edx; fdwReason
0x18000e651  mov     rcx, r14; hinstDLL
0x18000e654  call    DllMain
0x18000e659  mov     r8, rsi
0x18000e65c  xor     edx, edx
0x18000e65e  mov     rcx, r14
0x18000e661  call    dllmain_crt_dispatch
0x18000e666  mov     rax, cs:_pRawDllMain
0x18000e66d  test    rax, rax
0x18000e670  jz      short loc_18000E67F
0x18000e672  mov     r8, rsi
0x18000e675  xor     edx, edx
0x18000e677  mov     rcx, r14
0x18000e67a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e67f  test    edi, edi
0x18000e681  jz      short loc_18000E688
0x18000e683  cmp     edi, 3
0x18000e686  jnz     short loc_18000E6C3
0x18000e688  mov     r8, rsi
0x18000e68b  mov     edx, edi
0x18000e68d  mov     rcx, r14
0x18000e690  call    dllmain_crt_dispatch
0x18000e695  mov     ebx, eax
0x18000e697  mov     [rsp+58h+var_28], eax
0x18000e69b  test    eax, eax
0x18000e69d  jz      short loc_18000E6C3
0x18000e69f  mov     rax, cs:_pRawDllMain
0x18000e6a6  test    rax, rax
0x18000e6a9  jnz     short loc_18000E6B0
0x18000e6ab  lea     ebx, [rax+1]
0x18000e6ae  jmp     short loc_18000E6BF
0x18000e6b0  mov     r8, rsi
0x18000e6b3  mov     edx, edi
0x18000e6b5  mov     rcx, r14
0x18000e6b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e6bd  mov     ebx, eax
0x18000e6bf  mov     [rsp+58h+var_28], ebx
0x18000e6c3  jmp     short loc_18000E6CB
0x18000e6c5  xor     ebx, ebx
0x18000e6c7  mov     [rsp+58h+var_28], ebx
0x18000e6cb  mov     eax, ebx
0x18000e6cd  mov     rbx, [rsp+58h+arg_18]
0x18000e6d2  add     rsp, 40h
0x18000e6d6  pop     r14
0x18000e6d8  pop     rdi
0x18000e6d9  pop     rsi
0x18000e6da  retn
0x18001158c  push    rbp
0x18001158e  sub     rsp, 30h
0x180011592  mov     rbp, rdx
0x180011595  mov     rax, [rcx]
0x180011598  mov     edx, [rax]
0x18001159a  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x18001159f  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x1800115a3  lea     r9, dllmain_crt_dispatch; int
0x1800115aa  mov     r8, [rbp+70h]; int
0x1800115ae  mov     edx, [rbp+68h]; int
0x1800115b1  mov     rcx, [rbp+60h]; int
0x1800115b5  call    __scrt_dllmain_exception_filter
0x1800115ba  nop
0x1800115bb  add     rsp, 30h
0x1800115bf  pop     rbp
0x1800115c0  retn
```
