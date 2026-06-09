# Microsoft::HostGuardian::Client::Plugin::RegistryUtilities::QueryRegistryKeyForQword(HKEY__ * const,wchar_t const *,wchar_t const *)

- ea: `0x1800087e0`
- end: `0x1800088c3`
- name: `?QueryRegistryKeyForQword@RegistryUtilities@Plugin@Client@HostGuardian@Microsoft@@YA_JQEAUHKEY__@@PEB_W1@Z`
- size: `227`
- prototype: `unsigned __int64 __fastcall(Microsoft::HostGuardian::Client::Plugin::RegistryUtilities *this, HKEY, const wchar_t *, const wchar_t *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800065c0`

## callees

- `0x180006b00`
- `0x1800087e0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180008890`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180008890`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180008829`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180008829`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008856`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008856`

## string_xrefs

- `0x18000883d`: `Failed to call RegOpenKeyEx. subKey: %ws. Error code:0X%08X`

## pseudocode

```c
unsigned __int64 __fastcall Microsoft::HostGuardian::Client::Plugin::RegistryUtilities::QueryRegistryKeyForQword(
        Microsoft::HostGuardian::Client::Plugin::RegistryUtilities *this,
        HKEY a2,
        const wchar_t *a3,
        const wchar_t *a4)
{
  unsigned int v5; // eax
  unsigned __int64 v6; // rbx
  unsigned int Value; // eax
  unsigned __int64 Data; // [rsp+40h] [rbp+10h] BYREF
  HKEY cbData; // [rsp+48h] [rbp+18h] BYREF
  HKEY hKey; // [rsp+58h] [rbp+28h] BYREF

  cbData = a2;
  Data = 0;
  hKey = 0;
  v5 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\HgsClient", 0, 0x20019u, &hKey);
  if ( v5 )
  {
    Microsoft::HostGuardian::Client::Plugin::EventUtilities::TraceWarning(
      (wchar_t *)L"Failed to call RegOpenKeyEx. subKey: %ws. Error code:0X%08X",
      L"SOFTWARE\\Microsoft\\HgsClient",
      v5);
LABEL_3:
    v6 = Data;
    goto LABEL_4;
  }
  LODWORD(cbData) = 8;
  Value = RegQueryValueExW(hKey, a3, 0, 0, (LPBYTE)&Data, (LPDWORD)&cbData);
  if ( !Value )
    goto LABEL_3;
  Microsoft::HostGuardian::Client::Plugin::EventUtilities::TraceWarning(
    (wchar_t *)L"Failed to call RegQueryValueEx. subKey: %ws. valueName: %ws. Error code:0X%08X",
    L"SOFTWARE\\Microsoft\\HgsClient",
    a3,
    Value);
  v6 = 0x8000000000000000uLL;
  Data = 0x8000000000000000uLL;
LABEL_4:
  if ( hKey )
    RegCloseKey(hKey);
  return v6;
}

```

## disassembly

```asm
0x1800087e0  mov     r11, rsp
0x1800087e3  mov     [r11+18h], rbx
0x1800087e7  mov     [r11+10h], rdx
0x1800087eb  mov     [r11+8], rcx
0x1800087ef  push    rbp
0x1800087f0  mov     rbp, rsp
0x1800087f3  sub     rsp, 30h
0x1800087f7  mov     rbx, r8
0x1800087fa  mov     [rbp+Data], 0
0x180008802  lea     rax, [rbp+hKey]
0x180008806  mov     [rbp+hKey], 0
0x18000880e  xor     r8d, r8d; ulOptions
0x180008811  mov     [r11-18h], rax
0x180008815  mov     r9d, 20019h; samDesired
0x18000881b  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\HgsClient"
0x180008822  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180008829  call    cs:__imp_RegOpenKeyExW
0x18000882f  test    eax, eax
0x180008831  jz      short loc_18000886A
0x180008833  mov     r8d, eax
0x180008836  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\HgsClient"
0x18000883d  lea     rcx, aFailedToCallRe; "Failed to call RegOpenKeyEx. subKey: %w"...
0x180008844  call    ?TraceWarning@EventUtilities@Plugin@Client@HostGuardian@Microsoft@@YAXPEB_WZZ; Microsoft::HostGuardian::Client::Plugin::EventUtilities::TraceWarning(wchar_t const *,...)
0x180008849  mov     rbx, [rbp+Data]
0x18000884d  mov     rcx, [rbp+hKey]; hKey
0x180008851  test    rcx, rcx
0x180008854  jz      short loc_18000885C
0x180008856  call    cs:__imp_RegCloseKey
0x18000885c  mov     rax, rbx
0x18000885f  mov     rbx, [rsp+30h+arg_10]
0x180008864  add     rsp, 30h
0x180008868  pop     rbp
0x180008869  retn
0x18000886a  mov     rcx, [rbp+hKey]; hKey
0x18000886e  lea     rax, [rbp+cbData]
0x180008872  mov     [rsp+30h+lpcbData], rax; lpcbData
0x180008877  xor     r9d, r9d; lpType
0x18000887a  lea     rax, [rbp+Data]
0x18000887e  mov     dword ptr [rbp+cbData], 8
0x180008885  xor     r8d, r8d; lpReserved
0x180008888  mov     [rsp+30h+lpData], rax; lpData
0x18000888d  mov     rdx, rbx; lpValueName
0x180008890  call    cs:__imp_RegQueryValueExW
0x180008896  test    eax, eax
0x180008898  jz      short loc_180008849
0x18000889a  mov     r9d, eax
0x18000889d  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\HgsClient"
0x1800088a4  mov     r8, rbx
0x1800088a7  lea     rcx, aFailedToCallRe_2; "Failed to call RegQueryValueEx. subKey:"...
0x1800088ae  call    ?TraceWarning@EventUtilities@Plugin@Client@HostGuardian@Microsoft@@YAXPEB_WZZ; Microsoft::HostGuardian::Client::Plugin::EventUtilities::TraceWarning(wchar_t const *,...)
0x1800088b3  mov     rbx, 8000000000000000h
0x1800088bd  mov     [rbp+Data], rbx
0x1800088c1  jmp     short loc_18000884D
```
