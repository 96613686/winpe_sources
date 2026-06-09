# dllmain_dispatch

- ea: `0x180002cc4`
- end: `0x180002deb`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180002e00`

## callees

- `0x180002ae0`
- `0x180002cc4`
- `0x180002fb4`
- `0x18001e080`
- `0x180023010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_18002F530 <= 0 )
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
0x180002cc4  mov     rax, rsp
0x180002cc7  mov     [rax+20h], rbx
0x180002ccb  mov     [rax+18h], r8
0x180002ccf  mov     [rax+10h], edx
0x180002cd2  mov     [rax+8], rcx
0x180002cd6  push    rsi
0x180002cd7  push    rdi
0x180002cd8  push    r14
0x180002cda  sub     rsp, 40h
0x180002cde  mov     rsi, r8
0x180002ce1  mov     edi, edx
0x180002ce3  mov     r14, rcx
0x180002ce6  test    edx, edx
0x180002ce8  jnz     short loc_180002CF9
0x180002cea  cmp     cs:dword_18002F530, edx
0x180002cf0  jg      short loc_180002CF9
0x180002cf2  xor     eax, eax
0x180002cf4  jmp     loc_180002DDD
0x180002cf9  lea     eax, [rdx-1]
0x180002cfc  cmp     eax, 1
0x180002cff  ja      short loc_180002D40
0x180002d01  mov     rax, cs:_pRawDllMain
0x180002d08  test    rax, rax
0x180002d0b  jnz     short loc_180002D12
0x180002d0d  lea     ebx, [rax+1]
0x180002d10  jmp     short loc_180002D19
0x180002d12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002d17  mov     ebx, eax
0x180002d19  mov     [rsp+58h+var_28], ebx
0x180002d1d  test    ebx, ebx
0x180002d1f  jz      loc_180002DD3
0x180002d25  mov     r8, rsi
0x180002d28  mov     edx, edi
0x180002d2a  mov     rcx, r14
0x180002d2d  call    dllmain_crt_dispatch
0x180002d32  mov     ebx, eax
0x180002d34  mov     [rsp+58h+var_28], eax
0x180002d38  test    eax, eax
0x180002d3a  jz      loc_180002DD3
0x180002d40  mov     r8, rsi; lpvReserved
0x180002d43  mov     edx, edi; fdwReason
0x180002d45  mov     rcx, r14; hinstDLL
0x180002d48  call    DllMain
0x180002d4d  mov     ebx, eax
0x180002d4f  mov     [rsp+58h+var_28], eax
0x180002d53  cmp     edi, 1
0x180002d56  jnz     short loc_180002D8F
0x180002d58  test    eax, eax
0x180002d5a  jnz     short loc_180002D8F
0x180002d5c  mov     r8, rsi; lpvReserved
0x180002d5f  xor     edx, edx; fdwReason
0x180002d61  mov     rcx, r14; hinstDLL
0x180002d64  call    DllMain
0x180002d69  mov     r8, rsi
0x180002d6c  xor     edx, edx
0x180002d6e  mov     rcx, r14
0x180002d71  call    dllmain_crt_dispatch
0x180002d76  mov     rax, cs:_pRawDllMain
0x180002d7d  test    rax, rax
0x180002d80  jz      short loc_180002D8F
0x180002d82  mov     r8, rsi
0x180002d85  xor     edx, edx
0x180002d87  mov     rcx, r14
0x180002d8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002d8f  test    edi, edi
0x180002d91  jz      short loc_180002D98
0x180002d93  cmp     edi, 3
0x180002d96  jnz     short loc_180002DD3
0x180002d98  mov     r8, rsi
0x180002d9b  mov     edx, edi
0x180002d9d  mov     rcx, r14
0x180002da0  call    dllmain_crt_dispatch
0x180002da5  mov     ebx, eax
0x180002da7  mov     [rsp+58h+var_28], eax
0x180002dab  test    eax, eax
0x180002dad  jz      short loc_180002DD3
0x180002daf  mov     rax, cs:_pRawDllMain
0x180002db6  test    rax, rax
0x180002db9  jnz     short loc_180002DC0
0x180002dbb  lea     ebx, [rax+1]
0x180002dbe  jmp     short loc_180002DCF
0x180002dc0  mov     r8, rsi
0x180002dc3  mov     edx, edi
0x180002dc5  mov     rcx, r14
0x180002dc8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002dcd  mov     ebx, eax
0x180002dcf  mov     [rsp+58h+var_28], ebx
0x180002dd3  jmp     short loc_180002DDB
0x180002dd5  xor     ebx, ebx
0x180002dd7  mov     [rsp+58h+var_28], ebx
0x180002ddb  mov     eax, ebx
0x180002ddd  mov     rbx, [rsp+58h+arg_18]
0x180002de2  add     rsp, 40h
0x180002de6  pop     r14
0x180002de8  pop     rdi
0x180002de9  pop     rsi
0x180002dea  retn
0x18002094c  push    rbp
0x18002094e  sub     rsp, 30h
0x180020952  mov     rbp, rdx
0x180020955  mov     rax, [rcx]
0x180020958  mov     edx, [rax]
0x18002095a  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x18002095f  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x180020963  lea     r9, dllmain_crt_dispatch; int
0x18002096a  mov     r8, [rbp+70h]; int
0x18002096e  mov     edx, [rbp+68h]; int
0x180020971  mov     rcx, [rbp+60h]; int
0x180020975  call    __scrt_dllmain_exception_filter
0x18002097a  nop
0x18002097b  add     rsp, 30h
0x18002097f  pop     rbp
0x180020980  retn
```
