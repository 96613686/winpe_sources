# dllmain_dispatch

- ea: `0x180001674`
- end: `0x18000179b`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x1800017b0`

## callees

- `0x180001350`
- `0x180001490`
- `0x180001674`
- `0x180001a28`
- `0x180027010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_180034D10 <= 0 )
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
0x180001674  mov     rax, rsp
0x180001677  mov     [rax+20h], rbx
0x18000167b  mov     [rax+18h], r8
0x18000167f  mov     [rax+10h], edx
0x180001682  mov     [rax+8], rcx
0x180001686  push    rsi
0x180001687  push    rdi
0x180001688  push    r14
0x18000168a  sub     rsp, 40h
0x18000168e  mov     rsi, r8
0x180001691  mov     edi, edx
0x180001693  mov     r14, rcx
0x180001696  test    edx, edx
0x180001698  jnz     short loc_1800016A9
0x18000169a  cmp     cs:dword_180034D10, edx
0x1800016a0  jg      short loc_1800016A9
0x1800016a2  xor     eax, eax
0x1800016a4  jmp     loc_18000178D
0x1800016a9  lea     eax, [rdx-1]
0x1800016ac  cmp     eax, 1
0x1800016af  ja      short loc_1800016F0
0x1800016b1  mov     rax, cs:_pRawDllMain
0x1800016b8  test    rax, rax
0x1800016bb  jnz     short loc_1800016C2
0x1800016bd  lea     ebx, [rax+1]
0x1800016c0  jmp     short loc_1800016C9
0x1800016c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800016c7  mov     ebx, eax
0x1800016c9  mov     [rsp+58h+var_28], ebx
0x1800016cd  test    ebx, ebx
0x1800016cf  jz      loc_180001783
0x1800016d5  mov     r8, rsi
0x1800016d8  mov     edx, edi
0x1800016da  mov     rcx, r14
0x1800016dd  call    dllmain_crt_dispatch
0x1800016e2  mov     ebx, eax
0x1800016e4  mov     [rsp+58h+var_28], eax
0x1800016e8  test    eax, eax
0x1800016ea  jz      loc_180001783
0x1800016f0  mov     r8, rsi; lpvReserved
0x1800016f3  mov     edx, edi; fdwReason
0x1800016f5  mov     rcx, r14; hinstDLL
0x1800016f8  call    DllMain
0x1800016fd  mov     ebx, eax
0x1800016ff  mov     [rsp+58h+var_28], eax
0x180001703  cmp     edi, 1
0x180001706  jnz     short loc_18000173F
0x180001708  test    eax, eax
0x18000170a  jnz     short loc_18000173F
0x18000170c  mov     r8, rsi; lpvReserved
0x18000170f  xor     edx, edx; fdwReason
0x180001711  mov     rcx, r14; hinstDLL
0x180001714  call    DllMain
0x180001719  mov     r8, rsi
0x18000171c  xor     edx, edx
0x18000171e  mov     rcx, r14
0x180001721  call    dllmain_crt_dispatch
0x180001726  mov     rax, cs:_pRawDllMain
0x18000172d  test    rax, rax
0x180001730  jz      short loc_18000173F
0x180001732  mov     r8, rsi
0x180001735  xor     edx, edx
0x180001737  mov     rcx, r14
0x18000173a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000173f  test    edi, edi
0x180001741  jz      short loc_180001748
0x180001743  cmp     edi, 3
0x180001746  jnz     short loc_180001783
0x180001748  mov     r8, rsi
0x18000174b  mov     edx, edi
0x18000174d  mov     rcx, r14
0x180001750  call    dllmain_crt_dispatch
0x180001755  mov     ebx, eax
0x180001757  mov     [rsp+58h+var_28], eax
0x18000175b  test    eax, eax
0x18000175d  jz      short loc_180001783
0x18000175f  mov     rax, cs:_pRawDllMain
0x180001766  test    rax, rax
0x180001769  jnz     short loc_180001770
0x18000176b  lea     ebx, [rax+1]
0x18000176e  jmp     short loc_18000177F
0x180001770  mov     r8, rsi
0x180001773  mov     edx, edi
0x180001775  mov     rcx, r14
0x180001778  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000177d  mov     ebx, eax
0x18000177f  mov     [rsp+58h+var_28], ebx
0x180001783  jmp     short loc_18000178B
0x180001785  xor     ebx, ebx
0x180001787  mov     [rsp+58h+var_28], ebx
0x18000178b  mov     eax, ebx
0x18000178d  mov     rbx, [rsp+58h+arg_18]
0x180001792  add     rsp, 40h
0x180001796  pop     r14
0x180001798  pop     rdi
0x180001799  pop     rsi
0x18000179a  retn
0x18002536c  push    rbp
0x18002536e  sub     rsp, 30h
0x180025372  mov     rbp, rdx
0x180025375  mov     rax, [rcx]
0x180025378  mov     edx, [rax]
0x18002537a  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x18002537f  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x180025383  lea     r9, dllmain_crt_dispatch; int
0x18002538a  mov     r8, [rbp+70h]; int
0x18002538e  mov     edx, [rbp+68h]; int
0x180025391  mov     rcx, [rbp+60h]; int
0x180025395  call    __scrt_dllmain_exception_filter
0x18002539a  nop
0x18002539b  add     rsp, 30h
0x18002539f  pop     rbp
0x1800253a0  retn
```
