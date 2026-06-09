# dllmain_dispatch

- ea: `0x180001d64`
- end: `0x180001e8b`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180001ea0`

## callees

- `0x180001b80`
- `0x180001d64`
- `0x180002028`
- `0x180003770`
- `0x18000b010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_180010230 <= 0 )
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
0x180001d64  mov     rax, rsp
0x180001d67  mov     [rax+20h], rbx
0x180001d6b  mov     [rax+18h], r8
0x180001d6f  mov     [rax+10h], edx
0x180001d72  mov     [rax+8], rcx
0x180001d76  push    rsi
0x180001d77  push    rdi
0x180001d78  push    r14
0x180001d7a  sub     rsp, 40h
0x180001d7e  mov     rsi, r8
0x180001d81  mov     edi, edx
0x180001d83  mov     r14, rcx
0x180001d86  test    edx, edx
0x180001d88  jnz     short loc_180001D99
0x180001d8a  cmp     cs:dword_180010230, edx
0x180001d90  jg      short loc_180001D99
0x180001d92  xor     eax, eax
0x180001d94  jmp     loc_180001E7D
0x180001d99  lea     eax, [rdx-1]
0x180001d9c  cmp     eax, 1
0x180001d9f  ja      short loc_180001DE0
0x180001da1  mov     rax, cs:_pRawDllMain
0x180001da8  test    rax, rax
0x180001dab  jnz     short loc_180001DB2
0x180001dad  lea     ebx, [rax+1]
0x180001db0  jmp     short loc_180001DB9
0x180001db2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001db7  mov     ebx, eax
0x180001db9  mov     [rsp+58h+var_28], ebx
0x180001dbd  test    ebx, ebx
0x180001dbf  jz      loc_180001E73
0x180001dc5  mov     r8, rsi
0x180001dc8  mov     edx, edi
0x180001dca  mov     rcx, r14
0x180001dcd  call    dllmain_crt_dispatch
0x180001dd2  mov     ebx, eax
0x180001dd4  mov     [rsp+58h+var_28], eax
0x180001dd8  test    eax, eax
0x180001dda  jz      loc_180001E73
0x180001de0  mov     r8, rsi; lpvReserved
0x180001de3  mov     edx, edi; fdwReason
0x180001de5  mov     rcx, r14; hinstDLL
0x180001de8  call    DllMain
0x180001ded  mov     ebx, eax
0x180001def  mov     [rsp+58h+var_28], eax
0x180001df3  cmp     edi, 1
0x180001df6  jnz     short loc_180001E2F
0x180001df8  test    eax, eax
0x180001dfa  jnz     short loc_180001E2F
0x180001dfc  mov     r8, rsi; lpvReserved
0x180001dff  xor     edx, edx; fdwReason
0x180001e01  mov     rcx, r14; hinstDLL
0x180001e04  call    DllMain
0x180001e09  mov     r8, rsi
0x180001e0c  xor     edx, edx
0x180001e0e  mov     rcx, r14
0x180001e11  call    dllmain_crt_dispatch
0x180001e16  mov     rax, cs:_pRawDllMain
0x180001e1d  test    rax, rax
0x180001e20  jz      short loc_180001E2F
0x180001e22  mov     r8, rsi
0x180001e25  xor     edx, edx
0x180001e27  mov     rcx, r14
0x180001e2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001e2f  test    edi, edi
0x180001e31  jz      short loc_180001E38
0x180001e33  cmp     edi, 3
0x180001e36  jnz     short loc_180001E73
0x180001e38  mov     r8, rsi
0x180001e3b  mov     edx, edi
0x180001e3d  mov     rcx, r14
0x180001e40  call    dllmain_crt_dispatch
0x180001e45  mov     ebx, eax
0x180001e47  mov     [rsp+58h+var_28], eax
0x180001e4b  test    eax, eax
0x180001e4d  jz      short loc_180001E73
0x180001e4f  mov     rax, cs:_pRawDllMain
0x180001e56  test    rax, rax
0x180001e59  jnz     short loc_180001E60
0x180001e5b  lea     ebx, [rax+1]
0x180001e5e  jmp     short loc_180001E6F
0x180001e60  mov     r8, rsi
0x180001e63  mov     edx, edi
0x180001e65  mov     rcx, r14
0x180001e68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001e6d  mov     ebx, eax
0x180001e6f  mov     [rsp+58h+var_28], ebx
0x180001e73  jmp     short loc_180001E7B
0x180001e75  xor     ebx, ebx
0x180001e77  mov     [rsp+58h+var_28], ebx
0x180001e7b  mov     eax, ebx
0x180001e7d  mov     rbx, [rsp+58h+arg_18]
0x180001e82  add     rsp, 40h
0x180001e86  pop     r14
0x180001e88  pop     rdi
0x180001e89  pop     rsi
0x180001e8a  retn
0x18000a3ac  push    rbp
0x18000a3ae  sub     rsp, 30h
0x18000a3b2  mov     rbp, rdx
0x18000a3b5  mov     rax, [rcx]
0x18000a3b8  mov     edx, [rax]
0x18000a3ba  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x18000a3bf  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x18000a3c3  lea     r9, dllmain_crt_dispatch; int
0x18000a3ca  mov     r8, [rbp+70h]; int
0x18000a3ce  mov     edx, [rbp+68h]; int
0x18000a3d1  mov     rcx, [rbp+60h]; int
0x18000a3d5  call    __scrt_dllmain_exception_filter
0x18000a3da  nop
0x18000a3db  add     rsp, 30h
0x18000a3df  pop     rbp
0x18000a3e0  retn
```
