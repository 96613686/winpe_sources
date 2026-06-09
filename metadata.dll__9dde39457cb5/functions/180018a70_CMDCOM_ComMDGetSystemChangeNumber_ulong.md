# CMDCOM::ComMDGetSystemChangeNumber(ulong *)

- ea: `0x180018a70`
- end: `0x180018acb`
- name: `?ComMDGetSystemChangeNumber@CMDCOM@@UEAAJPEAK@Z`
- size: `91`
- prototype: `__int64 __fastcall(CMDCOM *__hidden this, unsigned int *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180018a70`

## import_xrefs

- `IisRTL!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180018ab8`
- `IisRTL!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180018ab8`
- `IisRTL!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x180018aa3`
- `IisRTL!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x180018aa3`

## pseudocode

```c
__int64 __fastcall CMDCOM::ComMDGetSystemChangeNumber(CMDCOM *this, unsigned int *a2)
{
  unsigned int v3; // ebx

  if ( g_dwInitialized )
  {
    if ( a2 )
    {
      v3 = 0;
      CReaderWriterLock3::ReadLock((CReaderWriterLock3 *)&g_LockMasterResource);
      *a2 = *(_DWORD *)&g_dwSystemChangeNumber;
      CReaderWriterLock3::ReadUnlock((CReaderWriterLock3 *)&g_LockMasterResource);
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
0x180018a70  mov     [rsp+arg_0], rbx
0x180018a75  push    rdi
0x180018a76  sub     rsp, 20h
0x180018a7a  mov     eax, cs:?g_dwInitialized@@3KC; ulong volatile g_dwInitialized
0x180018a80  mov     rdi, rdx
0x180018a83  test    eax, eax
0x180018a85  jnz     short loc_180018A8E
0x180018a87  mov     ebx, 800CC800h
0x180018a8c  jmp     short loc_180018ABE
0x180018a8e  test    rdi, rdi
0x180018a91  jnz     short loc_180018A9A
0x180018a93  mov     ebx, 80070057h
0x180018a98  jmp     short loc_180018ABE
0x180018a9a  lea     rcx, ?g_LockMasterResource@@3VCReaderWriterLock3@@A; CReaderWriterLock3 g_LockMasterResource
0x180018aa1  xor     ebx, ebx
0x180018aa3  call    cs:__imp_?ReadLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadLock(void)
0x180018aa9  mov     edx, cs:?g_dwSystemChangeNumber@@3KA; ulong g_dwSystemChangeNumber
0x180018aaf  lea     rcx, ?g_LockMasterResource@@3VCReaderWriterLock3@@A; CReaderWriterLock3 g_LockMasterResource
0x180018ab6  mov     [rdi], edx
0x180018ab8  call    cs:__imp_?ReadUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadUnlock(void)
0x180018abe  mov     eax, ebx
0x180018ac0  mov     rbx, [rsp+28h+arg_0]
0x180018ac5  add     rsp, 20h
0x180018ac9  pop     rdi
0x180018aca  retn
```
