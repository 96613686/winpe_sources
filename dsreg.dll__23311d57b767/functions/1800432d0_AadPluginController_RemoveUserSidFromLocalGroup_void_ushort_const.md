# AadPluginController::RemoveUserSidFromLocalGroup(void *,ushort const *)

- ea: `0x1800432d0`
- end: `0x180043479`
- name: `?RemoveUserSidFromLocalGroup@AadPluginController@@AEAAJPEAXPEBG@Z`
- size: `425`
- prototype: `int(AadPluginController *__hidden this, void *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180040014`
- `0x18004f068`

## callees

- `0x1800084f4`
- `0x18000bac0`
- `0x180012948`
- `0x1800307c4`
- `0x1800432d0`
- `0x180090f04`
- `0x180090fc0`

## import_xrefs

- `samcli!NetLocalGroupDelMembers` at `0x180043371`
- `samcli!NetLocalGroupDelMembers` at `0x180043371`

## string_xrefs

- `0x18004341e`: `Logger::WriteRemoveGroupMemberFailureEvent`
- `0x180043417`: `EventWriteRemoveGroupMemberFailureEvent`
- `0x1800432fd`: `AadPluginController::RemoveUserSidFromLocalGroup`
- `0x180043317`: `AadPluginController::RemoveUserSidFromLocalGroup`
- `0x180043339`: `AadPluginController::RemoveUserSidFromLocalGroup`
- `0x1800433b9`: `AadPluginController::RemoveUserSidFromLocalGroup`
- `0x1800433dc`: `AadPluginController::RemoveUserSidFromLocalGroup`
- `0x180043434`: `AadPluginController::RemoveUserSidFromLocalGroup`
- `0x18004345b`: `AadPluginController::RemoveUserSidFromLocalGroup`
- `0x1800433a6`: `Logger::WriteRemoveGroupMemberSuccessEvent`
- `0x18004339f`: `EventWriteRemoveGroupMemberSuccessEvent`
- `0x1800432f1`: `pUserSidToRemove`
- `0x180043310`: `pUserSidToRemove`

## pseudocode

```c
__int64 __fastcall AadPluginController::RemoveUserSidFromLocalGroup(
        AadPluginController *this,
        void *a2,
        const unsigned __int16 *a3)
{
  unsigned int v5; // ebx
  const unsigned __int16 *v6; // rdx
  DWORD v7; // eax
  __int64 v8; // rcx
  int v9; // edi
  unsigned int v10; // eax
  unsigned int v11; // eax
  void *buf; // [rsp+60h] [rbp+8h] BYREF

  buf = 0;
  if ( !a2 )
  {
    v5 = -2147024809;
    Logger::TraceError(
      L"%s: \"%s\" should not be null.",
      L"AadPluginController::RemoveUserSidFromLocalGroup",
      L"pUserSidToRemove");
    v6 = L"pUserSidToRemove";
LABEL_3:
    Logger::WriteNullOrEmptyParameterFailureEvent(L"AadPluginController::RemoveUserSidFromLocalGroup", v6);
    goto LABEL_19;
  }
  if ( !a3 )
  {
    v5 = -2147024809;
    Logger::TraceError(
      L"%s: \"%s\" should not be null.",
      L"AadPluginController::RemoveUserSidFromLocalGroup",
      L"pcszGroupName");
    v6 = L"pcszGroupName";
    goto LABEL_3;
  }
  buf = a2;
  v5 = 0;
  v7 = NetLocalGroupDelMembers(0, a3, 0, (LPBYTE)&buf, 1u);
  v9 = v7;
  if ( v7 )
  {
    if ( v7 == 1377 )
    {
      Logger::TraceInformation(
        L"%s: NetLocalGroupDelMembers returned that the user was not part admin group. netStatus: 0x%x.",
        L"AadPluginController::RemoveUserSidFromLocalGroup");
    }
    else
    {
      if ( (Microsoft_Windows_User_Device_RegistrationEnableBits & 1) != 0 )
      {
        v11 = McTemplateU0zkq_EventWriteTransfer(
                v8,
                (unsigned int)RemoveGroupMemberFailureEvent,
                (_DWORD)a3,
                (_DWORD)a2,
                v7);
        if ( v11 )
          Logger::TraceError(
            L"%s: %s failed with win32 error code: 0x%08x.",
            L"Logger::WriteRemoveGroupMemberFailureEvent",
            L"EventWriteRemoveGroupMemberFailureEvent",
            v11);
      }
      Logger::TraceError(
        L"%s: NetLocalGroupAddMembers failed with status 0x%x.",
        L"AadPluginController::RemoveUserSidFromLocalGroup",
        (unsigned int)v9);
      if ( v9 > 0 )
        v5 = (unsigned __int16)v9 | 0x80070000;
      else
        v5 = v9;
    }
  }
  else
  {
    if ( (Microsoft_Windows_User_Device_RegistrationEnableBits & 1) != 0 )
    {
      v10 = McTemplateU0zk_EventWriteTransfer(v8, RemoveGroupMemberSuccessEvent, a3, a2);
      if ( v10 )
        Logger::TraceError(
          L"%s: %s failed with win32 error code: 0x%08x.",
          L"Logger::WriteRemoveGroupMemberSuccessEvent",
          L"EventWriteRemoveGroupMemberSuccessEvent",
          v10);
    }
    Logger::TraceVerbose(
      (wchar_t *)L"%s: NetLocalGroupAddMembers succeeded.",
      L"AadPluginController::RemoveUserSidFromLocalGroup");
  }
LABEL_19:
  Logger::TraceVerbose((wchar_t *)L"%s - hr: 0x%08x", L"AadPluginController::RemoveUserSidFromLocalGroup", v5);
  return v5;
}

```

