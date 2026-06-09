# CPropSheetPage::CreatePage(uint,ulong,ushort const *,ushort const *,ushort const *,HINSTANCE__ *)

- ea: `0x180011e58`
- end: `0x180011ecd`
- name: `?CreatePage@CPropSheetPage@@QEAAPEAU_PSP@@IKPEBG00PEAUHINSTANCE__@@@Z`
- size: `117`
- prototype: `struct _PSP *__fastcall(CPropSheetPage *__hidden this, unsigned int, unsigned int, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, HINSTANCE)`
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180008e2c`
- `0x18000da34`

## import_xrefs

- `COMCTL32!CreatePropertySheetPageW` at `0x180011ebe`
- `COMCTL32!CreatePropertySheetPageW` at `0x180011ebe`

## pseudocode

```c
HPROPSHEETPAGE __fastcall CPropSheetPage::CreatePage(
        CPropSheetPage *this,
        unsigned __int16 a2,
        __int64 a3,
        const unsigned __int16 *a4)
{
  PROPSHEETPAGEW_V4 constPropSheetPagePointer; // [rsp+20h] [rbp-31h] BYREF

  constPropSheetPagePointer.lParam = (LPARAM)this;
  constPropSheetPagePointer.hIcon = 0;
  memset(&constPropSheetPagePointer.pcRefParent, 0, 40);
  constPropSheetPagePointer.hInstance = hInstance;
  constPropSheetPagePointer.pszTemplate = (LPCWSTR)a2;
  constPropSheetPagePointer.pfnDlgProc = (DLGPROC)CPropSheetPage::DialogProc;
  constPropSheetPagePointer.pfnCallback = (LPFNPSPCALLBACKW)CPropSheetPage::PropSheetPageProc;
  *(_QWORD *)&constPropSheetPagePointer.dwSize = 104;
  constPropSheetPagePointer.pszTitle = 0;
  return CreatePropertySheetPageW(&constPropSheetPagePointer);
}

```

## disassembly

```asm
0x180011e58  push    rbp
0x180011e5a  lea     rbp, [rsp-3Fh]
0x180011e5f  sub     rsp, 90h
0x180011e66  xor     eax, eax
0x180011e68  mov     [rbp+3Fh+constPropSheetPagePointer.lParam], rcx
0x180011e6c  mov     qword ptr [rbp+3Fh+constPropSheetPagePointer.18h], rax
0x180011e70  lea     rcx, [rbp+3Fh+constPropSheetPagePointer]; constPropSheetPagePointer
0x180011e74  mov     [rbp+3Fh+constPropSheetPagePointer.pcRefParent], rax
0x180011e78  xor     r8d, r8d
0x180011e7b  mov     rax, cs:hInstance
0x180011e82  xorps   xmm0, xmm0
0x180011e85  mov     [rbp+3Fh+constPropSheetPagePointer.hInstance], rax
0x180011e89  movzx   eax, dx
0x180011e8c  mov     qword ptr [rbp+3Fh+constPropSheetPagePointer.10h], rax
0x180011e90  lea     rax, ?DialogProc@CPropSheetPage@@SA_JPEAUHWND__@@I_K_J@Z; CPropSheetPage::DialogProc(HWND__ *,uint,unsigned __int64,__int64)
0x180011e97  mov     [rbp+3Fh+constPropSheetPagePointer.pfnDlgProc], rax
0x180011e9b  lea     rax, ?PropSheetPageProc@CPropSheetPage@@SAIPEAUHWND__@@IPEAU_PROPSHEETPAGEW@@@Z; CPropSheetPage::PropSheetPageProc(HWND__ *,uint,_PROPSHEETPAGEW *)
0x180011ea2  mov     [rbp+3Fh+constPropSheetPagePointer.pfnCallback], rax
0x180011ea6  movups  xmmword ptr [rbp+3Fh+constPropSheetPagePointer.hActCtx], xmm0
0x180011eaa  mov     qword ptr [rbp+3Fh+constPropSheetPagePointer.dwSize], 68h ; 'h'
0x180011eb2  mov     [rbp+3Fh+constPropSheetPagePointer.pszHeaderTitle], r8
0x180011eb6  mov     [rbp+3Fh+constPropSheetPagePointer.pszHeaderSubTitle], r8
0x180011eba  mov     [rbp+3Fh+constPropSheetPagePointer.pszTitle], r8
0x180011ebe  call    cs:__imp_CreatePropertySheetPageW
0x180011ec4  add     rsp, 90h
0x180011ecb  pop     rbp
0x180011ecc  retn
```
