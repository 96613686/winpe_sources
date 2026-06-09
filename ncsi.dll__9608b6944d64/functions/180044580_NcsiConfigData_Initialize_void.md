# NcsiConfigData::Initialize(void)

- ea: `0x180044580`
- end: `0x1800448f8`
- name: `?Initialize@NcsiConfigData@@QEAAXXZ`
- size: `888`
- prototype: `void __fastcall(NcsiConfigData *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x180050300`

## callees

- `0x180010200`
- `0x180011a58`
- `0x18001572c`
- `0x180044580`
- `0x180044900`
- `0x180047240`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x180044839`
- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x180044839`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeThread` at `0x1800445b8`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeThread` at `0x1800445b8`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180044650`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800446b6`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18004471a`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180044650`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800446b6`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18004471a`

## pseudocode

```c
void __fastcall NcsiConfigData::Initialize(NcsiConfigData *this)
{
  __int64 v1; // rcx
  __int64 v2; // rdx
  HANDLE EventW; // rax
  HANDLE v4; // rax
  HANDLE v5; // rax
  __int64 v6; // rbx
  DWORD ExitCode; // [rsp+30h] [rbp-18h] BYREF
  unsigned int v8; // [rsp+34h] [rbp-14h] BYREF

  NcsiConfigData::QueryRegistry(this);
  ExitCode = 0;
  if ( (char *)g_registryMonitorThread - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL
    && GetExitCodeThread(g_registryMonitorThread, &ExitCode)
    && ExitCode == 259 )
  {
    v1 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 0x10) != 0
      && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 2u )
    {
      v2 = 26;
LABEL_38:
      WPP_SF_(*(_QWORD *)(v1 + 16), v2, &WPP_5540ffa188b23fc0b8d03d8186783076_Traceguids);
    }
  }
  else if ( (char *)g_registryMonitorEvent - 1 > (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    EventW = CreateEventW(0, 0, 0, 0);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      &g_registryMonitorEvent,
      EventW);
    if ( (char *)g_registryNotificationEvent - 1 > (char *)0xFFFFFFFFFFFFFFFDLL )
    {
      v4 = CreateEventW(0, 1, 0, 0);
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
        &g_registryNotificationEvent,
        v4);
      if ( (char *)g_gpRegistryMonitorEvent - 1 > (char *)0xFFFFFFFFFFFFFFFDLL )
      {
        v5 = CreateEventW(0, 0, 0, 0);
        wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
          &g_gpRegistryMonitorEvent,
          v5);
        if ( (((unsigned __int64)g_registryMonitorEvent + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
        {
          if ( (((unsigned __int64)g_registryNotificationEvent + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
          {
            if ( (((unsigned __int64)g_gpRegistryMonitorEvent + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
            {
              v8 = 0;
              v6 = _o__beginthreadex(0, 0, NcsiConfigData::MonitorRegistry, 0, 0, &v8);
              if ( v6 )
              {
                wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
                  &g_registryMonitorThread,
                  0);
                _InterlockedExchange64((volatile __int64 *)&g_registryMonitorThread, v6);
                if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                  && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 0x10) != 0
                  && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 5u )
                {
                  WPP_SF_d(
                    *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
                    34,
                    &WPP_5540ffa188b23fc0b8d03d8186783076_Traceguids,
                    v8);
                }
              }
              else
              {
                if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                  && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 0x10) != 0
                  && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 2u )
                {
                  WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 33, &WPP_5540ffa188b23fc0b8d03d8186783076_Traceguids);
                }
                wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
                  &g_registryMonitorEvent,
                  0);
                wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
                  &g_gpRegistryMonitorEvent,
                  0);
              }
            }
            else
            {
              v1 = WPP_GLOBAL_Control;
              if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 0x10) != 0
                && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 2u )
              {
                v2 = 32;
                goto LABEL_38;
              }
            }
          }
          else
          {
            v1 = WPP_GLOBAL_Control;
            if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 0x10) != 0
              && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 2u )
            {
              v2 = 31;
              goto LABEL_38;
            }
          }
        }
        else
        {
          v1 = WPP_GLOBAL_Control;
          if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 0x10) != 0
            && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 2u )
          {
            v2 = 30;
            goto LABEL_38;
          }
        }
      }
      else
      {
        v1 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 0x10) != 0
          && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 2u )
        {
          v2 = 29;
          goto LABEL_38;
        }
      }
    }
    else
    {
      v1 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 0x10) != 0
        && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 2u )
      {
        v2 = 28;
        goto LABEL_38;
      }
    }
  }
  else
  {
    v1 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 0x10) != 0
      && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 2u )
    {
      v2 = 27;
      goto LABEL_38;
    }
  }
}

```

