# CConnectionFolder::GetDetailsOf(_ITEMIDLIST const *,uint,_SHELLDETAILS *)

- ea: `0x180048cb0`
- end: `0x1800492e7`
- name: `?GetDetailsOf@CConnectionFolder@@UEAAJPEFBU_ITEMIDLIST@@IPEAU_SHELLDETAILS@@@Z`
- size: `1591`
- prototype: `__int64 __fastcall(CConnectionFolder *__hidden this, const struct _ITEMIDLIST *, unsigned int, struct _SHELLDETAILS *)`
- caller_count: `0`
- callee_count: `27`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180001fd0`
- `0x1800020b0`
- `0x1800049e0`
- `0x180005c8c`
- `0x180008060`
- `0x18001644c`
- `0x1800166dc`
- `0x180017674`
- `0x180017b50`
- `0x18001e1e0`
- `0x1800228e8`
- `0x1800232d8`
- `0x18002b5e8`
- `0x180034a44`
- `0x1800415b8`
- `0x180048cb0`
- `0x1800492f0`
- `0x180049430`
- `0x1800496e0`
- `0x180049e28`
- `0x180049ec0`
- `0x180049f04`
- `0x180049f48`
- `0x18004a540`
- `0x18004a7b8`
- `0x180062130`
- `0x180065010`

## import_xrefs

- `SHELL32!__imp_SHAlloc` at `0x180049281`
- `SHELL32!__imp_SHAlloc` at `0x180049281`
- `ole32!CoTaskMemFree` at `0x1800490c8`
- `ole32!CoTaskMemFree` at `0x1800490d3`
- `ole32!CoTaskMemFree` at `0x1800490c8`
- `ole32!CoTaskMemFree` at `0x1800490d3`

## pseudocode

```c
__int64 __fastcall CConnectionFolder::GetDetailsOf(
        CConnectionFolder *this,
        const struct _ITEMIDLIST *a2,
        unsigned int a3,
        struct _SHELLDETAILS *a4)
{
  __int64 v5; // rbx
  unsigned int v8; // r8d
  WCHAR *Ids; // rsi
  __int64 v10; // r14
  __int64 v11; // rbx
  int PrimaryIPv6AddressForAdapter; // edi
  int v13; // ebx
  int v14; // ebx
  int v15; // ebx
  int v16; // ebx
  const unsigned __int16 *OwnerStringFromCharacteristics; // rax
  const unsigned __int16 *UserName; // rax
  int v19; // ebx
  int v20; // ebx
  int v21; // ebx
  int v22; // ebx
  const unsigned __int16 *v23; // rax
  __int64 v24; // r8
  const unsigned __int16 *v25; // rax
  __int64 v26; // r8
  int v27; // ebx
  __int64 v28; // rdx
  __int64 v29; // rdx
  __int64 v30; // rdx
  const wchar_t *v31; // rbx
  WCHAR *v32; // rax
  __int64 v34; // [rsp+28h] [rbp-D8h]
  LPVOID pv; // [rsp+50h] [rbp-B0h] BYREF
  ConFoldPidl_v3 *v36; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v37; // [rsp+60h] [rbp-A0h] BYREF
  char *Src[3]; // [rsp+68h] [rbp-98h] BYREF
  unsigned __int64 v39; // [rsp+80h] [rbp-80h]
  void *v40[2]; // [rsp+90h] [rbp-70h] BYREF
  unsigned int v41; // [rsp+B0h] [rbp-50h] BYREF
  unsigned int v42; // [rsp+B4h] [rbp-4Ch]
  unsigned int v43[2]; // [rsp+B8h] [rbp-48h]
  int v44; // [rsp+C0h] [rbp-40h]
  unsigned int v45; // [rsp+C4h] [rbp-3Ch]
  __int128 v46; // [rsp+D8h] [rbp-28h]
  unsigned int v47; // [rsp+E8h] [rbp-18h]
  WCHAR *v48; // [rsp+F0h] [rbp-10h]
  WCHAR *v49; // [rsp+F8h] [rbp-8h]
  unsigned __int16 *v50; // [rsp+100h] [rbp+0h]
  WCHAR *v51; // [rsp+118h] [rbp+18h]
  unsigned __int16 v52[8]; // [rsp+140h] [rbp+40h] BYREF
  unsigned __int16 v53[264]; // [rsp+170h] [rbp+70h] BYREF
  WCHAR v54[256]; // [rsp+380h] [rbp+280h] BYREF

