# AadPluginController::AddUserSidsToLocalGroup(ushort const * *,unsigned __int64,ushort const *,AadPluginController::_AADPLUGIN_ROLLBACK_CONTEXT *)

- ea: `0x18003fce4`
- end: `0x18004000b`
- name: `?AddUserSidsToLocalGroup@AadPluginController@@AEAAJPEAPEBG_KPEBGPEAU_AADPLUGIN_ROLLBACK_CONTEXT@1@@Z`
- size: `807`
- prototype: `__int64 __fastcall(AadPluginController *this, const unsigned __int16 **, unsigned __int64, const unsigned __int16 *, struct AadPluginController::_AADPLUGIN_ROLLBACK_CONTEXT *)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18004d1b4`

## callees

- `0x180005ba0`
- `0x1800084f4`
- `0x18000bac0`
- `0x180012948`
- `0x1800307c4`
- `0x18003334c`
- `0x18003fce4`
- `0x180040014`
- `0x180040330`
- `0x180043ef8`
- `0x18004654c`
- `0x18004cd68`
- `0x1800900a4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003fd9d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003fe1a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003fec9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003fd9d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003fe1a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003fec9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003ffcc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003ffcc`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18003fd93`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18003fd93`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x18003fe12`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x18003febf`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x18003fe12`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x18003febf`

## string_xrefs

- `0x18003ff1a`: `Logger::WriteLookupSidFailureEvent`
- `0x18003ff13`: `EventWriteLookupSidFailureEvent`
- `0x18003fdc8`: `ConvertStringSidToSidW`
- `0x18003fd0a`: `AadPluginController::AddUserSidsToLocalGroup`
- `0x18003fd52`: `AadPluginController::AddUserSidsToLocalGroup`
- `0x18003fdd6`: `AadPluginController::AddUserSidsToLocalGroup`
- `0x18003fe53`: `AadPluginController::AddUserSidsToLocalGroup`
- `0x18003ff8f`: `AadPluginController::AddUserSidsToLocalGroup`
- `0x18003ffdd`: `AadPluginController::AddUserSidsToLocalGroup`
- `0x18003fd30`: `pRollbackContext`
- `0x18003fd4b`: `pRollbackContext`
- `0x18003ffa4`: `%s: The user SID list is empty.`
- `0x18003ff31`: `LookupAccountSidW`
- `0x18003ff57`: `AadPluginController::AddGroupToRollbackContext`
- `0x18003ff88`: `AadPluginController::AddUserSidToLocalGroup`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall AadPluginController::AddUserSidsToLocalGroup(
        AadPluginController *this,
        const unsigned __int16 **a2,
        unsigned __int64 a3,
        const unsigned __int16 *a4,
        struct AadPluginController::_AADPLUGIN_ROLLBACK_CONTEXT *a5)
{
  WCHAR *v8; // rsi
  WCHAR *v9; // r13
  signed int v10; // ebx
  const WCHAR *v11; // rcx
  __int64 v12; // r9
  signed int LastError; // eax
  const wchar_t *v14; // r8
  const unsigned __int16 *v15; // r9
  BOOL v16; // ebx
  signed int v17; // eax
  AadPluginController *v18; // rcx
  unsigned __int64 v19; // rax
  unsigned __int64 v20; // rax
  unsigned int v21; // eax
  int v22; // eax
  AadPluginController *v23; // rcx
  unsigned __int64 i; // rdi
  int v25; // eax
  LPWSTR ReferencedDomainName; // [rsp+20h] [rbp-40h]
  DWORD cchName; // [rsp+40h] [rbp-20h] BYREF
  enum _SID_NAME_USE peUse; // [rsp+44h] [rbp-1Ch] BYREF
  PSID Sid; // [rsp+48h] [rbp-18h] BYREF
  struct AadPluginController::_MEMBERSHIP_CHANGE *v31; // [rsp+50h] [rbp-10h] BYREF
  DWORD cchReferencedDomainName; // [rsp+90h] [rbp+30h] BYREF
  int v33; // [rsp+94h] [rbp+34h]

