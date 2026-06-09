# ShowWarningDialogW

- ea: `0x18000bdd0`
- end: `0x18000becf`
- name: `ShowWarningDialogW`
- size: `255`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x18000a630`
- `0x18000bdd0`
- `0x180012a78`
- `0x180012b28`
- `0x18001557c`
- `0x18002dcd0`
- `0x180030ea0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000be9e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000be9e`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18000bdfe`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18000bdfe`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000bea4`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000bea4`
- `api-ms-win-shcore-obsolete-l1-1-0!CommandLineToArgvW` at `0x18000be1c`
- `api-ms-win-shcore-obsolete-l1-1-0!CommandLineToArgvW` at `0x18000be1c`
- `USER32!GetActiveWindow` at `0x18000be7e`
- `USER32!GetActiveWindow` at `0x18000be7e`
- `USER32!LockSetForegroundWindow` at `0x18000be68`
- `USER32!LockSetForegroundWindow` at `0x18000be68`

## pseudocode

```c
void __fastcall ShowWarningDialogW(__int64 a1, __int64 a2, const WCHAR *a3)
{
  LPWSTR *v4; // rax
  LPWSTR *v5; // rbx
  const unsigned __int16 *v6; // rdi
  int v7; // esi
  HWND ActiveWindow; // rax
  int pNumArgs; // [rsp+20h] [rbp-2B8h] BYREF
  INITCOMMONCONTROLSEX picce; // [rsp+28h] [rbp-2B0h] BYREF
  _BYTE v11[656]; // [rsp+30h] [rbp-2A8h] BYREF

  if ( CoInitializeEx(0, 2u) >= 0 )
  {
    pNumArgs = 0;
    v4 = CommandLineToArgvW(a3, &pNumArgs);
    v5 = v4;
    if ( v4 && pNumArgs == 1 )
    {
      v6 = *v4;
      if ( *v4 )
      {
        picce.dwSize = 8;
        picce.dwICC = 49152;
        if ( InitCommonControlsEx(&picce) )
        {
          v7 = IsDxgExclusiveModeActive();
          if ( v7 )
            LockSetForegroundWindow(1u);
          CWarningDialog::CWarningDialog((CWarningDialog *)v11, v6, v7);
          ActiveWindow = GetActiveWindow();
          ATL::CDialogImpl<CWarningBaseDlg,ATL::CWindow>::DoModal((__int64)v11, ActiveWindow);
          CWarningDialog::~CWarningDialog((CWarningDialog *)v11);
        }
      }
      LocalFree(v5);
    }
    CoUninitialize();
  }
}

```

## disassembly

```asm
0x18000bdd0  mov     [rsp+arg_0], rbx
0x18000bdd5  mov     [rsp+arg_8], rsi
0x18000bdda  push    rdi
0x18000bddb  sub     rsp, 2D0h
0x18000bde2  mov     rax, cs:__security_cookie
0x18000bde9  xor     rax, rsp
0x18000bdec  mov     [rsp+2D8h+var_18], rax
0x18000bdf4  mov     edx, 2; dwCoInit
0x18000bdf9  xor     ecx, ecx; pvReserved
0x18000bdfb  mov     rbx, r8
0x18000bdfe  call    cs:__imp_CoInitializeEx
0x18000be04  test    eax, eax
0x18000be06  js      loc_18000BEAA
0x18000be0c  lea     rdx, [rsp+2D8h+pNumArgs]; pNumArgs
0x18000be11  mov     [rsp+2D8h+pNumArgs], 0
0x18000be19  mov     rcx, rbx; lpCmdLine
0x18000be1c  call    cs:__imp_CommandLineToArgvW
0x18000be22  mov     rbx, rax
0x18000be25  test    rax, rax
0x18000be28  jz      short loc_18000BEA4
0x18000be2a  cmp     [rsp+2D8h+pNumArgs], 1
0x18000be2f  jnz     short loc_18000BEA4
0x18000be31  mov     rdi, [rax]
0x18000be34  test    rdi, rdi
0x18000be37  jz      short loc_18000BE9B
0x18000be39  lea     rcx, [rsp+2D8h+picce]; picce
0x18000be3e  mov     [rsp+2D8h+picce.dwSize], 8
0x18000be46  mov     [rsp+2D8h+picce.dwICC], 0C000h
0x18000be4e  call    InitCommonControlsEx
0x18000be53  cmp     eax, 1
0x18000be56  jnz     short loc_18000BE9B
0x18000be58  call    ?IsDxgExclusiveModeActive@@YAHXZ; IsDxgExclusiveModeActive(void)
0x18000be5d  mov     esi, eax
0x18000be5f  test    eax, eax
0x18000be61  jz      short loc_18000BE6E
0x18000be63  mov     ecx, 1; uLockCode
0x18000be68  call    cs:__imp_LockSetForegroundWindow
0x18000be6e  mov     r8d, esi; int
0x18000be71  lea     rcx, [rsp+2D8h+var_2A8]; this
0x18000be76  mov     rdx, rdi; unsigned __int16 *
0x18000be79  call    ??0CWarningDialog@@QEAA@PEBGH@Z; CWarningDialog::CWarningDialog(ushort const *,int)
0x18000be7e  call    cs:__imp_GetActiveWindow
0x18000be84  mov     rdx, rax
0x18000be87  lea     rcx, [rsp+2D8h+var_2A8]
0x18000be8c  call    ?DoModal@?$CDialogImpl@VCWarningBaseDlg@@VCWindow@ATL@@@ATL@@QEAA_JPEAUHWND__@@_J@Z; ATL::CDialogImpl<CWarningBaseDlg,ATL::CWindow>::DoModal(HWND__ *,__int64)
0x18000be91  lea     rcx, [rsp+2D8h+var_2A8]; this
0x18000be96  call    ??1CWarningDialog@@UEAA@XZ; CWarningDialog::~CWarningDialog(void)
0x18000be9b  mov     rcx, rbx; hMem
0x18000be9e  call    cs:__imp_LocalFree
0x18000bea4  call    cs:__imp_CoUninitialize
0x18000beaa  mov     rcx, [rsp+2D8h+var_18]
0x18000beb2  xor     rcx, rsp; StackCookie
0x18000beb5  call    __security_check_cookie
0x18000beba  lea     r11, [rsp+2D8h+var_8]
0x18000bec2  mov     rbx, [r11+10h]
0x18000bec6  mov     rsi, [r11+18h]
0x18000beca  mov     rsp, r11
0x18000becd  pop     rdi
0x18000bece  retn
```
