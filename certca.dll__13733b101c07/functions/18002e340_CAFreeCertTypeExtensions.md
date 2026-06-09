# CAFreeCertTypeExtensions

- ea: `0x18002e340`
- end: `0x18002e359`
- name: `CAFreeCertTypeExtensions`
- size: `25`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `5`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18002e320`
- `0x1800354fc`
- `0x180035cfc`
- `0x1800362f8`
- `0x1800365a4`

## callees

- `0x18002e340`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002e34c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002e34c`

## pseudocode

```c
__int64 __fastcall CAFreeCertTypeExtensions(__int64 a1, void *a2)
{
  if ( a2 )
    LocalFree(a2);
  return 0;
}

```

## disassembly

```asm
0x18002e340  sub     rsp, 28h
0x18002e344  test    rdx, rdx
0x18002e347  jz      short loc_18002E352
0x18002e349  mov     rcx, rdx; hMem
0x18002e34c  call    cs:__imp_LocalFree
0x18002e352  xor     eax, eax
0x18002e354  add     rsp, 28h
0x18002e358  retn
```
