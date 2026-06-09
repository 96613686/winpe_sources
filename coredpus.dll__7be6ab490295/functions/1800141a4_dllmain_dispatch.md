# dllmain_dispatch

- ea: `0x1800141a4`
- end: `0x1800142cb`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x1800142e0`

## callees

- `0x180004650`
- `0x180013fc0`
- `0x1800141a4`
- `0x1800148d0`
- `0x180030010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_18003E990 <= 0 )
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
0x1800141a4  mov     rax, rsp
0x1800141a7  mov     [rax+20h], rbx
0x1800141ab  mov     [rax+18h], r8
0x1800141af  mov     [rax+10h], edx
0x1800141b2  mov     [rax+8], rcx
0x1800141b6  push    rsi
0x1800141b7  push    rdi
0x1800141b8  push    r14
0x1800141ba  sub     rsp, 40h
0x1800141be  mov     rsi, r8
0x1800141c1  mov     edi, edx
0x1800141c3  mov     r14, rcx
0x1800141c6  test    edx, edx
0x1800141c8  jnz     short loc_1800141D9
0x1800141ca  cmp     cs:dword_18003E990, edx
0x1800141d0  jg      short loc_1800141D9
0x1800141d2  xor     eax, eax
0x1800141d4  jmp     loc_1800142BD
0x1800141d9  lea     eax, [rdx-1]
0x1800141dc  cmp     eax, 1
0x1800141df  ja      short loc_180014220
0x1800141e1  mov     rax, cs:_pRawDllMain
0x1800141e8  test    rax, rax
0x1800141eb  jnz     short loc_1800141F2
0x1800141ed  lea     ebx, [rax+1]
0x1800141f0  jmp     short loc_1800141F9
0x1800141f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800141f7  mov     ebx, eax
0x1800141f9  mov     [rsp+58h+var_28], ebx
0x1800141fd  test    ebx, ebx
0x1800141ff  jz      loc_1800142B3
0x180014205  mov     r8, rsi
0x180014208  mov     edx, edi
0x18001420a  mov     rcx, r14
0x18001420d  call    dllmain_crt_dispatch
0x180014212  mov     ebx, eax
0x180014214  mov     [rsp+58h+var_28], eax
0x180014218  test    eax, eax
0x18001421a  jz      loc_1800142B3
0x180014220  mov     r8, rsi; lpvReserved
0x180014223  mov     edx, edi; fdwReason
0x180014225  mov     rcx, r14; hinstDLL
0x180014228  call    DllMain
0x18001422d  mov     ebx, eax
0x18001422f  mov     [rsp+58h+var_28], eax
0x180014233  cmp     edi, 1
0x180014236  jnz     short loc_18001426F
0x180014238  test    eax, eax
0x18001423a  jnz     short loc_18001426F
0x18001423c  mov     r8, rsi; lpvReserved
0x18001423f  xor     edx, edx; fdwReason
0x180014241  mov     rcx, r14; hinstDLL
0x180014244  call    DllMain
0x180014249  mov     r8, rsi
0x18001424c  xor     edx, edx
0x18001424e  mov     rcx, r14
0x180014251  call    dllmain_crt_dispatch
0x180014256  mov     rax, cs:_pRawDllMain
0x18001425d  test    rax, rax
0x180014260  jz      short loc_18001426F
0x180014262  mov     r8, rsi
0x180014265  xor     edx, edx
0x180014267  mov     rcx, r14
0x18001426a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001426f  test    edi, edi
0x180014271  jz      short loc_180014278
0x180014273  cmp     edi, 3
0x180014276  jnz     short loc_1800142B3
0x180014278  mov     r8, rsi
0x18001427b  mov     edx, edi
0x18001427d  mov     rcx, r14
0x180014280  call    dllmain_crt_dispatch
0x180014285  mov     ebx, eax
0x180014287  mov     [rsp+58h+var_28], eax
0x18001428b  test    eax, eax
0x18001428d  jz      short loc_1800142B3
0x18001428f  mov     rax, cs:_pRawDllMain
0x180014296  test    rax, rax
0x180014299  jnz     short loc_1800142A0
0x18001429b  lea     ebx, [rax+1]
0x18001429e  jmp     short loc_1800142AF
0x1800142a0  mov     r8, rsi
0x1800142a3  mov     edx, edi
0x1800142a5  mov     rcx, r14
0x1800142a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800142ad  mov     ebx, eax
0x1800142af  mov     [rsp+58h+var_28], ebx
0x1800142b3  jmp     short loc_1800142BB
0x1800142b5  xor     ebx, ebx
0x1800142b7  mov     [rsp+58h+var_28], ebx
0x1800142bb  mov     eax, ebx
0x1800142bd  mov     rbx, [rsp+58h+arg_18]
0x1800142c2  add     rsp, 40h
0x1800142c6  pop     r14
0x1800142c8  pop     rdi
0x1800142c9  pop     rsi
0x1800142ca  retn
0x18002e758  push    rbp
0x18002e75a  sub     rsp, 30h
0x18002e75e  mov     rbp, rdx
0x18002e761  mov     rax, [rcx]
0x18002e764  mov     edx, [rax]
0x18002e766  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x18002e76b  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x18002e76f  lea     r9, dllmain_crt_dispatch; int
0x18002e776  mov     r8, [rbp+70h]; int
0x18002e77a  mov     edx, [rbp+68h]; int
0x18002e77d  mov     rcx, [rbp+60h]; int
0x18002e781  call    __scrt_dllmain_exception_filter
0x18002e786  nop
0x18002e787  add     rsp, 30h
0x18002e78b  pop     rbp
0x18002e78c  retn
```
