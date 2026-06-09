# SetRegistryClassIdv6

- ea: `0x18002ad18`
- end: `0x18002ae74`
- name: `SetRegistryClassIdv6`
- size: `348`
- prototype: `__int64 __fastcall(int, __int64, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, service_task`

## callers

- `0x180029fe4`

## callees

- `0x180009f58`
- `0x18000c740`
- `0x180016adc`
- `0x18002ab74`
- `0x18002ad18`
- `0x1800338c0`
- `0x180033c4c`

## string_xrefs

- `0x18002ade9`: `System\CurrentControlSet\Services\Tcpip6\Parameters\Interfaces\?\Dhcpv6ClassId`
- `0x18002adde`: `System\CurrentControlSet\Services\Dhcp\Parametersv6\Dhcp6ClientClassLocation`
- `0x18002ae1c`: `System\CurrentControlSet\Services\Tcpip6\Parameters\Interfaces\?\Dhcpv6ClassIdBin`

## pseudocode

```c
__int64 __fastcall SetRegistryClassIdv6(int a1, __int64 a2, __int64 a3)
{
  DWORD v3; // edi
  DWORD v4; // r14d
  _BOOL8 v6; // rcx
  unsigned int v7; // ebx
  int IsWCOSSystem; // eax
  wchar_t *v9; // r12
  wchar_t *v10; // rcx
  LPVOID v12; // [rsp+78h] [rbp+10h] BYREF
  DWORD v13; // [rsp+80h] [rbp+18h] BYREF

  v3 = a3;
  v4 = 0;
  v12 = 0;
  v13 = 0;
  if ( (xmmword_1800423E0 & 0x10) != 0 )
    WPP_SF_Sqd(a1, 16, (unsigned int)WPP_96fa1a2bf2273733f8a7cb3146f56f72_Traceguids, a1, a2, a3);
  v6 = a2 == 0;
  if ( v6 != (v3 == 0) )
    goto LABEL_4;
  if ( !a2 )
    goto LABEL_10;
  if ( v3 < 2 || (v3 & 1) != 0 )
  {
LABEL_4:
    v7 = 87;
    goto LABEL_16;
  }
  v7 = ConvertClassIdv6NameToBin(v6, a2, a3, &v12, &v13);
  if ( !v7 )
  {
    v4 = v13;
LABEL_10:
    IsWCOSSystem = DhcpIsWCOSSystem();
    v9 = L"OSDATA\\Networking\\Dhcp\\Client6\\Dhcp6ClientClassLocation";
    v10 = L"OSDATA\\Networking\\Dhcp\\Client6\\Dhcp6ClientClassLocation";
    if ( !IsWCOSSystem )
      v10 = L"System\\CurrentControlSet\\Services\\Dhcp\\Parametersv6\\Dhcp6ClientClassLocation";
    v7 = SetClassIdForLocation(
           v10,
           L"System\\CurrentControlSet\\Services\\Tcpip6\\Parameters\\Interfaces\\?\\Dhcpv6ClassId",
           v3,
           1u);
    if ( !v7 )
    {
      if ( !(unsigned int)DhcpIsWCOSSystem() )
        v9 = L"System\\CurrentControlSet\\Services\\Dhcp\\Parametersv6\\Dhcp6ClientClassLocation";
      v7 = SetClassIdForLocation(
             v9,
             L"System\\CurrentControlSet\\Services\\Tcpip6\\Parameters\\Interfaces\\?\\Dhcpv6ClassIdBin",
             v4,
             3u);
    }
  }
LABEL_16:
  DhcpFree(&v12);
  if ( (xmmword_1800423E0 & 0x10) != 0 )
    WPP_SF_D(1028, 17, WPP_96fa1a2bf2273733f8a7cb3146f56f72_Traceguids, v7);
  return v7;
}

```

## disassembly

