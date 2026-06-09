# VmbusTlEnumerateObjectTable

- ea: `0x1400015dc`
- end: `0x140001601`
- name: `VmbusTlEnumerateObjectTable`
- size: `37`
- prototype: `_QWORD *__fastcall(__int64, struct _RTL_AVL_TABLE *, BOOLEAN)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x1400187ac`
- `0x1400188c4`
- `0x140018bc8`
- `0x140018cf0`
- `0x1400220a8`

## callees

- `0x1400015dc`

## import_xrefs

- `ntoskrnl!RtlEnumerateGenericTableAvl` at `0x1400015e6`
- `ntoskrnl!RtlEnumerateGenericTableAvl` at `0x1400015e6`

## pseudocode

```c
_QWORD *__fastcall VmbusTlEnumerateObjectTable(__int64 a1, struct _RTL_AVL_TABLE *a2, BOOLEAN a3)
{
  _QWORD *result; // rax

  result = RtlEnumerateGenericTableAvl(a2, a3);
  if ( result )
    return (_QWORD *)result[2];
  return result;
}

```

## disassembly

```asm
0x1400015dc  sub     rsp, 28h
0x1400015e0  mov     rcx, rdx; Table
0x1400015e3  mov     dl, r8b; Restart
0x1400015e6  call    cs:__imp_RtlEnumerateGenericTableAvl
0x1400015ed  nop     dword ptr [rax+rax+00h]
0x1400015f2  test    rax, rax
0x1400015f5  jz      short loc_1400015FB
0x1400015f7  mov     rax, [rax+10h]
0x1400015fb  add     rsp, 28h
0x1400015ff  retn
```
