# TracingFailureDetails::CompareByTimeNewestFirst(void const *,void const *)

- ea: `0x1800085f0`
- end: `0x180008610`
- name: `?CompareByTimeNewestFirst@TracingFailureDetails@@SAHPEBX0@Z`
- size: `32`
- prototype: `int __cdecl(const void *, const void *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800085f0`

## pseudocode

```c
__int64 __fastcall TracingFailureDetails::CompareByTimeNewestFirst(_QWORD *a1, _QWORD *a2)
{
  unsigned __int64 v2; // r8
  unsigned __int64 v3; // rdx

  v2 = a2[287];
  v3 = a1[287];
  if ( v3 <= v2 )
    return v3 < v2;
  else
    return 0xFFFFFFFFLL;
}

```

## disassembly

```asm
0x1800085f0  mov     r8, [rdx+8F8h]
0x1800085f7  mov     rdx, [rcx+8F8h]
0x1800085fe  cmp     rdx, r8
0x180008601  jbe     short loc_180008607
0x180008603  or      eax, 0FFFFFFFFh
0x180008606  retn
0x180008607  xor     eax, eax
0x180008609  cmp     rdx, r8
0x18000860c  setb    al
0x18000860f  retn
```
