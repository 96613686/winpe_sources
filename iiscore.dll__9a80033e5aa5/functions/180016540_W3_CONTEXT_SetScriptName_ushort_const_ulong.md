# W3_CONTEXT::SetScriptName(ushort const *,ulong)

- ea: `0x180016540`
- end: `0x18001657b`
- name: `?SetScriptName@W3_CONTEXT@@UEAAJPEBGK@Z`
- size: `59`
- prototype: `__int64 __fastcall(W3_CONTEXT *__hidden this, const unsigned __int16 *, unsigned int)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x180016540`

## import_xrefs

- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x18001656e`

## pseudocode

```c
int __fastcall W3_CONTEXT::SetScriptName(W3_CONTEXT *this, const unsigned __int16 *a2, unsigned int a3)
{
  if ( !a2 || a3 > *(unsigned __int16 *)(*(_QWORD *)(*((_QWORD *)this + 4) + 40LL) + 68LL) >> 1 )
    return -2147024809;
  *((_BYTE *)this + 8085) = 0;
  *((_BYTE *)this + 8083) = 0;
  return STRU::Copy((W3_CONTEXT *)((char *)this + 8712), a2, a3);
}

```

## disassembly

```asm
0x180016540  test    rdx, rdx
0x180016543  jz      short loc_180016575
0x180016545  mov     rax, [rcx+20h]
0x180016549  mov     r9, [rax+28h]
0x18001654d  movzx   eax, word ptr [r9+44h]
0x180016552  shr     eax, 1
0x180016554  cmp     r8d, eax
0x180016557  ja      short loc_180016575
0x180016559  mov     byte ptr [rcx+1F95h], 0
0x180016560  mov     byte ptr [rcx+1F93h], 0
0x180016567  add     rcx, 2208h
0x18001656e  jmp     cs:__imp_?Copy@STRU@@QEAAJPEBGK@Z; STRU::Copy(ushort const *,ulong)
0x180016575  mov     eax, 80070057h
0x18001657a  retn
```
