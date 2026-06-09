# IsQuarantineInstalled

- ea: `0x18003771c`
- end: `0x1800377e1`
- name: `IsQuarantineInstalled`
- size: `197`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x18001555c`

## callees

- `0x18003771c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800377d3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800377d3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003776b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003776b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003779f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003779f`

## string_xrefs

- `0x18003775d`: `System\CurrentControlSet\Services\RemoteAccess\Parameters`
- `0x180037793`: `QuarantineInstalled`

## pseudocode

```c
__int64 __fastcall IsQuarantineInstalled(__int64 a1)
{
  LSTATUS v1; // eax
  unsigned int v2; // ebx
  HKEY hKey; // [rsp+30h] [rbp-18h] BYREF
  __int64 Type; // [rsp+50h] [rbp+8h] BYREF
  int Data; // [rsp+58h] [rbp+10h] BYREF
  unsigned int v7; // [rsp+60h] [rbp+18h]
  DWORD cbData; // [rsp+68h] [rbp+20h] BYREF

  Type = a1;
  try
  {
    hKey = 0;
    Data = 0;
    cbData = 4;
    LODWORD(Type) = 4;
    v2 = 0;
    v7 = 0;
    v1 = RegOpenKeyExW(
           HKEY_LOCAL_MACHINE,
           L"System\\CurrentControlSet\\Services\\RemoteAccess\\Parameters",
           0,
           0x20019u,
           &hKey);
  }
  catch ( ... )
  {
    v2 = v7;
    goto LABEL_8;
  }
  if ( !v1
    && (RegQueryValueExW(hKey, L"QuarantineInstalled", 0, (LPDWORD)&Type, (LPBYTE)&Data, &cbData) || (_DWORD)Type == 4) )
  {
    if ( Data )
      v2 = 1;
    v7 = v2;
  }
LABEL_8:
  if ( hKey )
    RegCloseKey(hKey);
  return v2;
}

```

## disassembly

```asm
0x18003771c  mov     rax, rsp
0x18003771f  mov     [rax+8], rcx
0x180037723  push    rbx
0x180037724  sub     rsp, 40h
0x180037728  mov     qword ptr [rax-18h], 0
0x180037730  mov     dword ptr [rax+10h], 0
0x180037737  mov     dword ptr [rax+20h], 4
0x18003773e  mov     dword ptr [rax+8], 4
0x180037745  xor     ebx, ebx
0x180037747  mov     [rsp+48h+arg_10], ebx
0x18003774b  lea     rax, [rax-18h]
0x18003774f  mov     [rsp+48h+phkResult], rax; phkResult
0x180037754  mov     r9d, 20019h; samDesired
0x18003775a  xor     r8d, r8d; ulOptions
0x18003775d  lea     rdx, aSystemCurrentc_1; "System\\CurrentControlSet\\Services\\Re"...
0x180037764  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003776b  call    cs:__imp_RegOpenKeyExW
0x180037771  test    eax, eax
0x180037773  jz      short loc_180037777
0x180037775  jmp     short loc_1800377C9
0x180037777  lea     rax, [rsp+48h+cbData]
0x18003777c  mov     [rsp+48h+lpcbData], rax; lpcbData
0x180037781  lea     rax, [rsp+48h+Data]
0x180037786  mov     [rsp+48h+phkResult], rax; lpData
0x18003778b  lea     r9, [rsp+48h+Type]; lpType
0x180037790  xor     r8d, r8d; lpReserved
0x180037793  lea     rdx, aQuarantineinst; "QuarantineInstalled"
0x18003779a  mov     rcx, [rsp+48h+hKey]; hKey
0x18003779f  call    cs:__imp_RegQueryValueExW
0x1800377a5  test    eax, eax
0x1800377a7  jnz     short loc_1800377B2
0x1800377a9  cmp     dword ptr [rsp+48h+Type], 4
0x1800377ae  jz      short loc_1800377B2
0x1800377b0  jmp     short loc_1800377C9
0x1800377b2  mov     eax, 1
0x1800377b7  cmp     [rsp+48h+Data], 0
0x1800377bc  cmovnz  ebx, eax
0x1800377bf  mov     [rsp+48h+arg_10], ebx
0x1800377c3  jmp     short loc_1800377C9
0x1800377c5  mov     ebx, [rsp+48h+arg_10]
0x1800377c9  mov     rcx, [rsp+48h+hKey]; hKey
0x1800377ce  test    rcx, rcx
0x1800377d1  jz      short loc_1800377D9
0x1800377d3  call    cs:__imp_RegCloseKey
0x1800377d9  mov     eax, ebx
0x1800377db  add     rsp, 40h
0x1800377df  pop     rbx
0x1800377e0  retn
```
