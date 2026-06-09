# DtlCreateList

- ea: `0x180026fd0`
- end: `0x180027003`
- name: `DtlCreateList`
- size: `51`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x1800262d0`
- `0x180026640`
- `0x180026cf8`

## callees

- `0x180026fd0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180026fdc`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180026fdc`

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
0x180026fd0  sub     rsp, 28h
0x180026fd4  mov     edx, 20h ; ' '; dwBytes
0x180026fd9  lea     ecx, [rdx+20h]; uFlags
0x180026fdc  call    cs:__imp_GlobalAlloc
0x180026fe3  nop     dword ptr [rax+rax+00h]
0x180026fe8  xor     ecx, ecx
0x180026fea  test    rax, rax
0x180026fed  jz      short loc_180026FFD
0x180026fef  mov     [rax], rcx
0x180026ff2  mov     [rax+8], rcx
0x180026ff6  mov     [rax+10h], ecx
0x180026ff9  mov     [rax+18h], rcx
0x180026ffd  add     rsp, 28h
0x180027001  retn
```
