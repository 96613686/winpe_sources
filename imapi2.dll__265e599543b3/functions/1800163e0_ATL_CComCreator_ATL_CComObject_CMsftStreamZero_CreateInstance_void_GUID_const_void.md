# ATL::CComCreator<ATL::CComObject<CMsftStreamZero>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x1800163e0`
- end: `0x180016496`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCMsftStreamZero@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `182`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1800162f0`

## callees

- `0x180005fa4`
- `0x18000ea44`
- `0x18000ee90`
- `0x18000fdd4`
- `0x180015f90`
- `0x1800163e0`
- `0x18004a010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObject<CMsftStreamZero>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  unsigned int v6; // edi
  void *v7; // rax
  __int64 v8; // rax
  __int64 v9; // rbx
  int v10; // eax

  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  v6 = -2147024882;
  v7 = operator new(0x70u);
  if ( v7 )
  {
    v8 = ATL::CComObject<CMsftStreamZero>::CComObject<CMsftStreamZero>(v7);
    v9 = v8;
    if ( v8 )
    {
      ATL::SafeIncrementReferenceMultiThread((volatile int *)(v8 + 56));
      v10 = ATL::CComSafeDeleteCriticalSection::Init((ATL::CComSafeDeleteCriticalSection *)(v9 + 64));
      if ( v10 >= 0 )
      {
        *(_BYTE *)(v9 + 48) = 1;
        v10 = 0;
      }
      v6 = 0;
      if ( v10 < 0 )
        v6 = v10;
      ATL::SafeDecrementReferenceMultiThread((volatile int *)(v9 + 56));
      if ( v6 || (v6 = (**(__int64 (__fastcall ***)(__int64, __int64, _QWORD *))v9)(v9, a2, a3)) != 0 )
        (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v9 + 112LL))(v9, 1);
    }
  }
  return v6;
}

```

## disassembly

```asm
0x1800163e0  push    rbx
0x1800163e2  push    rbp
0x1800163e3  push    rsi
0x1800163e4  push    rdi
0x1800163e5  push    r14
0x1800163e7  sub     rsp, 20h
0x1800163eb  mov     rsi, r8
0x1800163ee  mov     r14, rdx
0x1800163f1  test    r8, r8
0x1800163f4  jnz     short loc_180016400
0x1800163f6  mov     eax, 80004003h
0x1800163fb  jmp     loc_18001648B
0x180016400  mov     ecx, 70h ; 'p'; Size
0x180016405  mov     qword ptr [r8], 0
0x18001640c  mov     edi, 8007000Eh
0x180016411  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180016416  test    rax, rax
0x180016419  jz      short loc_180016489
0x18001641b  mov     rcx, rax
0x18001641e  call    ??0?$CComObject@VCMsftStreamZero@@@ATL@@QEAA@PEAX@Z; ATL::CComObject<CMsftStreamZero>::CComObject<CMsftStreamZero>(void *)
0x180016423  mov     rbx, rax
0x180016426  test    rax, rax
0x180016429  jz      short loc_180016489
0x18001642b  lea     rcx, [rax+38h]; volatile int *
0x18001642f  call    ?SafeIncrementReferenceMultiThread@ATL@@YAKPECJ@Z; ATL::SafeIncrementReferenceMultiThread(long volatile *)
0x180016434  lea     rcx, [rbx+40h]; this
0x180016438  call    ?Init@CComSafeDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComSafeDeleteCriticalSection::Init(void)
0x18001643d  test    eax, eax
0x18001643f  js      short loc_180016447
0x180016441  mov     byte ptr [rbx+30h], 1
0x180016445  xor     eax, eax
0x180016447  xor     edi, edi
0x180016449  lea     rcx, [rbx+38h]; volatile int *
0x18001644d  test    eax, eax
0x18001644f  cmovs   edi, eax
0x180016452  call    ?SafeDecrementReferenceMultiThread@ATL@@YAKPECJ@Z; ATL::SafeDecrementReferenceMultiThread(long volatile *)
0x180016457  test    edi, edi
0x180016459  jnz     short loc_180016475
0x18001645b  mov     rax, [rbx]
0x18001645e  mov     r8, rsi
0x180016461  mov     rdx, r14
0x180016464  mov     rcx, rbx
0x180016467  mov     rax, [rax]
0x18001646a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001646f  mov     edi, eax
0x180016471  test    eax, eax
0x180016473  jz      short loc_180016489
0x180016475  mov     rcx, [rbx]
0x180016478  mov     edx, 1
0x18001647d  mov     rax, [rcx+70h]
0x180016481  mov     rcx, rbx
0x180016484  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016489  mov     eax, edi
0x18001648b  add     rsp, 20h
0x18001648f  pop     r14
0x180016491  pop     rdi
0x180016492  pop     rsi
0x180016493  pop     rbp
0x180016494  pop     rbx
0x180016495  retn
```
