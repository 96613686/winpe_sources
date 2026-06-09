# CImpIMDCOMSINKW::AddRef(void)

- ea: `0x18000c190`
- end: `0x18000c19d`
- name: `?AddRef@CImpIMDCOMSINKW@@UEAAKXZ`
- size: `13`
- prototype: `unsigned int __fastcall(CImpIMDCOMSINKW *__hidden this)`
- caller_count: `0`
- callee_count: `0`
- tags: `installer_update, broker_com_uri`

## pseudocode

```c
__int64 __fastcall CImpIMDCOMSINKW::AddRef(CImpIMDCOMSINKW *this)
{
  return (unsigned int)_InterlockedIncrement((volatile signed __int32 *)this + 4);
}

```

## disassembly

```asm
0x18000c190  mov     eax, 1
0x18000c195  lock xadd [rcx+10h], eax
0x18000c19a  inc     eax
0x18000c19c  retn
```
