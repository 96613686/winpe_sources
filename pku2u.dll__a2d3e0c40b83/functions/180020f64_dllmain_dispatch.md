# dllmain_dispatch

- ea: `0x180020f64`
- end: `0x18002108b`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x1800210a0`

## callees

- `0x180020d80`
- `0x180020f64`
- `0x1800212f4`
- `0x180022a30`
- `0x180046010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_180054950 <= 0 )
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
0x180020f64  mov     rax, rsp
0x180020f67  mov     [rax+20h], rbx
0x180020f6b  mov     [rax+18h], r8
0x180020f6f  mov     [rax+10h], edx
0x180020f72  mov     [rax+8], rcx
0x180020f76  push    rsi
0x180020f77  push    rdi
0x180020f78  push    r14
0x180020f7a  sub     rsp, 40h
0x180020f7e  mov     rsi, r8
0x180020f81  mov     edi, edx
0x180020f83  mov     r14, rcx
0x180020f86  test    edx, edx
0x180020f88  jnz     short loc_180020F99
0x180020f8a  cmp     cs:dword_180054950, edx
0x180020f90  jg      short loc_180020F99
0x180020f92  xor     eax, eax
0x180020f94  jmp     loc_18002107D
0x180020f99  lea     eax, [rdx-1]
0x180020f9c  cmp     eax, 1
0x180020f9f  ja      short loc_180020FE0
0x180020fa1  mov     rax, cs:_pRawDllMain
0x180020fa8  test    rax, rax
0x180020fab  jnz     short loc_180020FB2
0x180020fad  lea     ebx, [rax+1]
0x180020fb0  jmp     short loc_180020FB9
0x180020fb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020fb7  mov     ebx, eax
0x180020fb9  mov     [rsp+58h+var_28], ebx
0x180020fbd  test    ebx, ebx
0x180020fbf  jz      loc_180021073
0x180020fc5  mov     r8, rsi
0x180020fc8  mov     edx, edi
0x180020fca  mov     rcx, r14
0x180020fcd  call    dllmain_crt_dispatch
0x180020fd2  mov     ebx, eax
0x180020fd4  mov     [rsp+58h+var_28], eax
0x180020fd8  test    eax, eax
0x180020fda  jz      loc_180021073
0x180020fe0  mov     r8, rsi; lpvReserved
0x180020fe3  mov     edx, edi; fdwReason
0x180020fe5  mov     rcx, r14; hinstDLL
0x180020fe8  call    DllMain
0x180020fed  mov     ebx, eax
0x180020fef  mov     [rsp+58h+var_28], eax
0x180020ff3  cmp     edi, 1
0x180020ff6  jnz     short loc_18002102F
0x180020ff8  test    eax, eax
0x180020ffa  jnz     short loc_18002102F
0x180020ffc  mov     r8, rsi; lpvReserved
0x180020fff  xor     edx, edx; fdwReason
0x180021001  mov     rcx, r14; hinstDLL
0x180021004  call    DllMain
0x180021009  mov     r8, rsi
0x18002100c  xor     edx, edx
0x18002100e  mov     rcx, r14
0x180021011  call    dllmain_crt_dispatch
0x180021016  mov     rax, cs:_pRawDllMain
0x18002101d  test    rax, rax
0x180021020  jz      short loc_18002102F
0x180021022  mov     r8, rsi
0x180021025  xor     edx, edx
0x180021027  mov     rcx, r14
0x18002102a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002102f  test    edi, edi
0x180021031  jz      short loc_180021038
0x180021033  cmp     edi, 3
0x180021036  jnz     short loc_180021073
0x180021038  mov     r8, rsi
0x18002103b  mov     edx, edi
0x18002103d  mov     rcx, r14
0x180021040  call    dllmain_crt_dispatch
0x180021045  mov     ebx, eax
0x180021047  mov     [rsp+58h+var_28], eax
0x18002104b  test    eax, eax
0x18002104d  jz      short loc_180021073
0x18002104f  mov     rax, cs:_pRawDllMain
0x180021056  test    rax, rax
0x180021059  jnz     short loc_180021060
0x18002105b  lea     ebx, [rax+1]
0x18002105e  jmp     short loc_18002106F
0x180021060  mov     r8, rsi
0x180021063  mov     edx, edi
0x180021065  mov     rcx, r14
0x180021068  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002106d  mov     ebx, eax
0x18002106f  mov     [rsp+58h+var_28], ebx
0x180021073  jmp     short loc_18002107B
0x180021075  xor     ebx, ebx
0x180021077  mov     [rsp+58h+var_28], ebx
0x18002107b  mov     eax, ebx
0x18002107d  mov     rbx, [rsp+58h+arg_18]
0x180021082  add     rsp, 40h
0x180021086  pop     r14
0x180021088  pop     rdi
0x180021089  pop     rsi
0x18002108a  retn
0x1800450a6  push    rbp
0x1800450a8  sub     rsp, 30h
0x1800450ac  mov     rbp, rdx
0x1800450af  mov     rax, [rcx]
0x1800450b2  mov     edx, [rax]
0x1800450b4  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x1800450b9  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x1800450bd  lea     r9, dllmain_crt_dispatch; int
0x1800450c4  mov     r8, [rbp+70h]; int
0x1800450c8  mov     edx, [rbp+68h]; int
0x1800450cb  mov     rcx, [rbp+60h]; int
0x1800450cf  call    __scrt_dllmain_exception_filter
0x1800450d4  nop
0x1800450d5  add     rsp, 30h
0x1800450d9  pop     rbp
0x1800450da  retn
```
