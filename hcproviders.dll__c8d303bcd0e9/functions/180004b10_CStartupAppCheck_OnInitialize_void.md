# CStartupAppCheck::_OnInitialize(void)

- ea: `0x180004b10`
- end: `0x180004cc9`
- name: `?_OnInitialize@CStartupAppCheck@@MEAAJXZ`
- size: `441`
- prototype: `__int64 __fastcall(CStartupAppCheck *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x180004b10`
- `0x180008550`
- `0x1800085b0`
- `0x180009e16`
- `0x180009e40`
- `0x18000b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180004bba`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180004bba`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180004b8b`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180004b8b`
- `api-ms-win-power-base-l1-1-0!GetPwrCapabilities` at `0x180004c8b`
- `api-ms-win-power-base-l1-1-0!GetPwrCapabilities` at `0x180004c8b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180004c62`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180004c62`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x180004c2a`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x180004c2a`

## pseudocode

```c
__int64 __fastcall CStartupAppCheck::_OnInitialize(CStartupAppCheck *this)
{
  signed int updated; // ebx
  LSTATUS Key; // eax
  HANDLE EventW; // rax
  PTP_WAIT v5; // rax
  _TP_CALLBACK_ENVIRON_V3 pcbe; // [rsp+50h] [rbp-59h] BYREF
  _SYSTEM_POWER_CAPABILITIES spc; // [rsp+A0h] [rbp-9h] BYREF

  updated = CStartupAppCheck::_UpdateState(this, 0);
  if ( updated >= 0 )
  {
    Key = RegCreateKeyExW(
            HKEY_CURRENT_USER,
            L"Software\\Microsoft\\Windows\\CurrentVersion\\StartupNotify",
            0,
            0,
            0,
            0x10u,
            0,
            (PHKEY)this + 28,
            0);
    updated = Key;
    if ( Key > 0 )
      updated = (unsigned __int16)Key | 0x80070000;
    if ( updated >= 0 )
    {
      EventW = CreateEventW(0, 1, 0, 0);
      *((_QWORD *)this + 29) = EventW;
      if ( EventW )
      {
        *(_QWORD *)&pcbe.Version = 3;
        *(_QWORD *)&pcbe.Size = 72;
        memset(&pcbe.Pool, 0, 48);
        pcbe.CallbackPriority = TP_CALLBACK_PRIORITY_NORMAL;
        pcbe.u.Flags = 2;
        v5 = CreateThreadpoolWait(CStartupAppCheck::s_WaitCallback, this, &pcbe);
        *((_QWORD *)this + 30) = v5;
        if ( v5 )
        {
          (*(void (__fastcall **)(CStartupAppCheck *))(*(_QWORD *)this + 8LL))(this);
          SetThreadpoolWait(*((PTP_WAIT *)this + 30), *((HANDLE *)this + 29), 0);
          updated = CStartupAppCheck::_StartWatching(this);
        }
      }
    }
  }
  memset_0(&spc, 0, sizeof(spc));
  if ( GetPwrCapabilities(&spc) )
    g_BatteryPresent = spc.SystemBatteriesPresent;
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x180004b10  mov     [rsp-8+arg_8], rbx
0x180004b15  mov     [rsp-8+arg_10], rdi
0x180004b1a  push    rbp
0x180004b1b  lea     rbp, [rsp-57h]
0x180004b20  sub     rsp, 100h
0x180004b27  mov     rax, cs:__security_cookie
0x180004b2e  xor     rax, rsp
0x180004b31  mov     [rbp+57h+var_10], rax
0x180004b35  xor     edx, edx; bool
0x180004b37  mov     rdi, rcx
0x180004b3a  call    ?_UpdateState@CStartupAppCheck@@AEAAJ_N@Z; CStartupAppCheck::_UpdateState(bool)
0x180004b3f  mov     ebx, eax
0x180004b41  test    eax, eax
0x180004b43  js      loc_180004C78
0x180004b49  mov     [rsp+100h+lpdwDisposition], 0; lpdwDisposition
0x180004b52  lea     rax, [rdi+0E0h]
0x180004b59  mov     [rsp+100h+phkResult], rax; phkResult
0x180004b5e  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180004b65  mov     [rsp+100h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180004b6e  xor     r9d, r9d; lpClass
0x180004b71  mov     [rsp+100h+samDesired], 10h; samDesired
0x180004b79  xor     r8d, r8d; Reserved
0x180004b7c  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180004b83  mov     [rsp+100h+dwOptions], 0; dwOptions
0x180004b8b  call    cs:__imp_RegCreateKeyExW
0x180004b92  nop     dword ptr [rax+rax+00h]
0x180004b97  mov     ebx, eax
0x180004b99  test    eax, eax
0x180004b9b  jle     short loc_180004BA6
0x180004b9d  movzx   ebx, ax
0x180004ba0  or      ebx, 80070000h
0x180004ba6  test    ebx, ebx
0x180004ba8  js      loc_180004C78
0x180004bae  xor     r9d, r9d; lpName
0x180004bb1  xor     r8d, r8d; bInitialState
0x180004bb4  xor     ecx, ecx; lpEventAttributes
0x180004bb6  lea     edx, [r9+1]; bManualReset
0x180004bba  call    cs:__imp_CreateEventW
0x180004bc1  nop     dword ptr [rax+rax+00h]
0x180004bc6  mov     [rdi+0E8h], rax
0x180004bcd  test    rax, rax
0x180004bd0  jz      loc_180004C78
0x180004bd6  xorps   xmm0, xmm0
0x180004bd9  mov     qword ptr [rbp+57h+pcbe.Version], 3
0x180004be1  lea     r8, [rbp+57h+pcbe]; pcbe
0x180004be5  movdqa  xmmword ptr [rbp+57h+pcbe.RaceDll], xmm0
0x180004bea  mov     rdx, rdi; pv
0x180004bed  mov     qword ptr [rbp+57h+pcbe.Size], 48h ; 'H'
0x180004bf5  lea     rcx, ?s_WaitCallback@CStartupAppCheck@@KAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@K@Z; pfnwa
0x180004bfc  mov     [rbp+57h+pcbe.Pool], 0
0x180004c04  mov     [rbp+57h+pcbe.CleanupGroup], 0
0x180004c0c  mov     [rbp+57h+pcbe.CleanupGroupCancelCallback], 0
0x180004c14  mov     [rbp+57h+pcbe.FinalizationCallback], 0
0x180004c1c  mov     [rbp+57h+pcbe.CallbackPriority], 1
0x180004c23  mov     dword ptr [rbp+57h+pcbe.u], 2
0x180004c2a  call    cs:__imp_CreateThreadpoolWait
0x180004c31  nop     dword ptr [rax+rax+00h]
0x180004c36  mov     [rdi+0F0h], rax
0x180004c3d  test    rax, rax
0x180004c40  jz      short loc_180004C78
0x180004c42  mov     rax, [rdi]
0x180004c45  mov     rcx, rdi
0x180004c48  mov     rax, [rax+8]
0x180004c4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004c51  mov     rdx, [rdi+0E8h]; h
0x180004c58  xor     r8d, r8d; pftTimeout
0x180004c5b  mov     rcx, [rdi+0F0h]; pwa
0x180004c62  call    cs:__imp_SetThreadpoolWait
0x180004c69  nop     dword ptr [rax+rax+00h]
0x180004c6e  mov     rcx, rdi; this
0x180004c71  call    ?_StartWatching@CStartupAppCheck@@AEAAJXZ; CStartupAppCheck::_StartWatching(void)
0x180004c76  mov     ebx, eax
0x180004c78  xor     edx, edx; Val
0x180004c7a  lea     rcx, [rbp+57h+spc]; void *
0x180004c7e  lea     r8d, [rdx+4Ch]; Size
0x180004c82  call    memset_0
0x180004c87  lea     rcx, [rbp+57h+spc]; lpspc
0x180004c8b  call    cs:__imp_GetPwrCapabilities
0x180004c92  nop     dword ptr [rax+rax+00h]
0x180004c97  test    al, al
0x180004c99  jz      short loc_180004CA5
0x180004c9b  movzx   eax, [rbp+57h+spc.SystemBatteriesPresent]
0x180004c9f  mov     cs:?g_BatteryPresent@@3HA, eax; int g_BatteryPresent
0x180004ca5  mov     eax, ebx
0x180004ca7  mov     rcx, [rbp+57h+var_10]
0x180004cab  xor     rcx, rsp; StackCookie
0x180004cae  call    __security_check_cookie
0x180004cb3  lea     r11, [rsp+100h+var_s0]
0x180004cbb  mov     rbx, [r11+18h]
0x180004cbf  mov     rdi, [r11+20h]
0x180004cc3  mov     rsp, r11
0x180004cc6  pop     rbp
0x180004cc7  retn
```
