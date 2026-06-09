# ReadRegistrySettings

- ea: `0x14000ebcc`
- end: `0x14000eeca`
- name: `ReadRegistrySettings`
- size: `766`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x14000ef40`

## callees

- `0x140002bd8`
- `0x140002c08`
- `0x14000ebcc`

## import_xrefs

- `NDIS!NdisOpenConfigurationEx` at `0x14000ec53`
- `NDIS!NdisOpenConfigurationEx` at `0x14000ec53`
- `NDIS!NdisCloseConfiguration` at `0x14000ee85`
- `NDIS!NdisCloseConfiguration` at `0x14000ee85`
- `NDIS!NdisReadConfiguration` at `0x14000ed10`
- `NDIS!NdisReadConfiguration` at `0x14000eddd`
- `NDIS!NdisReadConfiguration` at `0x14000ed10`
- `NDIS!NdisReadConfiguration` at `0x14000eddd`

## pseudocode

```c
void __fastcall ReadRegistrySettings(void *a1, _DWORD *a2, int *a3, ULONG *a4, ULONG *a5)
{
  int v9; // r8d
  ULONG IntegerData; // ecx
  ULONG v11; // ecx
  PNDIS_CONFIGURATION_PARAMETER ParameterValue; // [rsp+30h] [rbp-48h] BYREF
  PVOID ConfigurationHandle; // [rsp+38h] [rbp-40h] BYREF
  UNICODE_STRING Keyword; // [rsp+40h] [rbp-38h] BYREF
  _NDIS_CONFIGURATION_OBJECT ConfigObject; // [rsp+50h] [rbp-28h] BYREF
  int Status; // [rsp+B0h] [rbp+38h] BYREF

  Status = 0;
  ConfigurationHandle = 0;
  memset(&ConfigObject, 0, sizeof(ConfigObject));
  ParameterValue = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->Timer) & 0x81) == 0x81 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 15, WPP_bd95722c768d3598be23ac079e3ae056_Traceguids);
  ConfigObject.Header = (NDIS_OBJECT_HEADER)1573289;
  ConfigObject.NdisHandle = a1;
  Status = NdisOpenConfigurationEx(&ConfigObject, &ConfigurationHandle);
  v9 = Status;
  if ( Status >= 0 )
  {
    *a2 = 30000;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 17, WPP_bd95722c768d3598be23ac079e3ae056_Traceguids);
    }
    Keyword.Buffer = L"HelloDurationPerTick";
    *(_QWORD *)&Keyword.Length = 2752552;
    NdisReadConfiguration(&Status, &ParameterValue, ConfigurationHandle, &Keyword, NdisParameterInteger);
    if ( Status )
    {
      *a4 = 10;
      Status = 0;
    }
    else
    {
      IntegerData = ParameterValue->ParameterData.IntegerData;
      *a4 = IntegerData;
      if ( !IntegerData )
        Status = -1073676267;
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    {
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 18, WPP_bd95722c768d3598be23ac079e3ae056_Traceguids);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
      {
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 19, WPP_bd95722c768d3598be23ac079e3ae056_Traceguids);
      }
    }
    Keyword.Buffer = L"HelloTicks";
    *(_QWORD *)&Keyword.Length = 1441812;
    NdisReadConfiguration(&Status, &ParameterValue, ConfigurationHandle, &Keyword, NdisParameterInteger);
    if ( Status )
    {
      *a5 = 6;
      Status = 0;
    }
    else
    {
      v11 = ParameterValue->ParameterData.IntegerData;
      *a5 = v11;
      if ( !v11 )
        Status = -1073676267;
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    {
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 20, WPP_bd95722c768d3598be23ac079e3ae056_Traceguids);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
      {
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 21, WPP_bd95722c768d3598be23ac079e3ae056_Traceguids);
      }
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 16, WPP_bd95722c768d3598be23ac079e3ae056_Traceguids);
      v9 = Status;
    }
    *a3 = v9;
  }
  if ( ConfigurationHandle )
    NdisCloseConfiguration(ConfigurationHandle);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->Timer) & 0x81) == 0x81 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 22, WPP_bd95722c768d3598be23ac079e3ae056_Traceguids);
}

