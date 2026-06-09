# IpTlsConfigurationChangeNotification

- ea: `0x180043460`
- end: `0x180043649`
- name: `IpTlsConfigurationChangeNotification`
- size: `489`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context)`
- caller_count: `2`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180061438`
- `0x180061498`

## callees

- `0x1800028d4`
- `0x180003ce4`
- `0x180004f50`
- `0x18000a6f4`
- `0x18000d7b0`
- `0x180013490`
- `0x180013570`
- `0x1800159c4`
- `0x180043460`
- `0x18004b630`
- `0x1800601c4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800435be`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800435e7`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800435be`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800435e7`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180043625`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180043625`

## string_xrefs

- `0x180043492`: `onecoreuap\net\netio\iphlpsvc\service\iptls.c`
- `0x1800435f9`: `onecoreuap\net\netio\iphlpsvc\service\iptls.c`
- `0x180043499`: `IptlsConfigurationChangeNotification`
- `0x180043600`: `IptlsConfigurationChangeNotification`
- `0x180043503`: `IpTlsConfigurationChangeNotification:Starting always on interfaces`
- `0x180043556`: `IpTlsConfigurationChangeNotification:Adding outside interfaces`
- `0x1800435a3`: `IpTlsConfigurationChangeNotification:Starting corp connectivity timer`

## pseudocode

```c
void __fastcall IpTlsConfigurationChangeNotification(PTP_CALLBACK_INSTANCE Instance, PVOID Context)
{
  int v2; // ebx
  __int64 v3; // r8
  char v4; // si
  char v5; // bl
  unsigned __int8 v6; // di
  _BYTE v7[16]; // [rsp+30h] [rbp-48h] BYREF

  v2 = (int)Context;
  if ( (unsigned __int8)RoReferenceEx(&g_IpTlsInterfaceListReferenceObject) )
  {
    v4 = 0;
    if ( (Microsoft_Windows_Iphlpsvc_TraceEnableBits & 0x800) != 0 )
      McGenEventWrite_EventWriteTransfer(
        MS_IPHLPSVC_ETW_PROVIDER_ID_Context,
        EVENT_IPHLPSVC_ETW_IPHTTPS_CONFIG_CHANGE,
        v3,
        1,
        v7);
    IpTlsAcquireLock(g_IpTlsConfigChangeLock);
    if ( v2 )
    {
      g_IpTlsCorpConnectivityAdjusted = 0;
      g_IpTlsCorpConnectivityTimeout = 100000000;
    }
    IpTlsRemoveDeletedInterfaces();
    EventWrite0(0x10000000, L"IpTlsConfigurationChangeNotification:Starting always on interfaces");
    IpTlsAddEligibleInterfaces(2, 2);
    IpTlsAddEligibleInterfaces(2, 1);
    IpTlsAddEligibleInterfaces(2, 0);
    IpTlsDeleteConflictingInterfaces(2);
    IpTlsDeleteConflictingInterfaces(1);
    if ( g_IpTlsIsOutside )
    {
      if ( !g_IpTlsConfiguredForOutside )
      {
        EventWrite0(0x10000000, L"IpTlsConfigurationChangeNotification:Adding outside interfaces");
        v5 = IpTlsAddEligibleInterfaces(1, 2);
        v6 = v5 | IpTlsAddEligibleInterfaces(1, 1);
        if ( v6 | (unsigned __int8)IpTlsAddEligibleInterfaces(1, 0) )
          g_IpTlsConfiguredForOutside = 1;
      }
    }
    if ( !g_IpTlsConfiguredForCorpConnectivity )
    {
      EventWrite0(0x10000000, L"IpTlsConfigurationChangeNotification:Starting corp connectivity timer");
      v4 = 1;
    }
    ReleaseMutex(g_IpTlsConfigChangeLock);
    if ( v4 == 1 )
    {
      IpTlsAcquireLock(g_IpTlsNLMNotificationLock);
      IpTlsRestartCorpConnectivityTimer();
      ReleaseMutex(g_IpTlsNLMNotificationLock);
    }
    DereferenceServiceEx(
      "IptlsConfigurationChangeNotification",
      L"onecoreuap\\net\\netio\\iphlpsvc\\service\\iptls.c",
      4679);
    if ( _InterlockedExchangeAdd(&g_IpTlsInterfaceListReferenceObject, 0xFFFFFFFE) == 3 )
      SetEvent(g_IpTlsInterfaceListEmptyEvent);
  }
  else
  {
    DereferenceServiceEx(
      "IptlsConfigurationChangeNotification",
      L"onecoreuap\\net\\netio\\iphlpsvc\\service\\iptls.c",
      4618);
  }
}

