# CESimSettingServer::UpdateESimProfileCache(__MIDL_imports_0041 *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,bool)

- ea: `0x1800273e8`
- end: `0x18002823b`
- name: `?UpdateESimProfileCache@CESimSettingServer@@AEAAXPEAU__MIDL_imports_0041@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N@Z`
- size: `3667`
- prototype: ``
- caller_count: `1`
- callee_count: `20`
- tags: `file_ops, registry_config, installer_update`

## callers

- `0x180024334`

## callees

- `0x18000178c`
- `0x1800024e0`
- `0x1800028b0`
- `0x180002efc`
- `0x1800040d9`
- `0x180009ffc`
- `0x18001105c`
- `0x1800171b8`
- `0x1800172bc`
- `0x18001dd10`
- `0x18001e0d0`
- `0x18001e184`
- `0x18001e4f4`
- `0x18001ee30`
- `0x180020994`
- `0x180020b40`
- `0x18002163c`
- `0x1800273e8`
- `0x180028910`
- `0x18005c010`

## string_xrefs

- `0x180027482`: `CESimSettingServer::UpdateESimProfileCache`
- `0x18002803b`: `CESimSettingServer::UpdateESimProfileCache`
- `0x1800280ff`: `CESimSettingServer::UpdateESimProfileCache`
- `0x1800281c2`: `CESimSettingServer::UpdateESimProfileCache`
- `0x180028197`: `The eSim profile does not exist in cache. profileId = %ls`
- `0x18002751b`: `The eSIM profile update is missing LPA_PROFILE_INFO, dwParam = 0x%08x.`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
void __fastcall CESimSettingServer::UpdateESimProfileCache(__int64 a1, __int64 a2, __int64 a3)
{
  const struct _tlgProvider_t *v6; // rax
  __int64 v7; // r8
  __int64 v8; // r9
  const struct _tlgProvider_t *v9; // rax
  __int64 v10; // r8
  __int64 v11; // r9
  unsigned __int16 **v12; // rcx
  const struct _tlgProvider_t *v13; // rax
  __int64 v14; // r8
  __int64 v15; // r9
  const struct _tlgProvider_t *v16; // rax
  __int64 v17; // r8
  __int64 v18; // r9
  const struct _tlgProvider_t *v19; // rax
  __int64 v20; // r8
  __int64 v21; // r9
  const struct _tlgProvider_t *v22; // rax
  __int64 v23; // r8
  __int64 v24; // r9
  const struct _tlgProvider_t *v25; // rax
  __int64 v26; // r8
  __int64 v27; // r9
  const struct _tlgProvider_t *v28; // rax
  __int64 v29; // r8
  __int64 v30; // r9
  __int64 *v31; // rax
  __int64 v32; // r13
  _QWORD **v33; // r10
  _QWORD *i; // rbx
  _WORD *v35; // r12
  unsigned __int16 *v36; // r15
  unsigned __int16 *v37; // rcx
  int v38; // edx
  int v39; // r8d
  __int64 **v40; // rdx
  __int64 *j; // rcx
  __int64 *k; // rdx
  _QWORD **v43; // r9
  unsigned __int16 *v44; // rax
  int v45; // ecx
  int v46; // edx
  __int64 v47; // r9
  unsigned __int64 v48; // r14
  char **v49; // rdi
  __int64 v50; // rdi
  unsigned __int16 *v51; // rbx
  __int64 v52; // r9
  unsigned __int64 v53; // r14
  char v54; // r14
  int v55; // eax
  __int64 v56; // rbx
  __int64 v57; // rdx
  _WORD *v58; // rcx
  __int16 *v59; // r8
  unsigned __int16 *v60; // rax
  int v61; // r10d
  __int64 v62; // rax
  __int16 v63; // r10
  _WORD *v64; // rcx
  unsigned __int16 *v65; // r8
  unsigned __int16 *v66; // rax
  int v67; // r10d
  char v68; // r11
  __int64 v69; // rax
  __int64 v70; // rax
  const unsigned __int16 *v71; // r8
  _WORD *v72; // rcx
  unsigned __int16 *v73; // rdx
  unsigned __int16 *v74; // rax
  int v75; // r8d
  __int64 v76; // r8
  __int64 v77; // rax
  unsigned __int64 v78; // rbx
  __int64 v79; // r12
  __int64 v80; // rdx
  unsigned __int64 v81; // rcx
  size_t v82; // rax
  size_t v83; // rbx
  _WORD *v84; // rcx
  __int16 *v85; // rdx
  unsigned __int16 *v86; // rax
  int v87; // r8d
  __int64 v88; // rax
  __int16 v89; // r8
  int v90; // eax
  __int64 v91; // rdx
  const struct _tlgProvider_t *v92; // rax
  __int64 v93; // r8
  __int64 v94; // r9
  const struct _tlgProvider_t *v95; // rax
  __int64 v96; // r8
  __int64 v97; // r9
  const struct _tlgProvider_t *v98; // rax
  __int64 v99; // r8
  __int64 v100; // r9
  __int64 v101; // [rsp+20h] [rbp-69h]
  char v102; // [rsp+30h] [rbp-59h]
  unsigned __int16 *v103[2]; // [rsp+38h] [rbp-51h] BYREF
  __int64 v104; // [rsp+48h] [rbp-41h]
  unsigned __int16 *v105[2]; // [rsp+50h] [rbp-39h] BYREF
  __int64 v106; // [rsp+60h] [rbp-29h]
  unsigned __int16 *AdapterSlotPair; // [rsp+68h] [rbp-21h] BYREF
  char v108; // [rsp+70h] [rbp-19h]
  __int64 v109; // [rsp+78h] [rbp-11h]
  unsigned __int16 *v110[2]; // [rsp+80h] [rbp-9h] BYREF
  __int64 v111; // [rsp+90h] [rbp+7h]
  __int64 v112; // [rsp+98h] [rbp+Fh]

  v109 = a1;
  *(_OWORD *)v103 = 0;
  v104 = 0;
  *(_OWORD *)v105 = 0;
  v106 = 0;
  std::vector<unsigned short>::resize(v103);
  std::vector<unsigned short>::resize(v105);
  StringCchPrintfW(v103[0], v103[1] - v103[0], L"Enter");
  StringCchPrintfW(v105[0], v105[1] - v105[0], L"%S(%d):%s", "CESimSettingServer::UpdateESimProfileCache", 944, v103[0]);
  v6 = MbaeApiLogging::Provider();
  if ( *(_DWORD *)v6 > 5u )
  {
    AdapterSlotPair = v105[0];
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
      (__int64)v6,
      (__int64)&byte_180075787,
      v7,
      v8,
      (const unsigned __int16 **)&AdapterSlotPair);
  }
  std::vector<unsigned short>::~vector<unsigned short>((char **)v105);
  std::vector<unsigned short>::~vector<unsigned short>((char **)v103);
  if ( (*(_BYTE *)(a2 + 4) & 1) == 0 )
  {
    *(_OWORD *)v105 = 0;
    v106 = 0;
    *(_OWORD *)v103 = 0;
    v104 = 0;
    std::vector<unsigned short>::resize(v105);
    std::vector<unsigned short>::resize(v103);
    StringCchPrintfW(
      v105[0],
      v105[1] - v105[0],
      L"The eSIM profile update is missing LPA_PROFILE_INFO, dwParam = 0x%08x.",
      *(unsigned int *)(a2 + 4));
    LODWORD(v101) = 948;
    StringCchPrintfW(
      v103[0],
      v103[1] - v103[0],
      L"%S(%d):%s",
      "CESimSettingServer::UpdateESimProfileCache",
      v101,
      v105[0]);
    v9 = MbaeApiLogging::Provider();
    if ( *(_DWORD *)v9 > 2u )
    {
      AdapterSlotPair = v103[0];
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
        (__int64)v9,
        (__int64)&word_180075766,
        v10,
        v11,
        (const unsigned __int16 **)&AdapterSlotPair);
    }
    std::vector<unsigned short>::~vector<unsigned short>((char **)v103);
    v12 = v105;
    goto LABEL_160;
  }
  if ( (*(_BYTE *)(a2 + 8) & 2) != 0 )
  {
    *(_OWORD *)v105 = 0;
    v106 = 0;
    *(_OWORD *)v103 = 0;
    v104 = 0;
    std::vector<unsigned short>::resize(v105);
    std::vector<unsigned short>::resize(v103);
    StringCchPrintfW(v105[0], v105[1] - v105[0], L"Get profile details: state=0x%08x", *(unsigned int *)(a2 + 56));
    LODWORD(v101) = 956;
    StringCchPrintfW(
      v103[0],
      v103[1] - v103[0],
      L"%S(%d):%s",
      "CESimSettingServer::UpdateESimProfileCache",
      v101,
      v105[0]);
    v13 = MbaeApiLogging::Provider();
    if ( *(_DWORD *)v13 > 4u )
    {
      AdapterSlotPair = v103[0];
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
        (__int64)v13,
        (__int64)&word_180075746,
        v14,
        v15,
        (const unsigned __int16 **)&AdapterSlotPair);
    }
    std::vector<unsigned short>::~vector<unsigned short>((char **)v103);
    std::vector<unsigned short>::~vector<unsigned short>((char **)v105);
  }
  if ( (*(_BYTE *)(a2 + 4) & 8) != 0 )
  {
    *(_OWORD *)v105 = 0;
    v106 = 0;
    *(_OWORD *)v103 = 0;
    v104 = 0;
    std::vector<unsigned short>::resize(v105);
    std::vector<unsigned short>::resize(v103);
    StringCchPrintfW(v105[0], v105[1] - v105[0], L"Get profile details: nickname=%ls", a2 + 266);
    LODWORD(v101) = 960;
    StringCchPrintfW(
      v103[0],
      v103[1] - v103[0],
      L"%S(%d):%s",
      "CESimSettingServer::UpdateESimProfileCache",
      v101,
      v105[0]);
    v16 = MbaeApiLogging::Provider();
    if ( *(_DWORD *)v16 > 4u )
    {
      AdapterSlotPair = v103[0];
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
        (__int64)v16,
        (__int64)&word_180075726,
        v17,
        v18,
        (const unsigned __int16 **)&AdapterSlotPair);
    }
    std::vector<unsigned short>::~vector<unsigned short>((char **)v103);
    std::vector<unsigned short>::~vector<unsigned short>((char **)v105);
  }
  if ( (*(_BYTE *)(a2 + 4) & 0x10) != 0 )
  {
    *(_OWORD *)v105 = 0;
    v106 = 0;
    *(_OWORD *)v103 = 0;
    v104 = 0;
    std::vector<unsigned short>::resize(v105);
    std::vector<unsigned short>::resize(v103);
    StringCchPrintfW(v105[0], v105[1] - v105[0], L"Get profile details: providername=%ls", a2 + 396);
    LODWORD(v101) = 964;
    StringCchPrintfW(
      v103[0],
      v103[1] - v103[0],
      L"%S(%d):%s",
      "CESimSettingServer::UpdateESimProfileCache",
      v101,
      v105[0]);
    v19 = MbaeApiLogging::Provider();
    if ( *(_DWORD *)v19 > 4u )
    {
      AdapterSlotPair = v103[0];
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
        (__int64)v19,
        (__int64)&word_180075706,
        v20,
        v21,
        (const unsigned __int16 **)&AdapterSlotPair);
    }
    std::vector<unsigned short>::~vector<unsigned short>((char **)v103);
    std::vector<unsigned short>::~vector<unsigned short>((char **)v105);
  }
  if ( (*(_BYTE *)(a2 + 4) & 2) != 0 )
  {
    *(_OWORD *)v105 = 0;
    v106 = 0;
    *(_OWORD *)v103 = 0;
    v104 = 0;
    std::vector<unsigned short>::resize(v105);
    std::vector<unsigned short>::resize(v103);
    StringCchPrintfW(v105[0], v105[1] - v105[0], L"Get profile details: dwPolicies=0x%08x", *(unsigned int *)(a2 + 128));
    LODWORD(v101) = 968;
    StringCchPrintfW(
      v103[0],
      v103[1] - v103[0],
      L"%S(%d):%s",
      "CESimSettingServer::UpdateESimProfileCache",
      v101,
      v105[0]);
    v22 = MbaeApiLogging::Provider();
    if ( *(_DWORD *)v22 > 4u )
    {
      AdapterSlotPair = v103[0];
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
        (__int64)v22,
        (__int64)&word_1800756E6,
        v23,
        v24,
        (const unsigned __int16 **)&AdapterSlotPair);
    }
    std::vector<unsigned short>::~vector<unsigned short>((char **)v103);
    std::vector<unsigned short>::~vector<unsigned short>((char **)v105);
  }
  if ( (*(_BYTE *)(a2 + 4) & 4) != 0 )
  {
    *(_OWORD *)v105 = 0;
    v106 = 0;
    *(_OWORD *)v103 = 0;
    v104 = 0;
    std::vector<unsigned short>::resize(v105);
    std::vector<unsigned short>::resize(v103);
    StringCchPrintfW(
      v105[0],
      v105[1] - v105[0],
      L"Get profile details: profileClass=0x%08x",
      *(unsigned int *)(a2 + 132));
    LODWORD(v101) = 972;
    StringCchPrintfW(
      v103[0],
      v103[1] - v103[0],
      L"%S(%d):%s",
      "CESimSettingServer::UpdateESimProfileCache",
      v101,
      v105[0]);
    v25 = MbaeApiLogging::Provider();
    if ( *(_DWORD *)v25 > 4u )
    {
      AdapterSlotPair = v103[0];
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
        (__int64)v25,
        (__int64)&word_1800756C6,
        v26,
        v27,
        (const unsigned __int16 **)&AdapterSlotPair);
    }
    std::vector<unsigned short>::~vector<unsigned short>((char **)v103);
    std::vector<unsigned short>::~vector<unsigned short>((char **)v105);
  }
  if ( (*(_DWORD *)(a2 + 4) & 0x400) != 0 )
  {
    *(_OWORD *)v105 = 0;
    v106 = 0;
    *(_OWORD *)v103 = 0;
    v104 = 0;
    std::vector<unsigned short>::resize(v105);
    std::vector<unsigned short>::resize(v103);
    StringCchPrintfW(v105[0], v105[1] - v105[0], L"Get profile details: hriServerAddress=%ls", a2 + 478);
    LODWORD(v101) = 976;
    StringCchPrintfW(
      v103[0],
      v103[1] - v103[0],
      L"%S(%d):%s",
      "CESimSettingServer::UpdateESimProfileCache",
      v101,
      v105[0]);
    v28 = MbaeApiLogging::Provider();
    if ( *(_DWORD *)v28 > 4u )
    {
      AdapterSlotPair = v103[0];
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
        (__int64)v28,
        (__int64)&word_1800756A6,
        v29,
        v30,
        (const unsigned __int16 **)&AdapterSlotPair);
    }
    std::vector<unsigned short>::~vector<unsigned short>((char **)v103);
    std::vector<unsigned short>::~vector<unsigned short>((char **)v105);
  }
  if ( *(_QWORD *)(a3 + 16) )
  {
    v32 = *(_QWORD *)(CESimSettingServer::GetAdapterSlotData(a1, a3) + 16);
    if ( !v32 )
      goto LABEL_157;
    v43 = *(_QWORD ***)(v32 + 568);
    for ( i = *v43; ; i = (_QWORD *)*i )
    {
      if ( i == v43 )
        goto LABEL_157;
      v35 = (_WORD *)(a2 + 12);
      v36 = (unsigned __int16 *)i[2];
      v44 = v36;
      do
      {
        v45 = *(unsigned __int16 *)((char *)v44 + a2 + 12 - (_QWORD)v36);
        v46 = *v44 - v45;
        if ( v46 )
          break;
        ++v44;
      }
      while ( v45 );
      if ( !v46 )
        break;
    }
    if ( !v36 )
      goto LABEL_157;
LABEL_61:
    AdapterSlotPair = (unsigned __int16 *)CESimSettingServer::GetAdapterSlotPair(a1, v32);
    if ( *(_DWORD *)(a2 + 56) == 2 )
    {
      *(_QWORD *)i[1] = *i;
      *(_QWORD *)(*i + 8LL) = i[1];
      v48 = -1;
      --*(_QWORD *)(v32 + 576);
      v49 = (char **)i[2];
      if ( v49 )
      {
        std::vector<unsigned char>::~vector<unsigned char>(v49 + 113);
        operator delete(v49);
      }
      operator delete(i);
      *(_OWORD *)v110 = 0;
      v111 = 0;
      v112 = 0;
      do
        ++v48;
      while ( v35[v48] );
      std::wstring::_Construct<1,unsigned short const *>((char **)v110, v35, v48);
      std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::erase(
        v32 + 584,
        v110);
      std::wstring::~wstring((char **)v110);
      v50 = v109;
      v51 = AdapterSlotPair;
      (*(void (__fastcall **)(__int64, unsigned __int16 *, _QWORD, _WORD *))(*(_QWORD *)(v109 + 8) + 72LL))(
        v109 + 8,
        AdapterSlotPair,
        *((unsigned int *)AdapterSlotPair + 4),
        v35);
      goto LABEL_147;
    }
    if ( (*(_BYTE *)(a2 + 4) & 4) != 0 && *(_DWORD *)(a2 + 132) == 1 )
    {
      *(_OWORD *)v110 = 0;
      v111 = 0;
      v112 = 0;
      v53 = -1;
      do
        ++v53;
      while ( v35[v53] );
      std::wstring::_Construct<1,unsigned short const *>((char **)v110, v35, v53);
      std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::_Emplace<std::wstring>(
        v32 + 584,
        v105,
        v110);
      std::wstring::~wstring((char **)v110);
    }
    v102 = 0;
    v54 = 0;
    if ( (*(_BYTE *)(a2 + 8) & 2) != 0 && *((_BYTE *)v36 + 42) != (*(_DWORD *)(a2 + 56) == 1) )
    {
      v102 = 1;
      *((_BYTE *)v36 + 42) = *(_DWORD *)(a2 + 56) == 1;
    }
    if ( (*(_BYTE *)(a2 + 4) & 2) != 0 )
    {
      v55 = *(_DWORD *)(a2 + 128);
      if ( *((_DWORD *)v36 + 11) != v55 )
      {
        v102 = 1;
        *((_DWORD *)v36 + 11) = v55;
      }
    }
    v56 = 2147483646;
    v57 = 65;
    if ( (*(_DWORD *)(a2 + 4) & 0x800) != 0 )
    {
      v58 = v36 + 26;
      v59 = (__int16 *)(a2 + 136);
      v60 = (unsigned __int16 *)(a2 + 136);
      do
      {
        LODWORD(v47) = *(unsigned __int16 *)((char *)v36 + (_QWORD)v60 - a2 - 84);
        v61 = *v60 - (_DWORD)v47;
        if ( v61 )
          break;
        ++v60;
      }
      while ( (_DWORD)v47 );
      if ( v61 )
      {
        v102 = 1;
        v47 = 2147483646;
        v62 = 65;
        while ( v47 )
        {
          v63 = *v59;
          if ( *v59 )
          {
            ++v59;
            *v58++ = v63;
            --v47;
            if ( --v62 )
              continue;
          }
          if ( !v62 )
            --v58;
          break;
        }
        *v58 = 0;
      }
    }
    v64 = v36 + 91;
    if ( (*(_BYTE *)(a2 + 4) & 8) != 0 )
    {
      v65 = (unsigned __int16 *)(a2 + 266);
      v66 = (unsigned __int16 *)(a2 + 266);
      do
      {
        LODWORD(v47) = *(unsigned __int16 *)((char *)v64 + (_QWORD)v66 - a2 - 266);
        v67 = *v66 - (_DWORD)v47;
        if ( v67 )
          break;
        ++v66;
      }
      while ( (_DWORD)v47 );
      if ( v67 )
      {
        v68 = 1;
        v102 = 1;
        v69 = 2147483646;
        while ( v69 )
        {
          LODWORD(v47) = *v65;
          if ( (_WORD)v47 )
          {
            ++v65;
            *v64++ = v47;
            --v69;
            if ( --v57 )
              continue;
          }
          goto LABEL_99;
        }
LABEL_101:
        *v64 = 0;
LABEL_109:
        if ( (*(_BYTE *)(a2 + 4) & 0x10) != 0 )
        {
          v72 = v36 + 156;
          v73 = (unsigned __int16 *)(a2 + 396);
          v74 = (unsigned __int16 *)(a2 + 396);
          do
          {
            v75 = *(unsigned __int16 *)((char *)v36 + (_QWORD)v74 - a2 - 84);
            LODWORD(v47) = *v74 - v75;
            if ( (_DWORD)v47 )
              break;
            ++v74;
          }
          while ( v75 );
          if ( (_DWORD)v47 )
          {
            v68 = 1;
            v102 = 1;
            v76 = 2147483646;
            v77 = 33;
            while ( v76 )
            {
              LODWORD(v47) = *v73;
              if ( (_WORD)v47 )
              {
                ++v73;
                *v72++ = v47;
                --v76;
                if ( --v77 )
                  continue;
              }
              if ( !v77 )
                --v72;
              break;
            }
            *v72 = 0;
          }
        }
        if ( (*(_BYTE *)(a2 + 4) & 0xC0) != 0xC0 )
        {
LABEL_130:
          if ( (*(_DWORD *)(a2 + 4) & 0x400) != 0 )
          {
            v84 = v36 + 189;
            v85 = (__int16 *)(a2 + 478);
            v86 = (unsigned __int16 *)(a2 + 478);
            do
            {
              v87 = *(unsigned __int16 *)((char *)v36 + (_QWORD)v86 - a2 - 100);
              LODWORD(v47) = *v86 - v87;
              if ( (_DWORD)v47 )
                break;
              ++v86;
            }
            while ( v87 );
            if ( (_DWORD)v47 )
            {
              v68 = 1;
              v88 = 260;
              while ( v56 )
              {
                v89 = *v85;
                if ( *v85 )
                {
                  ++v85;
                  *v84++ = v89;
                  --v56;
                  if ( --v88 )
                    continue;
                }
                if ( !v88 )
                  --v84;
                break;
              }
              *v84 = 0;
            }
          }
          if ( (*(_BYTE *)(a2 + 4) & 4) == 0 || (v90 = *(_DWORD *)(a2 + 132), v90 == *((_DWORD *)v36 + 12)) )
          {
            if ( !v68 && !v54 )
            {
              *(_OWORD *)v110 = 0;
              v111 = 0;
              *(_OWORD *)v103 = 0;
              v104 = 0;
              std::vector<unsigned short>::resize(v110);
              std::vector<unsigned short>::resize(v103);
              StringCchPrintfW(v110[0], v110[1] - v110[0], L"No change in profile id: %ls", v36);
              LODWORD(v101) = 1115;
              StringCchPrintfW(
                v103[0],
                v103[1] - v103[0],
                L"%S(%d):%s",
                "CESimSettingServer::UpdateESimProfileCache",
                v101,
                v110[0]);
              v95 = MbaeApiLogging::Provider();
              if ( *(_DWORD *)v95 > 4u )
              {
                v105[0] = v103[0];
                _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
                  (__int64)v95,
                  (__int64)byte_180075665,
                  v96,
                  v97,
                  (const unsigned __int16 **)v105);
              }
              std::vector<unsigned short>::~vector<unsigned short>((char **)v103);
              std::vector<unsigned short>::~vector<unsigned short>((char **)v110);
              v50 = v109;
              goto LABEL_146;
            }
          }
          else
          {
            *((_DWORD *)v36 + 12) = v90;
          }
          LOBYTE(v47) = 1;
          v50 = v109;
          CESimSettingServer::NotifyESimProfile(v109, v32, (_DWORD)v36, v47, 0);
LABEL_146:
          v51 = AdapterSlotPair;
LABEL_147:
          v91 = *(_QWORD *)(v32 + 592);
          if ( *(_BYTE *)(v32 + 564) != (v91 != 0) )
          {
            *(_BYTE *)(v32 + 564) = v91 != 0;
            LOBYTE(v52) = v91 != 0;
            (*(void (__fastcall **)(__int64, unsigned __int16 *, _QWORD, __int64))(*(_QWORD *)(v50 + 8) + 104LL))(
              v50 + 8,
              v51,
              *((unsigned int *)v51 + 4),
              v52);
          }
          *(_OWORD *)v103 = 0;
          v104 = 0;
          *(_OWORD *)v110 = 0;
          v111 = 0;
          std::vector<unsigned short>::resize(v103);
          std::vector<unsigned short>::resize(v110);
          StringCchPrintfW(v103[0], v103[1] - v103[0], L"Exit");
          LODWORD(v101) = 1126;
          StringCchPrintfW(
            v110[0],
            v110[1] - v110[0],
            L"%S(%d):%s",
            "CESimSettingServer::UpdateESimProfileCache",
            v101,
            v103[0]);
          v92 = MbaeApiLogging::Provider();
          if ( *(_DWORD *)v92 > 5u )
          {
            v105[0] = v110[0];
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
              (__int64)v92,
              (__int64)word_180075642,
              v93,
              v94,
              (const unsigned __int16 **)v105);
          }
          goto LABEL_159;
        }
        v108 = 1;
        v78 = *(unsigned int *)(a2 + 1004);
        v79 = *((_QWORD *)v36 + 114);
        v80 = *((_QWORD *)v36 + 113);
        v81 = v79 - v80;
        if ( v78 < v79 - v80 )
        {
          v82 = v78 + v80;
LABEL_128:
          *((_QWORD *)v36 + 114) = v82;
          goto LABEL_129;
        }
        if ( v78 > v81 )
        {
          if ( v78 <= *((_QWORD *)v36 + 115) - v80 )
          {
            v83 = v78 - v81;
            memset_0(*((void **)v36 + 114), 0, v83);
            v82 = v83 + v79;
            goto LABEL_128;
          }
          std::vector<unsigned char>::_Resize_reallocate<std::_Value_init_tag>(v36 + 452, *(unsigned int *)(a2 + 1004));
        }
LABEL_129:
        memcpy_0(*((void **)v36 + 113), (const void *)(a2 + 1008), *(unsigned int *)(a2 + 1004));
        v68 = v102;
        v56 = 2147483646;
        v54 = v108;
        goto LABEL_130;
      }
    }
    else if ( *v64 )
    {
      v68 = 1;
      v102 = 1;
      v70 = 2147483646;
      v71 = &dword_1800684AC;
      while ( v70 )
      {
        LODWORD(v47) = *v71;
        if ( (_WORD)v47 )
        {
          ++v71;
          *v64++ = v47;
          --v70;
          if ( --v57 )
            continue;
        }
LABEL_99:
        if ( !v57 )
          --v64;
        goto LABEL_101;
      }
      goto LABEL_101;
    }
    v68 = v102;
    goto LABEL_109;
  }
  v31 = **(__int64 ***)(a1 + 88);
  while ( !*((_BYTE *)v31 + 25) )
  {
    v32 = *(_QWORD *)(v31[7] + 16);
    if ( v32 )
    {
      v33 = *(_QWORD ***)(v32 + 568);
      for ( i = *v33; i != v33; i = (_QWORD *)*i )
      {
        v35 = (_WORD *)(a2 + 12);
        v36 = (unsigned __int16 *)i[2];
        v37 = v36;
        do
        {
          v38 = *(unsigned __int16 *)((char *)v37 + a2 + 12 - (_QWORD)v36);
          v39 = *v37 - v38;
          if ( v39 )
            break;
          ++v37;
        }
        while ( v38 );
        if ( !v39 )
        {
          if ( v36 )
            goto LABEL_61;
          break;
        }
      }
    }
    v40 = (__int64 **)v31[2];
    if ( *((_BYTE *)v40 + 25) )
    {
      for ( j = (__int64 *)v31[1]; !*((_BYTE *)j + 25) && v31 == (__int64 *)j[2]; j = (__int64 *)j[1] )
        v31 = j;
      v31 = j;
    }
    else
    {
      v31 = (__int64 *)v31[2];
      for ( k = *v40; !*((_BYTE *)k + 25); k = (__int64 *)*k )
        v31 = k;
    }
  }