```

## disassembly

```asm
0x14000ebcc  push    rbp
0x14000ebce  push    rbx
0x14000ebcf  push    rsi
0x14000ebd0  push    rdi
0x14000ebd1  push    r12
0x14000ebd3  push    r14
0x14000ebd5  mov     rbp, rsp
0x14000ebd8  sub     rsp, 78h
0x14000ebdc  xorps   xmm0, xmm0
0x14000ebdf  mov     [rbp+Status], 0
0x14000ebe6  xor     eax, eax
0x14000ebe8  mov     [rbp+ConfigurationHandle], 0
0x14000ebf0  movups  xmmword ptr [rbp+ConfigObject.Header.Type], xmm0
0x14000ebf4  mov     qword ptr [rbp+ConfigObject.Flags], rax
0x14000ebf8  mov     rbx, r9
0x14000ebfb  mov     rsi, r8
0x14000ebfe  mov     [rbp+ParameterValue], 0
0x14000ec06  mov     rdi, rdx
0x14000ec09  mov     r14, rcx
0x14000ec0c  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ec13  lea     r12, WPP_GLOBAL_Control
0x14000ec1a  cmp     rcx, r12
0x14000ec1d  jz      short loc_14000EC40
0x14000ec1f  mov     eax, [rcx+2Ch]
0x14000ec22  and     eax, 81h
0x14000ec27  cmp     al, 81h
0x14000ec29  jnz     short loc_14000EC40
0x14000ec2b  mov     rcx, [rcx+18h]
0x14000ec2f  lea     r8, WPP_bd95722c768d3598be23ac079e3ae056_Traceguids
0x14000ec36  mov     edx, 0Fh
0x14000ec3b  call    WPP_SF_
0x14000ec40  lea     rdx, [rbp+ConfigurationHandle]; ConfigurationHandle
0x14000ec44  mov     dword ptr [rbp+ConfigObject.Header.Type], 1801A9h
0x14000ec4b  lea     rcx, [rbp+ConfigObject]; ConfigObject
0x14000ec4f  mov     [rbp+ConfigObject.NdisHandle], r14
0x14000ec53  call    cs:__imp_NdisOpenConfigurationEx
0x14000ec5a  nop     dword ptr [rax+rax+00h]
0x14000ec5f  mov     [rbp+Status], eax
0x14000ec62  mov     r8d, eax
0x14000ec65  mov     r14d, 16h
0x14000ec6b  test    eax, eax
0x14000ec6d  jns     short loc_14000ECAB
0x14000ec6f  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ec76  cmp     rcx, r12
0x14000ec79  jz      short loc_14000ECA3
0x14000ec7b  mov     eax, [rcx+2Ch]
0x14000ec7e  test    al, 1
0x14000ec80  jz      short loc_14000ECA3
0x14000ec82  cmp     byte ptr [rcx+29h], 1
0x14000ec86  jb      short loc_14000ECA3
0x14000ec88  mov     rcx, [rcx+18h]
0x14000ec8c  lea     edx, [r14-6]
0x14000ec90  mov     r9d, r8d
0x14000ec93  lea     r8, WPP_bd95722c768d3598be23ac079e3ae056_Traceguids
0x14000ec9a  call    WPP_SF_d
0x14000ec9f  mov     r8d, [rbp+Status]
0x14000eca3  mov     [rsi], r8d
0x14000eca6  jmp     loc_14000EE7C
0x14000ecab  mov     r9d, 7530h
0x14000ecb1  mov     [rdi], r9d
0x14000ecb4  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ecbb  mov     dil, 3
0x14000ecbe  cmp     rcx, r12
0x14000ecc1  jz      short loc_14000ECE5
0x14000ecc3  mov     eax, [rcx+2Ch]
0x14000ecc6  test    al, 1
0x14000ecc8  jz      short loc_14000ECE5
0x14000ecca  cmp     [rcx+29h], dil
0x14000ecce  jb      short loc_14000ECE5
0x14000ecd0  mov     rcx, [rcx+18h]
0x14000ecd4  lea     r8, WPP_bd95722c768d3598be23ac079e3ae056_Traceguids
0x14000ecdb  mov     edx, 11h
0x14000ece0  call    WPP_SF_d
0x14000ece5  mov     r8, [rbp+ConfigurationHandle]; ConfigurationHandle
0x14000ece9  lea     rax, aHellodurationp; "HelloDurationPerTick"
0x14000ecf0  lea     r9, [rbp+Keyword]; Keyword
0x14000ecf4  mov     [rbp+Keyword.Buffer], rax
0x14000ecf8  lea     rdx, [rbp+ParameterValue]; ParameterValue
0x14000ecfc  mov     qword ptr [rbp+Keyword.Length], 2A0028h
0x14000ed04  lea     rcx, [rbp+Status]; Status
0x14000ed08  mov     [rsp+78h+ParameterType], 0; ParameterType
0x14000ed10  call    cs:__imp_NdisReadConfiguration
0x14000ed17  nop     dword ptr [rax+rax+00h]
0x14000ed1c  mov     r9d, [rbp+Status]
0x14000ed20  mov     esi, 0C0010015h
0x14000ed25  test    r9d, r9d
0x14000ed28  jnz     short loc_14000ED40
0x14000ed2a  mov     rax, [rbp+ParameterValue]
0x14000ed2e  mov     ecx, [rax+8]
0x14000ed31  mov     [rbx], ecx
0x14000ed33  cmp     ecx, 1
0x14000ed36  jnb     short loc_14000ED4D
0x14000ed38  mov     r9d, esi
0x14000ed3b  mov     [rbp+Status], esi
0x14000ed3e  jmp     short loc_14000ED4D
0x14000ed40  xor     r9d, r9d
0x14000ed43  mov     dword ptr [rbx], 0Ah
0x14000ed49  mov     [rbp+Status], r9d
0x14000ed4d  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ed54  cmp     rcx, r12
0x14000ed57  jz      short loc_14000EDAC
0x14000ed59  mov     eax, [rcx+2Ch]
0x14000ed5c  test    al, 1
0x14000ed5e  jz      short loc_14000ED7B
0x14000ed60  cmp     [rcx+29h], dil
0x14000ed64  jb      short loc_14000ED7B
0x14000ed66  mov     rcx, [rcx+18h]
0x14000ed6a  lea     r8, WPP_bd95722c768d3598be23ac079e3ae056_Traceguids
0x14000ed71  mov     edx, 12h
0x14000ed76  call    WPP_SF_d
0x14000ed7b  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ed82  cmp     rcx, r12
0x14000ed85  jz      short loc_14000EDAC
0x14000ed87  mov     eax, [rcx+2Ch]
0x14000ed8a  test    al, 1
0x14000ed8c  jz      short loc_14000EDAC
0x14000ed8e  cmp     [rcx+29h], dil
0x14000ed92  jb      short loc_14000EDAC
0x14000ed94  mov     r9d, [rbx]
0x14000ed97  lea     r8, WPP_bd95722c768d3598be23ac079e3ae056_Traceguids
0x14000ed9e  mov     rcx, [rcx+18h]
0x14000eda2  mov     edx, 13h
0x14000eda7  call    WPP_SF_d
0x14000edac  mov     r8, [rbp+ConfigurationHandle]; ConfigurationHandle
0x14000edb0  lea     rax, aHelloticks; "HelloTicks"
0x14000edb7  lea     r9, [rbp+Keyword]; Keyword
0x14000edbb  mov     [rbp+Keyword.Buffer], rax
0x14000edbf  lea     rdx, [rbp+ParameterValue]; ParameterValue
0x14000edc3  mov     qword ptr [rbp+Keyword.Length], 160014h
0x14000edcb  lea     rcx, [rbp+Status]; Status
0x14000edcf  mov     [rsp+78h+ParameterType], 0; ParameterType
0x14000edd7  mov     r14d, 14h
0x14000eddd  call    cs:__imp_NdisReadConfiguration
0x14000ede4  nop     dword ptr [rax+rax+00h]
0x14000ede9  mov     r9d, [rbp+Status]
0x14000eded  mov     rbx, [rbp+arg_20]
0x14000edf1  test    r9d, r9d
0x14000edf4  jnz     short loc_14000EE0C
0x14000edf6  mov     rax, [rbp+ParameterValue]
0x14000edfa  mov     ecx, [rax+8]
0x14000edfd  mov     [rbx], ecx
0x14000edff  cmp     ecx, 1
0x14000ee02  jnb     short loc_14000EE19
0x14000ee04  mov     r9d, esi
0x14000ee07  mov     [rbp+Status], esi
0x14000ee0a  jmp     short loc_14000EE19
0x14000ee0c  xor     r9d, r9d
0x14000ee0f  mov     dword ptr [rbx], 6
0x14000ee15  mov     [rbp+Status], r9d
0x14000ee19  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ee20  cmp     rcx, r12
0x14000ee23  jz      short loc_14000EE76
0x14000ee25  mov     eax, [rcx+2Ch]
0x14000ee28  test    al, 1
0x14000ee2a  jz      short loc_14000EE45
0x14000ee2c  cmp     [rcx+29h], dil
0x14000ee30  jb      short loc_14000EE45
0x14000ee32  mov     rcx, [rcx+18h]
0x14000ee36  lea     r8, WPP_bd95722c768d3598be23ac079e3ae056_Traceguids
0x14000ee3d  mov     edx, r14d
0x14000ee40  call    WPP_SF_d
0x14000ee45  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ee4c  cmp     rcx, r12
0x14000ee4f  jz      short loc_14000EE76
0x14000ee51  mov     eax, [rcx+2Ch]
0x14000ee54  test    al, 1
0x14000ee56  jz      short loc_14000EE76
0x14000ee58  cmp     [rcx+29h], dil
0x14000ee5c  jb      short loc_14000EE76
0x14000ee5e  mov     r9d, [rbx]
0x14000ee61  lea     r8, WPP_bd95722c768d3598be23ac079e3ae056_Traceguids
0x14000ee68  mov     rcx, [rcx+18h]
0x14000ee6c  mov     edx, 15h
0x14000ee71  call    WPP_SF_d
0x14000ee76  mov     r14d, 16h
0x14000ee7c  mov     rcx, [rbp+ConfigurationHandle]; ConfigurationHandle
0x14000ee80  test    rcx, rcx
0x14000ee83  jz      short loc_14000EE91
0x14000ee85  call    cs:__imp_NdisCloseConfiguration
0x14000ee8c  nop     dword ptr [rax+rax+00h]
0x14000ee91  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ee98  cmp     rcx, r12
0x14000ee9b  jz      short loc_14000EEBC
0x14000ee9d  mov     eax, [rcx+2Ch]
0x14000eea0  and     eax, 81h
0x14000eea5  cmp     al, 81h
0x14000eea7  jnz     short loc_14000EEBC
0x14000eea9  mov     rcx, [rcx+18h]
0x14000eead  lea     r8, WPP_bd95722c768d3598be23ac079e3ae056_Traceguids
0x14000eeb4  mov     edx, r14d
0x14000eeb7  call    WPP_SF_
0x14000eebc  add     rsp, 78h
0x14000eec0  pop     r14
0x14000eec2  pop     r12
0x14000eec4  pop     rdi
0x14000eec5  pop     rsi
0x14000eec6  pop     rbx
0x14000eec7  pop     rbp
0x14000eec8  retn
```
