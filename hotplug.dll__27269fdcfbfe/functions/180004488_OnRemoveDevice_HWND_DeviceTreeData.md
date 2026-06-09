# OnRemoveDevice(HWND__ *,_DeviceTreeData *)

- ea: `0x180004488`
- end: `0x1800044c7`
- name: `?OnRemoveDevice@@YAXPEAUHWND__@@PEAU_DeviceTreeData@@@Z`
- size: `63`
- prototype: `void __fastcall(HWND hWndParent, LPARAM dwInitParam)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180003d70`

## callees

- `0x180004488`

## import_xrefs

- `USER32!DialogBoxParamW` at `0x1800044b7`
- `USER32!DialogBoxParamW` at `0x1800044b7`

## pseudocode

```c
void __fastcall OnRemoveDevice(HWND hWndParent, LPARAM dwInitParam)
{
  bool v2; // zf

  v2 = *(_QWORD *)(dwInitParam + 48) == 0;
  *(_BYTE *)(dwInitParam + 98) = 0;
  if ( !v2 )
    DialogBoxParamW(hHotPlug, (LPCWSTR)0x140, hWndParent, RemoveConfirmDlgProc, dwInitParam);
  *(_BYTE *)(dwInitParam + 98) = 1;
}

```

## disassembly

```asm
0x180004488  push    rbx
0x18000448a  sub     rsp, 30h
0x18000448e  cmp     qword ptr [rdx+30h], 0
0x180004493  mov     rbx, rdx
0x180004496  mov     byte ptr [rdx+62h], 0
0x18000449a  jz      short loc_1800044BD
0x18000449c  mov     [rsp+38h+dwInitParam], rdx; dwInitParam
0x1800044a1  lea     r9, ?RemoveConfirmDlgProc@@YA_JPEAUHWND__@@I_K_J@Z; lpDialogFunc
0x1800044a8  mov     r8, rcx; hWndParent
0x1800044ab  mov     edx, 140h; lpTemplateName
0x1800044b0  mov     rcx, cs:?hHotPlug@@3PEAUHINSTANCE__@@EA; hInstance
0x1800044b7  call    cs:__imp_DialogBoxParamW
0x1800044bd  mov     byte ptr [rbx+62h], 1
0x1800044c1  add     rsp, 30h
0x1800044c5  pop     rbx
0x1800044c6  retn
```
