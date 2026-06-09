# SyncNode(HKEY__ *,HKEY__ *)

- ea: `0x180051478`
- end: `0x180051623`
- name: `?SyncNode@@YAXPEAUHKEY__@@0@Z`
- size: `427`
- prototype: `void __fastcall(HKEY, HKEY)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1800513e8`
- `0x180051478`

## callees

- `0x180051478`
- `0x180081dd0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005158c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005158c`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180051547`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180051547`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800514f9`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800514f9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800515c1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800515cc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800515c1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800515cc`
- `ADVAPI32!RegCreateKeyW` at `0x1800515a3`
- `ADVAPI32!RegCreateKeyW` at `0x1800515a3`
- `ADVAPI32!RegEnumKeyW` at `0x1800515f3`
- `ADVAPI32!RegEnumKeyW` at `0x1800515f3`

## pseudocode

```c
void __fastcall SyncNode(HKEY a1, HKEY a2)
{
  DWORD v2; // edi
  HKEY v4; // rbx
  DWORD v5; // edx
  DWORD v6; // edi
  DWORD v7; // edx
  DWORD v8; // r9d
  DWORD cchValueName; // [rsp+40h] [rbp-C0h] BYREF
  DWORD cbData; // [rsp+44h] [rbp-BCh] BYREF
  DWORD dwType; // [rsp+48h] [rbp-B8h] BYREF
  HKEY phkResult; // [rsp+50h] [rbp-B0h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR Data[264]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR ValueName[264]; // [rsp+270h] [rbp+170h] BYREF

  v2 = 0;
  dwType = 0;
  v4 = a1;
  v5 = 0;
  while ( 1 )
  {
    cchValueName = 260;
    cbData = 520;
    if ( RegEnumValueW(a1, v5, ValueName, &cchValueName, 0, &dwType, (LPBYTE)Data, &cbData) )
      break;
    ++v2;
    RegSetValueExW(a2, ValueName, 0, dwType, (const BYTE *)Data, cbData);
    v5 = v2;
    a1 = v4;
  }
  v6 = 0;
  cchValueName = 260;
  phkResult = 0;
  v7 = 0;
  hKey = 0;
  v8 = 260;
  while ( !RegEnumKeyW(v4, v7, Data, v8) )
  {
    ++v6;
    if ( !RegOpenKeyExW(v4, Data, 0, 0xF003Fu, &phkResult) )
    {
      if ( !RegCreateKeyW(a2, Data, &hKey) )
      {
        SyncNode(phkResult, hKey);
        RegCloseKey(hKey);
      }
      RegCloseKey(phkResult);
    }
    v8 = cchValueName;
    v7 = v6;
    phkResult = 0;
    hKey = 0;
  }
}

```

## disassembly

