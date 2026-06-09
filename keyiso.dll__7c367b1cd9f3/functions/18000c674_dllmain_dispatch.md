# dllmain_dispatch

- ea: `0x18000c674`
- end: `0x18000c79b`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x18000c7b0`

## callees

- `0x180009aa4`
- `0x18000c490`
- `0x18000c674`
- `0x18000c8cc`
- `0x180019010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_180025920 <= 0 )
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
0x18000c674  mov     rax, rsp
0x18000c677  mov     [rax+20h], rbx
0x18000c67b  mov     [rax+18h], r8
0x18000c67f  mov     [rax+10h], edx
0x18000c682  mov     [rax+8], rcx
0x18000c686  push    rsi
0x18000c687  push    rdi
0x18000c688  push    r14
0x18000c68a  sub     rsp, 40h
0x18000c68e  mov     rsi, r8
0x18000c691  mov     edi, edx
0x18000c693  mov     r14, rcx
0x18000c696  test    edx, edx
0x18000c698  jnz     short loc_18000C6A9
0x18000c69a  cmp     cs:dword_180025920, edx
0x18000c6a0  jg      short loc_18000C6A9
0x18000c6a2  xor     eax, eax
0x18000c6a4  jmp     loc_18000C78D
0x18000c6a9  lea     eax, [rdx-1]
0x18000c6ac  cmp     eax, 1
0x18000c6af  ja      short loc_18000C6F0
0x18000c6b1  mov     rax, cs:_pRawDllMain
0x18000c6b8  test    rax, rax
0x18000c6bb  jnz     short loc_18000C6C2
0x18000c6bd  lea     ebx, [rax+1]
0x18000c6c0  jmp     short loc_18000C6C9
0x18000c6c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c6c7  mov     ebx, eax
0x18000c6c9  mov     [rsp+58h+var_28], ebx
0x18000c6cd  test    ebx, ebx
0x18000c6cf  jz      loc_18000C783
0x18000c6d5  mov     r8, rsi
0x18000c6d8  mov     edx, edi
0x18000c6da  mov     rcx, r14
0x18000c6dd  call    dllmain_crt_dispatch
0x18000c6e2  mov     ebx, eax
0x18000c6e4  mov     [rsp+58h+var_28], eax
0x18000c6e8  test    eax, eax
0x18000c6ea  jz      loc_18000C783
0x18000c6f0  mov     r8, rsi; lpvReserved
0x18000c6f3  mov     edx, edi; fdwReason
0x18000c6f5  mov     rcx, r14; hinstDLL
0x18000c6f8  call    DllMain
0x18000c6fd  mov     ebx, eax
0x18000c6ff  mov     [rsp+58h+var_28], eax
0x18000c703  cmp     edi, 1
0x18000c706  jnz     short loc_18000C73F
0x18000c708  test    eax, eax
0x18000c70a  jnz     short loc_18000C73F
0x18000c70c  mov     r8, rsi; lpvReserved
0x18000c70f  xor     edx, edx; fdwReason
0x18000c711  mov     rcx, r14; hinstDLL
0x18000c714  call    DllMain
0x18000c719  mov     r8, rsi
0x18000c71c  xor     edx, edx
0x18000c71e  mov     rcx, r14
0x18000c721  call    dllmain_crt_dispatch
0x18000c726  mov     rax, cs:_pRawDllMain
0x18000c72d  test    rax, rax
0x18000c730  jz      short loc_18000C73F
0x18000c732  mov     r8, rsi
0x18000c735  xor     edx, edx
0x18000c737  mov     rcx, r14
0x18000c73a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c73f  test    edi, edi
0x18000c741  jz      short loc_18000C748
0x18000c743  cmp     edi, 3
0x18000c746  jnz     short loc_18000C783
0x18000c748  mov     r8, rsi
0x18000c74b  mov     edx, edi
0x18000c74d  mov     rcx, r14
0x18000c750  call    dllmain_crt_dispatch
0x18000c755  mov     ebx, eax
0x18000c757  mov     [rsp+58h+var_28], eax
0x18000c75b  test    eax, eax
0x18000c75d  jz      short loc_18000C783
0x18000c75f  mov     rax, cs:_pRawDllMain
0x18000c766  test    rax, rax
0x18000c769  jnz     short loc_18000C770
0x18000c76b  lea     ebx, [rax+1]
0x18000c76e  jmp     short loc_18000C77F
0x18000c770  mov     r8, rsi
0x18000c773  mov     edx, edi
0x18000c775  mov     rcx, r14
0x18000c778  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c77d  mov     ebx, eax
0x18000c77f  mov     [rsp+58h+var_28], ebx
0x18000c783  jmp     short loc_18000C78B
0x18000c785  xor     ebx, ebx
0x18000c787  mov     [rsp+58h+var_28], ebx
0x18000c78b  mov     eax, ebx
0x18000c78d  mov     rbx, [rsp+58h+arg_18]
0x18000c792  add     rsp, 40h
0x18000c796  pop     r14
0x18000c798  pop     rdi
0x18000c799  pop     rsi
0x18000c79a  retn
0x180018a69  push    rbp
0x180018a6b  sub     rsp, 30h
0x180018a6f  mov     rbp, rdx
0x180018a72  mov     rax, [rcx]
0x180018a75  mov     edx, [rax]
0x180018a77  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x180018a7c  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x180018a80  lea     r9, dllmain_crt_dispatch; int
0x180018a87  mov     r8, [rbp+70h]; int
0x180018a8b  mov     edx, [rbp+68h]; int
0x180018a8e  mov     rcx, [rbp+60h]; int
0x180018a92  call    __scrt_dllmain_exception_filter
0x180018a97  nop
0x180018a98  add     rsp, 30h
0x180018a9c  pop     rbp
0x180018a9d  retn
```
