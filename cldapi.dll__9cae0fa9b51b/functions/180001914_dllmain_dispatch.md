# dllmain_dispatch

- ea: `0x180001914`
- end: `0x180001a3b`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180001a50`

## callees

- `0x180001730`
- `0x180001914`
- `0x180001ca4`
- `0x18000261c`
- `0x18001e010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_18002A810 <= 0 )
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
0x180001914  mov     rax, rsp
0x180001917  mov     [rax+20h], rbx
0x18000191b  mov     [rax+18h], r8
0x18000191f  mov     [rax+10h], edx
0x180001922  mov     [rax+8], rcx
0x180001926  push    rsi
0x180001927  push    rdi
0x180001928  push    r14
0x18000192a  sub     rsp, 40h
0x18000192e  mov     rsi, r8
0x180001931  mov     edi, edx
0x180001933  mov     r14, rcx
0x180001936  test    edx, edx
0x180001938  jnz     short loc_180001949
0x18000193a  cmp     cs:dword_18002A810, edx
0x180001940  jg      short loc_180001949
0x180001942  xor     eax, eax
0x180001944  jmp     loc_180001A2D
0x180001949  lea     eax, [rdx-1]
0x18000194c  cmp     eax, 1
0x18000194f  ja      short loc_180001990
0x180001951  mov     rax, cs:_pRawDllMain
0x180001958  test    rax, rax
0x18000195b  jnz     short loc_180001962
0x18000195d  lea     ebx, [rax+1]
0x180001960  jmp     short loc_180001969
0x180001962  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001967  mov     ebx, eax
0x180001969  mov     [rsp+58h+var_28], ebx
0x18000196d  test    ebx, ebx
0x18000196f  jz      loc_180001A23
0x180001975  mov     r8, rsi
0x180001978  mov     edx, edi
0x18000197a  mov     rcx, r14
0x18000197d  call    dllmain_crt_dispatch
0x180001982  mov     ebx, eax
0x180001984  mov     [rsp+58h+var_28], eax
0x180001988  test    eax, eax
0x18000198a  jz      loc_180001A23
0x180001990  mov     r8, rsi; lpvReserved
0x180001993  mov     edx, edi; fdwReason
0x180001995  mov     rcx, r14; hinstDLL
0x180001998  call    DllMain
0x18000199d  mov     ebx, eax
0x18000199f  mov     [rsp+58h+var_28], eax
0x1800019a3  cmp     edi, 1
0x1800019a6  jnz     short loc_1800019DF
0x1800019a8  test    eax, eax
0x1800019aa  jnz     short loc_1800019DF
0x1800019ac  mov     r8, rsi; lpvReserved
0x1800019af  xor     edx, edx; fdwReason
0x1800019b1  mov     rcx, r14; hinstDLL
0x1800019b4  call    DllMain
0x1800019b9  mov     r8, rsi
0x1800019bc  xor     edx, edx
0x1800019be  mov     rcx, r14
0x1800019c1  call    dllmain_crt_dispatch
0x1800019c6  mov     rax, cs:_pRawDllMain
0x1800019cd  test    rax, rax
0x1800019d0  jz      short loc_1800019DF
0x1800019d2  mov     r8, rsi
0x1800019d5  xor     edx, edx
0x1800019d7  mov     rcx, r14
0x1800019da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800019df  test    edi, edi
0x1800019e1  jz      short loc_1800019E8
0x1800019e3  cmp     edi, 3
0x1800019e6  jnz     short loc_180001A23
0x1800019e8  mov     r8, rsi
0x1800019eb  mov     edx, edi
0x1800019ed  mov     rcx, r14
0x1800019f0  call    dllmain_crt_dispatch
0x1800019f5  mov     ebx, eax
0x1800019f7  mov     [rsp+58h+var_28], eax
0x1800019fb  test    eax, eax
0x1800019fd  jz      short loc_180001A23
0x1800019ff  mov     rax, cs:_pRawDllMain
0x180001a06  test    rax, rax
0x180001a09  jnz     short loc_180001A10
0x180001a0b  lea     ebx, [rax+1]
0x180001a0e  jmp     short loc_180001A1F
0x180001a10  mov     r8, rsi
0x180001a13  mov     edx, edi
0x180001a15  mov     rcx, r14
0x180001a18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001a1d  mov     ebx, eax
0x180001a1f  mov     [rsp+58h+var_28], ebx
0x180001a23  jmp     short loc_180001A2B
0x180001a25  xor     ebx, ebx
0x180001a27  mov     [rsp+58h+var_28], ebx
0x180001a2b  mov     eax, ebx
0x180001a2d  mov     rbx, [rsp+58h+arg_18]
0x180001a32  add     rsp, 40h
0x180001a36  pop     r14
0x180001a38  pop     rdi
0x180001a39  pop     rsi
0x180001a3a  retn
0x18001d17c  push    rbp
0x18001d17e  sub     rsp, 30h
0x18001d182  mov     rbp, rdx
0x18001d185  mov     rax, [rcx]
0x18001d188  mov     edx, [rax]
0x18001d18a  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x18001d18f  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x18001d193  lea     r9, dllmain_crt_dispatch; int
0x18001d19a  mov     r8, [rbp+70h]; int
0x18001d19e  mov     edx, [rbp+68h]; int
0x18001d1a1  mov     rcx, [rbp+60h]; int
0x18001d1a5  call    __scrt_dllmain_exception_filter
0x18001d1aa  nop
0x18001d1ab  add     rsp, 30h
0x18001d1af  pop     rbp
0x18001d1b0  retn
```
