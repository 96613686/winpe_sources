# FdiCallbacks::CallbackFileRead(__int64,void *,uint)

- ea: `0x18000d060`
- end: `0x18000d068`
- name: `?CallbackFileRead@FdiCallbacks@@SAI_JPEAXI@Z`
- size: `8`
- prototype: `UINT __fastcall(void *const *hf, void *pv, UINT cb)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x18000bfdc`

## pseudocode

```c
UINT __fastcall FdiCallbacks::CallbackFileRead(void *const *hf, void *pv, UINT cb)
{
  return Utils::ReadFile(*hf, pv, cb);
}

```

## disassembly

```asm
0x18000d060  mov     rcx, [rcx]; void *
0x18000d063  jmp     ?ReadFile@Utils@@SAIQEAXPEAXI@Z; Utils::ReadFile(void * const,void *,uint)
```
