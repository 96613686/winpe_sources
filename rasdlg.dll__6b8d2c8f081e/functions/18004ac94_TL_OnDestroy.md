# TL_OnDestroy

- ea: `0x18004ac94`
- end: `0x18004acf7`
- name: `TL_OnDestroy`
- size: `99`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18004c060`

## callees

- `0x18004ab00`
- `0x18004ac94`

## import_xrefs

- `GDI32!DeleteDC` at `0x18004acd9`
- `GDI32!DeleteDC` at `0x18004acd9`
- `GDI32!DeleteObject` at `0x18004accc`
- `GDI32!DeleteObject` at `0x18004aceb`
- `GDI32!DeleteObject` at `0x18004accc`
- `GDI32!DeleteObject` at `0x18004aceb`
- `GDI32!SelectObject` at `0x18004acbf`
- `GDI32!SelectObject` at `0x18004acbf`

## pseudocode

```c
int __fastcall TL_OnDestroy(__int64 a1)
{
  int result; // eax
  HDC v3; // rcx
  void *v4; // rcx

  result = TL_OnDeleteAllItems();
  v3 = *(HDC *)(a1 + 232);
  if ( v3 )
  {
    if ( *(_QWORD *)(a1 + 240) )
    {
      SelectObject(v3, *(HGDIOBJ *)(a1 + 264));
      DeleteObject(*(HGDIOBJ *)(a1 + 240));
    }
    result = DeleteDC(*(HDC *)(a1 + 232));
  }
  v4 = *(void **)(a1 + 248);
  if ( v4 )
    return DeleteObject(v4);
  return result;
}

```

## disassembly

```asm
0x18004ac94  push    rbx
0x18004ac96  sub     rsp, 20h
0x18004ac9a  mov     rbx, rcx
0x18004ac9d  call    TL_OnDeleteAllItems
0x18004aca2  mov     rcx, [rbx+0E8h]; hdc
0x18004aca9  test    rcx, rcx
0x18004acac  jz      short loc_18004ACDF
0x18004acae  cmp     qword ptr [rbx+0F0h], 0
0x18004acb6  jz      short loc_18004ACD2
0x18004acb8  mov     rdx, [rbx+108h]; h
0x18004acbf  call    cs:__imp_SelectObject
0x18004acc5  mov     rcx, [rbx+0F0h]; ho
0x18004accc  call    cs:__imp_DeleteObject
0x18004acd2  mov     rcx, [rbx+0E8h]; hdc
0x18004acd9  call    cs:__imp_DeleteDC
0x18004acdf  mov     rcx, [rbx+0F8h]; ho
0x18004ace6  test    rcx, rcx
0x18004ace9  jz      short loc_18004ACF1
0x18004aceb  call    cs:__imp_DeleteObject
0x18004acf1  add     rsp, 20h
0x18004acf5  pop     rbx
0x18004acf6  retn
```
