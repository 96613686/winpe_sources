# AadPluginController::AddUserSidToLocalGroup(ushort const *,AadPluginController::_MEMBERSHIP_CHANGE *)

- ea: `0x180040014`
- end: `0x180040328`
- name: `?AddUserSidToLocalGroup@AadPluginController@@AEAAJPEBGPEAU_MEMBERSHIP_CHANGE@1@@Z`
- size: `788`
- prototype: `__int64 __fastcall(AadPluginController *this, const unsigned __int16 *, const wchar_t **)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18003fce4`

## callees

- `0x180005ba0`
- `0x1800084f4`
- `0x18000bac0`
- `0x180012948`
- `0x1800307c4`
- `0x180040014`
- `0x180040330`
- `0x1800432d0`
- `0x18004cf70`
- `0x180090f04`
- `0x180090fc0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040108`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040108`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800402fd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800402fd`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800400fe`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800400fe`
- `samcli!NetLocalGroupAddMembers` at `0x180040176`
- `samcli!NetLocalGroupAddMembers` at `0x180040176`

## string_xrefs

- `0x18004029f`: `EventWriteAddGroupMemberFailureEvent`
- `0x1800402a6`: `Logger::WriteAddGroupMemberFailureEvent`
- `0x1800402c4`: `%s: NetLocalGroupAddMembers failed with status 0x%x. User SID: %s; Group name: %s.`
- `0x18004011f`: `ConvertStringSidToSidW`
- `0x1800401aa`: `EventWriteAddGroupMemberSuccessEvent`
- `0x1800401b1`: `Logger::WriteAddGroupMemberSuccessEvent`
- `0x18004005a`: `AadPluginController::AddUserSidToLocalGroup`
- `0x180040064`: `%s started. User SID: %s. Group: %s.`
- `0x1800402e6`: `%s: Adding user SID to a local group. Either the SID is empty or the local group name is empty. SID: %s; Group: %s.`
- `0x1800401c7`: `%s: NetLocalGroupAddMembers succeeded. User SID: %s; Group name: %s.`
- `0x180040263`: `%s: NetLocalGroupAddMembers returned user "%s" already in group "%s" 0x%x.`
- `0x1800401fa`: `%s: AadPluginController::AddUserSidToRollbackContext failed to add user "%s" to group "%s" in rollback context. Error code: 0x%08x.`
- `0x180040220`: `%s: AadPluginController::RemoveUserSidFromLocalGroup succeeded. User SID: %s; Group Name: %s.`
- `0x18004023f`: `%s: AadPluginController::RemoveUserSidFromLocalGroup failed with error code 0x%08x. User SID: %s; Group Name: %s.`

## pseudocode

