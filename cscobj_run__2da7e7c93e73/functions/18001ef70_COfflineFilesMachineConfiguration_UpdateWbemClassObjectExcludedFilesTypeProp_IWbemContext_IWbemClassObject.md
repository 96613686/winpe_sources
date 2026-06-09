# COfflineFilesMachineConfiguration::UpdateWbemClassObjectExcludedFilesTypeProp(IWbemContext *,IWbemClassObject *)

- ea: `0x18001ef70`
- end: `0x18001f1be`
- name: `?UpdateWbemClassObjectExcludedFilesTypeProp@COfflineFilesMachineConfiguration@@CAJPEAUIWbemContext@@PEAUIWbemClassObject@@@Z`
- size: `590`
- prototype: `__int64 __fastcall(struct IWbemContext *, struct IWbemClassObject *)`
- caller_count: `1`
- callee_count: `18`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180021b60`

## callees

- `0x1800140c8`
- `0x18001957c`
- `0x18001c868`
- `0x18001c8f8`
- `0x18001c938`
- `0x18001c99c`
- `0x18001cb6c`
- `0x18001cbf0`
- `0x18001cc7c`
- `0x18001ce64`
- `0x18001d364`
- `0x18001d74c`
- `0x18001da18`
- `0x18001de98`
- `0x18001df5c`
- `0x18001e048`
- `0x18001ef70`
- `0x1800296a0`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18001f0a6`
- `OLEAUT32!__imp_SysFreeString` at `0x18001f0a6`
- `OLEAUT32!__imp_VariantInit` at `0x18001ef90`
- `OLEAUT32!__imp_VariantInit` at `0x18001ef90`
- `OLEAUT32!__imp_VariantClear` at `0x18001f1a3`
- `OLEAUT32!__imp_VariantClear` at `0x18001f1a3`

## pseudocode

