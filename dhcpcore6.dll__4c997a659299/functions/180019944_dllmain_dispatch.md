# dllmain_dispatch

- ea: `0x180019944`
- end: `0x180019a6b`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180019a80`

## callees

- `0x180019760`
- `0x180019944`
- `0x180019d00`
- `0x18001c260`
- `0x180035010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_1800422A0 <= 0 )
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
0x180019944  mov     rax, rsp
0x180019947  mov     [rax+20h], rbx
0x18001994b  mov     [rax+18h], r8
0x18001994f  mov     [rax+10h], edx
0x180019952  mov     [rax+8], rcx
0x180019956  push    rsi
0x180019957  push    rdi
0x180019958  push    r14
0x18001995a  sub     rsp, 40h
0x18001995e  mov     rsi, r8
0x180019961  mov     edi, edx
0x180019963  mov     r14, rcx
0x180019966  test    edx, edx
0x180019968  jnz     short loc_180019979
0x18001996a  cmp     cs:dword_1800422A0, edx
0x180019970  jg      short loc_180019979
0x180019972  xor     eax, eax
0x180019974  jmp     loc_180019A5D
0x180019979  lea     eax, [rdx-1]
0x18001997c  cmp     eax, 1
0x18001997f  ja      short loc_1800199C0
0x180019981  mov     rax, cs:_pRawDllMain
0x180019988  test    rax, rax
0x18001998b  jnz     short loc_180019992
0x18001998d  lea     ebx, [rax+1]
0x180019990  jmp     short loc_180019999
0x180019992  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019997  mov     ebx, eax
0x180019999  mov     [rsp+58h+var_28], ebx
0x18001999d  test    ebx, ebx
0x18001999f  jz      loc_180019A53
0x1800199a5  mov     r8, rsi
0x1800199a8  mov     edx, edi
0x1800199aa  mov     rcx, r14
0x1800199ad  call    dllmain_crt_dispatch
0x1800199b2  mov     ebx, eax
0x1800199b4  mov     [rsp+58h+var_28], eax
0x1800199b8  test    eax, eax
0x1800199ba  jz      loc_180019A53
0x1800199c0  mov     r8, rsi; lpvReserved
0x1800199c3  mov     edx, edi; fdwReason
0x1800199c5  mov     rcx, r14; hinstDLL
0x1800199c8  call    DllMain
0x1800199cd  mov     ebx, eax
0x1800199cf  mov     [rsp+58h+var_28], eax
0x1800199d3  cmp     edi, 1
0x1800199d6  jnz     short loc_180019A0F
0x1800199d8  test    eax, eax
0x1800199da  jnz     short loc_180019A0F
0x1800199dc  mov     r8, rsi; lpvReserved
0x1800199df  xor     edx, edx; fdwReason
0x1800199e1  mov     rcx, r14; hinstDLL
0x1800199e4  call    DllMain
0x1800199e9  mov     r8, rsi
0x1800199ec  xor     edx, edx
0x1800199ee  mov     rcx, r14
0x1800199f1  call    dllmain_crt_dispatch
0x1800199f6  mov     rax, cs:_pRawDllMain
0x1800199fd  test    rax, rax
0x180019a00  jz      short loc_180019A0F
0x180019a02  mov     r8, rsi
0x180019a05  xor     edx, edx
0x180019a07  mov     rcx, r14
0x180019a0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019a0f  test    edi, edi
0x180019a11  jz      short loc_180019A18
0x180019a13  cmp     edi, 3
0x180019a16  jnz     short loc_180019A53
0x180019a18  mov     r8, rsi
0x180019a1b  mov     edx, edi
0x180019a1d  mov     rcx, r14
0x180019a20  call    dllmain_crt_dispatch
0x180019a25  mov     ebx, eax
0x180019a27  mov     [rsp+58h+var_28], eax
0x180019a2b  test    eax, eax
0x180019a2d  jz      short loc_180019A53
0x180019a2f  mov     rax, cs:_pRawDllMain
0x180019a36  test    rax, rax
0x180019a39  jnz     short loc_180019A40
0x180019a3b  lea     ebx, [rax+1]
0x180019a3e  jmp     short loc_180019A4F
0x180019a40  mov     r8, rsi
0x180019a43  mov     edx, edi
0x180019a45  mov     rcx, r14
0x180019a48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019a4d  mov     ebx, eax
0x180019a4f  mov     [rsp+58h+var_28], ebx
0x180019a53  jmp     short loc_180019A5B
0x180019a55  xor     ebx, ebx
0x180019a57  mov     [rsp+58h+var_28], ebx
0x180019a5b  mov     eax, ebx
0x180019a5d  mov     rbx, [rsp+58h+arg_18]
0x180019a62  add     rsp, 40h
0x180019a66  pop     r14
0x180019a68  pop     rdi
0x180019a69  pop     rsi
0x180019a6a  retn
0x180030aac  push    rbp
0x180030aae  sub     rsp, 30h
0x180030ab2  mov     rbp, rdx
0x180030ab5  mov     rax, [rcx]
0x180030ab8  mov     edx, [rax]
0x180030aba  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x180030abf  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x180030ac3  lea     r9, dllmain_crt_dispatch; int
0x180030aca  mov     r8, [rbp+70h]; int
0x180030ace  mov     edx, [rbp+68h]; int
0x180030ad1  mov     rcx, [rbp+60h]; int
0x180030ad5  call    __scrt_dllmain_exception_filter
0x180030ada  nop
0x180030adb  add     rsp, 30h
0x180030adf  pop     rbp
0x180030ae0  retn
```
