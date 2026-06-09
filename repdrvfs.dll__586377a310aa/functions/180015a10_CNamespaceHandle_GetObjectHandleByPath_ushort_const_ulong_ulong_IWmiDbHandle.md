# CNamespaceHandle::GetObjectHandleByPath(ushort const *,ulong,ulong,IWmiDbHandle * *)

- ea: `0x180015a10`
- end: `0x1800161cb`
- name: `?GetObjectHandleByPath@CNamespaceHandle@@IEAAJPEBGKKPEAPEAUIWmiDbHandle@@@Z`
- size: `1979`
- prototype: `__int64 __fastcall(CNamespaceHandle *this, const unsigned __int16 *, __int64, int, struct IWmiDbHandle **)`
- caller_count: `2`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1800157d0`
- `0x18001d334`

## callees

- `0x1800012b8`
- `0x1800013a0`
- `0x1800013c8`
- `0x180004310`
- `0x180004f30`
- `0x180015a10`
- `0x1800161e0`
- `0x180048010`

## import_xrefs

- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180015a87`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180015b3e`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180015a87`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180015b3e`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180015c39`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180015c43`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180015cd5`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180015cdf`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180015ea6`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180015eb0`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180015ed6`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180015ee0`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180015f24`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180015f2e`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180015f67`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180015f71`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18001601f`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180015c39`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180015c43`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180015cd5`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180015cdf`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180015ea6`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180015eb0`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180015ed6`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180015ee0`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180015f24`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180015f2e`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180015f67`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180015f71`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18001601f`
- `wbemcomn!?Length@WString@@QEBAHXZ` at `0x180015b23`
- `wbemcomn!?Length@WString@@QEBAHXZ` at `0x180015b23`
- `wbemcomn!?Length@WString2@@QEBAHXZ` at `0x180015ba0`
- `wbemcomn!?Length@WString2@@QEBAHXZ` at `0x180016107`
- `wbemcomn!?Length@WString2@@QEBAHXZ` at `0x180015ba0`
- `wbemcomn!?Length@WString2@@QEBAHXZ` at `0x180016107`
- `wbemcomn!??BWString@@QEAAPEAGXZ` at `0x180015b88`
- `wbemcomn!??BWString@@QEAAPEAGXZ` at `0x1800160ef`
- `wbemcomn!??BWString@@QEAAPEAGXZ` at `0x180016141`
- `wbemcomn!??BWString@@QEAAPEAGXZ` at `0x180015b88`
- `wbemcomn!??BWString@@QEAAPEAGXZ` at `0x1800160ef`
- `wbemcomn!??BWString@@QEAAPEAGXZ` at `0x180016141`
- `wbemcomn!??BWString2@@QEAAPEAGXZ` at `0x180015bbf`
- `wbemcomn!??BWString2@@QEAAPEAGXZ` at `0x180016134`
- `wbemcomn!??BWString2@@QEAAPEAGXZ` at `0x180015bbf`
- `wbemcomn!??BWString2@@QEAAPEAGXZ` at `0x180016134`
- `wbemcomn!??0WString@@QEAA@XZ` at `0x180015d30`
- `wbemcomn!??0WString@@QEAA@XZ` at `0x180015d3b`
- `wbemcomn!??0WString@@QEAA@XZ` at `0x180015d46`
- `wbemcomn!??0WString@@QEAA@XZ` at `0x180015d30`
- `wbemcomn!??0WString@@QEAA@XZ` at `0x180015d3b`
- `wbemcomn!??0WString@@QEAA@XZ` at `0x180015d46`
- `wbemcomn!??0WString2@@QEAA@PEBG@Z` at `0x180015b95`
- `wbemcomn!??0WString2@@QEAA@PEBG@Z` at `0x1800160fc`
- `wbemcomn!??0WString2@@QEAA@PEBG@Z` at `0x180015b95`
- `wbemcomn!??0WString2@@QEAA@PEBG@Z` at `0x1800160fc`
- `wbemcomn!??1WString2@@QEAA@XZ` at `0x180015be8`
- `wbemcomn!??1WString2@@QEAA@XZ` at `0x18001615b`
- `wbemcomn!??1WString2@@QEAA@XZ` at `0x180015be8`
- `wbemcomn!??1WString2@@QEAA@XZ` at `0x18001615b`
- `wbemcomn!??YWString2@@QEAAAEAV0@PEBG@Z` at `0x180015bb5`
- `wbemcomn!??YWString2@@QEAAAEAV0@PEBG@Z` at `0x180015c5c`
- `wbemcomn!??YWString2@@QEAAAEAV0@PEBG@Z` at `0x18001611c`
- `wbemcomn!??YWString2@@QEAAAEAV0@PEBG@Z` at `0x18001612a`
- `wbemcomn!??YWString2@@QEAAAEAV0@PEBG@Z` at `0x180015bb5`
- `wbemcomn!??YWString2@@QEAAAEAV0@PEBG@Z` at `0x180015c5c`
- `wbemcomn!??YWString2@@QEAAAEAV0@PEBG@Z` at `0x18001611c`
- `wbemcomn!??YWString2@@QEAAAEAV0@PEBG@Z` at `0x18001612a`
- `wbemcomn!GetMemLogObject` at `0x180015a95`
- `wbemcomn!GetMemLogObject` at `0x180015c90`
- `wbemcomn!GetMemLogObject` at `0x180015e2a`
- `wbemcomn!GetMemLogObject` at `0x180015fda`
- `wbemcomn!GetMemLogObject` at `0x18001602d`
- `wbemcomn!GetMemLogObject` at `0x18001608c`
- `wbemcomn!GetMemLogObject` at `0x180016171`
- `wbemcomn!GetMemLogObject` at `0x180015a95`
- `wbemcomn!GetMemLogObject` at `0x180015c90`
- `wbemcomn!GetMemLogObject` at `0x180015e2a`
- `wbemcomn!GetMemLogObject` at `0x180015fda`
- `wbemcomn!GetMemLogObject` at `0x18001602d`
- `wbemcomn!GetMemLogObject` at `0x18001608c`
- `wbemcomn!GetMemLogObject` at `0x180016171`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180015aa3`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180015c9b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180015e35`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180015fe5`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001603b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001609a`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001617c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180015aa3`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180015c9b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180015e35`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180015fe5`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001603b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001609a`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001617c`
- `OLEAUT32!__imp_VariantInit` at `0x180015de8`
- `OLEAUT32!__imp_VariantInit` at `0x180015de8`
- `OLEAUT32!__imp_VariantClear` at `0x180015e77`
- `OLEAUT32!__imp_VariantClear` at `0x180015ef5`
- `OLEAUT32!__imp_VariantClear` at `0x180016166`
- `OLEAUT32!__imp_VariantClear` at `0x180015e77`
- `OLEAUT32!__imp_VariantClear` at `0x180015ef5`
- `OLEAUT32!__imp_VariantClear` at `0x180016166`

