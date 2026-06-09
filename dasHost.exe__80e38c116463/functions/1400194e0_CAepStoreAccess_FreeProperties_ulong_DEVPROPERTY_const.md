# CAepStoreAccess::FreeProperties(ulong,_DEVPROPERTY const *)

- ea: `0x1400194e0`
- end: `0x1400194ec`
- name: `?FreeProperties@CAepStoreAccess@@UEAAXKPEBU_DEVPROPERTY@@@Z`
- size: `12`
- prototype: `void __fastcall(CAepStoreAccess *__hidden this, unsigned int, const struct _DEVPROPERTY *)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-devices-query-l1-1-0!DevFreeObjectProperties` at `0x1400194e5`

## pseudocode

```c
void __fastcall CAepStoreAccess::FreeProperties(CAepStoreAccess *this, unsigned int a2, const struct _DEVPROPERTY *a3)
{
  DevFreeObjectProperties(a2, a3);
}

```

## disassembly

```asm
0x1400194e0  mov     ecx, edx
0x1400194e2  mov     rdx, r8
0x1400194e5  jmp     cs:__imp_DevFreeObjectProperties
```