```c
__int64 __fastcall AadPluginController::AddUserSidToLocalGroup(
        AadPluginController *this,
        const unsigned __int16 *a2,
        const wchar_t **a3)
{
  bool v4; // zf
  const wchar_t *v5; // r8
  const wchar_t *v7; // r9
  DWORD LastError; // ebx
  const unsigned __int16 *v9; // rdx
  const unsigned __int16 *v10; // rdi
  __int64 v11; // rcx
  signed int v12; // ebp
  unsigned int v13; // eax
  AadPluginController *v14; // rcx
  int v15; // eax
  AadPluginController *v16; // rcx
  int v17; // eax
  unsigned int v18; // eax
  DWORD totalentries[2]; // [rsp+20h] [rbp-38h]
  PSID Sid; // [rsp+60h] [rbp+8h] BYREF
  PSID buf; // [rsp+68h] [rbp+10h] BYREF

  buf = 0;
  v4 = a3 == 0;
  Sid = 0;
  v5 = L"<NULL>";
  v7 = L"<NULL>";
  if ( !v4 && *a3 )
    v7 = *a3;
  if ( a2 )
    v5 = a2;
  Logger::TraceVerbose(
    (wchar_t *)L"%s started. User SID: %s. Group: %s.",
    L"AadPluginController::AddUserSidToLocalGroup",
    v5,
    v7);
  if ( !a3 )
  {
    LastError = -2147024809;
    Logger::TraceError(
      L"%s: \"%s\" should not be null.",
      L"AadPluginController::AddUserSidToLocalGroup",
      L"pGroupMembershipChange");
    v9 = L"pGroupMembershipChange";
LABEL_8:
    Logger::WriteNullOrEmptyParameterFailureEvent(L"AadPluginController::AddUserSidToLocalGroup", v9);
    goto LABEL_36;
  }
  v10 = *a3;
  if ( !*a3 )
  {
    LastError = -2147024809;
    Logger::TraceError(
      L"%s: \"%s\" should not be null.",
      L"AadPluginController::AddUserSidToLocalGroup",
      L"pGroupMembershipChange->pcszLocalGroup");
    v9 = L"pGroupMembershipChange->pcszLocalGroup";
    goto LABEL_8;
  }
  LastError = 0;
  if ( (unsigned int)IsEmptyString(a2) || (unsigned int)IsEmptyString(v10) )
  {
    Logger::TraceInformation(
      L"%s: Adding user SID to a local group. Either the SID is empty or the local group name is empty. SID: %s; Group: %s.",
      L"AadPluginController::AddUserSidToLocalGroup",
      a2,
      v10);
    goto LABEL_36;
  }
  if ( ConvertStringSidToSidW(a2, &Sid) )
  {
    buf = Sid;
    v12 = NetLocalGroupAddMembers(0, v10, 0, (LPBYTE)&buf, 1u);
    if ( v12 )
    {
      if ( v12 == 1378 )
      {
        totalentries[0] = 1378;
        Logger::TraceInformation(
          L"%s: NetLocalGroupAddMembers returned user \"%s\" already in group \"%s\" 0x%x.",
          L"AadPluginController::AddUserSidToLocalGroup",
          a2,
          v10,
          *(_QWORD *)totalentries);
        goto LABEL_36;
      }
      if ( (Microsoft_Windows_User_Device_RegistrationEnableBits & 1) != 0 )
      {
        v18 = McTemplateU0zkq_EventWriteTransfer(
                v11,
                (unsigned int)AddGroupMemberFailureEvent,
                (_DWORD)v10,
                (_DWORD)Sid,
                v12);
        if ( v18 )
          Logger::TraceError(
            L"%s: %s failed with win32 error code: 0x%08x.",
            L"Logger::WriteAddGroupMemberFailureEvent",
            L"EventWriteAddGroupMemberFailureEvent",
            v18);
      }
      Logger::TraceError(
        L"%s: NetLocalGroupAddMembers failed with status 0x%x. User SID: %s; Group name: %s.",
        L"AadPluginController::AddUserSidToLocalGroup",
        (unsigned int)v12,
        a2,
        v10);
      if ( v12 <= 0 )
      {
        LastError = v12;
        goto LABEL_36;
      }
      LastError = (unsigned __int16)v12;
      goto LABEL_18;
    }
    if ( (Microsoft_Windows_User_Device_RegistrationEnableBits & 1) != 0 )
    {
      v13 = McTemplateU0zk_EventWriteTransfer(v11, AddGroupMemberSuccessEvent, v10, Sid);
      if ( v13 )
        Logger::TraceError(
          L"%s: %s failed with win32 error code: 0x%08x.",
          L"Logger::WriteAddGroupMemberSuccessEvent",
          L"EventWriteAddGroupMemberSuccessEvent",
          v13);
    }
    Logger::TraceVerbose(
      (wchar_t *)L"%s: NetLocalGroupAddMembers succeeded. User SID: %s; Group name: %s.",
      L"AadPluginController::AddUserSidToLocalGroup",
      a2,
      v10);
    v15 = AadPluginController::AddUserSidToRollbackContext(
            v14,
            Sid,
            (struct AadPluginController::_MEMBERSHIP_CHANGE *)a3);
    LastError = v15;
    if ( v15 < 0 )
    {
      totalentries[0] = v15;
      Logger::TraceError(
        L"%s: AadPluginController::AddUserSidToRollbackContext failed to add user \"%s\" to group \"%s\" in rollback conte"
         "xt. Error code: 0x%08x.",
        L"AadPluginController::AddUserSidToLocalGroup",
        a2,
        v10,
        *(_QWORD *)totalentries);
      v17 = AadPluginController::RemoveUserSidFromLocalGroup(v16, Sid, v10);
      if ( v17 < 0 )
        Logger::TraceError(
          L"%s: AadPluginController::RemoveUserSidFromLocalGroup failed with error code 0x%08x. User SID: %s; Group Name: %s.",
          L"AadPluginController::AddUserSidToLocalGroup",
          (unsigned int)v17,
          a2,
          v10);
      else
        Logger::TraceVerbose(
          (wchar_t *)L"%s: AadPluginController::RemoveUserSidFromLocalGroup succeeded. User SID: %s; Group Name: %s.",
          L"AadPluginController::AddUserSidToLocalGroup",
          a2,
          v10);
    }
  }
  else
  {
    LastError = GetLastError();
    Logger::WriteConvertStringSidFailureEvent(a2, LastError);
    if ( !LastError )
      LastError = 1359;
    Logger::TraceError(
      L"%s: %s(%s) failed with win32 error code: 0x%08x.",
      L"AadPluginController::AddUserSidToLocalGroup",
      L"ConvertStringSidToSidW",
      a2,
      LastError);
    if ( (int)LastError > 0 )
    {
      LastError = (unsigned __int16)LastError;
LABEL_18:
      LastError |= 0x80070000;
    }
  }
LABEL_36:
  LocalFree(Sid);
  Logger::TraceVerbose((wchar_t *)L"%s - hr: 0x%08x", L"AadPluginController::AddUserSidToLocalGroup", LastError);
  return LastError;
}

```

