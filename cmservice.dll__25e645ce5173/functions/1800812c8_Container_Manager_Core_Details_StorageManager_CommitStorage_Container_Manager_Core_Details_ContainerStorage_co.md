# Container::Manager::Core::Details::StorageManager::CommitStorage(Container::Manager::Core::Details::ContainerStorage const &,void *)

- ea: `0x1800812c8`
- end: `0x180081913`
- name: `?CommitStorage@StorageManager@Details@Core@Manager@Container@@QEAAJAEBVContainerStorage@2345@PEAX@Z`
- size: `1611`
- prototype: `__int64 __fastcall(Container::Manager::Core::Details::StorageManager *__hidden this, const struct Container::Manager::Core::Details::ContainerStorage *, void *)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x180053648`

## callees

- `0x180004fc4`
- `0x18000da68`
- `0x18000da88`
- `0x18002c5b4`
- `0x180032344`
- `0x1800343f0`
- `0x180034674`
- `0x1800346e8`
- `0x180034918`
- `0x180034968`
- `0x1800349e0`
- `0x18006cda4`
- `0x18007f8a4`
- `0x1800812c8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008137d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008137d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18008139c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18008139c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180081695`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180081730`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800817aa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800818ba`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180081695`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180081730`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800817aa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800818ba`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x180081661`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x180081661`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008138e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008146f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008148c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180081745`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800817c3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800818cf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008138e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008146f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008148c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180081745`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800817c3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800818cf`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x1800813b6`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x1800813b6`

## string_xrefs

- `0x1800813df`: `onecore\base\gendrv\silos\csl\lib\cslregistry.cpp`
- `0x1800813d3`: `Failed to delete subkey with name '%ws'`
- `0x18008186e`: `DebugConfiguration`
- `0x1800816c6`: `SecurityDescriptor`

## pseudocode

