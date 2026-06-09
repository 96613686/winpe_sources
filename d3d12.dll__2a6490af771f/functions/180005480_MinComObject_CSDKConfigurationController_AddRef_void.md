# MinComObject<CSDKConfigurationController>::AddRef(void)

- ea: `0x180005480`
- end: `0x18000548d`
- name: `?AddRef@?$MinComObject@VCSDKConfigurationController@@@@UEAAKXZ`
- size: `13`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## pseudocode

```c
__int64 __fastcall MinComObject<CSDKConfigurationController>::AddRef(__int64 a1)
{
  return (unsigned int)_InterlockedIncrement((volatile signed __int32 *)(a1 + 8));
}

```

## disassembly

```asm
0x180005480  mov     eax, 1
0x180005485  lock xadd [rcx+8], eax
0x18000548a  inc     eax
0x18000548c  retn
```