  v5 = a3;
  std::wstring::wstring((__int64)Src);
  if ( v8 > 0xB )
  {
    PrimaryIPv6AddressForAdapter = -2147467259;
    goto LABEL_104;
  }
  Ids = 0;
  CConFoldEntry::CConFoldEntry((CConFoldEntry *)&v41);
  v10 = -1;
  if ( !a2 )
  {
    v11 = 3 * v5;
    if ( *((_WORD *)&c_rgCols + 2 * v11 + 1) )
      Ids = (WCHAR *)SzLoadIds(*((__int16 *)&c_rgCols + 2 * v11 + 1));
    a4->fmt = *((__int16 *)&c_rgCols + 2 * v11 + 3);
    a4->cxChar = *((__int16 *)&c_rgCols + 2 * v11 + 2);
    goto LABEL_94;
  }
  LODWORD(pv) = 0;
  v36 = 0;
  PrimaryIPv6AddressForAdapter = CPConFoldPidl<ConFoldPidl_v3>::InitializeFromItemIDList(&v36, a2);
  if ( PrimaryIPv6AddressForAdapter < 0 )
  {
    CPConFoldPidl<ConFoldPidlFolder>::FreePIDLIfRequired(&v36);
    goto LABEL_102;
  }
  if ( !v36 )
  {
    PrimaryIPv6AddressForAdapter = -2147418113;
    goto LABEL_93;
  }
  PrimaryIPv6AddressForAdapter = ConFoldPidl_v3::ConvertToConFoldEntry(v36, (struct CConFoldEntry *)&v41);
  if ( PrimaryIPv6AddressForAdapter >= 0 )
  {
    a4->fmt = *((__int16 *)&c_rgCols + 6 * v5 + 2);
    a4->cxChar = *((__int16 *)&c_rgCols + 6 * v5 + 2);
    if ( (unsigned int)v5 <= 6 )
    {
      if ( (_DWORD)v5 == 6 )
      {
        MapNCMToResourceId(v41, v42, v47, &pv);
        Ids = (WCHAR *)SzLoadIds((unsigned int)pv);
        goto LABEL_93;
      }
      if ( !(_DWORD)v5 )
      {
        Ids = v48;
        goto LABEL_93;
      }
      v13 = v5 - 1;
      if ( !v13 )
      {
        *(_OWORD *)v40 = v46;
        MapNCSToComplexStatus((CConnectionList *)v43[0], v41, v42, v47, v54, v34, (struct _GUID *)v40, v50);
        Ids = v54;
        goto LABEL_93;
      }
      v14 = v13 - 1;
      if ( !v14 )
      {
        Ids = v49;
        goto LABEL_93;
      }
      v15 = v14 - 1;
      if ( v15 )
      {
        v16 = v15 - 1;
        if ( v16 )
        {
          if ( v16 == 1 )
          {
            if ( (v47 & 1) != 0 )
            {
              OwnerStringFromCharacteristics = SzLoadIds(0x834u);
            }
            else
            {
              UserName = CConnectionFolder::pszGetUserName((CConnectionFolder *)((char *)this - 16));
              OwnerStringFromCharacteristics = PszGetOwnerStringFromCharacteristics(UserName, v47);
            }
            goto LABEL_24;
          }
          goto LABEL_34;
        }
        OwnerStringFromCharacteristics = PszGetCategoryStringFromCategory(v45, v43[1]);
      }
      else
      {
        OwnerStringFromCharacteristics = PszGetConnectivityStringFromConnectivity(v43[1], v44);
      }
LABEL_24:
      Ids = (WCHAR *)OwnerStringFromCharacteristics;
      goto LABEL_93;
    }
    v19 = v5 - 7;
    if ( !v19 )
      goto LABEL_92;
    v20 = v19 - 1;
    if ( v20 )
    {
      v21 = v20 - 1;
      if ( v21 )
      {
        v22 = v21 - 1;
        if ( v22 )
        {
          if ( v22 != 1 )
          {
LABEL_34:
            Ids = 0;
LABEL_35:
            PrimaryIPv6AddressForAdapter = -2147467259;
            goto LABEL_93;
          }
          if ( !v43[0] || v43[0] - 4 <= 2 || v41 != 3 || v42 != 7 )
            goto LABEL_35;
          if ( (v47 & 0x10000) != 0 )
          {
            v23 = SzLoadIds(0x6AAu);
            v24 = -1;
            do
              ++v24;
            while ( v23[v24] );
          }
          else if ( (v47 & 0x40000) != 0 )
          {
            v23 = SzLoadIds(0x6A9u);
            v24 = -1;
            do
              ++v24;
            while ( v23[v24] );
          }
          else if ( (v47 & 0x20000) != 0 )
          {
            v23 = SzLoadIds(0x6ABu);
            v24 = -1;
            do
              ++v24;
            while ( v23[v24] );
          }
          else if ( (v47 & 0x80000) != 0 )
          {
            v23 = SzLoadIds(0x6ADu);
            v24 = -1;
            do
              ++v24;
            while ( v23[v24] );
          }
          else
          {
            if ( (v47 & 0xF0000) != 0 )
            {
LABEL_60:
              v40[0] = 0;
              if ( CConFoldEntry::HrGetNetCon((CConFoldEntry *)&v41, &IID_INetConnection, v40, 1) >= 0 )
              {
                v37 = 0;
                if ( (**(int (__fastcall ***)(void *, GUID *, __int64 *))v40[0])(
                       v40[0],
                       &GUID_15fd01a3_6e5d_4ecd_9ebd_1813cb3887a1,
                       &v37) >= 0 )
                {
                  pv = 0;
                  if ( !(*(unsigned int (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v37 + 64LL))(v37, &pv) )
                  {
                    StringCchPrintfW(
                      v52,
                      0x13u,
                      L"\n%02x-%02x-%02x-%02x-%02x-%02x",
                      *((unsigned __int8 *)pv + 21),
                      *((unsigned __int8 *)pv + 20),
                      *((unsigned __int8 *)pv + 19),
                      *((unsigned __int8 *)pv + 18),
                      *((unsigned __int8 *)pv + 17),
                      *((unsigned __int8 *)pv + 16));
                    v25 = SzLoadIds(0x6A7u);
                    if ( DwFormatString(v25, v53, 0x104u, v52) )
                    {
                      v26 = -1;
                      do
                        ++v26;
                      while ( v53[v26] );
                      std::wstring::_Append<unsigned short>(Src);
                    }
                    CoTaskMemFree(*((LPVOID *)pv + 3));
                    CoTaskMemFree(pv);
                  }
                }
                ATL::CComPtrBase<IUPnPService>::~CComPtrBase<IUPnPService>(&v37);
              }
              Ids = (WCHAR *)Src;
              PrimaryIPv6AddressForAdapter = 0;
              if ( v39 > 7 )
                Ids = (WCHAR *)Src[0];
              ATL::CComPtrBase<IUPnPService>::~CComPtrBase<IUPnPService>((__int64 *)v40);
              goto LABEL_93;
            }
            v23 = SzLoadIds(0x6ACu);
            v24 = -1;
            do
              ++v24;
            while ( v23[v24] );
          }
          std::wstring::_Assign<unsigned short>(Src, v23, (char *)v24);
          goto LABEL_60;
        }
      }
LABEL_92:
      Ids = v51;
      goto LABEL_93;
    }
    if ( v43[0] != 2 && v43[0] != 8 && v43[0] != 9 && v43[0] != 10 && v43[0] != 12 )
    {
      PrimaryIPv6AddressForAdapter = -2147467259;
      goto LABEL_93;
    }
    v27 = 0;
    std::wstring::wstring((__int64)v52);
    std::wstring::wstring((__int64)v40);
    if ( !(unsigned int)GetPrimaryIPv4AddressForAdapter(&v41, v28, v40) )
    {
      std::wstring::_Append<unsigned short>(Src);
      v27 = 1;
    }
    if ( !(unsigned int)GetIPv4AutoNetSettingsForAdapter(&v41, v29, v52) )
    {
      if ( v27 )
        std::wstring::_Append<unsigned short>(Src);
      std::wstring::_Append<unsigned short>(Src);
      v27 = 1;
    }
    PrimaryIPv6AddressForAdapter = GetPrimaryIPv6AddressForAdapter(&v41, v30, v40);
    if ( PrimaryIPv6AddressForAdapter )
    {
      if ( !v27 )
      {
LABEL_91:
        std::wstring::_Tidy_deallocate((__int64)v40);
        std::wstring::_Tidy_deallocate((__int64)v52);
        goto LABEL_93;
      }
    }
    else
    {
      if ( v27 )
        std::wstring::_Append<unsigned short>(Src);
      std::wstring::_Append<unsigned short>(Src);
    }
    Ids = (WCHAR *)Src;
    PrimaryIPv6AddressForAdapter = 0;
    if ( v39 > 7 )
      Ids = (WCHAR *)Src[0];
    goto LABEL_91;
  }
LABEL_93:
  CPConFoldPidl<ConFoldPidlFolder>::FreePIDLIfRequired(&v36);
  if ( PrimaryIPv6AddressForAdapter >= 0 )
  {
LABEL_94:
    v31 = L" ";
    if ( Ids )
      v31 = Ids;
    do
      ++v10;
    while ( v31[v10] );
    if ( a4 == (struct _SHELLDETAILS *)-8LL )
    {
      PrimaryIPv6AddressForAdapter = -2147024809;
    }
    else
    {
      a4->str.uType = 0;
      v32 = (WCHAR *)SHAlloc((unsigned int)(2 * v10 + 2));
      a4->str.pOleStr = v32;
      if ( v32 )
      {
        PrimaryIPv6AddressForAdapter = 0;
        memcpy_0(v32, v31, (unsigned int)(2 * v10 + 2));
      }
      else
      {
        PrimaryIPv6AddressForAdapter = -2147024882;
      }
    }
  }
LABEL_102:
  CConFoldEntry::~CConFoldEntry((CConFoldEntry *)&v41);
LABEL_104:
  std::wstring::_Tidy_deallocate((__int64)Src);
  return (unsigned int)PrimaryIPv6AddressForAdapter;
}

```

## disassembly

```asm
0x180048cb0  push    rbp
0x180048cb2  push    rbx
0x180048cb3  push    rsi
0x180048cb4  push    rdi
0x180048cb5  push    r12
0x180048cb7  push    r13
0x180048cb9  push    r14
0x180048cbb  push    r15
0x180048cbd  lea     rbp, [rsp-498h]
0x180048cc5  sub     rsp, 598h
0x180048ccc  mov     rax, cs:__security_cookie
0x180048cd3  xor     rax, rsp
0x180048cd6  mov     [rbp+4D0h+var_50], rax
0x180048cdd  mov     r13, rcx
0x180048ce0  mov     ebx, r8d
0x180048ce3  lea     rcx, [rsp+5D0h+Src]
0x180048ce8  mov     r12, r9
0x180048ceb  mov     rdi, rdx
0x180048cee  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180048cf3  cmp     r8d, 0Bh
0x180048cf7  ja      loc_1800492B3
0x180048cfd  xor     r15d, r15d
0x180048d00  lea     rcx, [rbp+4D0h+var_520]; this
0x180048d04  mov     esi, r15d
0x180048d07  call    ??0CConFoldEntry@@QEAA@XZ; CConFoldEntry::CConFoldEntry(void)
0x180048d0c  or      r14, 0FFFFFFFFFFFFFFFFh
0x180048d10  test    rdi, rdi
0x180048d13  jnz     short loc_180048D52
0x180048d15  lea     rbx, [rbx+rbx*2]
0x180048d19  lea     r15, ?c_rgCols@@3PAUtagCOLS@@A; tagCOLS near * c_rgCols
0x180048d20  movsx   eax, word ptr [r15+rbx*4+2]
0x180048d26  test    ax, ax
0x180048d29  jz      short loc_180048D35
0x180048d2b  mov     ecx, eax; unsigned int
0x180048d2d  call    ?SzLoadIds@@YAPEBGI@Z; SzLoadIds(uint)
0x180048d32  mov     rsi, rax
0x180048d35  movsx   ecx, word ptr [r15+rbx*4+6]
0x180048d3b  mov     [r12], ecx
0x180048d3f  movsx   ecx, word ptr [r15+rbx*4+4]
0x180048d45  xor     r15d, r15d
0x180048d48  mov     [r12+4], ecx
0x180048d4d  jmp     loc_180049249
0x180048d52  mov     rdx, rdi
0x180048d55  mov     dword ptr [rsp+5D0h+pv], r15d
0x180048d5a  lea     rcx, [rsp+5D0h+var_578]
0x180048d5f  mov     [rsp+5D0h+var_578], r15
0x180048d64  call    ?InitializeFromItemIDList@?$CPConFoldPidl@VConFoldPidl_v3@@@@QEAAJPEFBU_ITEMIDLIST@@@Z; CPConFoldPidl<ConFoldPidl_v3>::InitializeFromItemIDList(_ITEMIDLIST const *)
0x180048d69  mov     edi, eax
0x180048d6b  test    eax, eax
0x180048d6d  jns     short loc_180048D7E
0x180048d6f  lea     rcx, [rsp+5D0h+var_578]
0x180048d74  call    ?FreePIDLIfRequired@?$CPConFoldPidl@VConFoldPidlFolder@@@@AEAAJXZ; CPConFoldPidl<ConFoldPidlFolder>::FreePIDLIfRequired(void)
0x180048d79  jmp     loc_1800492A8
0x180048d7e  mov     rcx, [rsp+5D0h+var_578]; this
0x180048d83  test    rcx, rcx
0x180048d86  jnz     short loc_180048D92
0x180048d88  mov     edi, 8000FFFFh
0x180048d8d  jmp     loc_18004923B
0x180048d92  lea     rdx, [rbp+4D0h+var_520]; struct CConFoldEntry *
0x180048d96  call    ?ConvertToConFoldEntry@ConFoldPidl_v3@@QEBAJAEAVCConFoldEntry@@@Z; ConFoldPidl_v3::ConvertToConFoldEntry(CConFoldEntry &)
0x180048d9b  mov     edi, eax
0x180048d9d  test    eax, eax
0x180048d9f  js      loc_18004923B
0x180048da5  lea     rcx, [rbx+rbx*2]
0x180048da9  lea     r15, ?c_rgCols@@3PAUtagCOLS@@A; tagCOLS near * c_rgCols
0x180048db0  movsx   eax, word ptr [r15+rcx*4+4]
0x180048db6  mov     [r12], eax
0x180048dba  movsx   eax, word ptr [r15+rcx*4+4]
0x180048dc0  mov     [r12+4], eax
0x180048dc5  cmp     ebx, 6
0x180048dc8  ja      loc_180048EC0
0x180048dce  jz      loc_180048E9B
0x180048dd4  xor     r15d, r15d
0x180048dd7  test    ebx, ebx
0x180048dd9  jz      loc_180048E92
0x180048ddf  sub     ebx, 1
0x180048de2  jz      short loc_180048E4C
0x180048de4  sub     ebx, 1
0x180048de7  jz      short loc_180048E43
0x180048de9  sub     ebx, 1
0x180048dec  jz      short loc_180048E30
0x180048dee  sub     ebx, 1
0x180048df1  jz      short loc_180048E23
0x180048df3  cmp     ebx, 1
0x180048df6  jnz     loc_180048EEC
0x180048dfc  test    byte ptr [rbp+4D0h+var_4E8], bl
0x180048dff  jz      short loc_180048E0D
0x180048e01  mov     ecx, 834h; unsigned int
0x180048e06  call    ?SzLoadIds@@YAPEBGI@Z; SzLoadIds(uint)
0x180048e0b  jmp     short loc_180048E3B
0x180048e0d  lea     rcx, [r13-10h]; this
0x180048e11  call    ?pszGetUserName@CConnectionFolder@@QEAAPEBGXZ; CConnectionFolder::pszGetUserName(void)
0x180048e16  mov     edx, [rbp+4D0h+var_4E8]; unsigned int
0x180048e19  mov     rcx, rax; unsigned __int16 *
0x180048e1c  call    ?PszGetOwnerStringFromCharacteristics@@YAPEBGPEBGK@Z; PszGetOwnerStringFromCharacteristics(ushort const *,ulong)
0x180048e21  jmp     short loc_180048E3B
0x180048e23  mov     edx, [rbp+4D0h+var_518+4]; unsigned int
0x180048e26  mov     ecx, [rbp+4D0h+var_50C]; unsigned int
0x180048e29  call    ?PszGetCategoryStringFromCategory@@YAPEBGKK@Z; PszGetCategoryStringFromCategory(ulong,ulong)
0x180048e2e  jmp     short loc_180048E3B
0x180048e30  mov     edx, [rbp+4D0h+var_510]; int
0x180048e33  mov     ecx, [rbp+4D0h+var_518+4]; unsigned int
0x180048e36  call    ?PszGetConnectivityStringFromConnectivity@@YAPEBGKH@Z; PszGetConnectivityStringFromConnectivity(ulong,int)
0x180048e3b  mov     rsi, rax
0x180048e3e  jmp     loc_18004923B
0x180048e43  mov     rsi, [rbp+4D0h+var_4D8]
0x180048e47  jmp     loc_18004923B
0x180048e4c  mov     rax, [rbp+4D0h+var_4D0]
0x180048e50  movups  xmm0, [rbp+4D0h+var_4F8]
0x180048e54  mov     r9d, [rbp+4D0h+var_4E8]
0x180048e58  mov     r8d, [rbp+4D0h+var_51C]
0x180048e5c  mov     edx, [rbp+4D0h+var_520]
0x180048e5f  mov     ecx, [rbp+4D0h+var_518]
0x180048e62  mov     [rsp+5D0h+var_598], rax
0x180048e67  lea     rax, [rbp+4D0h+var_540]
0x180048e6b  mov     [rsp+5D0h+var_5A0], rax
0x180048e70  lea     rax, [rbp+4D0h+var_250]
0x180048e77  mov     [rsp+5D0h+var_5B0], rax
0x180048e7c  movdqu  xmmword ptr [rbp+4D0h+var_540], xmm0
0x180048e81  call    ?MapNCSToComplexStatus@@YAXW4tagNETCON_STATUS@@W4tagNETCON_MEDIATYPE@@W4tagNETCON_SUBMEDIATYPE@@KPEAGKU_GUID@@PEBG@Z; MapNCSToComplexStatus(tagNETCON_STATUS,tagNETCON_MEDIATYPE,tagNETCON_SUBMEDIATYPE,ulong,ushort *,ulong,_GUID,ushort const *)
0x180048e86  lea     rsi, [rbp+4D0h+var_250]
0x180048e8d  jmp     loc_18004923B
0x180048e92  mov     rsi, [rbp+4D0h+var_4E0]
0x180048e96  jmp     loc_18004923B
0x180048e9b  mov     ecx, [rbp+4D0h+var_520]
0x180048e9e  lea     r9, [rsp+5D0h+pv]
0x180048ea3  mov     r8d, [rbp+4D0h+var_4E8]
0x180048ea7  mov     edx, [rbp+4D0h+var_51C]
0x180048eaa  call    ?MapNCMToResourceId@@YAXW4tagNETCON_MEDIATYPE@@W4tagNETCON_SUBMEDIATYPE@@KPEAH@Z; MapNCMToResourceId(tagNETCON_MEDIATYPE,tagNETCON_SUBMEDIATYPE,ulong,int *)
0x180048eaf  mov     ecx, dword ptr [rsp+5D0h+pv]; unsigned int
0x180048eb3  call    ?SzLoadIds@@YAPEBGI@Z; SzLoadIds(uint)
0x180048eb8  mov     rsi, rax
0x180048ebb  jmp     loc_180049238
0x180048ec0  sub     ebx, 7
0x180048ec3  jz      loc_180049234
0x180048ec9  sub     ebx, 1
0x180048ecc  jz      loc_180049104
0x180048ed2  sub     ebx, 1
0x180048ed5  jz      loc_180049234
0x180048edb  sub     ebx, 1
0x180048ede  jz      loc_180049234
0x180048ee4  xor     r15d, r15d
0x180048ee7  cmp     ebx, 1
0x180048eea  jz      short loc_180048EF9
0x180048eec  mov     rsi, r15
0x180048eef  mov     edi, 80004005h
0x180048ef4  jmp     loc_18004923B
0x180048ef9  mov     eax, [rbp+4D0h+var_518]
0x180048efc  test    eax, eax
0x180048efe  jz      short loc_180048EEF
0x180048f00  add     eax, 0FFFFFFFCh
0x180048f03  cmp     eax, 2
0x180048f06  jbe     short loc_180048EEF
0x180048f08  cmp     [rbp+4D0h+var_520], 3
0x180048f0c  jnz     short loc_180048EEF
0x180048f0e  cmp     [rbp+4D0h+var_51C], 7
0x180048f12  jnz     short loc_180048EEF
0x180048f14  mov     eax, [rbp+4D0h+var_4E8]
0x180048f17  bt      eax, 10h
0x180048f1b  jnb     short loc_180048F36
0x180048f1d  mov     ecx, 6AAh; unsigned int
0x180048f22  call    ?SzLoadIds@@YAPEBGI@Z; SzLoadIds(uint)
0x180048f27  mov     r8, r14
0x180048f2a  inc     r8
0x180048f2d  cmp     [rax+r8*2], r15w
0x180048f32  jnz     short loc_180048F2A
0x180048f34  jmp     short loc_180048FB1
0x180048f36  bt      eax, 12h
0x180048f3a  jnb     short loc_180048F55
0x180048f3c  mov     ecx, 6A9h; unsigned int
0x180048f41  call    ?SzLoadIds@@YAPEBGI@Z; SzLoadIds(uint)
0x180048f46  mov     r8, r14
0x180048f49  inc     r8
0x180048f4c  cmp     [rax+r8*2], r15w
0x180048f51  jnz     short loc_180048F49
0x180048f53  jmp     short loc_180048FB1
0x180048f55  bt      eax, 11h
0x180048f59  jnb     short loc_180048F74
0x180048f5b  mov     ecx, 6ABh; unsigned int
0x180048f60  call    ?SzLoadIds@@YAPEBGI@Z; SzLoadIds(uint)
0x180048f65  mov     r8, r14
0x180048f68  inc     r8
0x180048f6b  cmp     [rax+r8*2], r15w
0x180048f70  jnz     short loc_180048F68
0x180048f72  jmp     short loc_180048FB1
0x180048f74  bt      eax, 13h
0x180048f78  jnb     short loc_180048F93
0x180048f7a  mov     ecx, 6ADh; unsigned int
0x180048f7f  call    ?SzLoadIds@@YAPEBGI@Z; SzLoadIds(uint)
0x180048f84  mov     r8, r14
0x180048f87  inc     r8
0x180048f8a  cmp     [rax+r8*2], r15w
0x180048f8f  jnz     short loc_180048F87
0x180048f91  jmp     short loc_180048FB1
0x180048f93  test    eax, 0F0000h
0x180048f98  jnz     short loc_180048FBE
0x180048f9a  mov     ecx, 6ACh; unsigned int
0x180048f9f  call    ?SzLoadIds@@YAPEBGI@Z; SzLoadIds(uint)
0x180048fa4  mov     r8, r14
0x180048fa7  inc     r8
0x180048faa  cmp     [rax+r8*2], r15w
0x180048faf  jnz     short loc_180048FA7
0x180048fb1  mov     rdx, rax
0x180048fb4  lea     rcx, [rsp+5D0h+Src]
0x180048fb9  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x180048fbe  mov     r9d, 1; int
0x180048fc4  mov     [rbp+4D0h+var_540], r15
0x180048fc8  lea     r8, [rbp+4D0h+var_540]; void **
0x180048fcc  lea     rdx, IID_INetConnection; struct _GUID *
0x180048fd3  lea     rcx, [rbp+4D0h+var_520]; this
0x180048fd7  call    ?HrGetNetCon@CConFoldEntry@@QEBAJAEBU_GUID@@PEAPEAXH@Z; CConFoldEntry::HrGetNetCon(_GUID const &,void * *,int)
0x180048fdc  test    eax, eax
0x180048fde  js      loc_1800490E3
0x180048fe4  mov     rcx, [rbp+4D0h+var_540]
0x180048fe8  lea     r8, [rsp+5D0h+var_570]
0x180048fed  mov     [rsp+5D0h+var_570], r15
0x180048ff2  lea     rdx, _GUID_15fd01a3_6e5d_4ecd_9ebd_1813cb3887a1
0x180048ff9  mov     rax, [rcx]
0x180048ffc  mov     rax, [rax]
0x180048fff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049004  test    eax, eax
0x180049006  js      loc_1800490D9
0x18004900c  mov     rcx, [rsp+5D0h+var_570]
0x180049011  lea     rdx, [rsp+5D0h+pv]
0x180049016  mov     [rsp+5D0h+pv], r15
0x18004901b  mov     rax, [rcx]
0x18004901e  mov     rax, [rax+40h]
0x180049022  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049027  test    eax, eax
0x180049029  jnz     loc_1800490D9
0x18004902f  mov     rax, [rsp+5D0h+pv]
0x180049034  movzx   ecx, byte ptr [rax+10h]
0x180049038  movzx   edx, byte ptr [rax+11h]
0x18004903c  movzx   r8d, byte ptr [rax+12h]
0x180049041  movzx   r10d, byte ptr [rax+13h]
0x180049046  movzx   r11d, byte ptr [rax+14h]
0x18004904b  movzx   r9d, byte ptr [rax+15h]
0x180049050  mov     [rsp+5D0h+var_590], ecx
0x180049054  lea     rcx, [rbp+4D0h+var_490]; unsigned __int16 *
0x180049058  mov     dword ptr [rsp+5D0h+var_598], edx
0x18004905c  mov     edx, 13h; unsigned __int64
0x180049061  mov     dword ptr [rsp+5D0h+var_5A0], r8d
0x180049066  lea     r8, a02x02x02x02x02; "\n%02x-%02x-%02x-%02x-%02x-%02x"
0x18004906d  mov     dword ptr [rsp+5D0h+var_5A8], r10d
0x180049072  mov     dword ptr [rsp+5D0h+var_5B0], r11d
0x180049077  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004907c  mov     ecx, 6A7h; unsigned int
0x180049081  call    ?SzLoadIds@@YAPEBGI@Z; SzLoadIds(uint)
0x180049086  mov     rcx, rax; lpSource
0x180049089  lea     r9, [rbp+4D0h+var_490]
0x18004908d  mov     r8d, 104h; unsigned int
0x180049093  lea     rdx, [rbp+4D0h+var_460]; unsigned __int16 *
0x180049097  call    ?DwFormatString@@YAKPEBGPEAGKZZ; DwFormatString(ushort const *,ushort *,ulong,...)
0x18004909c  test    eax, eax
0x18004909e  jz      short loc_1800490BF
0x1800490a0  lea     rax, [rbp+4D0h+var_460]
0x1800490a4  mov     r8, r14
0x1800490a7  inc     r8
0x1800490aa  cmp     [rax+r8*2], r15w
0x1800490af  jnz     short loc_1800490A7
0x1800490b1  lea     rdx, [rbp+4D0h+var_460]
0x1800490b5  lea     rcx, [rsp+5D0h+Src]; Src
0x1800490ba  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x1800490bf  mov     rcx, [rsp+5D0h+pv]
0x1800490c4  mov     rcx, [rcx+18h]; pv
0x1800490c8  call    cs:__imp_CoTaskMemFree
0x1800490ce  mov     rcx, [rsp+5D0h+pv]; pv
0x1800490d3  call    cs:__imp_CoTaskMemFree
0x1800490d9  lea     rcx, [rsp+5D0h+var_570]
0x1800490de  call    ??1?$CComPtrBase@UIUPnPService@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUPnPService>::~CComPtrBase<IUPnPService>(void)
0x1800490e3  cmp     [rbp+4D0h+var_550], 7
0x1800490e8  lea     rsi, [rsp+5D0h+Src]
0x1800490ed  lea     rcx, [rbp+4D0h+var_540]
0x1800490f1  mov     edi, r15d
0x1800490f4  cmova   rsi, [rsp+5D0h+Src]
0x1800490fa  call    ??1?$CComPtrBase@UIUPnPService@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUPnPService>::~CComPtrBase<IUPnPService>(void)
0x1800490ff  jmp     loc_18004923B
0x180049104  mov     rcx, qword ptr [rbp+4D0h+var_518]
0x180049108  sub     ecx, 2
0x18004910b  jz      short loc_18004912B
0x18004910d  sub     ecx, 6
0x180049110  jz      short loc_18004912B
0x180049112  sub     ecx, 1
0x180049115  jz      short loc_18004912B
0x180049117  sub     ecx, 1
0x18004911a  jz      short loc_18004912B
0x18004911c  cmp     ecx, 2
0x18004911f  jz      short loc_18004912B
0x180049121  mov     edi, 80004005h
0x180049126  jmp     loc_180049238
0x18004912b  xor     r15d, r15d
0x18004912e  lea     rcx, [rbp+4D0h+var_490]
0x180049132  mov     ebx, r15d
0x180049135  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18004913a  lea     rcx, [rbp+4D0h+var_540]
0x18004913e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180049143  lea     r8, [rbp+4D0h+var_540]
0x180049147  lea     rcx, [rbp+4D0h+var_520]
0x18004914b  call    ?GetPrimaryIPv4AddressForAdapter@@YAJAEBVCConFoldEntry@@IAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; GetPrimaryIPv4AddressForAdapter(CConFoldEntry const &,uint,std::wstring &)
0x180049150  test    eax, eax
  ... truncated ...
```