```c
__int64 __fastcall Container::Manager::Core::Details::StorageManager::CommitStorage(
        Container::Manager::Core::Details::StorageManager *this,
        const struct Container::Manager::Core::Details::ContainerStorage *a2,
        void *a3)
{
  int v6; // eax
  int RegistryKeyTransacted; // ebx
  WCHAR *v8; // rcx
  bool v9; // zf
  __int64 v11; // rcx
  int v12; // eax
  __int64 v13; // r8
  HKEY v14; // rsi
  DWORD LastError; // ebx
  const char *v16; // rsi
  HKEY v17; // rbx
  unsigned int v18; // eax
  int v19; // esi
  HKEY v20; // rcx
  __int64 v21; // rcx
  __int64 v22; // rdx
  void *v23; // rcx
  const char *v24; // r9
  __int64 v25; // rax
  unsigned int v26; // r9d
  __int64 v27; // rdx
  int v28; // eax
  __int64 v29; // rcx
  __int64 v30; // rdx
  int StringSecurityDescriptorLen; // [rsp+20h] [rbp-60h]
  int StringSecurityDescriptorLena; // [rsp+20h] [rbp-60h]
  HKEY v33; // [rsp+30h] [rbp-50h] BYREF
  LPWSTR StringSecurityDescriptor; // [rsp+38h] [rbp-48h] BYREF
  LPCWSTR lpSubKey[2]; // [rsp+40h] [rbp-40h] BYREF
  _WORD v36[8]; // [rsp+50h] [rbp-30h] BYREF
  unsigned __int16 *v37; // [rsp+60h] [rbp-20h] BYREF
  _WORD *v38; // [rsp+68h] [rbp-18h]
  _WORD v39[8]; // [rsp+70h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+28h]
  HKEY hKey; // [rsp+C8h] [rbp+48h] BYREF

  lpSubKey[0] = v36;
  lpSubKey[1] = v36;
  v36[0] = 0;
  v6 = Csl::GuidToString(a2, lpSubKey);
  RegistryKeyTransacted = v6;
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x30C,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\storage.cpp",
      (const char *)(unsigned int)v6,
      StringSecurityDescriptorLen);
LABEL_3:
    v8 = (WCHAR *)lpSubKey[0];
    v9 = lpSubKey[0] == v36;
LABEL_4:
    if ( !v9 )
      operator delete(v8, (const struct std::nothrow_t *)&std::nothrow);
    return (unsigned int)RegistryKeyTransacted;
  }
  v11 = *((_QWORD *)this + 1);
  hKey = 0;
  v12 = Csl::OpenRegistryKey(v11, lpSubKey[0], 131103, &hKey);
  RegistryKeyTransacted = v12;
  if ( v12 < 0 )
  {
    if ( v12 != -2147024894 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x31E,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\storage.cpp",
        (const char *)(unsigned int)v12,
        StringSecurityDescriptorLen);
      v20 = hKey;
      goto LABEL_21;
    }
    v17 = hKey;
  }
  else
  {
    v14 = hKey;
    if ( hKey )
    {
      LastError = GetLastError();
      RegCloseKey(v14);
      SetLastError(LastError);
    }
    v16 = (const char *)lpSubKey[0];
    v17 = 0;
    v18 = RegDeleteKeyW(*((HKEY *)this + 1), lpSubKey[0]);
    if ( v18 == 2 )
    {
      v19 = -2147024894;
LABEL_15:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x31A,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\storage.cpp",
        (const char *)(unsigned int)v19,
        StringSecurityDescriptorLen);
LABEL_16:
      if ( lpSubKey[0] != v36 )
        operator delete((void *)lpSubKey[0], (const struct std::nothrow_t *)&std::nothrow);
      return (unsigned int)v19;
    }
    if ( v18 )
    {
      v19 = wil::details::in1diag3::Return_Win32Msg(
              retaddr,
              (void *)0x10B,
              (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslregistry.cpp",
              (const char *)v18,
              (unsigned int)"Failed to delete subkey with name '%ws'",
              v16);
      if ( v19 < 0 )
        goto LABEL_15;
    }
  }
  if ( v17 )
    RegCloseKey(v17);
  v21 = *((_QWORD *)this + 1);
  v33 = 0;
  LOBYTE(hKey) = 0;
  RegistryKeyTransacted = Csl::CreateRegistryKeyTransacted(v21, lpSubKey[0], v13, a3);
  if ( RegistryKeyTransacted < 0 )
  {
    v22 = 809;
LABEL_28:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v22,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\storage.cpp",
      (const char *)(unsigned int)RegistryKeyTransacted,
      (int)&v33);
LABEL_29:
    v20 = v33;
LABEL_21:
    if ( v20 )
      RegCloseKey(v20);
    goto LABEL_3;
  }
  RegistryKeyTransacted = Csl::RegistryKey::SetDwordValue((Csl::RegistryKey *)&v33, L"ClientId", *((_DWORD *)a2 + 9));
  if ( RegistryKeyTransacted < 0 )
  {
    v22 = 816;
    goto LABEL_28;
  }
  RegistryKeyTransacted = Csl::RegistryKey::SetDwordValue((Csl::RegistryKey *)&v33, L"ParentType", *((_DWORD *)a2 + 4));
  if ( RegistryKeyTransacted < 0 )
  {
    v22 = 820;
    goto LABEL_28;
  }
  RegistryKeyTransacted = Csl::RegistryKey::SetGuidValue(
                            (Csl::RegistryKey *)&v33,
                            L"ParentId",
                            (const struct _GUID *)((char *)a2 + 20));
  if ( RegistryKeyTransacted < 0 )
  {
    v22 = 824;
    goto LABEL_28;
  }
  RegistryKeyTransacted = Csl::RegistryKey::SetDwordValue((Csl::RegistryKey *)&v33, L"State", *((_DWORD *)a2 + 60));
  if ( RegistryKeyTransacted < 0 )
  {
    v22 = 828;
    goto LABEL_28;
  }
  RegistryKeyTransacted = Csl::RegistryKey::SetPathValue(
                            (Csl::RegistryKey *)&v33,
                            L"StorageFolder",
                            (const struct Container::Manager::Core::Details::ContainerStorage *)((char *)a2 + 48));
  if ( RegistryKeyTransacted < 0 )
  {
    v22 = 832;
    goto LABEL_28;
  }
  RegistryKeyTransacted = Csl::RegistryKey::SetDwordValue(
                            (Csl::RegistryKey *)&v33,
                            L"BackingType",
                            *((_DWORD *)a2 + 36));
  if ( RegistryKeyTransacted < 0 )
  {
    v22 = 836;
    goto LABEL_28;
  }
  RegistryKeyTransacted = Csl::RegistryKey::SetDwordValue((Csl::RegistryKey *)&v33, L"Flags", *((_DWORD *)a2 + 68));
  if ( RegistryKeyTransacted < 0 )
  {
    v22 = 840;
    goto LABEL_28;
  }
  if ( *((_BYTE *)a2 + 368) )
  {
    RegistryKeyTransacted = Csl::RegistryKey::SetGuidValue(
                              (Csl::RegistryKey *)&v33,
                              L"ServicingTransactionId",
                              (const struct _GUID *)a2 + 22);
    if ( RegistryKeyTransacted < 0 )
    {
      v22 = 846;
      goto LABEL_28;
    }
  }
  if ( !*((_BYTE *)a2 + 400) )
    __int2c();
  RegistryKeyTransacted = Csl::RegistryKey::SetQwordValue(
                            (Csl::RegistryKey *)&v33,
                            L"MaxSizeInBytes",
                            *((_QWORD *)a2 + 49));
  if ( RegistryKeyTransacted < 0 )
  {
    v22 = 852;
    goto LABEL_28;
  }
  v23 = (void *)*((_QWORD *)a2 + 51);
  StringSecurityDescriptor = 0;
  if ( !ConvertSecurityDescriptorToStringSecurityDescriptorW(v23, 1u, 0xFu, &StringSecurityDescriptor, 0) )
  {
    RegistryKeyTransacted = wil::details::in1diag3::Return_GetLastError(
                              retaddr,
                              (void *)0x363,
                              (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\storage.cpp",
                              v24);
    goto LABEL_53;
  }
  if ( StringSecurityDescriptor )
  {
    v25 = -1;
    do
      ++v25;
    while ( StringSecurityDescriptor[v25] );
    v26 = v25 + 1;
  }
  else
  {
    v26 = 0;
  }
  RegistryKeyTransacted = Csl::RegistryKey::SetStringValue(
                            (Csl::RegistryKey *)&v33,
                            L"SecurityDescriptor",
                            StringSecurityDescriptor,
                            v26);
  if ( RegistryKeyTransacted < 0 )
  {
    v27 = 870;
LABEL_62:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v27,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\storage.cpp",
      (const char *)(unsigned int)RegistryKeyTransacted,
      StringSecurityDescriptorLena);
LABEL_53:
    if ( StringSecurityDescriptor )
      LocalFree(StringSecurityDescriptor);
    goto LABEL_29;
  }
  if ( *((_DWORD *)a2 + 36) != 1 )
  {
    if ( *((_DWORD *)a2 + 36) != 2 )
    {
      RegistryKeyTransacted = -2147418113;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x381,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\storage.cpp",
        (const char *)0x8000FFFFLL,
        StringSecurityDescriptorLena);
      if ( StringSecurityDescriptor )
        LocalFree(StringSecurityDescriptor);
      if ( v33 )
        RegCloseKey(v33);
      v8 = (WCHAR *)lpSubKey[0];
      v9 = lpSubKey[0] == v36;
      goto LABEL_4;
    }
    if ( !*((_BYTE *)a2 + 224) )
      __int2c();
    v28 = Csl::RegistryKey::SetGuidValue((Csl::RegistryKey *)&v33, L"PoolId", (const struct _GUID *)a2 + 12);
    v19 = v28;
    if ( v28 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x375,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\storage.cpp",
        (const char *)(unsigned int)v28,
        StringSecurityDescriptorLena);
      if ( StringSecurityDescriptor )
        LocalFree(StringSecurityDescriptor);
      if ( v33 )
        RegCloseKey(v33);
      goto LABEL_16;
    }
    RegistryKeyTransacted = Csl::RegistryKey::SetGuidValue(
                              (Csl::RegistryKey *)&v33,
                              L"SpaceId",
                              (const struct _GUID *)a2 + 13);
    if ( RegistryKeyTransacted < 0 )
    {
      v27 = 889;
      goto LABEL_62;
    }
  }
  v29 = *((_QWORD *)a2 + 47);
  if ( v29 )
  {
    v39[0] = 0;
    v37 = v39;
    v38 = v39;
    RegistryKeyTransacted = Csl::MarshalToJson<Container::Manager::Core::Details::DebugConfiguration>(v29 + 16, &v37);
    if ( RegistryKeyTransacted < 0 )
    {
      v30 = 907;
      goto LABEL_82;
    }
    RegistryKeyTransacted = Csl::RegistryKey::SetStringValue(
                              (Csl::RegistryKey *)&v33,
                              L"DebugConfiguration",
                              v37,
                              v38 - v37 + 1);
    if ( RegistryKeyTransacted < 0 )
    {
      v30 = 910;
LABEL_82:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v30,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\storage.cpp",
        (const char *)(unsigned int)RegistryKeyTransacted,
        StringSecurityDescriptorLena);
      if ( v37 != v39 )
        operator delete(v37, (const struct std::nothrow_t *)&std::nothrow);
      goto LABEL_53;
    }
    if ( v37 != v39 )
      operator delete(v37, (const struct std::nothrow_t *)&std::nothrow);
  }
  if ( StringSecurityDescriptor )
    LocalFree(StringSecurityDescriptor);
  if ( v33 )
    RegCloseKey(v33);
  if ( lpSubKey[0] != v36 )
    operator delete((void *)lpSubKey[0], (const struct std::nothrow_t *)&std::nothrow);
  return 0;
}

```

