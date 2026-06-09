# DhcpIsFSEFlagEnabledInRegistry

- ea: `0x180004070`
- end: `0x18000415c`
- name: `DhcpIsFSEFlagEnabledInRegistry`
- size: `236`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x180002760`

## callees

- `0x180004070`
- `0x180012794`
- `0x180012b80`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800040cd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800040cd`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180004109`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180004109`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004137`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004137`

## string_xrefs

- `0x1800040bf`: `System\CurrentControlSet\Services\Tcpip\Parameters`

## pseudocode

```c
__int64 DhcpIsFSEFlagEnabledInRegistry()
{
  unsigned int v0; // ebx
  __int64 v1; // rdx
  LSTATUS v2; // edi
  __int64 v3; // r8
  HKEY v4; // rcx
  DWORD cbData; // [rsp+50h] [rbp+8h] BYREF
  DWORD Type; // [rsp+58h] [rbp+10h] BYREF
  int Data; // [rsp+60h] [rbp+18h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+20h] BYREF

  v0 = 0;
  cbData = 0;
  Type = 0;
  Data = 0;
  hKey = 0;
  if ( (xmmword_18001E1E0 & 0x10) != 0 )
    WPP_SF_(1028, 26, WPP_94d5010c5674399d06148e3a91870046_Traceguids);
  v2 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Services\\Tcpip\\Parameters", 0, 1u, &hKey);
  if ( !v2 )
  {
    cbData = 4;
    v2 = RegQueryValueExW(hKey, L"PortTrackerEnabledMode", 0, &Type, (LPBYTE)&Data, &cbData);
    if ( !v2 )
    {
      if ( Type == 4 )
      {
        v2 = 0;
        LOBYTE(v0) = Data == 1;
      }
      else
      {
        v2 = 87;
      }
    }
  }
  v4 = hKey;
  if ( hKey )
    RegCloseKey(hKey);
  if ( (xmmword_18001E1E0 & 0x10) != 0 )
    WPP_SF_lD(v4, v1, v3, v0, v2);
  return v0;
}

```

## disassembly

```asm
0x180004070  push    rbx
0x180004072  push    rsi
0x180004073  push    rdi
0x180004074  sub     rsp, 30h
0x180004078  xor     esi, esi
0x18000407a  mov     ebx, esi
0x18000407c  mov     [rsp+48h+cbData], esi
0x180004080  mov     [rsp+48h+Type], esi
0x180004084  mov     [rsp+48h+Data], esi
0x180004088  mov     [rsp+48h+hKey], rsi
0x18000408d  test    byte ptr cs:xmmword_18001E1E0, 10h
0x180004094  jz      short loc_1800040AC
0x180004096  mov     edx, 1Ah
0x18000409b  lea     r8, WPP_94d5010c5674399d06148e3a91870046_Traceguids
0x1800040a2  mov     ecx, 404h
0x1800040a7  call    WPP_SF_
0x1800040ac  lea     rax, [rsp+48h+hKey]
0x1800040b1  mov     r9d, 1; samDesired
0x1800040b7  xor     r8d, r8d; ulOptions
0x1800040ba  mov     [rsp+48h+phkResult], rax; phkResult
0x1800040bf  lea     rdx, aSystemCurrentc; "System\\CurrentControlSet\\Services\\Tc"...
0x1800040c6  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800040cd  call    cs:__imp_RegOpenKeyExW
0x1800040d3  mov     edi, eax
0x1800040d5  test    eax, eax
0x1800040d7  jnz     short loc_18000412D
0x1800040d9  mov     rcx, [rsp+48h+hKey]; hKey
0x1800040de  lea     rax, [rsp+48h+cbData]
0x1800040e3  mov     [rsp+48h+lpcbData], rax; lpcbData
0x1800040e8  lea     r9, [rsp+48h+Type]; lpType
0x1800040ed  lea     rax, [rsp+48h+Data]
0x1800040f2  mov     [rsp+48h+cbData], 4
0x1800040fa  xor     r8d, r8d; lpReserved
0x1800040fd  mov     [rsp+48h+phkResult], rax; lpData
0x180004102  lea     rdx, aPorttrackerena; "PortTrackerEnabledMode"
0x180004109  call    cs:__imp_RegQueryValueExW
0x18000410f  mov     edi, eax
0x180004111  test    eax, eax
0x180004113  jnz     short loc_18000412D
0x180004115  cmp     [rsp+48h+Type], 4
0x18000411a  jz      short loc_180004123
0x18000411c  mov     edi, 57h ; 'W'
0x180004121  jmp     short loc_18000412D
0x180004123  cmp     [rsp+48h+Data], 1
0x180004128  mov     edi, esi
0x18000412a  setz    bl
0x18000412d  mov     rcx, [rsp+48h+hKey]; hKey
0x180004132  test    rcx, rcx
0x180004135  jz      short loc_18000413D
0x180004137  call    cs:__imp_RegCloseKey
0x18000413d  test    byte ptr cs:xmmword_18001E1E0, 10h
0x180004144  jz      short loc_180004152
0x180004146  mov     r9d, ebx
0x180004149  mov     dword ptr [rsp+48h+phkResult], edi
0x18000414d  call    WPP_SF_lD
0x180004152  mov     eax, ebx
0x180004154  add     rsp, 30h
0x180004158  pop     rdi
0x180004159  pop     rsi
0x18000415a  pop     rbx
0x18000415b  retn
```
