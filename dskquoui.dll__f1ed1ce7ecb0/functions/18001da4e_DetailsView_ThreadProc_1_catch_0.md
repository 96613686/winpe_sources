# _DetailsView::ThreadProc_::_1_::catch$0

- ea: `0x18001da4e`
- end: `0x18001db00`
- name: `_DetailsView::ThreadProc_::_1_::catch$0`
- size: `178`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x18000a48c`
- `0x18001ab24`
- `0x18001da4e`
- `0x18001f010`

## import_xrefs

- `ole32!OleIsCurrentClipboard` at `0x18001dadd`
- `ole32!OleIsCurrentClipboard` at `0x18001dadd`
- `ole32!OleFlushClipboard` at `0x18001dae7`
- `ole32!OleFlushClipboard` at `0x18001dae7`
- `USER32!SetWindowLongPtrW` at `0x18001da93`
- `USER32!SetWindowLongPtrW` at `0x18001da93`
- `USER32!GetDesktopWindow` at `0x18001da5c`
- `USER32!GetDesktopWindow` at `0x18001da5c`

## pseudocode

```c
__int64 __fastcall DetailsView::ThreadProc_::_1_::catch_0(__int64 a1, __int64 a2)
{
  HWND DesktopWindow; // rax
  unsigned int v4; // r8d
  __int64 v5; // rbx

  DesktopWindow = GetDesktopWindow();
  DiskQuotaMsgBox(DesktopWindow, 0x9E76u, v4, 0x10u);
  v5 = *(_QWORD *)(a2 + 112);
  if ( *(_QWORD *)(v5 + 168) )
    SetWindowLongPtrW(*(HWND *)(v5 + 104), -4, *(_QWORD *)(v5 + 168));
  DetailsView::DisconnectEventSink((DetailsView *)v5);
  if ( *(_QWORD *)(v5 + 176) )
  {
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v5 + 176) + 16LL))(*(_QWORD *)(v5 + 176));
    *(_QWORD *)(v5 + 176) = 0;
  }
  if ( *(_QWORD *)(v5 + 496) && !OleIsCurrentClipboard(*(LPDATAOBJECT *)(v5 + 496)) )
    OleFlushClipboard();
  return 0;
}

```

## disassembly

```asm
0x18001da4e  mov     [rsp+arg_8], rdx
0x18001da53  push    rbx
0x18001da54  push    rbp
0x18001da55  sub     rsp, 38h
0x18001da59  mov     rbp, rdx
0x18001da5c  call    cs:__imp_GetDesktopWindow
0x18001da62  mov     rcx, rax; hWnd
0x18001da65  mov     edx, 9E76h; unsigned int
0x18001da6a  mov     r9d, 10h; unsigned int
0x18001da70  call    ?DiskQuotaMsgBox@@YAHPEAUHWND__@@III@Z; DiskQuotaMsgBox(HWND__ *,uint,uint,uint)
0x18001da75  mov     rbx, [rbp+70h]
0x18001da79  cmp     qword ptr [rbx+0A8h], 0
0x18001da81  jz      short loc_18001DA99
0x18001da83  mov     r8, [rbx+0A8h]; dwNewLong
0x18001da8a  mov     edx, 0FFFFFFFCh; nIndex
0x18001da8f  mov     rcx, [rbx+68h]; hWnd
0x18001da93  call    cs:__imp_SetWindowLongPtrW
0x18001da99  mov     rcx, rbx; this
0x18001da9c  call    ?DisconnectEventSink@DetailsView@@AEAAJXZ; DetailsView::DisconnectEventSink(void)
0x18001daa1  cmp     qword ptr [rbx+0B0h], 0
0x18001daa9  jz      short loc_18001DACC
0x18001daab  mov     rax, [rbx+0B0h]
0x18001dab2  mov     rdx, [rax]
0x18001dab5  mov     rcx, rax
0x18001dab8  mov     rax, [rdx+10h]
0x18001dabc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dac1  mov     qword ptr [rbx+0B0h], 0
0x18001dacc  cmp     qword ptr [rbx+1F0h], 0
0x18001dad4  jz      short loc_18001DAEE
0x18001dad6  mov     rcx, [rbx+1F0h]; pDataObj
0x18001dadd  call    cs:__imp_OleIsCurrentClipboard
0x18001dae3  test    eax, eax
0x18001dae5  jnz     short loc_18001DAEE
0x18001dae7  call    cs:__imp_OleFlushClipboard
0x18001daed  nop
0x18001daee  mov     rax, 0
0x18001daf8  add     rsp, 38h
0x18001dafc  pop     rbp
0x18001dafd  pop     rbx
0x18001dafe  retn
```