## disassembly

```asm
0x180044580  push    rbx
0x180044582  sub     rsp, 40h
0x180044586  mov     rax, cs:__security_cookie
0x18004458d  xor     rax, rsp
0x180044590  mov     [rsp+48h+var_10], rax
0x180044595  call    ?QueryRegistry@NcsiConfigData@@QEAAXXZ; NcsiConfigData::QueryRegistry(void)
0x18004459a  mov     rcx, cs:?g_registryMonitorThread@@3V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@A; hThread
0x1800445a1  mov     [rsp+48h+ExitCode], 0
0x1800445a9  lea     rax, [rcx-1]
0x1800445ad  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800445b1  ja      short loc_180044601
0x1800445b3  lea     rdx, [rsp+48h+ExitCode]; lpExitCode
0x1800445b8  call    cs:__imp_GetExitCodeThread
0x1800445be  test    eax, eax
0x1800445c0  jz      short loc_180044601
0x1800445c2  cmp     [rsp+48h+ExitCode], 103h
0x1800445ca  jnz     short loc_180044601
0x1800445cc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800445d3  lea     rax, WPP_GLOBAL_Control
0x1800445da  cmp     rcx, rax
0x1800445dd  jz      loc_1800448E5
0x1800445e3  test    byte ptr [rcx+1Ch], 10h
0x1800445e7  jz      loc_1800448E5
0x1800445ed  cmp     byte ptr [rcx+19h], 2
0x1800445f1  jb      loc_1800448E5
0x1800445f7  mov     edx, 1Ah
0x1800445fc  jmp     loc_1800447FC
0x180044601  mov     rax, cs:?g_registryMonitorEvent@@3V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@A; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> g_registryMonitorEvent
0x180044608  dec     rax
0x18004460b  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18004460f  ja      short loc_180044646
0x180044611  mov     rcx, cs:WPP_GLOBAL_Control
0x180044618  lea     rax, WPP_GLOBAL_Control
0x18004461f  cmp     rcx, rax
0x180044622  jz      loc_1800448E5
0x180044628  test    byte ptr [rcx+1Ch], 10h
0x18004462c  jz      loc_1800448E5
0x180044632  cmp     byte ptr [rcx+19h], 2
0x180044636  jb      loc_1800448E5
0x18004463c  mov     edx, 1Bh
0x180044641  jmp     loc_1800447FC
0x180044646  xor     r9d, r9d; lpName
0x180044649  xor     r8d, r8d; bInitialState
0x18004464c  xor     edx, edx; bManualReset
0x18004464e  xor     ecx, ecx; lpEventAttributes
0x180044650  call    cs:__imp_CreateEventW
0x180044656  mov     rdx, rax
0x180044659  lea     rcx, ?g_registryMonitorEvent@@3V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@A; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> g_registryMonitorEvent
0x180044660  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180044665  mov     rax, cs:?g_registryNotificationEvent@@3V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@A; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> g_registryNotificationEvent
0x18004466c  dec     rax
0x18004466f  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180044673  ja      short loc_1800446AA
0x180044675  mov     rcx, cs:WPP_GLOBAL_Control
0x18004467c  lea     rax, WPP_GLOBAL_Control
0x180044683  cmp     rcx, rax
0x180044686  jz      loc_1800448E5
0x18004468c  test    byte ptr [rcx+1Ch], 10h
0x180044690  jz      loc_1800448E5
0x180044696  cmp     byte ptr [rcx+19h], 2
0x18004469a  jb      loc_1800448E5
0x1800446a0  mov     edx, 1Ch
0x1800446a5  jmp     loc_1800447FC
0x1800446aa  xor     r9d, r9d; lpName
0x1800446ad  xor     r8d, r8d; bInitialState
0x1800446b0  xor     ecx, ecx; lpEventAttributes
0x1800446b2  lea     edx, [r9+1]; bManualReset
0x1800446b6  call    cs:__imp_CreateEventW
0x1800446bc  mov     rdx, rax
0x1800446bf  lea     rcx, ?g_registryNotificationEvent@@3V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@A; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> g_registryNotificationEvent
0x1800446c6  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1800446cb  mov     rax, cs:?g_gpRegistryMonitorEvent@@3V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@A; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> g_gpRegistryMonitorEvent
0x1800446d2  dec     rax
0x1800446d5  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800446d9  ja      short loc_180044710
0x1800446db  mov     rcx, cs:WPP_GLOBAL_Control
0x1800446e2  lea     rax, WPP_GLOBAL_Control
0x1800446e9  cmp     rcx, rax
0x1800446ec  jz      loc_1800448E5
0x1800446f2  test    byte ptr [rcx+1Ch], 10h
0x1800446f6  jz      loc_1800448E5
0x1800446fc  cmp     byte ptr [rcx+19h], 2
0x180044700  jb      loc_1800448E5
0x180044706  mov     edx, 1Dh
0x18004470b  jmp     loc_1800447FC
0x180044710  xor     r9d, r9d; lpName
0x180044713  xor     r8d, r8d; bInitialState
0x180044716  xor     edx, edx; bManualReset
0x180044718  xor     ecx, ecx; lpEventAttributes
0x18004471a  call    cs:__imp_CreateEventW
0x180044720  mov     rdx, rax
0x180044723  lea     rcx, ?g_gpRegistryMonitorEvent@@3V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@A; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> g_gpRegistryMonitorEvent
0x18004472a  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18004472f  mov     rax, cs:?g_registryMonitorEvent@@3V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@A; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> g_registryMonitorEvent
0x180044736  inc     rax
0x180044739  test    rax, 0FFFFFFFFFFFFFFFEh
0x18004473f  jnz     short loc_180044776
0x180044741  mov     rcx, cs:WPP_GLOBAL_Control
0x180044748  lea     rax, WPP_GLOBAL_Control
0x18004474f  cmp     rcx, rax
0x180044752  jz      loc_1800448E5
0x180044758  test    byte ptr [rcx+1Ch], 10h
0x18004475c  jz      loc_1800448E5
0x180044762  cmp     byte ptr [rcx+19h], 2
0x180044766  jb      loc_1800448E5
0x18004476c  mov     edx, 1Eh
0x180044771  jmp     loc_1800447FC
0x180044776  mov     rax, cs:?g_registryNotificationEvent@@3V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@A; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> g_registryNotificationEvent
0x18004477d  inc     rax
0x180044780  test    rax, 0FFFFFFFFFFFFFFFEh
0x180044786  jnz     short loc_1800447BA
0x180044788  mov     rcx, cs:WPP_GLOBAL_Control
0x18004478f  lea     rax, WPP_GLOBAL_Control
0x180044796  cmp     rcx, rax
0x180044799  jz      loc_1800448E5
0x18004479f  test    byte ptr [rcx+1Ch], 10h
0x1800447a3  jz      loc_1800448E5
0x1800447a9  cmp     byte ptr [rcx+19h], 2
0x1800447ad  jb      loc_1800448E5
0x1800447b3  mov     edx, 1Fh
0x1800447b8  jmp     short loc_1800447FC
0x1800447ba  mov     rax, cs:?g_gpRegistryMonitorEvent@@3V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@A; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> g_gpRegistryMonitorEvent
0x1800447c1  inc     rax
0x1800447c4  test    rax, 0FFFFFFFFFFFFFFFEh
0x1800447ca  jnz     short loc_180044811
0x1800447cc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800447d3  lea     rax, WPP_GLOBAL_Control
0x1800447da  cmp     rcx, rax
0x1800447dd  jz      loc_1800448E5
0x1800447e3  test    byte ptr [rcx+1Ch], 10h
0x1800447e7  jz      loc_1800448E5
0x1800447ed  cmp     byte ptr [rcx+19h], 2
0x1800447f1  jb      loc_1800448E5
0x1800447f7  mov     edx, 20h ; ' '
0x1800447fc  mov     rcx, [rcx+10h]
0x180044800  lea     r8, WPP_5540ffa188b23fc0b8d03d8186783076_Traceguids
0x180044807  call    WPP_SF_
0x18004480c  jmp     loc_1800448E5
0x180044811  lea     rax, [rsp+48h+var_14]
0x180044816  mov     [rsp+48h+var_14], 0
0x18004481e  mov     [rsp+48h+var_20], rax
0x180044823  lea     r8, ?MonitorRegistry@NcsiConfigData@@CAIPEAX@Z; NcsiConfigData::MonitorRegistry(void *)
0x18004482a  xor     r9d, r9d
0x18004482d  mov     [rsp+48h+var_28], 0
0x180044835  xor     edx, edx
0x180044837  xor     ecx, ecx
0x180044839  call    cs:__imp__o__beginthreadex
0x18004483f  mov     rbx, rax
0x180044842  test    rax, rax
0x180044845  jnz     short loc_180044897
0x180044847  mov     rcx, cs:WPP_GLOBAL_Control
0x18004484e  lea     rax, WPP_GLOBAL_Control
0x180044855  cmp     rcx, rax
0x180044858  jz      short loc_180044879
0x18004485a  test    byte ptr [rcx+1Ch], 10h
0x18004485e  jz      short loc_180044879
0x180044860  cmp     byte ptr [rcx+19h], 2
0x180044864  jb      short loc_180044879
0x180044866  mov     rcx, [rcx+10h]
0x18004486a  lea     edx, [rbx+21h]
0x18004486d  lea     r8, WPP_5540ffa188b23fc0b8d03d8186783076_Traceguids
0x180044874  call    WPP_SF_
0x180044879  xor     edx, edx
0x18004487b  lea     rcx, ?g_registryMonitorEvent@@3V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@A; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> g_registryMonitorEvent
0x180044882  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180044887  xor     edx, edx
0x180044889  lea     rcx, ?g_gpRegistryMonitorEvent@@3V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@A; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> g_gpRegistryMonitorEvent
0x180044890  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180044895  jmp     short loc_1800448E5
0x180044897  xor     edx, edx
0x180044899  lea     rcx, ?g_registryMonitorThread@@3V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@A; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> g_registryMonitorThread
0x1800448a0  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1800448a5  xchg    rbx, cs:?g_registryMonitorThread@@3V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@A; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> g_registryMonitorThread
0x1800448ac  mov     rcx, cs:WPP_GLOBAL_Control
0x1800448b3  lea     rax, WPP_GLOBAL_Control
0x1800448ba  cmp     rcx, rax
0x1800448bd  jz      short loc_1800448E5
0x1800448bf  test    byte ptr [rcx+1Ch], 10h
0x1800448c3  jz      short loc_1800448E5
0x1800448c5  cmp     byte ptr [rcx+19h], 5
0x1800448c9  jb      short loc_1800448E5
0x1800448cb  mov     r9d, [rsp+48h+var_14]
0x1800448d0  lea     r8, WPP_5540ffa188b23fc0b8d03d8186783076_Traceguids
0x1800448d7  mov     rcx, [rcx+10h]
0x1800448db  mov     edx, 22h ; '"'
0x1800448e0  call    WPP_SF_d
0x1800448e5  mov     rcx, [rsp+48h+var_10]
0x1800448ea  xor     rcx, rsp; StackCookie
0x1800448ed  call    __security_check_cookie
0x1800448f2  add     rsp, 40h
0x1800448f6  pop     rbx
0x1800448f7  retn
```
