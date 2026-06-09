# SetH264EncodingParamsFromRegistry

- ea: `0x18008ce38`
- end: `0x18008cf22`
- name: `SetH264EncodingParamsFromRegistry`
- size: `234`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18008cbdc`

## callees

- `0x18008ce38`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18008ceb4`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18008cef8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18008ceb4`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18008cef8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008cf15`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008cf15`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18008ce75`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18008ce75`

## string_xrefs

- `0x18008ce6e`: `Software\Policies\Microsoft\Windows NT\Terminal Services\H264Encoding`

## pseudocode

```c
void __fastcall SetH264EncodingParamsFromRegistry(__int64 a1)
{
  DWORD Type; // [rsp+50h] [rbp+18h] BYREF
  int Data; // [rsp+58h] [rbp+20h] BYREF
  DWORD cbData; // [rsp+60h] [rbp+28h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+30h] BYREF

  if ( a1 )
  {
    hKey = 0;
    if ( !RegOpenKeyExW(
            HKEY_LOCAL_MACHINE,
            L"Software\\Policies\\Microsoft\\Windows NT\\Terminal Services\\H264Encoding",
            0,
            0x20019u,
            &hKey) )
    {
      Data = 0;
      Type = 0;
      cbData = 4;
      if ( !RegQueryValueExW(hKey, L"EnableQPSingleStep", 0, &Type, (LPBYTE)&Data, &cbData) && Type == 4 )
        *(_DWORD *)(a1 + 280) = Data;
      cbData = 4;
      if ( !RegQueryValueExW(hKey, L"VideoDetectorRectDisplayMode", 0, &Type, (LPBYTE)&Data, &cbData) && Type == 4 )
        *(_DWORD *)(a1 + 304) = Data;
      RegCloseKey(hKey);
    }
  }
}

```

## disassembly

```asm
0x18008ce38  test    rcx, rcx
0x18008ce3b  jz      locret_18008CF21
0x18008ce41  push    rbp
0x18008ce42  push    rbx
0x18008ce43  mov     rbp, rsp
0x18008ce46  sub     rsp, 38h
0x18008ce4a  mov     rbx, rcx
0x18008ce4d  mov     [rbp+hKey], 0
0x18008ce55  lea     rax, [rbp+hKey]
0x18008ce59  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18008ce60  mov     r9d, 20019h; samDesired
0x18008ce66  mov     [rsp+38h+phkResult], rax; phkResult
0x18008ce6b  xor     r8d, r8d; ulOptions
0x18008ce6e  lea     rdx, aSoftwarePolici_1; "Software\\Policies\\Microsoft\\Windows "...
0x18008ce75  call    cs:__imp_RegOpenKeyExW
0x18008ce7b  test    eax, eax
0x18008ce7d  jnz     loc_18008CF1B
0x18008ce83  mov     rcx, [rbp+hKey]; hKey
0x18008ce87  lea     r9, [rbp+Type]; lpType
0x18008ce8b  mov     [rbp+Data], eax
0x18008ce8e  lea     rdx, aEnableqpsingle; "EnableQPSingleStep"
0x18008ce95  mov     [rbp+Type], eax
0x18008ce98  xor     r8d, r8d; lpReserved
0x18008ce9b  lea     rax, [rbp+cbData]
0x18008ce9f  mov     [rbp+cbData], 4
0x18008cea6  mov     [rsp+38h+lpcbData], rax; lpcbData
0x18008ceab  lea     rax, [rbp+Data]
0x18008ceaf  mov     [rsp+38h+phkResult], rax; lpData
0x18008ceb4  call    cs:__imp_RegQueryValueExW
0x18008ceba  test    eax, eax
0x18008cebc  jnz     short loc_18008CECD
0x18008cebe  cmp     [rbp+Type], 4
0x18008cec2  jnz     short loc_18008CECD
0x18008cec4  mov     eax, [rbp+Data]
0x18008cec7  mov     [rbx+118h], eax
0x18008cecd  mov     rcx, [rbp+hKey]; hKey
0x18008ced1  lea     rax, [rbp+cbData]
0x18008ced5  mov     [rsp+38h+lpcbData], rax; lpcbData
0x18008ceda  lea     r9, [rbp+Type]; lpType
0x18008cede  lea     rax, [rbp+Data]
0x18008cee2  mov     [rbp+cbData], 4
0x18008cee9  xor     r8d, r8d; lpReserved
0x18008ceec  mov     [rsp+38h+phkResult], rax; lpData
0x18008cef1  lea     rdx, aVideodetectorr; "VideoDetectorRectDisplayMode"
0x18008cef8  call    cs:__imp_RegQueryValueExW
0x18008cefe  test    eax, eax
0x18008cf00  jnz     short loc_18008CF11
0x18008cf02  cmp     [rbp+Type], 4
0x18008cf06  jnz     short loc_18008CF11
0x18008cf08  mov     eax, [rbp+Data]
0x18008cf0b  mov     [rbx+130h], eax
0x18008cf11  mov     rcx, [rbp+hKey]; hKey
0x18008cf15  call    cs:__imp_RegCloseKey
0x18008cf1b  add     rsp, 38h
0x18008cf1f  pop     rbx
0x18008cf20  pop     rbp
0x18008cf21  retn
```
