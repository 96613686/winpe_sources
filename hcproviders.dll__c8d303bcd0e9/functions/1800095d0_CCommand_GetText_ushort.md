# CCommand::GetText(ushort * *)

- ea: `0x1800095d0`
- end: `0x1800095dc`
- name: `?GetText@CCommand@@UEAAJPEAPEAG@Z`
- size: `12`
- prototype: `__int64 __fastcall(CCommand *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180002eb0`

## pseudocode

```c
__int64 __fastcall CCommand::GetText(char **this, unsigned __int16 **a2)
{
  return _AllocString<CTCoAllocPolicy>((__int64)this, (__int64)a2, *(this - 3), a2);
}

```

## disassembly

```asm
0x1800095d0  mov     r8, [rcx-18h]
0x1800095d4  mov     r9, rdx
0x1800095d7  jmp     ??$_AllocString@VCTCoAllocPolicy@@@@YAJPEAXKPEBGPEAPEAG@Z; _AllocString<CTCoAllocPolicy>(void *,ulong,ushort const *,ushort * *)
```
