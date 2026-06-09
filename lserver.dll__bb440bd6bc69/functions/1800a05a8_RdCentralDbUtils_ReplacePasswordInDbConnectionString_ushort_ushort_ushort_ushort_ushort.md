# RdCentralDbUtils::ReplacePasswordInDbConnectionString(ushort *,ushort *,ushort *,ushort * *,ushort * *)

- ea: `0x1800a05a8`
- end: `0x1800a0dda`
- name: `?ReplacePasswordInDbConnectionString@RdCentralDbUtils@@SAJPEAG00PEAPEAG1@Z`
- size: `2098`
- prototype: `static int(unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, unsigned __int16 **, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `26`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800994cc`

## callees

- `0x180002ce0`
- `0x18000cf54`
- `0x18000cff0`
- `0x18001ad74`
- `0x180077e9c`
- `0x180078a94`
- `0x1800790c0`
- `0x18008619c`
- `0x1800861cc`
- `0x180086238`
- `0x18008625c`
- `0x180086464`
- `0x180086660`
- `0x180086ad4`
- `0x1800871bc`
- `0x180087484`
- `0x180088814`
- `0x180088b08`
- `0x180088e68`
- `0x180098314`
- `0x1800983d0`
- `0x18009872c`
- `0x18009a200`
- `0x18009fcf8`
- `0x1800a05a8`
- `0x1800a0fb0`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x1800a0774`
- `OLEAUT32!__imp_SysAllocString` at `0x1800a0cb4`
- `OLEAUT32!__imp_SysAllocString` at `0x1800a0774`
- `OLEAUT32!__imp_SysAllocString` at `0x1800a0cb4`
- `OLEAUT32!__imp_SysFreeString` at `0x1800a062a`
- `OLEAUT32!__imp_SysFreeString` at `0x1800a0907`
- `OLEAUT32!__imp_SysFreeString` at `0x1800a0cd7`
- `OLEAUT32!__imp_SysFreeString` at `0x1800a0d44`
- `OLEAUT32!__imp_SysFreeString` at `0x1800a0d59`
- `OLEAUT32!__imp_SysFreeString` at `0x1800a062a`
- `OLEAUT32!__imp_SysFreeString` at `0x1800a0907`
- `OLEAUT32!__imp_SysFreeString` at `0x1800a0cd7`
- `OLEAUT32!__imp_SysFreeString` at `0x1800a0d44`
- `OLEAUT32!__imp_SysFreeString` at `0x1800a0d59`
- `KERNEL32!LocalAlloc` at `0x1800a06a2`
- `KERNEL32!LocalAlloc` at `0x1800a071d`
- `KERNEL32!LocalAlloc` at `0x1800a06a2`
- `KERNEL32!LocalAlloc` at `0x1800a071d`
- `KERNEL32!LocalFree` at `0x1800a0d7a`
- `KERNEL32!LocalFree` at `0x1800a0d96`
- `KERNEL32!LocalFree` at `0x1800a0d7a`
- `KERNEL32!LocalFree` at `0x1800a0d96`

## string_xrefs

- `0x1800a0a2f`: `{password_replaced}`
- `0x1800a0ad1`: `StringCchCopy(REPLACE_PASSWORD) failed`
- `0x1800a087e`: `StringCchCopy(token) failed`
- `0x1800a07ff`: `StringCchCopy(pwszConnSTr) failed`
- `0x1800a0b5b`: `StringCchCopy(pwszConnSTr) failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall RdCentralDbUtils::ReplacePasswordInDbConnectionString(
        unsigned __int16 *a1,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        unsigned __int16 **a4,
        unsigned __int16 **a5)
{
  unsigned int v6; // edi
  int v7; // ebx
  unsigned __int16 **v8; // r14
  __int64 v9; // r15
  ATL::CComBSTR *v10; // rax
  OLECHAR *v11; // rsi
  unsigned int ConnectionStringParamsNumber; // eax
  __int64 v13; // r13
  unsigned int CurrentThreadActivityIdPrefix; // eax
  __int64 v15; // rsi
  unsigned int v16; // eax
  int v17; // edx
  const char *v18; // r8
  unsigned __int16 *v19; // rax
  OLECHAR *v20; // rdi
  wchar_t **v21; // r8
  wchar_t *v22; // rax
  wchar_t **v23; // r8
  wchar_t *v24; // r11
  unsigned int v25; // eax
  wchar_t *v26; // rax
  unsigned int v27; // eax
  unsigned int i; // r15d
  __int64 v29; // rax
  int v30; // ebx
  __int64 v31; // rdx
  __int64 v32; // r8
  int v33; // ebx
  int v34; // ebx
  int v35; // edi
  int v36; // ebx
  __int64 Manager; // rax
  int *v38; // rdi
  __int64 v39; // rbx
  __int64 v40; // rax
  __int64 v41; // r8
  unsigned int v42; // ebx
  unsigned int v43; // eax
  unsigned int v44; // eax
  int v45; // edx
  const char *v46; // r8
  unsigned int j; // edi
  unsigned int v48; // eax
  int v49; // edx
  const char *v50; // r8
  BSTR v51; // rax
  unsigned int v52; // eax
  HLOCAL *v53; // rdi
  __int64 v55; // [rsp+30h] [rbp-D0h] BYREF
  OLECHAR *v56; // [rsp+38h] [rbp-C8h]
  __int64 v57; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v58; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v59; // [rsp+50h] [rbp-B0h] BYREF
  BSTR v60; // [rsp+58h] [rbp-A8h]
  BSTR bstrString; // [rsp+60h] [rbp-A0h] BYREF
  BSTR v62; // [rsp+68h] [rbp-98h] BYREF
  unsigned __int16 **v63; // [rsp+70h] [rbp-90h]
  unsigned __int16 **v64; // [rsp+78h] [rbp-88h]
  BSTR v65; // [rsp+80h] [rbp-80h]
  _BYTE v66[40]; // [rsp+88h] [rbp-78h] BYREF
  OLECHAR psz[1024]; // [rsp+B0h] [rbp-50h] BYREF

  v64 = a4;
  v63 = a5;
  v6 = 0;
  v7 = -2147467259;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v55);
  v60 = 0;
  v8 = 0;
  LODWORD(v9) = 0;
  v10 = (ATL::CComBSTR *)ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&bstrString, a2);
  v11 = ATL::CComBSTR::Copy(v10);
  v65 = v11;
  SysFreeString(bstrString);
  ConnectionStringParamsNumber = RdCentralDbUtils::GetConnectionStringParamsNumber(v11);
  v13 = ConnectionStringParamsNumber;
  if ( !ConnectionStringParamsNumber )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_D(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        21,
        WPP_5c640882e6c13d67d94d4d82c5094b20_Traceguids,
        CurrentThreadActivityIdPrefix);
    }
    v15 = v13;
    goto LABEL_102;
  }
  v15 = ConnectionStringParamsNumber;
  v8 = (unsigned __int16 **)LocalAlloc(0x40u, 8LL * ConnectionStringParamsNumber);
  if ( !v8 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v16 = RdpWppGetCurrentThreadActivityIdPrefix();
      v17 = 22;
      v18 = "\"*ppConnStrParams\"";
      goto LABEL_12;
    }
    goto LABEL_13;
  }
  while ( 1 )
  {
    if ( v6 >= (unsigned int)v13 )
    {
      v20 = SysAllocString(L"Pwd=");
      v56 = v20;
      v22 = wcstok_mvcrt_legacy_two_parameter_form(a2, L";", v21);
      if ( v22 && *v22 )
      {
        v7 = StringCchCopyW(*v8, 0x104u, v22);
        if ( v7 < 0 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v25 = RdpWppGetCurrentThreadActivityIdPrefix();
            WPP_SF_DsD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              25,
              (unsigned int)WPP_5c640882e6c13d67d94d4d82c5094b20_Traceguids,
              v25,
              (__int64)"StringCchCopy(pwszConnSTr) failed",
              v7);
          }
          goto LABEL_100;
        }
        while ( v24 )
        {
          v26 = wcstok_mvcrt_legacy_two_parameter_form(0, L";", v23);
          v24 = v26;
          if ( v26 )
          {
            v9 = (unsigned int)(v9 + 1);
            if ( (unsigned int)v9 < (unsigned int)v13 )
            {
              v7 = StringCchCopyW(v8[v9], 0x104u, v26);
              if ( v7 < 0 )
              {
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  v27 = RdpWppGetCurrentThreadActivityIdPrefix();
                  WPP_SF_DsD(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    26,
                    (unsigned int)WPP_5c640882e6c13d67d94d4d82c5094b20_Traceguids,
                    v27,
                    (__int64)"StringCchCopy(token) failed",
                    v7);
                }
                goto LABEL_100;
              }
            }
          }
        }
        for ( i = 0; i < (unsigned int)v13; ++i )
        {
          v29 = CBaseStringT<unsigned short>::CBaseStringT<unsigned short>(v66, v8[i]);
          v30 = CBaseStringT<unsigned short>::Contains(v29, v20, 1);
          CBaseStringT<unsigned short>::~CBaseStringT<unsigned short>(v66);
          if ( v30 )
          {
            v31 = *(_QWORD *)ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&v62, v8[i]);
            if ( v31 )
            {
              v32 = -1;
              do
                ++v32;
              while ( *(_WORD *)(v31 + 2 * v32) );
            }
            else
            {
              v32 = 0;
            }
            ATL::CSimpleStringT<unsigned short,0>::SetString(&v55, v31, v32);
            SysFreeString(v62);
            v33 = *(_DWORD *)(v55 - 16);
            ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
              &v59,
              v20);
            v34 = v33 - *(_DWORD *)(v59 - 16);
            v35 = 0;
            if ( v34 >= 0 )
              v35 = v34;
            v36 = 0;
            if ( *(int *)(v55 - 16) >= 0 )
              v36 = *(_DWORD *)(v55 - 16);
            if ( v35 < v36 )
            {
              Manager = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::GetManager(&v55);
              ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
                &v57,
                v55 + 2 * (v36 - (__int64)v35),
                (unsigned int)v35,
                Manager);
            }
            else
            {
              ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
                &v57,
                &v55);
            }
            v38 = (int *)(v55 - 24);
            if ( v57 - 24 != v55 - 24 )
            {
              if ( v38[4] >= 0 && *(_QWORD *)(v57 - 24) == *(_QWORD *)v38 )
              {
                v39 = ATL::CSimpleStringT<unsigned short,0>::CloneData();
                ATL::CStringData::Release((ATL::CStringData *)v38);
                v55 = v39 + 24;
              }
              else
              {
                ATL::CSimpleStringT<unsigned short,0>::SetString(&v55, v57, *(unsigned int *)(v57 - 16));
              }
            }
            ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::~CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v57);
            v40 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::AllocSysString(&v55);
            *v63 = (unsigned __int16 *)v40;
            v20 = v56;
            if ( v56 )
            {
              v41 = -1;
              do
                ++v41;
              while ( v56[v41] );
            }
            else
            {
              v41 = 0;
            }
            ATL::CSimpleStringT<unsigned short,0>::SetString(&v55, v56, v41);
            v42 = *(_DWORD *)(v55 - 16);
            ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
              &v58,
              L"{password_replaced}");
            ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Insert(
              &v55,
              v42,
              v58);
            v60 = (BSTR)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::AllocSysString(&v55);
            v7 = StringCchCopyW(v8[i], 0x104u, v60);
            if ( v7 < 0 )
            {
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                v43 = RdpWppGetCurrentThreadActivityIdPrefix();
                WPP_SF_DsD(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  27,
                  (unsigned int)WPP_5c640882e6c13d67d94d4d82c5094b20_Traceguids,
                  v43,
                  (__int64)"StringCchCopy(REPLACE_PASSWORD) failed",
                  v7);
              }
              ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::~CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v58);
              ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::~CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v59);
              goto LABEL_94;
            }
            ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::~CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v58);
            ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::~CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v59);
          }
        }
        v7 = StringCchCopyW(psz, 0x104u, *v8);
        if ( v7 < 0 )
        {
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_94;
          }
          v44 = RdpWppGetCurrentThreadActivityIdPrefix();
          v45 = 28;
          v46 = "StringCchCopy(pwszConnSTr) failed";
