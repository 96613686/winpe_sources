# dllmain_dispatch

- ea: `0x180009184`
- end: `0x1800092ab`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x1800092c0`

## callees

- `0x180008fa0`
- `0x180009184`
- `0x180009514`
- `0x18000a7a8`
- `0x18000b010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_18000F090 <= 0 )
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
0x180009184  mov     rax, rsp
0x180009187  mov     [rax+20h], rbx
0x18000918b  mov     [rax+18h], r8
0x18000918f  mov     [rax+10h], edx
0x180009192  mov     [rax+8], rcx
0x180009196  push    rsi
0x180009197  push    rdi
0x180009198  push    r14
0x18000919a  sub     rsp, 40h
0x18000919e  mov     rsi, r8
0x1800091a1  mov     edi, edx
0x1800091a3  mov     r14, rcx
0x1800091a6  test    edx, edx
0x1800091a8  jnz     short loc_1800091B9
0x1800091aa  cmp     cs:dword_18000F090, edx
0x1800091b0  jg      short loc_1800091B9
0x1800091b2  xor     eax, eax
0x1800091b4  jmp     loc_18000929D
0x1800091b9  lea     eax, [rdx-1]
0x1800091bc  cmp     eax, 1
0x1800091bf  ja      short loc_180009200
0x1800091c1  mov     rax, cs:_pRawDllMain
0x1800091c8  test    rax, rax
0x1800091cb  jnz     short loc_1800091D2
0x1800091cd  lea     ebx, [rax+1]
0x1800091d0  jmp     short loc_1800091D9
0x1800091d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800091d7  mov     ebx, eax
0x1800091d9  mov     [rsp+58h+var_28], ebx
0x1800091dd  test    ebx, ebx
0x1800091df  jz      loc_180009293
0x1800091e5  mov     r8, rsi
0x1800091e8  mov     edx, edi
0x1800091ea  mov     rcx, r14
0x1800091ed  call    dllmain_crt_dispatch
0x1800091f2  mov     ebx, eax
0x1800091f4  mov     [rsp+58h+var_28], eax
0x1800091f8  test    eax, eax
0x1800091fa  jz      loc_180009293
0x180009200  mov     r8, rsi; lpvReserved
0x180009203  mov     edx, edi; fdwReason
0x180009205  mov     rcx, r14; hinstDLL
0x180009208  call    DllMain
0x18000920d  mov     ebx, eax
0x18000920f  mov     [rsp+58h+var_28], eax
0x180009213  cmp     edi, 1
0x180009216  jnz     short loc_18000924F
0x180009218  test    eax, eax
0x18000921a  jnz     short loc_18000924F
0x18000921c  mov     r8, rsi; lpvReserved
0x18000921f  xor     edx, edx; fdwReason
0x180009221  mov     rcx, r14; hinstDLL
0x180009224  call    DllMain
0x180009229  mov     r8, rsi
0x18000922c  xor     edx, edx
0x18000922e  mov     rcx, r14
0x180009231  call    dllmain_crt_dispatch
0x180009236  mov     rax, cs:_pRawDllMain
0x18000923d  test    rax, rax
0x180009240  jz      short loc_18000924F
0x180009242  mov     r8, rsi
0x180009245  xor     edx, edx
0x180009247  mov     rcx, r14
0x18000924a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000924f  test    edi, edi
0x180009251  jz      short loc_180009258
0x180009253  cmp     edi, 3
0x180009256  jnz     short loc_180009293
0x180009258  mov     r8, rsi
0x18000925b  mov     edx, edi
0x18000925d  mov     rcx, r14
0x180009260  call    dllmain_crt_dispatch
0x180009265  mov     ebx, eax
0x180009267  mov     [rsp+58h+var_28], eax
0x18000926b  test    eax, eax
0x18000926d  jz      short loc_180009293
0x18000926f  mov     rax, cs:_pRawDllMain
0x180009276  test    rax, rax
0x180009279  jnz     short loc_180009280
0x18000927b  lea     ebx, [rax+1]
0x18000927e  jmp     short loc_18000928F
0x180009280  mov     r8, rsi
0x180009283  mov     edx, edi
0x180009285  mov     rcx, r14
0x180009288  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000928d  mov     ebx, eax
0x18000928f  mov     [rsp+58h+var_28], ebx
0x180009293  jmp     short loc_18000929B
0x180009295  xor     ebx, ebx
0x180009297  mov     [rsp+58h+var_28], ebx
0x18000929b  mov     eax, ebx
0x18000929d  mov     rbx, [rsp+58h+arg_18]
0x1800092a2  add     rsp, 40h
0x1800092a6  pop     r14
0x1800092a8  pop     rdi
0x1800092a9  pop     rsi
0x1800092aa  retn
0x18000abac  push    rbp
0x18000abae  sub     rsp, 30h
0x18000abb2  mov     rbp, rdx
0x18000abb5  mov     rax, [rcx]
0x18000abb8  mov     edx, [rax]
0x18000abba  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x18000abbf  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x18000abc3  lea     r9, dllmain_crt_dispatch; int
0x18000abca  mov     r8, [rbp+70h]; int
0x18000abce  mov     edx, [rbp+68h]; int
0x18000abd1  mov     rcx, [rbp+60h]; int
0x18000abd5  call    __scrt_dllmain_exception_filter
0x18000abda  nop
0x18000abdb  add     rsp, 30h
0x18000abdf  pop     rbp
0x18000abe0  retn
```
