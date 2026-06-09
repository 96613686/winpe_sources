# ConvertFromNonDhcpToStateless

- ea: `0x180013580`
- end: `0x1800136f9`
- name: `ConvertFromNonDhcpToStateless`
- size: `377`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x180001894`
- `0x180004b30`
- `0x180008a70`
- `0x18000db84`
- `0x180013580`
- `0x1800310e4`
- `0x1800337d0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180013619`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180013619`

## pseudocode

```c
__int64 __fastcall ConvertFromNonDhcpToStateless(__int64 a1)
{
  _QWORD *v2; // rsi
  HKEY v3; // rcx
  int v4; // ecx
  _DWORD *v5; // rax
  unsigned int v6; // eax
  unsigned int v7; // edi
  int Data; // [rsp+40h] [rbp+8h] BYREF

  Data = 0;
  v2 = (_QWORD *)(a1 + 56);
  if ( (xmmword_1800423E0 & 0x10) != 0 )
  {
    WPP_SF_S(1028, 314, WPP_d400c6d7dc7d3cccc0799e5e1f792179_Traceguids, *v2);
    if ( (xmmword_1800423E0 & 0x10) != 0 )
      WPP_SF_S(1028, 315, WPP_d400c6d7dc7d3cccc0799e5e1f792179_Traceguids, *v2);
  }
  Dhcpv6DeleteRegValues(a1);
  v3 = *(HKEY *)(a1 + 648);
  Data = 2;
  RegSetValueExW(v3, L"Dhcpv6State", 0, 4u, (const BYTE *)&Data, 4u);
  v4 = g_fVelocityDhcpv6ContextBitfieldUpdate;
  *(_QWORD *)(a1 + 576) = ReConfigureParams;
  v5 = (_DWORD *)(a1 + 8860);
  if ( v4 )
    *(_DWORD *)(a1 + 8876) = 1;
  else
    *v5 |= 0x10u;
  if ( v4 )
    *(_DWORD *)(a1 + 8880) = 1;
  else
    *v5 |= 0x20u;
  *(_DWORD *)(a1 + 496) = 0;
  v6 = ReConfigureParams(a1);
  v7 = v6;
  if ( (xmmword_1800423E0 & 2) != 0 )
    WPP_SF_SDJ(
      *(_QWORD *)(a1 + 24),
      316,
      (unsigned int)WPP_d400c6d7dc7d3cccc0799e5e1f792179_Traceguids,
      *v2,
      v6,
      *(_QWORD *)(a1 + 24));
  if ( (Microsoft_Windows_DHCPv6_ClientEnableBits & 1) != 0 )
    McTemplateU0qqqq_EtwEventWriteTransfer(
      *(_DWORD *)(a1 + 8944) & 1,
      (unsigned int)NondhcpToStateless,
      *(_DWORD *)(a1 + 48),
      v7,
      *(_BYTE *)(a1 + 8944) & 1,
      *(_BYTE *)(a1 + 8944) & 2);
  TraceLogErrorv6(a1, v7, 82);
  return v7;
}

```

## disassembly

