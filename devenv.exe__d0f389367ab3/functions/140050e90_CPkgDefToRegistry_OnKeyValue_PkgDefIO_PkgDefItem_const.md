# CPkgDefToRegistry::OnKeyValue(PkgDefIO::PkgDefItem const &)

- ea: `0x140050e90`
- end: `0x140051340`
- name: `?OnKeyValue@CPkgDefToRegistry@@MEAAJAEBUPkgDefItem@PkgDefIO@@@Z`
- size: `1200`
- prototype: `__int64 __fastcall(CPkgDefToRegistry *__hidden this, const struct PkgDefIO::PkgDefItem *)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callees

- `0x140001020`
- `0x140002c10`
- `0x140006e90`
- `0x140007740`
- `0x140033ab0`
- `0x1400464b0`
- `0x140046514`
- `0x140050e90`

## import_xrefs

- `ADVAPI32!RegSetValueExW` at `0x1400512e7`
- `ADVAPI32!RegSetValueExW` at `0x1400512e7`
- `ADVAPI32!RegQueryValueExW` at `0x140050ef4`
- `ADVAPI32!RegQueryValueExW` at `0x140050ef4`
- `OLEAUT32!__imp_VariantClear` at `0x140051035`
- `OLEAUT32!__imp_VariantClear` at `0x1400510b1`
- `OLEAUT32!__imp_VariantClear` at `0x140051136`
- `OLEAUT32!__imp_VariantClear` at `0x1400511be`
- `OLEAUT32!__imp_VariantClear` at `0x140051241`
- `OLEAUT32!__imp_VariantClear` at `0x1400512b5`
- `OLEAUT32!__imp_VariantClear` at `0x140051035`
- `OLEAUT32!__imp_VariantClear` at `0x1400510b1`
- `OLEAUT32!__imp_VariantClear` at `0x140051136`
- `OLEAUT32!__imp_VariantClear` at `0x1400511be`
- `OLEAUT32!__imp_VariantClear` at `0x140051241`
- `OLEAUT32!__imp_VariantClear` at `0x1400512b5`

## string_xrefs

- `0x1400512fc`: `Error writing to registry value name`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall CPkgDefToRegistry::OnKeyValue(CPkgDefToRegistry *this, const struct PkgDefIO::PkgDefItem *a2)
{
  char v4; // si
  char v5; // r15
  unsigned int v6; // r12d
  LSTATUS Value; // ebx
  struct ATL::IAtlStringMgr *Instance; // rax
  __int64 v9; // r9
  LPCWSTR v10; // r8
  unsigned __int16 *v11; // rbx
  unsigned int v12; // edx
  int v13; // ecx
  int v14; // ecx
  int v15; // ecx
  int v16; // ecx
  int v17; // ecx
  __int64 v18; // rcx
  LONGLONG v19; // rax
  LPCWSTR *v20; // rbx
  LSTATUS v21; // eax
  __int64 v22; // rcx
  LONG v23; // eax
  __int64 v24; // rcx
  const BYTE **v25; // r13
  __int64 v26; // rcx
  const BYTE **v27; // r13
  const unsigned __int16 **v28; // r13
  DWORD v29; // r9d
  char v30; // di
  char v32; // [rsp+30h] [rbp-30h]
  unsigned __int16 *v33; // [rsp+38h] [rbp-28h] BYREF
  VARIANTARG pvarg; // [rsp+40h] [rbp-20h] BYREF

  v4 = 0;
  v5 = 0;
  LODWORD(v33) = 0;
  v6 = 0;
  if ( CLogger::ms_bLoggingOn )
  {
    Value = RegQueryValueExW(*((HKEY *)this + 27), *((LPCWSTR *)a2 + 1), 0, 0, 0, 0);
    if ( Value != 2 )
    {
      Instance = ATL::CAtlStringMgr::GetInstance();
      if ( !Instance )
        ATL::AtlThrowImpl(-2147467259);
      v33 = (unsigned __int16 *)((*(__int64 (__fastcall **)(struct ATL::IAtlStringMgr *))(*(_QWORD *)Instance + 24LL))(Instance)
                               + 24);
      v9 = *((_QWORD *)a2 + 1);
      v10 = *(LPCWSTR *)a2;
      if ( Value )
      {
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
          &v33,
          L"Error while processing section '%s', value '%s'",
          v10,
          v9);
        v12 = (unsigned __int16)Value | 0x80070000;
        if ( Value <= 0 )
          v12 = Value;
        v11 = v33;
        CLogger::LogError(v33, v12, **((const unsigned __int16 ***)this + 31));
      }
      else
      {
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
          &v33,
          L"PkgDef encountered data collision in section '%s' for value '%s'",
          v10,
          v9);
        v11 = v33;
        CLogger::LogWarn(v33, 0, **((const unsigned __int16 ***)this + 31));
      }
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v11 - 2, 0xFFFFFFFF) <= 1 )
      {
        _mm_lfence();
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v11 - 3) + 8LL))(*((_QWORD *)v11 - 3));
      }
    }
  }
  v13 = *((_DWORD *)a2 + 4);
  if ( !v13 )
  {
    v28 = (const unsigned __int16 **)((char *)a2 + 24);
    if ( *((_QWORD *)this + 24) )
    {
      ATL::CComVariant::CComVariant((ATL::CComVariant *)&pvarg, *v28);
      v5 = 4;
      LODWORD(v33) = 4;
      v20 = (LPCWSTR *)((char *)a2 + 8);
      if ( !(*(unsigned __int8 (__fastcall **)(_QWORD, _QWORD, _QWORD, VARIANTARG *))(**((_QWORD **)this + 24) + 16LL))(
              *((_QWORD *)this + 24),
              *(_QWORD *)a2,
              *((_QWORD *)a2 + 1),
              &pvarg) )
      {
        v30 = 0;
LABEL_67:
        if ( (v5 & 4) != 0 )
          VariantClear(&pvarg);
        if ( !v30 )
          return v6;
        v29 = 1;
        goto LABEL_71;
      }
    }
    else
    {
      v20 = (LPCWSTR *)((char *)a2 + 8);
    }
    v30 = 1;
    goto LABEL_67;
  }
  v14 = v13 - 1;
  if ( !v14 )
  {
    v28 = (const unsigned __int16 **)((char *)a2 + 24);
    if ( *((_QWORD *)this + 24) )
    {
      ATL::CComVariant::CComVariant((ATL::CComVariant *)&pvarg, *v28);
      v5 = 2;
      LODWORD(v33) = 2;
      v20 = (LPCWSTR *)((char *)a2 + 8);
      if ( !(*(unsigned __int8 (__fastcall **)(_QWORD, _QWORD, _QWORD, VARIANTARG *))(**((_QWORD **)this + 24) + 16LL))(
              *((_QWORD *)this + 24),
              *(_QWORD *)a2,
              *((_QWORD *)a2 + 1),
              &pvarg) )
        goto LABEL_58;
    }
    else
    {
      v20 = (LPCWSTR *)((char *)a2 + 8);
    }
    v4 = 1;
LABEL_58:
    if ( (v5 & 2) != 0 )
      VariantClear(&pvarg);
    if ( !v4 )
      return v6;
    v29 = 2;
LABEL_71:
    v21 = RegSetValueExW(*((HKEY *)this + 27), *v20, 0, v29, (const BYTE *)*v28, 2 * *((_DWORD *)*v28 - 4) + 2);
    goto LABEL_72;
  }
  v15 = v14 - 1;
  if ( !v15 )
  {
    v26 = *((_QWORD *)this + 24);
    v27 = (const BYTE **)((char *)a2 + 32);
    if ( v26 )
    {
      pvarg.vt = 11;
      pvarg.iVal = -(*v27 != 0);
      v5 = 1;
      LODWORD(v33) = 1;
      v20 = (LPCWSTR *)((char *)a2 + 8);
      if ( !(*(unsigned __int8 (__fastcall **)(__int64, _QWORD, _QWORD, VARIANTARG *))(*(_QWORD *)v26 + 16LL))(
              v26,
              *(_QWORD *)a2,
              *((_QWORD *)a2 + 1),
              &pvarg) )
      {
        v32 = 0;
LABEL_49:
        if ( (v5 & 1) != 0 )
          VariantClear(&pvarg);
        if ( !v32 )
          return v6;
        v21 = RegSetValueExW(*((HKEY *)this + 27), *v20, 0, 7u, *v27, *((_DWORD *)a2 + 10));
LABEL_72:
        v6 = v21;
        if ( v21 < 0 )
        {
          _mm_lfence();
          CLogger::LogError(L"Error writing to registry value name", v21, *v20);
        }
        return v6;
      }
    }
    else
    {
      v20 = (LPCWSTR *)((char *)a2 + 8);
    }
    v32 = 1;
    goto LABEL_49;
  }
  v16 = v15 - 1;
  if ( !v16 )
  {
    v24 = *((_QWORD *)this + 24);
    v25 = (const BYTE **)((char *)a2 + 32);
    if ( v24 )
    {
      pvarg.vt = 11;
      pvarg.iVal = -(*v25 != 0);
      v5 = 32;
      LODWORD(v33) = 32;
      v20 = (LPCWSTR *)((char *)a2 + 8);
      if ( !(*(unsigned __int8 (__fastcall **)(__int64, _QWORD, _QWORD, VARIANTARG *))(*(_QWORD *)v24 + 16LL))(
              v24,
              *(_QWORD *)a2,
              *((_QWORD *)a2 + 1),
              &pvarg) )
        goto LABEL_40;
    }
    else
    {
      v20 = (LPCWSTR *)((char *)a2 + 8);
    }
    v4 = 1;
LABEL_40:
    if ( (v5 & 0x20) != 0 )
      VariantClear(&pvarg);
    if ( !v4 )
      return v6;
    v21 = RegSetValueExW(*((HKEY *)this + 27), *v20, 0, 3u, *v25, *((_DWORD *)a2 + 10));
    goto LABEL_72;
  }
  v17 = v16 - 1;
  if ( !v17 )
  {
    v22 = *((_QWORD *)this + 24);
    if ( v22 )
    {
      v23 = *((_DWORD *)a2 + 12);
      pvarg.vt = 19;
      pvarg.lVal = v23;
      v5 = 8;
      LODWORD(v33) = 8;
      v20 = (LPCWSTR *)((char *)a2 + 8);
      if ( !(*(unsigned __int8 (__fastcall **)(__int64, _QWORD, _QWORD, VARIANTARG *))(*(_QWORD *)v22 + 16LL))(
              v22,
              *(_QWORD *)a2,
              *((_QWORD *)a2 + 1),
              &pvarg) )
        goto LABEL_31;
    }
    else
    {
      v20 = (LPCWSTR *)((char *)a2 + 8);
    }
    v4 = 1;
LABEL_31:
    if ( (v5 & 8) != 0 )
      VariantClear(&pvarg);
    if ( !v4 )
      return v6;
    v21 = RegSetValueExW(*((HKEY *)this + 27), *v20, 0, 4u, (const BYTE *)a2 + 48, 4u);
    goto LABEL_72;
  }
  if ( v17 != 1 )
    return v6;
  v18 = *((_QWORD *)this + 24);
  if ( !v18 )
  {
    v20 = (LPCWSTR *)((char *)a2 + 8);
    goto LABEL_21;
  }
  v19 = *((_QWORD *)a2 + 7);
  pvarg.vt = 21;
  pvarg.llVal = v19;
  v5 = 16;
  LODWORD(v33) = 16;
  v20 = (LPCWSTR *)((char *)a2 + 8);
  if ( (*(unsigned __int8 (__fastcall **)(__int64, _QWORD, _QWORD, VARIANTARG *))(*(_QWORD *)v18 + 16LL))(
         v18,
         *(_QWORD *)a2,
         *((_QWORD *)a2 + 1),
         &pvarg) )
  {
LABEL_21:
    v4 = 1;
  }
  if ( (v5 & 0x10) != 0 )
    VariantClear(&pvarg);
  if ( v4 )
  {
    v21 = RegSetValueExW(*((HKEY *)this + 27), *v20, 0, 0xBu, (const BYTE *)a2 + 56, 8u);
    goto LABEL_72;
  }
  return v6;
}

```