LABEL_72:
          WPP_SF_DsD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v45,
            (unsigned int)WPP_5c640882e6c13d67d94d4d82c5094b20_Traceguids,
            v44,
            (__int64)v46,
            v7);
          goto LABEL_94;
        }
        v7 = StringCchCatW(psz, 0x104u, L";");
        if ( v7 < 0 )
        {
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_94;
          }
          v44 = RdpWppGetCurrentThreadActivityIdPrefix();
          v45 = 29;
          v46 = "StringCchCat(;) failed";
          goto LABEL_72;
        }
        for ( j = 1; ; ++j )
        {
          if ( j >= (unsigned int)v13 )
          {
            v51 = SysAllocString(psz);
            *v64 = v51;
            goto LABEL_93;
          }
          v7 = StringCchCatW(psz, 0x104u, v8[j]);
          if ( v7 < 0 )
            break;
          v7 = StringCchCatW(psz, 0x104u, L";");
          if ( v7 < 0 )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v48 = RdpWppGetCurrentThreadActivityIdPrefix();
              v49 = 31;
              v50 = "StringCchCat(;) failed";
LABEL_87:
              WPP_SF_DsD(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                v49,
                (unsigned int)WPP_5c640882e6c13d67d94d4d82c5094b20_Traceguids,
                v48,
                (__int64)v50,
                v7);
              goto LABEL_93;
            }
            goto LABEL_93;
          }
        }
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v48 = RdpWppGetCurrentThreadActivityIdPrefix();
          v49 = 30;
          v50 = "StringCchCat(pwszConnSTr) failed";
          goto LABEL_87;
        }
