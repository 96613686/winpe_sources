# KeyManager::DeleteContainer(bool,bool,bool)

- ea: `0x1800822b0`
- end: `0x180082715`
- name: `?DeleteContainer@KeyManager@@QEAAJ_N00@Z`
- size: `1125`
- prototype: `__int64 __fastcall(KeyManager *__hidden this, bool, bool, bool)`
- caller_count: `5`
- callee_count: `14`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180029e68`
- `0x180080100`
- `0x1800805d0`
- `0x180080ca4`
- `0x1800811cc`

## callees

- `0x1800084f4`
- `0x180008530`
- `0x18000bac0`
- `0x180012948`
- `0x18001b560`
- `0x180034cd0`
- `0x180048960`
- `0x1800822b0`
- `0x18008271c`
- `0x180082afc`
- `0x180083004`
- `0x1800909fc`
- `0x180091cc8`
- `0x180091dc8`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008234b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800826d5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008234b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800826d5`
- `cryptngc!NgcDeleteContainerEx` at `0x1800824ed`
- `cryptngc!NgcDeleteContainerEx` at `0x1800824ed`
- `cryptngc!NgcFreeEnumState` at `0x1800826df`
- `cryptngc!NgcFreeEnumState` at `0x1800826df`
- `cryptngc!NgcEnumUserIdKeys` at `0x180082373`
- `cryptngc!NgcEnumUserIdKeys` at `0x180082373`
- `ext-ms-win-security-ngc-local-l1-1-0!NgcLocalRemoveCredential` at `0x180082645`
- `ext-ms-win-security-ngc-local-l1-1-0!NgcLocalRemoveCredential` at `0x180082645`

## string_xrefs

- `0x18008243b`: `StringCompare`
- `0x1800825b4`: `EventWriteContainerDeleteSuccessEvent`
- `0x1800825bb`: `Logger::WriteContainerDeleteSuccessEvent`
- `0x18008267a`: `Logger::WriteNgcLocalRemoveCredsFailureEvent`
- `0x180082673`: `EventWriteNgcLocalRemoveCredsFailureEvent`
- `0x18008254c`: `Logger::WriteNgcDeleteContainerFailureEvent`
- `0x180082545`: `EventWriteNgcDeleteContainerFailureEvent`
- `0x180082308`: `KeyManager::DeleteContainer`
- `0x18008239c`: `KeyManager::DeleteContainer`
- `0x1800823c9`: `KeyManager::DeleteContainer`
- `0x180082415`: `KeyManager::DeleteContainer`
- `0x180082466`: `KeyManager::DeleteContainer`
- `0x180082484`: `KeyManager::DeleteContainer`
- `0x1800824b3`: `KeyManager::DeleteContainer`
- `0x1800824c5`: `KeyManager::DeleteContainer`
- `0x180082565`: `KeyManager::DeleteContainer`
- `0x1800825cd`: `KeyManager::DeleteContainer`
- `0x1800825ef`: `KeyManager::DeleteContainer`
- `0x18008268c`: `KeyManager::DeleteContainer`
- `0x1800826a9`: `KeyManager::DeleteContainer`
- `0x1800826be`: `KeyManager::DeleteContainer`
- `0x1800826e8`: `KeyManager::DeleteContainer`
- `0x18008257d`: `KeyManager::DeleteUserKey`
- `0x18008248e`: `%s: User ID key is not found. SID: "%s", IDP domain: "", Tenant domain: "", User ID: "", Error code: 0x%08x.`
- `0x1800822ff`: `%s: started. force = %s, ignoreDeleteKeyFailure = %s.`
- `0x1800823a6`: `%s: NgcEnumUserIdKeys returns NULL pKeyInfo. SID: "%s", IDP domain: "", Tenant domain: "", User ID: "", HRESULT: 0x%08x.`
- `0x180082470`: `%s: Cannot find user ID key. NgcEnumUserIdKeys failed. SID: "%s", IDP domain: "", Tenant domain: "", User ID: "", Error code: 0x%08x.`
- `0x1800823f4`: `%s: Found non AAD user ID key. Will not delete the default container.`
- `0x1800824d2`: `%s: No user ID key or local PIN is found in the default container. Delete it.`
- `0x18008256c`: `%s: NgcDeleteContainerEx failed. SID: %s, Flag: %d, Error code: 0x%08x.`
- `0x1800825f6`: `%s: NgcDeleteContainerEx failed because the container is not found. Ignoring this error. SID: %s, Flag: %d, Error code: 0x%08x.`
- `0x180082696`: `%s: Cannot delete local PIN. NgcLocalRemoveCredential failed. SID: %s, Error code: 0x%08x.`
- `0x1800825d7`: `%s: NgcDeleteContainerEx succeeded. SID: %s, Flag: %d.`
- `0x1800826b0`: `%s: Local PIN was deleted. SID: %s.`
- `0x180082428`: `%s: KeyManager::DeleteUserKey failed with error code: 0x%08x. Ignore this error as requested...`

