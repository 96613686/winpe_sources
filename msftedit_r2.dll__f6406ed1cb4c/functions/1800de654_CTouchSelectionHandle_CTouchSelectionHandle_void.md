# CTouchSelectionHandle::~CTouchSelectionHandle(void)

- ea: `0x1800de654`
- end: `0x1800de6dd`
- name: `??1CTouchSelectionHandle@@UEAA@XZ`
- size: `137`
- prototype: `void __fastcall(CTouchSelectionHandle *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800de62c`
- `0x1801fe6b0`

## callees

- `0x1800de654`
- `0x18012bddc`

## import_xrefs

- `ext-ms-win-ntuser-window-l1-1-0!DestroyWindow` at `0x1800de6a8`
- `ext-ms-win-ntuser-window-l1-1-0!DestroyWindow` at `0x1800de6a8`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!UnregisterClassW` at `0x1800de6c4`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!UnregisterClassW` at `0x1800de6c4`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x1800de69a`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x1800de69a`

## pseudocode

```c
void __fastcall CTouchSelectionHandle::~CTouchSelectionHandle(CTouchSelectionHandle *this)
{
  void *v2; // rcx
  HWND v3; // rcx

  *(_QWORD *)this = &CTouchSelectionHandle::`vftable';
  v2 = (void *)*((_QWORD *)this + 10);
  if ( v2 )
    DeleteObject(v2);
  v3 = (HWND)*((_QWORD *)this + 9);
  if ( v3 )
    DestroyWindow(v3);
  if ( CTouchSelectionHandle::s_ClassAtom && UnregisterClassW(L"RichEditGripperWnd", hinstRE) )
    CTouchSelectionHandle::s_ClassAtom = 0;
  CTouchTracker::~CTouchTracker(this);
}

```

## disassembly

```asm
0x1800de654  mov     [rsp+arg_0], rbx
0x1800de659  push    rdi
0x1800de65a  sub     rsp, 20h
0x1800de65e  lea     rax, ??_7CTouchSelectionHandle@@6B@; const CTouchSelectionHandle::`vftable'
0x1800de665  mov     rbx, rcx
0x1800de668  mov     [rcx], rax
0x1800de66b  xor     edi, edi
0x1800de66d  mov     rcx, [rcx+50h]; ho
0x1800de671  test    rcx, rcx
0x1800de674  jnz     short loc_1800DE69A
0x1800de676  mov     rcx, [rbx+48h]; hWnd
0x1800de67a  test    rcx, rcx
0x1800de67d  jnz     short loc_1800DE6A8
0x1800de67f  cmp     cs:?s_ClassAtom@CTouchSelectionHandle@@1GA, di; ushort CTouchSelectionHandle::s_ClassAtom
0x1800de686  jnz     short loc_1800DE6B6
0x1800de688  mov     rcx, rbx; this
0x1800de68b  mov     rbx, [rsp+28h+arg_0]
0x1800de690  add     rsp, 20h
0x1800de694  pop     rdi
0x1800de695  jmp     ??1CTouchTracker@@UEAA@XZ; CTouchTracker::~CTouchTracker(void)
0x1800de69a  call    cs:__imp_DeleteObject
0x1800de6a1  nop     dword ptr [rax+rax+00h]
0x1800de6a6  jmp     short loc_1800DE676
0x1800de6a8  call    cs:__imp_DestroyWindow
0x1800de6af  nop     dword ptr [rax+rax+00h]
0x1800de6b4  jmp     short loc_1800DE67F
0x1800de6b6  mov     rdx, cs:?hinstRE@@3PEAUHINSTANCE__@@EA; hInstance
0x1800de6bd  lea     rcx, aRicheditgrippe; "RichEditGripperWnd"
0x1800de6c4  call    cs:__imp_UnregisterClassW
0x1800de6cb  nop     dword ptr [rax+rax+00h]
0x1800de6d0  test    eax, eax
0x1800de6d2  jz      short loc_1800DE688
0x1800de6d4  mov     cs:?s_ClassAtom@CTouchSelectionHandle@@1GA, di; ushort CTouchSelectionHandle::s_ClassAtom
0x1800de6db  jmp     short loc_1800DE688
```
