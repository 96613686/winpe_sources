# dllmain_dispatch

- ea: `0x1800075b4`
- end: `0x1800076db`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x1800076f0`

## callees

- `0x1800073d0`
- `0x1800075b4`
- `0x180007944`
- `0x180008534`
- `0x18001f010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_18002B4D0 <= 0 )
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
0x1800075b4  mov     rax, rsp
0x1800075b7  mov     [rax+20h], rbx
0x1800075bb  mov     [rax+18h], r8
0x1800075bf  mov     [rax+10h], edx
0x1800075c2  mov     [rax+8], rcx
0x1800075c6  push    rsi
0x1800075c7  push    rdi
0x1800075c8  push    r14
0x1800075ca  sub     rsp, 40h
0x1800075ce  mov     rsi, r8
0x1800075d1  mov     edi, edx
0x1800075d3  mov     r14, rcx
0x1800075d6  test    edx, edx
0x1800075d8  jnz     short loc_1800075E9
0x1800075da  cmp     cs:dword_18002B4D0, edx
0x1800075e0  jg      short loc_1800075E9
0x1800075e2  xor     eax, eax
0x1800075e4  jmp     loc_1800076CD
0x1800075e9  lea     eax, [rdx-1]
0x1800075ec  cmp     eax, 1
0x1800075ef  ja      short loc_180007630
0x1800075f1  mov     rax, cs:_pRawDllMain
0x1800075f8  test    rax, rax
0x1800075fb  jnz     short loc_180007602
0x1800075fd  lea     ebx, [rax+1]
0x180007600  jmp     short loc_180007609
0x180007602  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007607  mov     ebx, eax
0x180007609  mov     [rsp+58h+var_28], ebx
0x18000760d  test    ebx, ebx
0x18000760f  jz      loc_1800076C3
0x180007615  mov     r8, rsi
0x180007618  mov     edx, edi
0x18000761a  mov     rcx, r14
0x18000761d  call    dllmain_crt_dispatch
0x180007622  mov     ebx, eax
0x180007624  mov     [rsp+58h+var_28], eax
0x180007628  test    eax, eax
0x18000762a  jz      loc_1800076C3
0x180007630  mov     r8, rsi; lpvReserved
0x180007633  mov     edx, edi; fdwReason
0x180007635  mov     rcx, r14; hinstDLL
0x180007638  call    DllMain
0x18000763d  mov     ebx, eax
0x18000763f  mov     [rsp+58h+var_28], eax
0x180007643  cmp     edi, 1
0x180007646  jnz     short loc_18000767F
0x180007648  test    eax, eax
0x18000764a  jnz     short loc_18000767F
0x18000764c  mov     r8, rsi; lpvReserved
0x18000764f  xor     edx, edx; fdwReason
0x180007651  mov     rcx, r14; hinstDLL
0x180007654  call    DllMain
0x180007659  mov     r8, rsi
0x18000765c  xor     edx, edx
0x18000765e  mov     rcx, r14
0x180007661  call    dllmain_crt_dispatch
0x180007666  mov     rax, cs:_pRawDllMain
0x18000766d  test    rax, rax
0x180007670  jz      short loc_18000767F
0x180007672  mov     r8, rsi
0x180007675  xor     edx, edx
0x180007677  mov     rcx, r14
0x18000767a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000767f  test    edi, edi
0x180007681  jz      short loc_180007688
0x180007683  cmp     edi, 3
0x180007686  jnz     short loc_1800076C3
0x180007688  mov     r8, rsi
0x18000768b  mov     edx, edi
0x18000768d  mov     rcx, r14
0x180007690  call    dllmain_crt_dispatch
0x180007695  mov     ebx, eax
0x180007697  mov     [rsp+58h+var_28], eax
0x18000769b  test    eax, eax
0x18000769d  jz      short loc_1800076C3
0x18000769f  mov     rax, cs:_pRawDllMain
0x1800076a6  test    rax, rax
0x1800076a9  jnz     short loc_1800076B0
0x1800076ab  lea     ebx, [rax+1]
0x1800076ae  jmp     short loc_1800076BF
0x1800076b0  mov     r8, rsi
0x1800076b3  mov     edx, edi
0x1800076b5  mov     rcx, r14
0x1800076b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800076bd  mov     ebx, eax
0x1800076bf  mov     [rsp+58h+var_28], ebx
0x1800076c3  jmp     short loc_1800076CB
0x1800076c5  xor     ebx, ebx
0x1800076c7  mov     [rsp+58h+var_28], ebx
0x1800076cb  mov     eax, ebx
0x1800076cd  mov     rbx, [rsp+58h+arg_18]
0x1800076d2  add     rsp, 40h
0x1800076d6  pop     r14
0x1800076d8  pop     rdi
0x1800076d9  pop     rsi
0x1800076da  retn
0x18001e50c  push    rbp
0x18001e50e  sub     rsp, 30h
0x18001e512  mov     rbp, rdx
0x18001e515  mov     rax, [rcx]
0x18001e518  mov     edx, [rax]
0x18001e51a  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x18001e51f  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x18001e523  lea     r9, dllmain_crt_dispatch; int
0x18001e52a  mov     r8, [rbp+70h]; int
0x18001e52e  mov     edx, [rbp+68h]; int
0x18001e531  mov     rcx, [rbp+60h]; int
0x18001e535  call    __scrt_dllmain_exception_filter
0x18001e53a  nop
0x18001e53b  add     rsp, 30h
0x18001e53f  pop     rbp
0x18001e540  retn
```
