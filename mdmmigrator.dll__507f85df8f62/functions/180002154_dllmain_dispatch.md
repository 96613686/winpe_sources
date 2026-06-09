# dllmain_dispatch

- ea: `0x180002154`
- end: `0x18000227b`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180002290`

## callees

- `0x180001f70`
- `0x180002154`
- `0x1800023dc`
- `0x180007378`
- `0x180020010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_18002B550 <= 0 )
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
0x180002154  mov     rax, rsp
0x180002157  mov     [rax+20h], rbx
0x18000215b  mov     [rax+18h], r8
0x18000215f  mov     [rax+10h], edx
0x180002162  mov     [rax+8], rcx
0x180002166  push    rsi
0x180002167  push    rdi
0x180002168  push    r14
0x18000216a  sub     rsp, 40h
0x18000216e  mov     rsi, r8
0x180002171  mov     edi, edx
0x180002173  mov     r14, rcx
0x180002176  test    edx, edx
0x180002178  jnz     short loc_180002189
0x18000217a  cmp     cs:dword_18002B550, edx
0x180002180  jg      short loc_180002189
0x180002182  xor     eax, eax
0x180002184  jmp     loc_18000226D
0x180002189  lea     eax, [rdx-1]
0x18000218c  cmp     eax, 1
0x18000218f  ja      short loc_1800021D0
0x180002191  mov     rax, cs:_pRawDllMain
0x180002198  test    rax, rax
0x18000219b  jnz     short loc_1800021A2
0x18000219d  lea     ebx, [rax+1]
0x1800021a0  jmp     short loc_1800021A9
0x1800021a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800021a7  mov     ebx, eax
0x1800021a9  mov     [rsp+58h+var_28], ebx
0x1800021ad  test    ebx, ebx
0x1800021af  jz      loc_180002263
0x1800021b5  mov     r8, rsi
0x1800021b8  mov     edx, edi
0x1800021ba  mov     rcx, r14
0x1800021bd  call    dllmain_crt_dispatch
0x1800021c2  mov     ebx, eax
0x1800021c4  mov     [rsp+58h+var_28], eax
0x1800021c8  test    eax, eax
0x1800021ca  jz      loc_180002263
0x1800021d0  mov     r8, rsi; lpvReserved
0x1800021d3  mov     edx, edi; fdwReason
0x1800021d5  mov     rcx, r14; hinstDLL
0x1800021d8  call    DllMain
0x1800021dd  mov     ebx, eax
0x1800021df  mov     [rsp+58h+var_28], eax
0x1800021e3  cmp     edi, 1
0x1800021e6  jnz     short loc_18000221F
0x1800021e8  test    eax, eax
0x1800021ea  jnz     short loc_18000221F
0x1800021ec  mov     r8, rsi; lpvReserved
0x1800021ef  xor     edx, edx; fdwReason
0x1800021f1  mov     rcx, r14; hinstDLL
0x1800021f4  call    DllMain
0x1800021f9  mov     r8, rsi
0x1800021fc  xor     edx, edx
0x1800021fe  mov     rcx, r14
0x180002201  call    dllmain_crt_dispatch
0x180002206  mov     rax, cs:_pRawDllMain
0x18000220d  test    rax, rax
0x180002210  jz      short loc_18000221F
0x180002212  mov     r8, rsi
0x180002215  xor     edx, edx
0x180002217  mov     rcx, r14
0x18000221a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000221f  test    edi, edi
0x180002221  jz      short loc_180002228
0x180002223  cmp     edi, 3
0x180002226  jnz     short loc_180002263
0x180002228  mov     r8, rsi
0x18000222b  mov     edx, edi
0x18000222d  mov     rcx, r14
0x180002230  call    dllmain_crt_dispatch
0x180002235  mov     ebx, eax
0x180002237  mov     [rsp+58h+var_28], eax
0x18000223b  test    eax, eax
0x18000223d  jz      short loc_180002263
0x18000223f  mov     rax, cs:_pRawDllMain
0x180002246  test    rax, rax
0x180002249  jnz     short loc_180002250
0x18000224b  lea     ebx, [rax+1]
0x18000224e  jmp     short loc_18000225F
0x180002250  mov     r8, rsi
0x180002253  mov     edx, edi
0x180002255  mov     rcx, r14
0x180002258  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000225d  mov     ebx, eax
0x18000225f  mov     [rsp+58h+var_28], ebx
0x180002263  jmp     short loc_18000226B
0x180002265  xor     ebx, ebx
0x180002267  mov     [rsp+58h+var_28], ebx
0x18000226b  mov     eax, ebx
0x18000226d  mov     rbx, [rsp+58h+arg_18]
0x180002272  add     rsp, 40h
0x180002276  pop     r14
0x180002278  pop     rdi
0x180002279  pop     rsi
0x18000227a  retn
0x18001eb1c  push    rbp
0x18001eb1e  sub     rsp, 30h
0x18001eb22  mov     rbp, rdx
0x18001eb25  mov     rax, [rcx]
0x18001eb28  mov     edx, [rax]
0x18001eb2a  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x18001eb2f  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x18001eb33  lea     r9, dllmain_crt_dispatch; int
0x18001eb3a  mov     r8, [rbp+70h]; int
0x18001eb3e  mov     edx, [rbp+68h]; int
0x18001eb41  mov     rcx, [rbp+60h]; int
0x18001eb45  call    __scrt_dllmain_exception_filter
0x18001eb4a  nop
0x18001eb4b  add     rsp, 30h
0x18001eb4f  pop     rbp
0x18001eb50  retn
```
