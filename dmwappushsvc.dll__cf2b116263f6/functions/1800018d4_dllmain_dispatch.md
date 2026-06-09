# dllmain_dispatch

- ea: `0x1800018d4`
- end: `0x1800019fb`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180001a10`

## callees

- `0x1800016f0`
- `0x1800018d4`
- `0x180001c20`
- `0x180001d70`
- `0x180012010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_18001C650 <= 0 )
    return 0;
  if ( fdwReason - 1 > 1
    || (pRawDllMain ? (v7 = ((__int64 (*)(void))pRawDllMain)()) : (v7 = 1),
        v7 && (v7 = dllmain_crt_dispatch((__int64)hinstDLL, fdwReason, (__int64)lpvReserved)) != 0) )
  {
    v8 = DllMain(hinstDLL, fdwReason, lpvReserved);
    v7 = v8;
    if ( fdwReason == 1 && !v8 )
    {
      DllMain(hinstDLL, 0, lpvReserved);
      dllmain_crt_dispatch((__int64)hinstDLL, 0, (__int64)lpvReserved);
      if ( pRawDllMain )
        pRawDllMain(hinstDLL, 0, lpvReserved);
    }
    if ( !fdwReason || fdwReason == 3 )
    {
      v7 = dllmain_crt_dispatch((__int64)hinstDLL, fdwReason, (__int64)lpvReserved);
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
0x1800018d4  mov     rax, rsp
0x1800018d7  mov     [rax+20h], rbx
0x1800018db  mov     [rax+18h], r8
0x1800018df  mov     [rax+10h], edx
0x1800018e2  mov     [rax+8], rcx
0x1800018e6  push    rsi
0x1800018e7  push    rdi
0x1800018e8  push    r14
0x1800018ea  sub     rsp, 40h
0x1800018ee  mov     rsi, r8
0x1800018f1  mov     edi, edx
0x1800018f3  mov     r14, rcx
0x1800018f6  test    edx, edx
0x1800018f8  jnz     short loc_180001909
0x1800018fa  cmp     cs:dword_18001C650, edx
0x180001900  jg      short loc_180001909
0x180001902  xor     eax, eax
0x180001904  jmp     loc_1800019ED
0x180001909  lea     eax, [rdx-1]
0x18000190c  cmp     eax, 1
0x18000190f  ja      short loc_180001950
0x180001911  mov     rax, cs:_pRawDllMain
0x180001918  test    rax, rax
0x18000191b  jnz     short loc_180001922
0x18000191d  lea     ebx, [rax+1]
0x180001920  jmp     short loc_180001929
0x180001922  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001927  mov     ebx, eax
0x180001929  mov     [rsp+58h+var_28], ebx
0x18000192d  test    ebx, ebx
0x18000192f  jz      loc_1800019E3
0x180001935  mov     r8, rsi
0x180001938  mov     edx, edi
0x18000193a  mov     rcx, r14
0x18000193d  call    dllmain_crt_dispatch
0x180001942  mov     ebx, eax
0x180001944  mov     [rsp+58h+var_28], eax
0x180001948  test    eax, eax
0x18000194a  jz      loc_1800019E3
0x180001950  mov     r8, rsi; lpvReserved
0x180001953  mov     edx, edi; fdwReason
0x180001955  mov     rcx, r14; hinstDLL
0x180001958  call    DllMain
0x18000195d  mov     ebx, eax
0x18000195f  mov     [rsp+58h+var_28], eax
0x180001963  cmp     edi, 1
0x180001966  jnz     short loc_18000199F
0x180001968  test    eax, eax
0x18000196a  jnz     short loc_18000199F
0x18000196c  mov     r8, rsi; lpvReserved
0x18000196f  xor     edx, edx; fdwReason
0x180001971  mov     rcx, r14; hinstDLL
0x180001974  call    DllMain
0x180001979  mov     r8, rsi
0x18000197c  xor     edx, edx
0x18000197e  mov     rcx, r14
0x180001981  call    dllmain_crt_dispatch
0x180001986  mov     rax, cs:_pRawDllMain
0x18000198d  test    rax, rax
0x180001990  jz      short loc_18000199F
0x180001992  mov     r8, rsi
0x180001995  xor     edx, edx
0x180001997  mov     rcx, r14
0x18000199a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000199f  test    edi, edi
0x1800019a1  jz      short loc_1800019A8
0x1800019a3  cmp     edi, 3
0x1800019a6  jnz     short loc_1800019E3
0x1800019a8  mov     r8, rsi
0x1800019ab  mov     edx, edi
0x1800019ad  mov     rcx, r14
0x1800019b0  call    dllmain_crt_dispatch
0x1800019b5  mov     ebx, eax
0x1800019b7  mov     [rsp+58h+var_28], eax
0x1800019bb  test    eax, eax
0x1800019bd  jz      short loc_1800019E3
0x1800019bf  mov     rax, cs:_pRawDllMain
0x1800019c6  test    rax, rax
0x1800019c9  jnz     short loc_1800019D0
0x1800019cb  lea     ebx, [rax+1]
0x1800019ce  jmp     short loc_1800019DF
0x1800019d0  mov     r8, rsi
0x1800019d3  mov     edx, edi
0x1800019d5  mov     rcx, r14
0x1800019d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800019dd  mov     ebx, eax
0x1800019df  mov     [rsp+58h+var_28], ebx
0x1800019e3  jmp     short loc_1800019EB
0x1800019e5  xor     ebx, ebx
0x1800019e7  mov     [rsp+58h+var_28], ebx
0x1800019eb  mov     eax, ebx
0x1800019ed  mov     rbx, [rsp+58h+arg_18]
0x1800019f2  add     rsp, 40h
0x1800019f6  pop     r14
0x1800019f8  pop     rdi
0x1800019f9  pop     rsi
0x1800019fa  retn
0x1800117cc  push    rbp
0x1800117ce  sub     rsp, 30h
0x1800117d2  mov     rbp, rdx
0x1800117d5  mov     rax, [rcx]
0x1800117d8  mov     edx, [rax]
0x1800117da  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x1800117df  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x1800117e3  lea     r9, dllmain_crt_dispatch; int
0x1800117ea  mov     r8, [rbp+70h]; int
0x1800117ee  mov     edx, [rbp+68h]; int
0x1800117f1  mov     rcx, [rbp+60h]; int
0x1800117f5  call    __scrt_dllmain_exception_filter
0x1800117fa  nop
0x1800117fb  add     rsp, 30h
0x1800117ff  pop     rbp
0x180011800  retn
```
