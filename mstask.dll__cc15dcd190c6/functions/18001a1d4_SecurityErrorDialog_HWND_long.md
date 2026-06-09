# SecurityErrorDialog(HWND__ *,long)

- ea: `0x18001a1d4`
- end: `0x18001a232`
- name: `?SecurityErrorDialog@@YAXPEAUHWND__@@J@Z`
- size: `94`
- prototype: `void(HWND, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180019f64`

## callees

- `0x180017df4`
- `0x18001a1d4`

## pseudocode

```c
void __fastcall SecurityErrorDialog(HWND a1, int a2)
{
  UINT v2; // r9d

  switch ( a2 )
  {
    case -2147216624:
      v2 = 3402;
      break;
    case -2147216623:
      v2 = 3403;
      break;
    case -2147024891:
      v2 = 3404;
      break;
    default:
      if ( a2 == -2147216619 || (a2 & 0x1FFF0000) == 0x10000 )
        v2 = 3405;
      else
        v2 = 0;
      break;
  }
  SchedUIErrorDialog(a1, 0xD48u, a2, v2);
}

```

## disassembly

```asm
0x18001a1d4  cmp     edx, 80041310h
0x18001a1da  jnz     short loc_18001A1E4
0x18001a1dc  mov     r9d, 0D4Ah
0x18001a1e2  jmp     short loc_18001A225
0x18001a1e4  cmp     edx, 80041311h
0x18001a1ea  jnz     short loc_18001A1F4
0x18001a1ec  mov     r9d, 0D4Bh
0x18001a1f2  jmp     short loc_18001A225
0x18001a1f4  cmp     edx, 80070005h
0x18001a1fa  jnz     short loc_18001A204
0x18001a1fc  mov     r9d, 0D4Ch
0x18001a202  jmp     short loc_18001A225
0x18001a204  cmp     edx, 80041315h
0x18001a20a  jz      short loc_18001A21F
0x18001a20c  mov     eax, edx
0x18001a20e  and     eax, 1FFF0000h
0x18001a213  cmp     eax, 10000h
0x18001a218  jz      short loc_18001A21F
0x18001a21a  xor     r9d, r9d
0x18001a21d  jmp     short loc_18001A225
0x18001a21f  mov     r9d, 0D4Dh; UINT
0x18001a225  mov     r8d, edx; int
0x18001a228  mov     edx, 0D48h; uID
0x18001a22d  jmp     ?SchedUIErrorDialog@@YAXPEAUHWND__@@HJI@Z; SchedUIErrorDialog(HWND__ *,int,long,uint)
```
