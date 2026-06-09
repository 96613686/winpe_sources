# ConvertFromNonDhcpToStateful

- ea: `0x180013410`
- end: `0x18001356b`
- name: `ConvertFromNonDhcpToStateful`
- size: `347`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x180001d8c`
- `0x180004b30`
- `0x18000db84`
- `0x180013410`
- `0x180014590`
- `0x1800310e4`
- `0x1800337d0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800134a8`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800134a8`

## pseudocode

```c
__int64 __fastcall ConvertFromNonDhcpToStateful(__int64 a1)
{
  _QWORD *v2; // rsi
  HKEY v3; // rcx
  int v4; // ecx
  _DWORD *v5; // rax
  unsigned int v6; // eax
  __int64 v7; // rcx
  unsigned int v8; // edi
  int Data; // [rsp+40h] [rbp+8h] BYREF

  Data = 0;
  v2 = (_QWORD *)(a1 + 56);
  if ( (xmmword_1800423E0 & 0x10) != 0 )
  {
    WPP_SF_S(1028, 311, WPP_d400c6d7dc7d3cccc0799e5e1f792179_Traceguids, *v2);
    if ( (xmmword_1800423E0 & 0x10) != 0 )
      WPP_SF_S(1028, 312, WPP_d400c6d7dc7d3cccc0799e5e1f792179_Traceguids, *v2);
  }
  Dhcpv6DeleteRegValues(a1);
  v3 = *(HKEY *)(a1 + 648);
  Data = 1;
  RegSetValueExW(v3, L"Dhcpv6State", 0, 4u, (const BYTE *)&Data, 4u);
  v4 = g_fVelocityDhcpv6ContextBitfieldUpdate;
  *(_QWORD *)(a1 + 576) = ReSolicitParameters;
  v5 = (_DWORD *)(a1 + 8860);
  *(_QWORD *)(a1 + 8928) = 0;
  if ( v4 )
    *(_DWORD *)(a1 + 8876) = 1;
  else
    *v5 |= 0x10u;
  if ( v4 )
    *(_DWORD *)(a1 + 8880) = 0;
  else
    *v5 &= ~0x20u;
  v6 = ReSolicitParameters(a1);
  v8 = v6;
  if ( (xmmword_1800423E0 & 2) != 0 )
    WPP_SF_SDJ(
      *(_QWORD *)(a1 + 24),
      313,
      (unsigned int)WPP_d400c6d7dc7d3cccc0799e5e1f792179_Traceguids,
      *v2,
      v6,
      *(_QWORD *)(a1 + 24));
  if ( (Microsoft_Windows_DHCPv6_ClientEnableBits & 1) != 0 )
    McTemplateU0qq_EtwEventWriteTransfer(v7, NondhcpToStateful, *(unsigned int *)(a1 + 48), v8);
  TraceLogErrorv6(a1, v8, 81);
  return v8;
}

```

## disassembly

```asm
0x180013410  mov     [rsp+arg_8], rbx
0x180013415  mov     [rsp+arg_10], rsi
0x18001341a  push    rdi
0x18001341b  sub     rsp, 30h
0x18001341f  xor     edi, edi
0x180013421  mov     rbx, rcx
0x180013424  mov     [rsp+38h+Data], edi
0x180013428  mov     al, byte ptr cs:xmmword_1800423E0
0x18001342e  lea     rsi, [rcx+38h]
0x180013432  test    al, 10h
0x180013434  jz      short loc_180013472
0x180013436  mov     r9, [rsi]
0x180013439  lea     r8, WPP_d400c6d7dc7d3cccc0799e5e1f792179_Traceguids
0x180013440  mov     edx, 137h
0x180013445  mov     ecx, 404h
0x18001344a  call    WPP_SF_S
0x18001344f  mov     al, byte ptr cs:xmmword_1800423E0
0x180013455  test    al, 10h
0x180013457  jz      short loc_180013472
0x180013459  mov     r9, [rsi]
0x18001345c  lea     r8, WPP_d400c6d7dc7d3cccc0799e5e1f792179_Traceguids
0x180013463  mov     edx, 138h
0x180013468  mov     ecx, 404h
0x18001346d  call    WPP_SF_S
0x180013472  mov     rcx, rbx
0x180013475  call    Dhcpv6DeleteRegValues
0x18001347a  mov     rcx, [rbx+288h]; hKey
0x180013481  lea     rax, [rsp+38h+Data]
0x180013486  mov     r9d, 4; dwType
0x18001348c  mov     [rsp+38h+Data], 1
0x180013494  mov     [rsp+38h+cbData], r9d; cbData
0x180013499  lea     rdx, aDhcpv6state; "Dhcpv6State"
0x1800134a0  xor     r8d, r8d; Reserved
0x1800134a3  mov     [rsp+38h+lpData], rax; lpData
0x1800134a8  call    cs:__imp_RegSetValueExW
0x1800134af  nop     dword ptr [rax+rax+00h]
0x1800134b4  mov     ecx, cs:g_fVelocityDhcpv6ContextBitfieldUpdate
0x1800134ba  lea     rax, ReSolicitParameters
0x1800134c1  mov     [rbx+240h], rax
0x1800134c8  lea     rax, [rbx+229Ch]
0x1800134cf  mov     [rbx+22E0h], rdi
0x1800134d6  test    ecx, ecx
0x1800134d8  jz      short loc_1800134E6
0x1800134da  mov     dword ptr [rbx+22ACh], 1
0x1800134e4  jmp     short loc_1800134E9
0x1800134e6  or      dword ptr [rax], 10h
0x1800134e9  test    ecx, ecx
0x1800134eb  jz      short loc_1800134F5
0x1800134ed  mov     [rbx+22B0h], edi
0x1800134f3  jmp     short loc_1800134F8
0x1800134f5  and     dword ptr [rax], 0FFFFFFDFh
0x1800134f8  mov     rcx, rbx; int
0x1800134fb  call    ReSolicitParameters
0x180013500  mov     edi, eax
0x180013502  test    byte ptr cs:xmmword_1800423E0, 2
0x180013509  jz      short loc_18001352C
0x18001350b  mov     rcx, [rbx+18h]
0x18001350f  lea     r8, WPP_d400c6d7dc7d3cccc0799e5e1f792179_Traceguids
0x180013516  mov     r9, [rsi]
0x180013519  mov     edx, 139h
0x18001351e  mov     qword ptr [rsp+38h+cbData], rcx
0x180013523  mov     dword ptr [rsp+38h+lpData], eax
0x180013527  call    WPP_SF_SDJ
0x18001352c  test    byte ptr cs:Microsoft_Windows_DHCPv6_ClientEnableBits, 1
0x180013533  jz      short loc_180013548
0x180013535  mov     r8d, [rbx+30h]
0x180013539  lea     rdx, NondhcpToStateful
0x180013540  mov     r9d, edi
0x180013543  call    McTemplateU0qq_EtwEventWriteTransfer
0x180013548  mov     r8d, 51h ; 'Q'
0x18001354e  mov     edx, edi
0x180013550  mov     rcx, rbx
0x180013553  call    TraceLogErrorv6
0x180013558  mov     rbx, [rsp+38h+arg_8]
0x18001355d  mov     eax, edi
0x18001355f  mov     rsi, [rsp+38h+arg_10]
0x180013564  add     rsp, 30h
0x180013568  pop     rdi
0x180013569  retn
```
