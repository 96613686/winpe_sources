# CSpinLock::_CurrentThreadId(void)

- ea: `0x180010de0`
- end: `0x180010df2`
- name: `?_CurrentThreadId@CSpinLock@@CAJXZ`
- size: `18`
- prototype: `__int64(void)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180010de4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180010de4`

## pseudocode

```c
__int64 CSpinLock::_CurrentThreadId(void)
{
  return GetCurrentThreadId() & 0xFFFFFFFC;
}

```

## disassembly

```asm
0x180010de0  sub     rsp, 28h; private: static long CReaderWriterLock3::_CurrentThreadId(void)
0x180010de4  call    cs:__imp_GetCurrentThreadId
0x180010dea  and     eax, 0FFFFFFFCh
0x180010ded  add     rsp, 28h
0x180010df1  retn
```
