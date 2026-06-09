# InitThemeData(HWND__ *)

- ea: `0x18010f6cc`
- end: `0x18010f733`
- name: `?InitThemeData@@YAXPEAUHWND__@@@Z`
- size: `103`
- prototype: `void __fastcall(HWND hwnd)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180121050`
- `0x1801fcd00`

## callees

- `0x18010f6cc`
- `0x18012c638`

## import_xrefs

- `ext-ms-win-uxtheme-themes-l1-1-0!OpenThemeData` at `0x18010f6f2`
- `ext-ms-win-uxtheme-themes-l1-1-0!OpenThemeData` at `0x18010f719`
- `ext-ms-win-uxtheme-themes-l1-1-0!OpenThemeData` at `0x18010f6f2`
- `ext-ms-win-uxtheme-themes-l1-1-0!OpenThemeData` at `0x18010f719`

## string_xrefs

- `0x18010f6e8`: `ComboBox`

## pseudocode

```c
void __fastcall InitThemeData(HWND hwnd)
{
  if ( (unsigned int)FIsThemeActive() )
  {
    if ( !vhThemeComboBox )
      vhThemeComboBox = OpenThemeData(hwnd, L"ComboBox");
    if ( !vhThemeEdit )
      vhThemeEdit = OpenThemeData(hwnd, L"Edit");
  }
}

```

## disassembly

```asm
0x18010f6cc  push    rbx
0x18010f6ce  sub     rsp, 20h
0x18010f6d2  mov     rbx, rcx
0x18010f6d5  call    ?FIsThemeActive@@YAHXZ; FIsThemeActive(void)
0x18010f6da  test    eax, eax
0x18010f6dc  jz      short loc_18010F72C
0x18010f6de  cmp     cs:?vhThemeComboBox@@3PEAXEA, 0; void * vhThemeComboBox
0x18010f6e6  jnz     short loc_18010F705
0x18010f6e8  lea     rdx, pszClassList; "ComboBox"
0x18010f6ef  mov     rcx, rbx; hwnd
0x18010f6f2  call    cs:__imp_OpenThemeData
0x18010f6f9  nop     dword ptr [rax+rax+00h]
0x18010f6fe  mov     cs:?vhThemeComboBox@@3PEAXEA, rax; void * vhThemeComboBox
0x18010f705  cmp     cs:?vhThemeEdit@@3PEAXEA, 0; void * vhThemeEdit
0x18010f70d  jnz     short loc_18010F72C
0x18010f70f  lea     rdx, aEdit; "Edit"
0x18010f716  mov     rcx, rbx; hwnd
0x18010f719  call    cs:__imp_OpenThemeData
0x18010f720  nop     dword ptr [rax+rax+00h]
0x18010f725  mov     cs:?vhThemeEdit@@3PEAXEA, rax; void * vhThemeEdit
0x18010f72c  add     rsp, 20h
0x18010f730  pop     rbx
0x18010f731  retn
```