LABEL_93:
        v20 = v56;
LABEL_94:
        if ( v60 )
          SysFreeString(v60);
      }
      else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
             && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
             && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v52 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          24,
          (unsigned int)WPP_5c640882e6c13d67d94d4d82c5094b20_Traceguids,
          v52,
          (__int64)"Parsing the database connection string for pswd failed!",
          -2147467259);
      }
LABEL_100:
      if ( v20 )
        SysFreeString(v20);
      goto LABEL_102;
    }
    v19 = (unsigned __int16 *)LocalAlloc(0x40u, 0x208u);
    v8[v6] = v19;
    if ( !v19 )
      break;
    ++v6;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v16 = RdpWppGetCurrentThreadActivityIdPrefix();
    v17 = 23;
    v18 = "\"*ppConnStrParams[i]\"";
LABEL_12:
    WPP_SF_Ds(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v17,
      (unsigned int)WPP_5c640882e6c13d67d94d4d82c5094b20_Traceguids,
      v16,
      (__int64)v18);
  }
LABEL_13:
  v7 = -2147024882;
LABEL_102:
  if ( v65 )
    SysFreeString(v65);
  if ( v8 )
  {
    if ( (_DWORD)v13 )
    {
      v53 = (HLOCAL *)v8;
      do
      {
        if ( *v53 )
        {
          LocalFree(*v53);
          *v53 = 0;
        }
        ++v53;
        --v15;
      }
      while ( v15 );
    }
    LocalFree(v8);
  }
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::~CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v55);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800a05a8  mov     [rsp-8+arg_0], rbx
0x1800a05ad  push    rbp
0x1800a05ae  push    rsi
0x1800a05af  push    rdi
0x1800a05b0  push    r12
0x1800a05b2  push    r13
0x1800a05b4  push    r14
0x1800a05b6  push    r15
0x1800a05b8  lea     rbp, [rsp-7C0h]
0x1800a05c0  sub     rsp, 8C0h
0x1800a05c7  mov     rax, cs:__security_cookie
0x1800a05ce  xor     rax, rsp
0x1800a05d1  mov     [rbp+7F0h+var_40], rax
0x1800a05d8  mov     [rsp+8F0h+var_878], r9
0x1800a05dd  mov     r12, rdx
0x1800a05e0  mov     rax, [rbp+7F0h+arg_20]
0x1800a05e7  mov     [rsp+8F0h+var_880], rax
0x1800a05ec  xor     edi, edi
0x1800a05ee  mov     ebx, 80004005h
0x1800a05f3  lea     rcx, [rsp+8F0h+var_8C0]
0x1800a05f8  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x1800a05fd  nop
0x1800a05fe  mov     [rsp+8F0h+var_898], rdi
0x1800a0603  mov     r14d, edi
0x1800a0606  mov     r15d, edi
0x1800a0609  mov     rdx, r12; unsigned __int16 *
0x1800a060c  lea     rcx, [rsp+8F0h+bstrString]; this
0x1800a0611  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x1800a0616  mov     rcx, rax; this
0x1800a0619  call    ?Copy@CComBSTR@ATL@@QEBAPEAGXZ; ATL::CComBSTR::Copy(void)
0x1800a061e  mov     rsi, rax
0x1800a0621  mov     [rbp+7F0h+var_870], rax
0x1800a0625  mov     rcx, [rsp+8F0h+bstrString]; bstrString
0x1800a062a  call    cs:__imp_SysFreeString
0x1800a0631  nop     dword ptr [rax+rax+00h]
0x1800a0636  nop
0x1800a0637  mov     rcx, rsi; unsigned __int16 *
0x1800a063a  call    ?GetConnectionStringParamsNumber@RdCentralDbUtils@@CAKPEAG@Z; RdCentralDbUtils::GetConnectionStringParamsNumber(ushort *)
0x1800a063f  mov     r13d, eax
0x1800a0642  test    eax, eax
0x1800a0644  jnz     short loc_1800A0692
0x1800a0646  lea     rcx, WPP_GLOBAL_Control
0x1800a064d  mov     rdx, cs:WPP_GLOBAL_Control
0x1800a0654  cmp     rdx, rcx
0x1800a0657  jz      short loc_1800A0687
0x1800a0659  test    byte ptr [rdx+1Ch], 1
0x1800a065d  jz      short loc_1800A0687
0x1800a065f  cmp     byte ptr [rdx+19h], 2
0x1800a0663  jb      short loc_1800A0687
0x1800a0665  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800a066a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a0671  lea     edx, [rdi+15h]
0x1800a0674  mov     r9d, eax
0x1800a0677  lea     r8, WPP_5c640882e6c13d67d94d4d82c5094b20_Traceguids
0x1800a067e  mov     rcx, [rcx+10h]
0x1800a0682  call    WPP_SF_D
0x1800a0687  mov     rsi, r13
0x1800a068a  xor     r12d, r12d
0x1800a068d  jmp     loc_1800A0D50
0x1800a0692  mov     rsi, r13
0x1800a0695  lea     rdx, ds:0[r13*8]; uBytes
0x1800a069d  mov     ecx, 40h ; '@'; uFlags
0x1800a06a2  call    cs:__imp_LocalAlloc
0x1800a06a9  nop     dword ptr [rax+rax+00h]
0x1800a06ae  mov     r14, rax
0x1800a06b1  test    rax, rax
0x1800a06b4  jnz     short loc_1800A070E
0x1800a06b6  lea     rcx, WPP_GLOBAL_Control
0x1800a06bd  mov     rax, cs:WPP_GLOBAL_Control
0x1800a06c4  cmp     rax, rcx
0x1800a06c7  jz      short loc_1800A0704
0x1800a06c9  test    byte ptr [rax+1Ch], 8
0x1800a06cd  jz      short loc_1800A0704
0x1800a06cf  cmp     byte ptr [rax+19h], 2
0x1800a06d3  jb      short loc_1800A0704
0x1800a06d5  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800a06da  lea     edx, [r14+16h]
0x1800a06de  lea     r8, aPpconnstrparam; "\"*ppConnStrParams\""
0x1800a06e5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a06ec  mov     [rsp+8F0h+var_8D0], r8
0x1800a06f1  mov     r9d, eax
0x1800a06f4  lea     r8, WPP_5c640882e6c13d67d94d4d82c5094b20_Traceguids
0x1800a06fb  mov     rcx, [rcx+10h]
0x1800a06ff  call    WPP_SF_Ds
0x1800a0704  mov     ebx, 8007000Eh
0x1800a0709  jmp     loc_1800A068A
0x1800a070e  cmp     edi, r13d
0x1800a0711  jnb     short loc_1800A076D
0x1800a0713  mov     edx, 208h; uBytes
0x1800a0718  mov     ecx, 40h ; '@'; uFlags
0x1800a071d  call    cs:__imp_LocalAlloc
0x1800a0724  nop     dword ptr [rax+rax+00h]
0x1800a0729  mov     ecx, edi
0x1800a072b  mov     [r14+rcx*8], rax
0x1800a072f  test    rax, rax
0x1800a0732  jz      short loc_1800A0738
0x1800a0734  inc     edi
0x1800a0736  jmp     short loc_1800A070E
0x1800a0738  lea     rcx, WPP_GLOBAL_Control
0x1800a073f  mov     rax, cs:WPP_GLOBAL_Control
0x1800a0746  cmp     rax, rcx
0x1800a0749  jz      short loc_1800A0704
0x1800a074b  test    byte ptr [rax+1Ch], 8
0x1800a074f  jz      short loc_1800A0704
0x1800a0751  cmp     byte ptr [rax+19h], 2
0x1800a0755  jb      short loc_1800A0704
0x1800a0757  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800a075c  mov     edx, 17h
0x1800a0761  lea     r8, aPpconnstrparam_0; "\"*ppConnStrParams[i]\""
0x1800a0768  jmp     loc_1800A06E5
0x1800a076d  lea     rcx, aPwd_0; "Pwd="
0x1800a0774  call    cs:__imp_SysAllocString
0x1800a077b  nop     dword ptr [rax+rax+00h]
0x1800a0780  mov     rdi, rax
0x1800a0783  mov     [rsp+8F0h+var_8B8], rax
0x1800a0788  lea     rdx, asc_1800C145C; ";"
0x1800a078f  mov     rcx, r12; String
0x1800a0792  call    wcstok_mvcrt_legacy_two_parameter_form
0x1800a0797  mov     r11, rax
0x1800a079a  xor     r12d, r12d
0x1800a079d  test    rax, rax
0x1800a07a0  jz      loc_1800A0CE5
0x1800a07a6  cmp     [rax], r12w
0x1800a07aa  jz      loc_1800A0CE5
0x1800a07b0  mov     r8, rax; unsigned __int16 *
0x1800a07b3  mov     edx, 104h; unsigned __int64
0x1800a07b8  mov     rcx, [r14]; unsigned __int16 *
0x1800a07bb  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800a07c0  mov     ebx, eax
0x1800a07c2  test    eax, eax
0x1800a07c4  jns     short loc_1800A080B
0x1800a07c6  lea     rcx, WPP_GLOBAL_Control
0x1800a07cd  mov     rax, cs:WPP_GLOBAL_Control
0x1800a07d4  cmp     rax, rcx
0x1800a07d7  jz      loc_1800A0D3C
0x1800a07dd  test    byte ptr [rax+1Ch], 8
0x1800a07e1  jz      loc_1800A0D3C
0x1800a07e7  cmp     byte ptr [rax+19h], 2
0x1800a07eb  jb      loc_1800A0D3C
0x1800a07f1  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800a07f6  lea     edx, [r12+19h]
0x1800a07fb  mov     [rsp+8F0h+var_8C8], ebx
0x1800a07ff  lea     r8, aStringcchcopyP_1; "StringCchCopy(pwszConnSTr) failed"
0x1800a0806  jmp     loc_1800A0D1D
0x1800a080b  test    r11, r11
0x1800a080e  jz      short loc_1800A088A
0x1800a0810  lea     rdx, asc_1800C145C; ";"
0x1800a0817  xor     ecx, ecx; String
0x1800a0819  call    wcstok_mvcrt_legacy_two_parameter_form
0x1800a081e  mov     r11, rax
0x1800a0821  test    rax, rax
0x1800a0824  jz      short loc_1800A080B
0x1800a0826  inc     r15d
0x1800a0829  cmp     r15d, r13d
0x1800a082c  jnb     short loc_1800A080B
0x1800a082e  mov     r8, rax; unsigned __int16 *
0x1800a0831  mov     edx, 104h; unsigned __int64
0x1800a0836  mov     rcx, [r14+r15*8]; unsigned __int16 *
0x1800a083a  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800a083f  mov     ebx, eax
0x1800a0841  test    eax, eax
0x1800a0843  jns     short loc_1800A080B
0x1800a0845  lea     rcx, WPP_GLOBAL_Control
0x1800a084c  mov     rax, cs:WPP_GLOBAL_Control
0x1800a0853  cmp     rax, rcx
0x1800a0856  jz      loc_1800A0D3C
0x1800a085c  test    byte ptr [rax+1Ch], 8
0x1800a0860  jz      loc_1800A0D3C
0x1800a0866  cmp     byte ptr [rax+19h], 2
0x1800a086a  jb      loc_1800A0D3C
0x1800a0870  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800a0875  mov     edx, 1Ah
0x1800a087a  mov     [rsp+8F0h+var_8C8], ebx
0x1800a087e  lea     r8, aStringcchcopyT; "StringCchCopy(token) failed"
0x1800a0885  jmp     loc_1800A0D1D
0x1800a088a  mov     r15d, r12d
0x1800a088d  cmp     r15d, r13d
0x1800a0890  jnb     loc_1800A0B0B
0x1800a0896  mov     r12d, r15d
0x1800a0899  mov     rdx, [r14+r12*8]
0x1800a089d  lea     rcx, [rbp+7F0h+var_868]
0x1800a08a1  call    ??0?$CBaseStringT@G@@QEAA@PEBG@Z; CBaseStringT<ushort>::CBaseStringT<ushort>(ushort const *)
0x1800a08a6  nop
0x1800a08a7  mov     r8d, 1
0x1800a08ad  mov     rdx, rdi
0x1800a08b0  mov     rcx, rax
0x1800a08b3  call    ?Contains@?$CBaseStringT@G@@QEBAHPEBGH@Z; CBaseStringT<ushort>::Contains(ushort const *,int)
0x1800a08b8  mov     ebx, eax
0x1800a08ba  lea     rcx, [rbp+7F0h+var_868]
0x1800a08be  call    ??1?$CBaseStringT@G@@QEAA@XZ; CBaseStringT<ushort>::~CBaseStringT<ushort>(void)
0x1800a08c3  test    ebx, ebx
0x1800a08c5  jz      loc_1800A0A92
0x1800a08cb  mov     rdx, [r14+r12*8]; unsigned __int16 *
0x1800a08cf  lea     rcx, [rsp+8F0h+var_888]; this
0x1800a08d4  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x1800a08d9  nop
0x1800a08da  mov     rdx, [rax]
0x1800a08dd  xor     eax, eax
0x1800a08df  test    rdx, rdx
0x1800a08e2  jnz     short loc_1800A08E9
0x1800a08e4  mov     r8d, eax
0x1800a08e7  jmp     short loc_1800A08F7
0x1800a08e9  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800a08ed  inc     r8
0x1800a08f0  cmp     [rdx+r8*2], ax
0x1800a08f5  jnz     short loc_1800A08ED
0x1800a08f7  lea     rcx, [rsp+8F0h+var_8C0]
0x1800a08fc  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x1800a0901  nop
0x1800a0902  mov     rcx, [rsp+8F0h+var_888]; bstrString
0x1800a0907  call    cs:__imp_SysFreeString
0x1800a090e  nop     dword ptr [rax+rax+00h]
0x1800a0913  nop
0x1800a0914  mov     rax, [rsp+8F0h+var_8C0]
0x1800a0919  mov     ebx, [rax-10h]
0x1800a091c  mov     rdx, rdi
0x1800a091f  lea     rcx, [rsp+8F0h+var_8A0]
0x1800a0924  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x1800a0929  nop
0x1800a092a  mov     rax, [rsp+8F0h+var_8A0]
0x1800a092f  sub     ebx, [rax-10h]
0x1800a0932  mov     ecx, 0
0x1800a0937  mov     edi, ecx
0x1800a0939  cmovns  edi, ebx
0x1800a093c  mov     rax, [rsp+8F0h+var_8C0]
0x1800a0941  mov     ebx, ecx
0x1800a0943  cmp     [rax-10h], ecx
0x1800a0946  cmovge  ebx, [rax-10h]
0x1800a094a  cmp     edi, ebx
0x1800a094c  jl      short loc_1800A095F
0x1800a094e  lea     rdx, [rsp+8F0h+var_8C0]
0x1800a0953  lea     rcx, [rsp+8F0h+var_8B0]
0x1800a0958  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x1800a095d  jmp     short loc_1800A098C
0x1800a095f  lea     rcx, [rsp+8F0h+var_8C0]
0x1800a0964  call    ?GetManager@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBAPEAUIAtlStringMgr@2@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::GetManager(void)
0x1800a0969  movsxd  rdx, ebx
0x1800a096c  movsxd  rcx, edi
0x1800a096f  sub     rdx, rcx
0x1800a0972  mov     rcx, [rsp+8F0h+var_8C0]
0x1800a0977  lea     rdx, [rcx+rdx*2]
0x1800a097b  mov     r9, rax
0x1800a097e  mov     r8d, edi
0x1800a0981  lea     rcx, [rsp+8F0h+var_8B0]
0x1800a0986  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBGHPEAUIAtlStringMgr@1@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *,int,ATL::IAtlStringMgr *)
0x1800a098b  nop
0x1800a098c  mov     rdx, [rsp+8F0h+var_8B0]
0x1800a0991  lea     rcx, [rdx-18h]
0x1800a0995  mov     rdi, [rsp+8F0h+var_8C0]
0x1800a099a  add     rdi, 0FFFFFFFFFFFFFFE8h
0x1800a099e  cmp     rcx, rdi
0x1800a09a1  jz      short loc_1800A09DF
0x1800a09a3  mov     eax, [rdi+10h]
0x1800a09a6  shr     eax, 1Fh
0x1800a09a9  test    al, al
0x1800a09ab  jnz     short loc_1800A09D0
0x1800a09ad  mov     rax, [rdi]
0x1800a09b0  cmp     [rcx], rax
0x1800a09b3  jnz     short loc_1800A09D0
0x1800a09b5  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x1800a09ba  mov     rbx, rax
0x1800a09bd  mov     rcx, rdi; this
0x1800a09c0  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800a09c5  lea     rax, [rbx+18h]
0x1800a09c9  mov     [rsp+8F0h+var_8C0], rax
0x1800a09ce  jmp     short loc_1800A09DF
0x1800a09d0  mov     r8d, [rdx-10h]
0x1800a09d4  lea     rcx, [rsp+8F0h+var_8C0]
0x1800a09d9  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x1800a09de  nop
0x1800a09df  lea     rcx, [rsp+8F0h+var_8B0]
0x1800a09e4  call    ??1?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::~CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x1800a09e9  lea     rcx, [rsp+8F0h+var_8C0]
0x1800a09ee  call    ?AllocSysString@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBAPEAGXZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::AllocSysString(void)
0x1800a09f3  mov     rcx, [rsp+8F0h+var_880]
0x1800a09f8  mov     [rcx], rax
0x1800a09fb  mov     rdi, [rsp+8F0h+var_8B8]
0x1800a0a00  xor     eax, eax
0x1800a0a02  test    rdi, rdi
0x1800a0a05  jnz     short loc_1800A0A0C
0x1800a0a07  mov     r8d, eax
0x1800a0a0a  jmp     short loc_1800A0A1A
0x1800a0a0c  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800a0a10  inc     r8
0x1800a0a13  cmp     [rdi+r8*2], ax
0x1800a0a18  jnz     short loc_1800A0A10
0x1800a0a1a  mov     rdx, rdi
0x1800a0a1d  lea     rcx, [rsp+8F0h+var_8C0]
0x1800a0a22  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x1800a0a27  mov     rax, [rsp+8F0h+var_8C0]
0x1800a0a2c  mov     ebx, [rax-10h]
0x1800a0a2f  lea     rdx, aPasswordReplac; "{password_replaced}"
0x1800a0a36  lea     rcx, [rsp+8F0h+var_8A8]
0x1800a0a3b  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x1800a0a40  nop
0x1800a0a41  mov     r8, [rsp+8F0h+var_8A8]
0x1800a0a46  mov     edx, ebx
0x1800a0a48  lea     rcx, [rsp+8F0h+var_8C0]
0x1800a0a4d  call    ?Insert@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAHHPEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Insert(int,ushort const *)
0x1800a0a52  lea     rcx, [rsp+8F0h+var_8C0]
  ... truncated ...
```
