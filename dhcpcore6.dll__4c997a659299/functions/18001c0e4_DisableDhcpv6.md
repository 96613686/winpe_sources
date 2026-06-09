# DisableDhcpv6

- ea: `0x18001c0e4`
- end: `0x18001c253`
- name: `DisableDhcpv6`
- size: `367`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800132c0`

## callees

- `0x180001d8c`
- `0x180004b30`
- `0x180005b88`
- `0x180007efc`
- `0x18001c0e4`
- `0x1800216a4`
- `0x180031008`
- `0x1800337d0`
- `0x180033a9c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001c1b3`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001c1b3`

## pseudocode

```c
__int64 __fastcall DisableDhcpv6(__int64 a1)
{
  _DWORD *v1; // rdi
  __int64 result; // rax
  unsigned int v4; // eax
  unsigned int v5; // esi
  HKEY v6; // rcx
  LSTATUS v7; // eax
  __int64 v8; // rcx
  bool v9; // zf
  unsigned int v10; // ebp
  int Data; // [rsp+68h] [rbp+10h] BYREF

  v1 = (_DWORD *)(a1 + 8860);
  Data = 0;
  if ( g_fVelocityDhcpv6ContextBitfieldUpdate )
    result = *(unsigned int *)(a1 + 8876);
  else
    result = (*v1 >> 4) & 1;
  if ( (_DWORD)result )
  {
    if ( (xmmword_1800423E0 & 0x10) != 0 )
      WPP_SF_J(1028, 153, WPP_adff602ec73e393dc921a742cb89b1f2_Traceguids, *(_QWORD *)(a1 + 24));
    v4 = ReleaseIpv6Addresses(a1);
    v5 = v4;
    if ( (BYTE2(xmmword_1800423E0) & 8) != 0 )
      WPP_SF_DS(1043, 154, (unsigned int)WPP_adff602ec73e393dc921a742cb89b1f2_Traceguids, v4, *(_QWORD *)(a1 + 56));
    Dhcpv6ClearAllOptions((RTL_SRWLOCK *)a1);
    NotifyDnsCache();
    v6 = *(HKEY *)(a1 + 648);
    Data = 0;
    v7 = RegSetValueExW(v6, L"Dhcpv6State", 0, 4u, (const BYTE *)&Data, 4u);
    v9 = g_fVelocityDhcpv6ContextBitfieldUpdate == 0;
    v10 = v7;
    *(_DWORD *)(a1 + 600) = 0;
    *(_QWORD *)(a1 + 544) = 0x7FFFFFFFFFFFFFFFLL;
    if ( v9 )
      *v1 &= ~0x10u;
    else
      *(_DWORD *)(a1 + 8876) = 0;
    if ( !v5 )
    {
      if ( (xmmword_1800423E0 & 2) != 0 )
        WPP_SF_S(1025, 155, WPP_adff602ec73e393dc921a742cb89b1f2_Traceguids, *(_QWORD *)(a1 + 56));
      if ( (Microsoft_Windows_DHCPv6_ClientEnableBits & 1) != 0 )
        McTemplateU0qq_EtwEventWriteTransfer(v8, DisableDhcpV6, *(unsigned int *)(a1 + 48), v10);
      TraceLogErrorv6(a1, v10, 11);
    }
    return v5;
  }
  return result;
}

```

## disassembly

