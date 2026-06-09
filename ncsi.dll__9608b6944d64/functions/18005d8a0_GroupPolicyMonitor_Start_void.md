# GroupPolicyMonitor::Start(void)

- ea: `0x18005d8a0`
- end: `0x18005da7f`
- name: `?Start@GroupPolicyMonitor@@QEAAXXZ`
- size: `479`
- prototype: `void __fastcall(GroupPolicyMonitor *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, installer_update`

## callers

- `0x180050300`

## callees

- `0x180010200`
- `0x180011a58`
- `0x1800407b4`
- `0x180048254`
- `0x18005d8a0`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18005d9e7`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18005d9e7`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x18005d923`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x18005d923`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005d933`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005da28`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005d933`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005da28`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005d8fb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005d8fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d9ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d9ac`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005da1b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005da1b`
- `USERENV!RegisterGPNotification` at `0x18005d962`
- `USERENV!RegisterGPNotification` at `0x18005d962`

## pseudocode

```c
void __fastcall GroupPolicyMonitor::Start(GroupPolicyMonitor *this)
{
  __int64 v1; // rcx
  __int64 v2; // rdx
  struct _TP_WAIT *ThreadpoolWait; // rbx
  BOOL v4; // eax
  DWORD LastError; // eax

  if ( byte_18009B2F8 )
  {
    v1 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 0x10) != 0
      && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 3u )
    {
      v2 = 11;
LABEL_6:
      WPP_SF_(*(_QWORD *)(v1 + 16), v2, WPP_8c649a3b49c335dd6fdbca526a2b3512_Traceguids);
      return;
    }
    return;
  }
  EnterCriticalSection(&stru_18009D4B8);
  if ( !byte_18009DAA0 )
  {
    SetLastError(0x45Bu);
    LeaveCriticalSection(&stru_18009D4B8);
    pwa = 0;
LABEL_20:
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 0x10) != 0
      && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 3u )
    {
      WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 12, WPP_8c649a3b49c335dd6fdbca526a2b3512_Traceguids);
    }
    GroupPolicyMonitor::Cleanup((GroupPolicyMonitor *)&g_groupPolicyMonitor);
    return;
  }
  ThreadpoolWait = CreateThreadpoolWait(
                     GroupPolicyMonitor::MachinePolicyUpdatedCallbackThunk,
                     &g_groupPolicyMonitor,
                     pcbe);
  LeaveCriticalSection(&stru_18009D4B8);
  pwa = ThreadpoolWait;
  if ( !ThreadpoolWait )
    goto LABEL_20;
  if ( !(unsigned __int8)IsRegisterGPNotificationInternalWorkerPresent()
    || (v4 = RegisterGPNotification(g_groupPolicyMonitor, 1), byte_18009B2F8 = v4, v4) )
  {
    SetThreadpoolWait(pwa, g_groupPolicyMonitor, 0);
    v1 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 0x10) != 0
      && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 4u )
    {
      v2 = 14;
      goto LABEL_6;
    }
  }
  else
  {
    GroupPolicyMonitor::Cleanup((GroupPolicyMonitor *)&g_groupPolicyMonitor);
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 0x10) != 0
      && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 3u )
    {
      LastError = GetLastError();
      WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 13, WPP_8c649a3b49c335dd6fdbca526a2b3512_Traceguids, LastError);
    }
  }
}

```

## disassembly

