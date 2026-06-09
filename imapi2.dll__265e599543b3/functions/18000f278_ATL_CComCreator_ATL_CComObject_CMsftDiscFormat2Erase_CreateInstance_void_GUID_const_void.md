# ATL::CComCreator<ATL::CComObject<CMsftDiscFormat2Erase>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x18000f278`
- end: `0x18000f32e`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCMsftDiscFormat2Erase@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `182`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18000f250`

## callees

- `0x180005fa4`
- `0x18000ea44`
- `0x18000ee90`
- `0x18000f278`
- `0x18000fdd4`
- `0x180024d68`
- `0x18004a010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObject<CMsftDiscFormat2Erase>>::CreateInstance(
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
  v7 = operator new(0xD8u);
  if ( v7 )
  {
    v8 = ATL::CComObject<CMsftDiscFormat2Erase>::CComObject<CMsftDiscFormat2Erase>(v7);
    v9 = (volatile int *)v8;
    if ( v8 )
    {
      ATL::SafeIncrementReferenceMultiThread((volatile int *)(v8 + 104));
      v10 = ATL::CComSafeDeleteCriticalSection::Init((ATL::CComSafeDeleteCriticalSection *)(v9 + 28));
      v11 = 0;
      if ( v10 < 0 )
        v11 = v10;
      v6 = 0;
      if ( v11 < 0 )
        v6 = v11;
      ATL::SafeDecrementReferenceMultiThread(v9 + 26);
      if ( v6 || (v6 = (**(__int64 (__fastcall ***)(volatile int *, __int64, _QWORD *))v9)(v9, a2, a3)) != 0 )
        (*(void (__fastcall **)(volatile int *, __int64))(*(_QWORD *)v9 + 168LL))(v9, 1);
    }
  }
  return v6;
}

```

## disassembly

```asm
0x18000f278  push    rbx
0x18000f27a  push    rbp
0x18000f27b  push    rsi
0x18000f27c  push    rdi
0x18000f27d  push    r14
0x18000f27f  sub     rsp, 20h
0x18000f283  mov     r14, r8
0x18000f286  mov     rbp, rdx
0x18000f289  test    r8, r8
0x18000f28c  jnz     short loc_18000F298
0x18000f28e  mov     eax, 80004003h
0x18000f293  jmp     loc_18000F323
0x18000f298  mov     ecx, 0D8h; Size
0x18000f29d  mov     qword ptr [r8], 0
0x18000f2a4  mov     esi, 8007000Eh
0x18000f2a9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000f2ae  test    rax, rax
0x18000f2b1  jz      short loc_18000F321
0x18000f2b3  mov     rcx, rax
0x18000f2b6  call    ??0?$CComObject@VCMsftDiscFormat2Erase@@@ATL@@QEAA@PEAX@Z; ATL::CComObject<CMsftDiscFormat2Erase>::CComObject<CMsftDiscFormat2Erase>(void *)
0x18000f2bb  mov     rdi, rax
0x18000f2be  test    rax, rax
0x18000f2c1  jz      short loc_18000F321
0x18000f2c3  lea     rcx, [rax+68h]; volatile int *
0x18000f2c7  call    ?SafeIncrementReferenceMultiThread@ATL@@YAKPECJ@Z; ATL::SafeIncrementReferenceMultiThread(long volatile *)
0x18000f2cc  lea     rcx, [rdi+70h]; this
0x18000f2d0  call    ?Init@CComSafeDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComSafeDeleteCriticalSection::Init(void)
0x18000f2d5  xor     edx, edx
0x18000f2d7  lea     rcx, [rdi+68h]; volatile int *
0x18000f2db  test    eax, eax
0x18000f2dd  cmovs   edx, eax
0x18000f2e0  xor     esi, esi
0x18000f2e2  test    edx, edx
0x18000f2e4  cmovs   esi, edx
0x18000f2e7  call    ?SafeDecrementReferenceMultiThread@ATL@@YAKPECJ@Z; ATL::SafeDecrementReferenceMultiThread(long volatile *)
0x18000f2ec  test    esi, esi
0x18000f2ee  jnz     short loc_18000F30A
0x18000f2f0  mov     rax, [rdi]
0x18000f2f3  mov     r8, r14
0x18000f2f6  mov     rdx, rbp
0x18000f2f9  mov     rcx, rdi
0x18000f2fc  mov     rax, [rax]
0x18000f2ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f304  mov     esi, eax
0x18000f306  test    eax, eax
0x18000f308  jz      short loc_18000F321
0x18000f30a  mov     rcx, [rdi]
0x18000f30d  mov     edx, 1
0x18000f312  mov     rax, [rcx+0A8h]
0x18000f319  mov     rcx, rdi
0x18000f31c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f321  mov     eax, esi
0x18000f323  add     rsp, 20h
0x18000f327  pop     r14
0x18000f329  pop     rdi
0x18000f32a  pop     rsi
0x18000f32b  pop     rbp
0x18000f32c  pop     rbx
0x18000f32d  retn
```
