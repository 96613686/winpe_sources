# GetRegistryParameters

- ea: `0x14001a100`
- end: `0x14001a317`
- name: `GetRegistryParameters`
- size: `535`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x14001a320`

## callees

- `0x140001b84`
- `0x14001a078`
- `0x14001a100`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x14001a144`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001a144`
- `NDIS!NdisCloseConfiguration` at `0x14001a302`
- `NDIS!NdisCloseConfiguration` at `0x14001a302`
- `NDIS!NdisOpenConfigurationKeyByName` at `0x14001a1c4`
- `NDIS!NdisOpenConfigurationKeyByName` at `0x14001a1c4`
- `NDIS!NdisOpenConfigurationEx` at `0x14001a163`
- `NDIS!NdisOpenConfigurationEx` at `0x14001a163`

## pseudocode

```c
void __fastcall GetRegistryParameters(void *a1)
{
  unsigned int v2; // eax
  int ConfigDword; // eax
  int v4; // eax
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-30h] BYREF
  _NDIS_CONFIGURATION_OBJECT ConfigObject; // [rsp+40h] [rbp-20h] BYREF
  int Status; // [rsp+80h] [rbp+20h] BYREF
  PVOID SubKeyHandle; // [rsp+88h] [rbp+28h] BYREF
  PVOID ConfigurationHandle; // [rsp+90h] [rbp+30h] BYREF

  ConfigurationHandle = 0;
  Status = 0;
  SubKeyHandle = 0;
  DestinationString = 0;
  memset(&ConfigObject, 0, sizeof(ConfigObject));
  RtlInitUnicodeString(&DestinationString, L"Parameters");
  ConfigObject.Header = (NDIS_OBJECT_HEADER)1573289;
  ConfigObject.NdisHandle = a1;
  v2 = NdisOpenConfigurationEx(&ConfigObject, &ConfigurationHandle);
  Status = v2;
  if ( v2 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 13, WPP_34912d7d109837df8a78d6a31dde47b4_Traceguids, v2);
    Status = -1073741823;
  }
  else
  {
    NdisOpenConfigurationKeyByName(&Status, ConfigurationHandle, &DestinationString, &SubKeyHandle);
    if ( Status < 0 )
      goto LABEL_23;
    ConfigDword = GetConfigDword(SubKeyHandle);
    Status = ConfigDword;
    if ( ConfigDword >= 0 )
    {
      *((_DWORD *)WPP_MAIN_CB.Dpc.DeferredRoutine + 12) |= 1u;
    }
    else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    {
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        14,
        WPP_34912d7d109837df8a78d6a31dde47b4_Traceguids,
        (unsigned int)ConfigDword);
    }
    v4 = GetConfigDword(SubKeyHandle);
    Status = v4;
    if ( v4 >= 0 )
    {
      *((_DWORD *)WPP_MAIN_CB.Dpc.DeferredRoutine + 12) |= 2u;
    }
    else
    {
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        goto LABEL_23;
      if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          15,
          WPP_34912d7d109837df8a78d6a31dde47b4_Traceguids,
          (unsigned int)v4);
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    {
      if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          16,
          WPP_34912d7d109837df8a78d6a31dde47b4_Traceguids,
          *((unsigned int *)WPP_MAIN_CB.Dpc.DeferredRoutine + 13));
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          17,
          WPP_34912d7d109837df8a78d6a31dde47b4_Traceguids,
          *((unsigned int *)WPP_MAIN_CB.Dpc.DeferredRoutine + 14));
    }
  }
LABEL_23:
  if ( ConfigurationHandle )
    NdisCloseConfiguration(ConfigurationHandle);
}

