# Windows::Internal::CHSTRINGResult::Close(void)

- ea: `0x18002669c`
- end: `0x1800266ef`
- name: `?Close@CHSTRINGResult@Internal@Windows@@QEAAXXZ`
- size: `83`
- prototype: `void __fastcall(Windows::Internal::CHSTRINGResult *__hidden this)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180029400`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800266b2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800266b2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800266d0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800266d0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800266ba`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800266ba`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800266e8`

## pseudocode

```c
void __fastcall Windows::Internal::CHSTRINGResult::Close(RTL_SRWLOCK *this)
{
  HSTRING Ptr; // rbx

  AcquireSRWLockExclusive(this + 3);
  WindowsDeleteString(0);
  Ptr = (HSTRING)this[2].Ptr;
  this[2].Ptr = 0;
  ReleaseSRWLockExclusive(this + 3);
  WindowsDeleteString(Ptr);
}

```

## disassembly

```asm
0x18002669c  mov     [rsp+arg_0], rbx
0x1800266a1  mov     [rsp+arg_8], rsi
0x1800266a6  push    rdi
0x1800266a7  sub     rsp, 20h
0x1800266ab  mov     rsi, rcx
0x1800266ae  add     rcx, 18h; SRWLock
0x1800266b2  call    cs:__imp_AcquireSRWLockExclusive
0x1800266b8  xor     ecx, ecx; string
0x1800266ba  call    cs:__imp_WindowsDeleteString
0x1800266c0  mov     rbx, [rsi+10h]
0x1800266c4  lea     rcx, [rsi+18h]; SRWLock
0x1800266c8  mov     qword ptr [rsi+10h], 0
0x1800266d0  call    cs:__imp_ReleaseSRWLockExclusive
0x1800266d6  mov     rcx, rbx
0x1800266d9  mov     rbx, [rsp+28h+arg_0]
0x1800266de  mov     rsi, [rsp+28h+arg_8]
0x1800266e3  add     rsp, 20h
0x1800266e7  pop     rdi
0x1800266e8  jmp     cs:__imp_WindowsDeleteString
```
