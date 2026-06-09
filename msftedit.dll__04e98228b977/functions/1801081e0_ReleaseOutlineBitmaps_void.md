# ReleaseOutlineBitmaps(void)

- ea: `0x1801081e0`
- end: `0x180108254`
- name: `?ReleaseOutlineBitmaps@@YAXXZ`
- size: `116`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800de2e8`

## callees

- `0x1801081e0`

## import_xrefs

- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x18010821a`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x180108228`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x180108236`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x18010821a`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x180108228`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x180108236`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x180108248`

## pseudocode

```c
void ReleaseOutlineBitmaps(void)
{
  if ( h )
    DeleteObject(h);
  if ( qword_1802E4558 )
    DeleteObject(qword_1802E4558);
  if ( qword_1802E4550 )
    DeleteObject(qword_1802E4550);
  if ( qword_1802E4548 )
    DeleteObject((HGDIOBJ)qword_1802E4548);
}

```

## disassembly

```asm
0x1801081e0  sub     rsp, 28h
0x1801081e4  mov     rcx, cs:h; ho
0x1801081eb  test    rcx, rcx
0x1801081ee  jnz     short loc_18010821A
0x1801081f0  mov     rcx, cs:qword_1802E4558; ho
0x1801081f7  test    rcx, rcx
0x1801081fa  jnz     short loc_180108228
0x1801081fc  mov     rcx, cs:qword_1802E4550; ho
0x180108203  test    rcx, rcx
0x180108206  jnz     short loc_180108236
0x180108208  mov     rcx, cs:qword_1802E4548
0x18010820f  test    rcx, rcx
0x180108212  jnz     short loc_180108244
0x180108214  add     rsp, 28h
0x180108218  retn
0x18010821a  call    cs:__imp_DeleteObject
0x180108221  nop     dword ptr [rax+rax+00h]
0x180108226  jmp     short loc_1801081F0
0x180108228  call    cs:__imp_DeleteObject
0x18010822f  nop     dword ptr [rax+rax+00h]
0x180108234  jmp     short loc_1801081FC
0x180108236  call    cs:__imp_DeleteObject
0x18010823d  nop     dword ptr [rax+rax+00h]
0x180108242  jmp     short loc_180108208
0x180108244  add     rsp, 28h
0x180108248  jmp     cs:__imp_DeleteObject
```
