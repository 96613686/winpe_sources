# CReaderWriterLock3::TryReadOrWriteLock(bool &)

- ea: `0x180010f90`
- end: `0x18001100b`
- name: `?TryReadOrWriteLock@CReaderWriterLock3@@QEAA_NAEA_N@Z`
- size: `123`
- prototype: `bool __fastcall(CReaderWriterLock3 *__hidden this, bool *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180005c80`
- `0x180010f90`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180010fa8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180010fa8`

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
0x180010f90  mov     [rsp+arg_0], rbx
0x180010f95  mov     [rsp+arg_8], rsi
0x180010f9a  push    rdi
0x180010f9b  sub     rsp, 20h
0x180010f9f  mov     ebx, [rcx+4]
0x180010fa2  mov     rsi, rdx
0x180010fa5  mov     rdi, rcx
0x180010fa8  call    cs:__imp_GetCurrentThreadId
0x180010faf  nop     dword ptr [rax+rax+00h]
0x180010fb4  xor     eax, ebx
0x180010fb6  test    eax, 0FFFFFFFCh
0x180010fbb  jz      short loc_180010FED
0x180010fbd  mov     ecx, [rdi]
0x180010fbf  cmp     cx, 0FFFFh
0x180010fc4  jz      short loc_180010FE9
0x180010fc6  lea     edx, [rcx+1]
0x180010fc9  mov     eax, ecx
0x180010fcb  lock cmpxchg [rdi], edx
0x180010fcf  cmp     ecx, eax
0x180010fd1  jnz     short loc_180010FE9
0x180010fd3  mov     byte ptr [rsi], 1
0x180010fd6  mov     al, 1
0x180010fd8  mov     rbx, [rsp+28h+arg_0]
0x180010fdd  mov     rsi, [rsp+28h+arg_8]
0x180010fe2  add     rsp, 20h
0x180010fe6  pop     rdi
0x180010fe7  retn
0x180010fe9  xor     al, al
0x180010feb  jmp     short loc_180010FD8
0x180010fed  mov     rcx, rdi; this
0x180010ff0  call    ?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x180010ff5  mov     rbx, [rsp+28h+arg_0]
0x180010ffa  mov     al, 1
0x180010ffc  mov     byte ptr [rsi], 0
0x180010fff  mov     rsi, [rsp+28h+arg_8]
0x180011004  add     rsp, 20h
0x180011008  pop     rdi
0x180011009  retn
```
