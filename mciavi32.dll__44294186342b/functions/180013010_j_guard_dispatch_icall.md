# j__guard_dispatch_icall

- ea: `0x180013010`
- end: `0x180013015`
- name: `j__guard_dispatch_icall`
- size: `5`
- prototype: ``
- caller_count: `28`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x1800010e8`
- `0x180001274`
- `0x18000164c`
- `0x1800018dc`
- `0x180001920`
- `0x18000397c`
- `0x180003d50`
- `0x180004c40`
- `0x1800051e8`
- `0x180005524`
- `0x180005c6c`
- `0x1800060a0`
- `0x1800067d0`
- `0x18000a0f8`
- `0x18000a85c`
- `0x18000ae48`
- `0x18000b0d8`
- `0x18000b2f0`
- `0x18000bbb4`
- `0x18000c3c8`
- `0x18000c830`
- `0x18000d7b0`
- `0x1800108a4`
- `0x1800109fc`
- `0x180010acc`
- `0x180010b88`
- `0x180010bcc`
- `0x180011420`

## callees

- `0x180011f40`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall j__guard_dispatch_icall()
{
  __int64 (__fastcall *v0)(); // rax

  return v0();
}

```

## disassembly

```asm
0x180013010  jmp     _guard_dispatch_icall
```