## pseudocode

```c
__int64 __fastcall KeyManager::DeleteContainer(const unsigned __int16 **this, char a2, char a3, char a4)
{
  const wchar_t *v6; // r8
  const wchar_t *v7; // r9
  int UserSid; // ebx
  int v11; // r14d
  unsigned __int16 *v12; // rdi
  LPCWCH *v13; // rcx
  int LocalCredential; // eax
  const wchar_t *v15; // r8
  unsigned int v16; // esi
  int v17; // eax
  int v18; // ecx
  unsigned int v19; // eax
  unsigned int v20; // eax
  int v21; // eax
  int v22; // eax
  __int64 v23; // rcx
  unsigned int v24; // eax
  int v26[2]; // [rsp+20h] [rbp-30h]
  HLOCAL hMem; // [rsp+30h] [rbp-20h] BYREF
  unsigned __int16 *v28; // [rsp+38h] [rbp-18h] BYREF
  __int64 v29; // [rsp+40h] [rbp-10h] BYREF
  int v30; // [rsp+98h] [rbp+48h] BYREF
  int v31; // [rsp+A0h] [rbp+50h] BYREF

  v28 = 0;
  hMem = 0;
  v6 = L"TRUE";
  v29 = 0;
  v7 = L"TRUE";
  v30 = 0;
  v31 = 0;
  if ( !a3 )
    v7 = L"FALSE";
  if ( !a2 )
    v6 = L"FALSE";
  Logger::TraceVerbose(
    (wchar_t *)L"%s: started. force = %s, ignoreDeleteKeyFailure = %s.",
    L"KeyManager::DeleteContainer",
    v6,
    v7);
  UserSid = KeyManager::GetUserSid((KeyManager *)this, &v28);
  if ( UserSid >= 0 )
  {
    v11 = 0;
    v12 = v28;
    if ( !a2 )
    {
      while ( 1 )
      {
        LocalFree(hMem);
        hMem = 0;
        UserSid = NgcEnumUserIdKeys(
                    &cchOriginalDestLength,
                    &cchOriginalDestLength,
                    &cchOriginalDestLength,
                    v12,
                    &hMem,
                    &v29);
        if ( UserSid == -2146893782 )
          break;
        if ( UserSid < 0 )
        {
          Logger::WriteNgcEnumUserIdKeysFailureEvent(
            v12,
            &cchOriginalDestLength,
            &cchOriginalDestLength,
            &cchOriginalDestLength,
            UserSid);
          Logger::TraceError(
            L"%s: Cannot find user ID key. NgcEnumUserIdKeys failed. SID: \"%s\", IDP domain: \"\", Tenant domain: \"\", U"
             "ser ID: \"\", Error code: 0x%08x.",
            L"KeyManager::DeleteContainer",
            v12,
            (unsigned int)UserSid);
          goto LABEL_51;
        }
        v13 = (LPCWCH *)hMem;
        if ( !hMem )
        {
          Logger::TraceError(
            L"%s: NgcEnumUserIdKeys returns NULL pKeyInfo. SID: \"%s\", IDP domain: \"\", Tenant domain: \"\", User ID: \""
             "\", HRESULT: 0x%08x.",
            L"KeyManager::DeleteContainer",
            v12,
            (unsigned int)UserSid);
          v13 = (LPCWCH *)hMem;
        }
        LocalCredential = StringCompare(*v13, this[2], 0, &v31);
        UserSid = LocalCredential;
        if ( LocalCredential < 0 )
        {
          v15 = L"StringCompare";
LABEL_19:
          Logger::TraceError(
            L"%s: %s failed with error code: 0x%08x.",
            L"KeyManager::DeleteContainer",
            v15,
            (unsigned int)LocalCredential);
          goto LABEL_51;
        }
        if ( !v31 )
        {
          Logger::TraceVerbose(
            (wchar_t *)L"%s: Found non AAD user ID key. Will not delete the default container.",
            L"KeyManager::DeleteContainer");
          goto LABEL_15;
        }
        Logger::TraceVerbose(
          (wchar_t *)L"%s: Found AAD user key with name %s. Skipping...",
          L"KeyManager::DeleteContainer",
          *((_QWORD *)hMem + 4));
      }
      Logger::TraceVerbose(
        (wchar_t *)L"%s: User ID key is not found. SID: \"%s\", IDP domain: \"\", Tenant domain: \"\", User ID: \"\", Error code: 0x%08x.",
        L"KeyManager::DeleteContainer",
        v12,
        2148073514LL);
      LocalCredential = KeyManager::FindLocalCredential(v12, &v30);
      UserSid = LocalCredential;
      if ( LocalCredential < 0 )
      {
        v15 = L"KeyManager::FindLocalCredential";
        goto LABEL_19;
      }
      if ( v30 )
      {
LABEL_15:
        LocalCredential = KeyManager::DeleteUserKey((KeyManager *)this, v12);
        UserSid = LocalCredential;
        if ( LocalCredential >= 0 )
          goto LABEL_51;
        if ( a3 )
        {
          Logger::TraceVerbose(
            (wchar_t *)L"%s: KeyManager::DeleteUserKey failed with error code: 0x%08x. Ignore this error as requested...",
            L"KeyManager::DeleteContainer",
            (unsigned int)LocalCredential);
          UserSid = 0;
          goto LABEL_51;
        }
        v15 = L"KeyManager::DeleteUserKey";
        goto LABEL_19;
      }
      v11 = 1;
      Logger::TraceVerbose(
        (wchar_t *)L"%s: No user ID key or local PIN is found in the default container. Delete it.",
        L"KeyManager::DeleteContainer");
    }
    v16 = a4 != 0 ? 4 : 1;
    v17 = NgcDeleteContainerEx(v12, v16);
    UserSid = v17;
    if ( v17 == -2147023728 || v17 == -2146893807 )
    {
      v26[0] = v17;
      Logger::TraceVerbose(
        (wchar_t *)L"%s: NgcDeleteContainerEx failed because the container is not found. Ignoring this error. SID: %s, Fla"
                    "g: %d, Error code: 0x%08x.",
        L"KeyManager::DeleteContainer",
        v12,
        v16,
        *(_QWORD *)v26);
      UserSid = 0;
    }
    else
    {
      if ( v17 < 0 )
      {
        if ( (Microsoft_Windows_User_Device_RegistrationEnableBits & 2) != 0 )
        {
          v19 = McTemplateU0zzzd_EventWriteTransfer(
                  v18,
                  (unsigned int)NgcDeleteContainerFailureEvent,
                  (_DWORD)v12,
                  0,
                  0,
                  v17);
          if ( v19 )
            Logger::TraceError(
              L"%s: %s failed with win32 error code: 0x%08x.",
              L"Logger::WriteNgcDeleteContainerFailureEvent",
              L"EventWriteNgcDeleteContainerFailureEvent",
              v19);
        }
        v26[0] = UserSid;
        Logger::TraceError(
          L"%s: NgcDeleteContainerEx failed. SID: %s, Flag: %d, Error code: 0x%08x.",
          L"KeyManager::DeleteContainer",
          v12,
          v16,
          *(_QWORD *)v26);
        goto LABEL_51;
      }
      if ( (Microsoft_Windows_User_Device_RegistrationEnableBits & 1) != 0 )
      {
        v20 = McTemplateU0zzz_EventWriteTransfer(v18, (unsigned int)ContainerDeleteSuccessEvent, (_DWORD)v12, 0, 0);
        if ( v20 )
          Logger::TraceError(
            L"%s: %s failed with win32 error code: 0x%08x.",
            L"Logger::WriteContainerDeleteSuccessEvent",
            L"EventWriteContainerDeleteSuccessEvent",
            v20);
      }
      Logger::TraceInformation(
        L"%s: NgcDeleteContainerEx succeeded. SID: %s, Flag: %d.",
        L"KeyManager::DeleteContainer",
        v12,
        v16);
    }
    *((_DWORD *)this + 14) = 0;
    if ( v11 || (UserSid = KeyManager::FindLocalCredential(v12, &v30), UserSid >= 0) )
    {
      v21 = v30;
    }
    else
    {
      v21 = 0;
      v30 = 0;
      UserSid = 0;
    }
    if ( v21 )
    {
      if ( (unsigned __int8)IsNgcLocalRemoveCredentialPresent() )
      {
        v22 = NgcLocalRemoveCredential(v12, 0);
        UserSid = v22;
        if ( v22 >= 0 )
        {
          Logger::TraceVerbose((wchar_t *)L"%s: Local PIN was deleted. SID: %s.", L"KeyManager::DeleteContainer", v12);
        }
        else
        {
          if ( (Microsoft_Windows_User_Device_RegistrationEnableBits & 4) != 0 )
          {
            v24 = McTemplateU0zq_EventWriteTransfer(v23, NgcLocalRemoveCredsFailureEvent, v12, (unsigned int)v22);
            if ( v24 )
              Logger::TraceError(
                L"%s: %s failed with win32 error code: 0x%08x.",
                L"Logger::WriteNgcLocalRemoveCredsFailureEvent",
                L"EventWriteNgcLocalRemoveCredsFailureEvent",
                v24);
          }
          Logger::TraceWarning(
            (wchar_t *)L"%s: Cannot delete local PIN. NgcLocalRemoveCredential failed. SID: %s, Error code: 0x%08x.",
            L"KeyManager::DeleteContainer",
            v12,
            (unsigned int)UserSid);
          UserSid = 0;
        }
      }
      else
      {
        Logger::TraceVerbose((wchar_t *)L"%s: Local PINs are not supported", L"KeyManager::DeleteContainer");
      }
    }
  }
LABEL_51:
  LocalFree(hMem);
  NgcFreeEnumState(v29);
  Logger::TraceVerbose((wchar_t *)L"%s - hr: 0x%08x", L"KeyManager::DeleteContainer", (unsigned int)UserSid);
  return (unsigned int)UserSid;
}

```