LABEL_157:
  *(_OWORD *)v103 = 0;
  v104 = 0;
  *(_OWORD *)v110 = 0;
  v111 = 0;
  std::vector<unsigned short>::resize(v103);
  std::vector<unsigned short>::resize(v110);
  StringCchPrintfW(v103[0], v103[1] - v103[0], L"The eSim profile does not exist in cache. profileId = %ls", a2 + 12);
  LODWORD(v101) = 1025;
  StringCchPrintfW(
    v110[0],
    v110[1] - v110[0],
    L"%S(%d):%s",
    "CESimSettingServer::UpdateESimProfileCache",
    v101,
    v103[0]);
  v98 = MbaeApiLogging::Provider();
  if ( *(_DWORD *)v98 > 2u )
  {
    v105[0] = v110[0];
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
      (__int64)v98,
      (__int64)byte_180075685,
      v99,
      v100,
      (const unsigned __int16 **)v105);
  }
LABEL_159:
  std::vector<unsigned short>::~vector<unsigned short>((char **)v110);
  v12 = v103;
LABEL_160:
  std::vector<unsigned short>::~vector<unsigned short>((char **)v12);
}

```

## disassembly

```asm
0x1800273e8  mov     [rsp-8+arg_18], rbx
0x1800273ed  push    rbp
0x1800273ee  push    rsi
0x1800273ef  push    rdi
0x1800273f0  push    r12
0x1800273f2  push    r13
0x1800273f4  push    r14
0x1800273f6  push    r15
0x1800273f8  lea     rbp, [rsp-27h]
0x1800273fd  sub     rsp, 0B0h
0x180027404  mov     rax, cs:__security_cookie
0x18002740b  xor     rax, rsp
0x18002740e  mov     [rbp+57h+var_40], rax
0x180027412  mov     rbx, r8
0x180027415  mov     rdi, rdx
0x180027418  mov     r14, rcx
0x18002741b  mov     [rbp+57h+var_68], rcx
0x18002741f  xorps   xmm0, xmm0
0x180027422  movdqu  xmmword ptr [rbp+57h+var_A8], xmm0
0x180027427  xor     r15d, r15d
0x18002742a  mov     [rbp+57h+var_98], r15
0x18002742e  movdqu  xmmword ptr [rbp+57h+var_90], xmm0
0x180027433  mov     [rbp+57h+var_80], r15
0x180027437  lea     rcx, [rbp+57h+var_A8]
0x18002743b  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x180027440  lea     rcx, [rbp+57h+var_90]
0x180027444  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x180027449  mov     rdx, [rbp+57h+var_A8+8]
0x18002744d  mov     rcx, [rbp+57h+var_A8]; unsigned __int16 *
0x180027451  sub     rdx, rcx
0x180027454  sar     rdx, 1; unsigned __int64
0x180027457  lea     r8, aEnter; "Enter"
0x18002745e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180027463  mov     rdx, [rbp+57h+var_90+8]
0x180027467  mov     rcx, [rbp+57h+var_90]; unsigned __int16 *
0x18002746b  sub     rdx, rcx
0x18002746e  sar     rdx, 1; unsigned __int64
0x180027471  mov     rax, [rbp+57h+var_A8]
0x180027475  mov     [rsp+0E0h+var_B8], rax
0x18002747a  mov     dword ptr [rsp+0E0h+var_C0], 3B0h
0x180027482  lea     r13, aCesimsettingse_29; "CESimSettingServer::UpdateESimProfileCa"...
0x180027489  mov     r9, r13
0x18002748c  lea     r8, aSDS; "%S(%d):%s"
0x180027493  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180027498  call    ?Provider@MbaeApiLogging@@SAPEBU_tlgProvider_t@@XZ; MbaeApiLogging::Provider(void)
0x18002749d  mov     ecx, [rax]
0x18002749f  cmp     ecx, 5
0x1800274a2  jbe     short loc_1800274C5
0x1800274a4  mov     rcx, [rbp+57h+var_90]
0x1800274a8  mov     [rbp+57h+var_78], rcx
0x1800274ac  lea     rcx, [rbp+57h+var_78]
0x1800274b0  mov     [rsp+0E0h+var_C0], rcx
0x1800274b5  lea     rdx, byte_180075787
0x1800274bc  mov     rcx, rax
0x1800274bf  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x1800274c4  nop
0x1800274c5  lea     rcx, [rbp+57h+var_90]
0x1800274c9  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x1800274ce  nop
0x1800274cf  lea     rcx, [rbp+57h+var_A8]
0x1800274d3  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x1800274d8  test    byte ptr [rdi+4], 1
0x1800274dc  jnz     loc_180027599
0x1800274e2  xorps   xmm0, xmm0
0x1800274e5  movdqu  xmmword ptr [rbp+57h+var_90], xmm0
0x1800274ea  mov     [rbp+57h+var_80], r15
0x1800274ee  movdqu  xmmword ptr [rbp+57h+var_A8], xmm0
0x1800274f3  mov     [rbp+57h+var_98], r15
0x1800274f7  lea     rcx, [rbp+57h+var_90]
0x1800274fb  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x180027500  lea     rcx, [rbp+57h+var_A8]
0x180027504  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x180027509  mov     rdx, [rbp+57h+var_90+8]
0x18002750d  mov     rcx, [rbp+57h+var_90]; unsigned __int16 *
0x180027511  sub     rdx, rcx
0x180027514  sar     rdx, 1; unsigned __int64
0x180027517  mov     r9d, [rdi+4]
0x18002751b  lea     r8, aTheEsimProfile_0; "The eSIM profile update is missing LPA_"...
0x180027522  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180027527  mov     rdx, [rbp+57h+var_A8+8]
0x18002752b  mov     rcx, [rbp+57h+var_A8]; unsigned __int16 *
0x18002752f  sub     rdx, rcx
0x180027532  sar     rdx, 1; unsigned __int64
0x180027535  mov     rax, [rbp+57h+var_90]
0x180027539  mov     [rsp+0E0h+var_B8], rax
0x18002753e  mov     dword ptr [rsp+0E0h+var_C0], 3B4h
0x180027546  mov     r9, r13
0x180027549  lea     r8, aSDS; "%S(%d):%s"
0x180027550  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180027555  call    ?Provider@MbaeApiLogging@@SAPEBU_tlgProvider_t@@XZ; MbaeApiLogging::Provider(void)
0x18002755a  mov     ecx, [rax]
0x18002755c  mov     esi, 2
0x180027561  cmp     ecx, esi
0x180027563  jbe     short loc_180027586
0x180027565  mov     rcx, [rbp+57h+var_A8]
0x180027569  mov     [rbp+57h+var_78], rcx
0x18002756d  lea     rcx, [rbp+57h+var_78]
0x180027571  mov     [rsp+0E0h+var_C0], rcx
0x180027576  lea     rdx, word_180075766
0x18002757d  mov     rcx, rax
0x180027580  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x180027585  nop
0x180027586  lea     rcx, [rbp+57h+var_A8]
0x18002758a  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18002758f  nop
0x180027590  lea     rcx, [rbp+57h+var_90]
0x180027594  jmp     loc_18002820F
0x180027599  mov     esi, 2
0x18002759e  lea     r12d, [rsi+2]
0x1800275a2  test    [rdi+8], sil
0x1800275a6  jz      loc_18002765F
0x1800275ac  xorps   xmm0, xmm0
0x1800275af  movdqu  xmmword ptr [rbp+57h+var_90], xmm0
0x1800275b4  mov     [rbp+57h+var_80], r15
0x1800275b8  movdqu  xmmword ptr [rbp+57h+var_A8], xmm0
0x1800275bd  mov     [rbp+57h+var_98], r15
0x1800275c1  lea     rcx, [rbp+57h+var_90]
0x1800275c5  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x1800275ca  lea     rcx, [rbp+57h+var_A8]
0x1800275ce  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x1800275d3  mov     rdx, [rbp+57h+var_90+8]
0x1800275d7  mov     rcx, [rbp+57h+var_90]; unsigned __int16 *
0x1800275db  sub     rdx, rcx
0x1800275de  sar     rdx, 1; unsigned __int64
0x1800275e1  mov     r9d, [rdi+38h]
0x1800275e5  lea     r8, aGetProfileDeta; "Get profile details: state=0x%08x"
0x1800275ec  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800275f1  mov     rdx, [rbp+57h+var_A8+8]
0x1800275f5  mov     rcx, [rbp+57h+var_A8]; unsigned __int16 *
0x1800275f9  sub     rdx, rcx
0x1800275fc  sar     rdx, 1; unsigned __int64
0x1800275ff  mov     rax, [rbp+57h+var_90]
0x180027603  mov     [rsp+0E0h+var_B8], rax
0x180027608  mov     dword ptr [rsp+0E0h+var_C0], 3BCh
0x180027610  mov     r9, r13
0x180027613  lea     r8, aSDS; "%S(%d):%s"
0x18002761a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002761f  call    ?Provider@MbaeApiLogging@@SAPEBU_tlgProvider_t@@XZ; MbaeApiLogging::Provider(void)
0x180027624  mov     ecx, [rax]
0x180027626  cmp     ecx, r12d
0x180027629  jbe     short loc_18002764C
0x18002762b  mov     rcx, [rbp+57h+var_A8]
0x18002762f  mov     [rbp+57h+var_78], rcx
0x180027633  lea     rcx, [rbp+57h+var_78]
0x180027637  mov     [rsp+0E0h+var_C0], rcx
0x18002763c  lea     rdx, word_180075746
0x180027643  mov     rcx, rax
0x180027646  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18002764b  nop
0x18002764c  lea     rcx, [rbp+57h+var_A8]
0x180027650  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x180027655  nop
0x180027656  lea     rcx, [rbp+57h+var_90]
0x18002765a  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18002765f  test    byte ptr [rdi+4], 8
0x180027663  jz      loc_18002771F
0x180027669  xorps   xmm0, xmm0
0x18002766c  movdqu  xmmword ptr [rbp+57h+var_90], xmm0
0x180027671  mov     [rbp+57h+var_80], r15
0x180027675  movdqu  xmmword ptr [rbp+57h+var_A8], xmm0
0x18002767a  mov     [rbp+57h+var_98], r15
0x18002767e  lea     rcx, [rbp+57h+var_90]
0x180027682  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x180027687  lea     rcx, [rbp+57h+var_A8]
0x18002768b  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x180027690  lea     r9, [rdi+10Ah]
0x180027697  mov     rdx, [rbp+57h+var_90+8]
0x18002769b  mov     rcx, [rbp+57h+var_90]; unsigned __int16 *
0x18002769f  sub     rdx, rcx
0x1800276a2  sar     rdx, 1; unsigned __int64
0x1800276a5  lea     r8, aGetProfileDeta_4; "Get profile details: nickname=%ls"
0x1800276ac  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800276b1  mov     rdx, [rbp+57h+var_A8+8]
0x1800276b5  mov     rcx, [rbp+57h+var_A8]; unsigned __int16 *
0x1800276b9  sub     rdx, rcx
0x1800276bc  sar     rdx, 1; unsigned __int64
0x1800276bf  mov     rax, [rbp+57h+var_90]
0x1800276c3  mov     [rsp+0E0h+var_B8], rax
0x1800276c8  mov     dword ptr [rsp+0E0h+var_C0], 3C0h
0x1800276d0  mov     r9, r13
0x1800276d3  lea     r8, aSDS; "%S(%d):%s"
0x1800276da  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800276df  call    ?Provider@MbaeApiLogging@@SAPEBU_tlgProvider_t@@XZ; MbaeApiLogging::Provider(void)
0x1800276e4  mov     ecx, [rax]
0x1800276e6  cmp     ecx, r12d
0x1800276e9  jbe     short loc_18002770C
0x1800276eb  mov     rcx, [rbp+57h+var_A8]
0x1800276ef  mov     [rbp+57h+var_78], rcx
0x1800276f3  lea     rcx, [rbp+57h+var_78]
0x1800276f7  mov     [rsp+0E0h+var_C0], rcx
0x1800276fc  lea     rdx, word_180075726
0x180027703  mov     rcx, rax
0x180027706  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18002770b  nop
0x18002770c  lea     rcx, [rbp+57h+var_A8]
0x180027710  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x180027715  nop
0x180027716  lea     rcx, [rbp+57h+var_90]
0x18002771a  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18002771f  test    byte ptr [rdi+4], 10h
0x180027723  jz      loc_1800277DF
0x180027729  xorps   xmm0, xmm0
0x18002772c  movdqu  xmmword ptr [rbp+57h+var_90], xmm0
0x180027731  mov     [rbp+57h+var_80], r15
0x180027735  movdqu  xmmword ptr [rbp+57h+var_A8], xmm0
0x18002773a  mov     [rbp+57h+var_98], r15
0x18002773e  lea     rcx, [rbp+57h+var_90]
0x180027742  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x180027747  lea     rcx, [rbp+57h+var_A8]
0x18002774b  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x180027750  lea     r9, [rdi+18Ch]
0x180027757  mov     rdx, [rbp+57h+var_90+8]
0x18002775b  mov     rcx, [rbp+57h+var_90]; unsigned __int16 *
0x18002775f  sub     rdx, rcx
0x180027762  sar     rdx, 1; unsigned __int64
0x180027765  lea     r8, aGetProfileDeta_3; "Get profile details: providername=%ls"
0x18002776c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180027771  mov     rdx, [rbp+57h+var_A8+8]
0x180027775  mov     rcx, [rbp+57h+var_A8]; unsigned __int16 *
0x180027779  sub     rdx, rcx
0x18002777c  sar     rdx, 1; unsigned __int64
0x18002777f  mov     rax, [rbp+57h+var_90]
0x180027783  mov     [rsp+0E0h+var_B8], rax
0x180027788  mov     dword ptr [rsp+0E0h+var_C0], 3C4h
0x180027790  mov     r9, r13
0x180027793  lea     r8, aSDS; "%S(%d):%s"
0x18002779a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002779f  call    ?Provider@MbaeApiLogging@@SAPEBU_tlgProvider_t@@XZ; MbaeApiLogging::Provider(void)
0x1800277a4  mov     ecx, [rax]
0x1800277a6  cmp     ecx, r12d
0x1800277a9  jbe     short loc_1800277CC
0x1800277ab  mov     rcx, [rbp+57h+var_A8]
0x1800277af  mov     [rbp+57h+var_78], rcx
0x1800277b3  lea     rcx, [rbp+57h+var_78]
0x1800277b7  mov     [rsp+0E0h+var_C0], rcx
0x1800277bc  lea     rdx, word_180075706
0x1800277c3  mov     rcx, rax
0x1800277c6  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x1800277cb  nop
0x1800277cc  lea     rcx, [rbp+57h+var_A8]
0x1800277d0  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x1800277d5  nop
0x1800277d6  lea     rcx, [rbp+57h+var_90]
0x1800277da  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x1800277df  test    [rdi+4], sil
0x1800277e3  jz      loc_18002789F
0x1800277e9  xorps   xmm0, xmm0
0x1800277ec  movdqu  xmmword ptr [rbp+57h+var_90], xmm0
0x1800277f1  mov     [rbp+57h+var_80], r15
0x1800277f5  movdqu  xmmword ptr [rbp+57h+var_A8], xmm0
0x1800277fa  mov     [rbp+57h+var_98], r15
0x1800277fe  lea     rcx, [rbp+57h+var_90]
0x180027802  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x180027807  lea     rcx, [rbp+57h+var_A8]
0x18002780b  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x180027810  mov     rdx, [rbp+57h+var_90+8]
0x180027814  mov     rcx, [rbp+57h+var_90]; unsigned __int16 *
0x180027818  sub     rdx, rcx
0x18002781b  sar     rdx, 1; unsigned __int64
0x18002781e  mov     r9d, [rdi+80h]
0x180027825  lea     r8, aGetProfileDeta_0; "Get profile details: dwPolicies=0x%08x"
0x18002782c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180027831  mov     rdx, [rbp+57h+var_A8+8]
0x180027835  mov     rcx, [rbp+57h+var_A8]; unsigned __int16 *
0x180027839  sub     rdx, rcx
0x18002783c  sar     rdx, 1; unsigned __int64
0x18002783f  mov     rax, [rbp+57h+var_90]
0x180027843  mov     [rsp+0E0h+var_B8], rax
0x180027848  mov     dword ptr [rsp+0E0h+var_C0], 3C8h
0x180027850  mov     r9, r13
0x180027853  lea     r8, aSDS; "%S(%d):%s"
0x18002785a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002785f  call    ?Provider@MbaeApiLogging@@SAPEBU_tlgProvider_t@@XZ; MbaeApiLogging::Provider(void)
0x180027864  mov     ecx, [rax]
0x180027866  cmp     ecx, r12d
0x180027869  jbe     short loc_18002788C
0x18002786b  mov     rcx, [rbp+57h+var_A8]
0x18002786f  mov     [rbp+57h+var_78], rcx
0x180027873  lea     rcx, [rbp+57h+var_78]
0x180027877  mov     [rsp+0E0h+var_C0], rcx
0x18002787c  lea     rdx, word_1800756E6
0x180027883  mov     rcx, rax
0x180027886  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18002788b  nop
0x18002788c  lea     rcx, [rbp+57h+var_A8]
0x180027890  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x180027895  nop
0x180027896  lea     rcx, [rbp+57h+var_90]
0x18002789a  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18002789f  test    [rdi+4], r12b
0x1800278a3  jz      loc_18002795F
0x1800278a9  xorps   xmm0, xmm0
0x1800278ac  movdqu  xmmword ptr [rbp+57h+var_90], xmm0
0x1800278b1  mov     [rbp+57h+var_80], r15
0x1800278b5  movdqu  xmmword ptr [rbp+57h+var_A8], xmm0
0x1800278ba  mov     [rbp+57h+var_98], r15
0x1800278be  lea     rcx, [rbp+57h+var_90]
0x1800278c2  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x1800278c7  lea     rcx, [rbp+57h+var_A8]
0x1800278cb  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
  ... truncated ...
```
