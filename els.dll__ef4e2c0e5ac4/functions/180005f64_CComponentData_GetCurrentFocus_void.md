# CComponentData::GetCurrentFocus(void)

- ea: `0x180005f64`
- end: `0x180005f9c`
- name: `?GetCurrentFocus@CComponentData@@QEAAPEBGXZ`
- size: `56`
- prototype: `const unsigned __int16 *__fastcall(CComponentData *__hidden this)`
- caller_count: `6`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180008b70`
- `0x180008be0`
- `0x1800098e0`
- `0x180016084`
- `0x180016ffc`
- `0x1800214b8`

## callees

- `0x180005f64`

## pseudocode

```c
wchar_t *__fastcall CComponentData::GetCurrentFocus(CComponentData *this)
{
  wchar_t *result; // rax

  result = 0;
  if ( !g_fMachineNameOverride || (*((_BYTE *)this + 56) & 0x40) == 0 || *((char *)this + 56) < 0 )
    return (wchar_t *)(((unsigned __int64)this + 88) & -(__int64)(*((_WORD *)this + 44) != 0));
  if ( g_wszMachineNameOverride )
    return &g_wszMachineNameOverride;
  return result;
}

```

## disassembly

```asm
0x180005f64  xor     eax, eax
0x180005f66  cmp     cs:?g_fMachineNameOverride@@3HA, eax; int g_fMachineNameOverride
0x180005f6c  jz      short loc_180005F8B
0x180005f6e  test    byte ptr [rcx+38h], 40h
0x180005f72  jz      short loc_180005F8B
0x180005f74  test    byte ptr [rcx+38h], 80h
0x180005f78  jnz     short loc_180005F8B
0x180005f7a  cmp     cs:?g_wszMachineNameOverride@@3PAGA, ax; ushort near * g_wszMachineNameOverride
0x180005f81  jz      short locret_180005F9B
0x180005f83  lea     rax, ?g_wszMachineNameOverride@@3PAGA; ushort near * g_wszMachineNameOverride
0x180005f8a  retn
0x180005f8b  add     rcx, 58h ; 'X'
0x180005f8f  movzx   eax, word ptr [rcx]
0x180005f92  neg     ax
0x180005f95  sbb     rax, rax
0x180005f98  and     rax, rcx
0x180005f9b  retn
```
