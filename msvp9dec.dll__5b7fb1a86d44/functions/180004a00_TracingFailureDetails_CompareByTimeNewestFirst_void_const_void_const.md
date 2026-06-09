# TracingFailureDetails::CompareByTimeNewestFirst(void const *,void const *)

- ea: `0x180004a00`
- end: `0x180004a20`
- name: `?CompareByTimeNewestFirst@TracingFailureDetails@@SAHPEBX0@Z`
- size: `32`
- prototype: `int __cdecl(const void *, const void *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180004a00`

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
0x180004a00  mov     r8, [rdx+8F8h]
0x180004a07  mov     rdx, [rcx+8F8h]
0x180004a0e  cmp     rdx, r8
0x180004a11  jbe     short loc_180004A17
0x180004a13  or      eax, 0FFFFFFFFh
0x180004a16  retn
0x180004a17  xor     eax, eax
0x180004a19  cmp     rdx, r8
0x180004a1c  setb    al
0x180004a1f  retn
```
