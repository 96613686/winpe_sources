# ComboEx_OnDestroy

- ea: `0x1800382d0`
- end: `0x18003837b`
- name: `ComboEx_OnDestroy`
- size: `171`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800371b0`
- `0x180038160`

## callees

- `0x18002fd4c`
- `0x1800306e0`
- `0x1800382d0`

## import_xrefs

- `GDI32!DeleteObject` at `0x180038328`
- `GDI32!DeleteObject` at `0x180038328`
- `KERNEL32!LocalFree` at `0x180038374`
- `USER32!SendMessageW` at `0x1800382e8`
- `USER32!SendMessageW` at `0x18003831b`
- `USER32!SendMessageW` at `0x1800382e8`
- `USER32!SendMessageW` at `0x18003831b`
- `USER32!SetWindowLongPtrW` at `0x180038366`
- `USER32!SetWindowLongPtrW` at `0x180038366`

## pseudocode

```c
HLOCAL __fastcall ComboEx_OnDestroy(__int64 a1)
{
  HWND v2; // rcx
  void *v3; // rax
  HWND v4; // rcx
  HWND v5; // rcx

  SendMessageW(*(HWND *)(a1 + 56), 0x14Bu, 0, 0);
  if ( *(_QWORD *)(a1 + 112) )
    Str_Set(a1 + 112, 0);
  if ( (*(_BYTE *)(a1 + 144) & 4) != 0 )
  {
    v2 = *(HWND *)(a1 + 56);
    if ( v2 )
      v3 = (void *)SendMessageW(v2, 0x31u, 0, 0);
    else
      v3 = 0;
    DeleteObject(v3);
  }
  v4 = *(HWND *)(a1 + 64);
  if ( v4 )
    RemoveWindowSubclass(v4, EditSubclassProc, 0);
  v5 = *(HWND *)(a1 + 56);
  if ( v5 )
    RemoveWindowSubclass(v5, ComboSubclassProc, 0);
  SetWindowLongPtrW(*(HWND *)a1, 0, 0);
  return LocalFree((HLOCAL)a1);
}

```

## disassembly

```asm
0x1800382d0  push    rbx
0x1800382d2  sub     rsp, 20h
0x1800382d6  mov     rbx, rcx
0x1800382d9  xor     r9d, r9d; lParam
0x1800382dc  mov     rcx, [rcx+38h]; hWnd
0x1800382e0  xor     r8d, r8d; wParam
0x1800382e3  mov     edx, 14Bh; Msg
0x1800382e8  call    cs:__imp_SendMessageW
0x1800382ee  lea     rcx, [rbx+70h]
0x1800382f2  cmp     qword ptr [rcx], 0
0x1800382f6  jz      short loc_1800382FF
0x1800382f8  xor     edx, edx
0x1800382fa  call    Str_Set
0x1800382ff  test    byte ptr [rbx+90h], 4
0x180038306  jz      short loc_18003832E
0x180038308  mov     rcx, [rbx+38h]; hWnd
0x18003830c  test    rcx, rcx
0x18003830f  jz      short loc_180038323
0x180038311  xor     r9d, r9d; lParam
0x180038314  xor     r8d, r8d; wParam
0x180038317  lea     edx, [r9+31h]; Msg
0x18003831b  call    cs:__imp_SendMessageW
0x180038321  jmp     short loc_180038325
0x180038323  xor     eax, eax
0x180038325  mov     rcx, rax; ho
0x180038328  call    cs:__imp_DeleteObject
0x18003832e  mov     rcx, [rbx+40h]; hWnd
0x180038332  test    rcx, rcx
0x180038335  jz      short loc_180038346
0x180038337  xor     r8d, r8d; uIdSubclass
0x18003833a  lea     rdx, EditSubclassProc; pfnSubclass
0x180038341  call    RemoveWindowSubclass
0x180038346  mov     rcx, [rbx+38h]; hWnd
0x18003834a  test    rcx, rcx
0x18003834d  jz      short loc_18003835E
0x18003834f  xor     r8d, r8d; uIdSubclass
0x180038352  lea     rdx, ComboSubclassProc; pfnSubclass
0x180038359  call    RemoveWindowSubclass
0x18003835e  mov     rcx, [rbx]; hWnd
0x180038361  xor     r8d, r8d; dwNewLong
0x180038364  xor     edx, edx; nIndex
0x180038366  call    cs:__imp_SetWindowLongPtrW
0x18003836c  mov     rcx, rbx
0x18003836f  add     rsp, 20h
0x180038373  pop     rbx
0x180038374  jmp     cs:__imp_LocalFree
```
