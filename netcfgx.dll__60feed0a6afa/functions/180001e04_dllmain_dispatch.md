# dllmain_dispatch

- ea: `0x180001e04`
- end: `0x180001f2b`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180001f40`

## callees

- `0x180001c20`
- `0x180001e04`
- `0x1800020f8`
- `0x1800064c0`
- `0x180013010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_18001A4D0 <= 0 )
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
0x180001e04  mov     rax, rsp
0x180001e07  mov     [rax+20h], rbx
0x180001e0b  mov     [rax+18h], r8
0x180001e0f  mov     [rax+10h], edx
0x180001e12  mov     [rax+8], rcx
0x180001e16  push    rsi
0x180001e17  push    rdi
0x180001e18  push    r14
0x180001e1a  sub     rsp, 40h
0x180001e1e  mov     rsi, r8
0x180001e21  mov     edi, edx
0x180001e23  mov     r14, rcx
0x180001e26  test    edx, edx
0x180001e28  jnz     short loc_180001E39
0x180001e2a  cmp     cs:dword_18001A4D0, edx
0x180001e30  jg      short loc_180001E39
0x180001e32  xor     eax, eax
0x180001e34  jmp     loc_180001F1D
0x180001e39  lea     eax, [rdx-1]
0x180001e3c  cmp     eax, 1
0x180001e3f  ja      short loc_180001E80
0x180001e41  mov     rax, cs:_pRawDllMain
0x180001e48  test    rax, rax
0x180001e4b  jnz     short loc_180001E52
0x180001e4d  lea     ebx, [rax+1]
0x180001e50  jmp     short loc_180001E59
0x180001e52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001e57  mov     ebx, eax
0x180001e59  mov     [rsp+58h+var_28], ebx
0x180001e5d  test    ebx, ebx
0x180001e5f  jz      loc_180001F13
0x180001e65  mov     r8, rsi
0x180001e68  mov     edx, edi
0x180001e6a  mov     rcx, r14
0x180001e6d  call    dllmain_crt_dispatch
0x180001e72  mov     ebx, eax
0x180001e74  mov     [rsp+58h+var_28], eax
0x180001e78  test    eax, eax
0x180001e7a  jz      loc_180001F13
0x180001e80  mov     r8, rsi; lpvReserved
0x180001e83  mov     edx, edi; fdwReason
0x180001e85  mov     rcx, r14; hinstDLL
0x180001e88  call    DllMain
0x180001e8d  mov     ebx, eax
0x180001e8f  mov     [rsp+58h+var_28], eax
0x180001e93  cmp     edi, 1
0x180001e96  jnz     short loc_180001ECF
0x180001e98  test    eax, eax
0x180001e9a  jnz     short loc_180001ECF
0x180001e9c  mov     r8, rsi; lpvReserved
0x180001e9f  xor     edx, edx; fdwReason
0x180001ea1  mov     rcx, r14; hinstDLL
0x180001ea4  call    DllMain
0x180001ea9  mov     r8, rsi
0x180001eac  xor     edx, edx
0x180001eae  mov     rcx, r14
0x180001eb1  call    dllmain_crt_dispatch
0x180001eb6  mov     rax, cs:_pRawDllMain
0x180001ebd  test    rax, rax
0x180001ec0  jz      short loc_180001ECF
0x180001ec2  mov     r8, rsi
0x180001ec5  xor     edx, edx
0x180001ec7  mov     rcx, r14
0x180001eca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001ecf  test    edi, edi
0x180001ed1  jz      short loc_180001ED8
0x180001ed3  cmp     edi, 3
0x180001ed6  jnz     short loc_180001F13
0x180001ed8  mov     r8, rsi
0x180001edb  mov     edx, edi
0x180001edd  mov     rcx, r14
0x180001ee0  call    dllmain_crt_dispatch
0x180001ee5  mov     ebx, eax
0x180001ee7  mov     [rsp+58h+var_28], eax
0x180001eeb  test    eax, eax
0x180001eed  jz      short loc_180001F13
0x180001eef  mov     rax, cs:_pRawDllMain
0x180001ef6  test    rax, rax
0x180001ef9  jnz     short loc_180001F00
0x180001efb  lea     ebx, [rax+1]
0x180001efe  jmp     short loc_180001F0F
0x180001f00  mov     r8, rsi
0x180001f03  mov     edx, edi
0x180001f05  mov     rcx, r14
0x180001f08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001f0d  mov     ebx, eax
0x180001f0f  mov     [rsp+58h+var_28], ebx
0x180001f13  jmp     short loc_180001F1B
0x180001f15  xor     ebx, ebx
0x180001f17  mov     [rsp+58h+var_28], ebx
0x180001f1b  mov     eax, ebx
0x180001f1d  mov     rbx, [rsp+58h+arg_18]
0x180001f22  add     rsp, 40h
0x180001f26  pop     r14
0x180001f28  pop     rdi
0x180001f29  pop     rsi
0x180001f2a  retn
0x18001249c  push    rbp
0x18001249e  sub     rsp, 30h
0x1800124a2  mov     rbp, rdx
0x1800124a5  mov     rax, [rcx]
0x1800124a8  mov     edx, [rax]
0x1800124aa  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x1800124af  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x1800124b3  lea     r9, dllmain_crt_dispatch; int
0x1800124ba  mov     r8, [rbp+70h]; int
0x1800124be  mov     edx, [rbp+68h]; int
0x1800124c1  mov     rcx, [rbp+60h]; int
0x1800124c5  call    __scrt_dllmain_exception_filter
0x1800124ca  nop
0x1800124cb  add     rsp, 30h
0x1800124cf  pop     rbp
0x1800124d0  retn
```
