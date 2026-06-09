# StartList::LoadSettings(void)

- ea: `0x14001f728`
- end: `0x14001fba7`
- name: `?LoadSettings@StartList@@AEAAJXZ`
- size: `1151`
- prototype: `__int64 __fastcall(StartList *__hidden this)`
- caller_count: `5`
- callee_count: `23`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14001d9b8`
- `0x14001fdc8`
- `0x140020938`
- `0x140020d24`
- `0x140020ebc`

## callees

- `0x140002de3`
- `0x1400045f4`
- `0x140004700`
- `0x140005c90`
- `0x140007e90`
- `0x140009524`
- `0x140009cd8`
- `0x14000df20`
- `0x14001c508`
- `0x14001c714`
- `0x14001c768`
- `0x14001c8a8`
- `0x14001dae4`
- `0x14001dccc`
- `0x14001ddc4`
- `0x14001eb30`
- `0x14001ec2c`
- `0x14001ed8c`
- `0x14001ef2c`
- `0x14001f060`
- `0x14001f728`
- `0x140025d70`
- `0x140025e30`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x14001fa54`
- `KERNEL32!CloseHandle` at `0x14001fa54`
- `KERNEL32!OpenMutexW` at `0x14001fa42`
- `KERNEL32!OpenMutexW` at `0x14001fa42`

## string_xrefs

