# ClatMgrRegisterRegistryChangeNotification

- ea: `0x18007cef4`
- end: `0x18007d0a5`
- name: `ClatMgrRegisterRegistryChangeNotification`
- size: `433`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task`

## callers

- `0x18007c660`

## callees

- `0x18000d7b0`
- `0x18007cef4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x18007d008`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x18007d008`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007d072`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007d072`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18007cf3e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18007cf3e`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18007cf81`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18007cf81`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007cf96`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007cfdd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007cf96`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007cfdd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007d03a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007d056`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007d03a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007d056`
- `api-ms-win-core-kernel32-legacy-l1-1-0!RegisterWaitForSingleObject` at `0x18007cfcd`
- `api-ms-win-core-kernel32-legacy-l1-1-0!RegisterWaitForSingleObject` at `0x18007cfcd`

## string_xrefs

- `0x18007cf5a`: `IPxlatCfgSvc registry root is not present.`
- `0x18007cf6b`: `Failed to open IPxlatCfgSvc registry root key. Status = %d`
- `0x18007cfa4`: `Failed to create Registry change notification event. Status = %d`
- `0x18007cfeb`: `Failed to associate registry change wait object. Status = %d`
- `0x18007d01a`: `Failed to register for registry change notification. Status = %d\n`
- `0x18007d087`: `Registry change notification registered successfully.`
- `0x18007cf22`: `System\CurrentControlSet\Services\IpxlatCfgSvc`

## pseudocode

```c
__int64 __fastcall ClatMgrRegisterRegistryChangeNotification(__int64 a1, __int64 a2)
{
  HKEY *v2; // rsi
  void **v3; // r14
  unsigned int v5; // eax
  DWORD LastError; // ebx
  HANDLE EventW; // rax
  const wchar_t *v8; // rdx
  void *v9; // rcx

  v2 = (HKEY *)(a2 + 240);
  *(_QWORD *)(a2 + 72) = 0;
  v3 = (void **)(a2 + 80);
  *(_QWORD *)(a2 + 240) = 0;
  *(_QWORD *)(a2 + 80) = 0;
  v5 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"System\\CurrentControlSet\\Services\\IpxlatCfgSvc",
         0,
         0x20019u,
         (PHKEY)(a2 + 240));
  LastError = v5;
  if ( !v5 )
  {
    EventW = CreateEventW(0, 0, 0, 0);
    *(_QWORD *)(a2 + 72) = EventW;
    if ( EventW )
    {
      if ( RegisterWaitForSingleObject(v3, EventW, ClatMgrRegKeyChangeCallback, (PVOID)a2, 0xFFFFFFFF, 0) )
      {
        LastError = RegNotifyChangeKeyValue(*v2, 1, 4u, *(HANDLE *)(a2 + 72), 1);
        if ( !LastError )
        {
          EventWrite0(0x4000000, L"Registry change notification registered successfully.");
          return LastError;
        }
        v8 = L"Failed to register for registry change notification. Status = %d\n";
      }
      else
      {
        LastError = GetLastError();
        v8 = L"Failed to associate registry change wait object. Status = %d";
      }
    }
    else
    {
      LastError = GetLastError();
      v8 = L"Failed to create Registry change notification event. Status = %d";
    }
    EventWrite0(0x4000000, v8, LastError);
LABEL_12:
    if ( !LastError )
      return LastError;
    goto LABEL_13;
  }
  if ( v5 != 2 )
  {
    EventWrite0(0x4000000, L"Failed to open IPxlatCfgSvc registry root key. Status = %d", v5);
    goto LABEL_12;
  }
  EventWrite0(0x4000000, L"IPxlatCfgSvc registry root is not present.");
LABEL_13:
  if ( *v3 )
  {
    CloseHandle(*v3);
    *v3 = 0;
  }
  v9 = *(void **)(a2 + 72);
  if ( v9 )
  {
    CloseHandle(v9);
    *(_QWORD *)(a2 + 72) = 0;
  }
  if ( *v2 )
  {
    RegCloseKey(*v2);
    *v2 = 0;
  }
  return LastError;
}

