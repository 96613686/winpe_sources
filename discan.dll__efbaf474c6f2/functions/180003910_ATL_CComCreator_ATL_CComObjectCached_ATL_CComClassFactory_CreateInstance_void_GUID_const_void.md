# ATL::CComCreator<ATL::CComObjectCached<ATL::CComClassFactory>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180003910`
- end: `0x180003a0f`
- name: `?CreateInstance@?$CComCreator@V?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `255`
- prototype: `__int64 __fastcall(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD), __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180001b78`
- `0x180003458`
- `0x180003910`
- `0x180004a4c`
- `0x180039010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObjectCached<ATL::CComClassFactory>>::CreateInstance(
        __int64 (__fastcall **a1)(_QWORD, _QWORD, _QWORD),
        __int64 a2,
        _QWORD *a3)
{
  _QWORD *v3; // rsi
  __int64 v4; // r15
  __int64 (__fastcall **v5)(_QWORD, _QWORD, _QWORD); // r14
  unsigned int v7; // edi
  _BYTE *v8; // rax
  _BYTE *v9; // rbx
  int v10; // ecx
  int v11; // eax
  _BYTE *v12; // [rsp+20h] [rbp-38h]

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
      *((_QWORD *)v8 + 6) = 0;
      v8[56] = 0;
      *(_QWORD *)v8 = &ATL::CComObjectCached<ATL::CComClassFactory>::`vftable';
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
    *((_QWORD *)v9 + 8) = v5;
    v10 = ATL::CComCriticalSection::Init((ATL::CComCriticalSection *)(v9 + 16));
    if ( v10 >= 0 )
      v9[56] = 1;
    v11 = 0;
    if ( v10 < 0 )
      v11 = v10;
    v7 = 0;
    if ( v11 < 0 )
      v7 = v11;
    if ( v7 || (v7 = (**(__int64 (__fastcall ***)(_BYTE *, __int64, _QWORD *))v9)(v9, v4, v3)) != 0 )
      ATL::CComObjectCached<ATL::CComClassFactory>::`scalar deleting destructor'(v9);
  }
  return v7;
}

```

## disassembly

```asm
0x180003910  mov     [rsp+arg_10], r8
0x180003915  mov     [rsp+arg_8], rdx
0x18000391a  mov     [rsp+arg_0], rcx
0x18000391f  push    rbx
0x180003920  push    rsi
0x180003921  push    rdi
0x180003922  push    r14
0x180003924  push    r15
0x180003926  sub     rsp, 30h
0x18000392a  mov     rsi, r8
0x18000392d  mov     r15, rdx
0x180003930  mov     r14, rcx
0x180003933  test    r8, r8
0x180003936  jnz     short loc_180003942
0x180003938  mov     eax, 80004003h
0x18000393d  jmp     loc_180003A03
0x180003942  mov     qword ptr [r8], 0
0x180003949  mov     edi, 8007000Eh
0x18000394e  mov     [rsp+58h+arg_18], edi
0x180003952  mov     [rsp+58h+var_38], 0
0x18000395b  mov     ecx, 48h ; 'H'; Size
0x180003960  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180003965  mov     rbx, rax
0x180003968  test    rbx, rbx
0x18000396b  jz      short loc_180003992
0x18000396d  mov     dword ptr [rax+8], 0
0x180003974  xorps   xmm0, xmm0
0x180003977  xor     eax, eax
0x180003979  movups  xmmword ptr [rbx+10h], xmm0
0x18000397d  movups  xmmword ptr [rbx+20h], xmm0
0x180003981  mov     [rbx+30h], rax
0x180003985  mov     [rbx+38h], al
0x180003988  lea     rax, ??_7?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@6B@; const ATL::CComObjectCached<ATL::CComClassFactory>::`vftable'
0x18000398f  mov     [rbx], rax
0x180003992  mov     [rsp+58h+var_38], rbx
0x180003997  jmp     short loc_1800039B1
0x180003999  mov     rsi, [rsp+58h+arg_10]
0x18000399e  mov     r15, [rsp+58h+arg_8]
0x1800039a3  mov     r14, [rsp+58h+arg_0]
0x1800039a8  mov     edi, [rsp+58h+arg_18]
0x1800039ac  mov     rbx, [rsp+58h+var_38]
0x1800039b1  test    rbx, rbx
0x1800039b4  jz      short loc_180003A01
0x1800039b6  mov     [rbx+40h], r14
0x1800039ba  lea     rcx, [rbx+10h]; this
0x1800039be  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x1800039c3  mov     ecx, eax
0x1800039c5  test    eax, eax
0x1800039c7  js      short loc_1800039CD
0x1800039c9  mov     byte ptr [rbx+38h], 1
0x1800039cd  xor     eax, eax
0x1800039cf  test    ecx, ecx
0x1800039d1  cmovs   eax, ecx
0x1800039d4  xor     edi, edi
0x1800039d6  test    eax, eax
0x1800039d8  cmovs   edi, eax
0x1800039db  test    edi, edi
0x1800039dd  jnz     short loc_1800039F9
0x1800039df  mov     rax, [rbx]
0x1800039e2  mov     r8, rsi
0x1800039e5  mov     rdx, r15
0x1800039e8  mov     rcx, rbx
0x1800039eb  mov     rax, [rax]
0x1800039ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800039f3  mov     edi, eax
0x1800039f5  test    eax, eax
0x1800039f7  jz      short loc_180003A01
0x1800039f9  mov     rcx, rbx; Block
0x1800039fc  call    ??_G?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@QEAAPEAXI@Z; ATL::CComObjectCached<ATL::CComClassFactory>::`scalar deleting destructor'(uint)
0x180003a01  mov     eax, edi
0x180003a03  add     rsp, 30h
0x180003a07  pop     r15
0x180003a09  pop     r14
0x180003a0b  pop     rdi
0x180003a0c  pop     rsi
0x180003a0d  pop     rbx
0x180003a0e  retn
```
