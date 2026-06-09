# EapHost::ECPManager::WaitBeforeNextSync(void)

- ea: `0x18001064c`
- end: `0x180010ef8`
- name: `?WaitBeforeNextSync@ECPManager@EapHost@@AEAAXXZ`
- size: `2220`
- prototype: `void __fastcall(EapHost::ECPManager *__hidden this)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18000f184`

## callees

- `0x180001f60`
- `0x18000a5ac`
- `0x18000bbd8`
- `0x18000c150`
- `0x18000c1a8`
- `0x18000c39c`
- `0x18000c40c`
- `0x18000ce54`
- `0x18000d338`
- `0x18000d4e8`
- `0x18000d534`
- `0x18001064c`
- `0x180010f18`
- `0x180014e74`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x1800109ed`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x1800109ed`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001074d`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180010aa8`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001074d`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180010aa8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010d29`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010d29`
- `ntdll!EtwEventEnabled` at `0x18001069a`
- `ntdll!EtwEventEnabled` at `0x1800107cf`
- `ntdll!EtwEventEnabled` at `0x180010887`
- `ntdll!EtwEventEnabled` at `0x180010929`
- `ntdll!EtwEventEnabled` at `0x180010a08`
- `ntdll!EtwEventEnabled` at `0x180010ae8`
- `ntdll!EtwEventEnabled` at `0x180010bbd`
- `ntdll!EtwEventEnabled` at `0x180010c3a`
- `ntdll!EtwEventEnabled` at `0x180010cb6`
- `ntdll!EtwEventEnabled` at `0x180010d3b`
- `ntdll!EtwEventEnabled` at `0x180010de2`
- `ntdll!EtwEventEnabled` at `0x180010e65`
- `ntdll!EtwEventEnabled` at `0x18001069a`
- `ntdll!EtwEventEnabled` at `0x1800107cf`
- `ntdll!EtwEventEnabled` at `0x180010887`
- `ntdll!EtwEventEnabled` at `0x180010929`
- `ntdll!EtwEventEnabled` at `0x180010a08`
- `ntdll!EtwEventEnabled` at `0x180010ae8`
- `ntdll!EtwEventEnabled` at `0x180010bbd`
- `ntdll!EtwEventEnabled` at `0x180010c3a`
- `ntdll!EtwEventEnabled` at `0x180010cb6`
- `ntdll!EtwEventEnabled` at `0x180010d3b`
- `ntdll!EtwEventEnabled` at `0x180010de2`
- `ntdll!EtwEventEnabled` at `0x180010e65`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x18001090f`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x18001090f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180010b7f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180010b7f`

## string_xrefs

- `0x180010862`: `SYSTEM\CurrentControlSet\Services\EapHost`
- `0x18001078a`: `SYSTEM\CurrentControlSet\Services\EapHost\ECP`
- `0x180010c44`: `Service shutdown detected during initial waiting.`
- `0x180010894`: `Failed to open eaphost reg key while trying to register for registry notification, %u`
- `0x180010def`: `Failed to open ECP reg key while trying to register for registry notification, %u`
- `0x180010937`: `Registry change notification set up successfully. Waiting max %u seconds for the notification ... `
- `0x180010a16`: `Got registry change notification, do additional wait of %u seconds`
- `0x180010cc0`: `Service shutdown detected while doing addition wait after got the registry change notification`
- `0x180010bc7`: `Service shutdown detected while waiting for registry notification`
- `0x180010d4c`: `Unexpected error while waiting for registry notification, wait result: %u, win error 0x%x`

## pseudocode

```c
void __fastcall EapHost::ECPManager::WaitBeforeNextSync(EapHost::ECPManager *this)
{
  int v2; // r8d
  int v3; // r9d
  __int64 v4; // rsi
  DWORD v5; // eax
  __int64 v6; // rdx
  unsigned int v7; // ebx
  __int64 v8; // rsi
  __int64 v9; // rdx
  int v10; // r8d
  int v11; // r9d
  __int64 v12; // rax
  _QWORD *v13; // rcx
  __int64 v14; // rdx
  int v15; // ebx
  int v16; // r8d
  int v17; // r9d
  __int64 v18; // rax
  DWORD v19; // r13d
  int v20; // r8d
  int v21; // r9d
  DWORD v22; // eax
  int v23; // r8d
  int v24; // r9d
  signed int LastError; // ebx
  char pExceptionObject; // [rsp+30h] [rbp-D0h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  int v28; // [rsp+40h] [rbp-C0h]
  _BYTE v29[8]; // [rsp+48h] [rbp-B8h] BYREF
  HANDLE hEvent; // [rsp+50h] [rbp-B0h]
  _BYTE v31[16]; // [rsp+58h] [rbp-A8h] BYREF
  char *v32; // [rsp+68h] [rbp-98h]
  int v33; // [rsp+70h] [rbp-90h]
  int v34; // [rsp+74h] [rbp-8Ch]
  HANDLE Handles[3]; // [rsp+78h] [rbp-88h] BYREF
  int v36; // [rsp+90h] [rbp-70h]
  int v37; // [rsp+94h] [rbp-6Ch]
  char v38[2048]; // [rsp+A0h] [rbp-60h] BYREF

  if ( *((_BYTE *)this + 24) )
  {
    if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugInfoEvent)
      && (int)StringCchPrintfA(v38, 0x800u, "Starting initial wait of %u seconds", *((_DWORD *)this + 12)) >= 0
      && Microsoft_Windows_EapHostEnableBits < 0 )
    {
      v4 = -1;
      do
        ++v4;
      while ( v38[v4] );
      Handles[2] = v38;
      v36 = v4 + 1;
      v37 = 0;
      McGenEventWrite_EtwEventWriteTransfer(
        (unsigned int)&eaphost_Context,
        (unsigned int)DebugInfoEvent,
        v2,
        v3,
        (__int64)Handles);
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        23,
        WPP_7b801e82f26e3453209b6da2f48854a6_Traceguids,
        *((unsigned int *)this + 12));
    *((_BYTE *)this + 24) = 0;
    v5 = WaitForSingleObject(*((HANDLE *)this + 2), 1000 * *((_DWORD *)this + 12));
    if ( v5 == -1 )
      SystemError::Throw(L"WaitForSingleObject");
    if ( v5 != 258 )
    {
      if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugInfoEvent)
        && (int)StringCchPrintfA(v38, 0x800u, "Service shutdown detected during initial waiting.") >= 0
        && Microsoft_Windows_EapHostEnableBits < 0 )
      {
        McTemplateU0s_EtwEventWriteTransfer(&eaphost_Context, DebugInfoEvent, v38);
      }
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, WPP_7b801e82f26e3453209b6da2f48854a6_Traceguids);
      throw (EapHost::ECPShutdownException *)&pExceptionObject;
    }
    return;
  }
  Event::Event((Event *)v29);
  hKey = 0;
  v28 = 1;
  v7 = RegistryKey::Open((__int64)&hKey, v6, L"SYSTEM\\CurrentControlSet\\Services\\EapHost\\ECP", 16);
  v8 = -1;
  if ( v7 == 1 )
  {
    if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugInfoEvent)
      && (int)StringCchPrintfA(v38, 0x800u, "ECP key does not exist. Monitor EapHost key instead") >= 0
      && Microsoft_Windows_EapHostEnableBits < 0 )
    {
      v12 = -1;
      do
        ++v12;
      while ( v38[v12] );
      v32 = v38;
      v33 = v12 + 1;
      v34 = 0;
      McGenEventWrite_EtwEventWriteTransfer(
        (unsigned int)&eaphost_Context,
        (unsigned int)DebugInfoEvent,
        v10,
        v11,
        (__int64)v31);
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, WPP_7b801e82f26e3453209b6da2f48854a6_Traceguids);
    v7 = RegistryKey::Open((__int64)&hKey, v9, L"SYSTEM\\CurrentControlSet\\Services\\EapHost", 16);
    if ( v7 )
    {
      if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugErrorEvent)
        && (int)StringCchPrintfA(
                  v38,
                  0x800u,
                  "Failed to open eaphost reg key while trying to register for registry notification, %u",
                  v7) >= 0
        && (byte_180020AC1 & 8) != 0 )
      {
        McTemplateU0s_EtwEventWriteTransfer(&eaphost_Context, DebugErrorEvent, v38);
      }
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v14 = 26;
LABEL_110:
        WPP_SF_d(v13[2], v14, WPP_7b801e82f26e3453209b6da2f48854a6_Traceguids, v7);
        goto LABEL_111;
      }
      goto LABEL_111;
    }
  }
  else if ( v7 )
  {
    if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugErrorEvent)
      && (int)StringCchPrintfA(
                v38,
                0x800u,
                "Failed to open ECP reg key while trying to register for registry notification, %u",
                v7) >= 0
      && (byte_180020AC1 & 8) != 0 )
    {
      McTemplateU0s_EtwEventWriteTransfer(&eaphost_Context, DebugErrorEvent, v38);
    }
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v14 = 27;
      goto LABEL_110;
    }
