# DtlCreateList

- ea: `0x180026024`
- end: `0x180026050`
- name: `DtlCreateList`
- size: `44`
- prototype: `_QWORD *()`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x18002541c`
- `0x180025740`
- `0x180025d98`

## callees

- `0x180026024`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180026030`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180026030`

## pseudocode

```c
_QWORD *DtlCreateList()
{
  _QWORD *result; // rax

  result = GlobalAlloc(0x40u, 0x20u);
  if ( result )
  {
    *result = 0;
    result[1] = 0;
    *((_DWORD *)result + 4) = 0;
    result[3] = 0;
  }
  return result;
}

```

## disassembly

```asm
0x180026024  sub     rsp, 28h
0x180026028  mov     edx, 20h ; ' '; dwBytes
0x18002602d  lea     ecx, [rdx+20h]; uFlags
0x180026030  call    cs:__imp_GlobalAlloc
0x180026036  xor     ecx, ecx
0x180026038  test    rax, rax
0x18002603b  jz      short loc_18002604B
0x18002603d  mov     [rax], rcx
0x180026040  mov     [rax+8], rcx
0x180026044  mov     [rax+10h], ecx
0x180026047  mov     [rax+18h], rcx
0x18002604b  add     rsp, 28h
0x18002604f  retn
```
