# dllmain_dispatch

- ea: `0x180001584`
- end: `0x1800016ab`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x1800016c0`

## callees

- `0x1800013a0`
- `0x180001584`
- `0x18000180c`
- `0x180001ed4`
- `0x18002c010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_18003C528 <= 0 )
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
0x180001584  mov     rax, rsp
0x180001587  mov     [rax+20h], rbx
0x18000158b  mov     [rax+18h], r8
0x18000158f  mov     [rax+10h], edx
0x180001592  mov     [rax+8], rcx
0x180001596  push    rsi
0x180001597  push    rdi
0x180001598  push    r14
0x18000159a  sub     rsp, 40h
0x18000159e  mov     rsi, r8
0x1800015a1  mov     edi, edx
0x1800015a3  mov     r14, rcx
0x1800015a6  test    edx, edx
0x1800015a8  jnz     short loc_1800015B9
0x1800015aa  cmp     cs:dword_18003C528, edx
0x1800015b0  jg      short loc_1800015B9
0x1800015b2  xor     eax, eax
0x1800015b4  jmp     loc_18000169D
0x1800015b9  lea     eax, [rdx-1]
0x1800015bc  cmp     eax, 1
0x1800015bf  ja      short loc_180001600
0x1800015c1  mov     rax, cs:_pRawDllMain
0x1800015c8  test    rax, rax
0x1800015cb  jnz     short loc_1800015D2
0x1800015cd  lea     ebx, [rax+1]
0x1800015d0  jmp     short loc_1800015D9
0x1800015d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800015d7  mov     ebx, eax
0x1800015d9  mov     [rsp+58h+var_28], ebx
0x1800015dd  test    ebx, ebx
0x1800015df  jz      loc_180001693
0x1800015e5  mov     r8, rsi
0x1800015e8  mov     edx, edi
0x1800015ea  mov     rcx, r14
0x1800015ed  call    dllmain_crt_dispatch
0x1800015f2  mov     ebx, eax
0x1800015f4  mov     [rsp+58h+var_28], eax
0x1800015f8  test    eax, eax
0x1800015fa  jz      loc_180001693
0x180001600  mov     r8, rsi; lpvReserved
0x180001603  mov     edx, edi; fdwReason
0x180001605  mov     rcx, r14; hinstDLL
0x180001608  call    DllMain
0x18000160d  mov     ebx, eax
0x18000160f  mov     [rsp+58h+var_28], eax
0x180001613  cmp     edi, 1
0x180001616  jnz     short loc_18000164F
0x180001618  test    eax, eax
0x18000161a  jnz     short loc_18000164F
0x18000161c  mov     r8, rsi; lpvReserved
0x18000161f  xor     edx, edx; fdwReason
0x180001621  mov     rcx, r14; hinstDLL
0x180001624  call    DllMain
0x180001629  mov     r8, rsi
0x18000162c  xor     edx, edx
0x18000162e  mov     rcx, r14
0x180001631  call    dllmain_crt_dispatch
0x180001636  mov     rax, cs:_pRawDllMain
0x18000163d  test    rax, rax
0x180001640  jz      short loc_18000164F
0x180001642  mov     r8, rsi
0x180001645  xor     edx, edx
0x180001647  mov     rcx, r14
0x18000164a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000164f  test    edi, edi
0x180001651  jz      short loc_180001658
0x180001653  cmp     edi, 3
0x180001656  jnz     short loc_180001693
0x180001658  mov     r8, rsi
0x18000165b  mov     edx, edi
0x18000165d  mov     rcx, r14
0x180001660  call    dllmain_crt_dispatch
0x180001665  mov     ebx, eax
0x180001667  mov     [rsp+58h+var_28], eax
0x18000166b  test    eax, eax
0x18000166d  jz      short loc_180001693
0x18000166f  mov     rax, cs:_pRawDllMain
0x180001676  test    rax, rax
0x180001679  jnz     short loc_180001680
0x18000167b  lea     ebx, [rax+1]
0x18000167e  jmp     short loc_18000168F
0x180001680  mov     r8, rsi
0x180001683  mov     edx, edi
0x180001685  mov     rcx, r14
0x180001688  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000168d  mov     ebx, eax
0x18000168f  mov     [rsp+58h+var_28], ebx
0x180001693  jmp     short loc_18000169B
0x180001695  xor     ebx, ebx
0x180001697  mov     [rsp+58h+var_28], ebx
0x18000169b  mov     eax, ebx
0x18000169d  mov     rbx, [rsp+58h+arg_18]
0x1800016a2  add     rsp, 40h
0x1800016a6  pop     r14
0x1800016a8  pop     rdi
0x1800016a9  pop     rsi
0x1800016aa  retn
0x18002b08c  push    rbp
0x18002b08e  sub     rsp, 30h
0x18002b092  mov     rbp, rdx
0x18002b095  mov     rax, [rcx]
0x18002b098  mov     edx, [rax]
0x18002b09a  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x18002b09f  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x18002b0a3  lea     r9, dllmain_crt_dispatch; int
0x18002b0aa  mov     r8, [rbp+70h]; int
0x18002b0ae  mov     edx, [rbp+68h]; int
0x18002b0b1  mov     rcx, [rbp+60h]; int
0x18002b0b5  call    __scrt_dllmain_exception_filter
0x18002b0ba  nop
0x18002b0bb  add     rsp, 30h
0x18002b0bf  pop     rbp
0x18002b0c0  retn
```