## disassembly

```asm
0x180040014  mov     rax, rsp
0x180040017  mov     [rax+18h], rbx
0x18004001b  mov     [rax+8], rcx
0x18004001f  push    rbp
0x180040020  push    rsi
0x180040021  push    rdi
0x180040022  push    r12
0x180040024  push    r14
0x180040026  sub     rsp, 30h
0x18004002a  mov     r14, r8
0x18004002d  mov     qword ptr [rax+10h], 0
0x180040035  test    r8, r8
0x180040038  mov     qword ptr [rax+8], 0
0x180040040  lea     r8, aNull_2; "<NULL>"
0x180040047  mov     rsi, rdx
0x18004004a  mov     r9, r8
0x18004004d  jz      short loc_180040057
0x18004004f  cmp     qword ptr [r14], 0
0x180040053  cmovnz  r9, [r14]
0x180040057  test    rsi, rsi
0x18004005a  lea     r12, aAadplugincontr_16; "AadPluginController::AddUserSidToLocalG"...
0x180040061  mov     rdx, r12
0x180040064  lea     rcx, aSStartedUserSi; "%s started. User SID: %s. Group: %s."
0x18004006b  cmovnz  r8, rsi
0x18004006f  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x180040074  test    r14, r14
0x180040077  jnz     short loc_1800400A8
0x180040079  lea     r8, aPgroupmembersh; "pGroupMembershipChange"
0x180040080  mov     rdx, r12
0x180040083  lea     rcx, aSSShouldNotBeN_0; "%s: \"%s\" should not be null."
0x18004008a  mov     ebx, 80070057h
0x18004008f  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180040094  lea     rdx, aPgroupmembersh; "pGroupMembershipChange"
0x18004009b  mov     rcx, r12; unsigned __int16 *
0x18004009e  call    ?WriteNullOrEmptyParameterFailureEvent@Logger@@SAJPEBG0@Z; Logger::WriteNullOrEmptyParameterFailureEvent(ushort const *,ushort const *)
0x1800400a3  jmp     loc_1800402F8
0x1800400a8  mov     rdi, [r14]
0x1800400ab  test    rdi, rdi
0x1800400ae  jnz     short loc_1800400D4
0x1800400b0  lea     r8, aPgroupmembersh_0; "pGroupMembershipChange->pcszLocalGroup"
0x1800400b7  mov     rdx, r12
0x1800400ba  lea     rcx, aSSShouldNotBeN_0; "%s: \"%s\" should not be null."
0x1800400c1  mov     ebx, 80070057h
0x1800400c6  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800400cb  lea     rdx, aPgroupmembersh_0; "pGroupMembershipChange->pcszLocalGroup"
0x1800400d2  jmp     short loc_18004009B
0x1800400d4  mov     rcx, rsi; unsigned __int16 *
0x1800400d7  xor     ebx, ebx
0x1800400d9  call    ?IsEmptyString@@YAHPEBG@Z; IsEmptyString(ushort const *)
0x1800400de  test    eax, eax
0x1800400e0  jnz     loc_1800402E3
0x1800400e6  mov     rcx, rdi; unsigned __int16 *
0x1800400e9  call    ?IsEmptyString@@YAHPEBG@Z; IsEmptyString(ushort const *)
0x1800400ee  test    eax, eax
0x1800400f0  jnz     loc_1800402E3
0x1800400f6  lea     rdx, [rsp+58h+Sid]; Sid
0x1800400fb  mov     rcx, rsi; StringSid
0x1800400fe  call    cs:__imp_ConvertStringSidToSidW
0x180040104  test    eax, eax
0x180040106  jnz     short loc_180040157
0x180040108  call    cs:__imp_GetLastError
0x18004010e  mov     edx, eax; unsigned int
0x180040110  mov     rcx, rsi; unsigned __int16 *
0x180040113  mov     ebx, eax
0x180040115  call    ?WriteConvertStringSidFailureEvent@Logger@@SAJPEBGK@Z; Logger::WriteConvertStringSidFailureEvent(ushort const *,ulong)
0x18004011a  mov     eax, 54Fh
0x18004011f  lea     r8, aConvertstrings_1; "ConvertStringSidToSidW"
0x180040126  test    ebx, ebx
0x180040128  lea     rcx, aSSSFailedWithW; "%s: %s(%s) failed with win32 error code"...
0x18004012f  mov     r9, rsi
0x180040132  mov     rdx, r12
0x180040135  cmovz   ebx, eax
0x180040138  mov     [rsp+58h+totalentries], ebx
0x18004013c  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180040141  test    ebx, ebx
0x180040143  jle     loc_1800402F8
0x180040149  movzx   ebx, bx
0x18004014c  or      ebx, 80070000h
0x180040152  jmp     loc_1800402F8
0x180040157  mov     rax, [rsp+58h+Sid]
0x18004015c  lea     r9, [rsp+58h+buf]; buf
0x180040161  xor     r8d, r8d; level
0x180040164  mov     [rsp+58h+buf], rax
0x180040169  mov     rdx, rdi; groupname
0x18004016c  mov     [rsp+58h+totalentries], 1; totalentries
0x180040174  xor     ecx, ecx; servername
0x180040176  call    cs:__imp_NetLocalGroupAddMembers
0x18004017c  mov     ebp, eax
0x18004017e  test    eax, eax
0x180040180  jnz     loc_180040250
0x180040186  test    cs:Microsoft_Windows_User_Device_RegistrationEnableBits, 1
0x18004018d  jz      short loc_1800401C4
0x18004018f  mov     r9, [rsp+58h+Sid]
0x180040194  lea     rdx, AddGroupMemberSuccessEvent
0x18004019b  mov     r8, rdi
0x18004019e  call    McTemplateU0zk_EventWriteTransfer
0x1800401a3  test    eax, eax
0x1800401a5  jz      short loc_1800401C4
0x1800401a7  mov     r9d, eax
0x1800401aa  lea     r8, aEventwriteaddg_0; "EventWriteAddGroupMemberSuccessEvent"
0x1800401b1  lea     rdx, aLoggerWriteadd; "Logger::WriteAddGroupMemberSuccessEvent"
0x1800401b8  lea     rcx, Str; "%s: %s failed with win32 error code: 0x"...
0x1800401bf  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800401c4  mov     r9, rdi
0x1800401c7  lea     rcx, aSNetlocalgroup_1; "%s: NetLocalGroupAddMembers succeeded. "...
0x1800401ce  mov     r8, rsi
0x1800401d1  mov     rdx, r12
0x1800401d4  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x1800401d9  mov     rdx, [rsp+58h+Sid]; void *
0x1800401de  mov     r8, r14; struct AadPluginController::_MEMBERSHIP_CHANGE *
0x1800401e1  call    ?AddUserSidToRollbackContext@AadPluginController@@AEAAJPEAXPEAU_MEMBERSHIP_CHANGE@1@@Z; AadPluginController::AddUserSidToRollbackContext(void *,AadPluginController::_MEMBERSHIP_CHANGE *)
0x1800401e6  mov     ebx, eax
0x1800401e8  test    eax, eax
0x1800401ea  jns     loc_1800402F8
0x1800401f0  mov     r9, rdi
0x1800401f3  mov     [rsp+58h+totalentries], eax
0x1800401f7  mov     r8, rsi
0x1800401fa  lea     rcx, aSAadplugincont_5; "%s: AadPluginController::AddUserSidToRo"...
0x180040201  mov     rdx, r12
0x180040204  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180040209  mov     rdx, [rsp+58h+Sid]; void *
0x18004020e  mov     r8, rdi; unsigned __int16 *
0x180040211  call    ?RemoveUserSidFromLocalGroup@AadPluginController@@AEAAJPEAXPEBG@Z; AadPluginController::RemoveUserSidFromLocalGroup(void *,ushort const *)
0x180040216  mov     rdx, r12
0x180040219  test    eax, eax
0x18004021b  js      short loc_180040234
0x18004021d  mov     r9, rdi
0x180040220  lea     rcx, aSAadplugincont_8; "%s: AadPluginController::RemoveUserSidF"...
0x180040227  mov     r8, rsi
0x18004022a  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x18004022f  jmp     loc_1800402F8
0x180040234  mov     r9, rsi
0x180040237  mov     qword ptr [rsp+58h+totalentries], rdi
0x18004023c  mov     r8d, eax
0x18004023f  lea     rcx, aSAadplugincont_4; "%s: AadPluginController::RemoveUserSidF"...
0x180040246  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18004024b  jmp     loc_1800402F8
0x180040250  mov     eax, 562h
0x180040255  cmp     ebp, eax
0x180040257  jnz     short loc_180040277
0x180040259  mov     r9, rdi
0x18004025c  mov     [rsp+58h+totalentries], eax
0x180040260  mov     r8, rsi
0x180040263  lea     rcx, aSNetlocalgroup_4; "%s: NetLocalGroupAddMembers returned us"...
0x18004026a  mov     rdx, r12
0x18004026d  call    ?TraceInformation@Logger@@SAJPEBGZZ; Logger::TraceInformation(ushort const *,...)
0x180040272  jmp     loc_1800402F8
0x180040277  test    cs:Microsoft_Windows_User_Device_RegistrationEnableBits, 1
0x18004027e  jz      short loc_1800402B9
0x180040280  mov     r9, [rsp+58h+Sid]
0x180040285  lea     rdx, AddGroupMemberFailureEvent
0x18004028c  mov     r8, rdi
0x18004028f  mov     [rsp+58h+totalentries], ebp
0x180040293  call    McTemplateU0zkq_EventWriteTransfer
0x180040298  test    eax, eax
0x18004029a  jz      short loc_1800402B9
0x18004029c  mov     r9d, eax
0x18004029f  lea     r8, aEventwriteaddg; "EventWriteAddGroupMemberFailureEvent"
0x1800402a6  lea     rdx, aLoggerWriteadd_0; "Logger::WriteAddGroupMemberFailureEvent"
0x1800402ad  lea     rcx, Str; "%s: %s failed with win32 error code: 0x"...
0x1800402b4  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800402b9  mov     r9, rsi
0x1800402bc  mov     qword ptr [rsp+58h+totalentries], rdi
0x1800402c1  mov     r8d, ebp
0x1800402c4  lea     rcx, aSNetlocalgroup_3; "%s: NetLocalGroupAddMembers failed with"...
0x1800402cb  mov     rdx, r12
0x1800402ce  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800402d3  test    ebp, ebp
0x1800402d5  jg      short loc_1800402DB
0x1800402d7  mov     ebx, ebp
0x1800402d9  jmp     short loc_1800402F8
0x1800402db  movzx   ebx, bp
0x1800402de  jmp     loc_18004014C
0x1800402e3  mov     r9, rdi
0x1800402e6  lea     rcx, aSAddingUserSid; "%s: Adding user SID to a local group. E"...
0x1800402ed  mov     r8, rsi
0x1800402f0  mov     rdx, r12
0x1800402f3  call    ?TraceInformation@Logger@@SAJPEBGZZ; Logger::TraceInformation(ushort const *,...)
0x1800402f8  mov     rcx, [rsp+58h+Sid]; hMem
0x1800402fd  call    cs:__imp_LocalFree
0x180040303  mov     r8d, ebx
0x180040306  lea     rcx, aSHr0x08x; "%s - hr: 0x%08x"
0x18004030d  mov     rdx, r12
0x180040310  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x180040315  mov     eax, ebx
0x180040317  mov     rbx, [rsp+58h+arg_10]
0x18004031c  add     rsp, 30h
0x180040320  pop     r14
0x180040322  pop     r12
0x180040324  pop     rdi
0x180040325  pop     rsi
0x180040326  pop     rbp
0x180040327  retn
```