## disassembly

```asm
0x1800432d0  mov     [rsp+buf], rcx
0x1800432d5  push    rbx
0x1800432d6  push    rbp
0x1800432d7  push    rsi
0x1800432d8  push    rdi
0x1800432d9  sub     rsp, 38h
0x1800432dd  mov     [rsp+58h+buf], 0
0x1800432e6  mov     rsi, r8
0x1800432e9  mov     rbp, rdx
0x1800432ec  test    rdx, rdx
0x1800432ef  jnz     short loc_180043328
0x1800432f1  lea     r8, aPusersidtoremo; "pUserSidToRemove"
0x1800432f8  mov     ebx, 80070057h
0x1800432fd  lea     rdx, aAadplugincontr_2; "AadPluginController::RemoveUserSidFromL"...
0x180043304  lea     rcx, aSSShouldNotBeN_0; "%s: \"%s\" should not be null."
0x18004330b  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180043310  lea     rdx, aPusersidtoremo; "pUserSidToRemove"
0x180043317  lea     rcx, aAadplugincontr_2; "AadPluginController::RemoveUserSidFromL"...
0x18004331e  call    ?WriteNullOrEmptyParameterFailureEvent@Logger@@SAJPEBG0@Z; Logger::WriteNullOrEmptyParameterFailureEvent(ushort const *,ushort const *)
0x180043323  jmp     loc_180043458
0x180043328  test    rsi, rsi
0x18004332b  jnz     short loc_180043355
0x18004332d  lea     r8, aPcszgroupname; "pcszGroupName"
0x180043334  mov     ebx, 80070057h
0x180043339  lea     rdx, aAadplugincontr_2; "AadPluginController::RemoveUserSidFromL"...
0x180043340  lea     rcx, aSSShouldNotBeN_0; "%s: \"%s\" should not be null."
0x180043347  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18004334c  lea     rdx, aPcszgroupname; "pcszGroupName"
0x180043353  jmp     short loc_180043317
0x180043355  lea     r9, [rsp+58h+buf]; buf
0x18004335a  mov     [rsp+58h+buf], rbp
0x18004335f  xor     r8d, r8d; level
0x180043362  mov     [rsp+58h+totalentries], 1; totalentries
0x18004336a  mov     rdx, rsi; groupname
0x18004336d  xor     ecx, ecx; servername
0x18004336f  xor     ebx, ebx
0x180043371  call    cs:__imp_NetLocalGroupDelMembers
0x180043377  mov     edi, eax
0x180043379  test    eax, eax
0x18004337b  jnz     short loc_1800433D1
0x18004337d  test    cs:Microsoft_Windows_User_Device_RegistrationEnableBits, 1
0x180043384  jz      short loc_1800433B9
0x180043386  mov     r9, rbp
0x180043389  lea     rdx, RemoveGroupMemberSuccessEvent
0x180043390  mov     r8, rsi
0x180043393  call    McTemplateU0zk_EventWriteTransfer
0x180043398  test    eax, eax
0x18004339a  jz      short loc_1800433B9
0x18004339c  mov     r9d, eax
0x18004339f  lea     r8, aEventwriteremo_2; "EventWriteRemoveGroupMemberSuccessEvent"
0x1800433a6  lea     rdx, aLoggerWriterem; "Logger::WriteRemoveGroupMemberSuccessEv"...
0x1800433ad  lea     rcx, Str; "%s: %s failed with win32 error code: 0x"...
0x1800433b4  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800433b9  lea     rdx, aAadplugincontr_2; "AadPluginController::RemoveUserSidFromL"...
0x1800433c0  lea     rcx, aSNetlocalgroup_0; "%s: NetLocalGroupAddMembers succeeded."
0x1800433c7  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x1800433cc  jmp     loc_180043458
0x1800433d1  mov     r8d, 561h
0x1800433d7  cmp     edi, r8d
0x1800433da  jnz     short loc_1800433F1
0x1800433dc  lea     rdx, aAadplugincontr_2; "AadPluginController::RemoveUserSidFromL"...
0x1800433e3  lea     rcx, aSNetlocalgroup; "%s: NetLocalGroupDelMembers returned th"...
0x1800433ea  call    ?TraceInformation@Logger@@SAJPEBGZZ; Logger::TraceInformation(ushort const *,...)
0x1800433ef  jmp     short loc_180043458
0x1800433f1  test    cs:Microsoft_Windows_User_Device_RegistrationEnableBits, 1
0x1800433f8  jz      short loc_180043431
0x1800433fa  mov     r9, rbp
0x1800433fd  mov     [rsp+58h+totalentries], edi
0x180043401  mov     r8, rsi
0x180043404  lea     rdx, RemoveGroupMemberFailureEvent
0x18004340b  call    McTemplateU0zkq_EventWriteTransfer
0x180043410  test    eax, eax
0x180043412  jz      short loc_180043431
0x180043414  mov     r9d, eax
0x180043417  lea     r8, aEventwriteremo_1; "EventWriteRemoveGroupMemberFailureEvent"
0x18004341e  lea     rdx, aLoggerWriterem_2; "Logger::WriteRemoveGroupMemberFailureEv"...
0x180043425  lea     rcx, Str; "%s: %s failed with win32 error code: 0x"...
0x18004342c  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180043431  mov     r8d, edi
0x180043434  lea     rdx, aAadplugincontr_2; "AadPluginController::RemoveUserSidFromL"...
0x18004343b  lea     rcx, aSNetlocalgroup_2; "%s: NetLocalGroupAddMembers failed with"...
0x180043442  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180043447  test    edi, edi
0x180043449  jg      short loc_18004344F
0x18004344b  mov     ebx, edi
0x18004344d  jmp     short loc_180043458
0x18004344f  movzx   ebx, di
0x180043452  or      ebx, 80070000h
0x180043458  mov     r8d, ebx
0x18004345b  lea     rdx, aAadplugincontr_2; "AadPluginController::RemoveUserSidFromL"...
0x180043462  lea     rcx, aSHr0x08x; "%s - hr: 0x%08x"
0x180043469  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x18004346e  mov     eax, ebx
0x180043470  add     rsp, 38h
0x180043474  pop     rdi
0x180043475  pop     rsi
0x180043476  pop     rbp
0x180043477  pop     rbx
0x180043478  retn
```
