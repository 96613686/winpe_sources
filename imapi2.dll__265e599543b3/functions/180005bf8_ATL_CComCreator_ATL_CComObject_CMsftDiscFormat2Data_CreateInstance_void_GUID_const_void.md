# ATL::CComCreator<ATL::CComObject<CMsftDiscFormat2Data>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180005bf8`
- end: `0x180005cae`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCMsftDiscFormat2Data@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `182`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180005bd0`

## callees

- `0x180005bf8`
- `0x180005fa4`
- `0x180005fc8`
- `0x18000ea44`
- `0x18000ee90`
- `0x18000fdd4`
- `0x18004a010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObject<CMsftDiscFormat2Data>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  unsigned int v6; // esi
  void *v7; // rax
  __int64 v8; // rax
  volatile int *v9; // rdi
  int v10; // eax
  int v11; // edx

  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  v6 = -2147024882;
  v7 = operator new(0x108u);
  if ( v7 )
  {
    v8 = ATL::CComObject<CMsftDiscFormat2Data>::CComObject<CMsftDiscFormat2Data>(v7);
    v9 = (volatile int *)v8;
    if ( v8 )
    {
      ATL::SafeIncrementReferenceMultiThread((volatile int *)(v8 + 112));
      v10 = ATL::CComSafeDeleteCriticalSection::Init((ATL::CComSafeDeleteCriticalSection *)(v9 + 30));
      v11 = 0;
      if ( v10 < 0 )
        v11 = v10;
      v6 = 0;
      if ( v11 < 0 )
        v6 = v11;
      ATL::SafeDecrementReferenceMultiThread(v9 + 28);
      if ( v6 || (v6 = (**(__int64 (__fastcall ***)(volatile int *, __int64, _QWORD *))v9)(v9, a2, a3)) != 0 )
        (*(void (__fastcall **)(volatile int *, __int64))(*(_QWORD *)v9 + 368LL))(v9, 1);
    }
  }
  return v6;
}

```

## disassembly

```asm
0x180005bf8  push    rbx
0x180005bfa  push    rbp
0x180005bfb  push    rsi
0x180005bfc  push    rdi
0x180005bfd  push    r14
0x180005bff  sub     rsp, 20h
0x180005c03  mov     r14, r8
0x180005c06  mov     rbp, rdx
0x180005c09  test    r8, r8
0x180005c0c  jnz     short loc_180005C18
0x180005c0e  mov     eax, 80004003h
0x180005c13  jmp     loc_180005CA3
0x180005c18  mov     ecx, 108h; Size
0x180005c1d  mov     qword ptr [r8], 0
0x180005c24  mov     esi, 8007000Eh
0x180005c29  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180005c2e  test    rax, rax
0x180005c31  jz      short loc_180005CA1
0x180005c33  mov     rcx, rax
0x180005c36  call    ??0?$CComObject@VCMsftDiscFormat2Data@@@ATL@@QEAA@PEAX@Z; ATL::CComObject<CMsftDiscFormat2Data>::CComObject<CMsftDiscFormat2Data>(void *)
0x180005c3b  mov     rdi, rax
0x180005c3e  test    rax, rax
0x180005c41  jz      short loc_180005CA1
0x180005c43  lea     rcx, [rax+70h]; volatile int *
0x180005c47  call    ?SafeIncrementReferenceMultiThread@ATL@@YAKPECJ@Z; ATL::SafeIncrementReferenceMultiThread(long volatile *)
0x180005c4c  lea     rcx, [rdi+78h]; this
0x180005c50  call    ?Init@CComSafeDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComSafeDeleteCriticalSection::Init(void)
0x180005c55  xor     edx, edx
0x180005c57  lea     rcx, [rdi+70h]; volatile int *
0x180005c5b  test    eax, eax
0x180005c5d  cmovs   edx, eax
0x180005c60  xor     esi, esi
0x180005c62  test    edx, edx
0x180005c64  cmovs   esi, edx
0x180005c67  call    ?SafeDecrementReferenceMultiThread@ATL@@YAKPECJ@Z; ATL::SafeDecrementReferenceMultiThread(long volatile *)
0x180005c6c  test    esi, esi
0x180005c6e  jnz     short loc_180005C8A
0x180005c70  mov     rax, [rdi]
0x180005c73  mov     r8, r14
0x180005c76  mov     rdx, rbp
0x180005c79  mov     rcx, rdi
0x180005c7c  mov     rax, [rax]
0x180005c7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005c84  mov     esi, eax
0x180005c86  test    eax, eax
0x180005c88  jz      short loc_180005CA1
0x180005c8a  mov     rcx, [rdi]
0x180005c8d  mov     edx, 1
0x180005c92  mov     rax, [rcx+170h]
0x180005c99  mov     rcx, rdi
0x180005c9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005ca1  mov     eax, esi
0x180005ca3  add     rsp, 20h
0x180005ca7  pop     r14
0x180005ca9  pop     rdi
0x180005caa  pop     rsi
0x180005cab  pop     rbp
0x180005cac  pop     rbx
0x180005cad  retn
```
