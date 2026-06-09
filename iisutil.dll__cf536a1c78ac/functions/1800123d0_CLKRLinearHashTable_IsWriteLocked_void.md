# CLKRLinearHashTable::IsWriteLocked(void)

- ea: `0x1800123d0`
- end: `0x1800123f6`
- name: `?IsWriteLocked@CLKRLinearHashTable@@QEBA_NXZ`
- size: `38`
- prototype: `bool __fastcall(CLKRLinearHashTable *__hidden this)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800123d9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800123d9`

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
0x1800123d0  push    rbx
0x1800123d2  sub     rsp, 20h
0x1800123d6  mov     ebx, [rcx+1Ch]
0x1800123d9  call    cs:__imp_GetCurrentThreadId
0x1800123e0  nop     dword ptr [rax+rax+00h]
0x1800123e5  xor     eax, ebx
0x1800123e7  test    eax, 0FFFFFFFCh
0x1800123ec  setz    al
0x1800123ef  add     rsp, 20h
0x1800123f3  pop     rbx
0x1800123f4  retn
```
