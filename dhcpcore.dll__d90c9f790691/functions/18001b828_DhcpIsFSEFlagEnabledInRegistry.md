# DhcpIsFSEFlagEnabledInRegistry

- ea: `0x18001b828`
- end: `0x18001b915`
- name: `DhcpIsFSEFlagEnabledInRegistry`
- size: `237`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x18000a100`

## callees

- `0x18001b828`
- `0x18004d1e0`
- `0x18004dd28`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001b8df`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001b8df`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001b87f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001b87f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001b8b6`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001b8b6`

## string_xrefs

- `0x18001b871`: `System\CurrentControlSet\Services\Tcpip\Parameters`

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
  if ( (xmmword_1800616A0 & 0x10) != 0 )
    WPP_SF_(1028, 26, WPP_94d5010c5674399d06148e3a91870046_Traceguids);
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
  if ( (xmmword_1800616A0 & 0x10) != 0 )
    WPP_SF_Dd(1028, 27, WPP_94d5010c5674399d06148e3a91870046_Traceguids, v0, v1);
  return v0;
}

```

## disassembly

```asm
0x18001b828  push    rbp
0x18001b82a  push    rbx
0x18001b82b  push    rdi
0x18001b82c  mov     rbp, rsp
0x18001b82f  sub     rsp, 30h
0x18001b833  xor     ebx, ebx
0x18001b835  mov     [rbp+cbData], ebx
0x18001b838  mov     [rbp+Type], ebx
0x18001b83b  mov     [rbp+Data], ebx
0x18001b83e  mov     [rbp+hKey], rbx
0x18001b842  test    byte ptr cs:xmmword_1800616A0, 10h
0x18001b849  jz      short loc_18001B85F
0x18001b84b  lea     edx, [rbx+1Ah]
0x18001b84e  mov     ecx, 404h
0x18001b853  lea     r8, WPP_94d5010c5674399d06148e3a91870046_Traceguids
0x18001b85a  call    WPP_SF_
0x18001b85f  lea     rax, [rbp+hKey]
0x18001b863  mov     r9d, 1; samDesired
0x18001b869  xor     r8d, r8d; ulOptions
0x18001b86c  mov     [rsp+30h+phkResult], rax; phkResult
0x18001b871  lea     rdx, aSystemCurrentc_12; "System\\CurrentControlSet\\Services\\Tc"...
0x18001b878  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001b87f  call    cs:__imp_RegOpenKeyExW
0x18001b885  mov     edi, eax
0x18001b887  test    eax, eax
0x18001b889  jnz     short loc_18001B8D6
0x18001b88b  mov     rcx, [rbp+hKey]; hKey
0x18001b88f  lea     rax, [rbp+cbData]
0x18001b893  mov     [rsp+30h+lpcbData], rax; lpcbData
0x18001b898  lea     r9, [rbp+Type]; lpType
0x18001b89c  lea     rax, [rbp+Data]
0x18001b8a0  mov     [rbp+cbData], 4
0x18001b8a7  xor     r8d, r8d; lpReserved
0x18001b8aa  mov     [rsp+30h+phkResult], rax; lpData
0x18001b8af  lea     rdx, aPorttrackerena; "PortTrackerEnabledMode"
0x18001b8b6  call    cs:__imp_RegQueryValueExW
0x18001b8bc  mov     edi, eax
0x18001b8be  test    eax, eax
0x18001b8c0  jnz     short loc_18001B8D6
0x18001b8c2  cmp     [rbp+Type], 4
0x18001b8c6  jz      short loc_18001B8CD
0x18001b8c8  lea     edi, [rax+57h]
0x18001b8cb  jmp     short loc_18001B8D6
0x18001b8cd  xor     edi, edi
0x18001b8cf  cmp     [rbp+Data], 1
0x18001b8d3  setz    bl
0x18001b8d6  mov     rcx, [rbp+hKey]; hKey
0x18001b8da  test    rcx, rcx
0x18001b8dd  jz      short loc_18001B8E5
0x18001b8df  call    cs:__imp_RegCloseKey
0x18001b8e5  test    byte ptr cs:xmmword_1800616A0, 10h
0x18001b8ec  jz      short loc_18001B90B
0x18001b8ee  mov     edx, 1Bh
0x18001b8f3  mov     dword ptr [rsp+30h+phkResult], edi
0x18001b8f7  mov     ecx, 404h
0x18001b8fc  lea     r8, WPP_94d5010c5674399d06148e3a91870046_Traceguids
0x18001b903  mov     r9d, ebx
0x18001b906  call    WPP_SF_Dd
0x18001b90b  mov     eax, ebx
0x18001b90d  add     rsp, 30h
0x18001b911  pop     rdi
0x18001b912  pop     rbx
0x18001b913  pop     rbp
0x18001b914  retn
```
