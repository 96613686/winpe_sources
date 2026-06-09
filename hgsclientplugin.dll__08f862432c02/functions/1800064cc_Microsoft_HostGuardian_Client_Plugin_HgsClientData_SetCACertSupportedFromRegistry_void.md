# Microsoft::HostGuardian::Client::Plugin::HgsClientData::SetCACertSupportedFromRegistry(void)

- ea: `0x1800064cc`
- end: `0x1800065ba`
- name: `?SetCACertSupportedFromRegistry@HgsClientData@Plugin@Client@HostGuardian@Microsoft@@AEAAXXZ`
- size: `238`
- prototype: `void __fastcall(Microsoft::HostGuardian::Client::Plugin::HgsClientData *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180006060`

## callees

- `0x1800064cc`
- `0x1800069fc`
- `0x180006b00`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000650b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000650b`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180006569`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180006569`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800065a9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800065a9`

## string_xrefs

- `0x18000651c`: `Failed to call RegOpenKeyEx. Key: %ws. Error code:0X%08X`
- `0x180006587`: `Retrieves Registry Value %s : %d`

## pseudocode

```c
void __fastcall Microsoft::HostGuardian::Client::Plugin::HgsClientData::SetCACertSupportedFromRegistry(
        Microsoft::HostGuardian::Client::Plugin::HgsClientData *this)
{
  unsigned int ValueW; // eax
  const wchar_t *v3; // rdx
  wchar_t *v4; // rcx
  unsigned int pvData; // [rsp+58h] [rbp+18h] BYREF
  DWORD pcbData; // [rsp+60h] [rbp+20h] BYREF
  HKEY hkey; // [rsp+68h] [rbp+28h] BYREF

  pvData = 0;
  hkey = 0;
  ValueW = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\HgsClient", 0, 0x20019u, &hkey);
  if ( ValueW )
  {
    v3 = L"SOFTWARE\\Microsoft\\HgsClient";
    v4 = (wchar_t *)L"Failed to call RegOpenKeyEx. Key: %ws. Error code:0X%08X";
LABEL_3:
    Microsoft::HostGuardian::Client::Plugin::EventUtilities::TraceWarning(v4, v3, ValueW);
    *((_BYTE *)this + 128) = 0;
    goto LABEL_7;
  }
  pcbData = 4;
  ValueW = RegGetValueW(hkey, 0, L"LocalCACertSupported", 0x10u, 0, &pvData, &pcbData);
  v3 = L"LocalCACertSupported";
  if ( ValueW )
  {
    v4 = L"Failed to call RegGetValue. ValueName: %ws. Error code:0X%08X";
    goto LABEL_3;
  }
  Microsoft::HostGuardian::Client::Plugin::EventUtilities::TraceInfo(
    (wchar_t *)L"Retrieves Registry Value %s : %d",
    L"LocalCACertSupported",
    pvData);
  *((_BYTE *)this + 128) = pvData != 0;
LABEL_7:
  if ( hkey )
    RegCloseKey(hkey);
}

```

## disassembly

```asm
0x1800064cc  mov     [rsp-8+arg_0], rbx
0x1800064d1  push    rbp
0x1800064d2  mov     rbp, rsp
0x1800064d5  sub     rsp, 40h
0x1800064d9  mov     rbx, rcx
0x1800064dc  mov     [rbp+arg_8], 0
0x1800064e3  lea     rax, [rbp+hkey]
0x1800064e7  mov     [rbp+hkey], 0
0x1800064ef  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800064f6  mov     [rsp+40h+phkResult], rax; phkResult
0x1800064fb  mov     r9d, 20019h; samDesired
0x180006501  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\HgsClient"
0x180006508  xor     r8d, r8d; ulOptions
0x18000650b  call    cs:__imp_RegOpenKeyExW
0x180006511  test    eax, eax
0x180006513  jz      short loc_180006534
0x180006515  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\HgsClient"
0x18000651c  lea     rcx, aFailedToCallRe_1; "Failed to call RegOpenKeyEx. Key: %ws. "...
0x180006523  mov     r8d, eax
0x180006526  call    ?TraceWarning@EventUtilities@Plugin@Client@HostGuardian@Microsoft@@YAXPEB_WZZ; Microsoft::HostGuardian::Client::Plugin::EventUtilities::TraceWarning(wchar_t const *,...)
0x18000652b  mov     byte ptr [rbx+80h], 0
0x180006532  jmp     short loc_1800065A0
0x180006534  mov     rcx, [rbp+hkey]; hkey
0x180006538  lea     rax, [rbp+arg_10]
0x18000653c  mov     [rsp+40h+pcbData], rax; pcbData
0x180006541  lea     r8, aLocalcacertsup; "LocalCACertSupported"
0x180006548  lea     rax, [rbp+arg_8]
0x18000654c  mov     [rbp+arg_10], 4
0x180006553  mov     [rsp+40h+pvData], rax; pvData
0x180006558  mov     r9d, 10h; dwFlags
0x18000655e  xor     edx, edx; lpSubKey
0x180006560  mov     [rsp+40h+phkResult], 0; pdwType
0x180006569  call    cs:__imp_RegGetValueW
0x18000656f  lea     rdx, aLocalcacertsup; "LocalCACertSupported"
0x180006576  test    eax, eax
0x180006578  jz      short loc_180006583
0x18000657a  lea     rcx, aFailedToCallRe_0; "Failed to call RegGetValue. ValueName: "...
0x180006581  jmp     short loc_180006523
0x180006583  mov     r8d, [rbp+arg_8]
0x180006587  lea     rcx, aRetrievesRegis; "Retrieves Registry Value %s : %d"
0x18000658e  call    ?TraceInfo@EventUtilities@Plugin@Client@HostGuardian@Microsoft@@YAXPEB_WZZ; Microsoft::HostGuardian::Client::Plugin::EventUtilities::TraceInfo(wchar_t const *,...)
0x180006593  cmp     [rbp+arg_8], 0
0x180006597  setnz   al
0x18000659a  mov     [rbx+80h], al
0x1800065a0  mov     rcx, [rbp+hkey]; hKey
0x1800065a4  test    rcx, rcx
0x1800065a7  jz      short loc_1800065AF
0x1800065a9  call    cs:__imp_RegCloseKey
0x1800065af  mov     rbx, [rsp+40h+arg_0]
0x1800065b4  add     rsp, 40h
0x1800065b8  pop     rbp
0x1800065b9  retn
```
