# CActiveXInstallBroker::UpdateSharedDlls(char const *)

- ea: `0x140007340`
- end: `0x140007475`
- name: `?UpdateSharedDlls@CActiveXInstallBroker@@AEAAJPEBD@Z`
- size: `309`
- prototype: `int(CActiveXInstallBroker *__hidden this, const char *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x140006fa4`

## callees

- `0x140007340`
- `0x14000d314`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x14000745e`
- `ADVAPI32!RegCloseKey` at `0x14000745e`
- `ADVAPI32!RegCreateKeyW` at `0x1400073c6`
- `ADVAPI32!RegCreateKeyW` at `0x1400073c6`
- `ADVAPI32!RegOpenKeyExW` at `0x1400073a7`
- `ADVAPI32!RegOpenKeyExW` at `0x1400073a7`
- `ADVAPI32!RegSetValueExA` at `0x140007436`
- `ADVAPI32!RegSetValueExA` at `0x140007436`
- `ADVAPI32!RegQueryValueExA` at `0x1400073f6`
- `ADVAPI32!RegQueryValueExA` at `0x1400073f6`

## string_xrefs

- `0x1400073a0`: `SOFTWARE\Microsoft\Windows\CurrentVersion\SharedDlls`
- `0x1400073bf`: `SOFTWARE\Microsoft\Windows\CurrentVersion\SharedDlls`

## pseudocode

```c
__int64 __fastcall CActiveXInstallBroker::UpdateSharedDlls(CActiveXInstallBroker *this, const char *a2)
{
  unsigned int RegistrationRootKeyFromIntegrityLevel; // ebx
  LSTATUS v4; // eax
  bool v5; // cc
  int v6; // eax
  HKEY phkResult; // [rsp+30h] [rbp-10h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-8h] BYREF
  int Data; // [rsp+60h] [rbp+20h] BYREF
  int v11; // [rsp+64h] [rbp+24h]
  DWORD cbData; // [rsp+70h] [rbp+30h] BYREF
  DWORD Type; // [rsp+78h] [rbp+38h] BYREF

  v11 = HIDWORD(this);
  hKey = 0;
  phkResult = 0;
  Type = 0;
  Data = 0;
  cbData = 4;
  RegistrationRootKeyFromIntegrityLevel = GetRegistrationRootKeyFromIntegrityLevel(&hKey);
  if ( !RegistrationRootKeyFromIntegrityLevel )
  {
    if ( RegOpenKeyExW(hKey, L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\SharedDlls", 0, 0x2001Fu, &phkResult)
      && (v4 = RegCreateKeyW(hKey, L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\SharedDlls", &phkResult),
          v5 = v4 <= 0,
          v4)
      || (RegQueryValueExA(phkResult, a2, 0, &Type, (LPBYTE)&Data, &cbData) ? (v6 = 1) : (v6 = Data + 1),
          Data = v6,
          v4 = RegSetValueExA(phkResult, a2, 0, 4u, (const BYTE *)&Data, 4u),
          v5 = v4 <= 0,
          v4) )
    {
      if ( v5 )
        RegistrationRootKeyFromIntegrityLevel = v4;
      else
        RegistrationRootKeyFromIntegrityLevel = (unsigned __int16)v4 | 0x80070000;
    }
  }
  if ( phkResult )
    RegCloseKey(phkResult);
  return RegistrationRootKeyFromIntegrityLevel;
}

```

## disassembly

```asm
0x140007340  mov     qword ptr [rsp-18h+Data], rcx
0x140007345  push    rbp
0x140007346  push    rbx
0x140007347  push    rdi
0x140007348  mov     rbp, rsp
0x14000734b  sub     rsp, 40h
0x14000734f  lea     rcx, [rbp+hKey]; HKEY *
0x140007353  mov     [rbp+hKey], 0
0x14000735b  mov     rdi, rdx
0x14000735e  mov     [rbp+var_10], 0
0x140007366  mov     [rbp+Type], 0
0x14000736d  mov     [rbp+Data], 0
0x140007374  mov     [rbp+cbData], 4
0x14000737b  call    ?GetRegistrationRootKeyFromIntegrityLevel@@YAJPEAPEAUHKEY__@@@Z; GetRegistrationRootKeyFromIntegrityLevel(HKEY__ * *)
0x140007380  mov     ebx, eax
0x140007382  test    eax, eax
0x140007384  jnz     loc_140007455
0x14000738a  mov     rcx, [rbp+hKey]; hKey
0x14000738e  lea     rax, [rbp+var_10]
0x140007392  mov     r9d, 2001Fh; samDesired
0x140007398  mov     [rsp+40h+phkResult], rax; phkResult
0x14000739d  xor     r8d, r8d; ulOptions
0x1400073a0  lea     rdx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1400073a7  call    cs:__imp_RegOpenKeyExW
0x1400073ae  nop     dword ptr [rax+rax+00h]
0x1400073b3  test    eax, eax
0x1400073b5  jz      short loc_1400073D6
0x1400073b7  mov     rcx, [rbp+hKey]; hKey
0x1400073bb  lea     r8, [rbp+var_10]; phkResult
0x1400073bf  lea     rdx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1400073c6  call    cs:__imp_RegCreateKeyW
0x1400073cd  nop     dword ptr [rax+rax+00h]
0x1400073d2  test    eax, eax
0x1400073d4  jnz     short loc_140007446
0x1400073d6  mov     rcx, [rbp+var_10]; hKey
0x1400073da  lea     rax, [rbp+cbData]
0x1400073de  mov     [rsp+40h+lpcbData], rax; lpcbData
0x1400073e3  lea     r9, [rbp+Type]; lpType
0x1400073e7  lea     rax, [rbp+Data]
0x1400073eb  xor     r8d, r8d; lpReserved
0x1400073ee  mov     rdx, rdi; lpValueName
0x1400073f1  mov     [rsp+40h+phkResult], rax; lpData
0x1400073f6  call    cs:__imp_RegQueryValueExA
0x1400073fd  nop     dword ptr [rax+rax+00h]
0x140007402  test    eax, eax
0x140007404  jnz     short loc_14000740D
0x140007406  mov     eax, [rbp+Data]
0x140007409  inc     eax
0x14000740b  jmp     short loc_140007412
0x14000740d  mov     eax, 1
0x140007412  mov     rcx, [rbp+var_10]; hKey
0x140007416  mov     r9d, 4; dwType
0x14000741c  mov     [rbp+Data], eax
0x14000741f  xor     r8d, r8d; Reserved
0x140007422  lea     rax, [rbp+Data]
0x140007426  mov     dword ptr [rsp+40h+lpcbData], 4; cbData
0x14000742e  mov     rdx, rdi; lpValueName
0x140007431  mov     [rsp+40h+phkResult], rax; lpData
0x140007436  call    cs:__imp_RegSetValueExA
0x14000743d  nop     dword ptr [rax+rax+00h]
0x140007442  test    eax, eax
0x140007444  jz      short loc_140007455
0x140007446  jg      short loc_14000744C
0x140007448  mov     ebx, eax
0x14000744a  jmp     short loc_140007455
0x14000744c  movzx   ebx, ax
0x14000744f  or      ebx, 80070000h
0x140007455  mov     rcx, [rbp+var_10]; hKey
0x140007459  test    rcx, rcx
0x14000745c  jz      short loc_14000746A
0x14000745e  call    cs:__imp_RegCloseKey
0x140007465  nop     dword ptr [rax+rax+00h]
0x14000746a  mov     eax, ebx
0x14000746c  add     rsp, 40h
0x140007470  pop     rdi
0x140007471  pop     rbx
0x140007472  pop     rbp
0x140007473  retn
```
