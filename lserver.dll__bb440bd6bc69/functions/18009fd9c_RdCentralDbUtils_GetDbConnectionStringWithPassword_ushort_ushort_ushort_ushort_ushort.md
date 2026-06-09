# RdCentralDbUtils::GetDbConnectionStringWithPassword(ushort *,ushort *,ushort *,ushort *,ushort * *)

- ea: `0x18009fd9c`
- end: `0x1800a059f`
- name: `?GetDbConnectionStringWithPassword@RdCentralDbUtils@@SAJPEAG000PEAPEAG@Z`
- size: `2051`
- prototype: `__int64 __usercall@<rax>(wchar_t *String1@<rcx>, unsigned __int16 *@<rdx>, unsigned __int16 *@<r8>, unsigned __int16 *@<r9>, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `23`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x180099768`

## callees

- `0x180002ce0`
- `0x180005665`
- `0x18000cf54`
- `0x18000cff0`
- `0x18001ad74`
- `0x180077e9c`
- `0x180078a94`
- `0x1800790c0`
- `0x1800861cc`
- `0x18008625c`
- `0x180086464`
- `0x180086660`
- `0x180087484`
- `0x180088b08`
- `0x180088e68`
- `0x180098314`
- `0x1800983d0`
- `0x18009872c`
- `0x18009a200`
- `0x18009f6b4`
- `0x18009fcf8`
- `0x18009fd9c`
- `0x1800a0fb0`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18009ffff`
- `OLEAUT32!__imp_SysAllocString` at `0x1800a04bd`
- `OLEAUT32!__imp_SysAllocString` at `0x18009ffff`
- `OLEAUT32!__imp_SysAllocString` at `0x1800a04bd`
- `OLEAUT32!__imp_SysFreeString` at `0x18009fe2e`
- `OLEAUT32!__imp_SysFreeString` at `0x1800a020f`
- `OLEAUT32!__imp_SysFreeString` at `0x1800a0247`
- `OLEAUT32!__imp_SysFreeString` at `0x1800a04db`
- `OLEAUT32!__imp_SysFreeString` at `0x1800a04ef`
- `OLEAUT32!__imp_SysFreeString` at `0x1800a0508`
- `OLEAUT32!__imp_SysFreeString` at `0x1800a051e`
- `OLEAUT32!__imp_SysFreeString` at `0x18009fe2e`
- `OLEAUT32!__imp_SysFreeString` at `0x1800a020f`
- `OLEAUT32!__imp_SysFreeString` at `0x1800a0247`
- `OLEAUT32!__imp_SysFreeString` at `0x1800a04db`
- `OLEAUT32!__imp_SysFreeString` at `0x1800a04ef`
- `OLEAUT32!__imp_SysFreeString` at `0x1800a0508`
- `OLEAUT32!__imp_SysFreeString` at `0x1800a051e`
- `KERNEL32!LocalAlloc` at `0x18009fea8`
- `KERNEL32!LocalAlloc` at `0x18009ff27`
- `KERNEL32!LocalAlloc` at `0x18009fea8`
- `KERNEL32!LocalAlloc` at `0x18009ff27`
- `KERNEL32!LocalFree` at `0x1800a053f`
- `KERNEL32!LocalFree` at `0x1800a055b`
- `KERNEL32!LocalFree` at `0x1800a053f`
- `KERNEL32!LocalFree` at `0x1800a055b`

## string_xrefs

- `0x18009ff7a`: `System\CurrentControlSet\Services\Tssdis\Parameters\Secrets`
- `0x1800a0167`: `StringCchCopy(token) failed`
- `0x1800a00c9`: `StringCchCopy(pwszConnSTr) failed`
- `0x1800a03b3`: `StringCchCopy(pwszConnSTr) failed`
- `0x1800a02d0`: `StringCchCopy(pswdStr) failed`
- `0x1800a0334`: `StringCchCopy(pwszPswdStr) failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall RdCentralDbUtils::GetDbConnectionStringWithPassword(
        wchar_t *String1,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4,
        unsigned __int16 **a5)
{
  unsigned __int16 **v7; // r14
  __int64 v8; // r15
  ATL::CComBSTR *v9; // rax
  OLECHAR *v10; // rbx
  unsigned int ConnectionStringParamsNumber; // eax
  __int64 v12; // r13
  unsigned int v13; // eax
  int v14; // ebx
  __int64 v15; // rdi
  unsigned int CurrentThreadActivityIdPrefix; // eax
  int v17; // edx
  const char *v18; // rcx
  unsigned int i; // ebx
  unsigned __int16 *v20; // rax
  unsigned int v21; // eax
  wchar_t **v22; // r8
  unsigned __int16 *v23; // r12
  unsigned int v24; // eax
  wchar_t *v25; // rax
  unsigned int v26; // esi
  wchar_t **v27; // r8
  wchar_t *v28; // r11
  unsigned int v29; // eax
  int v30; // edx
  const char *v31; // r8
  wchar_t *v32; // rax
  __int64 v33; // rax
  int v34; // ebx
  __int64 v35; // rdx
  __int64 v36; // r8
  unsigned int v37; // ebx
  _QWORD *v38; // rax
  unsigned int v39; // eax
  unsigned int v40; // eax
  int v41; // edx
  const char *v42; // r8
  unsigned int j; // esi
  BSTR v44; // rax
  HLOCAL *v45; // rsi
  __int64 v47; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v48; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int16 *v49; // [rsp+40h] [rbp-C0h]
  BSTR v50; // [rsp+48h] [rbp-B8h] BYREF
  BSTR v51; // [rsp+50h] [rbp-B0h]
  BSTR bstrString; // [rsp+58h] [rbp-A8h] BYREF
  BSTR v53; // [rsp+60h] [rbp-A0h] BYREF
  BSTR v54; // [rsp+68h] [rbp-98h] BYREF
  unsigned __int16 **v55; // [rsp+70h] [rbp-90h]
  BSTR v56; // [rsp+78h] [rbp-88h]
  _BYTE v57[48]; // [rsp+80h] [rbp-80h] BYREF
  OLECHAR psz[1024]; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int16 v59[264]; // [rsp+8B0h] [rbp+7B0h] BYREF

  v55 = a5;
  v50 = 0;
  v7 = 0;
  LODWORD(v8) = 0;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v47);
  v51 = 0;
  memset_0(psz, 0, sizeof(psz));
  v9 = (ATL::CComBSTR *)ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&bstrString, a3);
  v10 = ATL::CComBSTR::Copy(v9);
  v56 = v10;
  SysFreeString(bstrString);
  ConnectionStringParamsNumber = RdCentralDbUtils::GetConnectionStringParamsNumber(v10);
  v12 = ConnectionStringParamsNumber;
  if ( ConnectionStringParamsNumber )
  {
    v15 = ConnectionStringParamsNumber;
    v7 = (unsigned __int16 **)LocalAlloc(0x40u, 8LL * ConnectionStringParamsNumber);
    if ( v7 )
    {
      for ( i = 0; i < (unsigned int)v12; ++i )
      {
        v20 = (unsigned __int16 *)LocalAlloc(0x40u, 0x208u);
        v7[i] = v20;
        if ( !v20 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
            v17 = 34;
            v18 = "\"*ppConnStrParams[i]\"";
            goto LABEL_12;
          }
          goto LABEL_13;
        }
      }
      v14 = RdCentralDbUtils::DecryptCredsData(
              String1,
              &v50,
              L"System\\CurrentControlSet\\Services\\Tssdis\\Parameters\\Secrets");
      if ( v14 < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v21 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_DsD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            35,
            (unsigned int)WPP_5c640882e6c13d67d94d4d82c5094b20_Traceguids,
            v21,
            (__int64)"DecryptCredsData failed!",
            v14);
        }
        goto LABEL_95;
      }
      v23 = SysAllocString(L"Pwd=");
      v49 = v23;
      if ( !v23 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v24 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_Ds(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            36,
            (unsigned int)WPP_5c640882e6c13d67d94d4d82c5094b20_Traceguids,
            v24,
            (__int64)"\"pwszSbDbPasswordTag\"");
        }
        goto LABEL_13;
      }
      v25 = wcstok_mvcrt_legacy_two_parameter_form(a3, L";", v22);
      v26 = 0;
      v14 = StringCchCopyW(*v7, 0x104u, v25);
      if ( v14 >= 0 )
      {
        while ( 1 )
        {
          if ( !v28 )
          {
            while ( v26 <= (unsigned int)v8 )
            {
              v33 = CBaseStringT<unsigned short>::CBaseStringT<unsigned short>(v57, v7[v26]);
              v34 = CBaseStringT<unsigned short>::Contains(v33, v49, 1);
              CBaseStringT<unsigned short>::~CBaseStringT<unsigned short>(v57);
              if ( v34 )
              {
                v14 = StringCchCopyW(v59, 0x104u, v7[v26]);
                if ( v14 < 0 )
                {
                  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                    || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
                    || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                  {
                    goto LABEL_91;
                  }
                  v40 = RdpWppGetCurrentThreadActivityIdPrefix();
                  v41 = 40;
                  v42 = "StringCchCopy(pwszPswdStr) failed";
                  goto LABEL_65;
                }
                v35 = *(_QWORD *)ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&v53, v49);
                if ( v35 )
                {
                  v36 = -1;
                  do
                    ++v36;
                  while ( *(_WORD *)(v35 + 2 * v36) );
                }
                else
                {
                  v36 = 0;
                }
                ATL::CSimpleStringT<unsigned short,0>::SetString(&v47, v35, v36);
                SysFreeString(v53);
                v37 = *(_DWORD *)(v47 - 16);
                v38 = (_QWORD *)ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&v54, v50);
                ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
                  &v48,
                  *v38);
                SysFreeString(v54);
                ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Insert(
                  &v47,
                  v37,
                  v48);
                v51 = (BSTR)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::AllocSysString(&v47);
                v14 = StringCchCopyW(v7[v26], 0x104u, v51);
                if ( v14 < 0 )
                {
                  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                  {
                    v39 = RdpWppGetCurrentThreadActivityIdPrefix();
                    WPP_SF_DsD(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      41,
                      (unsigned int)WPP_5c640882e6c13d67d94d4d82c5094b20_Traceguids,
                      v39,
                      (__int64)"StringCchCopy(pswdStr) failed",
                      v14);
                  }
                  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::~CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v48);
                  goto LABEL_91;
                }
                ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::~CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v48);
              }
              ++v26;
            }
            v14 = StringCchCopyW(psz, 0x104u, *v7);
            if ( v14 >= 0 )
            {
              v14 = StringCchCatW(psz, 0x104u, L";");
              if ( v14 >= 0 )
              {
                for ( j = 1; ; ++j )
                {
                  if ( j >= (unsigned int)v12 )
                  {
                    v44 = SysAllocString(psz);
                    *v55 = v44;
                    goto LABEL_91;
                  }
                  v14 = StringCchCatW(psz, 0x104u, v7[j]);
                  if ( v14 < 0 )
                    break;
                  v14 = StringCchCatW(psz, 0x104u, L";");
                  if ( v14 < 0 )
                  {
                    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                    {
                      v40 = RdpWppGetCurrentThreadActivityIdPrefix();
                      v41 = 45;
                      goto LABEL_76;
                    }
                    goto LABEL_91;
                  }
                }
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  v40 = RdpWppGetCurrentThreadActivityIdPrefix();
                  v41 = 44;
                  v42 = "StringCchCat(pwszConnStr) failed";
                  goto LABEL_65;
                }
LABEL_91:
                if ( v51 )
                  SysFreeString(v51);
                v23 = v49;
                goto LABEL_94;
              }
              if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
                || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
              {
                goto LABEL_91;
              }
              v40 = RdpWppGetCurrentThreadActivityIdPrefix();
              v41 = 43;