  v33 = HIDWORD(this);
  v8 = 0;
  v9 = 0;
  cchName = 0;
  cchReferencedDomainName = 0;
  peUse = 0;
  Sid = 0;
  v31 = 0;
  if ( !a5 )
  {
    v10 = -2147024809;
    Logger::TraceError(
      L"%s: \"%s\" should not be null.",
      L"AadPluginController::AddUserSidsToLocalGroup",
      L"pRollbackContext");
    Logger::WriteNullOrEmptyParameterFailureEvent(L"AadPluginController::AddUserSidsToLocalGroup", L"pRollbackContext");
    goto LABEL_44;
  }
  v10 = 0;
  if ( (unsigned int)IsEmptyString(a4) )
  {
    Logger::TraceInformation(L"%s: The local group name is empty.", v12);
    goto LABEL_44;
  }
  if ( a3 && a2 )
  {
    if ( !ConvertStringSidToSidW(v11, &Sid) )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        v10 = (unsigned __int16)LastError | 0x80070000;
      else
        v10 = LastError;
      if ( v10 >= 0 )
        v10 = -2147023537;
      Logger::WriteConvertStringSidFailureEvent(a4, LastError);
      v14 = L"ConvertStringSidToSidW";
LABEL_14:
      v15 = a4;
      LODWORD(ReferencedDomainName) = v10;
LABEL_15:
      Logger::TraceError(
        L"%s: %s(%s) failed with error code: 0x%08x.",
        L"AadPluginController::AddUserSidsToLocalGroup",
        v14,
        v15,
        ReferencedDomainName);
      goto LABEL_44;
    }
    v16 = LookupAccountSidW(0, Sid, 0, &cchName, 0, &cchReferencedDomainName, &peUse);
    v17 = GetLastError();
    if ( v17 == 122 )
    {
      v19 = 2LL * cchName;
      if ( !is_mul_ok(cchName, 2u) )
        v19 = -1;
      v8 = (WCHAR *)operator new[](v19, (const struct std::nothrow_t *)&std::nothrow);
      if ( !v8 )
        goto LABEL_20;
      v20 = 2LL * cchReferencedDomainName;
      if ( !is_mul_ok(cchReferencedDomainName, 2u) )
        v20 = -1;
      v9 = (WCHAR *)operator new[](v20, (const struct std::nothrow_t *)&std::nothrow);
      if ( !v9 )
      {
LABEL_20:
        v10 = -2147024882;
        Logger::TraceCritical(L"%s: Out of memory. Allocation failed.", L"AadPluginController::AddUserSidsToLocalGroup");
        goto LABEL_44;
      }
      if ( !LookupAccountSidW(0, Sid, v8, &cchName, v9, &cchReferencedDomainName, &peUse) )
      {
        v17 = GetLastError();
LABEL_27:
        if ( v17 > 0 )
          v10 = (unsigned __int16)v17 | 0x80070000;
        else
          v10 = v17;
        if ( v10 >= 0 )
          v10 = -2147023537;
        if ( (Microsoft_Windows_User_Device_RegistrationEnableBits & 1) != 0 )
        {
          v21 = McTemplateU0kq_EventWriteTransfer(2147943759LL, LookupSidFailureEvent, Sid, (unsigned int)v17);
          if ( v21 )
            Logger::TraceError(
              L"%s: %s failed with win32 error code: 0x%08x.",
              L"Logger::WriteLookupSidFailureEvent",
              L"EventWriteLookupSidFailureEvent",
              v21);
        }
        v14 = L"LookupAccountSidW";
        goto LABEL_14;
      }
    }
    else if ( !v16 )
    {
      goto LABEL_27;
    }
    v22 = AadPluginController::AddGroupToRollbackContext(v18, v8, a5, &v31);
    v10 = v22;
    if ( v22 < 0 )
    {
      LODWORD(ReferencedDomainName) = v22;
      v14 = L"AadPluginController::AddGroupToRollbackContext";
      v15 = v8;
      goto LABEL_15;
    }
    for ( i = 0; i < a3; ++i )
    {
      v25 = AadPluginController::AddUserSidToLocalGroup(v23, a2[i], v31);
      v10 = v25;
      if ( v25 < 0 )
      {
        Logger::TraceError(
          L"%s: %s failed with error code: 0x%08x.",
          L"AadPluginController::AddUserSidsToLocalGroup",
          L"AadPluginController::AddUserSidToLocalGroup",
          (unsigned int)v25);
        break;
      }
    }
  }
  else
  {
    Logger::TraceInformation(L"%s: The user SID list is empty.", v12);
  }
LABEL_44:
  operator delete(v8);
  operator delete(v9);
  if ( Sid )
  {
    LocalFree(Sid);
    Sid = 0;
  }
  Logger::TraceVerbose(
    (wchar_t *)L"%s - hr: 0x%08x",
    L"AadPluginController::AddUserSidsToLocalGroup",
    (unsigned int)v10);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18003fce4  mov     [rsp-28h+arg_8], rbx
