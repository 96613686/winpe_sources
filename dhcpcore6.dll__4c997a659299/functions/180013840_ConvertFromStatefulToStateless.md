# ConvertFromStatefulToStateless

- ea: `0x180013840`
- end: `0x1800139f6`
- name: `ConvertFromStatefulToStateless`
- size: `438`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x180001894`
- `0x180004b30`
- `0x180007efc`
- `0x180008a70`
- `0x18000db84`
- `0x180013840`
- `0x1800216a4`
- `0x1800310e4`
- `0x1800311c4`
- `0x1800337d0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001390c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001390c`

## pseudocode

```c
__int64 __fastcall ConvertFromStatefulToStateless(__int64 a1)
{
  _QWORD *v2; // rsi
  int v3; // ecx
  _DWORD *v4; // rax
  HKEY v5; // rcx
  unsigned int v6; // eax
  int v7; // ecx
  unsigned int v8; // edi
  int Data; // [rsp+40h] [rbp+8h] BYREF

  Data = 0;
  v2 = (_QWORD *)(a1 + 56);
  if ( (xmmword_1800423E0 & 0x10) != 0 )
  {
    WPP_SF_S(1028, 307, WPP_d400c6d7dc7d3cccc0799e5e1f792179_Traceguids, *v2);
    if ( (xmmword_1800423E0 & 0x10) != 0 )
      WPP_SF_S(1028, 308, WPP_d400c6d7dc7d3cccc0799e5e1f792179_Traceguids, *v2);
  }
  v3 = g_fVelocityDhcpv6ContextBitfieldUpdate;
  v4 = (_DWORD *)(a1 + 8860);
  if ( g_fVelocityDhcpv6ContextBitfieldUpdate )
    *(_DWORD *)(a1 + 8876) = 1;
  else
    *v4 |= 0x10u;
  if ( v3 )
    *(_DWORD *)(a1 + 8880) = 1;
  else
    *v4 |= 0x20u;
  Dhcpv6ClearAllOptions((RTL_SRWLOCK *)a1);
  v5 = *(HKEY *)(a1 + 648);
  Data = 2;
  RegSetValueExW(v5, L"Dhcpv6State", 0, 4u, (const BYTE *)&Data, 4u);
  v6 = ReleaseIpv6Addresses(a1);
  v8 = v6;
  if ( (xmmword_1800423E0 & 2) != 0 )
    WPP_SF_dJ(1025, 309, WPP_d400c6d7dc7d3cccc0799e5e1f792179_Traceguids, v6, *(_QWORD *)(a1 + 24));
  if ( !v8 )
  {
    Dhcpv6DeleteRegValues(a1);
    *(_DWORD *)(a1 + 496) = 0;
    *(_QWORD *)(a1 + 576) = ReConfigureParams;
    v8 = ReConfigureParams(a1);
  }
  if ( (xmmword_1800423E0 & 2) != 0 )
    WPP_SF_SDJ(v7, 310, (unsigned int)WPP_d400c6d7dc7d3cccc0799e5e1f792179_Traceguids, *v2, v8, *(_QWORD *)(a1 + 24));
  if ( (Microsoft_Windows_DHCPv6_ClientEnableBits & 1) != 0 )
    McTemplateU0qqqq_EtwEventWriteTransfer(
      *(_DWORD *)(a1 + 8944) & 1,
      (unsigned int)StatefulToStateless,
      *(_DWORD *)(a1 + 48),
      v8,
      *(_BYTE *)(a1 + 8944) & 1,
      *(_BYTE *)(a1 + 8944) & 2);
  TraceLogErrorv6(a1, v8, 85);
  return v8;
}