```asm
0x18001c0e4  push    rbx
0x18001c0e6  push    rbp
0x18001c0e7  push    rsi
0x18001c0e8  push    rdi
0x18001c0e9  sub     rsp, 38h
0x18001c0ed  cmp     cs:g_fVelocityDhcpv6ContextBitfieldUpdate, 0
0x18001c0f4  lea     rdi, [rcx+229Ch]
0x18001c0fb  mov     rbx, rcx
0x18001c0fe  mov     [rsp+58h+Data], 0
0x18001c106  jz      short loc_18001C110
0x18001c108  mov     eax, [rcx+22ACh]
0x18001c10e  jmp     short loc_18001C118
0x18001c110  mov     eax, [rdi]
0x18001c112  shr     eax, 4
0x18001c115  and     eax, 1
0x18001c118  test    eax, eax
0x18001c11a  jz      loc_18001C249
0x18001c120  test    byte ptr cs:xmmword_1800423E0, 10h
0x18001c127  jz      short loc_18001C143
0x18001c129  mov     r9, [rbx+18h]
0x18001c12d  lea     r8, WPP_adff602ec73e393dc921a742cb89b1f2_Traceguids
0x18001c134  mov     edx, 99h
0x18001c139  mov     ecx, 404h
0x18001c13e  call    WPP_SF_J
0x18001c143  mov     rcx, rbx; int
0x18001c146  call    ReleaseIpv6Addresses
0x18001c14b  mov     esi, eax
0x18001c14d  test    byte ptr cs:xmmword_1800423E0+2, 8
0x18001c154  jz      short loc_18001C178
0x18001c156  mov     r8, [rbx+38h]
0x18001c15a  mov     edx, 9Ah
0x18001c15f  mov     [rsp+58h+lpData], r8
0x18001c164  mov     ecx, 413h
0x18001c169  lea     r8, WPP_adff602ec73e393dc921a742cb89b1f2_Traceguids
0x18001c170  mov     r9d, eax
0x18001c173  call    WPP_SF_DS
0x18001c178  mov     rcx, rbx
0x18001c17b  call    Dhcpv6ClearAllOptions
0x18001c180  call    NotifyDnsCache
0x18001c185  mov     rcx, [rbx+288h]; hKey
0x18001c18c  lea     rax, [rsp+58h+Data]
0x18001c191  mov     r9d, 4; dwType
0x18001c197  mov     [rsp+58h+Data], 0
0x18001c19f  mov     [rsp+58h+cbData], r9d; cbData
0x18001c1a4  lea     rdx, aDhcpv6state; "Dhcpv6State"
0x18001c1ab  xor     r8d, r8d; Reserved
0x18001c1ae  mov     [rsp+58h+lpData], rax; lpData
0x18001c1b3  call    cs:__imp_RegSetValueExW
0x18001c1ba  nop     dword ptr [rax+rax+00h]
0x18001c1bf  cmp     cs:g_fVelocityDhcpv6ContextBitfieldUpdate, 0
0x18001c1c6  mov     ebp, eax
0x18001c1c8  mov     rax, 7FFFFFFFFFFFFFFFh
0x18001c1d2  mov     dword ptr [rbx+258h], 0
0x18001c1dc  mov     [rbx+220h], rax
0x18001c1e3  jz      short loc_18001C1F1
0x18001c1e5  mov     dword ptr [rbx+22ACh], 0
0x18001c1ef  jmp     short loc_18001C1F4
0x18001c1f1  and     dword ptr [rdi], 0FFFFFFEFh
0x18001c1f4  test    esi, esi
0x18001c1f6  jnz     short loc_18001C247
0x18001c1f8  test    byte ptr cs:xmmword_1800423E0, 2
0x18001c1ff  jz      short loc_18001C21B
0x18001c201  mov     r9, [rbx+38h]
0x18001c205  lea     r8, WPP_adff602ec73e393dc921a742cb89b1f2_Traceguids
0x18001c20c  mov     edx, 9Bh
0x18001c211  mov     ecx, 401h
0x18001c216  call    WPP_SF_S
0x18001c21b  test    byte ptr cs:Microsoft_Windows_DHCPv6_ClientEnableBits, 1
0x18001c222  jz      short loc_18001C237
0x18001c224  mov     r8d, [rbx+30h]
0x18001c228  lea     rdx, DisableDhcpV6
0x18001c22f  mov     r9d, ebp
0x18001c232  call    McTemplateU0qq_EtwEventWriteTransfer
0x18001c237  mov     r8d, 0Bh
0x18001c23d  mov     edx, ebp
0x18001c23f  mov     rcx, rbx
0x18001c242  call    TraceLogErrorv6
0x18001c247  mov     eax, esi
0x18001c249  add     rsp, 38h
0x18001c24d  pop     rdi
0x18001c24e  pop     rsi
0x18001c24f  pop     rbp
0x18001c250  pop     rbx
0x18001c251  retn
```