```

## disassembly

```asm
0x14001a100  push    rbp
0x14001a102  push    rbx
0x14001a103  push    rdi
0x14001a104  mov     rbp, rsp
0x14001a107  sub     rsp, 60h
0x14001a10b  mov     rbx, rcx
0x14001a10e  mov     [rbp+ConfigurationHandle], 0
0x14001a116  xorps   xmm0, xmm0
0x14001a119  mov     [rbp+Status], 0
0x14001a120  xorps   xmm1, xmm1
0x14001a123  mov     [rbp+SubKeyHandle], 0
0x14001a12b  xor     eax, eax
0x14001a12d  lea     rcx, [rbp+DestinationString]; DestinationString
0x14001a131  lea     rdx, aParameters; "Parameters"
0x14001a138  mov     qword ptr [rbp+ConfigObject.Flags], rax
0x14001a13c  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x14001a140  movups  xmmword ptr [rbp+ConfigObject.Header.Type], xmm1
0x14001a144  call    cs:__imp_RtlInitUnicodeString
0x14001a14b  nop     dword ptr [rax+rax+00h]
0x14001a150  lea     rdx, [rbp+ConfigurationHandle]; ConfigurationHandle
0x14001a154  mov     dword ptr [rbp+ConfigObject.Header.Type], 1801A9h
0x14001a15b  lea     rcx, [rbp+ConfigObject]; ConfigObject
0x14001a15f  mov     [rbp+ConfigObject.NdisHandle], rbx
0x14001a163  call    cs:__imp_NdisOpenConfigurationEx
0x14001a16a  nop     dword ptr [rax+rax+00h]
0x14001a16f  mov     [rbp+Status], eax
0x14001a172  test    eax, eax
0x14001a174  jz      short loc_14001A1B4
0x14001a176  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a17d  lea     rdi, WPP_GLOBAL_Control
0x14001a184  cmp     rcx, rdi
0x14001a187  jz      short loc_14001A1A8
0x14001a189  mov     bl, 5
0x14001a18b  cmp     [rcx+29h], bl
0x14001a18e  jb      short loc_14001A1A8
0x14001a190  mov     rcx, [rcx+18h]
0x14001a194  lea     r8, WPP_34912d7d109837df8a78d6a31dde47b4_Traceguids
0x14001a19b  mov     edx, 0Dh
0x14001a1a0  mov     r9d, eax
0x14001a1a3  call    WPP_SF_d
0x14001a1a8  mov     [rbp+Status], 0C0000001h
0x14001a1af  jmp     loc_14001A2F9
0x14001a1b4  mov     rdx, [rbp+ConfigurationHandle]; ConfigurationHandle
0x14001a1b8  lea     r9, [rbp+SubKeyHandle]; SubKeyHandle
0x14001a1bc  lea     r8, [rbp+DestinationString]; SubKeyName
0x14001a1c0  lea     rcx, [rbp+Status]; Status
0x14001a1c4  call    cs:__imp_NdisOpenConfigurationKeyByName
0x14001a1cb  nop     dword ptr [rax+rax+00h]
0x14001a1d0  cmp     [rbp+Status], 0
0x14001a1d4  jl      loc_14001A2F9
0x14001a1da  mov     r8, cs:WPP_MAIN_CB.Dpc.DeferredRoutine
0x14001a1e1  lea     rdx, aTxrate; "TxRate"
0x14001a1e8  mov     rcx, [rbp+SubKeyHandle]; ConfigurationHandle
0x14001a1ec  add     r8, 34h ; '4'
0x14001a1f0  call    GetConfigDword
0x14001a1f5  mov     [rbp+Status], eax
0x14001a1f8  mov     bl, 5
0x14001a1fa  lea     rdi, WPP_GLOBAL_Control
0x14001a201  test    eax, eax
0x14001a203  jns     short loc_14001A230
0x14001a205  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a20c  cmp     rcx, rdi
0x14001a20f  jz      short loc_14001A23B
0x14001a211  cmp     [rcx+29h], bl
0x14001a214  jb      short loc_14001A23B
0x14001a216  mov     rcx, [rcx+18h]
0x14001a21a  lea     r8, WPP_34912d7d109837df8a78d6a31dde47b4_Traceguids
0x14001a221  mov     edx, 0Eh
0x14001a226  mov     r9d, eax
0x14001a229  call    WPP_SF_d
0x14001a22e  jmp     short loc_14001A23B
0x14001a230  mov     rax, cs:WPP_MAIN_CB.Dpc.DeferredRoutine
0x14001a237  or      dword ptr [rax+30h], 1
0x14001a23b  mov     r8, cs:WPP_MAIN_CB.Dpc.DeferredRoutine
0x14001a242  lea     rdx, aRxrate; "RxRate"
0x14001a249  mov     rcx, [rbp+SubKeyHandle]; ConfigurationHandle
0x14001a24d  add     r8, 38h ; '8'
0x14001a251  call    GetConfigDword
0x14001a256  mov     [rbp+Status], eax
0x14001a259  test    eax, eax
0x14001a25b  jns     short loc_14001A28C
0x14001a25d  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a264  cmp     rcx, rdi
0x14001a267  jz      loc_14001A2F9
0x14001a26d  cmp     [rcx+29h], bl
0x14001a270  jb      short loc_14001A297
0x14001a272  mov     rcx, [rcx+18h]
0x14001a276  lea     r8, WPP_34912d7d109837df8a78d6a31dde47b4_Traceguids
0x14001a27d  mov     edx, 0Fh
0x14001a282  mov     r9d, eax
0x14001a285  call    WPP_SF_d
0x14001a28a  jmp     short loc_14001A297
0x14001a28c  mov     rax, cs:WPP_MAIN_CB.Dpc.DeferredRoutine
0x14001a293  or      dword ptr [rax+30h], 2
0x14001a297  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a29e  cmp     rcx, rdi
0x14001a2a1  jz      short loc_14001A2F9
0x14001a2a3  cmp     [rcx+29h], bl
0x14001a2a6  jb      short loc_14001A2C8
0x14001a2a8  mov     r9, cs:WPP_MAIN_CB.Dpc.DeferredRoutine
0x14001a2af  lea     r8, WPP_34912d7d109837df8a78d6a31dde47b4_Traceguids
0x14001a2b6  mov     rcx, [rcx+18h]
0x14001a2ba  mov     edx, 10h
0x14001a2bf  mov     r9d, [r9+34h]
0x14001a2c3  call    WPP_SF_d
0x14001a2c8  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a2cf  cmp     rcx, rdi
0x14001a2d2  jz      short loc_14001A2F9
0x14001a2d4  cmp     [rcx+29h], bl
0x14001a2d7  jb      short loc_14001A2F9
0x14001a2d9  mov     r9, cs:WPP_MAIN_CB.Dpc.DeferredRoutine
0x14001a2e0  lea     r8, WPP_34912d7d109837df8a78d6a31dde47b4_Traceguids
0x14001a2e7  mov     rcx, [rcx+18h]
0x14001a2eb  mov     edx, 11h
0x14001a2f0  mov     r9d, [r9+38h]
0x14001a2f4  call    WPP_SF_d
0x14001a2f9  mov     rcx, [rbp+ConfigurationHandle]; ConfigurationHandle
0x14001a2fd  test    rcx, rcx
0x14001a300  jz      short loc_14001A30E
0x14001a302  call    cs:__imp_NdisCloseConfiguration
0x14001a309  nop     dword ptr [rax+rax+00h]
0x14001a30e  add     rsp, 60h
0x14001a312  pop     rdi
0x14001a313  pop     rbx
0x14001a314  pop     rbp
0x14001a315  retn
```
