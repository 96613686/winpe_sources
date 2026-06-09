# CMDCOM::ComMDReleaseReferenceData(ulong)

- ea: `0x180019110`
- end: `0x180019170`
- name: `?ComMDReleaseReferenceData@CMDCOM@@UEAAJK@Z`
- size: `96`
- prototype: `int(CMDCOM *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180014abc`
- `0x180014fc8`
- `0x180019110`

## import_xrefs

- `IisRTL!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18001915d`
- `IisRTL!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18001915d`
- `IisRTL!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x180019141`
- `IisRTL!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x180019141`

## pseudocode

```c
__int64 __fastcall CMDCOM::ComMDReleaseReferenceData(CMDCOM *this, unsigned int a2)
{
  unsigned int v3; // ebx
  CIdToPointerMapper *v4; // rcx
  CMDBaseData *Mapping; // rax

  if ( g_dwInitialized )
  {
    if ( a2 )
    {
      v3 = 0;
      CReaderWriterLock3::WriteLock((CReaderWriterLock3 *)&g_LockMasterResource);
      Mapping = (CMDBaseData *)CIdToPointerMapper::FindMapping(v4, a2);
      CMDBaseData::DecrementReferenceCount(Mapping);
      CReaderWriterLock3::WriteUnlock((CReaderWriterLock3 *)&g_LockMasterResource);
    }
    else
    {
      return (unsigned int)-2147024809;
    }
  }
  else
  {
    return (unsigned int)-2146646016;
  }
  return v3;
}

```

## disassembly

```asm
0x180019110  mov     [rsp+arg_0], rbx
0x180019115  push    rdi
0x180019116  sub     rsp, 20h
0x18001911a  mov     eax, cs:?g_dwInitialized@@3KC; ulong volatile g_dwInitialized
0x180019120  mov     edi, edx
0x180019122  test    eax, eax
0x180019124  jnz     short loc_18001912D
0x180019126  mov     ebx, 800CC800h
0x18001912b  jmp     short loc_180019163
0x18001912d  test    edi, edi
0x18001912f  jnz     short loc_180019138
0x180019131  mov     ebx, 80070057h
0x180019136  jmp     short loc_180019163
0x180019138  lea     rcx, ?g_LockMasterResource@@3VCReaderWriterLock3@@A; CReaderWriterLock3 g_LockMasterResource
0x18001913f  xor     ebx, ebx
0x180019141  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x180019147  mov     edx, edi; unsigned int
0x180019149  call    ?FindMapping@CIdToPointerMapper@@QEAAPEAXK@Z; CIdToPointerMapper::FindMapping(ulong)
0x18001914e  mov     rcx, rax; this
0x180019151  call    ?DecrementReferenceCount@CMDBaseData@@QEAAKXZ; CMDBaseData::DecrementReferenceCount(void)
0x180019156  lea     rcx, ?g_LockMasterResource@@3VCReaderWriterLock3@@A; CReaderWriterLock3 g_LockMasterResource
0x18001915d  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x180019163  mov     eax, ebx
0x180019165  mov     rbx, [rsp+28h+arg_0]
0x18001916a  add     rsp, 20h
0x18001916e  pop     rdi
0x18001916f  retn
```
