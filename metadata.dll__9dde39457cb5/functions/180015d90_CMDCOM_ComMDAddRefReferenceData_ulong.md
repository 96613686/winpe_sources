# CMDCOM::ComMDAddRefReferenceData(ulong)

- ea: `0x180015d90`
- end: `0x180015dec`
- name: `?ComMDAddRefReferenceData@CMDCOM@@UEAAJK@Z`
- size: `92`
- prototype: `int(CMDCOM *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180014abc`
- `0x180015d90`

## import_xrefs

- `IisRTL!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180015dd9`
- `IisRTL!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180015dd9`
- `IisRTL!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x180015dc1`
- `IisRTL!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x180015dc1`

## pseudocode

```c
__int64 __fastcall CMDCOM::ComMDAddRefReferenceData(CMDCOM *this, unsigned int a2)
{
  unsigned int v3; // ebx
  CIdToPointerMapper *v4; // rcx

  if ( g_dwInitialized )
  {
    if ( a2 )
    {
      v3 = 0;
      CReaderWriterLock3::WriteLock((CReaderWriterLock3 *)&g_LockMasterResource);
      _InterlockedIncrement((volatile signed __int32 *)CIdToPointerMapper::FindMapping(v4, a2) + 8);
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
0x180015d90  mov     [rsp+arg_0], rbx
0x180015d95  push    rdi
0x180015d96  sub     rsp, 20h
0x180015d9a  mov     eax, cs:?g_dwInitialized@@3KC; ulong volatile g_dwInitialized
0x180015da0  mov     edi, edx
0x180015da2  test    eax, eax
0x180015da4  jnz     short loc_180015DAD
0x180015da6  mov     ebx, 800CC800h
0x180015dab  jmp     short loc_180015DDF
0x180015dad  test    edi, edi
0x180015daf  jnz     short loc_180015DB8
0x180015db1  mov     ebx, 80070057h
0x180015db6  jmp     short loc_180015DDF
0x180015db8  lea     rcx, ?g_LockMasterResource@@3VCReaderWriterLock3@@A; CReaderWriterLock3 g_LockMasterResource
0x180015dbf  xor     ebx, ebx
0x180015dc1  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x180015dc7  mov     edx, edi; unsigned int
0x180015dc9  call    ?FindMapping@CIdToPointerMapper@@QEAAPEAXK@Z; CIdToPointerMapper::FindMapping(ulong)
0x180015dce  lock inc dword ptr [rax+20h]
0x180015dd2  lea     rcx, ?g_LockMasterResource@@3VCReaderWriterLock3@@A; CReaderWriterLock3 g_LockMasterResource
0x180015dd9  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x180015ddf  mov     eax, ebx
0x180015de1  mov     rbx, [rsp+28h+arg_0]
0x180015de6  add     rsp, 20h
0x180015dea  pop     rdi
0x180015deb  retn
```
