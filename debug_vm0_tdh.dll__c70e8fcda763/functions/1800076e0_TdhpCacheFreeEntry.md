# TdhpCacheFreeEntry

- ea: `0x1800076e0`
- end: `0x180007715`
- name: `TdhpCacheFreeEntry`
- size: `53`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `10`
- callee_count: `1`
- tags: ``

## callers

- `0x1800074e8`
- `0x18001e820`
- `0x1800259a4`
- `0x1800268b0`
- `0x180026ae4`
- `0x180026dc8`
- `0x180026f34`
- `0x1800270cc`
- `0x180029a28`
- `0x180029e6c`

## callees

- `0x1800076e0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000770e`

## pseudocode

```c
void __fastcall TdhpCacheFreeEntry(struct TDH_CACHE *a1, __int64 a2)
{
  unsigned __int8 v2; // al
  struct TDH_CACHE *v3; // r9
  __int64 i; // r8
  char v5; // al

  v2 = 0;
  v3 = a1;
  for ( i = 0; i != 16; ++i )
  {
    v5 = *(_BYTE *)(a2 + i + 8) ^ v2;
    v2 = __ROL1__(v5, 3);
  }
  if ( !a1 )
    v3 = g_TdhCache;
  ReleaseSRWLockShared((PSRWLOCK)v3 + 8 * (unsigned __int64)v2);
}

```

## disassembly

```asm
0x1800076e0  xor     al, al
0x1800076e2  mov     r9, rcx
0x1800076e5  xor     r8d, r8d
0x1800076e8  xor     al, [rdx+r8+8]
0x1800076ed  inc     r8
0x1800076f0  rol     al, 3
0x1800076f3  cmp     r8, 10h
0x1800076f7  jnz     short loc_1800076E8
0x1800076f9  test    r9, r9
0x1800076fc  movzx   ecx, al
0x1800076ff  cmovz   r9, cs:?g_TdhCache@@3PEAUTDH_CACHE@@EA; TDH_CACHE * g_TdhCache
0x180007707  shl     rcx, 6
0x18000770b  add     rcx, r9
0x18000770e  jmp     cs:__imp_ReleaseSRWLockShared
```