LABEL_111:
    SystemError::Throw<long>((__int64)&byte_180018CBC, 4317);
  }
  v15 = RegNotifyChangeKeyValue(hKey, 0, 1u, hEvent, 1);
  if ( v15 )
  {
    if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugErrorEvent)
      && (int)StringCchPrintfA(v38, 0x800u, "Failed RegNotifyChangeKeyValue, 0x%x", v15) >= 0
      && (byte_180020AC1 & 8) != 0 )
    {
      McTemplateU0s_EtwEventWriteTransfer(&eaphost_Context, DebugErrorEvent, v38);
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        28,
        WPP_7b801e82f26e3453209b6da2f48854a6_Traceguids,
        (unsigned int)v15);
    if ( v15 > 0 )
      v15 = (unsigned __int16)v15 | 0x80070000;
    SystemError::Throw<long>((__int64)&byte_180018CBC, v15);
  }
  if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugInfoEvent)
    && (int)StringCchPrintfA(
              v38,
              0x800u,
              "Registry change notification set up successfully. Waiting max %u seconds for the notification ... ",
              *((_DWORD *)this + 14)) >= 0
    && Microsoft_Windows_EapHostEnableBits < 0 )
  {
    v18 = -1;
    do
      ++v18;
    while ( v38[v18] );
    v32 = v38;
    v33 = v18 + 1;
    v34 = 0;
    McGenEventWrite_EtwEventWriteTransfer(
      (unsigned int)&eaphost_Context,
      (unsigned int)DebugInfoEvent,
      v16,
      v17,
      (__int64)v31);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      29,
      WPP_7b801e82f26e3453209b6da2f48854a6_Traceguids,
      *((unsigned int *)this + 14));
  Handles[0] = hEvent;
  Handles[1] = *((HANDLE *)this + 2);
  v19 = WaitForMultipleObjectsEx(2u, Handles, 0, 1000 * *((_DWORD *)this + 14), 0);
  if ( v19 )
  {
    if ( v19 == 1 )
    {
      if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugInfoEvent)
        && (int)StringCchPrintfA(v38, 0x800u, "Service shutdown detected while waiting for registry notification") >= 0
        && Microsoft_Windows_EapHostEnableBits < 0 )
      {
        McTemplateU0s_EtwEventWriteTransfer(&eaphost_Context, DebugInfoEvent, v38);
      }
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, WPP_7b801e82f26e3453209b6da2f48854a6_Traceguids);
      throw (EapHost::ECPShutdownException *)&pExceptionObject;
    }
    if ( v19 != 258 )
    {
      LastError = GetLastError();
      if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugInfoEvent)
        && (int)StringCchPrintfA(
                  v38,
                  0x800u,
                  "Unexpected error while waiting for registry notification, wait result: %u, win error 0x%x",
                  v19,
                  LastError) >= 0
        && Microsoft_Windows_EapHostEnableBits < 0 )
      {
        McTemplateU0s_EtwEventWriteTransfer(&eaphost_Context, DebugInfoEvent, v38);
      }
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_DD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          34,
          WPP_7b801e82f26e3453209b6da2f48854a6_Traceguids,
          v19,
          LastError);
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      SystemError::Throw<long>((__int64)&byte_180018CBC, LastError);
    }
    if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugInfoEvent)
      && (int)StringCchPrintfA(v38, 0x800u, "Scan interval passed") >= 0
      && Microsoft_Windows_EapHostEnableBits < 0 )
    {
      do
        ++v8;
      while ( v38[v8] );
      v32 = v38;
      v33 = v8 + 1;
      v34 = 0;
      McGenEventWrite_EtwEventWriteTransfer(
        (unsigned int)&eaphost_Context,
        (unsigned int)DebugInfoEvent,
        v23,
        v24,
        (__int64)v31);
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, WPP_7b801e82f26e3453209b6da2f48854a6_Traceguids);
  }
  else
  {
    if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugInfoEvent)
      && (int)StringCchPrintfA(
                v38,
                0x800u,
                "Got registry change notification, do additional wait of %u seconds",
                *((_DWORD *)this + 13)) >= 0
      && Microsoft_Windows_EapHostEnableBits < 0 )
    {
      do
        ++v8;
      while ( v38[v8] );
      v32 = v38;
      v33 = v8 + 1;
      v34 = 0;
      McGenEventWrite_EtwEventWriteTransfer(
        (unsigned int)&eaphost_Context,
        (unsigned int)DebugInfoEvent,
        v20,
        v21,
        (__int64)v31);
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        30,
        WPP_7b801e82f26e3453209b6da2f48854a6_Traceguids,
        *((unsigned int *)this + 13));
    v22 = WaitForSingleObject(*((HANDLE *)this + 2), 1000 * *((_DWORD *)this + 13));
    if ( v22 == -1 )
      SystemError::Throw(L"WaitForSingleObject");
    if ( v22 != 258 )
    {
      if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugInfoEvent)
        && (int)StringCchPrintfA(
                  v38,
                  0x800u,
                  "Service shutdown detected while doing addition wait after got the registry change notification") >= 0
        && Microsoft_Windows_EapHostEnableBits < 0 )
      {
        McTemplateU0s_EtwEventWriteTransfer(&eaphost_Context, DebugInfoEvent, v38);
      }
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, WPP_7b801e82f26e3453209b6da2f48854a6_Traceguids);
      throw (EapHost::ECPShutdownException *)&pExceptionObject;
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  ObjectHandle::~ObjectHandle((ObjectHandle *)v29);
}

