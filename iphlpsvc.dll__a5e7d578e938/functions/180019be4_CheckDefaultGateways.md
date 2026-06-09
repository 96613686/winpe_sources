# CheckDefaultGateways

- ea: `0x180019be4`
- end: `0x180019de6`
- name: `CheckDefaultGateways`
- size: `514`
- prototype: `char()`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x1800197a0`
- `0x18002ffa0`

## callees

- `0x18000d7c0`
- `0x180019be4`
- `0x18001b824`
- `0x18003451c`
- `0x1800383b4`
- `0x18004b5f0`
- `0x18004c188`
- `0x180053f5c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180019da3`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180019da3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180019dc4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180019dc4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180019c99`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180019c99`
- `IPHLPAPI!GetIpForwardTable2` at `0x180019d10`
- `IPHLPAPI!GetIpForwardTable2` at `0x180019d10`
- `IPHLPAPI!FreeMibTable` at `0x180019dd5`
- `IPHLPAPI!FreeMibTable` at `0x180019dd5`

## string_xrefs

- `0x180019c88`: `System\CurrentControlSet\Services\iphlpsvc\Diagnostics`
- `0x180019cac`: `System\CurrentControlSet\Services\iphlpsvc\Diagnostics`
- `0x180019cb3`: `Unable to open key %s. Error %u`

## pseudocode

```c
char CheckDefaultGateways()
{
  char result; // al
  unsigned int v1; // edi
  unsigned int v2; // eax
  ULONG i; // ebx
  __int64 v4; // rdx
  ULONG cbInput; // [rsp+30h] [rbp-D0h] BYREF
  DWORD cbData; // [rsp+34h] [rbp-CCh] BYREF
  BYTE Data[8]; // [rsp+38h] [rbp-C8h] BYREF
  HKEY hKey; // [rsp+40h] [rbp-C0h] BYREF
  DWORD Type; // [rsp+48h] [rbp-B8h] BYREF
  PMIB_IPFORWARD_TABLE2 Table; // [rsp+50h] [rbp-B0h] BYREF
  UCHAR pbInput[40]; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR ValueName[72]; // [rsp+80h] [rbp-80h] BYREF

  Type = 0;
  cbData = 0;
  *(_DWORD *)Data = 0;
  memset_0(ValueName, 0, 0x82u);
  cbInput = 0;
  Table = 0;
  hKey = 0;
  result = AdminConfiguredAutoTuning(2);
  if ( !result )
  {
    result = AdminConfiguredAutoTuning(23);
    if ( !result )
    {
      hKey = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
      v1 = 3;
      v2 = RegOpenKeyExW(
             HKEY_LOCAL_MACHINE,
             L"System\\CurrentControlSet\\Services\\iphlpsvc\\Diagnostics",
             0,
             0x2001Fu,
             &hKey);
      if ( v2 )
      {
        EventWrite0(
          0x100000,
          L"Unable to open key %s. Error %u",
          L"System\\CurrentControlSet\\Services\\iphlpsvc\\Diagnostics",
          v2);
      }
      else if ( !GetIpForwardTable2(2u, &Table) )
      {
        for ( i = 0; i < Table->NumEntries; ++i )
        {
          v4 = i;
          if ( !Table->Table[v4].DestinationPrefix.PrefixLength
            && !(unsigned int)GetPhysicalAddressForNextHopAddress(&Table->Table[v4].NextHop, 0, &cbInput, pbInput) )
          {
            if ( (unsigned int)GenerateHashKey(cbInput, pbInput) )
              break;
            ValueName[31] = 0;
            cbData = 4;
            if ( !RegQueryValueExW(hKey, ValueName, 0, &Type, Data, &cbData) )
              v1 &= -(*(_DWORD *)Data != 0);
          }
        }
      }
      if ( hKey )
        RegCloseKey(hKey);
      if ( Table )
        FreeMibTable(Table);
      return UpdateWindowScalingLevel(v1);
    }
  }
  return result;
}

