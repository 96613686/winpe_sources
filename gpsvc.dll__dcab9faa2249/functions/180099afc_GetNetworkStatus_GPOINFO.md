# GetNetworkStatus(_GPOINFO *)

- ea: `0x180099afc`
- end: `0x180099f24`
- name: `?GetNetworkStatus@@YA?AW4SyncModeNetworkStatus@@PEAU_GPOINFO@@@Z`
- size: `1064`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180058f20`

## callees

- `0x18000a504`
- `0x18000a52c`
- `0x180016640`
- `0x1800183d4`
- `0x18001ae40`
- `0x1800253c0`
- `0x180039148`
- `0x180054ff0`
- `0x180070458`
- `0x180075ec0`
- `0x180098b54`
- `0x180099afc`
- `0x1800bf010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180099ed2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180099ed2`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180099c67`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180099c67`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180099cdc`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180099cdc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180099eee`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180099eee`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180099f01`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180099f01`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180099b20`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180099c07`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180099c82`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180099e72`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180099b20`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180099c07`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180099c82`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180099e72`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180099ccd`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180099cee`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180099ccd`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180099cee`
- `api-ms-win-core-threadpool-legacy-l1-1-0!QueueUserWorkItem` at `0x180099cc3`
- `api-ms-win-core-threadpool-legacy-l1-1-0!QueueUserWorkItem` at `0x180099cc3`

## string_xrefs

