# CompressedStreamDump::CompressedMemStream::DumpStreamHeader(void)

- ea: `0x18001e028`
- end: `0x18001e10b`
- name: `?DumpStreamHeader@CompressedMemStream@CompressedStreamDump@@AEAAXXZ`
- size: `227`
- prototype: `void __fastcall(CompressedStreamDump::CompressedMemStream *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18001ddd8`

## callees

- `0x1800289b8`

## string_xrefs

- `0x18001e0f2`: `  *** Compressed Memory Stream Header ***\n  Stream Signature: %I64u\n  DumpId: %I64u\n  ProcessId: %I64u\n  MaxTransferSize: %u KB\n  CompresedStreamOffset: %I64u\n  CompressedStreamSize: %I64u\n  Total MemoryReadBytes: %I64u\n  Total MemoryCompressedBytes: %I64u\n  CompressionRate: %I64u%%\n  NumberOfRegions: %I64u\n  RegionArrayOffset: %I64u\n  RegionArraySize: %I64u\n  NumberOfBuckets: %I64u\n  BucketArrayOffset: %I64u\n  BucketArraySize: %I64u\n  BucketStreamOffset: %I64u\n  BucketStreamSiz`

## pseudocode

```c
void __fastcall CompressedStreamDump::CompressedMemStream::DumpStreamHeader(
        CompressedStreamDump::CompressedMemStream *this)
{
  int v1; // [rsp+28h] [rbp-80h]
  int v2; // [rsp+98h] [rbp-10h]

  v2 = *((_DWORD *)this + 66);
  v1 = *((_DWORD *)this + 38) >> 10;
  CompressedStreamDump::LogMessage(
    (CompressedStreamDump *)1,
    (int)"  *** Compressed Memory Stream Header ***\n"
         "  Stream Signature: %I64u\n"
         "  DumpId: %I64u\n"
         "  ProcessId: %I64u\n"
         "  MaxTransferSize: %u KB\n"
         "  CompresedStreamOffset: %I64u\n"
         "  CompressedStreamSize: %I64u\n"
         "  Total MemoryReadBytes: %I64u\n"
         "  Total MemoryCompressedBytes: %I64u\n"
         "  CompressionRate: %I64u%%\n"
         "  NumberOfRegions: %I64u\n"
         "  RegionArrayOffset: %I64u\n"
         "  RegionArraySize: %I64u\n"
         "  NumberOfBuckets: %I64u\n"
         "  BucketArrayOffset: %I64u\n"
         "  BucketArraySize: %I64u\n"
         "  BucketStreamOffset: %I64u\n"
         "  BucketStreamSize: %I64u\n"
         "  CompressionLibType: %d\n",
    *((const char **)this + 16),
    *((_QWORD *)this + 17),
    *((_QWORD *)this + 18),
    v1,
    *((_QWORD *)this + 20),
    *((_QWORD *)this + 21),
    *((_QWORD *)this + 22),
    *((_QWORD *)this + 23),
    *((_QWORD *)this + 24),
    *((_QWORD *)this + 25),
    *((_QWORD *)this + 26),
    *((_QWORD *)this + 27),
    *((_QWORD *)this + 28),
    *((_QWORD *)this + 29),
    *((_QWORD *)this + 30),
    *((_QWORD *)this + 31),
    *((_QWORD *)this + 32),
    v2);
}

```

## disassembly

```asm
0x18001e028  mov     r11, rsp
0x18001e02b  sub     rsp, 0A8h
0x18001e032  mov     eax, [rcx+108h]
0x18001e038  mov     edx, [rcx+98h]
0x18001e03e  mov     r9, [rcx+88h]
0x18001e045  mov     r8, [rcx+80h]; char *
0x18001e04c  mov     [r11-10h], eax
0x18001e050  mov     rax, [rcx+100h]
0x18001e057  mov     [r11-18h], rax
0x18001e05b  mov     rax, [rcx+0F8h]
0x18001e062  mov     [r11-20h], rax
0x18001e066  mov     rax, [rcx+0F0h]
0x18001e06d  mov     [r11-28h], rax
0x18001e071  mov     rax, [rcx+0E8h]
0x18001e078  mov     [r11-30h], rax
0x18001e07c  mov     rax, [rcx+0E0h]
0x18001e083  mov     [r11-38h], rax
0x18001e087  mov     rax, [rcx+0D8h]
0x18001e08e  mov     [r11-40h], rax
0x18001e092  mov     rax, [rcx+0D0h]
0x18001e099  mov     [r11-48h], rax
0x18001e09d  mov     rax, [rcx+0C8h]
0x18001e0a4  mov     [r11-50h], rax
0x18001e0a8  mov     rax, [rcx+0C0h]
0x18001e0af  mov     [r11-58h], rax
0x18001e0b3  mov     rax, [rcx+0B8h]
0x18001e0ba  mov     [r11-60h], rax
0x18001e0be  mov     rax, [rcx+0B0h]
0x18001e0c5  mov     [r11-68h], rax
0x18001e0c9  mov     rax, [rcx+0A8h]
0x18001e0d0  mov     [r11-70h], rax
0x18001e0d4  mov     rax, [rcx+0A0h]
0x18001e0db  mov     [r11-78h], rax
0x18001e0df  mov     rax, [rcx+90h]
0x18001e0e6  mov     ecx, 1; this
0x18001e0eb  shr     edx, 0Ah
0x18001e0ee  mov     [rsp+0A8h+var_80], edx
0x18001e0f2  lea     rdx, aCompressedMemo; "  *** Compressed Memory Stream Header *"...
0x18001e0f9  mov     [rsp+0A8h+var_88], rax
0x18001e0fe  call    ?LogMessage@CompressedStreamDump@@YAXHPEBDZZ; CompressedStreamDump::LogMessage(int,char const *,...)
0x18001e103  add     rsp, 0A8h
0x18001e10a  retn
```
