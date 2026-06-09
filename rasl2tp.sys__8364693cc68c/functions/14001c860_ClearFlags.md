# ClearFlags

- ea: `0x14001c860`
- end: `0x14001c882`
- name: `ClearFlags`
- size: `34`
- prototype: ``
- caller_count: `17`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140001e60`
- `0x1400022e0`
- `0x14000f008`
- `0x14000f2ec`
- `0x1400106b4`
- `0x1400109d0`
- `0x140010f90`
- `0x140011518`
- `0x140012078`
- `0x140012138`
- `0x1400126c8`
- `0x140012dc4`
- `0x140015bbc`
- `0x140018620`
- `0x1400188d0`
- `0x140019280`
- `0x140019358`

## callees

- `0x14001c860`

## pseudocode

```c
__int64 __fastcall ClearFlags(int *a1, int a2)
{
  unsigned int v2; // r10d
  int v3; // ett

  _m_prefetchw(a1);
  do
  {
    v2 = a2 & *a1;
    v3 = *a1;
  }
  while ( v3 != _InterlockedCompareExchange(a1, *a1 & ~a2, *a1) );
  return v2;
}

```

## disassembly

```asm
0x14001c860  mov     r8d, edx
0x14001c863  not     r8d
0x14001c866  prefetchw byte ptr [rcx]
0x14001c869  mov     eax, [rcx]
0x14001c86b  mov     r9d, r8d
0x14001c86e  mov     r10d, eax
0x14001c871  and     r10d, edx
0x14001c874  and     r9d, eax
0x14001c877  lock cmpxchg [rcx], r9d
0x14001c87c  jnz     short loc_14001C869
0x14001c87e  mov     eax, r10d
0x14001c881  retn
```
