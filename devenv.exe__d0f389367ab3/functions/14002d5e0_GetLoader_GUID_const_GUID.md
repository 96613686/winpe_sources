# GetLoader(_GUID const &,_GUID *)

- ea: `0x14002d5e0`
- end: `0x14002dad4`
- name: `?GetLoader@@YAJAEBU_GUID@@PEAU1@@Z`
- size: `1268`
- prototype: `__int64 __fastcall(IID *rclsid, struct _GUID *)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x14002d3e0`

## callees

- `0x140001020`
- `0x140002c10`
- `0x140002dd0`
- `0x140002f00`
- `0x140003ec0`
- `0x140004950`
- `0x14000fce0`
- `0x14001b3e0`
- `0x14001c380`
- `0x14002d5e0`
- `0x14002fa90`
- `0x140033280`
- `0x140033ab0`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x14002d7d3`
- `ADVAPI32!RegCloseKey` at `0x14002da2a`
- `ADVAPI32!RegCloseKey` at `0x14002d7d3`
- `ADVAPI32!RegCloseKey` at `0x14002da2a`
- `ADVAPI32!RegOpenKeyExW` at `0x14002d709`
- `ADVAPI32!RegOpenKeyExW` at `0x14002d894`
- `ADVAPI32!RegOpenKeyExW` at `0x14002d709`
- `ADVAPI32!RegOpenKeyExW` at `0x14002d894`
- `ADVAPI32!RegQueryValueExW` at `0x14002d76a`
- `ADVAPI32!RegQueryValueExW` at `0x14002d8e8`
- `ADVAPI32!RegQueryValueExW` at `0x14002d76a`
- `ADVAPI32!RegQueryValueExW` at `0x14002d8e8`
- `ole32!StringFromCLSID` at `0x14002d66c`
- `ole32!StringFromCLSID` at `0x14002d66c`
- `ole32!CoTaskMemFree` at `0x14002da1b`
- `ole32!CoTaskMemFree` at `0x14002da1b`

## string_xrefs

- `0x14002d816`: `CLSID\`
- `0x14002d67c`: `\CLSID\`
- `0x14002d75f`: `ThreadingModel`
- `0x14002d8dd`: `ThreadingModel`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall GetLoader(IID *rclsid, struct _GUID *a2)
{
  struct ATL::IAtlStringMgr *Instance; // rax
  BYTE *v5; // rbx
  struct ATL::IAtlStringMgr *v6; // rax
  HRESULT v7; // esi
  __int64 v8; // rax
  LPCWSTR v9; // rdx
  __int64 v10; // r8
  signed int v11; // edi
  LSTATUS v12; // r13d
  LSTATUS v13; // r12d
  int v14; // eax
  struct ATL::IAtlStringMgr *v15; // rax
  __int64 v16; // r8
  LPCWSTR v17; // rdi
  LSTATUS v18; // r15d
  int v19; // eax
  GUID v20; // xmm0
  __int64 v21; // rcx
  int v22; // eax
  LPCWSTR v23; // rdx
  BYTE *v25; // [rsp+30h] [rbp-40h] BYREF
  LPCWSTR v26; // [rsp+38h] [rbp-38h] BYREF
  LPCWSTR lpSubKey; // [rsp+40h] [rbp-30h] BYREF
  DWORD cbData; // [rsp+48h] [rbp-28h] BYREF
  HKEY hKey; // [rsp+50h] [rbp-20h] BYREF
  LPOLESTR lpsz; // [rsp+58h] [rbp-18h] BYREF
  DWORD Type; // [rsp+60h] [rbp-10h] BYREF

  Type = 1;
  Instance = ATL::CAtlStringMgr::GetInstance();
  if ( !Instance )
    ATL::AtlThrowImpl(-2147467259);
  v5 = (BYTE *)((*(__int64 (__fastcall **)(struct ATL::IAtlStringMgr *))(*(_QWORD *)Instance + 24LL))(Instance) + 24);
  v25 = v5;
  cbData = 260;
  hKey = 0;
  lpsz = 0;
  v6 = ATL::CAtlStringMgr::GetInstance();
  if ( !v6 )
    ATL::AtlThrowImpl(-2147467259);
  lpSubKey = (LPCWSTR)((*(__int64 (__fastcall **)(struct ATL::IAtlStringMgr *))(*(_QWORD *)v6 + 24LL))(v6) + 24);
  v7 = StringFromCLSID(rclsid, &lpsz);
  if ( v7 >= 0 )
  {
    v8 = ATL::operator+(&v26, &detail::strRegistryRoot, L"\\CLSID\\");
    ATL::CSimpleStringT<unsigned short,0>::operator=(&lpSubKey, v8);
    v9 = v26 - 12;
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v26 - 2, 0xFFFFFFFF) <= 1 )
    {
      _mm_lfence();
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v9 + 8LL))(*(_QWORD *)v9);
    }
    if ( lpsz )
    {
      v10 = -1;
      do
        ++v10;
      while ( lpsz[v10] );
    }
    else
    {
      v10 = 0;
    }
    ATL::CSimpleStringT<unsigned short,0>::Append(&lpSubKey, lpsz, v10);
    v7 = -2147467259;
    v11 = -2147467259;
    v12 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0x20019u, &hKey);
    if ( !v12 )
    {
      if ( (cbData & 0x80000000) != 0 )
        goto LABEL_67;
      if ( (((1 - *((_DWORD *)v5 - 2)) | (*((_DWORD *)v5 - 3) - cbData)) & 0x80000000) != 0 )
      {
        _mm_lfence();
        ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(&v25, cbData);
        v5 = v25;
      }
      v13 = RegQueryValueExW(hKey, L"ThreadingModel", 0, &Type, v5, &cbData);
      v14 = wcsnlen_0((const wchar_t *)v5, *((int *)v5 - 3));
      if ( v14 < 0 || v14 > *((_DWORD *)v5 - 3) )
LABEL_67:
        ATL::AtlThrowImpl(-2147024809);
      *((_DWORD *)v5 - 4) = v14;
      *(_WORD *)&v5[2 * v14] = 0;
      if ( v13 )
      {
        ATL::CSimpleStringT<unsigned short,0>::SetString(&v25, &WindowName);
        v5 = v25;
      }
      else
      {
        ATL::CSimpleStringT<unsigned short,0>::AppendChar(&v25, 0);
        v5 = v25;
        v11 = *((_DWORD *)v25 - 4) == 0 ? 0x80004005 : 0;
      }
      RegCloseKey(hKey);
      hKey = 0;
    }
    ATL::CSimpleStringT<unsigned short,0>::Empty(&lpSubKey);
    if ( v11 >= 0 )
    {
LABEL_37:
      *a2 = GUID_NULL;
      if ( !wcscmp_0((const wchar_t *)v5, L"Apartment") )
      {
        v20 = CLSID_VsApartmentLoader;
      }
      else if ( !wcscmp_0((const wchar_t *)v5, L"Both") )
      {
        v20 = CLSID_VsBothLoader;
      }
      else if ( !wcscmp_0((const wchar_t *)v5, L"Free") )
      {
        v20 = CLSID_VsFreeLoader;
      }
      else
      {
        if ( *((_DWORD *)v5 - 4) )
        {
LABEL_49:
          v21 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&GUID_NULL.Data1;
          if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&GUID_NULL.Data1 )
            v21 = *(_QWORD *)a2->Data4 - *(_QWORD *)GUID_NULL.Data4;
          v22 = 0;
          if ( !v21 )
            v22 = -2147467259;
          v7 = v22;
          goto LABEL_54;
        }
        v20 = CLSID_VsDefaultLoader;
      }
      *a2 = v20;
      goto LABEL_49;
    }
    v15 = ATL::CAtlStringMgr::GetInstance();
    if ( !v15 )
      ATL::AtlThrowImpl(-2147467259);
    v26 = (LPCWSTR)((*(__int64 (__fastcall **)(struct ATL::IAtlStringMgr *))(*(_QWORD *)v15 + 24LL))(v15) + 24);
    ATL::CSimpleStringT<unsigned short,0>::SetString(&v26, L"CLSID\\");
    if ( lpsz )
    {
      v16 = -1;
      do
        ++v16;
      while ( lpsz[v16] );
    }
    else
    {
      v16 = 0;
    }
    ATL::CSimpleStringT<unsigned short,0>::Append(&v26, lpsz, v16);
    ATL::CSimpleStringT<unsigned short,0>::Append(&v26, L"\\", 1);
    ATL::CSimpleStringT<unsigned short,0>::Append(&v26, L"InProcServer32", 14);
    v17 = v26;
    if ( !RegOpenKeyExW(HKEY_CLASSES_ROOT, v26, 0, 0x20019u, &hKey) )
    {
      cbData = 260;
      if ( ((1 - *((_DWORD *)v5 - 2)) | (*((_DWORD *)v5 - 3) - 260)) < 0 )
      {
        _mm_lfence();
        ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(&v25, 260);
        v5 = v25;
      }
      v18 = RegQueryValueExW(hKey, L"ThreadingModel", 0, &Type, v5, &cbData);
      v19 = wcsnlen_0((const wchar_t *)v5, *((int *)v5 - 3));
      if ( v19 < 0 || v19 > *((_DWORD *)v5 - 3) )
        ATL::AtlThrowImpl(-2147024809);
      *((_DWORD *)v5 - 4) = v19;
      *(_WORD *)&v5[2 * v19] = 0;
      if ( v18 )
        ATL::CSimpleStringT<unsigned short,0>::SetString(&v25, &WindowName);
      else
        ATL::CSimpleStringT<unsigned short,0>::AppendChar(&v25, 0);
      v5 = v25;
      goto LABEL_35;
    }
    if ( !v12 )
    {
LABEL_35:
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v17 - 2, 0xFFFFFFFF) <= 1 )
      {
        _mm_lfence();
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v17 - 3) + 8LL))(*((_QWORD *)v17 - 3));
      }
      goto LABEL_37;
    }
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v17 - 2, 0xFFFFFFFF) <= 1 )
    {
      _mm_lfence();
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v17 - 3) + 8LL))(*((_QWORD *)v17 - 3));
    }
  }
LABEL_54:
  if ( lpsz )
    CoTaskMemFree(lpsz);
  if ( hKey )
    RegCloseKey(hKey);
  v23 = lpSubKey - 12;
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)lpSubKey - 2, 0xFFFFFFFF) <= 1 )
  {
    _mm_lfence();
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v23 + 8LL))(*(_QWORD *)v23);
  }
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)v5 - 2, 0xFFFFFFFF) <= 1 )
  {
    _mm_lfence();
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v5 - 3) + 8LL))(*((_QWORD *)v5 - 3));
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x14002d5e0  mov     [rsp-38h+arg_10], rbx
0x14002d5e5  push    rbp
0x14002d5e6  push    rsi
0x14002d5e7  push    rdi
0x14002d5e8  push    r12
0x14002d5ea  push    r13
0x14002d5ec  push    r14
0x14002d5ee  push    r15
0x14002d5f0  mov     rbp, rsp
0x14002d5f3  sub     rsp, 70h
0x14002d5f7  mov     rax, cs:__security_cookie
0x14002d5fe  xor     rax, rsp
0x14002d601  mov     [rbp+var_8], rax
0x14002d605  mov     r14, rdx
0x14002d608  mov     rdi, rcx
0x14002d60b  mov     r15d, 1
0x14002d611  mov     [rbp+Type], r15d
0x14002d615  call    ?GetInstance@CAtlStringMgr@ATL@@SAPEAUIAtlStringMgr@2@XZ; ATL::CAtlStringMgr::GetInstance(void)
0x14002d61a  mov     rcx, rax
0x14002d61d  xor     r12d, r12d
0x14002d620  test    rax, rax
0x14002d623  jz      loc_14002DAA5
0x14002d629  mov     rax, [rax]
0x14002d62c  call    qword ptr [rax+18h]
0x14002d62f  lea     rbx, [rax+18h]
0x14002d633  mov     [rbp+var_40], rbx
0x14002d637  mov     [rbp+cbData], 104h
0x14002d63e  mov     [rbp+hKey], r12
0x14002d642  mov     [rbp+lpsz], r12
0x14002d646  call    ?GetInstance@CAtlStringMgr@ATL@@SAPEAUIAtlStringMgr@2@XZ; ATL::CAtlStringMgr::GetInstance(void)
0x14002d64b  mov     rcx, rax
0x14002d64e  test    rax, rax
0x14002d651  jz      loc_14002DAB3
0x14002d657  mov     rax, [rax]
0x14002d65a  call    qword ptr [rax+18h]
0x14002d65d  add     rax, 18h
0x14002d661  mov     [rbp+lpSubKey], rax
0x14002d665  lea     rdx, [rbp+lpsz]; lplpsz
0x14002d669  mov     rcx, rdi; rclsid
0x14002d66c  call    cs:__imp_StringFromCLSID
0x14002d672  mov     esi, eax
0x14002d674  test    eax, eax
0x14002d676  js      loc_14002DA12
0x14002d67c  lea     r8, aClsid_0; "\\CLSID\\"
0x14002d683  lea     rdx, ?strRegistryRoot@detail@@3V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@A; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> detail::strRegistryRoot
0x14002d68a  lea     rcx, [rbp+var_38]
0x14002d68e  call    ??HATL@@YA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@0@AEBV10@PEBG@Z; ATL::operator+(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ushort const *)
0x14002d693  mov     rdx, rax
0x14002d696  lea     rcx, [rbp+lpSubKey]
0x14002d69a  call    ??4?$CSimpleStringT@G$0A@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CSimpleStringT<ushort,0>::operator=(ATL::CSimpleStringT<ushort,0> const &)
0x14002d69f  mov     rdx, [rbp+var_38]
0x14002d6a3  add     rdx, 0FFFFFFFFFFFFFFE8h
0x14002d6a7  or      eax, 0FFFFFFFFh
0x14002d6aa  lock xadd [rdx+10h], eax
0x14002d6af  sub     eax, r15d
0x14002d6b2  jg      short loc_14002D6C0
0x14002d6b4  lfence
0x14002d6b7  mov     rcx, [rdx]
0x14002d6ba  mov     rax, [rcx]
0x14002d6bd  call    qword ptr [rax+8]
0x14002d6c0  mov     rdx, [rbp+lpsz]
0x14002d6c4  test    rdx, rdx
0x14002d6c7  jnz     short loc_14002D6CE
0x14002d6c9  mov     r8d, r12d
0x14002d6cc  jmp     short loc_14002D6DC
0x14002d6ce  or      r8, 0FFFFFFFFFFFFFFFFh
0x14002d6d2  inc     r8
0x14002d6d5  cmp     [rdx+r8*2], r12w
0x14002d6da  jnz     short loc_14002D6D2
0x14002d6dc  lea     rcx, [rbp+lpSubKey]
0x14002d6e0  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *,int)
0x14002d6e5  mov     esi, 80004005h
0x14002d6ea  mov     edi, esi
0x14002d6ec  lea     rax, [rbp+hKey]
0x14002d6f0  mov     [rsp+70h+phkResult], rax; phkResult
0x14002d6f5  mov     r9d, 20019h; samDesired
0x14002d6fb  xor     r8d, r8d; ulOptions
0x14002d6fe  mov     rdx, [rbp+lpSubKey]; lpSubKey
0x14002d702  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14002d709  call    cs:__imp_RegOpenKeyExW
0x14002d70f  mov     r13d, eax
0x14002d712  test    eax, eax
0x14002d714  jnz     loc_14002D7E0
0x14002d71a  mov     r8d, [rbp+cbData]
0x14002d71e  test    r8d, r8d
0x14002d721  js      loc_14002DAC9
0x14002d727  mov     edx, r15d
0x14002d72a  sub     edx, [rbx-8]
0x14002d72d  mov     ecx, [rbx-0Ch]
0x14002d730  sub     ecx, r8d
0x14002d733  or      ecx, edx
0x14002d735  jge     short loc_14002D74A
0x14002d737  lfence
0x14002d73a  mov     edx, [rbp+cbData]
0x14002d73d  lea     rcx, [rbp+var_40]
0x14002d741  call    ?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)
0x14002d746  mov     rbx, [rbp+var_40]
0x14002d74a  lea     rax, [rbp+cbData]
0x14002d74e  mov     [rsp+70h+lpcbData], rax; lpcbData
0x14002d753  mov     [rsp+70h+phkResult], rbx; lpData
0x14002d758  lea     r9, [rbp+Type]; lpType
0x14002d75c  xor     r8d, r8d; lpReserved
0x14002d75f  lea     rdx, aThreadingmodel; "ThreadingModel"
0x14002d766  mov     rcx, [rbp+hKey]; hKey
0x14002d76a  call    cs:__imp_RegQueryValueExW
0x14002d770  mov     r12d, eax
0x14002d773  movsxd  rdx, dword ptr [rbx-0Ch]; MaxCount
0x14002d777  mov     rcx, rbx; Source
0x14002d77a  call    wcsnlen_0
0x14002d77f  xor     ecx, ecx
0x14002d781  test    eax, eax
0x14002d783  js      loc_14002DAC9
0x14002d789  cmp     eax, [rbx-0Ch]
0x14002d78c  jg      loc_14002DAC9
0x14002d792  mov     [rbx-10h], eax
0x14002d795  cdqe
0x14002d797  mov     [rbx+rax*2], cx
0x14002d79b  lea     rcx, [rbp+var_40]
0x14002d79f  test    r12d, r12d
0x14002d7a2  jnz     short loc_14002D7BC
0x14002d7a4  xor     edx, edx
0x14002d7a6  call    ?AppendChar@?$CSimpleStringT@G$0A@@ATL@@QEAAXG@Z; ATL::CSimpleStringT<ushort,0>::AppendChar(ushort)
0x14002d7ab  mov     rbx, [rbp+var_40]
0x14002d7af  mov     eax, [rbx-10h]
0x14002d7b2  neg     eax
0x14002d7b4  sbb     edi, edi
0x14002d7b6  not     edi
0x14002d7b8  and     edi, esi
0x14002d7ba  jmp     short loc_14002D7CF
0x14002d7bc  xor     r8d, r8d
0x14002d7bf  lea     rdx, WindowName
0x14002d7c6  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x14002d7cb  mov     rbx, [rbp+var_40]
0x14002d7cf  mov     rcx, [rbp+hKey]; hKey
0x14002d7d3  call    cs:__imp_RegCloseKey
0x14002d7d9  xor     r12d, r12d
0x14002d7dc  mov     [rbp+hKey], r12
0x14002d7e0  lea     rcx, [rbp+lpSubKey]
0x14002d7e4  call    ?Empty@?$CSimpleStringT@G$0A@@ATL@@QEAAXXZ; ATL::CSimpleStringT<ushort,0>::Empty(void)
0x14002d7e9  test    edi, edi
0x14002d7eb  jns     loc_14002D95A
0x14002d7f1  call    ?GetInstance@CAtlStringMgr@ATL@@SAPEAUIAtlStringMgr@2@XZ; ATL::CAtlStringMgr::GetInstance(void)
0x14002d7f6  mov     rcx, rax
0x14002d7f9  test    rax, rax
0x14002d7fc  jz      loc_14002DAC1
0x14002d802  mov     rax, [rax]
0x14002d805  call    qword ptr [rax+18h]
0x14002d808  add     rax, 18h
0x14002d80c  mov     [rbp+var_38], rax
0x14002d810  mov     r8d, 6
0x14002d816  lea     rdx, aClsid; "CLSID\\"
0x14002d81d  lea     rcx, [rbp+var_38]
0x14002d821  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x14002d826  mov     rdx, [rbp+lpsz]
0x14002d82a  test    rdx, rdx
0x14002d82d  jnz     short loc_14002D834
0x14002d82f  mov     r8d, r12d
0x14002d832  jmp     short loc_14002D842
0x14002d834  or      r8, 0FFFFFFFFFFFFFFFFh
0x14002d838  inc     r8
0x14002d83b  cmp     [rdx+r8*2], r12w
0x14002d840  jnz     short loc_14002D838
0x14002d842  lea     rcx, [rbp+var_38]
0x14002d846  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *,int)
0x14002d84b  mov     r8d, r15d
0x14002d84e  lea     rdx, SubBlock; "\\"
0x14002d855  lea     rcx, [rbp+var_38]
0x14002d859  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *,int)
0x14002d85e  mov     r8d, 0Eh
0x14002d864  lea     rdx, aInprocserver32_0; "InProcServer32"
0x14002d86b  lea     rcx, [rbp+var_38]
0x14002d86f  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *,int)
0x14002d874  lea     rax, [rbp+hKey]
0x14002d878  mov     [rsp+70h+phkResult], rax; phkResult
0x14002d87d  mov     r9d, 20019h; samDesired
0x14002d883  xor     r8d, r8d; ulOptions
0x14002d886  mov     rdi, [rbp+var_38]
0x14002d88a  mov     rdx, rdi; lpSubKey
0x14002d88d  mov     rcx, 0FFFFFFFF80000000h; hKey
0x14002d894  call    cs:__imp_RegOpenKeyExW
0x14002d89a  test    eax, eax
0x14002d89c  jnz     loc_14002D982
0x14002d8a2  mov     edx, 104h
0x14002d8a7  mov     [rbp+cbData], edx
0x14002d8aa  sub     r15d, [rbx-8]
0x14002d8ae  mov     eax, [rbx-0Ch]
0x14002d8b1  sub     eax, edx
0x14002d8b3  or      eax, r15d
0x14002d8b6  jge     short loc_14002D8C8
0x14002d8b8  lfence
0x14002d8bb  lea     rcx, [rbp+var_40]
0x14002d8bf  call    ?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)
0x14002d8c4  mov     rbx, [rbp+var_40]
0x14002d8c8  lea     rax, [rbp+cbData]
0x14002d8cc  mov     [rsp+70h+lpcbData], rax; lpcbData
0x14002d8d1  mov     [rsp+70h+phkResult], rbx; lpData
0x14002d8d6  lea     r9, [rbp+Type]; lpType
0x14002d8da  xor     r8d, r8d; lpReserved
0x14002d8dd  lea     rdx, aThreadingmodel; "ThreadingModel"
0x14002d8e4  mov     rcx, [rbp+hKey]; hKey
0x14002d8e8  call    cs:__imp_RegQueryValueExW
0x14002d8ee  mov     r15d, eax
0x14002d8f1  movsxd  rdx, dword ptr [rbx-0Ch]; MaxCount
0x14002d8f5  mov     rcx, rbx; Source
0x14002d8f8  call    wcsnlen_0
0x14002d8fd  test    eax, eax
0x14002d8ff  js      loc_14002DA96
0x14002d905  cmp     eax, [rbx-0Ch]
0x14002d908  jg      loc_14002DA96
0x14002d90e  mov     [rbx-10h], eax
0x14002d911  cdqe
0x14002d913  mov     [rbx+rax*2], r12w
0x14002d918  lea     rcx, [rbp+var_40]
0x14002d91c  test    r15d, r15d
0x14002d91f  jnz     short loc_14002D92A
0x14002d921  xor     edx, edx
0x14002d923  call    ?AppendChar@?$CSimpleStringT@G$0A@@ATL@@QEAAXG@Z; ATL::CSimpleStringT<ushort,0>::AppendChar(ushort)
0x14002d928  jmp     short loc_14002D939
0x14002d92a  xor     r8d, r8d
0x14002d92d  lea     rdx, WindowName
0x14002d934  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x14002d939  mov     rbx, [rbp+var_40]
0x14002d93d  lea     rdx, [rdi-18h]
0x14002d941  or      eax, 0FFFFFFFFh
0x14002d944  lock xadd [rdx+10h], eax
0x14002d949  sub     eax, 1
0x14002d94c  jg      short loc_14002D95A
0x14002d94e  lfence
0x14002d951  mov     rcx, [rdx]
0x14002d954  mov     rax, [rcx]
0x14002d957  call    qword ptr [rax+8]
0x14002d95a  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x14002d961  movdqu  xmmword ptr [r14], xmm0
0x14002d966  lea     rdx, aApartment; "Apartment"
0x14002d96d  mov     rcx, rbx; String1
0x14002d970  call    wcscmp_0
0x14002d975  test    eax, eax
0x14002d977  jnz     short loc_14002D9A6
0x14002d979  movups  xmm0, xmmword ptr cs:CLSID_VsApartmentLoader.Data1
0x14002d980  jmp     short loc_14002D9EB
0x14002d982  test    r13d, r13d
0x14002d985  jz      short loc_14002D93D
0x14002d987  lea     rdx, [rdi-18h]
0x14002d98b  or      eax, 0FFFFFFFFh
0x14002d98e  lock xadd [rdx+10h], eax
0x14002d993  sub     eax, 1
0x14002d996  jg      short loc_14002DA12
0x14002d998  lfence
0x14002d99b  mov     rcx, [rdx]
0x14002d99e  mov     rax, [rcx]
0x14002d9a1  call    qword ptr [rax+8]
0x14002d9a4  jmp     short loc_14002DA12
0x14002d9a6  lea     rdx, aBoth; "Both"
0x14002d9ad  mov     rcx, rbx; String1
0x14002d9b0  call    wcscmp_0
0x14002d9b5  test    eax, eax
0x14002d9b7  jnz     short loc_14002D9C2
0x14002d9b9  movups  xmm0, xmmword ptr cs:CLSID_VsBothLoader.Data1
0x14002d9c0  jmp     short loc_14002D9EB
0x14002d9c2  lea     rdx, aFree; "Free"
0x14002d9c9  mov     rcx, rbx; String1
0x14002d9cc  call    wcscmp_0
0x14002d9d1  test    eax, eax
0x14002d9d3  jnz     short loc_14002D9DE
0x14002d9d5  movups  xmm0, xmmword ptr cs:CLSID_VsFreeLoader.Data1
0x14002d9dc  jmp     short loc_14002D9EB
0x14002d9de  cmp     [rbx-10h], r12d
0x14002d9e2  jnz     short loc_14002D9F0
0x14002d9e4  movups  xmm0, xmmword ptr cs:CLSID_VsDefaultLoader.Data1
0x14002d9eb  movdqu  xmmword ptr [r14], xmm0
0x14002d9f0  mov     rcx, [r14]
0x14002d9f3  sub     rcx, qword ptr cs:GUID_NULL.Data1
0x14002d9fa  jnz     short loc_14002DA07
0x14002d9fc  mov     rcx, [r14+8]
0x14002da00  sub     rcx, qword ptr cs:GUID_NULL.Data4
0x14002da07  mov     eax, r12d
0x14002da0a  test    rcx, rcx
0x14002da0d  cmovz   eax, esi
0x14002da10  mov     esi, eax
0x14002da12  mov     rcx, [rbp+lpsz]; pv
0x14002da16  test    rcx, rcx
0x14002da19  jz      short loc_14002DA21
0x14002da1b  call    cs:__imp_CoTaskMemFree
0x14002da21  mov     rcx, [rbp+hKey]; hKey
0x14002da25  test    rcx, rcx
0x14002da28  jz      short loc_14002DA31
0x14002da2a  call    cs:__imp_RegCloseKey
0x14002da30  nop
0x14002da31  mov     rdx, [rbp+lpSubKey]
0x14002da35  add     rdx, 0FFFFFFFFFFFFFFE8h
0x14002da39  or      eax, 0FFFFFFFFh
0x14002da3c  lock xadd [rdx+10h], eax
0x14002da41  sub     eax, 1
0x14002da44  jg      short loc_14002DA53
0x14002da46  lfence
0x14002da49  mov     rcx, [rdx]
0x14002da4c  mov     rax, [rcx]
0x14002da4f  call    qword ptr [rax+8]
0x14002da52  nop
0x14002da53  lea     rdx, [rbx-18h]
  ... truncated ...
```
