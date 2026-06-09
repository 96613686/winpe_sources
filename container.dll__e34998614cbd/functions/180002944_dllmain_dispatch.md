# dllmain_dispatch

- ea: `0x180002944`
- end: `0x180002a6b`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180002a80`

## callees

- `0x180002760`
- `0x180002944`
- `0x180002c10`
- `0x18002c5e8`
- `0x180034010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_1800449B0 <= 0 )
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
0x180002944  mov     rax, rsp
0x180002947  mov     [rax+20h], rbx
0x18000294b  mov     [rax+18h], r8
0x18000294f  mov     [rax+10h], edx
0x180002952  mov     [rax+8], rcx
0x180002956  push    rsi
0x180002957  push    rdi
0x180002958  push    r14
0x18000295a  sub     rsp, 40h
0x18000295e  mov     rsi, r8
0x180002961  mov     edi, edx
0x180002963  mov     r14, rcx
0x180002966  test    edx, edx
0x180002968  jnz     short loc_180002979
0x18000296a  cmp     cs:dword_1800449B0, edx
0x180002970  jg      short loc_180002979
0x180002972  xor     eax, eax
0x180002974  jmp     loc_180002A5D
0x180002979  lea     eax, [rdx-1]
0x18000297c  cmp     eax, 1
0x18000297f  ja      short loc_1800029C0
0x180002981  mov     rax, cs:_pRawDllMain
0x180002988  test    rax, rax
0x18000298b  jnz     short loc_180002992
0x18000298d  lea     ebx, [rax+1]
0x180002990  jmp     short loc_180002999
0x180002992  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002997  mov     ebx, eax
0x180002999  mov     [rsp+58h+var_28], ebx
0x18000299d  test    ebx, ebx
0x18000299f  jz      loc_180002A53
0x1800029a5  mov     r8, rsi
0x1800029a8  mov     edx, edi
0x1800029aa  mov     rcx, r14
0x1800029ad  call    dllmain_crt_dispatch
0x1800029b2  mov     ebx, eax
0x1800029b4  mov     [rsp+58h+var_28], eax
0x1800029b8  test    eax, eax
0x1800029ba  jz      loc_180002A53
0x1800029c0  mov     r8, rsi; lpvReserved
0x1800029c3  mov     edx, edi; fdwReason
0x1800029c5  mov     rcx, r14; hinstDLL
0x1800029c8  call    DllMain
0x1800029cd  mov     ebx, eax
0x1800029cf  mov     [rsp+58h+var_28], eax
0x1800029d3  cmp     edi, 1
0x1800029d6  jnz     short loc_180002A0F
0x1800029d8  test    eax, eax
0x1800029da  jnz     short loc_180002A0F
0x1800029dc  mov     r8, rsi; lpvReserved
0x1800029df  xor     edx, edx; fdwReason
0x1800029e1  mov     rcx, r14; hinstDLL
0x1800029e4  call    DllMain
0x1800029e9  mov     r8, rsi
0x1800029ec  xor     edx, edx
0x1800029ee  mov     rcx, r14
0x1800029f1  call    dllmain_crt_dispatch
0x1800029f6  mov     rax, cs:_pRawDllMain
0x1800029fd  test    rax, rax
0x180002a00  jz      short loc_180002A0F
0x180002a02  mov     r8, rsi
0x180002a05  xor     edx, edx
0x180002a07  mov     rcx, r14
0x180002a0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002a0f  test    edi, edi
0x180002a11  jz      short loc_180002A18
0x180002a13  cmp     edi, 3
0x180002a16  jnz     short loc_180002A53
0x180002a18  mov     r8, rsi
0x180002a1b  mov     edx, edi
0x180002a1d  mov     rcx, r14
0x180002a20  call    dllmain_crt_dispatch
0x180002a25  mov     ebx, eax
0x180002a27  mov     [rsp+58h+var_28], eax
0x180002a2b  test    eax, eax
0x180002a2d  jz      short loc_180002A53
0x180002a2f  mov     rax, cs:_pRawDllMain
0x180002a36  test    rax, rax
0x180002a39  jnz     short loc_180002A40
0x180002a3b  lea     ebx, [rax+1]
0x180002a3e  jmp     short loc_180002A4F
0x180002a40  mov     r8, rsi
0x180002a43  mov     edx, edi
0x180002a45  mov     rcx, r14
0x180002a48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002a4d  mov     ebx, eax
0x180002a4f  mov     [rsp+58h+var_28], ebx
0x180002a53  jmp     short loc_180002A5B
0x180002a55  xor     ebx, ebx
0x180002a57  mov     [rsp+58h+var_28], ebx
0x180002a5b  mov     eax, ebx
0x180002a5d  mov     rbx, [rsp+58h+arg_18]
0x180002a62  add     rsp, 40h
0x180002a66  pop     r14
0x180002a68  pop     rdi
0x180002a69  pop     rsi
0x180002a6a  retn
0x180031f0c  push    rbp
0x180031f0e  sub     rsp, 30h
0x180031f12  mov     rbp, rdx
0x180031f15  mov     rax, [rcx]
0x180031f18  mov     edx, [rax]
0x180031f1a  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x180031f1f  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x180031f23  lea     r9, dllmain_crt_dispatch; int
0x180031f2a  mov     r8, [rbp+70h]; int
0x180031f2e  mov     edx, [rbp+68h]; int
0x180031f31  mov     rcx, [rbp+60h]; int
0x180031f35  call    __scrt_dllmain_exception_filter
0x180031f3a  nop
0x180031f3b  add     rsp, 30h
0x180031f3f  pop     rbp
0x180031f40  retn
```