0x18003fce9  mov     [rsp-28h+arg_10], rsi
0x18003fcee  mov     qword ptr [rsp-28h+arg_0], rcx
0x18003fcf3  push    rbp
0x18003fcf4  push    rdi
0x18003fcf5  push    r12
0x18003fcf7  push    r13
0x18003fcf9  push    r14
0x18003fcfb  mov     rbp, rsp
0x18003fcfe  sub     rsp, 60h
0x18003fd02  mov     r12, rdx
0x18003fd05  mov     rdi, r9
0x18003fd08  xor     edx, edx
0x18003fd0a  lea     r9, aAadplugincontr_0; "AadPluginController::AddUserSidsToLocal"...
0x18003fd11  mov     r14, r8
0x18003fd14  mov     esi, edx
0x18003fd16  mov     r13d, edx
0x18003fd19  mov     [rbp+cchName], edx
0x18003fd1c  mov     [rbp+arg_0], edx
0x18003fd1f  mov     [rbp+var_1C], edx
0x18003fd22  mov     [rbp+Sid], rdx
0x18003fd26  mov     [rbp+var_10], rdx
0x18003fd2a  cmp     [rbp+arg_20], rdx
0x18003fd2e  jnz     short loc_18003FD63
0x18003fd30  lea     r8, aProllbackconte; "pRollbackContext"
0x18003fd37  mov     rdx, r9
0x18003fd3a  lea     rcx, aSSShouldNotBeN_0; "%s: \"%s\" should not be null."
0x18003fd41  mov     ebx, 80070057h
0x18003fd46  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18003fd4b  lea     rdx, aProllbackconte; "pRollbackContext"
0x18003fd52  lea     rcx, aAadplugincontr_0; "AadPluginController::AddUserSidsToLocal"...
0x18003fd59  call    ?WriteNullOrEmptyParameterFailureEvent@Logger@@SAJPEBG0@Z; Logger::WriteNullOrEmptyParameterFailureEvent(ushort const *,ushort const *)
0x18003fd5e  jmp     loc_18003FFB3
0x18003fd63  mov     rcx, rdi; unsigned __int16 *
0x18003fd66  mov     ebx, edx
0x18003fd68  call    ?IsEmptyString@@YAHPEBG@Z; IsEmptyString(ushort const *)
0x18003fd6d  test    eax, eax
0x18003fd6f  jz      short loc_18003FD7D
0x18003fd71  lea     rcx, aSTheLocalGroup; "%s: The local group name is empty."
0x18003fd78  jmp     loc_18003FFAB
0x18003fd7d  test    r14, r14
0x18003fd80  jz      loc_18003FFA4
0x18003fd86  test    r12, r12
0x18003fd89  jz      loc_18003FFA4
0x18003fd8f  lea     rdx, [rbp+Sid]; Sid
0x18003fd93  call    cs:__imp_ConvertStringSidToSidW
0x18003fd99  test    eax, eax
0x18003fd9b  jnz     short loc_18003FDEE
0x18003fd9d  call    cs:__imp_GetLastError
0x18003fda3  test    eax, eax
0x18003fda5  jg      short loc_18003FDAB
0x18003fda7  mov     ebx, eax
0x18003fda9  jmp     short loc_18003FDB4
0x18003fdab  movzx   ebx, ax
0x18003fdae  or      ebx, 80070000h
0x18003fdb4  test    ebx, ebx
0x18003fdb6  mov     ecx, 8007054Fh
0x18003fdbb  mov     edx, eax; unsigned int
0x18003fdbd  cmovns  ebx, ecx
0x18003fdc0  mov     rcx, rdi; unsigned __int16 *
0x18003fdc3  call    ?WriteConvertStringSidFailureEvent@Logger@@SAJPEBGK@Z; Logger::WriteConvertStringSidFailureEvent(ushort const *,ulong)
0x18003fdc8  lea     r8, aConvertstrings_1; "ConvertStringSidToSidW"
0x18003fdcf  mov     r9, rdi
0x18003fdd2  mov     dword ptr [rsp+60h+ReferencedDomainName], ebx
0x18003fdd6  lea     rdx, aAadplugincontr_0; "AadPluginController::AddUserSidsToLocal"...
0x18003fddd  lea     rcx, aSSSFailedWithE; "%s: %s(%s) failed with error code: 0x%0"...
0x18003fde4  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18003fde9  jmp     loc_18003FFB3
0x18003fdee  mov     rdx, [rbp+Sid]; Sid
0x18003fdf2  lea     rax, [rbp+var_1C]
0x18003fdf6  mov     [rsp+60h+peUse], rax; peUse
0x18003fdfb  lea     r9, [rbp+cchName]; cchName
0x18003fdff  lea     rax, [rbp+arg_0]
0x18003fe03  xor     r8d, r8d; Name
0x18003fe06  mov     [rsp+60h+cchReferencedDomainName], rax; cchReferencedDomainName
0x18003fe0b  xor     ecx, ecx; lpSystemName
0x18003fe0d  mov     [rsp+60h+ReferencedDomainName], rbx; ReferencedDomainName
0x18003fe12  call    cs:__imp_LookupAccountSidW
0x18003fe18  mov     ebx, eax
0x18003fe1a  call    cs:__imp_GetLastError
0x18003fe20  cmp     eax, 7Ah ; 'z'
0x18003fe23  jnz     loc_18003FED1
0x18003fe29  mov     ecx, [rbp+cchName]
0x18003fe2c  lea     ebx, [rax-78h]
0x18003fe2f  mov     eax, ebx
0x18003fe31  mul     rcx
0x18003fe34  lea     rcx, [rbx-3]
0x18003fe38  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18003fe3f  cmovb   rax, rcx
0x18003fe43  mov     rcx, rax; unsigned __int64
0x18003fe46  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18003fe4b  mov     rsi, rax
0x18003fe4e  test    rax, rax
0x18003fe51  jnz     short loc_18003FE70
0x18003fe53  lea     rdx, aAadplugincontr_0; "AadPluginController::AddUserSidsToLocal"...
0x18003fe5a  mov     ebx, 8007000Eh
0x18003fe5f  lea     rcx, aSOutOfMemoryAl_0; "%s: Out of memory. Allocation failed."
0x18003fe66  call    ?TraceCritical@Logger@@SAJPEBGZZ; Logger::TraceCritical(ushort const *,...)
0x18003fe6b  jmp     loc_18003FFB3
0x18003fe70  mov     ecx, [rbp+arg_0]
0x18003fe73  mov     rax, rbx
0x18003fe76  mul     rcx
0x18003fe79  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18003fe80  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18003fe87  cmovb   rax, rcx
0x18003fe8b  mov     rcx, rax; unsigned __int64
0x18003fe8e  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18003fe93  mov     r13, rax
0x18003fe96  test    rax, rax
0x18003fe99  jz      short loc_18003FE53
0x18003fe9b  mov     rdx, [rbp+Sid]; Sid
0x18003fe9f  lea     rax, [rbp+var_1C]
0x18003fea3  mov     [rsp+60h+peUse], rax; peUse
0x18003fea8  lea     r9, [rbp+cchName]; cchName
0x18003feac  lea     rax, [rbp+arg_0]
0x18003feb0  mov     r8, rsi; Name
0x18003feb3  mov     [rsp+60h+cchReferencedDomainName], rax; cchReferencedDomainName
0x18003feb8  xor     ecx, ecx; lpSystemName
0x18003feba  mov     [rsp+60h+ReferencedDomainName], r13; ReferencedDomainName
0x18003febf  call    cs:__imp_LookupAccountSidW
0x18003fec5  test    eax, eax
0x18003fec7  jnz     short loc_18003FF3D
0x18003fec9  call    cs:__imp_GetLastError
0x18003fecf  jmp     short loc_18003FED5
0x18003fed1  test    ebx, ebx
0x18003fed3  jnz     short loc_18003FF3D
0x18003fed5  test    eax, eax
0x18003fed7  jg      short loc_18003FEDD
0x18003fed9  mov     ebx, eax
0x18003fedb  jmp     short loc_18003FEE6
0x18003fedd  movzx   ebx, ax
0x18003fee0  or      ebx, 80070000h
0x18003fee6  test    ebx, ebx
0x18003fee8  mov     ecx, 8007054Fh
0x18003feed  cmovns  ebx, ecx
0x18003fef0  test    cs:Microsoft_Windows_User_Device_RegistrationEnableBits, 1
0x18003fef7  jz      short loc_18003FF31
0x18003fef9  mov     r8, [rbp+Sid]
0x18003fefd  lea     rdx, LookupSidFailureEvent
0x18003ff04  mov     r9d, eax
0x18003ff07  call    McTemplateU0kq_EventWriteTransfer
0x18003ff0c  test    eax, eax
0x18003ff0e  jz      short loc_18003FF2D
0x18003ff10  mov     r9d, eax
0x18003ff13  lea     r8, aEventwritelook; "EventWriteLookupSidFailureEvent"
0x18003ff1a  lea     rdx, aLoggerWriteloo; "Logger::WriteLookupSidFailureEvent"
0x18003ff21  lea     rcx, Str; "%s: %s failed with win32 error code: 0x"...
0x18003ff28  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18003ff2d  test    ebx, ebx
0x18003ff2f  jns     short loc_18003FF3D
0x18003ff31  lea     r8, aLookupaccounts_0; "LookupAccountSidW"
0x18003ff38  jmp     loc_18003FDCF
0x18003ff3d  mov     r8, [rbp+arg_20]; struct AadPluginController::_AADPLUGIN_ROLLBACK_CONTEXT *
0x18003ff41  lea     r9, [rbp+var_10]; struct AadPluginController::_MEMBERSHIP_CHANGE **
0x18003ff45  mov     rdx, rsi; unsigned __int16 *
0x18003ff48  call    ?AddGroupToRollbackContext@AadPluginController@@AEAAJPEBGPEAU_AADPLUGIN_ROLLBACK_CONTEXT@1@PEAPEAU_MEMBERSHIP_CHANGE@1@@Z; AadPluginController::AddGroupToRollbackContext(ushort const *,AadPluginController::_AADPLUGIN_ROLLBACK_CONTEXT *,AadPluginController::_MEMBERSHIP_CHANGE * *)
0x18003ff4d  mov     ebx, eax
0x18003ff4f  test    eax, eax
0x18003ff51  jns     short loc_18003FF66
0x18003ff53  mov     dword ptr [rsp+60h+ReferencedDomainName], eax
0x18003ff57  lea     r8, aAadplugincontr_11; "AadPluginController::AddGroupToRollback"...
0x18003ff5e  mov     r9, rsi
0x18003ff61  jmp     loc_18003FDD6
0x18003ff66  xor     edi, edi
0x18003ff68  cmp     rdi, r14
0x18003ff6b  jnb     short loc_18003FFB3
0x18003ff6d  mov     r8, [rbp+var_10]; struct AadPluginController::_MEMBERSHIP_CHANGE *
0x18003ff71  mov     rdx, [r12+rdi*8]; unsigned __int16 *
0x18003ff75  call    ?AddUserSidToLocalGroup@AadPluginController@@AEAAJPEBGPEAU_MEMBERSHIP_CHANGE@1@@Z; AadPluginController::AddUserSidToLocalGroup(ushort const *,AadPluginController::_MEMBERSHIP_CHANGE *)
0x18003ff7a  mov     ebx, eax
0x18003ff7c  test    eax, eax
0x18003ff7e  js      short loc_18003FF85
0x18003ff80  inc     rdi
0x18003ff83  jmp     short loc_18003FF68
0x18003ff85  mov     r9d, eax
0x18003ff88  lea     r8, aAadplugincontr_16; "AadPluginController::AddUserSidToLocalG"...
0x18003ff8f  lea     rdx, aAadplugincontr_0; "AadPluginController::AddUserSidsToLocal"...
0x18003ff96  lea     rcx, aSSFailedWithEr_2; "%s: %s failed with error code: 0x%08x."
0x18003ff9d  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18003ffa2  jmp     short loc_18003FFB3
0x18003ffa4  lea     rcx, aSTheUserSidLis; "%s: The user SID list is empty."
0x18003ffab  mov     rdx, r9
0x18003ffae  call    ?TraceInformation@Logger@@SAJPEBGZZ; Logger::TraceInformation(ushort const *,...)
0x18003ffb3  mov     rcx, rsi; Block
0x18003ffb6  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18003ffbb  mov     rcx, r13; Block
0x18003ffbe  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18003ffc3  mov     rcx, [rbp+Sid]; hMem
0x18003ffc7  test    rcx, rcx
0x18003ffca  jz      short loc_18003FFDA
0x18003ffcc  call    cs:__imp_LocalFree
0x18003ffd2  mov     [rbp+Sid], 0
0x18003ffda  mov     r8d, ebx
0x18003ffdd  lea     rdx, aAadplugincontr_0; "AadPluginController::AddUserSidsToLocal"...
0x18003ffe4  lea     rcx, aSHr0x08x; "%s - hr: 0x%08x"
0x18003ffeb  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x18003fff0  lea     r11, [rsp+60h+var_s0]
0x18003fff5  mov     eax, ebx
0x18003fff7  mov     rbx, [r11+38h]
0x18003fffb  mov     rsi, [r11+40h]
0x18003ffff  mov     rsp, r11
0x180040002  pop     r14
0x180040004  pop     r13
0x180040006  pop     r12
0x180040008  pop     rdi
0x180040009  pop     rbp
0x18004000a  retn
```
