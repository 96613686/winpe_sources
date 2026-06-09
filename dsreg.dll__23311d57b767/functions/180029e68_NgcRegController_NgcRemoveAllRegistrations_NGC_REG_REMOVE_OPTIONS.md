# NgcRegController::NgcRemoveAllRegistrations(_NGC_REG_REMOVE_OPTIONS)

- ea: `0x180029e68`
- end: `0x18002a761`
- name: `?NgcRemoveAllRegistrations@NgcRegController@@SAJW4_NGC_REG_REMOVE_OPTIONS@@@Z`
- size: `2297`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `28`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180034684`
- `0x180052ba4`

## callees

- `0x180005ba0`
- `0x1800084f4`
- `0x180008530`
- `0x18000bac0`
- `0x180012280`
- `0x18001288c`
- `0x18001b560`
- `0x18001c02c`
- `0x180029e68`
- `0x18002a768`
- `0x18002b9b4`
- `0x18002ba70`
- `0x180033730`
- `0x180034cd0`
- `0x180038f40`
- `0x180043cac`
- `0x180044300`
- `0x18004c490`
- `0x18007df3c`
- `0x18007eaf8`
- `0x180081b74`
- `0x1800822b0`
- `0x18008271c`
- `0x1800830b0`
- `0x180094810`
- `0x1800b9908`
- `0x1800b9ab0`
- `0x1800b9d78`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a2e0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a6b4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a2e0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a6b4`
- `cryptngc!NgcFreeEnumState` at `0x18002a2f4`
- `cryptngc!NgcFreeEnumState` at `0x18002a6bf`
- `cryptngc!NgcFreeEnumState` at `0x18002a2f4`
- `cryptngc!NgcFreeEnumState` at `0x18002a6bf`
- `cryptngc!NgcEnumUserIdKeys` at `0x18002a343`
- `cryptngc!NgcEnumUserIdKeys` at `0x18002a343`

## string_xrefs

