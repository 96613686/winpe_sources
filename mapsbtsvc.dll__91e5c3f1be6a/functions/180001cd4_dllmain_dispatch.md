# dllmain_dispatch

- ea: `0x180001cd4`
- end: `0x180001dfb`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180001e10`

## callees

- `0x180001af0`
- `0x180001cd4`
- `0x180001f78`
- `0x180003314`
- `0x180015010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_18001D590 <= 0 )
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
0x180001cd4  mov     rax, rsp
0x180001cd7  mov     [rax+20h], rbx
0x180001cdb  mov     [rax+18h], r8
0x180001cdf  mov     [rax+10h], edx
0x180001ce2  mov     [rax+8], rcx
0x180001ce6  push    rsi
0x180001ce7  push    rdi
0x180001ce8  push    r14
0x180001cea  sub     rsp, 40h
0x180001cee  mov     rsi, r8
0x180001cf1  mov     edi, edx
0x180001cf3  mov     r14, rcx
0x180001cf6  test    edx, edx
0x180001cf8  jnz     short loc_180001D09
0x180001cfa  cmp     cs:dword_18001D590, edx
0x180001d00  jg      short loc_180001D09
0x180001d02  xor     eax, eax
0x180001d04  jmp     loc_180001DED
0x180001d09  lea     eax, [rdx-1]
0x180001d0c  cmp     eax, 1
0x180001d0f  ja      short loc_180001D50
0x180001d11  mov     rax, cs:_pRawDllMain
0x180001d18  test    rax, rax
0x180001d1b  jnz     short loc_180001D22
0x180001d1d  lea     ebx, [rax+1]
0x180001d20  jmp     short loc_180001D29
0x180001d22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001d27  mov     ebx, eax
0x180001d29  mov     [rsp+58h+var_28], ebx
0x180001d2d  test    ebx, ebx
0x180001d2f  jz      loc_180001DE3
0x180001d35  mov     r8, rsi
0x180001d38  mov     edx, edi
0x180001d3a  mov     rcx, r14
0x180001d3d  call    dllmain_crt_dispatch
0x180001d42  mov     ebx, eax
0x180001d44  mov     [rsp+58h+var_28], eax
0x180001d48  test    eax, eax
0x180001d4a  jz      loc_180001DE3
0x180001d50  mov     r8, rsi; lpvReserved
0x180001d53  mov     edx, edi; fdwReason
0x180001d55  mov     rcx, r14; hinstDLL
0x180001d58  call    DllMain
0x180001d5d  mov     ebx, eax
0x180001d5f  mov     [rsp+58h+var_28], eax
0x180001d63  cmp     edi, 1
0x180001d66  jnz     short loc_180001D9F
0x180001d68  test    eax, eax
0x180001d6a  jnz     short loc_180001D9F
0x180001d6c  mov     r8, rsi; lpvReserved
0x180001d6f  xor     edx, edx; fdwReason
0x180001d71  mov     rcx, r14; hinstDLL
0x180001d74  call    DllMain
0x180001d79  mov     r8, rsi
0x180001d7c  xor     edx, edx
0x180001d7e  mov     rcx, r14
0x180001d81  call    dllmain_crt_dispatch
0x180001d86  mov     rax, cs:_pRawDllMain
0x180001d8d  test    rax, rax
0x180001d90  jz      short loc_180001D9F
0x180001d92  mov     r8, rsi
0x180001d95  xor     edx, edx
0x180001d97  mov     rcx, r14
0x180001d9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001d9f  test    edi, edi
0x180001da1  jz      short loc_180001DA8
0x180001da3  cmp     edi, 3
0x180001da6  jnz     short loc_180001DE3
0x180001da8  mov     r8, rsi
0x180001dab  mov     edx, edi
0x180001dad  mov     rcx, r14
0x180001db0  call    dllmain_crt_dispatch
0x180001db5  mov     ebx, eax
0x180001db7  mov     [rsp+58h+var_28], eax
0x180001dbb  test    eax, eax
0x180001dbd  jz      short loc_180001DE3
0x180001dbf  mov     rax, cs:_pRawDllMain
0x180001dc6  test    rax, rax
0x180001dc9  jnz     short loc_180001DD0
0x180001dcb  lea     ebx, [rax+1]
0x180001dce  jmp     short loc_180001DDF
0x180001dd0  mov     r8, rsi
0x180001dd3  mov     edx, edi
0x180001dd5  mov     rcx, r14
0x180001dd8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001ddd  mov     ebx, eax
0x180001ddf  mov     [rsp+58h+var_28], ebx
0x180001de3  jmp     short loc_180001DEB
0x180001de5  xor     ebx, ebx
0x180001de7  mov     [rsp+58h+var_28], ebx
0x180001deb  mov     eax, ebx
0x180001ded  mov     rbx, [rsp+58h+arg_18]
0x180001df2  add     rsp, 40h
0x180001df6  pop     r14
0x180001df8  pop     rdi
0x180001df9  pop     rsi
0x180001dfa  retn
0x180013abc  push    rbp
0x180013abe  sub     rsp, 30h
0x180013ac2  mov     rbp, rdx
0x180013ac5  mov     rax, [rcx]
0x180013ac8  mov     edx, [rax]
0x180013aca  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x180013acf  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x180013ad3  lea     r9, dllmain_crt_dispatch; int
0x180013ada  mov     r8, [rbp+70h]; int
0x180013ade  mov     edx, [rbp+68h]; int
0x180013ae1  mov     rcx, [rbp+60h]; int
0x180013ae5  call    __scrt_dllmain_exception_filter
0x180013aea  nop
0x180013aeb  add     rsp, 30h
0x180013aef  pop     rbp
0x180013af0  retn
```
