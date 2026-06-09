# dllmain_dispatch

- ea: `0x180001424`
- end: `0x18000154b`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180001560`

## callees

- `0x180001240`
- `0x180001424`
- `0x18000183c`
- `0x180006cfc`
- `0x18000a010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_1800101F0 <= 0 )
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
0x180001424  mov     rax, rsp
0x180001427  mov     [rax+20h], rbx
0x18000142b  mov     [rax+18h], r8
0x18000142f  mov     [rax+10h], edx
0x180001432  mov     [rax+8], rcx
0x180001436  push    rsi
0x180001437  push    rdi
0x180001438  push    r14
0x18000143a  sub     rsp, 40h
0x18000143e  mov     rsi, r8
0x180001441  mov     edi, edx
0x180001443  mov     r14, rcx
0x180001446  test    edx, edx
0x180001448  jnz     short loc_180001459
0x18000144a  cmp     cs:dword_1800101F0, edx
0x180001450  jg      short loc_180001459
0x180001452  xor     eax, eax
0x180001454  jmp     loc_18000153D
0x180001459  lea     eax, [rdx-1]
0x18000145c  cmp     eax, 1
0x18000145f  ja      short loc_1800014A0
0x180001461  mov     rax, cs:_pRawDllMain
0x180001468  test    rax, rax
0x18000146b  jnz     short loc_180001472
0x18000146d  lea     ebx, [rax+1]
0x180001470  jmp     short loc_180001479
0x180001472  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001477  mov     ebx, eax
0x180001479  mov     [rsp+58h+var_28], ebx
0x18000147d  test    ebx, ebx
0x18000147f  jz      loc_180001533
0x180001485  mov     r8, rsi
0x180001488  mov     edx, edi
0x18000148a  mov     rcx, r14
0x18000148d  call    dllmain_crt_dispatch
0x180001492  mov     ebx, eax
0x180001494  mov     [rsp+58h+var_28], eax
0x180001498  test    eax, eax
0x18000149a  jz      loc_180001533
0x1800014a0  mov     r8, rsi; lpvReserved
0x1800014a3  mov     edx, edi; fdwReason
0x1800014a5  mov     rcx, r14; hinstDLL
0x1800014a8  call    DllMain
0x1800014ad  mov     ebx, eax
0x1800014af  mov     [rsp+58h+var_28], eax
0x1800014b3  cmp     edi, 1
0x1800014b6  jnz     short loc_1800014EF
0x1800014b8  test    eax, eax
0x1800014ba  jnz     short loc_1800014EF
0x1800014bc  mov     r8, rsi; lpvReserved
0x1800014bf  xor     edx, edx; fdwReason
0x1800014c1  mov     rcx, r14; hinstDLL
0x1800014c4  call    DllMain
0x1800014c9  mov     r8, rsi
0x1800014cc  xor     edx, edx
0x1800014ce  mov     rcx, r14
0x1800014d1  call    dllmain_crt_dispatch
0x1800014d6  mov     rax, cs:_pRawDllMain
0x1800014dd  test    rax, rax
0x1800014e0  jz      short loc_1800014EF
0x1800014e2  mov     r8, rsi
0x1800014e5  xor     edx, edx
0x1800014e7  mov     rcx, r14
0x1800014ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800014ef  test    edi, edi
0x1800014f1  jz      short loc_1800014F8
0x1800014f3  cmp     edi, 3
0x1800014f6  jnz     short loc_180001533
0x1800014f8  mov     r8, rsi
0x1800014fb  mov     edx, edi
0x1800014fd  mov     rcx, r14
0x180001500  call    dllmain_crt_dispatch
0x180001505  mov     ebx, eax
0x180001507  mov     [rsp+58h+var_28], eax
0x18000150b  test    eax, eax
0x18000150d  jz      short loc_180001533
0x18000150f  mov     rax, cs:_pRawDllMain
0x180001516  test    rax, rax
0x180001519  jnz     short loc_180001520
0x18000151b  lea     ebx, [rax+1]
0x18000151e  jmp     short loc_18000152F
0x180001520  mov     r8, rsi
0x180001523  mov     edx, edi
0x180001525  mov     rcx, r14
0x180001528  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000152d  mov     ebx, eax
0x18000152f  mov     [rsp+58h+var_28], ebx
0x180001533  jmp     short loc_18000153B
0x180001535  xor     ebx, ebx
0x180001537  mov     [rsp+58h+var_28], ebx
0x18000153b  mov     eax, ebx
0x18000153d  mov     rbx, [rsp+58h+arg_18]
0x180001542  add     rsp, 40h
0x180001546  pop     r14
0x180001548  pop     rdi
0x180001549  pop     rsi
0x18000154a  retn
0x18000961c  push    rbp
0x18000961e  sub     rsp, 30h
0x180009622  mov     rbp, rdx
0x180009625  mov     rax, [rcx]
0x180009628  mov     edx, [rax]
0x18000962a  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x18000962f  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x180009633  lea     r9, dllmain_crt_dispatch; int
0x18000963a  mov     r8, [rbp+70h]; int
0x18000963e  mov     edx, [rbp+68h]; int
0x180009641  mov     rcx, [rbp+60h]; int
0x180009645  call    __scrt_dllmain_exception_filter
0x18000964a  nop
0x18000964b  add     rsp, 30h
0x18000964f  pop     rbp
0x180009650  retn
```
