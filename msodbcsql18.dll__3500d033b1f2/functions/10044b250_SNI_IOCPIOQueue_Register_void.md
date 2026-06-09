# SNI_IOCPIOQueue::Register(void *)

- ea: `0x10044b250`
- end: `0x10044b2d7`
- name: `?Register@SNI_IOCPIOQueue@@UEAAKPEAX@Z`
- size: `135`
- prototype: `unsigned int(SNI_IOCPIOQueue *__hidden this, void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x10043a7c4`
- `0x10043a930`
- `0x10044b250`
- `0x100546aa8`

## import_xrefs

- `KERNEL32!CreateIoCompletionPort` at `0x10044b266`
- `KERNEL32!CreateIoCompletionPort` at `0x10044b266`
- `KERNEL32!GetLastError` at `0x10044b271`
- `KERNEL32!GetLastError` at `0x10044b271`

## pseudocode

```c
__int64 __fastcall SNI_IOCPIOQueue::Register(SNI_IOCPIOQueue *this, void *a2)
{
  DWORD LastError; // ebx

  if ( CreateIoCompletionPort(a2, ghIoCompletionPort, 0, 0) )
    return 0;
  LastError = GetLastError();
  if ( (bidGblFlags & 2) != 0 )
  {
    if ( off_1005E6728[0] )
    {
      SniErrorIdFromStringId(0xC3BDu);
      bidTraceW(0, 38912, off_1005E6728[0], 9);
    }
  }
  SNISetLastError(9, LastError, 50109);
  return LastError;
}

```

## disassembly

```asm
0x10044b250  push    rbx
0x10044b252  sub     rsp, 30h
0x10044b256  mov     rcx, rdx; FileHandle
0x10044b259  xor     r9d, r9d; NumberOfConcurrentThreads
0x10044b25c  mov     rdx, cs:?ghIoCompletionPort@@3PEAXEA; ExistingCompletionPort
0x10044b263  xor     r8d, r8d; CompletionKey
0x10044b266  call    cs:__imp_CreateIoCompletionPort
0x10044b26c  test    rax, rax
0x10044b26f  jnz     short loc_10044B2CF
0x10044b271  call    cs:__imp_GetLastError
0x10044b277  test    byte ptr cs:_bidGblFlags, 2
0x10044b27e  mov     ebx, eax
0x10044b280  jz      short loc_10044B2B9
0x10044b282  mov     rcx, cs:off_1005E6728; "<SNI_IOCPIOQueue::Register|ERR|SNI> Pro"...
0x10044b289  test    rcx, rcx
0x10044b28c  jz      short loc_10044B2B9
0x10044b28e  mov     ecx, 0C3BDh; unsigned int
0x10044b293  call    ?SniErrorIdFromStringId@@YAKK@Z; SniErrorIdFromStringId(ulong)
0x10044b298  mov     r8, cs:off_1005E6728; "<SNI_IOCPIOQueue::Register|ERR|SNI> Pro"...
0x10044b29f  mov     r9d, 9
0x10044b2a5  mov     edx, 9800h
0x10044b2aa  mov     [rsp+38h+var_10], ebx
0x10044b2ae  xor     ecx, ecx
0x10044b2b0  mov     [rsp+38h+var_18], eax
0x10044b2b4  call    _bidTraceW
0x10044b2b9  mov     r8d, 0C3BDh
0x10044b2bf  mov     edx, ebx
0x10044b2c1  mov     ecx, 9
0x10044b2c6  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x10044b2cb  mov     eax, ebx
0x10044b2cd  jmp     short loc_10044B2D1
0x10044b2cf  xor     eax, eax
0x10044b2d1  add     rsp, 30h
0x10044b2d5  pop     rbx
0x10044b2d6  retn
```
