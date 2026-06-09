# dllmain_dispatch

- ea: `0x180004ab4`
- end: `0x180004bdb`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180004bf0`

## callees

- `0x1800048d0`
- `0x180004ab4`
- `0x180004e44`
- `0x180005658`
- `0x180009010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_18000E510 <= 0 )
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
0x180004ab4  mov     rax, rsp
0x180004ab7  mov     [rax+20h], rbx
0x180004abb  mov     [rax+18h], r8
0x180004abf  mov     [rax+10h], edx
0x180004ac2  mov     [rax+8], rcx
0x180004ac6  push    rsi
0x180004ac7  push    rdi
0x180004ac8  push    r14
0x180004aca  sub     rsp, 40h
0x180004ace  mov     rsi, r8
0x180004ad1  mov     edi, edx
0x180004ad3  mov     r14, rcx
0x180004ad6  test    edx, edx
0x180004ad8  jnz     short loc_180004AE9
0x180004ada  cmp     cs:dword_18000E510, edx
0x180004ae0  jg      short loc_180004AE9
0x180004ae2  xor     eax, eax
0x180004ae4  jmp     loc_180004BCD
0x180004ae9  lea     eax, [rdx-1]
0x180004aec  cmp     eax, 1
0x180004aef  ja      short loc_180004B30
0x180004af1  mov     rax, cs:_pRawDllMain
0x180004af8  test    rax, rax
0x180004afb  jnz     short loc_180004B02
0x180004afd  lea     ebx, [rax+1]
0x180004b00  jmp     short loc_180004B09
0x180004b02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004b07  mov     ebx, eax
0x180004b09  mov     [rsp+58h+var_28], ebx
0x180004b0d  test    ebx, ebx
0x180004b0f  jz      loc_180004BC3
0x180004b15  mov     r8, rsi
0x180004b18  mov     edx, edi
0x180004b1a  mov     rcx, r14
0x180004b1d  call    dllmain_crt_dispatch
0x180004b22  mov     ebx, eax
0x180004b24  mov     [rsp+58h+var_28], eax
0x180004b28  test    eax, eax
0x180004b2a  jz      loc_180004BC3
0x180004b30  mov     r8, rsi; lpvReserved
0x180004b33  mov     edx, edi; fdwReason
0x180004b35  mov     rcx, r14; hinstDLL
0x180004b38  call    DllMain
0x180004b3d  mov     ebx, eax
0x180004b3f  mov     [rsp+58h+var_28], eax
0x180004b43  cmp     edi, 1
0x180004b46  jnz     short loc_180004B7F
0x180004b48  test    eax, eax
0x180004b4a  jnz     short loc_180004B7F
0x180004b4c  mov     r8, rsi; lpvReserved
0x180004b4f  xor     edx, edx; fdwReason
0x180004b51  mov     rcx, r14; hinstDLL
0x180004b54  call    DllMain
0x180004b59  mov     r8, rsi
0x180004b5c  xor     edx, edx
0x180004b5e  mov     rcx, r14
0x180004b61  call    dllmain_crt_dispatch
0x180004b66  mov     rax, cs:_pRawDllMain
0x180004b6d  test    rax, rax
0x180004b70  jz      short loc_180004B7F
0x180004b72  mov     r8, rsi
0x180004b75  xor     edx, edx
0x180004b77  mov     rcx, r14
0x180004b7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004b7f  test    edi, edi
0x180004b81  jz      short loc_180004B88
0x180004b83  cmp     edi, 3
0x180004b86  jnz     short loc_180004BC3
0x180004b88  mov     r8, rsi
0x180004b8b  mov     edx, edi
0x180004b8d  mov     rcx, r14
0x180004b90  call    dllmain_crt_dispatch
0x180004b95  mov     ebx, eax
0x180004b97  mov     [rsp+58h+var_28], eax
0x180004b9b  test    eax, eax
0x180004b9d  jz      short loc_180004BC3
0x180004b9f  mov     rax, cs:_pRawDllMain
0x180004ba6  test    rax, rax
0x180004ba9  jnz     short loc_180004BB0
0x180004bab  lea     ebx, [rax+1]
0x180004bae  jmp     short loc_180004BBF
0x180004bb0  mov     r8, rsi
0x180004bb3  mov     edx, edi
0x180004bb5  mov     rcx, r14
0x180004bb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004bbd  mov     ebx, eax
0x180004bbf  mov     [rsp+58h+var_28], ebx
0x180004bc3  jmp     short loc_180004BCB
0x180004bc5  xor     ebx, ebx
0x180004bc7  mov     [rsp+58h+var_28], ebx
0x180004bcb  mov     eax, ebx
0x180004bcd  mov     rbx, [rsp+58h+arg_18]
0x180004bd2  add     rsp, 40h
0x180004bd6  pop     r14
0x180004bd8  pop     rdi
0x180004bd9  pop     rsi
0x180004bda  retn
0x1800084ec  push    rbp
0x1800084ee  sub     rsp, 30h
0x1800084f2  mov     rbp, rdx
0x1800084f5  mov     rax, [rcx]
0x1800084f8  mov     edx, [rax]
0x1800084fa  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x1800084ff  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x180008503  lea     r9, dllmain_crt_dispatch; int
0x18000850a  mov     r8, [rbp+70h]; int
0x18000850e  mov     edx, [rbp+68h]; int
0x180008511  mov     rcx, [rbp+60h]; int
0x180008515  call    __scrt_dllmain_exception_filter
0x18000851a  nop
0x18000851b  add     rsp, 30h
0x18000851f  pop     rbp
0x180008520  retn
```
