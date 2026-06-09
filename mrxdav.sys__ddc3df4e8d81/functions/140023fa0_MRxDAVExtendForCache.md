# MRxDAVExtendForCache

- ea: `0x140023fa0`
- end: `0x140023fb7`
- name: `MRxDAVExtendForCache`
- size: `23`
- prototype: `__int64 __fastcall(__int64, _QWORD *, _QWORD *)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x140025d00`

## pseudocode

```c
__int64 __fastcall MRxDAVExtendForCache(__int64 a1, _QWORD *a2, _QWORD *a3)
{
  *a3 = *a2;
  MRxDAVUpdateFileInfoCacheFileSize(a1, a2);
  return 0;
}

```

## disassembly

```asm
0x140023fa0  sub     rsp, 28h
0x140023fa4  mov     rax, [rdx]
0x140023fa7  mov     [r8], rax
0x140023faa  call    MRxDAVUpdateFileInfoCacheFileSize
0x140023faf  xor     eax, eax
0x140023fb1  add     rsp, 28h
0x140023fb5  retn
```
