# dllmain_dispatch

- ea: `0x18001e034`
- end: `0x18001e15b`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x18001e170`

## callees

- `0x180011ec4`
- `0x18001de50`
- `0x18001e034`
- `0x18001e2cc`
- `0x180030010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_18003C490 <= 0 )
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
0x18001e034  mov     rax, rsp
0x18001e037  mov     [rax+20h], rbx
0x18001e03b  mov     [rax+18h], r8
0x18001e03f  mov     [rax+10h], edx
0x18001e042  mov     [rax+8], rcx
0x18001e046  push    rsi
0x18001e047  push    rdi
0x18001e048  push    r14
0x18001e04a  sub     rsp, 40h
0x18001e04e  mov     rsi, r8
0x18001e051  mov     edi, edx
0x18001e053  mov     r14, rcx
0x18001e056  test    edx, edx
0x18001e058  jnz     short loc_18001E069
0x18001e05a  cmp     cs:dword_18003C490, edx
0x18001e060  jg      short loc_18001E069
0x18001e062  xor     eax, eax
0x18001e064  jmp     loc_18001E14D
0x18001e069  lea     eax, [rdx-1]
0x18001e06c  cmp     eax, 1
0x18001e06f  ja      short loc_18001E0B0
0x18001e071  mov     rax, cs:_pRawDllMain
0x18001e078  test    rax, rax
0x18001e07b  jnz     short loc_18001E082
0x18001e07d  lea     ebx, [rax+1]
0x18001e080  jmp     short loc_18001E089
0x18001e082  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e087  mov     ebx, eax
0x18001e089  mov     [rsp+58h+var_28], ebx
0x18001e08d  test    ebx, ebx
0x18001e08f  jz      loc_18001E143
0x18001e095  mov     r8, rsi
0x18001e098  mov     edx, edi
0x18001e09a  mov     rcx, r14
0x18001e09d  call    dllmain_crt_dispatch
0x18001e0a2  mov     ebx, eax
0x18001e0a4  mov     [rsp+58h+var_28], eax
0x18001e0a8  test    eax, eax
0x18001e0aa  jz      loc_18001E143
0x18001e0b0  mov     r8, rsi; lpvReserved
0x18001e0b3  mov     edx, edi; fdwReason
0x18001e0b5  mov     rcx, r14; hinstDLL
0x18001e0b8  call    DllMain
0x18001e0bd  mov     ebx, eax
0x18001e0bf  mov     [rsp+58h+var_28], eax
0x18001e0c3  cmp     edi, 1
0x18001e0c6  jnz     short loc_18001E0FF
0x18001e0c8  test    eax, eax
0x18001e0ca  jnz     short loc_18001E0FF
0x18001e0cc  mov     r8, rsi; lpvReserved
0x18001e0cf  xor     edx, edx; fdwReason
0x18001e0d1  mov     rcx, r14; hinstDLL
0x18001e0d4  call    DllMain
0x18001e0d9  mov     r8, rsi
0x18001e0dc  xor     edx, edx
0x18001e0de  mov     rcx, r14
0x18001e0e1  call    dllmain_crt_dispatch
0x18001e0e6  mov     rax, cs:_pRawDllMain
0x18001e0ed  test    rax, rax
0x18001e0f0  jz      short loc_18001E0FF
0x18001e0f2  mov     r8, rsi
0x18001e0f5  xor     edx, edx
0x18001e0f7  mov     rcx, r14
0x18001e0fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e0ff  test    edi, edi
0x18001e101  jz      short loc_18001E108
0x18001e103  cmp     edi, 3
0x18001e106  jnz     short loc_18001E143
0x18001e108  mov     r8, rsi
0x18001e10b  mov     edx, edi
0x18001e10d  mov     rcx, r14
0x18001e110  call    dllmain_crt_dispatch
0x18001e115  mov     ebx, eax
0x18001e117  mov     [rsp+58h+var_28], eax
0x18001e11b  test    eax, eax
0x18001e11d  jz      short loc_18001E143
0x18001e11f  mov     rax, cs:_pRawDllMain
0x18001e126  test    rax, rax
0x18001e129  jnz     short loc_18001E130
0x18001e12b  lea     ebx, [rax+1]
0x18001e12e  jmp     short loc_18001E13F
0x18001e130  mov     r8, rsi
0x18001e133  mov     edx, edi
0x18001e135  mov     rcx, r14
0x18001e138  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e13d  mov     ebx, eax
0x18001e13f  mov     [rsp+58h+var_28], ebx
0x18001e143  jmp     short loc_18001E14B
0x18001e145  xor     ebx, ebx
0x18001e147  mov     [rsp+58h+var_28], ebx
0x18001e14b  mov     eax, ebx
0x18001e14d  mov     rbx, [rsp+58h+arg_18]
0x18001e152  add     rsp, 40h
0x18001e156  pop     r14
0x18001e158  pop     rdi
0x18001e159  pop     rsi
0x18001e15a  retn
0x18002f750  push    rbp
0x18002f752  sub     rsp, 30h
0x18002f756  mov     rbp, rdx
0x18002f759  mov     rax, [rcx]
0x18002f75c  mov     edx, [rax]
0x18002f75e  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x18002f763  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x18002f767  lea     r9, dllmain_crt_dispatch; int
0x18002f76e  mov     r8, [rbp+70h]; int
0x18002f772  mov     edx, [rbp+68h]; int
0x18002f775  mov     rcx, [rbp+60h]; int
0x18002f779  call    __scrt_dllmain_exception_filter
0x18002f77e  nop
0x18002f77f  add     rsp, 30h
0x18002f783  pop     rbp
0x18002f784  retn
```
