# DisableDhcp

- ea: `0x18003f140`
- end: `0x18003f2bd`
- name: `DisableDhcp`
- size: `381`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800227ac`

## callees

- `0x180009038`
- `0x180015344`
- `0x180019a98`
- `0x18001a2e4`
- `0x18003f140`
- `0x18003ff30`
- `0x18004d1a0`
- `0x18004d1e0`
- `0x18004d200`
- `0x18004d4c0`
- `0x18004dbc4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003f1df`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003f1df`

## pseudocode

```c
__int64 __fastcall DisableDhcp(__int64 a1)
{
  __int64 result; // rax
  unsigned int v3; // edi
  unsigned int v4; // eax
  unsigned int v5; // eax
  __int64 v6; // rcx
  int Data; // [rsp+40h] [rbp+8h] BYREF

  result = *(unsigned int *)(a1 + 792);
  Data = 0;
  if ( (_DWORD)result )
  {
    if ( (xmmword_1800616A0 & 0x10) != 0 )
    {
      WPP_SF_q(1028, 37, WPP_da8b49cc2af8370da0dc466f7a1bd175_Traceguids, *(_QWORD *)(a1 + 24));
      if ( (xmmword_1800616A0 & 0x10) != 0 )
        WPP_SF_S(1028, 38, WPP_da8b49cc2af8370da0dc466f7a1bd175_Traceguids, *(_QWORD *)(a1 + 56));
    }
    Data = 0;
    v3 = RegSetValueExW(*(HKEY *)(a1 + 728), L"EnableDhcp", 0, 4u, (const BYTE *)&Data, 4u);
    if ( v3 )
      goto LABEL_13;
    v4 = ReleaseParameters(a1);
    if ( (xmmword_1800616A0 & 2) != 0 )
      WPP_SF_dJ(1025, 39, WPP_da8b49cc2af8370da0dc466f7a1bd175_Traceguids, v4, *(_QWORD *)(a1 + 24));
    DhcpRegDeleteIpAddressAndOtherValues(*(HKEY *)(a1 + 728));
    UnScheduleDhcpRenewal(a1);
    v5 = SetEventNotification(4, *(_QWORD *)(a1 + 56));
    *(_DWORD *)(a1 + 796) = 1;
    v3 = v5;
    if ( (Microsoft_Windows_Dhcp_ClientEnableBits & 1) != 0 )
      McTemplateU0q_EtwEventWriteTransfer(v6, DhcpDisabled, *(unsigned int *)(a1 + 48));
    *(_DWORD *)(a1 + 792) = 0;
    if ( v3 )
    {
LABEL_13:
      if ( (xmmword_1800616A0 & 2) != 0 )
        WPP_SF_D(1025, 40, WPP_da8b49cc2af8370da0dc466f7a1bd175_Traceguids, v3);
    }
    else if ( (xmmword_1800616A0 & 0x10) != 0 )
    {
      WPP_SF_(1028, 41, WPP_da8b49cc2af8370da0dc466f7a1bd175_Traceguids);
    }
    return v3;
  }
  return result;
}

```

## disassembly

