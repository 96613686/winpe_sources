# CSchedule::IncrementAndSaveID(void)

- ea: `0x18000f2d8`
- end: `0x18000f3a4`
- name: `?IncrementAndSaveID@CSchedule@@QEAAJXZ`
- size: `204`
- prototype: `__int64 __fastcall(CSchedule *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task`

## callers

- `0x18000e750`

## callees

- `0x18000f2d8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000f36c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000f381`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000f36c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000f381`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000f321`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000f321`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000f359`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000f359`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000f2f1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000f2f1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000f38c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000f38c`

## string_xrefs

- `0x18000f313`: `System\CurrentControlSet\Services\Schedule`

## pseudocode

```c
__int64 __fastcall CSchedule::IncrementAndSaveID(CSchedule *this)
{
  struct _RTL_CRITICAL_SECTION *v1; // rsi
  LSTATUS v3; // eax
  int v4; // ebx
  HKEY v5; // rcx
  const BYTE *v6; // rdi
  LSTATUS v7; // eax
  HKEY v8; // rcx
  HKEY hKey; // [rsp+40h] [rbp+8h] BYREF

  v1 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 8);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  hKey = 0;
  v3 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Services\\Schedule", 0, 2u, &hKey);
  v4 = v3;
  if ( v3 )
  {
    if ( v3 > 0 )
    {
      v4 = (unsigned __int16)v3;
LABEL_7:
      v4 |= 0x80070000;
    }
  }
  else
  {
    v5 = hKey;
    v6 = (const BYTE *)this + 48;
    ++*(_DWORD *)v6;
    v7 = RegSetValueExW(v5, L"NextAtJobId", 0, 4u, v6, 4u);
    v8 = hKey;
    v4 = v7;
    if ( !v7 )
    {
      RegCloseKey(hKey);
      v4 = 0;
      goto LABEL_9;
    }
    --*(_DWORD *)v6;
    RegCloseKey(v8);
    if ( v4 > 0 )
    {
      v4 = (unsigned __int16)v4;
      goto LABEL_7;
    }
  }
LABEL_9:
  LeaveCriticalSection(v1);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18000f2d8  mov     [rsp+arg_8], rbx
0x18000f2dd  mov     [rsp+arg_10], rsi
0x18000f2e2  push    rdi
0x18000f2e3  sub     rsp, 30h
0x18000f2e7  lea     rsi, [rcx+8]
0x18000f2eb  mov     rdi, rcx
0x18000f2ee  mov     rcx, rsi; lpCriticalSection
0x18000f2f1  call    cs:__imp_EnterCriticalSection
0x18000f2f7  lea     rax, [rsp+38h+hKey]
0x18000f2fc  mov     [rsp+38h+hKey], 0
0x18000f305  mov     r9d, 2; samDesired
0x18000f30b  mov     [rsp+38h+phkResult], rax; phkResult
0x18000f310  xor     r8d, r8d; ulOptions
0x18000f313  lea     rdx, aSystemCurrentc; "System\\CurrentControlSet\\Services\\Sc"...
0x18000f31a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000f321  call    cs:__imp_RegOpenKeyExW
0x18000f327  mov     ebx, eax
0x18000f329  test    eax, eax
0x18000f32b  jz      short loc_18000F334
0x18000f32d  jle     short loc_18000F389
0x18000f32f  movzx   ebx, ax
0x18000f332  jmp     short loc_18000F379
0x18000f334  mov     rcx, [rsp+38h+hKey]; hKey
0x18000f339  lea     rdx, aNextatjobid; "NextAtJobId"
0x18000f340  add     rdi, 30h ; '0'
0x18000f344  mov     r9d, 4; dwType
0x18000f34a  mov     [rsp+38h+cbData], r9d; cbData
0x18000f34f  xor     r8d, r8d; Reserved
0x18000f352  mov     [rsp+38h+phkResult], rdi; lpData
0x18000f357  inc     dword ptr [rdi]
0x18000f359  call    cs:__imp_RegSetValueExW
0x18000f35f  mov     rcx, [rsp+38h+hKey]; hKey
0x18000f364  mov     ebx, eax
0x18000f366  test    eax, eax
0x18000f368  jz      short loc_18000F381
0x18000f36a  dec     dword ptr [rdi]
0x18000f36c  call    cs:__imp_RegCloseKey
0x18000f372  test    ebx, ebx
0x18000f374  jle     short loc_18000F389
0x18000f376  movzx   ebx, bx
0x18000f379  or      ebx, 80070000h
0x18000f37f  jmp     short loc_18000F389
0x18000f381  call    cs:__imp_RegCloseKey
0x18000f387  xor     ebx, ebx
0x18000f389  mov     rcx, rsi; lpCriticalSection
0x18000f38c  call    cs:__imp_LeaveCriticalSection
0x18000f392  mov     rsi, [rsp+38h+arg_10]
0x18000f397  mov     eax, ebx
0x18000f399  mov     rbx, [rsp+38h+arg_8]
0x18000f39e  add     rsp, 30h
0x18000f3a2  pop     rdi
0x18000f3a3  retn
```
