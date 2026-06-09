# dllmain_dispatch

- ea: `0x180002494`
- end: `0x1800025bb`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x1800025d0`

## callees

- `0x1800022b0`
- `0x180002494`
- `0x180002728`
- `0x180012208`
- `0x180013010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_18001A210 <= 0 )
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
0x180002494  mov     rax, rsp
0x180002497  mov     [rax+20h], rbx
0x18000249b  mov     [rax+18h], r8
0x18000249f  mov     [rax+10h], edx
0x1800024a2  mov     [rax+8], rcx
0x1800024a6  push    rsi
0x1800024a7  push    rdi
0x1800024a8  push    r14
0x1800024aa  sub     rsp, 40h
0x1800024ae  mov     rsi, r8
0x1800024b1  mov     edi, edx
0x1800024b3  mov     r14, rcx
0x1800024b6  test    edx, edx
0x1800024b8  jnz     short loc_1800024C9
0x1800024ba  cmp     cs:dword_18001A210, edx
0x1800024c0  jg      short loc_1800024C9
0x1800024c2  xor     eax, eax
0x1800024c4  jmp     loc_1800025AD
0x1800024c9  lea     eax, [rdx-1]
0x1800024cc  cmp     eax, 1
0x1800024cf  ja      short loc_180002510
0x1800024d1  mov     rax, cs:_pRawDllMain
0x1800024d8  test    rax, rax
0x1800024db  jnz     short loc_1800024E2
0x1800024dd  lea     ebx, [rax+1]
0x1800024e0  jmp     short loc_1800024E9
0x1800024e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800024e7  mov     ebx, eax
0x1800024e9  mov     [rsp+58h+var_28], ebx
0x1800024ed  test    ebx, ebx
0x1800024ef  jz      loc_1800025A3
0x1800024f5  mov     r8, rsi
0x1800024f8  mov     edx, edi
0x1800024fa  mov     rcx, r14
0x1800024fd  call    dllmain_crt_dispatch
0x180002502  mov     ebx, eax
0x180002504  mov     [rsp+58h+var_28], eax
0x180002508  test    eax, eax
0x18000250a  jz      loc_1800025A3
0x180002510  mov     r8, rsi; lpvReserved
0x180002513  mov     edx, edi; fdwReason
0x180002515  mov     rcx, r14; hinstDLL
0x180002518  call    DllMain
0x18000251d  mov     ebx, eax
0x18000251f  mov     [rsp+58h+var_28], eax
0x180002523  cmp     edi, 1
0x180002526  jnz     short loc_18000255F
0x180002528  test    eax, eax
0x18000252a  jnz     short loc_18000255F
0x18000252c  mov     r8, rsi; lpvReserved
0x18000252f  xor     edx, edx; fdwReason
0x180002531  mov     rcx, r14; hinstDLL
0x180002534  call    DllMain
0x180002539  mov     r8, rsi
0x18000253c  xor     edx, edx
0x18000253e  mov     rcx, r14
0x180002541  call    dllmain_crt_dispatch
0x180002546  mov     rax, cs:_pRawDllMain
0x18000254d  test    rax, rax
0x180002550  jz      short loc_18000255F
0x180002552  mov     r8, rsi
0x180002555  xor     edx, edx
0x180002557  mov     rcx, r14
0x18000255a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000255f  test    edi, edi
0x180002561  jz      short loc_180002568
0x180002563  cmp     edi, 3
0x180002566  jnz     short loc_1800025A3
0x180002568  mov     r8, rsi
0x18000256b  mov     edx, edi
0x18000256d  mov     rcx, r14
0x180002570  call    dllmain_crt_dispatch
0x180002575  mov     ebx, eax
0x180002577  mov     [rsp+58h+var_28], eax
0x18000257b  test    eax, eax
0x18000257d  jz      short loc_1800025A3
0x18000257f  mov     rax, cs:_pRawDllMain
0x180002586  test    rax, rax
0x180002589  jnz     short loc_180002590
0x18000258b  lea     ebx, [rax+1]
0x18000258e  jmp     short loc_18000259F
0x180002590  mov     r8, rsi
0x180002593  mov     edx, edi
0x180002595  mov     rcx, r14
0x180002598  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000259d  mov     ebx, eax
0x18000259f  mov     [rsp+58h+var_28], ebx
0x1800025a3  jmp     short loc_1800025AB
0x1800025a5  xor     ebx, ebx
0x1800025a7  mov     [rsp+58h+var_28], ebx
0x1800025ab  mov     eax, ebx
0x1800025ad  mov     rbx, [rsp+58h+arg_18]
0x1800025b2  add     rsp, 40h
0x1800025b6  pop     r14
0x1800025b8  pop     rdi
0x1800025b9  pop     rsi
0x1800025ba  retn
0x180012b5c  push    rbp
0x180012b5e  sub     rsp, 30h
0x180012b62  mov     rbp, rdx
0x180012b65  mov     rax, [rcx]
0x180012b68  mov     edx, [rax]
0x180012b6a  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x180012b6f  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x180012b73  lea     r9, dllmain_crt_dispatch; int
0x180012b7a  mov     r8, [rbp+70h]; int
0x180012b7e  mov     edx, [rbp+68h]; int
0x180012b81  mov     rcx, [rbp+60h]; int
0x180012b85  call    __scrt_dllmain_exception_filter
0x180012b8a  nop
0x180012b8b  add     rsp, 30h
0x180012b8f  pop     rbp
0x180012b90  retn
```
