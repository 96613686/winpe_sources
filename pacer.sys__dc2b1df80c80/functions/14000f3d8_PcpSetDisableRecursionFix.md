# PcpSetDisableRecursionFix

- ea: `0x14000f3d8`
- end: `0x14000f486`
- name: `PcpSetDisableRecursionFix`
- size: `174`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x14000ebc0`

## callees

- `0x14000f3d8`

## import_xrefs

- `NDIS!NdisOpenConfigurationEx` at `0x14000f404`
- `NDIS!NdisOpenConfigurationEx` at `0x14000f404`
- `NDIS!NdisCloseConfiguration` at `0x14000f473`
- `NDIS!NdisCloseConfiguration` at `0x14000f473`
- `NDIS!NdisReadConfiguration` at `0x14000f44a`
- `NDIS!NdisReadConfiguration` at `0x14000f44a`

## pseudocode

```c
void __fastcall PcpSetDisableRecursionFix(void *a1)
{
  UNICODE_STRING Keyword; // [rsp+30h] [rbp-30h] BYREF
  _NDIS_CONFIGURATION_OBJECT ConfigObject; // [rsp+40h] [rbp-20h] BYREF
  int Status; // [rsp+70h] [rbp+10h] BYREF
  PVOID ConfigurationHandle; // [rsp+78h] [rbp+18h] BYREF
  PNDIS_CONFIGURATION_PARAMETER ParameterValue; // [rsp+80h] [rbp+20h] BYREF

  *(_QWORD *)&ConfigObject.Header.Type = 1311145;
  *(_QWORD *)&ConfigObject.Flags = 0;
  ConfigObject.NdisHandle = a1;
  ConfigurationHandle = 0;
  Status = NdisOpenConfigurationEx(&ConfigObject, &ConfigurationHandle);
  if ( !Status )
  {
    Keyword.Buffer = L"DisableRecursionFix";
    ParameterValue = 0;
    *(_QWORD *)&Keyword.Length = 2621478;
    NdisReadConfiguration(&Status, &ParameterValue, ConfigurationHandle, &Keyword, NdisParameterInteger);
    if ( !Status )
      PcgDisableRecursionFix = ParameterValue->ParameterData.IntegerData == 1;
    NdisCloseConfiguration(ConfigurationHandle);
  }
}

```

## disassembly

```asm
0x14000f3d8  push    rbp
0x14000f3da  mov     rbp, rsp
0x14000f3dd  sub     rsp, 60h
0x14000f3e1  xorps   xmm0, xmm0
0x14000f3e4  mov     qword ptr [rbp+ConfigObject.Header.Type], 1401A9h
0x14000f3ec  movups  xmmword ptr [rbp+ConfigObject.NdisHandle], xmm0
0x14000f3f0  mov     [rbp+ConfigObject.NdisHandle], rcx
0x14000f3f4  lea     rdx, [rbp+ConfigurationHandle]; ConfigurationHandle
0x14000f3f8  lea     rcx, [rbp+ConfigObject]; ConfigObject
0x14000f3fc  mov     [rbp+ConfigurationHandle], 0
0x14000f404  call    cs:__imp_NdisOpenConfigurationEx
0x14000f40b  nop     dword ptr [rax+rax+00h]
0x14000f410  mov     [rbp+Status], eax
0x14000f413  test    eax, eax
0x14000f415  jnz     short loc_14000F47F
0x14000f417  mov     r8, [rbp+ConfigurationHandle]; ConfigurationHandle
0x14000f41b  lea     rax, aDisablerecursi; "DisableRecursionFix"
0x14000f422  lea     r9, [rbp+Keyword]; Keyword
0x14000f426  mov     [rbp+Keyword.Buffer], rax
0x14000f42a  lea     rdx, [rbp+ParameterValue]; ParameterValue
0x14000f42e  mov     [rbp+ParameterValue], 0
0x14000f436  lea     rcx, [rbp+Status]; Status
0x14000f43a  mov     qword ptr [rbp+Keyword.Length], 280026h
0x14000f442  mov     [rsp+60h+ParameterType], 0; ParameterType
0x14000f44a  call    cs:__imp_NdisReadConfiguration
0x14000f451  nop     dword ptr [rax+rax+00h]
0x14000f456  cmp     [rbp+Status], 0
0x14000f45a  jnz     short loc_14000F46F
0x14000f45c  mov     rax, [rbp+ParameterValue]
0x14000f460  xor     ecx, ecx
0x14000f462  cmp     dword ptr [rax+8], 1
0x14000f466  setz    cl
0x14000f469  mov     cs:PcgDisableRecursionFix, ecx
0x14000f46f  mov     rcx, [rbp+ConfigurationHandle]; ConfigurationHandle
0x14000f473  call    cs:__imp_NdisCloseConfiguration
0x14000f47a  nop     dword ptr [rax+rax+00h]
0x14000f47f  add     rsp, 60h
0x14000f483  pop     rbp
0x14000f484  retn
```
