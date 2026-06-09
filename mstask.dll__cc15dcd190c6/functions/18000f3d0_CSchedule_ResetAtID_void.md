# CSchedule::ResetAtID(void)

- ea: `0x18000f3d0`
- end: `0x18000f491`
- name: `?ResetAtID@CSchedule@@QEAAJXZ`
- size: `193`
- prototype: `__int64 __fastcall(CSchedule *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task`

## callers

- `0x18000e7f8`

## callees

- `0x18000f3d0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000f441`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000f441`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000f420`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000f420`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000f481`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000f481`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000f3f3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000f3f3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000f44a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000f44a`

## string_xrefs

- `0x18000f412`: `System\CurrentControlSet\Services\Schedule`

## pseudocode

```c
__int64 __fastcall CSchedule::ResetAtID(CSchedule *this)
{
  struct _RTL_CRITICAL_SECTION *v1; // rdi
  BYTE *v2; // rsi
  LSTATUS v3; // eax
  unsigned int v4; // ebx
  HKEY hKey; // [rsp+40h] [rbp+8h] BYREF

  v1 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 8);
  hKey = 0;
  v2 = (BYTE *)this + 48;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  *(_DWORD *)v2 = 1;
  v3 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Services\\Schedule", 0, 0x2001Fu, &hKey);
  v4 = v3;
  if ( v3 )
  {
    if ( v3 <= 0 )
      goto LABEL_4;
    goto LABEL_3;
  }
  v4 = 0;
  v3 = RegSetValueExW(hKey, L"NextAtJobId", 0, 4u, v2, 4u);
  if ( v3 )
  {
    if ( v3 > 0 )
    {
LABEL_3:
      v4 = (unsigned __int16)v3 | 0x80070000;
      goto LABEL_4;
    }
    v4 = v3;
  }
LABEL_4:
  if ( hKey )
    RegCloseKey(hKey);
  LeaveCriticalSection(v1);
  return v4;
}

```

## disassembly

```asm
0x18000f3d0  mov     [rsp+arg_8], rbx
0x18000f3d5  mov     [rsp+arg_10], rsi
0x18000f3da  push    rdi
0x18000f3db  sub     rsp, 30h
0x18000f3df  lea     rdi, [rcx+8]
0x18000f3e3  mov     [rsp+38h+hKey], 0
0x18000f3ec  lea     rsi, [rcx+30h]
0x18000f3f0  mov     rcx, rdi; lpCriticalSection
0x18000f3f3  call    cs:__imp_EnterCriticalSection
0x18000f3f9  lea     rax, [rsp+38h+hKey]
0x18000f3fe  mov     dword ptr [rsi], 1
0x18000f404  mov     r9d, 2001Fh; samDesired
0x18000f40a  mov     [rsp+38h+phkResult], rax; phkResult
0x18000f40f  xor     r8d, r8d; ulOptions
0x18000f412  lea     rdx, aSystemCurrentc; "System\\CurrentControlSet\\Services\\Sc"...
0x18000f419  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000f420  call    cs:__imp_RegOpenKeyExW
0x18000f426  mov     ebx, eax
0x18000f428  test    eax, eax
0x18000f42a  jz      short loc_18000F462
0x18000f42c  jle     short loc_18000F437
0x18000f42e  movzx   ebx, ax
0x18000f431  or      ebx, 80070000h
0x18000f437  mov     rcx, [rsp+38h+hKey]; hKey
0x18000f43c  test    rcx, rcx
0x18000f43f  jz      short loc_18000F447
0x18000f441  call    cs:__imp_RegCloseKey
0x18000f447  mov     rcx, rdi; lpCriticalSection
0x18000f44a  call    cs:__imp_LeaveCriticalSection
0x18000f450  mov     rsi, [rsp+38h+arg_10]
0x18000f455  mov     eax, ebx
0x18000f457  mov     rbx, [rsp+38h+arg_8]
0x18000f45c  add     rsp, 30h
0x18000f460  pop     rdi
0x18000f461  retn
0x18000f462  mov     rcx, [rsp+38h+hKey]; hKey
0x18000f467  lea     rdx, aNextatjobid; "NextAtJobId"
0x18000f46e  xor     ebx, ebx
0x18000f470  xor     r8d, r8d; Reserved
0x18000f473  lea     r9d, [rbx+4]; dwType
0x18000f477  mov     [rsp+38h+cbData], r9d; cbData
0x18000f47c  mov     [rsp+38h+phkResult], rsi; lpData
0x18000f481  call    cs:__imp_RegSetValueExW
0x18000f487  test    eax, eax
0x18000f489  jz      short loc_18000F437
0x18000f48b  jg      short loc_18000F42E
0x18000f48d  mov     ebx, eax
0x18000f48f  jmp     short loc_18000F437
```