```

## disassembly

```asm
0x18001064c  push    rbp
0x18001064e  push    rbx
0x18001064f  push    rsi
0x180010650  push    rdi
0x180010651  push    r12
0x180010653  push    r13
0x180010655  push    r14
0x180010657  push    r15
0x180010659  lea     rbp, [rsp-7B8h]
0x180010661  sub     rsp, 8B8h
0x180010668  mov     rax, cs:__security_cookie
0x18001066f  xor     rax, rsp
0x180010672  mov     [rbp+7F0h+var_50], rax
0x180010679  mov     r15, rcx
0x18001067c  xor     r13d, r13d
0x18001067f  cmp     [rcx+18h], r13b
0x180010683  jz      loc_18001076C
0x180010689  lea     rdi, DebugInfoEvent
0x180010690  mov     rdx, rdi
0x180010693  mov     rcx, cs:eaphost_Context
0x18001069a  call    cs:__imp_EtwEventEnabled
0x1800106a0  mov     ebx, 800h
0x1800106a5  test    al, al
0x1800106a7  jz      short loc_180010708
0x1800106a9  mov     r9d, [r15+30h]
0x1800106ad  lea     r8, aStartingInitia; "Starting initial wait of %u seconds"
0x1800106b4  mov     edx, ebx; unsigned __int64
0x1800106b6  lea     rcx, [rbp+7F0h+var_850]; char *
0x1800106ba  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x1800106bf  test    eax, eax
0x1800106c1  js      short loc_180010708
0x1800106c3  test    cs:Microsoft_Windows_EapHostEnableBits, 80h
0x1800106ca  jz      short loc_180010708
0x1800106cc  lea     rax, [rbp+7F0h+var_850]
0x1800106d0  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800106d4  inc     rsi
0x1800106d7  cmp     [rax+rsi], r13b
0x1800106db  jnz     short loc_1800106D4
0x1800106dd  lea     eax, [rsi+1]
0x1800106e0  lea     rcx, [rbp+7F0h+var_850]
0x1800106e4  mov     [rbp+7F0h+var_868], rcx
0x1800106e8  mov     [rbp+7F0h+var_860], eax
0x1800106eb  mov     [rbp+7F0h+var_85C], r13d
0x1800106ef  lea     rax, [rsp+8F0h+Handles]
0x1800106f4  mov     qword ptr [rsp+8F0h+fAsynchronous], rax
0x1800106f9  mov     rdx, rdi
0x1800106fc  lea     rcx, eaphost_Context
0x180010703  call    McGenEventWrite_EtwEventWriteTransfer
0x180010708  lea     r14, WPP_GLOBAL_Control
0x18001070f  lea     r12, WPP_7b801e82f26e3453209b6da2f48854a6_Traceguids
0x180010716  mov     rcx, cs:WPP_GLOBAL_Control
0x18001071d  cmp     rcx, r14
0x180010720  jz      short loc_18001073D
0x180010722  test    byte ptr [rcx+1Ch], 4
0x180010726  jz      short loc_18001073D
0x180010728  mov     edx, 17h
0x18001072d  mov     r9d, [r15+30h]
0x180010731  mov     r8, r12
0x180010734  mov     rcx, [rcx+10h]
0x180010738  call    WPP_SF_d
0x18001073d  mov     [r15+18h], r13b
0x180010741  imul    edx, [r15+30h], 3E8h; dwMilliseconds
0x180010749  mov     rcx, [r15+10h]; hHandle
0x18001074d  call    cs:__imp_WaitForSingleObject
0x180010753  cmp     eax, 0FFFFFFFFh
0x180010756  jz      loc_180010DC7
0x18001075c  cmp     eax, 102h
0x180010761  jnz     loc_180010C30
0x180010767  jmp     loc_180010B90
0x18001076c  lea     rcx, [rsp+8F0h+var_8A8]; this
0x180010771  call    ??0Event@@QEAA@_N0@Z; Event::Event(bool,bool)
0x180010776  nop
0x180010777  mov     [rsp+8F0h+hKey], r13
0x18001077c  mov     [rsp+8F0h+var_8B0], 1
0x180010784  mov     r9d, 10h
0x18001078a  lea     r8, aSystemCurrentc_1; "SYSTEM\\CurrentControlSet\\Services\\Ea"...
0x180010791  lea     rcx, [rsp+8F0h+hKey]
0x180010796  call    ?Open@RegistryKey@@QEAA?AW4ResultType@ResultValue@1@PEAUHKEY__@@PEB_WK@Z; RegistryKey::Open(HKEY__ *,wchar_t const *,ulong)
0x18001079b  mov     ebx, eax
0x18001079d  lea     rdi, DebugInfoEvent
0x1800107a4  mov     r13d, 800h
0x1800107aa  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800107ae  lea     r14, WPP_GLOBAL_Control
0x1800107b5  lea     r12, WPP_7b801e82f26e3453209b6da2f48854a6_Traceguids
0x1800107bc  cmp     eax, 1
0x1800107bf  jnz     loc_1800108EF
0x1800107c5  mov     rdx, rdi
0x1800107c8  mov     rcx, cs:eaphost_Context
0x1800107cf  call    cs:__imp_EtwEventEnabled
0x1800107d5  test    al, al
0x1800107d7  jz      short loc_180010839
0x1800107d9  lea     r8, aEcpKeyDoesNotE; "ECP key does not exist. Monitor EapHost"...
0x1800107e0  mov     edx, r13d; unsigned __int64
0x1800107e3  lea     rcx, [rbp+7F0h+var_850]; char *
0x1800107e7  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x1800107ec  test    eax, eax
0x1800107ee  js      short loc_180010839
0x1800107f0  test    cs:Microsoft_Windows_EapHostEnableBits, 80h
0x1800107f7  jz      short loc_180010839
0x1800107f9  lea     rcx, [rbp+7F0h+var_850]
0x1800107fd  mov     rax, rsi
0x180010800  inc     rax
0x180010803  cmp     byte ptr [rcx+rax], 0
0x180010807  jnz     short loc_180010800
0x180010809  inc     eax
0x18001080b  lea     rcx, [rbp+7F0h+var_850]
0x18001080f  mov     [rsp+8F0h+var_888], rcx
0x180010814  mov     [rsp+8F0h+var_880], eax
0x180010818  mov     [rsp+8F0h+var_87C], 0
0x180010820  lea     rax, [rsp+8F0h+var_898]
0x180010825  mov     qword ptr [rsp+8F0h+fAsynchronous], rax
0x18001082a  mov     rdx, rdi
0x18001082d  lea     rcx, eaphost_Context
0x180010834  call    McGenEventWrite_EtwEventWriteTransfer
0x180010839  mov     rcx, cs:WPP_GLOBAL_Control
0x180010840  cmp     rcx, r14
0x180010843  jz      short loc_18001085C
0x180010845  test    byte ptr [rcx+1Ch], 4
0x180010849  jz      short loc_18001085C
0x18001084b  mov     edx, 19h
0x180010850  mov     r8, r12
0x180010853  mov     rcx, [rcx+10h]
0x180010857  call    WPP_SF_
0x18001085c  mov     r9d, 10h
0x180010862  lea     r8, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Services\\Ea"...
0x180010869  lea     rcx, [rsp+8F0h+hKey]
0x18001086e  call    ?Open@RegistryKey@@QEAA?AW4ResultType@ResultValue@1@PEAUHKEY__@@PEB_WK@Z; RegistryKey::Open(HKEY__ *,wchar_t const *,ulong)
0x180010873  mov     ebx, eax
0x180010875  test    eax, eax
0x180010877  jz      short loc_1800108F7
0x180010879  lea     rdx, DebugErrorEvent
0x180010880  mov     rcx, cs:eaphost_Context
0x180010887  call    cs:__imp_EtwEventEnabled
0x18001088d  test    al, al
0x18001088f  jz      short loc_1800108CB
0x180010891  mov     r9d, ebx
0x180010894  lea     r8, aFailedToOpenEa; "Failed to open eaphost reg key while tr"...
0x18001089b  mov     rdx, r13; unsigned __int64
0x18001089e  lea     rcx, [rbp+7F0h+var_850]; char *
0x1800108a2  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x1800108a7  test    eax, eax
0x1800108a9  js      short loc_1800108CB
0x1800108ab  test    cs:byte_180020AC1, 8
0x1800108b2  jz      short loc_1800108CB
0x1800108b4  lea     r8, [rbp+7F0h+var_850]
0x1800108b8  lea     rdx, DebugErrorEvent
0x1800108bf  lea     rcx, eaphost_Context
0x1800108c6  call    McTemplateU0s_EtwEventWriteTransfer
0x1800108cb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800108d2  cmp     rcx, r14
0x1800108d5  jz      loc_180010E4C
0x1800108db  test    byte ptr [rcx+1Ch], 1
0x1800108df  jz      loc_180010E4C
0x1800108e5  mov     edx, 1Ah
0x1800108ea  jmp     loc_180010E3D
0x1800108ef  test    ebx, ebx
0x1800108f1  jnz     loc_180010DD4
0x1800108f7  mov     [rsp+8F0h+fAsynchronous], 1; fAsynchronous
0x1800108ff  mov     r9, [rsp+8F0h+hEvent]; hEvent
0x180010904  xor     edx, edx; bWatchSubtree
0x180010906  lea     r8d, [rdx+1]; dwNotifyFilter
0x18001090a  mov     rcx, [rsp+8F0h+hKey]; hKey
0x18001090f  call    cs:__imp_RegNotifyChangeKeyValue
0x180010915  mov     ebx, eax
0x180010917  mov     rcx, cs:eaphost_Context
0x18001091e  test    eax, eax
0x180010920  jnz     loc_180010E5E
0x180010926  mov     rdx, rdi
0x180010929  call    cs:__imp_EtwEventEnabled
0x18001092f  test    al, al
0x180010931  jz      short loc_180010997
0x180010933  mov     r9d, [r15+38h]
0x180010937  lea     r8, aRegistryChange; "Registry change notification set up suc"...
0x18001093e  mov     rdx, r13; unsigned __int64
0x180010941  lea     rcx, [rbp+7F0h+var_850]; char *
0x180010945  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x18001094a  test    eax, eax
0x18001094c  js      short loc_180010997
0x18001094e  test    cs:Microsoft_Windows_EapHostEnableBits, 80h
0x180010955  jz      short loc_180010997
0x180010957  lea     rcx, [rbp+7F0h+var_850]
0x18001095b  mov     rax, rsi
0x18001095e  inc     rax
0x180010961  cmp     byte ptr [rcx+rax], 0
0x180010965  jnz     short loc_18001095E
0x180010967  inc     eax
0x180010969  lea     rcx, [rbp+7F0h+var_850]
0x18001096d  mov     [rsp+8F0h+var_888], rcx
0x180010972  mov     [rsp+8F0h+var_880], eax
0x180010976  mov     [rsp+8F0h+var_87C], 0
0x18001097e  lea     rax, [rsp+8F0h+var_898]
0x180010983  mov     qword ptr [rsp+8F0h+fAsynchronous], rax
0x180010988  mov     rdx, rdi
0x18001098b  lea     rcx, eaphost_Context
0x180010992  call    McGenEventWrite_EtwEventWriteTransfer
0x180010997  mov     rcx, cs:WPP_GLOBAL_Control
0x18001099e  mov     bl, 4
0x1800109a0  cmp     rcx, r14
0x1800109a3  jz      short loc_1800109BF
0x1800109a5  test    [rcx+1Ch], bl
0x1800109a8  jz      short loc_1800109BF
0x1800109aa  mov     edx, 1Dh
0x1800109af  mov     r9d, [r15+38h]
0x1800109b3  mov     r8, r12
0x1800109b6  mov     rcx, [rcx+10h]
0x1800109ba  call    WPP_SF_d
0x1800109bf  mov     rax, [rsp+8F0h+hEvent]
0x1800109c4  mov     [rsp+8F0h+Handles], rax
0x1800109c9  mov     rax, [r15+10h]
0x1800109cd  mov     [rbp+7F0h+var_870], rax
0x1800109d1  imul    r9d, [r15+38h], 3E8h; dwMilliseconds
0x1800109d9  mov     [rsp+8F0h+fAsynchronous], 0; bAlertable
0x1800109e1  xor     r8d, r8d; bWaitAll
0x1800109e4  lea     rdx, [rsp+8F0h+Handles]; lpHandles
0x1800109e9  lea     ecx, [r8+2]; nCount
0x1800109ed  call    cs:__imp_WaitForMultipleObjectsEx
0x1800109f3  mov     r13d, eax
0x1800109f6  test    eax, eax
0x1800109f8  jnz     loc_180010AC7
0x1800109fe  mov     rdx, rdi
0x180010a01  mov     rcx, cs:eaphost_Context
0x180010a08  call    cs:__imp_EtwEventEnabled
0x180010a0e  test    al, al
0x180010a10  jz      short loc_180010A76
0x180010a12  mov     r9d, [r15+34h]
0x180010a16  lea     r8, aGotRegistryCha; "Got registry change notification, do ad"...
0x180010a1d  mov     edx, 800h; unsigned __int64
0x180010a22  lea     rcx, [rbp+7F0h+var_850]; char *
0x180010a26  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x180010a2b  test    eax, eax
0x180010a2d  js      short loc_180010A76
0x180010a2f  test    cs:Microsoft_Windows_EapHostEnableBits, 80h
0x180010a36  jz      short loc_180010A76
0x180010a38  lea     rax, [rbp+7F0h+var_850]
0x180010a3c  inc     rsi
0x180010a3f  cmp     byte ptr [rax+rsi], 0
0x180010a43  jnz     short loc_180010A3C
0x180010a45  lea     eax, [rsi+1]
0x180010a48  lea     rcx, [rbp+7F0h+var_850]
0x180010a4c  mov     [rsp+8F0h+var_888], rcx
0x180010a51  mov     [rsp+8F0h+var_880], eax
0x180010a55  mov     [rsp+8F0h+var_87C], 0
0x180010a5d  lea     rax, [rsp+8F0h+var_898]
0x180010a62  mov     qword ptr [rsp+8F0h+fAsynchronous], rax
0x180010a67  mov     rdx, rdi
0x180010a6a  lea     rcx, eaphost_Context
0x180010a71  call    McGenEventWrite_EtwEventWriteTransfer
0x180010a76  mov     rcx, cs:WPP_GLOBAL_Control
0x180010a7d  cmp     rcx, r14
0x180010a80  jz      short loc_180010A9C
0x180010a82  test    [rcx+1Ch], bl
0x180010a85  jz      short loc_180010A9C
0x180010a87  mov     edx, 1Eh
0x180010a8c  mov     r9d, [r15+34h]
0x180010a90  mov     r8, r12
0x180010a93  mov     rcx, [rcx+10h]
0x180010a97  call    WPP_SF_d
0x180010a9c  imul    edx, [r15+34h], 3E8h; dwMilliseconds
0x180010aa4  mov     rcx, [r15+10h]; hHandle
0x180010aa8  call    cs:__imp_WaitForSingleObject
0x180010aae  cmp     eax, 0FFFFFFFFh
0x180010ab1  jz      loc_180010EEB
0x180010ab7  cmp     eax, 102h
0x180010abc  jnz     loc_180010CAC
0x180010ac2  jmp     loc_180010B75
0x180010ac7  cmp     r13d, 1
0x180010acb  jz      loc_180010BB3
0x180010ad1  cmp     r13d, 102h
0x180010ad8  jnz     loc_180010D29
0x180010ade  mov     rdx, rdi
0x180010ae1  mov     rcx, cs:eaphost_Context
0x180010ae8  call    cs:__imp_EtwEventEnabled
0x180010aee  test    al, al
0x180010af0  jz      short loc_180010B52
0x180010af2  lea     r8, aScanIntervalPa; "Scan interval passed"
0x180010af9  mov     edx, 800h; unsigned __int64
0x180010afe  lea     rcx, [rbp+7F0h+var_850]; char *
0x180010b02  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x180010b07  test    eax, eax
0x180010b09  js      short loc_180010B52
0x180010b0b  test    cs:Microsoft_Windows_EapHostEnableBits, 80h
0x180010b12  jz      short loc_180010B52
0x180010b14  lea     rax, [rbp+7F0h+var_850]
0x180010b18  inc     rsi
0x180010b1b  cmp     byte ptr [rax+rsi], 0
0x180010b1f  jnz     short loc_180010B18
0x180010b21  lea     eax, [rsi+1]
0x180010b24  lea     rcx, [rbp+7F0h+var_850]
0x180010b28  mov     [rsp+8F0h+var_888], rcx
0x180010b2d  mov     [rsp+8F0h+var_880], eax
0x180010b31  mov     [rsp+8F0h+var_87C], 0
0x180010b39  lea     rax, [rsp+8F0h+var_898]
0x180010b3e  mov     qword ptr [rsp+8F0h+fAsynchronous], rax
0x180010b43  mov     rdx, rdi
0x180010b46  lea     rcx, eaphost_Context
0x180010b4d  call    McGenEventWrite_EtwEventWriteTransfer
0x180010b52  mov     rcx, cs:WPP_GLOBAL_Control
0x180010b59  cmp     rcx, r14
0x180010b5c  jz      short loc_180010B75
0x180010b5e  test    [rcx+1Ch], bl
  ... truncated ...
```