```

## disassembly

```asm
0x180013840  mov     [rsp+arg_8], rbx
0x180013845  mov     [rsp+arg_10], rsi
0x18001384a  push    rdi
0x18001384b  sub     rsp, 30h
0x18001384f  mov     rbx, rcx
0x180013852  mov     [rsp+38h+Data], 0
0x18001385a  mov     al, byte ptr cs:xmmword_1800423E0
0x180013860  lea     rsi, [rcx+38h]
0x180013864  mov     edi, 404h
0x180013869  test    al, 10h
0x18001386b  jz      short loc_1800138A3
0x18001386d  mov     r9, [rsi]
0x180013870  lea     r8, WPP_d400c6d7dc7d3cccc0799e5e1f792179_Traceguids
0x180013877  mov     edx, 133h
0x18001387c  mov     ecx, edi
0x18001387e  call    WPP_SF_S
0x180013883  mov     al, byte ptr cs:xmmword_1800423E0
0x180013889  test    al, 10h
0x18001388b  jz      short loc_1800138A3
0x18001388d  mov     r9, [rsi]
0x180013890  lea     r8, WPP_d400c6d7dc7d3cccc0799e5e1f792179_Traceguids
0x180013897  mov     edx, 134h
0x18001389c  mov     ecx, edi
0x18001389e  call    WPP_SF_S
0x1800138a3  mov     ecx, cs:g_fVelocityDhcpv6ContextBitfieldUpdate
0x1800138a9  lea     rax, [rbx+229Ch]
0x1800138b0  test    ecx, ecx
0x1800138b2  jz      short loc_1800138C0
0x1800138b4  mov     dword ptr [rbx+22ACh], 1
0x1800138be  jmp     short loc_1800138C3
0x1800138c0  or      dword ptr [rax], 10h
0x1800138c3  test    ecx, ecx
0x1800138c5  jz      short loc_1800138D3
0x1800138c7  mov     dword ptr [rbx+22B0h], 1
0x1800138d1  jmp     short loc_1800138D6
0x1800138d3  or      dword ptr [rax], 20h
0x1800138d6  mov     rcx, rbx
0x1800138d9  call    Dhcpv6ClearAllOptions
0x1800138de  mov     rcx, [rbx+288h]; hKey
0x1800138e5  lea     rax, [rsp+38h+Data]
0x1800138ea  mov     r9d, 4; dwType
0x1800138f0  mov     [rsp+38h+Data], 2
0x1800138f8  mov     [rsp+38h+cbData], r9d; cbData
0x1800138fd  lea     rdx, aDhcpv6state; "Dhcpv6State"
0x180013904  xor     r8d, r8d; Reserved
0x180013907  mov     [rsp+38h+lpData], rax; lpData
0x18001390c  call    cs:__imp_RegSetValueExW
0x180013913  nop     dword ptr [rax+rax+00h]
0x180013918  mov     rcx, rbx; int
0x18001391b  call    ReleaseIpv6Addresses
0x180013920  mov     edi, eax
0x180013922  test    byte ptr cs:xmmword_1800423E0, 2
0x180013929  jz      short loc_18001394D
0x18001392b  mov     r8, [rbx+18h]
0x18001392f  mov     edx, 135h
0x180013934  mov     [rsp+38h+lpData], r8
0x180013939  mov     ecx, 401h
0x18001393e  lea     r8, WPP_d400c6d7dc7d3cccc0799e5e1f792179_Traceguids
0x180013945  mov     r9d, eax
0x180013948  call    WPP_SF_dJ
0x18001394d  test    edi, edi
0x18001394f  jnz     short loc_180013977
0x180013951  mov     rcx, rbx
0x180013954  call    Dhcpv6DeleteRegValues
0x180013959  lea     rax, ReConfigureParams
0x180013960  mov     [rbx+1F0h], edi
0x180013966  mov     rcx, rbx
0x180013969  mov     [rbx+240h], rax
0x180013970  call    ReConfigureParams
0x180013975  mov     edi, eax
0x180013977  test    byte ptr cs:xmmword_1800423E0, 2
0x18001397e  jz      short loc_1800139A1
0x180013980  mov     rax, [rbx+18h]
0x180013984  lea     r8, WPP_d400c6d7dc7d3cccc0799e5e1f792179_Traceguids
0x18001398b  mov     r9, [rsi]
0x18001398e  mov     edx, 136h
0x180013993  mov     qword ptr [rsp+38h+cbData], rax
0x180013998  mov     dword ptr [rsp+38h+lpData], edi
0x18001399c  call    WPP_SF_SDJ
0x1800139a1  test    byte ptr cs:Microsoft_Windows_DHCPv6_ClientEnableBits, 1
0x1800139a8  jz      short loc_1800139D3
0x1800139aa  mov     ecx, [rbx+22F0h]
0x1800139b0  lea     rdx, StatefulToStateless
0x1800139b7  mov     r8d, [rbx+30h]
0x1800139bb  mov     eax, ecx
0x1800139bd  and     eax, 2
0x1800139c0  and     ecx, 1
0x1800139c3  mov     [rsp+38h+cbData], eax
0x1800139c7  mov     r9d, edi
0x1800139ca  mov     dword ptr [rsp+38h+lpData], ecx
0x1800139ce  call    McTemplateU0qqqq_EtwEventWriteTransfer
0x1800139d3  mov     r8d, 55h ; 'U'
0x1800139d9  mov     edx, edi
0x1800139db  mov     rcx, rbx
0x1800139de  call    TraceLogErrorv6
0x1800139e3  mov     rbx, [rsp+38h+arg_8]
0x1800139e8  mov     eax, edi
0x1800139ea  mov     rsi, [rsp+38h+arg_10]
0x1800139ef  add     rsp, 30h
0x1800139f3  pop     rdi
0x1800139f4  retn
```
