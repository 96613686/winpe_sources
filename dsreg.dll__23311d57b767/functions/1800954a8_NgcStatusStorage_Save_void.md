# NgcStatusStorage::Save(void)

- ea: `0x1800954a8`
- end: `0x180095a9d`
- name: `?Save@NgcStatusStorage@@QEAAJXZ`
- size: `1525`
- prototype: `__int64 __fastcall(NgcStatusStorage *__hidden this)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800952b4`

## callees

- `0x1800084f4`
- `0x180008530`
- `0x180012948`
- `0x18001c74c`
- `0x18004255c`
- `0x180043e54`
- `0x18008bb70`
- `0x18008c2d4`
- `0x18008c3f8`
- `0x18008dc44`
- `0x1800913c8`
- `0x1800954a8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18009552a`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800955de`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18009552a`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800955de`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180095a3e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180095a55`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180095a6c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180095a3e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180095a55`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180095a6c`
- `RPCRT4!RpcStringFreeW` at `0x180095585`
- `RPCRT4!RpcStringFreeW` at `0x180095a85`
- `RPCRT4!RpcStringFreeW` at `0x180095585`
- `RPCRT4!RpcStringFreeW` at `0x180095a85`
- `RPCRT4!UuidToStringW` at `0x1800955a0`
- `RPCRT4!UuidToStringW` at `0x180095901`
- `RPCRT4!UuidToStringW` at `0x1800955a0`
- `RPCRT4!UuidToStringW` at `0x180095901`

## string_xrefs

- `0x180095783`: `EventWriteNgcSaveStatusSuccessEvent`
- `0x18009578a`: `Logger::WriteNgcSaveStatusSuccessEvent`
- `0x1800959ac`: `Logger::WriteNgcSaveStatusFailureEvent`
- `0x1800959a5`: `EventWriteNgcSaveStatusFailureEvent`
- `0x1800954ea`: `OpenRootKey`
- `0x18009553f`: `RegCreateKeyExW`
- `0x180095836`: `RegCreateKeyExW`
- `0x180095555`: `%s: Failed to create or open registry key "%s". Error code: 0x%08x.`
- `0x1800957ed`: `%s: Successfully saved NGC key status to the registry "%s\%s".\nKeyId = "%s", AttestationLevel = %lu, AikStatus = %lu, KeyType = %lu, KeyName = "%s", IdpDomain = "%s", TenantId = "%s", UserEmail = "%s".`
- `0x180095856`: `%s: Failed to create or open registry key "%s\%s". Error code: 0x%08x.`
- `0x180095a29`: `%s: Failed to save NGC key status to the registry. Error = 0x%08x, KeyId = "%s", AttestationLevel = %lu, AikStatus = %lu, KeyType = %lu, KeyName = "%s", IdpDomain = "%s", TenantId = "%s", UserEmail = "%s".`

## pseudocode

