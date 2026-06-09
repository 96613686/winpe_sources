# FwQuarantineMonitorInitialize

- ea: `0x180091750`
- end: `0x1800919c3`
- name: `FwQuarantineMonitorInitialize`
- size: `627`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180090590`

## callees

- `0x18000af3c`
- `0x18008fc50`
- `0x180091750`
- `0x1800919cc`
- `0x1800cc3b0`
- `0x1800dc58c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180091832`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180091832`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180091774`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800917d0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009183d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800918a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180091900`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180091774`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800917d0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009183d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800918a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180091900`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180091762`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800917be`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18009188e`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180091762`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800917be`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18009188e`
- `api-ms-win-core-threadpool-private-l1-1-0!RegisterWaitForSingleObjectEx` at `0x1800918ee`
- `api-ms-win-core-threadpool-private-l1-1-0!RegisterWaitForSingleObjectEx` at `0x1800918ee`

## pseudocode

```c
__int64 FwQuarantineMonitorInitialize()
{
  signed int LastError; // eax
  unsigned int v1; // ebx
  __int64 v2; // rcx
  __int64 v3; // rdx
  signed int v4; // eax
  HANDLE Thread; // rax
  signed int v6; // eax
  HANDLE EventW; // rax
  signed int v8; // eax
  signed int v9; // eax

  qword_1801314A8 = CreateEventW(0, 1, 0, 0);
  if ( !qword_1801314A8 )
  {
    LastError = GetLastError();
    v1 = LastError;
    if ( LastError > 0 )
      v1 = (unsigned __int16)LastError | 0x80070000;
    v2 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      v3 = 165;
LABEL_31:
      WPP_SF_d(*(_QWORD *)(v2 + 16), v3, WPP_c17a8bb60d3a3c8fffd8e1287cd6d1ad_Traceguids, v1);
      goto LABEL_32;
    }
    goto LABEL_32;
  }
  qword_1801314B0 = CreateEventW(0, 0, 0, 0);
  if ( !qword_1801314B0 )
  {
    v4 = GetLastError();
    v1 = v4;
    if ( v4 > 0 )
      v1 = (unsigned __int16)v4 | 0x80070000;
    v2 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      v3 = 166;
      goto LABEL_31;
    }
LABEL_32:
    if ( (v1 & 0x80000000) != 0 )
    {
LABEL_39:
      FwQuarantineMonitorShutdown();
      return v1;
    }
    return v1;
  }
  Thread = CreateThread(0, 0, FwMonitorQuarantineState, 0, 0, &dword_1801314A0);
  if ( !Thread )
  {
    v6 = GetLastError();
    v1 = v6;
    if ( v6 > 0 )
      v1 = (unsigned __int16)v6 | 0x80070000;
    v2 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      v3 = 167;
      goto LABEL_31;
    }
    goto LABEL_32;
  }
  gFwQuarantineComp = Thread;
  EventW = CreateEventW(0, 0, 0, 0);
  qword_1801314C0 = EventW;
  if ( !EventW )
  {
    v8 = GetLastError();
    v1 = v8;
    if ( v8 > 0 )
      v1 = (unsigned __int16)v8 | 0x80070000;
    v2 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      v3 = 168;
      goto LABEL_31;
    }
    goto LABEL_32;
  }
  qword_1801314B8 = (HANDLE)RegisterWaitForSingleObjectEx(EventW, FwQuarantineFastReconnect, 0, 0xFFFFFFFFLL, 0);
  if ( !qword_1801314B8 )
  {
    v9 = GetLastError();
    v1 = v9;
    if ( v9 > 0 )
      v1 = (unsigned __int16)v9 | 0x80070000;
    v2 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      v3 = 169;
      goto LABEL_31;
    }
    goto LABEL_32;
  }
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFix_NLM_Updates_In_Firewall>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_BugFix_NLM_Updates_In_Firewall>::GetImpl'::`2'::impl) )
  {
    v1 = 0;
    Nla::CNlaManager::RegisterFastReconnectPossible(gFwDynDataNLAComp, qword_1801314C0);
    return v1;
  }
  v1 = Nlm::CNlmManager::RegisterFastReconnectPossible(qword_18012D138, qword_1801314C0);
  if ( (v1 & 0x80000000) != 0 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 170, WPP_c17a8bb60d3a3c8fffd8e1287cd6d1ad_Traceguids, v1);
    goto LABEL_39;
  }
  return v1;
}