```asm
0x18005d8a0  push    rbx
0x18005d8a2  sub     rsp, 20h
0x18005d8a6  cmp     cs:byte_18009B2F8, 0
0x18005d8ad  jz      short loc_18005D8F4
0x18005d8af  mov     rcx, cs:WPP_GLOBAL_Control
0x18005d8b6  lea     rax, WPP_GLOBAL_Control
0x18005d8bd  cmp     rcx, rax
0x18005d8c0  jz      loc_18005DA79
0x18005d8c6  test    byte ptr [rcx+1Ch], 10h
0x18005d8ca  jz      loc_18005DA79
0x18005d8d0  cmp     byte ptr [rcx+19h], 3
0x18005d8d4  jb      loc_18005DA79
0x18005d8da  mov     edx, 0Bh
0x18005d8df  mov     rcx, [rcx+10h]
0x18005d8e3  lea     r8, WPP_8c649a3b49c335dd6fdbca526a2b3512_Traceguids
0x18005d8ea  add     rsp, 20h
0x18005d8ee  pop     rbx
0x18005d8ef  jmp     WPP_SF_
0x18005d8f4  lea     rcx, stru_18009D4B8; lpCriticalSection
0x18005d8fb  call    cs:__imp_EnterCriticalSection
0x18005d901  cmp     cs:byte_18009DAA0, 0
0x18005d908  jz      loc_18005DA16
0x18005d90e  mov     r8, cs:pcbe; pcbe
0x18005d915  lea     rdx, ?g_groupPolicyMonitor@@3VGroupPolicyMonitor@@A; pv
0x18005d91c  lea     rcx, ?MachinePolicyUpdatedCallbackThunk@GroupPolicyMonitor@@KAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z; pfnwa
0x18005d923  call    cs:__imp_CreateThreadpoolWait
0x18005d929  lea     rcx, stru_18009D4B8; lpCriticalSection
0x18005d930  mov     rbx, rax
0x18005d933  call    cs:__imp_LeaveCriticalSection
0x18005d939  mov     cs:pwa, rbx
0x18005d940  test    rbx, rbx
0x18005d943  jz      loc_18005DA39
0x18005d949  call    IsRegisterGPNotificationInternalWorkerPresent
0x18005d94e  test    al, al
0x18005d950  jz      loc_18005D9D6
0x18005d956  mov     rcx, cs:?g_groupPolicyMonitor@@3VGroupPolicyMonitor@@A; hEvent
0x18005d95d  mov     edx, 1; bMachine
0x18005d962  call    cs:__imp_RegisterGPNotification
0x18005d968  test    eax, eax
0x18005d96a  setnz   cs:byte_18009B2F8
0x18005d971  test    eax, eax
0x18005d973  jnz     short loc_18005D9D6
0x18005d975  lea     rcx, ?g_groupPolicyMonitor@@3VGroupPolicyMonitor@@A; this
0x18005d97c  call    ?Cleanup@GroupPolicyMonitor@@IEAAXXZ; GroupPolicyMonitor::Cleanup(void)
0x18005d981  mov     rcx, cs:WPP_GLOBAL_Control
0x18005d988  lea     rax, WPP_GLOBAL_Control
0x18005d98f  cmp     rcx, rax
0x18005d992  jz      loc_18005DA79
0x18005d998  test    byte ptr [rcx+1Ch], 10h
0x18005d99c  jz      loc_18005DA79
0x18005d9a2  cmp     byte ptr [rcx+19h], 3
0x18005d9a6  jb      loc_18005DA79
0x18005d9ac  call    cs:__imp_GetLastError
0x18005d9b2  mov     rcx, cs:WPP_GLOBAL_Control
0x18005d9b9  lea     r8, WPP_8c649a3b49c335dd6fdbca526a2b3512_Traceguids
0x18005d9c0  mov     edx, 0Dh
0x18005d9c5  mov     r9d, eax
0x18005d9c8  mov     rcx, [rcx+10h]
0x18005d9cc  add     rsp, 20h
0x18005d9d0  pop     rbx
0x18005d9d1  jmp     WPP_SF_d
0x18005d9d6  mov     rdx, cs:?g_groupPolicyMonitor@@3VGroupPolicyMonitor@@A; h
0x18005d9dd  xor     r8d, r8d; pftTimeout
0x18005d9e0  mov     rcx, cs:pwa; pwa
0x18005d9e7  call    cs:__imp_SetThreadpoolWait
0x18005d9ed  mov     rcx, cs:WPP_GLOBAL_Control
0x18005d9f4  lea     rax, WPP_GLOBAL_Control
0x18005d9fb  cmp     rcx, rax
0x18005d9fe  jz      short loc_18005DA79
0x18005da00  test    byte ptr [rcx+1Ch], 10h
0x18005da04  jz      short loc_18005DA79
0x18005da06  cmp     byte ptr [rcx+19h], 4
0x18005da0a  jb      short loc_18005DA79
0x18005da0c  mov     edx, 0Eh
0x18005da11  jmp     loc_18005D8DF
0x18005da16  mov     ecx, 45Bh; dwErrCode
0x18005da1b  call    cs:__imp_SetLastError
0x18005da21  lea     rcx, stru_18009D4B8; lpCriticalSection
0x18005da28  call    cs:__imp_LeaveCriticalSection
0x18005da2e  mov     cs:pwa, 0
0x18005da39  mov     rcx, cs:WPP_GLOBAL_Control
0x18005da40  lea     rax, WPP_GLOBAL_Control
0x18005da47  cmp     rcx, rax
0x18005da4a  jz      short loc_18005DA6D
0x18005da4c  test    byte ptr [rcx+1Ch], 10h
0x18005da50  jz      short loc_18005DA6D
0x18005da52  cmp     byte ptr [rcx+19h], 3
0x18005da56  jb      short loc_18005DA6D
0x18005da58  mov     rcx, [rcx+10h]
0x18005da5c  lea     r8, WPP_8c649a3b49c335dd6fdbca526a2b3512_Traceguids
0x18005da63  mov     edx, 0Ch
0x18005da68  call    WPP_SF_
0x18005da6d  lea     rcx, ?g_groupPolicyMonitor@@3VGroupPolicyMonitor@@A; this
0x18005da74  call    ?Cleanup@GroupPolicyMonitor@@IEAAXXZ; GroupPolicyMonitor::Cleanup(void)
0x18005da79  add     rsp, 20h
0x18005da7d  pop     rbx
0x18005da7e  retn
```
