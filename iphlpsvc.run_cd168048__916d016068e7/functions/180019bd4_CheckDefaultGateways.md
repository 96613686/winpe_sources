# CheckDefaultGateways

- ea: `0x180019bd4`
- end: `0x180019dd6`
- name: `CheckDefaultGateways`
- size: `514`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x180019790`
- `0x18002ff90`

## callees

- `0x18000d7b0`
- `0x180019bd4`
- `0x18001b814`
- `0x18003450c`
- `0x1800383a4`
- `0x18004b630`
- `0x18004c1c8`
- `0x180053f38`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180019d93`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180019d93`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180019db4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180019db4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180019c89`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180019c89`
- `IPHLPAPI!GetIpForwardTable2` at `0x180019d00`
- `IPHLPAPI!GetIpForwardTable2` at `0x180019d00`
- `IPHLPAPI!FreeMibTable` at `0x180019dc5`
- `IPHLPAPI!FreeMibTable` at `0x180019dc5`

## string_xrefs

- `0x180019c78`: `System\CurrentControlSet\Services\iphlpsvc\Diagnostics`
- `0x180019c9c`: `System\CurrentControlSet\Services\iphlpsvc\Diagnostics`
- `0x180019ca3`: `Unable to open key %s. Error %u`

## pseudocode

```c
__int64 CheckDefaultGateways()
{
  __int64 result; // rax
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
  if ( !(_BYTE)result )
  {
    result = AdminConfiguredAutoTuning(23);
    if ( !(_BYTE)result )
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
            if ( (unsigned int)GenerateHashKey(cbInput, pbInput, (__int64)ValueName) )
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
0x180019bd4  mov     [rsp-8+arg_0], rbx
0x180019bd9  mov     [rsp-8+arg_8], rdi
0x180019bde  push    rbp
0x180019bdf  lea     rbp, [rsp-20h]
0x180019be4  sub     rsp, 120h
0x180019beb  mov     rax, cs:__security_cookie
0x180019bf2  xor     rax, rsp
0x180019bf5  mov     [rbp+20h+var_10], rax
0x180019bf9  xor     edx, edx; Val
0x180019bfb  mov     [rsp+120h+Type], 0
0x180019c03  mov     r8d, 82h; Size
0x180019c09  mov     [rsp+120h+cbData], 0
0x180019c11  lea     rcx, [rbp+20h+ValueName]; void *
0x180019c15  mov     dword ptr [rsp+120h+Data], 0
0x180019c1d  call    memset_0
0x180019c22  mov     ebx, 2
0x180019c27  mov     [rsp+120h+cbInput], 0
0x180019c2f  mov     ecx, ebx
0x180019c31  mov     [rsp+120h+Table], 0
0x180019c3a  mov     [rsp+120h+hKey], 0
0x180019c43  call    AdminConfiguredAutoTuning
0x180019c48  test    al, al
0x180019c4a  jnz     loc_180019CD7
0x180019c50  lea     ecx, [rbx+15h]
0x180019c53  call    AdminConfiguredAutoTuning
0x180019c58  test    al, al
0x180019c5a  jnz     short loc_180019CD7
0x180019c5c  lea     rax, [rsp+120h+hKey]
0x180019c61  mov     [rsp+120h+hKey], 0FFFFFFFFFFFFFFFFh
0x180019c6a  mov     r9d, 2001Fh; samDesired
0x180019c70  mov     [rsp+120h+phkResult], rax; phkResult
0x180019c75  xor     r8d, r8d; ulOptions
0x180019c78  lea     rdx, aSystemCurrentc_11; "System\\CurrentControlSet\\Services\\ip"...
0x180019c7f  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180019c86  lea     edi, [rbx+1]
0x180019c89  call    cs:__imp_RegOpenKeyExW
0x180019c90  nop     dword ptr [rax+rax+00h]
0x180019c95  test    eax, eax
0x180019c97  jz      short loc_180019CF9
0x180019c99  mov     r9d, eax
0x180019c9c  lea     r8, aSystemCurrentc_11; "System\\CurrentControlSet\\Services\\ip"...
0x180019ca3  lea     rdx, aUnableToOpenKe; "Unable to open key %s. Error %u"
0x180019caa  mov     ecx, 100000h
0x180019caf  call    EventWrite0
0x180019cb4  mov     rcx, [rsp+120h+hKey]; hKey
0x180019cb9  test    rcx, rcx
0x180019cbc  jnz     loc_180019DB4
0x180019cc2  mov     rcx, [rsp+120h+Table]; Memory
0x180019cc7  test    rcx, rcx
0x180019cca  jnz     loc_180019DC5
0x180019cd0  mov     ecx, edi
0x180019cd2  call    UpdateWindowScalingLevel
0x180019cd7  mov     rcx, [rbp+20h+var_10]
0x180019cdb  xor     rcx, rsp; StackCookie
0x180019cde  call    __security_check_cookie
0x180019ce3  lea     r11, [rsp+120h+var_s0]
0x180019ceb  mov     rbx, [r11+10h]
0x180019cef  mov     rdi, [r11+18h]
0x180019cf3  mov     rsp, r11
0x180019cf6  pop     rbp
0x180019cf7  retn
0x180019cf9  mov     ecx, ebx; Family
0x180019cfb  lea     rdx, [rsp+120h+Table]; Table
0x180019d00  call    cs:__imp_GetIpForwardTable2
0x180019d07  nop     dword ptr [rax+rax+00h]
0x180019d0c  test    eax, eax
0x180019d0e  jnz     short loc_180019CB4
0x180019d10  xor     ebx, ebx
0x180019d12  mov     rcx, [rsp+120h+Table]
0x180019d17  cmp     ebx, [rcx]
0x180019d19  jnb     short loc_180019CB4
0x180019d1b  mov     eax, ebx
0x180019d1d  imul    rdx, rax, 68h ; 'h'
0x180019d21  cmp     byte ptr [rdx+rcx+30h], 0
0x180019d26  jnz     loc_180019DAD
0x180019d2c  add     rcx, 34h ; '4'
0x180019d30  lea     r9, [rsp+120h+pbInput]
0x180019d35  add     rcx, rdx
0x180019d38  lea     r8, [rsp+120h+cbInput]
0x180019d3d  xor     edx, edx
0x180019d3f  call    GetPhysicalAddressForNextHopAddress
0x180019d44  test    eax, eax
0x180019d46  jnz     short loc_180019DAD
0x180019d48  mov     ecx, [rsp+120h+cbInput]; cbInput
0x180019d4c  lea     r8, [rbp+20h+ValueName]
0x180019d50  lea     rdx, [rsp+120h+pbInput]; pbInput
0x180019d55  call    GenerateHashKey
0x180019d5a  test    eax, eax
0x180019d5c  jnz     loc_180019CB4
0x180019d62  mov     rcx, [rsp+120h+hKey]; hKey
0x180019d67  lea     r9, [rsp+120h+Type]; lpType
0x180019d6c  mov     [rbp+20h+var_62], ax
0x180019d70  lea     rdx, [rbp+20h+ValueName]; lpValueName
0x180019d74  lea     rax, [rsp+120h+cbData]
0x180019d79  mov     [rsp+120h+cbData], 4
0x180019d81  mov     [rsp+120h+lpcbData], rax; lpcbData
0x180019d86  xor     r8d, r8d; lpReserved
0x180019d89  lea     rax, [rsp+120h+Data]
0x180019d8e  mov     [rsp+120h+phkResult], rax; lpData
0x180019d93  call    cs:__imp_RegQueryValueExW
0x180019d9a  nop     dword ptr [rax+rax+00h]
0x180019d9f  test    eax, eax
0x180019da1  jnz     short loc_180019DAD
0x180019da3  mov     eax, dword ptr [rsp+120h+Data]
0x180019da7  neg     eax
0x180019da9  sbb     ecx, ecx
0x180019dab  and     edi, ecx
0x180019dad  inc     ebx
0x180019daf  jmp     loc_180019D12
0x180019db4  call    cs:__imp_RegCloseKey
0x180019dbb  nop     dword ptr [rax+rax+00h]
0x180019dc0  jmp     loc_180019CC2
0x180019dc5  call    cs:__imp_FreeMibTable
0x180019dcc  nop     dword ptr [rax+rax+00h]
0x180019dd1  jmp     loc_180019CD0
```
