# GetMetadataBuffer32(_KSSTREAM_HEADER32 *)

- ea: `0x140002474`
- end: `0x140002489`
- name: `?GetMetadataBuffer32@@YAPEAUKSSTREAM_METADATA_INFO32@@PEAU_KSSTREAM_HEADER32@@@Z`
- size: `21`
- prototype: `struct KSSTREAM_METADATA_INFO32 *__fastcall(struct _KSSTREAM_HEADER32 *)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x14000b064`

## pseudocode

```c
struct KSSTREAM_METADATA_INFO32 *__fastcall GetMetadataBuffer32(struct _KSSTREAM_HEADER32 *a1)
{
  return (struct KSSTREAM_METADATA_INFO32 *)(((unsigned __int64)a1 + 112)
                                           & -(__int64)((*((_DWORD *)a1 + 11) & 0x1000) != 0));
}

```

## disassembly

```asm
0x140002474  mov     eax, [rcx+2Ch]
0x140002477  add     rcx, 70h ; 'p'
0x14000247b  and     eax, 1000h
0x140002480  neg     eax
0x140002482  sbb     rax, rax
0x140002485  and     rax, rcx
0x140002488  retn
```