- `0x180099bbf`: `SyncModeSlowLinkThresholdOnServerSKU`
- `0x180099bd4`: `SyncModeSlowLinkThreshold`
- `0x180099c2b`: `GetNetworkStatus: Failed to read DomainName.`
- `0x180099c51`: `GetNetworkStatus: Failed to read DomainName.`
- `0x180099d4a`: `GetNetworkStatus: can not successfully get dc name during Sync mode process.`
- `0x180099d6f`: `GetNetworkStatus: can not successfully get dc name during Sync mode process.`
- `0x180099da0`: `GetNetworkStatus: can't detect dc or detection is timeout during Sync mode process.`
- `0x180099dbb`: `GetNetworkStatus: can't detect dc or detection is timeout during Sync mode process.`
- `0x180099e9b`: `GetNetworkStatus: network status is SlowLink during Sync mode process.`
- `0x180099ebd`: `GetNetworkStatus: network status is SlowLink during Sync mode process.`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall GetNetworkStatus(__int64 a1)
{
  unsigned int v2; // esi
  __int64 v3; // rcx
  DWORD LastError; // ebx
  void (*v5)(unsigned int, const unsigned __int16 *, ...); // rax
  const wchar_t *v6; // rdx
  const unsigned __int16 *v7; // rdx
  HKEY v8; // rcx
  const unsigned __int16 *v9; // rdx
  HKEY v10; // rcx
  const unsigned __int16 *v11; // r8
  HANDLE EventW; // rax
  void *v13; // rdi
  DWORD TickCount; // r15d
  DWORD v15; // eax
  unsigned int v16; // r12d
  DWORD v17; // eax
  DWORD v18; // edi
  void (*v19)(unsigned int, const unsigned __int16 *, ...); // rax
  const wchar_t *v20; // rdx
  const struct _EVENT_DESCRIPTOR *v21; // rdx
  __int128 v23; // [rsp+20h] [rbp-48h] BYREF
  void *v24; // [rsp+30h] [rbp-38h] BYREF
  __int64 v25; // [rsp+38h] [rbp-30h]
  __int128 Context; // [rsp+40h] [rbp-28h] BYREF
  __int128 v27; // [rsp+50h] [rbp-18h]
  DWORD dwMilliseconds; // [rsp+B8h] [rbp+50h] BYREF
  unsigned int v29; // [rsp+C0h] [rbp+58h] BYREF
  unsigned int v30; // [rsp+C8h] [rbp+60h] BYREF

  v2 = 2;
  LastError = GetLastError();
  v23 = 0u;
  Context = 0;
  v27 = 0;
  if ( !a1 )
  {
    LastError = 87;
    if ( !*(_DWORD *)&g_dwDebugLevel )
      goto LABEL_57;
    v5 = g_lpDebugMsg;
    if ( !g_lpDebugMsg )
    {
      if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        RedirectDebugMsg(2u, L"GetNetworkStatus: lpGPOInfo is NULL.");
      goto LABEL_51;
    }
    v6 = L"GetNetworkStatus: lpGPOInfo is NULL.";
    goto LABEL_5;
  }
  v29 = 500;
  dwMilliseconds = 30000;
  if ( (unsigned int)GetFgPolicySettingImpl(v3, *(_DWORD *)a1 & 1) )
  {
    GetRegistrySettingValue(v8, v7, L"SyncModeSlowLinkThresholdOnServerSKU", &v29);
    v11 = L"SyncModeNoDCThresholdOnServerSKU";
  }
  else
  {
    GetRegistrySettingValue(v8, v7, L"SyncModeSlowLinkThreshold", &v29);
    v11 = L"SyncModeNoDCThreshold";
  }
  GetRegistrySettingValue(v10, v9, v11, &dwMilliseconds);
  if ( !(unsigned int)GetCachedString((struct _GPOINFO *)a1, L"DomainName", (unsigned __int16 **)&v23) )
  {
    LastError = GetLastError();
    if ( !*(_DWORD *)&g_dwDebugLevel )
      goto LABEL_57;
    v5 = g_lpDebugMsg;
    if ( !g_lpDebugMsg )
    {
      if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        RedirectDebugMsg(2u, L"GetNetworkStatus: Failed to read DomainName.");
      goto LABEL_51;
    }
    v6 = L"GetNetworkStatus: Failed to read DomainName.";
LABEL_5:
    v5(2u, v6);
    goto LABEL_51;
  }
  EventW = CreateEventW(0, 0, 0, 0);
  XHandle::operator=((void **)&v23 + 1, EventW);
  v13 = (void *)*((_QWORD *)&v23 + 1);
  if ( *((_QWORD *)&v23 + 1) )
  {
    Context = v23;
    LODWORD(v27) = 0;
    *(_DWORD *)(a1 + 312) = 0;
    *((_QWORD *)&v27 + 1) = a1;
    if ( QueueUserWorkItem(AsyncPingDomain, &Context, 0x100u) )
    {
      TickCount = GetTickCount();
      v15 = WaitForSingleObject(v13, dwMilliseconds);
      v16 = v29;
      if ( v15 )
      {
        if ( v15 != 258 )
        {
          LastError = GetLastError();
LABEL_50:
          if ( v2 != 2 )
            goto LABEL_57;
          goto LABEL_51;
        }
        v18 = 0;
        v2 = 4;
        if ( *(_DWORD *)&g_dwDebugLevel )
        {
          v19 = g_lpDebugMsg;
          if ( g_lpDebugMsg )
          {
            v20 = L"GetNetworkStatus: can't detect dc or detection is timeout during Sync mode process.";
            goto LABEL_32;
          }
          if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
            RedirectDebugMsg(2u, L"GetNetworkStatus: can't detect dc or detection is timeout during Sync mode process.");
        }
      }
      else
      {
        v17 = GetTickCount();
        v18 = v17;
        if ( !(_DWORD)v27 )
        {
          if ( v17 - TickCount >= v16 )
          {
            v2 = 2;
          }
          else
          {
            v2 = 1;
            if ( (unsigned int)DAIsSlowlink((struct _GPOINFO *)a1) )
              v2 = 2;
          }
          goto LABEL_43;
        }
        v2 = 4;
        if ( !*(_DWORD *)&g_dwDebugLevel )
          goto LABEL_43;
        v19 = g_lpDebugMsg;
        if ( g_lpDebugMsg )
        {
          v20 = L"GetNetworkStatus: can not successfully get dc name during Sync mode process.";
LABEL_32:
          v19(2u, v20);
          goto LABEL_43;
        }
        if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
          RedirectDebugMsg(2u, L"GetNetworkStatus: can not successfully get dc name during Sync mode process.");
      }
LABEL_43:
      v24 = 0;
      v25 = 0;
      if ( v2 == 2 )
      {
        v30 = v18 - TickCount;
        v29 = v16;
        dwMilliseconds = *(_DWORD *)a1 & 1;
        HIDWORD(v25) = 0;
        COperationalBaseEvent::AddArg((COperationalBaseEvent *)&v24, &dwMilliseconds);
        COperationalBaseEvent::AddArg((COperationalBaseEvent *)&v24, &v29);
        COperationalBaseEvent::AddArg((COperationalBaseEvent *)&v24, &v30);
        v21 = (const struct _EVENT_DESCRIPTOR *)gpEvent_GPO_PROC_SYNC_MODE_SLOWLINK;
      }
      else
      {
        if ( v2 != 4 )
        {
LABEL_48:
          CServiceConfigurationChangeOperationalEvent::~CServiceConfigurationChangeOperationalEvent(&v24);
          goto LABEL_50;
        }
        v29 = v18 - TickCount;
        dwMilliseconds = *(_DWORD *)a1 & 1;
        HIDWORD(v25) = 0;
        COperationalBaseEvent::AddArg((COperationalBaseEvent *)&v24, &dwMilliseconds);
        COperationalBaseEvent::AddArg((COperationalBaseEvent *)&v24, &v29);
        v21 = &gpEvent_GPO_PROC_SYNC_MODE_NO_DC;
      }
      COperationalBaseEvent::ReportOperationalEvent((COperationalBaseEvent *)&v24, v21);
      goto LABEL_48;
    }
  }
  LastError = GetLastError();
LABEL_51:
  if ( *(_DWORD *)&g_dwDebugLevel )
  {
    if ( g_lpDebugMsg )
    {
      g_lpDebugMsg(2u, L"GetNetworkStatus: network status is SlowLink during Sync mode process.");
    }
    else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
    {
      RedirectDebugMsg(2u, L"GetNetworkStatus: network status is SlowLink during Sync mode process.");
    }
  }
LABEL_57:
  EnterCriticalSection(&g_StatusCallbackCS);
  *(_DWORD *)(a1 + 312) = 1;
  *((_QWORD *)&Context + 1) = 0;
  LeaveCriticalSection(&g_StatusCallbackCS);
  XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>((void **)&v23);
  SetLastError(LastError);
  XHandle::~XHandle((void **)&v23 + 1);
  return v2;
}

