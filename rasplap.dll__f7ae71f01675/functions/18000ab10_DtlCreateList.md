# DtlCreateList

- ea: `0x18000ab10`
- end: `0x18000ab3c`
- name: `DtlCreateList`
- size: `44`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180009588`
- `0x180009784`
- `0x18000a0c4`
- `0x18000aca4`

## callees

- `0x18000ab10`

## import_xrefs

- `KERNEL32!GlobalAlloc` at `0x18000ab1c`
- `KERNEL32!GlobalAlloc` at `0x18000ab1c`

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
0x18000ab10  sub     rsp, 28h
0x18000ab14  mov     edx, 20h ; ' '; dwBytes
0x18000ab19  lea     ecx, [rdx+20h]; uFlags
0x18000ab1c  call    cs:__imp_GlobalAlloc
0x18000ab22  xor     ecx, ecx
0x18000ab24  test    rax, rax
0x18000ab27  jz      short loc_18000AB37
0x18000ab29  mov     [rax], rcx
0x18000ab2c  mov     [rax+8], rcx
0x18000ab30  mov     [rax+10h], ecx
0x18000ab33  mov     [rax+18h], rcx
0x18000ab37  add     rsp, 28h
0x18000ab3b  retn
```
