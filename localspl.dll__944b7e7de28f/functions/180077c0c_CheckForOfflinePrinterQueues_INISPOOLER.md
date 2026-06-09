# CheckForOfflinePrinterQueues(_INISPOOLER *)

- ea: `0x180077c0c`
- end: `0x180077e21`
- name: `?CheckForOfflinePrinterQueues@@YAHPEAU_INISPOOLER@@@Z`
- size: `533`
- prototype: `__int64 __fastcall(struct _INISPOOLER *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18007e088`

## callees

- `0x18003e984`
- `0x180046650`
- `0x180054638`
- `0x180077284`
- `0x180077c0c`
- `0x18007ef0c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180077d6b`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180077dd5`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180077d6b`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180077dd5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180077d35`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180077dbb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180077d35`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180077dbb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180077c8b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180077d01`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180077c8b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180077d01`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180077da8`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180077da8`

## string_xrefs

- `0x180077c56`: `Attempt to read the registry sub keys under OfflinePrinters one by one to check for offline printer queues`
- `0x180077de0`: `RegOpenKeyEx failed with %d when read the OfflinePrinters registry key`

## pseudocode

```c
_BOOL8 __fastcall CheckForOfflinePrinterQueues(struct _INISPOOLER *a1)
{
  unsigned int v2; // eax
  __int64 v3; // rbx
  DWORD v4; // edi
  LSTATUS i; // eax
  DWORD v6; // esi
  __int64 v7; // rcx
  DWORD cchName; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  HKEY phkResult; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR SubKey[264]; // [rsp+60h] [rbp-A0h] BYREF

  hKey = 0;
  phkResult = 0;
  cchName = 0;
  LocalSpoolerTelemetry::WriteDbgTraceInfo(
    "CheckForOfflinePrinterQueues",
    L"Attempt to read the registry sub keys under OfflinePrinters one by one to check for offline printer queues");
  v2 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Print\\OfflinePrinters",
         0,
         0x20019u,
         &hKey);
  LODWORD(v3) = v2;
  if ( v2 )
  {
    LocalSpoolerTelemetry::WriteDbgTraceWarning(
      "CheckForOfflinePrinterQueues",
      L"RegOpenKeyEx failed with %d when read the OfflinePrinters registry key",
      v2);
  }
  else
  {
    v4 = 0;
    cchName = 260;
    for ( i = RegEnumKeyExW(hKey, 0, SubKey, &cchName, 0, 0, 0, 0);
          !i;
          i = RegEnumKeyExW(hKey, v4, SubKey, &cchName, 0, 0, 0, 0) )
    {
      v6 = v4;
      LocalSpoolerTelemetry::WriteDbgTraceInfo("CheckForOfflinePrinterQueues", L"Found offline printer %ws", SubKey);
      cchName = 260;
      ++v4;
      if ( !RegOpenKeyExW(hKey, SubKey, 0, 0x20019u, &phkResult) )
      {
        v3 = (unsigned int)AddPrinterForOfflinePrinteQueue(phkResult, a1);
        LocalSpoolerTelemetry::WriteDbgTraceInfo(
          "CheckForOfflinePrinterQueues",
          L"AddPrinterForOfflinePrinteQueue returns: %d",
          v3);
        RegCloseKey(phkResult);
        if ( !(_DWORD)v3 || (_DWORD)v3 == 1802 || (_DWORD)v3 == -1 )
        {
          RegDeleteKeyExW(hKey, SubKey, 0, 0);
          v4 = v6;
        }
        else
        {
          LogOfflinePrinterInstallationError(v7, SubKey, (unsigned int)v3);
        }
      }
    }
    RegCloseKey(hKey);
    RegDeleteKeyExW(
      HKEY_LOCAL_MACHINE,
      L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Print\\OfflinePrinters",
      0,
      0);
  }
  return (_DWORD)v3 == 0;
}

```

## disassembly

