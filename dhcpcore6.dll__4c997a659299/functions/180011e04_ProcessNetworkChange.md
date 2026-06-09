# ProcessNetworkChange

- ea: `0x180011e04`
- end: `0x180012253`
- name: `ProcessNetworkChange`
- size: `1103`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180010088`

## callees

- `0x180001ac0`
- `0x1800075b0`
- `0x18000bc88`
- `0x18000cabc`
- `0x18000e848`
- `0x18000f3a4`
- `0x180011b98`
- `0x180011e04`
- `0x180016440`
- `0x1800191fc`
- `0x18001ca14`
- `0x1800338c0`
- `0x180033900`
- `0x1800340b4`

## import_xrefs

- `api-ms-win-crt-time-l1-1-0!_time64` at `0x180012049`
- `api-ms-win-crt-time-l1-1-0!_time64` at `0x180012049`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180011e9b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180011e9b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180011f0e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180011f77`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180011f0e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180011f77`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x1800120b5`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x1800120b5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001222e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001222e`

## pseudocode

```c
__int64 __fastcall ProcessNetworkChange(__int64 a1, const WCHAR *a2, __int64 a3, int a4, unsigned int a5)
{
  HKEY v9; // rcx
  int v10; // ecx
  unsigned int v11; // esi
  __int64 v12; // rdx
  char *v13; // rax
  signed __int64 v14; // r8
  int v15; // edx
  int v16; // ecx
  unsigned int v17; // eax
  unsigned int v18; // eax
  __int64 v19; // rdx
  unsigned int v20; // r8d
  int v21; // ecx
  LSTATUS v22; // eax
  int v23; // r8d
  __int64 v24; // r9
  int v25; // edx
  int v26; // ecx
  int v27; // eax
  __int64 v28; // rcx
  int v29; // r8d
  __int64 *i; // rax
  DWORD cbData; // [rsp+40h] [rbp-20h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-18h] BYREF
  BYTE v33[8]; // [rsp+50h] [rbp-10h] BYREF
  unsigned int Data; // [rsp+90h] [rbp+30h] BYREF

  hKey = 0;
  cbData = 0;
  *(_QWORD *)v33 = 0;
  Data = 0;
  if ( (unsigned int)DhcpIsFSEGuestSystem() )
  {
    if ( (xmmword_1800423E0 & 0x10) != 0 )
      WPP_SF_(1028, 124, WPP_adff602ec73e393dc921a742cb89b1f2_Traceguids);
    return 0;
  }
  v9 = *(HKEY *)(a1 + 648);
  *(_DWORD *)(a1 + 9152) = 0;
  if ( RegOpenKeyExW(v9, a2, 0, 0xFu, &hKey) )
  {
    if ( (xmmword_1800423E0 & 0x10) != 0 )
      WPP_SF_(1028, 133, WPP_adff602ec73e393dc921a742cb89b1f2_Traceguids);
    Dhcpv6SaveInterfaceConfiguration(a1);
    v22 = Dhcpv6UnplumbStack(a1, 1);
    goto LABEL_61;
  }
  *(_DWORD *)(a1 + 8980) = 1;
  if ( (Microsoft_Windows_DHCPv6_ClientEnableBits & 1) != 0 )
    McTemplateU0zzqbr2_EtwEventWriteTransfer(
      v10,
      (unsigned int)DHCPv6NetworkHintMatch,
      a4,
      (_DWORD)a2,
      *(_DWORD *)(a1 + 88),
      *(_QWORD *)(a1 + 80));
  cbData = 4;
  v11 = RegQueryValueExW(hKey, L"Dhcpv6State", 0, 0, (LPBYTE)&Data, &cbData);
  if ( !v11 )
  {
    if ( (unsigned int)IsModeStateful(Data) )
    {
      v11 = RegQueryValueExW(hKey, L"Dhcpv6MaxLeaseExpireTime", 0, 0, v33, &cbData);
      if ( v11 )
      {
        if ( (xmmword_1800423E0 & 0x10) == 0 )
          goto LABEL_62;
        v12 = 126;
        goto LABEL_11;
      }
    }
    v13 = *(char **)(a1 + 8952);
    if ( v13 )
    {
      v14 = (char *)a2 - v13;
      do
      {
        v15 = *(unsigned __int16 *)&v13[v14];
        v16 = *(unsigned __int16 *)v13 - v15;
        if ( v16 )
          break;
        v13 += 2;
      }
      while ( v15 );
      if ( v16 )
      {
        v17 = Dhcpv6SaveInterfaceConfiguration(a1);
        if ( v17 )
        {
          if ( (xmmword_1800423E0 & 0x10) != 0 )
            WPP_SF_D(1028, 127, WPP_adff602ec73e393dc921a742cb89b1f2_Traceguids, v17);
        }
      }
    }
    v18 = Dhcpv6UnplumbStack(a1, 1);
    v11 = v18;
    if ( v18 )
    {
      if ( (xmmword_1800423E0 & 0x10) == 0 )
        goto LABEL_62;
      v19 = 128;
      goto LABEL_27;
    }
    if ( (unsigned int)IsModeStateful(Data) )
    {
      if ( _time64(0) > *(__int64 *)v33 )
      {
        if ( (Microsoft_Windows_DHCPv6_ClientEnableBits & 1) != 0 )
          McTemplateU0zzqbr2_EtwEventWriteTransfer(
            v21,
            (unsigned int)DHCPv6NetworkHintConfigExpired,
            a4,
            (_DWORD)a2,
            *(_DWORD *)(a1 + 88),
            *(_QWORD *)(a1 + 80));
        if ( (xmmword_1800423E0 & 0x10) != 0 )
          WPP_SF_(1028, 129, WPP_adff602ec73e393dc921a742cb89b1f2_Traceguids);
        v22 = RegDeleteKeyExW(*(HKEY *)(a1 + 648), a2, 0, 0);
LABEL_61:
        v11 = v22;
        goto LABEL_62;
      }
      v20 = Data;
    }
    if ( !(unsigned int)Dhcpv6CompareMode(a5, v20) )
    {
      if ( (xmmword_1800423E0 & 0x10) != 0 )
        WPP_SF_dd(1028, 132, WPP_adff602ec73e393dc921a742cb89b1f2_Traceguids, v24, v23);
      goto LABEL_62;
    }
    v18 = Dhcpv6CopyToCurrentContext(a1, a2);
    v11 = v18;
    if ( !v18 )
    {
      RefillDhcpv6Context(a1);
      v11 = Dhcpv6PlumbConfig(a1, 1, 0);
      if ( g_fVelocityDhcpv6ContextBitfieldUpdate )
        v27 = *(_DWORD *)(a1 + 8880);
      else
        v27 = (*(_DWORD *)(a1 + 8860) >> 5) & 1;
      if ( v27 )
      {
        if ( (Microsoft_Windows_DHCPv6_ClientEnableBits & 1) != 0 )
          McTemplateU0zzqbr2_EtwEventWriteTransfer(
            v26,
            (unsigned int)DHCPv6NetworkHintStatelessConfig,
            a4,
            (_DWORD)a2,
            *(_DWORD *)(a1 + 88),
            *(_QWORD *)(a1 + 80));
      }
      else
      {
        v28 = a1 + 104;
        v29 = 0;
        for ( i = *(__int64 **)(a1 + 104); i != (__int64 *)v28; i = (__int64 *)*i )
        {
          if ( *((_DWORD *)i + 9) )
          {
            v29 = (_DWORD)i + 56;
            break;
          }
        }
        if ( (Microsoft_Windows_DHCPv6_ClientEnableBits & 1) != 0 )
          McTemplateU0b16zzqbr3_EtwEventWriteTransfer(
            v28,
            v25,
            v29,
            a4,
            (__int64)a2,
            *(_DWORD *)(a1 + 88),
            *(_QWORD *)(a1 + 80));
      }
      if ( (xmmword_1800423E0 & 0x10) == 0 )
        goto LABEL_62;
      v12 = 131;
      goto LABEL_11;
    }
    if ( (xmmword_1800423E0 & 0x10) == 0 )
      goto LABEL_62;
    v19 = 130;
LABEL_27:
    WPP_SF_D(1028, v19, WPP_adff602ec73e393dc921a742cb89b1f2_Traceguids, v18);
    goto LABEL_62;
  }
  if ( (xmmword_1800423E0 & 0x10) != 0 )
  {
    v12 = 125;
LABEL_11:
    WPP_SF_(1028, v12, WPP_adff602ec73e393dc921a742cb89b1f2_Traceguids);
  }
LABEL_62:
  if ( hKey )
    RegCloseKey(hKey);
  return v11;
}

