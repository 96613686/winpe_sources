# ClearPersistentDhcpExceptions(void)

- ea: `0x18002f690`
- end: `0x18002f7a3`
- name: `?ClearPersistentDhcpExceptions@@YAXXZ`
- size: `275`
- prototype: `void(void)`
- caller_count: `5`
- callee_count: `4`
- tags: ``

## callers

- `0x1800222b8`
- `0x18002ef3c`
- `0x18002f0f8`
- `0x18006e294`
- `0x180070598`

## callees

- `0x18000c110`
- `0x18000c750`
- `0x18002f690`
- `0x180031410`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002f6a6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002f6a6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002f787`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002f787`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f723`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f723`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18002f76a`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18002f76a`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18002f711`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18002f711`
- `FirewallAPI!FWFreeFirewallRules` at `0x18002f797`
- `FirewallAPI!FWFreeFirewallRules` at `0x18002f797`

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
      ThreadpoolWork = CreateThreadpoolWork(FirewallCleanupBackgroundProcessing, pv, &g_FwEnvironment);
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
    FWFreeFirewallRules();
}

```

## disassembly

```asm
0x18002f690  push    rdi
0x18002f692  sub     rsp, 20h
0x18002f696  lea     rcx, ?DhcpGlobalInfoLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18002f69d  mov     [rsp+28h+pv], 0
0x18002f6a6  call    cs:__imp_EnterCriticalSection
0x18002f6ac  cmp     cs:?fClearedDhcpExceptions@@3EA, 0; uchar fClearedDhcpExceptions
0x18002f6b3  jnz     loc_18002F779
0x18002f6b9  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f6c0  lea     rdi, WPP_GLOBAL_Control
0x18002f6c7  cmp     rcx, rdi
0x18002f6ca  jz      short loc_18002F6F0
0x18002f6cc  test    dword ptr [rcx+1Ch], 200h
0x18002f6d3  jz      short loc_18002F6F0
0x18002f6d5  cmp     byte ptr [rcx+19h], 5
0x18002f6d9  jb      short loc_18002F6F0
0x18002f6db  mov     rcx, [rcx+10h]
0x18002f6df  lea     r8, WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids
0x18002f6e6  mov     edx, 40h ; '@'
0x18002f6eb  call    WPP_SF_
0x18002f6f0  lea     rcx, [rsp+28h+pv]; struct _tag_FW_RULE **
0x18002f6f5  call    ?NatGetExistingDhcpRules@@YAKPEAPEAU_tag_FW_RULE@@@Z; NatGetExistingDhcpRules(_tag_FW_RULE * *)
0x18002f6fa  test    eax, eax
0x18002f6fc  jnz     short loc_18002F779
0x18002f6fe  mov     rdx, [rsp+28h+pv]; pv
0x18002f703  lea     r8, ?g_FwEnvironment@@3U_TP_CALLBACK_ENVIRON_V3@@A; pcbe
0x18002f70a  lea     rcx, ?FirewallCleanupBackgroundProcessing@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x18002f711  call    cs:__imp_CreateThreadpoolWork
0x18002f717  mov     cs:?g_FirewallCleanupBackgroundWork@@3PEAU_TP_WORK@@EA, rax; _TP_WORK * g_FirewallCleanupBackgroundWork
0x18002f71e  test    rax, rax
0x18002f721  jnz     short loc_18002F767
0x18002f723  call    cs:__imp_GetLastError
0x18002f729  test    eax, eax
0x18002f72b  jle     short loc_18002F735
0x18002f72d  movzx   eax, ax
0x18002f730  or      eax, 80070000h
0x18002f735  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f73c  cmp     rcx, rdi
0x18002f73f  jz      short loc_18002F779
0x18002f741  test    byte ptr [rcx+1Ch], 40h
0x18002f745  jz      short loc_18002F779
0x18002f747  cmp     byte ptr [rcx+19h], 2
0x18002f74b  jb      short loc_18002F779
0x18002f74d  mov     rcx, [rcx+10h]
0x18002f751  lea     r8, WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids
0x18002f758  mov     edx, 41h ; 'A'
0x18002f75d  mov     r9d, eax
0x18002f760  call    WPP_SF_d
0x18002f765  jmp     short loc_18002F779
0x18002f767  mov     rcx, rax; pwk
0x18002f76a  call    cs:__imp_SubmitThreadpoolWork
0x18002f770  mov     [rsp+28h+pv], 0
0x18002f779  lea     rcx, ?DhcpGlobalInfoLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18002f780  mov     cs:?fClearedDhcpExceptions@@3EA, 1; uchar fClearedDhcpExceptions
0x18002f787  call    cs:__imp_LeaveCriticalSection
0x18002f78d  mov     rcx, [rsp+28h+pv]
0x18002f792  test    rcx, rcx
0x18002f795  jz      short loc_18002F79D
0x18002f797  call    cs:__imp_FWFreeFirewallRules
0x18002f79d  add     rsp, 20h
0x18002f7a1  pop     rdi
0x18002f7a2  retn
```
