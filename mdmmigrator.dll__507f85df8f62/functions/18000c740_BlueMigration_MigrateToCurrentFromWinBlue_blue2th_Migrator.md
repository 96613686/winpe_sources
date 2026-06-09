# BlueMigration::MigrateToCurrentFromWinBlue(blue2th::Migrator *)

- ea: `0x18000c740`
- end: `0x18000ca80`
- name: `?MigrateToCurrentFromWinBlue@BlueMigration@@SAXPEAVMigrator@blue2th@@@Z`
- size: `832`
- prototype: `void __fastcall(struct blue2th::Migrator *, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180008940`

## callees

- `0x1800018cc`
- `0x1800022e0`
- `0x1800034ac`
- `0x1800076a4`
- `0x180007720`
- `0x180007b38`
- `0x1800082ac`
- `0x180008520`
- `0x1800088a4`
- `0x1800097fc`
- `0x18000a8a8`
- `0x18000c214`
- `0x18000c3f8`
- `0x18000c42c`
- `0x18000c740`

## string_xrefs

- `0x18000c83c`: `Migration Attempted B2T`
- `0x18000c876`: `Migration Attempted B2T`
- `0x18000c8fc`: `Migration Attempted B2T`
- `0x18000c982`: `C:\Windows\System32\MDMAgent.exe`

## pseudocode

