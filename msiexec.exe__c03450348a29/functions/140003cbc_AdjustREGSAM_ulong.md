# AdjustREGSAM(ulong &)

- ea: `0x140003cbc`
- end: `0x140003cde`
- name: `?AdjustREGSAM@@YAXAEAK@Z`
- size: `34`
- prototype: `void __fastcall(unsigned int *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x14000669c`
- `0x140007110`

## callees

- `0x140003cbc`

## pseudocode

```c
void __fastcall AdjustREGSAM(unsigned int *a1)
{
  if ( !g_fWoW && g_fWinNT64 && (*a1 & 0x100) == 0 )
    *a1 |= 0x100u;
}

```

## disassembly

```asm
0x140003cbc  cmp     cs:?g_fWoW@@3_NA, 0; bool g_fWoW
0x140003cc3  jnz     short locret_140003CDD
0x140003cc5  cmp     cs:?g_fWinNT64@@3_NA, 0; bool g_fWinNT64
0x140003ccc  jz      short locret_140003CDD
0x140003cce  mov     eax, [rcx]
0x140003cd0  mov     edx, 100h
0x140003cd5  test    edx, eax
0x140003cd7  jnz     short locret_140003CDD
0x140003cd9  or      eax, edx
0x140003cdb  mov     [rcx], eax
0x140003cdd  retn
```
