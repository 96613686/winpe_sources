# OnConfigChange

- ea: `0x1800530ac`
- end: `0x18005334e`
- name: `OnConfigChange`
- size: `674`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18002d2f0`

## callees

- `0x180004f60`
- `0x180008210`
- `0x180024250`
- `0x18002dcc0`
- `0x1800530ac`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x1800530fe`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x18005314e`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x180053196`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x1800531e4`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x18005322f`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x18005327a`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x1800532c5`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x18005330c`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x1800530fe`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x18005314e`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x180053196`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x1800531e4`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x18005322f`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x18005327a`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x1800532c5`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x18005330c`

## string_xrefs

- `0x1800530d7`: `Process6to4ConfigurationChange`
- `0x180053117`: `Process6to4ConfigurationChange`
- `0x1800531c1`: `TeredoConfigurationChangeNotification`
- `0x1800531fd`: `TeredoConfigurationChangeNotification`
- `0x1800532a5`: `Dns64ConfigurationChangeNotification`
- `0x1800532de`: `Dns64ConfigurationChangeNotification`
- `0x1800532f0`: `DaSiteMgrGpConfigurationChangeNotification`
- `0x180053322`: `DaSiteMgrGpConfigurationChangeNotification`
- `0x18005320f`: `IptlsConfigurationChangeNotification`
- `0x180053248`: `IptlsConfigurationChangeNotification`
- `0x1800530b6`: `Entered: Common: OnConfigChange`
- `0x1800530c7`: `onecoreuap\net\netio\iphlpsvc\service\common.c`
- `0x18005312e`: `PortConfigurationChangeNotification`
- `0x180053167`: `PortConfigurationChangeNotification`
- `0x180053176`: `IsatapConfigurationChangeNotification`
- `0x1800531af`: `IsatapConfigurationChangeNotification`
- `0x18005325a`: `SplTunMgrConfigurationChangeNotification`
- `0x180053293`: `SplTunMgrConfigurationChangeNotification`
- `0x180053331`: `Leaving: Common: OnConfigChange`

## pseudocode

```c
__int64 OnConfigChange()
{
  __int64 result; // rax
  __int64 v1; // r8
  const char *v2; // rcx

  EventWriteEnterEx(0x20000, L"Entered: Common: OnConfigChange");
  result = ReferenceServiceEx(
             "Process6to4ConfigurationChange",
             L"onecoreuap\\net\\netio\\iphlpsvc\\service\\common.c",
             1187);
  if ( (_DWORD)result )
  {
    if ( !TrySubmitThreadpoolCallback((PTP_SIMPLE_CALLBACK)Process6to4ConfigurationChange, 0, &CallbackEnvironment) )
    {
      v1 = 1191;
      v2 = "Process6to4ConfigurationChange";
      return DereferenceServiceEx(v2, L"onecoreuap\\net\\netio\\iphlpsvc\\service\\common.c", v1);
    }
    result = ReferenceServiceEx(
               "PortConfigurationChangeNotification",
               L"onecoreuap\\net\\netio\\iphlpsvc\\service\\common.c",
               1195);
    if ( (_DWORD)result )
    {
      if ( !TrySubmitThreadpoolCallback(
              (PTP_SIMPLE_CALLBACK)PortConfigurationChangeNotification,
              0,
              &CallbackEnvironment) )
      {
        v1 = 1199;
        v2 = "PortConfigurationChangeNotification";
        return DereferenceServiceEx(v2, L"onecoreuap\\net\\netio\\iphlpsvc\\service\\common.c", v1);
      }
      result = ReferenceServiceEx(
                 "IsatapConfigurationChangeNotification",
                 L"onecoreuap\\net\\netio\\iphlpsvc\\service\\common.c",
                 1203);
      if ( (_DWORD)result )
      {
        if ( !TrySubmitThreadpoolCallback(
                (PTP_SIMPLE_CALLBACK)IsatapConfigurationChangeNotification,
                0,
                &CallbackEnvironment) )
        {
          v1 = 1207;
          v2 = "IsatapConfigurationChangeNotification";
          return DereferenceServiceEx(v2, L"onecoreuap\\net\\netio\\iphlpsvc\\service\\common.c", v1);
        }
        result = ReferenceServiceEx(
                   "TeredoConfigurationChangeNotification",
                   L"onecoreuap\\net\\netio\\iphlpsvc\\service\\common.c",
                   1211);
        if ( (_DWORD)result )
        {
          if ( !TrySubmitThreadpoolCallback(
                  (PTP_SIMPLE_CALLBACK)TeredoConfigurationChangeNotification,
                  (PVOID)5,
                  &CallbackEnvironment) )
          {
            v1 = 1218;
            v2 = "TeredoConfigurationChangeNotification";
            return DereferenceServiceEx(v2, L"onecoreuap\\net\\netio\\iphlpsvc\\service\\common.c", v1);
          }
          result = ReferenceServiceEx(
                     "IptlsConfigurationChangeNotification",
                     L"onecoreuap\\net\\netio\\iphlpsvc\\service\\common.c",
                     1222);
          if ( (_DWORD)result )
          {
            if ( !TrySubmitThreadpoolCallback(
                    (PTP_SIMPLE_CALLBACK)IpTlsConfigurationChangeNotification,
                    0,
                    &CallbackEnvironment) )
            {
              v1 = 1226;
              v2 = "IptlsConfigurationChangeNotification";
              return DereferenceServiceEx(v2, L"onecoreuap\\net\\netio\\iphlpsvc\\service\\common.c", v1);
            }
            result = ReferenceServiceEx(
                       "SplTunMgrConfigurationChangeNotification",
                       L"onecoreuap\\net\\netio\\iphlpsvc\\service\\common.c",
                       1230);
            if ( (_DWORD)result )
            {
              if ( !TrySubmitThreadpoolCallback(SplTunMgrConfigurationChangeNotification, 0, &CallbackEnvironment) )
              {
                v1 = 1234;
                v2 = "SplTunMgrConfigurationChangeNotification";
                return DereferenceServiceEx(v2, L"onecoreuap\\net\\netio\\iphlpsvc\\service\\common.c", v1);
              }
              result = ReferenceServiceEx(
                         "Dns64ConfigurationChangeNotification",
                         L"onecoreuap\\net\\netio\\iphlpsvc\\service\\common.c",
                         1238);
              if ( (_DWORD)result )
              {
                if ( !TrySubmitThreadpoolCallback(
                        (PTP_SIMPLE_CALLBACK)Dns64ConfigurationChangeNotification,
                        0,
                        &CallbackEnvironment) )
                {
                  v1 = 1242;
                  v2 = "Dns64ConfigurationChangeNotification";
                  return DereferenceServiceEx(v2, L"onecoreuap\\net\\netio\\iphlpsvc\\service\\common.c", v1);
                }
                result = ReferenceServiceEx(
                           "DaSiteMgrGpConfigurationChangeNotification",
                           L"onecoreuap\\net\\netio\\iphlpsvc\\service\\common.c",
                           1246);
                if ( (_DWORD)result )
                {
                  if ( !TrySubmitThreadpoolCallback(DaSiteMgrGpConfigurationChangeNotification, 0, &CallbackEnvironment) )
                  {
                    v1 = 1250;
                    v2 = "DaSiteMgrGpConfigurationChangeNotification";
                    return DereferenceServiceEx(v2, L"onecoreuap\\net\\netio\\iphlpsvc\\service\\common.c", v1);
                  }
                  return EventWriteLeaveEx(0x20000, L"Leaving: Common: OnConfigChange");
                }
              }
            }
          }
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800530ac  mov     [rsp+arg_0], rbx
0x1800530b1  push    rdi
0x1800530b2  sub     rsp, 20h
0x1800530b6  lea     rdx, aEnteredCommonO_0; "Entered: Common: OnConfigChange"
0x1800530bd  mov     ecx, 20000h
0x1800530c2  call    EventWriteEnterEx
0x1800530c7  lea     rbx, aOnecoreuapNetN_18; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x1800530ce  mov     r8d, 4A3h
0x1800530d4  mov     rdx, rbx
0x1800530d7  lea     rcx, aProcess6to4con; "Process6to4ConfigurationChange"
0x1800530de  call    ReferenceServiceEx
0x1800530e3  test    eax, eax
0x1800530e5  jz      loc_180053342
0x1800530eb  lea     rdi, CallbackEnvironment
0x1800530f2  xor     edx, edx; pv
0x1800530f4  mov     r8, rdi; pcbe
0x1800530f7  lea     rcx, Process6to4ConfigurationChange; pfns
0x1800530fe  call    cs:__imp_TrySubmitThreadpoolCallback
0x180053105  nop     dword ptr [rax+rax+00h]
0x18005310a  mov     rdx, rbx
0x18005310d  test    eax, eax
0x18005310f  jnz     short loc_180053128
0x180053111  mov     r8d, 4A7h
0x180053117  lea     rcx, aProcess6to4con; "Process6to4ConfigurationChange"
0x18005311e  call    DereferenceServiceEx
0x180053123  jmp     loc_180053342
0x180053128  mov     r8d, 4ABh
0x18005312e  lea     rcx, aPortconfigurat; "PortConfigurationChangeNotification"
0x180053135  call    ReferenceServiceEx
0x18005313a  test    eax, eax
0x18005313c  jz      loc_180053342
0x180053142  mov     r8, rdi; pcbe
0x180053145  lea     rcx, PortConfigurationChangeNotification; pfns
0x18005314c  xor     edx, edx; pv
0x18005314e  call    cs:__imp_TrySubmitThreadpoolCallback
0x180053155  nop     dword ptr [rax+rax+00h]
0x18005315a  mov     rdx, rbx
0x18005315d  test    eax, eax
0x18005315f  jnz     short loc_180053170
0x180053161  mov     r8d, 4AFh
0x180053167  lea     rcx, aPortconfigurat; "PortConfigurationChangeNotification"
0x18005316e  jmp     short loc_18005311E
0x180053170  mov     r8d, 4B3h
0x180053176  lea     rcx, aIsatapconfigur; "IsatapConfigurationChangeNotification"
0x18005317d  call    ReferenceServiceEx
0x180053182  test    eax, eax
0x180053184  jz      loc_180053342
0x18005318a  mov     r8, rdi; pcbe
0x18005318d  lea     rcx, IsatapConfigurationChangeNotification; pfns
0x180053194  xor     edx, edx; pv
0x180053196  call    cs:__imp_TrySubmitThreadpoolCallback
0x18005319d  nop     dword ptr [rax+rax+00h]
0x1800531a2  mov     rdx, rbx
0x1800531a5  test    eax, eax
0x1800531a7  jnz     short loc_1800531BB
0x1800531a9  mov     r8d, 4B7h
0x1800531af  lea     rcx, aIsatapconfigur; "IsatapConfigurationChangeNotification"
0x1800531b6  jmp     loc_18005311E
0x1800531bb  mov     r8d, 4BBh
0x1800531c1  lea     rcx, aTeredoconfigur; "TeredoConfigurationChangeNotification"
0x1800531c8  call    ReferenceServiceEx
0x1800531cd  test    eax, eax
0x1800531cf  jz      loc_180053342
0x1800531d5  mov     r8, rdi; pcbe
0x1800531d8  lea     rcx, TeredoConfigurationChangeNotification; pfns
0x1800531df  mov     edx, 5; pv
0x1800531e4  call    cs:__imp_TrySubmitThreadpoolCallback
0x1800531eb  nop     dword ptr [rax+rax+00h]
0x1800531f0  mov     rdx, rbx
0x1800531f3  test    eax, eax
0x1800531f5  jnz     short loc_180053209
0x1800531f7  mov     r8d, 4C2h
0x1800531fd  lea     rcx, aTeredoconfigur; "TeredoConfigurationChangeNotification"
0x180053204  jmp     loc_18005311E
0x180053209  mov     r8d, 4C6h
0x18005320f  lea     rcx, aIptlsconfigura; "IptlsConfigurationChangeNotification"
0x180053216  call    ReferenceServiceEx
0x18005321b  test    eax, eax
0x18005321d  jz      loc_180053342
0x180053223  mov     r8, rdi; pcbe
0x180053226  lea     rcx, IpTlsConfigurationChangeNotification; pfns
0x18005322d  xor     edx, edx; pv
0x18005322f  call    cs:__imp_TrySubmitThreadpoolCallback
0x180053236  nop     dword ptr [rax+rax+00h]
0x18005323b  mov     rdx, rbx
0x18005323e  test    eax, eax
0x180053240  jnz     short loc_180053254
0x180053242  mov     r8d, 4CAh
0x180053248  lea     rcx, aIptlsconfigura; "IptlsConfigurationChangeNotification"
0x18005324f  jmp     loc_18005311E
0x180053254  mov     r8d, 4CEh
0x18005325a  lea     rcx, aSpltunmgrconfi_0; "SplTunMgrConfigurationChangeNotificatio"...
0x180053261  call    ReferenceServiceEx
0x180053266  test    eax, eax
0x180053268  jz      loc_180053342
0x18005326e  mov     r8, rdi; pcbe
0x180053271  lea     rcx, SplTunMgrConfigurationChangeNotification; pfns
0x180053278  xor     edx, edx; pv
0x18005327a  call    cs:__imp_TrySubmitThreadpoolCallback
0x180053281  nop     dword ptr [rax+rax+00h]
0x180053286  mov     rdx, rbx
0x180053289  test    eax, eax
0x18005328b  jnz     short loc_18005329F
0x18005328d  mov     r8d, 4D2h
0x180053293  lea     rcx, aSpltunmgrconfi_0; "SplTunMgrConfigurationChangeNotificatio"...
0x18005329a  jmp     loc_18005311E
0x18005329f  mov     r8d, 4D6h
0x1800532a5  lea     rcx, aDns64configura; "Dns64ConfigurationChangeNotification"
0x1800532ac  call    ReferenceServiceEx
0x1800532b1  test    eax, eax
0x1800532b3  jz      loc_180053342
0x1800532b9  mov     r8, rdi; pcbe
0x1800532bc  lea     rcx, Dns64ConfigurationChangeNotification; pfns
0x1800532c3  xor     edx, edx; pv
0x1800532c5  call    cs:__imp_TrySubmitThreadpoolCallback
0x1800532cc  nop     dword ptr [rax+rax+00h]
0x1800532d1  mov     rdx, rbx
0x1800532d4  test    eax, eax
0x1800532d6  jnz     short loc_1800532EA
0x1800532d8  mov     r8d, 4DAh
0x1800532de  lea     rcx, aDns64configura; "Dns64ConfigurationChangeNotification"
0x1800532e5  jmp     loc_18005311E
0x1800532ea  mov     r8d, 4DEh
0x1800532f0  lea     rcx, aDasitemgrgpcon; "DaSiteMgrGpConfigurationChangeNotificat"...
0x1800532f7  call    ReferenceServiceEx
0x1800532fc  test    eax, eax
0x1800532fe  jz      short loc_180053342
0x180053300  mov     r8, rdi; pcbe
0x180053303  lea     rcx, DaSiteMgrGpConfigurationChangeNotification; pfns
0x18005330a  xor     edx, edx; pv
0x18005330c  call    cs:__imp_TrySubmitThreadpoolCallback
0x180053313  nop     dword ptr [rax+rax+00h]
0x180053318  test    eax, eax
0x18005331a  jnz     short loc_180053331
0x18005331c  mov     r8d, 4E2h
0x180053322  lea     rcx, aDasitemgrgpcon; "DaSiteMgrGpConfigurationChangeNotificat"...
0x180053329  mov     rdx, rbx
0x18005332c  jmp     loc_18005311E
0x180053331  lea     rdx, aLeavingCommonO_0; "Leaving: Common: OnConfigChange"
0x180053338  mov     ecx, 20000h
0x18005333d  call    EventWriteLeaveEx
0x180053342  mov     rbx, [rsp+28h+arg_0]
0x180053347  add     rsp, 20h
0x18005334b  pop     rdi
0x18005334c  retn
```
