# HgServiceModule::DecrementObjectCount(void)

- ea: `0x180009a70`
- end: `0x180009a7a`
- name: `?DecrementObjectCount@HgServiceModule@@UEAAKXZ`
- size: `10`
- prototype: `__int64 __fastcall(HgServiceModule *this)`
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## import_xrefs

- `combase!__imp_CoReleaseSharedService` at `0x180009a73`

## pseudocode

```c
__int64 __fastcall HgServiceModule::DecrementObjectCount(HgServiceModule *this)
{
  return CoReleaseSharedService(*((unsigned int *)this + 4));
}

```

## disassembly

```asm
0x180009a70  mov     ecx, [rcx+10h]
0x180009a73  jmp     cs:__imp_CoReleaseSharedService
```
