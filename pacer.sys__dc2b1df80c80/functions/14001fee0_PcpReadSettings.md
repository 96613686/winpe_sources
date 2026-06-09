# PcpReadSettings

- ea: `0x14001fee0`
- end: `0x140020563`
- name: `PcpReadSettings`
- size: `1667`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1400010e0`
- `0x14000b5e0`
- `0x14001d8b0`

## callees

- `0x14001fee0`
- `0x14002056c`

## import_xrefs

- `NDIS!NdisOpenConfigurationEx` at `0x1400204b4`
- `NDIS!NdisOpenConfigurationEx` at `0x1400204b4`
- `NDIS!NdisCloseConfiguration` at `0x1400204ff`
- `NDIS!NdisCloseConfiguration` at `0x140020510`
- `NDIS!NdisCloseConfiguration` at `0x140020541`
- `NDIS!NdisCloseConfiguration` at `0x140020552`
- `NDIS!NdisCloseConfiguration` at `0x1400204ff`
- `NDIS!NdisCloseConfiguration` at `0x140020510`
- `NDIS!NdisCloseConfiguration` at `0x140020541`
- `NDIS!NdisCloseConfiguration` at `0x140020552`
- `NDIS!NdisOpenConfigurationKeyByName` at `0x140020173`
- `NDIS!NdisOpenConfigurationKeyByName` at `0x1400204ea`
- `NDIS!NdisOpenConfigurationKeyByName` at `0x14002052c`
- `NDIS!NdisOpenConfigurationKeyByName` at `0x140020173`
- `NDIS!NdisOpenConfigurationKeyByName` at `0x1400204ea`
- `NDIS!NdisOpenConfigurationKeyByName` at `0x14002052c`

## pseudocode

```c
void __fastcall PcpReadSettings(void *a1, __int64 a2)
{
  NDIS_HANDLE v3; // rcx
  PVOID v5; // rcx
  PVOID v6; // rcx
  PVOID v7; // rcx
  PVOID v8; // rcx
  PVOID v9; // rcx
  PVOID v10; // rcx
  PVOID v11; // rcx
  PVOID v12; // rcx
  PVOID v13; // rcx
  PVOID v14; // rcx
  PVOID v15; // rcx
  PVOID v16; // rcx
  PVOID v17; // rcx
  PVOID v18; // rcx
  PVOID v19; // rcx
  PVOID v20; // rcx
  PVOID v21; // rcx
  PVOID v22; // rcx
  PVOID v23; // rcx
  PVOID v24; // rcx
  PVOID v25; // rcx
  NDIS_STATUS v26; // eax
  NDIS_HANDLE ConfigurationHandle; // [rsp+40h] [rbp-28h] BYREF
  struct _NDIS_CONFIGURATION_OBJECT ConfigObject; // [rsp+48h] [rbp-20h] BYREF
  __int64 v29; // [rsp+A0h] [rbp+38h] BYREF
  int Status; // [rsp+A8h] [rbp+40h] BYREF
  int v31; // [rsp+B0h] [rbp+48h]
  PVOID SubKeyHandle; // [rsp+B8h] [rbp+50h] BYREF

  LODWORD(v29) = -1;
  Status = 0;
  v3 = 0;
  SubKeyHandle = 0;
  ConfigObject.Flags = 0;
  *(_DWORD *)a2 = 0xFFFF;
  *(_QWORD *)(a2 + 12) = 1;
  *(_DWORD *)(a2 + 40) = 0;
  *(_QWORD *)(a2 + 4) = 80;
  *(_DWORD *)(a2 + 20) = 0;
  *(_DWORD *)(a2 + 24) = -1063231488;
  *(_QWORD *)(a2 + 30) = 0;
  *(_WORD *)(a2 + 28) = 0;
  *(_WORD *)(a2 + 38) = 0;
  ConfigurationHandle = 0;
  *(_OWORD *)&ConfigObject.Header.Type = 0;
  if ( a1 )
  {
    ConfigObject.Header = (NDIS_OBJECT_HEADER)1573289;
    ConfigObject.NdisHandle = a1;
    ConfigObject.Flags = 0;
    v26 = NdisOpenConfigurationEx(&ConfigObject, &ConfigurationHandle);
    v3 = ConfigurationHandle;
    Status = v26;
  }
  if ( (unsigned __int8)PcpReadRegistryUlong(v3, &PcRegKeyMaxOutstandingSends, -1, 0, (__int64)&v29, 0) )
  {
    *(_BYTE *)(a2 + 43) = 1;
  }
  else if ( !*(_DWORD *)a2 )
  {
    *(_DWORD *)a2 = 0xFFFF;
  }
  PcpReadRegistryUlong(ConfigurationHandle, &PcRegKeyNonBestEffortLimit, 100, 80, (__int64)&v29, 0);
  v5 = 0;
  SubKeyHandle = 0;
  if ( ConfigurationHandle )
  {
    NdisOpenConfigurationKeyByName(&Status, ConfigurationHandle, &PcRegKeyDiffservConf, &SubKeyHandle);
    v5 = SubKeyHandle;
  }
  v31 = 0;
  PcpReadRegistryUlong(v5, &PcRegKeyTcpTraffic, 63, 0, (__int64)&v29, (__int64)&PcRegKeyDiffservConf);
  v6 = SubKeyHandle;
  *(_BYTE *)(a2 + 29) = 4 * v31;
  v31 = 0;
  PcpReadRegistryUlong(v6, &PcRegKeyBestEffort, 63, 0, (__int64)&v29, (__int64)&PcRegKeyDiffservConf);
  v7 = SubKeyHandle;
  *(_BYTE *)(a2 + 24) = 4 * v31;
  v31 = 0;
  PcpReadRegistryUlong(v7, &PcRegKeyControlledLoad, 63, 24, (__int64)&v29, (__int64)&PcRegKeyDiffservConf);
  v8 = SubKeyHandle;
  *(_BYTE *)(a2 + 25) = 4 * v31;
  v31 = 0;
  PcpReadRegistryUlong(v8, &PcRegKeyGuaranteed, 63, 40, (__int64)&v29, (__int64)&PcRegKeyDiffservConf);
  v9 = SubKeyHandle;
  *(_BYTE *)(a2 + 26) = 4 * v31;
  v31 = 0;
  PcpReadRegistryUlong(v9, &PcRegKeyQualitative, 63, 0, (__int64)&v29, (__int64)&PcRegKeyDiffservConf);
  v10 = SubKeyHandle;
  *(_BYTE *)(a2 + 28) = 4 * v31;
  v31 = 0;
  PcpReadRegistryUlong(v10, &PcRegKeyNetworkControl, 63, 48, (__int64)&v29, (__int64)&PcRegKeyDiffservConf);
  v11 = SubKeyHandle;
  *(_BYTE *)(a2 + 27) = 4 * v31;
  if ( v11 )
    NdisCloseConfiguration(v11);
  v12 = 0;
  SubKeyHandle = 0;
  if ( ConfigurationHandle )
  {
    NdisOpenConfigurationKeyByName(&Status, ConfigurationHandle, &PcRegKeyDiffservNonConf, &SubKeyHandle);
    v12 = SubKeyHandle;
  }
  v31 = 0;
  PcpReadRegistryUlong(v12, &PcRegKeyTcpTraffic, 63, 0, (__int64)&v29, (__int64)&PcRegKeyDiffservNonConf);
  v13 = SubKeyHandle;
  *(_BYTE *)(a2 + 35) = 4 * v31;
  v31 = 0;
  PcpReadRegistryUlong(v13, &PcRegKeyBestEffort, 63, 0, (__int64)&v29, (__int64)&PcRegKeyDiffservNonConf);
  v14 = SubKeyHandle;
  *(_BYTE *)(a2 + 30) = 4 * v31;
  v31 = 0;
  PcpReadRegistryUlong(v14, &PcRegKeyControlledLoad, 63, 0, (__int64)&v29, (__int64)&PcRegKeyDiffservNonConf);
  v15 = SubKeyHandle;
  *(_BYTE *)(a2 + 31) = 4 * v31;
  v31 = 0;
  PcpReadRegistryUlong(v15, &PcRegKeyGuaranteed, 63, 0, (__int64)&v29, (__int64)&PcRegKeyDiffservNonConf);
  v16 = SubKeyHandle;
  *(_BYTE *)(a2 + 32) = 4 * v31;
  v31 = 0;
  PcpReadRegistryUlong(v16, &PcRegKeyQualitative, 63, 0, (__int64)&v29, (__int64)&PcRegKeyDiffservNonConf);
  v17 = SubKeyHandle;
  *(_BYTE *)(a2 + 34) = 4 * v31;
  v31 = 0;
  PcpReadRegistryUlong(v17, &PcRegKeyNetworkControl, 63, 0, (__int64)&v29, (__int64)&PcRegKeyDiffservNonConf);
  v18 = SubKeyHandle;
  *(_BYTE *)(a2 + 33) = 4 * v31;
  if ( v18 )
    NdisCloseConfiguration(v18);
  v19 = 0;
  SubKeyHandle = 0;
  if ( ConfigurationHandle )
  {
    NdisOpenConfigurationKeyByName(&Status, ConfigurationHandle, &PcRegKeyUserPriority, &SubKeyHandle);
    v19 = SubKeyHandle;
  }
  v31 = 0;
  PcpReadRegistryUlong(v19, &PcRegKeyTcpTraffic, 7, 0, (__int64)&v29, (__int64)&PcRegKeyUserPriority);
  v20 = SubKeyHandle;
  *(_BYTE *)(a2 + 41) = v31;
  v31 = 0;
  PcpReadRegistryUlong(v20, &PcRegKeyBestEffort, 7, 0, (__int64)&v29, (__int64)&PcRegKeyUserPriority);
  v21 = SubKeyHandle;
  *(_BYTE *)(a2 + 36) = v31;
  v31 = 0;
  PcpReadRegistryUlong(v21, &PcRegKeyControlledLoad, 7, 0, (__int64)&v29, (__int64)&PcRegKeyUserPriority);
  v22 = SubKeyHandle;
  *(_BYTE *)(a2 + 37) = v31;
  v31 = 0;
  PcpReadRegistryUlong(v22, &PcRegKeyGuaranteed, 7, 0, (__int64)&v29, (__int64)&PcRegKeyUserPriority);
  v23 = SubKeyHandle;
  *(_BYTE *)(a2 + 38) = v31;
  v31 = 0;
  PcpReadRegistryUlong(v23, &PcRegKeyQualitative, 7, 0, (__int64)&v29, (__int64)&PcRegKeyUserPriority);
  v24 = SubKeyHandle;
  *(_BYTE *)(a2 + 40) = v31;
  v31 = 0;
  PcpReadRegistryUlong(v24, &PcRegKeyNetworkControl, 7, 0, (__int64)&v29, (__int64)&PcRegKeyUserPriority);
  *(_BYTE *)(a2 + 39) = v31;
  v31 = 0;
  PcpReadRegistryUlong(SubKeyHandle, &PcRegKeyNonConforming, 7, 0, (__int64)&v29, (__int64)&PcRegKeyUserPriority);
  v25 = SubKeyHandle;
  *(_BYTE *)(a2 + 42) = v31;
  if ( v25 )
    NdisCloseConfiguration(v25);
  if ( ConfigurationHandle )
    NdisCloseConfiguration(ConfigurationHandle);
}

