# Helper::OpenDialogHookAddButton(HWND__ *,uint,unsigned __int64,__int64)

- ea: `0x180014a30`
- end: `0x180014aa4`
- name: `?OpenDialogHookAddButton@Helper@@YA_KPEAUHWND__@@I_K_J@Z`
- size: `116`
- prototype: `unsigned __int64 __fastcall(HWND hWnd, HWND, __int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180014b40`

## callees

- `0x180014a30`
- `0x18001772c`
- `0x1800179f0`

## import_xrefs

- `USER32!GetParent` at `0x180014a70`
- `USER32!GetParent` at `0x180014a70`
- `USER32!SetWindowTextW` at `0x180014a8c`
- `USER32!SetWindowTextW` at `0x180014a8c`
- `USER32!GetDlgItem` at `0x180014a7e`
- `USER32!GetDlgItem` at `0x180014a7e`

## pseudocode

```c
unsigned __int64 __fastcall Helper::OpenDialogHookAddButton(HWND hWnd, HWND a2, __int64 a3, __int64 a4)
{
  HINSTANCE v5; // rdx
  HWND Parent; // rax
  HWND DlgItem; // rax
  int v9; // [rsp+20h] [rbp-18h] BYREF
  LPCWSTR lpString; // [rsp+28h] [rbp-10h]

  if ( (_DWORD)a2 == 272 )
  {
    v5 = *(HINSTANCE *)(a4 + 16);
    lpString = &NCoreLibrary::TString::gszNullState;
    v9 = 1735554163;
    if ( (int)NCoreLibrary::TString::LoadStringFromRC((NCoreLibrary::TString *)&v9, v5, 0x712u) >= 0 )
    {
      Parent = GetParent(hWnd);
      DlgItem = GetDlgItem(Parent, 1);
      SetWindowTextW(DlgItem, lpString);
    }
    NCoreLibrary::TString::~TString((NCoreLibrary::TString *)&v9);
  }
  return 0;
}

```

## disassembly

```asm
0x180014a30  push    rbx
0x180014a32  sub     rsp, 30h
0x180014a36  mov     rbx, rcx
0x180014a39  cmp     edx, 110h
0x180014a3f  jnz     short loc_180014A9C
0x180014a41  mov     rdx, [r9+10h]; HINSTANCE
0x180014a45  lea     rax, ?gszNullState@TString@NCoreLibrary@@0PAGA; ushort near * NCoreLibrary::TString::gszNullState
0x180014a4c  mov     r8d, 712h; unsigned int
0x180014a52  mov     [rsp+38h+lpString], rax
0x180014a57  lea     rcx, [rsp+38h+var_18]; this
0x180014a5c  mov     [rsp+38h+var_18], 67727473h
0x180014a64  call    ?LoadStringFromRC@TString@NCoreLibrary@@QEAAJPEAUHINSTANCE__@@I@Z; NCoreLibrary::TString::LoadStringFromRC(HINSTANCE__ *,uint)
0x180014a69  test    eax, eax
0x180014a6b  js      short loc_180014A92
0x180014a6d  mov     rcx, rbx; hWnd
0x180014a70  call    cs:__imp_GetParent
0x180014a76  mov     rcx, rax; hDlg
0x180014a79  mov     edx, 1; nIDDlgItem
0x180014a7e  call    cs:__imp_GetDlgItem
0x180014a84  mov     rdx, [rsp+38h+lpString]; lpString
0x180014a89  mov     rcx, rax; hWnd
0x180014a8c  call    cs:__imp_SetWindowTextW
0x180014a92  lea     rcx, [rsp+38h+var_18]; this
0x180014a97  call    ??1TString@NCoreLibrary@@QEAA@XZ; NCoreLibrary::TString::~TString(void)
0x180014a9c  xor     eax, eax
0x180014a9e  add     rsp, 30h
0x180014aa2  pop     rbx
0x180014aa3  retn
```
