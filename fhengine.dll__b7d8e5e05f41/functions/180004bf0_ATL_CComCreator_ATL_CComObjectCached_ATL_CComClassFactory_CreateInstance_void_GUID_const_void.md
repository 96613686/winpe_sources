# ATL::CComCreator<ATL::CComObjectCached<ATL::CComClassFactory>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180004bf0`
- end: `0x180004ce5`
- name: `?CreateInstance@?$CComCreator@V?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `245`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180001a5c`
- `0x1800036c8`
- `0x180004bf0`
- `0x180004f34`
- `0x180034010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObjectCached<ATL::CComClassFactory>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  _QWORD *v3; // rsi
  __int64 v4; // r15
  __int64 v5; // r14
  unsigned int v7; // edi
  _QWORD *v8; // rax
  _QWORD *v9; // rbx
  int v10; // eax
  int v11; // ecx
  _QWORD *v12; // [rsp+20h] [rbp-38h]

  v3 = a3;
  v4 = a2;
  v5 = a1;
  if ( !a3 )
    return 2147500035LL;
  try
  {
    *a3 = 0;
    v7 = -2147024882;
    v8 = operator new(0x48u);
    v9 = v8;
    if ( v8 )
    {
      *((_DWORD *)v8 + 2) = 0;
      *((_OWORD *)v8 + 1) = 0;
      *((_OWORD *)v8 + 2) = 0;
      v8[6] = 0;
      *((_BYTE *)v8 + 56) = 0;
      *v8 = &ATL::CComObjectCached<ATL::CComClassFactory>::`vftable';
    }
    v12 = v8;
  }
  catch ( ... )
  {
    v3 = a3;
    v4 = a2;
    v5 = a1;
    v7 = -2147024882;
    v9 = v12;
  }
  if ( v9 )
  {
    v9[8] = v5;
    v10 = ATL::CComSafeDeleteCriticalSection::Init((ATL::CComSafeDeleteCriticalSection *)(v9 + 2));
    v11 = 0;
    if ( v10 < 0 )
      v11 = v10;
    v7 = 0;
    if ( v11 < 0 )
      v7 = v11;
    if ( v7 || (v7 = (*(__int64 (__fastcall **)(_QWORD *, __int64, _QWORD *))*v9)(v9, v4, v3)) != 0 )
      ATL::CComObjectCached<ATL::CComClassFactory>::`scalar deleting destructor'(v9);
  }
  return v7;
}

```

## disassembly

```asm
0x180004bf0  mov     [rsp+arg_10], r8
0x180004bf5  mov     [rsp+arg_8], rdx
0x180004bfa  mov     [rsp+arg_0], rcx
0x180004bff  push    rbx
0x180004c00  push    rsi
0x180004c01  push    rdi
0x180004c02  push    r14
0x180004c04  push    r15
0x180004c06  sub     rsp, 30h
0x180004c0a  mov     rsi, r8
0x180004c0d  mov     r15, rdx
0x180004c10  mov     r14, rcx
0x180004c13  test    r8, r8
0x180004c16  jnz     short loc_180004C22
0x180004c18  mov     eax, 80004003h
0x180004c1d  jmp     loc_180004CD9
0x180004c22  mov     qword ptr [r8], 0
0x180004c29  mov     edi, 8007000Eh
0x180004c2e  mov     [rsp+58h+arg_18], edi
0x180004c32  mov     [rsp+58h+var_38], 0
0x180004c3b  mov     ecx, 48h ; 'H'; Size
0x180004c40  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180004c45  mov     rbx, rax
0x180004c48  test    rbx, rbx
0x180004c4b  jz      short loc_180004C72
0x180004c4d  mov     dword ptr [rax+8], 0
0x180004c54  xorps   xmm0, xmm0
0x180004c57  xor     eax, eax
0x180004c59  movups  xmmword ptr [rbx+10h], xmm0
0x180004c5d  movups  xmmword ptr [rbx+20h], xmm0
0x180004c61  mov     [rbx+30h], rax
0x180004c65  mov     [rbx+38h], al
0x180004c68  lea     rax, ??_7?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@6B@; const ATL::CComObjectCached<ATL::CComClassFactory>::`vftable'
0x180004c6f  mov     [rbx], rax
0x180004c72  mov     [rsp+58h+var_38], rbx
0x180004c77  jmp     short loc_180004C91
0x180004c79  mov     rsi, [rsp+58h+arg_10]
0x180004c7e  mov     r15, [rsp+58h+arg_8]
0x180004c83  mov     r14, [rsp+58h+arg_0]
0x180004c88  mov     edi, [rsp+58h+arg_18]
0x180004c8c  mov     rbx, [rsp+58h+var_38]
0x180004c91  test    rbx, rbx
0x180004c94  jz      short loc_180004CD7
0x180004c96  mov     [rbx+40h], r14
0x180004c9a  lea     rcx, [rbx+10h]; this
0x180004c9e  call    ?Init@CComSafeDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComSafeDeleteCriticalSection::Init(void)
0x180004ca3  xor     ecx, ecx
0x180004ca5  test    eax, eax
0x180004ca7  cmovs   ecx, eax
0x180004caa  xor     edi, edi
0x180004cac  test    ecx, ecx
0x180004cae  cmovs   edi, ecx
0x180004cb1  test    edi, edi
0x180004cb3  jnz     short loc_180004CCF
0x180004cb5  mov     rax, [rbx]
0x180004cb8  mov     r8, rsi
0x180004cbb  mov     rdx, r15
0x180004cbe  mov     rcx, rbx
0x180004cc1  mov     rax, [rax]
0x180004cc4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004cc9  mov     edi, eax
0x180004ccb  test    eax, eax
0x180004ccd  jz      short loc_180004CD7
0x180004ccf  mov     rcx, rbx
0x180004cd2  call    ??_G?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@QEAAPEAXI@Z; ATL::CComObjectCached<ATL::CComClassFactory>::`scalar deleting destructor'(uint)
0x180004cd7  mov     eax, edi
0x180004cd9  add     rsp, 30h
0x180004cdd  pop     r15
0x180004cdf  pop     r14
0x180004ce1  pop     rdi
0x180004ce2  pop     rsi
0x180004ce3  pop     rbx
0x180004ce4  retn
```
