# FwDynDataNLSConnectionPointInitialize

- ea: `0x180090db4`
- end: `0x180090f12`
- name: `FwDynDataNLSConnectionPointInitialize`
- size: `350`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180090590`

## callees

- `0x18000af3c`
- `0x18008fc50`
- `0x180090db4`
- `0x180090f18`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180090eb4`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180090eb4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180090e3e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180090ebf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180090e3e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180090ebf`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180090e2c`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180090e2c`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180090efb`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180090efb`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180090dd8`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180090dd8`

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

  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFix_NLM_Updates_In_Firewall>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_BugFix_NLM_Updates_In_Firewall>::GetImpl'::`2'::impl) )
    dword_18012DAD8 = 0;
  v0 = CoInitializeEx(0, 0);
  if ( v0 < 0 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_d(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        39,
        WPP_c17a8bb60d3a3c8fffd8e1287cd6d1ad_Traceguids,
        (unsigned int)v0);
    goto LABEL_22;
  }
  qword_18012D160 = CreateEventW(0, 0, 0, 0);
  if ( qword_18012D160 )
  {
    Thread = CreateThread(0, 0, (LPTHREAD_START_ROUTINE)FwDynDataNotifySinkProc, lpParameter, 0, &ThreadId);
    if ( Thread )
    {
      qword_18012D150 = Thread;
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
      WPP_SF_d(*(_QWORD *)(v2 + 16), v3, WPP_c17a8bb60d3a3c8fffd8e1287cd6d1ad_Traceguids, (unsigned int)v0);
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
0x180090db4  push    rbx
0x180090db6  sub     rsp, 30h
0x180090dba  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_BugFix_NLM_Updates_In_Firewall@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_BugFix_NLM_Updates_In_Firewall@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFix_NLM_Updates_In_Firewall> `wil::Feature<__WilFeatureTraits_Feature_BugFix_NLM_Updates_In_Firewall>::GetImpl(void)'::`2'::impl
0x180090dc1  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_BugFix_NLM_Updates_In_Firewall@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFix_NLM_Updates_In_Firewall>::__private_IsEnabled(void)
0x180090dc6  test    al, al
0x180090dc8  jnz     short loc_180090DD4
0x180090dca  mov     cs:dword_18012DAD8, 0
0x180090dd4  xor     edx, edx; dwCoInit
0x180090dd6  xor     ecx, ecx; pvReserved
0x180090dd8  call    cs:__imp_CoInitializeEx
0x180090dde  mov     ebx, eax
0x180090de0  test    eax, eax
0x180090de2  jns     short loc_180090E22
0x180090de4  mov     rcx, cs:WPP_GLOBAL_Control
0x180090deb  lea     rax, WPP_GLOBAL_Control
0x180090df2  cmp     rcx, rax
0x180090df5  jz      loc_180090F05
0x180090dfb  test    byte ptr [rcx+1Ch], 1
0x180090dff  jz      loc_180090F05
0x180090e05  mov     rcx, [rcx+10h]
0x180090e09  lea     r8, WPP_c17a8bb60d3a3c8fffd8e1287cd6d1ad_Traceguids
0x180090e10  mov     edx, 27h ; '''
0x180090e15  mov     r9d, ebx
0x180090e18  call    WPP_SF_d
0x180090e1d  jmp     loc_180090F05
0x180090e22  xor     r9d, r9d; lpName
0x180090e25  xor     r8d, r8d; bInitialState
0x180090e28  xor     edx, edx; bManualReset
0x180090e2a  xor     ecx, ecx; lpEventAttributes
0x180090e2c  call    cs:__imp_CreateEventW
0x180090e32  mov     cs:qword_18012D160, rax
0x180090e39  test    rax, rax
0x180090e3c  jnz     short loc_180090E8E
0x180090e3e  call    cs:__imp_GetLastError
0x180090e44  mov     ebx, eax
0x180090e46  test    eax, eax
0x180090e48  jle     short loc_180090E53
0x180090e4a  movzx   ebx, ax
0x180090e4d  or      ebx, 80070000h
0x180090e53  mov     rcx, cs:WPP_GLOBAL_Control
0x180090e5a  lea     rax, WPP_GLOBAL_Control
0x180090e61  cmp     rcx, rax
0x180090e64  jz      loc_180090EFB
0x180090e6a  test    byte ptr [rcx+1Ch], 1
0x180090e6e  jz      loc_180090EFB
0x180090e74  mov     edx, 28h ; '('
0x180090e79  mov     rcx, [rcx+10h]
0x180090e7d  lea     r8, WPP_c17a8bb60d3a3c8fffd8e1287cd6d1ad_Traceguids
0x180090e84  mov     r9d, ebx
0x180090e87  call    WPP_SF_d
0x180090e8c  jmp     short loc_180090EFB
0x180090e8e  mov     r9, cs:lpParameter; lpParameter
0x180090e95  lea     rax, ThreadId
0x180090e9c  mov     [rsp+38h+lpThreadId], rax; lpThreadId
0x180090ea1  lea     r8, FwDynDataNotifySinkProc; lpStartAddress
0x180090ea8  xor     edx, edx; dwStackSize
0x180090eaa  mov     [rsp+38h+dwCreationFlags], 0; dwCreationFlags
0x180090eb2  xor     ecx, ecx; lpThreadAttributes
0x180090eb4  call    cs:__imp_CreateThread
0x180090eba  test    rax, rax
0x180090ebd  jnz     short loc_180090EF4
0x180090ebf  call    cs:__imp_GetLastError
0x180090ec5  mov     ebx, eax
0x180090ec7  test    eax, eax
0x180090ec9  jle     short loc_180090ED4
0x180090ecb  movzx   ebx, ax
0x180090ece  or      ebx, 80070000h
0x180090ed4  mov     rcx, cs:WPP_GLOBAL_Control
0x180090edb  lea     rax, WPP_GLOBAL_Control
0x180090ee2  cmp     rcx, rax
0x180090ee5  jz      short loc_180090EFB
0x180090ee7  test    byte ptr [rcx+1Ch], 1
0x180090eeb  jz      short loc_180090EFB
0x180090eed  mov     edx, 29h ; ')'
0x180090ef2  jmp     short loc_180090E79
0x180090ef4  mov     cs:qword_18012D150, rax
0x180090efb  call    cs:__imp_CoUninitialize
0x180090f01  test    ebx, ebx
0x180090f03  jns     short loc_180090F0A
0x180090f05  call    FwDynDataNLSConnectionPointShutdown
0x180090f0a  mov     eax, ebx
0x180090f0c  add     rsp, 30h
0x180090f10  pop     rbx
0x180090f11  retn
```