```asm
0x180077c0c  mov     [rsp-8+arg_8], rbx
0x180077c11  mov     [rsp-8+arg_10], rsi
0x180077c16  push    rbp
0x180077c17  push    rdi
0x180077c18  push    r14
0x180077c1a  lea     rbp, [rsp-180h]
0x180077c22  sub     rsp, 280h
0x180077c29  mov     rax, cs:__security_cookie
0x180077c30  xor     rax, rsp
0x180077c33  mov     [rbp+190h+var_20], rax
0x180077c3a  mov     r14, rcx
0x180077c3d  mov     [rsp+290h+hKey], 0
0x180077c46  lea     rcx, aCheckforofflin; "CheckForOfflinePrinterQueues"
0x180077c4d  mov     [rsp+290h+var_240], 0
0x180077c56  lea     rdx, aAttemptToReadT; "Attempt to read the registry sub keys u"...
0x180077c5d  mov     [rsp+290h+cchName], 0
0x180077c65  call    ?WriteDbgTraceInfo@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180077c6a  lea     rax, [rsp+290h+hKey]
0x180077c6f  mov     r9d, 20019h; samDesired
0x180077c75  xor     r8d, r8d; ulOptions
0x180077c78  mov     [rsp+290h+phkResult], rax; phkResult
0x180077c7d  lea     rdx, aSoftwareMicros_12; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x180077c84  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180077c8b  call    cs:__imp_RegOpenKeyExW
0x180077c91  mov     ebx, eax
0x180077c93  test    eax, eax
0x180077c95  jnz     loc_180077DDD
0x180077c9b  xor     edi, edi
0x180077c9d  mov     [rsp+290h+cchName], 104h
0x180077ca5  mov     [rsp+290h+lpftLastWriteTime], rdi
0x180077caa  xor     edx, edx
0x180077cac  mov     [rsp+290h+lpcchClass], rdi
0x180077cb1  mov     [rsp+290h+lpClass], rdi
0x180077cb6  mov     [rsp+290h+phkResult], rdi
0x180077cbb  jmp     loc_180077D99
0x180077cc0  lea     r8, [rsp+290h+SubKey]
0x180077cc5  mov     esi, edi
0x180077cc7  lea     rdx, aFoundOfflinePr; "Found offline printer %ws"
0x180077cce  lea     rcx, aCheckforofflin; "CheckForOfflinePrinterQueues"
0x180077cd5  call    ?WriteDbgTraceInfo@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180077cda  mov     rcx, [rsp+290h+hKey]; hKey
0x180077cdf  lea     rax, [rsp+290h+var_240]
0x180077ce4  mov     r9d, 20019h; samDesired
0x180077cea  mov     [rsp+290h+phkResult], rax; phkResult
0x180077cef  xor     r8d, r8d; ulOptions
0x180077cf2  mov     [rsp+290h+cchName], 104h
0x180077cfa  lea     rdx, [rsp+290h+SubKey]; lpSubKey
0x180077cff  inc     edi
0x180077d01  call    cs:__imp_RegOpenKeyExW
0x180077d07  test    eax, eax
0x180077d09  jnz     short loc_180077D73
0x180077d0b  mov     rcx, [rsp+290h+var_240]; void *
0x180077d10  mov     rdx, r14; struct _INISPOOLER *
0x180077d13  call    ?AddPrinterForOfflinePrinteQueue@@YAKPEAXPEAU_INISPOOLER@@@Z; AddPrinterForOfflinePrinteQueue(void *,_INISPOOLER *)
0x180077d18  mov     r8d, eax
0x180077d1b  lea     rdx, aAddprinterforo_0; "AddPrinterForOfflinePrinteQueue returns"...
0x180077d22  lea     rcx, aCheckforofflin; "CheckForOfflinePrinterQueues"
0x180077d29  mov     ebx, eax
0x180077d2b  call    ?WriteDbgTraceInfo@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180077d30  mov     rcx, [rsp+290h+var_240]; hKey
0x180077d35  call    cs:__imp_RegCloseKey
0x180077d3b  test    ebx, ebx
0x180077d3d  jz      short loc_180077D5B
0x180077d3f  cmp     ebx, 70Ah
0x180077d45  jz      short loc_180077D5B
0x180077d47  cmp     ebx, 0FFFFFFFFh
0x180077d4a  jz      short loc_180077D5B
0x180077d4c  mov     r8d, ebx
0x180077d4f  lea     rdx, [rsp+290h+SubKey]
0x180077d54  call    LogOfflinePrinterInstallationError
0x180077d59  jmp     short loc_180077D73
0x180077d5b  mov     rcx, [rsp+290h+hKey]; hKey
0x180077d60  lea     rdx, [rsp+290h+SubKey]; lpSubKey
0x180077d65  xor     r9d, r9d; Reserved
0x180077d68  xor     r8d, r8d; samDesired
0x180077d6b  call    cs:__imp_RegDeleteKeyExW
0x180077d71  mov     edi, esi
0x180077d73  mov     [rsp+290h+lpftLastWriteTime], 0; lpftLastWriteTime
0x180077d7c  mov     edx, edi; dwIndex
0x180077d7e  mov     [rsp+290h+lpcchClass], 0; lpcchClass
0x180077d87  mov     [rsp+290h+lpClass], 0; lpClass
0x180077d90  mov     [rsp+290h+phkResult], 0; lpReserved
0x180077d99  mov     rcx, [rsp+290h+hKey]; hKey
0x180077d9e  lea     r9, [rsp+290h+cchName]; lpcchName
0x180077da3  lea     r8, [rsp+290h+SubKey]; lpName
0x180077da8  call    cs:__imp_RegEnumKeyExW
0x180077dae  test    eax, eax
0x180077db0  jz      loc_180077CC0
0x180077db6  mov     rcx, [rsp+290h+hKey]; hKey
0x180077dbb  call    cs:__imp_RegCloseKey
0x180077dc1  xor     r9d, r9d; Reserved
0x180077dc4  lea     rdx, aSoftwareMicros_12; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x180077dcb  xor     r8d, r8d; samDesired
0x180077dce  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180077dd5  call    cs:__imp_RegDeleteKeyExW
0x180077ddb  jmp     short loc_180077DF3
0x180077ddd  mov     r8d, eax
0x180077de0  lea     rdx, aRegopenkeyexFa; "RegOpenKeyEx failed with %d when read t"...
0x180077de7  lea     rcx, aCheckforofflin; "CheckForOfflinePrinterQueues"
0x180077dee  call    ?WriteDbgTraceWarning@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x180077df3  xor     eax, eax
0x180077df5  test    ebx, ebx
0x180077df7  setz    al
0x180077dfa  mov     rcx, [rbp+190h+var_20]
0x180077e01  xor     rcx, rsp; StackCookie
0x180077e04  call    __security_check_cookie
0x180077e09  lea     r11, [rsp+290h+var_10]
0x180077e11  mov     rbx, [r11+28h]
0x180077e15  mov     rsi, [r11+30h]
0x180077e19  mov     rsp, r11
0x180077e1c  pop     r14
0x180077e1e  pop     rdi
0x180077e1f  pop     rbp
0x180077e20  retn
```
