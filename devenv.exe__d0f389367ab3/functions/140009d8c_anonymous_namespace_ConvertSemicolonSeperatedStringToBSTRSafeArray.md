# _anonymous_namespace_::ConvertSemicolonSeperatedStringToBSTRSafeArray

- ea: `0x140009d8c`
- end: `0x140009f9a`
- name: `_anonymous_namespace_::ConvertSemicolonSeperatedStringToBSTRSafeArray`
- size: `526`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x140005b70`

## callees

- `0x140001020`
- `0x140003160`
- `0x140009d8c`
- `0x140010138`
- `0x140010e44`
- `0x1400339e0`
- `0x140033ab0`
- `0x14003b9dc`

## import_xrefs

- `OLEAUT32!__imp_SysAllocStringLen` at `0x140009e6c`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x140009e6c`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x140009de2`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x140009e99`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x140009de2`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x140009e99`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x140009ecc`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x140009ecc`
- `OLEAUT32!__imp_SafeArrayLock` at `0x140009df3`
- `OLEAUT32!__imp_SafeArrayLock` at `0x140009eae`
- `OLEAUT32!__imp_SafeArrayLock` at `0x140009f25`
- `OLEAUT32!__imp_SafeArrayLock` at `0x140009df3`
- `OLEAUT32!__imp_SafeArrayLock` at `0x140009eae`
- `OLEAUT32!__imp_SafeArrayLock` at `0x140009f25`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x140009f07`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x140009f07`
- `OLEAUT32!__imp_SafeArrayRedim` at `0x140009f1a`
- `OLEAUT32!__imp_SafeArrayRedim` at `0x140009f1a`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall anonymous_namespace_::ConvertSemicolonSeperatedStringToBSTRSafeArray(__int64 a1, SAFEARRAY **a2)
{
  SAFEARRAY *v3; // rax
  _QWORD *v4; // rdx
  signed __int32 v5; // eax
  bool v6; // cc
  __int64 result; // rax
  SAFEARRAYBOUND v8; // rax
  UINT v9; // edx
  BSTR v10; // rax
  SAFEARRAY *v11; // rax
  HRESULT LBound; // eax
  LONG v13; // r14d
  SAFEARRAY *v14; // rcx
  HRESULT v15; // esi
  HRESULT v16; // eax
  int Count; // eax
  int v18; // [rsp+20h] [rbp-40h] BYREF
  __int64 v19; // [rsp+28h] [rbp-38h] BYREF
  BSTR v20; // [rsp+30h] [rbp-30h] BYREF
  SAFEARRAYBOUND rgsabound; // [rsp+38h] [rbp-28h] BYREF
  LONG plLbound; // [rsp+40h] [rbp-20h] BYREF
  SAFEARRAYBOUND v23; // [rsp+48h] [rbp-18h] BYREF
  SAFEARRAYBOUND psaboundNew; // [rsp+50h] [rbp-10h] BYREF

  v19 = 0;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &v19,
    a1);
  if ( *(_DWORD *)(v19 - 16) || *a2 )
  {
    v18 = 0;
    do
    {
      rgsabound = 0;
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Tokenize(
        &v19,
        &rgsabound,
        L";",
        &v18);
      v8 = rgsabound;
      v9 = *(_DWORD *)(*(_QWORD *)&rgsabound - 16LL);
      if ( v9 )
      {
        v10 = SysAllocStringLen(*(const OLECHAR **)&rgsabound, v9);
        if ( !v10 )
          ATL::CSimpleStringT<char,0>::ThrowMemoryException();
        v20 = v10;
        if ( *a2
          || (v23.cElements = 0, v23.lLbound = 0, v11 = SafeArrayCreate(8u, 1u, &v23), (*a2 = v11) != 0)
          && SafeArrayLock(v11) >= 0 )
        {
          plLbound = 0;
          LBound = SafeArrayGetLBound(*a2, 1u, &plLbound);
          if ( LBound < 0 )
          {
            _mm_lfence();
            ATL::AtlThrowImpl(LBound);
          }
          psaboundNew.cElements = ATL::CComSafeArray<unsigned short *,8>::GetCount(a2) + 1;
          v13 = plLbound;
          psaboundNew.lLbound = plLbound;
          v14 = *a2;
          if ( !*a2 )
            ATL::AtlThrowImpl(-2147467259);
          if ( (v14->fFeatures & 0x10) == 0 )
          {
            v15 = SafeArrayUnlock(v14);
            if ( v15 >= 0 )
            {
              v15 = SafeArrayRedim(*a2, &psaboundNew);
              v16 = SafeArrayLock(*a2);
              if ( v15 >= 0 )
                v15 = v16;
            }
            if ( v15 >= 0 )
            {
              Count = ATL::CComSafeArray<unsigned short *,8>::GetCount(a2);
              ATL::CComSafeArray<unsigned short *,8>::SetAt(a2, (unsigned int)(Count + v13 - 1), &v20);
            }
          }
        }
        v8 = rgsabound;
      }
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*(_QWORD *)&v8 - 24LL + 16), 0xFFFFFFFF) <= 1 )
      {
        _mm_lfence();
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(*(_QWORD *)&v8 - 24LL) + 8LL))(*(_QWORD *)(*(_QWORD *)&v8 - 24LL));
      }
    }
    while ( v18 != -1 );
  }
  else
  {
    rgsabound.cElements = 0;
    rgsabound.lLbound = 0;
    v3 = SafeArrayCreate(8u, 1u, &rgsabound);
    *a2 = v3;
    if ( v3 )
      SafeArrayLock(v3);
  }
  v4 = (_QWORD *)(v19 - 24);
  v5 = _InterlockedExchangeAdd((volatile signed __int32 *)(v19 - 24 + 16), 0xFFFFFFFF);
  v6 = v5 <= 1;
  result = (unsigned int)(v5 - 1);
  if ( v6 )
  {
    _mm_lfence();
    return (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v4 + 8LL))(*v4);
  }
  return result;
}

