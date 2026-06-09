# DhcpIsFSEFlagEnabledInRegistry

- ea: `0x18002dbe0`
- end: `0x18002dce0`
- name: `DhcpIsFSEFlagEnabledInRegistry`
- size: `256`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x1800075b0`
- `0x18000aaa0`

## callees

- `0x18002dbe0`
- `0x180033900`
- `0x1800340b4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002dc37`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002dc37`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002dc74`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002dc74`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002dca3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002dca3`

## string_xrefs

- `0x18002dc29`: `System\CurrentControlSet\Services\Tcpip\Parameters`

## pseudocode

```c
__int64 DhcpIsFSEFlagEnabledInRegistry()
{
  unsigned int v0; // ebx
  LSTATUS v1; // edi
  DWORD cbData; // [rsp+50h] [rbp+20h] BYREF
  DWORD Type; // [rsp+58h] [rbp+28h] BYREF
  int Data; // [rsp+60h] [rbp+30h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+38h] BYREF

  v0 = 0;
  cbData = 0;
  Type = 0;
  Data = 0;
  hKey = 0;
  if ( (xmmword_1800423E0 & 0x10) != 0 )
    WPP_SF_(1028, 26, WPP_5d68708c8ecd3afe0a2d79d623927bf9_Traceguids);
  v1 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Services\\Tcpip\\Parameters", 0, 1u, &hKey);
  if ( !v1 )
  {
    cbData = 4;
    v1 = RegQueryValueExW(hKey, L"PortTrackerEnabledMode", 0, &Type, (LPBYTE)&Data, &cbData);
    if ( !v1 )
    {
      if ( Type == 4 )
      {
        v1 = 0;
        LOBYTE(v0) = Data == 1;
      }
      else
      {
        v1 = 87;
      }
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  if ( (xmmword_1800423E0 & 0x10) != 0 )
    WPP_SF_dd(1028, 27, WPP_5d68708c8ecd3afe0a2d79d623927bf9_Traceguids, v0, v1);
  return v0;
}

```

## disassembly

```asm
0x18002dbe0  push    rbp
0x18002dbe2  push    rbx
0x18002dbe3  push    rdi
0x18002dbe4  mov     rbp, rsp
0x18002dbe7  sub     rsp, 30h
0x18002dbeb  xor     ebx, ebx
0x18002dbed  mov     [rbp+cbData], ebx
0x18002dbf0  mov     [rbp+Type], ebx
0x18002dbf3  mov     [rbp+Data], ebx
0x18002dbf6  mov     [rbp+hKey], rbx
0x18002dbfa  test    byte ptr cs:xmmword_1800423E0, 10h
0x18002dc01  jz      short loc_18002DC17
0x18002dc03  lea     edx, [rbx+1Ah]
0x18002dc06  mov     ecx, 404h
0x18002dc0b  lea     r8, WPP_5d68708c8ecd3afe0a2d79d623927bf9_Traceguids
0x18002dc12  call    WPP_SF_
0x18002dc17  lea     rax, [rbp+hKey]
0x18002dc1b  mov     r9d, 1; samDesired
0x18002dc21  xor     r8d, r8d; ulOptions
0x18002dc24  mov     [rsp+30h+phkResult], rax; phkResult
0x18002dc29  lea     rdx, aSystemCurrentc_8; "System\\CurrentControlSet\\Services\\Tc"...
0x18002dc30  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002dc37  call    cs:__imp_RegOpenKeyExW
0x18002dc3e  nop     dword ptr [rax+rax+00h]
0x18002dc43  mov     edi, eax
0x18002dc45  test    eax, eax
0x18002dc47  jnz     short loc_18002DC9A
0x18002dc49  mov     rcx, [rbp+hKey]; hKey
0x18002dc4d  lea     rax, [rbp+cbData]
0x18002dc51  mov     [rsp+30h+lpcbData], rax; lpcbData
0x18002dc56  lea     r9, [rbp+Type]; lpType
0x18002dc5a  lea     rax, [rbp+Data]
0x18002dc5e  mov     [rbp+cbData], 4
0x18002dc65  xor     r8d, r8d; lpReserved
0x18002dc68  mov     [rsp+30h+phkResult], rax; lpData
0x18002dc6d  lea     rdx, aPorttrackerena; "PortTrackerEnabledMode"
0x18002dc74  call    cs:__imp_RegQueryValueExW
0x18002dc7b  nop     dword ptr [rax+rax+00h]
0x18002dc80  mov     edi, eax
0x18002dc82  test    eax, eax
0x18002dc84  jnz     short loc_18002DC9A
0x18002dc86  cmp     [rbp+Type], 4
0x18002dc8a  jz      short loc_18002DC91
0x18002dc8c  lea     edi, [rax+57h]
0x18002dc8f  jmp     short loc_18002DC9A
0x18002dc91  xor     edi, edi
0x18002dc93  cmp     [rbp+Data], 1
0x18002dc97  setz    bl
0x18002dc9a  mov     rcx, [rbp+hKey]; hKey
0x18002dc9e  test    rcx, rcx
0x18002dca1  jz      short loc_18002DCAF
0x18002dca3  call    cs:__imp_RegCloseKey
0x18002dcaa  nop     dword ptr [rax+rax+00h]
0x18002dcaf  test    byte ptr cs:xmmword_1800423E0, 10h
0x18002dcb6  jz      short loc_18002DCD5
0x18002dcb8  mov     edx, 1Bh
0x18002dcbd  mov     dword ptr [rsp+30h+phkResult], edi
0x18002dcc1  mov     ecx, 404h
0x18002dcc6  lea     r8, WPP_5d68708c8ecd3afe0a2d79d623927bf9_Traceguids
0x18002dccd  mov     r9d, ebx
0x18002dcd0  call    WPP_SF_dd
0x18002dcd5  mov     eax, ebx
0x18002dcd7  add     rsp, 30h
0x18002dcdb  pop     rdi
0x18002dcdc  pop     rbx
0x18002dcdd  pop     rbp
0x18002dcde  retn
```
