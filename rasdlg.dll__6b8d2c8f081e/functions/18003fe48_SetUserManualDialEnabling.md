# SetUserManualDialEnabling

- ea: `0x18003fe48`
- end: `0x18003ff4a`
- name: `SetUserManualDialEnabling`
- size: `258`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800290c0`

## callees

- `0x18003fe48`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003feec`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003feec`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003ff30`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003ff30`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003ff23`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003ff23`
- `rtutils!TracePrintfExA` at `0x18003fe84`
- `rtutils!TracePrintfExA` at `0x18003fe84`

## pseudocode

```c
LSTATUS __fastcall SetUserManualDialEnabling(int a1, int a2)
{
  const WCHAR *v4; // rdx
  __int64 v5; // rcx
  LSTATUS result; // eax
  LSTATUS v7; // ebx
  DWORD dwDisposition; // [rsp+68h] [rbp+10h] BYREF
  BOOL Data; // [rsp+70h] [rbp+18h] BYREF
  HKEY hKey; // [rsp+78h] [rbp+20h] BYREF

  dwDisposition = 0;
  hKey = 0;
  if ( g_dwTraceId != -1 )
    TracePrintfExA(g_dwTraceId, 0xCu, "SetUserManualDialEnabling (en=%d) (m=%d)", a1, a2);
  if ( a2 )
  {
    if ( a2 != 1 )
      return 87;
    v4 = L".DEFAULT\\Software\\Microsoft\\RAS Logon Phonebook";
    v5 = -2147483645;
  }
  else
  {
    v4 = L"Software\\Microsoft\\RAS Phonebook";
    v5 = -2147483647;
  }
  result = RegCreateKeyExW((HKEY)v5, v4, 0, (LPWSTR)&WideCharStr, 0, 0x20006u, 0, &hKey, &dwDisposition);
  if ( !result )
  {
    Data = a1 != 0;
    v7 = RegSetValueExW(hKey, L"OperatorDial", 0, 4u, (const BYTE *)&Data, 4u);
    RegCloseKey(hKey);
    return v7;
  }
  return result;
}

```

## disassembly

```asm
0x18003fe48  mov     rax, rsp
0x18003fe4b  mov     [rax+8], rbx
0x18003fe4f  push    rdi
0x18003fe50  sub     rsp, 50h
0x18003fe54  mov     edi, ecx
0x18003fe56  mov     dword ptr [rax+10h], 0
0x18003fe5d  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18003fe63  mov     ebx, edx
0x18003fe65  mov     qword ptr [rax+20h], 0
0x18003fe6d  cmp     ecx, 0FFFFFFFFh
0x18003fe70  jz      short loc_18003FE8A
0x18003fe72  mov     [rax-38h], edx
0x18003fe75  lea     r8, aSetusermanuald; "SetUserManualDialEnabling (en=%d) (m=%d"...
0x18003fe7c  mov     edx, 0Ch; dwFlags
0x18003fe81  mov     r9d, edi
0x18003fe84  call    cs:__imp_TracePrintfExA
0x18003fe8a  test    ebx, ebx
0x18003fe8c  jnz     short loc_18003FE9E
0x18003fe8e  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\RAS Phonebook"
0x18003fe95  mov     rcx, 0FFFFFFFF80000001h
0x18003fe9c  jmp     short loc_18003FEB5
0x18003fe9e  cmp     ebx, 1
0x18003fea1  jnz     loc_18003FF3A
0x18003fea7  lea     rdx, aDefaultSoftwar; ".DEFAULT\\Software\\Microsoft\\RAS Logo"...
0x18003feae  mov     rcx, 0FFFFFFFF80000003h; hKey
0x18003feb5  lea     rax, [rsp+58h+dwDisposition]
0x18003feba  xor     r8d, r8d; Reserved
0x18003febd  mov     [rsp+58h+lpdwDisposition], rax; lpdwDisposition
0x18003fec2  lea     r9, WideCharStr; lpClass
0x18003fec9  lea     rax, [rsp+58h+hKey]
0x18003fece  mov     [rsp+58h+phkResult], rax; phkResult
0x18003fed3  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18003fedc  mov     [rsp+58h+samDesired], 20006h; samDesired
0x18003fee4  mov     [rsp+58h+dwOptions], 0; dwOptions
0x18003feec  call    cs:__imp_RegCreateKeyExW
0x18003fef2  test    eax, eax
0x18003fef4  jnz     short loc_18003FF3F
0x18003fef6  mov     rcx, [rsp+58h+hKey]; hKey
0x18003fefb  lea     rdx, aOperatordial; "OperatorDial"
0x18003ff02  mov     r9d, 4; dwType
0x18003ff08  test    edi, edi
0x18003ff0a  mov     [rsp+58h+samDesired], r9d; cbData
0x18003ff0f  setnz   al
0x18003ff12  xor     r8d, r8d; Reserved
0x18003ff15  mov     [rsp+58h+Data], eax
0x18003ff19  lea     rax, [rsp+58h+Data]
0x18003ff1e  mov     qword ptr [rsp+58h+dwOptions], rax; lpData
0x18003ff23  call    cs:__imp_RegSetValueExW
0x18003ff29  mov     rcx, [rsp+58h+hKey]; hKey
0x18003ff2e  mov     ebx, eax
0x18003ff30  call    cs:__imp_RegCloseKey
0x18003ff36  mov     eax, ebx
0x18003ff38  jmp     short loc_18003FF3F
0x18003ff3a  mov     eax, 57h ; 'W'
0x18003ff3f  mov     rbx, [rsp+58h+arg_0]
0x18003ff44  add     rsp, 50h
0x18003ff48  pop     rdi
0x18003ff49  retn
```
