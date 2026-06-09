# ReleaseOutlineBitmaps(void)

- ea: `0x180047424`
- end: `0x1800474a1`
- name: `?ReleaseOutlineBitmaps@@YAXXZ`
- size: `125`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180022d48`

## callees

- `0x180047424`

## import_xrefs

- `GDI32!DeleteObject` at `0x180047434`
- `GDI32!DeleteObject` at `0x180047451`
- `GDI32!DeleteObject` at `0x18004746e`
- `GDI32!DeleteObject` at `0x18004748b`
- `GDI32!DeleteObject` at `0x180047434`
- `GDI32!DeleteObject` at `0x180047451`
- `GDI32!DeleteObject` at `0x18004746e`
- `GDI32!DeleteObject` at `0x18004748b`

## pseudocode

```c
void ReleaseOutlineBitmaps(void)
{
  if ( h )
  {
    DeleteObject(h);
    h = 0;
  }
  if ( qword_1800A4240 )
  {
    DeleteObject(qword_1800A4240);
    qword_1800A4240 = 0;
  }
  if ( qword_1800A4238 )
  {
    DeleteObject(qword_1800A4238);
    qword_1800A4238 = 0;
  }
  if ( qword_1800A4230 )
  {
    DeleteObject(qword_1800A4230);
    qword_1800A4230 = 0;
  }
}

```

## disassembly

```asm
0x180047424  sub     rsp, 28h
0x180047428  mov     rcx, cs:h; ho
0x18004742f  test    rcx, rcx
0x180047432  jz      short loc_180047445
0x180047434  call    cs:__imp_DeleteObject
0x18004743a  mov     cs:h, 0
0x180047445  mov     rcx, cs:qword_1800A4240; ho
0x18004744c  test    rcx, rcx
0x18004744f  jz      short loc_180047462
0x180047451  call    cs:__imp_DeleteObject
0x180047457  mov     cs:qword_1800A4240, 0
0x180047462  mov     rcx, cs:qword_1800A4238; ho
0x180047469  test    rcx, rcx
0x18004746c  jz      short loc_18004747F
0x18004746e  call    cs:__imp_DeleteObject
0x180047474  mov     cs:qword_1800A4238, 0
0x18004747f  mov     rcx, cs:qword_1800A4230; ho
0x180047486  test    rcx, rcx
0x180047489  jz      short loc_18004749C
0x18004748b  call    cs:__imp_DeleteObject
0x180047491  mov     cs:qword_1800A4230, 0
0x18004749c  add     rsp, 28h
0x1800474a0  retn
```