## disassembly

```asm
0x140050e90  mov     r11, rsp
0x140050e93  mov     [r11+8], rbx
0x140050e97  mov     [r11+10h], rsi
0x140050e9b  mov     [r11+18h], rdi
0x140050e9f  push    rbp
0x140050ea0  push    r12
0x140050ea2  push    r13
0x140050ea4  push    r14
0x140050ea6  push    r15
0x140050ea8  mov     rbp, rsp
0x140050eab  sub     rsp, 60h
0x140050eaf  mov     rax, cs:__security_cookie
0x140050eb6  xor     rax, rsp
0x140050eb9  mov     [rbp+var_8], rax
0x140050ebd  mov     rdi, rdx
0x140050ec0  mov     r14, rcx
0x140050ec3  xor     esi, esi
0x140050ec5  mov     r15d, esi
0x140050ec8  mov     dword ptr [rbp+var_28], esi
0x140050ecb  mov     r12d, esi
0x140050ece  cmp     cs:?ms_bLoggingOn@CLogger@@0_NA, sil; bool CLogger::ms_bLoggingOn
0x140050ed5  jz      loc_140050FA7
0x140050edb  mov     [r11-60h], rsi
0x140050edf  mov     [r11-68h], rsi
0x140050ee3  xor     r9d, r9d; lpType
0x140050ee6  xor     r8d, r8d; lpReserved
0x140050ee9  mov     rdx, [rdx+8]; lpValueName
0x140050eed  mov     rcx, [rcx+0D8h]; hKey
0x140050ef4  call    cs:__imp_RegQueryValueExW
0x140050efa  mov     ebx, eax
0x140050efc  cmp     eax, 2
0x140050eff  jz      loc_140050FA7
0x140050f05  call    ?GetInstance@CAtlStringMgr@ATL@@SAPEAUIAtlStringMgr@2@XZ; ATL::CAtlStringMgr::GetInstance(void)
0x140050f0a  mov     rcx, rax
0x140050f0d  test    rax, rax
0x140050f10  jz      loc_140051335
0x140050f16  mov     rax, [rax]
0x140050f19  call    qword ptr [rax+18h]
0x140050f1c  add     rax, 18h
0x140050f20  mov     [rbp+var_28], rax
0x140050f24  mov     r9, [rdi+8]
0x140050f28  mov     r8, [rdi]
0x140050f2b  lea     rcx, [rbp+var_28]
0x140050f2f  test    ebx, ebx
0x140050f31  jnz     short loc_140050F59
0x140050f33  lea     rdx, aPkgdefEncounte; "PkgDef encountered data collision in se"...
0x140050f3a  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x140050f3f  mov     r8, [r14+0F8h]
0x140050f46  mov     r8, [r8]; unsigned __int16 *
0x140050f49  xor     edx, edx; int
0x140050f4b  mov     rbx, [rbp+var_28]
0x140050f4f  mov     rcx, rbx; unsigned __int16 *
0x140050f52  call    ?LogWarn@CLogger@@SAXPEBGJ0@Z; CLogger::LogWarn(ushort const *,long,ushort const *)
0x140050f57  jmp     short loc_140050F8A
0x140050f59  lea     rdx, aErrorWhileProc; "Error while processing section '%s', va"...
0x140050f60  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x140050f65  mov     r8, [r14+0F8h]
0x140050f6c  movzx   edx, bx
0x140050f6f  or      edx, 80070000h
0x140050f75  test    ebx, ebx
0x140050f77  cmovle  edx, ebx; int
0x140050f7a  mov     r8, [r8]; unsigned __int16 *
0x140050f7d  mov     rbx, [rbp+var_28]
0x140050f81  mov     rcx, rbx; unsigned __int16 *
0x140050f84  call    ?LogError@CLogger@@SAXPEBGJ0@Z; CLogger::LogError(ushort const *,long,ushort const *)
0x140050f89  nop
0x140050f8a  lea     rdx, [rbx-18h]
0x140050f8e  or      eax, 0FFFFFFFFh
0x140050f91  lock xadd [rdx+10h], eax
0x140050f96  sub     eax, 1
0x140050f99  jg      short loc_140050FA7
0x140050f9b  lfence
0x140050f9e  mov     rcx, [rdx]
0x140050fa1  mov     rax, [rcx]
0x140050fa4  call    qword ptr [rax+8]
0x140050fa7  mov     ecx, [rdi+10h]
0x140050faa  test    ecx, ecx
0x140050fac  jz      loc_140051258
0x140050fb2  sub     ecx, 1
0x140050fb5  jz      loc_1400511E9
0x140050fbb  sub     ecx, 1
0x140050fbe  jz      loc_140051160
0x140050fc4  sub     ecx, 1
0x140050fc7  jz      loc_1400510D8
0x140050fcd  sub     ecx, 1
0x140050fd0  jz      loc_14005105C
0x140050fd6  cmp     ecx, 1
0x140050fd9  jnz     loc_140051308
0x140050fdf  mov     rcx, [r14+0C0h]
0x140050fe6  lea     r13, [rdi+38h]
0x140050fea  test    rcx, rcx
0x140050fed  jz      short loc_140051022
0x140050fef  mov     rax, [r13+0]
0x140050ff3  mov     edx, 15h
0x140050ff8  mov     word ptr [rbp+pvarg], dx
0x140050ffc  mov     qword ptr [rbp+pvarg+8], rax
0x140051000  lea     r15d, [rdx-5]
0x140051004  mov     dword ptr [rbp+var_28], r15d
0x140051008  lea     rbx, [rdi+8]
0x14005100c  mov     rax, [rcx]
0x14005100f  lea     r9, [rbp+pvarg]
0x140051013  mov     r8, [rbx]
0x140051016  mov     rdx, [rdi]
0x140051019  call    qword ptr [rax+10h]
0x14005101c  test    al, al
0x14005101e  jnz     short loc_140051026
0x140051020  jmp     short loc_14005102B
0x140051022  lea     rbx, [rdi+8]
0x140051026  mov     esi, 1
0x14005102b  test    r15b, 10h
0x14005102f  jz      short loc_14005103B
0x140051031  lea     rcx, [rbp+pvarg]; pvarg
0x140051035  call    cs:__imp_VariantClear
0x14005103b  test    sil, sil
0x14005103e  jz      loc_140051308
0x140051044  mov     [rsp+60h+cbData], 8
0x14005104c  mov     [rsp+60h+lpData], r13
0x140051051  mov     r9d, 0Bh
0x140051057  jmp     loc_1400512DA
0x14005105c  mov     rcx, [r14+0C0h]
0x140051063  lea     r13, [rdi+30h]
0x140051067  test    rcx, rcx
0x14005106a  jz      short loc_14005109E
0x14005106c  mov     eax, [r13+0]
0x140051070  mov     edx, 13h
0x140051075  mov     word ptr [rbp+pvarg], dx
0x140051079  mov     dword ptr [rbp+pvarg+8], eax
0x14005107c  lea     r15d, [rdx-0Bh]
0x140051080  mov     dword ptr [rbp+var_28], r15d
0x140051084  lea     rbx, [rdi+8]
0x140051088  mov     rax, [rcx]
0x14005108b  lea     r9, [rbp+pvarg]
0x14005108f  mov     r8, [rbx]
0x140051092  mov     rdx, [rdi]
0x140051095  call    qword ptr [rax+10h]
0x140051098  test    al, al
0x14005109a  jnz     short loc_1400510A2
0x14005109c  jmp     short loc_1400510A7
0x14005109e  lea     rbx, [rdi+8]
0x1400510a2  mov     esi, 1
0x1400510a7  test    r15b, 8
0x1400510ab  jz      short loc_1400510B7
0x1400510ad  lea     rcx, [rbp+pvarg]; pvarg
0x1400510b1  call    cs:__imp_VariantClear
0x1400510b7  test    sil, sil
0x1400510ba  jz      loc_140051308
0x1400510c0  mov     [rsp+60h+cbData], 4
0x1400510c8  mov     [rsp+60h+lpData], r13
0x1400510cd  mov     r9d, 4
0x1400510d3  jmp     loc_1400512DA
0x1400510d8  mov     rcx, [r14+0C0h]
0x1400510df  lea     r13, [rdi+20h]
0x1400510e3  test    rcx, rcx
0x1400510e6  jz      short loc_140051123
0x1400510e8  mov     eax, 0Bh
0x1400510ed  mov     word ptr [rbp+pvarg], ax
0x1400510f1  mov     rax, [r13+0]
0x1400510f5  neg     rax
0x1400510f8  sbb     dx, dx
0x1400510fb  mov     word ptr [rbp+pvarg+8], dx
0x1400510ff  mov     r15d, 20h ; ' '
0x140051105  mov     dword ptr [rbp+var_28], r15d
0x140051109  lea     rbx, [rdi+8]
0x14005110d  mov     rax, [rcx]
0x140051110  lea     r9, [rbp+pvarg]
0x140051114  mov     r8, [rbx]
0x140051117  mov     rdx, [rdi]
0x14005111a  call    qword ptr [rax+10h]
0x14005111d  test    al, al
0x14005111f  jnz     short loc_140051127
0x140051121  jmp     short loc_14005112C
0x140051123  lea     rbx, [rdi+8]
0x140051127  mov     esi, 1
0x14005112c  test    r15b, 20h
0x140051130  jz      short loc_14005113C
0x140051132  lea     rcx, [rbp+pvarg]; pvarg
0x140051136  call    cs:__imp_VariantClear
0x14005113c  test    sil, sil
0x14005113f  jz      loc_140051308
0x140051145  mov     eax, [rdi+28h]
0x140051148  mov     [rsp+60h+cbData], eax
0x14005114c  mov     rax, [r13+0]
0x140051150  mov     [rsp+60h+lpData], rax
0x140051155  mov     r9d, 3
0x14005115b  jmp     loc_1400512DA
0x140051160  mov     rcx, [r14+0C0h]
0x140051167  mov     esi, 1
0x14005116c  lea     r13, [rdi+20h]
0x140051170  test    rcx, rcx
0x140051173  jz      short loc_1400511AD
0x140051175  lea     eax, [rsi+0Ah]
0x140051178  mov     word ptr [rbp+pvarg], ax
0x14005117c  mov     rax, [r13+0]
0x140051180  neg     rax
0x140051183  sbb     dx, dx
0x140051186  mov     word ptr [rbp+pvarg+8], dx
0x14005118a  mov     r15d, esi
0x14005118d  mov     dword ptr [rbp+var_28], esi
0x140051190  lea     rbx, [rdi+8]
0x140051194  mov     rax, [rcx]
0x140051197  lea     r9, [rbp+pvarg]
0x14005119b  mov     r8, [rbx]
0x14005119e  mov     rdx, [rdi]
0x1400511a1  call    qword ptr [rax+10h]
0x1400511a4  test    al, al
0x1400511a6  jnz     short loc_1400511B1
0x1400511a8  mov     [rbp+var_30], al
0x1400511ab  jmp     short loc_1400511B5
0x1400511ad  lea     rbx, [rdi+8]
0x1400511b1  mov     [rbp+var_30], sil
0x1400511b5  test    sil, r15b
0x1400511b8  jz      short loc_1400511C4
0x1400511ba  lea     rcx, [rbp+pvarg]; pvarg
0x1400511be  call    cs:__imp_VariantClear
0x1400511c4  cmp     [rbp+var_30], 0
0x1400511c8  jz      loc_140051308
0x1400511ce  mov     eax, [rdi+28h]
0x1400511d1  mov     [rsp+60h+cbData], eax
0x1400511d5  mov     rax, [r13+0]
0x1400511d9  mov     [rsp+60h+lpData], rax
0x1400511de  mov     r9d, 7
0x1400511e4  jmp     loc_1400512DA
0x1400511e9  lea     r13, [rdi+18h]
0x1400511ed  cmp     [r14+0C0h], rsi
0x1400511f4  jz      short loc_14005122E
0x1400511f6  mov     rdx, [r13+0]; unsigned __int16 *
0x1400511fa  lea     rcx, [rbp+pvarg]; this
0x1400511fe  call    ??0CComVariant@ATL@@QEAA@PEBG@Z; ATL::CComVariant::CComVariant(ushort const *)
0x140051203  mov     r15d, 2
0x140051209  mov     dword ptr [rbp+var_28], r15d
0x14005120d  mov     rcx, [r14+0C0h]
0x140051214  lea     rbx, [rdi+8]
0x140051218  mov     rax, [rcx]
0x14005121b  lea     r9, [rbp+pvarg]
0x14005121f  mov     r8, [rbx]
0x140051222  mov     rdx, [rdi]
0x140051225  call    qword ptr [rax+10h]
0x140051228  test    al, al
0x14005122a  jnz     short loc_140051232
0x14005122c  jmp     short loc_140051237
0x14005122e  lea     rbx, [rdi+8]
0x140051232  mov     esi, 1
0x140051237  test    r15b, 2
0x14005123b  jz      short loc_140051247
0x14005123d  lea     rcx, [rbp+pvarg]; pvarg
0x140051241  call    cs:__imp_VariantClear
0x140051247  test    sil, sil
0x14005124a  jz      loc_140051308
0x140051250  mov     r9d, 2
0x140051256  jmp     short loc_1400512C3
0x140051258  mov     esi, 1
0x14005125d  lea     r13, [rdi+18h]
0x140051261  cmp     qword ptr [r14+0C0h], 0
0x140051269  jz      short loc_1400512A4
0x14005126b  mov     rdx, [r13+0]; unsigned __int16 *
0x14005126f  lea     rcx, [rbp+pvarg]; this
0x140051273  call    ??0CComVariant@ATL@@QEAA@PEBG@Z; ATL::CComVariant::CComVariant(ushort const *)
0x140051278  lea     r15d, [rsi+3]
0x14005127c  mov     dword ptr [rbp+var_28], r15d
0x140051280  mov     rcx, [r14+0C0h]
0x140051287  lea     rbx, [rdi+8]
0x14005128b  mov     rax, [rcx]
0x14005128e  lea     r9, [rbp+pvarg]
0x140051292  mov     r8, [rbx]
0x140051295  mov     rdx, [rdi]
0x140051298  call    qword ptr [rax+10h]
0x14005129b  test    al, al
0x14005129d  jnz     short loc_1400512A8
0x14005129f  xor     dil, dil
0x1400512a2  jmp     short loc_1400512AB
0x1400512a4  lea     rbx, [rdi+8]
0x1400512a8  mov     dil, sil
0x1400512ab  test    r15b, 4
0x1400512af  jz      short loc_1400512BB
0x1400512b1  lea     rcx, [rbp+pvarg]; pvarg
0x1400512b5  call    cs:__imp_VariantClear
0x1400512bb  test    dil, dil
0x1400512be  jz      short loc_140051308
0x1400512c0  mov     r9d, esi; dwType
0x1400512c3  mov     rcx, [r13+0]
0x1400512c7  mov     eax, [rcx-10h]
0x1400512ca  lea     eax, ds:2[rax*2]
0x1400512d1  mov     [rsp+60h+cbData], eax; cbData
0x1400512d5  mov     [rsp+60h+lpData], rcx; lpData
0x1400512da  xor     r8d, r8d; Reserved
0x1400512dd  mov     rdx, [rbx]; lpValueName
0x1400512e0  mov     rcx, [r14+0D8h]; hKey
0x1400512e7  call    cs:__imp_RegSetValueExW
0x1400512ed  mov     r12d, eax
0x1400512f0  test    eax, eax
0x1400512f2  jns     short loc_140051308
0x1400512f4  lfence
0x1400512f7  mov     r8, [rbx]; unsigned __int16 *
0x1400512fa  mov     edx, eax; int
0x1400512fc  lea     rcx, aErrorWritingTo; "Error writing to registry value name"
0x140051303  call    ?LogError@CLogger@@SAXPEBGJ0@Z; CLogger::LogError(ushort const *,long,ushort const *)
0x140051308  mov     eax, r12d
0x14005130b  mov     rcx, [rbp+var_8]
0x14005130f  xor     rcx, rsp; StackCookie
0x140051312  call    __security_check_cookie
  ... truncated ...
```
