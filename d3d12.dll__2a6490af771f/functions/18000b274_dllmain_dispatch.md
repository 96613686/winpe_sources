# dllmain_dispatch

- ea: `0x18000b274`
- end: `0x18000b39b`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x18000b3b0`

## callees

- `0x180004ba8`
- `0x18000b090`
- `0x18000b274`
- `0x18000b50c`
- `0x180015010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_18001C510 <= 0 )
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
0x18000b274  mov     rax, rsp
0x18000b277  mov     [rax+20h], rbx
0x18000b27b  mov     [rax+18h], r8
0x18000b27f  mov     [rax+10h], edx
0x18000b282  mov     [rax+8], rcx
0x18000b286  push    rsi
0x18000b287  push    rdi
0x18000b288  push    r14
0x18000b28a  sub     rsp, 40h
0x18000b28e  mov     rsi, r8
0x18000b291  mov     edi, edx
0x18000b293  mov     r14, rcx
0x18000b296  test    edx, edx
0x18000b298  jnz     short loc_18000B2A9
0x18000b29a  cmp     cs:dword_18001C510, edx
0x18000b2a0  jg      short loc_18000B2A9
0x18000b2a2  xor     eax, eax
0x18000b2a4  jmp     loc_18000B38D
0x18000b2a9  lea     eax, [rdx-1]
0x18000b2ac  cmp     eax, 1
0x18000b2af  ja      short loc_18000B2F0
0x18000b2b1  mov     rax, cs:_pRawDllMain
0x18000b2b8  test    rax, rax
0x18000b2bb  jnz     short loc_18000B2C2
0x18000b2bd  lea     ebx, [rax+1]
0x18000b2c0  jmp     short loc_18000B2C9
0x18000b2c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b2c7  mov     ebx, eax
0x18000b2c9  mov     [rsp+58h+var_28], ebx
0x18000b2cd  test    ebx, ebx
0x18000b2cf  jz      loc_18000B383
0x18000b2d5  mov     r8, rsi
0x18000b2d8  mov     edx, edi
0x18000b2da  mov     rcx, r14
0x18000b2dd  call    dllmain_crt_dispatch
0x18000b2e2  mov     ebx, eax
0x18000b2e4  mov     [rsp+58h+var_28], eax
0x18000b2e8  test    eax, eax
0x18000b2ea  jz      loc_18000B383
0x18000b2f0  mov     r8, rsi; lpvReserved
0x18000b2f3  mov     edx, edi; fdwReason
0x18000b2f5  mov     rcx, r14; hinstDLL
0x18000b2f8  call    DllMain
0x18000b2fd  mov     ebx, eax
0x18000b2ff  mov     [rsp+58h+var_28], eax
0x18000b303  cmp     edi, 1
0x18000b306  jnz     short loc_18000B33F
0x18000b308  test    eax, eax
0x18000b30a  jnz     short loc_18000B33F
0x18000b30c  mov     r8, rsi; lpvReserved
0x18000b30f  xor     edx, edx; fdwReason
0x18000b311  mov     rcx, r14; hinstDLL
0x18000b314  call    DllMain
0x18000b319  mov     r8, rsi
0x18000b31c  xor     edx, edx
0x18000b31e  mov     rcx, r14
0x18000b321  call    dllmain_crt_dispatch
0x18000b326  mov     rax, cs:_pRawDllMain
0x18000b32d  test    rax, rax
0x18000b330  jz      short loc_18000B33F
0x18000b332  mov     r8, rsi
0x18000b335  xor     edx, edx
0x18000b337  mov     rcx, r14
0x18000b33a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b33f  test    edi, edi
0x18000b341  jz      short loc_18000B348
0x18000b343  cmp     edi, 3
0x18000b346  jnz     short loc_18000B383
0x18000b348  mov     r8, rsi
0x18000b34b  mov     edx, edi
0x18000b34d  mov     rcx, r14
0x18000b350  call    dllmain_crt_dispatch
0x18000b355  mov     ebx, eax
0x18000b357  mov     [rsp+58h+var_28], eax
0x18000b35b  test    eax, eax
0x18000b35d  jz      short loc_18000B383
0x18000b35f  mov     rax, cs:_pRawDllMain
0x18000b366  test    rax, rax
0x18000b369  jnz     short loc_18000B370
0x18000b36b  lea     ebx, [rax+1]
0x18000b36e  jmp     short loc_18000B37F
0x18000b370  mov     r8, rsi
0x18000b373  mov     edx, edi
0x18000b375  mov     rcx, r14
0x18000b378  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b37d  mov     ebx, eax
0x18000b37f  mov     [rsp+58h+var_28], ebx
0x18000b383  jmp     short loc_18000B38B
0x18000b385  xor     ebx, ebx
0x18000b387  mov     [rsp+58h+var_28], ebx
0x18000b38b  mov     eax, ebx
0x18000b38d  mov     rbx, [rsp+58h+arg_18]
0x18000b392  add     rsp, 40h
0x18000b396  pop     r14
0x18000b398  pop     rdi
0x18000b399  pop     rsi
0x18000b39a  retn
0x180013e7e  push    rbp
0x180013e80  sub     rsp, 30h
0x180013e84  mov     rbp, rdx
0x180013e87  mov     rax, [rcx]
0x180013e8a  mov     edx, [rax]
0x180013e8c  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x180013e91  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x180013e95  lea     r9, dllmain_crt_dispatch; int
0x180013e9c  mov     r8, [rbp+70h]; int
0x180013ea0  mov     edx, [rbp+68h]; int
0x180013ea3  mov     rcx, [rbp+60h]; int
0x180013ea7  call    __scrt_dllmain_exception_filter
0x180013eac  nop
0x180013ead  add     rsp, 30h
0x180013eb1  pop     rbp
0x180013eb2  retn
```
