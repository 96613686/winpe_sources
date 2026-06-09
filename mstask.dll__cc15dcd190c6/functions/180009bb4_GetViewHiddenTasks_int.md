# GetViewHiddenTasks(int *)

- ea: `0x180009bb4`
- end: `0x180009c43`
- name: `?GetViewHiddenTasks@@YAJPEAH@Z`
- size: `143`
- prototype: `__int64 __fastcall(int *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180006550`

## callees

- `0x180009bb4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009c36`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009c36`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180009c2b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180009c2b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180009bf0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180009bf0`

## string_xrefs

- `0x180009be2`: `SOFTWARE\Microsoft\SchedulingAgent`
- `0x180009c12`: `ViewHiddenTasks`

## pseudocode

```c
__int64 __fastcall GetViewHiddenTasks(int *a1)
{
  int *cbData; // [rsp+40h] [rbp+8h] BYREF
  HKEY hKey; // [rsp+48h] [rbp+10h] BYREF

  cbData = a1;
  *(_DWORD *)&g_fViewHiddenTasks = 0;
  hKey = 0;
  RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\SchedulingAgent", 0, 0x20019u, &hKey);
  if ( hKey )
  {
    LODWORD(cbData) = 4;
    RegQueryValueExW(hKey, L"ViewHiddenTasks", 0, 0, &g_fViewHiddenTasks, (LPDWORD)&cbData);
    RegCloseKey(hKey);
  }
  return 0;
}

```

## disassembly

```asm
0x180009bb4  mov     r11, rsp
0x180009bb7  mov     [r11+8], rcx
0x180009bbb  sub     rsp, 38h
0x180009bbf  lea     rax, [r11+10h]
0x180009bc3  mov     cs:?g_fViewHiddenTasks@@3HA, 0; int g_fViewHiddenTasks
0x180009bcd  mov     r9d, 20019h; samDesired
0x180009bd3  mov     [r11-18h], rax
0x180009bd7  xor     r8d, r8d; ulOptions
0x180009bda  mov     qword ptr [r11+10h], 0
0x180009be2  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\SchedulingAgent"
0x180009be9  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180009bf0  call    cs:__imp_RegOpenKeyExW
0x180009bf6  mov     rcx, [rsp+38h+hKey]; hKey
0x180009bfb  test    rcx, rcx
0x180009bfe  jz      short loc_180009C3C
0x180009c00  lea     rax, [rsp+38h+cbData]
0x180009c05  mov     dword ptr [rsp+38h+cbData], 4
0x180009c0d  mov     [rsp+38h+lpcbData], rax; lpcbData
0x180009c12  lea     rdx, aViewhiddentask; "ViewHiddenTasks"
0x180009c19  lea     rax, ?g_fViewHiddenTasks@@3HA; int g_fViewHiddenTasks
0x180009c20  xor     r9d, r9d; lpType
0x180009c23  xor     r8d, r8d; lpReserved
0x180009c26  mov     [rsp+38h+lpData], rax; lpData
0x180009c2b  call    cs:__imp_RegQueryValueExW
0x180009c31  mov     rcx, [rsp+38h+hKey]; hKey
0x180009c36  call    cs:__imp_RegCloseKey
0x180009c3c  xor     eax, eax
0x180009c3e  add     rsp, 38h
0x180009c42  retn
```
