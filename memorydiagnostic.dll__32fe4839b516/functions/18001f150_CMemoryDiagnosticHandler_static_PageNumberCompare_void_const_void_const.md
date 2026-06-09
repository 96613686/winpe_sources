# CMemoryDiagnosticHandler::static_PageNumberCompare(void const *,void const *)

- ea: `0x18001f150`
- end: `0x18001f166`
- name: `?static_PageNumberCompare@CMemoryDiagnosticHandler@@CAHPEBX0@Z`
- size: `22`
- prototype: `int __cdecl(const void *, const void *)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18001f150`

## pseudocode

```c
__int64 __fastcall CMemoryDiagnosticHandler::static_PageNumberCompare(_QWORD *a1, _QWORD *a2)
{
  if ( *a1 >= *a2 )
    return *a1 != *a2;
  else
    return 0xFFFFFFFFLL;
}

```

## disassembly

```asm
0x18001f150  mov     r8, [rdx]
0x18001f153  cmp     [rcx], r8
0x18001f156  jnb     short loc_18001F15D
0x18001f158  or      eax, 0FFFFFFFFh
0x18001f15b  retn
0x18001f15d  xor     eax, eax
0x18001f15f  cmp     [rcx], r8
0x18001f162  setnz   al
0x18001f165  retn
```
