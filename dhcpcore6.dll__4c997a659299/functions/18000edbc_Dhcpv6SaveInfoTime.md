# Dhcpv6SaveInfoTime

- ea: `0x18000edbc`
- end: `0x18000ee84`
- name: `Dhcpv6SaveInfoTime`
- size: `200`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180008a70`

## callees

- `0x18000edbc`
- `0x18003176c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000ee26`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000ee26`

## pseudocode

```c
__int64 __fastcall Dhcpv6SaveInfoTime(__int64 a1)
{
  unsigned int v1; // esi
  __int64 v2; // rdi
  __int64 v4; // rbx
  int v5; // ecx
  LSTATUS v6; // r14d
  LPCWSTR lpValueName; // [rsp+30h] [rbp-48h]
  _DWORD v9[2]; // [rsp+38h] [rbp-40h] BYREF
  const WCHAR *v10; // [rsp+40h] [rbp-38h]
  int v11; // [rsp+48h] [rbp-30h]

  v1 = 0;
  lpValueName = L"Dhcpv6InformationObtainedTime";
  v2 = 0;
  v9[0] = *(_DWORD *)(a1 + 8960);
  v4 = 0;
  v10 = L"Dhcpv6InformationRefreshTime";
  v11 = *(_DWORD *)(a1 + 8968);
  do
  {
    v6 = RegSetValueExW(*(HKEY *)(a1 + 648), *(LPCWSTR *)&v9[v4 - 2], 0, 4u, (const BYTE *)&v9[v4], 4u);
    if ( v6 )
    {
      if ( (xmmword_1800423E0 & 2) != 0 )
        WPP_SF_SDS(
          v5,
          45,
          (unsigned int)WPP_ec2a5d0085f33850f7877cb54422e2ef_Traceguids,
          *(_QWORD *)&v9[v4 - 2],
          v6,
          *(_QWORD *)(a1 + 56));
      v1 = v6;
    }
    ++v2;
    v4 += 4;
  }
  while ( v2 != 2 );
  return v1;
}

```

## disassembly

```asm
0x18000edbc  push    rbx
0x18000edbe  push    rbp
0x18000edbf  push    rsi
0x18000edc0  push    rdi
0x18000edc1  push    r14
0x18000edc3  sub     rsp, 50h
0x18000edc7  lea     rax, aDhcpv6informat_0; "Dhcpv6InformationObtainedTime"
0x18000edce  xor     esi, esi
0x18000edd0  mov     [rsp+78h+lpValueName], rax
0x18000edd5  xor     edi, edi
0x18000edd7  mov     eax, [rcx+2300h]
0x18000eddd  mov     rbp, rcx
0x18000ede0  mov     [rsp+78h+var_40], eax
0x18000ede4  xor     ebx, ebx
0x18000ede6  lea     rax, aDhcpv6informat; "Dhcpv6InformationRefreshTime"
0x18000eded  mov     [rsp+78h+var_38], rax
0x18000edf2  mov     eax, [rcx+2308h]
0x18000edf8  mov     [rsp+78h+var_30], eax
0x18000edfc  mov     rdx, [rsp+rbx+78h+lpValueName]; lpValueName
0x18000ee01  lea     rax, [rsp+78h+var_40]
0x18000ee06  mov     rcx, [rbp+288h]; hKey
0x18000ee0d  add     rax, rbx
0x18000ee10  mov     [rsp+78h+cbData], 4; cbData
0x18000ee18  mov     r9d, 4; dwType
0x18000ee1e  xor     r8d, r8d; Reserved
0x18000ee21  mov     [rsp+78h+lpData], rax; lpData
0x18000ee26  call    cs:__imp_RegSetValueExW
0x18000ee2d  nop     dword ptr [rax+rax+00h]
0x18000ee32  mov     r14d, eax
0x18000ee35  test    eax, eax
0x18000ee37  jz      short loc_18000EE69
0x18000ee39  test    byte ptr cs:xmmword_1800423E0, 2
0x18000ee40  jz      short loc_18000EE66
0x18000ee42  mov     rax, [rbp+38h]
0x18000ee46  lea     r8, WPP_ec2a5d0085f33850f7877cb54422e2ef_Traceguids
0x18000ee4d  mov     r9, [rsp+rbx+78h+lpValueName]
0x18000ee52  mov     edx, 2Dh ; '-'
0x18000ee57  mov     qword ptr [rsp+78h+cbData], rax
0x18000ee5c  mov     dword ptr [rsp+78h+lpData], r14d
0x18000ee61  call    WPP_SF_SDS
0x18000ee66  mov     esi, r14d
0x18000ee69  inc     rdi
0x18000ee6c  add     rbx, 10h
0x18000ee70  cmp     rdi, 2
0x18000ee74  jnz     short loc_18000EDFC
0x18000ee76  mov     eax, esi
0x18000ee78  add     rsp, 50h
0x18000ee7c  pop     r14
0x18000ee7e  pop     rdi
0x18000ee7f  pop     rsi
0x18000ee80  pop     rbp
0x18000ee81  pop     rbx
0x18000ee82  retn
```
