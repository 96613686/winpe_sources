# CscAgentp_OnUserLogoffThreadProc(void *)

- ea: `0x18003df20`
- end: `0x18003e04c`
- name: `?CscAgentp_OnUserLogoffThreadProc@@YAKPEAX@Z`
- size: `300`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18003cc6c`

## callees

- `0x18000c3f0`
- `0x18001b150`
- `0x18002d400`
- `0x180036038`
- `0x180036394`
- `0x18003df20`
- `0x180040d04`
- `0x180040e74`
- `0x18004e428`
- `0x1800518c0`
- `0x18005f860`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18003e016`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18003e016`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18003e027`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18003e027`

## pseudocode

```c
__int64 __fastcall CscAgentp_OnUserLogoffThreadProc(PVOID Parameter)
{
  unsigned int v1; // edi
  CAuthInfoList *v2; // rcx
  CRefCounted *v3; // rbx
  __int64 v4; // r9
  CPolicyChgMonitor *v5; // rcx
  CAuthInfoList *v6; // rcx
  __int128 v8; // [rsp+20h] [rbp-28h] BYREF
  void **v9; // [rsp+30h] [rbp-18h] BYREF
  unsigned int v10; // [rsp+38h] [rbp-10h]
  CRefCounted *v11; // [rsp+70h] [rbp+28h] BYREF

  v1 = (unsigned int)Parameter;
  v2 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, WPP_ef399ae69b0439092b78fa9bd8d7e9cf_Traceguids, v1);
  v11 = 0;
  v9 = &CAuthInfoMatchBySessionId::`vftable';
  v10 = v1;
  if ( (int)CAuthInfoList::FindAuthInfo(v2, (struct CAuthInfoMatcher *)&v9, &v11) >= 0 )
  {
    v3 = v11;
    CscEvt_UserLogonOrLogoff(v1, *((void **)v11 + 4), &CSC_SERVICE_EVENT_USER_LOGOFF);
    v4 = *((unsigned int *)v3 + 10);
    *(_QWORD *)((char *)&v8 + 4) = *((_QWORD *)v3 + 6);
    LODWORD(v8) = v4;
    if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 45, WPP_ec025b6fc19f3c7778dfc92dc65caf05_Traceguids, v4);
    }
    EventDispatcher_UnregisterConnection((const struct CLogonSessionId *)&v8);
    *(_QWORD *)&v8 = &CAgentTaskGroupVisitor_NotifyUserLogoff::`vftable';
    *((_QWORD *)&v8 + 1) = *((_QWORD *)v3 + 6);
    CscAgentp_VisitTaskGroupTable((struct CAgentTaskGroupVisitor *)&v8, 0);
    CPolicyChgMonitor::_RemoveUserPolicyHandler(v5, *((void **)v3 + 7));
    CAuthInfoList::ReleaseAuthInfoForUserSession(v6, v1);
    if ( ImpersonateLoggedOnUser(*((HANDLE *)v3 + 4)) )
    {
      CscLib_OfflineDirectoryRenameClearPaths(0);
      RevertToSelf();
    }
    CRefCounted::ReleaseReference(v3);
  }
  CInvSemaphore::Decrement((CInvSemaphore *)&g_invsemTasksInProgress);
  return 0;
}