## disassembly

```asm
0x1800812c8  mov     [rsp-28h+arg_0], rbx
0x1800812cd  mov     [rsp-28h+arg_8], rsi
0x1800812d2  push    rbp
0x1800812d3  push    rdi
0x1800812d4  push    r12
0x1800812d6  push    r14
0x1800812d8  push    r15
0x1800812da  mov     rbp, rsp
0x1800812dd  sub     rsp, 80h
0x1800812e4  mov     rdi, rdx
0x1800812e7  lea     rax, [rbp+var_30]
0x1800812eb  mov     [rbp+lpSubKey], rax
0x1800812ef  lea     rdx, [rbp+lpSubKey]
0x1800812f3  lea     rax, [rbp+var_30]
0x1800812f7  mov     r14, rcx
0x1800812fa  xor     r12d, r12d
0x1800812fd  mov     [rbp+var_38], rax
0x180081301  mov     rcx, rdi
0x180081304  mov     [rbp+var_30], r12w
0x180081309  mov     r15, r8
0x18008130c  call    ?GuidToString@Csl@@YAJAEBU_GUID@@AEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z; Csl::GuidToString(_GUID const &,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &)
0x180081311  mov     ebx, eax
0x180081313  test    eax, eax
0x180081315  jns     short loc_18008134F
0x180081317  mov     rcx, [rbp+28h]; this
0x18008131b  lea     r8, aOnecoreBaseGen_54; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x180081322  mov     r9d, eax; char *
0x180081325  mov     edx, 30Ch; void *
0x18008132a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008132f  mov     rcx, [rbp+lpSubKey]; void *
0x180081333  lea     rax, [rbp+var_30]
0x180081337  cmp     rcx, rax
0x18008133a  jz      short loc_180081348
0x18008133c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180081343  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180081348  mov     eax, ebx
0x18008134a  jmp     loc_1800818F6
0x18008134f  mov     rdx, [rbp+lpSubKey]
0x180081353  lea     r9, [rbp+hKey]
0x180081357  mov     rcx, [r14+8]
0x18008135b  mov     r8d, 2001Fh
0x180081361  mov     [rbp+hKey], r12
0x180081365  call    ?OpenRegistryKey@Csl@@YAJPEAUHKEY__@@PEBGW4RegistryKeyAccess@1@AEAVRegistryKey@1@@Z; Csl::OpenRegistryKey(HKEY__ *,ushort const *,Csl::RegistryKeyAccess,Csl::RegistryKey &)
0x18008136a  mov     ebx, eax
0x18008136c  test    eax, eax
0x18008136e  js      loc_180081441
0x180081374  mov     rsi, [rbp+hKey]
0x180081378  test    rsi, rsi
0x18008137b  jz      short loc_1800813A8
0x18008137d  call    cs:__imp_GetLastError
0x180081384  nop     dword ptr [rax+rax+00h]
0x180081389  mov     rcx, rsi; hKey
0x18008138c  mov     ebx, eax
0x18008138e  call    cs:__imp_RegCloseKey
0x180081395  nop     dword ptr [rax+rax+00h]
0x18008139a  mov     ecx, ebx; dwErrCode
0x18008139c  call    cs:__imp_SetLastError
0x1800813a3  nop     dword ptr [rax+rax+00h]
0x1800813a8  mov     rsi, [rbp+lpSubKey]
0x1800813ac  mov     rbx, r12
0x1800813af  mov     rcx, [r14+8]; hKey
0x1800813b3  mov     rdx, rsi; lpSubKey
0x1800813b6  call    cs:__imp_RegDeleteKeyW
0x1800813bd  nop     dword ptr [rax+rax+00h]
0x1800813c2  cmp     eax, 2
0x1800813c5  jz      short loc_180081404
0x1800813c7  test    eax, eax
0x1800813c9  jz      loc_180081484
0x1800813cf  mov     rcx, [rbp+28h]; this
0x1800813d3  lea     rdx, aFailedToDelete_0; "Failed to delete subkey with name '%ws'"
0x1800813da  mov     [rsp+80h+var_58], rsi; char *
0x1800813df  lea     r8, aOnecoreBaseGen_77; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x1800813e6  mov     [rsp+80h+StringSecurityDescriptorLen], rdx; unsigned int
0x1800813eb  mov     r9d, eax; char *
0x1800813ee  mov     edx, 10Bh; void *
0x1800813f3  call    ?Return_Win32Msg@in1diag3@details@wil@@YAJPEAXIPEBDK1ZZ; wil::details::in1diag3::Return_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x1800813f8  mov     esi, eax
0x1800813fa  test    eax, eax
0x1800813fc  jns     loc_180081484
0x180081402  jmp     short loc_180081409
0x180081404  mov     esi, 80070002h
0x180081409  mov     rcx, [rbp+28h]; this
0x18008140d  lea     r8, aOnecoreBaseGen_54; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x180081414  mov     r9d, esi; char *
0x180081417  mov     edx, 31Ah; void *
0x18008141c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180081421  mov     rcx, [rbp+lpSubKey]; void *
0x180081425  lea     rax, [rbp+var_30]
0x180081429  cmp     rcx, rax
0x18008142c  jz      short loc_18008143A
0x18008142e  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180081435  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18008143a  mov     eax, esi
0x18008143c  jmp     loc_1800818F6
0x180081441  mov     esi, 80070002h
0x180081446  cmp     ebx, esi
0x180081448  jz      short loc_180081480
0x18008144a  mov     rcx, [rbp+28h]; this
0x18008144e  lea     r8, aOnecoreBaseGen_54; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x180081455  mov     r9d, ebx; char *
0x180081458  mov     edx, 31Eh; void *
0x18008145d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180081462  mov     rcx, [rbp+hKey]; hKey
0x180081466  test    rcx, rcx
0x180081469  jz      loc_18008132F
0x18008146f  call    cs:__imp_RegCloseKey
0x180081476  nop     dword ptr [rax+rax+00h]
0x18008147b  jmp     loc_18008132F
0x180081480  mov     rbx, [rbp+hKey]
0x180081484  test    rbx, rbx
0x180081487  jz      short loc_180081498
0x180081489  mov     rcx, rbx; hKey
0x18008148c  call    cs:__imp_RegCloseKey
0x180081493  nop     dword ptr [rax+rax+00h]
0x180081498  mov     rdx, [rbp+lpSubKey]
0x18008149c  lea     rax, [rbp+hKey]
0x1800814a0  mov     rcx, [r14+8]
0x1800814a4  mov     r9, r15
0x1800814a7  mov     [rsp+80h+var_58], rax
0x1800814ac  lea     rax, [rbp+var_50]
0x1800814b0  mov     [rsp+80h+StringSecurityDescriptorLen], rax; int
0x1800814b5  mov     [rbp+var_50], r12
0x1800814b9  mov     byte ptr [rbp+hKey], r12b
0x1800814bd  call    ?CreateRegistryKeyTransacted@Csl@@YAJPEAUHKEY__@@PEBGW4RegistryKeyAccess@1@PEAXAEAVRegistryKey@1@AEA_N@Z; Csl::CreateRegistryKeyTransacted(HKEY__ *,ushort const *,Csl::RegistryKeyAccess,void *,Csl::RegistryKey &,bool &)
0x1800814c2  mov     ebx, eax
0x1800814c4  test    eax, eax
0x1800814c6  jns     short loc_1800814E6
0x1800814c8  mov     edx, 329h; void *
0x1800814cd  mov     rcx, [rbp+28h]; this
0x1800814d1  lea     r8, aOnecoreBaseGen_54; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x1800814d8  mov     r9d, ebx; char *
0x1800814db  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800814e0  mov     rcx, [rbp+var_50]
0x1800814e4  jmp     short loc_180081466
0x1800814e6  mov     r8d, [rdi+24h]; unsigned int
0x1800814ea  lea     rdx, aClientid; "ClientId"
0x1800814f1  lea     rcx, [rbp+var_50]; this
0x1800814f5  call    ?SetDwordValue@RegistryKey@Csl@@QEAAJPEBGK@Z; Csl::RegistryKey::SetDwordValue(ushort const *,ulong)
0x1800814fa  mov     ebx, eax
0x1800814fc  test    eax, eax
0x1800814fe  jns     short loc_180081507
0x180081500  mov     edx, 330h
0x180081505  jmp     short loc_1800814CD
0x180081507  mov     r8d, [rdi+10h]; unsigned int
0x18008150b  lea     rdx, aParenttype; "ParentType"
0x180081512  lea     rcx, [rbp+var_50]; this
0x180081516  call    ?SetDwordValue@RegistryKey@Csl@@QEAAJPEBGK@Z; Csl::RegistryKey::SetDwordValue(ushort const *,ulong)
0x18008151b  mov     ebx, eax
0x18008151d  test    eax, eax
0x18008151f  jns     short loc_180081528
0x180081521  mov     edx, 334h
0x180081526  jmp     short loc_1800814CD
0x180081528  lea     r8, [rdi+14h]; struct _GUID *
0x18008152c  lea     rdx, aParentid; "ParentId"
0x180081533  lea     rcx, [rbp+var_50]; this
0x180081537  call    ?SetGuidValue@RegistryKey@Csl@@QEAAJPEBGAEBU_GUID@@@Z; Csl::RegistryKey::SetGuidValue(ushort const *,_GUID const &)
0x18008153c  mov     ebx, eax
0x18008153e  test    eax, eax
0x180081540  jns     short loc_180081549
0x180081542  mov     edx, 338h
0x180081547  jmp     short loc_1800814CD
0x180081549  mov     r8d, [rdi+0F0h]; unsigned int
0x180081550  lea     rdx, aState; "State"
0x180081557  lea     rcx, [rbp+var_50]; this
0x18008155b  call    ?SetDwordValue@RegistryKey@Csl@@QEAAJPEBGK@Z; Csl::RegistryKey::SetDwordValue(ushort const *,ulong)
0x180081560  mov     ebx, eax
0x180081562  test    eax, eax
0x180081564  jns     short loc_180081570
0x180081566  mov     edx, 33Ch
0x18008156b  jmp     loc_1800814CD
0x180081570  lea     r8, [rdi+30h]; struct Path *
0x180081574  lea     rdx, aStoragefolder; "StorageFolder"
0x18008157b  lea     rcx, [rbp+var_50]; this
0x18008157f  call    ?SetPathValue@RegistryKey@Csl@@QEAAJPEBGAEBVPath@2@@Z; Csl::RegistryKey::SetPathValue(ushort const *,Csl::Path const &)
0x180081584  mov     ebx, eax
0x180081586  test    eax, eax
0x180081588  jns     short loc_180081594
0x18008158a  mov     edx, 340h
0x18008158f  jmp     loc_1800814CD
0x180081594  mov     r8d, [rdi+90h]; unsigned int
0x18008159b  lea     rdx, aBackingtype; "BackingType"
0x1800815a2  lea     rcx, [rbp+var_50]; this
0x1800815a6  call    ?SetDwordValue@RegistryKey@Csl@@QEAAJPEBGK@Z; Csl::RegistryKey::SetDwordValue(ushort const *,ulong)
0x1800815ab  mov     ebx, eax
0x1800815ad  test    eax, eax
0x1800815af  jns     short loc_1800815BB
0x1800815b1  mov     edx, 344h
0x1800815b6  jmp     loc_1800814CD
0x1800815bb  mov     r8d, [rdi+110h]; unsigned int
0x1800815c2  lea     rdx, aFlags; "Flags"
0x1800815c9  lea     rcx, [rbp+var_50]; this
0x1800815cd  call    ?SetDwordValue@RegistryKey@Csl@@QEAAJPEBGK@Z; Csl::RegistryKey::SetDwordValue(ushort const *,ulong)
0x1800815d2  mov     ebx, eax
0x1800815d4  test    eax, eax
0x1800815d6  jns     short loc_1800815E2
0x1800815d8  mov     edx, 348h
0x1800815dd  jmp     loc_1800814CD
0x1800815e2  cmp     [rdi+170h], r12b
0x1800815e9  jz      short loc_180081612
0x1800815eb  lea     r8, [rdi+160h]; struct _GUID *
0x1800815f2  lea     rdx, aServicingtrans_1; "ServicingTransactionId"
0x1800815f9  lea     rcx, [rbp+var_50]; this
0x1800815fd  call    ?SetGuidValue@RegistryKey@Csl@@QEAAJPEBGAEBU_GUID@@@Z; Csl::RegistryKey::SetGuidValue(ushort const *,_GUID const &)
0x180081602  mov     ebx, eax
0x180081604  test    eax, eax
0x180081606  jns     short loc_180081612
0x180081608  mov     edx, 34Eh
0x18008160d  jmp     loc_1800814CD
0x180081612  cmp     [rdi+190h], r12b
0x180081619  jnz     short loc_18008161D
0x18008161b  int     2Ch; Windows NT - assertion failure
0x18008161d  mov     r8, [rdi+188h]; unsigned __int64
0x180081624  lea     rdx, aMaxsizeinbytes; "MaxSizeInBytes"
0x18008162b  lea     rcx, [rbp+var_50]; this
0x18008162f  call    ?SetQwordValue@RegistryKey@Csl@@QEAAJPEBG_K@Z; Csl::RegistryKey::SetQwordValue(ushort const *,unsigned __int64)
0x180081634  mov     ebx, eax
0x180081636  test    eax, eax
0x180081638  jns     short loc_180081644
0x18008163a  mov     edx, 354h
0x18008163f  jmp     loc_1800814CD
0x180081644  mov     rcx, [rdi+198h]; SecurityDescriptor
0x18008164b  lea     r9, [rbp+StringSecurityDescriptor]; StringSecurityDescriptor
0x18008164f  mov     edx, 1; RequestedStringSDRevision
0x180081654  mov     [rbp+StringSecurityDescriptor], r12
0x180081658  mov     [rsp+80h+StringSecurityDescriptorLen], r12; int
0x18008165d  lea     r8d, [rdx+0Eh]; SecurityInformation
0x180081661  call    cs:__imp_ConvertSecurityDescriptorToStringSecurityDescriptorW
0x180081668  nop     dword ptr [rax+rax+00h]
0x18008166d  test    eax, eax
0x18008166f  jnz     short loc_1800816A6
0x180081671  mov     rcx, [rbp+28h]; this
0x180081675  lea     r8, aOnecoreBaseGen_54; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x18008167c  mov     edx, 363h; void *
0x180081681  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180081686  mov     ebx, eax
0x180081688  mov     rcx, [rbp+StringSecurityDescriptor]; hMem
0x18008168c  test    rcx, rcx
0x18008168f  jz      loc_1800814E0
0x180081695  call    cs:__imp_LocalFree
0x18008169c  nop     dword ptr [rax+rax+00h]
0x1800816a1  jmp     loc_1800814E0
0x1800816a6  mov     r8, [rbp+StringSecurityDescriptor]; unsigned __int16 *
0x1800816aa  test    r8, r8
0x1800816ad  jz      short loc_1800816C3
0x1800816af  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800816b3  inc     rax
0x1800816b6  cmp     [r8+rax*2], r12w
0x1800816bb  jnz     short loc_1800816B3
0x1800816bd  lea     r9d, [rax+1]
0x1800816c1  jmp     short loc_1800816C6
0x1800816c3  mov     r9d, r12d; unsigned int
0x1800816c6  lea     rdx, aSecuritydescri; "SecurityDescriptor"
0x1800816cd  lea     rcx, [rbp+var_50]; this
0x1800816d1  call    ?SetStringValue@RegistryKey@Csl@@QEAAJPEBG0K@Z; Csl::RegistryKey::SetStringValue(ushort const *,ushort const *,ulong)
0x1800816d6  mov     ebx, eax
0x1800816d8  test    eax, eax
0x1800816da  jns     short loc_1800816F6
0x1800816dc  mov     edx, 366h; void *
0x1800816e1  mov     rcx, [rbp+28h]; this
0x1800816e5  lea     r8, aOnecoreBaseGen_54; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x1800816ec  mov     r9d, ebx; char *
0x1800816ef  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800816f4  jmp     short loc_180081688
0x1800816f6  mov     ecx, [rdi+90h]
0x1800816fc  sub     ecx, 1
0x1800816ff  jz      loc_1800817F8
0x180081705  cmp     ecx, 1
0x180081708  jz      short loc_180081761
0x18008170a  mov     rcx, [rbp+28h]; this
0x18008170e  lea     r8, aOnecoreBaseGen_54; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x180081715  mov     ebx, 8000FFFFh
0x18008171a  mov     edx, 381h; void *
0x18008171f  mov     r9d, ebx; char *
0x180081722  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180081727  mov     rcx, [rbp+StringSecurityDescriptor]; hMem
0x18008172b  test    rcx, rcx
0x18008172e  jz      short loc_18008173C
0x180081730  call    cs:__imp_LocalFree
0x180081737  nop     dword ptr [rax+rax+00h]
0x18008173c  mov     rcx, [rbp+var_50]; hKey
0x180081740  test    rcx, rcx
0x180081743  jz      short loc_180081751
0x180081745  call    cs:__imp_RegCloseKey
0x18008174c  nop     dword ptr [rax+rax+00h]
0x180081751  mov     rcx, [rbp+lpSubKey]
0x180081755  lea     rdx, [rbp+var_30]
0x180081759  cmp     rcx, rdx
0x18008175c  jmp     loc_18008133A
0x180081761  lea     rbx, [rdi+0C0h]
0x180081768  cmp     [rbx+20h], r12b
0x18008176c  jnz     short loc_180081770
0x18008176e  int     2Ch; Windows NT - assertion failure
0x180081770  mov     r8, rbx; struct _GUID *
0x180081773  lea     rdx, aPoolid; "PoolId"
0x18008177a  lea     rcx, [rbp+var_50]; this
0x18008177e  call    ?SetGuidValue@RegistryKey@Csl@@QEAAJPEBGAEBU_GUID@@@Z; Csl::RegistryKey::SetGuidValue(ushort const *,_GUID const &)
0x180081783  mov     esi, eax
0x180081785  test    eax, eax
0x180081787  jns     short loc_1800817D4
0x180081789  mov     rcx, [rbp+28h]; this
  ... truncated ...
```