```asm
0x180051478  mov     [rsp-8+arg_10], rbx
0x18005147d  push    rbp
0x18005147e  push    rsi
0x18005147f  push    rdi
0x180051480  lea     rbp, [rsp-390h]
0x180051488  sub     rsp, 490h
0x18005148f  mov     rax, cs:__security_cookie
0x180051496  xor     rax, rsp
0x180051499  mov     [rbp+3A0h+var_20], rax
0x1800514a0  xor     edi, edi
0x1800514a2  lea     rax, [rsp+4A0h+var_45C]
0x1800514a7  mov     [rsp+4A0h+lpcbData], rax
0x1800514ac  mov     rsi, rdx
0x1800514af  lea     rax, [rsp+4A0h+Data]
0x1800514b4  mov     [rsp+4A0h+dwType], edi
0x1800514b8  mov     [rsp+4A0h+var_470], rax
0x1800514bd  mov     rbx, rcx
0x1800514c0  lea     rax, [rsp+4A0h+dwType]
0x1800514c5  xor     edx, edx
0x1800514c7  mov     qword ptr [rsp+4A0h+cbData], rax
0x1800514cc  mov     [rsp+4A0h+lpData], rdi
0x1800514d1  jmp     short loc_18005152B
0x1800514d3  mov     eax, [rsp+4A0h+var_45C]
0x1800514d7  lea     rdx, [rbp+3A0h+ValueName]; lpValueName
0x1800514de  mov     r9d, [rsp+4A0h+dwType]; dwType
0x1800514e3  inc     edi
0x1800514e5  mov     [rsp+4A0h+cbData], eax; cbData
0x1800514e9  xor     r8d, r8d; Reserved
0x1800514ec  lea     rax, [rsp+4A0h+Data]
0x1800514f1  mov     rcx, rsi; hKey
0x1800514f4  mov     [rsp+4A0h+lpData], rax; lpData
0x1800514f9  call    cs:__imp_RegSetValueExW
0x1800514ff  lea     rax, [rsp+4A0h+var_45C]
0x180051504  mov     edx, edi; dwIndex
0x180051506  mov     [rsp+4A0h+lpcbData], rax; lpcbData
0x18005150b  mov     rcx, rbx; hKey
0x18005150e  lea     rax, [rsp+4A0h+Data]
0x180051513  mov     [rsp+4A0h+var_470], rax; lpData
0x180051518  lea     rax, [rsp+4A0h+dwType]
0x18005151d  mov     qword ptr [rsp+4A0h+cbData], rax; lpType
0x180051522  mov     [rsp+4A0h+lpData], 0; lpReserved
0x18005152b  lea     r9, [rsp+4A0h+cchValueName]; lpcchValueName
0x180051530  mov     [rsp+4A0h+cchValueName], 104h
0x180051538  lea     r8, [rbp+3A0h+ValueName]; lpValueName
0x18005153f  mov     [rsp+4A0h+var_45C], 208h
0x180051547  call    cs:__imp_RegEnumValueW
0x18005154d  test    eax, eax
0x18005154f  jz      short loc_1800514D3
0x180051551  xor     edi, edi
0x180051553  mov     [rsp+4A0h+cchValueName], 104h
0x18005155b  mov     [rsp+4A0h+phkResult], rdi
0x180051560  xor     edx, edx
0x180051562  mov     [rsp+4A0h+hKey], rdi
0x180051567  mov     r9d, 104h
0x18005156d  jmp     short loc_1800515EB
0x18005156f  lea     rax, [rsp+4A0h+phkResult]
0x180051574  mov     r9d, 0F003Fh; samDesired
0x18005157a  xor     r8d, r8d; ulOptions
0x18005157d  mov     [rsp+4A0h+lpData], rax; phkResult
0x180051582  lea     rdx, [rsp+4A0h+Data]; lpSubKey
0x180051587  mov     rcx, rbx; hKey
0x18005158a  inc     edi
0x18005158c  call    cs:__imp_RegOpenKeyExW
0x180051592  test    eax, eax
0x180051594  jnz     short loc_1800515D2
0x180051596  lea     r8, [rsp+4A0h+hKey]; phkResult
0x18005159b  mov     rcx, rsi; hKey
0x18005159e  lea     rdx, [rsp+4A0h+Data]; lpSubKey
0x1800515a3  call    cs:__imp_RegCreateKeyW
0x1800515a9  test    eax, eax
0x1800515ab  jnz     short loc_1800515C7
0x1800515ad  mov     rdx, [rsp+4A0h+hKey]; HKEY
0x1800515b2  mov     rcx, [rsp+4A0h+phkResult]; HKEY
0x1800515b7  call    ?SyncNode@@YAXPEAUHKEY__@@0@Z; SyncNode(HKEY__ *,HKEY__ *)
0x1800515bc  mov     rcx, [rsp+4A0h+hKey]; hKey
0x1800515c1  call    cs:__imp_RegCloseKey
0x1800515c7  mov     rcx, [rsp+4A0h+phkResult]; hKey
0x1800515cc  call    cs:__imp_RegCloseKey
0x1800515d2  mov     r9d, [rsp+4A0h+cchValueName]; cchName
0x1800515d7  mov     edx, edi; dwIndex
0x1800515d9  mov     [rsp+4A0h+phkResult], 0
0x1800515e2  mov     [rsp+4A0h+hKey], 0
0x1800515eb  lea     r8, [rsp+4A0h+Data]; lpName
0x1800515f0  mov     rcx, rbx; hKey
0x1800515f3  call    cs:__imp_RegEnumKeyW
0x1800515f9  test    eax, eax
0x1800515fb  jz      loc_18005156F
0x180051601  mov     rcx, [rbp+3A0h+var_20]
0x180051608  xor     rcx, rsp; StackCookie
0x18005160b  call    __security_check_cookie
0x180051610  mov     rbx, [rsp+4A0h+arg_10]
0x180051618  add     rsp, 490h
0x18005161f  pop     rdi
0x180051620  pop     rsi
0x180051621  pop     rbp
0x180051622  retn
```