```asm
0x18002ad18  mov     rax, rsp
0x18002ad1b  mov     [rax+8], rbx
0x18002ad1f  push    rbp
0x18002ad20  push    rsi
0x18002ad21  push    rdi
0x18002ad22  push    r12
0x18002ad24  push    r13
0x18002ad26  push    r14
0x18002ad28  push    r15
0x18002ad2a  sub     rsp, 30h
0x18002ad2e  xor     ebp, ebp
0x18002ad30  mov     edi, r8d
0x18002ad33  xor     r14d, r14d
0x18002ad36  mov     [rax+10h], rbp
0x18002ad3a  mov     [rax+18h], r14d
0x18002ad3e  mov     rsi, rdx
0x18002ad41  mov     r15, rcx
0x18002ad44  test    byte ptr cs:xmmword_1800423E0, 10h
0x18002ad4b  jz      short loc_18002AD67
0x18002ad4d  mov     [rax-40h], r8d
0x18002ad51  lea     edx, [rbp+10h]
0x18002ad54  lea     r8, WPP_96fa1a2bf2273733f8a7cb3146f56f72_Traceguids
0x18002ad5b  mov     [rax-48h], rsi
0x18002ad5f  mov     r9, rcx
0x18002ad62  call    WPP_SF_Sqd
0x18002ad67  xor     ecx, ecx
0x18002ad69  test    rsi, rsi
0x18002ad6c  setz    cl
0x18002ad6f  xor     eax, eax
0x18002ad71  test    edi, edi
0x18002ad73  setz    al
0x18002ad76  cmp     ecx, eax
0x18002ad78  jz      short loc_18002AD84
0x18002ad7a  mov     ebx, 57h ; 'W'
0x18002ad7f  jmp     loc_18002AE30
0x18002ad84  test    rsi, rsi
0x18002ad87  jz      short loc_18002ADC1
0x18002ad89  cmp     edi, 2
0x18002ad8c  jb      short loc_18002AD7A
0x18002ad8e  test    dil, 1
0x18002ad92  jnz     short loc_18002AD7A
0x18002ad94  lea     rax, [rsp+68h+arg_10]
0x18002ad9c  mov     rdx, rsi
0x18002ad9f  lea     r9, [rsp+68h+arg_8]
0x18002ada4  mov     qword ptr [rsp+68h+var_48], rax
0x18002ada9  call    ConvertClassIdv6NameToBin
0x18002adae  mov     ebx, eax
0x18002adb0  test    eax, eax
0x18002adb2  jnz     short loc_18002AE30
0x18002adb4  mov     rbp, [rsp+68h+arg_8]
0x18002adb9  mov     r14d, [rsp+68h+arg_10]
0x18002adc1  call    DhcpIsWCOSSystem
0x18002adc6  test    eax, eax
0x18002adc8  mov     [rsp+68h+dwType], 1; dwType
0x18002add0  lea     r12, aOsdataNetworki_0; "OSDATA\\Networking\\Dhcp\\Client6\\Dhcp"...
0x18002add7  mov     [rsp+68h+var_48], edi; DWORD
0x18002addb  mov     rcx, r12
0x18002adde  lea     r13, aSystemCurrentc_7; "System\\CurrentControlSet\\Services\\Dh"...
0x18002ade5  cmovz   rcx, r13; Src
0x18002ade9  lea     rdx, aSystemCurrentc_6; "System\\CurrentControlSet\\Services\\Tc"...
0x18002adf0  mov     r9, rsi
0x18002adf3  mov     r8, r15
0x18002adf6  call    SetClassIdForLocation
0x18002adfb  mov     ebx, eax
0x18002adfd  test    eax, eax
0x18002adff  jnz     short loc_18002AE30
0x18002ae01  call    DhcpIsWCOSSystem
0x18002ae06  test    eax, eax
0x18002ae08  mov     [rsp+68h+dwType], 3; dwType
0x18002ae10  mov     r9, rbp
0x18002ae13  mov     [rsp+68h+var_48], r14d; DWORD
0x18002ae18  cmovz   r12, r13
0x18002ae1c  lea     rdx, aSystemCurrentc_9; "System\\CurrentControlSet\\Services\\Tc"...
0x18002ae23  mov     rcx, r12; Src
0x18002ae26  mov     r8, r15
0x18002ae29  call    SetClassIdForLocation
0x18002ae2e  mov     ebx, eax
0x18002ae30  lea     rcx, [rsp+68h+arg_8]
0x18002ae35  call    DhcpFree
0x18002ae3a  test    byte ptr cs:xmmword_1800423E0, 10h
0x18002ae41  jz      short loc_18002AE5C
0x18002ae43  mov     edx, 11h
0x18002ae48  lea     r8, WPP_96fa1a2bf2273733f8a7cb3146f56f72_Traceguids
0x18002ae4f  mov     ecx, 404h
0x18002ae54  mov     r9d, ebx
0x18002ae57  call    WPP_SF_D
0x18002ae5c  mov     eax, ebx
0x18002ae5e  mov     rbx, [rsp+68h+arg_0]
0x18002ae63  add     rsp, 30h
0x18002ae67  pop     r15
0x18002ae69  pop     r14
0x18002ae6b  pop     r13
0x18002ae6d  pop     r12
0x18002ae6f  pop     rdi
0x18002ae70  pop     rsi
0x18002ae71  pop     rbp
0x18002ae72  retn
```