```

## disassembly

```asm
0x14001fee0  push    rbp
0x14001fee2  push    rbx
0x14001fee3  push    rsi
0x14001fee4  push    rdi
0x14001fee5  push    r13
0x14001fee7  push    r14
0x14001fee9  mov     rbp, rsp
0x14001feec  sub     rsp, 68h
0x14001fef0  xor     esi, esi
0x14001fef2  mov     dword ptr [rbp+arg_0], 0FFFFFFFFh
0x14001fef9  mov     rax, rcx
0x14001fefc  mov     [rbp+Status], esi
0x14001feff  xor     ecx, ecx; ConfigurationHandle
0x14001ff01  mov     [rbp+SubKeyHandle], rsi
0x14001ff05  mov     [rbp+ConfigObject.Flags], ecx
0x14001ff08  xorps   xmm0, xmm0
0x14001ff0b  mov     dword ptr [rdx], 0FFFFh
0x14001ff11  lea     r14d, [rsi+1]
0x14001ff15  mov     [rdx+0Ch], r14
0x14001ff19  mov     rbx, rdx
0x14001ff1c  mov     [rdx+28h], esi
0x14001ff1f  lea     r13d, [rsi+18h]
0x14001ff23  mov     qword ptr [rdx+4], 50h ; 'P'
0x14001ff2b  mov     [rdx+14h], esi
0x14001ff2e  mov     dword ptr [rdx+18h], 0C0A06000h
0x14001ff35  mov     [rdx+1Eh], rsi
0x14001ff39  mov     [rdx+1Ch], si
0x14001ff3d  mov     [rdx+26h], si
0x14001ff41  mov     [rbp+ConfigurationHandle], rcx
0x14001ff45  movups  xmmword ptr [rbp+ConfigObject.Header.Type], xmm0
0x14001ff49  test    rax, rax
0x14001ff4c  jnz     loc_14002049E
0x14001ff52  mov     [rsp+68h+var_30], rsi; __int64
0x14001ff57  lea     rax, [rbp+arg_0]
0x14001ff5b  mov     [rsp+68h+var_38], rax; __int64
0x14001ff60  lea     rdx, PcRegKeyMaxOutstandingSends; Keyword
0x14001ff67  mov     [rsp+68h+var_40], esi; int
0x14001ff6b  mov     r9d, r14d
0x14001ff6e  mov     r8, rbx
0x14001ff71  mov     [rsp+68h+var_48], 0FFFFFFFFh; int
0x14001ff79  call    PcpReadRegistryUlong
0x14001ff7e  test    al, al
0x14001ff80  jz      loc_1400204CC
0x14001ff86  mov     [rbx+2Bh], r14b
0x14001ff8a  mov     rcx, [rbp+ConfigurationHandle]; ConfigurationHandle
0x14001ff8e  lea     rax, [rbp+arg_0]
0x14001ff92  mov     [rsp+68h+var_30], rsi; __int64
0x14001ff97  lea     r8, [rbx+4]
0x14001ff9b  mov     [rsp+68h+var_38], rax; __int64
0x14001ffa0  lea     rdx, PcRegKeyNonBestEffortLimit; Keyword
0x14001ffa7  mov     [rsp+68h+var_40], 50h ; 'P'; int
0x14001ffaf  xor     r9d, r9d
0x14001ffb2  mov     [rsp+68h+var_48], 64h ; 'd'; int
0x14001ffba  call    PcpReadRegistryUlong
0x14001ffbf  mov     rdx, [rbp+ConfigurationHandle]; ConfigurationHandle
0x14001ffc3  lea     rdi, PcRegKeyDiffservConf
0x14001ffca  mov     rcx, rsi; ConfigurationHandle
0x14001ffcd  mov     [rbp+SubKeyHandle], rcx
0x14001ffd1  test    rdx, rdx
0x14001ffd4  jnz     loc_1400204DF
0x14001ffda  mov     [rsp+68h+var_30], rdi; __int64
0x14001ffdf  lea     rax, [rbp+arg_0]
0x14001ffe3  mov     [rsp+68h+var_38], rax; __int64
0x14001ffe8  lea     r8, [rbp+arg_10]
0x14001ffec  mov     r14d, 3Fh ; '?'
0x14001fff2  mov     [rsp+68h+var_40], esi; int
0x14001fff6  xor     r9d, r9d
0x14001fff9  mov     [rsp+68h+var_48], r14d; int
0x14001fffe  lea     rdx, PcRegKeyTcpTraffic; Keyword
0x140020005  mov     [rbp+arg_10], esi
0x140020008  call    PcpReadRegistryUlong
0x14002000d  mov     al, byte ptr [rbp+arg_10]
0x140020010  lea     r8, [rbp+arg_10]
0x140020014  mov     rcx, [rbp+SubKeyHandle]; ConfigurationHandle
0x140020018  lea     rdx, PcRegKeyBestEffort; Keyword
0x14002001f  shl     al, 2
0x140020022  xor     r9d, r9d
0x140020025  mov     [rsp+68h+var_30], rdi; __int64
0x14002002a  mov     [rbx+1Dh], al
0x14002002d  lea     rax, [rbp+arg_0]
0x140020031  mov     [rsp+68h+var_38], rax; __int64
0x140020036  mov     [rsp+68h+var_40], esi; int
0x14002003a  mov     [rsp+68h+var_48], r14d; int
0x14002003f  mov     [rbp+arg_10], esi
0x140020042  call    PcpReadRegistryUlong
0x140020047  mov     al, byte ptr [rbp+arg_10]
0x14002004a  lea     r8, [rbp+arg_10]
0x14002004e  mov     rcx, [rbp+SubKeyHandle]; ConfigurationHandle
0x140020052  xor     r9d, r9d
0x140020055  shl     al, 2
0x140020058  mov     [rsp+68h+var_30], rdi; __int64
0x14002005d  mov     [rbx+18h], al
0x140020060  lea     rax, [rbp+arg_0]
0x140020064  mov     [rsp+68h+var_38], rax; __int64
0x140020069  mov     [rsp+68h+var_40], r13d; int
0x14002006e  lea     r13, PcRegKeyControlledLoad
0x140020075  mov     rdx, r13; Keyword
0x140020078  mov     [rbp+arg_10], esi
0x14002007b  mov     [rsp+68h+var_48], r14d; int
0x140020080  call    PcpReadRegistryUlong
0x140020085  mov     al, byte ptr [rbp+arg_10]
0x140020088  lea     r8, [rbp+arg_10]
0x14002008c  mov     rcx, [rbp+SubKeyHandle]; ConfigurationHandle
0x140020090  lea     rdx, PcRegKeyGuaranteed; Keyword
0x140020097  shl     al, 2
0x14002009a  xor     r9d, r9d
0x14002009d  mov     [rsp+68h+var_30], rdi; __int64
0x1400200a2  mov     [rbx+19h], al
0x1400200a5  lea     rax, [rbp+arg_0]
0x1400200a9  mov     [rsp+68h+var_38], rax; __int64
0x1400200ae  mov     [rsp+68h+var_40], 28h ; '('; int
0x1400200b6  mov     [rsp+68h+var_48], r14d; int
0x1400200bb  mov     [rbp+arg_10], esi
0x1400200be  call    PcpReadRegistryUlong
0x1400200c3  mov     al, byte ptr [rbp+arg_10]
0x1400200c6  lea     r8, [rbp+arg_10]
0x1400200ca  mov     rcx, [rbp+SubKeyHandle]; ConfigurationHandle
0x1400200ce  lea     rdx, PcRegKeyQualitative; Keyword
0x1400200d5  shl     al, 2
0x1400200d8  xor     r9d, r9d
0x1400200db  mov     [rsp+68h+var_30], rdi; __int64
0x1400200e0  mov     [rbx+1Ah], al
0x1400200e3  lea     rax, [rbp+arg_0]
0x1400200e7  mov     [rsp+68h+var_38], rax; __int64
0x1400200ec  mov     [rsp+68h+var_40], esi; int
0x1400200f0  mov     [rsp+68h+var_48], r14d; int
0x1400200f5  mov     [rbp+arg_10], esi
0x1400200f8  call    PcpReadRegistryUlong
0x1400200fd  mov     al, byte ptr [rbp+arg_10]
0x140020100  lea     r8, [rbp+arg_10]
0x140020104  mov     rcx, [rbp+SubKeyHandle]; ConfigurationHandle
0x140020108  lea     rdx, PcRegKeyNetworkControl; Keyword
0x14002010f  shl     al, 2
0x140020112  mov     [rsp+68h+var_30], rdi; __int64
0x140020117  xor     r9d, r9d
0x14002011a  mov     [rbx+1Ch], al
0x14002011d  lea     rax, [rbp+arg_0]
0x140020121  mov     [rsp+68h+var_38], rax; __int64
0x140020126  mov     [rsp+68h+var_40], 30h ; '0'; int
0x14002012e  mov     [rsp+68h+var_48], r14d; int
0x140020133  mov     [rbp+arg_10], esi
0x140020136  call    PcpReadRegistryUlong
0x14002013b  mov     al, byte ptr [rbp+arg_10]
0x14002013e  mov     rcx, [rbp+SubKeyHandle]; ConfigurationHandle
0x140020142  shl     al, 2
0x140020145  mov     [rbx+1Bh], al
0x140020148  test    rcx, rcx
0x14002014b  jnz     loc_1400204FF
0x140020151  mov     rdx, [rbp+ConfigurationHandle]; ConfigurationHandle
0x140020155  lea     rdi, PcRegKeyDiffservNonConf
0x14002015c  mov     rcx, rsi
0x14002015f  mov     [rbp+SubKeyHandle], rcx
0x140020163  test    rdx, rdx
0x140020166  jz      short loc_140020183
0x140020168  lea     r9, [rbp+SubKeyHandle]; SubKeyHandle
0x14002016c  mov     r8, rdi; SubKeyName
0x14002016f  lea     rcx, [rbp+Status]; Status
0x140020173  call    cs:__imp_NdisOpenConfigurationKeyByName
0x14002017a  nop     dword ptr [rax+rax+00h]
0x14002017f  mov     rcx, [rbp+SubKeyHandle]; ConfigurationHandle
0x140020183  mov     [rsp+68h+var_30], rdi; __int64
0x140020188  lea     rax, [rbp+arg_0]
0x14002018c  mov     [rsp+68h+var_38], rax; __int64
0x140020191  lea     r8, [rbp+arg_10]
0x140020195  mov     [rsp+68h+var_40], esi; int
0x140020199  lea     rdx, PcRegKeyTcpTraffic; Keyword
0x1400201a0  xor     r9d, r9d
0x1400201a3  mov     [rsp+68h+var_48], r14d; int
0x1400201a8  mov     [rbp+arg_10], esi
0x1400201ab  call    PcpReadRegistryUlong
0x1400201b0  mov     al, byte ptr [rbp+arg_10]
0x1400201b3  lea     r8, [rbp+arg_10]
0x1400201b7  mov     rcx, [rbp+SubKeyHandle]; ConfigurationHandle
0x1400201bb  lea     rdx, PcRegKeyBestEffort; Keyword
0x1400201c2  shl     al, 2
0x1400201c5  xor     r9d, r9d
0x1400201c8  mov     [rsp+68h+var_30], rdi; __int64
0x1400201cd  mov     [rbx+23h], al
0x1400201d0  lea     rax, [rbp+arg_0]
0x1400201d4  mov     [rsp+68h+var_38], rax; __int64
0x1400201d9  mov     [rsp+68h+var_40], esi; int
0x1400201dd  mov     [rsp+68h+var_48], r14d; int
0x1400201e2  mov     [rbp+arg_10], esi
0x1400201e5  call    PcpReadRegistryUlong
0x1400201ea  mov     al, byte ptr [rbp+arg_10]
0x1400201ed  lea     r8, [rbp+arg_10]
0x1400201f1  mov     rcx, [rbp+SubKeyHandle]; ConfigurationHandle
0x1400201f5  xor     r9d, r9d
0x1400201f8  shl     al, 2
0x1400201fb  mov     rdx, r13; Keyword
0x1400201fe  mov     [rsp+68h+var_30], rdi; __int64
0x140020203  mov     [rbx+1Eh], al
0x140020206  lea     rax, [rbp+arg_0]
0x14002020a  mov     [rsp+68h+var_38], rax; __int64
0x14002020f  mov     [rsp+68h+var_40], esi; int
0x140020213  mov     [rsp+68h+var_48], r14d; int
0x140020218  mov     [rbp+arg_10], esi
0x14002021b  call    PcpReadRegistryUlong
0x140020220  mov     al, byte ptr [rbp+arg_10]
0x140020223  lea     r8, [rbp+arg_10]
0x140020227  mov     rcx, [rbp+SubKeyHandle]; ConfigurationHandle
0x14002022b  lea     rdx, PcRegKeyGuaranteed; Keyword
0x140020232  shl     al, 2
0x140020235  xor     r9d, r9d
0x140020238  mov     [rsp+68h+var_30], rdi; __int64
0x14002023d  mov     [rbx+1Fh], al
0x140020240  lea     rax, [rbp+arg_0]
0x140020244  mov     [rsp+68h+var_38], rax; __int64
0x140020249  mov     [rsp+68h+var_40], esi; int
0x14002024d  mov     [rsp+68h+var_48], r14d; int
0x140020252  mov     [rbp+arg_10], esi
0x140020255  call    PcpReadRegistryUlong
0x14002025a  mov     al, byte ptr [rbp+arg_10]
0x14002025d  lea     r8, [rbp+arg_10]
0x140020261  mov     rcx, [rbp+SubKeyHandle]; ConfigurationHandle
0x140020265  lea     rdx, PcRegKeyQualitative; Keyword
0x14002026c  shl     al, 2
0x14002026f  xor     r9d, r9d
0x140020272  mov     [rsp+68h+var_30], rdi; __int64
0x140020277  mov     [rbx+20h], al
0x14002027a  lea     rax, [rbp+arg_0]
0x14002027e  mov     [rsp+68h+var_38], rax; __int64
0x140020283  mov     [rsp+68h+var_40], esi; int
0x140020287  mov     [rsp+68h+var_48], r14d; int
0x14002028c  mov     [rbp+arg_10], esi
0x14002028f  call    PcpReadRegistryUlong
0x140020294  mov     al, byte ptr [rbp+arg_10]
0x140020297  lea     r8, [rbp+arg_10]
0x14002029b  mov     rcx, [rbp+SubKeyHandle]; ConfigurationHandle
0x14002029f  lea     rdx, PcRegKeyNetworkControl; Keyword
0x1400202a6  shl     al, 2
0x1400202a9  xor     r9d, r9d
0x1400202ac  mov     [rsp+68h+var_30], rdi; __int64
0x1400202b1  mov     [rbx+22h], al
0x1400202b4  lea     rax, [rbp+arg_0]
0x1400202b8  mov     [rsp+68h+var_38], rax; __int64
0x1400202bd  mov     [rsp+68h+var_40], esi; int
0x1400202c1  mov     [rsp+68h+var_48], r14d; int
0x1400202c6  mov     [rbp+arg_10], esi
0x1400202c9  call    PcpReadRegistryUlong
0x1400202ce  mov     al, byte ptr [rbp+arg_10]
0x1400202d1  mov     rcx, [rbp+SubKeyHandle]; ConfigurationHandle
0x1400202d5  shl     al, 2
0x1400202d8  mov     [rbx+21h], al
0x1400202db  test    rcx, rcx
0x1400202de  jnz     loc_140020510
0x1400202e4  mov     rdx, [rbp+ConfigurationHandle]; ConfigurationHandle
0x1400202e8  lea     r14, PcRegKeyUserPriority
0x1400202ef  mov     rcx, rsi; ConfigurationHandle
0x1400202f2  mov     [rbp+SubKeyHandle], rcx
0x1400202f6  test    rdx, rdx
0x1400202f9  jnz     loc_140020521
0x1400202ff  mov     [rsp+68h+var_30], r14; __int64
0x140020304  lea     rax, [rbp+arg_0]
0x140020308  mov     [rsp+68h+var_38], rax; __int64
0x14002030d  lea     r8, [rbp+arg_10]
0x140020311  mov     edi, 7
0x140020316  mov     [rsp+68h+var_40], esi; int
0x14002031a  xor     r9d, r9d
0x14002031d  mov     [rsp+68h+var_48], edi; int
0x140020321  lea     rdx, PcRegKeyTcpTraffic; Keyword
0x140020328  mov     [rbp+arg_10], esi
0x14002032b  call    PcpReadRegistryUlong
0x140020330  mov     al, byte ptr [rbp+arg_10]
0x140020333  lea     r8, [rbp+arg_10]
0x140020337  mov     rcx, [rbp+SubKeyHandle]; ConfigurationHandle
0x14002033b  lea     rdx, PcRegKeyBestEffort; Keyword
0x140020342  mov     [rsp+68h+var_30], r14; __int64
0x140020347  xor     r9d, r9d
0x14002034a  mov     [rbx+29h], al
0x14002034d  lea     rax, [rbp+arg_0]
0x140020351  mov     [rsp+68h+var_38], rax; __int64
0x140020356  mov     [rsp+68h+var_40], esi; int
0x14002035a  mov     [rsp+68h+var_48], edi; int
0x14002035e  mov     [rbp+arg_10], esi
0x140020361  call    PcpReadRegistryUlong
0x140020366  mov     al, byte ptr [rbp+arg_10]
0x140020369  lea     r8, [rbp+arg_10]
0x14002036d  mov     rcx, [rbp+SubKeyHandle]; ConfigurationHandle
0x140020371  xor     r9d, r9d
0x140020374  mov     [rsp+68h+var_30], r14; __int64
0x140020379  mov     rdx, r13; Keyword
0x14002037c  mov     [rbx+24h], al
0x14002037f  lea     rax, [rbp+arg_0]
0x140020383  mov     [rsp+68h+var_38], rax; __int64
0x140020388  mov     [rsp+68h+var_40], esi; int
0x14002038c  mov     [rsp+68h+var_48], edi; int
0x140020390  mov     [rbp+arg_10], esi
0x140020393  call    PcpReadRegistryUlong
0x140020398  mov     al, byte ptr [rbp+arg_10]
0x14002039b  lea     r8, [rbp+arg_10]
0x14002039f  mov     rcx, [rbp+SubKeyHandle]; ConfigurationHandle
0x1400203a3  lea     rdx, PcRegKeyGuaranteed; Keyword
0x1400203aa  mov     [rsp+68h+var_30], r14; __int64
0x1400203af  xor     r9d, r9d
0x1400203b2  mov     [rbx+25h], al
0x1400203b5  lea     rax, [rbp+arg_0]
0x1400203b9  mov     [rsp+68h+var_38], rax; __int64
0x1400203be  mov     [rsp+68h+var_40], esi; int
0x1400203c2  mov     [rsp+68h+var_48], edi; int
  ... truncated ...
```
