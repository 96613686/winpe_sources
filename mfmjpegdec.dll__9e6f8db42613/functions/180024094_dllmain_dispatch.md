# dllmain_dispatch

- ea: `0x180024094`
- end: `0x1800241bb`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x1800241d0`

## callees

- `0x18001c8e4`
- `0x180023eb0`
- `0x180024094`
- `0x18002431c`
- `0x180070010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_18009CC10 <= 0 )
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
0x180024094  mov     rax, rsp
0x180024097  mov     [rax+20h], rbx
0x18002409b  mov     [rax+18h], r8
0x18002409f  mov     [rax+10h], edx
0x1800240a2  mov     [rax+8], rcx
0x1800240a6  push    rsi
0x1800240a7  push    rdi
0x1800240a8  push    r14
0x1800240aa  sub     rsp, 40h
0x1800240ae  mov     rsi, r8
0x1800240b1  mov     edi, edx
0x1800240b3  mov     r14, rcx
0x1800240b6  test    edx, edx
0x1800240b8  jnz     short loc_1800240C9
0x1800240ba  cmp     cs:dword_18009CC10, edx
0x1800240c0  jg      short loc_1800240C9
0x1800240c2  xor     eax, eax
0x1800240c4  jmp     loc_1800241AD
0x1800240c9  lea     eax, [rdx-1]
0x1800240cc  cmp     eax, 1
0x1800240cf  ja      short loc_180024110
0x1800240d1  mov     rax, cs:_pRawDllMain
0x1800240d8  test    rax, rax
0x1800240db  jnz     short loc_1800240E2
0x1800240dd  lea     ebx, [rax+1]
0x1800240e0  jmp     short loc_1800240E9
0x1800240e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800240e7  mov     ebx, eax
0x1800240e9  mov     [rsp+58h+var_28], ebx
0x1800240ed  test    ebx, ebx
0x1800240ef  jz      loc_1800241A3
0x1800240f5  mov     r8, rsi
0x1800240f8  mov     edx, edi
0x1800240fa  mov     rcx, r14
0x1800240fd  call    dllmain_crt_dispatch
0x180024102  mov     ebx, eax
0x180024104  mov     [rsp+58h+var_28], eax
0x180024108  test    eax, eax
0x18002410a  jz      loc_1800241A3
0x180024110  mov     r8, rsi; lpvReserved
0x180024113  mov     edx, edi; fdwReason
0x180024115  mov     rcx, r14; hinstDLL
0x180024118  call    DllMain
0x18002411d  mov     ebx, eax
0x18002411f  mov     [rsp+58h+var_28], eax
0x180024123  cmp     edi, 1
0x180024126  jnz     short loc_18002415F
0x180024128  test    eax, eax
0x18002412a  jnz     short loc_18002415F
0x18002412c  mov     r8, rsi; lpvReserved
0x18002412f  xor     edx, edx; fdwReason
0x180024131  mov     rcx, r14; hinstDLL
0x180024134  call    DllMain
0x180024139  mov     r8, rsi
0x18002413c  xor     edx, edx
0x18002413e  mov     rcx, r14
0x180024141  call    dllmain_crt_dispatch
0x180024146  mov     rax, cs:_pRawDllMain
0x18002414d  test    rax, rax
0x180024150  jz      short loc_18002415F
0x180024152  mov     r8, rsi
0x180024155  xor     edx, edx
0x180024157  mov     rcx, r14
0x18002415a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002415f  test    edi, edi
0x180024161  jz      short loc_180024168
0x180024163  cmp     edi, 3
0x180024166  jnz     short loc_1800241A3
0x180024168  mov     r8, rsi
0x18002416b  mov     edx, edi
0x18002416d  mov     rcx, r14
0x180024170  call    dllmain_crt_dispatch
0x180024175  mov     ebx, eax
0x180024177  mov     [rsp+58h+var_28], eax
0x18002417b  test    eax, eax
0x18002417d  jz      short loc_1800241A3
0x18002417f  mov     rax, cs:_pRawDllMain
0x180024186  test    rax, rax
0x180024189  jnz     short loc_180024190
0x18002418b  lea     ebx, [rax+1]
0x18002418e  jmp     short loc_18002419F
0x180024190  mov     r8, rsi
0x180024193  mov     edx, edi
0x180024195  mov     rcx, r14
0x180024198  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002419d  mov     ebx, eax
0x18002419f  mov     [rsp+58h+var_28], ebx
0x1800241a3  jmp     short loc_1800241AB
0x1800241a5  xor     ebx, ebx
0x1800241a7  mov     [rsp+58h+var_28], ebx
0x1800241ab  mov     eax, ebx
0x1800241ad  mov     rbx, [rsp+58h+arg_18]
0x1800241b2  add     rsp, 40h
0x1800241b6  pop     r14
0x1800241b8  pop     rdi
0x1800241b9  pop     rsi
0x1800241ba  retn
0x18006f0ea  push    rbp
0x18006f0ec  sub     rsp, 30h
0x18006f0f0  mov     rbp, rdx
0x18006f0f3  mov     rax, [rcx]
0x18006f0f6  mov     edx, [rax]
0x18006f0f8  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x18006f0fd  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x18006f101  lea     r9, dllmain_crt_dispatch; int
0x18006f108  mov     r8, [rbp+70h]; int
0x18006f10c  mov     edx, [rbp+68h]; int
0x18006f10f  mov     rcx, [rbp+60h]; int
0x18006f113  call    __scrt_dllmain_exception_filter
0x18006f118  nop
0x18006f119  add     rsp, 30h
0x18006f11d  pop     rbp
0x18006f11e  retn
```