```

## disassembly

```asm
0x18007cef4  push    rbx
0x18007cef6  push    rsi
0x18007cef7  push    rdi
0x18007cef8  push    r14
0x18007cefa  sub     rsp, 38h
0x18007cefe  lea     rsi, [rdx+0F0h]
0x18007cf05  mov     qword ptr [rdx+48h], 0
0x18007cf0d  lea     r14, [rdx+50h]
0x18007cf11  mov     qword ptr [rsi], 0
0x18007cf18  mov     rdi, rdx
0x18007cf1b  mov     qword ptr [r14], 0
0x18007cf22  lea     rdx, aSystemCurrentc_9; "System\\CurrentControlSet\\Services\\Ip"...
0x18007cf29  mov     [rsp+58h+phkResult], rsi; phkResult
0x18007cf2e  mov     r9d, 20019h; samDesired
0x18007cf34  xor     r8d, r8d; ulOptions
0x18007cf37  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18007cf3e  call    cs:__imp_RegOpenKeyExW
0x18007cf45  nop     dword ptr [rax+rax+00h]
0x18007cf4a  mov     ebx, eax
0x18007cf4c  test    eax, eax
0x18007cf4e  jz      short loc_18007CF77
0x18007cf50  mov     ecx, 4000000h
0x18007cf55  cmp     eax, 2
0x18007cf58  jnz     short loc_18007CF6B
0x18007cf5a  lea     rdx, aIpxlatcfgsvcRe; "IPxlatCfgSvc registry root is not prese"...
0x18007cf61  call    EventWrite0
0x18007cf66  jmp     loc_18007D032
0x18007cf6b  lea     rdx, aFailedToOpenIp; "Failed to open IPxlatCfgSvc registry ro"...
0x18007cf72  jmp     loc_18007D026
0x18007cf77  xor     r9d, r9d; lpName
0x18007cf7a  xor     r8d, r8d; bInitialState
0x18007cf7d  xor     edx, edx; bManualReset
0x18007cf7f  xor     ecx, ecx; lpEventAttributes
0x18007cf81  call    cs:__imp_CreateEventW
0x18007cf88  nop     dword ptr [rax+rax+00h]
0x18007cf8d  mov     [rdi+48h], rax
0x18007cf91  test    rax, rax
0x18007cf94  jnz     short loc_18007CFAD
0x18007cf96  call    cs:__imp_GetLastError
0x18007cf9d  nop     dword ptr [rax+rax+00h]
0x18007cfa2  mov     ebx, eax
0x18007cfa4  lea     rdx, aFailedToCreate; "Failed to create Registry change notifi"...
0x18007cfab  jmp     short loc_18007D021
0x18007cfad  mov     [rsp+58h+dwFlags], 0; dwFlags
0x18007cfb5  lea     r8, ClatMgrRegKeyChangeCallback; Callback
0x18007cfbc  mov     r9, rdi; Context
0x18007cfbf  mov     dword ptr [rsp+58h+phkResult], 0FFFFFFFFh; dwMilliseconds
0x18007cfc7  mov     rdx, rax; hObject
0x18007cfca  mov     rcx, r14; phNewWaitObject
0x18007cfcd  call    cs:__imp_RegisterWaitForSingleObject
0x18007cfd4  nop     dword ptr [rax+rax+00h]
0x18007cfd9  test    eax, eax
0x18007cfdb  jnz     short loc_18007CFF4
0x18007cfdd  call    cs:__imp_GetLastError
0x18007cfe4  nop     dword ptr [rax+rax+00h]
0x18007cfe9  mov     ebx, eax
0x18007cfeb  lea     rdx, aFailedToAssoci; "Failed to associate registry change wai"...
0x18007cff2  jmp     short loc_18007D021
0x18007cff4  mov     r9, [rdi+48h]; hEvent
0x18007cff8  mov     edx, 1; bWatchSubtree
0x18007cffd  mov     rcx, [rsi]; hKey
0x18007d000  mov     dword ptr [rsp+58h+phkResult], edx; fAsynchronous
0x18007d004  lea     r8d, [rdx+3]; dwNotifyFilter
0x18007d008  call    cs:__imp_RegNotifyChangeKeyValue
0x18007d00f  nop     dword ptr [rax+rax+00h]
0x18007d014  mov     ebx, eax
0x18007d016  test    eax, eax
0x18007d018  jz      short loc_18007D087
0x18007d01a  lea     rdx, aFailedToRegist_1; "Failed to register for registry change "...
0x18007d021  mov     ecx, 4000000h
0x18007d026  mov     r8d, ebx
0x18007d029  call    EventWrite0
0x18007d02e  test    ebx, ebx
0x18007d030  jz      short loc_18007D098
0x18007d032  mov     rcx, [r14]; hObject
0x18007d035  test    rcx, rcx
0x18007d038  jz      short loc_18007D04D
0x18007d03a  call    cs:__imp_CloseHandle
0x18007d041  nop     dword ptr [rax+rax+00h]
0x18007d046  mov     qword ptr [r14], 0
0x18007d04d  mov     rcx, [rdi+48h]; hObject
0x18007d051  test    rcx, rcx
0x18007d054  jz      short loc_18007D06A
0x18007d056  call    cs:__imp_CloseHandle
0x18007d05d  nop     dword ptr [rax+rax+00h]
0x18007d062  mov     qword ptr [rdi+48h], 0
0x18007d06a  mov     rcx, [rsi]; hKey
0x18007d06d  test    rcx, rcx
0x18007d070  jz      short loc_18007D098
0x18007d072  call    cs:__imp_RegCloseKey
0x18007d079  nop     dword ptr [rax+rax+00h]
0x18007d07e  mov     qword ptr [rsi], 0
0x18007d085  jmp     short loc_18007D098
0x18007d087  lea     rdx, aRegistryChange; "Registry change notification registered"...
0x18007d08e  mov     ecx, 4000000h
0x18007d093  call    EventWrite0
0x18007d098  mov     eax, ebx
0x18007d09a  add     rsp, 38h
0x18007d09e  pop     r14
0x18007d0a0  pop     rdi
0x18007d0a1  pop     rsi
0x18007d0a2  pop     rbx
0x18007d0a3  retn
```
