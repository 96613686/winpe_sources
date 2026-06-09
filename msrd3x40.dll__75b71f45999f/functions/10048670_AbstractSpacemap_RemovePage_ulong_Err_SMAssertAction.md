# AbstractSpacemap::RemovePage(ulong,Err &,SMAssertAction)

- ea: `0x10048670`
- end: `0x100486cf`
- name: `?RemovePage@AbstractSpacemap@@QAEXKAAVErr@@W4SMAssertAction@@@Z`
- size: `95`
- prototype: ``
- caller_count: `5`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x1001c3d0`
- `0x1001cf90`
- `0x1003f180`
- `0x1003f550`
- `0x10047000`

## callees

- `0x1000f890`
- `0x100471e0`
- `0x100473e0`
- `0x10047a60`
- `0x10048670`

## pseudocode

```c
void __thiscall AbstractSpacemap::RemovePage(_DWORD *this, unsigned int a2, struct Err *a3, int a4)
{
  AbstractSpacemap::Setup(this, 1, a3);
  if ( (*(_BYTE *)a3 & 8) == 0
    && AbstractSpacemap::GetBitmap(this, a2, 2, a3) == 1
    && (*(_BYTE *)(((a2 - this[6]) >> 3) + this[4]) & *((_BYTE *)&Bitmap::ThisBit + ((a2 - this[6]) & 7))) != 0 )
  {
    Bitmap::Clear((Bitmap *)(this + 4), a2, a3);
    AbstractSpacemap::UpdateBitmap((AbstractSpacemap *)this);
  }
}

```

## disassembly

```asm
0x10048670  mov     edi, edi
0x10048672  push    ebp
0x10048673  mov     ebp, esp
0x10048675  push    ebx
0x10048676  push    esi
0x10048677  push    edi
0x10048678  mov     edi, [ebp+arg_4]
0x1004867b  mov     ebx, ecx
0x1004867d  push    edi
0x1004867e  push    1
0x10048680  call    ?Setup@AbstractSpacemap@@IAEXW4SetupType@1@AAVErr@@@Z; AbstractSpacemap::Setup(AbstractSpacemap::SetupType,Err &)
0x10048685  test    byte ptr [edi], 8
0x10048688  jnz     short loc_100486C8
0x1004868a  mov     esi, [ebp+arg_0]
0x1004868d  mov     ecx, ebx
0x1004868f  push    edi
0x10048690  push    2
0x10048692  push    esi
0x10048693  call    ?GetBitmap@AbstractSpacemap@@IAE?AW4GBResult@1@KW4GBDirection@1@AAVErr@@@Z; AbstractSpacemap::GetBitmap(ulong,AbstractSpacemap::GBDirection,Err &)
0x10048698  cmp     eax, 1
0x1004869b  jnz     short loc_100486C8
0x1004869d  sub     esi, [ebx+18h]
0x100486a0  lea     ecx, [ebx+10h]; this
0x100486a3  mov     eax, [ecx]
0x100486a5  mov     edx, esi
0x100486a7  shr     edx, 3
0x100486aa  and     esi, 7
0x100486ad  mov     al, [edx+eax]
0x100486b0  test    ds:?ThisBit@Bitmap@@1QBEB[esi], al; uchar const * const Bitmap::ThisBit
0x100486b6  jz      short loc_100486C8
0x100486b8  push    edi; struct Err *
0x100486b9  push    [ebp+arg_0]; unsigned int
0x100486bc  call    ?Clear@Bitmap@@QAEXKAAVErr@@@Z; Bitmap::Clear(ulong,Err &)
0x100486c1  mov     ecx, ebx; this
0x100486c3  call    ?UpdateBitmap@AbstractSpacemap@@IAEXXZ; AbstractSpacemap::UpdateBitmap(void)
0x100486c8  pop     edi
0x100486c9  pop     esi
0x100486ca  pop     ebx
0x100486cb  pop     ebp
0x100486cc  retn    0Ch
```
