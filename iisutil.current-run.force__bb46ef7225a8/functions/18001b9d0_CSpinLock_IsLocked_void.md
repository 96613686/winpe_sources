# CSpinLock::_IsLocked(void)

- ea: `0x18001b9d0`
- end: `0x18001b9f2`
- name: `?_IsLocked@CSpinLock@@AEBA_NXZ`
- size: `34`
- prototype: `bool __fastcall(CSpinLock *__hidden this)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x18001ac80`
- `0x18001adc0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001b9d9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001b9d9`

## pseudocode

```c
bool __fastcall CSpinLock::_IsLocked(CSpinLock *this)
{
  return (*(_DWORD *)this & 0xFFFFFFFC) == (GetCurrentThreadId() & 0xFFFFFFFC);
}

```

## disassembly

```asm
0x18001b9d0  push    rbx
0x18001b9d2  sub     rsp, 20h
0x18001b9d6  mov     rbx, rcx
0x18001b9d9  call    cs:__imp_GetCurrentThreadId
0x18001b9df  mov     ecx, [rbx]
0x18001b9e1  and     eax, 0FFFFFFFCh
0x18001b9e4  and     ecx, 0FFFFFFFCh
0x18001b9e7  cmp     ecx, eax
0x18001b9e9  setz    al
0x18001b9ec  add     rsp, 20h
0x18001b9f0  pop     rbx
0x18001b9f1  retn
```
