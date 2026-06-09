# IASVssWriter::ReleaseVssLock(void)

- ea: `0x18000ca40`
- end: `0x18000ca4b`
- name: `?ReleaseVssLock@IASVssWriter@@UEAAXXZ`
- size: `11`
- prototype: `void __fastcall(IASVssWriter *__hidden this)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18000ca44`

## pseudocode

```c
void __fastcall IASVssWriter::ReleaseVssLock(IASVssWriter *this)
{
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
}

```

## disassembly

```asm
0x18000ca40  add     rcx, 8
0x18000ca44  jmp     cs:__imp_LeaveCriticalSection
```
