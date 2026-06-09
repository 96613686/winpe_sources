# Windows::Internal::CHSTRINGResult::Close(void)

- ea: `0x18008d1fc`
- end: `0x18008d24f`
- name: `?Close@CHSTRINGResult@Internal@Windows@@QEAAXXZ`
- size: `83`
- prototype: `void __fastcall(Windows::Internal::CHSTRINGResult *__hidden this)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x18008de10`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18008d212`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18008d212`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18008d230`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18008d230`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008d21a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008d21a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008d248`

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
0x18008d1fc  mov     [rsp+arg_0], rbx
0x18008d201  mov     [rsp+arg_8], rsi
0x18008d206  push    rdi
0x18008d207  sub     rsp, 20h
0x18008d20b  mov     rsi, rcx
0x18008d20e  add     rcx, 18h; SRWLock
0x18008d212  call    cs:__imp_AcquireSRWLockExclusive
0x18008d218  xor     ecx, ecx; string
0x18008d21a  call    cs:__imp_WindowsDeleteString
0x18008d220  mov     rbx, [rsi+10h]
0x18008d224  lea     rcx, [rsi+18h]; SRWLock
0x18008d228  mov     qword ptr [rsi+10h], 0
0x18008d230  call    cs:__imp_ReleaseSRWLockExclusive
0x18008d236  mov     rcx, rbx
0x18008d239  mov     rbx, [rsp+28h+arg_0]
0x18008d23e  mov     rsi, [rsp+28h+arg_8]
0x18008d243  add     rsp, 20h
0x18008d247  pop     rdi
0x18008d248  jmp     cs:__imp_WindowsDeleteString
```