- `0x18002a2c6`: `StringCompare`
- `0x180029e9b`: `NgcRegController::NgcRemoveAllRegistrations`
- `0x180029f34`: `NgcRegController::NgcRemoveAllRegistrations`
- `0x180029f9f`: `NgcRegController::NgcRemoveAllRegistrations`
- `0x18002a014`: `NgcRegController::NgcRemoveAllRegistrations`
- `0x18002a058`: `NgcRegController::NgcRemoveAllRegistrations`
- `0x18002a103`: `NgcRegController::NgcRemoveAllRegistrations`
- `0x18002a1a2`: `NgcRegController::NgcRemoveAllRegistrations`
- `0x18002a1c4`: `NgcRegController::NgcRemoveAllRegistrations`
- `0x18002a25a`: `NgcRegController::NgcRemoveAllRegistrations`
- `0x18002a3da`: `NgcRegController::NgcRemoveAllRegistrations`
- `0x18002a4a2`: `NgcRegController::NgcRemoveAllRegistrations`
- `0x18002a501`: `NgcRegController::NgcRemoveAllRegistrations`
- `0x18002a545`: `NgcRegController::NgcRemoveAllRegistrations`
- `0x18002a608`: `NgcRegController::NgcRemoveAllRegistrations`
- `0x18002a651`: `NgcRegController::NgcRemoveAllRegistrations`
- `0x18002a6d3`: `NgcRegController::NgcRemoveAllRegistrations`
- `0x18002a54c`: `%s: NGC key successfully deleted. IdpDomain: %s, TenantId: %s, UserEmail: %s, UserSid: %s.`
- `0x18002a4e3`: `%s: Enterprise NGC key found. Skipping user with SID: %s.`
- `0x18002a05f`: `%s: User with SID "%s" is not AD or AAD user. Skipping...`
- `0x18002a14f`: `%s: User with SID "%s" does not have any AAD NGC key registered. Skipping...`
- `0x18002a3e1`: `%s: User ID key is missing. SID: %s, IDP domain: %s, Tenant domain: %s, User ID: %s, Error code: 0x%08x.`
- `0x18002a09f`: `%s: DsrHKeyUserHandle::Open failed for sid %s with error code: 0x%08x.`
- `0x180029fa6`: `%s: Looking for NGC keys to delete for user SID %s`
- `0x18002a658`: `%s: DsrHKeyUserHandle::Close failed for SID "%s" with error code: 0x%08x.`
- `0x18002a4a9`: `%s: Cannot enumerate user ID key. NgcEnumUserIdKeys failed. SID: %s, IDP domain: %s, Tenant domain: %s, User ID: %s, Error code: 0x%08x.`
- `0x18002a5fe`: `%s: NGC registry metadata successfully deleted for SID "%s".`
- `0x18002a5b9`: `%s: NgcStatusStorage::Delete failed for SID "%s" with error code: 0x%08x.`
- `0x18002a1cb`: `%s: Password-less state successfully reset for UserSid: %s`
- `0x18002a1a9`: `%s: ResetPasswordLessNgcSetState for UserSid %s failed with error code: 0x%08x.`
- `0x18002a00d`: `%s: NgcRegController::IsAdOrAadSid failed checking sid "%s" with error code: 0x%08x.`
- `0x18002a0fc`: `%s: NgcStatusStorage::Load failed for sid "%s" with error code: 0x%08x.`
- `0x18002a412`: `KeyManager::DeleteContainer`
- `0x18002a508`: `%s: KeyManager::DeleteUserKey failed with error code: 0x%08x. Ignoring this error as requested.`
- `0x18002a5db`: `KeyManager::DeleteUserKey`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall NgcRegController::NgcRemoveAllRegistrations(unsigned int a1)
{
  unsigned int v1; // edi
  int v2; // r12d
  int HKeyUserHandles; // eax
  int IsAdOrAadSid; // ebx
  unsigned __int64 v5; // r13
  DsrHKeyUserHandle *v6; // rcx
  __int64 v7; // r14
  __int64 v8; // rsi
  _QWORD *UserSid; // rax
  __int64 v10; // rax
  DsrHKeyUserHandle *v11; // rcx
  _QWORD *v12; // rax
  _QWORD *v13; // rax
  char *v14; // rcx
  _QWORD *v15; // rax
  __int64 v16; // rax
  int v17; // ebx
  _QWORD *v18; // rax
  int IsEmpty; // eax
  char *v20; // rcx
  _QWORD *v21; // rax
  __int64 v22; // rax
  int v23; // ebx
  _QWORD *v24; // rax
  int v25; // eax
  const unsigned __int16 *v26; // rcx
  const unsigned __int16 *v27; // r8
  const unsigned __int16 *v28; // rdx
  int v29; // ebx
  __int64 v30; // r9
  const wchar_t *v31; // r8
  int v32; // eax
  int v33; // ebx
  _QWORD *v34; // rax
  int v35; // edi
  _QWORD *v36; // rax
  char v37; // dl
  int v38; // eax
  __int64 v39; // rax
  _QWORD *v40; // rax
  _QWORD *v41; // rax
  int v42; // eax
  _QWORD *v43; // rax
  __int64 v44; // rax
  NgcStatusStorage *v45; // rcx
  _QWORD *v46; // rax
  int v47; // eax
  _QWORD *v48; // rax
  unsigned __int16 *v50; // [rsp+30h] [rbp-D0h]
  unsigned __int16 *v51; // [rsp+30h] [rbp-D0h]
  DsrHKeyUserHandle *v52[2]; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v53; // [rsp+50h] [rbp-B0h]
  int v54; // [rsp+58h] [rbp-A8h] BYREF
  int v55; // [rsp+5Ch] [rbp-A4h] BYREF
  unsigned int v56; // [rsp+60h] [rbp-A0h]
  HLOCAL hMem; // [rsp+68h] [rbp-98h] BYREF
  __int64 v58; // [rsp+70h] [rbp-90h] BYREF
  _QWORD v59[3]; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int16 *v60[2]; // [rsp+90h] [rbp-70h] BYREF
  __int128 v61; // [rsp+A0h] [rbp-60h]
  __int64 v62; // [rsp+B0h] [rbp-50h]
  __int64 v63; // [rsp+B8h] [rbp-48h]
  __int64 v64; // [rsp+C0h] [rbp-40h]
  int v65; // [rsp+C8h] [rbp-38h]
  __int128 v66; // [rsp+D0h] [rbp-30h]
  __int64 v67; // [rsp+E0h] [rbp-20h]
  __int64 v68; // [rsp+E8h] [rbp-18h]
  __int64 v69; // [rsp+F0h] [rbp-10h]
  int v70; // [rsp+F8h] [rbp-8h]
  __int64 v71; // [rsp+100h] [rbp+0h]
  __int64 v72; // [rsp+108h] [rbp+8h]
  struct _GUID v73; // [rsp+110h] [rbp+10h] BYREF
  unsigned __int16 *v74; // [rsp+120h] [rbp+20h]
  unsigned int v75; // [rsp+128h] [rbp+28h]
  unsigned int v76; // [rsp+12Ch] [rbp+2Ch]
  unsigned int v77; // [rsp+130h] [rbp+30h]
  unsigned __int16 *v78; // [rsp+138h] [rbp+38h]
  LPCWCH lpString1; // [rsp+140h] [rbp+40h]
  unsigned __int16 *v80; // [rsp+148h] [rbp+48h]
  _BYTE v81[32]; // [rsp+150h] [rbp+50h] BYREF

  v1 = a1;
  v56 = a1;
  Logger::TraceVerbose((wchar_t *)L"%s started. Options: %d.", L"NgcRegController::NgcRemoveAllRegistrations", a1);
  v2 = 0;
  v61 = 0;
  v62 = 0;
  *(_OWORD *)v60 = 0;
  v63 = 0;
  v64 = 0;
  v65 = 0;
  v66 = 0;
  v67 = 0;
  v68 = 0;
  v69 = 0;
  v70 = 0;
  v71 = 0;
  v72 = 0;
  hMem = 0;
  v58 = 0;
  v54 = 0;
  v59[0] = 0;
  v59[1] = 0;
  std::vector<DsrHKeyUserHandle>::vector<DsrHKeyUserHandle>(v52);
  HKeyUserHandles = DsrHKeyUserHandle::GetHKeyUserHandles(v52);
  IsAdOrAadSid = HKeyUserHandles;
  if ( HKeyUserHandles >= 0 )
  {
    v5 = 0;
    v6 = v52[0];
    if ( !(0xCCCCCCCCCCCCCCCDuLL * ((v52[1] - v52[0]) >> 4)) )
      goto LABEL_98;
    v7 = 0;
    while ( 1 )
    {
      v8 = 80 * v5;
      UserSid = (_QWORD *)DsrHKeyUserHandle::GetUserSid((char *)v6 + 80 * v5, v81);
      if ( UserSid[3] > 7u )
        UserSid = (_QWORD *)*UserSid;
      Logger::TraceVerbose(
        (wchar_t *)L"%s: Looking for NGC keys to delete for user SID %s",
        L"NgcRegController::NgcRemoveAllRegistrations",
        UserSid);
      std::wstring::_Tidy_deallocate((__int64)v81);
      v10 = DsrHKeyUserHandle::GetUserSid((char *)v52[0] + v8, v81);
      if ( *(_QWORD *)(v10 + 24) > 7u )
        v10 = *(_QWORD *)v10;
      IsAdOrAadSid = NgcRegController::IsAdOrAadSid((const unsigned __int16 *)v10, &v54);
      std::wstring::_Tidy_deallocate((__int64)v81);
      v11 = (DsrHKeyUserHandle *)((char *)v52[0] + v7);
      if ( IsAdOrAadSid >= 0 )
      {
        if ( !v54 )
        {
          v13 = (_QWORD *)DsrHKeyUserHandle::GetUserSid(v11, v81);
          if ( v13[3] > 7u )
            v13 = (_QWORD *)*v13;
          Logger::TraceVerbose(
            (wchar_t *)L"%s: User with SID \"%s\" is not AD or AAD user. Skipping...",
            L"NgcRegController::NgcRemoveAllRegistrations",
            v13);
          std::wstring::_Tidy_deallocate((__int64)v81);
          goto LABEL_97;
        }
        IsAdOrAadSid = DsrHKeyUserHandle::Open(v11);
        v14 = (char *)v52[0] + v7;
        if ( IsAdOrAadSid >= 0 )
        {
          v16 = DsrHKeyUserHandle::GetUserSid(v14, v81);
          if ( *(_QWORD *)(v16 + 24) > 7u )
            v16 = *(_QWORD *)v16;
          v17 = NgcStatusStorage::Load(
                  (NgcStatusStorage *)v59,
                  *(HKEY *)((char *)v52[0] + v8 + 8),
                  (const unsigned __int16 *)v16);
          std::wstring::_Tidy_deallocate((__int64)v81);
          if ( v17 < 0 )
          {
            v18 = (_QWORD *)DsrHKeyUserHandle::GetUserSid((char *)v52[0] + v7, v81);
            if ( v18[3] > 7u )
              v18 = (_QWORD *)*v18;
            Logger::TraceError(
              L"%s: NgcStatusStorage::Load failed for sid \"%s\" with error code: 0x%08x.",
              L"NgcRegController::NgcRemoveAllRegistrations",
              v18,
              (unsigned int)v17);
            goto LABEL_28;
          }
          IsEmpty = NgcStatusStorage::IsEmpty((NgcStatusStorage *)v59);
          v20 = (char *)v52[0] + v7;
          if ( IsEmpty )
          {
            v21 = (_QWORD *)DsrHKeyUserHandle::GetUserSid(v20, v81);
            if ( v21[3] > 7u )
              v21 = (_QWORD *)*v21;
            Logger::TraceVerbose(
              L"%s: User with SID \"%s\" does not have any AAD NGC key registered. Skipping...",
              L"NgcRegController::NgcRemoveAllRegistrations",
              v21);
            goto LABEL_91;
          }
          v22 = DsrHKeyUserHandle::GetUserSid(v20, v81);
          if ( *(_QWORD *)(v22 + 24) > 7u )
            v22 = *(_QWORD *)v22;
          v23 = ResetPasswordLessNgcSetState((const unsigned __int16 *)v22);
          std::wstring::_Tidy_deallocate((__int64)v81);
          v24 = (_QWORD *)DsrHKeyUserHandle::GetUserSid((char *)v52[0] + v7, v81);
          if ( v23 >= 0 )
          {
            if ( v24[3] > 7u )
              v24 = (_QWORD *)*v24;
            Logger::TraceVerbose(
              (wchar_t *)L"%s: Password-less state successfully reset for UserSid: %s",
              L"NgcRegController::NgcRemoveAllRegistrations",
              v24);
          }
          else
          {
            if ( v24[3] > 7u )
              v24 = (_QWORD *)*v24;
            Logger::TraceError(
              L"%s: ResetPasswordLessNgcSetState for UserSid %s failed with error code: 0x%08x.",
              L"NgcRegController::NgcRemoveAllRegistrations",
              v24,
              (unsigned int)v23);
          }
          std::wstring::_Tidy_deallocate((__int64)v81);
          NgcStatusStorage::GetKey(v59, &v73);
          DsrHKeyUserHandle::GetUserSid((char *)v52[0] + v8, v81);
          v25 = IsEmptyString(v78);
          v28 = L"login.windows.net";
          if ( !v25 )
            v28 = v26;
          v29 = KeyManager::Initialize(v60, v28, lpString1, v80, v27, v74);
          std::wstring::_Tidy_deallocate((__int64)v81);
          if ( v29 < 0 )
          {
            v30 = (unsigned int)v29;
            v31 = L"KeyManager::Initialize";
            goto LABEL_46;
          }
          if ( !v1 )
            goto LABEL_61;
          if ( v1 == 1 )
          {
            v37 = 0;
            goto LABEL_62;
          }
          if ( v1 == 2 )
          {
            v47 = KeyManager::DeleteUserKey((KeyManager *)v60, 0);
            if ( v47 >= 0 )
              goto LABEL_76;
            v30 = (unsigned int)v47;
            v31 = L"KeyManager::DeleteUserKey";
LABEL_46:
            Logger::TraceError(
              L"%s: %s failed with error code: 0x%08x.",
              L"NgcRegController::NgcRemoveAllRegistrations",
              v31,
              v30);
          }
          else
          {
            if ( v1 == 3 )
            {
              v42 = KeyManager::DeleteUserKey((KeyManager *)v60, 0);
              if ( v42 < 0 )
                Logger::TraceError(
                  L"%s: KeyManager::DeleteUserKey failed with error code: 0x%08x. Ignoring this error as requested.",
                  L"NgcRegController::NgcRemoveAllRegistrations",
                  (unsigned int)v42);
            }
            else if ( v1 == 4 )
            {
              v55 = 0;
              v32 = StringCompare(lpString1, L"383a3889-5bc9-47a3-846c-2b70f0b7fe0e", 1u, &v55);
              if ( v32 < 0 )
              {
                v30 = (unsigned int)v32;
                v31 = L"StringCompare";
                goto LABEL_46;
              }
              v33 = v55;
              if ( v55 )
              {
                LocalFree(hMem);
                hMem = 0;
                NgcFreeEnumState(v58);
                v58 = 0;
                v34 = (_QWORD *)DsrHKeyUserHandle::GetUserSid((char *)v52[0] + v8, v81);
                if ( v34[3] > 7u )
                  v34 = (_QWORD *)*v34;
                v35 = NgcEnumUserIdKeys(
                        v78,
                        L"383a3889-5bc9-47a3-846c-2b70f0b7fe0e",
                        &cchOriginalDestLength,
                        v34,
                        &hMem,
                        &v58);
                std::wstring::_Tidy_deallocate((__int64)v81);
                if ( v35 == -2146893782 )
                {
                  Logger::WriteMissingNgcKeyEvent(&v73, v75, v76, v77, v74, v78, lpString1, v80);
                  v36 = (_QWORD *)DsrHKeyUserHandle::GetUserSid((char *)v52[0] + v8, v81);
                  if ( v36[3] > 7u )
                    v36 = (_QWORD *)*v36;
                  LODWORD(v51) = -2146893782;
                  Logger::TraceWarning(
                    (wchar_t *)L"%s: User ID key is missing. SID: %s, IDP domain: %s, Tenant domain: %s, User ID: %s, Error code: 0x%08x.",
                    L"NgcRegController::NgcRemoveAllRegistrations",
                    v36,
                    v78,
                    L"383a3889-5bc9-47a3-846c-2b70f0b7fe0e",
                    &cchOriginalDestLength,
                    v51);
                  std::wstring::_Tidy_deallocate((__int64)v81);
                  goto LABEL_61;
                }
                if ( v35 < 0 )
                {
                  v39 = DsrHKeyUserHandle::GetUserSid((char *)v52[0] + v8, v81);
                  if ( *(_QWORD *)(v39 + 24) > 7u )
                    v39 = *(_QWORD *)v39;
                  Logger::WriteNgcEnumUserIdKeysFailureEvent(
                    (const unsigned __int16 *)v39,
                    v78,
                    L"383a3889-5bc9-47a3-846c-2b70f0b7fe0e",
                    &cchOriginalDestLength,
                    v35);
                  std::wstring::_Tidy_deallocate((__int64)v81);
                  v40 = (_QWORD *)DsrHKeyUserHandle::GetUserSid((char *)v52[0] + v8, v81);
                  if ( v40[3] > 7u )
                    v40 = (_QWORD *)*v40;
                  LODWORD(v50) = v35;
                  Logger::TraceError(
                    L"%s: Cannot enumerate user ID key. NgcEnumUserIdKeys failed. SID: %s, IDP domain: %s, Tenant domain: "
                     "%s, User ID: %s, Error code: 0x%08x.",
                    L"NgcRegController::NgcRemoveAllRegistrations",
                    v40,
                    v78,
                    L"383a3889-5bc9-47a3-846c-2b70f0b7fe0e",
                    &cchOriginalDestLength,
                    v50);
                  std::wstring::_Tidy_deallocate((__int64)v81);
                  v33 = 0;
                }
                if ( v33 )
                {
                  v41 = (_QWORD *)DsrHKeyUserHandle::GetUserSid((char *)v52[0] + v8, v81);
                  if ( v41[3] > 7u )
                    v41 = (_QWORD *)*v41;
                  Logger::TraceVerbose(
                    L"%s: Enterprise NGC key found. Skipping user with SID: %s.",
                    L"NgcRegController::NgcRemoveAllRegistrations",
                    v41);
LABEL_91:
                  std::wstring::_Tidy_deallocate((__int64)v81);
                  goto LABEL_92;
                }
              }
LABEL_61:
              v37 = 1;
LABEL_62:
              v38 = KeyManager::DeleteContainer((const unsigned __int16 **)v60, v37, 0, 0);
              if ( v38 < 0 )
              {
                v30 = (unsigned int)v38;
                v31 = L"KeyManager::DeleteContainer";
                goto LABEL_46;
              }
            }
LABEL_76:
            v43 = (_QWORD *)DsrHKeyUserHandle::GetUserSid((char *)v52[0] + v8, v81);
            if ( v43[3] > 7u )
              v43 = (_QWORD *)*v43;
            Logger::TraceVerbose(
              (wchar_t *)L"%s: NGC key successfully deleted. IdpDomain: %s, TenantId: %s, UserEmail: %s, UserSid: %s.",
              L"NgcRegController::NgcRemoveAllRegistrations",
              v78,
              lpString1,
              v80,
              v43);
            std::wstring::_Tidy_deallocate((__int64)v81);
          }
          v44 = DsrHKeyUserHandle::GetUserSid((char *)v52[0] + v8, v81);
          if ( *(_QWORD *)(v44 + 24) > 7u )
            v44 = *(_QWORD *)v44;
          v17 = NgcStatusStorage::Delete(v45, *(HKEY *)((char *)v52[0] + v8 + 8), (unsigned __int16 *)v44);
          std::wstring::_Tidy_deallocate((__int64)v81);
          v46 = (_QWORD *)DsrHKeyUserHandle::GetUserSid((char *)v52[0] + v7, v81);
          if ( v17 >= 0 )
          {
            if ( v46[3] > 7u )
              v46 = (_QWORD *)*v46;
            Logger::TraceVerbose(
              (wchar_t *)L"%s: NGC registry metadata successfully deleted for SID \"%s\".",
              L"NgcRegController::NgcRemoveAllRegistrations",
              v46);
            goto LABEL_91;
          }
          if ( v46[3] > 7u )
            v46 = (_QWORD *)*v46;
          Logger::TraceError(
            L"%s: NgcStatusStorage::Delete failed for SID \"%s\" with error code: 0x%08x.",
            L"NgcRegController::NgcRemoveAllRegistrations",
            v46,
            (unsigned int)v17);
LABEL_28:
          std::wstring::_Tidy_deallocate((__int64)v81);
          v2 = v17;
LABEL_92:
          IsAdOrAadSid = DsrHKeyUserHandle::Close((DsrHKeyUserHandle *)((char *)v52[0] + v8));
          if ( IsAdOrAadSid >= 0 )
          {
            v1 = v56;
          }
          else
          {
            v48 = (_QWORD *)DsrHKeyUserHandle::GetUserSid((char *)v52[0] + v8, v81);
            if ( v48[3] > 7u )
              v48 = (_QWORD *)*v48;
            Logger::TraceError(
              L"%s: DsrHKeyUserHandle::Close failed for SID \"%s\" with error code: 0x%08x.",
              L"NgcRegController::NgcRemoveAllRegistrations",
              v48,
              (unsigned int)IsAdOrAadSid);
            std::wstring::_Tidy_deallocate((__int64)v81);
            IsAdOrAadSid = 0;
            v1 = v56;
          }
          goto LABEL_97;
        }
        v15 = (_QWORD *)DsrHKeyUserHandle::GetUserSid(v14, v81);
        if ( v15[3] > 7u )
          v15 = (_QWORD *)*v15;
        Logger::TraceError(
          L"%s: DsrHKeyUserHandle::Open failed for sid %s with error code: 0x%08x.",
          L"NgcRegController::NgcRemoveAllRegistrations",
          v15,
          (unsigned int)IsAdOrAadSid);
      }
      else
      {
        v12 = (_QWORD *)DsrHKeyUserHandle::GetUserSid(v11, v81);
        if ( v12[3] > 7u )
          v12 = (_QWORD *)*v12;
        Logger::TraceError(
          L"%s: NgcRegController::IsAdOrAadSid failed checking sid \"%s\" with error code: 0x%08x.",
          L"NgcRegController::NgcRemoveAllRegistrations",
          v12,
          (unsigned int)IsAdOrAadSid);
      }
      std::wstring::_Tidy_deallocate((__int64)v81);
      v2 = IsAdOrAadSid;
      IsAdOrAadSid = 0;
LABEL_97:
      ++v5;
      v7 += 80;
      v6 = v52[0];
      if ( v5 >= 0xCCCCCCCCCCCCCCCDuLL * ((v52[1] - v52[0]) >> 4) )
        goto LABEL_98;
    }
  }
  Logger::TraceError(
    L"%s: %s failed with error code: 0x%08x.",
    L"NgcRegController::NgcRemoveAllRegistrations",
    L"DsrHKeyUserHandle::GetHKeyUserHandles",
    (unsigned int)HKeyUserHandles);
LABEL_98:
  LocalFree(hMem);
  NgcFreeEnumState(v58);
  if ( IsAdOrAadSid >= 0 && v2 < 0 )
    IsAdOrAadSid = v2;
  Logger::TraceVerbose(
    (wchar_t *)L"%s - hr: 0x%08x",
    L"NgcRegController::NgcRemoveAllRegistrations",
    (unsigned int)IsAdOrAadSid);
  if ( v52[0] )
  {
    std::_Destroy_range<std::allocator<DsrHKeyUserHandle>>(v52[0]);
    std::_Deallocate<16>(v52[0], 16 * ((signed __int64)(v53 - (unsigned __int64)v52[0]) >> 4));
    *(_OWORD *)v52 = 0;
    v53 = 0;
  }
  NgcStatusStorage::Cleanup((NgcStatusStorage *)v59);
  KeyManager::Cleanup((KeyManager *)v60);
  return (unsigned int)IsAdOrAadSid;
}

