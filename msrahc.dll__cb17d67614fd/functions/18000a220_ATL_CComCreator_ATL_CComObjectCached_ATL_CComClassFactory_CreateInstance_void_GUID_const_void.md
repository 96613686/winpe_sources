# ATL::CComCreator<ATL::CComObjectCached<ATL::CComClassFactory>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x18000a220`
- end: `0x18000a315`
- name: `?CreateInstance@?$CComCreator@V?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `245`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180001394`
- `0x180008aa8`
- `0x18000a220`
- `0x18000a970`
- `0x18001c010`

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
0x18000a220  mov     [rsp+arg_10], r8
0x18000a225  mov     [rsp+arg_8], rdx
0x18000a22a  mov     [rsp+arg_0], rcx
0x18000a22f  push    rbx
0x18000a230  push    rsi
0x18000a231  push    rdi
0x18000a232  push    r14
0x18000a234  push    r15
0x18000a236  sub     rsp, 30h
0x18000a23a  mov     rsi, r8
0x18000a23d  mov     r15, rdx
0x18000a240  mov     r14, rcx
0x18000a243  test    r8, r8
0x18000a246  jnz     short loc_18000A252
0x18000a248  mov     eax, 80004003h
0x18000a24d  jmp     loc_18000A309
0x18000a252  mov     qword ptr [r8], 0
0x18000a259  mov     edi, 8007000Eh
0x18000a25e  mov     [rsp+58h+arg_18], edi
0x18000a262  mov     [rsp+58h+var_38], 0
0x18000a26b  mov     ecx, 48h ; 'H'; Size
0x18000a270  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000a275  mov     rbx, rax
0x18000a278  test    rbx, rbx
0x18000a27b  jz      short loc_18000A2A2
0x18000a27d  mov     dword ptr [rax+8], 0
0x18000a284  xorps   xmm0, xmm0
0x18000a287  xor     eax, eax
0x18000a289  movups  xmmword ptr [rbx+10h], xmm0
0x18000a28d  movups  xmmword ptr [rbx+20h], xmm0
0x18000a291  mov     [rbx+30h], rax
0x18000a295  mov     [rbx+38h], al
0x18000a298  lea     rax, ??_7?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@6B@; const ATL::CComObjectCached<ATL::CComClassFactory>::`vftable'
0x18000a29f  mov     [rbx], rax
0x18000a2a2  mov     [rsp+58h+var_38], rbx
0x18000a2a7  jmp     short loc_18000A2C1
0x18000a2a9  mov     rsi, [rsp+58h+arg_10]
0x18000a2ae  mov     r15, [rsp+58h+arg_8]
0x18000a2b3  mov     r14, [rsp+58h+arg_0]
0x18000a2b8  mov     edi, [rsp+58h+arg_18]
0x18000a2bc  mov     rbx, [rsp+58h+var_38]
0x18000a2c1  test    rbx, rbx
0x18000a2c4  jz      short loc_18000A307
0x18000a2c6  mov     [rbx+40h], r14
0x18000a2ca  lea     rcx, [rbx+10h]; this
0x18000a2ce  call    ?Init@CComSafeDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComSafeDeleteCriticalSection::Init(void)
0x18000a2d3  xor     ecx, ecx
0x18000a2d5  test    eax, eax
0x18000a2d7  cmovs   ecx, eax
0x18000a2da  xor     edi, edi
0x18000a2dc  test    ecx, ecx
0x18000a2de  cmovs   edi, ecx
0x18000a2e1  test    edi, edi
0x18000a2e3  jnz     short loc_18000A2FF
0x18000a2e5  mov     rax, [rbx]
0x18000a2e8  mov     r8, rsi
0x18000a2eb  mov     rdx, r15
0x18000a2ee  mov     rcx, rbx
0x18000a2f1  mov     rax, [rax]
0x18000a2f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a2f9  mov     edi, eax
0x18000a2fb  test    eax, eax
0x18000a2fd  jz      short loc_18000A307
0x18000a2ff  mov     rcx, rbx
0x18000a302  call    ??_G?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@QEAAPEAXI@Z; ATL::CComObjectCached<ATL::CComClassFactory>::`scalar deleting destructor'(uint)
0x18000a307  mov     eax, edi
0x18000a309  add     rsp, 30h
0x18000a30d  pop     r15
0x18000a30f  pop     r14
0x18000a311  pop     rdi
0x18000a312  pop     rsi
0x18000a313  pop     rbx
0x18000a314  retn
```