## string_xrefs

- `0x180015e10`: `__RELPATH`

## pseudocode

```c
__int64 __fastcall CNamespaceHandle::GetObjectHandleByPath(
        CNamespaceHandle *this,
        const unsigned __int16 *a2,
        __int64 a3,
        int a4,
        struct IWmiDbHandle **a5)
{
  __int64 v7; // rax
  unsigned __int64 v8; // rax
  unsigned __int64 v9; // rdi
  unsigned __int16 *v10; // rax
  unsigned __int16 *v11; // r14
  CMemoryLog *MemLogObject; // rax
  int v14; // ebx
  unsigned __int16 *v15; // r12
  void *v16; // rbx
  _QWORD *v17; // rsi
  const unsigned __int16 *v18; // rax
  const unsigned __int16 *v19; // rax
  int v20; // edi
  int InstanceByKey; // ebx
  CMemoryLog *v22; // rax
  __int64 v23; // rdi
  void (__fastcall ***v24)(_QWORD, _QWORD *); // rcx
  CMemoryLog *v25; // rax
  CMemoryLog *v26; // rax
  CMemoryLog *v27; // rax
  CMemoryLog *v28; // rax
  const unsigned __int16 *v29; // rax
  const unsigned __int16 *v30; // rdi
  const unsigned __int16 *v31; // rax
  CMemoryLog *v32; // rax
  void *v33; // [rsp+40h] [rbp-71h] BYREF
  unsigned __int16 *v34; // [rsp+48h] [rbp-69h] BYREF
  VARIANTARG pvarg; // [rsp+50h] [rbp-61h] BYREF
  _BYTE v36[40]; // [rsp+68h] [rbp-49h] BYREF
  _QWORD *v37; // [rsp+90h] [rbp-21h]
  unsigned __int16 *v38; // [rsp+98h] [rbp-19h]
  unsigned __int16 *v39; // [rsp+A0h] [rbp-11h]
  void *v40; // [rsp+A8h] [rbp-9h]
  VARIANTARG *p_pvarg; // [rsp+B0h] [rbp-1h]
  int v42; // [rsp+128h] [rbp+77h] BYREF

  v42 = a4;
  if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 98, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids, a2);
  }
  v7 = -1;
  do
    ++v7;
  while ( a2[v7] );
  v8 = v7 + 1;
  v9 = 2;
  if ( v8 > 2 )
    v9 = (unsigned int)v8;
  v10 = (unsigned __int16 *)CWin32DefaultArena::WbemMemAlloc(saturated_mul(v9, 2u));
  v11 = v10;
  if ( !v10 )
  {
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, -2147217402);
    if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 99, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids, 2147749894LL);
    }
    return 2147749894LL;
  }
  v38 = v10;
  LOBYTE(v42) = 0;
  v34 = 0;
  v14 = CNamespaceHandle::ComputeKeyFromPath(this, a2, v10, v9, &v34, (bool *)&v42, 0);
  if ( v14 < 0 )
  {
    v26 = GetMemLogObject();
    CMemoryLog::Write(v26, v14);
    if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        100,
        WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids,
        (unsigned int)v14);
    }
    CWin32DefaultArena::WbemMemFree(v11);
    return (unsigned int)v14;
  }
  else
  {
    v15 = v34;
    v39 = v34;
    v33 = 0;
    if ( (int)WString::Length((CNamespaceHandle *)((char *)this + 32)) > 0 )
    {
      InstanceByKey = CNamespaceHandle::GetInstanceByKey(this, v34, v11, &IID__IWmiObject, &v33);
      if ( InstanceByKey < 0 )
      {
        v22 = GetMemLogObject();
        CMemoryLog::Write(v22, InstanceByKey);
        if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            101,
            WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids,
            (unsigned int)InstanceByKey);
        }
        CWin32DefaultArena::WbemMemFree(v15);
        CWin32DefaultArena::WbemMemFree(v11);
        return (unsigned int)InstanceByKey;
      }
    }
    v16 = v33;
    v40 = v33;
    v17 = CWin32DefaultArena::WbemMemAlloc(0x70u);
    v37 = v17;
    if ( v17 )
    {
      v23 = *((_QWORD *)this + 3);
      v24 = (void (__fastcall ***)(_QWORD, _QWORD *))*((_QWORD *)this + 2);
      *v17 = &CUnkBase<IWmiDbHandle,&_GUID const IID_IWmiDbHandle>::`vftable';
      *((_DWORD *)v17 + 2) = 0;
      v17[2] = v24;
      if ( v24 )
        (**v24)(v24, v17);
      *v17 = &CNamespaceHandle::`vftable';
      v17[3] = v23;
      WString::WString((WString *)(v17 + 4));
      WString::WString((WString *)(v17 + 5));
      WString::WString((WString *)(v17 + 6));
      v17[11] = 0;
      v17[12] = 0;
      *((_WORD *)v17 + 52) = 256;
      if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 81, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids);
      }
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v17[3] + 8LL))(v17[3]);
      v17[7] = 0;
      v17[9] = 0;
      _InterlockedIncrement(&CNamespaceHandle::s_lActiveRepNs);
    }
    if ( v17 )
    {
      (*(void (__fastcall **)(_QWORD *))(*v17 + 8LL))(v17);
      v37 = v17;
      if ( v33
        && (*(unsigned int (__fastcall **)(void *, const wchar_t *))(*(_QWORD *)v33 + 144LL))(v33, L"__Namespace") )
      {
        memset(&pvarg, 0, sizeof(pvarg));
        VariantInit(&pvarg);
        p_pvarg = &pvarg;
        v20 = (*(__int64 (__fastcall **)(void *, const wchar_t *, _QWORD, VARIANTARG *, _QWORD, _QWORD))(*(_QWORD *)v33 + 32LL))(
                v33,
                L"__RELPATH",
                0,
                &pvarg,
                0,
                0);
        if ( v20 < 0 )
        {
          v25 = GetMemLogObject();
          CMemoryLog::Write(v25, v20);
          if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              103,
              WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids,
              (unsigned int)v20);
          }
          VariantClear(&pvarg);
          (*(void (__fastcall **)(_QWORD *))(*v17 + 16LL))(v17);
          if ( v16 )
            (*(void (__fastcall **)(void *))(*(_QWORD *)v16 + 16LL))(v16);
LABEL_54:
          CWin32DefaultArena::WbemMemFree(v15);
          CWin32DefaultArena::WbemMemFree(v11);
          return (unsigned int)v20;
        }
        if ( pvarg.vt != 8 )
        {
          v28 = GetMemLogObject();
          CMemoryLog::Write(v28, -2147217393);
          if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              104,
              WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids,
              2147749903LL);
          }
          VariantClear(&pvarg);
          (*(void (__fastcall **)(_QWORD *))(*v17 + 16LL))(v17);
          if ( v16 )
            (*(void (__fastcall **)(void *))(*(_QWORD *)v16 + 16LL))(v16);
          CWin32DefaultArena::WbemMemFree(v15);
          CWin32DefaultArena::WbemMemFree(v11);
          return 2147749903LL;
        }
        v29 = (const unsigned __int16 *)WString::operator unsigned short *((char *)this + 40);
        WString2::WString2((WString2 *)v36, v29);
        if ( (int)WString2::Length((WString2 *)v36) > 0 )
          WString2::operator+=(v36, L":");
        WString2::operator+=(v36, pvarg.llVal);
        v30 = (const unsigned __int16 *)WString2::operator unsigned short *(v36);
        v31 = (const unsigned __int16 *)WString::operator unsigned short *((char *)this + 32);
        v20 = CNamespaceHandle::Initialize((CNamespaceHandle *)v17, v31, v30);
        WString2::~WString2((WString2 *)v36);
        VariantClear(&pvarg);
      }
      else
      {
        v18 = (const unsigned __int16 *)WString::operator unsigned short *((char *)this + 32);
        WString2::WString2((WString2 *)v36, v18);
        if ( (int)WString2::Length((WString2 *)v36) > 0 )
          WString2::operator+=(v36, L"\\");
        WString2::operator+=(v36, v11);
        v19 = (const unsigned __int16 *)WString2::operator unsigned short *(v36);
        v20 = CNamespaceHandle::Initialize((CNamespaceHandle *)v17, v19, 0);
        if ( v20 >= 0 )
          *(_DWORD *)(v17[11] + 48LL) = 0;
        WString2::~WString2((WString2 *)v36);
      }
      if ( v20 < 0 )
      {
        v32 = GetMemLogObject();
        CMemoryLog::Write(v32, v20);
        if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            105,
            WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids,
            (unsigned int)v20);
        }
        (*(void (__fastcall **)(_QWORD *))(*v17 + 16LL))(v17);
        if ( v16 )
          (*(void (__fastcall **)(void *))(*(_QWORD *)v16 + 16LL))(v16);
      }
      else
      {
        v20 = (*(__int64 (__fastcall **)(_QWORD *, GUID *, struct IWmiDbHandle **))*v17)(v17, &IID_IWmiDbHandle, a5);
        (*(void (__fastcall **)(_QWORD *))(*v17 + 16LL))(v17);
        if ( v16 )
          (*(void (__fastcall **)(void *))(*(_QWORD *)v16 + 16LL))(v16);
      }
      goto LABEL_54;
    }
    v27 = GetMemLogObject();
    CMemoryLog::Write(v27, -2147217402);
    if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 102, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids, 2147749894LL);
    }
    if ( v16 )
      (*(void (__fastcall **)(void *))(*(_QWORD *)v16 + 16LL))(v16);
    CWin32DefaultArena::WbemMemFree(v15);
    CWin32DefaultArena::WbemMemFree(v11);
    return 2147749894LL;
  }
}

```