```c
__int64 __fastcall NgcStatusStorage::Save(NgcStatusStorage *this)
{
  unsigned __int64 v2; // rsi
  unsigned int v3; // eax
  LSTATUS v4; // ebx
  const wchar_t *v5; // r8
  LSTATUS v6; // eax
  __int64 v7; // r14
  unsigned int v8; // eax
  int v9; // r12d
  unsigned int v10; // eax
  unsigned int v11; // r14d
  unsigned int v12; // eax
  __int64 v13; // rsi
  int v14; // ecx
  int v15; // edx
  int v16; // r8d
  __int64 v17; // r9
  __int64 v18; // r10
  __int64 v19; // r11
  __int64 v20; // rbx
  unsigned int v21; // eax
  DWORD v22; // ecx
  REGSAM v23; // edx
  int v24; // r8d
  __int64 v25; // r9
  __int64 v26; // r10
  __int64 v27; // r11
  __int64 v28; // rax
  DWORD dwOptions[2]; // [rsp+20h] [rbp-50h]
  DWORD dwOptionsa[2]; // [rsp+20h] [rbp-50h]
  REGSAM samDesired[2]; // [rsp+28h] [rbp-48h]
  LPSECURITY_ATTRIBUTES lpSecurityAttributes; // [rsp+30h] [rbp-40h]
  HKEY hKey; // [rsp+60h] [rbp-10h] BYREF
  RPC_WSTR String; // [rsp+B8h] [rbp+48h] BYREF
  HKEY v36; // [rsp+C0h] [rbp+50h] BYREF
  HKEY phkResult; // [rsp+C8h] [rbp+58h] BYREF

  v36 = 0;
  phkResult = 0;
  hKey = 0;
  String = 0;
  v2 = 0;
  v3 = RegOpenCurrentUserKey(0x20006u, &hKey);
  v4 = v3;
  if ( v3 )
  {
    v5 = L"OpenRootKey";
  }
  else
  {
    v6 = RegCreateKeyExW(
           hKey,
           L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\WorkplaceJoin\\AADNGC",
           0,
           0,
           0,
           0x20006u,
           0,
           &phkResult,
           0);
    v4 = v6;
    if ( v6 )
    {
      Logger::WriteRegistryFailureEvent(
        v6,
        L"RegCreateKeyExW",
        L"HKEY_CURRENT_USER\\SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\WorkplaceJoin\\AADNGC");
      Logger::TraceError(
        L"%s: Failed to create or open registry key \"%s\". Error code: 0x%08x.",
        L"NgcStatusStorage::Save",
        L"HKEY_CURRENT_USER\\SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\WorkplaceJoin\\AADNGC",
        (unsigned int)v4);
      goto LABEL_28;
    }
    while ( v2 < *((_QWORD *)this + 1) )
    {
      if ( String )
      {
        RpcStringFreeW(&String);
        String = 0;
      }
      v7 = v2 << 6;
      v8 = UuidToStringW((const UUID *)((v2 << 6) + *(_QWORD *)this), &String);
      v9 = v8;
      if ( v8 )
      {
        Logger::TraceError(
          L"%s: Cannot convert the NGC key ID to a GUID string. Error code: 0x%08x.",
          L"NgcStatusStorage::Save",
          v8);
        if ( v9 > 0 )
          v11 = (unsigned __int16)v9 | 0x80070000;
        else
          v11 = v9;
        goto LABEL_34;
      }
      v4 = RegCreateKeyExW(phkResult, String, 0, 0, 0, 0x20006u, 0, &v36, 0);
      if ( v4 )
      {
        Logger::WriteRegistryFailureEventEx(
          v4,
          L"RegCreateKeyExW",
          L"%s\\%s",
          L"HKEY_CURRENT_USER\\SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\WorkplaceJoin\\AADNGC",
          String);
        dwOptionsa[0] = v4;
        Logger::TraceError(
          L"%s: Failed to create or open registry key \"%s\\%s\". Error code: 0x%08x.",
          L"NgcStatusStorage::Save",
          L"HKEY_CURRENT_USER\\SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\WorkplaceJoin\\AADNGC",
          String,
          *(_QWORD *)dwOptionsa);
        goto LABEL_28;
      }
      v3 = RegSaveDwordValue(v36, 0, L"AttestationLevel", String, *(_DWORD *)(v7 + *(_QWORD *)this + 24));
      v4 = v3;
      if ( v3
        || (v3 = RegSaveDwordValue(v36, 0, L"AikCertStatus", String, *(_DWORD *)(v7 + *(_QWORD *)this + 28)),
            (v4 = v3) != 0)
        || (v3 = RegSaveDwordValue(v36, 0, L"NgcKeyStatus", String, *(_DWORD *)(v7 + *(_QWORD *)this + 32)),
            (v4 = v3) != 0) )
      {
        v5 = L"RegSaveDwordValue";
        goto LABEL_27;
      }
      v3 = RegSaveStringValue(v36, 0, L"NgcKeyName", String, *(wchar_t **)(v7 + *(_QWORD *)this + 16));
      v4 = v3;
      if ( v3
        || (v3 = RegSaveStringValue(v36, 0, L"IdpDomain", String, *(wchar_t **)(v7 + *(_QWORD *)this + 40)),
            (v4 = v3) != 0)
        || (v3 = RegSaveStringValue(v36, 0, L"TenantDomain", String, *(wchar_t **)(v7 + *(_QWORD *)this + 48)),
            (v4 = v3) != 0)
        || (v3 = RegSaveStringValue(v36, 0, L"UserId", String, *(wchar_t **)(v7 + *(_QWORD *)this + 56)), (v4 = v3) != 0) )
      {
        v5 = L"RegSaveStringValue";
        goto LABEL_27;
      }
      if ( (Microsoft_Windows_User_Device_RegistrationEnableBits & 1) != 0 )
      {
        v10 = McTemplateU0zxxxzzzz_EventWriteTransfer(
                *(_DWORD *)(v7 + *(_QWORD *)this + 32),
                *(_DWORD *)(v7 + *(_QWORD *)this + 28),
                (_DWORD)String,
                *(_DWORD *)(v7 + *(_QWORD *)this + 24),
                *(_DWORD *)(v7 + *(_QWORD *)this + 28),
                *(_DWORD *)(v7 + *(_QWORD *)this + 32),
                *(_QWORD *)(v7 + *(_QWORD *)this + 16),
                *(_QWORD *)(v7 + *(_QWORD *)this + 40),
                *(_QWORD *)(v7 + *(_QWORD *)this + 48),
                *(_QWORD *)(v7 + *(_QWORD *)this + 56));
        if ( v10 )
          Logger::TraceError(
            L"%s: %s failed with win32 error code: 0x%08x.",
            L"Logger::WriteNgcSaveStatusSuccessEvent",
            L"EventWriteNgcSaveStatusSuccessEvent",
            v10);
      }
      dwOptions[1] = HIDWORD(String);
      Logger::TraceInformation(
        L"%s: Successfully saved NGC key status to the registry \"%s\\%s\".\n"
         "KeyId = \"%s\", AttestationLevel = %lu, AikStatus = %lu, KeyType = %lu, KeyName = \"%s\", IdpDomain = \"%s\", T"
         "enantId = \"%s\", UserEmail = \"%s\".",
        L"NgcStatusStorage::Save",
        L"HKEY_CURRENT_USER\\SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\WorkplaceJoin\\AADNGC");
      ++v2;
    }
    v11 = 0;
    v3 = RegFlush(
           phkResult,
           L"HKEY_CURRENT_USER\\SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\WorkplaceJoin\\AADNGC");
    v4 = v3;
    if ( !v3 )
      goto LABEL_48;
    v5 = L"RegFlush";
  }
LABEL_27:
  Logger::TraceError(L"%s: %s failed with win32 error code: 0x%08x.", L"NgcStatusStorage::Save", v5, v3);
LABEL_28:
  if ( v4 > 0 )
    v11 = (unsigned __int16)v4 | 0x80070000;
  else
    v11 = v4;
LABEL_34:
  if ( (v11 & 0x80000000) != 0 )
  {
    if ( !String )
    {
      if ( !*((_QWORD *)this + 1) )
        goto LABEL_40;
      v12 = UuidToStringW((const UUID *)(*(_QWORD *)this + (v2 << 6)), &String);
      Logger::TraceWarning(
        (wchar_t *)L"%s: Cannot conver the NGC key ID a GUID string. Error code: 0x%08x.",
        L"NgcStatusStorage::Save",
        v12);
    }
    if ( *((_QWORD *)this + 1) )
    {
      v13 = v2 << 6;
      v14 = *(_DWORD *)(v13 + *(_QWORD *)this + 24);
      v15 = *(_DWORD *)(v13 + *(_QWORD *)this + 28);
      v16 = *(_DWORD *)(v13 + *(_QWORD *)this + 32);
      v17 = *(_QWORD *)(v13 + *(_QWORD *)this + 16);
      v18 = *(_QWORD *)(v13 + *(_QWORD *)this + 40);
      v19 = *(_QWORD *)(v13 + *(_QWORD *)this + 48);
      v20 = *(_QWORD *)(v13 + *(_QWORD *)this + 56);
      goto LABEL_41;
    }
LABEL_40:
    v14 = 0;
    v15 = 0;
    LOBYTE(v16) = 0;
    v17 = 0;
    v18 = 0;
    v19 = 0;
    v20 = 0;
    v13 = v2 << 6;
LABEL_41:
    if ( (Microsoft_Windows_User_Device_RegistrationEnableBits & 2) != 0 )
    {
      v21 = McTemplateU0dzxxxzzzz_EventWriteTransfer(v14, v15, v11, (_DWORD)String, v14, v15, v16, v17, v18, v19, v20);
      if ( v21 )
        Logger::TraceError(
          L"%s: %s failed with win32 error code: 0x%08x.",
          L"Logger::WriteNgcSaveStatusFailureEvent",
          L"EventWriteNgcSaveStatusFailureEvent",
          v21);
    }
    if ( *((_QWORD *)this + 1) )
    {
      v22 = *(_DWORD *)(v13 + *(_QWORD *)this + 24);
      v23 = *(_DWORD *)(v13 + *(_QWORD *)this + 28);
      v24 = *(_DWORD *)(v13 + *(_QWORD *)this + 32);
      v25 = *(_QWORD *)(v13 + *(_QWORD *)this + 16);
      v26 = *(_QWORD *)(v13 + *(_QWORD *)this + 40);
      v27 = *(_QWORD *)(v13 + *(_QWORD *)this + 48);
      v28 = *(_QWORD *)(v13 + *(_QWORD *)this + 56);
    }
    else
    {
      v22 = 0;
      v23 = 0;
      v24 = 0;
      v25 = 0;
      v26 = 0;
      v27 = 0;
      v28 = 0;
    }
    LODWORD(lpSecurityAttributes) = v24;
    samDesired[0] = v23;
    dwOptions[0] = v22;
    Logger::TraceError(
      L"%s: Failed to save NGC key status to the registry. Error = 0x%08x, KeyId = \"%s\", AttestationLevel = %lu, AikStat"
       "us = %lu, KeyType = %lu, KeyName = \"%s\", IdpDomain = \"%s\", TenantId = \"%s\", UserEmail = \"%s\".",
      L"NgcStatusStorage::Save",
      v11,
      String,
      *(_QWORD *)dwOptions,
      *(_QWORD *)samDesired,
      lpSecurityAttributes,
      v25,
      v26,
      v27,
      v28);
  }
LABEL_48:
  if ( v36 )
  {
    RegCloseKey(v36);
    v36 = 0;
  }
  if ( phkResult )
  {
    RegCloseKey(phkResult);
    phkResult = 0;
  }
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  if ( String )
    RpcStringFreeW(&String);
  return v11;
}

```