```asm
0x18003f140  mov     [rsp+arg_8], rbx
0x18003f145  mov     [rsp+arg_10], rdi
0x18003f14a  push    r14
0x18003f14c  sub     rsp, 30h
0x18003f150  mov     eax, [rcx+318h]
0x18003f156  mov     rbx, rcx
0x18003f159  mov     [rsp+38h+Data], 0
0x18003f161  test    eax, eax
0x18003f163  jz      loc_18003F2AC
0x18003f169  mov     al, byte ptr cs:xmmword_1800616A0
0x18003f16f  lea     r14, WPP_da8b49cc2af8370da0dc466f7a1bd175_Traceguids
0x18003f176  test    al, 10h
0x18003f178  jz      short loc_18003F1B0
0x18003f17a  mov     r9, [rbx+18h]
0x18003f17e  mov     edx, 25h ; '%'
0x18003f183  mov     ecx, 404h
0x18003f188  mov     r8, r14
0x18003f18b  call    WPP_SF_q
0x18003f190  mov     al, byte ptr cs:xmmword_1800616A0
0x18003f196  test    al, 10h
0x18003f198  jz      short loc_18003F1B0
0x18003f19a  mov     r9, [rbx+38h]
0x18003f19e  mov     edx, 26h ; '&'
0x18003f1a3  mov     ecx, 404h
0x18003f1a8  mov     r8, r14
0x18003f1ab  call    WPP_SF_S
0x18003f1b0  mov     ecx, 4
0x18003f1b5  mov     [rsp+38h+Data], 0
0x18003f1bd  mov     [rsp+38h+cbData], ecx; cbData
0x18003f1c1  lea     rax, [rsp+38h+Data]
0x18003f1c6  mov     r9d, ecx; dwType
0x18003f1c9  mov     [rsp+38h+lpData], rax; lpData
0x18003f1ce  mov     rcx, [rbx+2D8h]; hKey
0x18003f1d5  lea     rdx, aEnabledhcp; "EnableDhcp"
0x18003f1dc  xor     r8d, r8d; Reserved
0x18003f1df  call    cs:__imp_RegSetValueExW
0x18003f1e5  mov     edi, eax
0x18003f1e7  test    eax, eax
0x18003f1e9  jnz     loc_18003F28C
0x18003f1ef  mov     rcx, rbx
0x18003f1f2  call    ReleaseParameters
0x18003f1f7  test    byte ptr cs:xmmword_1800616A0, 2
0x18003f1fe  jz      short loc_18003F21C
0x18003f200  mov     r8, [rbx+18h]
0x18003f204  lea     edx, [rdi+27h]
0x18003f207  mov     [rsp+38h+lpData], r8
0x18003f20c  mov     ecx, 401h
0x18003f211  mov     r8, r14
0x18003f214  mov     r9d, eax
0x18003f217  call    WPP_SF_dJ
0x18003f21c  mov     rcx, [rbx+2D8h]; hKey
0x18003f223  call    DhcpRegDeleteIpAddressAndOtherValues
0x18003f228  mov     rcx, rbx
0x18003f22b  call    UnScheduleDhcpRenewal
0x18003f230  mov     rdx, [rbx+38h]
0x18003f234  mov     ecx, 4
0x18003f239  call    SetEventNotification
0x18003f23e  mov     dword ptr [rbx+31Ch], 1
0x18003f248  mov     edi, eax
0x18003f24a  test    cs:Microsoft_Windows_Dhcp_ClientEnableBits, 1
0x18003f251  jz      short loc_18003F263
0x18003f253  mov     r8d, [rbx+30h]
0x18003f257  lea     rdx, DhcpDisabled
0x18003f25e  call    McTemplateU0q_EtwEventWriteTransfer
0x18003f263  mov     dword ptr [rbx+318h], 0
0x18003f26d  test    edi, edi
0x18003f26f  jnz     short loc_18003F28C
0x18003f271  test    byte ptr cs:xmmword_1800616A0, 10h
0x18003f278  jz      short loc_18003F2AA
0x18003f27a  lea     edx, [rdi+29h]
0x18003f27d  mov     ecx, 404h
0x18003f282  mov     r8, r14
0x18003f285  call    WPP_SF_
0x18003f28a  jmp     short loc_18003F2AA
0x18003f28c  test    byte ptr cs:xmmword_1800616A0, 2
0x18003f293  jz      short loc_18003F2AA
0x18003f295  mov     edx, 28h ; '('
0x18003f29a  mov     ecx, 401h
0x18003f29f  mov     r9d, edi
0x18003f2a2  mov     r8, r14
0x18003f2a5  call    WPP_SF_D
0x18003f2aa  mov     eax, edi
0x18003f2ac  mov     rbx, [rsp+38h+arg_8]
0x18003f2b1  mov     rdi, [rsp+38h+arg_10]
0x18003f2b6  add     rsp, 30h
0x18003f2ba  pop     r14
0x18003f2bc  retn
```
