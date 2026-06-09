# dllmain_dispatch

- ea: `0x180002514`
- end: `0x18000263b`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180002644`

## callees

- `0x18000128c`
- `0x180002330`
- `0x180002514`
- `0x1800029a8`
- `0x18000c010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_180012240 <= 0 )
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
0x180002514  mov     rax, rsp
0x180002517  mov     [rax+20h], rbx
0x18000251b  mov     [rax+18h], r8
0x18000251f  mov     [rax+10h], edx
0x180002522  mov     [rax+8], rcx
0x180002526  push    rsi
0x180002527  push    rdi
0x180002528  push    r14
0x18000252a  sub     rsp, 40h
0x18000252e  mov     rsi, r8
0x180002531  mov     edi, edx
0x180002533  mov     r14, rcx
0x180002536  test    edx, edx
0x180002538  jnz     short loc_180002549
0x18000253a  cmp     cs:dword_180012240, edx
0x180002540  jg      short loc_180002549
0x180002542  xor     eax, eax
0x180002544  jmp     loc_18000262D
0x180002549  lea     eax, [rdx-1]
0x18000254c  cmp     eax, 1
0x18000254f  ja      short loc_180002590
0x180002551  mov     rax, cs:_pRawDllMain
0x180002558  test    rax, rax
0x18000255b  jnz     short loc_180002562
0x18000255d  lea     ebx, [rax+1]
0x180002560  jmp     short loc_180002569
0x180002562  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002567  mov     ebx, eax
0x180002569  mov     [rsp+58h+var_28], ebx
0x18000256d  test    ebx, ebx
0x18000256f  jz      loc_180002623
0x180002575  mov     r8, rsi
0x180002578  mov     edx, edi
0x18000257a  mov     rcx, r14
0x18000257d  call    dllmain_crt_dispatch
0x180002582  mov     ebx, eax
0x180002584  mov     [rsp+58h+var_28], eax
0x180002588  test    eax, eax
0x18000258a  jz      loc_180002623
0x180002590  mov     r8, rsi; lpvReserved
0x180002593  mov     edx, edi; fdwReason
0x180002595  mov     rcx, r14; hinstDLL
0x180002598  call    DllMain
0x18000259d  mov     ebx, eax
0x18000259f  mov     [rsp+58h+var_28], eax
0x1800025a3  cmp     edi, 1
0x1800025a6  jnz     short loc_1800025DF
0x1800025a8  test    eax, eax
0x1800025aa  jnz     short loc_1800025DF
0x1800025ac  mov     r8, rsi; lpvReserved
0x1800025af  xor     edx, edx; fdwReason
0x1800025b1  mov     rcx, r14; hinstDLL
0x1800025b4  call    DllMain
0x1800025b9  mov     r8, rsi
0x1800025bc  xor     edx, edx
0x1800025be  mov     rcx, r14
0x1800025c1  call    dllmain_crt_dispatch
0x1800025c6  mov     rax, cs:_pRawDllMain
0x1800025cd  test    rax, rax
0x1800025d0  jz      short loc_1800025DF
0x1800025d2  mov     r8, rsi
0x1800025d5  xor     edx, edx
0x1800025d7  mov     rcx, r14
0x1800025da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800025df  test    edi, edi
0x1800025e1  jz      short loc_1800025E8
0x1800025e3  cmp     edi, 3
0x1800025e6  jnz     short loc_180002623
0x1800025e8  mov     r8, rsi
0x1800025eb  mov     edx, edi
0x1800025ed  mov     rcx, r14
0x1800025f0  call    dllmain_crt_dispatch
0x1800025f5  mov     ebx, eax
0x1800025f7  mov     [rsp+58h+var_28], eax
0x1800025fb  test    eax, eax
0x1800025fd  jz      short loc_180002623
0x1800025ff  mov     rax, cs:_pRawDllMain
0x180002606  test    rax, rax
0x180002609  jnz     short loc_180002610
0x18000260b  lea     ebx, [rax+1]
0x18000260e  jmp     short loc_18000261F
0x180002610  mov     r8, rsi
0x180002613  mov     edx, edi
0x180002615  mov     rcx, r14
0x180002618  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000261d  mov     ebx, eax
0x18000261f  mov     [rsp+58h+var_28], ebx
0x180002623  jmp     short loc_18000262B
0x180002625  xor     ebx, ebx
0x180002627  mov     [rsp+58h+var_28], ebx
0x18000262b  mov     eax, ebx
0x18000262d  mov     rbx, [rsp+58h+arg_18]
0x180002632  add     rsp, 40h
0x180002636  pop     r14
0x180002638  pop     rdi
0x180002639  pop     rsi
0x18000263a  retn
0x18000b4ba  push    rbp
0x18000b4bc  sub     rsp, 30h
0x18000b4c0  mov     rbp, rdx
0x18000b4c3  mov     rax, [rcx]
0x18000b4c6  mov     edx, [rax]
0x18000b4c8  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x18000b4cd  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x18000b4d1  lea     r9, dllmain_crt_dispatch; int
0x18000b4d8  mov     r8, [rbp+70h]; int
0x18000b4dc  mov     edx, [rbp+68h]; int
0x18000b4df  mov     rcx, [rbp+60h]; int
0x18000b4e3  call    __scrt_dllmain_exception_filter
0x18000b4e8  nop
0x18000b4e9  add     rsp, 30h
0x18000b4ed  pop     rbp
0x18000b4ee  retn
```
