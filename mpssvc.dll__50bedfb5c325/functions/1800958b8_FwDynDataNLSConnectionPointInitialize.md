# FwDynDataNLSConnectionPointInitialize

- ea: `0x1800958b8`
- end: `0x180095a3e`
- name: `FwDynDataNLSConnectionPointInitialize`
- size: `390`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180095030`

## callees

- `0x18000a710`
- `0x180094610`
- `0x1800958b8`
- `0x180095a44`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800959ca`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800959ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009594e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800959db`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009594e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800959db`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180095936`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180095936`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180095a20`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180095a20`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800958dc`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800958dc`

## pseudocode

```c
__int64 FwDynDataNLSConnectionPointInitialize()
{
  int v0; // ebx
  signed int v1; // eax
  __int64 v2; // rcx
  __int64 v3; // rdx
  HANDLE Thread; // rax
  signed int LastError; // eax

  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFix_NLM_Updates_In_Firewall>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_BugFix_NLM_Updates_In_Firewall>::GetImpl'::`2'::impl) )
    dword_180133CA8 = 0;
  v0 = CoInitializeEx(0, 0);
  if ( v0 < 0 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_d(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        39,
        WPP_0043c1167b9d39bdb1a15ac1c4aee9c9_Traceguids,
        (unsigned int)v0);
    goto LABEL_22;
  }
  qword_180133330 = CreateEventW(0, 0, 0, 0);
  if ( qword_180133330 )
  {
    Thread = CreateThread(0, 0, (LPTHREAD_START_ROUTINE)FwDynDataNotifySinkProc, lpParameter, 0, &ThreadId);
    if ( Thread )
    {
      qword_180133320 = Thread;
    }
    else
    {
      LastError = GetLastError();
      v0 = LastError;
      if ( LastError > 0 )
        v0 = (unsigned __int16)LastError | 0x80070000;
      v2 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      {
        v3 = 41;
        goto LABEL_13;
      }
    }
  }
  else
  {
    v1 = GetLastError();
    v0 = v1;
    if ( v1 > 0 )
      v0 = (unsigned __int16)v1 | 0x80070000;
    v2 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      v3 = 40;
LABEL_13:
      WPP_SF_d(*(_QWORD *)(v2 + 16), v3, WPP_0043c1167b9d39bdb1a15ac1c4aee9c9_Traceguids, (unsigned int)v0);
    }
  }
  CoUninitialize();
  if ( v0 < 0 )
LABEL_22:
    FwDynDataNLSConnectionPointShutdown();
  return (unsigned int)v0;
}