## disassembly

```asm
0x180015a10  mov     [rsp-8+arg_18], r9d
0x180015a15  push    rbp
0x180015a16  push    rbx
0x180015a17  push    rsi
0x180015a18  push    rdi
0x180015a19  push    r12
0x180015a1b  push    r13
0x180015a1d  push    r14
0x180015a1f  push    r15
0x180015a21  lea     rbp, [rsp-17h]
0x180015a26  sub     rsp, 0C8h
0x180015a2d  mov     rbx, rdx
0x180015a30  mov     r13, rcx
0x180015a33  lea     rsi, WPP_GLOBAL_Control
0x180015a3a  mov     rcx, cs:WPP_GLOBAL_Control
0x180015a41  cmp     rcx, rsi
0x180015a44  jz      short loc_180015A50
0x180015a46  test    byte ptr [rcx+1Ch], 1
0x180015a4a  jnz     loc_180015F7F
0x180015a50  mov     r8, 0FFFFFFFFFFFFFFFFh
0x180015a57  mov     rax, r8
0x180015a5a  nop     word ptr [rax+rax+00h]
0x180015a60  inc     rax
0x180015a63  cmp     word ptr [rbx+rax*2], 0
0x180015a68  jnz     short loc_180015A60
0x180015a6a  inc     rax
0x180015a6d  mov     edi, 2
0x180015a72  cmp     rax, rdi
0x180015a75  cmova   edi, eax
0x180015a78  mov     eax, 2
0x180015a7d  mul     rdi
0x180015a80  cmovb   rax, r8
0x180015a84  mov     rcx, rax
0x180015a87  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x180015a8d  mov     r14, rax
0x180015a90  test    rax, rax
0x180015a93  jnz     short loc_180015AD2
0x180015a95  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180015a9b  mov     edx, 80041006h
0x180015aa0  mov     rcx, rax
0x180015aa3  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180015aa9  mov     rcx, cs:WPP_GLOBAL_Control
0x180015ab0  cmp     rcx, rsi
0x180015ab3  jnz     loc_180015FA6
0x180015ab9  mov     eax, 80041006h
0x180015abe  add     rsp, 0C8h
0x180015ac5  pop     r15
0x180015ac7  pop     r14
0x180015ac9  pop     r13
0x180015acb  pop     r12
0x180015acd  pop     rdi
0x180015ace  pop     rsi
0x180015acf  pop     rbx
0x180015ad0  pop     rbp
0x180015ad1  retn
0x180015ad2  mov     [rbp+4Fh+var_68], r14
0x180015ad6  mov     byte ptr [rbp+4Fh+arg_18], 0
0x180015ada  xor     r15d, r15d
0x180015add  mov     [rbp+4Fh+var_B8], r15
0x180015ae1  mov     [rsp+100h+var_D0], r15; unsigned __int16 **
0x180015ae6  lea     rax, [rbp+4Fh+arg_18]
0x180015aea  mov     [rsp+100h+var_D8], rax; bool *
0x180015aef  lea     rax, [rbp+4Fh+var_B8]
0x180015af3  mov     [rsp+100h+var_E0], rax; unsigned __int16 **
0x180015af8  mov     r9, rdi; unsigned __int64
0x180015afb  mov     r8, r14; unsigned __int16 *
0x180015afe  mov     rdx, rbx; unsigned __int16 *
0x180015b01  mov     rcx, r13; this
0x180015b04  call    ?ComputeKeyFromPath@CNamespaceHandle@@IEAAJPEBGPEAG_KPEAPEAGPEA_N3@Z; CNamespaceHandle::ComputeKeyFromPath(ushort const *,ushort *,unsigned __int64,ushort * *,bool *,ushort * *)
0x180015b09  mov     ebx, eax
0x180015b0b  test    eax, eax
0x180015b0d  js      loc_180015FDA
0x180015b13  mov     r12, [rbp+4Fh+var_B8]
0x180015b17  mov     [rbp+4Fh+var_60], r12
0x180015b1b  mov     [rbp+4Fh+var_C0], r15
0x180015b1f  lea     rcx, [r13+20h]
0x180015b23  call    cs:__imp_?Length@WString@@QEBAHXZ; WString::Length(void)
0x180015b29  test    eax, eax
0x180015b2b  jg      loc_180015C67
0x180015b31  mov     rbx, [rbp+4Fh+var_C0]
0x180015b35  mov     [rbp+4Fh+var_58], rbx
0x180015b39  mov     ecx, 70h ; 'p'
0x180015b3e  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x180015b44  mov     rsi, rax
0x180015b47  mov     [rbp+4Fh+var_70], rax
0x180015b4b  test    rax, rax
0x180015b4e  jnz     loc_180015CED
0x180015b54  lea     rdi, WPP_GLOBAL_Control
0x180015b5b  test    rsi, rsi
0x180015b5e  jz      loc_18001602D
0x180015b64  mov     rax, [rsi]
0x180015b67  mov     rcx, rsi
0x180015b6a  mov     rax, [rax+8]
0x180015b6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015b73  mov     [rbp+4Fh+var_70], rsi
0x180015b77  mov     rcx, [rbp+4Fh+var_C0]
0x180015b7b  test    rcx, rcx
0x180015b7e  jnz     loc_180015DB9
0x180015b84  lea     rcx, [r13+20h]
0x180015b88  call    cs:__imp_??BWString@@QEAAPEAGXZ; WString::operator ushort *(void)
0x180015b8e  mov     rdx, rax
0x180015b91  lea     rcx, [rbp+4Fh+var_98]
0x180015b95  call    cs:__imp_??0WString2@@QEAA@PEBG@Z; WString2::WString2(ushort const *)
0x180015b9b  nop
0x180015b9c  lea     rcx, [rbp+4Fh+var_98]
0x180015ba0  call    cs:__imp_?Length@WString2@@QEBAHXZ; WString2::Length(void)
0x180015ba6  test    eax, eax
0x180015ba8  jg      loc_180015C51
0x180015bae  mov     rdx, r14
0x180015bb1  lea     rcx, [rbp+4Fh+var_98]
0x180015bb5  call    cs:__imp_??YWString2@@QEAAAEAV0@PEBG@Z; WString2::operator+=(ushort const *)
0x180015bbb  lea     rcx, [rbp+4Fh+var_98]
0x180015bbf  call    cs:__imp_??BWString2@@QEAAPEAGXZ; WString2::operator ushort *(void)
0x180015bc5  mov     rdx, rax; unsigned __int16 *
0x180015bc8  xor     r8d, r8d; unsigned __int16 *
0x180015bcb  mov     rcx, rsi; this
0x180015bce  call    ?Initialize@CNamespaceHandle@@QEAAJPEBG0@Z; CNamespaceHandle::Initialize(ushort const *,ushort const *)
0x180015bd3  mov     edi, eax
0x180015bd5  test    eax, eax
0x180015bd7  js      short loc_180015BE4
0x180015bd9  mov     rax, [rsi+58h]
0x180015bdd  mov     dword ptr [rax+30h], 0
0x180015be4  lea     rcx, [rbp+4Fh+var_98]
0x180015be8  call    cs:__imp_??1WString2@@QEAA@XZ; WString2::~WString2(void)
0x180015bee  test    edi, edi
0x180015bf0  js      loc_180016171
0x180015bf6  mov     rax, [rsi]
0x180015bf9  mov     r8, [rbp+4Fh+arg_20]
0x180015bfd  lea     rdx, IID_IWmiDbHandle
0x180015c04  mov     rcx, rsi
0x180015c07  mov     rax, [rax]
0x180015c0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015c0f  mov     edi, eax
0x180015c11  mov     rcx, [rsi]
0x180015c14  mov     rax, [rcx+10h]
0x180015c18  mov     rcx, rsi
0x180015c1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015c20  nop
0x180015c21  test    rbx, rbx
0x180015c24  jz      short loc_180015C36
0x180015c26  mov     rax, [rbx]
0x180015c29  mov     rcx, rbx
0x180015c2c  mov     rax, [rax+10h]
0x180015c30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015c35  nop
0x180015c36  mov     rcx, r12
0x180015c39  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x180015c3f  nop
0x180015c40  mov     rcx, r14
0x180015c43  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x180015c49  nop
0x180015c4a  mov     eax, edi
0x180015c4c  jmp     loc_180015ABE
0x180015c51  lea     rdx, asc_18004B0E0; "\\"
0x180015c58  lea     rcx, [rbp+4Fh+var_98]
0x180015c5c  call    cs:__imp_??YWString2@@QEAAAEAV0@PEBG@Z; WString2::operator+=(ushort const *)
0x180015c62  jmp     loc_180015BAE
0x180015c67  lea     rax, [rbp+4Fh+var_C0]
0x180015c6b  mov     [rsp+100h+var_E0], rax; void **
0x180015c70  lea     r9, IID__IWmiObject; struct _GUID *
0x180015c77  mov     r8, r14; unsigned __int16 *
0x180015c7a  mov     rdx, [rbp+4Fh+var_B8]; unsigned __int16 *
0x180015c7e  mov     rcx, r13; this
0x180015c81  call    ?GetInstanceByKey@CNamespaceHandle@@IEAAJPEBG0AEBU_GUID@@PEAPEAX@Z; CNamespaceHandle::GetInstanceByKey(ushort const *,ushort const *,_GUID const &,void * *)
0x180015c86  mov     ebx, eax
0x180015c88  test    eax, eax
0x180015c8a  jns     loc_180015B31
0x180015c90  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180015c96  mov     edx, ebx
0x180015c98  mov     rcx, rax
0x180015c9b  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180015ca1  mov     rcx, cs:WPP_GLOBAL_Control
0x180015ca8  cmp     rcx, rsi
0x180015cab  jz      short loc_180015CD2
0x180015cad  test    byte ptr [rcx+1Ch], 1
0x180015cb1  jz      short loc_180015CD2
0x180015cb3  cmp     byte ptr [rcx+19h], 2
0x180015cb7  jb      short loc_180015CD2
0x180015cb9  mov     edx, 65h ; 'e'
0x180015cbe  mov     r9d, ebx
0x180015cc1  lea     r8, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids
0x180015cc8  mov     rcx, [rcx+10h]
0x180015ccc  call    WPP_SF_d
0x180015cd1  nop
0x180015cd2  mov     rcx, r12
0x180015cd5  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x180015cdb  nop
0x180015cdc  mov     rcx, r14
0x180015cdf  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x180015ce5  nop
0x180015ce6  mov     eax, ebx
0x180015ce8  jmp     loc_180015ABE
0x180015ced  mov     rdi, [r13+18h]
0x180015cf1  mov     rcx, [r13+10h]
0x180015cf5  lea     rax, ??_7?$CUnkBase@UIWmiDbHandle@@$1?IID_IWmiDbHandle@@3U_GUID@@B@@6B@; const CUnkBase<IWmiDbHandle,&_GUID const IID_IWmiDbHandle>::`vftable'
0x180015cfc  mov     [rsi], rax
0x180015cff  mov     dword ptr [rsi+8], 0
0x180015d06  mov     [rsi+10h], rcx
0x180015d0a  test    rcx, rcx
0x180015d0d  jz      short loc_180015D1E
0x180015d0f  mov     rax, [rcx]
0x180015d12  mov     rdx, rsi
0x180015d15  mov     rax, [rax]
0x180015d18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015d1d  nop
0x180015d1e  lea     rax, ??_7CNamespaceHandle@@6B@; const CNamespaceHandle::`vftable'
0x180015d25  mov     [rsi], rax
0x180015d28  mov     [rsi+18h], rdi
0x180015d2c  lea     rcx, [rsi+20h]
0x180015d30  call    cs:__imp_??0WString@@QEAA@XZ; WString::WString(void)
0x180015d36  nop
0x180015d37  lea     rcx, [rsi+28h]
0x180015d3b  call    cs:__imp_??0WString@@QEAA@XZ; WString::WString(void)
0x180015d41  nop
0x180015d42  lea     rcx, [rsi+30h]
0x180015d46  call    cs:__imp_??0WString@@QEAA@XZ; WString::WString(void)
0x180015d4c  nop
0x180015d4d  xor     eax, eax
0x180015d4f  mov     [rsi+58h], rax
0x180015d53  mov     [rsi+60h], rax
0x180015d57  mov     word ptr [rsi+68h], 100h
0x180015d5d  mov     rcx, cs:WPP_GLOBAL_Control
0x180015d64  lea     rdi, WPP_GLOBAL_Control
0x180015d6b  cmp     rcx, rdi
0x180015d6e  jnz     short loc_180015D96
0x180015d70  mov     rcx, [rsi+18h]
0x180015d74  mov     rax, [rcx]
0x180015d77  mov     rax, [rax+8]
0x180015d7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015d80  xor     eax, eax
0x180015d82  mov     [rsi+38h], rax
0x180015d86  mov     [rsi+48h], rax
0x180015d8a  lock inc cs:?s_lActiveRepNs@CNamespaceHandle@@1JA; long CNamespaceHandle::s_lActiveRepNs
0x180015d91  jmp     loc_180015B5B
0x180015d96  test    byte ptr [rcx+1Ch], 1
0x180015d9a  jz      short loc_180015D70
0x180015d9c  cmp     byte ptr [rcx+19h], 5
0x180015da0  jb      short loc_180015D70
0x180015da2  mov     edx, 51h ; 'Q'
0x180015da7  lea     r8, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids
0x180015dae  mov     rcx, [rcx+10h]
0x180015db2  call    WPP_SF_
0x180015db7  jmp     short loc_180015D70
0x180015db9  mov     rax, [rcx]
0x180015dbc  lea     rdx, aNamespace_1; "__Namespace"
0x180015dc3  mov     rax, [rax+90h]
0x180015dca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015dcf  test    eax, eax
0x180015dd1  jz      loc_180015B84
0x180015dd7  xorps   xmm0, xmm0
0x180015dda  xor     eax, eax
0x180015ddc  movups  xmmword ptr [rbp+4Fh+pvarg], xmm0
0x180015de0  mov     qword ptr [rbp+4Fh+pvarg+10h], rax
0x180015de4  lea     rcx, [rbp+4Fh+pvarg]; pvarg
0x180015de8  call    cs:__imp_VariantInit
0x180015dee  lea     rax, [rbp+4Fh+pvarg]
0x180015df2  mov     [rbp+4Fh+var_50], rax
0x180015df6  mov     rcx, [rbp+4Fh+var_C0]
0x180015dfa  mov     rax, [rcx]
0x180015dfd  xor     edx, edx
0x180015dff  mov     [rsp+100h+var_D8], rdx
0x180015e04  mov     [rsp+100h+var_E0], rdx
0x180015e09  lea     r9, [rbp+4Fh+pvarg]
0x180015e0d  xor     r8d, r8d
0x180015e10  lea     rdx, aRelpath_0; "__RELPATH"
0x180015e17  mov     rax, [rax+20h]
0x180015e1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015e20  mov     edi, eax
0x180015e22  test    eax, eax
0x180015e24  jns     loc_180016085
0x180015e2a  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180015e30  mov     edx, edi
0x180015e32  mov     rcx, rax
0x180015e35  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180015e3b  mov     rcx, cs:WPP_GLOBAL_Control
0x180015e42  lea     rax, WPP_GLOBAL_Control
0x180015e49  cmp     rcx, rax
0x180015e4c  jz      short loc_180015E73
0x180015e4e  test    byte ptr [rcx+1Ch], 1
0x180015e52  jz      short loc_180015E73
0x180015e54  cmp     byte ptr [rcx+19h], 2
0x180015e58  jb      short loc_180015E73
0x180015e5a  mov     edx, 67h ; 'g'
0x180015e5f  mov     r9d, edi
0x180015e62  lea     r8, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids
0x180015e69  mov     rcx, [rcx+10h]
0x180015e6d  call    WPP_SF_d
0x180015e72  nop
0x180015e73  lea     rcx, [rbp+4Fh+pvarg]; pvarg
0x180015e77  call    cs:__imp_VariantClear
0x180015e7d  nop
0x180015e7e  mov     rax, [rsi]
0x180015e81  mov     rcx, rsi
0x180015e84  mov     rax, [rax+10h]
0x180015e88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015e8d  nop
0x180015e8e  test    rbx, rbx
0x180015e91  jz      short loc_180015EA3
0x180015e93  mov     rax, [rbx]
0x180015e96  mov     rcx, rbx
  ... truncated ...
```