```

## disassembly

```asm
0x180019be4  mov     [rsp-8+arg_0], rbx
0x180019be9  mov     [rsp-8+arg_8], rdi
0x180019bee  push    rbp
0x180019bef  lea     rbp, [rsp-20h]
0x180019bf4  sub     rsp, 120h
0x180019bfb  mov     rax, cs:__security_cookie
0x180019c02  xor     rax, rsp
0x180019c05  mov     [rbp+20h+var_10], rax
0x180019c09  xor     edx, edx; Val
0x180019c0b  mov     [rsp+120h+Type], 0
0x180019c13  mov     r8d, 82h; Size
0x180019c19  mov     [rsp+120h+cbData], 0
0x180019c21  lea     rcx, [rbp+20h+ValueName]; void *
0x180019c25  mov     dword ptr [rsp+120h+Data], 0
0x180019c2d  call    memset_0
0x180019c32  mov     ebx, 2
0x180019c37  mov     [rsp+120h+cbInput], 0
0x180019c3f  mov     ecx, ebx
0x180019c41  mov     [rsp+120h+Table], 0
0x180019c4a  mov     [rsp+120h+hKey], 0
0x180019c53  call    AdminConfiguredAutoTuning
0x180019c58  test    al, al
0x180019c5a  jnz     loc_180019CE7
0x180019c60  lea     ecx, [rbx+15h]
0x180019c63  call    AdminConfiguredAutoTuning
0x180019c68  test    al, al
0x180019c6a  jnz     short loc_180019CE7
0x180019c6c  lea     rax, [rsp+120h+hKey]
0x180019c71  mov     [rsp+120h+hKey], 0FFFFFFFFFFFFFFFFh
0x180019c7a  mov     r9d, 2001Fh; samDesired
0x180019c80  mov     [rsp+120h+phkResult], rax; phkResult
0x180019c85  xor     r8d, r8d; ulOptions
0x180019c88  lea     rdx, aSystemCurrentc_11; "System\\CurrentControlSet\\Services\\ip"...
0x180019c8f  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180019c96  lea     edi, [rbx+1]
0x180019c99  call    cs:__imp_RegOpenKeyExW
0x180019ca0  nop     dword ptr [rax+rax+00h]
0x180019ca5  test    eax, eax
0x180019ca7  jz      short loc_180019D09
0x180019ca9  mov     r9d, eax
0x180019cac  lea     r8, aSystemCurrentc_11; "System\\CurrentControlSet\\Services\\ip"...
0x180019cb3  lea     rdx, aUnableToOpenKe; "Unable to open key %s. Error %u"
0x180019cba  mov     ecx, 100000h
0x180019cbf  call    EventWrite0
0x180019cc4  mov     rcx, [rsp+120h+hKey]; hKey
0x180019cc9  test    rcx, rcx
0x180019ccc  jnz     loc_180019DC4
0x180019cd2  mov     rcx, [rsp+120h+Table]; Memory
0x180019cd7  test    rcx, rcx
0x180019cda  jnz     loc_180019DD5
0x180019ce0  mov     ecx, edi
0x180019ce2  call    UpdateWindowScalingLevel
0x180019ce7  mov     rcx, [rbp+20h+var_10]
0x180019ceb  xor     rcx, rsp; StackCookie
0x180019cee  call    __security_check_cookie
0x180019cf3  lea     r11, [rsp+120h+var_s0]
0x180019cfb  mov     rbx, [r11+10h]
0x180019cff  mov     rdi, [r11+18h]
0x180019d03  mov     rsp, r11
0x180019d06  pop     rbp
0x180019d07  retn
0x180019d09  mov     ecx, ebx; Family
0x180019d0b  lea     rdx, [rsp+120h+Table]; Table
0x180019d10  call    cs:__imp_GetIpForwardTable2
0x180019d17  nop     dword ptr [rax+rax+00h]
0x180019d1c  test    eax, eax
0x180019d1e  jnz     short loc_180019CC4
0x180019d20  xor     ebx, ebx
0x180019d22  mov     rcx, [rsp+120h+Table]
0x180019d27  cmp     ebx, [rcx]
0x180019d29  jnb     short loc_180019CC4
0x180019d2b  mov     eax, ebx
0x180019d2d  imul    rdx, rax, 68h ; 'h'
0x180019d31  cmp     byte ptr [rdx+rcx+30h], 0
0x180019d36  jnz     loc_180019DBD
0x180019d3c  add     rcx, 34h ; '4'
0x180019d40  lea     r9, [rsp+120h+pbInput]
0x180019d45  add     rcx, rdx
0x180019d48  lea     r8, [rsp+120h+cbInput]
0x180019d4d  xor     edx, edx
0x180019d4f  call    GetPhysicalAddressForNextHopAddress
0x180019d54  test    eax, eax
0x180019d56  jnz     short loc_180019DBD
0x180019d58  mov     ecx, [rsp+120h+cbInput]; cbInput
0x180019d5c  lea     r8, [rbp+20h+ValueName]
0x180019d60  lea     rdx, [rsp+120h+pbInput]; pbInput
0x180019d65  call    GenerateHashKey
0x180019d6a  test    eax, eax
0x180019d6c  jnz     loc_180019CC4
0x180019d72  mov     rcx, [rsp+120h+hKey]; hKey
0x180019d77  lea     r9, [rsp+120h+Type]; lpType
0x180019d7c  mov     [rbp+20h+var_62], ax
0x180019d80  lea     rdx, [rbp+20h+ValueName]; lpValueName
0x180019d84  lea     rax, [rsp+120h+cbData]
0x180019d89  mov     [rsp+120h+cbData], 4
0x180019d91  mov     [rsp+120h+lpcbData], rax; lpcbData
0x180019d96  xor     r8d, r8d; lpReserved
0x180019d99  lea     rax, [rsp+120h+Data]
0x180019d9e  mov     [rsp+120h+phkResult], rax; lpData
0x180019da3  call    cs:__imp_RegQueryValueExW
0x180019daa  nop     dword ptr [rax+rax+00h]
0x180019daf  test    eax, eax
0x180019db1  jnz     short loc_180019DBD
0x180019db3  mov     eax, dword ptr [rsp+120h+Data]
0x180019db7  neg     eax
0x180019db9  sbb     ecx, ecx
0x180019dbb  and     edi, ecx
0x180019dbd  inc     ebx
0x180019dbf  jmp     loc_180019D22
0x180019dc4  call    cs:__imp_RegCloseKey
0x180019dcb  nop     dword ptr [rax+rax+00h]
0x180019dd0  jmp     loc_180019CD2
0x180019dd5  call    cs:__imp_FreeMibTable
0x180019ddc  nop     dword ptr [rax+rax+00h]
0x180019de1  jmp     loc_180019CE0
```
