# dllmain_dispatch

- ea: `0x1800015f4`
- end: `0x18000171b`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180001730`

## callees

- `0x180001410`
- `0x1800015f4`
- `0x1800018b4`
- `0x18000607c`
- `0x18000f010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_180015390 <= 0 )
    return 0;
  if ( fdwReason - 1 > 1
    || (pRawDllMain ? (v7 = pRawDllMain()) : (v7 = 1),
        v7 && (v7 = dllmain_crt_dispatch(hinstDLL, fdwReason, lpvReserved)) != 0) )
  {
    v8 = DllMain(hinstDLL, fdwReason, lpvReserved);
    v7 = v8;
    if ( fdwReason == 1 && !v8 )
    {
      DllMain(hinstDLL, 0, lpvReserved);
      dllmain_crt_dispatch(hinstDLL, 0, lpvReserved);
      if ( pRawDllMain )
        pRawDllMain();
    }
    if ( !fdwReason || fdwReason == 3 )
    {
      v7 = dllmain_crt_dispatch(hinstDLL, fdwReason, lpvReserved);
      if ( v7 )
      {
        if ( pRawDllMain )
          return (unsigned int)pRawDllMain();
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
0x1800015f4  mov     rax, rsp
0x1800015f7  mov     [rax+20h], rbx
0x1800015fb  mov     [rax+18h], r8
0x1800015ff  mov     [rax+10h], edx
0x180001602  mov     [rax+8], rcx
0x180001606  push    rsi
0x180001607  push    rdi
0x180001608  push    r14
0x18000160a  sub     rsp, 40h
0x18000160e  mov     rsi, r8
0x180001611  mov     edi, edx
0x180001613  mov     r14, rcx
0x180001616  test    edx, edx
0x180001618  jnz     short loc_180001629
0x18000161a  cmp     cs:dword_180015390, edx
0x180001620  jg      short loc_180001629
0x180001622  xor     eax, eax
0x180001624  jmp     loc_18000170D
0x180001629  lea     eax, [rdx-1]
0x18000162c  cmp     eax, 1
0x18000162f  ja      short loc_180001670
0x180001631  mov     rax, cs:_pRawDllMain
0x180001638  test    rax, rax
0x18000163b  jnz     short loc_180001642
0x18000163d  lea     ebx, [rax+1]
0x180001640  jmp     short loc_180001649
0x180001642  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001647  mov     ebx, eax
0x180001649  mov     [rsp+58h+var_28], ebx
0x18000164d  test    ebx, ebx
0x18000164f  jz      loc_180001703
0x180001655  mov     r8, rsi
0x180001658  mov     edx, edi
0x18000165a  mov     rcx, r14
0x18000165d  call    dllmain_crt_dispatch
0x180001662  mov     ebx, eax
0x180001664  mov     [rsp+58h+var_28], eax
0x180001668  test    eax, eax
0x18000166a  jz      loc_180001703
0x180001670  mov     r8, rsi; lpvReserved
0x180001673  mov     edx, edi; fdwReason
0x180001675  mov     rcx, r14; hinstDLL
0x180001678  call    DllMain
0x18000167d  mov     ebx, eax
0x18000167f  mov     [rsp+58h+var_28], eax
0x180001683  cmp     edi, 1
0x180001686  jnz     short loc_1800016BF
0x180001688  test    eax, eax
0x18000168a  jnz     short loc_1800016BF
0x18000168c  mov     r8, rsi; lpvReserved
0x18000168f  xor     edx, edx; fdwReason
0x180001691  mov     rcx, r14; hinstDLL
0x180001694  call    DllMain
0x180001699  mov     r8, rsi
0x18000169c  xor     edx, edx
0x18000169e  mov     rcx, r14
0x1800016a1  call    dllmain_crt_dispatch
0x1800016a6  mov     rax, cs:_pRawDllMain
0x1800016ad  test    rax, rax
0x1800016b0  jz      short loc_1800016BF
0x1800016b2  mov     r8, rsi
0x1800016b5  xor     edx, edx
0x1800016b7  mov     rcx, r14
0x1800016ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800016bf  test    edi, edi
0x1800016c1  jz      short loc_1800016C8
0x1800016c3  cmp     edi, 3
0x1800016c6  jnz     short loc_180001703
0x1800016c8  mov     r8, rsi
0x1800016cb  mov     edx, edi
0x1800016cd  mov     rcx, r14
0x1800016d0  call    dllmain_crt_dispatch
0x1800016d5  mov     ebx, eax
0x1800016d7  mov     [rsp+58h+var_28], eax
0x1800016db  test    eax, eax
0x1800016dd  jz      short loc_180001703
0x1800016df  mov     rax, cs:_pRawDllMain
0x1800016e6  test    rax, rax
0x1800016e9  jnz     short loc_1800016F0
0x1800016eb  lea     ebx, [rax+1]
0x1800016ee  jmp     short loc_1800016FF
0x1800016f0  mov     r8, rsi
0x1800016f3  mov     edx, edi
0x1800016f5  mov     rcx, r14
0x1800016f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800016fd  mov     ebx, eax
0x1800016ff  mov     [rsp+58h+var_28], ebx
0x180001703  jmp     short loc_18000170B
0x180001705  xor     ebx, ebx
0x180001707  mov     [rsp+58h+var_28], ebx
0x18000170b  mov     eax, ebx
0x18000170d  mov     rbx, [rsp+58h+arg_18]
0x180001712  add     rsp, 40h
0x180001716  pop     r14
0x180001718  pop     rdi
0x180001719  pop     rsi
0x18000171a  retn
0x18000dffc  push    rbp
0x18000dffe  sub     rsp, 30h
0x18000e002  mov     rbp, rdx
0x18000e005  mov     rax, [rcx]
0x18000e008  mov     edx, [rax]
0x18000e00a  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x18000e00f  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x18000e013  lea     r9, dllmain_crt_dispatch; int
0x18000e01a  mov     r8, [rbp+70h]; int
0x18000e01e  mov     edx, [rbp+68h]; int
0x18000e021  mov     rcx, [rbp+60h]; int
0x18000e025  call    __scrt_dllmain_exception_filter
0x18000e02a  nop
0x18000e02b  add     rsp, 30h
0x18000e02f  pop     rbp
0x18000e030  retn
```