```asm
0x180013580  mov     [rsp+arg_8], rbx
0x180013585  mov     [rsp+arg_10], rsi
0x18001358a  push    rdi
0x18001358b  sub     rsp, 30h
0x18001358f  mov     rbx, rcx
0x180013592  mov     [rsp+38h+Data], 0
0x18001359a  mov     al, byte ptr cs:xmmword_1800423E0
0x1800135a0  lea     rsi, [rcx+38h]
0x1800135a4  mov     edi, 404h
0x1800135a9  test    al, 10h
0x1800135ab  jz      short loc_1800135E3
0x1800135ad  mov     r9, [rsi]
0x1800135b0  lea     r8, WPP_d400c6d7dc7d3cccc0799e5e1f792179_Traceguids
0x1800135b7  mov     edx, 13Ah
0x1800135bc  mov     ecx, edi
0x1800135be  call    WPP_SF_S
0x1800135c3  mov     al, byte ptr cs:xmmword_1800423E0
0x1800135c9  test    al, 10h
0x1800135cb  jz      short loc_1800135E3
0x1800135cd  mov     r9, [rsi]
0x1800135d0  lea     r8, WPP_d400c6d7dc7d3cccc0799e5e1f792179_Traceguids
0x1800135d7  mov     edx, 13Bh
0x1800135dc  mov     ecx, edi
0x1800135de  call    WPP_SF_S
0x1800135e3  mov     rcx, rbx
0x1800135e6  call    Dhcpv6DeleteRegValues
0x1800135eb  mov     rcx, [rbx+288h]; hKey
0x1800135f2  lea     rax, [rsp+38h+Data]
0x1800135f7  mov     r9d, 4; dwType
0x1800135fd  mov     [rsp+38h+Data], 2
0x180013605  mov     [rsp+38h+cbData], r9d; cbData
0x18001360a  lea     rdx, aDhcpv6state; "Dhcpv6State"
0x180013611  xor     r8d, r8d; Reserved
0x180013614  mov     [rsp+38h+lpData], rax; lpData
0x180013619  call    cs:__imp_RegSetValueExW
0x180013620  nop     dword ptr [rax+rax+00h]
0x180013625  mov     ecx, cs:g_fVelocityDhcpv6ContextBitfieldUpdate
0x18001362b  lea     rax, ReConfigureParams
0x180013632  mov     [rbx+240h], rax
0x180013639  lea     rax, [rbx+229Ch]
0x180013640  test    ecx, ecx
0x180013642  jz      short loc_180013650
0x180013644  mov     dword ptr [rbx+22ACh], 1
0x18001364e  jmp     short loc_180013653
0x180013650  or      dword ptr [rax], 10h
0x180013653  test    ecx, ecx
0x180013655  jz      short loc_180013663
0x180013657  mov     dword ptr [rbx+22B0h], 1
0x180013661  jmp     short loc_180013666
0x180013663  or      dword ptr [rax], 20h
0x180013666  mov     rcx, rbx
0x180013669  mov     dword ptr [rbx+1F0h], 0
0x180013673  call    ReConfigureParams
0x180013678  mov     edi, eax
0x18001367a  test    byte ptr cs:xmmword_1800423E0, 2
0x180013681  jz      short loc_1800136A4
0x180013683  mov     rcx, [rbx+18h]
0x180013687  lea     r8, WPP_d400c6d7dc7d3cccc0799e5e1f792179_Traceguids
0x18001368e  mov     r9, [rsi]
0x180013691  mov     edx, 13Ch
0x180013696  mov     qword ptr [rsp+38h+cbData], rcx
0x18001369b  mov     dword ptr [rsp+38h+lpData], eax
0x18001369f  call    WPP_SF_SDJ
0x1800136a4  test    byte ptr cs:Microsoft_Windows_DHCPv6_ClientEnableBits, 1
0x1800136ab  jz      short loc_1800136D6
0x1800136ad  mov     ecx, [rbx+22F0h]
0x1800136b3  lea     rdx, NondhcpToStateless
0x1800136ba  mov     r8d, [rbx+30h]
0x1800136be  mov     eax, ecx
0x1800136c0  and     eax, 2
0x1800136c3  and     ecx, 1
0x1800136c6  mov     [rsp+38h+cbData], eax
0x1800136ca  mov     r9d, edi
0x1800136cd  mov     dword ptr [rsp+38h+lpData], ecx
0x1800136d1  call    McTemplateU0qqqq_EtwEventWriteTransfer
0x1800136d6  mov     r8d, 52h ; 'R'
0x1800136dc  mov     edx, edi
0x1800136de  mov     rcx, rbx
0x1800136e1  call    TraceLogErrorv6
0x1800136e6  mov     rbx, [rsp+38h+arg_8]
0x1800136eb  mov     eax, edi
0x1800136ed  mov     rsi, [rsp+38h+arg_10]
0x1800136f2  add     rsp, 30h
0x1800136f6  pop     rdi
0x1800136f7  retn
```
