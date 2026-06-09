# COConnectionPoint::Unadvise(ulong)

- ea: `0x18000d890`
- end: `0x18000d924`
- name: `?Unadvise@COConnectionPoint@@UEAAJK@Z`
- size: `148`
- prototype: `__int64 __fastcall(COConnectionPoint *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1800084a0`
- `0x18000d890`
- `0x18000d92c`

## import_xrefs

- `IisRTL!?ConvertExclusiveToShared@CReaderWriterLock3@@QEAAXXZ` at `0x18000d902`
- `IisRTL!?ConvertExclusiveToShared@CReaderWriterLock3@@QEAAXXZ` at `0x18000d902`
- `IisRTL!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000d8ce`
- `IisRTL!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000d8ce`
- `IisRTL!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000d91c`
- `IisRTL!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000d91c`
- `IisRTL!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000d8b9`
- `IisRTL!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000d8b9`

## pseudocode

```c
__int64 __fastcall COConnectionPoint::Unadvise(COConnectionPoint *this, unsigned int a2)
{
  unsigned int v4; // edi
  CReaderWriterLock3 *v5; // rsi

  if ( *((_DWORD *)this + 10) )
    return (unsigned int)-2147418113;
  v5 = (COConnectionPoint *)((char *)this + 8);
  CReaderWriterLock3::WriteLock((COConnectionPoint *)((char *)this + 8));
  if ( *((_DWORD *)this + 10) )
  {
    v4 = -2147418113;
LABEL_5:
    CReaderWriterLock3::WriteUnlock(v5);
    return v4;
  }
  v4 = COConnectionPoint::Unadvise_Worker(this, a2);
  if ( v4 == -2147418113 || *((_DWORD *)this + 6) )
    goto LABEL_5;
  CReaderWriterLock3::ConvertExclusiveToShared(v5);
  if ( !*((_DWORD *)this + 6) )
    CADMCOMW::RemoveAllPendingNotifications(*((CADMCOMW **)this + 2), 0);
  CReaderWriterLock3::ReadUnlock(v5);
  return v4;
}

```

## disassembly

```asm
0x18000d890  mov     [rsp+arg_0], rbx
0x18000d895  mov     [rsp+arg_8], rsi
0x18000d89a  push    rdi
0x18000d89b  sub     rsp, 20h
0x18000d89f  mov     eax, [rcx+28h]
0x18000d8a2  mov     edi, edx
0x18000d8a4  mov     rbx, rcx
0x18000d8a7  test    eax, eax
0x18000d8a9  jz      short loc_18000D8B2
0x18000d8ab  mov     edi, 8000FFFFh
0x18000d8b0  jmp     short loc_18000D8D4
0x18000d8b2  lea     rsi, [rcx+8]
0x18000d8b6  mov     rcx, rsi
0x18000d8b9  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x18000d8bf  mov     eax, [rbx+28h]
0x18000d8c2  test    eax, eax
0x18000d8c4  jz      short loc_18000D8E6
0x18000d8c6  mov     edi, 8000FFFFh
0x18000d8cb  mov     rcx, rsi
0x18000d8ce  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x18000d8d4  mov     rbx, [rsp+28h+arg_0]
0x18000d8d9  mov     eax, edi
0x18000d8db  mov     rsi, [rsp+28h+arg_8]
0x18000d8e0  add     rsp, 20h
0x18000d8e4  pop     rdi
0x18000d8e5  retn
0x18000d8e6  mov     edx, edi; unsigned int
0x18000d8e8  mov     rcx, rbx; this
0x18000d8eb  call    ?Unadvise_Worker@COConnectionPoint@@AEAAJK@Z; COConnectionPoint::Unadvise_Worker(ulong)
0x18000d8f0  mov     edi, eax
0x18000d8f2  cmp     eax, 8000FFFFh
0x18000d8f7  jz      short loc_18000D8CB
0x18000d8f9  cmp     dword ptr [rbx+18h], 0
0x18000d8fd  jnz     short loc_18000D8CB
0x18000d8ff  mov     rcx, rsi
0x18000d902  call    cs:__imp_?ConvertExclusiveToShared@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ConvertExclusiveToShared(void)
0x18000d908  cmp     dword ptr [rbx+18h], 0
0x18000d90c  jnz     short loc_18000D919
0x18000d90e  mov     rcx, [rbx+10h]; this
0x18000d912  xor     edx, edx; int
0x18000d914  call    ?RemoveAllPendingNotifications@CADMCOMW@@QEAAJH@Z; CADMCOMW::RemoveAllPendingNotifications(int)
0x18000d919  mov     rcx, rsi
0x18000d91c  call    cs:__imp_?ReadUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadUnlock(void)
0x18000d922  jmp     short loc_18000D8D4
```
