# AbstractSpacemap::UpdateBitmap(void)

- ea: `0x100473e0`
- end: `0x10047419`
- name: `?UpdateBitmap@AbstractSpacemap@@IAEXXZ`
- size: `57`
- prototype: `void __thiscall(AbstractSpacemap *__hidden this)`
- caller_count: `8`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x10012190`
- `0x1001c8c0`
- `0x1001cf90`
- `0x10031660`
- `0x1003b2d0`
- `0x1003f550`
- `0x100481d0`
- `0x10048670`

## callees

- `0x100473e0`

## pseudocode

```c
void __thiscall AbstractSpacemap::UpdateBitmap(AbstractSpacemap *this)
{
  int v2; // ecx
  int v3; // ecx

  if ( **((_BYTE **)this + 17) )
  {
    if ( **((_BYTE **)this + 17) == 1 )
    {
      v2 = *((_DWORD *)this + 11);
      *(_DWORD *)(v2 + 4 * *(_DWORD *)(v2 + 24) + 28) |= 8u;
      ++*(_DWORD *)(v2 + 64);
    }
  }
  else
  {
    v3 = *((_DWORD *)this + 7);
    *(_DWORD *)(v3 + 4 * *(_DWORD *)(v3 + 24) + 28) |= 8u;
    ++*(_DWORD *)(v3 + 64);
    *((_DWORD *)this + 9) = *(_DWORD *)(*((_DWORD *)this + 7) + 64);
  }
}

```

## disassembly

```asm
0x100473e0  mov     edx, ecx
0x100473e2  mov     eax, [edx+44h]
0x100473e5  movzx   eax, byte ptr [eax]
0x100473e8  sub     eax, 0
0x100473eb  jz      short loc_10047401
0x100473ed  sub     eax, 1
0x100473f0  jnz     short locret_10047418
0x100473f2  mov     ecx, [edx+2Ch]
0x100473f5  mov     eax, [ecx+18h]
0x100473f8  or      dword ptr [ecx+eax*4+1Ch], 8
0x100473fd  inc     dword ptr [ecx+40h]
0x10047400  retn
0x10047401  mov     ecx, [edx+1Ch]
0x10047404  mov     eax, [ecx+18h]
0x10047407  or      dword ptr [ecx+eax*4+1Ch], 8
0x1004740c  inc     dword ptr [ecx+40h]
0x1004740f  mov     eax, [edx+1Ch]
0x10047412  mov     eax, [eax+40h]
0x10047415  mov     [edx+24h], eax
0x10047418  retn
```
