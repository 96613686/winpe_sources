# dllmain_dispatch

- ea: `0x180003024`
- end: `0x18000314b`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180003160`

## callees

- `0x180002e40`
- `0x180003024`
- `0x1800033b4`
- `0x1800072f4`
- `0x180024010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_180032990 <= 0 )
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
0x180003024  mov     rax, rsp
0x180003027  mov     [rax+20h], rbx
0x18000302b  mov     [rax+18h], r8
0x18000302f  mov     [rax+10h], edx
0x180003032  mov     [rax+8], rcx
0x180003036  push    rsi
0x180003037  push    rdi
0x180003038  push    r14
0x18000303a  sub     rsp, 40h
0x18000303e  mov     rsi, r8
0x180003041  mov     edi, edx
0x180003043  mov     r14, rcx
0x180003046  test    edx, edx
0x180003048  jnz     short loc_180003059
0x18000304a  cmp     cs:dword_180032990, edx
0x180003050  jg      short loc_180003059
0x180003052  xor     eax, eax
0x180003054  jmp     loc_18000313D
0x180003059  lea     eax, [rdx-1]
0x18000305c  cmp     eax, 1
0x18000305f  ja      short loc_1800030A0
0x180003061  mov     rax, cs:_pRawDllMain
0x180003068  test    rax, rax
0x18000306b  jnz     short loc_180003072
0x18000306d  lea     ebx, [rax+1]
0x180003070  jmp     short loc_180003079
0x180003072  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003077  mov     ebx, eax
0x180003079  mov     [rsp+58h+var_28], ebx
0x18000307d  test    ebx, ebx
0x18000307f  jz      loc_180003133
0x180003085  mov     r8, rsi
0x180003088  mov     edx, edi
0x18000308a  mov     rcx, r14
0x18000308d  call    dllmain_crt_dispatch
0x180003092  mov     ebx, eax
0x180003094  mov     [rsp+58h+var_28], eax
0x180003098  test    eax, eax
0x18000309a  jz      loc_180003133
0x1800030a0  mov     r8, rsi; lpvReserved
0x1800030a3  mov     edx, edi; fdwReason
0x1800030a5  mov     rcx, r14; hinstDLL
0x1800030a8  call    DllMain
0x1800030ad  mov     ebx, eax
0x1800030af  mov     [rsp+58h+var_28], eax
0x1800030b3  cmp     edi, 1
0x1800030b6  jnz     short loc_1800030EF
0x1800030b8  test    eax, eax
0x1800030ba  jnz     short loc_1800030EF
0x1800030bc  mov     r8, rsi; lpvReserved
0x1800030bf  xor     edx, edx; fdwReason
0x1800030c1  mov     rcx, r14; hinstDLL
0x1800030c4  call    DllMain
0x1800030c9  mov     r8, rsi
0x1800030cc  xor     edx, edx
0x1800030ce  mov     rcx, r14
0x1800030d1  call    dllmain_crt_dispatch
0x1800030d6  mov     rax, cs:_pRawDllMain
0x1800030dd  test    rax, rax
0x1800030e0  jz      short loc_1800030EF
0x1800030e2  mov     r8, rsi
0x1800030e5  xor     edx, edx
0x1800030e7  mov     rcx, r14
0x1800030ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800030ef  test    edi, edi
0x1800030f1  jz      short loc_1800030F8
0x1800030f3  cmp     edi, 3
0x1800030f6  jnz     short loc_180003133
0x1800030f8  mov     r8, rsi
0x1800030fb  mov     edx, edi
0x1800030fd  mov     rcx, r14
0x180003100  call    dllmain_crt_dispatch
0x180003105  mov     ebx, eax
0x180003107  mov     [rsp+58h+var_28], eax
0x18000310b  test    eax, eax
0x18000310d  jz      short loc_180003133
0x18000310f  mov     rax, cs:_pRawDllMain
0x180003116  test    rax, rax
0x180003119  jnz     short loc_180003120
0x18000311b  lea     ebx, [rax+1]
0x18000311e  jmp     short loc_18000312F
0x180003120  mov     r8, rsi
0x180003123  mov     edx, edi
0x180003125  mov     rcx, r14
0x180003128  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000312d  mov     ebx, eax
0x18000312f  mov     [rsp+58h+var_28], ebx
0x180003133  jmp     short loc_18000313B
0x180003135  xor     ebx, ebx
0x180003137  mov     [rsp+58h+var_28], ebx
0x18000313b  mov     eax, ebx
0x18000313d  mov     rbx, [rsp+58h+arg_18]
0x180003142  add     rsp, 40h
0x180003146  pop     r14
0x180003148  pop     rdi
0x180003149  pop     rsi
0x18000314a  retn
0x180022aac  push    rbp
0x180022aae  sub     rsp, 30h
0x180022ab2  mov     rbp, rdx
0x180022ab5  mov     rax, [rcx]
0x180022ab8  mov     edx, [rax]
0x180022aba  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x180022abf  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x180022ac3  lea     r9, dllmain_crt_dispatch; int
0x180022aca  mov     r8, [rbp+70h]; int
0x180022ace  mov     edx, [rbp+68h]; int
0x180022ad1  mov     rcx, [rbp+60h]; int
0x180022ad5  call    __scrt_dllmain_exception_filter
0x180022ada  nop
0x180022adb  add     rsp, 30h
0x180022adf  pop     rbp
0x180022ae0  retn
```
