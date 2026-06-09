# IASLengthRequiredChildSid

- ea: `0x18002a878`
- end: `0x18002a892`
- name: `IASLengthRequiredChildSid`
- size: `26`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x1800282e4`
- `0x1800291bc`

## import_xrefs

- `ntdll!RtlLengthRequiredSid` at `0x18002a88b`
- `ntdll!RtlSubAuthorityCountSid` at `0x18002a87c`
- `ntdll!RtlSubAuthorityCountSid` at `0x18002a87c`

## pseudocode

```c
ULONG __fastcall IASLengthRequiredChildSid(void *a1)
{
  PUCHAR v1; // rax

  v1 = RtlSubAuthorityCountSid(a1);
  return RtlLengthRequiredSid(*v1 + 1);
}

```

## disassembly

```asm
0x18002a878  sub     rsp, 28h
0x18002a87c  call    cs:__imp_RtlSubAuthorityCountSid
0x18002a882  movzx   ecx, byte ptr [rax]
0x18002a885  inc     ecx
0x18002a887  add     rsp, 28h
0x18002a88b  jmp     cs:__imp_RtlLengthRequiredSid
```
