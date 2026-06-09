# CSmallSpinLock::IsWriteLocked(void)

- ea: `0x180016010`
- end: `0x18001602c`
- name: `?IsWriteLocked@CSmallSpinLock@@QEBA_NXZ`
- size: `28`
- prototype: `bool __fastcall(CSmallSpinLock *__hidden this)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x18001ad00`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180016019`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180016019`

## pseudocode

```c
bool __fastcall CSmallSpinLock::IsWriteLocked(CSmallSpinLock *this)
{
  return *(_DWORD *)this == GetCurrentThreadId();
}

```

## disassembly

```asm
0x180016010  push    rbx
0x180016012  sub     rsp, 20h
0x180016016  mov     rbx, rcx
0x180016019  call    cs:__imp_GetCurrentThreadId
0x18001601f  mov     ecx, [rbx]
0x180016021  cmp     ecx, eax
0x180016023  setz    al
0x180016026  add     rsp, 20h
0x18001602a  pop     rbx
0x18001602b  retn
```