## disassembly

```asm
0x1800954a8  push    rbp
0x1800954aa  push    rbx
0x1800954ab  push    rsi
0x1800954ac  push    rdi
0x1800954ad  push    r12
0x1800954af  push    r14
0x1800954b1  push    r15
0x1800954b3  mov     rbp, rsp
0x1800954b6  sub     rsp, 70h
0x1800954ba  xor     r12d, r12d
0x1800954bd  lea     rdx, [rbp+hKey]; HKEY *
0x1800954c1  mov     rdi, rcx
0x1800954c4  mov     [rbp+arg_10], r12
0x1800954c8  mov     r14d, 20006h
0x1800954ce  mov     [rbp+arg_18], r12
0x1800954d2  mov     ecx, r14d; unsigned int
0x1800954d5  mov     [rbp+hKey], r12
0x1800954d9  mov     [rbp+String], r12
0x1800954dd  xor     esi, esi
0x1800954df  call    ?RegOpenCurrentUserKey@@YAKKPEAPEAUHKEY__@@@Z; RegOpenCurrentUserKey(ulong,HKEY__ * *)
0x1800954e4  mov     ebx, eax
0x1800954e6  test    eax, eax
0x1800954e8  jz      short loc_1800954FD
0x1800954ea  lea     r8, aOpenrootkey; "OpenRootKey"
0x1800954f1  lea     r15, aNgcstatusstora_9; "NgcStatusStorage::Save"
0x1800954f8  jmp     loc_18009589C
0x1800954fd  mov     rcx, [rbp+hKey]; hKey
0x180095501  lea     rax, [rbp+arg_18]
0x180095505  mov     [rsp+70h+lpdwDisposition], rsi; lpdwDisposition
0x18009550a  lea     rdx, aSoftwareMicros_6; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x180095511  mov     [rsp+70h+phkResult], rax; phkResult
0x180095516  xor     r9d, r9d; lpClass
0x180095519  mov     [rsp+70h+lpSecurityAttributes], rsi; lpSecurityAttributes
0x18009551e  xor     r8d, r8d; Reserved
0x180095521  mov     [rsp+70h+samDesired], r14d; samDesired
0x180095526  mov     [rsp+70h+dwOptions], esi; dwOptions
0x18009552a  call    cs:__imp_RegCreateKeyExW
0x180095530  mov     ebx, eax
0x180095532  test    eax, eax
0x180095534  jz      short loc_180095568
0x180095536  lea     r8, aHkeyCurrentUse_0; "HKEY_CURRENT_USER\\SOFTWARE\\Microsoft"...
0x18009553d  mov     ecx, eax; unsigned int
0x18009553f  lea     rdx, aRegcreatekeyex; "RegCreateKeyExW"
0x180095546  call    ?WriteRegistryFailureEvent@Logger@@SAJKPEBG0@Z; Logger::WriteRegistryFailureEvent(ulong,ushort const *,ushort const *)
0x18009554b  mov     r9d, ebx
0x18009554e  lea     r8, aHkeyCurrentUse_0; "HKEY_CURRENT_USER\\SOFTWARE\\Microsoft"...
0x180095555  lea     rcx, aSFailedToCreat_0; "%s: Failed to create or open registry k"...
0x18009555c  lea     r15, aNgcstatusstora_9; "NgcStatusStorage::Save"
0x180095563  jmp     loc_1800958A6
0x180095568  lea     r15, aNgcstatusstora_9; "NgcStatusStorage::Save"
0x18009556f  cmp     rsi, [rdi+8]
0x180095573  jnb     loc_180095878
0x180095579  xor     ebx, ebx
0x18009557b  cmp     [rbp+String], rbx
0x18009557f  jz      short loc_18009558F
0x180095581  lea     rcx, [rbp+String]; String
0x180095585  call    cs:__imp_RpcStringFreeW
0x18009558b  mov     [rbp+String], rbx
0x18009558f  mov     rcx, [rdi]
0x180095592  lea     rdx, [rbp+String]; StringUuid
0x180095596  mov     r14, rsi
0x180095599  shl     r14, 6
0x18009559d  add     rcx, r14; Uuid
0x1800955a0  call    cs:__imp_UuidToStringW
0x1800955a6  mov     r12d, eax
0x1800955a9  test    eax, eax
0x1800955ab  jnz     loc_180095864
0x1800955b1  mov     rdx, [rbp+String]; lpSubKey
0x1800955b5  lea     rax, [rbp+arg_10]
0x1800955b9  mov     rcx, [rbp+arg_18]; hKey
0x1800955bd  xor     r9d, r9d; lpClass
0x1800955c0  mov     [rsp+70h+lpdwDisposition], rbx; lpdwDisposition
0x1800955c5  xor     r8d, r8d; Reserved
0x1800955c8  mov     [rsp+70h+phkResult], rax; phkResult
0x1800955cd  mov     [rsp+70h+lpSecurityAttributes], rbx; lpSecurityAttributes
0x1800955d2  mov     [rsp+70h+samDesired], 20006h; samDesired
0x1800955da  mov     [rsp+70h+dwOptions], ebx; dwOptions
0x1800955de  call    cs:__imp_RegCreateKeyExW
0x1800955e4  mov     ebx, eax
0x1800955e6  test    eax, eax
0x1800955e8  jnz     loc_18009581F
0x1800955ee  mov     rax, [rdi]
0x1800955f1  lea     r8, Value; "AttestationLevel"
0x1800955f8  mov     r9, [rbp+String]; unsigned __int16 *
0x1800955fc  mov     rcx, [rbp+arg_10]; HKEY
0x180095600  mov     edx, [r14+rax+18h]
0x180095605  mov     [rsp+70h+dwOptions], edx; unsigned int
0x180095609  xor     edx, edx; unsigned __int16 *
0x18009560b  call    ?RegSaveDwordValue@@YAKPEAUHKEY__@@PEBG11K@Z; RegSaveDwordValue(HKEY__ *,ushort const *,ushort const *,ushort const *,ulong)
0x180095610  mov     ebx, eax
0x180095612  test    eax, eax
0x180095614  jnz     loc_180095816
0x18009561a  mov     rax, [rdi]
0x18009561d  lea     r8, aAikcertstatus; "AikCertStatus"
0x180095624  mov     r9, [rbp+String]; unsigned __int16 *
0x180095628  mov     rcx, [rbp+arg_10]; HKEY
0x18009562c  mov     edx, [r14+rax+1Ch]
0x180095631  mov     [rsp+70h+dwOptions], edx; unsigned int
0x180095635  xor     edx, edx; unsigned __int16 *
0x180095637  call    ?RegSaveDwordValue@@YAKPEAUHKEY__@@PEBG11K@Z; RegSaveDwordValue(HKEY__ *,ushort const *,ushort const *,ushort const *,ulong)
0x18009563c  mov     ebx, eax
0x18009563e  test    eax, eax
0x180095640  jnz     loc_180095816
0x180095646  mov     rax, [rdi]
0x180095649  lea     r8, aNgckeystatus; "NgcKeyStatus"
0x180095650  mov     r9, [rbp+String]; unsigned __int16 *
0x180095654  mov     rcx, [rbp+arg_10]; HKEY
0x180095658  mov     edx, [r14+rax+20h]
0x18009565d  mov     [rsp+70h+dwOptions], edx; unsigned int
0x180095661  xor     edx, edx; unsigned __int16 *
0x180095663  call    ?RegSaveDwordValue@@YAKPEAUHKEY__@@PEBG11K@Z; RegSaveDwordValue(HKEY__ *,ushort const *,ushort const *,ushort const *,ulong)
0x180095668  mov     ebx, eax
0x18009566a  test    eax, eax
0x18009566c  jnz     loc_180095816
0x180095672  mov     rax, [rdi]
0x180095675  lea     r8, aNgckeyname; "NgcKeyName"
0x18009567c  mov     r9, [rbp+String]; unsigned __int16 *
0x180095680  mov     rcx, [rbp+arg_10]; hKey
0x180095684  mov     rdx, [r14+rax+10h]
0x180095689  mov     qword ptr [rsp+70h+dwOptions], rdx; Source
0x18009568e  xor     edx, edx; lpSubKey
0x180095690  call    ?RegSaveStringValue@@YAKPEAUHKEY__@@PEBG111@Z; RegSaveStringValue(HKEY__ *,ushort const *,ushort const *,ushort const *,ushort const *)
0x180095695  mov     ebx, eax
0x180095697  test    eax, eax
0x180095699  jnz     loc_18009580A
0x18009569f  mov     rax, [rdi]
0x1800956a2  lea     r8, aIdpdomain; "IdpDomain"
0x1800956a9  mov     r9, [rbp+String]; unsigned __int16 *
0x1800956ad  mov     rcx, [rbp+arg_10]; hKey
0x1800956b1  mov     rdx, [r14+rax+28h]
0x1800956b6  mov     qword ptr [rsp+70h+dwOptions], rdx; Source
0x1800956bb  xor     edx, edx; lpSubKey
0x1800956bd  call    ?RegSaveStringValue@@YAKPEAUHKEY__@@PEBG111@Z; RegSaveStringValue(HKEY__ *,ushort const *,ushort const *,ushort const *,ushort const *)
0x1800956c2  mov     ebx, eax
0x1800956c4  test    eax, eax
0x1800956c6  jnz     loc_18009580A
0x1800956cc  mov     rax, [rdi]
0x1800956cf  lea     r8, aTenantdomain; "TenantDomain"
0x1800956d6  mov     r9, [rbp+String]; unsigned __int16 *
0x1800956da  mov     rcx, [rbp+arg_10]; hKey
0x1800956de  mov     rdx, [r14+rax+30h]
0x1800956e3  mov     qword ptr [rsp+70h+dwOptions], rdx; Source
0x1800956e8  xor     edx, edx; lpSubKey
0x1800956ea  call    ?RegSaveStringValue@@YAKPEAUHKEY__@@PEBG111@Z; RegSaveStringValue(HKEY__ *,ushort const *,ushort const *,ushort const *,ushort const *)
0x1800956ef  mov     ebx, eax
0x1800956f1  test    eax, eax
0x1800956f3  jnz     loc_18009580A
0x1800956f9  mov     rax, [rdi]
0x1800956fc  lea     r8, aUserid_0; "UserId"
0x180095703  mov     r9, [rbp+String]; unsigned __int16 *
0x180095707  mov     rcx, [rbp+arg_10]; hKey
0x18009570b  mov     rdx, [r14+rax+38h]
0x180095710  mov     qword ptr [rsp+70h+dwOptions], rdx; Source
0x180095715  xor     edx, edx; lpSubKey
0x180095717  call    ?RegSaveStringValue@@YAKPEAUHKEY__@@PEBG111@Z; RegSaveStringValue(HKEY__ *,ushort const *,ushort const *,ushort const *,ushort const *)
0x18009571c  mov     ebx, eax
0x18009571e  test    eax, eax
0x180095720  jnz     loc_18009580A
0x180095726  test    cs:Microsoft_Windows_User_Device_RegistrationEnableBits, 1
0x18009572d  jz      short loc_18009579D
0x18009572f  mov     r10, [rdi]
0x180095732  mov     r8, [rbp+String]
0x180095736  mov     rax, [r14+r10+38h]
0x18009573b  mov     ecx, [r14+r10+20h]
0x180095740  mov     edx, [r14+r10+1Ch]
0x180095745  mov     r9d, [r14+r10+18h]
0x18009574a  mov     [rsp+70h+var_28], rax
0x18009574f  mov     rax, [r14+r10+30h]
0x180095754  mov     [rsp+70h+lpdwDisposition], rax
0x180095759  mov     rax, [r14+r10+28h]
0x18009575e  mov     [rsp+70h+phkResult], rax
0x180095763  mov     rax, [r14+r10+10h]
0x180095768  mov     [rsp+70h+lpSecurityAttributes], rax
0x18009576d  mov     qword ptr [rsp+70h+samDesired], rcx
0x180095772  mov     qword ptr [rsp+70h+dwOptions], rdx
0x180095777  call    McTemplateU0zxxxzzzz_EventWriteTransfer
0x18009577c  test    eax, eax
0x18009577e  jz      short loc_18009579D
0x180095780  mov     r9d, eax
0x180095783  lea     r8, aEventwritengcs; "EventWriteNgcSaveStatusSuccessEvent"
0x18009578a  lea     rdx, aLoggerWritengc_33; "Logger::WriteNgcSaveStatusSuccessEvent"
0x180095791  lea     rcx, Str; "%s: %s failed with win32 error code: 0x"...
0x180095798  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18009579d  mov     rcx, [rdi]
0x1800957a0  lea     r8, aHkeyCurrentUse_0; "HKEY_CURRENT_USER\\SOFTWARE\\Microsoft"...
0x1800957a7  mov     r9, [rbp+String]
0x1800957ab  mov     rdx, r15
0x1800957ae  mov     rax, [r14+rcx+38h]
0x1800957b3  mov     [rsp+70h+var_18], rax
0x1800957b8  mov     rax, [r14+rcx+30h]
0x1800957bd  mov     [rsp+70h+var_20], rax
0x1800957c2  mov     rax, [r14+rcx+28h]
0x1800957c7  mov     [rsp+70h+var_28], rax
0x1800957cc  mov     rax, [r14+rcx+10h]
0x1800957d1  mov     [rsp+70h+lpdwDisposition], rax
0x1800957d6  mov     eax, [r14+rcx+20h]
0x1800957db  mov     dword ptr [rsp+70h+phkResult], eax
0x1800957df  mov     eax, [r14+rcx+1Ch]
0x1800957e4  mov     dword ptr [rsp+70h+lpSecurityAttributes], eax
0x1800957e8  mov     eax, [r14+rcx+18h]
0x1800957ed  lea     rcx, aSSuccessfullyS_0; "%s: Successfully saved NGC key status t"...
0x1800957f4  mov     [rsp+70h+samDesired], eax
0x1800957f8  mov     qword ptr [rsp+70h+dwOptions], r9
0x1800957fd  call    ?TraceInformation@Logger@@SAJPEBGZZ; Logger::TraceInformation(ushort const *,...)
0x180095802  inc     rsi
0x180095805  jmp     loc_18009556F
0x18009580a  lea     r8, aRegsavestringv; "RegSaveStringValue"
0x180095811  jmp     loc_18009589C
0x180095816  lea     r8, aRegsavedwordva; "RegSaveDwordValue"
0x18009581d  jmp     short loc_18009589C
0x18009581f  mov     rax, [rbp+String]
0x180095823  lea     r9, aHkeyCurrentUse_0; "HKEY_CURRENT_USER\\SOFTWARE\\Microsoft"...
0x18009582a  lea     r8, aSS_3; "%s\\%s"
0x180095831  mov     qword ptr [rsp+70h+dwOptions], rax
0x180095836  lea     rdx, aRegcreatekeyex; "RegCreateKeyExW"
0x18009583d  mov     ecx, ebx; unsigned int
0x18009583f  call    ?WriteRegistryFailureEventEx@Logger@@SAJKPEBG0ZZ; Logger::WriteRegistryFailureEventEx(ulong,ushort const *,ushort const *,...)
0x180095844  mov     r9, [rbp+String]
0x180095848  lea     r8, aHkeyCurrentUse_0; "HKEY_CURRENT_USER\\SOFTWARE\\Microsoft"...
0x18009584f  mov     rdx, r15
0x180095852  mov     [rsp+70h+dwOptions], ebx
0x180095856  lea     rcx, aSFailedToCreat; "%s: Failed to create or open registry k"...
0x18009585d  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180095862  jmp     short loc_1800958AE
0x180095864  mov     r8d, eax
0x180095867  lea     rcx, aSCannotConvert_1; "%s: Cannot convert the NGC key ID to a "...
0x18009586e  mov     rdx, r15
0x180095871  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180095876  jmp     short loc_1800958C7
0x180095878  mov     rcx, [rbp+arg_18]; HKEY
0x18009587c  lea     rdx, aHkeyCurrentUse_0; "HKEY_CURRENT_USER\\SOFTWARE\\Microsoft"...
0x180095883  xor     r14d, r14d
0x180095886  call    ?RegFlush@@YAKPEAUHKEY__@@PEBG@Z; RegFlush(HKEY__ *,ushort const *)
0x18009588b  mov     ebx, eax
0x18009588d  test    eax, eax
0x18009588f  jz      loc_180095A35
0x180095895  lea     r8, aRegflush; "RegFlush"
0x18009589c  lea     rcx, Str; "%s: %s failed with win32 error code: 0x"...
0x1800958a3  mov     r9d, eax
0x1800958a6  mov     rdx, r15
0x1800958a9  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800958ae  test    ebx, ebx
0x1800958b0  jg      short loc_1800958B7
0x1800958b2  mov     r14d, ebx
0x1800958b5  jmp     short loc_1800958C2
0x1800958b7  movzx   r14d, bx
0x1800958bb  or      r14d, 80070000h
0x1800958c2  test    r12d, r12d
0x1800958c5  jz      short loc_1800958DC
0x1800958c7  test    r12d, r12d
0x1800958ca  jg      short loc_1800958D1
0x1800958cc  mov     r14d, r12d
0x1800958cf  jmp     short loc_1800958DC
0x1800958d1  movzx   r14d, r12w
0x1800958d5  or      r14d, 80070000h
0x1800958dc  test    r14d, r14d
0x1800958df  jns     loc_180095A35
0x1800958e5  cmp     [rbp+String], 0
0x1800958ea  jnz     short loc_180095919
0x1800958ec  cmp     qword ptr [rdi+8], 0
0x1800958f1  jbe     short loc_18009594A
0x1800958f3  mov     rcx, rsi
0x1800958f6  lea     rdx, [rbp+String]; StringUuid
0x1800958fa  shl     rcx, 6
0x1800958fe  add     rcx, [rdi]; Uuid
0x180095901  call    cs:__imp_UuidToStringW
0x180095907  mov     rdx, r15
0x18009590a  lea     rcx, aSCannotConverT; "%s: Cannot conver the NGC key ID a GUID"...
0x180095911  mov     r8d, eax
0x180095914  call    ?TraceWarning@Logger@@SAJPEBGZZ; Logger::TraceWarning(ushort const *,...)
0x180095919  cmp     qword ptr [rdi+8], 0
0x18009591e  jbe     short loc_18009594A
0x180095920  mov     rax, [rdi]
0x180095923  shl     rsi, 6
0x180095927  mov     ecx, [rsi+rax+18h]
0x18009592b  mov     edx, [rsi+rax+1Ch]
0x18009592f  mov     r8d, [rsi+rax+20h]
0x180095934  mov     r9, [rsi+rax+10h]
0x180095939  mov     r10, [rsi+rax+28h]
0x18009593e  mov     r11, [rsi+rax+30h]
0x180095943  mov     rbx, [rsi+rax+38h]
0x180095948  jmp     short loc_180095960
0x18009594a  xor     ecx, ecx
0x18009594c  xor     edx, edx
0x18009594e  xor     r8d, r8d
0x180095951  xor     r9d, r9d
0x180095954  xor     r10d, r10d
0x180095957  xor     r11d, r11d
0x18009595a  xor     ebx, ebx
0x18009595c  shl     rsi, 6
0x180095960  test    cs:Microsoft_Windows_User_Device_RegistrationEnableBits, 2
0x180095967  jz      short loc_1800959BF
0x180095969  mov     [rsp+70h+var_20], rbx
0x18009596e  mov     [rsp+70h+var_28], r11
0x180095973  mov     [rsp+70h+lpdwDisposition], r10
0x180095978  mov     [rsp+70h+phkResult], r9
0x18009597d  mov     r9, [rbp+String]
0x180095981  mov     eax, r8d
0x180095984  mov     [rsp+70h+lpSecurityAttributes], rax
0x180095989  mov     r8d, ecx
  ... truncated ...
```
