# CReaderWriterLock3::_TryWriteLock2(void)

- ea: `0x180004450`
- end: `0x180004483`
- name: `?_TryWriteLock2@CReaderWriterLock3@@AEAA_NXZ`
- size: `51`
- prototype: `bool __fastcall(CReaderWriterLock3 *__hidden this)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180004160`
- `0x180004320`
- `0x180004490`
- `0x180007e60`
- `0x18000a820`
- `0x18001c800`

## callees

- `0x180004450`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004459`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004459`

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
0x180004450  push    rbx
0x180004452  sub     rsp, 20h
0x180004456  mov     rbx, rcx
0x180004459  call    cs:__imp_GetCurrentThreadId
0x180004460  nop     dword ptr [rax+rax+00h]
0x180004465  mov     edx, [rbx+4]
0x180004468  and     eax, 0FFFFFFFCh
0x18000446b  and     edx, 0FFFFFFFCh
0x18000446e  cmp     edx, eax
0x180004470  jz      short loc_18000447B
0x180004472  xor     al, al
0x180004474  add     rsp, 20h
0x180004478  pop     rbx
0x180004479  retn
0x18000447b  lock inc dword ptr [rbx+4]
0x18000447f  mov     al, 1
0x180004481  jmp     short loc_180004474
```
