# CFileOwnerDialog::OnInitDialog(HWND__ *)

- ea: `0x180014114`
- end: `0x180014217`
- name: `?OnInitDialog@CFileOwnerDialog@@AEAA_JPEAUHWND__@@@Z`
- size: `259`
- prototype: `__int64 __fastcall(CFileOwnerDialog *__hidden this, HWND hDlg)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800131a0`

## callees

- `0x180015560`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800141fa`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800141fa`
- `USER32!EnableWindow` at `0x180014160`
- `USER32!EnableWindow` at `0x18001416c`
- `USER32!EnableWindow` at `0x180014178`
- `USER32!EnableWindow` at `0x180014191`
- `USER32!EnableWindow` at `0x1800141aa`
- `USER32!EnableWindow` at `0x1800141c3`
- `USER32!EnableWindow` at `0x180014160`
- `USER32!EnableWindow` at `0x18001416c`
- `USER32!EnableWindow` at `0x180014178`
- `USER32!EnableWindow` at `0x180014191`
- `USER32!EnableWindow` at `0x1800141aa`
- `USER32!EnableWindow` at `0x1800141c3`
- `USER32!GetDlgItem` at `0x18001412c`
- `USER32!GetDlgItem` at `0x18001413e`
- `USER32!GetDlgItem` at `0x180014150`
- `USER32!GetDlgItem` at `0x180014186`
- `USER32!GetDlgItem` at `0x18001419f`
- `USER32!GetDlgItem` at `0x1800141b8`
- `USER32!GetDlgItem` at `0x18001412c`
- `USER32!GetDlgItem` at `0x18001413e`
- `USER32!GetDlgItem` at `0x180014150`
- `USER32!GetDlgItem` at `0x180014186`
- `USER32!GetDlgItem` at `0x18001419f`
- `USER32!GetDlgItem` at `0x1800141b8`

## pseudocode

```c
__int64 __fastcall CFileOwnerDialog::OnInitDialog(CFileOwnerDialog *this, HWND hDlg)
{
  HWND DlgItem; // rax
  HWND v5; // rcx
  HWND v6; // rax
  HWND v7; // rax
  HWND v8; // rax
  DWORD ThreadId; // [rsp+40h] [rbp+8h] BYREF

  *((_QWORD *)this + 3) = GetDlgItem(hDlg, 1071);
  *((_QWORD *)this + 4) = GetDlgItem(hDlg, 1073);
  DlgItem = GetDlgItem(hDlg, 1083);
  v5 = (HWND)*((_QWORD *)this + 3);
  *((_QWORD *)this + 5) = DlgItem;
  EnableWindow(v5, 0);
  EnableWindow(*((HWND *)this + 4), 0);
  EnableWindow(*((HWND *)this + 5), 0);
  v6 = GetDlgItem(hDlg, 1082);
  EnableWindow(v6, 0);
  v7 = GetDlgItem(hDlg, 1096);
  EnableWindow(v7, 0);
  v8 = GetDlgItem(hDlg, 1095);
  EnableWindow(v8, 0);
  COwnerList::Clear((CFileOwnerDialog *)((char *)this + 80));
  ThreadId = 0;
  *((_QWORD *)this + 20) = CreateThread(0, 0, CFileOwnerDialog::OwnerListThreadProc, this, 0, &ThreadId);
  return 1;
}

```

## disassembly

```asm
0x180014114  mov     [rsp+arg_8], rbx
0x180014119  push    rdi
0x18001411a  sub     rsp, 30h
0x18001411e  mov     rbx, rdx
0x180014121  mov     rdi, rcx
0x180014124  mov     rcx, rbx; hDlg
0x180014127  mov     edx, 42Fh; nIDDlgItem
0x18001412c  call    cs:__imp_GetDlgItem
0x180014132  mov     edx, 431h; nIDDlgItem
0x180014137  mov     rcx, rbx; hDlg
0x18001413a  mov     [rdi+18h], rax
0x18001413e  call    cs:__imp_GetDlgItem
0x180014144  mov     edx, 43Bh; nIDDlgItem
0x180014149  mov     rcx, rbx; hDlg
0x18001414c  mov     [rdi+20h], rax
0x180014150  call    cs:__imp_GetDlgItem
0x180014156  mov     rcx, [rdi+18h]; hWnd
0x18001415a  xor     edx, edx; bEnable
0x18001415c  mov     [rdi+28h], rax
0x180014160  call    cs:__imp_EnableWindow
0x180014166  mov     rcx, [rdi+20h]; hWnd
0x18001416a  xor     edx, edx; bEnable
0x18001416c  call    cs:__imp_EnableWindow
0x180014172  mov     rcx, [rdi+28h]; hWnd
0x180014176  xor     edx, edx; bEnable
0x180014178  call    cs:__imp_EnableWindow
0x18001417e  mov     edx, 43Ah; nIDDlgItem
0x180014183  mov     rcx, rbx; hDlg
0x180014186  call    cs:__imp_GetDlgItem
0x18001418c  mov     rcx, rax; hWnd
0x18001418f  xor     edx, edx; bEnable
0x180014191  call    cs:__imp_EnableWindow
0x180014197  mov     edx, 448h; nIDDlgItem
0x18001419c  mov     rcx, rbx; hDlg
0x18001419f  call    cs:__imp_GetDlgItem
0x1800141a5  mov     rcx, rax; hWnd
0x1800141a8  xor     edx, edx; bEnable
0x1800141aa  call    cs:__imp_EnableWindow
0x1800141b0  mov     edx, 447h; nIDDlgItem
0x1800141b5  mov     rcx, rbx; hDlg
0x1800141b8  call    cs:__imp_GetDlgItem
0x1800141be  mov     rcx, rax; hWnd
0x1800141c1  xor     edx, edx; bEnable
0x1800141c3  call    cs:__imp_EnableWindow
0x1800141c9  lea     rcx, [rdi+50h]; this
0x1800141cd  call    ?Clear@COwnerList@@QEAAXXZ; COwnerList::Clear(void)
0x1800141d2  lea     rax, [rsp+38h+ThreadId]
0x1800141d7  mov     [rsp+38h+ThreadId], 0
0x1800141df  mov     [rsp+38h+lpThreadId], rax; lpThreadId
0x1800141e4  lea     r8, ?OwnerListThreadProc@CFileOwnerDialog@@CAKPEAX@Z; lpStartAddress
0x1800141eb  mov     r9, rdi; lpParameter
0x1800141ee  mov     [rsp+38h+dwCreationFlags], 0; dwCreationFlags
0x1800141f6  xor     edx, edx; dwStackSize
0x1800141f8  xor     ecx, ecx; lpThreadAttributes
0x1800141fa  call    cs:__imp_CreateThread
0x180014200  mov     rbx, [rsp+38h+arg_8]
0x180014205  mov     [rdi+0A0h], rax
0x18001420c  mov     eax, 1
0x180014211  add     rsp, 30h
0x180014215  pop     rdi
0x180014216  retn
```
