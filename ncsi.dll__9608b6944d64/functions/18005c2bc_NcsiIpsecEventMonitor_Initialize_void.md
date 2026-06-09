# NcsiIpsecEventMonitor::Initialize(void)

- ea: `0x18005c2bc`
- end: `0x18005c543`
- name: `?Initialize@NcsiIpsecEventMonitor@@QEAAXXZ`
- size: `647`
- prototype: `void __fastcall(NcsiIpsecEventMonitor *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180050300`

## callees

- `0x180010200`
- `0x180011a58`
- `0x18003f248`
- `0x180047240`
- `0x18004813c`
- `0x18005c2bc`
- `0x18005c73c`
- `0x18005c778`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005c37d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005c449`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005c4c9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005c37d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005c449`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005c4c9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005c2e0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005c2e0`
- `ext-ms-win-wevtapi-eventlog-l1-1-0!EvtSubscribe` at `0x18005c33a`
- `ext-ms-win-wevtapi-eventlog-l1-1-0!EvtSubscribe` at `0x18005c492`
- `ext-ms-win-wevtapi-eventlog-l1-1-0!EvtSubscribe` at `0x18005c33a`
- `ext-ms-win-wevtapi-eventlog-l1-1-0!EvtSubscribe` at `0x18005c492`
- `ext-ms-win-wevtapi-eventlog-l1-1-1!EvtOpenSession` at `0x18005c40e`
- `ext-ms-win-wevtapi-eventlog-l1-1-1!EvtOpenSession` at `0x18005c40e`

## string_xrefs

- `0x18005c328`: `Microsoft-Windows-Windows Firewall With Advanced Security/Firewall`
- `0x18005c47f`: `Microsoft-Windows-Windows Firewall With Advanced Security/Firewall`

## pseudocode

```c
void __fastcall NcsiIpsecEventMonitor::Initialize(NcsiIpsecEventMonitor *this)
{
  EVT_HANDLE v1; // rax
  __int64 v2; // rcx
  DWORD v3; // eax
  EVT_HANDLE v4; // rax
  DWORD LastError; // eax
  __int64 v6; // rdx
  EVT_HANDLE v7; // rax
  __int64 v8; // rcx
  EVT_HANDLE v9; // [rsp+40h] [rbp-48h] BYREF
  _OWORD Login[2]; // [rsp+48h] [rbp-40h] BYREF
  __int64 v11; // [rsp+68h] [rbp-20h]

  if ( !(unsigned __int8)IsEvtOpenSessionPresent(this) )
  {
    SetLastError(0x78u);
    return;
  }
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_NCSI_Fix_RemoteEvtSubscribe>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_NCSI_Fix_RemoteEvtSubscribe>::GetImpl'::`2'::impl) )
  {
    v11 = 0;
    memset(Login, 0, sizeof(Login));
    v4 = EvtOpenSession(EvtRpcLogin, Login, 0, 0);
    v9 = v4;
    if ( v4 )
    {
      v7 = EvtSubscribe(
             v4,
             0,
             L"Microsoft-Windows-Windows Firewall With Advanced Security/Firewall",
             L"*[System/EventID='2008']",
             0,
             qword_18009B230,
             NcsiIpsecEventMonitor::EventCallback,
             1u);
      wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int EvtCloseSafe(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
        v8,
        v7);
      if ( g_ncsiIpsecEventMonitor )
      {
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 0x10) != 0
          && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 5u )
        {
          WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 14, WPP_8cdf5a0688f636034b8a43fdd2ac3dae_Traceguids);
        }
        goto LABEL_28;
      }
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 0x10) == 0
        || *(_BYTE *)(WPP_GLOBAL_Control + 25LL) < 2u )
      {
LABEL_28:
        wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int EvtCloseSafe(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int EvtCloseSafe(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v9);
        return;
      }
      LastError = GetLastError();
      v6 = 13;
    }
    else
    {
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 0x10) == 0
        || *(_BYTE *)(WPP_GLOBAL_Control + 25LL) < 2u )
      {
        goto LABEL_28;
      }
      LastError = GetLastError();
      v6 = 12;
    }
    WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), v6, WPP_8cdf5a0688f636034b8a43fdd2ac3dae_Traceguids, LastError);
    goto LABEL_28;
  }
  v1 = EvtSubscribe(
         0,
         0,
         L"Microsoft-Windows-Windows Firewall With Advanced Security/Firewall",
         L"*[System/EventID='2008']",
         0,
         qword_18009B230,
         NcsiIpsecEventMonitor::EventCallback,
         1u);
  wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int EvtCloseSafe(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
    v2,
    v1);
  if ( g_ncsiIpsecEventMonitor )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 0x10) != 0
      && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 5u )
    {
      WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 11, WPP_8cdf5a0688f636034b8a43fdd2ac3dae_Traceguids);
    }
  }
  else if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
         && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 0x10) != 0
         && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 2u )
  {
    v3 = GetLastError();
    WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 10, WPP_8cdf5a0688f636034b8a43fdd2ac3dae_Traceguids, v3);
  }
}

