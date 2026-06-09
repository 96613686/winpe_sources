# dllmain_dispatch

- ea: `0x180002304`
- end: `0x18000242b`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180002440`

## callees

- `0x180002120`
- `0x180002304`
- `0x18000258c`
- `0x18000299c`
- `0x180030010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_18003F570 <= 0 )
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
0x180002304  mov     rax, rsp
0x180002307  mov     [rax+20h], rbx
0x18000230b  mov     [rax+18h], r8
0x18000230f  mov     [rax+10h], edx
0x180002312  mov     [rax+8], rcx
0x180002316  push    rsi
0x180002317  push    rdi
0x180002318  push    r14
0x18000231a  sub     rsp, 40h
0x18000231e  mov     rsi, r8
0x180002321  mov     edi, edx
0x180002323  mov     r14, rcx
0x180002326  test    edx, edx
0x180002328  jnz     short loc_180002339
0x18000232a  cmp     cs:dword_18003F570, edx
0x180002330  jg      short loc_180002339
0x180002332  xor     eax, eax
0x180002334  jmp     loc_18000241D
0x180002339  lea     eax, [rdx-1]
0x18000233c  cmp     eax, 1
0x18000233f  ja      short loc_180002380
0x180002341  mov     rax, cs:_pRawDllMain
0x180002348  test    rax, rax
0x18000234b  jnz     short loc_180002352
0x18000234d  lea     ebx, [rax+1]
0x180002350  jmp     short loc_180002359
0x180002352  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002357  mov     ebx, eax
0x180002359  mov     [rsp+58h+var_28], ebx
0x18000235d  test    ebx, ebx
0x18000235f  jz      loc_180002413
0x180002365  mov     r8, rsi
0x180002368  mov     edx, edi
0x18000236a  mov     rcx, r14
0x18000236d  call    dllmain_crt_dispatch
0x180002372  mov     ebx, eax
0x180002374  mov     [rsp+58h+var_28], eax
0x180002378  test    eax, eax
0x18000237a  jz      loc_180002413
0x180002380  mov     r8, rsi; lpvReserved
0x180002383  mov     edx, edi; fdwReason
0x180002385  mov     rcx, r14; hinstDLL
0x180002388  call    DllMain
0x18000238d  mov     ebx, eax
0x18000238f  mov     [rsp+58h+var_28], eax
0x180002393  cmp     edi, 1
0x180002396  jnz     short loc_1800023CF
0x180002398  test    eax, eax
0x18000239a  jnz     short loc_1800023CF
0x18000239c  mov     r8, rsi; lpvReserved
0x18000239f  xor     edx, edx; fdwReason
0x1800023a1  mov     rcx, r14; hinstDLL
0x1800023a4  call    DllMain
0x1800023a9  mov     r8, rsi
0x1800023ac  xor     edx, edx
0x1800023ae  mov     rcx, r14
0x1800023b1  call    dllmain_crt_dispatch
0x1800023b6  mov     rax, cs:_pRawDllMain
0x1800023bd  test    rax, rax
0x1800023c0  jz      short loc_1800023CF
0x1800023c2  mov     r8, rsi
0x1800023c5  xor     edx, edx
0x1800023c7  mov     rcx, r14
0x1800023ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800023cf  test    edi, edi
0x1800023d1  jz      short loc_1800023D8
0x1800023d3  cmp     edi, 3
0x1800023d6  jnz     short loc_180002413
0x1800023d8  mov     r8, rsi
0x1800023db  mov     edx, edi
0x1800023dd  mov     rcx, r14
0x1800023e0  call    dllmain_crt_dispatch
0x1800023e5  mov     ebx, eax
0x1800023e7  mov     [rsp+58h+var_28], eax
0x1800023eb  test    eax, eax
0x1800023ed  jz      short loc_180002413
0x1800023ef  mov     rax, cs:_pRawDllMain
0x1800023f6  test    rax, rax
0x1800023f9  jnz     short loc_180002400
0x1800023fb  lea     ebx, [rax+1]
0x1800023fe  jmp     short loc_18000240F
0x180002400  mov     r8, rsi
0x180002403  mov     edx, edi
0x180002405  mov     rcx, r14
0x180002408  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000240d  mov     ebx, eax
0x18000240f  mov     [rsp+58h+var_28], ebx
0x180002413  jmp     short loc_18000241B
0x180002415  xor     ebx, ebx
0x180002417  mov     [rsp+58h+var_28], ebx
0x18000241b  mov     eax, ebx
0x18000241d  mov     rbx, [rsp+58h+arg_18]
0x180002422  add     rsp, 40h
0x180002426  pop     r14
0x180002428  pop     rdi
0x180002429  pop     rsi
0x18000242a  retn
0x18002e0cc  push    rbp
0x18002e0ce  sub     rsp, 30h
0x18002e0d2  mov     rbp, rdx
0x18002e0d5  mov     rax, [rcx]
0x18002e0d8  mov     edx, [rax]
0x18002e0da  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x18002e0df  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x18002e0e3  lea     r9, dllmain_crt_dispatch; int
0x18002e0ea  mov     r8, [rbp+70h]; int
0x18002e0ee  mov     edx, [rbp+68h]; int
0x18002e0f1  mov     rcx, [rbp+60h]; int
0x18002e0f5  call    __scrt_dllmain_exception_filter
0x18002e0fa  nop
0x18002e0fb  add     rsp, 30h
0x18002e0ff  pop     rbp
0x18002e100  retn
```