```

## disassembly

```asm
0x180091750  push    rbx
0x180091752  sub     rsp, 30h
0x180091756  xor     r9d, r9d; lpName
0x180091759  xor     r8d, r8d; bInitialState
0x18009175c  xor     ecx, ecx; lpEventAttributes
0x18009175e  lea     edx, [r9+1]; bManualReset
0x180091762  call    cs:__imp_CreateEventW
0x180091768  mov     cs:qword_1801314A8, rax
0x18009176f  test    rax, rax
0x180091772  jnz     short loc_1800917B4
0x180091774  call    cs:__imp_GetLastError
0x18009177a  mov     ebx, eax
0x18009177c  test    eax, eax
0x18009177e  jle     short loc_180091789
0x180091780  movzx   ebx, ax
0x180091783  or      ebx, 80070000h
0x180091789  mov     rcx, cs:WPP_GLOBAL_Control
0x180091790  lea     rax, WPP_GLOBAL_Control
0x180091797  cmp     rcx, rax
0x18009179a  jz      loc_180091946
0x1800917a0  test    byte ptr [rcx+1Ch], 1
0x1800917a4  jz      loc_180091946
0x1800917aa  mov     edx, 0A5h
0x1800917af  jmp     loc_180091933
0x1800917b4  xor     r9d, r9d; lpName
0x1800917b7  xor     r8d, r8d; bInitialState
0x1800917ba  xor     edx, edx; bManualReset
0x1800917bc  xor     ecx, ecx; lpEventAttributes
0x1800917be  call    cs:__imp_CreateEventW
0x1800917c4  mov     cs:qword_1801314B0, rax
0x1800917cb  test    rax, rax
0x1800917ce  jnz     short loc_180091810
0x1800917d0  call    cs:__imp_GetLastError
0x1800917d6  mov     ebx, eax
0x1800917d8  test    eax, eax
0x1800917da  jle     short loc_1800917E5
0x1800917dc  movzx   ebx, ax
0x1800917df  or      ebx, 80070000h
0x1800917e5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800917ec  lea     rax, WPP_GLOBAL_Control
0x1800917f3  cmp     rcx, rax
0x1800917f6  jz      loc_180091946
0x1800917fc  test    byte ptr [rcx+1Ch], 1
0x180091800  jz      loc_180091946
0x180091806  mov     edx, 0A6h
0x18009180b  jmp     loc_180091933
0x180091810  lea     rax, dword_1801314A0
0x180091817  xor     r9d, r9d; lpParameter
0x18009181a  mov     [rsp+38h+lpThreadId], rax; lpThreadId
0x18009181f  lea     r8, ?FwMonitorQuarantineState@@YAKPEAX@Z; lpStartAddress
0x180091826  xor     edx, edx; dwStackSize
0x180091828  mov     [rsp+38h+dwCreationFlags], 0; dwCreationFlags
0x180091830  xor     ecx, ecx; lpThreadAttributes
0x180091832  call    cs:__imp_CreateThread
0x180091838  test    rax, rax
0x18009183b  jnz     short loc_18009187D
0x18009183d  call    cs:__imp_GetLastError
0x180091843  mov     ebx, eax
0x180091845  test    eax, eax
0x180091847  jle     short loc_180091852
0x180091849  movzx   ebx, ax
0x18009184c  or      ebx, 80070000h
0x180091852  mov     rcx, cs:WPP_GLOBAL_Control
0x180091859  lea     rax, WPP_GLOBAL_Control
0x180091860  cmp     rcx, rax
0x180091863  jz      loc_180091946
0x180091869  test    byte ptr [rcx+1Ch], 1
0x18009186d  jz      loc_180091946
0x180091873  mov     edx, 0A7h
0x180091878  jmp     loc_180091933
0x18009187d  xor     r9d, r9d; lpName
0x180091880  mov     cs:?gFwQuarantineComp@@3U_FW_QUARANTINE_COMP@@A, rax; _FW_QUARANTINE_COMP gFwQuarantineComp
0x180091887  xor     r8d, r8d; bInitialState
0x18009188a  xor     edx, edx; bManualReset
0x18009188c  xor     ecx, ecx; lpEventAttributes
0x18009188e  call    cs:__imp_CreateEventW
0x180091894  mov     cs:qword_1801314C0, rax
0x18009189b  test    rax, rax
0x18009189e  jnz     short loc_1800918D5
0x1800918a0  call    cs:__imp_GetLastError
0x1800918a6  mov     ebx, eax
0x1800918a8  test    eax, eax
0x1800918aa  jle     short loc_1800918B5
0x1800918ac  movzx   ebx, ax
0x1800918af  or      ebx, 80070000h
0x1800918b5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800918bc  lea     rax, WPP_GLOBAL_Control
0x1800918c3  cmp     rcx, rax
0x1800918c6  jz      short loc_180091946
0x1800918c8  test    byte ptr [rcx+1Ch], 1
0x1800918cc  jz      short loc_180091946
0x1800918ce  mov     edx, 0A8h
0x1800918d3  jmp     short loc_180091933
0x1800918d5  or      r9d, 0FFFFFFFFh
0x1800918d9  mov     [rsp+38h+dwCreationFlags], 0
0x1800918e1  xor     r8d, r8d
0x1800918e4  lea     rdx, ?FwQuarantineFastReconnect@@YAXPEAXE@Z; FwQuarantineFastReconnect(void *,uchar)
0x1800918eb  mov     rcx, rax
0x1800918ee  call    cs:__imp_RegisterWaitForSingleObjectEx
0x1800918f4  mov     cs:qword_1801314B8, rax
0x1800918fb  test    rax, rax
0x1800918fe  jnz     short loc_18009194C
0x180091900  call    cs:__imp_GetLastError
0x180091906  mov     ebx, eax
0x180091908  test    eax, eax
0x18009190a  jle     short loc_180091915
0x18009190c  movzx   ebx, ax
0x18009190f  or      ebx, 80070000h
0x180091915  mov     rcx, cs:WPP_GLOBAL_Control
0x18009191c  lea     rax, WPP_GLOBAL_Control
0x180091923  cmp     rcx, rax
0x180091926  jz      short loc_180091946
0x180091928  test    byte ptr [rcx+1Ch], 1
0x18009192c  jz      short loc_180091946
0x18009192e  mov     edx, 0A9h
0x180091933  mov     rcx, [rcx+10h]
0x180091937  lea     r8, WPP_c17a8bb60d3a3c8fffd8e1287cd6d1ad_Traceguids
0x18009193e  mov     r9d, ebx
0x180091941  call    WPP_SF_d
0x180091946  test    ebx, ebx
0x180091948  jns     short loc_1800919BB
0x18009194a  jmp     short loc_1800919A6
0x18009194c  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_BugFix_NLM_Updates_In_Firewall@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_BugFix_NLM_Updates_In_Firewall@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFix_NLM_Updates_In_Firewall> `wil::Feature<__WilFeatureTraits_Feature_BugFix_NLM_Updates_In_Firewall>::GetImpl(void)'::`2'::impl
0x180091953  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_BugFix_NLM_Updates_In_Firewall@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFix_NLM_Updates_In_Firewall>::__private_IsEnabled(void)
0x180091958  mov     rdx, cs:qword_1801314C0; void *
0x18009195f  test    al, al
0x180091961  jz      short loc_1800919AD
0x180091963  mov     rcx, cs:qword_18012D138; this
0x18009196a  call    ?RegisterFastReconnectPossible@CNlmManager@Nlm@@QEAAJPEAX@Z; Nlm::CNlmManager::RegisterFastReconnectPossible(void *)
0x18009196f  mov     ebx, eax
0x180091971  test    eax, eax
0x180091973  jns     short loc_1800919BB
0x180091975  mov     rcx, cs:WPP_GLOBAL_Control
0x18009197c  lea     rax, WPP_GLOBAL_Control
0x180091983  cmp     rcx, rax
0x180091986  jz      short loc_1800919A6
0x180091988  test    byte ptr [rcx+1Ch], 1
0x18009198c  jz      short loc_1800919A6
0x18009198e  mov     rcx, [rcx+10h]
0x180091992  lea     r8, WPP_c17a8bb60d3a3c8fffd8e1287cd6d1ad_Traceguids
0x180091999  mov     edx, 0AAh
0x18009199e  mov     r9d, ebx
0x1800919a1  call    WPP_SF_d
0x1800919a6  call    FwQuarantineMonitorShutdown
0x1800919ab  jmp     short loc_1800919BB
0x1800919ad  mov     rcx, cs:?gFwDynDataNLAComp@@3U_tagFWDYNDATANLACOMP@@A; this
0x1800919b4  xor     ebx, ebx
0x1800919b6  call    ?RegisterFastReconnectPossible@CNlaManager@Nla@@QEAAXPEAX@Z; Nla::CNlaManager::RegisterFastReconnectPossible(void *)
0x1800919bb  mov     eax, ebx
0x1800919bd  add     rsp, 30h
0x1800919c1  pop     rbx
0x1800919c2  retn
```
