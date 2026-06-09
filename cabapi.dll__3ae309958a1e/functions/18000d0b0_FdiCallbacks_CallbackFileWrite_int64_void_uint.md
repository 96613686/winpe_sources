# FdiCallbacks::CallbackFileWrite(__int64,void *,uint)

- ea: `0x18000d0b0`
- end: `0x18000d0b8`
- name: `?CallbackFileWrite@FdiCallbacks@@SAI_JPEAXI@Z`
- size: `8`
- prototype: `UINT __fastcall(void *const *hf, void *pv, UINT cb)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x18000c48c`

## pseudocode

```c
UINT __fastcall FdiCallbacks::CallbackFileWrite(void *const *hf, void *pv, UINT cb)
{
  return Utils::WriteFile(*hf, pv, cb);
}

```

## disassembly

```asm
0x18000d0b0  mov     rcx, [rcx]; void *
0x18000d0b3  jmp     ?WriteFile@Utils@@SAIQEAXPEBXI@Z; Utils::WriteFile(void * const,void const *,uint)
```