```c
void __fastcall BlueMigration::MigrateToCurrentFromWinBlue(
        struct blue2th::Migrator *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  _DWORD *v4; // rcx
  unsigned int v5; // r9d
  _DWORD *v6; // rcx
  int v7; // eax
  unsigned int v8; // r9d
  int v9; // eax
  unsigned int v10; // r9d
  unsigned int v11; // r9d
  _DWORD *v12; // r8
  __int64 v13; // r8
  __int64 v14; // r9
  _QWORD *v15; // rax
  blue2th::Migrator *v16; // rbx
  unsigned __int64 v17; // r8
  __int64 v18; // rax
  ScheduleMigrator *v19; // rcx
  __int64 v20; // r8
  unsigned int v21; // [rsp+20h] [rbp-59h]
  unsigned int v22; // [rsp+20h] [rbp-59h]
  unsigned int v23; // [rsp+20h] [rbp-59h]
  unsigned __int8 v24[8]; // [rsp+40h] [rbp-39h] BYREF
  int v25; // [rsp+48h] [rbp-31h] BYREF
  blue2th::Migrator *v26; // [rsp+50h] [rbp-29h] BYREF
  const unsigned __int16 *v27; // [rsp+58h] [rbp-21h] BYREF
  const unsigned __int16 *v28[2]; // [rsp+60h] [rbp-19h] BYREF
  __int128 v29; // [rsp+70h] [rbp-9h] BYREF
  unsigned int v30[2]; // [rsp+80h] [rbp+7h] BYREF
  blue2th::Migrator **v31; // [rsp+88h] [rbp+Fh]
  __int128 v32; // [rsp+90h] [rbp+17h] BYREF
  __int128 v33; // [rsp+A0h] [rbp+27h]

  v26 = a1;
  v25 = 0;
  if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 0x10) != 0 )
    McGenEventWrite_EventWriteTransfer(&MDM_ENTERPRISE_DIAGNOSTICS_Context, UserMigrationTaskStarted, a3, 1, v30);
  if ( (unsigned int)dword_18002B0C0 > 5
    && (qword_18002B0D0 & 0x400000000000LL) != 0
    && (qword_18002B0D8 & 0x400000000000LL) == qword_18002B0D8 )
  {
    v27 = L"Started";
    v28[0] = (const unsigned __int16 *)"onecoreuap\\admin\\enterprisemgmt\\migrator\\blue2th\\lib\\bluemigration.cpp";
    *(_DWORD *)v24 = 16;
    *(_QWORD *)v30 = L"BlueMigration::MigrateToCurrentFromWinBlue";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
      qword_18002B0D8,
      (__int64)&word_1800258B6,
      a3,
      a4,
      (const unsigned __int16 **)v30,
      (__int64)v24,
      v28,
      &v27);
  }
  *(_DWORD *)v24 = 0;
  v4 = (_DWORD *)*((_QWORD *)v26 + 3);
  if ( v4 )
    *v4 = 0;
  RegistryHelper::Write(L"SOFTWARE\\Microsoft\\Enrollment", L"Migration Attempted B2T", v24, a4, v21);
  blue2th::Migrator::GenerateRuntimeVariables((__int64 ***)v26);
  *(_DWORD *)v24 = 2;
  v6 = (_DWORD *)*((_QWORD *)v26 + 3);
  if ( v6 )
    *v6 = 2;
  RegistryHelper::Write(L"SOFTWARE\\Microsoft\\Enrollment", L"Migration Attempted B2T", v24, v5, v22);
  *(_QWORD *)v30 = &v25;
  v31 = &v26;
  v7 = wil::ResultFromException__lambda_3e99124a2e5926726931da8d3774c6b3___(v30);
  blue2th::Migrator::LogResult((__int64)v26, 4, v7, v8);
  *(_QWORD *)v30 = &v25;
  v31 = &v26;
  v9 = wil::ResultFromException__lambda_e38df7dad9b1c1b37a5409cde95813d1___(v30);
  blue2th::Migrator::LogResult((__int64)v26, 5, v9, v10);
  *(_DWORD *)v24 = 7;
  v12 = (_DWORD *)*((_QWORD *)v26 + 3);
  if ( v12 )
    *v12 = 7;
  RegistryHelper::Write(L"SOFTWARE\\Microsoft\\Enrollment", L"Migration Attempted B2T", v24, v11, v23);
  if ( (unsigned int)dword_18002B0C0 > 5
    && (qword_18002B0D0 & 0x400000000000LL) != 0
    && (qword_18002B0D8 & 0x400000000000LL) == qword_18002B0D8 )
  {
    *(_QWORD *)v30 = L"Success";
    v28[0] = (const unsigned __int16 *)"onecoreuap\\admin\\enterprisemgmt\\migrator\\blue2th\\lib\\bluemigration.cpp";
    *(_DWORD *)v24 = 38;
    v27 = L"BlueMigration::MigrateToCurrentFromWinBlue";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
      qword_18002B0D8,
      (__int64)qword_180025878,
      v13,
      v14,
      &v27,
      (__int64)v24,
      v28,
      (const unsigned __int16 **)v30);
  }
  v28[1] = L"C:\\Windows\\System32\\MDMAgent.exe";
  v29 = 0;
  v15 = operator new(0x60u);
  *v15 = v15;
  v15[1] = v15;
  v15[2] = v15;
  *((_WORD *)v15 + 12) = 257;
  *(_QWORD *)&v29 = v15;
  v16 = v26;
  v32 = 0;
  v33 = 0;
  v17 = -1;
  do
    ++v17;
  while ( userSidRtv[v17] );
  std::wstring::_Construct<1,unsigned short const *>(&v32, userSidRtv, v17);
  v18 = std::map<std::wstring,std::wstring>::operator[](v16, &v32);
  if ( *(_QWORD *)(v18 + 24) > 7u )
    v18 = *(_QWORD *)v18;
  v25 = ScheduleMigrator::DeleteSchedule(v19, (const unsigned __int16 *)v18);
  std::wstring::~wstring((char **)&v32);
  std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>((void **)&v29);
  if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 0x10) != 0 )
  {
    *(_DWORD *)v24 = v25;
    *(_QWORD *)&v33 = v24;
    *((_QWORD *)&v33 + 1) = 4;
    McGenEventWrite_EventWriteTransfer(&MDM_ENTERPRISE_DIAGNOSTICS_Context, UserMigrationTaskDeleted, v20, 2, &v32);
  }
}

```

## disassembly

