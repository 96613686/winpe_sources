# dllmain_dispatch

- ea: `0x180003564`
- end: `0x18000368b`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x1800036a0`

## callees

- `0x180003380`
- `0x180003564`
- `0x180003830`
- `0x1800083d0`
- `0x18002a010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_18003C810 <= 0 )
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
0x180003564  mov     rax, rsp
0x180003567  mov     [rax+20h], rbx
0x18000356b  mov     [rax+18h], r8
0x18000356f  mov     [rax+10h], edx
0x180003572  mov     [rax+8], rcx
0x180003576  push    rsi
0x180003577  push    rdi
0x180003578  push    r14
0x18000357a  sub     rsp, 40h
0x18000357e  mov     rsi, r8
0x180003581  mov     edi, edx
0x180003583  mov     r14, rcx
0x180003586  test    edx, edx
0x180003588  jnz     short loc_180003599
0x18000358a  cmp     cs:dword_18003C810, edx
0x180003590  jg      short loc_180003599
0x180003592  xor     eax, eax
0x180003594  jmp     loc_18000367D
0x180003599  lea     eax, [rdx-1]
0x18000359c  cmp     eax, 1
0x18000359f  ja      short loc_1800035E0
0x1800035a1  mov     rax, cs:_pRawDllMain
0x1800035a8  test    rax, rax
0x1800035ab  jnz     short loc_1800035B2
0x1800035ad  lea     ebx, [rax+1]
0x1800035b0  jmp     short loc_1800035B9
0x1800035b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800035b7  mov     ebx, eax
0x1800035b9  mov     [rsp+58h+var_28], ebx
0x1800035bd  test    ebx, ebx
0x1800035bf  jz      loc_180003673
0x1800035c5  mov     r8, rsi
0x1800035c8  mov     edx, edi
0x1800035ca  mov     rcx, r14
0x1800035cd  call    dllmain_crt_dispatch
0x1800035d2  mov     ebx, eax
0x1800035d4  mov     [rsp+58h+var_28], eax
0x1800035d8  test    eax, eax
0x1800035da  jz      loc_180003673
0x1800035e0  mov     r8, rsi; lpvReserved
0x1800035e3  mov     edx, edi; fdwReason
0x1800035e5  mov     rcx, r14; hinstDLL
0x1800035e8  call    DllMain
0x1800035ed  mov     ebx, eax
0x1800035ef  mov     [rsp+58h+var_28], eax
0x1800035f3  cmp     edi, 1
0x1800035f6  jnz     short loc_18000362F
0x1800035f8  test    eax, eax
0x1800035fa  jnz     short loc_18000362F
0x1800035fc  mov     r8, rsi; lpvReserved
0x1800035ff  xor     edx, edx; fdwReason
0x180003601  mov     rcx, r14; hinstDLL
0x180003604  call    DllMain
0x180003609  mov     r8, rsi
0x18000360c  xor     edx, edx
0x18000360e  mov     rcx, r14
0x180003611  call    dllmain_crt_dispatch
0x180003616  mov     rax, cs:_pRawDllMain
0x18000361d  test    rax, rax
0x180003620  jz      short loc_18000362F
0x180003622  mov     r8, rsi
0x180003625  xor     edx, edx
0x180003627  mov     rcx, r14
0x18000362a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000362f  test    edi, edi
0x180003631  jz      short loc_180003638
0x180003633  cmp     edi, 3
0x180003636  jnz     short loc_180003673
0x180003638  mov     r8, rsi
0x18000363b  mov     edx, edi
0x18000363d  mov     rcx, r14
0x180003640  call    dllmain_crt_dispatch
0x180003645  mov     ebx, eax
0x180003647  mov     [rsp+58h+var_28], eax
0x18000364b  test    eax, eax
0x18000364d  jz      short loc_180003673
0x18000364f  mov     rax, cs:_pRawDllMain
0x180003656  test    rax, rax
0x180003659  jnz     short loc_180003660
0x18000365b  lea     ebx, [rax+1]
0x18000365e  jmp     short loc_18000366F
0x180003660  mov     r8, rsi
0x180003663  mov     edx, edi
0x180003665  mov     rcx, r14
0x180003668  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000366d  mov     ebx, eax
0x18000366f  mov     [rsp+58h+var_28], ebx
0x180003673  jmp     short loc_18000367B
0x180003675  xor     ebx, ebx
0x180003677  mov     [rsp+58h+var_28], ebx
0x18000367b  mov     eax, ebx
0x18000367d  mov     rbx, [rsp+58h+arg_18]
0x180003682  add     rsp, 40h
0x180003686  pop     r14
0x180003688  pop     rdi
0x180003689  pop     rsi
0x18000368a  retn
0x18002841c  push    rbp
0x18002841e  sub     rsp, 30h
0x180028422  mov     rbp, rdx
0x180028425  mov     rax, [rcx]
0x180028428  mov     edx, [rax]
0x18002842a  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x18002842f  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x180028433  lea     r9, dllmain_crt_dispatch; int
0x18002843a  mov     r8, [rbp+70h]; int
0x18002843e  mov     edx, [rbp+68h]; int
0x180028441  mov     rcx, [rbp+60h]; int
0x180028445  call    __scrt_dllmain_exception_filter
0x18002844a  nop
0x18002844b  add     rsp, 30h
0x18002844f  pop     rbp
0x180028450  retn
```
