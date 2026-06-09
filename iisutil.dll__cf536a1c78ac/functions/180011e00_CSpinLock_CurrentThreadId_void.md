# CSpinLock::_CurrentThreadId(void)

- ea: `0x180011e00`
- end: `0x180011e19`
- name: `?_CurrentThreadId@CSpinLock@@CAJXZ`
- size: `25`
- prototype: `__int64(void)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180011e04`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180011e04`

## pseudocode

```c
__int64 CSpinLock::_CurrentThreadId(void)
{
  return GetCurrentThreadId() & 0xFFFFFFFC;
}

```

## disassembly

```asm
0x180011e00  sub     rsp, 28h; private: static long CReaderWriterLock3::_CurrentThreadId(void)
0x180011e04  call    cs:__imp_GetCurrentThreadId
0x180011e0b  nop     dword ptr [rax+rax+00h]
0x180011e10  and     eax, 0FFFFFFFCh
0x180011e13  add     rsp, 28h
0x180011e17  retn
```
