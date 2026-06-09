# CMFCDynamicLayout::CorrectItem(AFX_DYNAMIC_LAYOUT_ITEM &)

- ea: `0x1800188b0`
- end: `0x180018955`
- name: `?CorrectItem@CMFCDynamicLayout@@IEBAXAEAUAFX_DYNAMIC_LAYOUT_ITEM@@@Z`
- size: `165`
- prototype: `void __fastcall(CMFCDynamicLayout *__hidden this, struct AFX_DYNAMIC_LAYOUT_ITEM *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180018360`

## callees

- `0x1800188b0`

## import_xrefs

- `MFC42u!__imp_??0CString@@QEAA@XZ` at `0x1800188c2`
- `MFC42u!__imp_??0CString@@QEAA@XZ` at `0x1800188c2`
- `MFC42u!__imp_??1CString@@QEAA@XZ` at `0x180018949`
- `MFC42u!__imp_??1CString@@QEAA@XZ` at `0x180018949`
- `MFC42u!__imp_?GetBufferSetLength@CString@@QEAAPEAGH@Z` at `0x1800188d3`
- `MFC42u!__imp_?GetBufferSetLength@CString@@QEAAPEAGH@Z` at `0x1800188d3`
- `MFC42u!__imp_?ReleaseBuffer@CString@@QEAAXH@Z` at `0x1800188f3`
- `MFC42u!__imp_?ReleaseBuffer@CString@@QEAAXH@Z` at `0x1800188f3`
- `msvcrt!_wcsicmp` at `0x180018905`
- `msvcrt!_wcsicmp` at `0x18001891b`
- `msvcrt!_wcsicmp` at `0x180018905`
- `msvcrt!_wcsicmp` at `0x18001891b`
- `USER32!GetClassNameW` at `0x1800188e5`
- `USER32!GetClassNameW` at `0x1800188e5`
- `USER32!GetWindowLongW` at `0x18001892d`
- `USER32!GetWindowLongW` at `0x18001892d`

## string_xrefs

- `0x1800188f9`: `ComboBox`
- `0x18001890f`: `ComboBoxEx32`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CMFCDynamicLayout::CorrectItem(wchar_t *this, HWND *a2)
{
  WCHAR *BufferSetLength; // rax
  char WindowLongW; // al
  wchar_t *String1; // [rsp+30h] [rbp+8h] BYREF

  String1 = this;
  CString::CString((CString *)&String1);
  BufferSetLength = CString::GetBufferSetLength((CString *)&String1, 1024);
  GetClassNameW(*a2, BufferSetLength, 1024);
  CString::ReleaseBuffer((CString *)&String1, -1);
  if ( !_wcsicmp(String1, L"ComboBox") || !_wcsicmp(String1, L"ComboBoxEx32") )
  {
    WindowLongW = GetWindowLongW(*a2, -16);
    if ( *((int *)a2 + 13) > 0 && (WindowLongW & 1) == 0 )
      *((_DWORD *)a2 + 13) = 0;
  }
  CString::~CString((CString *)&String1);
}

```

## disassembly

```asm
0x1800188b0  mov     [rsp+String1], rcx
0x1800188b5  push    rbx
0x1800188b6  sub     rsp, 20h
0x1800188ba  mov     rbx, rdx
0x1800188bd  lea     rcx, [rsp+28h+String1]
0x1800188c2  call    cs:__imp_??0CString@@QEAA@XZ; CString::CString(void)
0x1800188c8  nop
0x1800188c9  mov     edx, 400h
0x1800188ce  lea     rcx, [rsp+28h+String1]
0x1800188d3  call    cs:__imp_?GetBufferSetLength@CString@@QEAAPEAGH@Z; CString::GetBufferSetLength(int)
0x1800188d9  mov     r8d, 400h; nMaxCount
0x1800188df  mov     rdx, rax; lpClassName
0x1800188e2  mov     rcx, [rbx]; hWnd
0x1800188e5  call    cs:__imp_GetClassNameW
0x1800188eb  or      edx, 0FFFFFFFFh
0x1800188ee  lea     rcx, [rsp+28h+String1]
0x1800188f3  call    cs:__imp_?ReleaseBuffer@CString@@QEAAXH@Z; CString::ReleaseBuffer(int)
0x1800188f9  lea     rdx, aCombobox; "ComboBox"
0x180018900  mov     rcx, [rsp+28h+String1]; String1
0x180018905  call    cs:__imp__wcsicmp
0x18001890b  test    eax, eax
0x18001890d  jz      short loc_180018925
0x18001890f  lea     rdx, aComboboxex32; "ComboBoxEx32"
0x180018916  mov     rcx, [rsp+28h+String1]; String1
0x18001891b  call    cs:__imp__wcsicmp
0x180018921  test    eax, eax
0x180018923  jnz     short loc_180018944
0x180018925  mov     edx, 0FFFFFFF0h; nIndex
0x18001892a  mov     rcx, [rbx]; hWnd
0x18001892d  call    cs:__imp_GetWindowLongW
0x180018933  cmp     dword ptr [rbx+34h], 0
0x180018937  jle     short loc_180018944
0x180018939  test    al, 1
0x18001893b  jnz     short loc_180018944
0x18001893d  mov     dword ptr [rbx+34h], 0
0x180018944  lea     rcx, [rsp+28h+String1]
0x180018949  call    cs:__imp_??1CString@@QEAA@XZ; CString::~CString(void)
0x18001894f  add     rsp, 20h
0x180018953  pop     rbx
0x180018954  retn
```