LABEL_76:
              v42 = "StringCchCat(;) failed";
            }
            else
            {
              if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
                || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
              {
                goto LABEL_91;
              }
              v40 = RdpWppGetCurrentThreadActivityIdPrefix();
              v41 = 42;
              v42 = "StringCchCopy(pwszConnSTr) failed";
            }
LABEL_65:
            WPP_SF_DsD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              v41,
              (unsigned int)WPP_5c640882e6c13d67d94d4d82c5094b20_Traceguids,
              v40,
              (__int64)v42,
              v14);
            goto LABEL_91;
          }
          v32 = wcstok_mvcrt_legacy_two_parameter_form(0, L";", v27);
          v28 = v32;
          if ( v32 )
          {
            v8 = (unsigned int)(v8 + 1);
            if ( (unsigned int)v8 < (unsigned int)v12 )
            {
              v14 = StringCchCopyW(v7[v8], 0x104u, v32);
              if ( v14 < 0 )
                break;
            }
          }
        }
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v29 = RdpWppGetCurrentThreadActivityIdPrefix();
          v30 = 39;
          v31 = "StringCchCopy(token) failed";
LABEL_37:
          WPP_SF_DsD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v30,
            (unsigned int)WPP_5c640882e6c13d67d94d4d82c5094b20_Traceguids,
            v29,
            (__int64)v31,
            v14);
        }
      }
      else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
             && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
             && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v29 = RdpWppGetCurrentThreadActivityIdPrefix();
        v30 = 38;
        v31 = "StringCchCopy(pwszConnSTr) failed";
        goto LABEL_37;
      }
