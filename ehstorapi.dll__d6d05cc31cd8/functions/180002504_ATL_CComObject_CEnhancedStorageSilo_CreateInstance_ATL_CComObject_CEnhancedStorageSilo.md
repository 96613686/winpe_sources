# ATL::CComObject<CEnhancedStorageSilo>::CreateInstance(ATL::CComObject<CEnhancedStorageSilo> * *)

- ea: `0x180002504`
- end: `0x1800025d5`
- name: `?CreateInstance@?$CComObject@VCEnhancedStorageSilo@@@ATL@@SAJPEAPEAV12@@Z`
- size: `209`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180002d68`

## callees

- `0x180001264`
- `0x180002008`
- `0x180002504`
- `0x180002d44`
- `0x180003894`
- `0x1800038bc`
- `0x180006a64`
- `0x18000d010`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CEnhancedStorageSilo>::CreateInstance(volatile int **a1)
{
  volatile int **v1; // rsi
  unsigned int v3; // ebx
  void *v4; // rax
  volatile int *v5; // rdi
  int v6; // eax
  CEnhancedStorageSilo *v7; // rcx
  volatile int *v9; // [rsp+50h] [rbp+18h]

  v1 = a1;
  if ( !a1 )
    return 2147500035LL;
  try
  {
    *a1 = 0;
    v3 = -2147024882;
    v4 = operator new(0x60u);
    if ( v4 )
      v5 = (volatile int *)ATL::CComObject<CEnhancedStorageSilo>::CComObject<CEnhancedStorageSilo>(v4);
    else
      v5 = 0;
    v9 = v5;
  }
  catch ( ... )
  {
    v1 = a1;
    v3 = -2147024882;
    v5 = v9;
  }
  if ( v5 )
  {
    ATL::SafeIncrementReferenceMultiThread(v5 + 2);
    v6 = ATL::CComSafeDeleteCriticalSection::Init((ATL::CComSafeDeleteCriticalSection *)(v5 + 4));
    if ( v6 >= 0 )
      v6 = CEnhancedStorageSilo::FinalConstruct(v7);
    v3 = 0;
    if ( v6 < 0 )
      v3 = v6;
    ATL::SafeDecrementReferenceMultiThread(v5 + 2);
    if ( v3 )
    {
      (*(void (__fastcall **)(volatile int *, __int64))(*(_QWORD *)v5 + 64LL))(v5, 1);
      v5 = 0;
    }
    else
    {
      v3 = 0;
    }
  }
  *v1 = v5;
  return v3;
}

```

## disassembly

```asm
0x180002504  mov     [rsp+arg_18], rbx
0x180002509  mov     [rsp+arg_0], rcx
0x18000250e  push    rsi
0x18000250f  push    rdi
0x180002510  push    r14
0x180002512  sub     rsp, 20h
0x180002516  mov     rsi, rcx
0x180002519  test    rcx, rcx
0x18000251c  jnz     short loc_180002528
0x18000251e  mov     eax, 80004003h
0x180002523  jmp     loc_1800025C7
0x180002528  mov     qword ptr [rcx], 0
0x18000252f  mov     ebx, 8007000Eh
0x180002534  mov     [rsp+38h+arg_8], ebx
0x180002538  mov     [rsp+38h+arg_10], 0
0x180002541  mov     ecx, 60h ; '`'; Size
0x180002546  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000254b  test    rax, rax
0x18000254e  jz      short loc_18000255D
0x180002550  mov     rcx, rax
0x180002553  call    ??0?$CComObject@VCEnhancedStorageSilo@@@ATL@@QEAA@PEAX@Z; ATL::CComObject<CEnhancedStorageSilo>::CComObject<CEnhancedStorageSilo>(void *)
0x180002558  mov     rdi, rax
0x18000255b  jmp     short loc_18000255F
0x18000255d  xor     edi, edi
0x18000255f  mov     [rsp+38h+arg_10], rdi
0x180002564  jmp     short loc_180002574
0x180002566  mov     rsi, [rsp+38h+arg_0]
0x18000256b  mov     ebx, [rsp+38h+arg_8]
0x18000256f  mov     rdi, [rsp+38h+arg_10]
0x180002574  test    rdi, rdi
0x180002577  jz      short loc_1800025C2
0x180002579  lea     rcx, [rdi+8]; volatile int *
0x18000257d  call    ?SafeIncrementReferenceMultiThread@ATL@@YAKPECJ@Z; ATL::SafeIncrementReferenceMultiThread(long volatile *)
0x180002582  lea     rcx, [rdi+10h]; this
0x180002586  call    ?Init@CComSafeDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComSafeDeleteCriticalSection::Init(void)
0x18000258b  test    eax, eax
0x18000258d  js      short loc_180002594
0x18000258f  call    ?FinalConstruct@CEnhancedStorageSilo@@QEAAJXZ; CEnhancedStorageSilo::FinalConstruct(void)
0x180002594  xor     ebx, ebx
0x180002596  test    eax, eax
0x180002598  cmovs   ebx, eax
0x18000259b  lea     rcx, [rdi+8]; volatile int *
0x18000259f  call    ?SafeDecrementReferenceMultiThread@ATL@@YAKPECJ@Z; ATL::SafeDecrementReferenceMultiThread(long volatile *)
0x1800025a4  test    ebx, ebx
0x1800025a6  jz      short loc_1800025C0
0x1800025a8  mov     rax, [rdi]
0x1800025ab  mov     edx, 1
0x1800025b0  mov     rcx, rdi
0x1800025b3  mov     rax, [rax+40h]
0x1800025b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800025bc  xor     edi, edi
0x1800025be  jmp     short loc_1800025C2
0x1800025c0  xor     ebx, ebx
0x1800025c2  mov     [rsi], rdi
0x1800025c5  mov     eax, ebx
0x1800025c7  mov     rbx, [rsp+38h+arg_18]
0x1800025cc  add     rsp, 20h
0x1800025d0  pop     r14
0x1800025d2  pop     rdi
0x1800025d3  pop     rsi
0x1800025d4  retn
```
