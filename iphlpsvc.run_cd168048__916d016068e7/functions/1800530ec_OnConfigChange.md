# OnConfigChange

- ea: `0x1800530ec`
- end: `0x18005338e`
- name: `OnConfigChange`
- size: `674`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18002d2e0`

## callees

- `0x180004f50`
- `0x180008200`
- `0x180024240`
- `0x18002dcb0`
- `0x1800530ec`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x18005313e`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x18005318e`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x1800531d6`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x180053224`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x18005326f`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x1800532ba`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x180053305`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x18005334c`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x18005313e`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x18005318e`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x1800531d6`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x180053224`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x18005326f`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x1800532ba`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x180053305`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x18005334c`

## string_xrefs

- `0x180053117`: `Process6to4ConfigurationChange`
- `0x180053157`: `Process6to4ConfigurationChange`
- `0x180053201`: `TeredoConfigurationChangeNotification`
- `0x18005323d`: `TeredoConfigurationChangeNotification`
- `0x1800532e5`: `Dns64ConfigurationChangeNotification`
- `0x18005331e`: `Dns64ConfigurationChangeNotification`
- `0x180053330`: `DaSiteMgrGpConfigurationChangeNotification`
- `0x180053362`: `DaSiteMgrGpConfigurationChangeNotification`
- `0x18005324f`: `IptlsConfigurationChangeNotification`
- `0x180053288`: `IptlsConfigurationChangeNotification`
- `0x1800530f6`: `Entered: Common: OnConfigChange`
- `0x180053107`: `onecoreuap\net\netio\iphlpsvc\service\common.c`
- `0x18005316e`: `PortConfigurationChangeNotification`
- `0x1800531a7`: `PortConfigurationChangeNotification`
- `0x1800531b6`: `IsatapConfigurationChangeNotification`
- `0x1800531ef`: `IsatapConfigurationChangeNotification`
- `0x18005329a`: `SplTunMgrConfigurationChangeNotification`
- `0x1800532d3`: `SplTunMgrConfigurationChangeNotification`
- `0x180053371`: `Leaving: Common: OnConfigChange`

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
    if ( !TrySubmitThreadpoolCallback(Process6to4ConfigurationChange, 0, &CallbackEnvironment) )
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
      if ( !TrySubmitThreadpoolCallback(PortConfigurationChangeNotification, 0, &CallbackEnvironment) )
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
        if ( !TrySubmitThreadpoolCallback(IsatapConfigurationChangeNotification, 0, &CallbackEnvironment) )
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
          if ( !TrySubmitThreadpoolCallback(TeredoConfigurationChangeNotification, (PVOID)5, &CallbackEnvironment) )
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
            if ( !TrySubmitThreadpoolCallback(IpTlsConfigurationChangeNotification, 0, &CallbackEnvironment) )
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
                if ( !TrySubmitThreadpoolCallback(Dns64ConfigurationChangeNotification, 0, &CallbackEnvironment) )
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
0x1800530ec  mov     [rsp+arg_0], rbx
0x1800530f1  push    rdi
0x1800530f2  sub     rsp, 20h
0x1800530f6  lea     rdx, aEnteredCommonO_0; "Entered: Common: OnConfigChange"
0x1800530fd  mov     ecx, 20000h
0x180053102  call    EventWriteEnterEx
0x180053107  lea     rbx, aOnecoreuapNetN_18; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x18005310e  mov     r8d, 4A3h
0x180053114  mov     rdx, rbx
0x180053117  lea     rcx, aProcess6to4con; "Process6to4ConfigurationChange"
0x18005311e  call    ReferenceServiceEx
0x180053123  test    eax, eax
0x180053125  jz      loc_180053382
0x18005312b  lea     rdi, CallbackEnvironment
0x180053132  xor     edx, edx; pv
0x180053134  mov     r8, rdi; pcbe
0x180053137  lea     rcx, Process6to4ConfigurationChange; pfns
0x18005313e  call    cs:__imp_TrySubmitThreadpoolCallback
0x180053145  nop     dword ptr [rax+rax+00h]
0x18005314a  mov     rdx, rbx
0x18005314d  test    eax, eax
0x18005314f  jnz     short loc_180053168
0x180053151  mov     r8d, 4A7h
0x180053157  lea     rcx, aProcess6to4con; "Process6to4ConfigurationChange"
0x18005315e  call    DereferenceServiceEx
0x180053163  jmp     loc_180053382
0x180053168  mov     r8d, 4ABh
0x18005316e  lea     rcx, aPortconfigurat; "PortConfigurationChangeNotification"
0x180053175  call    ReferenceServiceEx
0x18005317a  test    eax, eax
0x18005317c  jz      loc_180053382
0x180053182  mov     r8, rdi; pcbe
0x180053185  lea     rcx, PortConfigurationChangeNotification; pfns
0x18005318c  xor     edx, edx; pv
0x18005318e  call    cs:__imp_TrySubmitThreadpoolCallback
0x180053195  nop     dword ptr [rax+rax+00h]
0x18005319a  mov     rdx, rbx
0x18005319d  test    eax, eax
0x18005319f  jnz     short loc_1800531B0
0x1800531a1  mov     r8d, 4AFh
0x1800531a7  lea     rcx, aPortconfigurat; "PortConfigurationChangeNotification"
0x1800531ae  jmp     short loc_18005315E
0x1800531b0  mov     r8d, 4B3h
0x1800531b6  lea     rcx, aIsatapconfigur; "IsatapConfigurationChangeNotification"
0x1800531bd  call    ReferenceServiceEx
0x1800531c2  test    eax, eax
0x1800531c4  jz      loc_180053382
0x1800531ca  mov     r8, rdi; pcbe
0x1800531cd  lea     rcx, IsatapConfigurationChangeNotification; pfns
0x1800531d4  xor     edx, edx; pv
0x1800531d6  call    cs:__imp_TrySubmitThreadpoolCallback
0x1800531dd  nop     dword ptr [rax+rax+00h]
0x1800531e2  mov     rdx, rbx
0x1800531e5  test    eax, eax
0x1800531e7  jnz     short loc_1800531FB
0x1800531e9  mov     r8d, 4B7h
0x1800531ef  lea     rcx, aIsatapconfigur; "IsatapConfigurationChangeNotification"
0x1800531f6  jmp     loc_18005315E
0x1800531fb  mov     r8d, 4BBh
0x180053201  lea     rcx, aTeredoconfigur; "TeredoConfigurationChangeNotification"
0x180053208  call    ReferenceServiceEx
0x18005320d  test    eax, eax
0x18005320f  jz      loc_180053382
0x180053215  mov     r8, rdi; pcbe
0x180053218  lea     rcx, TeredoConfigurationChangeNotification; pfns
0x18005321f  mov     edx, 5; pv
0x180053224  call    cs:__imp_TrySubmitThreadpoolCallback
0x18005322b  nop     dword ptr [rax+rax+00h]
0x180053230  mov     rdx, rbx
0x180053233  test    eax, eax
0x180053235  jnz     short loc_180053249
0x180053237  mov     r8d, 4C2h
0x18005323d  lea     rcx, aTeredoconfigur; "TeredoConfigurationChangeNotification"
0x180053244  jmp     loc_18005315E
0x180053249  mov     r8d, 4C6h
0x18005324f  lea     rcx, aIptlsconfigura; "IptlsConfigurationChangeNotification"
0x180053256  call    ReferenceServiceEx
0x18005325b  test    eax, eax
0x18005325d  jz      loc_180053382
0x180053263  mov     r8, rdi; pcbe
0x180053266  lea     rcx, IpTlsConfigurationChangeNotification; pfns
0x18005326d  xor     edx, edx; pv
0x18005326f  call    cs:__imp_TrySubmitThreadpoolCallback
0x180053276  nop     dword ptr [rax+rax+00h]
0x18005327b  mov     rdx, rbx
0x18005327e  test    eax, eax
0x180053280  jnz     short loc_180053294
0x180053282  mov     r8d, 4CAh
0x180053288  lea     rcx, aIptlsconfigura; "IptlsConfigurationChangeNotification"
0x18005328f  jmp     loc_18005315E
0x180053294  mov     r8d, 4CEh
0x18005329a  lea     rcx, aSpltunmgrconfi_0; "SplTunMgrConfigurationChangeNotificatio"...
0x1800532a1  call    ReferenceServiceEx
0x1800532a6  test    eax, eax
0x1800532a8  jz      loc_180053382
0x1800532ae  mov     r8, rdi; pcbe
0x1800532b1  lea     rcx, SplTunMgrConfigurationChangeNotification; pfns
0x1800532b8  xor     edx, edx; pv
0x1800532ba  call    cs:__imp_TrySubmitThreadpoolCallback
0x1800532c1  nop     dword ptr [rax+rax+00h]
0x1800532c6  mov     rdx, rbx
0x1800532c9  test    eax, eax
0x1800532cb  jnz     short loc_1800532DF
0x1800532cd  mov     r8d, 4D2h
0x1800532d3  lea     rcx, aSpltunmgrconfi_0; "SplTunMgrConfigurationChangeNotificatio"...
0x1800532da  jmp     loc_18005315E
0x1800532df  mov     r8d, 4D6h
0x1800532e5  lea     rcx, aDns64configura; "Dns64ConfigurationChangeNotification"
0x1800532ec  call    ReferenceServiceEx
0x1800532f1  test    eax, eax
0x1800532f3  jz      loc_180053382
0x1800532f9  mov     r8, rdi; pcbe
0x1800532fc  lea     rcx, Dns64ConfigurationChangeNotification; pfns
0x180053303  xor     edx, edx; pv
0x180053305  call    cs:__imp_TrySubmitThreadpoolCallback
0x18005330c  nop     dword ptr [rax+rax+00h]
0x180053311  mov     rdx, rbx
0x180053314  test    eax, eax
0x180053316  jnz     short loc_18005332A
0x180053318  mov     r8d, 4DAh
0x18005331e  lea     rcx, aDns64configura; "Dns64ConfigurationChangeNotification"
0x180053325  jmp     loc_18005315E
0x18005332a  mov     r8d, 4DEh
0x180053330  lea     rcx, aDasitemgrgpcon; "DaSiteMgrGpConfigurationChangeNotificat"...
0x180053337  call    ReferenceServiceEx
0x18005333c  test    eax, eax
0x18005333e  jz      short loc_180053382
0x180053340  mov     r8, rdi; pcbe
0x180053343  lea     rcx, DaSiteMgrGpConfigurationChangeNotification; pfns
0x18005334a  xor     edx, edx; pv
0x18005334c  call    cs:__imp_TrySubmitThreadpoolCallback
0x180053353  nop     dword ptr [rax+rax+00h]
0x180053358  test    eax, eax
0x18005335a  jnz     short loc_180053371
0x18005335c  mov     r8d, 4E2h
0x180053362  lea     rcx, aDasitemgrgpcon; "DaSiteMgrGpConfigurationChangeNotificat"...
0x180053369  mov     rdx, rbx
0x18005336c  jmp     loc_18005315E
0x180053371  lea     rdx, aLeavingCommonO_0; "Leaving: Common: OnConfigChange"
0x180053378  mov     ecx, 20000h
0x18005337d  call    EventWriteLeaveEx
0x180053382  mov     rbx, [rsp+28h+arg_0]
0x180053387  add     rsp, 20h
0x18005338b  pop     rdi
0x18005338c  retn
```
