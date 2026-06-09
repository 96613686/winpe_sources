# Microsoft::WRL::Details::RaiseException(long,ulong)

- ea: `0x14000f44c`
- end: `0x14000f45d`
- name: `?RaiseException@Details@WRL@Microsoft@@YAXJK@Z`
- size: `17`
- prototype: `void __fastcall(Microsoft::WRL::Details *__hidden this, int, unsigned int)`
- caller_count: `4`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x14000ec30`
- `0x14000ec9c`
- `0x14000ed0c`
- `0x14000ee40`

## import_xrefs

- `KERNEL32!RaiseException` at `0x14000f456`

## pseudocode

```c
void __fastcall Microsoft::WRL::Details::RaiseException(Microsoft::WRL::Details *this)
{
  RaiseException((DWORD)this, 1u, 0, 0);
}

```

## disassembly

```asm
0x14000f44c  xor     r9d, r9d
0x14000f44f  xor     r8d, r8d
0x14000f452  lea     edx, [r9+1]
0x14000f456  jmp     cs:__imp_RaiseException
```