```

## disassembly

```asm
0x18003df20  push    rbp
0x18003df22  push    rbx
0x18003df23  push    rsi
0x18003df24  push    rdi
0x18003df25  mov     rbp, rsp
0x18003df28  sub     rsp, 48h
0x18003df2c  mov     rdi, rcx
0x18003df2f  mov     rcx, cs:WPP_GLOBAL_Control
0x18003df36  lea     rsi, WPP_GLOBAL_Control
0x18003df3d  cmp     rcx, rsi
0x18003df40  jz      short loc_18003DF63
0x18003df42  test    dword ptr [rcx+1Ch], 400h
0x18003df49  jz      short loc_18003DF63
0x18003df4b  mov     rcx, [rcx+10h]
0x18003df4f  lea     r8, WPP_ef399ae69b0439092b78fa9bd8d7e9cf_Traceguids
0x18003df56  mov     r9d, edi
0x18003df59  mov     edx, 20h ; ' '
0x18003df5e  call    WPP_SF_d
0x18003df63  lea     rax, ??_7CAuthInfoMatchBySessionId@@6B@; const CAuthInfoMatchBySessionId::`vftable'
0x18003df6a  mov     [rbp+arg_0], 0
0x18003df72  lea     r8, [rbp+arg_0]; struct CAuthInfo **
0x18003df76  mov     [rbp+var_18], rax
0x18003df7a  lea     rdx, [rbp+var_18]; struct CAuthInfoMatcher *
0x18003df7e  mov     [rbp+var_10], edi
0x18003df81  call    ?FindAuthInfo@CAuthInfoList@@QEAAJAEAVCAuthInfoMatcher@@PEAPEAVCAuthInfo@@@Z; CAuthInfoList::FindAuthInfo(CAuthInfoMatcher &,CAuthInfo * *)
0x18003df86  test    eax, eax
0x18003df88  js      loc_18003E035
0x18003df8e  mov     rbx, [rbp+arg_0]
0x18003df92  lea     r8, CSC_SERVICE_EVENT_USER_LOGOFF; struct _EVENT_DESCRIPTOR *
0x18003df99  mov     ecx, edi; unsigned int
0x18003df9b  mov     rdx, [rbx+20h]; void *
0x18003df9f  call    ?CscEvt_UserLogonOrLogoff@@YAKKPEAXPEBU_EVENT_DESCRIPTOR@@@Z; CscEvt_UserLogonOrLogoff(ulong,void *,_EVENT_DESCRIPTOR const *)
0x18003dfa4  mov     rax, [rbx+30h]
0x18003dfa8  mov     r9d, [rbx+28h]
0x18003dfac  mov     [rbp+var_28+4], rax
0x18003dfb0  mov     dword ptr [rbp+var_28], r9d
0x18003dfb4  mov     rcx, cs:WPP_GLOBAL_Control
0x18003dfbb  cmp     rcx, rsi
0x18003dfbe  jz      short loc_18003DFDB
0x18003dfc0  test    byte ptr [rcx+1Ch], 10h
0x18003dfc4  jz      short loc_18003DFDB
0x18003dfc6  mov     rcx, [rcx+10h]
0x18003dfca  lea     r8, WPP_ec025b6fc19f3c7778dfc92dc65caf05_Traceguids
0x18003dfd1  mov     edx, 2Dh ; '-'
0x18003dfd6  call    WPP_SF_d
0x18003dfdb  lea     rcx, [rbp+var_28]; struct CLogonSessionId *
0x18003dfdf  call    ?EventDispatcher_UnregisterConnection@@YAJAEBVCLogonSessionId@@@Z; EventDispatcher_UnregisterConnection(CLogonSessionId const &)
0x18003dfe4  lea     rax, ??_7CAgentTaskGroupVisitor_NotifyUserLogoff@@6B@; const CAgentTaskGroupVisitor_NotifyUserLogoff::`vftable'
0x18003dfeb  xor     edx, edx; int
0x18003dfed  mov     [rbp+var_28], rax
0x18003dff1  lea     rcx, [rbp+var_28]; struct CAgentTaskGroupVisitor *
0x18003dff5  mov     rax, [rbx+30h]
0x18003dff9  mov     [rbp+var_20], rax
0x18003dffd  call    ?CscAgentp_VisitTaskGroupTable@@YAJAEAVCAgentTaskGroupVisitor@@H@Z; CscAgentp_VisitTaskGroupTable(CAgentTaskGroupVisitor &,int)
0x18003e002  mov     rdx, [rbx+38h]; void *
0x18003e006  call    ?_RemoveUserPolicyHandler@CPolicyChgMonitor@@AEAAJPEAX@Z; CPolicyChgMonitor::_RemoveUserPolicyHandler(void *)
0x18003e00b  mov     edx, edi; unsigned int
0x18003e00d  call    ?ReleaseAuthInfoForUserSession@CAuthInfoList@@QEAAJK@Z; CAuthInfoList::ReleaseAuthInfoForUserSession(ulong)
0x18003e012  mov     rcx, [rbx+20h]; hToken
0x18003e016  call    cs:__imp_ImpersonateLoggedOnUser
0x18003e01c  test    eax, eax
0x18003e01e  jz      short loc_18003E02D
0x18003e020  xor     ecx, ecx; int
0x18003e022  call    ?CscLib_OfflineDirectoryRenameClearPaths@@YAJH@Z; CscLib_OfflineDirectoryRenameClearPaths(int)
0x18003e027  call    cs:__imp_RevertToSelf
0x18003e02d  mov     rcx, rbx; this
0x18003e030  call    ?ReleaseReference@CRefCounted@@QEAAXXZ; CRefCounted::ReleaseReference(void)
0x18003e035  lea     rcx, ?g_invsemTasksInProgress@@3VCInvSemaphore@@A; this
0x18003e03c  call    ?Decrement@CInvSemaphore@@QEAAXXZ; CInvSemaphore::Decrement(void)
0x18003e041  xor     eax, eax
0x18003e043  add     rsp, 48h
0x18003e047  pop     rdi
0x18003e048  pop     rsi
0x18003e049  pop     rbx
0x18003e04a  pop     rbp
0x18003e04b  retn
```