```

## disassembly

```asm
0x180029e68  push    rbp
0x180029e6a  push    rbx
0x180029e6b  push    rsi
0x180029e6c  push    rdi
0x180029e6d  push    r12
0x180029e6f  push    r13
0x180029e71  push    r14
0x180029e73  push    r15
0x180029e75  lea     rbp, [rsp-88h]
0x180029e7d  sub     rsp, 188h
0x180029e84  mov     rax, cs:__security_cookie
0x180029e8b  xor     rax, rsp
0x180029e8e  mov     [rbp+0C0h+var_50], rax
0x180029e92  mov     edi, ecx
0x180029e94  mov     [rsp+1C0h+var_160], ecx
0x180029e98  mov     r8d, ecx
0x180029e9b  lea     rdx, aNgcregcontroll; "NgcRegController::NgcRemoveAllRegistrat"...
0x180029ea2  lea     rcx, aSStartedOption; "%s started. Options: %d."
0x180029ea9  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x180029eae  xor     esi, esi
0x180029eb0  mov     r12d, esi
0x180029eb3  xorps   xmm0, xmm0
0x180029eb6  movdqa  [rbp+0C0h+var_120], xmm0
0x180029ebb  mov     [rbp+0C0h+var_110], rsi
0x180029ebf  xorps   xmm1, xmm1
0x180029ec2  movdqa  xmmword ptr [rbp+0C0h+var_130], xmm1
0x180029ec7  mov     [rbp+0C0h+var_108], rsi
0x180029ecb  mov     [rbp+0C0h+var_100], rsi
0x180029ecf  mov     [rbp+0C0h+var_F8], esi
0x180029ed2  movdqa  [rbp+0C0h+var_F0], xmm0
0x180029ed7  mov     [rbp+0C0h+var_E0], rsi
0x180029edb  mov     [rbp+0C0h+var_D8], rsi
0x180029edf  mov     [rbp+0C0h+var_D0], rsi
0x180029ee3  mov     [rbp+0C0h+var_C8], esi
0x180029ee6  mov     [rbp+0C0h+var_C0], rsi
0x180029eea  mov     [rbp+0C0h+var_B8], rsi
0x180029eee  mov     [rsp+1C0h+hMem], rsi
0x180029ef3  mov     [rsp+1C0h+var_150], rsi
0x180029ef8  mov     [rsp+1C0h+var_168], esi
0x180029efc  mov     [rsp+1C0h+var_148], rsi
0x180029f01  mov     [rbp+0C0h+var_140], rsi
0x180029f05  lea     rcx, [rsp+1C0h+var_180]; void *
0x180029f0a  call    ??0?$vector@VDsrHKeyUserHandle@@V?$allocator@VDsrHKeyUserHandle@@@std@@@std@@QEAA@XZ; std::vector<DsrHKeyUserHandle>::vector<DsrHKeyUserHandle>(void)
0x180029f0f  nop
0x180029f10  lea     rcx, [rsp+1C0h+var_180]
0x180029f15  call    ?GetHKeyUserHandles@DsrHKeyUserHandle@@SAJAEAV?$vector@VDsrHKeyUserHandle@@V?$allocator@VDsrHKeyUserHandle@@@std@@@std@@@Z; DsrHKeyUserHandle::GetHKeyUserHandles(std::vector<DsrHKeyUserHandle> &)
0x180029f1a  mov     ebx, eax
0x180029f1c  mov     r14, 0CCCCCCCCCCCCCCCDh
0x180029f26  test    eax, eax
0x180029f28  jns     short loc_180029F4C
0x180029f2a  mov     r9d, eax
0x180029f2d  lea     r8, aDsrhkeyuserhan; "DsrHKeyUserHandle::GetHKeyUserHandles"
0x180029f34  lea     rdx, aNgcregcontroll; "NgcRegController::NgcRemoveAllRegistrat"...
0x180029f3b  lea     rcx, aSSFailedWithEr_2; "%s: %s failed with error code: 0x%08x."
0x180029f42  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180029f47  jmp     loc_18002A6AF
0x180029f4c  mov     r13, rsi
0x180029f4f  mov     rax, [rsp+1C0h+var_180+8]
0x180029f54  mov     rcx, [rsp+1C0h+var_180]
0x180029f59  sub     rax, rcx
0x180029f5c  sar     rax, 4
0x180029f60  imul    rax, r14
0x180029f64  test    rax, rax
0x180029f67  jz      loc_18002A6AF
0x180029f6d  mov     r14, rsi
0x180029f70  lea     r15, aSSFailedWithEr_2; "%s: %s failed with error code: 0x%08x."
0x180029f77  lea     rsi, ds:0[r13*4]
0x180029f7f  add     rsi, r13
0x180029f82  shl     rsi, 4
0x180029f86  add     rcx, rsi
0x180029f89  lea     rdx, [rbp+0C0h+var_70]
0x180029f8d  call    ?GetUserSid@DsrHKeyUserHandle@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; DsrHKeyUserHandle::GetUserSid(void)
0x180029f92  cmp     qword ptr [rax+18h], 7
0x180029f97  jbe     short loc_180029F9C
0x180029f99  mov     rax, [rax]
0x180029f9c  mov     r8, rax
0x180029f9f  lea     rdx, aNgcregcontroll; "NgcRegController::NgcRemoveAllRegistrat"...
0x180029fa6  lea     rcx, aSLookingForNgc; "%s: Looking for NGC keys to delete for "...
0x180029fad  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x180029fb2  lea     rcx, [rbp+0C0h+var_70]
0x180029fb6  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180029fbb  mov     rcx, [rsp+1C0h+var_180]
0x180029fc0  add     rcx, rsi
0x180029fc3  lea     rdx, [rbp+0C0h+var_70]
0x180029fc7  call    ?GetUserSid@DsrHKeyUserHandle@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; DsrHKeyUserHandle::GetUserSid(void)
0x180029fcc  cmp     qword ptr [rax+18h], 7
0x180029fd1  jbe     short loc_180029FD6
0x180029fd3  mov     rax, [rax]
0x180029fd6  lea     rdx, [rsp+1C0h+var_168]; int *
0x180029fdb  mov     rcx, rax; unsigned __int16 *
0x180029fde  call    ?IsAdOrAadSid@NgcRegController@@CAJPEBGPEAH@Z; NgcRegController::IsAdOrAadSid(ushort const *,int *)
0x180029fe3  mov     ebx, eax
0x180029fe5  lea     rcx, [rbp+0C0h+var_70]
0x180029fe9  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180029fee  mov     rcx, [rsp+1C0h+var_180]
0x180029ff3  add     rcx, r14; this
0x180029ff6  test    ebx, ebx
0x180029ff8  jns     short loc_18002A03B
0x180029ffa  lea     rdx, [rbp+0C0h+var_70]
0x180029ffe  call    ?GetUserSid@DsrHKeyUserHandle@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; DsrHKeyUserHandle::GetUserSid(void)
0x18002a003  cmp     qword ptr [rax+18h], 7
0x18002a008  jbe     short loc_18002A00D
0x18002a00a  mov     rax, [rax]
0x18002a00d  lea     rcx, aSNgcregcontrol_4; "%s: NgcRegController::IsAdOrAadSid fail"...
0x18002a014  lea     rdx, aNgcregcontroll; "NgcRegController::NgcRemoveAllRegistrat"...
0x18002a01b  mov     r8, rax
0x18002a01e  mov     r9d, ebx
0x18002a021  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18002a026  lea     rcx, [rbp+0C0h+var_70]
0x18002a02a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002a02f  mov     r12d, ebx
0x18002a032  xor     esi, esi
0x18002a034  mov     ebx, esi
0x18002a036  jmp     loc_18002A67D
0x18002a03b  cmp     [rsp+1C0h+var_168], 0
0x18002a040  jnz     short loc_18002A079
0x18002a042  lea     rdx, [rbp+0C0h+var_70]
0x18002a046  call    ?GetUserSid@DsrHKeyUserHandle@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; DsrHKeyUserHandle::GetUserSid(void)
0x18002a04b  cmp     qword ptr [rax+18h], 7
0x18002a050  jbe     short loc_18002A055
0x18002a052  mov     rax, [rax]
0x18002a055  mov     r8, rax
0x18002a058  lea     rdx, aNgcregcontroll; "NgcRegController::NgcRemoveAllRegistrat"...
0x18002a05f  lea     rcx, aSUserWithSidSI; "%s: User with SID \"%s\" is not AD or A"...
0x18002a066  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x18002a06b  lea     rcx, [rbp+0C0h+var_70]
0x18002a06f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002a074  jmp     loc_18002A67B
0x18002a079  call    ?Open@DsrHKeyUserHandle@@QEAAJXZ; DsrHKeyUserHandle::Open(void)
0x18002a07e  mov     ebx, eax
0x18002a080  mov     rcx, [rsp+1C0h+var_180]
0x18002a085  lea     rdx, [rbp+0C0h+var_70]
0x18002a089  add     rcx, r14
0x18002a08c  test    eax, eax
0x18002a08e  jns     short loc_18002A0AB
0x18002a090  call    ?GetUserSid@DsrHKeyUserHandle@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; DsrHKeyUserHandle::GetUserSid(void)
0x18002a095  cmp     qword ptr [rax+18h], 7
0x18002a09a  jbe     short loc_18002A09F
0x18002a09c  mov     rax, [rax]
0x18002a09f  lea     rcx, aSDsrhkeyuserha_0; "%s: DsrHKeyUserHandle::Open failed for "...
0x18002a0a6  jmp     loc_18002A014
0x18002a0ab  call    ?GetUserSid@DsrHKeyUserHandle@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; DsrHKeyUserHandle::GetUserSid(void)
0x18002a0b0  nop
0x18002a0b1  cmp     qword ptr [rax+18h], 7
0x18002a0b6  jbe     short loc_18002A0BB
0x18002a0b8  mov     rax, [rax]
0x18002a0bb  mov     r8, rax; unsigned __int16 *
0x18002a0be  mov     rdx, [rsp+1C0h+var_180]
0x18002a0c3  mov     rdx, [rdx+rsi+8]; hKey
0x18002a0c8  lea     rcx, [rsp+1C0h+var_148]; this
0x18002a0cd  call    ?Load@NgcStatusStorage@@QEAAJPEAUHKEY__@@PEBG@Z; NgcStatusStorage::Load(HKEY__ *,ushort const *)
0x18002a0d2  mov     ebx, eax
0x18002a0d4  lea     rcx, [rbp+0C0h+var_70]
0x18002a0d8  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002a0dd  test    ebx, ebx
0x18002a0df  jns     short loc_18002A126
0x18002a0e1  mov     rcx, [rsp+1C0h+var_180]
0x18002a0e6  add     rcx, r14
0x18002a0e9  lea     rdx, [rbp+0C0h+var_70]
0x18002a0ed  call    ?GetUserSid@DsrHKeyUserHandle@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; DsrHKeyUserHandle::GetUserSid(void)
0x18002a0f2  cmp     qword ptr [rax+18h], 7
0x18002a0f7  jbe     short loc_18002A0FC
0x18002a0f9  mov     rax, [rax]
0x18002a0fc  lea     rcx, aSNgcstatusstor_1; "%s: NgcStatusStorage::Load failed for s"...
0x18002a103  lea     rdx, aNgcregcontroll; "NgcRegController::NgcRemoveAllRegistrat"...
0x18002a10a  mov     r8, rax
0x18002a10d  mov     r9d, ebx
0x18002a110  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18002a115  lea     rcx, [rbp+0C0h+var_70]
0x18002a119  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002a11e  mov     r12d, ebx
0x18002a121  jmp     loc_18002A61D
0x18002a126  lea     rcx, [rsp+1C0h+var_148]; this
0x18002a12b  call    ?IsEmpty@NgcStatusStorage@@QEAAHXZ; NgcStatusStorage::IsEmpty(void)
0x18002a130  mov     rcx, [rsp+1C0h+var_180]
0x18002a135  lea     rdx, [rbp+0C0h+var_70]
0x18002a139  add     rcx, r14
0x18002a13c  test    eax, eax
0x18002a13e  jz      short loc_18002A15B
0x18002a140  call    ?GetUserSid@DsrHKeyUserHandle@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; DsrHKeyUserHandle::GetUserSid(void)
0x18002a145  cmp     qword ptr [rax+18h], 7
0x18002a14a  jbe     short loc_18002A14F
0x18002a14c  mov     rax, [rax]
0x18002a14f  lea     rcx, aSUserWithSidSD; "%s: User with SID \"%s\" does not have "...
0x18002a156  jmp     loc_18002A605
0x18002a15b  call    ?GetUserSid@DsrHKeyUserHandle@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; DsrHKeyUserHandle::GetUserSid(void)
0x18002a160  cmp     qword ptr [rax+18h], 7
0x18002a165  jbe     short loc_18002A16A
0x18002a167  mov     rax, [rax]
0x18002a16a  mov     rcx, rax; unsigned __int16 *
0x18002a16d  call    ?ResetPasswordLessNgcSetState@@YAJPEBG@Z; ResetPasswordLessNgcSetState(ushort const *)
0x18002a172  mov     ebx, eax
0x18002a174  lea     rcx, [rbp+0C0h+var_70]
0x18002a178  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002a17d  mov     rcx, [rsp+1C0h+var_180]
0x18002a182  lea     rdx, [rbp+0C0h+var_70]
0x18002a186  add     rcx, r14
0x18002a189  call    ?GetUserSid@DsrHKeyUserHandle@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; DsrHKeyUserHandle::GetUserSid(void)
0x18002a18e  test    ebx, ebx
0x18002a190  jns     short loc_18002A1B7
0x18002a192  cmp     qword ptr [rax+18h], 7
0x18002a197  jbe     short loc_18002A19C
0x18002a199  mov     rax, [rax]
0x18002a19c  mov     r9d, ebx
0x18002a19f  mov     r8, rax
0x18002a1a2  lea     rdx, aNgcregcontroll; "NgcRegController::NgcRemoveAllRegistrat"...
0x18002a1a9  lea     rcx, aSResetpassword; "%s: ResetPasswordLessNgcSetState for Us"...
0x18002a1b0  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18002a1b5  jmp     short loc_18002A1D7
0x18002a1b7  cmp     qword ptr [rax+18h], 7
0x18002a1bc  jbe     short loc_18002A1C1
0x18002a1be  mov     rax, [rax]
0x18002a1c1  mov     r8, rax
0x18002a1c4  lea     rdx, aNgcregcontroll; "NgcRegController::NgcRemoveAllRegistrat"...
0x18002a1cb  lea     rcx, aSPasswordLessS; "%s: Password-less state successfully re"...
0x18002a1d2  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x18002a1d7  lea     rcx, [rbp+0C0h+var_70]
0x18002a1db  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002a1e0  lea     rdx, [rbp+0C0h+var_B0]
0x18002a1e4  lea     rcx, [rsp+1C0h+var_148]
0x18002a1e9  call    ?GetKey@NgcStatusStorage@@QEAA?AUSTRUCT_NGC_REG_KEY@@XZ; NgcStatusStorage::GetKey(void)
0x18002a1ee  mov     rcx, [rsp+1C0h+var_180]
0x18002a1f3  add     rcx, rsi
0x18002a1f6  lea     rdx, [rbp+0C0h+var_70]
0x18002a1fa  call    ?GetUserSid@DsrHKeyUserHandle@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; DsrHKeyUserHandle::GetUserSid(void)
0x18002a1ff  mov     r8, rax
0x18002a202  cmp     qword ptr [rax+18h], 7
0x18002a207  jbe     short loc_18002A20C
0x18002a209  mov     r8, [rax]
0x18002a20c  mov     rcx, [rbp+0C0h+var_88]; unsigned __int16 *
0x18002a210  call    ?IsEmptyString@@YAHPEBG@Z; IsEmptyString(ushort const *)
0x18002a215  lea     rdx, aLoginWindowsNe; "login.windows.net"
0x18002a21c  test    eax, eax
0x18002a21e  cmovz   rdx, rcx; unsigned __int16 *
0x18002a222  mov     rax, [rbp+0C0h+var_A0]
0x18002a226  mov     [rsp+1C0h+var_198], rax; unsigned __int16 *
0x18002a22b  mov     [rsp+1C0h+var_1A0], r8; unsigned __int16 *
0x18002a230  mov     r9, [rbp+0C0h+var_78]; unsigned __int16 *
0x18002a234  mov     r8, [rbp+0C0h+lpString1]; unsigned __int16 *
0x18002a238  lea     rcx, [rbp+0C0h+var_130]; this
0x18002a23c  call    ?Initialize@KeyManager@@QEAAJPEBG0000@Z; KeyManager::Initialize(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *)
0x18002a241  mov     ebx, eax
0x18002a243  lea     rcx, [rbp+0C0h+var_70]
0x18002a247  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002a24c  test    ebx, ebx
0x18002a24e  jns     short loc_18002A26E
0x18002a250  mov     r9d, ebx
0x18002a253  lea     r8, aKeymanagerInit; "KeyManager::Initialize"
0x18002a25a  lea     rdx, aNgcregcontroll; "NgcRegController::NgcRemoveAllRegistrat"...
0x18002a261  mov     rcx, r15; unsigned __int16 *
0x18002a264  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18002a269  jmp     loc_18002A561
0x18002a26e  mov     ecx, edi
0x18002a270  test    edi, edi
0x18002a272  jz      loc_18002A3F6
0x18002a278  sub     ecx, 1
0x18002a27b  jz      loc_18002A5E7
0x18002a281  sub     ecx, 1
0x18002a284  jz      loc_18002A5C5
0x18002a28a  sub     ecx, 1
0x18002a28d  jz      loc_18002A4EF
0x18002a293  cmp     ecx, 1
0x18002a296  jnz     loc_18002A514
0x18002a29c  mov     [rsp+1C0h+var_164], 0
0x18002a2a4  lea     r9, [rsp+1C0h+var_164]; int *
0x18002a2a9  mov     r8d, ecx; unsigned int
0x18002a2ac  lea     rdi, a383a38895bc947; "383a3889-5bc9-47a3-846c-2b70f0b7fe0e"
0x18002a2b3  mov     rdx, rdi; unsigned __int16 *
0x18002a2b6  mov     rcx, [rbp+0C0h+lpString1]; lpString1
0x18002a2ba  call    ?StringCompare@@YAJPEBG0KPEAH@Z; StringCompare(ushort const *,ushort const *,ulong,int *)
0x18002a2bf  test    eax, eax
0x18002a2c1  jns     short loc_18002A2CF
0x18002a2c3  mov     r9d, eax
0x18002a2c6  lea     r8, aStringcompare; "StringCompare"
0x18002a2cd  jmp     short loc_18002A25A
0x18002a2cf  mov     ebx, [rsp+1C0h+var_164]
0x18002a2d3  test    ebx, ebx
0x18002a2d5  jz      loc_18002A3F6
0x18002a2db  mov     rcx, [rsp+1C0h+hMem]; hMem
0x18002a2e0  call    cs:__imp_LocalFree
0x18002a2e6  mov     [rsp+1C0h+hMem], 0
0x18002a2ef  mov     rcx, [rsp+1C0h+var_150]
0x18002a2f4  call    cs:__imp_NgcFreeEnumState
0x18002a2fa  mov     [rsp+1C0h+var_150], 0
0x18002a303  mov     rcx, [rsp+1C0h+var_180]
0x18002a308  add     rcx, rsi
0x18002a30b  lea     rdx, [rbp+0C0h+var_70]
0x18002a30f  call    ?GetUserSid@DsrHKeyUserHandle@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; DsrHKeyUserHandle::GetUserSid(void)
0x18002a314  cmp     qword ptr [rax+18h], 7
0x18002a319  jbe     short loc_18002A31E
0x18002a31b  mov     rax, [rax]
0x18002a31e  lea     rcx, [rsp+1C0h+var_150]
0x18002a323  mov     [rsp+1C0h+var_198], rcx
0x18002a328  lea     rcx, [rsp+1C0h+hMem]
0x18002a32d  mov     [rsp+1C0h+var_1A0], rcx
0x18002a332  mov     r9, rax
0x18002a335  lea     r8, cchOriginalDestLength
0x18002a33c  mov     rdx, rdi
0x18002a33f  mov     rcx, [rbp+0C0h+var_88]
0x18002a343  call    cs:__imp_NgcEnumUserIdKeys
  ... truncated ...
```
