# CscAgentp_OnUserLogonThreadProc(void *)

- ea: `0x18003e060`
- end: `0x18003e1cc`
- name: `?CscAgentp_OnUserLogonThreadProc@@YAKPEAX@Z`
- size: `364`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `1`
- callee_count: `18`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18003cd00`

## callees

- `0x18000c3f0`
- `0x18000f69c`
- `0x18001b150`
- `0x18002af38`
- `0x180036394`
- `0x18003cd94`
- `0x18003e060`
- `0x18003efe4`
- `0x180040c30`
- `0x180040d04`
- `0x180048b14`
- `0x1800518c0`
- `0x180056928`
- `0x18005696c`
- `0x18005732c`
- `0x18005ebec`
- `0x18005fbb0`
- `0x18005fc7c`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18003e10b`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18003e10b`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18003e15c`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18003e15c`

## string_xrefs

- `0x18003e11c`: `EncryptCache`

## pseudocode

```c
__int64 __fastcall CscAgentp_OnUserLogonThreadProc(PVOID Parameter)
{
  unsigned int v1; // ebx
  CAuthInfoList *v2; // rcx
  CAuthInfoList *v3; // rcx
  CRefCounted *v4; // rdi
  CPolicyChgMonitor *v5; // rcx
  void *v6; // rcx
  int v7; // ebx
  int SettingValue; // ebx
  void *v9; // rdx
  void **v11; // [rsp+20h] [rbp-50h] BYREF
  unsigned int v12; // [rsp+28h] [rbp-48h]
  _BYTE v13[64]; // [rsp+30h] [rbp-40h] BYREF
  CRefCounted *v14; // [rsp+80h] [rbp+10h] BYREF

  v1 = (unsigned int)Parameter;
  v2 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, WPP_ef399ae69b0439092b78fa9bd8d7e9cf_Traceguids, v1);
  if ( CAuthInfoList::CollectAuthInfoForUserSession(v2, v1) >= 0 )
  {
    v14 = 0;
    v11 = &CAuthInfoMatchBySessionId::`vftable';
    v12 = v1;
    if ( (int)CAuthInfoList::FindAuthInfo(v3, (struct CAuthInfoMatcher *)&v11, &v14) >= 0 )
    {
      v4 = v14;
      CscEvt_UserLogonOrLogoff(v1, *((void **)v14 + 4), &CSC_SERVICE_EVENT_USER_LOGON);
      CPolicyChgMonitor::_AddUserPolicyHandler(v5, *((void **)v4 + 7));
      v6 = (void *)*((_QWORD *)v4 + 4);
      v7 = 0;
      LODWORD(v14) = 0;
      if ( ImpersonateLoggedOnUser(v6) )
      {
        SettingValue = CscService_GetSettingValue(L"EncryptCache", (unsigned int *)&v14, 0);
        SlowLink_DeleteOnlineTransitionLog();
        SlowLink_DeleteOfflineTransitionLog();
        COfflineRenameDeleteConfig::COfflineRenameDeleteConfig((COfflineRenameDeleteConfig *)v13);
        if ( (int)COfflineRenameDeleteConfig::_Load((COfflineRenameDeleteConfig *)v13, 0) >= 0 )
          COfflineRenameDeleteConfig::Apply((COfflineRenameDeleteConfig *)v13, 0);
        LogUserPinnedShareCountTelemetry();
        RevertToSelf();
        COfflineRenameDeleteConfig::_Clear((COfflineRenameDeleteConfig *)v13);
        if ( SettingValue < 0 )
          goto LABEL_13;
        v7 = (int)v14;
      }
      v9 = (void *)*((_QWORD *)v4 + 4);
      v14 = 0;
      if ( CscAgent_CreateEncryptionTask(v7 != 0, v9, &v14) >= 0 )
      {
        CscAgent_QueueTask(v14);
        CRefCounted::ReleaseReference(v14);
      }
LABEL_13:
      CRefCounted::ReleaseReference(v4);
    }
  }
  CInvSemaphore::Decrement((CInvSemaphore *)&g_invsemTasksInProgress);
  return 0;
}

```

## disassembly

```asm
0x18003e060  mov     [rsp-8+arg_8], rbx
0x18003e065  mov     [rsp-8+arg_10], rdi
0x18003e06a  push    rbp
0x18003e06b  mov     rbp, rsp
0x18003e06e  sub     rsp, 70h
0x18003e072  mov     rbx, rcx
0x18003e075  mov     rcx, cs:WPP_GLOBAL_Control
0x18003e07c  lea     rax, WPP_GLOBAL_Control
0x18003e083  cmp     rcx, rax
0x18003e086  jz      short loc_18003E0A9
0x18003e088  test    dword ptr [rcx+1Ch], 400h
0x18003e08f  jz      short loc_18003E0A9
0x18003e091  mov     rcx, [rcx+10h]
0x18003e095  lea     r8, WPP_ef399ae69b0439092b78fa9bd8d7e9cf_Traceguids
0x18003e09c  mov     r9d, ebx
0x18003e09f  mov     edx, 1Fh
0x18003e0a4  call    WPP_SF_d
0x18003e0a9  mov     edx, ebx; unsigned int
0x18003e0ab  call    ?CollectAuthInfoForUserSession@CAuthInfoList@@QEAAJK@Z; CAuthInfoList::CollectAuthInfoForUserSession(ulong)
0x18003e0b0  test    eax, eax
0x18003e0b2  js      loc_18003E1AC
0x18003e0b8  lea     rax, ??_7CAuthInfoMatchBySessionId@@6B@; const CAuthInfoMatchBySessionId::`vftable'
0x18003e0bf  mov     [rbp+arg_0], 0
0x18003e0c7  lea     r8, [rbp+arg_0]; struct CAuthInfo **
0x18003e0cb  mov     [rbp+var_50], rax
0x18003e0cf  lea     rdx, [rbp+var_50]; struct CAuthInfoMatcher *
0x18003e0d3  mov     [rbp+var_48], ebx
0x18003e0d6  call    ?FindAuthInfo@CAuthInfoList@@QEAAJAEAVCAuthInfoMatcher@@PEAPEAVCAuthInfo@@@Z; CAuthInfoList::FindAuthInfo(CAuthInfoMatcher &,CAuthInfo * *)
0x18003e0db  test    eax, eax
0x18003e0dd  js      loc_18003E1AC
0x18003e0e3  mov     rdi, [rbp+arg_0]
0x18003e0e7  lea     r8, CSC_SERVICE_EVENT_USER_LOGON; struct _EVENT_DESCRIPTOR *
0x18003e0ee  mov     ecx, ebx; unsigned int
0x18003e0f0  mov     rdx, [rdi+20h]; void *
0x18003e0f4  call    ?CscEvt_UserLogonOrLogoff@@YAKKPEAXPEBU_EVENT_DESCRIPTOR@@@Z; CscEvt_UserLogonOrLogoff(ulong,void *,_EVENT_DESCRIPTOR const *)
0x18003e0f9  mov     rdx, [rdi+38h]; void *
0x18003e0fd  call    ?_AddUserPolicyHandler@CPolicyChgMonitor@@AEAAJPEAX@Z; CPolicyChgMonitor::_AddUserPolicyHandler(void *)
0x18003e102  mov     rcx, [rdi+20h]; hToken
0x18003e106  xor     ebx, ebx
0x18003e108  mov     dword ptr [rbp+arg_0], ebx
0x18003e10b  call    cs:__imp_ImpersonateLoggedOnUser
0x18003e111  test    eax, eax
0x18003e113  jz      short loc_18003E172
0x18003e115  xor     r8d, r8d; int *
0x18003e118  lea     rdx, [rbp+arg_0]; unsigned int *
0x18003e11c  lea     rcx, String2; "EncryptCache"
0x18003e123  call    ?CscService_GetSettingValue@@YAJPEBGPEAKPEAH@Z; CscService_GetSettingValue(ushort const *,ulong *,int *)
0x18003e128  mov     ebx, eax
0x18003e12a  call    ?SlowLink_DeleteOnlineTransitionLog@@YAJXZ; SlowLink_DeleteOnlineTransitionLog(void)
0x18003e12f  call    ?SlowLink_DeleteOfflineTransitionLog@@YAJXZ; SlowLink_DeleteOfflineTransitionLog(void)
0x18003e134  lea     rcx, [rbp+var_40]; this
0x18003e138  call    ??0COfflineRenameDeleteConfig@@QEAA@XZ; COfflineRenameDeleteConfig::COfflineRenameDeleteConfig(void)
0x18003e13d  xor     edx, edx; int
0x18003e13f  lea     rcx, [rbp+var_40]; this
0x18003e143  call    ?_Load@COfflineRenameDeleteConfig@@AEAAJH@Z; COfflineRenameDeleteConfig::_Load(int)
0x18003e148  test    eax, eax
0x18003e14a  js      short loc_18003E157
0x18003e14c  xor     edx, edx; int *
0x18003e14e  lea     rcx, [rbp+var_40]; this
0x18003e152  call    ?Apply@COfflineRenameDeleteConfig@@QEAAJPEAH@Z; COfflineRenameDeleteConfig::Apply(int *)
0x18003e157  call    ?LogUserPinnedShareCountTelemetry@@YAXXZ; LogUserPinnedShareCountTelemetry(void)
0x18003e15c  call    cs:__imp_RevertToSelf
0x18003e162  lea     rcx, [rbp+var_40]; this
0x18003e166  call    ?_Clear@COfflineRenameDeleteConfig@@AEAAXXZ; COfflineRenameDeleteConfig::_Clear(void)
0x18003e16b  test    ebx, ebx
0x18003e16d  js      short loc_18003E1A4
0x18003e16f  mov     ebx, dword ptr [rbp+arg_0]
0x18003e172  mov     rdx, [rdi+20h]; void *
0x18003e176  lea     r8, [rbp+arg_0]; struct CAgentTask **
0x18003e17a  xor     ecx, ecx
0x18003e17c  mov     [rbp+arg_0], 0
0x18003e184  test    ebx, ebx
0x18003e186  setnz   cl; int
0x18003e189  call    ?CscAgent_CreateEncryptionTask@@YAJHPEAXPEAPEAVCAgentTask@@@Z; CscAgent_CreateEncryptionTask(int,void *,CAgentTask * *)
0x18003e18e  test    eax, eax
0x18003e190  js      short loc_18003E1A4
0x18003e192  mov     rcx, [rbp+arg_0]; struct CAgentTask *
0x18003e196  call    ?CscAgent_QueueTask@@YAJPEAVCAgentTask@@@Z; CscAgent_QueueTask(CAgentTask *)
0x18003e19b  mov     rcx, [rbp+arg_0]; this
0x18003e19f  call    ?ReleaseReference@CRefCounted@@QEAAXXZ; CRefCounted::ReleaseReference(void)
0x18003e1a4  mov     rcx, rdi; this
0x18003e1a7  call    ?ReleaseReference@CRefCounted@@QEAAXXZ; CRefCounted::ReleaseReference(void)
0x18003e1ac  lea     rcx, ?g_invsemTasksInProgress@@3VCInvSemaphore@@A; this
0x18003e1b3  call    ?Decrement@CInvSemaphore@@QEAAXXZ; CInvSemaphore::Decrement(void)
0x18003e1b8  lea     r11, [rsp+70h+var_s0]
0x18003e1bd  xor     eax, eax
0x18003e1bf  mov     rbx, [r11+18h]
0x18003e1c3  mov     rdi, [r11+20h]
0x18003e1c7  mov     rsp, r11
0x18003e1ca  pop     rbp
0x18003e1cb  retn
```
