# DestroyCombinedHashTable

- ea: `0x18003ff84`
- end: `0x18003ffb1`
- name: `DestroyCombinedHashTable`
- size: `45`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18003c204`
- `0x180040108`

## callees

- `0x18003ff84`

## import_xrefs

- `ntdll!RtlDeleteHashTable` at `0x18003ff96`
- `ntdll!RtlDeleteHashTable` at `0x18003ff96`

## pseudocode

```c
__int64 __fastcall DestroyCombinedHashTable(__int64 a1)
{
  __int64 result; // rax

  if ( (*(_DWORD *)a1)-- == 1 )
  {
    result = RtlDeleteHashTable(*(_QWORD *)(a1 + 8));
    *(_QWORD *)(a1 + 8) = 0;
  }
  return result;
}

```

## disassembly

```asm
0x18003ff84  push    rbx
0x18003ff86  sub     rsp, 20h
0x18003ff8a  add     dword ptr [rcx], 0FFFFFFFFh
0x18003ff8d  mov     rbx, rcx
0x18003ff90  jnz     short loc_18003FFAA
0x18003ff92  mov     rcx, [rcx+8]
0x18003ff96  call    cs:__imp_RtlDeleteHashTable
0x18003ff9d  nop     dword ptr [rax+rax+00h]
0x18003ffa2  mov     qword ptr [rbx+8], 0
0x18003ffaa  add     rsp, 20h
0x18003ffae  pop     rbx
0x18003ffaf  retn
```
