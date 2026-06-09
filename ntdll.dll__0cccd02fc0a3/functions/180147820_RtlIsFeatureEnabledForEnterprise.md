# RtlIsFeatureEnabledForEnterprise

- ea: `0x180147820`
- end: `0x18014789a`
- name: `RtlIsFeatureEnabledForEnterprise`
- size: `122`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, installer_update`

## callees

- `0x180147820`
- `0x1801478a0`
- `0x180147948`
- `0x180147a94`
- `0x180147b18`

## string_xrefs

- `0x180147841`: `ActiveConfig`
- `0x18014782d`: `\Registry\Machine\SYSTEM\CurrentControlSet\Control\FeatureManagement\EnterpriseTempControls\Active`

## pseudocode

```c
char __fastcall RtlIsFeatureEnabledForEnterprise(int a1)
{
  char v3; // [rsp+38h] [rbp+10h] BYREF
  unsigned int v4; // [rsp+40h] [rbp+18h] BYREF

  v3 = 1;
  v4 = 0;
  if ( (int)RtlpEtcGetDwordFromRegistry(
              L"\\Registry\\Machine\\SYSTEM\\CurrentControlSet\\Control\\FeatureManagement\\EnterpriseTempControls\\Active",
              L"ActiveConfig",
              &v4) >= 0
    && (unsigned __int8)RtlpEtcIsValidFeatureId(
                          __ROR4__(_byteswap_ulong(a1 ^ 0x74161A4E) ^ 0x8FB23D4F, 255) ^ 0x833EA8FF,
                          v4)
    && (int)RtlpEcReadPolicyState((bool *)&v3) < 0 )
  {
    RtlpEcReadSkuUpdateManagementGroup(&v3);
  }
  return v3;
}

```

## disassembly

```asm
0x180147820  push    rbx
0x180147822  sub     rsp, 20h
0x180147826  mov     ebx, ecx
0x180147828  mov     [rsp+28h+arg_8], 1
0x18014782d  lea     rcx, aRegistryMachin_11; "\\Registry\\Machine\\SYSTEM\\CurrentCon"...
0x180147834  mov     [rsp+28h+arg_10], 0
0x18014783c  lea     r8, [rsp+28h+arg_10]
0x180147841  lea     rdx, aActiveconfig; "ActiveConfig"
0x180147848  call    RtlpEtcGetDwordFromRegistry
0x18014784d  test    eax, eax
0x18014784f  js      short loc_18014788F
0x180147851  mov     edx, [rsp+28h+arg_10]
0x180147855  xor     ebx, 74161A4Eh
0x18014785b  bswap   ebx
0x18014785d  xor     ebx, 8FB23D4Fh
0x180147863  ror     ebx, 0FFh
0x180147866  xor     ebx, 833EA8FFh
0x18014786c  mov     ecx, ebx
0x18014786e  call    RtlpEtcIsValidFeatureId
0x180147873  test    al, al
0x180147875  jz      short loc_18014788F
0x180147877  lea     rcx, [rsp+28h+arg_8]
0x18014787c  call    RtlpEcReadPolicyState
0x180147881  test    eax, eax
0x180147883  jns     short loc_18014788F
0x180147885  lea     rcx, [rsp+28h+arg_8]
0x18014788a  call    RtlpEcReadSkuUpdateManagementGroup
0x18014788f  mov     al, [rsp+28h+arg_8]
0x180147893  add     rsp, 20h
0x180147897  pop     rbx
0x180147898  retn
```
