# CPreferredKeys::CPreferredKey::CreateAndSave(void)

- ea: `0x180030f00`
- end: `0x1800310d7`
- name: `?CreateAndSave@CPreferredKey@CPreferredKeys@@QEAAJXZ`
- size: `471`
- prototype: `DWORD __fastcall(CPreferredKeys::CPreferredKey *this)`
- caller_count: `2`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x180033090`
- `0x180035320`

## callees

- `0x18000128c`
- `0x180007f10`
- `0x180007f60`
- `0x18001467c`
- `0x18002f914`
- `0x180030414`
- `0x180030f00`
- `0x1800310e0`
- `0x180031674`
- `0x180032898`
- `0x1800367a4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030fa2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030fd2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030fe2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030ff3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030fa2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030fd2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030fe2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030ff3`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaStorePrivateData` at `0x180031065`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaStorePrivateData` at `0x180031065`

## string_xrefs

- `0x1800310aa`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keysrv.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
DWORD __fastcall CPreferredKeys::CPreferredKey::CreateAndSave(CPreferredKeys::CPreferredKey *this)
{
  int v2; // edi
  unsigned int *v3; // r8
  unsigned __int8 **v4; // rdx
  WCHAR *v5; // rsi
  struct _GUID *v6; // rcx
  int BackupKeyW2K; // eax
  int v8; // ebx
  __int64 v9; // r9
  DWORD LastError; // eax
  const wchar_t *v11; // r8
  unsigned __int16 *v13; // rdx
  unsigned __int16 *v14; // rcx
  __int64 v15; // rcx
  NTSTATUS v16; // ebx
  const wchar_t *v17; // r8
  struct _LSA_UNICODE_STRING PrivateData; // [rsp+30h] [rbp-20h] BYREF
  struct _LSA_UNICODE_STRING KeyName; // [rsp+40h] [rbp-10h] BYREF
  int v20; // [rsp+80h] [rbp+30h] BYREF
  BOOL v21; // [rsp+88h] [rbp+38h] BYREF
  LSA_HANDLE PolicyHandle; // [rsp+90h] [rbp+40h] BYREF

  CPreferredKeys::CPreferredKey::Clean(this);
  v2 = *(_DWORD *)this;
  v3 = (unsigned int *)((char *)this + 32);
  v4 = (unsigned __int8 **)((char *)this + 24);
  v5 = (WCHAR *)((char *)this + 4);
  v6 = (struct _GUID *)((char *)this + 4);
  if ( *(_DWORD *)this == 1 )
    BackupKeyW2K = CreateBackupKeyW2K(v6, v4, v3);
  else
    BackupKeyW2K = CreateBackupKey(v6, v4, v3);
  v8 = BackupKeyW2K;
  if ( (unsigned int)dword_18004C260 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18004C260, 0x200000000000LL) )
  {
    v20 = v8;
    v21 = v2 == 1;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      (int)&dword_18004C260,
      (int)byte_180045101,
      0,
      v9,
      (__int64)&v21,
      (__int64)&v20);
  }
  if ( v8 )
  {
    KeyName = 0;
    v13 = L"G$BCKUPKEY_P";
    if ( v2 != 1 )
      v13 = L"G$BCKUPKEY_PREFERRED";
    InitLsaString((struct _UNICODE_STRING *)&KeyName, v13);
    *(_QWORD *)&PrivateData.Length = 1048592;
    PrivateData.Buffer = v5;
    PolicyHandle = 0;
    v16 = OpenPolicy(v14, 0x20u, &PolicyHandle);
    if ( v16 < 0 || (v16 = LsaStorePrivateData(PolicyHandle, &KeyName, &PrivateData), v16 < 0) )
    {
      if ( (Microsoft_Windows_Crypto_DPAPIEnableBits & 2) != 0 )
      {
        v17 = L"Setting legacy preferred backup key GUID failed.";
        if ( v2 != 1 )
          v17 = L"Setting preferred backup key GUID failed.";
        McTemplateU0zd_EtwEventWriteTransfer(v15, ETW_LOG_BACKUPKEYSVC_SETUP_FAILED, v17, (unsigned int)v16);
      }
      DebugTraceError(
        (unsigned int)v16,
        "status",
        "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keysrv.cpp",
        3795);
    }
    wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long LsaClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long LsaClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&PolicyHandle);
    return v16;
  }
  else
  {
    if ( (Microsoft_Windows_Crypto_DPAPIEnableBits & 2) != 0 )
    {
      LastError = GetLastError();
      v11 = L"Creating legacy backup key failed.";
      if ( v2 != 1 )
        v11 = L"Creating backup key failed.";
      McTemplateU0zd_EtwEventWriteTransfer(
        L"Creating backup key failed.",
        ETW_LOG_BACKUPKEYSVC_SETUP_FAILED,
        v11,
        LastError);
    }
    if ( (int)GetLastError() > 0 )
      return (unsigned __int16)GetLastError() | 0xC0070000;
    else
      return GetLastError();
  }
}

```

