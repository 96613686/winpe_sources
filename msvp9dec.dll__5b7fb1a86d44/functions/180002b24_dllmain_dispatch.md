# dllmain_dispatch

- ea: `0x180002b24`
- end: `0x180002c4b`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180002c60`

## callees

- `0x180001150`
- `0x180002940`
- `0x180002b24`
- `0x180002dd0`
- `0x180006010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_18000A1D0 <= 0 )
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
0x180002b24  mov     rax, rsp
0x180002b27  mov     [rax+20h], rbx
0x180002b2b  mov     [rax+18h], r8
0x180002b2f  mov     [rax+10h], edx
0x180002b32  mov     [rax+8], rcx
0x180002b36  push    rsi
0x180002b37  push    rdi
0x180002b38  push    r14
0x180002b3a  sub     rsp, 40h
0x180002b3e  mov     rsi, r8
0x180002b41  mov     edi, edx
0x180002b43  mov     r14, rcx
0x180002b46  test    edx, edx
0x180002b48  jnz     short loc_180002B59
0x180002b4a  cmp     cs:dword_18000A1D0, edx
0x180002b50  jg      short loc_180002B59
0x180002b52  xor     eax, eax
0x180002b54  jmp     loc_180002C3D
0x180002b59  lea     eax, [rdx-1]
0x180002b5c  cmp     eax, 1
0x180002b5f  ja      short loc_180002BA0
0x180002b61  mov     rax, cs:_pRawDllMain
0x180002b68  test    rax, rax
0x180002b6b  jnz     short loc_180002B72
0x180002b6d  lea     ebx, [rax+1]
0x180002b70  jmp     short loc_180002B79
0x180002b72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002b77  mov     ebx, eax
0x180002b79  mov     [rsp+58h+var_28], ebx
0x180002b7d  test    ebx, ebx
0x180002b7f  jz      loc_180002C33
0x180002b85  mov     r8, rsi
0x180002b88  mov     edx, edi
0x180002b8a  mov     rcx, r14
0x180002b8d  call    dllmain_crt_dispatch
0x180002b92  mov     ebx, eax
0x180002b94  mov     [rsp+58h+var_28], eax
0x180002b98  test    eax, eax
0x180002b9a  jz      loc_180002C33
0x180002ba0  mov     r8, rsi; lpvReserved
0x180002ba3  mov     edx, edi; fdwReason
0x180002ba5  mov     rcx, r14; hinstDLL
0x180002ba8  call    DllMain
0x180002bad  mov     ebx, eax
0x180002baf  mov     [rsp+58h+var_28], eax
0x180002bb3  cmp     edi, 1
0x180002bb6  jnz     short loc_180002BEF
0x180002bb8  test    eax, eax
0x180002bba  jnz     short loc_180002BEF
0x180002bbc  mov     r8, rsi; lpvReserved
0x180002bbf  xor     edx, edx; fdwReason
0x180002bc1  mov     rcx, r14; hinstDLL
0x180002bc4  call    DllMain
0x180002bc9  mov     r8, rsi
0x180002bcc  xor     edx, edx
0x180002bce  mov     rcx, r14
0x180002bd1  call    dllmain_crt_dispatch
0x180002bd6  mov     rax, cs:_pRawDllMain
0x180002bdd  test    rax, rax
0x180002be0  jz      short loc_180002BEF
0x180002be2  mov     r8, rsi
0x180002be5  xor     edx, edx
0x180002be7  mov     rcx, r14
0x180002bea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002bef  test    edi, edi
0x180002bf1  jz      short loc_180002BF8
0x180002bf3  cmp     edi, 3
0x180002bf6  jnz     short loc_180002C33
0x180002bf8  mov     r8, rsi
0x180002bfb  mov     edx, edi
0x180002bfd  mov     rcx, r14
0x180002c00  call    dllmain_crt_dispatch
0x180002c05  mov     ebx, eax
0x180002c07  mov     [rsp+58h+var_28], eax
0x180002c0b  test    eax, eax
0x180002c0d  jz      short loc_180002C33
0x180002c0f  mov     rax, cs:_pRawDllMain
0x180002c16  test    rax, rax
0x180002c19  jnz     short loc_180002C20
0x180002c1b  lea     ebx, [rax+1]
0x180002c1e  jmp     short loc_180002C2F
0x180002c20  mov     r8, rsi
0x180002c23  mov     edx, edi
0x180002c25  mov     rcx, r14
0x180002c28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002c2d  mov     ebx, eax
0x180002c2f  mov     [rsp+58h+var_28], ebx
0x180002c33  jmp     short loc_180002C3B
0x180002c35  xor     ebx, ebx
0x180002c37  mov     [rsp+58h+var_28], ebx
0x180002c3b  mov     eax, ebx
0x180002c3d  mov     rbx, [rsp+58h+arg_18]
0x180002c42  add     rsp, 40h
0x180002c46  pop     r14
0x180002c48  pop     rdi
0x180002c49  pop     rsi
0x180002c4a  retn
0x1800050fc  push    rbp
0x1800050fe  sub     rsp, 30h
0x180005102  mov     rbp, rdx
0x180005105  mov     rax, [rcx]
0x180005108  mov     edx, [rax]
0x18000510a  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x18000510f  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x180005113  lea     r9, dllmain_crt_dispatch; int
0x18000511a  mov     r8, [rbp+70h]; int
0x18000511e  mov     edx, [rbp+68h]; int
0x180005121  mov     rcx, [rbp+60h]; int
0x180005125  call    __scrt_dllmain_exception_filter
0x18000512a  nop
0x18000512b  add     rsp, 30h
0x18000512f  pop     rbp
0x180005130  retn
```
