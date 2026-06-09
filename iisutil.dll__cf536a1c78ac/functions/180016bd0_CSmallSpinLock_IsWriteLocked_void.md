# CSmallSpinLock::IsWriteLocked(void)

- ea: `0x180016bd0`
- end: `0x180016bf3`
- name: `?IsWriteLocked@CSmallSpinLock@@QEBA_NXZ`
- size: `35`
- prototype: `bool __fastcall(CSmallSpinLock *__hidden this)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x18001bbe0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180016bd9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180016bd9`

## pseudocode

```c
bool __fastcall CSmallSpinLock::IsWriteLocked(CSmallSpinLock *this)
{
  return *(_DWORD *)this == GetCurrentThreadId();
}

```

## disassembly

```asm
0x180016bd0  push    rbx
0x180016bd2  sub     rsp, 20h
0x180016bd6  mov     rbx, rcx
0x180016bd9  call    cs:__imp_GetCurrentThreadId
0x180016be0  nop     dword ptr [rax+rax+00h]
0x180016be5  mov     ecx, [rbx]
0x180016be7  cmp     ecx, eax
0x180016be9  setz    al
0x180016bec  add     rsp, 20h
0x180016bf0  pop     rbx
0x180016bf1  retn
```