## disassembly

```asm
0x1800822b0  mov     [rsp-38h+arg_0], rbx
0x1800822b5  push    rbp
0x1800822b6  push    rsi
0x1800822b7  push    rdi
0x1800822b8  push    r12
0x1800822ba  push    r13
0x1800822bc  push    r14
0x1800822be  push    r15
0x1800822c0  mov     rbp, rsp
0x1800822c3  sub     rsp, 50h
0x1800822c7  xor     edi, edi
0x1800822c9  lea     rax, aFalse_0; "FALSE"
0x1800822d0  mov     r13b, r8b
0x1800822d3  mov     [rbp+var_18], rdi
0x1800822d7  mov     r12b, r9b
0x1800822da  mov     [rbp+hMem], rdi
0x1800822de  lea     r8, aTrue_0; "TRUE"
0x1800822e5  mov     [rbp+var_10], rdi
0x1800822e9  mov     r9, r8
0x1800822ec  mov     [rbp+arg_8], edi
0x1800822ef  test    r13b, r13b
0x1800822f2  mov     [rbp+arg_10], edi
0x1800822f5  mov     sil, dl
0x1800822f8  mov     r15, rcx
0x1800822fb  cmovz   r9, rax
0x1800822ff  lea     rcx, aSStartedForceS; "%s: started. force = %s, ignoreDeleteKe"...
0x180082306  test    dl, dl
0x180082308  lea     rdx, aKeymanagerDele; "KeyManager::DeleteContainer"
0x18008230f  cmovz   r8, rax
0x180082313  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x180082318  lea     rdx, [rbp+var_18]; unsigned __int16 **
0x18008231c  mov     rcx, r15; this
0x18008231f  call    ?GetUserSid@KeyManager@@AEAAJPEAPEAG@Z; KeyManager::GetUserSid(ushort * *)
0x180082324  mov     ebx, eax
0x180082326  test    eax, eax
0x180082328  js      loc_1800826D1
0x18008232e  mov     r14d, edi
0x180082331  mov     rdi, [rbp+var_18]
0x180082335  test    sil, sil
0x180082338  jnz     loc_1800824DE
0x18008233e  lea     r14, cchOriginalDestLength
0x180082345  xor     esi, esi
0x180082347  mov     rcx, [rbp+hMem]; hMem
0x18008234b  call    cs:__imp_LocalFree
0x180082351  lea     rax, [rbp+var_10]
0x180082355  mov     [rbp+hMem], rsi
0x180082359  mov     [rsp+50h+var_28], rax
0x18008235e  mov     r9, rdi
0x180082361  lea     rax, [rbp+hMem]
0x180082365  mov     r8, r14
0x180082368  mov     rdx, r14
0x18008236b  mov     qword ptr [rsp+50h+var_30], rax
0x180082370  mov     rcx, r14
0x180082373  call    cs:__imp_NgcEnumUserIdKeys
0x180082379  mov     ebx, eax
0x18008237b  mov     eax, 8009002Ah
0x180082380  cmp     ebx, eax
0x180082382  jz      loc_180082481
0x180082388  test    ebx, ebx
0x18008238a  js      loc_18008244E
0x180082390  mov     rcx, [rbp+hMem]
0x180082394  test    rcx, rcx
0x180082397  jnz     short loc_1800823B6
0x180082399  mov     r9d, ebx
0x18008239c  lea     rdx, aKeymanagerDele; "KeyManager::DeleteContainer"
0x1800823a3  mov     r8, rdi
0x1800823a6  lea     rcx, aSNgcenumuserid_0; "%s: NgcEnumUserIdKeys returns NULL pKey"...
0x1800823ad  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800823b2  mov     rcx, [rbp+hMem]
0x1800823b6  mov     rdx, [r15+10h]; unsigned __int16 *
0x1800823ba  lea     r9, [rbp+arg_10]; int *
0x1800823be  mov     rcx, [rcx]; lpString1
0x1800823c1  xor     r8d, r8d; unsigned int
0x1800823c4  call    ?StringCompare@@YAJPEBG0KPEAH@Z; StringCompare(ushort const *,ushort const *,ulong,int *)
0x1800823c9  lea     rdx, aKeymanagerDele; "KeyManager::DeleteContainer"
0x1800823d0  mov     ebx, eax
0x1800823d2  test    eax, eax
0x1800823d4  js      short loc_18008243B
0x1800823d6  cmp     [rbp+arg_10], esi
0x1800823d9  jz      short loc_1800823F4
0x1800823db  mov     r8, [rbp+hMem]
0x1800823df  lea     rcx, aSFoundAadUserK; "%s: Found AAD user key with name %s. Sk"...
0x1800823e6  mov     r8, [r8+20h]
0x1800823ea  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x1800823ef  jmp     loc_180082347
0x1800823f4  lea     rcx, aSFoundNonAadUs; "%s: Found non AAD user ID key. Will not"...
0x1800823fb  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x180082400  mov     rdx, rdi; unsigned __int16 *
0x180082403  mov     rcx, r15; this
0x180082406  call    ?DeleteUserKey@KeyManager@@AEAAJPEBG@Z; KeyManager::DeleteUserKey(ushort const *)
0x18008240b  mov     ebx, eax
0x18008240d  test    eax, eax
0x18008240f  jns     loc_1800826D1
0x180082415  lea     rdx, aKeymanagerDele; "KeyManager::DeleteContainer"
0x18008241c  test    r13b, r13b
0x18008241f  jz      loc_18008257D
0x180082425  mov     r8d, eax
0x180082428  lea     rcx, aSKeymanagerDel; "%s: KeyManager::DeleteUserKey failed wi"...
0x18008242f  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x180082434  mov     ebx, esi
0x180082436  jmp     loc_1800826D1
0x18008243b  lea     r8, aStringcompare; "StringCompare"
0x180082442  mov     r9d, eax
0x180082445  lea     rcx, aSSFailedWithEr_2; "%s: %s failed with error code: 0x%08x."
0x18008244c  jmp     short loc_180082477
0x18008244e  mov     r9, r14; unsigned __int16 *
0x180082451  mov     [rsp+50h+var_30], ebx; int
0x180082455  mov     r8, r14; unsigned __int16 *
0x180082458  mov     rdx, r14; unsigned __int16 *
0x18008245b  mov     rcx, rdi; unsigned __int16 *
0x18008245e  call    ?WriteNgcEnumUserIdKeysFailureEvent@Logger@@SAJPEBG000J@Z; Logger::WriteNgcEnumUserIdKeysFailureEvent(ushort const *,ushort const *,ushort const *,ushort const *,long)
0x180082463  mov     r9d, ebx
0x180082466  lea     rdx, aKeymanagerDele; "KeyManager::DeleteContainer"
0x18008246d  mov     r8, rdi
0x180082470  lea     rcx, aSCannotFindUse; "%s: Cannot find user ID key. NgcEnumUse"...
0x180082477  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18008247c  jmp     loc_1800826D1
0x180082481  mov     r9d, eax
0x180082484  lea     rdx, aKeymanagerDele; "KeyManager::DeleteContainer"
0x18008248b  mov     r8, rdi
0x18008248e  lea     rcx, aSUserIdKeyIsNo_0; "%s: User ID key is not found. SID: \"%s"...
0x180082495  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x18008249a  lea     rdx, [rbp+arg_8]; int *
0x18008249e  mov     rcx, rdi; unsigned __int16 *
0x1800824a1  call    ?FindLocalCredential@KeyManager@@CAJPEAGPEAH@Z; KeyManager::FindLocalCredential(ushort *,int *)
0x1800824a6  mov     ebx, eax
0x1800824a8  test    eax, eax
0x1800824aa  jns     short loc_1800824BC
0x1800824ac  lea     r8, aKeymanagerFind; "KeyManager::FindLocalCredential"
0x1800824b3  lea     rdx, aKeymanagerDele; "KeyManager::DeleteContainer"
0x1800824ba  jmp     short loc_180082442
0x1800824bc  cmp     [rbp+arg_8], esi
0x1800824bf  jnz     loc_180082400
0x1800824c5  lea     rdx, aKeymanagerDele; "KeyManager::DeleteContainer"
0x1800824cc  mov     r14d, 1
0x1800824d2  lea     rcx, aSNoUserIdKeyOr; "%s: No user ID key or local PIN is foun"...
0x1800824d9  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x1800824de  neg     r12b
0x1800824e1  mov     rcx, rdi
0x1800824e4  sbb     esi, esi
0x1800824e6  and     esi, 3
0x1800824e9  inc     esi
0x1800824eb  mov     edx, esi
0x1800824ed  call    cs:__imp_NgcDeleteContainerEx
0x1800824f3  lea     r12, Str; "%s: %s failed with win32 error code: 0x"...
0x1800824fa  mov     ebx, eax
0x1800824fc  cmp     eax, 80070490h
0x180082501  jz      loc_1800825E5
0x180082507  cmp     eax, 80090011h
0x18008250c  jz      loc_1800825E5
0x180082512  test    eax, eax
0x180082514  jns     short loc_180082589
0x180082516  test    cs:Microsoft_Windows_User_Device_RegistrationEnableBits, 2
0x18008251d  jz      short loc_18008255B
0x18008251f  mov     dword ptr [rsp+50h+var_28], eax
0x180082523  lea     rdx, NgcDeleteContainerFailureEvent
0x18008252a  xor     r9d, r9d
0x18008252d  mov     qword ptr [rsp+50h+var_30], 0
0x180082536  mov     r8, rdi
0x180082539  call    McTemplateU0zzzd_EventWriteTransfer
0x18008253e  test    eax, eax
0x180082540  jz      short loc_18008255B
0x180082542  mov     r9d, eax
0x180082545  lea     r8, aEventwritengcd_3; "EventWriteNgcDeleteContainerFailureEven"...
0x18008254c  lea     rdx, aLoggerWritengc_14; "Logger::WriteNgcDeleteContainerFailureE"...
0x180082553  mov     rcx, r12; unsigned __int16 *
0x180082556  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18008255b  mov     r9d, esi
0x18008255e  mov     [rsp+50h+var_30], ebx
0x180082562  mov     r8, rdi
0x180082565  lea     rdx, aKeymanagerDele; "KeyManager::DeleteContainer"
0x18008256c  lea     rcx, aSNgcdeletecont_0; "%s: NgcDeleteContainerEx failed. SID: %"...
0x180082573  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180082578  jmp     loc_1800826D1
0x18008257d  lea     r8, aKeymanagerDele_0; "KeyManager::DeleteUserKey"
0x180082584  jmp     loc_180082442
0x180082589  test    cs:Microsoft_Windows_User_Device_RegistrationEnableBits, 1
0x180082590  jz      short loc_1800825CA
0x180082592  xor     r9d, r9d
0x180082595  mov     qword ptr [rsp+50h+var_30], 0
0x18008259e  mov     r8, rdi
0x1800825a1  lea     rdx, ContainerDeleteSuccessEvent
0x1800825a8  call    McTemplateU0zzz_EventWriteTransfer
0x1800825ad  test    eax, eax
0x1800825af  jz      short loc_1800825CA
0x1800825b1  mov     r9d, eax
0x1800825b4  lea     r8, aEventwritecont; "EventWriteContainerDeleteSuccessEvent"
0x1800825bb  lea     rdx, aLoggerWritecon; "Logger::WriteContainerDeleteSuccessEven"...
0x1800825c2  mov     rcx, r12; unsigned __int16 *
0x1800825c5  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800825ca  mov     r9d, esi
0x1800825cd  lea     rdx, aKeymanagerDele; "KeyManager::DeleteContainer"
0x1800825d4  mov     r8, rdi
0x1800825d7  lea     rcx, aSNgcdeletecont_1; "%s: NgcDeleteContainerEx succeeded. SID"...
0x1800825de  call    ?TraceInformation@Logger@@SAJPEBGZZ; Logger::TraceInformation(ushort const *,...)
0x1800825e3  jmp     short loc_180082604
0x1800825e5  mov     r9d, esi
0x1800825e8  mov     [rsp+50h+var_30], ebx
0x1800825ec  mov     r8, rdi
0x1800825ef  lea     rdx, aKeymanagerDele; "KeyManager::DeleteContainer"
0x1800825f6  lea     rcx, aSNgcdeletecont; "%s: NgcDeleteContainerEx failed because"...
0x1800825fd  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x180082602  xor     ebx, ebx
0x180082604  mov     dword ptr [r15+38h], 0
0x18008260c  test    r14d, r14d
0x18008260f  jnz     short loc_18008262C
0x180082611  lea     rdx, [rbp+arg_8]; int *
0x180082615  mov     rcx, rdi; unsigned __int16 *
0x180082618  call    ?FindLocalCredential@KeyManager@@CAJPEAGPEAH@Z; KeyManager::FindLocalCredential(ushort *,int *)
0x18008261d  mov     ebx, eax
0x18008261f  test    eax, eax
0x180082621  jns     short loc_18008262C
0x180082623  xor     eax, eax
0x180082625  mov     [rbp+arg_8], eax
0x180082628  xor     ebx, ebx
0x18008262a  jmp     short loc_18008262F
0x18008262c  mov     eax, [rbp+arg_8]
0x18008262f  test    eax, eax
0x180082631  jz      loc_1800826D1
0x180082637  call    IsNgcLocalRemoveCredentialPresent
0x18008263c  test    al, al
0x18008263e  jz      short loc_1800826BE
0x180082640  xor     edx, edx
0x180082642  mov     rcx, rdi
0x180082645  call    cs:__imp_NgcLocalRemoveCredential
0x18008264b  mov     ebx, eax
0x18008264d  test    eax, eax
0x18008264f  jns     short loc_1800826A6
0x180082651  test    cs:Microsoft_Windows_User_Device_RegistrationEnableBits, 4
0x180082658  jz      short loc_180082689
0x18008265a  mov     r9d, eax
0x18008265d  lea     rdx, NgcLocalRemoveCredsFailureEvent
0x180082664  mov     r8, rdi
0x180082667  call    McTemplateU0zq_EventWriteTransfer
0x18008266c  test    eax, eax
0x18008266e  jz      short loc_180082689
0x180082670  mov     r9d, eax
0x180082673  lea     r8, aEventwritengcl_0; "EventWriteNgcLocalRemoveCredsFailureEve"...
0x18008267a  lea     rdx, aLoggerWritengc_1; "Logger::WriteNgcLocalRemoveCredsFailure"...
0x180082681  mov     rcx, r12; unsigned __int16 *
0x180082684  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180082689  mov     r9d, ebx
0x18008268c  lea     rdx, aKeymanagerDele; "KeyManager::DeleteContainer"
0x180082693  mov     r8, rdi
0x180082696  lea     rcx, aSCannotDeleteL; "%s: Cannot delete local PIN. NgcLocalRe"...
0x18008269d  call    ?TraceWarning@Logger@@SAJPEBGZZ; Logger::TraceWarning(ushort const *,...)
0x1800826a2  xor     ebx, ebx
0x1800826a4  jmp     short loc_1800826D1
0x1800826a6  mov     r8, rdi
0x1800826a9  lea     rdx, aKeymanagerDele; "KeyManager::DeleteContainer"
0x1800826b0  lea     rcx, aSLocalPinWasDe; "%s: Local PIN was deleted. SID: %s."
0x1800826b7  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x1800826bc  jmp     short loc_1800826D1
0x1800826be  lea     rdx, aKeymanagerDele; "KeyManager::DeleteContainer"
0x1800826c5  lea     rcx, aSLocalPinsAreN; "%s: Local PINs are not supported"
0x1800826cc  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x1800826d1  mov     rcx, [rbp+hMem]; hMem
0x1800826d5  call    cs:__imp_LocalFree
0x1800826db  mov     rcx, [rbp+var_10]
0x1800826df  call    cs:__imp_NgcFreeEnumState
0x1800826e5  mov     r8d, ebx
0x1800826e8  lea     rdx, aKeymanagerDele; "KeyManager::DeleteContainer"
0x1800826ef  lea     rcx, aSHr0x08x; "%s - hr: 0x%08x"
0x1800826f6  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x1800826fb  mov     eax, ebx
0x1800826fd  mov     rbx, [rsp+50h+arg_0]
0x180082705  add     rsp, 50h
0x180082709  pop     r15
0x18008270b  pop     r14
0x18008270d  pop     r13
0x18008270f  pop     r12
0x180082711  pop     rdi
0x180082712  pop     rsi
0x180082713  pop     rbp
0x180082714  retn
```
