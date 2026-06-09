# VctComputeTransportAddressSize

- ea: `0x140041324`
- end: `0x14004135a`
- name: `VctComputeTransportAddressSize`
- size: `54`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140015020`
- `0x140040ea0`

## callees

- `0x140041324`

## import_xrefs

- `ntoskrnl!RtlxUnicodeStringToOemSize` at `0x14004132d`
- `ntoskrnl!RtlxUnicodeStringToOemSize` at `0x14004132d`

## pseudocode

```c
__int64 __fastcall VctComputeTransportAddressSize(const UNICODE_STRING *a1)
{
  ULONG v2; // eax
  int v3; // edx

  v2 = RtlxUnicodeStringToOemSize(a1);
  v3 = 18;
  if ( v2 > 0x10 )
    v3 = v2 + 2;
  return 3 * v3 + (unsigned int)a1->Length + 632;
}

```

## disassembly

```asm
0x140041324  push    rbx
0x140041326  sub     rsp, 20h
0x14004132a  mov     rbx, rcx
0x14004132d  call    cs:__imp_RtlxUnicodeStringToOemSize
0x140041334  nop     dword ptr [rax+rax+00h]
0x140041339  mov     edx, 12h
0x14004133e  cmp     eax, 10h
0x140041341  jbe     short loc_140041346
0x140041343  lea     edx, [rax+2]
0x140041346  movzx   eax, word ptr [rbx]
0x140041349  lea     edx, [rdx+rdx*2]
0x14004134c  add     eax, 278h
0x140041351  add     eax, edx
0x140041353  add     rsp, 20h
0x140041357  pop     rbx
0x140041358  retn
```
