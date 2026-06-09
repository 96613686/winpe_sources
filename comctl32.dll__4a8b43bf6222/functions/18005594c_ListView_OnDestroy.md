# ListView_OnDestroy

- ea: `0x18005594c`
- end: `0x180055a0c`
- name: `ListView_OnDestroy`
- size: `192`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18005c0a0`

## callees

- `0x18002fd4c`
- `0x180051a90`
- `0x180055458`
- `0x18005594c`
- `0x18008698c`

## import_xrefs

- `GDI32!DeleteObject` at `0x1800559d4`
- `GDI32!DeleteObject` at `0x1800559e6`
- `GDI32!DeleteObject` at `0x1800559d4`
- `GDI32!DeleteObject` at `0x1800559e6`
- `KERNEL32!LocalFree` at `0x180055a00`
- `KERNEL32!LocalFree` at `0x180055a00`
- `USER32!IsWindow` at `0x18005595c`
- `USER32!IsWindow` at `0x18005595c`
- `USER32!DestroyWindow` at `0x18005596d`
- `USER32!DestroyWindow` at `0x18005596d`
- `USER32!DestroyCursor` at `0x18005597f`
- `USER32!DestroyCursor` at `0x18005597f`

## pseudocode

```c
HLOCAL __fastcall ListView_OnDestroy(__int64 a1)
{
  HCURSOR v2; // rcx
  void *v3; // rcx
  void *v4; // rcx
  HLOCAL result; // rax
  void *v6; // rcx

  if ( IsWindow(*(HWND *)(a1 + 208)) )
    DestroyWindow(*(HWND *)(a1 + 208));
  v2 = *(HCURSOR *)(a1 + 552);
  if ( v2 )
    DestroyCursor(v2);
  *(_QWORD *)(a1 + 208) = 0;
  Str_Set(a1 + 224, 0);
  Str_Set(a1 + 608, 0);
  TerminateDitherBrush();
  if ( (*(_DWORD *)(a1 + 16) & 0x1000) == 0 )
    ListView_OnDeleteAllItems(a1);
  if ( (*(_DWORD *)(a1 + 72) & 0x100) != 0 )
  {
    v3 = *(void **)(a1 + 88);
    if ( v3 )
      DeleteObject(v3);
  }
  v4 = *(void **)(a1 + 536);
  if ( v4 )
    DeleteObject(v4);
  result = (HLOCAL)ListView_DeleteHrgnInval(a1);
  v6 = *(void **)(a1 + 176);
  if ( v6 )
    return LocalFree(v6);
  return result;
}

```

## disassembly

```asm
0x18005594c  push    rbx
0x18005594e  sub     rsp, 20h
0x180055952  mov     rbx, rcx
0x180055955  mov     rcx, [rcx+0D0h]; hWnd
0x18005595c  call    cs:__imp_IsWindow
0x180055962  test    eax, eax
0x180055964  jz      short loc_180055973
0x180055966  mov     rcx, [rbx+0D0h]; hWnd
0x18005596d  call    cs:__imp_DestroyWindow
0x180055973  mov     rcx, [rbx+228h]; hCursor
0x18005597a  test    rcx, rcx
0x18005597d  jz      short loc_180055985
0x18005597f  call    cs:__imp_DestroyCursor
0x180055985  lea     rcx, [rbx+0E0h]
0x18005598c  mov     qword ptr [rbx+0D0h], 0
0x180055997  xor     edx, edx
0x180055999  call    Str_Set
0x18005599e  lea     rcx, [rbx+260h]
0x1800559a5  xor     edx, edx
0x1800559a7  call    Str_Set
0x1800559ac  call    TerminateDitherBrush
0x1800559b1  test    dword ptr [rbx+10h], 1000h
0x1800559b8  jnz     short loc_1800559C2
0x1800559ba  mov     rcx, rbx
0x1800559bd  call    ListView_OnDeleteAllItems
0x1800559c2  test    dword ptr [rbx+48h], 100h
0x1800559c9  jz      short loc_1800559DA
0x1800559cb  mov     rcx, [rbx+58h]; ho
0x1800559cf  test    rcx, rcx
0x1800559d2  jz      short loc_1800559DA
0x1800559d4  call    cs:__imp_DeleteObject
0x1800559da  mov     rcx, [rbx+218h]; ho
0x1800559e1  test    rcx, rcx
0x1800559e4  jz      short loc_1800559EC
0x1800559e6  call    cs:__imp_DeleteObject
0x1800559ec  mov     rcx, rbx
0x1800559ef  call    ListView_DeleteHrgnInval
0x1800559f4  mov     rcx, [rbx+0B0h]; hMem
0x1800559fb  test    rcx, rcx
0x1800559fe  jz      short loc_180055A06
0x180055a00  call    cs:__imp_LocalFree
0x180055a06  add     rsp, 20h
0x180055a0a  pop     rbx
0x180055a0b  retn
```