LABEL_94:
      SysFreeString(v23);
    }
    else
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v17 = 33;
        v18 = "\"*ppConnStrParams\"";
LABEL_12:
        WPP_SF_Ds(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v17,
          (unsigned int)WPP_5c640882e6c13d67d94d4d82c5094b20_Traceguids,
          CurrentThreadActivityIdPrefix,
          (__int64)v18);
      }
LABEL_13:
      v14 = -2147024882;
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v13 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, WPP_5c640882e6c13d67d94d4d82c5094b20_Traceguids, v13);
    }
    v14 = -2147467259;
    v15 = v12;
  }
LABEL_95:
  if ( v50 )
    SysFreeString(v50);
  if ( v56 )
    SysFreeString(v56);
  if ( v7 )
  {
    if ( (_DWORD)v12 )
    {
      v45 = (HLOCAL *)v7;
      do
      {
        if ( *v45 )
        {
          LocalFree(*v45);
          *v45 = 0;
        }
        ++v45;
        --v15;
      }
      while ( v15 );
    }
    LocalFree(v7);
  }
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::~CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v47);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x18009fd9c  mov     [rsp-8+arg_8], rbx
0x18009fda1  push    rbp
0x18009fda2  push    rsi
0x18009fda3  push    rdi
0x18009fda4  push    r12
0x18009fda6  push    r13
0x18009fda8  push    r14
0x18009fdaa  push    r15
0x18009fdac  lea     rbp, [rsp-9D0h]
0x18009fdb4  sub     rsp, 0AD0h
0x18009fdbb  mov     rax, cs:__security_cookie
0x18009fdc2  xor     rax, rsp
0x18009fdc5  mov     [rbp+0A00h+var_40], rax
0x18009fdcc  mov     rsi, r8
0x18009fdcf  mov     r12, rcx
0x18009fdd2  mov     rax, [rbp+0A00h+arg_20]
0x18009fdd9  mov     [rsp+0B00h+var_A90], rax
0x18009fdde  xor     edi, edi
0x18009fde0  mov     [rsp+0B00h+var_AB8], rdi
0x18009fde5  mov     r14d, edi
0x18009fde8  mov     r15d, edi
0x18009fdeb  lea     rcx, [rsp+0B00h+var_AD0]
0x18009fdf0  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18009fdf5  nop
0x18009fdf6  mov     [rsp+0B00h+var_AB0], rdi
0x18009fdfb  xor     edx, edx; Val
0x18009fdfd  mov     r8d, 800h; Size
0x18009fe03  lea     rcx, [rbp+0A00h+psz]; void *
0x18009fe07  call    memset_0
0x18009fe0c  mov     rdx, rsi; unsigned __int16 *
0x18009fe0f  lea     rcx, [rsp+0B00h+bstrString]; this
0x18009fe14  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x18009fe19  mov     rcx, rax; this
0x18009fe1c  call    ?Copy@CComBSTR@ATL@@QEBAPEAGXZ; ATL::CComBSTR::Copy(void)
0x18009fe21  mov     rbx, rax
0x18009fe24  mov     [rsp+0B00h+var_A88], rax
0x18009fe29  mov     rcx, [rsp+0B00h+bstrString]; bstrString
0x18009fe2e  call    cs:__imp_SysFreeString
0x18009fe35  nop     dword ptr [rax+rax+00h]
0x18009fe3a  nop
0x18009fe3b  mov     rcx, rbx; unsigned __int16 *
0x18009fe3e  call    ?GetConnectionStringParamsNumber@RdCentralDbUtils@@CAKPEAG@Z; RdCentralDbUtils::GetConnectionStringParamsNumber(ushort *)
0x18009fe43  mov     r13d, eax
0x18009fe46  test    eax, eax
0x18009fe48  jnz     short loc_18009FE98
0x18009fe4a  lea     rcx, WPP_GLOBAL_Control
0x18009fe51  mov     rdx, cs:WPP_GLOBAL_Control
0x18009fe58  cmp     rdx, rcx
0x18009fe5b  jz      short loc_18009FE8B
0x18009fe5d  test    byte ptr [rdx+1Ch], 1
0x18009fe61  jz      short loc_18009FE8B
0x18009fe63  cmp     byte ptr [rdx+19h], 2
0x18009fe67  jb      short loc_18009FE8B
0x18009fe69  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18009fe6e  mov     rcx, cs:WPP_GLOBAL_Control
0x18009fe75  lea     edx, [rdi+20h]
0x18009fe78  mov     r9d, eax
0x18009fe7b  lea     r8, WPP_5c640882e6c13d67d94d4d82c5094b20_Traceguids
0x18009fe82  mov     rcx, [rcx+10h]
0x18009fe86  call    WPP_SF_D
0x18009fe8b  mov     ebx, 80004005h
0x18009fe90  mov     rdi, r13
0x18009fe93  jmp     loc_1800A04FB
0x18009fe98  mov     rdi, r13
0x18009fe9b  lea     rdx, ds:0[r13*8]; uBytes
0x18009fea3  mov     ecx, 40h ; '@'; uFlags
0x18009fea8  call    cs:__imp_LocalAlloc
0x18009feaf  nop     dword ptr [rax+rax+00h]
0x18009feb4  mov     r14, rax
0x18009feb7  xor     eax, eax
0x18009feb9  test    r14, r14
0x18009febc  jnz     short loc_18009FF16
0x18009febe  lea     rcx, WPP_GLOBAL_Control
0x18009fec5  mov     rax, cs:WPP_GLOBAL_Control
0x18009fecc  cmp     rax, rcx
0x18009fecf  jz      short loc_18009FF0C
0x18009fed1  test    byte ptr [rax+1Ch], 8
0x18009fed5  jz      short loc_18009FF0C
0x18009fed7  cmp     byte ptr [rax+19h], 2
0x18009fedb  jb      short loc_18009FF0C
0x18009fedd  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18009fee2  lea     edx, [r14+21h]
0x18009fee6  lea     rcx, aPpconnstrparam; "\"*ppConnStrParams\""
0x18009feed  mov     r9d, eax
0x18009fef0  mov     rax, cs:WPP_GLOBAL_Control
0x18009fef7  mov     [rsp+0B00h+var_AE0], rcx
0x18009fefc  mov     rcx, [rax+10h]
0x18009ff00  lea     r8, WPP_5c640882e6c13d67d94d4d82c5094b20_Traceguids
0x18009ff07  call    WPP_SF_Ds
0x18009ff0c  mov     ebx, 8007000Eh
0x18009ff11  jmp     loc_1800A04FB
0x18009ff16  mov     ebx, eax
0x18009ff18  cmp     ebx, r13d
0x18009ff1b  jnb     short loc_18009FF7A
0x18009ff1d  mov     edx, 208h; uBytes
0x18009ff22  mov     ecx, 40h ; '@'; uFlags
0x18009ff27  call    cs:__imp_LocalAlloc
0x18009ff2e  nop     dword ptr [rax+rax+00h]
0x18009ff33  mov     rcx, rax
0x18009ff36  mov     eax, ebx
0x18009ff38  mov     [r14+rax*8], rcx
0x18009ff3c  test    rcx, rcx
0x18009ff3f  jz      short loc_18009FF45
0x18009ff41  inc     ebx
0x18009ff43  jmp     short loc_18009FF18
0x18009ff45  lea     rcx, WPP_GLOBAL_Control
0x18009ff4c  mov     rax, cs:WPP_GLOBAL_Control
0x18009ff53  cmp     rax, rcx
0x18009ff56  jz      short loc_18009FF0C
0x18009ff58  test    byte ptr [rax+1Ch], 8
0x18009ff5c  jz      short loc_18009FF0C
0x18009ff5e  cmp     byte ptr [rax+19h], 2
0x18009ff62  jb      short loc_18009FF0C
0x18009ff64  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18009ff69  mov     edx, 22h ; '"'
0x18009ff6e  lea     rcx, aPpconnstrparam_0; "\"*ppConnStrParams[i]\""
0x18009ff75  jmp     loc_18009FEED
0x18009ff7a  lea     r8, aSystemCurrentc_3; "System\\CurrentControlSet\\Services\\Ts"...
0x18009ff81  lea     rdx, [rsp+0B00h+var_AB8]; unsigned __int16 **
0x18009ff86  mov     rcx, r12; String1
0x18009ff89  call    ?DecryptCredsData@RdCentralDbUtils@@CAJPEAGPEAPEAG0@Z; RdCentralDbUtils::DecryptCredsData(ushort *,ushort * *,ushort *)
0x18009ff8e  mov     ebx, eax
0x18009ff90  test    eax, eax
0x18009ff92  jns     short loc_18009FFF8
0x18009ff94  lea     rcx, WPP_GLOBAL_Control
0x18009ff9b  mov     rax, cs:WPP_GLOBAL_Control
0x18009ffa2  cmp     rax, rcx
0x18009ffa5  jz      loc_1800A04FB
0x18009ffab  test    byte ptr [rax+1Ch], 8
0x18009ffaf  jz      loc_1800A04FB
0x18009ffb5  cmp     byte ptr [rax+19h], 2
0x18009ffb9  jb      loc_1800A04FB
0x18009ffbf  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18009ffc4  mov     rcx, cs:WPP_GLOBAL_Control
0x18009ffcb  mov     edx, 23h ; '#'
0x18009ffd0  mov     [rsp+0B00h+var_AD8], ebx
0x18009ffd4  lea     r8, aDecryptcredsda; "DecryptCredsData failed!"
0x18009ffdb  mov     [rsp+0B00h+var_AE0], r8
0x18009ffe0  mov     r9d, eax
0x18009ffe3  lea     r8, WPP_5c640882e6c13d67d94d4d82c5094b20_Traceguids
0x18009ffea  mov     rcx, [rcx+10h]
0x18009ffee  call    WPP_SF_DsD
0x18009fff3  jmp     loc_1800A04FB
0x18009fff8  lea     rcx, aPwd_0; "Pwd="
0x18009ffff  call    cs:__imp_SysAllocString
0x1800a0006  nop     dword ptr [rax+rax+00h]
0x1800a000b  mov     r12, rax
0x1800a000e  mov     [rsp+0B00h+var_AC0], rax
0x1800a0013  test    rax, rax
0x1800a0016  jnz     short loc_1800A006C
0x1800a0018  lea     rcx, WPP_GLOBAL_Control
0x1800a001f  mov     rax, cs:WPP_GLOBAL_Control
0x1800a0026  cmp     rax, rcx
0x1800a0029  jz      loc_18009FF0C
0x1800a002f  test    byte ptr [rax+1Ch], 8
0x1800a0033  jz      loc_18009FF0C
0x1800a0039  cmp     byte ptr [rax+19h], 2
0x1800a003d  jb      loc_18009FF0C
0x1800a0043  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800a0048  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a004f  lea     edx, [r12+24h]
0x1800a0054  lea     r8, aPwszsbdbpasswo; "\"pwszSbDbPasswordTag\""
0x1800a005b  mov     [rsp+0B00h+var_AE0], r8
0x1800a0060  mov     r9d, eax
0x1800a0063  mov     rcx, [rcx+10h]
0x1800a0067  jmp     loc_18009FF00
0x1800a006c  lea     rdx, asc_1800C145C; ";"
0x1800a0073  mov     rcx, rsi; String
0x1800a0076  call    wcstok_mvcrt_legacy_two_parameter_form
0x1800a007b  mov     r11, rax
0x1800a007e  xor     esi, esi
0x1800a0080  mov     r8, rax; unsigned __int16 *
0x1800a0083  mov     edx, 104h; unsigned __int64
0x1800a0088  mov     rcx, [r14]; unsigned __int16 *
0x1800a008b  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800a0090  mov     ebx, eax
0x1800a0092  test    eax, eax
0x1800a0094  jns     short loc_1800A00F8
0x1800a0096  lea     rcx, WPP_GLOBAL_Control
0x1800a009d  mov     rax, cs:WPP_GLOBAL_Control
0x1800a00a4  cmp     rax, rcx
0x1800a00a7  jz      loc_1800A04EC
0x1800a00ad  test    byte ptr [rax+1Ch], 8
0x1800a00b1  jz      loc_1800A04EC
0x1800a00b7  cmp     byte ptr [rax+19h], 2
0x1800a00bb  jb      loc_1800A04EC
0x1800a00c1  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800a00c6  lea     edx, [rsi+26h]
0x1800a00c9  lea     r8, aStringcchcopyP_1; "StringCchCopy(pwszConnSTr) failed"
0x1800a00d0  mov     [rsp+0B00h+var_AD8], ebx
0x1800a00d4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a00db  mov     [rsp+0B00h+var_AE0], r8
0x1800a00e0  mov     r9d, eax
0x1800a00e3  lea     r8, WPP_5c640882e6c13d67d94d4d82c5094b20_Traceguids
0x1800a00ea  mov     rcx, [rcx+10h]
0x1800a00ee  call    WPP_SF_DsD
0x1800a00f3  jmp     loc_1800A04EC
0x1800a00f8  test    r11, r11
0x1800a00fb  jz      short loc_1800A0173
0x1800a00fd  lea     rdx, asc_1800C145C; ";"
0x1800a0104  xor     ecx, ecx; String
0x1800a0106  call    wcstok_mvcrt_legacy_two_parameter_form
0x1800a010b  mov     r11, rax
0x1800a010e  test    rax, rax
0x1800a0111  jz      short loc_1800A00F8
0x1800a0113  inc     r15d
0x1800a0116  cmp     r15d, r13d
0x1800a0119  jnb     short loc_1800A00F8
0x1800a011b  mov     r8, rax; unsigned __int16 *
0x1800a011e  mov     edx, 104h; unsigned __int64
0x1800a0123  mov     rcx, [r14+r15*8]; unsigned __int16 *
0x1800a0127  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800a012c  mov     ebx, eax
0x1800a012e  test    eax, eax
0x1800a0130  jns     short loc_1800A00F8
0x1800a0132  lea     rcx, WPP_GLOBAL_Control
0x1800a0139  mov     rax, cs:WPP_GLOBAL_Control
0x1800a0140  cmp     rax, rcx
0x1800a0143  jz      loc_1800A04EC
0x1800a0149  test    byte ptr [rax+1Ch], 8
0x1800a014d  jz      loc_1800A04EC
0x1800a0153  cmp     byte ptr [rax+19h], 2
0x1800a0157  jb      loc_1800A04EC
0x1800a015d  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800a0162  mov     edx, 27h ; '''
0x1800a0167  lea     r8, aStringcchcopyT; "StringCchCopy(token) failed"
0x1800a016e  jmp     loc_1800A00D0
0x1800a0173  cmp     esi, r15d
0x1800a0176  ja      loc_1800A0363
0x1800a017c  mov     r12d, esi
0x1800a017f  mov     rdx, [r14+r12*8]
0x1800a0183  lea     rcx, [rbp+0A00h+var_A80]
0x1800a0187  call    ??0?$CBaseStringT@G@@QEAA@PEBG@Z; CBaseStringT<ushort>::CBaseStringT<ushort>(ushort const *)
0x1800a018c  nop
0x1800a018d  mov     r8d, 1
0x1800a0193  mov     rdx, [rsp+0B00h+var_AC0]
0x1800a0198  mov     rcx, rax
0x1800a019b  call    ?Contains@?$CBaseStringT@G@@QEBAHPEBGH@Z; CBaseStringT<ushort>::Contains(ushort const *,int)
0x1800a01a0  mov     ebx, eax
0x1800a01a2  lea     rcx, [rbp+0A00h+var_A80]
0x1800a01a6  call    ??1?$CBaseStringT@G@@QEAA@XZ; CBaseStringT<ushort>::~CBaseStringT<ushort>(void)
0x1800a01ab  test    ebx, ebx
0x1800a01ad  jz      loc_1800A0295
0x1800a01b3  mov     r8, [r14+r12*8]; unsigned __int16 *
0x1800a01b7  mov     edx, 104h; unsigned __int64
0x1800a01bc  lea     rcx, [rbp+0A00h+var_250]; unsigned __int16 *
0x1800a01c3  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800a01c8  mov     ebx, eax
0x1800a01ca  test    eax, eax
0x1800a01cc  js      loc_1800A02FF
0x1800a01d2  mov     rdx, [rsp+0B00h+var_AC0]; unsigned __int16 *
0x1800a01d7  lea     rcx, [rsp+0B00h+var_AA0]; this
0x1800a01dc  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x1800a01e1  nop
0x1800a01e2  mov     rdx, [rax]
0x1800a01e5  xor     eax, eax
0x1800a01e7  test    rdx, rdx
0x1800a01ea  jnz     short loc_1800A01F1
0x1800a01ec  mov     r8d, eax
0x1800a01ef  jmp     short loc_1800A01FF
0x1800a01f1  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800a01f5  inc     r8
0x1800a01f8  cmp     [rdx+r8*2], ax
0x1800a01fd  jnz     short loc_1800A01F5
0x1800a01ff  lea     rcx, [rsp+0B00h+var_AD0]
0x1800a0204  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x1800a0209  nop
0x1800a020a  mov     rcx, [rsp+0B00h+var_AA0]; bstrString
0x1800a020f  call    cs:__imp_SysFreeString
0x1800a0216  nop     dword ptr [rax+rax+00h]
0x1800a021b  nop
0x1800a021c  mov     rax, [rsp+0B00h+var_AD0]
0x1800a0221  mov     ebx, [rax-10h]
0x1800a0224  mov     rdx, [rsp+0B00h+var_AB8]; unsigned __int16 *
0x1800a0229  lea     rcx, [rsp+0B00h+var_A98]; this
0x1800a022e  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x1800a0233  nop
0x1800a0234  mov     rdx, [rax]
0x1800a0237  lea     rcx, [rsp+0B00h+var_AC8]
0x1800a023c  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x1800a0241  nop
0x1800a0242  mov     rcx, [rsp+0B00h+var_A98]; bstrString
0x1800a0247  call    cs:__imp_SysFreeString
0x1800a024e  nop     dword ptr [rax+rax+00h]
0x1800a0253  nop
0x1800a0254  mov     r8, [rsp+0B00h+var_AC8]
0x1800a0259  mov     edx, ebx
0x1800a025b  lea     rcx, [rsp+0B00h+var_AD0]
0x1800a0260  call    ?Insert@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAHHPEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Insert(int,ushort const *)
0x1800a0265  lea     rcx, [rsp+0B00h+var_AD0]
0x1800a026a  call    ?AllocSysString@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBAPEAGXZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::AllocSysString(void)
0x1800a026f  mov     [rsp+0B00h+var_AB0], rax
0x1800a0274  mov     r8, rax; unsigned __int16 *
0x1800a0277  mov     edx, 104h; unsigned __int64
0x1800a027c  mov     rcx, [r14+r12*8]; unsigned __int16 *
0x1800a0280  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800a0285  mov     ebx, eax
0x1800a0287  test    eax, eax
0x1800a0289  js      short loc_1800A029C
0x1800a028b  lea     rcx, [rsp+0B00h+var_AC8]
  ... truncated ...
```
