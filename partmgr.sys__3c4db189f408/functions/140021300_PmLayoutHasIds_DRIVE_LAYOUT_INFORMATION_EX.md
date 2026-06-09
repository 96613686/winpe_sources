# PmLayoutHasIds(_DRIVE_LAYOUT_INFORMATION_EX *)

- ea: `0x140021300`
- end: `0x140021335`
- name: `?PmLayoutHasIds@@YAEPEAU_DRIVE_LAYOUT_INFORMATION_EX@@@Z`
- size: `53`
- prototype: `unsigned __int8 __fastcall(struct _DRIVE_LAYOUT_INFORMATION_EX *)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x140005b2c`

## callees

- `0x140021300`

## pseudocode

```c
unsigned __int8 __fastcall PmLayoutHasIds(struct _DRIVE_LAYOUT_INFORMATION_EX *a1)
{
  char v1; // dl

  v1 = 0;
  if ( a1->PartitionStyle )
  {
    if ( a1->PartitionStyle == 1 )
      return 1;
  }
  else
  {
    if ( !a1->PartitionCount )
    {
      if ( !a1->Mbr.Signature )
        return v1;
      return 1;
    }
    if ( a1->PartitionEntry[0].StartingOffset.QuadPart || a1->PartitionEntry[0].PartitionLength.QuadPart <= 0 )
      return 1;
  }
  return v1;
}

```

## disassembly

```asm
0x140021300  mov     r8d, [rcx]
0x140021303  xor     r9d, r9d
0x140021306  mov     dl, r9b
0x140021309  test    r8d, r8d
0x14002130c  jz      short loc_140021316
0x14002130e  cmp     r8d, 1
0x140021312  jnz     short loc_140021332
0x140021314  jmp     short loc_140021330
0x140021316  cmp     [rcx+4], r9d
0x14002131a  jnz     short loc_140021324
0x14002131c  cmp     [rcx+8], r9d
0x140021320  jnz     short loc_140021330
0x140021322  jmp     short loc_140021332
0x140021324  cmp     [rcx+38h], r9
0x140021328  jnz     short loc_140021330
0x14002132a  cmp     [rcx+40h], r9
0x14002132e  jg      short loc_140021332
0x140021330  mov     dl, 1
0x140021332  mov     al, dl
0x140021334  retn
```
