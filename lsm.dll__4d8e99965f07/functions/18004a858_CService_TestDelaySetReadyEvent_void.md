# CService::TestDelaySetReadyEvent(void)

- ea: `0x18004a858`
- end: `0x18004a92f`
- name: `?TestDelaySetReadyEvent@CService@@IEAAJXZ`
- size: `215`
- prototype: `__int64 __fastcall(CService *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x18002cf00`

## callees

- `0x18004a858`

## import_xrefs

- `ntdll!NtDelayExecution` at `0x18004a90a`
- `ntdll!NtDelayExecution` at `0x18004a90a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004a8aa`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004a8aa`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18004a8df`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18004a8df`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004a91a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004a91a`

## string_xrefs

- `0x18004a8d3`: `DelayReadyEventTimeout`

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
0x18004a858  mov     qword ptr [rsp-8+Data], rcx
0x18004a85d  push    rbp
0x18004a85e  mov     rbp, rsp
0x18004a861  sub     rsp, 40h
0x18004a865  lea     rax, [rbp+hKey]
0x18004a869  mov     [rbp+Type], 0
0x18004a870  mov     r9d, 20019h; samDesired
0x18004a876  mov     [rsp+40h+phkResult], rax; phkResult
0x18004a87b  xor     r8d, r8d; ulOptions
0x18004a87e  mov     [rbp+cbData], 4
0x18004a885  lea     rdx, SubKey; "System\\CurrentControlSet\\Control\\Ter"...
0x18004a88c  mov     [rbp+Data], 0
0x18004a893  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18004a89a  mov     [rbp+hKey], 0
0x18004a8a2  mov     qword ptr [rbp+Interval], 0
0x18004a8aa  call    cs:__imp_RegOpenKeyExW
0x18004a8b1  nop     dword ptr [rax+rax+00h]
0x18004a8b6  mov     rcx, [rbp+hKey]; hKey
0x18004a8ba  test    rcx, rcx
0x18004a8bd  jz      short loc_18004A926
0x18004a8bf  lea     rax, [rbp+cbData]
0x18004a8c3  xor     r8d, r8d; lpReserved
0x18004a8c6  mov     [rsp+40h+lpcbData], rax; lpcbData
0x18004a8cb  lea     r9, [rbp+Type]; lpType
0x18004a8cf  lea     rax, [rbp+Data]
0x18004a8d3  lea     rdx, aDelayreadyeven; "DelayReadyEventTimeout"
0x18004a8da  mov     [rsp+40h+phkResult], rax; lpData
0x18004a8df  call    cs:__imp_RegQueryValueExW
0x18004a8e6  nop     dword ptr [rax+rax+00h]
0x18004a8eb  test    eax, eax
0x18004a8ed  jnz     short loc_18004A916
0x18004a8ef  imul    eax, [rbp+Data], 0EA60h
0x18004a8f6  lea     rdx, [rbp+Interval]; Interval
0x18004a8fa  movsxd  rcx, eax
0x18004a8fd  imul    rax, rcx, 0FFFFFFFFFFFFD8F0h
0x18004a904  xor     ecx, ecx; Alertable
0x18004a906  mov     qword ptr [rbp+Interval], rax
0x18004a90a  call    cs:__imp_NtDelayExecution
0x18004a911  nop     dword ptr [rax+rax+00h]
0x18004a916  mov     rcx, [rbp+hKey]; hKey
0x18004a91a  call    cs:__imp_RegCloseKey
0x18004a921  nop     dword ptr [rax+rax+00h]
0x18004a926  xor     eax, eax
0x18004a928  add     rsp, 40h
0x18004a92c  pop     rbp
0x18004a92d  retn
```
