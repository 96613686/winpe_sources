# FwQuarantineMonitorInitialize

- ea: `0x180096338`
- end: `0x1800965f0`
- name: `FwQuarantineMonitorInitialize`
- size: `696`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180095030`

## callees

- `0x18000a710`
- `0x180094610`
- `0x180096338`
- `0x1800965f8`
- `0x1800d3ae0`
- `0x1800e25bc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180096432`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180096432`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180096362`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800963ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180096443`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800964b2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180096526`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180096362`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800963ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180096443`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800964b2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180096526`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18009634a`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800963b2`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18009649a`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18009634a`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800963b2`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18009649a`
- `api-ms-win-core-threadpool-private-l1-1-0!RegisterWaitForSingleObjectEx` at `0x18009650e`
- `api-ms-win-core-threadpool-private-l1-1-0!RegisterWaitForSingleObjectEx` at `0x18009650e`

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

  qword_180137668 = CreateEventW(0, 1, 0, 0);
  if ( !qword_180137668 )
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
      WPP_SF_d(*(_QWORD *)(v2 + 16), v3, WPP_0043c1167b9d39bdb1a15ac1c4aee9c9_Traceguids, v1);
      goto LABEL_32;
    }
    goto LABEL_32;
  }
  qword_180137670 = CreateEventW(0, 0, 0, 0);
  if ( !qword_180137670 )
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
  Thread = CreateThread(0, 0, FwMonitorQuarantineState, 0, 0, &dword_180137660);
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
  qword_180137680 = EventW;
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
  qword_180137678 = (HANDLE)RegisterWaitForSingleObjectEx(EventW, FwQuarantineFastReconnect, 0, 0xFFFFFFFFLL, 0);
  if ( !qword_180137678 )
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
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFix_NLM_Updates_In_Firewall>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_BugFix_NLM_Updates_In_Firewall>::GetImpl'::`2'::impl) )
  {
    v1 = 0;
    Nla::CNlaManager::RegisterFastReconnectPossible(gFwDynDataNLAComp, qword_180137680);
    return v1;
  }
  v1 = Nlm::CNlmManager::RegisterFastReconnectPossible(qword_180133308, qword_180137680);
  if ( (v1 & 0x80000000) != 0 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 170, WPP_0043c1167b9d39bdb1a15ac1c4aee9c9_Traceguids, v1);
    goto LABEL_39;
  }
  return v1;
}

