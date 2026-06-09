# _guard_dispatch_icall

- ea: `0x14003abe0`
- end: `0x14003abe6`
- name: `_guard_dispatch_icall`
- size: `6`
- prototype: ``
- caller_count: `57`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x140009f60`
- `0x14000baf0`
- `0x1400159cc`
- `0x1400159fc`
- `0x140015a40`
- `0x140015ab8`
- `0x1400173f8`
- `0x14001744c`
- `0x140017538`
- `0x140017590`
- `0x1400175d4`
- `0x140018310`
- `0x140018a20`
- `0x140019cd0`
- `0x140019d7c`
- `0x140019e3c`
- `0x140019fc4`
- `0x14001db18`
- `0x140020b64`
- `0x140020bf4`
- `0x1400222b4`
- `0x140022300`
- `0x140022364`
- `0x1400232c0`
- `0x140023518`
- `0x140024f6c`
- `0x140025be0`
- `0x14002a1ac`
- `0x14002a20c`
- `0x14002a2fc`
- `0x14002a3c8`
- `0x14002a478`
- `0x14002b650`
- `0x14002b6b8`
- `0x14002b730`
- `0x14002cb04`
- `0x14002cc34`
- `0x14002cd24`
- `0x14002cdf0`
- `0x14002cef0`
- `0x14002d2e8`
- `0x14002efe0`
- `0x140034534`
- `0x140034590`
- `0x140034600`
- `0x140034f90`
- `0x140035048`
- `0x140037244`
- `0x1400384f4`
- `0x140038550`

## callees

- `0x14003ac10`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall guard_dispatch_icall()
{
  __int64 (__fastcall *v0)(); // rax

  return v0();
}

```

## disassembly

```asm
0x14003abe0  jmp     cs:__guard_dispatch_icall_fptr
```
