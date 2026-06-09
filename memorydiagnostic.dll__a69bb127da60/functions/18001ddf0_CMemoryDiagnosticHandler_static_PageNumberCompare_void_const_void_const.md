# CMemoryDiagnosticHandler::static_PageNumberCompare(void const *,void const *)

- ea: `0x18001ddf0`
- end: `0x18001de05`
- name: `?static_PageNumberCompare@CMemoryDiagnosticHandler@@CAHPEBX0@Z`
- size: `21`
- prototype: `__int64 __fastcall(_QWORD *, _QWORD *)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18001ddf0`

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
0x18001ddf0  mov     r8, [rdx]
0x18001ddf3  cmp     [rcx], r8
0x18001ddf6  jnb     short loc_18001DDFC
0x18001ddf8  or      eax, 0FFFFFFFFh
0x18001ddfb  retn
0x18001ddfc  xor     eax, eax
0x18001ddfe  cmp     [rcx], r8
0x18001de01  setnz   al
0x18001de04  retn
```
