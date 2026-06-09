# IpTlsConfigurationChangeNotification

- ea: `0x180043420`
- end: `0x180043609`
- name: `IpTlsConfigurationChangeNotification`
- size: `489`
- prototype: `void __fastcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context)`
- caller_count: `2`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180061458`
- `0x1800614b8`

## callees

- `0x1800028e4`
- `0x180003cf4`
- `0x180004f60`
- `0x18000a704`
- `0x18000d7c0`
- `0x1800134a0`
- `0x180013580`
- `0x1800159d4`
- `0x180043420`
- `0x18004b5f0`
- `0x1800601e4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18004357e`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800435a7`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18004357e`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800435a7`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800435e5`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800435e5`

## string_xrefs

- `0x180043452`: `onecoreuap\net\netio\iphlpsvc\service\iptls.c`
- `0x1800435b9`: `onecoreuap\net\netio\iphlpsvc\service\iptls.c`
- `0x180043459`: `IptlsConfigurationChangeNotification`
- `0x1800435c0`: `IptlsConfigurationChangeNotification`
- `0x1800434c3`: `IpTlsConfigurationChangeNotification:Starting always on interfaces`
- `0x180043516`: `IpTlsConfigurationChangeNotification:Adding outside interfaces`
- `0x180043563`: `IpTlsConfigurationChangeNotification:Starting corp connectivity timer`

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
0x180043420  push    rbx
0x180043422  push    rsi
0x180043423  push    rdi
0x180043424  push    r14
0x180043426  sub     rsp, 58h
0x18004342a  mov     rax, cs:__security_cookie
0x180043431  xor     rax, rsp
0x180043434  mov     [rsp+78h+var_38], rax
0x180043439  lea     rcx, g_IpTlsInterfaceListReferenceObject
0x180043440  mov     rbx, rdx
0x180043443  call    RoReferenceEx
0x180043448  test    al, al
0x18004344a  jnz     short loc_18004346A
0x18004344c  mov     r8d, 120Ah
0x180043452  lea     rdx, aOnecoreuapNetN_21; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x180043459  lea     rcx, aIptlsconfigura; "IptlsConfigurationChangeNotification"
0x180043460  call    DereferenceServiceEx
0x180043465  jmp     loc_1800435F1
0x18004346a  xor     sil, sil
0x18004346d  mov     r14d, 1
0x180043473  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+1, 8
0x18004347a  jz      short loc_18004349C
0x18004347c  lea     rax, [rsp+78h+var_48]
0x180043481  mov     r9d, r14d
0x180043484  lea     rdx, EVENT_IPHLPSVC_ETW_IPHTTPS_CONFIG_CHANGE
0x18004348b  mov     [rsp+78h+var_58], rax
0x180043490  lea     rcx, MS_IPHLPSVC_ETW_PROVIDER_ID_Context
0x180043497  call    McGenEventWrite_EventWriteTransfer
0x18004349c  mov     rcx, cs:g_IpTlsConfigChangeLock
0x1800434a3  call    IpTlsAcquireLock
0x1800434a8  test    ebx, ebx
0x1800434aa  jz      short loc_1800434BE
0x1800434ac  mov     cs:g_IpTlsCorpConnectivityAdjusted, sil
0x1800434b3  mov     cs:g_IpTlsCorpConnectivityTimeout, 5F5E100h
0x1800434be  call    IpTlsRemoveDeletedInterfaces
0x1800434c3  lea     rdx, aIptlsconfigura_0; "IpTlsConfigurationChangeNotification:St"...
0x1800434ca  mov     ecx, 10000000h
0x1800434cf  call    EventWrite0
0x1800434d4  mov     ebx, 2
0x1800434d9  mov     edx, ebx
0x1800434db  mov     ecx, ebx
0x1800434dd  call    IpTlsAddEligibleInterfaces
0x1800434e2  mov     edx, r14d
0x1800434e5  mov     ecx, ebx
0x1800434e7  call    IpTlsAddEligibleInterfaces
0x1800434ec  xor     edx, edx
0x1800434ee  mov     ecx, ebx
0x1800434f0  call    IpTlsAddEligibleInterfaces
0x1800434f5  mov     ecx, ebx
0x1800434f7  call    IpTlsDeleteConflictingInterfaces
0x1800434fc  mov     ecx, r14d
0x1800434ff  call    IpTlsDeleteConflictingInterfaces
0x180043504  cmp     cs:g_IpTlsIsOutside, sil
0x18004350b  jz      short loc_18004355A
0x18004350d  cmp     cs:g_IpTlsConfiguredForOutside, sil
0x180043514  jnz     short loc_18004355A
0x180043516  lea     rdx, aIptlsconfigura_2; "IpTlsConfigurationChangeNotification:Ad"...
0x18004351d  mov     ecx, 10000000h
0x180043522  call    EventWrite0
0x180043527  mov     edx, ebx
0x180043529  mov     ecx, r14d
0x18004352c  call    IpTlsAddEligibleInterfaces
0x180043531  mov     edx, r14d
0x180043534  mov     ecx, r14d
0x180043537  mov     bl, al
0x180043539  call    IpTlsAddEligibleInterfaces
0x18004353e  mov     dil, al
0x180043541  xor     edx, edx
0x180043543  mov     ecx, r14d
0x180043546  or      dil, bl
0x180043549  call    IpTlsAddEligibleInterfaces
0x18004354e  or      al, dil
0x180043551  jz      short loc_18004355A
0x180043553  mov     cs:g_IpTlsConfiguredForOutside, r14b
0x18004355a  cmp     cs:g_IpTlsConfiguredForCorpConnectivity, sil
0x180043561  jnz     short loc_180043577
0x180043563  lea     rdx, aIptlsconfigura_1; "IpTlsConfigurationChangeNotification:St"...
0x18004356a  mov     ecx, 10000000h
0x18004356f  call    EventWrite0
0x180043574  mov     sil, r14b
0x180043577  mov     rcx, cs:g_IpTlsConfigChangeLock; hMutex
0x18004357e  call    cs:__imp_ReleaseMutex
0x180043585  nop     dword ptr [rax+rax+00h]
0x18004358a  cmp     sil, r14b
0x18004358d  jnz     short loc_1800435B3
0x18004358f  mov     rcx, cs:g_IpTlsNLMNotificationLock
0x180043596  call    IpTlsAcquireLock
0x18004359b  call    IpTlsRestartCorpConnectivityTimer
0x1800435a0  mov     rcx, cs:g_IpTlsNLMNotificationLock; hMutex
0x1800435a7  call    cs:__imp_ReleaseMutex
0x1800435ae  nop     dword ptr [rax+rax+00h]
0x1800435b3  mov     r8d, 1247h
0x1800435b9  lea     rdx, aOnecoreuapNetN_21; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x1800435c0  lea     rcx, aIptlsconfigura; "IptlsConfigurationChangeNotification"
0x1800435c7  call    DereferenceServiceEx
0x1800435cc  mov     eax, 0FFFFFFFEh
0x1800435d1  lock xadd cs:g_IpTlsInterfaceListReferenceObject, eax
0x1800435d9  cmp     eax, 3
0x1800435dc  jnz     short loc_1800435F1
0x1800435de  mov     rcx, cs:g_IpTlsInterfaceListEmptyEvent; hEvent
0x1800435e5  call    cs:__imp_SetEvent
0x1800435ec  nop     dword ptr [rax+rax+00h]
0x1800435f1  mov     rcx, [rsp+78h+var_38]
0x1800435f6  xor     rcx, rsp; StackCookie
0x1800435f9  call    __security_check_cookie
0x1800435fe  add     rsp, 58h
0x180043602  pop     r14
0x180043604  pop     rdi
0x180043605  pop     rsi
0x180043606  pop     rbx
0x180043607  retn
```
