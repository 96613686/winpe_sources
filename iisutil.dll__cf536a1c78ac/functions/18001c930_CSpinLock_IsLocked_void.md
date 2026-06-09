# CSpinLock::_IsLocked(void)

- ea: `0x18001c930`
- end: `0x18001c959`
- name: `?_IsLocked@CSpinLock@@AEBA_NXZ`
- size: `41`
- prototype: `bool __fastcall(CSpinLock *__hidden this)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x18001bb60`
- `0x18001bca0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001c939`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001c939`

## pseudocode

```c
bool __fastcall CSpinLock::_IsLocked(CSpinLock *this)
{
  return (*(_DWORD *)this & 0xFFFFFFFC) == (GetCurrentThreadId() & 0xFFFFFFFC);
}

```

## disassembly

```asm
0x18001c930  push    rbx
0x18001c932  sub     rsp, 20h
0x18001c936  mov     rbx, rcx
0x18001c939  call    cs:__imp_GetCurrentThreadId
0x18001c940  nop     dword ptr [rax+rax+00h]
0x18001c945  mov     ecx, [rbx]
0x18001c947  and     eax, 0FFFFFFFCh
0x18001c94a  and     ecx, 0FFFFFFFCh
0x18001c94d  cmp     ecx, eax
0x18001c94f  setz    al
0x18001c952  add     rsp, 20h
0x18001c956  pop     rbx
0x18001c957  retn
```
