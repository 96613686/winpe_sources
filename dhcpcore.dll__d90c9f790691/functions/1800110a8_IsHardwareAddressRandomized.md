# IsHardwareAddressRandomized

- ea: `0x1800110a8`
- end: `0x180011222`
- name: `IsHardwareAddressRandomized`
- size: `378`
- prototype: `_BOOL8 __fastcall(_BYTE *, const WCHAR *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18001f148`

## callees

- `0x1800069d0`
- `0x1800110a8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011170`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001117a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001120c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011170`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001117a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001120c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800110fd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180011125`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800111bf`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800110fd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180011125`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800111bf`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001115b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800111f6`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001115b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800111f6`

## string_xrefs

- `0x180011197`: `System\CurrentControlSet\Services\Dhcp`

## pseudocode

```c
_BOOL8 __fastcall IsHardwareAddressRandomized(_BYTE *a1, const WCHAR *a2)
{
  BOOL v2; // ebx
  BOOL IsWCOSSystem; // eax
  const WCHAR *v5; // rdx
  HKEY hKey[2]; // [rsp+30h] [rbp-10h] BYREF
  int Data; // [rsp+68h] [rbp+28h] BYREF
  DWORD cbData; // [rsp+70h] [rbp+30h] BYREF
  HKEY phkResult; // [rsp+78h] [rbp+38h] BYREF

  v2 = 0;
  if ( a2 )
  {
    if ( a1 )
    {
      if ( (*a1 & 2) != 0 )
      {
        hKey[0] = 0;
        if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\WlanSvc\\Interfaces", 0, 1u, hKey) )
        {
          phkResult = 0;
          if ( !RegOpenKeyExW(hKey[0], a2, 0, 1u, &phkResult) )
          {
            Data = 0;
            cbData = 4;
            if ( !RegQueryValueExW(phkResult, L"RandomMacState", 0, 0, (LPBYTE)&Data, &cbData) )
              v2 = Data != 0;
            RegCloseKey(phkResult);
          }
          RegCloseKey(hKey[0]);
          if ( v2 )
          {
            hKey[0] = 0;
            IsWCOSSystem = DhcpIsWCOSSystem();
            v5 = L"OSDATA\\Networking\\Dhcp\\PDC";
            if ( !IsWCOSSystem )
              v5 = L"System\\CurrentControlSet\\Services\\Dhcp";
            if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, v5, 0, 1u, hKey) )
            {
              Data = 0;
              LODWORD(phkResult) = 0;
              cbData = 4;
              if ( !RegQueryValueExW(hKey[0], L"PrivacyDisabled", 0, (LPDWORD)&phkResult, (LPBYTE)&Data, &cbData)
                && Data )
              {
                v2 = 0;
              }
              RegCloseKey(hKey[0]);
            }
          }
        }
      }
    }
  }
  return v2;
}

