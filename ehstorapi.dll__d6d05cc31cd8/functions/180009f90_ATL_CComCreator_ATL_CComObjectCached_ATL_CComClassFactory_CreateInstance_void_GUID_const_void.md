# ATL::CComCreator<ATL::CComObjectCached<ATL::CComClassFactory>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180009f90`
- end: `0x18000a085`
- name: `?CreateInstance@?$CComCreator@V?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `245`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180001264`
- `0x180002d44`
- `0x180008db8`
- `0x180009f90`
- `0x18000d010`

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
0x180009f90  mov     [rsp+arg_10], r8
0x180009f95  mov     [rsp+arg_8], rdx
0x180009f9a  mov     [rsp+arg_0], rcx
0x180009f9f  push    rbx
0x180009fa0  push    rsi
0x180009fa1  push    rdi
0x180009fa2  push    r14
0x180009fa4  push    r15
0x180009fa6  sub     rsp, 30h
0x180009faa  mov     rsi, r8
0x180009fad  mov     r15, rdx
0x180009fb0  mov     r14, rcx
0x180009fb3  test    r8, r8
0x180009fb6  jnz     short loc_180009FC2
0x180009fb8  mov     eax, 80004003h
0x180009fbd  jmp     loc_18000A079
0x180009fc2  mov     qword ptr [r8], 0
0x180009fc9  mov     edi, 8007000Eh
0x180009fce  mov     [rsp+58h+arg_18], edi
0x180009fd2  mov     [rsp+58h+var_38], 0
0x180009fdb  mov     ecx, 48h ; 'H'; Size
0x180009fe0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180009fe5  mov     rbx, rax
0x180009fe8  test    rbx, rbx
0x180009feb  jz      short loc_18000A012
0x180009fed  mov     dword ptr [rax+8], 0
0x180009ff4  xorps   xmm0, xmm0
0x180009ff7  xor     eax, eax
0x180009ff9  movups  xmmword ptr [rbx+10h], xmm0
0x180009ffd  movups  xmmword ptr [rbx+20h], xmm0
0x18000a001  mov     [rbx+30h], rax
0x18000a005  mov     [rbx+38h], al
0x18000a008  lea     rax, ??_7?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@6B@; const ATL::CComObjectCached<ATL::CComClassFactory>::`vftable'
0x18000a00f  mov     [rbx], rax
0x18000a012  mov     [rsp+58h+var_38], rbx
0x18000a017  jmp     short loc_18000A031
0x18000a019  mov     rsi, [rsp+58h+arg_10]
0x18000a01e  mov     r15, [rsp+58h+arg_8]
0x18000a023  mov     r14, [rsp+58h+arg_0]
0x18000a028  mov     edi, [rsp+58h+arg_18]
0x18000a02c  mov     rbx, [rsp+58h+var_38]
0x18000a031  test    rbx, rbx
0x18000a034  jz      short loc_18000A077
0x18000a036  mov     [rbx+40h], r14
0x18000a03a  lea     rcx, [rbx+10h]; this
0x18000a03e  call    ?Init@CComSafeDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComSafeDeleteCriticalSection::Init(void)
0x18000a043  xor     ecx, ecx
0x18000a045  test    eax, eax
0x18000a047  cmovs   ecx, eax
0x18000a04a  xor     edi, edi
0x18000a04c  test    ecx, ecx
0x18000a04e  cmovs   edi, ecx
0x18000a051  test    edi, edi
0x18000a053  jnz     short loc_18000A06F
0x18000a055  mov     rax, [rbx]
0x18000a058  mov     r8, rsi
0x18000a05b  mov     rdx, r15
0x18000a05e  mov     rcx, rbx
0x18000a061  mov     rax, [rax]
0x18000a064  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a069  mov     edi, eax
0x18000a06b  test    eax, eax
0x18000a06d  jz      short loc_18000A077
0x18000a06f  mov     rcx, rbx; Block
0x18000a072  call    ??_G?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@QEAAPEAXI@Z; ATL::CComObjectCached<ATL::CComClassFactory>::`scalar deleting destructor'(uint)
0x18000a077  mov     eax, edi
0x18000a079  add     rsp, 30h
0x18000a07d  pop     r15
0x18000a07f  pop     r14
0x18000a081  pop     rdi
0x18000a082  pop     rsi
0x18000a083  pop     rbx
0x18000a084  retn
```
