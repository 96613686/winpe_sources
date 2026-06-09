# _Init_thread_footer

- ea: `0x180014860`
- end: `0x1800148c0`
- name: `_Init_thread_footer`
- size: `96`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180005d0c`

## callees

- `0x180014934`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800148b0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800148b0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180014870`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180014870`

## pseudocode

```c
int __fastcall Init_thread_footer(_DWORD *a1)
{
  __int64 v2; // rdx

  EnterCriticalSection(&CriticalSection);
  v2 = (unsigned int)tls_index;
  *a1 = ++Init_global_epoch;
  *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + v2) + 4LL) = Init_global_epoch;
  LeaveCriticalSection(&CriticalSection);
  return Init_thread_notify();
}

```

## disassembly

```asm
0x180014860  push    rbx
0x180014862  sub     rsp, 20h
0x180014866  mov     rbx, rcx
0x180014869  lea     rcx, CriticalSection; lpCriticalSection
0x180014870  call    cs:__imp_EnterCriticalSection
0x180014876  mov     eax, cs:_Init_global_epoch
0x18001487c  lea     rcx, CriticalSection; lpCriticalSection
0x180014883  mov     edx, cs:_tls_index
0x180014889  inc     eax
0x18001488b  mov     cs:_Init_global_epoch, eax
0x180014891  mov     [rbx], eax
0x180014893  mov     rax, gs:58h
0x18001489c  mov     r9d, 4
0x1800148a2  mov     r8, [rax+rdx*8]
0x1800148a6  mov     eax, cs:_Init_global_epoch
0x1800148ac  mov     [r9+r8], eax
0x1800148b0  call    cs:__imp_LeaveCriticalSection
0x1800148b6  add     rsp, 20h
0x1800148ba  pop     rbx
0x1800148bb  jmp     _Init_thread_notify
```
