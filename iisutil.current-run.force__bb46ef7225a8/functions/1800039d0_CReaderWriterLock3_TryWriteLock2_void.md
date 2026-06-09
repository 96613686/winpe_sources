# CReaderWriterLock3::_TryWriteLock2(void)

- ea: `0x1800039d0`
- end: `0x1800039fc`
- name: `?_TryWriteLock2@CReaderWriterLock3@@AEAA_NXZ`
- size: `44`
- prototype: `bool __fastcall(CReaderWriterLock3 *__hidden this)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180003700`
- `0x1800038a0`
- `0x180003a10`
- `0x180007180`
- `0x180009af0`
- `0x18001b8b0`

## callees

- `0x1800039d0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800039d9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800039d9`

## pseudocode

```c
char __fastcall CReaderWriterLock3::_TryWriteLock2(CReaderWriterLock3 *this)
{
  if ( (*((_DWORD *)this + 1) & 0xFFFFFFFC) != (GetCurrentThreadId() & 0xFFFFFFFC) )
    return 0;
  _InterlockedIncrement((volatile signed __int32 *)this + 1);
  return 1;
}

```

## disassembly

```asm
0x1800039d0  push    rbx
0x1800039d2  sub     rsp, 20h
0x1800039d6  mov     rbx, rcx
0x1800039d9  call    cs:__imp_GetCurrentThreadId
0x1800039df  mov     edx, [rbx+4]
0x1800039e2  and     eax, 0FFFFFFFCh
0x1800039e5  and     edx, 0FFFFFFFCh
0x1800039e8  cmp     edx, eax
0x1800039ea  jz      short loc_1800039F4
0x1800039ec  xor     al, al
0x1800039ee  add     rsp, 20h
0x1800039f2  pop     rbx
0x1800039f3  retn
0x1800039f4  lock inc dword ptr [rbx+4]
0x1800039f8  mov     al, 1
0x1800039fa  jmp     short loc_1800039EE
```
