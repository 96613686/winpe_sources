# CReaderWriterLock3::TryReadOrWriteLock(bool &)

- ea: `0x18000fbd0`
- end: `0x18000fc43`
- name: `?TryReadOrWriteLock@CReaderWriterLock3@@QEAA_NAEA_N@Z`
- size: `115`
- prototype: `bool __fastcall(CReaderWriterLock3 *__hidden this, bool *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180005110`
- `0x18000fbd0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000fbe8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000fbe8`

## pseudocode

```c
bool __fastcall CReaderWriterLock3::TryReadOrWriteLock(CReaderWriterLock3 *this, bool *a2)
{
  int v2; // ebx
  signed __int32 v5; // ecx
  bool result; // al

  v2 = *((_DWORD *)this + 1);
  if ( ((v2 ^ GetCurrentThreadId()) & 0xFFFFFFFC) != 0 )
  {
    if ( (unsigned __int16)*(_DWORD *)this == 0xFFFF )
      return 0;
    v5 = *(_DWORD *)this;
    if ( v5 != _InterlockedCompareExchange((volatile signed __int32 *)this, v5 + 1, v5) )
    {
      return 0;
    }
    else
    {
      *a2 = 1;
      return 1;
    }
  }
  else
  {
    CReaderWriterLock3::WriteLock(this);
    result = 1;
    *a2 = 0;
  }
  return result;
}

```

## disassembly

```asm
0x18000fbd0  mov     [rsp+arg_0], rbx
0x18000fbd5  mov     [rsp+arg_8], rsi
0x18000fbda  push    rdi
0x18000fbdb  sub     rsp, 20h
0x18000fbdf  mov     ebx, [rcx+4]
0x18000fbe2  mov     rsi, rdx
0x18000fbe5  mov     rdi, rcx
0x18000fbe8  call    cs:__imp_GetCurrentThreadId
0x18000fbee  xor     eax, ebx
0x18000fbf0  test    eax, 0FFFFFFFCh
0x18000fbf5  jz      short loc_18000FC26
0x18000fbf7  mov     ecx, [rdi]
0x18000fbf9  cmp     cx, 0FFFFh
0x18000fbfe  jz      short loc_18000FC22
0x18000fc00  lea     edx, [rcx+1]
0x18000fc03  mov     eax, ecx
0x18000fc05  lock cmpxchg [rdi], edx
0x18000fc09  cmp     ecx, eax
0x18000fc0b  jnz     short loc_18000FC22
0x18000fc0d  mov     byte ptr [rsi], 1
0x18000fc10  mov     al, 1
0x18000fc12  mov     rbx, [rsp+28h+arg_0]
0x18000fc17  mov     rsi, [rsp+28h+arg_8]
0x18000fc1c  add     rsp, 20h
0x18000fc20  pop     rdi
0x18000fc21  retn
0x18000fc22  xor     al, al
0x18000fc24  jmp     short loc_18000FC12
0x18000fc26  mov     rcx, rdi; this
0x18000fc29  call    ?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x18000fc2e  mov     rbx, [rsp+28h+arg_0]
0x18000fc33  mov     al, 1
0x18000fc35  mov     byte ptr [rsi], 0
0x18000fc38  mov     rsi, [rsp+28h+arg_8]
0x18000fc3d  add     rsp, 20h
0x18000fc41  pop     rdi
0x18000fc42  retn
```