- `0x14001fa9c`: `Configuration`
- `0x14001fa6f`: `SOFTWARE\Microsoft\Windows NT\CurrentVersion\Accessibility\OOBE`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall StartList::LoadSettings(StartList *this)
{
  StartList *v3; // rcx
  unsigned int v4; // r8d
  unsigned int IsInteractiveUser; // edi
  __int64 v6; // rcx
  __int64 v7; // rbx
  unsigned int v8; // r8d
  StartList *v9; // rcx
  unsigned int v10; // r8d
  int UserValue; // eax
  int v12; // edi
  __int64 v13; // rcx
  _QWORD *v14; // rcx
  __int64 v15; // rdx
  StartList *v16; // rcx
  __int64 v17; // r8
  HANDLE v18; // rax
  StartList *v19; // rcx
  unsigned int v20; // r8d
  __int64 v21; // r8
  __int64 v22; // r8
  unsigned int v23; // [rsp+20h] [rbp-E0h]
  __int64 v24; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v25[2]; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v26; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v27; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v28; // [rsp+50h] [rbp-B0h]
  __int64 v29; // [rsp+58h] [rbp-A8h]
  __int64 v30; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD v31[3]; // [rsp+68h] [rbp-98h] BYREF
  _QWORD v32[4]; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int16 v33[1024]; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int16 v34[1024]; // [rsp+8A0h] [rbp+7A0h] BYREF
  unsigned __int16 v35[1024]; // [rsp+10A0h] [rbp+FA0h] BYREF

  if ( *((_DWORD *)this + 72) )
    return 0;
  *((_DWORD *)this + 72) = 1;
  if ( CATUtils::IsDesktopOOBERunning() )
  {
    memset_0(v34, 0, sizeof(v34));
    v27 = 0;
    v28 = 0;
    v29 = 0;
    StartList::GetSettingConfigurationValue(v3, v34, v4, (struct ATL::CRegKey *)&v27);
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      &v26,
      v34);
    StartList::BuildConfigList(&v26, (char *)this + 144);
    ATL::CStringData::Release((ATL::CStringData *)(v26 - 24));
    ATL::CRegKey::Close((ATL::CRegKey *)&v27);
  }
  IsInteractiveUser = CATUtils::IsInteractiveUser();
  memset(v32, 0, 24);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v26);
  StartList::BuildSessionListStringBasedOnCurrentSessionContext(v6, IsInteractiveUser, &v26, v32);
  StartList::BuildConfigList(&v26, (char *)this + 48);
  memset_0(v33, 0, sizeof(v33));
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v24);
  v7 = v26;
  if ( !IsInteractiveUser )
  {
    v18 = OpenMutexW(0x100000u, 0, L"Global\\Windows.Machine.OOBE");
    if ( !v18 )
    {
      StartList::GetSessionValue(v19, v33, v20, (struct ATL::CRegKey *)v32, 1);
      v22 = -1;
      do
        ++v22;
      while ( v33[v22] );
      ATL::CSimpleStringT<unsigned short,0>::SetString(&v24, v33, v22);
      if ( *(_DWORD *)(v24 - 16) )
        ATL::CSimpleStringT<unsigned short,0>::Append(&v24, L",", 1);
      ATL::CSimpleStringT<unsigned short,0>::Append(&v24, v7, *(unsigned int *)(v7 - 16));
      goto LABEL_36;
    }
    CloseHandle(v18);
    v27 = 0;
    v28 = 0;
    v29 = 0;
    if ( !(unsigned int)ATL::CRegKey::Open(
                          (ATL::CRegKey *)&v27,
                          HKEY_LOCAL_MACHINE,
                          StartList::_oobeAccessibilityKeyString,
                          0x20019u) )
    {
      v25[0] = 1024;
      if ( (unsigned int)ATL::CRegKey::QueryStringValue((ATL::CRegKey *)&v27, L"Configuration", v33, v25) )
        v33[0] = 0;
    }
    v21 = -1;
    do
      ++v21;
    while ( v33[v21] );
    ATL::CSimpleStringT<unsigned short,0>::SetString(&v24, v33, v21);
LABEL_30:
    ATL::CRegKey::Close((ATL::CRegKey *)&v27);
LABEL_36:
    StartList::BuildConfigList(&v24, this);
    v12 = 0;
    goto LABEL_37;
  }
  v27 = 0;
  v28 = 0;
  v29 = 0;
  memset_0(v34, 0, sizeof(v34));
  memset_0(v35, 0, sizeof(v35));
  StartList::GetTempValue(this, v34, v8, v35, v23, (struct ATL::CRegKey *)&v27);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &v30,
    v34);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    v25,
    v35);
  StartList::BuildConfigList(&v30, (char *)this + 192);
  StartList::BuildConfigList(v25, (char *)this + 240);
  memset(v31, 0, sizeof(v31));
  UserValue = StartList::GetUserValue(v9, v33, v10, (struct ATL::CRegKey *)v31);
  v12 = UserValue;
  if ( UserValue >= 0 )
  {
    v17 = -1;
    do
      ++v17;
    while ( v33[v17] );
    ATL::CSimpleStringT<unsigned short,0>::SetString(&v24, v33, v17);
LABEL_22:
    StartList::ClearSessionSecureConfiguration(v16, (struct ATL::CRegKey *)v32);
    ATL::CRegKey::Close((ATL::CRegKey *)v31);
    ATL::CStringData::Release((ATL::CStringData *)(*(_QWORD *)v25 - 24LL));
    ATL::CStringData::Release((ATL::CStringData *)(v30 - 24));
    goto LABEL_30;
  }
  v13 = UserValue & 0x1FFF0000;
  if ( (_DWORD)v13 == 458752 )
    UserValue = (unsigned __int16)UserValue;
  if ( UserValue == 2 )
  {
    v12 = StartList::HandleFirstTime(v13, (_QWORD *)this + 6, &v24, (ATL::CRegKey *)v31);
    if ( v12 < 0 )
    {
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
        goto LABEL_18;
      v15 = 21;
      goto LABEL_17;
    }
    goto LABEL_22;
  }
  v14 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
    goto LABEL_18;
  v15 = 20;
LABEL_17:
  WPP_SF_d(v14[2], v15, &WPP_0cfc691c390c3581aa6c7b8081e34e7b_Traceguids, (unsigned int)v12);
LABEL_18:
  ATL::CRegKey::Close((ATL::CRegKey *)v31);
  ATL::CStringData::Release((ATL::CStringData *)(*(_QWORD *)v25 - 24LL));
  ATL::CStringData::Release((ATL::CStringData *)(v30 - 24));
  ATL::CRegKey::Close((ATL::CRegKey *)&v27);
LABEL_37:
  ATL::CStringData::Release((ATL::CStringData *)(v24 - 24));
  ATL::CStringData::Release((ATL::CStringData *)(v7 - 24));
  ATL::CRegKey::Close((ATL::CRegKey *)v32);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x14001f728  mov     [rsp-8+arg_8], rbx
