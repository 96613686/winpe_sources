# dllmain_dispatch

- ea: `0x1800020e4`
- end: `0x18000220b`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180002220`

## callees

- `0x180001f00`
- `0x1800020e4`
- `0x18000236c`
- `0x180002ed0`
- `0x180015010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_18001E750 <= 0 )
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
0x1800020e4  mov     rax, rsp
0x1800020e7  mov     [rax+20h], rbx
0x1800020eb  mov     [rax+18h], r8
0x1800020ef  mov     [rax+10h], edx
0x1800020f2  mov     [rax+8], rcx
0x1800020f6  push    rsi
0x1800020f7  push    rdi
0x1800020f8  push    r14
0x1800020fa  sub     rsp, 40h
0x1800020fe  mov     rsi, r8
0x180002101  mov     edi, edx
0x180002103  mov     r14, rcx
0x180002106  test    edx, edx
0x180002108  jnz     short loc_180002119
0x18000210a  cmp     cs:dword_18001E750, edx
0x180002110  jg      short loc_180002119
0x180002112  xor     eax, eax
0x180002114  jmp     loc_1800021FD
0x180002119  lea     eax, [rdx-1]
0x18000211c  cmp     eax, 1
0x18000211f  ja      short loc_180002160
0x180002121  mov     rax, cs:_pRawDllMain
0x180002128  test    rax, rax
0x18000212b  jnz     short loc_180002132
0x18000212d  lea     ebx, [rax+1]
0x180002130  jmp     short loc_180002139
0x180002132  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002137  mov     ebx, eax
0x180002139  mov     [rsp+58h+var_28], ebx
0x18000213d  test    ebx, ebx
0x18000213f  jz      loc_1800021F3
0x180002145  mov     r8, rsi
0x180002148  mov     edx, edi
0x18000214a  mov     rcx, r14
0x18000214d  call    dllmain_crt_dispatch
0x180002152  mov     ebx, eax
0x180002154  mov     [rsp+58h+var_28], eax
0x180002158  test    eax, eax
0x18000215a  jz      loc_1800021F3
0x180002160  mov     r8, rsi; lpvReserved
0x180002163  mov     edx, edi; fdwReason
0x180002165  mov     rcx, r14; hinstDLL
0x180002168  call    DllMain
0x18000216d  mov     ebx, eax
0x18000216f  mov     [rsp+58h+var_28], eax
0x180002173  cmp     edi, 1
0x180002176  jnz     short loc_1800021AF
0x180002178  test    eax, eax
0x18000217a  jnz     short loc_1800021AF
0x18000217c  mov     r8, rsi; lpvReserved
0x18000217f  xor     edx, edx; fdwReason
0x180002181  mov     rcx, r14; hinstDLL
0x180002184  call    DllMain
0x180002189  mov     r8, rsi
0x18000218c  xor     edx, edx
0x18000218e  mov     rcx, r14
0x180002191  call    dllmain_crt_dispatch
0x180002196  mov     rax, cs:_pRawDllMain
0x18000219d  test    rax, rax
0x1800021a0  jz      short loc_1800021AF
0x1800021a2  mov     r8, rsi
0x1800021a5  xor     edx, edx
0x1800021a7  mov     rcx, r14
0x1800021aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800021af  test    edi, edi
0x1800021b1  jz      short loc_1800021B8
0x1800021b3  cmp     edi, 3
0x1800021b6  jnz     short loc_1800021F3
0x1800021b8  mov     r8, rsi
0x1800021bb  mov     edx, edi
0x1800021bd  mov     rcx, r14
0x1800021c0  call    dllmain_crt_dispatch
0x1800021c5  mov     ebx, eax
0x1800021c7  mov     [rsp+58h+var_28], eax
0x1800021cb  test    eax, eax
0x1800021cd  jz      short loc_1800021F3
0x1800021cf  mov     rax, cs:_pRawDllMain
0x1800021d6  test    rax, rax
0x1800021d9  jnz     short loc_1800021E0
0x1800021db  lea     ebx, [rax+1]
0x1800021de  jmp     short loc_1800021EF
0x1800021e0  mov     r8, rsi
0x1800021e3  mov     edx, edi
0x1800021e5  mov     rcx, r14
0x1800021e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800021ed  mov     ebx, eax
0x1800021ef  mov     [rsp+58h+var_28], ebx
0x1800021f3  jmp     short loc_1800021FB
0x1800021f5  xor     ebx, ebx
0x1800021f7  mov     [rsp+58h+var_28], ebx
0x1800021fb  mov     eax, ebx
0x1800021fd  mov     rbx, [rsp+58h+arg_18]
0x180002202  add     rsp, 40h
0x180002206  pop     r14
0x180002208  pop     rdi
0x180002209  pop     rsi
0x18000220a  retn
0x18001412c  push    rbp
0x18001412e  sub     rsp, 30h
0x180014132  mov     rbp, rdx
0x180014135  mov     rax, [rcx]
0x180014138  mov     edx, [rax]
0x18001413a  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x18001413f  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x180014143  lea     r9, dllmain_crt_dispatch; int
0x18001414a  mov     r8, [rbp+70h]; int
0x18001414e  mov     edx, [rbp+68h]; int
0x180014151  mov     rcx, [rbp+60h]; int
0x180014155  call    __scrt_dllmain_exception_filter
0x18001415a  nop
0x18001415b  add     rsp, 30h
0x18001415f  pop     rbp
0x180014160  retn
```
