# RegUtil::GetHotpatchAutoRemediationSettings(ulong *)

- ea: `0x18000d3ec`
- end: `0x18000d4ad`
- name: `?GetHotpatchAutoRemediationSettings@RegUtil@@SAJPEAK@Z`
- size: `193`
- prototype: `__int64 __fastcall(unsigned int *)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x180007400`
- `0x18000ed44`

## callees

- `0x18000d3ec`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000d472`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000d472`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000d490`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000d490`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000d431`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000d431`

## pseudocode

```c
__int64 __fastcall RegUtil::GetHotpatchAutoRemediationSettings(unsigned int *a1)
{
  LSTATUS v2; // eax
  signed int v3; // ebx
  LSTATUS v4; // eax
  unsigned int Data; // [rsp+48h] [rbp+10h] BYREF
  DWORD cbData; // [rsp+50h] [rbp+18h] BYREF
  HKEY hKey; // [rsp+58h] [rbp+20h] BYREF

  Data = 0;
  hKey = 0;
  cbData = 4;
  v2 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, RegUtil::SERVICE_KEY, 0, 0x20019u, &hKey);
  v3 = v2;
  if ( v2 )
  {
    if ( v2 > 0 )
      v3 = (unsigned __int16)v2 | 0x80070000;
  }
  else
  {
    v3 = 0;
    v4 = RegQueryValueExW(hKey, RegUtil::HOTPATCH_SERVICE_ERRORCONFIG_VALUE_NAME, 0, 0, (LPBYTE)&Data, &cbData);
    if ( v4 )
    {
      if ( v4 > 0 )
        v3 = (unsigned __int16)v4 | 0x80070000;
      else
        v3 = v4;
    }
    RegCloseKey(hKey);
  }
  if ( v3 >= 0 )
    *a1 = Data;
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18000d3ec  mov     rax, rsp
0x18000d3ef  mov     [rax+8], rbx
0x18000d3f3  push    rdi
0x18000d3f4  sub     rsp, 30h
0x18000d3f8  mov     rdx, cs:?SERVICE_KEY@RegUtil@@0QEBGEB; lpSubKey
0x18000d3ff  mov     rdi, rcx
0x18000d402  mov     dword ptr [rax+10h], 0
0x18000d409  mov     r9d, 20019h; samDesired
0x18000d40f  mov     qword ptr [rax+20h], 0
0x18000d417  xor     r8d, r8d; ulOptions
0x18000d41a  mov     dword ptr [rax+18h], 4
0x18000d421  lea     rax, [rax+20h]
0x18000d425  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000d42c  mov     [rsp+38h+phkResult], rax; phkResult
0x18000d431  call    cs:__imp_RegOpenKeyExW
0x18000d437  mov     ebx, eax
0x18000d439  test    eax, eax
0x18000d43b  jz      short loc_18000D44A
0x18000d43d  jle     short loc_18000D496
0x18000d43f  movzx   ebx, ax
0x18000d442  or      ebx, 80070000h
0x18000d448  jmp     short loc_18000D496
0x18000d44a  mov     rdx, cs:?HOTPATCH_SERVICE_ERRORCONFIG_VALUE_NAME@RegUtil@@0QEBGEB; lpValueName
0x18000d451  lea     rax, [rsp+38h+cbData]
0x18000d456  mov     rcx, [rsp+38h+hKey]; hKey
0x18000d45b  xor     r9d, r9d; lpType
0x18000d45e  mov     [rsp+38h+lpcbData], rax; lpcbData
0x18000d463  xor     r8d, r8d; lpReserved
0x18000d466  lea     rax, [rsp+38h+Data]
0x18000d46b  xor     ebx, ebx
0x18000d46d  mov     [rsp+38h+phkResult], rax; lpData
0x18000d472  call    cs:__imp_RegQueryValueExW
0x18000d478  test    eax, eax
0x18000d47a  jz      short loc_18000D48B
0x18000d47c  jg      short loc_18000D482
0x18000d47e  mov     ebx, eax
0x18000d480  jmp     short loc_18000D48B
0x18000d482  movzx   ebx, ax
0x18000d485  or      ebx, 80070000h
0x18000d48b  mov     rcx, [rsp+38h+hKey]; hKey
0x18000d490  call    cs:__imp_RegCloseKey
0x18000d496  test    ebx, ebx
0x18000d498  js      short loc_18000D4A0
0x18000d49a  mov     ecx, [rsp+38h+Data]
0x18000d49e  mov     [rdi], ecx
0x18000d4a0  mov     eax, ebx
0x18000d4a2  mov     rbx, [rsp+38h+arg_0]
0x18000d4a7  add     rsp, 30h
0x18000d4ab  pop     rdi
0x18000d4ac  retn
```
