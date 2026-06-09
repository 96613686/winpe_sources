# MinComObject<CSDKConfigurationController>::~MinComObject<CSDKConfigurationController>(void)

- ea: `0x18000e7e8`
- end: `0x18000e7fa`
- name: `??1?$MinComObject@VCSDKConfigurationController@@@@UEAA@XZ`
- size: `18`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000e800`

## pseudocode

```c
void **__fastcall MinComObject<CSDKConfigurationController>::~MinComObject<CSDKConfigurationController>(__int64 a1)
{
  void **result; // rax

  result = &MinComObject<CSDKConfigurationController>::`vftable';
  *(_DWORD *)(a1 + 8) = -1073741823;
  *(_QWORD *)a1 = &MinComObject<CSDKConfigurationController>::`vftable';
  return result;
}

```

## disassembly

```asm
0x18000e7e8  lea     rax, ??_7?$MinComObject@VCSDKConfigurationController@@@@6B@; const MinComObject<CSDKConfigurationController>::`vftable'
0x18000e7ef  mov     dword ptr [rcx+8], 0C0000001h
0x18000e7f6  mov     [rcx], rax
0x18000e7f9  retn
```