```

## disassembly

```asm
0x140009d8c  mov     [rsp-18h+arg_10], rbx
0x140009d91  push    rbp
0x140009d92  push    rsi
0x140009d93  push    r14
0x140009d95  mov     rbp, rsp
0x140009d98  sub     rsp, 60h
0x140009d9c  mov     rax, cs:__security_cookie
0x140009da3  xor     rax, rsp
0x140009da6  mov     [rbp+var_8], rax
0x140009daa  mov     rbx, rdx
0x140009dad  and     [rbp+var_38], 0
0x140009db2  mov     rdx, rcx
0x140009db5  lea     rcx, [rbp+var_38]
0x140009db9  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x140009dbe  mov     rax, [rbp+var_38]
0x140009dc2  cmp     dword ptr [rax-10h], 0
0x140009dc6  jnz     short loc_140009E38
0x140009dc8  cmp     qword ptr [rbx], 0
0x140009dcc  jnz     short loc_140009E38
0x140009dce  and     [rbp+rgsabound.cElements], 0
0x140009dd2  and     [rbp+rgsabound.lLbound], 0
0x140009dd6  mov     ecx, 8; vt
0x140009ddb  lea     r8, [rbp+rgsabound]; rgsabound
0x140009ddf  lea     edx, [rcx-7]; cDims
0x140009de2  call    cs:__imp_SafeArrayCreate
0x140009de8  mov     [rbx], rax
0x140009deb  test    rax, rax
0x140009dee  jz      short loc_140009DFA
0x140009df0  mov     rcx, rax; psa
0x140009df3  call    cs:__imp_SafeArrayLock
0x140009df9  nop
0x140009dfa  mov     rdx, [rbp+var_38]
0x140009dfe  add     rdx, 0FFFFFFFFFFFFFFE8h
0x140009e02  or      eax, 0FFFFFFFFh
0x140009e05  lock xadd [rdx+10h], eax
0x140009e0a  sub     eax, 1
0x140009e0d  jg      short loc_140009E1B
0x140009e0f  lfence
0x140009e12  mov     rcx, [rdx]
0x140009e15  mov     rax, [rcx]
0x140009e18  call    qword ptr [rax+8]
0x140009e1b  mov     rcx, [rbp+var_8]
0x140009e1f  xor     rcx, rsp; StackCookie
0x140009e22  call    __security_check_cookie
0x140009e27  mov     rbx, [rsp+60h+arg_10]
0x140009e2f  add     rsp, 60h
0x140009e33  pop     r14
0x140009e35  pop     rsi
0x140009e36  pop     rbp
0x140009e37  retn
0x140009e38  and     [rbp+var_40], 0
0x140009e3c  and     qword ptr [rbp+rgsabound.cElements], 0
0x140009e41  lea     r9, [rbp+var_40]
0x140009e45  lea     r8, asc_140071870; ";"
0x140009e4c  lea     rdx, [rbp+rgsabound]
0x140009e50  lea     rcx, [rbp+var_38]
0x140009e54  call    ?Tokenize@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBA?AV12@PEBGAEAH@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Tokenize(ushort const *,int &)
0x140009e59  nop
0x140009e5a  mov     rax, qword ptr [rbp+rgsabound.cElements]
0x140009e5e  mov     edx, [rax-10h]; ui
0x140009e61  test    edx, edx
0x140009e63  jz      loc_140009F52
0x140009e69  mov     rcx, rax; strIn
0x140009e6c  call    cs:__imp_SysAllocStringLen
0x140009e72  test    rax, rax
0x140009e75  jz      loc_140009F89
0x140009e7b  mov     [rbp+var_30], rax
0x140009e7f  cmp     qword ptr [rbx], 0
0x140009e83  jnz     short loc_140009EBC
0x140009e85  and     [rbp+var_18.cElements], 0
0x140009e89  and     [rbp+var_18.lLbound], 0
0x140009e8d  mov     ecx, 8; vt
0x140009e92  lea     r8, [rbp+var_18]; rgsabound
0x140009e96  lea     edx, [rcx-7]; cDims
0x140009e99  call    cs:__imp_SafeArrayCreate
0x140009e9f  mov     [rbx], rax
0x140009ea2  test    rax, rax
0x140009ea5  jz      loc_140009F4E
0x140009eab  mov     rcx, rax; psa
0x140009eae  call    cs:__imp_SafeArrayLock
0x140009eb4  test    eax, eax
0x140009eb6  js      loc_140009F4E
0x140009ebc  and     [rbp+plLbound], 0
0x140009ec0  lea     r8, [rbp+plLbound]; plLbound
0x140009ec4  mov     edx, 1; nDim
0x140009ec9  mov     rcx, [rbx]; psa
0x140009ecc  call    cs:__imp_SafeArrayGetLBound
0x140009ed2  test    eax, eax
0x140009ed4  js      loc_140009F7E
0x140009eda  mov     rcx, rbx
0x140009edd  call    ?GetCount@?$CComSafeArray@PEAG$07@ATL@@QEBAKI@Z; ATL::CComSafeArray<ushort *,8>::GetCount(uint)
0x140009ee2  inc     eax
0x140009ee4  mov     [rbp+psaboundNew.cElements], eax
0x140009ee7  mov     r14d, [rbp+plLbound]
0x140009eeb  mov     [rbp+psaboundNew.lLbound], r14d
0x140009eef  mov     rcx, [rbx]; psa
0x140009ef2  test    rcx, rcx
0x140009ef5  jz      loc_140009F8F
0x140009efb  mov     al, [rcx+2]
0x140009efe  shr     al, 4
0x140009f01  not     al
0x140009f03  test    al, 1
0x140009f05  jz      short loc_140009F4E
0x140009f07  call    cs:__imp_SafeArrayUnlock
0x140009f0d  mov     esi, eax
0x140009f0f  test    eax, eax
0x140009f11  js      short loc_140009F30
0x140009f13  lea     rdx, [rbp+psaboundNew]; psaboundNew
0x140009f17  mov     rcx, [rbx]; psa
0x140009f1a  call    cs:__imp_SafeArrayRedim
0x140009f20  mov     esi, eax
0x140009f22  mov     rcx, [rbx]; psa
0x140009f25  call    cs:__imp_SafeArrayLock
0x140009f2b  test    esi, esi
0x140009f2d  cmovns  esi, eax
0x140009f30  test    esi, esi
0x140009f32  js      short loc_140009F4E
0x140009f34  mov     rcx, rbx
0x140009f37  call    ?GetCount@?$CComSafeArray@PEAG$07@ATL@@QEBAKI@Z; ATL::CComSafeArray<ushort *,8>::GetCount(uint)
0x140009f3c  lea     edx, [r14-1]
0x140009f40  add     edx, eax
0x140009f42  lea     r8, [rbp+var_30]
0x140009f46  mov     rcx, rbx
0x140009f49  call    ?SetAt@?$CComSafeArray@PEAG$07@ATL@@QEAAJJAEBQEAGH@Z; ATL::CComSafeArray<ushort *,8>::SetAt(long,ushort * const &,int)
0x140009f4e  mov     rax, qword ptr [rbp+rgsabound.cElements]
0x140009f52  lea     rdx, [rax-18h]
0x140009f56  or      eax, 0FFFFFFFFh
0x140009f59  lock xadd [rdx+10h], eax
0x140009f5e  sub     eax, 1
0x140009f61  jg      short loc_140009F6F
0x140009f63  lfence
0x140009f66  mov     rcx, [rdx]
0x140009f69  mov     rax, [rcx]
0x140009f6c  call    qword ptr [rax+8]
0x140009f6f  cmp     [rbp+var_40], 0FFFFFFFFh
0x140009f73  jnz     loc_140009E3C
0x140009f79  jmp     loc_140009DFA
0x140009f7e  lfence
0x140009f81  mov     ecx, eax; int
0x140009f83  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x140009f89  call    ?ThrowMemoryException@?$CSimpleStringT@D$0A@@ATL@@KAXXZ; ATL::CSimpleStringT<char,0>::ThrowMemoryException(void)
0x140009f8f  mov     ecx, 80004005h; int
0x140009f94  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
