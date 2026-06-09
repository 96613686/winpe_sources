# dllmain_dispatch

- ea: `0x180001374`
- end: `0x18000149b`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(__int64, unsigned int, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x1800014b0`

## callees

- `0x180001190`
- `0x180001374`
- `0x1800015fc`
- `0x180001a40`
- `0x18000d010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(__int64 a1, unsigned int a2, __int64 a3)
{
  unsigned int v7; // ebx
  _crt_argv_mode startup_argv_mode; // eax

  if ( !a2 && dword_180014248 <= 0 )
    return 0;
  if ( a2 - 1 > 1
    || (pRawDllMain ? (v7 = ((__int64 (*)(void))pRawDllMain)()) : (v7 = 1),
        v7 && (v7 = dllmain_crt_dispatch(a1, a2, a3)) != 0) )
  {
    startup_argv_mode = get_startup_argv_mode();
    v7 = startup_argv_mode;
    if ( a2 == 1 && startup_argv_mode == _crt_argv_no_arguments )
    {
      get_startup_argv_mode();
      dllmain_crt_dispatch(a1, 0, a3);
      if ( pRawDllMain )
        pRawDllMain(a1, 0, a3);
    }
    if ( !a2 || a2 == 3 )
    {
      v7 = dllmain_crt_dispatch(a1, a2, a3);
      if ( v7 )
      {
        if ( pRawDllMain )
          return (unsigned int)pRawDllMain(a1, a2, a3);
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
0x180001374  mov     rax, rsp
0x180001377  mov     [rax+20h], rbx
0x18000137b  mov     [rax+18h], r8
0x18000137f  mov     [rax+10h], edx
0x180001382  mov     [rax+8], rcx
0x180001386  push    rsi
0x180001387  push    rdi
0x180001388  push    r14
0x18000138a  sub     rsp, 40h
0x18000138e  mov     rsi, r8
0x180001391  mov     edi, edx
0x180001393  mov     r14, rcx
0x180001396  test    edx, edx
0x180001398  jnz     short loc_1800013A9
0x18000139a  cmp     cs:dword_180014248, edx
0x1800013a0  jg      short loc_1800013A9
0x1800013a2  xor     eax, eax
0x1800013a4  jmp     loc_18000148D
0x1800013a9  lea     eax, [rdx-1]
0x1800013ac  cmp     eax, 1
0x1800013af  ja      short loc_1800013F0
0x1800013b1  mov     rax, cs:_pRawDllMain
0x1800013b8  test    rax, rax
0x1800013bb  jnz     short loc_1800013C2
0x1800013bd  lea     ebx, [rax+1]
0x1800013c0  jmp     short loc_1800013C9
0x1800013c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800013c7  mov     ebx, eax
0x1800013c9  mov     [rsp+58h+var_28], ebx
0x1800013cd  test    ebx, ebx
0x1800013cf  jz      loc_180001483
0x1800013d5  mov     r8, rsi
0x1800013d8  mov     edx, edi
0x1800013da  mov     rcx, r14
0x1800013dd  call    dllmain_crt_dispatch
0x1800013e2  mov     ebx, eax
0x1800013e4  mov     [rsp+58h+var_28], eax
0x1800013e8  test    eax, eax
0x1800013ea  jz      loc_180001483
0x1800013f0  mov     r8, rsi
0x1800013f3  mov     edx, edi
0x1800013f5  mov     rcx, r14
0x1800013f8  call    _get_startup_argv_mode
0x1800013fd  mov     ebx, eax
0x1800013ff  mov     [rsp+58h+var_28], eax
0x180001403  cmp     edi, 1
0x180001406  jnz     short loc_18000143F
0x180001408  test    eax, eax
0x18000140a  jnz     short loc_18000143F
0x18000140c  mov     r8, rsi
0x18000140f  xor     edx, edx
0x180001411  mov     rcx, r14
0x180001414  call    _get_startup_argv_mode
0x180001419  mov     r8, rsi
0x18000141c  xor     edx, edx
0x18000141e  mov     rcx, r14
0x180001421  call    dllmain_crt_dispatch
0x180001426  mov     rax, cs:_pRawDllMain
0x18000142d  test    rax, rax
0x180001430  jz      short loc_18000143F
0x180001432  mov     r8, rsi
0x180001435  xor     edx, edx
0x180001437  mov     rcx, r14
0x18000143a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000143f  test    edi, edi
0x180001441  jz      short loc_180001448
0x180001443  cmp     edi, 3
0x180001446  jnz     short loc_180001483
0x180001448  mov     r8, rsi
0x18000144b  mov     edx, edi
0x18000144d  mov     rcx, r14
0x180001450  call    dllmain_crt_dispatch
0x180001455  mov     ebx, eax
0x180001457  mov     [rsp+58h+var_28], eax
0x18000145b  test    eax, eax
0x18000145d  jz      short loc_180001483
0x18000145f  mov     rax, cs:_pRawDllMain
0x180001466  test    rax, rax
0x180001469  jnz     short loc_180001470
0x18000146b  lea     ebx, [rax+1]
0x18000146e  jmp     short loc_18000147F
0x180001470  mov     r8, rsi
0x180001473  mov     edx, edi
0x180001475  mov     rcx, r14
0x180001478  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000147d  mov     ebx, eax
0x18000147f  mov     [rsp+58h+var_28], ebx
0x180001483  jmp     short loc_18000148B
0x180001485  xor     ebx, ebx
0x180001487  mov     [rsp+58h+var_28], ebx
0x18000148b  mov     eax, ebx
0x18000148d  mov     rbx, [rsp+58h+arg_18]
0x180001492  add     rsp, 40h
0x180001496  pop     r14
0x180001498  pop     rdi
0x180001499  pop     rsi
0x18000149a  retn
0x18000bc90  push    rbp
0x18000bc92  sub     rsp, 30h
0x18000bc96  mov     rbp, rdx
0x18000bc99  mov     rax, [rcx]
0x18000bc9c  mov     edx, [rax]
0x18000bc9e  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x18000bca3  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x18000bca7  lea     r9, dllmain_crt_dispatch; int
0x18000bcae  mov     r8, [rbp+70h]; int
0x18000bcb2  mov     edx, [rbp+68h]; int
0x18000bcb5  mov     rcx, [rbp+60h]; int
0x18000bcb9  call    __scrt_dllmain_exception_filter
0x18000bcbe  nop
0x18000bcbf  add     rsp, 30h
0x18000bcc3  pop     rbp
0x18000bcc4  retn
```
