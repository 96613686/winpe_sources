# CService::TestDelaySetReadyEvent(void)

- ea: `0x1800477c4`
- end: `0x180047882`
- name: `?TestDelaySetReadyEvent@CService@@IEAAJXZ`
- size: `190`
- prototype: `__int64 __fastcall(CService *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x18002ae4c`

## callees

- `0x1800477c4`

## import_xrefs

- `ntdll!NtDelayExecution` at `0x18004786a`
- `ntdll!NtDelayExecution` at `0x18004786a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180047816`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180047816`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180047845`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180047845`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180047874`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180047874`

## string_xrefs

- `0x180047839`: `DelayReadyEventTimeout`

## pseudocode

```c
__int64 __fastcall CService::TestDelaySetReadyEvent(CService *this)
{
  LARGE_INTEGER Interval; // [rsp+30h] [rbp-10h] BYREF
  int Data; // [rsp+50h] [rbp+10h] BYREF
  int v4; // [rsp+54h] [rbp+14h]
  DWORD cbData; // [rsp+58h] [rbp+18h] BYREF
  DWORD Type; // [rsp+60h] [rbp+20h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+28h] BYREF

  v4 = HIDWORD(this);
  Type = 0;
  cbData = 4;
  Data = 0;
  hKey = 0;
  Interval.QuadPart = 0;
  RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Control\\Terminal Server", 0, 0x20019u, &hKey);
  if ( hKey )
  {
    if ( !RegQueryValueExW(hKey, L"DelayReadyEventTimeout", 0, &Type, (LPBYTE)&Data, &cbData) )
    {
      Interval.QuadPart = -600000000LL * Data;
      NtDelayExecution(0, &Interval);
    }
    RegCloseKey(hKey);
  }
  return 0;
}

```

## disassembly

```asm
0x1800477c4  mov     qword ptr [rsp-8+Data], rcx
0x1800477c9  push    rbp
0x1800477ca  mov     rbp, rsp
0x1800477cd  sub     rsp, 40h
0x1800477d1  lea     rax, [rbp+hKey]
0x1800477d5  mov     [rbp+Type], 0
0x1800477dc  mov     r9d, 20019h; samDesired
0x1800477e2  mov     [rsp+40h+phkResult], rax; phkResult
0x1800477e7  xor     r8d, r8d; ulOptions
0x1800477ea  mov     [rbp+cbData], 4
0x1800477f1  lea     rdx, SubKey; "System\\CurrentControlSet\\Control\\Ter"...
0x1800477f8  mov     [rbp+Data], 0
0x1800477ff  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180047806  mov     [rbp+hKey], 0
0x18004780e  mov     qword ptr [rbp+Interval], 0
0x180047816  call    cs:__imp_RegOpenKeyExW
0x18004781c  mov     rcx, [rbp+hKey]; hKey
0x180047820  test    rcx, rcx
0x180047823  jz      short loc_18004787A
0x180047825  lea     rax, [rbp+cbData]
0x180047829  xor     r8d, r8d; lpReserved
0x18004782c  mov     [rsp+40h+lpcbData], rax; lpcbData
0x180047831  lea     r9, [rbp+Type]; lpType
0x180047835  lea     rax, [rbp+Data]
0x180047839  lea     rdx, aDelayreadyeven; "DelayReadyEventTimeout"
0x180047840  mov     [rsp+40h+phkResult], rax; lpData
0x180047845  call    cs:__imp_RegQueryValueExW
0x18004784b  test    eax, eax
0x18004784d  jnz     short loc_180047870
0x18004784f  imul    eax, [rbp+Data], 0EA60h
0x180047856  lea     rdx, [rbp+Interval]; Interval
0x18004785a  movsxd  rcx, eax
0x18004785d  imul    rax, rcx, 0FFFFFFFFFFFFD8F0h
0x180047864  xor     ecx, ecx; Alertable
0x180047866  mov     qword ptr [rbp+Interval], rax
0x18004786a  call    cs:__imp_NtDelayExecution
0x180047870  mov     rcx, [rbp+hKey]; hKey
0x180047874  call    cs:__imp_RegCloseKey
0x18004787a  xor     eax, eax
0x18004787c  add     rsp, 40h
0x180047880  pop     rbp
0x180047881  retn
```
