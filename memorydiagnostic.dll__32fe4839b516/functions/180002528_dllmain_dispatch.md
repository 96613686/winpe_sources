# dllmain_dispatch

- ea: `0x180002528`
- end: `0x180002658`
- name: `dllmain_dispatch`
- size: `304`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180002660`

## callees

- `0x180002330`
- `0x180002528`
- `0x180002820`
- `0x18001f3c8`
- `0x180024010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_180030490 <= 0 )
    return 0;
  if ( fdwReason - 1 > 1
    || (!pRawDllMain || (v7 = ((__int64 (*)(void))pRawDllMain)()) != 0)
    && (v7 = dllmain_crt_dispatch(hinstDLL, fdwReason, lpvReserved)) != 0 )
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
      JUMPOUT(0x180002606LL);
  }
  return v7;
}

```

## disassembly

```asm
0x180002528  mov     rax, rsp
0x18000252b  mov     [rax+20h], rbx
0x18000252f  mov     [rax+18h], r8
0x180002533  mov     [rax+10h], edx
0x180002536  mov     [rax+8], rcx
0x18000253a  push    rsi
0x18000253b  push    rdi
0x18000253c  push    r14
0x18000253e  sub     rsp, 40h
0x180002542  mov     rsi, r8
0x180002545  mov     edi, edx
0x180002547  mov     r14, rcx
0x18000254a  test    edx, edx
0x18000254c  jnz     short loc_18000255D
0x18000254e  cmp     cs:dword_180030490, edx
0x180002554  jg      short loc_18000255D
0x180002556  xor     eax, eax
0x180002558  jmp     loc_18000264A
0x18000255d  lea     eax, [rdx-1]
0x180002560  cmp     eax, 1
0x180002563  ja      short loc_1800025A9
0x180002565  mov     rax, cs:_pRawDllMain
0x18000256c  test    rax, rax
0x18000256f  jnz     short loc_18000257B
0x180002571  mov     [rsp+58h+var_28], 1
0x180002579  jmp     short loc_18000258E
0x18000257b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002580  mov     ebx, eax
0x180002582  mov     [rsp+58h+var_28], eax
0x180002586  test    eax, eax
0x180002588  jz      loc_180002640
0x18000258e  mov     r8, rsi
0x180002591  mov     edx, edi
0x180002593  mov     rcx, r14
0x180002596  call    dllmain_crt_dispatch
0x18000259b  mov     ebx, eax
0x18000259d  mov     [rsp+58h+var_28], eax
0x1800025a1  test    eax, eax
0x1800025a3  jz      loc_180002640
0x1800025a9  mov     r8, rsi; lpvReserved
0x1800025ac  mov     edx, edi; fdwReason
0x1800025ae  mov     rcx, r14; hinstDLL
0x1800025b1  call    DllMain
0x1800025b6  mov     ebx, eax
0x1800025b8  mov     [rsp+58h+var_28], eax
0x1800025bc  cmp     edi, 1
0x1800025bf  jnz     short loc_1800025F8
0x1800025c1  test    eax, eax
0x1800025c3  jnz     short loc_1800025F8
0x1800025c5  mov     r8, rsi; lpvReserved
0x1800025c8  xor     edx, edx; fdwReason
0x1800025ca  mov     rcx, r14; hinstDLL
0x1800025cd  call    DllMain
0x1800025d2  mov     r8, rsi
0x1800025d5  xor     edx, edx
0x1800025d7  mov     rcx, r14
0x1800025da  call    dllmain_crt_dispatch
0x1800025df  mov     rax, cs:_pRawDllMain
0x1800025e6  test    rax, rax
0x1800025e9  jz      short loc_1800025F8
0x1800025eb  mov     r8, rsi
0x1800025ee  xor     edx, edx
0x1800025f0  mov     rcx, r14
0x1800025f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800025f8  test    edi, edi
0x1800025fa  jz      short loc_180002601
0x1800025fc  cmp     edi, 3
0x1800025ff  jnz     short loc_180002640
0x180002601  mov     r8, rsi
0x180002604  mov     edx, edi
0x180002607  mov     ecx, esi
0x180002609  call    dllmain_crt_dispatch
0x18000260e  mov     ebx, eax
0x180002610  mov     [rsp+58h+var_28], eax
0x180002614  test    eax, eax
0x180002616  jz      short loc_180002640
0x180002618  mov     rax, cs:_pRawDllMain
0x18000261f  test    rax, rax
0x180002622  jnz     short loc_18000262D
0x180002624  lea     ebx, [rax+1]
0x180002627  mov     [rsp+58h+var_28], ebx
0x18000262b  jmp     short loc_180002640
0x18000262d  mov     r8, rsi
0x180002630  mov     edx, edi
0x180002632  mov     rcx, r14
0x180002635  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000263a  mov     ebx, eax
0x18000263c  mov     [rsp+58h+var_28], eax
0x180002640  jmp     short loc_180002648
0x180002642  xor     ebx, ebx
0x180002644  mov     [rsp+58h+var_28], ebx
0x180002648  mov     eax, ebx
0x18000264a  mov     rbx, [rsp+58h+arg_18]
0x18000264f  add     rsp, 40h
0x180002653  pop     r14
0x180002655  pop     rdi
0x180002656  pop     rsi
0x180002657  retn
0x1800220cc  push    rbp
0x1800220ce  sub     rsp, 30h
0x1800220d2  mov     rbp, rdx
0x1800220d5  mov     rax, [rcx]
0x1800220d8  mov     edx, [rax]
0x1800220da  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x1800220df  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x1800220e3  lea     r9, dllmain_crt_dispatch; int
0x1800220ea  mov     r8, [rbp+70h]; int
0x1800220ee  mov     edx, [rbp+68h]; int
0x1800220f1  mov     rcx, [rbp+60h]; int
0x1800220f5  call    __scrt_dllmain_exception_filter
0x1800220fa  nop
0x1800220fb  add     rsp, 30h
0x1800220ff  pop     rbp
0x180022100  retn
```
