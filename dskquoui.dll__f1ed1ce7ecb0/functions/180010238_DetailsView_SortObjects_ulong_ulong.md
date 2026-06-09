# DetailsView::SortObjects(ulong,ulong)

- ea: `0x180010238`
- end: `0x180010307`
- name: `?SortObjects@DetailsView@@AEAA_JKK@Z`
- size: `207`
- prototype: `__int64 __fastcall(DetailsView *__hidden this, unsigned int, unsigned int)`
- caller_count: `3`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18000de10`
- `0x18000eb10`
- `0x18000f31c`

## callees

- `0x180010238`
- `0x18001c6b0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800102bc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800102df`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800102bc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800102df`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180010287`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180010295`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180010287`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180010295`
- `USER32!UpdateWindow` at `0x1800102d6`
- `USER32!UpdateWindow` at `0x1800102d6`
- `USER32!SetCursor` at `0x180010259`
- `USER32!SetCursor` at `0x1800102f6`
- `USER32!SetCursor` at `0x180010259`
- `USER32!SetCursor` at `0x1800102f6`
- `USER32!LoadCursorW` at `0x180010250`
- `USER32!LoadCursorW` at `0x180010250`
- `USER32!ShowCursor` at `0x18001026c`
- `USER32!ShowCursor` at `0x1800102e8`
- `USER32!ShowCursor` at `0x18001026c`
- `USER32!ShowCursor` at `0x1800102e8`
- `USER32!InvalidateRect` at `0x1800102cc`
- `USER32!InvalidateRect` at `0x1800102cc`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall DetailsView::SortObjects(DetailsView *this, int a2, int a3)
{
  HCURSOR CursorW; // rax
  HCURSOR v7; // rbx
  LPARAM lParam; // [rsp+20h] [rbp-48h] BYREF
  DetailsView *v10; // [rsp+28h] [rbp-40h]
  char *v11; // [rsp+30h] [rbp-38h]
  int v12; // [rsp+38h] [rbp-30h]

  CursorW = LoadCursorW(0, (LPCWSTR)0x7F02);
  v7 = SetCursor(CursorW);
  ShowCursor(1);
  LODWORD(lParam) = a2;
  HIDWORD(lParam) = a3;
  v10 = this;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 56));
  v11 = (char *)this + 56;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 56));
  v12 = 1;
  DPA_Sort(*((HDPA *)this + 6), (PFNDACOMPARE)DetailsView::CompareItems, (LPARAM)&lParam);
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 56));
  InvalidateRect(*((HWND *)this + 13), 0, 1);
  UpdateWindow(*((HWND *)this + 13));
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 56));
  ShowCursor(0);
  if ( v7 )
    SetCursor(v7);
  return 0;
}

```

## disassembly

```asm
0x180010238  push    rbx
0x18001023a  push    rbp
0x18001023b  push    rsi
0x18001023c  push    rdi
0x18001023d  sub     rsp, 48h
0x180010241  mov     esi, r8d
0x180010244  mov     edi, edx
0x180010246  mov     rbp, rcx
0x180010249  mov     edx, 7F02h; lpCursorName
0x18001024e  xor     ecx, ecx; hInstance
0x180010250  call    cs:__imp_LoadCursorW
0x180010256  mov     rcx, rax; hCursor
0x180010259  call    cs:__imp_SetCursor
0x18001025f  mov     rbx, rax
0x180010262  mov     [rsp+68h+arg_0], rax
0x180010267  mov     ecx, 1; bShow
0x18001026c  call    cs:__imp_ShowCursor
0x180010272  nop
0x180010273  mov     dword ptr [rsp+68h+lParam], edi
0x180010277  mov     dword ptr [rsp+68h+lParam+4], esi
0x18001027b  mov     [rsp+68h+var_40], rbp
0x180010280  lea     rdi, [rbp+38h]
0x180010284  mov     rcx, rdi; lpCriticalSection
0x180010287  call    cs:__imp_EnterCriticalSection
0x18001028d  mov     [rsp+68h+var_38], rdi
0x180010292  mov     rcx, rdi; lpCriticalSection
0x180010295  call    cs:__imp_EnterCriticalSection
0x18001029b  mov     [rsp+68h+var_30], 1
0x1800102a3  lea     r8, [rsp+68h+lParam]; lParam
0x1800102a8  lea     rdx, ?CompareItems@DetailsView@@CAHPEAX0_J@Z; pfnCompare
0x1800102af  mov     rcx, [rbp+30h]; hdpa
0x1800102b3  call    DPA_Sort
0x1800102b8  nop
0x1800102b9  mov     rcx, rdi; lpCriticalSection
0x1800102bc  call    cs:__imp_LeaveCriticalSection
0x1800102c2  xor     edx, edx; lpRect
0x1800102c4  lea     r8d, [rdx+1]; bErase
0x1800102c8  mov     rcx, [rbp+68h]; hWnd
0x1800102cc  call    cs:__imp_InvalidateRect
0x1800102d2  mov     rcx, [rbp+68h]; hWnd
0x1800102d6  call    cs:__imp_UpdateWindow
0x1800102dc  mov     rcx, rdi; lpCriticalSection
0x1800102df  call    cs:__imp_LeaveCriticalSection
0x1800102e5  nop
0x1800102e6  xor     ecx, ecx; bShow
0x1800102e8  call    cs:__imp_ShowCursor
0x1800102ee  test    rbx, rbx
0x1800102f1  jz      short loc_1800102FC
0x1800102f3  mov     rcx, rbx; hCursor
0x1800102f6  call    cs:__imp_SetCursor
0x1800102fc  xor     eax, eax
0x1800102fe  add     rsp, 48h
0x180010302  pop     rdi
0x180010303  pop     rsi
0x180010304  pop     rbp
0x180010305  pop     rbx
0x180010306  retn
```