```

## disassembly

```asm
0x180099afc  push    rbp
0x180099afe  push    rbx
0x180099aff  push    rsi
0x180099b00  push    rdi
0x180099b01  push    r12
0x180099b03  push    r13
0x180099b05  push    r14
0x180099b07  push    r15
0x180099b09  mov     rbp, rsp
0x180099b0c  sub     rsp, 68h
0x180099b10  mov     r14, rcx
0x180099b13  xor     r13d, r13d
0x180099b16  mov     qword ptr [rbp+var_48+8], r13
0x180099b1a  lea     edi, [r13+2]
0x180099b1e  mov     esi, edi
0x180099b20  call    cs:__imp_GetLastError
0x180099b26  mov     ebx, eax
0x180099b28  mov     [rbp+arg_0], eax
0x180099b2b  mov     qword ptr [rbp+var_48], r13
0x180099b2f  xorps   xmm0, xmm0
0x180099b32  movups  [rbp+Context], xmm0
0x180099b36  movups  [rbp+var_18], xmm0
0x180099b3a  test    r14, r14
0x180099b3d  jnz     short loc_180099B9E
0x180099b3f  lea     ebx, [rdi+55h]
0x180099b42  mov     [rbp+arg_0], ebx
0x180099b45  cmp     cs:?g_dwDebugLevel@@3KA, r13d; ulong g_dwDebugLevel
0x180099b4c  jz      loc_180099ECB
0x180099b52  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x180099b59  test    rax, rax
0x180099b5c  jz      short loc_180099B71
0x180099b5e  lea     rdx, aGetnetworkstat; "GetNetworkStatus: lpGPOInfo is NULL."
0x180099b65  mov     ecx, edi
0x180099b67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180099b6c  jmp     loc_180099E86
0x180099b71  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r13; void * g_lpDebugMsgContextInstance
0x180099b78  jz      loc_180099E86
0x180099b7e  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r13; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x180099b85  jz      loc_180099E86
0x180099b8b  lea     rdx, aGetnetworkstat; "GetNetworkStatus: lpGPOInfo is NULL."
0x180099b92  mov     ecx, edi; unsigned int
0x180099b94  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x180099b99  jmp     loc_180099E86
0x180099b9e  mov     [rbp+arg_10], 1F4h
0x180099ba5  mov     [rbp+dwMilliseconds], 7530h
0x180099bac  mov     edx, [r14]
0x180099baf  and     edx, 1
0x180099bb2  call    GetFgPolicySettingImpl
0x180099bb7  lea     r9, [rbp+arg_10]; unsigned int *
0x180099bbb  test    eax, eax
0x180099bbd  jz      short loc_180099BD4
0x180099bbf  lea     r8, aSyncmodeslowli; "SyncModeSlowLinkThresholdOnServerSKU"
0x180099bc6  call    ?GetRegistrySettingValue@@YAHPEAUHKEY__@@PEBG1PEAK@Z; GetRegistrySettingValue(HKEY__ *,ushort const *,ushort const *,ulong *)
0x180099bcb  lea     r8, aSyncmodenodcth; "SyncModeNoDCThresholdOnServerSKU"
0x180099bd2  jmp     short loc_180099BE7
0x180099bd4  lea     r8, aSyncmodeslowli_0; "SyncModeSlowLinkThreshold"
0x180099bdb  call    ?GetRegistrySettingValue@@YAHPEAUHKEY__@@PEBG1PEAK@Z; GetRegistrySettingValue(HKEY__ *,ushort const *,ushort const *,ulong *)
0x180099be0  lea     r8, aSyncmodenodcth_0; "SyncModeNoDCThreshold"
0x180099be7  lea     r9, [rbp+dwMilliseconds]; unsigned int *
0x180099beb  call    ?GetRegistrySettingValue@@YAHPEAUHKEY__@@PEBG1PEAK@Z; GetRegistrySettingValue(HKEY__ *,ushort const *,ushort const *,ulong *)
0x180099bf0  lea     r8, [rbp+var_48]; unsigned __int16 **
0x180099bf4  lea     rdx, aDomainname; "DomainName"
0x180099bfb  mov     rcx, r14; struct _GPOINFO *
0x180099bfe  call    ?GetCachedString@@YAHPEAU_GPOINFO@@PEBGPEAPEAG@Z; GetCachedString(_GPOINFO *,ushort const *,ushort * *)
0x180099c03  test    eax, eax
0x180099c05  jnz     short loc_180099C5D
0x180099c07  call    cs:__imp_GetLastError
0x180099c0d  mov     ebx, eax
0x180099c0f  mov     [rbp+arg_0], eax
0x180099c12  cmp     cs:?g_dwDebugLevel@@3KA, r13d; ulong g_dwDebugLevel
0x180099c19  jz      loc_180099ECB
0x180099c1f  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x180099c26  test    rax, rax
0x180099c29  jz      short loc_180099C37
0x180099c2b  lea     rdx, aGetnetworkstat_2; "GetNetworkStatus: Failed to read Domain"...
0x180099c32  jmp     loc_180099B65
0x180099c37  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r13; void * g_lpDebugMsgContextInstance
0x180099c3e  jz      loc_180099E86
0x180099c44  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r13; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x180099c4b  jz      loc_180099E86
0x180099c51  lea     rdx, aGetnetworkstat_2; "GetNetworkStatus: Failed to read Domain"...
0x180099c58  jmp     loc_180099B92
0x180099c5d  xor     r9d, r9d; lpName
0x180099c60  xor     r8d, r8d; bInitialState
0x180099c63  xor     edx, edx; bManualReset
0x180099c65  xor     ecx, ecx; lpEventAttributes
0x180099c67  call    cs:__imp_CreateEventW
0x180099c6d  mov     rdx, rax
0x180099c70  lea     rcx, [rbp+var_48+8]
0x180099c74  call    ??4XHandle@@QEAAXPEAX@Z; XHandle::operator=(void *)
0x180099c79  mov     rdi, qword ptr [rbp+var_48+8]
0x180099c7d  test    rdi, rdi
0x180099c80  jnz     short loc_180099C97
0x180099c82  call    cs:__imp_GetLastError
0x180099c88  mov     ebx, eax
0x180099c8a  mov     [rbp+arg_0], eax
0x180099c8d  mov     edi, 2
0x180099c92  jmp     loc_180099E86
0x180099c97  mov     rax, qword ptr [rbp+var_48]
0x180099c9b  mov     qword ptr [rbp+Context], rax
0x180099c9f  mov     qword ptr [rbp+Context+8], rdi
0x180099ca3  mov     dword ptr [rbp+var_18], r13d
0x180099ca7  mov     [r14+138h], r13d
0x180099cae  mov     qword ptr [rbp+var_18+8], r14
0x180099cb2  mov     r8d, 100h; Flags
0x180099cb8  lea     rdx, [rbp+Context]; Context
0x180099cbc  lea     rcx, ?AsyncPingDomain@@YAKPEAX@Z; Function
0x180099cc3  call    cs:__imp_QueueUserWorkItem
0x180099cc9  test    eax, eax
0x180099ccb  jz      short loc_180099C82
0x180099ccd  call    cs:__imp_GetTickCount
0x180099cd3  mov     r15d, eax
0x180099cd6  mov     edx, [rbp+dwMilliseconds]; dwMilliseconds
0x180099cd9  mov     rcx, rdi; hHandle
0x180099cdc  call    cs:__imp_WaitForSingleObject
0x180099ce2  mov     r12d, [rbp+arg_10]
0x180099ce6  test    eax, eax
0x180099ce8  jnz     loc_180099D78
0x180099cee  call    cs:__imp_GetTickCount
0x180099cf4  mov     edi, eax
0x180099cf6  cmp     dword ptr [rbp+var_18], r13d
0x180099cfa  jnz     short loc_180099D2C
0x180099cfc  mov     ecx, eax
0x180099cfe  sub     ecx, r15d
0x180099d01  cmp     ecx, r12d
0x180099d04  jnb     short loc_180099D20
0x180099d06  mov     esi, 1
0x180099d0b  mov     rcx, r14; struct _GPOINFO *
0x180099d0e  call    ?DAIsSlowlink@@YAHPEAU_GPOINFO@@@Z; DAIsSlowlink(_GPOINFO *)
0x180099d13  test    eax, eax
0x180099d15  lea     eax, [rsi+1]
0x180099d18  cmovnz  esi, eax
0x180099d1b  jmp     loc_180099DD1
0x180099d20  mov     eax, 2
0x180099d25  mov     esi, eax
0x180099d27  jmp     loc_180099DD1
0x180099d2c  mov     esi, 4
0x180099d31  cmp     cs:?g_dwDebugLevel@@3KA, r13d; ulong g_dwDebugLevel
0x180099d38  jz      loc_180099DCC
0x180099d3e  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x180099d45  test    rax, rax
0x180099d48  jz      short loc_180099D5D
0x180099d4a  lea     rdx, aGetnetworkstat_3; "GetNetworkStatus: can not successfully "...
0x180099d51  mov     ecx, 2
0x180099d56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180099d5b  jmp     short loc_180099DCC
0x180099d5d  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r13; void * g_lpDebugMsgContextInstance
0x180099d64  jz      short loc_180099DCC
0x180099d66  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r13; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x180099d6d  jz      short loc_180099DCC
0x180099d6f  lea     rdx, aGetnetworkstat_3; "GetNetworkStatus: can not successfully "...
0x180099d76  jmp     short loc_180099DC2
0x180099d78  cmp     eax, 102h
0x180099d7d  jnz     loc_180099E72
0x180099d83  mov     edi, r13d
0x180099d86  mov     esi, 4
0x180099d8b  cmp     cs:?g_dwDebugLevel@@3KA, r13d; ulong g_dwDebugLevel
0x180099d92  jz      short loc_180099DCC
0x180099d94  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x180099d9b  test    rax, rax
0x180099d9e  jz      short loc_180099DA9
0x180099da0  lea     rdx, aGetnetworkstat_0; "GetNetworkStatus: can't detect dc or de"...
0x180099da7  jmp     short loc_180099D51
0x180099da9  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r13; void * g_lpDebugMsgContextInstance
0x180099db0  jz      short loc_180099DCC
0x180099db2  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r13; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x180099db9  jz      short loc_180099DCC
0x180099dbb  lea     rdx, aGetnetworkstat_0; "GetNetworkStatus: can't detect dc or de"...
0x180099dc2  mov     ecx, 2; unsigned int
0x180099dc7  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x180099dcc  mov     eax, 2
0x180099dd1  mov     [rbp+var_38], r13
0x180099dd5  mov     [rbp+var_30], r13
0x180099dd9  cmp     esi, eax
0x180099ddb  jnz     short loc_180099E24
0x180099ddd  sub     edi, r15d
0x180099de0  mov     [rbp+arg_18], edi
0x180099de3  mov     [rbp+arg_10], r12d
0x180099de7  mov     eax, [r14]
0x180099dea  and     eax, 1
0x180099ded  mov     [rbp+dwMilliseconds], eax
0x180099df0  mov     dword ptr [rbp+var_30+4], r13d
0x180099df4  lea     rdx, [rbp+dwMilliseconds]; unsigned int *
0x180099df8  lea     rcx, [rbp+var_38]; this
0x180099dfc  call    ?AddArg@COperationalBaseEvent@@IEAAKAEAK@Z; COperationalBaseEvent::AddArg(ulong &)
0x180099e01  lea     rdx, [rbp+arg_10]; unsigned int *
0x180099e05  lea     rcx, [rbp+var_38]; this
0x180099e09  call    ?AddArg@COperationalBaseEvent@@IEAAKAEAK@Z; COperationalBaseEvent::AddArg(ulong &)
0x180099e0e  lea     rdx, [rbp+arg_18]; unsigned int *
0x180099e12  lea     rcx, [rbp+var_38]; this
0x180099e16  call    ?AddArg@COperationalBaseEvent@@IEAAKAEAK@Z; COperationalBaseEvent::AddArg(ulong &)
0x180099e1b  lea     rdx, gpEvent_GPO_PROC_SYNC_MODE_SLOWLINK
0x180099e22  jmp     short loc_180099E5D
0x180099e24  cmp     esi, 4
0x180099e27  jnz     short loc_180099E67
0x180099e29  sub     edi, r15d
0x180099e2c  mov     [rbp+arg_10], edi
0x180099e2f  mov     eax, [r14]
0x180099e32  and     eax, 1
0x180099e35  mov     [rbp+dwMilliseconds], eax
0x180099e38  mov     dword ptr [rbp+var_30+4], r13d
0x180099e3c  lea     rdx, [rbp+dwMilliseconds]; unsigned int *
0x180099e40  lea     rcx, [rbp+var_38]; this
0x180099e44  call    ?AddArg@COperationalBaseEvent@@IEAAKAEAK@Z; COperationalBaseEvent::AddArg(ulong &)
0x180099e49  lea     rdx, [rbp+arg_10]; unsigned int *
0x180099e4d  lea     rcx, [rbp+var_38]; this
0x180099e51  call    ?AddArg@COperationalBaseEvent@@IEAAKAEAK@Z; COperationalBaseEvent::AddArg(ulong &)
0x180099e56  lea     rdx, gpEvent_GPO_PROC_SYNC_MODE_NO_DC; struct _EVENT_DESCRIPTOR *
0x180099e5d  lea     rcx, [rbp+var_38]; this
0x180099e61  call    ?ReportOperationalEvent@COperationalBaseEvent@@IEAAKPEBU_EVENT_DESCRIPTOR@@@Z; COperationalBaseEvent::ReportOperationalEvent(_EVENT_DESCRIPTOR const *)
0x180099e66  nop
0x180099e67  lea     rcx, [rbp+var_38]; this
0x180099e6b  call    ??1CServiceConfigurationChangeOperationalEvent@@QEAA@XZ; CServiceConfigurationChangeOperationalEvent::~CServiceConfigurationChangeOperationalEvent(void)
0x180099e70  jmp     short loc_180099E7D
0x180099e72  call    cs:__imp_GetLastError
0x180099e78  mov     ebx, eax
0x180099e7a  mov     [rbp+arg_0], eax
0x180099e7d  mov     edi, 2
0x180099e82  cmp     esi, edi
0x180099e84  jnz     short loc_180099ECB
0x180099e86  cmp     cs:?g_dwDebugLevel@@3KA, r13d; ulong g_dwDebugLevel
0x180099e8d  jz      short loc_180099ECB
0x180099e8f  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x180099e96  test    rax, rax
0x180099e99  jz      short loc_180099EAB
0x180099e9b  lea     rdx, aGetnetworkstat_1; "GetNetworkStatus: network status is Slo"...
0x180099ea2  mov     ecx, edi
0x180099ea4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180099ea9  jmp     short loc_180099ECB
0x180099eab  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r13; void * g_lpDebugMsgContextInstance
0x180099eb2  jz      short loc_180099ECB
0x180099eb4  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r13; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x180099ebb  jz      short loc_180099ECB
0x180099ebd  lea     rdx, aGetnetworkstat_1; "GetNetworkStatus: network status is Slo"...
0x180099ec4  mov     ecx, edi; unsigned int
0x180099ec6  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x180099ecb  lea     rcx, ?g_StatusCallbackCS@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180099ed2  call    cs:__imp_EnterCriticalSection
0x180099ed8  mov     dword ptr [r14+138h], 1
0x180099ee3  mov     qword ptr [rbp+Context+8], r13
0x180099ee7  lea     rcx, ?g_StatusCallbackCS@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180099eee  call    cs:__imp_LeaveCriticalSection
0x180099ef4  nop
0x180099ef5  lea     rcx, [rbp+var_48]
0x180099ef9  call    ??1?$XPtrLF@U_NOTIFYCONTEXT@@@@QEAA@XZ; XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>(void)
0x180099efe  nop
0x180099eff  mov     ecx, ebx; dwErrCode
0x180099f01  call    cs:__imp_SetLastError
0x180099f07  nop
0x180099f08  lea     rcx, [rbp+var_48+8]; this
0x180099f0c  call    ??1XHandle@@QEAA@XZ; XHandle::~XHandle(void)
0x180099f11  mov     eax, esi
0x180099f13  add     rsp, 68h
0x180099f17  pop     r15
0x180099f19  pop     r14
0x180099f1b  pop     r13
0x180099f1d  pop     r12
0x180099f1f  pop     rdi
0x180099f20  pop     rsi
0x180099f21  pop     rbx
0x180099f22  pop     rbp
0x180099f23  retn
```
