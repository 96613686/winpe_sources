# CLKRLinearHashTable::IsWriteLocked(void)

- ea: `0x180011120`
- end: `0x18001113f`
- name: `?IsWriteLocked@CLKRLinearHashTable@@QEBA_NXZ`
- size: `31`
- prototype: `bool __fastcall(CLKRLinearHashTable *__hidden this)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180011129`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180011129`

## pseudocode

```c
bool __fastcall CLKRLinearHashTable::IsWriteLocked(CLKRLinearHashTable *this)
{
  int v1; // ebx

  v1 = *((_DWORD *)this + 7);
  return ((v1 ^ GetCurrentThreadId()) & 0xFFFFFFFC) == 0;
}

```

## disassembly

```asm
0x180011120  push    rbx
0x180011122  sub     rsp, 20h
0x180011126  mov     ebx, [rcx+1Ch]
0x180011129  call    cs:__imp_GetCurrentThreadId
0x18001112f  xor     eax, ebx
0x180011131  test    eax, 0FFFFFFFCh
0x180011136  setz    al
0x180011139  add     rsp, 20h
0x18001113d  pop     rbx
0x18001113e  retn
```