## disassembly

```asm
0x180030f00  push    rbp
0x180030f02  push    rbx
0x180030f03  push    rsi
0x180030f04  push    rdi
0x180030f05  push    r14
0x180030f07  mov     rbp, rsp
0x180030f0a  sub     rsp, 50h
0x180030f0e  mov     rbx, rcx
0x180030f11  call    ?Clean@CPreferredKey@CPreferredKeys@@AEAAXXZ; CPreferredKeys::CPreferredKey::Clean(void)
0x180030f16  mov     edi, [rbx]
0x180030f18  xor     r14d, r14d
0x180030f1b  cmp     edi, 1
0x180030f1e  setz    r14b
0x180030f22  lea     r8, [rbx+20h]; unsigned int *
0x180030f26  lea     rdx, [rbx+18h]; unsigned __int8 **
0x180030f2a  lea     rsi, [rbx+4]
0x180030f2e  mov     rcx, rsi; struct _GUID *
0x180030f31  jnz     short loc_180030F3A
0x180030f33  call    ?CreateBackupKeyW2K@@YAHPEAU_GUID@@PEAPEAEPEAK@Z; CreateBackupKeyW2K(_GUID *,uchar * *,ulong *)
0x180030f38  jmp     short loc_180030F3F
0x180030f3a  call    ?CreateBackupKey@@YAHPEAU_GUID@@PEAPEAEPEAK@Z; CreateBackupKey(_GUID *,uchar * *,ulong *)
0x180030f3f  mov     ebx, eax
0x180030f41  mov     eax, cs:dword_18004C260
0x180030f47  cmp     eax, 5
0x180030f4a  jbe     short loc_180030F95
0x180030f4c  mov     rdx, 200000000000h
0x180030f56  lea     rcx, dword_18004C260
0x180030f5d  call    _tlgKeywordOn
0x180030f62  test    al, al
0x180030f64  jz      short loc_180030F95
0x180030f66  mov     [rbp+arg_0], ebx
0x180030f69  mov     [rbp+arg_8], r14d
0x180030f6d  lea     rax, [rbp+arg_0]
0x180030f71  mov     [rsp+50h+var_28], rax
0x180030f76  lea     rax, [rbp+arg_8]
0x180030f7a  mov     [rsp+50h+var_30], rax
0x180030f7f  xor     r8d, r8d
0x180030f82  lea     rdx, byte_180045101
0x180030f89  lea     rcx, dword_18004C260
0x180030f90  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180030f95  test    ebx, ebx
0x180030f97  jnz     short loc_18003100C
0x180030f99  test    cs:Microsoft_Windows_Crypto_DPAPIEnableBits, 2
0x180030fa0  jz      short loc_180030FD2
0x180030fa2  call    cs:__imp_GetLastError
0x180030fa9  nop     dword ptr [rax+rax+00h]
0x180030fae  lea     rcx, aCreatingBackup; "Creating backup key failed."
0x180030fb5  lea     r8, aCreatingLegacy; "Creating legacy backup key failed."
0x180030fbc  cmp     edi, 1
0x180030fbf  cmovnz  r8, rcx
0x180030fc3  mov     r9d, eax
0x180030fc6  lea     rdx, ETW_LOG_BACKUPKEYSVC_SETUP_FAILED
0x180030fcd  call    McTemplateU0zd_EtwEventWriteTransfer
0x180030fd2  call    cs:__imp_GetLastError
0x180030fd9  nop     dword ptr [rax+rax+00h]
0x180030fde  test    eax, eax
0x180030fe0  jg      short loc_180030FF3
0x180030fe2  call    cs:__imp_GetLastError
0x180030fe9  nop     dword ptr [rax+rax+00h]
0x180030fee  jmp     loc_1800310CB
0x180030ff3  call    cs:__imp_GetLastError
0x180030ffa  nop     dword ptr [rax+rax+00h]
0x180030fff  movzx   eax, ax
0x180031002  or      eax, 0C0070000h
0x180031007  jmp     loc_1800310CB
0x18003100c  xorps   xmm0, xmm0
0x18003100f  movups  xmmword ptr [rbp+KeyName.Length], xmm0
0x180031013  lea     rax, aGBckupkeyPrefe; "G$BCKUPKEY_PREFERRED"
0x18003101a  lea     rdx, aGBckupkeyP; "G$BCKUPKEY_P"
0x180031021  cmp     edi, 1
0x180031024  cmovnz  rdx, rax; unsigned __int16 *
0x180031028  lea     rcx, [rbp+KeyName]; struct _UNICODE_STRING *
0x18003102c  call    ?InitLsaString@@YAXPEAU_UNICODE_STRING@@PEAG@Z; InitLsaString(_UNICODE_STRING *,ushort *)
0x180031031  mov     qword ptr [rbp+PrivateData.Length], 100010h
0x180031039  mov     [rbp+PrivateData.Buffer], rsi
0x18003103d  mov     [rbp+PolicyHandle], 0
0x180031045  lea     r8, [rbp+PolicyHandle]; void **
0x180031049  mov     edx, 20h ; ' '; unsigned int
0x18003104e  call    ?OpenPolicy@@YAJPEAGKPEAPEAX@Z; OpenPolicy(ushort *,ulong,void * *)
0x180031053  mov     ebx, eax
0x180031055  test    eax, eax
0x180031057  js      short loc_180031077
0x180031059  lea     r8, [rbp+PrivateData]; PrivateData
0x18003105d  lea     rdx, [rbp+KeyName]; KeyName
0x180031061  mov     rcx, [rbp+PolicyHandle]; PolicyHandle
0x180031065  call    cs:__imp_LsaStorePrivateData
0x18003106c  nop     dword ptr [rax+rax+00h]
0x180031071  mov     ebx, eax
0x180031073  test    eax, eax
0x180031075  jns     short loc_1800310C0
0x180031077  test    cs:Microsoft_Windows_Crypto_DPAPIEnableBits, 2
0x18003107e  jz      short loc_1800310A4
0x180031080  lea     rax, aSettingPreferr; "Setting preferred backup key GUID faile"...
0x180031087  lea     r8, aSettingLegacyP; "Setting legacy preferred backup key GUI"...
0x18003108e  cmp     edi, 1
0x180031091  cmovnz  r8, rax
0x180031095  mov     r9d, ebx
0x180031098  lea     rdx, ETW_LOG_BACKUPKEYSVC_SETUP_FAILED
0x18003109f  call    McTemplateU0zd_EtwEventWriteTransfer
0x1800310a4  mov     r9d, 0ED3h
0x1800310aa  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\secst"...
0x1800310b1  lea     rdx, aStatus_0; "status"
0x1800310b8  mov     ecx, ebx
0x1800310ba  call    DebugTraceError
0x1800310bf  nop
0x1800310c0  lea     rcx, [rbp+PolicyHandle]
0x1800310c4  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?LsaClose@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&LsaClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&LsaClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800310c9  mov     eax, ebx
0x1800310cb  add     rsp, 50h
0x1800310cf  pop     r14
0x1800310d1  pop     rdi
0x1800310d2  pop     rsi
0x1800310d3  pop     rbx
0x1800310d4  pop     rbp
0x1800310d5  retn
```
