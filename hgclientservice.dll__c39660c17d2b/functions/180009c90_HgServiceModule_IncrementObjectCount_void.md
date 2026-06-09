# HgServiceModule::IncrementObjectCount(void)

- ea: `0x180009c90`
- end: `0x180009c9a`
- name: `?IncrementObjectCount@HgServiceModule@@UEAAKXZ`
- size: `10`
- prototype: `__int64 __fastcall(HgServiceModule *this)`
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## import_xrefs

- `combase!__imp_CoAddRefSharedService` at `0x180009c93`

## pseudocode

```c
__int64 __fastcall HgServiceModule::IncrementObjectCount(HgServiceModule *this)
{
  return CoAddRefSharedService(*((unsigned int *)this + 4));
}

```

## disassembly

```asm
0x180009c90  mov     ecx, [rcx+10h]
0x180009c93  jmp     cs:__imp_CoAddRefSharedService
```
