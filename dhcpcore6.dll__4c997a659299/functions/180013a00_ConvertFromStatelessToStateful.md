# ConvertFromStatelessToStateful

- ea: `0x180013a00`
- end: `0x180013b63`
- name: `ConvertFromStatelessToStateful`
- size: `355`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x180001d8c`
- `0x180004b30`
- `0x180007efc`
- `0x18000db84`
- `0x180013a00`
- `0x180014590`
- `0x1800310e4`
- `0x1800337d0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180013acf`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180013acf`

## pseudocode

```c
__int64 __fastcall ConvertFromStatelessToStateful(__int64 a1)
{
  _QWORD *v2; // rsi
  int v3; // ecx
  _DWORD *v4; // rax
  HKEY v5; // rcx
  unsigned int v6; // eax
  __int64 v7; // rcx
  unsigned int v8; // edi
  int Data; // [rsp+40h] [rbp+8h] BYREF

  Data = 0;
  v2 = (_QWORD *)(a1 + 56);
  if ( (xmmword_1800423E0 & 0x10) != 0 )
  {
    WPP_SF_S(1028, 304, WPP_d400c6d7dc7d3cccc0799e5e1f792179_Traceguids, *v2);
    if ( (xmmword_1800423E0 & 0x10) != 0 )
      WPP_SF_S(1028, 305, WPP_d400c6d7dc7d3cccc0799e5e1f792179_Traceguids, *v2);
  }
  v3 = g_fVelocityDhcpv6ContextBitfieldUpdate;
  v4 = (_DWORD *)(a1 + 8860);
  if ( g_fVelocityDhcpv6ContextBitfieldUpdate )
    *(_DWORD *)(a1 + 8876) = 1;
  else
    *v4 |= 0x10u;
  if ( v3 )
    *(_DWORD *)(a1 + 8880) = 0;
  else
    *v4 &= ~0x20u;
  Dhcpv6ClearAllOptions((RTL_SRWLOCK *)a1);
  Dhcpv6DeleteRegValues(a1);
  v5 = *(HKEY *)(a1 + 648);
  Data = 1;
  RegSetValueExW(v5, L"Dhcpv6State", 0, 4u, (const BYTE *)&Data, 4u);
  *(_QWORD *)(a1 + 8928) = 0;
  *(_QWORD *)(a1 + 576) = ReSolicitParameters;
  v6 = ReSolicitParameters(a1);
  v8 = v6;
  if ( (xmmword_1800423E0 & 2) != 0 )
    WPP_SF_SDJ(
      *(_QWORD *)(a1 + 24),
      306,
      (unsigned int)WPP_d400c6d7dc7d3cccc0799e5e1f792179_Traceguids,
      *v2,
      v6,
      *(_QWORD *)(a1 + 24));
  if ( (Microsoft_Windows_DHCPv6_ClientEnableBits & 1) != 0 )
    McTemplateU0qq_EtwEventWriteTransfer(v7, StatelessToStateful, *(unsigned int *)(a1 + 48), v8);
  TraceLogErrorv6(a1, v8, 86);
  return v8;
}

```

## disassembly