```

## disassembly

```asm
0x180096338  push    rbx
0x18009633a  sub     rsp, 30h
0x18009633e  xor     r9d, r9d; lpName
0x180096341  xor     r8d, r8d; bInitialState
0x180096344  xor     ecx, ecx; lpEventAttributes
0x180096346  lea     edx, [r9+1]; bManualReset
0x18009634a  call    cs:__imp_CreateEventW
0x180096351  nop     dword ptr [rax+rax+00h]
0x180096356  mov     cs:qword_180137668, rax
0x18009635d  test    rax, rax
0x180096360  jnz     short loc_1800963A8
0x180096362  call    cs:__imp_GetLastError
0x180096369  nop     dword ptr [rax+rax+00h]
0x18009636e  mov     ebx, eax
0x180096370  test    eax, eax
0x180096372  jle     short loc_18009637D
0x180096374  movzx   ebx, ax
0x180096377  or      ebx, 80070000h
0x18009637d  mov     rcx, cs:WPP_GLOBAL_Control
0x180096384  lea     rax, WPP_GLOBAL_Control
0x18009638b  cmp     rcx, rax
0x18009638e  jz      loc_180096572
0x180096394  test    byte ptr [rcx+1Ch], 1
0x180096398  jz      loc_180096572
0x18009639e  mov     edx, 0A5h
0x1800963a3  jmp     loc_18009655F
0x1800963a8  xor     r9d, r9d; lpName
0x1800963ab  xor     r8d, r8d; bInitialState
0x1800963ae  xor     edx, edx; bManualReset
0x1800963b0  xor     ecx, ecx; lpEventAttributes
0x1800963b2  call    cs:__imp_CreateEventW
0x1800963b9  nop     dword ptr [rax+rax+00h]
0x1800963be  mov     cs:qword_180137670, rax
0x1800963c5  test    rax, rax
0x1800963c8  jnz     short loc_180096410
0x1800963ca  call    cs:__imp_GetLastError
0x1800963d1  nop     dword ptr [rax+rax+00h]
0x1800963d6  mov     ebx, eax
0x1800963d8  test    eax, eax
0x1800963da  jle     short loc_1800963E5
0x1800963dc  movzx   ebx, ax
0x1800963df  or      ebx, 80070000h
0x1800963e5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800963ec  lea     rax, WPP_GLOBAL_Control
0x1800963f3  cmp     rcx, rax
0x1800963f6  jz      loc_180096572
0x1800963fc  test    byte ptr [rcx+1Ch], 1
0x180096400  jz      loc_180096572
0x180096406  mov     edx, 0A6h
0x18009640b  jmp     loc_18009655F
0x180096410  lea     rax, dword_180137660
0x180096417  xor     r9d, r9d; lpParameter
0x18009641a  mov     [rsp+38h+lpThreadId], rax; lpThreadId
0x18009641f  lea     r8, ?FwMonitorQuarantineState@@YAKPEAX@Z; lpStartAddress
0x180096426  xor     edx, edx; dwStackSize
0x180096428  mov     [rsp+38h+dwCreationFlags], 0; dwCreationFlags
0x180096430  xor     ecx, ecx; lpThreadAttributes
0x180096432  call    cs:__imp_CreateThread
0x180096439  nop     dword ptr [rax+rax+00h]
0x18009643e  test    rax, rax
0x180096441  jnz     short loc_180096489
0x180096443  call    cs:__imp_GetLastError
0x18009644a  nop     dword ptr [rax+rax+00h]
0x18009644f  mov     ebx, eax
0x180096451  test    eax, eax
0x180096453  jle     short loc_18009645E
0x180096455  movzx   ebx, ax
0x180096458  or      ebx, 80070000h
0x18009645e  mov     rcx, cs:WPP_GLOBAL_Control
0x180096465  lea     rax, WPP_GLOBAL_Control
0x18009646c  cmp     rcx, rax
0x18009646f  jz      loc_180096572
0x180096475  test    byte ptr [rcx+1Ch], 1
0x180096479  jz      loc_180096572
0x18009647f  mov     edx, 0A7h
0x180096484  jmp     loc_18009655F
0x180096489  xor     r9d, r9d; lpName
0x18009648c  mov     cs:?gFwQuarantineComp@@3U_FW_QUARANTINE_COMP@@A, rax; _FW_QUARANTINE_COMP gFwQuarantineComp
0x180096493  xor     r8d, r8d; bInitialState
0x180096496  xor     edx, edx; bManualReset
0x180096498  xor     ecx, ecx; lpEventAttributes
0x18009649a  call    cs:__imp_CreateEventW
0x1800964a1  nop     dword ptr [rax+rax+00h]
0x1800964a6  mov     cs:qword_180137680, rax
0x1800964ad  test    rax, rax
0x1800964b0  jnz     short loc_1800964F5
0x1800964b2  call    cs:__imp_GetLastError
0x1800964b9  nop     dword ptr [rax+rax+00h]
0x1800964be  mov     ebx, eax
0x1800964c0  test    eax, eax
0x1800964c2  jle     short loc_1800964CD
0x1800964c4  movzx   ebx, ax
0x1800964c7  or      ebx, 80070000h
0x1800964cd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800964d4  lea     rax, WPP_GLOBAL_Control
0x1800964db  cmp     rcx, rax
0x1800964de  jz      loc_180096572
0x1800964e4  test    byte ptr [rcx+1Ch], 1
0x1800964e8  jz      loc_180096572
0x1800964ee  mov     edx, 0A8h
0x1800964f3  jmp     short loc_18009655F
0x1800964f5  or      r9d, 0FFFFFFFFh
0x1800964f9  mov     [rsp+38h+dwCreationFlags], 0
0x180096501  xor     r8d, r8d
0x180096504  lea     rdx, ?FwQuarantineFastReconnect@@YAXPEAXE@Z; FwQuarantineFastReconnect(void *,uchar)
0x18009650b  mov     rcx, rax
0x18009650e  call    cs:__imp_RegisterWaitForSingleObjectEx
0x180096515  nop     dword ptr [rax+rax+00h]
0x18009651a  mov     cs:qword_180137678, rax
0x180096521  test    rax, rax
0x180096524  jnz     short loc_180096578
0x180096526  call    cs:__imp_GetLastError
0x18009652d  nop     dword ptr [rax+rax+00h]
0x180096532  mov     ebx, eax
0x180096534  test    eax, eax
0x180096536  jle     short loc_180096541
0x180096538  movzx   ebx, ax
0x18009653b  or      ebx, 80070000h
0x180096541  mov     rcx, cs:WPP_GLOBAL_Control
0x180096548  lea     rax, WPP_GLOBAL_Control
0x18009654f  cmp     rcx, rax
0x180096552  jz      short loc_180096572
0x180096554  test    byte ptr [rcx+1Ch], 1
0x180096558  jz      short loc_180096572
0x18009655a  mov     edx, 0A9h
0x18009655f  mov     rcx, [rcx+10h]
0x180096563  lea     r8, WPP_0043c1167b9d39bdb1a15ac1c4aee9c9_Traceguids
0x18009656a  mov     r9d, ebx
0x18009656d  call    WPP_SF_d
0x180096572  test    ebx, ebx
0x180096574  jns     short loc_1800965E7
0x180096576  jmp     short loc_1800965D2
0x180096578  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_BugFix_NLM_Updates_In_Firewall@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_BugFix_NLM_Updates_In_Firewall@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFix_NLM_Updates_In_Firewall> `wil::Feature<__WilFeatureTraits_Feature_BugFix_NLM_Updates_In_Firewall>::GetImpl(void)'::`2'::impl
0x18009657f  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_BugFix_NLM_Updates_In_Firewall@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFix_NLM_Updates_In_Firewall>::__private_IsEnabled(void)
0x180096584  mov     rdx, cs:qword_180137680; void *
0x18009658b  test    al, al
0x18009658d  jz      short loc_1800965D9
0x18009658f  mov     rcx, cs:qword_180133308; this
0x180096596  call    ?RegisterFastReconnectPossible@CNlmManager@Nlm@@QEAAJPEAX@Z; Nlm::CNlmManager::RegisterFastReconnectPossible(void *)
0x18009659b  mov     ebx, eax
0x18009659d  test    eax, eax
0x18009659f  jns     short loc_1800965E7
0x1800965a1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800965a8  lea     rax, WPP_GLOBAL_Control
0x1800965af  cmp     rcx, rax
0x1800965b2  jz      short loc_1800965D2
0x1800965b4  test    byte ptr [rcx+1Ch], 1
0x1800965b8  jz      short loc_1800965D2
0x1800965ba  mov     rcx, [rcx+10h]
0x1800965be  lea     r8, WPP_0043c1167b9d39bdb1a15ac1c4aee9c9_Traceguids
0x1800965c5  mov     edx, 0AAh
0x1800965ca  mov     r9d, ebx
0x1800965cd  call    WPP_SF_d
0x1800965d2  call    FwQuarantineMonitorShutdown
0x1800965d7  jmp     short loc_1800965E7
0x1800965d9  mov     rcx, cs:?gFwDynDataNLAComp@@3U_tagFWDYNDATANLACOMP@@A; this
0x1800965e0  xor     ebx, ebx
0x1800965e2  call    ?RegisterFastReconnectPossible@CNlaManager@Nla@@QEAAXPEAX@Z; Nla::CNlaManager::RegisterFastReconnectPossible(void *)
0x1800965e7  mov     eax, ebx
0x1800965e9  add     rsp, 30h
0x1800965ed  pop     rbx
0x1800965ee  retn
```