```

## disassembly

```asm
0x180011e04  mov     [rsp-18h+arg_0], rbx
0x180011e09  mov     [rsp-18h+arg_8], rsi
0x180011e0e  mov     [rsp-18h+Data], r8d
0x180011e13  push    rbp
0x180011e14  push    r12
0x180011e16  push    r15
0x180011e18  mov     rbp, rsp
0x180011e1b  sub     rsp, 60h
0x180011e1f  mov     r12, r9
0x180011e22  mov     [rbp+hKey], 0
0x180011e2a  mov     r15, rdx
0x180011e2d  mov     [rbp+cbData], 0
0x180011e34  mov     rbx, rcx
0x180011e37  mov     qword ptr [rbp+var_10], 0
0x180011e3f  mov     [rbp+Data], 0
0x180011e46  call    DhcpIsFSEGuestSystem
0x180011e4b  test    eax, eax
0x180011e4d  jz      short loc_180011E75
0x180011e4f  test    byte ptr cs:xmmword_1800423E0, 10h
0x180011e56  jz      short loc_180011E6E
0x180011e58  mov     edx, 7Ch ; '|'
0x180011e5d  lea     r8, WPP_adff602ec73e393dc921a742cb89b1f2_Traceguids
0x180011e64  mov     ecx, 404h
0x180011e69  call    WPP_SF_
0x180011e6e  xor     eax, eax
0x180011e70  jmp     loc_18001223C
0x180011e75  mov     rcx, [rbx+288h]; hKey
0x180011e7c  lea     rax, [rbp+hKey]
0x180011e80  mov     r9d, 0Fh; samDesired
0x180011e86  mov     [rsp+60h+phkResult], rax; phkResult
0x180011e8b  xor     r8d, r8d; ulOptions
0x180011e8e  mov     dword ptr [rbx+23C0h], 0
0x180011e98  mov     rdx, r15; lpSubKey
0x180011e9b  call    cs:__imp_RegOpenKeyExW
0x180011ea2  nop     dword ptr [rax+rax+00h]
0x180011ea7  test    eax, eax
0x180011ea9  jnz     loc_1800121EF
0x180011eaf  mov     dword ptr [rbx+2314h], 1
0x180011eb9  test    byte ptr cs:Microsoft_Windows_DHCPv6_ClientEnableBits, 1
0x180011ec0  jz      short loc_180011EE4
0x180011ec2  mov     rax, [rbx+50h]
0x180011ec6  lea     rdx, DHCPv6NetworkHintMatch
0x180011ecd  mov     [rsp+60h+lpcbData], rax
0x180011ed2  mov     r9, r15
0x180011ed5  mov     eax, [rbx+58h]
0x180011ed8  mov     r8, r12
0x180011edb  mov     dword ptr [rsp+60h+phkResult], eax
0x180011edf  call    McTemplateU0zzqbr2_EtwEventWriteTransfer
0x180011ee4  mov     rcx, [rbp+hKey]; hKey
0x180011ee8  lea     rax, [rbp+cbData]
0x180011eec  mov     [rsp+60h+lpcbData], rax; lpcbData
0x180011ef1  lea     rdx, aDhcpv6state; "Dhcpv6State"
0x180011ef8  lea     rax, [rbp+Data]
0x180011efc  mov     [rbp+cbData], 4
0x180011f03  xor     r9d, r9d; lpType
0x180011f06  mov     [rsp+60h+phkResult], rax; lpData
0x180011f0b  xor     r8d, r8d; lpReserved
0x180011f0e  call    cs:__imp_RegQueryValueExW
0x180011f15  nop     dword ptr [rax+rax+00h]
0x180011f1a  mov     esi, eax
0x180011f1c  test    eax, eax
0x180011f1e  jz      short loc_180011F48
0x180011f20  test    byte ptr cs:xmmword_1800423E0, 10h
0x180011f27  jz      loc_180012225
0x180011f2d  mov     edx, 7Dh ; '}'
0x180011f32  mov     ecx, 404h
0x180011f37  lea     r8, WPP_adff602ec73e393dc921a742cb89b1f2_Traceguids
0x180011f3e  call    WPP_SF_
0x180011f43  jmp     loc_180012225
0x180011f48  mov     ecx, [rbp+Data]
0x180011f4b  call    IsModeStateful
0x180011f50  test    eax, eax
0x180011f52  jz      short loc_180011F9D
0x180011f54  mov     rcx, [rbp+hKey]; hKey
0x180011f58  lea     rax, [rbp+cbData]
0x180011f5c  mov     [rsp+60h+lpcbData], rax; lpcbData
0x180011f61  lea     rdx, aDhcpv6maxlease; "Dhcpv6MaxLeaseExpireTime"
0x180011f68  lea     rax, [rbp+var_10]
0x180011f6c  xor     r9d, r9d; lpType
0x180011f6f  xor     r8d, r8d; lpReserved
0x180011f72  mov     [rsp+60h+phkResult], rax; lpData
0x180011f77  call    cs:__imp_RegQueryValueExW
0x180011f7e  nop     dword ptr [rax+rax+00h]
0x180011f83  mov     esi, eax
0x180011f85  test    eax, eax
0x180011f87  jz      short loc_180011F9D
0x180011f89  test    byte ptr cs:xmmword_1800423E0, 10h
0x180011f90  jz      loc_180012225
0x180011f96  mov     edx, 7Eh ; '~'
0x180011f9b  jmp     short loc_180011F32
0x180011f9d  mov     rax, [rbx+22F8h]
0x180011fa4  test    rax, rax
0x180011fa7  jz      short loc_180011FF5
0x180011fa9  mov     r8, r15
0x180011fac  sub     r8, rax
0x180011faf  movzx   ecx, word ptr [rax]
0x180011fb2  movzx   edx, word ptr [rax+r8]
0x180011fb7  sub     ecx, edx
0x180011fb9  jnz     short loc_180011FC3
0x180011fbb  add     rax, 2
0x180011fbf  test    edx, edx
0x180011fc1  jnz     short loc_180011FAF
0x180011fc3  test    ecx, ecx
0x180011fc5  jz      short loc_180011FF5
0x180011fc7  mov     rcx, rbx
0x180011fca  call    Dhcpv6SaveInterfaceConfiguration
0x180011fcf  test    eax, eax
0x180011fd1  jz      short loc_180011FF5
0x180011fd3  test    byte ptr cs:xmmword_1800423E0, 10h
0x180011fda  jz      short loc_180011FF5
0x180011fdc  mov     edx, 7Fh
0x180011fe1  lea     r8, WPP_adff602ec73e393dc921a742cb89b1f2_Traceguids
0x180011fe8  mov     ecx, 404h
0x180011fed  mov     r9d, eax
0x180011ff0  call    WPP_SF_D
0x180011ff5  mov     edx, 1
0x180011ffa  mov     rcx, rbx
0x180011ffd  call    Dhcpv6UnplumbStack
0x180012002  mov     esi, eax
0x180012004  test    eax, eax
0x180012006  jz      short loc_180012033
0x180012008  test    byte ptr cs:xmmword_1800423E0, 10h
0x18001200f  jz      loc_180012225
0x180012015  mov     edx, 80h
0x18001201a  mov     ecx, 404h
0x18001201f  lea     r8, WPP_adff602ec73e393dc921a742cb89b1f2_Traceguids
0x180012026  mov     r9d, eax
0x180012029  call    WPP_SF_D
0x18001202e  jmp     loc_180012225
0x180012033  mov     r8d, [rbp+Data]
0x180012037  mov     ecx, r8d
0x18001203a  call    IsModeStateful
0x18001203f  test    eax, eax
0x180012041  jz      loc_1800120CA
0x180012047  xor     ecx, ecx; Time
0x180012049  call    cs:__imp__time64
0x180012050  nop     dword ptr [rax+rax+00h]
0x180012055  cmp     rax, qword ptr [rbp+var_10]
0x180012059  jle     short loc_1800120C6
0x18001205b  test    byte ptr cs:Microsoft_Windows_DHCPv6_ClientEnableBits, 1
0x180012062  jz      short loc_180012086
0x180012064  mov     rax, [rbx+50h]
0x180012068  lea     rdx, DHCPv6NetworkHintConfigExpired
0x18001206f  mov     [rsp+60h+lpcbData], rax
0x180012074  mov     r9, r15
0x180012077  mov     eax, [rbx+58h]
0x18001207a  mov     r8, r12
0x18001207d  mov     dword ptr [rsp+60h+phkResult], eax
0x180012081  call    McTemplateU0zzqbr2_EtwEventWriteTransfer
0x180012086  test    byte ptr cs:xmmword_1800423E0, 10h
0x18001208d  jz      short loc_1800120A5
0x18001208f  mov     edx, 81h
0x180012094  lea     r8, WPP_adff602ec73e393dc921a742cb89b1f2_Traceguids
0x18001209b  mov     ecx, 404h
0x1800120a0  call    WPP_SF_
0x1800120a5  mov     rcx, [rbx+288h]; hKey
0x1800120ac  xor     r9d, r9d; Reserved
0x1800120af  xor     r8d, r8d; samDesired
0x1800120b2  mov     rdx, r15; lpSubKey
0x1800120b5  call    cs:__imp_RegDeleteKeyExW
0x1800120bc  nop     dword ptr [rax+rax+00h]
0x1800120c1  jmp     loc_180012223
0x1800120c6  mov     r8d, [rbp+Data]
0x1800120ca  mov     r9d, [rbp+arg_20]
0x1800120ce  mov     edx, r8d
0x1800120d1  mov     ecx, r9d
0x1800120d4  call    Dhcpv6CompareMode
0x1800120d9  test    eax, eax
0x1800120db  jz      loc_1800121C9
0x1800120e1  mov     rdx, r15
0x1800120e4  mov     rcx, rbx
0x1800120e7  call    Dhcpv6CopyToCurrentContext
0x1800120ec  mov     esi, eax
0x1800120ee  test    eax, eax
0x1800120f0  jz      short loc_180012109
0x1800120f2  test    byte ptr cs:xmmword_1800423E0, 10h
0x1800120f9  jz      loc_180012225
0x1800120ff  mov     edx, 82h
0x180012104  jmp     loc_18001201A
0x180012109  mov     rcx, rbx
0x18001210c  call    RefillDhcpv6Context
0x180012111  xor     r8d, r8d
0x180012114  mov     rcx, rbx
0x180012117  lea     edx, [r8+1]
0x18001211b  call    Dhcpv6PlumbConfig
0x180012120  cmp     cs:g_fVelocityDhcpv6ContextBitfieldUpdate, 0
0x180012127  mov     esi, eax
0x180012129  jz      short loc_180012133
0x18001212b  mov     eax, [rbx+22B0h]
0x180012131  jmp     short loc_18001213F
0x180012133  mov     eax, [rbx+229Ch]
0x180012139  shr     eax, 5
0x18001213c  and     eax, 1
0x18001213f  test    eax, eax
0x180012141  jnz     short loc_18001218B
0x180012143  lea     rcx, [rbx+68h]
0x180012147  xor     r8d, r8d
0x18001214a  mov     rax, [rcx]
0x18001214d  jmp     short loc_180012158
0x18001214f  cmp     [rax+24h], r8d
0x180012153  jnz     short loc_18001215F
0x180012155  mov     rax, [rax]
0x180012158  cmp     rax, rcx
0x18001215b  jnz     short loc_18001214F
0x18001215d  jmp     short loc_180012163
0x18001215f  lea     r8, [rax+38h]
0x180012163  test    byte ptr cs:Microsoft_Windows_DHCPv6_ClientEnableBits, 1
0x18001216a  jz      short loc_1800121B6
0x18001216c  mov     rax, [rbx+50h]
0x180012170  mov     r9, r12
0x180012173  mov     [rsp+60h+var_30], rax
0x180012178  mov     eax, [rbx+58h]
0x18001217b  mov     dword ptr [rsp+60h+lpcbData], eax
0x18001217f  mov     [rsp+60h+phkResult], r15
0x180012184  call    McTemplateU0b16zzqbr3_EtwEventWriteTransfer
0x180012189  jmp     short loc_1800121B6
0x18001218b  test    byte ptr cs:Microsoft_Windows_DHCPv6_ClientEnableBits, 1
0x180012192  jz      short loc_1800121B6
0x180012194  mov     rax, [rbx+50h]
0x180012198  lea     rdx, DHCPv6NetworkHintStatelessConfig
0x18001219f  mov     [rsp+60h+lpcbData], rax
0x1800121a4  mov     r9, r15
0x1800121a7  mov     eax, [rbx+58h]
0x1800121aa  mov     r8, r12
0x1800121ad  mov     dword ptr [rsp+60h+phkResult], eax
0x1800121b1  call    McTemplateU0zzqbr2_EtwEventWriteTransfer
0x1800121b6  test    byte ptr cs:xmmword_1800423E0, 10h
0x1800121bd  jz      short loc_180012225
0x1800121bf  mov     edx, 83h
0x1800121c4  jmp     loc_180011F32
0x1800121c9  test    byte ptr cs:xmmword_1800423E0, 10h
0x1800121d0  jz      short loc_180012225
0x1800121d2  mov     dword ptr [rsp+60h+phkResult], r8d
0x1800121d7  mov     edx, 84h
0x1800121dc  lea     r8, WPP_adff602ec73e393dc921a742cb89b1f2_Traceguids
0x1800121e3  mov     ecx, 404h
0x1800121e8  call    WPP_SF_dd
0x1800121ed  jmp     short loc_180012225
0x1800121ef  test    byte ptr cs:xmmword_1800423E0, 10h
0x1800121f6  jz      short loc_18001220E
0x1800121f8  mov     edx, 85h
0x1800121fd  lea     r8, WPP_adff602ec73e393dc921a742cb89b1f2_Traceguids
0x180012204  mov     ecx, 404h
0x180012209  call    WPP_SF_
0x18001220e  mov     rcx, rbx
0x180012211  call    Dhcpv6SaveInterfaceConfiguration
0x180012216  mov     edx, 1
0x18001221b  mov     rcx, rbx
0x18001221e  call    Dhcpv6UnplumbStack
0x180012223  mov     esi, eax
0x180012225  mov     rcx, [rbp+hKey]; hKey
0x180012229  test    rcx, rcx
0x18001222c  jz      short loc_18001223A
0x18001222e  call    cs:__imp_RegCloseKey
0x180012235  nop     dword ptr [rax+rax+00h]
0x18001223a  mov     eax, esi
0x18001223c  lea     r11, [rsp+60h+var_s0]
0x180012241  mov     rbx, [r11+20h]
0x180012245  mov     rsi, [r11+28h]
0x180012249  mov     rsp, r11
0x18001224c  pop     r15
0x18001224e  pop     r12
0x180012250  pop     rbp
0x180012251  retn
```
