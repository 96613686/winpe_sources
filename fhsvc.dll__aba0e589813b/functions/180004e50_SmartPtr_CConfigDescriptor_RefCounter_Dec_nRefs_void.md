# SmartPtr<CConfigDescriptor>::RefCounter::Dec_nRefs(void)

- ea: `0x180004e50`
- end: `0x180004e78`
- name: `?Dec_nRefs@RefCounter@?$SmartPtr@VCConfigDescriptor@@@@QEAAHXZ`
- size: `40`
- prototype: `__int64 __fastcall(__int64, unsigned int)`
- caller_count: `10`
- callee_count: `2`
- tags: `file_ops, registry_config`

## callers

- `0x1800011b0`
- `0x1800020c0`
- `0x180003190`
- `0x180003f00`
- `0x1800062b0`
- `0x1800065c0`
- `0x180006dd0`
- `0x180007330`
- `0x18000b5f8`
- `0x18000eefc`

## callees

- `0x180004e50`
- `0x18000eec4`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180004e6a`
- `msvcrt!??3@YAXPEAX@Z` at `0x180004e6a`

## pseudocode

```c
__int64 __fastcall SmartPtr<CConfigDescriptor>::RefCounter::Dec_nRefs(__int64 a1, unsigned int a2)
{
  bool v2; // zf
  __int64 result; // rax

  v2 = (*(_DWORD *)(a1 + 8))-- == 1;
  result = *(unsigned int *)(a1 + 8);
  if ( v2 )
  {
    SmartPtr<CConfigDescriptor>::RefCounter::~RefCounter((CConfigDescriptor **)a1, a2);
    operator delete((void *)a1);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180004e50  push    rbx
0x180004e52  sub     rsp, 20h
0x180004e56  sub     dword ptr [rcx+8], 1
0x180004e5a  mov     rbx, rcx
0x180004e5d  mov     eax, [rcx+8]
0x180004e60  jnz     short loc_180004E72
0x180004e62  call    ??1RefCounter@?$SmartPtr@VCConfigDescriptor@@@@QEAA@XZ; SmartPtr<CConfigDescriptor>::RefCounter::~RefCounter(void)
0x180004e67  mov     rcx, rbx
0x180004e6a  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180004e70  xor     eax, eax
0x180004e72  add     rsp, 20h
0x180004e76  pop     rbx
0x180004e77  retn
```