```

## disassembly

```asm
0x1800110a8  mov     [rsp-18h+arg_0], rbx
0x1800110ad  push    rbp
0x1800110ae  push    rdi
0x1800110af  push    r14
0x1800110b1  mov     rbp, rsp
0x1800110b4  sub     rsp, 40h
0x1800110b8  xor     ebx, ebx
0x1800110ba  mov     rdi, rdx
0x1800110bd  test    rdx, rdx
0x1800110c0  jz      loc_180011212
0x1800110c6  test    rcx, rcx
0x1800110c9  jz      loc_180011212
0x1800110cf  test    byte ptr [rcx], 2
0x1800110d2  jz      loc_180011212
0x1800110d8  lea     rax, [rbp+hKey]
0x1800110dc  mov     [rbp+hKey], rbx
0x1800110e0  lea     r14d, [rbx+1]
0x1800110e4  mov     [rsp+40h+phkResult], rax; phkResult
0x1800110e9  mov     r9d, r14d; samDesired
0x1800110ec  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\WlanSvc\\Interface"...
0x1800110f3  xor     r8d, r8d; ulOptions
0x1800110f6  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800110fd  call    cs:__imp_RegOpenKeyExW
0x180011103  test    eax, eax
0x180011105  jnz     loc_180011212
0x18001110b  mov     rcx, [rbp+hKey]; hKey
0x18001110f  lea     rax, [rbp+arg_18]
0x180011113  mov     r9d, r14d; samDesired
0x180011116  mov     [rsp+40h+phkResult], rax; phkResult
0x18001111b  xor     r8d, r8d; ulOptions
0x18001111e  mov     [rbp+arg_18], rbx
0x180011122  mov     rdx, rdi; lpSubKey
0x180011125  call    cs:__imp_RegOpenKeyExW
0x18001112b  lea     edi, [rbx+4]
0x18001112e  test    eax, eax
0x180011130  jnz     short loc_180011176
0x180011132  mov     rcx, [rbp+arg_18]; hKey
0x180011136  lea     rax, [rbp+cbData]
0x18001113a  mov     [rsp+40h+lpcbData], rax; lpcbData
0x18001113f  lea     rdx, aRandommacstate; "RandomMacState"
0x180011146  lea     rax, [rbp+Data]
0x18001114a  mov     [rbp+Data], ebx
0x18001114d  xor     r9d, r9d; lpType
0x180011150  mov     [rsp+40h+phkResult], rax; lpData
0x180011155  xor     r8d, r8d; lpReserved
0x180011158  mov     [rbp+cbData], edi
0x18001115b  call    cs:__imp_RegQueryValueExW
0x180011161  test    eax, eax
0x180011163  jnz     short loc_18001116C
0x180011165  cmp     [rbp+Data], ebx
0x180011168  cmovnz  ebx, r14d
0x18001116c  mov     rcx, [rbp+arg_18]; hKey
0x180011170  call    cs:__imp_RegCloseKey
0x180011176  mov     rcx, [rbp+hKey]; hKey
0x18001117a  call    cs:__imp_RegCloseKey
0x180011180  test    ebx, ebx
0x180011182  jz      loc_180011212
0x180011188  mov     [rbp+hKey], 0
0x180011190  call    DhcpIsWCOSSystem
0x180011195  test    eax, eax
0x180011197  lea     r8, aSystemCurrentc_17; "System\\CurrentControlSet\\Services\\Dh"...
0x18001119e  lea     rax, [rbp+hKey]
0x1800111a2  mov     r9d, r14d; samDesired
0x1800111a5  lea     rdx, aOsdataNetworki_6; "OSDATA\\Networking\\Dhcp\\PDC"
0x1800111ac  mov     [rsp+40h+phkResult], rax; phkResult
0x1800111b1  cmovz   rdx, r8; lpSubKey
0x1800111b5  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800111bc  xor     r8d, r8d; ulOptions
0x1800111bf  call    cs:__imp_RegOpenKeyExW
0x1800111c5  test    eax, eax
0x1800111c7  jnz     short loc_180011212
0x1800111c9  mov     rcx, [rbp+hKey]; hKey
0x1800111cd  lea     r9, [rbp+arg_18]; lpType
0x1800111d1  mov     [rbp+Data], eax
0x1800111d4  lea     rdx, aPrivacydisable; "PrivacyDisabled"
0x1800111db  mov     dword ptr [rbp+arg_18], eax
0x1800111de  xor     r8d, r8d; lpReserved
0x1800111e1  lea     rax, [rbp+cbData]
0x1800111e5  mov     [rbp+cbData], edi
0x1800111e8  mov     [rsp+40h+lpcbData], rax; lpcbData
0x1800111ed  lea     rax, [rbp+Data]
0x1800111f1  mov     [rsp+40h+phkResult], rax; lpData
0x1800111f6  call    cs:__imp_RegQueryValueExW
0x1800111fc  test    eax, eax
0x1800111fe  jnz     short loc_180011208
0x180011200  xor     ecx, ecx
0x180011202  cmp     [rbp+Data], ecx
0x180011205  cmovnz  ebx, ecx
0x180011208  mov     rcx, [rbp+hKey]; hKey
0x18001120c  call    cs:__imp_RegCloseKey
0x180011212  mov     eax, ebx
0x180011214  mov     rbx, [rsp+40h+arg_0]
0x180011219  add     rsp, 40h
0x18001121d  pop     r14
0x18001121f  pop     rdi
0x180011220  pop     rbp
0x180011221  retn
```
