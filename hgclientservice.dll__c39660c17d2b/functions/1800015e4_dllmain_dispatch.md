# dllmain_dispatch

- ea: `0x1800015e4`
- end: `0x18000170b`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180001720`

## callees

- `0x180001400`
- `0x1800015e4`
- `0x1800018d4`
- `0x1800075f8`
- `0x180017010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_1800202D0 <= 0 )
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
0x1800015e4  mov     rax, rsp
0x1800015e7  mov     [rax+20h], rbx
0x1800015eb  mov     [rax+18h], r8
0x1800015ef  mov     [rax+10h], edx
0x1800015f2  mov     [rax+8], rcx
0x1800015f6  push    rsi
0x1800015f7  push    rdi
0x1800015f8  push    r14
0x1800015fa  sub     rsp, 40h
0x1800015fe  mov     rsi, r8
0x180001601  mov     edi, edx
0x180001603  mov     r14, rcx
0x180001606  test    edx, edx
0x180001608  jnz     short loc_180001619
0x18000160a  cmp     cs:dword_1800202D0, edx
0x180001610  jg      short loc_180001619
0x180001612  xor     eax, eax
0x180001614  jmp     loc_1800016FD
0x180001619  lea     eax, [rdx-1]
0x18000161c  cmp     eax, 1
0x18000161f  ja      short loc_180001660
0x180001621  mov     rax, cs:_pRawDllMain
0x180001628  test    rax, rax
0x18000162b  jnz     short loc_180001632
0x18000162d  lea     ebx, [rax+1]
0x180001630  jmp     short loc_180001639
0x180001632  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001637  mov     ebx, eax
0x180001639  mov     [rsp+58h+var_28], ebx
0x18000163d  test    ebx, ebx
0x18000163f  jz      loc_1800016F3
0x180001645  mov     r8, rsi
0x180001648  mov     edx, edi
0x18000164a  mov     rcx, r14
0x18000164d  call    dllmain_crt_dispatch
0x180001652  mov     ebx, eax
0x180001654  mov     [rsp+58h+var_28], eax
0x180001658  test    eax, eax
0x18000165a  jz      loc_1800016F3
0x180001660  mov     r8, rsi; lpvReserved
0x180001663  mov     edx, edi; fdwReason
0x180001665  mov     rcx, r14; hinstDLL
0x180001668  call    DllMain
0x18000166d  mov     ebx, eax
0x18000166f  mov     [rsp+58h+var_28], eax
0x180001673  cmp     edi, 1
0x180001676  jnz     short loc_1800016AF
0x180001678  test    eax, eax
0x18000167a  jnz     short loc_1800016AF
0x18000167c  mov     r8, rsi; lpvReserved
0x18000167f  xor     edx, edx; fdwReason
0x180001681  mov     rcx, r14; hinstDLL
0x180001684  call    DllMain
0x180001689  mov     r8, rsi
0x18000168c  xor     edx, edx
0x18000168e  mov     rcx, r14
0x180001691  call    dllmain_crt_dispatch
0x180001696  mov     rax, cs:_pRawDllMain
0x18000169d  test    rax, rax
0x1800016a0  jz      short loc_1800016AF
0x1800016a2  mov     r8, rsi
0x1800016a5  xor     edx, edx
0x1800016a7  mov     rcx, r14
0x1800016aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800016af  test    edi, edi
0x1800016b1  jz      short loc_1800016B8
0x1800016b3  cmp     edi, 3
0x1800016b6  jnz     short loc_1800016F3
0x1800016b8  mov     r8, rsi
0x1800016bb  mov     edx, edi
0x1800016bd  mov     rcx, r14
0x1800016c0  call    dllmain_crt_dispatch
0x1800016c5  mov     ebx, eax
0x1800016c7  mov     [rsp+58h+var_28], eax
0x1800016cb  test    eax, eax
0x1800016cd  jz      short loc_1800016F3
0x1800016cf  mov     rax, cs:_pRawDllMain
0x1800016d6  test    rax, rax
0x1800016d9  jnz     short loc_1800016E0
0x1800016db  lea     ebx, [rax+1]
0x1800016de  jmp     short loc_1800016EF
0x1800016e0  mov     r8, rsi
0x1800016e3  mov     edx, edi
0x1800016e5  mov     rcx, r14
0x1800016e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800016ed  mov     ebx, eax
0x1800016ef  mov     [rsp+58h+var_28], ebx
0x1800016f3  jmp     short loc_1800016FB
0x1800016f5  xor     ebx, ebx
0x1800016f7  mov     [rsp+58h+var_28], ebx
0x1800016fb  mov     eax, ebx
0x1800016fd  mov     rbx, [rsp+58h+arg_18]
0x180001702  add     rsp, 40h
0x180001706  pop     r14
0x180001708  pop     rdi
0x180001709  pop     rsi
0x18000170a  retn
0x1800152ec  push    rbp
0x1800152ee  sub     rsp, 30h
0x1800152f2  mov     rbp, rdx
0x1800152f5  mov     rax, [rcx]
0x1800152f8  mov     edx, [rax]
0x1800152fa  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x1800152ff  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x180015303  lea     r9, dllmain_crt_dispatch; int
0x18001530a  mov     r8, [rbp+70h]; int
0x18001530e  mov     edx, [rbp+68h]; int
0x180015311  mov     rcx, [rbp+60h]; int
0x180015315  call    __scrt_dllmain_exception_filter
0x18001531a  nop
0x18001531b  add     rsp, 30h
0x18001531f  pop     rbp
0x180015320  retn
```