0x14001f72d  mov     [rsp-8+arg_10], rsi
0x14001f732  push    rbp
0x14001f733  push    rdi
0x14001f734  push    r13
0x14001f736  push    r14
0x14001f738  push    r15
0x14001f73a  lea     rbp, [rsp-17B0h]
0x14001f742  mov     eax, 18B0h
0x14001f747  call    _alloca_probe
0x14001f74c  sub     rsp, rax
0x14001f74f  mov     rax, cs:__security_cookie
0x14001f756  xor     rax, rsp
0x14001f759  mov     [rbp+17D0h+var_30], rax
0x14001f760  mov     rsi, rcx
0x14001f763  xor     r15d, r15d
0x14001f766  cmp     [rcx+120h], r15d
0x14001f76d  jz      short loc_14001F776
0x14001f76f  xor     eax, eax
0x14001f771  jmp     loc_14001FB7C
0x14001f776  mov     dword ptr [rcx+120h], 1
0x14001f780  call    ?IsDesktopOOBERunning@CATUtils@@SA_NXZ; CATUtils::IsDesktopOOBERunning(void)
0x14001f785  mov     r13d, 800h
0x14001f78b  test    al, al
0x14001f78d  jz      short loc_14001F7FD
0x14001f78f  mov     r8d, r13d; Size
0x14001f792  xor     edx, edx; Val
0x14001f794  lea     rcx, [rbp+17D0h+var_1030]; void *
0x14001f79b  call    memset_0
0x14001f7a0  mov     [rsp+18D0h+var_1888], r15
0x14001f7a5  mov     [rsp+18D0h+var_1880], r15
0x14001f7aa  mov     [rsp+18D0h+var_1878], r15
0x14001f7af  lea     r9, [rsp+18D0h+var_1888]; struct ATL::CRegKey *
0x14001f7b4  lea     rdx, [rbp+17D0h+var_1030]; unsigned __int16 *
0x14001f7bb  call    ?GetSettingConfigurationValue@StartList@@AEAAXPEAGIAEAVCRegKey@ATL@@@Z; StartList::GetSettingConfigurationValue(ushort *,uint,ATL::CRegKey &)
0x14001f7c0  lea     rdx, [rbp+17D0h+var_1030]
0x14001f7c7  lea     rcx, [rsp+18D0h+var_1890]
0x14001f7cc  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x14001f7d1  nop
0x14001f7d2  lea     rdx, [rsi+90h]
0x14001f7d9  lea     rcx, [rsp+18D0h+var_1890]
0x14001f7de  call    ?BuildConfigList@StartList@@SAXAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAV?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@3@@Z; StartList::BuildConfigList(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>> &)
0x14001f7e3  nop
0x14001f7e4  mov     rcx, [rsp+18D0h+var_1890]
0x14001f7e9  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x14001f7ed  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x14001f7f2  nop
0x14001f7f3  lea     rcx, [rsp+18D0h+var_1888]; this
0x14001f7f8  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x14001f7fd  call    ?IsInteractiveUser@CATUtils@@SAHXZ; CATUtils::IsInteractiveUser(void)
0x14001f802  mov     edi, eax
0x14001f804  mov     [rbp+17D0h+var_1850], r15
0x14001f808  mov     [rbp+17D0h+var_1848], r15
0x14001f80c  mov     [rbp+17D0h+var_1840], r15
0x14001f810  lea     rcx, [rsp+18D0h+var_1890]
0x14001f815  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x14001f81a  nop
0x14001f81b  lea     r9, [rbp+17D0h+var_1850]
0x14001f81f  lea     r8, [rsp+18D0h+var_1890]
0x14001f824  mov     edx, edi
0x14001f826  call    ?BuildSessionListStringBasedOnCurrentSessionContext@StartList@@AEBAXHAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAVCRegKey@3@@Z; StartList::BuildSessionListStringBasedOnCurrentSessionContext(int,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ATL::CRegKey &)
0x14001f82b  lea     rdx, [rsi+30h]
0x14001f82f  lea     rcx, [rsp+18D0h+var_1890]
0x14001f834  call    ?BuildConfigList@StartList@@SAXAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAV?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@3@@Z; StartList::BuildConfigList(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>> &)
0x14001f839  mov     r8, r13; Size
0x14001f83c  xor     edx, edx; Val
0x14001f83e  lea     rcx, [rbp+17D0h+var_1830]; void *
0x14001f842  call    memset_0
0x14001f847  lea     rcx, [rsp+18D0h+var_18A0]
0x14001f84c  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x14001f851  nop
0x14001f852  mov     rbx, [rsp+18D0h+var_1890]
0x14001f857  test    edi, edi
0x14001f859  jz      loc_14001FA34
0x14001f85f  mov     [rsp+18D0h+var_1888], r15
0x14001f864  mov     [rsp+18D0h+var_1880], r15
0x14001f869  mov     [rsp+18D0h+var_1878], r15
0x14001f86e  mov     r8, r13; Size
0x14001f871  xor     edx, edx; Val
0x14001f873  lea     rcx, [rbp+17D0h+var_1030]; void *
0x14001f87a  call    memset_0
0x14001f87f  mov     r8, r13; Size
0x14001f882  xor     edx, edx; Val
0x14001f884  lea     rcx, [rbp+17D0h+var_830]; void *
0x14001f88b  call    memset_0
0x14001f890  lea     rax, [rsp+18D0h+var_1888]
0x14001f895  mov     [rsp+18D0h+var_18A8], rax; struct ATL::CRegKey *
0x14001f89a  lea     r9, [rbp+17D0h+var_830]; unsigned __int16 *
0x14001f8a1  lea     rdx, [rbp+17D0h+var_1030]; unsigned __int16 *
0x14001f8a8  mov     rcx, rsi; this
0x14001f8ab  call    ?GetTempValue@StartList@@AEAAXPEAGI0IAEAVCRegKey@ATL@@@Z; StartList::GetTempValue(ushort *,uint,ushort *,uint,ATL::CRegKey &)
0x14001f8b0  lea     rdx, [rbp+17D0h+var_1030]
0x14001f8b7  lea     rcx, [rsp+18D0h+var_1870]
0x14001f8bc  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x14001f8c1  nop
0x14001f8c2  lea     rdx, [rbp+17D0h+var_830]
0x14001f8c9  lea     rcx, [rsp+18D0h+var_1898]
0x14001f8ce  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x14001f8d3  nop
0x14001f8d4  lea     rdx, [rsi+0C0h]
0x14001f8db  lea     rcx, [rsp+18D0h+var_1870]
0x14001f8e0  call    ?BuildConfigList@StartList@@SAXAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAV?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@3@@Z; StartList::BuildConfigList(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>> &)
0x14001f8e5  lea     rdx, [rsi+0F0h]
0x14001f8ec  lea     rcx, [rsp+18D0h+var_1898]
0x14001f8f1  call    ?BuildConfigList@StartList@@SAXAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAV?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@3@@Z; StartList::BuildConfigList(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>> &)
0x14001f8f6  mov     [rsp+18D0h+var_1868], r15
0x14001f8fb  mov     [rsp+18D0h+var_1860], r15
0x14001f900  mov     [rsp+18D0h+var_1858], r15
0x14001f905  lea     r9, [rsp+18D0h+var_1868]; struct ATL::CRegKey *
0x14001f90a  lea     rdx, [rbp+17D0h+var_1830]; unsigned __int16 *
0x14001f90e  call    ?GetUserValue@StartList@@AEAAJPEAGIAEAVCRegKey@ATL@@@Z; StartList::GetUserValue(ushort *,uint,ATL::CRegKey &)
0x14001f913  mov     edi, eax
0x14001f915  test    eax, eax
0x14001f917  jns     loc_14001F9DC
0x14001f91d  mov     ecx, eax
0x14001f91f  and     ecx, 1FFF0000h
0x14001f925  cmp     ecx, 70000h
0x14001f92b  jnz     short loc_14001F930
0x14001f92d  movzx   eax, di
0x14001f930  cmp     eax, 2
0x14001f933  jz      short loc_14001F955
0x14001f935  lea     rax, WPP_GLOBAL_Control
0x14001f93c  mov     rcx, cs:WPP_GLOBAL_Control
0x14001f943  cmp     rcx, rax
0x14001f946  jz      short loc_14001F9A4
0x14001f948  test    byte ptr [rcx+1Ch], 8
0x14001f94c  jz      short loc_14001F9A4
0x14001f94e  mov     edx, 14h
0x14001f953  jmp     short loc_14001F990
0x14001f955  lea     r9, [rsp+18D0h+var_1868]
0x14001f95a  lea     r8, [rsp+18D0h+var_18A0]
0x14001f95f  lea     rdx, [rsi+30h]
0x14001f963  call    ?HandleFirstTime@StartList@@AEAAJAEBV?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@AEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@3@AEAVCRegKey@3@@Z; StartList::HandleFirstTime(ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ATL::CRegKey &)
0x14001f968  mov     edi, eax
0x14001f96a  test    eax, eax
0x14001f96c  jns     loc_14001F9FC
0x14001f972  lea     rax, WPP_GLOBAL_Control
0x14001f979  mov     rcx, cs:WPP_GLOBAL_Control
0x14001f980  cmp     rcx, rax
0x14001f983  jz      short loc_14001F9A4
0x14001f985  test    byte ptr [rcx+1Ch], 8
0x14001f989  jz      short loc_14001F9A4
0x14001f98b  mov     edx, 15h
0x14001f990  mov     r9d, edi
0x14001f993  lea     r8, WPP_0cfc691c390c3581aa6c7b8081e34e7b_Traceguids
0x14001f99a  mov     rcx, [rcx+10h]
0x14001f99e  call    WPP_SF_d
0x14001f9a3  nop
0x14001f9a4  lea     rcx, [rsp+18D0h+var_1868]; this
0x14001f9a9  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x14001f9ae  nop
0x14001f9af  mov     rcx, qword ptr [rsp+18D0h+var_1898]
0x14001f9b4  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x14001f9b8  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x14001f9bd  nop
0x14001f9be  mov     rcx, [rsp+18D0h+var_1870]
0x14001f9c3  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x14001f9c7  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x14001f9cc  nop
0x14001f9cd  lea     rcx, [rsp+18D0h+var_1888]; this
0x14001f9d2  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x14001f9d7  jmp     loc_14001FB58
0x14001f9dc  lea     rax, [rbp+17D0h+var_1830]
0x14001f9e0  or      r8, 0FFFFFFFFFFFFFFFFh
0x14001f9e4  inc     r8
0x14001f9e7  cmp     [rax+r8*2], r15w
0x14001f9ec  jnz     short loc_14001F9E4
0x14001f9ee  lea     rdx, [rbp+17D0h+var_1830]
0x14001f9f2  lea     rcx, [rsp+18D0h+var_18A0]
0x14001f9f7  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x14001f9fc  lea     rdx, [rbp+17D0h+var_1850]; struct ATL::CRegKey *
0x14001fa00  call    ?ClearSessionSecureConfiguration@StartList@@AEBAXAEAVCRegKey@ATL@@@Z; StartList::ClearSessionSecureConfiguration(ATL::CRegKey &)
0x14001fa05  nop
0x14001fa06  lea     rcx, [rsp+18D0h+var_1868]; this
0x14001fa0b  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x14001fa10  nop
0x14001fa11  mov     rcx, qword ptr [rsp+18D0h+var_1898]
0x14001fa16  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x14001fa1a  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x14001fa1f  nop
0x14001fa20  mov     rcx, [rsp+18D0h+var_1870]
0x14001fa25  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x14001fa29  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x14001fa2e  nop
0x14001fa2f  jmp     loc_14001FAD7
0x14001fa34  lea     r8, aGlobalWindowsM_1; "Global\\Windows.Machine.OOBE"
0x14001fa3b  xor     edx, edx; bInheritHandle
0x14001fa3d  mov     ecx, 100000h; dwDesiredAccess
0x14001fa42  call    cs:__imp_OpenMutexW
0x14001fa48  test    rax, rax
0x14001fa4b  jz      loc_14001FAE3
0x14001fa51  mov     rcx, rax; hObject
0x14001fa54  call    cs:__imp_CloseHandle
0x14001fa5a  mov     [rsp+18D0h+var_1888], r15
0x14001fa5f  mov     [rsp+18D0h+var_1880], r15
0x14001fa64  mov     [rsp+18D0h+var_1878], r15
0x14001fa69  mov     r9d, 20019h; unsigned int
0x14001fa6f  lea     r8, ?_oobeAccessibilityKeyString@StartList@@0PAGA; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x14001fa76  mov     rdx, 0FFFFFFFF80000002h; hKey
0x14001fa7d  lea     rcx, [rsp+18D0h+var_1888]; this
0x14001fa82  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x14001fa87  test    eax, eax
0x14001fa89  jnz     short loc_14001FAB6
0x14001fa8b  mov     [rsp+18D0h+var_1898], 400h
0x14001fa93  lea     r9, [rsp+18D0h+var_1898]; unsigned int *
0x14001fa98  lea     r8, [rbp+17D0h+var_1830]; unsigned __int16 *
0x14001fa9c  lea     rdx, aConfiguration; "Configuration"
0x14001faa3  lea     rcx, [rsp+18D0h+var_1888]; this
0x14001faa8  call    ?QueryStringValue@CRegKey@ATL@@QEAAJPEBGPEAGPEAK@Z; ATL::CRegKey::QueryStringValue(ushort const *,ushort *,ulong *)
0x14001faad  test    eax, eax
0x14001faaf  jz      short loc_14001FAB6
0x14001fab1  mov     [rbp+17D0h+var_1830], r15w
0x14001fab6  lea     rax, [rbp+17D0h+var_1830]
0x14001faba  or      r8, 0FFFFFFFFFFFFFFFFh
0x14001fabe  inc     r8
0x14001fac1  cmp     [rax+r8*2], r15w
0x14001fac6  jnz     short loc_14001FABE
0x14001fac8  lea     rdx, [rbp+17D0h+var_1830]
0x14001facc  lea     rcx, [rsp+18D0h+var_18A0]
0x14001fad1  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x14001fad6  nop
0x14001fad7  lea     rcx, [rsp+18D0h+var_1888]; this
0x14001fadc  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x14001fae1  jmp     short loc_14001FB48
0x14001fae3  mov     [rsp+18D0h+var_18B0], 1; bool
0x14001fae8  lea     r9, [rbp+17D0h+var_1850]; struct ATL::CRegKey *
0x14001faec  lea     rdx, [rbp+17D0h+var_1830]; unsigned __int16 *
0x14001faf0  call    ?GetSessionValue@StartList@@AEBAXPEAGIAEAVCRegKey@ATL@@_N@Z; StartList::GetSessionValue(ushort *,uint,ATL::CRegKey &,bool)
0x14001faf5  lea     rax, [rbp+17D0h+var_1830]
0x14001faf9  or      r8, 0FFFFFFFFFFFFFFFFh
0x14001fafd  inc     r8
0x14001fb00  cmp     [rax+r8*2], r15w
0x14001fb05  jnz     short loc_14001FAFD
0x14001fb07  lea     rdx, [rbp+17D0h+var_1830]
0x14001fb0b  lea     rcx, [rsp+18D0h+var_18A0]
0x14001fb10  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x14001fb15  mov     rax, [rsp+18D0h+var_18A0]
0x14001fb1a  cmp     [rax-10h], r15d
0x14001fb1e  jz      short loc_14001FB37
0x14001fb20  mov     r8d, 1
0x14001fb26  lea     rdx, asc_14002C214; ","
0x14001fb2d  lea     rcx, [rsp+18D0h+var_18A0]
0x14001fb32  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *,int)
0x14001fb37  mov     r8d, [rbx-10h]
0x14001fb3b  mov     rdx, rbx
0x14001fb3e  lea     rcx, [rsp+18D0h+var_18A0]
0x14001fb43  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *,int)
0x14001fb48  mov     rdx, rsi
0x14001fb4b  lea     rcx, [rsp+18D0h+var_18A0]
0x14001fb50  call    ?BuildConfigList@StartList@@SAXAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAV?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@3@@Z; StartList::BuildConfigList(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>> &)
0x14001fb55  mov     edi, r15d
0x14001fb58  mov     rcx, [rsp+18D0h+var_18A0]
0x14001fb5d  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x14001fb61  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x14001fb66  nop
0x14001fb67  lea     rcx, [rbx-18h]; this
0x14001fb6b  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x14001fb70  nop
0x14001fb71  lea     rcx, [rbp+17D0h+var_1850]; this
0x14001fb75  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x14001fb7a  mov     eax, edi
0x14001fb7c  mov     rcx, [rbp+17D0h+var_30]
0x14001fb83  xor     rcx, rsp; StackCookie
0x14001fb86  call    __security_check_cookie
0x14001fb8b  lea     r11, [rsp+18D0h+var_20]
0x14001fb93  mov     rbx, [r11+38h]
0x14001fb97  mov     rsi, [r11+40h]
0x14001fb9b  mov     rsp, r11
0x14001fb9e  pop     r15
0x14001fba0  pop     r14
0x14001fba2  pop     r13
0x14001fba4  pop     rdi
0x14001fba5  pop     rbp
0x14001fba6  retn
```
