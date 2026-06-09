# dllmain_dispatch

- ea: `0x180001284`
- end: `0x1800013ab`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x1800013c0`

## callees

- `0x1800010a0`
- `0x180001284`
- `0x18000151c`
- `0x18000166c`
- `0x18001e010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_1800274D0 <= 0 )
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
0x180001284  mov     rax, rsp
0x180001287  mov     [rax+20h], rbx
0x18000128b  mov     [rax+18h], r8
0x18000128f  mov     [rax+10h], edx
0x180001292  mov     [rax+8], rcx
0x180001296  push    rsi
0x180001297  push    rdi
0x180001298  push    r14
0x18000129a  sub     rsp, 40h
0x18000129e  mov     rsi, r8
0x1800012a1  mov     edi, edx
0x1800012a3  mov     r14, rcx
0x1800012a6  test    edx, edx
0x1800012a8  jnz     short loc_1800012B9
0x1800012aa  cmp     cs:dword_1800274D0, edx
0x1800012b0  jg      short loc_1800012B9
0x1800012b2  xor     eax, eax
0x1800012b4  jmp     loc_18000139D
0x1800012b9  lea     eax, [rdx-1]
0x1800012bc  cmp     eax, 1
0x1800012bf  ja      short loc_180001300
0x1800012c1  mov     rax, cs:_pRawDllMain
0x1800012c8  test    rax, rax
0x1800012cb  jnz     short loc_1800012D2
0x1800012cd  lea     ebx, [rax+1]
0x1800012d0  jmp     short loc_1800012D9
0x1800012d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800012d7  mov     ebx, eax
0x1800012d9  mov     [rsp+58h+var_28], ebx
0x1800012dd  test    ebx, ebx
0x1800012df  jz      loc_180001393
0x1800012e5  mov     r8, rsi
0x1800012e8  mov     edx, edi
0x1800012ea  mov     rcx, r14
0x1800012ed  call    dllmain_crt_dispatch
0x1800012f2  mov     ebx, eax
0x1800012f4  mov     [rsp+58h+var_28], eax
0x1800012f8  test    eax, eax
0x1800012fa  jz      loc_180001393
0x180001300  mov     r8, rsi; lpvReserved
0x180001303  mov     edx, edi; fdwReason
0x180001305  mov     rcx, r14; hinstDLL
0x180001308  call    DllMain
0x18000130d  mov     ebx, eax
0x18000130f  mov     [rsp+58h+var_28], eax
0x180001313  cmp     edi, 1
0x180001316  jnz     short loc_18000134F
0x180001318  test    eax, eax
0x18000131a  jnz     short loc_18000134F
0x18000131c  mov     r8, rsi; lpvReserved
0x18000131f  xor     edx, edx; fdwReason
0x180001321  mov     rcx, r14; hinstDLL
0x180001324  call    DllMain
0x180001329  mov     r8, rsi
0x18000132c  xor     edx, edx
0x18000132e  mov     rcx, r14
0x180001331  call    dllmain_crt_dispatch
0x180001336  mov     rax, cs:_pRawDllMain
0x18000133d  test    rax, rax
0x180001340  jz      short loc_18000134F
0x180001342  mov     r8, rsi
0x180001345  xor     edx, edx
0x180001347  mov     rcx, r14
0x18000134a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000134f  test    edi, edi
0x180001351  jz      short loc_180001358
0x180001353  cmp     edi, 3
0x180001356  jnz     short loc_180001393
0x180001358  mov     r8, rsi
0x18000135b  mov     edx, edi
0x18000135d  mov     rcx, r14
0x180001360  call    dllmain_crt_dispatch
0x180001365  mov     ebx, eax
0x180001367  mov     [rsp+58h+var_28], eax
0x18000136b  test    eax, eax
0x18000136d  jz      short loc_180001393
0x18000136f  mov     rax, cs:_pRawDllMain
0x180001376  test    rax, rax
0x180001379  jnz     short loc_180001380
0x18000137b  lea     ebx, [rax+1]
0x18000137e  jmp     short loc_18000138F
0x180001380  mov     r8, rsi
0x180001383  mov     edx, edi
0x180001385  mov     rcx, r14
0x180001388  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000138d  mov     ebx, eax
0x18000138f  mov     [rsp+58h+var_28], ebx
0x180001393  jmp     short loc_18000139B
0x180001395  xor     ebx, ebx
0x180001397  mov     [rsp+58h+var_28], ebx
0x18000139b  mov     eax, ebx
0x18000139d  mov     rbx, [rsp+58h+arg_18]
0x1800013a2  add     rsp, 40h
0x1800013a6  pop     r14
0x1800013a8  pop     rdi
0x1800013a9  pop     rsi
0x1800013aa  retn
0x18001d45c  push    rbp
0x18001d45e  sub     rsp, 30h
0x18001d462  mov     rbp, rdx
0x18001d465  mov     rax, [rcx]
0x18001d468  mov     edx, [rax]
0x18001d46a  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x18001d46f  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x18001d473  lea     r9, dllmain_crt_dispatch; int
0x18001d47a  mov     r8, [rbp+70h]; int
0x18001d47e  mov     edx, [rbp+68h]; int
0x18001d481  mov     rcx, [rbp+60h]; int
0x18001d485  call    __scrt_dllmain_exception_filter
0x18001d48a  nop
0x18001d48b  add     rsp, 30h
0x18001d48f  pop     rbp
0x18001d490  retn
```
