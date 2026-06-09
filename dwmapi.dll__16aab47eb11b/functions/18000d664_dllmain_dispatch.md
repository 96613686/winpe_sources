# dllmain_dispatch

- ea: `0x18000d664`
- end: `0x18000d78b`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x18000d794`

## callees

- `0x1800075fc`
- `0x18000d19c`
- `0x18000d480`
- `0x18000d664`
- `0x180017010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_18001F594 <= 0 )
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
0x18000d664  mov     rax, rsp
0x18000d667  mov     [rax+20h], rbx
0x18000d66b  mov     [rax+18h], r8
0x18000d66f  mov     [rax+10h], edx
0x18000d672  mov     [rax+8], rcx
0x18000d676  push    rsi
0x18000d677  push    rdi
0x18000d678  push    r14
0x18000d67a  sub     rsp, 40h
0x18000d67e  mov     rsi, r8
0x18000d681  mov     edi, edx
0x18000d683  mov     r14, rcx
0x18000d686  test    edx, edx
0x18000d688  jnz     short loc_18000D699
0x18000d68a  cmp     cs:dword_18001F594, edx
0x18000d690  jg      short loc_18000D699
0x18000d692  xor     eax, eax
0x18000d694  jmp     loc_18000D77D
0x18000d699  lea     eax, [rdx-1]
0x18000d69c  cmp     eax, 1
0x18000d69f  ja      short loc_18000D6E0
0x18000d6a1  mov     rax, cs:_pRawDllMain
0x18000d6a8  test    rax, rax
0x18000d6ab  jnz     short loc_18000D6B2
0x18000d6ad  lea     ebx, [rax+1]
0x18000d6b0  jmp     short loc_18000D6B9
0x18000d6b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d6b7  mov     ebx, eax
0x18000d6b9  mov     [rsp+58h+var_28], ebx
0x18000d6bd  test    ebx, ebx
0x18000d6bf  jz      loc_18000D773
0x18000d6c5  mov     r8, rsi
0x18000d6c8  mov     edx, edi
0x18000d6ca  mov     rcx, r14
0x18000d6cd  call    dllmain_crt_dispatch
0x18000d6d2  mov     ebx, eax
0x18000d6d4  mov     [rsp+58h+var_28], eax
0x18000d6d8  test    eax, eax
0x18000d6da  jz      loc_18000D773
0x18000d6e0  mov     r8, rsi; lpvReserved
0x18000d6e3  mov     edx, edi; fdwReason
0x18000d6e5  mov     rcx, r14; hinstDLL
0x18000d6e8  call    DllMain
0x18000d6ed  mov     ebx, eax
0x18000d6ef  mov     [rsp+58h+var_28], eax
0x18000d6f3  cmp     edi, 1
0x18000d6f6  jnz     short loc_18000D72F
0x18000d6f8  test    eax, eax
0x18000d6fa  jnz     short loc_18000D72F
0x18000d6fc  mov     r8, rsi; lpvReserved
0x18000d6ff  xor     edx, edx; fdwReason
0x18000d701  mov     rcx, r14; hinstDLL
0x18000d704  call    DllMain
0x18000d709  mov     r8, rsi
0x18000d70c  xor     edx, edx
0x18000d70e  mov     rcx, r14
0x18000d711  call    dllmain_crt_dispatch
0x18000d716  mov     rax, cs:_pRawDllMain
0x18000d71d  test    rax, rax
0x18000d720  jz      short loc_18000D72F
0x18000d722  mov     r8, rsi
0x18000d725  xor     edx, edx
0x18000d727  mov     rcx, r14
0x18000d72a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d72f  test    edi, edi
0x18000d731  jz      short loc_18000D738
0x18000d733  cmp     edi, 3
0x18000d736  jnz     short loc_18000D773
0x18000d738  mov     r8, rsi
0x18000d73b  mov     edx, edi
0x18000d73d  mov     rcx, r14
0x18000d740  call    dllmain_crt_dispatch
0x18000d745  mov     ebx, eax
0x18000d747  mov     [rsp+58h+var_28], eax
0x18000d74b  test    eax, eax
0x18000d74d  jz      short loc_18000D773
0x18000d74f  mov     rax, cs:_pRawDllMain
0x18000d756  test    rax, rax
0x18000d759  jnz     short loc_18000D760
0x18000d75b  lea     ebx, [rax+1]
0x18000d75e  jmp     short loc_18000D76F
0x18000d760  mov     r8, rsi
0x18000d763  mov     edx, edi
0x18000d765  mov     rcx, r14
0x18000d768  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d76d  mov     ebx, eax
0x18000d76f  mov     [rsp+58h+var_28], ebx
0x18000d773  jmp     short loc_18000D77B
0x18000d775  xor     ebx, ebx
0x18000d777  mov     [rsp+58h+var_28], ebx
0x18000d77b  mov     eax, ebx
0x18000d77d  mov     rbx, [rsp+58h+arg_18]
0x18000d782  add     rsp, 40h
0x18000d786  pop     r14
0x18000d788  pop     rdi
0x18000d789  pop     rsi
0x18000d78a  retn
0x18001682a  push    rbp
0x18001682c  sub     rsp, 30h
0x180016830  mov     rbp, rdx
0x180016833  mov     rax, [rcx]
0x180016836  mov     edx, [rax]
0x180016838  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x18001683d  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x180016841  lea     r9, dllmain_crt_dispatch; int
0x180016848  mov     r8, [rbp+70h]; int
0x18001684c  mov     edx, [rbp+68h]; int
0x18001684f  mov     rcx, [rbp+60h]; int
0x180016853  call    __scrt_dllmain_exception_filter
0x180016858  nop
0x180016859  add     rsp, 30h
0x18001685d  pop     rbp
0x18001685e  retn
```
