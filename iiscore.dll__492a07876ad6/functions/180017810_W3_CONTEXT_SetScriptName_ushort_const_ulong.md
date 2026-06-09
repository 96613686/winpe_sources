# W3_CONTEXT::SetScriptName(ushort const *,ulong)

- ea: `0x180017810`
- end: `0x180017850`
- name: `?SetScriptName@W3_CONTEXT@@UEAAJPEBGK@Z`
- size: `64`
- prototype: `__int64 __fastcall(W3_CONTEXT *__hidden this, const unsigned __int16 *, unsigned int)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x180017810`

## import_xrefs

- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x18001783e`

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
0x180017810  test    rdx, rdx
0x180017813  jz      short loc_18001784A
0x180017815  mov     rax, [rcx+20h]
0x180017819  mov     r9, [rax+28h]
0x18001781d  movzx   eax, word ptr [r9+44h]
0x180017822  shr     eax, 1
0x180017824  cmp     r8d, eax
0x180017827  ja      short loc_18001784A
0x180017829  mov     byte ptr [rcx+1F95h], 0
0x180017830  mov     byte ptr [rcx+1F93h], 0
0x180017837  add     rcx, 2208h
0x18001783e  jmp     cs:__imp_?Copy@STRU@@QEAAJPEBGK@Z; STRU::Copy(ushort const *,ulong)
0x18001784a  mov     eax, 80070057h
0x18001784f  retn
```
