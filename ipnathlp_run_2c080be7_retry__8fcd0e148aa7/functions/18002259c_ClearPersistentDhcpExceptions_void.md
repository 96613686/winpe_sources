# ClearPersistentDhcpExceptions(void)

- ea: `0x18002259c`
- end: `0x1800226d8`
- name: `?ClearPersistentDhcpExceptions@@YAXXZ`
- size: `316`
- prototype: `void(void)`
- caller_count: `5`
- callee_count: `4`
- tags: ``

## callers

- `0x180021de8`
- `0x180021fb8`
- `0x180024484`
- `0x180073a7c`
- `0x180075f14`

## callees

- `0x18000ca20`
- `0x18000d090`
- `0x18002259c`
- `0x180033a50`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800225b2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800225b2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800226af`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800226af`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002263f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002263f`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18002268c`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18002268c`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180022627`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180022627`
- `FirewallAPI!FWFreeFirewallRules` at `0x1800226c5`
- `FirewallAPI!FWFreeFirewallRules` at `0x1800226c5`

## pseudocode

```c
void ClearPersistentDhcpExceptions(void)
{
  struct _TP_WORK *ThreadpoolWork; // rax
  signed int LastError; // eax
  PVOID pv; // [rsp+30h] [rbp+8h] BYREF

  pv = 0;
  EnterCriticalSection(&DhcpGlobalInfoLock);
  if ( !fClearedDhcpExceptions )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 64, &WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids);
    }
    if ( !NatGetExistingDhcpRules((struct _tag_FW_RULE **)&pv) )
    {
      ThreadpoolWork = CreateThreadpoolWork(
                         (PTP_WORK_CALLBACK)FirewallCleanupBackgroundProcessing,
                         pv,
                         &g_FwEnvironment);
      g_FirewallCleanupBackgroundWork = ThreadpoolWork;
      if ( ThreadpoolWork )
      {
        SubmitThreadpoolWork(ThreadpoolWork);
        pv = 0;
      }
      else
      {
        LastError = GetLastError();
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            65,
            &WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids,
            (unsigned int)LastError);
        }
      }
    }
  }
  fClearedDhcpExceptions = 1;
  LeaveCriticalSection(&DhcpGlobalInfoLock);
  if ( pv )
    FWFreeFirewallRules(pv);
}

```

## disassembly

```asm
0x18002259c  push    rdi
0x18002259e  sub     rsp, 20h
0x1800225a2  lea     rcx, ?DhcpGlobalInfoLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800225a9  mov     [rsp+28h+pv], 0
0x1800225b2  call    cs:__imp_EnterCriticalSection
0x1800225b9  nop     dword ptr [rax+rax+00h]
0x1800225be  cmp     cs:?fClearedDhcpExceptions@@3EA, 0; uchar fClearedDhcpExceptions
0x1800225c5  jnz     loc_1800226A1
0x1800225cb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800225d2  lea     rdi, WPP_GLOBAL_Control
0x1800225d9  cmp     rcx, rdi
0x1800225dc  jz      short loc_180022602
0x1800225de  test    dword ptr [rcx+1Ch], 200h
0x1800225e5  jz      short loc_180022602
0x1800225e7  cmp     byte ptr [rcx+19h], 5
0x1800225eb  jb      short loc_180022602
0x1800225ed  mov     rcx, [rcx+10h]
0x1800225f1  lea     r8, WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids
0x1800225f8  mov     edx, 40h ; '@'
0x1800225fd  call    WPP_SF_
0x180022602  lea     rcx, [rsp+28h+pv]; struct _tag_FW_RULE **
0x180022607  call    ?NatGetExistingDhcpRules@@YAKPEAPEAU_tag_FW_RULE@@@Z; NatGetExistingDhcpRules(_tag_FW_RULE * *)
0x18002260c  test    eax, eax
0x18002260e  jnz     loc_1800226A1
0x180022614  mov     rdx, [rsp+28h+pv]; pv
0x180022619  lea     r8, ?g_FwEnvironment@@3U_TP_CALLBACK_ENVIRON_V3@@A; pcbe
0x180022620  lea     rcx, ?FirewallCleanupBackgroundProcessing@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x180022627  call    cs:__imp_CreateThreadpoolWork
0x18002262e  nop     dword ptr [rax+rax+00h]
0x180022633  mov     cs:?g_FirewallCleanupBackgroundWork@@3PEAU_TP_WORK@@EA, rax; _TP_WORK * g_FirewallCleanupBackgroundWork
0x18002263a  test    rax, rax
0x18002263d  jnz     short loc_180022689
0x18002263f  call    cs:__imp_GetLastError
0x180022646  nop     dword ptr [rax+rax+00h]
0x18002264b  test    eax, eax
0x18002264d  jle     short loc_180022657
0x18002264f  movzx   eax, ax
0x180022652  or      eax, 80070000h
0x180022657  mov     rcx, cs:WPP_GLOBAL_Control
0x18002265e  cmp     rcx, rdi
0x180022661  jz      short loc_1800226A1
0x180022663  test    byte ptr [rcx+1Ch], 40h
0x180022667  jz      short loc_1800226A1
0x180022669  cmp     byte ptr [rcx+19h], 2
0x18002266d  jb      short loc_1800226A1
0x18002266f  mov     rcx, [rcx+10h]
0x180022673  lea     r8, WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids
0x18002267a  mov     edx, 41h ; 'A'
0x18002267f  mov     r9d, eax
0x180022682  call    WPP_SF_d
0x180022687  jmp     short loc_1800226A1
0x180022689  mov     rcx, rax; pwk
0x18002268c  call    cs:__imp_SubmitThreadpoolWork
0x180022693  nop     dword ptr [rax+rax+00h]
0x180022698  mov     [rsp+28h+pv], 0
0x1800226a1  lea     rcx, ?DhcpGlobalInfoLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800226a8  mov     cs:?fClearedDhcpExceptions@@3EA, 1; uchar fClearedDhcpExceptions
0x1800226af  call    cs:__imp_LeaveCriticalSection
0x1800226b6  nop     dword ptr [rax+rax+00h]
0x1800226bb  mov     rcx, [rsp+28h+pv]
0x1800226c0  test    rcx, rcx
0x1800226c3  jz      short loc_1800226D1
0x1800226c5  call    cs:__imp_FWFreeFirewallRules
0x1800226cc  nop     dword ptr [rax+rax+00h]
0x1800226d1  add     rsp, 20h
0x1800226d5  pop     rdi
0x1800226d6  retn
```
