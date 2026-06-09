# CReaderWriterLock3::IsWriteLocked(void)

- ea: `0x18000add0`
- end: `0x18000adef`
- name: `?IsWriteLocked@CReaderWriterLock3@@QEBA_NXZ`
- size: `31`
- prototype: `bool __fastcall(CReaderWriterLock3 *__hidden this)`
- caller_count: `7`
- callee_count: `0`
- tags: ``

## callers

- `0x1800049c0`
- `0x18000a400`
- `0x18000ae00`
- `0x18001ae10`
- `0x18001ae90`
- `0x18001aef0`
- `0x18001af20`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000add9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000add9`

## pseudocode

```c
bool __fastcall CReaderWriterLock3::IsWriteLocked(CReaderWriterLock3 *this)
{
  int v1; // ebx

  v1 = *((_DWORD *)this + 1);
  return ((v1 ^ GetCurrentThreadId()) & 0xFFFFFFFC) == 0;
}

```

## disassembly

```asm
0x18000add0  push    rbx
0x18000add2  sub     rsp, 20h
0x18000add6  mov     ebx, [rcx+4]
0x18000add9  call    cs:__imp_GetCurrentThreadId
0x18000addf  xor     eax, ebx
0x18000ade1  test    eax, 0FFFFFFFCh
0x18000ade6  setz    al
0x18000ade9  add     rsp, 20h
0x18000aded  pop     rbx
0x18000adee  retn
```
