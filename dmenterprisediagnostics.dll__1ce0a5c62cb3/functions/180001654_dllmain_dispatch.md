# dllmain_dispatch

- ea: `0x180001654`
- end: `0x18000177b`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180001790`

## callees

- `0x180001330`
- `0x180001470`
- `0x180001654`
- `0x180001a08`
- `0x180026010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_180033D10 <= 0 )
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
0x180001654  mov     rax, rsp
0x180001657  mov     [rax+20h], rbx
0x18000165b  mov     [rax+18h], r8
0x18000165f  mov     [rax+10h], edx
0x180001662  mov     [rax+8], rcx
0x180001666  push    rsi
0x180001667  push    rdi
0x180001668  push    r14
0x18000166a  sub     rsp, 40h
0x18000166e  mov     rsi, r8
0x180001671  mov     edi, edx
0x180001673  mov     r14, rcx
0x180001676  test    edx, edx
0x180001678  jnz     short loc_180001689
0x18000167a  cmp     cs:dword_180033D10, edx
0x180001680  jg      short loc_180001689
0x180001682  xor     eax, eax
0x180001684  jmp     loc_18000176D
0x180001689  lea     eax, [rdx-1]
0x18000168c  cmp     eax, 1
0x18000168f  ja      short loc_1800016D0
0x180001691  mov     rax, cs:_pRawDllMain
0x180001698  test    rax, rax
0x18000169b  jnz     short loc_1800016A2
0x18000169d  lea     ebx, [rax+1]
0x1800016a0  jmp     short loc_1800016A9
0x1800016a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800016a7  mov     ebx, eax
0x1800016a9  mov     [rsp+58h+var_28], ebx
0x1800016ad  test    ebx, ebx
0x1800016af  jz      loc_180001763
0x1800016b5  mov     r8, rsi
0x1800016b8  mov     edx, edi
0x1800016ba  mov     rcx, r14
0x1800016bd  call    dllmain_crt_dispatch
0x1800016c2  mov     ebx, eax
0x1800016c4  mov     [rsp+58h+var_28], eax
0x1800016c8  test    eax, eax
0x1800016ca  jz      loc_180001763
0x1800016d0  mov     r8, rsi; lpvReserved
0x1800016d3  mov     edx, edi; fdwReason
0x1800016d5  mov     rcx, r14; hinstDLL
0x1800016d8  call    DllMain
0x1800016dd  mov     ebx, eax
0x1800016df  mov     [rsp+58h+var_28], eax
0x1800016e3  cmp     edi, 1
0x1800016e6  jnz     short loc_18000171F
0x1800016e8  test    eax, eax
0x1800016ea  jnz     short loc_18000171F
0x1800016ec  mov     r8, rsi; lpvReserved
0x1800016ef  xor     edx, edx; fdwReason
0x1800016f1  mov     rcx, r14; hinstDLL
0x1800016f4  call    DllMain
0x1800016f9  mov     r8, rsi
0x1800016fc  xor     edx, edx
0x1800016fe  mov     rcx, r14
0x180001701  call    dllmain_crt_dispatch
0x180001706  mov     rax, cs:_pRawDllMain
0x18000170d  test    rax, rax
0x180001710  jz      short loc_18000171F
0x180001712  mov     r8, rsi
0x180001715  xor     edx, edx
0x180001717  mov     rcx, r14
0x18000171a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000171f  test    edi, edi
0x180001721  jz      short loc_180001728
0x180001723  cmp     edi, 3
0x180001726  jnz     short loc_180001763
0x180001728  mov     r8, rsi
0x18000172b  mov     edx, edi
0x18000172d  mov     rcx, r14
0x180001730  call    dllmain_crt_dispatch
0x180001735  mov     ebx, eax
0x180001737  mov     [rsp+58h+var_28], eax
0x18000173b  test    eax, eax
0x18000173d  jz      short loc_180001763
0x18000173f  mov     rax, cs:_pRawDllMain
0x180001746  test    rax, rax
0x180001749  jnz     short loc_180001750
0x18000174b  lea     ebx, [rax+1]
0x18000174e  jmp     short loc_18000175F
0x180001750  mov     r8, rsi
0x180001753  mov     edx, edi
0x180001755  mov     rcx, r14
0x180001758  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000175d  mov     ebx, eax
0x18000175f  mov     [rsp+58h+var_28], ebx
0x180001763  jmp     short loc_18000176B
0x180001765  xor     ebx, ebx
0x180001767  mov     [rsp+58h+var_28], ebx
0x18000176b  mov     eax, ebx
0x18000176d  mov     rbx, [rsp+58h+arg_18]
0x180001772  add     rsp, 40h
0x180001776  pop     r14
0x180001778  pop     rdi
0x180001779  pop     rsi
0x18000177a  retn
0x1800244ac  push    rbp
0x1800244ae  sub     rsp, 30h
0x1800244b2  mov     rbp, rdx
0x1800244b5  mov     rax, [rcx]
0x1800244b8  mov     edx, [rax]
0x1800244ba  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x1800244bf  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x1800244c3  lea     r9, dllmain_crt_dispatch; int
0x1800244ca  mov     r8, [rbp+70h]; int
0x1800244ce  mov     edx, [rbp+68h]; int
0x1800244d1  mov     rcx, [rbp+60h]; int
0x1800244d5  call    __scrt_dllmain_exception_filter
0x1800244da  nop
0x1800244db  add     rsp, 30h
0x1800244df  pop     rbp
0x1800244e0  retn
```