```

## disassembly

```asm
0x180043460  push    rbx
0x180043462  push    rsi
0x180043463  push    rdi
0x180043464  push    r14
0x180043466  sub     rsp, 58h
0x18004346a  mov     rax, cs:__security_cookie
0x180043471  xor     rax, rsp
0x180043474  mov     [rsp+78h+var_38], rax
0x180043479  lea     rcx, g_IpTlsInterfaceListReferenceObject
0x180043480  mov     rbx, rdx
0x180043483  call    RoReferenceEx
0x180043488  test    al, al
0x18004348a  jnz     short loc_1800434AA
0x18004348c  mov     r8d, 120Ah
0x180043492  lea     rdx, aOnecoreuapNetN_21; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x180043499  lea     rcx, aIptlsconfigura; "IptlsConfigurationChangeNotification"
0x1800434a0  call    DereferenceServiceEx
0x1800434a5  jmp     loc_180043631
0x1800434aa  xor     sil, sil
0x1800434ad  mov     r14d, 1
0x1800434b3  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+1, 8
0x1800434ba  jz      short loc_1800434DC
0x1800434bc  lea     rax, [rsp+78h+var_48]
0x1800434c1  mov     r9d, r14d
0x1800434c4  lea     rdx, EVENT_IPHLPSVC_ETW_IPHTTPS_CONFIG_CHANGE
0x1800434cb  mov     [rsp+78h+var_58], rax
0x1800434d0  lea     rcx, MS_IPHLPSVC_ETW_PROVIDER_ID_Context
0x1800434d7  call    McGenEventWrite_EventWriteTransfer
0x1800434dc  mov     rcx, cs:g_IpTlsConfigChangeLock
0x1800434e3  call    IpTlsAcquireLock
0x1800434e8  test    ebx, ebx
0x1800434ea  jz      short loc_1800434FE
0x1800434ec  mov     cs:g_IpTlsCorpConnectivityAdjusted, sil
0x1800434f3  mov     cs:g_IpTlsCorpConnectivityTimeout, 5F5E100h
0x1800434fe  call    IpTlsRemoveDeletedInterfaces
0x180043503  lea     rdx, aIptlsconfigura_0; "IpTlsConfigurationChangeNotification:St"...
0x18004350a  mov     ecx, 10000000h
0x18004350f  call    EventWrite0
0x180043514  mov     ebx, 2
0x180043519  mov     edx, ebx
0x18004351b  mov     ecx, ebx
0x18004351d  call    IpTlsAddEligibleInterfaces
0x180043522  mov     edx, r14d
0x180043525  mov     ecx, ebx
0x180043527  call    IpTlsAddEligibleInterfaces
0x18004352c  xor     edx, edx
0x18004352e  mov     ecx, ebx
0x180043530  call    IpTlsAddEligibleInterfaces
0x180043535  mov     ecx, ebx
0x180043537  call    IpTlsDeleteConflictingInterfaces
0x18004353c  mov     ecx, r14d
0x18004353f  call    IpTlsDeleteConflictingInterfaces
0x180043544  cmp     cs:g_IpTlsIsOutside, sil
0x18004354b  jz      short loc_18004359A
0x18004354d  cmp     cs:g_IpTlsConfiguredForOutside, sil
0x180043554  jnz     short loc_18004359A
0x180043556  lea     rdx, aIptlsconfigura_2; "IpTlsConfigurationChangeNotification:Ad"...
0x18004355d  mov     ecx, 10000000h
0x180043562  call    EventWrite0
0x180043567  mov     edx, ebx
0x180043569  mov     ecx, r14d
0x18004356c  call    IpTlsAddEligibleInterfaces
0x180043571  mov     edx, r14d
0x180043574  mov     ecx, r14d
0x180043577  mov     bl, al
0x180043579  call    IpTlsAddEligibleInterfaces
0x18004357e  mov     dil, al
0x180043581  xor     edx, edx
0x180043583  mov     ecx, r14d
0x180043586  or      dil, bl
0x180043589  call    IpTlsAddEligibleInterfaces
0x18004358e  or      al, dil
0x180043591  jz      short loc_18004359A
0x180043593  mov     cs:g_IpTlsConfiguredForOutside, r14b
0x18004359a  cmp     cs:g_IpTlsConfiguredForCorpConnectivity, sil
0x1800435a1  jnz     short loc_1800435B7
0x1800435a3  lea     rdx, aIptlsconfigura_1; "IpTlsConfigurationChangeNotification:St"...
0x1800435aa  mov     ecx, 10000000h
0x1800435af  call    EventWrite0
0x1800435b4  mov     sil, r14b
0x1800435b7  mov     rcx, cs:g_IpTlsConfigChangeLock; hMutex
0x1800435be  call    cs:__imp_ReleaseMutex
0x1800435c5  nop     dword ptr [rax+rax+00h]
0x1800435ca  cmp     sil, r14b
0x1800435cd  jnz     short loc_1800435F3
0x1800435cf  mov     rcx, cs:g_IpTlsNLMNotificationLock
0x1800435d6  call    IpTlsAcquireLock
0x1800435db  call    IpTlsRestartCorpConnectivityTimer
0x1800435e0  mov     rcx, cs:g_IpTlsNLMNotificationLock; hMutex
0x1800435e7  call    cs:__imp_ReleaseMutex
0x1800435ee  nop     dword ptr [rax+rax+00h]
0x1800435f3  mov     r8d, 1247h
0x1800435f9  lea     rdx, aOnecoreuapNetN_21; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x180043600  lea     rcx, aIptlsconfigura; "IptlsConfigurationChangeNotification"
0x180043607  call    DereferenceServiceEx
0x18004360c  mov     eax, 0FFFFFFFEh
0x180043611  lock xadd cs:g_IpTlsInterfaceListReferenceObject, eax
0x180043619  cmp     eax, 3
0x18004361c  jnz     short loc_180043631
0x18004361e  mov     rcx, cs:g_IpTlsInterfaceListEmptyEvent; hEvent
0x180043625  call    cs:__imp_SetEvent
0x18004362c  nop     dword ptr [rax+rax+00h]
0x180043631  mov     rcx, [rsp+78h+var_38]
0x180043636  xor     rcx, rsp; StackCookie
0x180043639  call    __security_check_cookie
0x18004363e  add     rsp, 58h
0x180043642  pop     r14
0x180043644  pop     rdi
0x180043645  pop     rsi
0x180043646  pop     rbx
0x180043647  retn
```
