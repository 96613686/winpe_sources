# dllmain_dispatch

- ea: `0x180001b64`
- end: `0x180001c8b`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180001ca0`

## callees

- `0x180001980`
- `0x180001b64`
- `0x180001e08`
- `0x180006c24`
- `0x18000d010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_180018350 <= 0 )
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
0x180001b64  mov     rax, rsp
0x180001b67  mov     [rax+20h], rbx
0x180001b6b  mov     [rax+18h], r8
0x180001b6f  mov     [rax+10h], edx
0x180001b72  mov     [rax+8], rcx
0x180001b76  push    rsi
0x180001b77  push    rdi
0x180001b78  push    r14
0x180001b7a  sub     rsp, 40h
0x180001b7e  mov     rsi, r8
0x180001b81  mov     edi, edx
0x180001b83  mov     r14, rcx
0x180001b86  test    edx, edx
0x180001b88  jnz     short loc_180001B99
0x180001b8a  cmp     cs:dword_180018350, edx
0x180001b90  jg      short loc_180001B99
0x180001b92  xor     eax, eax
0x180001b94  jmp     loc_180001C7D
0x180001b99  lea     eax, [rdx-1]
0x180001b9c  cmp     eax, 1
0x180001b9f  ja      short loc_180001BE0
0x180001ba1  mov     rax, cs:_pRawDllMain
0x180001ba8  test    rax, rax
0x180001bab  jnz     short loc_180001BB2
0x180001bad  lea     ebx, [rax+1]
0x180001bb0  jmp     short loc_180001BB9
0x180001bb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001bb7  mov     ebx, eax
0x180001bb9  mov     [rsp+58h+var_28], ebx
0x180001bbd  test    ebx, ebx
0x180001bbf  jz      loc_180001C73
0x180001bc5  mov     r8, rsi
0x180001bc8  mov     edx, edi
0x180001bca  mov     rcx, r14
0x180001bcd  call    dllmain_crt_dispatch
0x180001bd2  mov     ebx, eax
0x180001bd4  mov     [rsp+58h+var_28], eax
0x180001bd8  test    eax, eax
0x180001bda  jz      loc_180001C73
0x180001be0  mov     r8, rsi; lpvReserved
0x180001be3  mov     edx, edi; fdwReason
0x180001be5  mov     rcx, r14; hinstDLL
0x180001be8  call    DllMain
0x180001bed  mov     ebx, eax
0x180001bef  mov     [rsp+58h+var_28], eax
0x180001bf3  cmp     edi, 1
0x180001bf6  jnz     short loc_180001C2F
0x180001bf8  test    eax, eax
0x180001bfa  jnz     short loc_180001C2F
0x180001bfc  mov     r8, rsi; lpvReserved
0x180001bff  xor     edx, edx; fdwReason
0x180001c01  mov     rcx, r14; hinstDLL
0x180001c04  call    DllMain
0x180001c09  mov     r8, rsi
0x180001c0c  xor     edx, edx
0x180001c0e  mov     rcx, r14
0x180001c11  call    dllmain_crt_dispatch
0x180001c16  mov     rax, cs:_pRawDllMain
0x180001c1d  test    rax, rax
0x180001c20  jz      short loc_180001C2F
0x180001c22  mov     r8, rsi
0x180001c25  xor     edx, edx
0x180001c27  mov     rcx, r14
0x180001c2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001c2f  test    edi, edi
0x180001c31  jz      short loc_180001C38
0x180001c33  cmp     edi, 3
0x180001c36  jnz     short loc_180001C73
0x180001c38  mov     r8, rsi
0x180001c3b  mov     edx, edi
0x180001c3d  mov     rcx, r14
0x180001c40  call    dllmain_crt_dispatch
0x180001c45  mov     ebx, eax
0x180001c47  mov     [rsp+58h+var_28], eax
0x180001c4b  test    eax, eax
0x180001c4d  jz      short loc_180001C73
0x180001c4f  mov     rax, cs:_pRawDllMain
0x180001c56  test    rax, rax
0x180001c59  jnz     short loc_180001C60
0x180001c5b  lea     ebx, [rax+1]
0x180001c5e  jmp     short loc_180001C6F
0x180001c60  mov     r8, rsi
0x180001c63  mov     edx, edi
0x180001c65  mov     rcx, r14
0x180001c68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001c6d  mov     ebx, eax
0x180001c6f  mov     [rsp+58h+var_28], ebx
0x180001c73  jmp     short loc_180001C7B
0x180001c75  xor     ebx, ebx
0x180001c77  mov     [rsp+58h+var_28], ebx
0x180001c7b  mov     eax, ebx
0x180001c7d  mov     rbx, [rsp+58h+arg_18]
0x180001c82  add     rsp, 40h
0x180001c86  pop     r14
0x180001c88  pop     rdi
0x180001c89  pop     rsi
0x180001c8a  retn
0x18000c7fc  push    rbp
0x18000c7fe  sub     rsp, 30h
0x18000c802  mov     rbp, rdx
0x18000c805  mov     rax, [rcx]
0x18000c808  mov     edx, [rax]
0x18000c80a  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x18000c80f  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x18000c813  lea     r9, dllmain_crt_dispatch; int
0x18000c81a  mov     r8, [rbp+70h]; int
0x18000c81e  mov     edx, [rbp+68h]; int
0x18000c821  mov     rcx, [rbp+60h]; int
0x18000c825  call    __scrt_dllmain_exception_filter
0x18000c82a  nop
0x18000c82b  add     rsp, 30h
0x18000c82f  pop     rbp
0x18000c830  retn
```
