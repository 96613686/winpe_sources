# CompressedStreamDump::CompressedMemStream::~CompressedMemStream(void)

- ea: `0x18000450c`
- end: `0x18000455a`
- name: `??1CompressedMemStream@CompressedStreamDump@@QEAA@XZ`
- size: `78`
- prototype: `void __fastcall(CompressedStreamDump::CompressedMemStream *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18002b140`

## callees

- `0x180001ae0`
- `0x180004414`
- `0x18000449c`
- `0x18000450c`
- `0x180004560`

## pseudocode

```c
void __fastcall CompressedStreamDump::CompressedMemStream::~CompressedMemStream(
        CompressedStreamDump::CompressedMemStream *this)
{
  CompressedStreamDump::DumpWriter *v2; // rbx

  std::vector<MemoryBucket>::~vector<MemoryBucket>((char *)this + 360);
  std::vector<MemoryBucket>::~vector<MemoryBucket>((char *)this + 312);
  std::vector<MemoryRegion>::~vector<MemoryRegion>((char *)this + 80);
  v2 = (CompressedStreamDump::DumpWriter *)*((_QWORD *)this + 9);
  if ( v2 )
  {
    CompressedStreamDump::DumpWriter::~DumpWriter(v2);
    operator delete(v2);
  }
}

```

## disassembly

```asm
0x18000450c  push    rbx
0x18000450e  sub     rsp, 20h
0x180004512  mov     rbx, rcx
0x180004515  add     rcx, 168h
0x18000451c  call    ??1?$vector@UMemoryBucket@@V?$allocator@UMemoryBucket@@@std@@@std@@QEAA@XZ; std::vector<MemoryBucket>::~vector<MemoryBucket>(void)
0x180004521  lea     rcx, [rbx+138h]
0x180004528  call    ??1?$vector@UMemoryBucket@@V?$allocator@UMemoryBucket@@@std@@@std@@QEAA@XZ; std::vector<MemoryBucket>::~vector<MemoryBucket>(void)
0x18000452d  lea     rcx, [rbx+50h]
0x180004531  call    ??1?$vector@UMemoryRegion@@V?$allocator@UMemoryRegion@@@std@@@std@@QEAA@XZ; std::vector<MemoryRegion>::~vector<MemoryRegion>(void)
0x180004536  mov     rbx, [rbx+48h]
0x18000453a  test    rbx, rbx
0x18000453d  jz      short loc_180004554
0x18000453f  mov     rcx, rbx; this
0x180004542  call    ??1DumpWriter@CompressedStreamDump@@QEAA@XZ; CompressedStreamDump::DumpWriter::~DumpWriter(void)
0x180004547  mov     edx, 38h ; '8'; unsigned __int64
0x18000454c  mov     rcx, rbx; void *
0x18000454f  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180004554  add     rsp, 20h
0x180004558  pop     rbx
0x180004559  retn
```
