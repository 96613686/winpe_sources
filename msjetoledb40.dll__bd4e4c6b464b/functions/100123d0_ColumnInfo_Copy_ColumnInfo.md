# ColumnInfo::Copy(ColumnInfo &)

- ea: `0x100123d0`
- end: `0x10012467`
- name: `?Copy@ColumnInfo@@QAEJAAV1@@Z`
- size: `151`
- prototype: `int __thiscall(ColumnInfo *__hidden this, struct ColumnInfo *)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x10012e10`
- `0x1002e3e0`

## callees

- `0x10012360`
- `0x100123d0`
- `0x10012470`
- `0x10025940`

## pseudocode

```c
int __thiscall ColumnInfo::Copy(ColumnInfo *this, struct ColumnInfo *a2)
{
  int result; // eax
  ColumnInfo *v4; // ecx
  ColumnInfo *v5; // ecx

  ColumnInfo::Cleanup(this);
  result = CopyDBIDs((int)this + 8, (int)a2 + 8);
  if ( result >= 0 )
  {
    *((_DWORD *)this + 8) = *((_DWORD *)a2 + 8);
    result = CopyDBIDs((int)this + 76, (int)a2 + 76);
    if ( result >= 0 )
    {
      *(_OWORD *)((char *)this + 8) = *(_OWORD *)((char *)a2 + 8);
      *((_QWORD *)this + 3) = *((_QWORD *)a2 + 3);
      *((_DWORD *)this + 8) = *((_DWORD *)a2 + 8);
      *((_DWORD *)this + 9) = *((_DWORD *)a2 + 9);
      *((_WORD *)this + 20) = *((_WORD *)a2 + 20);
      *((_DWORD *)this + 11) = *((_DWORD *)a2 + 11);
      *((_DWORD *)this + 13) = *((_DWORD *)a2 + 13);
      *((_DWORD *)this + 14) = *((_DWORD *)a2 + 14);
      *((_DWORD *)this + 15) = *((_DWORD *)a2 + 15);
      result = ColumnInfo::ReplaceOldString(v4, (unsigned __int16 **)this + 25, *((const unsigned __int16 **)a2 + 25));
      if ( result >= 0 )
        return ColumnInfo::ReplaceOldString(v5, (unsigned __int16 **)this + 1, *((const unsigned __int16 **)a2 + 1));
    }
  }
  return result;
}

```

## disassembly

```asm
0x100123d0  mov     edi, edi
0x100123d2  push    ebp
0x100123d3  mov     ebp, esp
0x100123d5  push    ebx
0x100123d6  push    esi; struct tagDBID *
0x100123d7  push    edi; struct tagDBID *
0x100123d8  mov     esi, ecx
0x100123da  call    ?Cleanup@ColumnInfo@@AAEXXZ; ColumnInfo::Cleanup(void)
0x100123df  mov     edi, [ebp+arg_0]
0x100123e2  lea     ecx, [esi+8]
0x100123e5  lea     edx, [edi+8]
0x100123e8  call    ?CopyDBIDs@@YGJPAUtagDBID@@PBU1@@Z; CopyDBIDs(tagDBID *,tagDBID const *)
0x100123ed  test    eax, eax
0x100123ef  js      short loc_10012460
0x100123f1  mov     eax, [edi+20h]
0x100123f4  lea     edx, [edi+4Ch]
0x100123f7  lea     ecx, [esi+4Ch]
0x100123fa  mov     [esi+20h], eax
0x100123fd  call    ?CopyDBIDs@@YGJPAUtagDBID@@PBU1@@Z; CopyDBIDs(tagDBID *,tagDBID const *)
0x10012402  test    eax, eax
0x10012404  js      short loc_10012460
0x10012406  movups  xmm0, xmmword ptr [edi+8]
0x1001240a  movups  xmmword ptr [esi+8], xmm0
0x1001240e  movq    xmm0, qword ptr [edi+18h]
0x10012413  movq    qword ptr [esi+18h], xmm0
0x10012418  mov     eax, [edi+20h]
0x1001241b  mov     [esi+20h], eax
0x1001241e  mov     eax, [edi+24h]
0x10012421  mov     [esi+24h], eax
0x10012424  mov     ax, [edi+28h]
0x10012428  mov     [esi+28h], ax
0x1001242c  mov     eax, [edi+2Ch]
0x1001242f  mov     [esi+2Ch], eax
0x10012432  mov     eax, [edi+34h]
0x10012435  mov     [esi+34h], eax
0x10012438  mov     eax, [edi+38h]
0x1001243b  mov     [esi+38h], eax
0x1001243e  mov     eax, [edi+3Ch]
0x10012441  mov     [esi+3Ch], eax
0x10012444  lea     eax, [esi+64h]
0x10012447  push    dword ptr [edi+64h]; unsigned __int16 *
0x1001244a  push    eax; unsigned __int16 **
0x1001244b  call    ?ReplaceOldString@ColumnInfo@@AAEJPAPAGPBG@Z; ColumnInfo::ReplaceOldString(ushort * *,ushort const *)
0x10012450  test    eax, eax
0x10012452  js      short loc_10012460
0x10012454  push    dword ptr [edi+4]; unsigned __int16 *
0x10012457  lea     eax, [esi+4]
0x1001245a  push    eax; unsigned __int16 **
0x1001245b  call    ?ReplaceOldString@ColumnInfo@@AAEJPAPAGPBG@Z; ColumnInfo::ReplaceOldString(ushort * *,ushort const *)
0x10012460  pop     edi
0x10012461  pop     esi
0x10012462  pop     ebx
0x10012463  pop     ebp
0x10012464  retn    4
```