```asm
0x180013a00  mov     [rsp+arg_8], rbx
0x180013a05  mov     [rsp+arg_10], rsi
0x180013a0a  push    rdi
0x180013a0b  sub     rsp, 30h
0x180013a0f  xor     edi, edi
0x180013a11  mov     rbx, rcx
0x180013a14  mov     [rsp+38h+Data], edi
0x180013a18  mov     al, byte ptr cs:xmmword_1800423E0
0x180013a1e  lea     rsi, [rcx+38h]
0x180013a22  test    al, 10h
0x180013a24  jz      short loc_180013A62
0x180013a26  mov     r9, [rsi]
0x180013a29  lea     r8, WPP_d400c6d7dc7d3cccc0799e5e1f792179_Traceguids
0x180013a30  mov     edx, 130h
0x180013a35  mov     ecx, 404h
0x180013a3a  call    WPP_SF_S
0x180013a3f  mov     al, byte ptr cs:xmmword_1800423E0
0x180013a45  test    al, 10h
0x180013a47  jz      short loc_180013A62
0x180013a49  mov     r9, [rsi]
0x180013a4c  lea     r8, WPP_d400c6d7dc7d3cccc0799e5e1f792179_Traceguids
0x180013a53  mov     edx, 131h
0x180013a58  mov     ecx, 404h
0x180013a5d  call    WPP_SF_S
0x180013a62  mov     ecx, cs:g_fVelocityDhcpv6ContextBitfieldUpdate
0x180013a68  lea     rax, [rbx+229Ch]
0x180013a6f  test    ecx, ecx
0x180013a71  jz      short loc_180013A7F
0x180013a73  mov     dword ptr [rbx+22ACh], 1
0x180013a7d  jmp     short loc_180013A82
0x180013a7f  or      dword ptr [rax], 10h
0x180013a82  test    ecx, ecx
0x180013a84  jz      short loc_180013A8E
0x180013a86  mov     [rbx+22B0h], edi
0x180013a8c  jmp     short loc_180013A91
0x180013a8e  and     dword ptr [rax], 0FFFFFFDFh
0x180013a91  mov     rcx, rbx
0x180013a94  call    Dhcpv6ClearAllOptions
0x180013a99  mov     rcx, rbx
0x180013a9c  call    Dhcpv6DeleteRegValues
0x180013aa1  mov     rcx, [rbx+288h]; hKey
0x180013aa8  lea     rax, [rsp+38h+Data]
0x180013aad  mov     r9d, 4; dwType
0x180013ab3  mov     [rsp+38h+Data], 1
0x180013abb  mov     [rsp+38h+cbData], r9d; cbData
0x180013ac0  lea     rdx, aDhcpv6state; "Dhcpv6State"
0x180013ac7  xor     r8d, r8d; Reserved
0x180013aca  mov     [rsp+38h+lpData], rax; lpData
0x180013acf  call    cs:__imp_RegSetValueExW
0x180013ad6  nop     dword ptr [rax+rax+00h]
0x180013adb  lea     rax, ReSolicitParameters
0x180013ae2  mov     [rbx+22E0h], rdi
0x180013ae9  mov     rcx, rbx; int
0x180013aec  mov     [rbx+240h], rax
0x180013af3  call    ReSolicitParameters
0x180013af8  mov     edi, eax
0x180013afa  test    byte ptr cs:xmmword_1800423E0, 2
0x180013b01  jz      short loc_180013B24
0x180013b03  mov     rcx, [rbx+18h]
0x180013b07  lea     r8, WPP_d400c6d7dc7d3cccc0799e5e1f792179_Traceguids
0x180013b0e  mov     r9, [rsi]
0x180013b11  mov     edx, 132h
0x180013b16  mov     qword ptr [rsp+38h+cbData], rcx
0x180013b1b  mov     dword ptr [rsp+38h+lpData], eax
0x180013b1f  call    WPP_SF_SDJ
0x180013b24  test    byte ptr cs:Microsoft_Windows_DHCPv6_ClientEnableBits, 1
0x180013b2b  jz      short loc_180013B40
0x180013b2d  mov     r8d, [rbx+30h]
0x180013b31  lea     rdx, StatelessToStateful
0x180013b38  mov     r9d, edi
0x180013b3b  call    McTemplateU0qq_EtwEventWriteTransfer
0x180013b40  mov     r8d, 56h ; 'V'
0x180013b46  mov     edx, edi
0x180013b48  mov     rcx, rbx
0x180013b4b  call    TraceLogErrorv6
0x180013b50  mov     rbx, [rsp+38h+arg_8]
0x180013b55  mov     eax, edi
0x180013b57  mov     rsi, [rsp+38h+arg_10]
0x180013b5c  add     rsp, 30h
0x180013b60  pop     rdi
0x180013b61  retn
```
