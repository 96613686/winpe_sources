# CCompileProgressNotification::AddRef(void)

- ea: `0x140007260`
- end: `0x140007266`
- name: `?AddRef@CCompileProgressNotification@@UEAAKXZ`
- size: `6`
- prototype: `__int64 __fastcall(CCompileProgressNotification *this)`
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x14000a020`
- `0x14000a030`

## pseudocode

```c
__int64 __fastcall CCompileProgressNotification::AddRef(CCompileProgressNotification *this)
{
  return 2147500033LL;
}

```

## disassembly

```asm
0x140007260  mov     eax, 80004001h
0x140007265  retn
```
