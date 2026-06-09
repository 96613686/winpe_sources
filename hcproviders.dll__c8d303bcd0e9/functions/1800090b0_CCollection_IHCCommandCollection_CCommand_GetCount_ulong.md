# CCollection<IHCCommandCollection,CCommand>::GetCount(ulong *)

- ea: `0x1800090b0`
- end: `0x1800090c0`
- name: `?GetCount@?$CCollection@UIHCCommandCollection@@VCCommand@@@@UEAAJPEAK@Z`
- size: `16`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800090b0`

## pseudocode

```c
__int64 __fastcall CCollection<IHCCommandCollection,CCommand>::GetCount(__int64 a1, _DWORD *a2)
{
  _DWORD *v2; // rax

  v2 = *(_DWORD **)(a1 + 16);
  if ( v2 )
    LODWORD(v2) = *v2;
  *a2 = (_DWORD)v2;
  return 0;
}

```

## disassembly

```asm
0x1800090b0  mov     rax, [rcx+10h]
0x1800090b4  test    rax, rax
0x1800090b7  jz      short loc_1800090BB
0x1800090b9  mov     eax, [rax]
0x1800090bb  mov     [rdx], eax
0x1800090bd  xor     eax, eax
0x1800090bf  retn
```
