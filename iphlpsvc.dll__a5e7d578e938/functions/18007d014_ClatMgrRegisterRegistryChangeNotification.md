# ClatMgrRegisterRegistryChangeNotification

- ea: `0x18007d014`
- end: `0x18007d1c5`
- name: `ClatMgrRegisterRegistryChangeNotification`
- size: `433`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task`

## callers

- `0x18007c720`

## callees

- `0x18000d7c0`
- `0x18007d014`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x18007d128`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x18007d128`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007d192`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007d192`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18007d05e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18007d05e`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18007d0a1`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18007d0a1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007d0b6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007d0fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007d0b6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007d0fd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007d15a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007d176`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007d15a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007d176`
- `api-ms-win-core-kernel32-legacy-l1-1-0!RegisterWaitForSingleObject` at `0x18007d0ed`
- `api-ms-win-core-kernel32-legacy-l1-1-0!RegisterWaitForSingleObject` at `0x18007d0ed`

## string_xrefs

- `0x18007d07a`: `IPxlatCfgSvc registry root is not present.`
- `0x18007d08b`: `Failed to open IPxlatCfgSvc registry root key. Status = %d`
- `0x18007d0c4`: `Failed to create Registry change notification event. Status = %d`
- `0x18007d10b`: `Failed to associate registry change wait object. Status = %d`
- `0x18007d13a`: `Failed to register for registry change notification. Status = %d\n`
- `0x18007d1a7`: `Registry change notification registered successfully.`
- `0x18007d042`: `System\CurrentControlSet\Services\IpxlatCfgSvc`

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

  v2 = (HKEY *)(a2 + 256);
  *(_QWORD *)(a2 + 88) = 0;
  v3 = (void **)(a2 + 96);
  *(_QWORD *)(a2 + 256) = 0;
  *(_QWORD *)(a2 + 96) = 0;
  v5 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"System\\CurrentControlSet\\Services\\IpxlatCfgSvc",
         0,
         0x20019u,
         (PHKEY)(a2 + 256));
  LastError = v5;
  if ( !v5 )
  {
    EventW = CreateEventW(0, 0, 0, 0);
    *(_QWORD *)(a2 + 88) = EventW;
    if ( EventW )
    {
      if ( RegisterWaitForSingleObject(v3, EventW, ClatMgrRegKeyChangeCallback, (PVOID)a2, 0xFFFFFFFF, 0) )
      {
        LastError = RegNotifyChangeKeyValue(*v2, 1, 4u, *(HANDLE *)(a2 + 88), 1);
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
  v9 = *(void **)(a2 + 88);
  if ( v9 )
  {
    CloseHandle(v9);
    *(_QWORD *)(a2 + 88) = 0;
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
0x18007d014  push    rbx
0x18007d016  push    rsi
0x18007d017  push    rdi
0x18007d018  push    r14
0x18007d01a  sub     rsp, 38h
0x18007d01e  lea     rsi, [rdx+100h]
0x18007d025  mov     qword ptr [rdx+58h], 0
0x18007d02d  lea     r14, [rdx+60h]
0x18007d031  mov     qword ptr [rsi], 0
0x18007d038  mov     rdi, rdx
0x18007d03b  mov     qword ptr [r14], 0
0x18007d042  lea     rdx, aSystemCurrentc_9; "System\\CurrentControlSet\\Services\\Ip"...
0x18007d049  mov     [rsp+58h+phkResult], rsi; phkResult
0x18007d04e  mov     r9d, 20019h; samDesired
0x18007d054  xor     r8d, r8d; ulOptions
0x18007d057  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18007d05e  call    cs:__imp_RegOpenKeyExW
0x18007d065  nop     dword ptr [rax+rax+00h]
0x18007d06a  mov     ebx, eax
0x18007d06c  test    eax, eax
0x18007d06e  jz      short loc_18007D097
0x18007d070  mov     ecx, 4000000h
0x18007d075  cmp     eax, 2
0x18007d078  jnz     short loc_18007D08B
0x18007d07a  lea     rdx, aIpxlatcfgsvcRe; "IPxlatCfgSvc registry root is not prese"...
0x18007d081  call    EventWrite0
0x18007d086  jmp     loc_18007D152
0x18007d08b  lea     rdx, aFailedToOpenIp; "Failed to open IPxlatCfgSvc registry ro"...
0x18007d092  jmp     loc_18007D146
0x18007d097  xor     r9d, r9d; lpName
0x18007d09a  xor     r8d, r8d; bInitialState
0x18007d09d  xor     edx, edx; bManualReset
0x18007d09f  xor     ecx, ecx; lpEventAttributes
0x18007d0a1  call    cs:__imp_CreateEventW
0x18007d0a8  nop     dword ptr [rax+rax+00h]
0x18007d0ad  mov     [rdi+58h], rax
0x18007d0b1  test    rax, rax
0x18007d0b4  jnz     short loc_18007D0CD
0x18007d0b6  call    cs:__imp_GetLastError
0x18007d0bd  nop     dword ptr [rax+rax+00h]
0x18007d0c2  mov     ebx, eax
0x18007d0c4  lea     rdx, aFailedToCreate; "Failed to create Registry change notifi"...
0x18007d0cb  jmp     short loc_18007D141
0x18007d0cd  mov     [rsp+58h+dwFlags], 0; dwFlags
0x18007d0d5  lea     r8, ClatMgrRegKeyChangeCallback; Callback
0x18007d0dc  mov     r9, rdi; Context
0x18007d0df  mov     dword ptr [rsp+58h+phkResult], 0FFFFFFFFh; dwMilliseconds
0x18007d0e7  mov     rdx, rax; hObject
0x18007d0ea  mov     rcx, r14; phNewWaitObject
0x18007d0ed  call    cs:__imp_RegisterWaitForSingleObject
0x18007d0f4  nop     dword ptr [rax+rax+00h]
0x18007d0f9  test    eax, eax
0x18007d0fb  jnz     short loc_18007D114
0x18007d0fd  call    cs:__imp_GetLastError
0x18007d104  nop     dword ptr [rax+rax+00h]
0x18007d109  mov     ebx, eax
0x18007d10b  lea     rdx, aFailedToAssoci; "Failed to associate registry change wai"...
0x18007d112  jmp     short loc_18007D141
0x18007d114  mov     r9, [rdi+58h]; hEvent
0x18007d118  mov     edx, 1; bWatchSubtree
0x18007d11d  mov     rcx, [rsi]; hKey
0x18007d120  mov     dword ptr [rsp+58h+phkResult], edx; fAsynchronous
0x18007d124  lea     r8d, [rdx+3]; dwNotifyFilter
0x18007d128  call    cs:__imp_RegNotifyChangeKeyValue
0x18007d12f  nop     dword ptr [rax+rax+00h]
0x18007d134  mov     ebx, eax
0x18007d136  test    eax, eax
0x18007d138  jz      short loc_18007D1A7
0x18007d13a  lea     rdx, aFailedToRegist_1; "Failed to register for registry change "...
0x18007d141  mov     ecx, 4000000h
0x18007d146  mov     r8d, ebx
0x18007d149  call    EventWrite0
0x18007d14e  test    ebx, ebx
0x18007d150  jz      short loc_18007D1B8
0x18007d152  mov     rcx, [r14]; hObject
0x18007d155  test    rcx, rcx
0x18007d158  jz      short loc_18007D16D
0x18007d15a  call    cs:__imp_CloseHandle
0x18007d161  nop     dword ptr [rax+rax+00h]
0x18007d166  mov     qword ptr [r14], 0
0x18007d16d  mov     rcx, [rdi+58h]; hObject
0x18007d171  test    rcx, rcx
0x18007d174  jz      short loc_18007D18A
0x18007d176  call    cs:__imp_CloseHandle
0x18007d17d  nop     dword ptr [rax+rax+00h]
0x18007d182  mov     qword ptr [rdi+58h], 0
0x18007d18a  mov     rcx, [rsi]; hKey
0x18007d18d  test    rcx, rcx
0x18007d190  jz      short loc_18007D1B8
0x18007d192  call    cs:__imp_RegCloseKey
0x18007d199  nop     dword ptr [rax+rax+00h]
0x18007d19e  mov     qword ptr [rsi], 0
0x18007d1a5  jmp     short loc_18007D1B8
0x18007d1a7  lea     rdx, aRegistryChange; "Registry change notification registered"...
0x18007d1ae  mov     ecx, 4000000h
0x18007d1b3  call    EventWrite0
0x18007d1b8  mov     eax, ebx
0x18007d1ba  add     rsp, 38h
0x18007d1be  pop     r14
0x18007d1c0  pop     rdi
0x18007d1c1  pop     rsi
0x18007d1c2  pop     rbx
0x18007d1c3  retn
```
