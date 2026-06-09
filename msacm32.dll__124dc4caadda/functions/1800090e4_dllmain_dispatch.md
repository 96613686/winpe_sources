# dllmain_dispatch

- ea: `0x1800090e4`
- end: `0x18000920b`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180009220`

## callees

- `0x180007400`
- `0x180008f00`
- `0x1800090e4`
- `0x180009490`
- `0x180013010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_18001A130 <= 0 )
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
0x1800090e4  mov     rax, rsp
0x1800090e7  mov     [rax+20h], rbx
0x1800090eb  mov     [rax+18h], r8
0x1800090ef  mov     [rax+10h], edx
0x1800090f2  mov     [rax+8], rcx
0x1800090f6  push    rsi
0x1800090f7  push    rdi
0x1800090f8  push    r14
0x1800090fa  sub     rsp, 40h
0x1800090fe  mov     rsi, r8
0x180009101  mov     edi, edx
0x180009103  mov     r14, rcx
0x180009106  test    edx, edx
0x180009108  jnz     short loc_180009119
0x18000910a  cmp     cs:dword_18001A130, edx
0x180009110  jg      short loc_180009119
0x180009112  xor     eax, eax
0x180009114  jmp     loc_1800091FD
0x180009119  lea     eax, [rdx-1]
0x18000911c  cmp     eax, 1
0x18000911f  ja      short loc_180009160
0x180009121  mov     rax, cs:_pRawDllMain
0x180009128  test    rax, rax
0x18000912b  jnz     short loc_180009132
0x18000912d  lea     ebx, [rax+1]
0x180009130  jmp     short loc_180009139
0x180009132  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009137  mov     ebx, eax
0x180009139  mov     [rsp+58h+var_28], ebx
0x18000913d  test    ebx, ebx
0x18000913f  jz      loc_1800091F3
0x180009145  mov     r8, rsi
0x180009148  mov     edx, edi
0x18000914a  mov     rcx, r14
0x18000914d  call    dllmain_crt_dispatch
0x180009152  mov     ebx, eax
0x180009154  mov     [rsp+58h+var_28], eax
0x180009158  test    eax, eax
0x18000915a  jz      loc_1800091F3
0x180009160  mov     r8, rsi; lpvReserved
0x180009163  mov     edx, edi; fdwReason
0x180009165  mov     rcx, r14; hinstDLL
0x180009168  call    DllMain
0x18000916d  mov     ebx, eax
0x18000916f  mov     [rsp+58h+var_28], eax
0x180009173  cmp     edi, 1
0x180009176  jnz     short loc_1800091AF
0x180009178  test    eax, eax
0x18000917a  jnz     short loc_1800091AF
0x18000917c  mov     r8, rsi; lpvReserved
0x18000917f  xor     edx, edx; fdwReason
0x180009181  mov     rcx, r14; hinstDLL
0x180009184  call    DllMain
0x180009189  mov     r8, rsi
0x18000918c  xor     edx, edx
0x18000918e  mov     rcx, r14
0x180009191  call    dllmain_crt_dispatch
0x180009196  mov     rax, cs:_pRawDllMain
0x18000919d  test    rax, rax
0x1800091a0  jz      short loc_1800091AF
0x1800091a2  mov     r8, rsi
0x1800091a5  xor     edx, edx
0x1800091a7  mov     rcx, r14
0x1800091aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800091af  test    edi, edi
0x1800091b1  jz      short loc_1800091B8
0x1800091b3  cmp     edi, 3
0x1800091b6  jnz     short loc_1800091F3
0x1800091b8  mov     r8, rsi
0x1800091bb  mov     edx, edi
0x1800091bd  mov     rcx, r14
0x1800091c0  call    dllmain_crt_dispatch
0x1800091c5  mov     ebx, eax
0x1800091c7  mov     [rsp+58h+var_28], eax
0x1800091cb  test    eax, eax
0x1800091cd  jz      short loc_1800091F3
0x1800091cf  mov     rax, cs:_pRawDllMain
0x1800091d6  test    rax, rax
0x1800091d9  jnz     short loc_1800091E0
0x1800091db  lea     ebx, [rax+1]
0x1800091de  jmp     short loc_1800091EF
0x1800091e0  mov     r8, rsi
0x1800091e3  mov     edx, edi
0x1800091e5  mov     rcx, r14
0x1800091e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800091ed  mov     ebx, eax
0x1800091ef  mov     [rsp+58h+var_28], ebx
0x1800091f3  jmp     short loc_1800091FB
0x1800091f5  xor     ebx, ebx
0x1800091f7  mov     [rsp+58h+var_28], ebx
0x1800091fb  mov     eax, ebx
0x1800091fd  mov     rbx, [rsp+58h+arg_18]
0x180009202  add     rsp, 40h
0x180009206  pop     r14
0x180009208  pop     rdi
0x180009209  pop     rsi
0x18000920a  retn
0x18001277c  push    rbp
0x18001277e  sub     rsp, 30h
0x180012782  mov     rbp, rdx
0x180012785  mov     rax, [rcx]
0x180012788  mov     edx, [rax]
0x18001278a  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x18001278f  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x180012793  lea     r9, dllmain_crt_dispatch; int
0x18001279a  mov     r8, [rbp+70h]; int
0x18001279e  mov     edx, [rbp+68h]; int
0x1800127a1  mov     rcx, [rbp+60h]; int
0x1800127a5  call    __scrt_dllmain_exception_filter
0x1800127aa  nop
0x1800127ab  add     rsp, 30h
0x1800127af  pop     rbp
0x1800127b0  retn
```