```asm
0x18000c740  mov     [rsp-8+arg_8], rbx
0x18000c745  mov     [rsp-8+arg_10], rdi
0x18000c74a  push    rbp
0x18000c74b  push    r12
0x18000c74d  push    r13
0x18000c74f  lea     rbp, [rsp-47h]
0x18000c754  sub     rsp, 0C0h
0x18000c75b  mov     rax, cs:__security_cookie
0x18000c762  xor     rax, rsp
0x18000c765  mov     [rbp+57h+var_20], rax
0x18000c769  mov     [rbp+57h+var_80], rcx
0x18000c76d  xor     edi, edi
0x18000c76f  mov     [rbp+57h+var_88], edi
0x18000c772  test    cs:Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits, 10h
0x18000c779  jz      short loc_18000C79B
0x18000c77b  lea     rax, [rbp+57h+var_50]
0x18000c77f  mov     qword ptr [rsp+0D0h+var_B0], rax
0x18000c784  lea     r9d, [rdi+1]
0x18000c788  lea     rdx, UserMigrationTaskStarted
0x18000c78f  lea     rcx, MDM_ENTERPRISE_DIAGNOSTICS_Context
0x18000c796  call    McGenEventWrite_EventWriteTransfer
0x18000c79b  mov     eax, cs:dword_18002B0C0
0x18000c7a1  mov     rbx, 400000000000h
0x18000c7ab  lea     r12, aOnecoreuapAdmi_4; "onecoreuap\\admin\\enterprisemgmt\\migr"...
0x18000c7b2  lea     r13, aBluemigrationM; "BlueMigration::MigrateToCurrentFromWinB"...
0x18000c7b9  cmp     eax, 5
0x18000c7bc  jbe     short loc_18000C826
0x18000c7be  mov     rcx, cs:qword_18002B0D8
0x18000c7c5  mov     rax, cs:qword_18002B0D0
0x18000c7cc  test    rbx, rax
0x18000c7cf  jz      short loc_18000C826
0x18000c7d1  mov     rax, rcx
0x18000c7d4  and     rax, rbx
0x18000c7d7  cmp     rax, rcx
0x18000c7da  jnz     short loc_18000C826
0x18000c7dc  lea     rax, aStarted; "Started"
0x18000c7e3  mov     [rbp+57h+var_78], rax
0x18000c7e7  mov     [rbp+57h+var_70], r12
0x18000c7eb  mov     dword ptr [rbp+57h+var_90], 10h
0x18000c7f2  mov     qword ptr [rbp+57h+var_50], r13
0x18000c7f6  lea     rax, [rbp+57h+var_78]
0x18000c7fa  mov     [rsp+0D0h+var_98], rax
0x18000c7ff  lea     rax, [rbp+57h+var_70]
0x18000c803  mov     [rsp+0D0h+var_A0], rax
0x18000c808  lea     rax, [rbp+57h+var_90]
0x18000c80c  mov     [rsp+0D0h+var_A8], rax
0x18000c811  lea     rax, [rbp+57h+var_50]
0x18000c815  mov     qword ptr [rsp+0D0h+var_B0], rax; unsigned int
0x18000c81a  lea     rdx, word_1800258B6
0x18000c821  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x18000c826  mov     dword ptr [rbp+57h+var_90], edi
0x18000c829  mov     rax, [rbp+57h+var_80]
0x18000c82d  mov     rcx, [rax+18h]
0x18000c831  test    rcx, rcx
0x18000c834  jz      short loc_18000C838
0x18000c836  mov     [rcx], edi
0x18000c838  lea     r8, [rbp+57h+var_90]; unsigned __int8 *
0x18000c83c  lea     rdx, aMigrationAttem; "Migration Attempted B2T"
0x18000c843  lea     rcx, aSoftwareMicros_6; "SOFTWARE\\Microsoft\\Enrollment"
0x18000c84a  call    ?Write@RegistryHelper@@SAXPEBG0PEBEKK@Z; RegistryHelper::Write(ushort const *,ushort const *,uchar const *,ulong,ulong)
0x18000c84f  mov     rcx, [rbp+57h+var_80]; this
0x18000c853  call    ?GenerateRuntimeVariables@Migrator@blue2th@@QEAAXXZ; blue2th::Migrator::GenerateRuntimeVariables(void)
0x18000c858  mov     dword ptr [rbp+57h+var_90], 2
0x18000c85f  mov     rax, [rbp+57h+var_80]
0x18000c863  mov     rcx, [rax+18h]
0x18000c867  test    rcx, rcx
0x18000c86a  jz      short loc_18000C872
0x18000c86c  mov     dword ptr [rcx], 2
0x18000c872  lea     r8, [rbp+57h+var_90]; unsigned __int8 *
0x18000c876  lea     rdx, aMigrationAttem; "Migration Attempted B2T"
0x18000c87d  lea     rcx, aSoftwareMicros_6; "SOFTWARE\\Microsoft\\Enrollment"
0x18000c884  call    ?Write@RegistryHelper@@SAXPEBG0PEBEKK@Z; RegistryHelper::Write(ushort const *,ushort const *,uchar const *,ulong,ulong)
0x18000c889  lea     rax, [rbp+57h+var_88]
0x18000c88d  mov     qword ptr [rbp+57h+var_50], rax
0x18000c891  lea     rax, [rbp+57h+var_80]
0x18000c895  mov     [rbp+57h+var_48], rax
0x18000c899  lea     rcx, [rbp+57h+var_50]
0x18000c89d  call    wil__ResultFromException__lambda_3e99124a2e5926726931da8d3774c6b3___
0x18000c8a2  mov     r8d, eax
0x18000c8a5  mov     edx, 4
0x18000c8aa  mov     rcx, [rbp+57h+var_80]
0x18000c8ae  call    ?LogResult@Migrator@blue2th@@QEAAXW4Step@12@J@Z; blue2th::Migrator::LogResult(blue2th::Migrator::Step,long)
0x18000c8b3  lea     rax, [rbp+57h+var_88]
0x18000c8b7  mov     qword ptr [rbp+57h+var_50], rax
0x18000c8bb  lea     rax, [rbp+57h+var_80]
0x18000c8bf  mov     [rbp+57h+var_48], rax
0x18000c8c3  lea     rcx, [rbp+57h+var_50]
0x18000c8c7  call    wil__ResultFromException__lambda_e38df7dad9b1c1b37a5409cde95813d1___
0x18000c8cc  mov     r8d, eax
0x18000c8cf  mov     edx, 5
0x18000c8d4  mov     rcx, [rbp+57h+var_80]
0x18000c8d8  call    ?LogResult@Migrator@blue2th@@QEAAXW4Step@12@J@Z; blue2th::Migrator::LogResult(blue2th::Migrator::Step,long)
0x18000c8dd  mov     dword ptr [rbp+57h+var_90], 7
0x18000c8e4  mov     rax, [rbp+57h+var_80]
0x18000c8e8  mov     r8, [rax+18h]
0x18000c8ec  test    r8, r8
0x18000c8ef  jz      short loc_18000C8F8
0x18000c8f1  mov     dword ptr [r8], 7
0x18000c8f8  lea     r8, [rbp+57h+var_90]; unsigned __int8 *
0x18000c8fc  lea     rdx, aMigrationAttem; "Migration Attempted B2T"
0x18000c903  lea     rcx, aSoftwareMicros_6; "SOFTWARE\\Microsoft\\Enrollment"
0x18000c90a  call    ?Write@RegistryHelper@@SAXPEBG0PEBEKK@Z; RegistryHelper::Write(ushort const *,ushort const *,uchar const *,ulong,ulong)
0x18000c90f  mov     eax, cs:dword_18002B0C0
0x18000c915  cmp     eax, 5
0x18000c918  jbe     short loc_18000C982
0x18000c91a  mov     rcx, cs:qword_18002B0D8
0x18000c921  mov     rax, cs:qword_18002B0D0
0x18000c928  test    rbx, rax
0x18000c92b  jz      short loc_18000C982
0x18000c92d  mov     rax, rcx
0x18000c930  and     rax, rbx
0x18000c933  cmp     rax, rcx
0x18000c936  jnz     short loc_18000C982
0x18000c938  lea     rax, aSuccess; "Success"
0x18000c93f  mov     qword ptr [rbp+57h+var_50], rax
0x18000c943  mov     [rbp+57h+var_70], r12
0x18000c947  mov     dword ptr [rbp+57h+var_90], 26h ; '&'
0x18000c94e  mov     [rbp+57h+var_78], r13
0x18000c952  lea     rax, [rbp+57h+var_50]
0x18000c956  mov     [rsp+0D0h+var_98], rax
0x18000c95b  lea     rax, [rbp+57h+var_70]
0x18000c95f  mov     [rsp+0D0h+var_A0], rax
0x18000c964  lea     rax, [rbp+57h+var_90]
0x18000c968  mov     [rsp+0D0h+var_A8], rax
0x18000c96d  lea     rax, [rbp+57h+var_78]
0x18000c971  mov     qword ptr [rsp+0D0h+var_B0], rax
0x18000c976  lea     rdx, qword_180025878
0x18000c97d  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x18000c982  lea     rax, aCWindowsSystem; "C:\\Windows\\System32\\MDMAgent.exe"
0x18000c989  mov     [rbp+57h+var_68], rax
0x18000c98d  xorps   xmm0, xmm0
0x18000c990  movdqu  [rbp+57h+var_60], xmm0
0x18000c995  mov     ecx, 60h ; '`'; Size
0x18000c99a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000c99f  mov     [rax], rax
0x18000c9a2  mov     [rax+8], rax
0x18000c9a6  mov     [rax+10h], rax
0x18000c9aa  mov     word ptr [rax+18h], 101h
0x18000c9b0  mov     qword ptr [rbp+57h+var_60], rax
0x18000c9b4  mov     rbx, [rbp+57h+var_80]
0x18000c9b8  mov     rdx, cs:?userSidRtv@@3PEBGEB; ushort const * const userSidRtv
0x18000c9bf  xorps   xmm0, xmm0
0x18000c9c2  movups  [rbp+57h+var_40], xmm0
0x18000c9c6  xorps   xmm1, xmm1
0x18000c9c9  movdqu  [rbp+57h+var_30], xmm1
0x18000c9ce  or      r8, 0FFFFFFFFFFFFFFFFh
0x18000c9d2  inc     r8
0x18000c9d5  cmp     [rdx+r8*2], di
0x18000c9da  jnz     short loc_18000C9D2
0x18000c9dc  lea     rcx, [rbp+57h+var_40]
0x18000c9e0  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18000c9e5  nop
0x18000c9e6  lea     rdx, [rbp+57h+var_40]
0x18000c9ea  mov     rcx, rbx
0x18000c9ed  call    ??A?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@QEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAV21@@Z; std::map<std::wstring,std::wstring>::operator[](std::wstring &&)
0x18000c9f2  cmp     qword ptr [rax+18h], 7
0x18000c9f7  jbe     short loc_18000C9FC
0x18000c9f9  mov     rax, [rax]
0x18000c9fc  mov     rdx, rax; unsigned __int16 *
0x18000c9ff  call    ?DeleteSchedule@ScheduleMigrator@@QEAAJPEBG@Z; ScheduleMigrator::DeleteSchedule(ushort const *)
0x18000ca04  mov     [rbp+57h+var_88], eax
0x18000ca07  lea     rcx, [rbp+57h+var_40]; void *
0x18000ca0b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000ca10  nop
0x18000ca11  lea     rcx, [rbp+57h+var_60]
0x18000ca15  call    ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(void)
0x18000ca1a  test    cs:Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits, 10h
0x18000ca21  jz      short loc_18000CA5B
0x18000ca23  mov     eax, [rbp+57h+var_88]
0x18000ca26  mov     dword ptr [rbp+57h+var_90], eax
0x18000ca29  lea     rax, [rbp+57h+var_90]
0x18000ca2d  mov     qword ptr [rbp+57h+var_30], rax
0x18000ca31  mov     qword ptr [rbp+57h+var_30+8], 4
0x18000ca39  lea     rax, [rbp+57h+var_40]
0x18000ca3d  mov     qword ptr [rsp+0D0h+var_B0], rax
0x18000ca42  mov     r9d, 2
0x18000ca48  lea     rdx, UserMigrationTaskDeleted
0x18000ca4f  lea     rcx, MDM_ENTERPRISE_DIAGNOSTICS_Context
0x18000ca56  call    McGenEventWrite_EventWriteTransfer
0x18000ca5b  mov     rcx, [rbp+57h+var_20]
0x18000ca5f  xor     rcx, rsp; StackCookie
0x18000ca62  call    __security_check_cookie
0x18000ca67  lea     r11, [rsp+0D0h+var_10]
0x18000ca6f  mov     rbx, [r11+28h]
0x18000ca73  mov     rdi, [r11+30h]
0x18000ca77  mov     rsp, r11
0x18000ca7a  pop     r13
0x18000ca7c  pop     r12
0x18000ca7e  pop     rbp
0x18000ca7f  retn
```
