# dllmain_dispatch

- ea: `0x1800018c4`
- end: `0x1800019eb`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180001a00`

## callees

- `0x1800016e0`
- `0x1800018c4`
- `0x180001b58`
- `0x180001f38`
- `0x180012010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_180019610 <= 0 )
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
0x1800018c4  mov     rax, rsp
0x1800018c7  mov     [rax+20h], rbx
0x1800018cb  mov     [rax+18h], r8
0x1800018cf  mov     [rax+10h], edx
0x1800018d2  mov     [rax+8], rcx
0x1800018d6  push    rsi
0x1800018d7  push    rdi
0x1800018d8  push    r14
0x1800018da  sub     rsp, 40h
0x1800018de  mov     rsi, r8
0x1800018e1  mov     edi, edx
0x1800018e3  mov     r14, rcx
0x1800018e6  test    edx, edx
0x1800018e8  jnz     short loc_1800018F9
0x1800018ea  cmp     cs:dword_180019610, edx
0x1800018f0  jg      short loc_1800018F9
0x1800018f2  xor     eax, eax
0x1800018f4  jmp     loc_1800019DD
0x1800018f9  lea     eax, [rdx-1]
0x1800018fc  cmp     eax, 1
0x1800018ff  ja      short loc_180001940
0x180001901  mov     rax, cs:_pRawDllMain
0x180001908  test    rax, rax
0x18000190b  jnz     short loc_180001912
0x18000190d  lea     ebx, [rax+1]
0x180001910  jmp     short loc_180001919
0x180001912  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001917  mov     ebx, eax
0x180001919  mov     [rsp+58h+var_28], ebx
0x18000191d  test    ebx, ebx
0x18000191f  jz      loc_1800019D3
0x180001925  mov     r8, rsi
0x180001928  mov     edx, edi
0x18000192a  mov     rcx, r14
0x18000192d  call    dllmain_crt_dispatch
0x180001932  mov     ebx, eax
0x180001934  mov     [rsp+58h+var_28], eax
0x180001938  test    eax, eax
0x18000193a  jz      loc_1800019D3
0x180001940  mov     r8, rsi; lpvReserved
0x180001943  mov     edx, edi; fdwReason
0x180001945  mov     rcx, r14; hinstDLL
0x180001948  call    DllMain
0x18000194d  mov     ebx, eax
0x18000194f  mov     [rsp+58h+var_28], eax
0x180001953  cmp     edi, 1
0x180001956  jnz     short loc_18000198F
0x180001958  test    eax, eax
0x18000195a  jnz     short loc_18000198F
0x18000195c  mov     r8, rsi; lpvReserved
0x18000195f  xor     edx, edx; fdwReason
0x180001961  mov     rcx, r14; hinstDLL
0x180001964  call    DllMain
0x180001969  mov     r8, rsi
0x18000196c  xor     edx, edx
0x18000196e  mov     rcx, r14
0x180001971  call    dllmain_crt_dispatch
0x180001976  mov     rax, cs:_pRawDllMain
0x18000197d  test    rax, rax
0x180001980  jz      short loc_18000198F
0x180001982  mov     r8, rsi
0x180001985  xor     edx, edx
0x180001987  mov     rcx, r14
0x18000198a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000198f  test    edi, edi
0x180001991  jz      short loc_180001998
0x180001993  cmp     edi, 3
0x180001996  jnz     short loc_1800019D3
0x180001998  mov     r8, rsi
0x18000199b  mov     edx, edi
0x18000199d  mov     rcx, r14
0x1800019a0  call    dllmain_crt_dispatch
0x1800019a5  mov     ebx, eax
0x1800019a7  mov     [rsp+58h+var_28], eax
0x1800019ab  test    eax, eax
0x1800019ad  jz      short loc_1800019D3
0x1800019af  mov     rax, cs:_pRawDllMain
0x1800019b6  test    rax, rax
0x1800019b9  jnz     short loc_1800019C0
0x1800019bb  lea     ebx, [rax+1]
0x1800019be  jmp     short loc_1800019CF
0x1800019c0  mov     r8, rsi
0x1800019c3  mov     edx, edi
0x1800019c5  mov     rcx, r14
0x1800019c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800019cd  mov     ebx, eax
0x1800019cf  mov     [rsp+58h+var_28], ebx
0x1800019d3  jmp     short loc_1800019DB
0x1800019d5  xor     ebx, ebx
0x1800019d7  mov     [rsp+58h+var_28], ebx
0x1800019db  mov     eax, ebx
0x1800019dd  mov     rbx, [rsp+58h+arg_18]
0x1800019e2  add     rsp, 40h
0x1800019e6  pop     r14
0x1800019e8  pop     rdi
0x1800019e9  pop     rsi
0x1800019ea  retn
0x18001084c  push    rbp
0x18001084e  sub     rsp, 30h
0x180010852  mov     rbp, rdx
0x180010855  mov     rax, [rcx]
0x180010858  mov     edx, [rax]
0x18001085a  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x18001085f  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x180010863  lea     r9, dllmain_crt_dispatch; int
0x18001086a  mov     r8, [rbp+70h]; int
0x18001086e  mov     edx, [rbp+68h]; int
0x180010871  mov     rcx, [rbp+60h]; int
0x180010875  call    __scrt_dllmain_exception_filter
0x18001087a  nop
0x18001087b  add     rsp, 30h
0x18001087f  pop     rbp
0x180010880  retn
```