```c
__int64 __fastcall COfflineFilesMachineConfiguration::UpdateWbemClassObjectExcludedFilesTypeProp(
        struct IWbemContext *a1,
        struct IWbemClassObject *a2)
{
  unsigned int v3; // eax
  int UserStateSettingForWbemClassObject; // ebx
  __int64 v5; // r8
  _QWORD *v6; // rax
  unsigned __int16 *v7; // rbx
  int *v8; // rdi
  unsigned __int16 *v9; // rcx
  __int64 v10; // rbx
  __int64 i; // rcx
  __int64 v12; // r8
  unsigned __int16 *v13; // rdi
  __int64 v14; // rdx
  __int64 v15; // rax
  ATL::CStringData *v16; // rcx
  __int64 v17; // rbx
  struct tagSAFEARRAY *v19; // [rsp+30h] [rbp-19h] BYREF
  __int64 v20; // [rsp+38h] [rbp-11h] BYREF
  _BYTE v21[4]; // [rsp+40h] [rbp-9h] BYREF
  int v22; // [rsp+44h] [rbp-5h]
  VARIANTARG pvarg; // [rsp+48h] [rbp-1h] BYREF
  BSTR bstrString; // [rsp+60h] [rbp+17h] BYREF
  __int64 v25; // [rsp+68h] [rbp+1Fh] BYREF
  VARIANTARG v26[2]; // [rsp+70h] [rbp+27h] BYREF
  struct IWbemContext *v27; // [rsp+B0h] [rbp+67h] BYREF
  unsigned __int16 *v28; // [rsp+C0h] [rbp+77h] BYREF
  __int64 v29; // [rsp+C8h] [rbp+7Fh] BYREF

  v27 = a1;
  VariantInit(&pvarg);
  v3 = CSCWmiConfig::AddSettingAuthorityFlag(2);
  UserStateSettingForWbemClassObject = CSCWmiConfig::GetUserStateSettingForWbemClassObject(
                                         L"ExcludedFileTypes",
                                         &pvarg,
                                         0,
                                         v3);
  if ( UserStateSettingForWbemClassObject >= 0 )
  {
    if ( pvarg.vt == 8 )
    {
      ATL::CComSafeArrayBound::`default constructor closure'((ATL::CComSafeArrayBound *)v21);
      v22 = 0;
      ATL::CComSafeArray<unsigned short *,8>::CComSafeArray<unsigned short *,8>(&v19, v21);
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
        &v29,
        pvarg.llVal);
      ATL::CSimpleStringT<unsigned short,0>::CSimpleStringT<unsigned short,0>(&v28, &ATL::g_strmgr);
      LODWORD(v27) = 0;
      v6 = (_QWORD *)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Tokenize(
                       &v29,
                       &v20,
                       v5,
                       &v27);
      v7 = v28;
      v8 = (int *)(v28 - 12);
      v9 = (unsigned __int16 *)(*v6 - 24LL);
      if ( v9 != v28 - 12 )
      {
        if ( v8[4] >= 0 && *(_QWORD *)v9 == *(_QWORD *)v8 )
        {
          v10 = ATL::CSimpleStringT<unsigned short,0>::CloneData();
          ATL::CStringData::Release((ATL::CStringData *)v8);
          v7 = (unsigned __int16 *)(v10 + 24);
          v28 = v7;
        }
        else
        {
          ATL::CSimpleStringT<unsigned short,0>::SetString(&v28, *v6, *(unsigned int *)(*v6 - 16LL));
          v7 = v28;
        }
      }
      for ( i = v20; ; i = v25 )
      {
        ATL::CStringData::Release((ATL::CStringData *)(i - 24));
        if ( !*v7 )
          break;
        v20 = *(_QWORD *)ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&bstrString, v7);
        ATL::CComSafeArray<unsigned short *,8>::Add(&v19, &v20);
        SysFreeString(bstrString);
        v13 = v7 - 12;
        v14 = *(_QWORD *)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Tokenize(
                           &v29,
                           &v25,
                           v12,
                           &v27);
        if ( (unsigned __int16 *)(v14 - 24) != v7 - 12 )
        {
          if ( *((int *)v13 + 4) >= 0 && *(_QWORD *)(v14 - 24) == *(_QWORD *)v13 )
          {
            v15 = ATL::CSimpleStringT<unsigned short,0>::CloneData();
            v16 = (ATL::CStringData *)(v7 - 12);
            v17 = v15;
            ATL::CStringData::Release(v16);
            v7 = (unsigned __int16 *)(v17 + 24);
            v28 = v7;
          }
          else
          {
            ATL::CSimpleStringT<unsigned short,0>::SetString(&v28, v14, *(unsigned int *)(v14 - 16));
            v7 = v28;
          }
        }
      }
      ATL::CComVariant::operator=(&pvarg, v19);
      ATL::CStringData::Release((ATL::CStringData *)(v7 - 12));
      ATL::CStringData::Release((ATL::CStringData *)(v29 - 24));
      ATL::CComSafeArray<unsigned short *,8>::Destroy(&v19);
    }
    v26[0].vt = 0;
    ATL::CComVariant::InternalCopy(v26, &pvarg);
    UserStateSettingForWbemClassObject = WmiProp_SetProperty(a2, L"ExcludedFileTypes", v26);
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*(_DWORD *)(WPP_GLOBAL_Control + 28LL) & 0x4000000) != 0 )
    {
      WPP_SF_SD(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        101,
        (unsigned int)WPP_a9b0d90f6b723a76085a448a6e9a8bc7_Traceguids,
        (unsigned int)L"ExcludedFileTypes",
        UserStateSettingForWbemClassObject);
    }
  }
  VariantClear(&pvarg);
  return (unsigned int)UserStateSettingForWbemClassObject;
}

