# CReaderWriterLock3::IsWriteLocked(void)

- ea: `0x18000bea0`
- end: `0x18000bec6`
- name: `?IsWriteLocked@CReaderWriterLock3@@QEBA_NXZ`
- size: `38`
- prototype: `bool __fastcall(CReaderWriterLock3 *__hidden this)`
- caller_count: `7`
- callee_count: `0`
- tags: ``

## callers

- `0x180005520`
- `0x18000b690`
- `0x18000b840`
- `0x18001bcf0`
- `0x18001bd80`
- `0x18001bde0`
- `0x18001be20`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000bea9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000bea9`

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
0x18000bea0  push    rbx
0x18000bea2  sub     rsp, 20h
0x18000bea6  mov     ebx, [rcx+4]
0x18000bea9  call    cs:__imp_GetCurrentThreadId
0x18000beb0  nop     dword ptr [rax+rax+00h]
0x18000beb5  xor     eax, ebx
0x18000beb7  test    eax, 0FFFFFFFCh
0x18000bebc  setz    al
0x18000bebf  add     rsp, 20h
0x18000bec3  pop     rbx
0x18000bec4  retn
```
