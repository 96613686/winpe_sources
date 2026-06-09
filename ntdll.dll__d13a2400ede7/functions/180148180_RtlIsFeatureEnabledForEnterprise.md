# RtlIsFeatureEnabledForEnterprise

- ea: `0x180148180`
- end: `0x1801481fa`
- name: `RtlIsFeatureEnabledForEnterprise`
- size: `122`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, installer_update`

## callees

- `0x180148180`
- `0x180148200`
- `0x1801482a8`
- `0x1801483f4`
- `0x180148478`

## string_xrefs

- `0x1801481a1`: `ActiveConfig`
- `0x18014818d`: `\Registry\Machine\SYSTEM\CurrentControlSet\Control\FeatureManagement\EnterpriseTempControls\Active`

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
0x180148180  push    rbx
0x180148182  sub     rsp, 20h
0x180148186  mov     ebx, ecx
0x180148188  mov     [rsp+28h+arg_8], 1
0x18014818d  lea     rcx, aRegistryMachin_11; "\\Registry\\Machine\\SYSTEM\\CurrentCon"...
0x180148194  mov     [rsp+28h+arg_10], 0
0x18014819c  lea     r8, [rsp+28h+arg_10]
0x1801481a1  lea     rdx, aActiveconfig; "ActiveConfig"
0x1801481a8  call    RtlpEtcGetDwordFromRegistry
0x1801481ad  test    eax, eax
0x1801481af  js      short loc_1801481EF
0x1801481b1  mov     edx, [rsp+28h+arg_10]
0x1801481b5  xor     ebx, 74161A4Eh
0x1801481bb  bswap   ebx
0x1801481bd  xor     ebx, 8FB23D4Fh
0x1801481c3  ror     ebx, 0FFh
0x1801481c6  xor     ebx, 833EA8FFh
0x1801481cc  mov     ecx, ebx
0x1801481ce  call    RtlpEtcIsValidFeatureId
0x1801481d3  test    al, al
0x1801481d5  jz      short loc_1801481EF
0x1801481d7  lea     rcx, [rsp+28h+arg_8]
0x1801481dc  call    RtlpEcReadPolicyState
0x1801481e1  test    eax, eax
0x1801481e3  jns     short loc_1801481EF
0x1801481e5  lea     rcx, [rsp+28h+arg_8]
0x1801481ea  call    RtlpEcReadSkuUpdateManagementGroup
0x1801481ef  mov     al, [rsp+28h+arg_8]
0x1801481f3  add     rsp, 20h
0x1801481f7  pop     rbx
0x1801481f8  retn
```
