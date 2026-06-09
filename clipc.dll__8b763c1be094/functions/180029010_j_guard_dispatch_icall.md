# j__guard_dispatch_icall

- ea: `0x180029010`
- end: `0x180029015`
- name: `j__guard_dispatch_icall`
- size: `5`
- prototype: ``
- caller_count: `58`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x180001260`
- `0x1800014d8`
- `0x180001664`
- `0x1800018ec`
- `0x180001d40`
- `0x180001d84`
- `0x1800031ac`
- `0x180003a10`
- `0x180003af8`
- `0x1800051a0`
- `0x1800058d0`
- `0x1800059f0`
- `0x180005b10`
- `0x180005c28`
- `0x180005e7c`
- `0x180006320`
- `0x180006640`
- `0x180006920`
- `0x180006990`
- `0x180006ad0`
- `0x180006f34`
- `0x180007054`
- `0x18000717c`
- `0x180007410`
- `0x18001003c`
- `0x180019730`
- `0x18001a0d0`
- `0x18001a160`
- `0x18001a478`
- `0x18001a810`
- `0x18001ba90`
- `0x18001bb60`
- `0x18001bc30`
- `0x18001bca0`
- `0x18001dfd0`
- `0x18001e3f0`
- `0x18001eb10`
- `0x18001ed40`
- `0x18001efa0`
- `0x18001f280`
- `0x18001f600`
- `0x18001f730`
- `0x18001f910`
- `0x180021e30`
- `0x180022280`
- `0x1800224b0`
- `0x1800228b0`
- `0x180022df0`
- `0x1800230f0`
- `0x180023330`

## callees

- `0x1800280f0`

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
0x180029010  jmp     _guard_dispatch_icall
```