```

## disassembly

```asm
0x18001ef70  mov     [rsp-8+arg_8], rbx
0x18001ef75  mov     [rsp-8+arg_0], rcx
0x18001ef7a  push    rbp
0x18001ef7b  push    rsi
0x18001ef7c  push    rdi
0x18001ef7d  lea     rbp, [rsp-47h]
0x18001ef82  sub     rsp, 90h
0x18001ef89  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18001ef8d  mov     rsi, rdx
0x18001ef90  call    cs:__imp_VariantInit
0x18001ef96  mov     ecx, 2
0x18001ef9b  call    ?AddSettingAuthorityFlag@CSCWmiConfig@@YA?AW4USERSTATE_SETTING_SOURCES@@W42@@Z; CSCWmiConfig::AddSettingAuthorityFlag(USERSTATE_SETTING_SOURCES)
0x18001efa0  mov     r9d, eax
0x18001efa3  lea     rdx, [rbp+57h+pvarg]
0x18001efa7  xor     r8d, r8d
0x18001efaa  lea     rcx, CSCWMI_STR_PROP_EXCLUDEDFILETYPES; "ExcludedFileTypes"
0x18001efb1  call    ?GetUserStateSettingForWbemClassObject@CSCWmiConfig@@YAJPEBGAEAVCComVariant@ATL@@PEAXW4USERSTATE_SETTING_SOURCES@@@Z; CSCWmiConfig::GetUserStateSettingForWbemClassObject(ushort const *,ATL::CComVariant &,void *,USERSTATE_SETTING_SOURCES)
0x18001efb6  mov     ebx, eax
0x18001efb8  test    eax, eax
0x18001efba  js      loc_18001F19F
0x18001efc0  cmp     word ptr [rbp+57h+pvarg], 8
0x18001efc5  jnz     loc_18001F13B
0x18001efcb  lea     rcx, [rbp+57h+var_60]; this
0x18001efcf  call    ??_FCComSafeArrayBound@ATL@@QEAAXXZ; ATL::CComSafeArrayBound::`default constructor closure'(void)
0x18001efd4  lea     rdx, [rbp+57h+var_60]
0x18001efd8  mov     [rbp+57h+var_5C], 0
0x18001efdf  lea     rcx, [rbp+57h+var_70]
0x18001efe3  call    ??0?$CComSafeArray@PEAG$07@ATL@@QEAA@PEBUtagSAFEARRAYBOUND@@I@Z; ATL::CComSafeArray<ushort *,8>::CComSafeArray<ushort *,8>(tagSAFEARRAYBOUND const *,uint)
0x18001efe8  mov     rdx, qword ptr [rbp+57h+pvarg+8]
0x18001efec  lea     rcx, [rbp+57h+arg_18]
0x18001eff0  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x18001eff5  lea     rdx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18001effc  lea     rcx, [rbp+57h+arg_10]
0x18001f000  call    ??0?$CSimpleStringT@G$0A@@ATL@@QEAA@PEAUIAtlStringMgr@1@@Z; ATL::CSimpleStringT<ushort,0>::CSimpleStringT<ushort,0>(ATL::IAtlStringMgr *)
0x18001f005  lea     r9, [rbp+57h+arg_0]
0x18001f009  mov     dword ptr [rbp+57h+arg_0], 0
0x18001f010  lea     rdx, [rbp+57h+var_68]
0x18001f014  lea     rcx, [rbp+57h+arg_18]
0x18001f018  call    ?Tokenize@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBA?AV12@PEBGAEAH@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Tokenize(ushort const *,int &)
0x18001f01d  mov     rbx, [rbp+57h+arg_10]
0x18001f021  mov     rdx, [rax]
0x18001f024  lea     rdi, [rbx-18h]
0x18001f028  lea     rcx, [rdx-18h]
0x18001f02c  cmp     rcx, rdi
0x18001f02f  jz      short loc_18001F06A
0x18001f031  cmp     dword ptr [rdi+10h], 0
0x18001f035  jl      short loc_18001F059
0x18001f037  mov     rax, [rdi]
0x18001f03a  cmp     [rcx], rax
0x18001f03d  jnz     short loc_18001F059
0x18001f03f  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x18001f044  mov     rcx, rdi; this
0x18001f047  mov     rbx, rax
0x18001f04a  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18001f04f  add     rbx, 18h
0x18001f053  mov     [rbp+57h+arg_10], rbx
0x18001f057  jmp     short loc_18001F06A
0x18001f059  mov     r8d, [rdx-10h]
0x18001f05d  lea     rcx, [rbp+57h+arg_10]
0x18001f061  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x18001f066  mov     rbx, [rbp+57h+arg_10]
0x18001f06a  mov     rcx, [rbp+57h+var_68]
0x18001f06e  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18001f072  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18001f077  xor     eax, eax
0x18001f079  cmp     [rbx], ax
0x18001f07c  jz      loc_18001F10F
0x18001f082  mov     rdx, rbx; unsigned __int16 *
0x18001f085  lea     rcx, [rbp+57h+bstrString]; this
0x18001f089  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x18001f08e  lea     rdx, [rbp+57h+var_68]
0x18001f092  mov     rcx, [rax]
0x18001f095  mov     [rbp+57h+var_68], rcx
0x18001f099  lea     rcx, [rbp+57h+var_70]
0x18001f09d  call    ?Add@?$CComSafeArray@PEAG$07@ATL@@QEAAJAEBQEAGH@Z; ATL::CComSafeArray<ushort *,8>::Add(ushort * const &,int)
0x18001f0a2  mov     rcx, [rbp+57h+bstrString]; bstrString
0x18001f0a6  call    cs:__imp_SysFreeString
0x18001f0ac  lea     r9, [rbp+57h+arg_0]
0x18001f0b0  lea     rdx, [rbp+57h+var_38]
0x18001f0b4  lea     rcx, [rbp+57h+arg_18]
0x18001f0b8  call    ?Tokenize@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBA?AV12@PEBGAEAH@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Tokenize(ushort const *,int &)
0x18001f0bd  lea     rdi, [rbx-18h]
0x18001f0c1  mov     rdx, [rax]
0x18001f0c4  lea     rcx, [rdx-18h]
0x18001f0c8  cmp     rcx, rdi
0x18001f0cb  jz      short loc_18001F106
0x18001f0cd  cmp     dword ptr [rdi+10h], 0
0x18001f0d1  jl      short loc_18001F0F5
0x18001f0d3  mov     rax, [rdi]
0x18001f0d6  cmp     [rcx], rax
0x18001f0d9  jnz     short loc_18001F0F5
0x18001f0db  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x18001f0e0  mov     rcx, rdi; this
0x18001f0e3  mov     rbx, rax
0x18001f0e6  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18001f0eb  add     rbx, 18h
0x18001f0ef  mov     [rbp+57h+arg_10], rbx
0x18001f0f3  jmp     short loc_18001F106
0x18001f0f5  mov     r8d, [rdx-10h]
0x18001f0f9  lea     rcx, [rbp+57h+arg_10]
0x18001f0fd  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x18001f102  mov     rbx, [rbp+57h+arg_10]
0x18001f106  mov     rcx, [rbp+57h+var_38]
0x18001f10a  jmp     loc_18001F06E
0x18001f10f  mov     rdx, [rbp+57h+var_70]; struct tagSAFEARRAY *
0x18001f113  lea     rcx, [rbp+57h+pvarg]; unsigned __int16 *
0x18001f117  call    ??4CComVariant@ATL@@QEAAAEAV01@PEBUtagSAFEARRAY@@@Z; ATL::CComVariant::operator=(tagSAFEARRAY const *)
0x18001f11c  lea     rcx, [rbx-18h]; this
0x18001f120  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18001f125  mov     rcx, [rbp+57h+arg_18]
0x18001f129  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18001f12d  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18001f132  lea     rcx, [rbp+57h+var_70]
0x18001f136  call    ?Destroy@?$CComSafeArray@PEAG$07@ATL@@QEAAJXZ; ATL::CComSafeArray<ushort *,8>::Destroy(void)
0x18001f13b  xor     eax, eax
0x18001f13d  lea     rdx, [rbp+57h+pvarg]; struct tagVARIANT *
0x18001f141  lea     rcx, [rbp+57h+var_30]; this
0x18001f145  mov     [rbp+57h+var_30], ax
0x18001f149  call    ?InternalCopy@CComVariant@ATL@@QEAAXPEBUtagVARIANT@@@Z; ATL::CComVariant::InternalCopy(tagVARIANT const *)
0x18001f14e  lea     r8, [rbp+57h+var_30]
0x18001f152  mov     rcx, rsi
0x18001f155  lea     rdx, CSCWMI_STR_PROP_EXCLUDEDFILETYPES; "ExcludedFileTypes"
0x18001f15c  call    ?WmiProp_SetProperty@@YAJPEAUIWbemClassObject@@PEBGVCComVariant@ATL@@@Z; WmiProp_SetProperty(IWbemClassObject *,ushort const *,ATL::CComVariant)
0x18001f161  mov     ebx, eax
0x18001f163  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f16a  lea     rax, WPP_GLOBAL_Control
0x18001f171  cmp     rcx, rax
0x18001f174  jz      short loc_18001F19F
0x18001f176  test    dword ptr [rcx+1Ch], 4000000h
0x18001f17d  jz      short loc_18001F19F
0x18001f17f  mov     rcx, [rcx+10h]
0x18001f183  lea     r9, CSCWMI_STR_PROP_EXCLUDEDFILETYPES; "ExcludedFileTypes"
0x18001f18a  mov     edx, 65h ; 'e'
0x18001f18f  mov     [rsp+0A0h+var_80], ebx
0x18001f193  lea     r8, WPP_a9b0d90f6b723a76085a448a6e9a8bc7_Traceguids
0x18001f19a  call    WPP_SF_SD
0x18001f19f  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18001f1a3  call    cs:__imp_VariantClear
0x18001f1a9  mov     eax, ebx
0x18001f1ab  mov     rbx, [rsp+0A0h+arg_8]
0x18001f1b3  add     rsp, 90h
0x18001f1ba  pop     rdi
0x18001f1bb  pop     rsi
0x18001f1bc  pop     rbp
0x18001f1bd  retn
```
