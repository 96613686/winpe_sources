# GetMetadataBuffer64(KSSTREAM_HEADER *)

- ea: `0x140002490`
- end: `0x1400024a5`
- name: `?GetMetadataBuffer64@@YAPEAUKSSTREAM_METADATA_INFO@@PEAUKSSTREAM_HEADER@@@Z`
- size: `21`
- prototype: `struct KSSTREAM_METADATA_INFO *__fastcall(struct KSSTREAM_HEADER *)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x14000b064`

## pseudocode

```c
struct KSSTREAM_METADATA_INFO *__fastcall GetMetadataBuffer64(struct KSSTREAM_HEADER *a1)
{
  return (struct KSSTREAM_METADATA_INFO *)((unsigned __int64)&a1[2].PresentationTime.Numerator
                                         & -(__int64)((a1->OptionsFlags & 0x1000) != 0));
}

```

## disassembly

```asm
0x140002490  mov     eax, [rcx+30h]
0x140002493  sub     rcx, 0FFFFFFFFFFFFFF80h
0x140002497  and     eax, 1000h
0x14000249c  neg     eax
0x14000249e  sbb     rax, rax
0x1400024a1  and     rax, rcx
0x1400024a4  retn
```
