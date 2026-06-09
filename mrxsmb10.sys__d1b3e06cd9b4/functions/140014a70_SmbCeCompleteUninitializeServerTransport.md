# SmbCeCompleteUninitializeServerTransport

- ea: `0x140014a70`
- end: `0x140014ab3`
- name: `SmbCeCompleteUninitializeServerTransport`
- size: `67`
- prototype: `__int64 __fastcall(PVOID pContext)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x140002470`
- `0x140003e20`
- `0x140004030`

## string_xrefs

- `0x140014a7c`: `SmbCeCompleteUninitializeServerTransport`
- `0x140014a98`: `SmbCeCompleteUninitializeServerTransport`

## pseudocode

```c
void __fastcall SmbCeCompleteUninitializeServerTransport(char *pContext)
{
  MRxSmbTrackDerefCount(pContext, "SmbCeCompleteUninitializeServerTransport", 553);
  SmbReferenceRecord(pContext + 792, "SmbCeCompleteUninitializeServerTransport", 553);
  SmbCepDereferenceServerEntry(pContext);
}

```

## disassembly

```asm
0x140014a70  push    rbx
0x140014a72  sub     rsp, 20h
0x140014a76  mov     r8d, 229h
0x140014a7c  lea     rdx, aSmbcecompleteu; "SmbCeCompleteUninitializeServerTranspor"...
0x140014a83  mov     rbx, rcx
0x140014a86  call    MRxSmbTrackDerefCount
0x140014a8b  lea     rcx, [rbx+318h]
0x140014a92  mov     r8d, 229h
0x140014a98  lea     rdx, aSmbcecompleteu; "SmbCeCompleteUninitializeServerTranspor"...
0x140014a9f  call    SmbReferenceRecord
0x140014aa4  mov     rcx, rbx; pContext
0x140014aa7  call    SmbCepDereferenceServerEntry
0x140014aac  add     rsp, 20h
0x140014ab0  pop     rbx
0x140014ab1  retn
```