```

## disassembly

```asm
0x1800958b8  push    rbx
0x1800958ba  sub     rsp, 30h
0x1800958be  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_BugFix_NLM_Updates_In_Firewall@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_BugFix_NLM_Updates_In_Firewall@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFix_NLM_Updates_In_Firewall> `wil::Feature<__WilFeatureTraits_Feature_BugFix_NLM_Updates_In_Firewall>::GetImpl(void)'::`2'::impl
0x1800958c5  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_BugFix_NLM_Updates_In_Firewall@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFix_NLM_Updates_In_Firewall>::__private_IsEnabled(void)
0x1800958ca  test    al, al
0x1800958cc  jnz     short loc_1800958D8
0x1800958ce  mov     cs:dword_180133CA8, 0
0x1800958d8  xor     edx, edx; dwCoInit
0x1800958da  xor     ecx, ecx; pvReserved
0x1800958dc  call    cs:__imp_CoInitializeEx
0x1800958e3  nop     dword ptr [rax+rax+00h]
0x1800958e8  mov     ebx, eax
0x1800958ea  test    eax, eax
0x1800958ec  jns     short loc_18009592C
0x1800958ee  mov     rcx, cs:WPP_GLOBAL_Control
0x1800958f5  lea     rax, WPP_GLOBAL_Control
0x1800958fc  cmp     rcx, rax
0x1800958ff  jz      loc_180095A30
0x180095905  test    byte ptr [rcx+1Ch], 1
0x180095909  jz      loc_180095A30
0x18009590f  mov     rcx, [rcx+10h]
0x180095913  lea     r8, WPP_0043c1167b9d39bdb1a15ac1c4aee9c9_Traceguids
0x18009591a  mov     edx, 27h ; '''
0x18009591f  mov     r9d, ebx
0x180095922  call    WPP_SF_d
0x180095927  jmp     loc_180095A30
0x18009592c  xor     r9d, r9d; lpName
0x18009592f  xor     r8d, r8d; bInitialState
0x180095932  xor     edx, edx; bManualReset
0x180095934  xor     ecx, ecx; lpEventAttributes
0x180095936  call    cs:__imp_CreateEventW
0x18009593d  nop     dword ptr [rax+rax+00h]
0x180095942  mov     cs:qword_180133330, rax
0x180095949  test    rax, rax
0x18009594c  jnz     short loc_1800959A4
0x18009594e  call    cs:__imp_GetLastError
0x180095955  nop     dword ptr [rax+rax+00h]
0x18009595a  mov     ebx, eax
0x18009595c  test    eax, eax
0x18009595e  jle     short loc_180095969
0x180095960  movzx   ebx, ax
0x180095963  or      ebx, 80070000h
0x180095969  mov     rcx, cs:WPP_GLOBAL_Control
0x180095970  lea     rax, WPP_GLOBAL_Control
0x180095977  cmp     rcx, rax
0x18009597a  jz      loc_180095A20
0x180095980  test    byte ptr [rcx+1Ch], 1
0x180095984  jz      loc_180095A20
0x18009598a  mov     edx, 28h ; '('
0x18009598f  mov     rcx, [rcx+10h]
0x180095993  lea     r8, WPP_0043c1167b9d39bdb1a15ac1c4aee9c9_Traceguids
0x18009599a  mov     r9d, ebx
0x18009599d  call    WPP_SF_d
0x1800959a2  jmp     short loc_180095A20
0x1800959a4  mov     r9, cs:lpParameter; lpParameter
0x1800959ab  lea     rax, ThreadId
0x1800959b2  mov     [rsp+38h+lpThreadId], rax; lpThreadId
0x1800959b7  lea     r8, FwDynDataNotifySinkProc; lpStartAddress
0x1800959be  xor     edx, edx; dwStackSize
0x1800959c0  mov     [rsp+38h+dwCreationFlags], 0; dwCreationFlags
0x1800959c8  xor     ecx, ecx; lpThreadAttributes
0x1800959ca  call    cs:__imp_CreateThread
0x1800959d1  nop     dword ptr [rax+rax+00h]
0x1800959d6  test    rax, rax
0x1800959d9  jnz     short loc_180095A19
0x1800959db  call    cs:__imp_GetLastError
0x1800959e2  nop     dword ptr [rax+rax+00h]
0x1800959e7  mov     ebx, eax
0x1800959e9  test    eax, eax
0x1800959eb  jle     short loc_1800959F6
0x1800959ed  movzx   ebx, ax
0x1800959f0  or      ebx, 80070000h
0x1800959f6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800959fd  lea     rax, WPP_GLOBAL_Control
0x180095a04  cmp     rcx, rax
0x180095a07  jz      short loc_180095A20
0x180095a09  test    byte ptr [rcx+1Ch], 1
0x180095a0d  jz      short loc_180095A20
0x180095a0f  mov     edx, 29h ; ')'
0x180095a14  jmp     loc_18009598F
0x180095a19  mov     cs:qword_180133320, rax
0x180095a20  call    cs:__imp_CoUninitialize
0x180095a27  nop     dword ptr [rax+rax+00h]
0x180095a2c  test    ebx, ebx
0x180095a2e  jns     short loc_180095A35
0x180095a30  call    FwDynDataNLSConnectionPointShutdown
0x180095a35  mov     eax, ebx
0x180095a37  add     rsp, 30h
0x180095a3b  pop     rbx
0x180095a3c  retn
```