```

## disassembly

```asm
0x18005c2bc  sub     rsp, 88h
0x18005c2c3  mov     rax, cs:__security_cookie
0x18005c2ca  xor     rax, rsp
0x18005c2cd  mov     [rsp+88h+var_18], rax
0x18005c2d2  call    IsEvtOpenSessionPresent
0x18005c2d7  test    al, al
0x18005c2d9  jnz     short loc_18005C2EB
0x18005c2db  mov     ecx, 78h ; 'x'; dwErrCode
0x18005c2e0  call    cs:__imp_SetLastError
0x18005c2e6  jmp     loc_18005C52E
0x18005c2eb  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_NCSI_Fix_RemoteEvtSubscribe@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_NCSI_Fix_RemoteEvtSubscribe@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_NCSI_Fix_RemoteEvtSubscribe> `wil::Feature<__WilFeatureTraits_Feature_NCSI_Fix_RemoteEvtSubscribe>::GetImpl(void)'::`2'::impl
0x18005c2f2  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_NCSI_Fix_RemoteEvtSubscribe@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_NCSI_Fix_RemoteEvtSubscribe>::__private_IsEnabled(void)
0x18005c2f7  test    al, al
0x18005c2f9  jz      loc_18005C3EC
0x18005c2ff  mov     [rsp+88h+Flags], 1; Flags
0x18005c307  lea     rcx, ?EventCallback@NcsiIpsecEventMonitor@@CAKW4_EVT_SUBSCRIBE_NOTIFY_ACTION@@PEAX1@Z; NcsiIpsecEventMonitor::EventCallback(_EVT_SUBSCRIBE_NOTIFY_ACTION,void *,void *)
0x18005c30e  mov     [rsp+88h+Callback], rcx; Callback
0x18005c313  lea     r9, Query; "*[System/EventID='2008']"
0x18005c31a  lea     rcx, qword_18009B230
0x18005c321  xor     edx, edx; SignalEvent
0x18005c323  mov     [rsp+88h+Context], rcx; Context
0x18005c328  lea     r8, ChannelPath; "Microsoft-Windows-Windows Firewall With"...
0x18005c32f  xor     ecx, ecx; Session
0x18005c331  mov     [rsp+88h+Bookmark], 0; Bookmark
0x18005c33a  call    cs:__imp_EvtSubscribe
0x18005c340  mov     rdx, rax
0x18005c343  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AHPEAX@Z$1?EvtCloseSafe@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&EvtCloseSafe(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x18005c348  cmp     cs:?g_ncsiIpsecEventMonitor@@3VNcsiIpsecEventMonitor@@A, 0; NcsiIpsecEventMonitor g_ncsiIpsecEventMonitor
0x18005c350  jnz     short loc_18005C3A7
0x18005c352  mov     rcx, cs:WPP_GLOBAL_Control
0x18005c359  lea     rax, WPP_GLOBAL_Control
0x18005c360  cmp     rcx, rax
0x18005c363  jz      loc_18005C52E
0x18005c369  test    byte ptr [rcx+1Ch], 10h
0x18005c36d  jz      loc_18005C52E
0x18005c373  cmp     byte ptr [rcx+19h], 2
0x18005c377  jb      loc_18005C52E
0x18005c37d  call    cs:__imp_GetLastError
0x18005c383  mov     rcx, cs:WPP_GLOBAL_Control
0x18005c38a  lea     r8, WPP_8cdf5a0688f636034b8a43fdd2ac3dae_Traceguids
0x18005c391  mov     edx, 0Ah
0x18005c396  mov     r9d, eax
0x18005c399  mov     rcx, [rcx+10h]
0x18005c39d  call    WPP_SF_d
0x18005c3a2  jmp     loc_18005C52E
0x18005c3a7  mov     rcx, cs:WPP_GLOBAL_Control
0x18005c3ae  lea     rax, WPP_GLOBAL_Control
0x18005c3b5  cmp     rcx, rax
0x18005c3b8  jz      loc_18005C52E
0x18005c3be  test    byte ptr [rcx+1Ch], 10h
0x18005c3c2  jz      loc_18005C52E
0x18005c3c8  cmp     byte ptr [rcx+19h], 5
0x18005c3cc  jb      loc_18005C52E
0x18005c3d2  mov     rcx, [rcx+10h]
0x18005c3d6  lea     r8, WPP_8cdf5a0688f636034b8a43fdd2ac3dae_Traceguids
0x18005c3dd  mov     edx, 0Bh
0x18005c3e2  call    WPP_SF_
0x18005c3e7  jmp     loc_18005C52E
0x18005c3ec  xor     eax, eax
0x18005c3ee  lea     rdx, [rsp+88h+Login]; Login
0x18005c3f3  xorps   xmm0, xmm0
0x18005c3f6  mov     [rsp+88h+var_20], rax
0x18005c3fb  xor     r9d, r9d; Flags
0x18005c3fe  xor     r8d, r8d; Timeout
0x18005c401  movups  [rsp+88h+Login], xmm0
0x18005c406  lea     ecx, [rax+1]; LoginClass
0x18005c409  movups  [rsp+88h+var_30], xmm0
0x18005c40e  call    cs:__imp_EvtOpenSession
0x18005c414  mov     [rsp+88h+var_48], rax
0x18005c419  test    rax, rax
0x18005c41c  jnz     short loc_18005C456
0x18005c41e  mov     rcx, cs:WPP_GLOBAL_Control
0x18005c425  lea     rax, WPP_GLOBAL_Control
0x18005c42c  cmp     rcx, rax
0x18005c42f  jz      loc_18005C524
0x18005c435  test    byte ptr [rcx+1Ch], 10h
0x18005c439  jz      loc_18005C524
0x18005c43f  cmp     byte ptr [rcx+19h], 2
0x18005c443  jb      loc_18005C524
0x18005c449  call    cs:__imp_GetLastError
0x18005c44f  mov     edx, 0Ch
0x18005c454  jmp     short loc_18005C4D4
0x18005c456  mov     [rsp+88h+Flags], 1; Flags
0x18005c45e  lea     rcx, ?EventCallback@NcsiIpsecEventMonitor@@CAKW4_EVT_SUBSCRIBE_NOTIFY_ACTION@@PEAX1@Z; NcsiIpsecEventMonitor::EventCallback(_EVT_SUBSCRIBE_NOTIFY_ACTION,void *,void *)
0x18005c465  mov     [rsp+88h+Callback], rcx; Callback
0x18005c46a  lea     r9, Query; "*[System/EventID='2008']"
0x18005c471  lea     rcx, qword_18009B230
0x18005c478  xor     edx, edx; SignalEvent
0x18005c47a  mov     [rsp+88h+Context], rcx; Context
0x18005c47f  lea     r8, ChannelPath; "Microsoft-Windows-Windows Firewall With"...
0x18005c486  mov     rcx, rax; Session
0x18005c489  mov     [rsp+88h+Bookmark], 0; Bookmark
0x18005c492  call    cs:__imp_EvtSubscribe
0x18005c498  mov     rdx, rax
0x18005c49b  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AHPEAX@Z$1?EvtCloseSafe@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&EvtCloseSafe(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x18005c4a0  cmp     cs:?g_ncsiIpsecEventMonitor@@3VNcsiIpsecEventMonitor@@A, 0; NcsiIpsecEventMonitor g_ncsiIpsecEventMonitor
0x18005c4a8  jnz     short loc_18005C4F0
0x18005c4aa  mov     rcx, cs:WPP_GLOBAL_Control
0x18005c4b1  lea     rax, WPP_GLOBAL_Control
0x18005c4b8  cmp     rcx, rax
0x18005c4bb  jz      short loc_18005C524
0x18005c4bd  test    byte ptr [rcx+1Ch], 10h
0x18005c4c1  jz      short loc_18005C524
0x18005c4c3  cmp     byte ptr [rcx+19h], 2
0x18005c4c7  jb      short loc_18005C524
0x18005c4c9  call    cs:__imp_GetLastError
0x18005c4cf  mov     edx, 0Dh
0x18005c4d4  mov     rcx, cs:WPP_GLOBAL_Control
0x18005c4db  lea     r8, WPP_8cdf5a0688f636034b8a43fdd2ac3dae_Traceguids
0x18005c4e2  mov     r9d, eax
0x18005c4e5  mov     rcx, [rcx+10h]
0x18005c4e9  call    WPP_SF_d
0x18005c4ee  jmp     short loc_18005C524
0x18005c4f0  mov     rcx, cs:WPP_GLOBAL_Control
0x18005c4f7  lea     rax, WPP_GLOBAL_Control
0x18005c4fe  cmp     rcx, rax
0x18005c501  jz      short loc_18005C524
0x18005c503  test    byte ptr [rcx+1Ch], 10h
0x18005c507  jz      short loc_18005C524
0x18005c509  cmp     byte ptr [rcx+19h], 5
0x18005c50d  jb      short loc_18005C524
0x18005c50f  mov     rcx, [rcx+10h]
0x18005c513  lea     r8, WPP_8cdf5a0688f636034b8a43fdd2ac3dae_Traceguids
0x18005c51a  mov     edx, 0Eh
0x18005c51f  call    WPP_SF_
0x18005c524  lea     rcx, [rsp+88h+var_48]
0x18005c529  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AHPEAX@Z$1?EvtCloseSafe@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&EvtCloseSafe(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&EvtCloseSafe(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18005c52e  mov     rcx, [rsp+88h+var_18]
0x18005c533  xor     rcx, rsp; StackCookie
0x18005c536  call    __security_check_cookie
0x18005c53b  add     rsp, 88h
0x18005c542  retn
```
