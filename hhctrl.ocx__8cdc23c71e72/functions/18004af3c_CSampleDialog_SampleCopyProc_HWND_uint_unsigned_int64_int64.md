# CSampleDialog::SampleCopyProc(HWND__ *,uint,unsigned __int64,__int64)

- ea: `0x18004af3c`
- end: `0x18004bf38`
- name: `?SampleCopyProc@CSampleDialog@@QEAA_JPEAUHWND__@@I_K_J@Z`
- size: `4092`
- prototype: `__int64 __fastcall(CSampleDialog *__hidden this, HWND, unsigned int, unsigned __int64, struct tagDRAWITEMSTRUCT *)`
- caller_count: `1`
- callee_count: `29`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18004bf40`

## callees

- `0x1800020b8`
- `0x180005a4c`
- `0x1800095c8`
- `0x180009650`
- `0x18000d5bc`
- `0x18000f460`
- `0x180011d00`
- `0x180011e94`
- `0x1800123d0`
- `0x180042d40`
- `0x1800496ac`
- `0x1800496dc`
- `0x1800498dc`
- `0x180049bcc`
- `0x180049da8`
- `0x180049ddc`
- `0x18004a400`
- `0x18004a694`
- `0x18004a848`
- `0x18004af3c`
- `0x18004c960`
- `0x18004cab4`
- `0x18004cba0`
- `0x18004cc88`
- `0x18004e6a8`
- `0x18004e98c`
- `0x18004f514`
- `0x180075c90`
- `0x180075d50`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x18004b51c`
- `KERNEL32!CloseHandle` at `0x18004b646`
- `KERNEL32!CloseHandle` at `0x18004b6ab`
- `KERNEL32!CloseHandle` at `0x18004b51c`
- `KERNEL32!CloseHandle` at `0x18004b646`
- `KERNEL32!CloseHandle` at `0x18004b6ab`
- `KERNEL32!GetFileAttributesA` at `0x18004b6b8`
- `KERNEL32!GetFileAttributesA` at `0x18004b6b8`
- `KERNEL32!CreateFileA` at `0x18004b510`
- `KERNEL32!CreateFileA` at `0x18004b602`
- `KERNEL32!CreateFileA` at `0x18004b682`
- `KERNEL32!CreateFileA` at `0x18004b510`
- `KERNEL32!CreateFileA` at `0x18004b602`
- `KERNEL32!CreateFileA` at `0x18004b682`
- `KERNEL32!DeleteFileA` at `0x18004b721`
- `KERNEL32!DeleteFileA` at `0x18004b7d6`
- `KERNEL32!DeleteFileA` at `0x18004b721`
- `KERNEL32!DeleteFileA` at `0x18004b7d6`
- `KERNEL32!GetFileSize` at `0x18004b639`
- `KERNEL32!GetFileSize` at `0x18004b696`
- `KERNEL32!GetFileSize` at `0x18004b639`
- `KERNEL32!GetFileSize` at `0x18004b696`
- `KERNEL32!CopyFileA` at `0x18004b5cf`
- `KERNEL32!CopyFileA` at `0x18004b5cf`
- `KERNEL32!SetFileAttributesA` at `0x18004b6cf`
- `KERNEL32!SetFileAttributesA` at `0x18004b6cf`
- `KERNEL32!lstrlenW` at `0x18004ba0f`
- `KERNEL32!lstrlenW` at `0x18004ba0f`
- `KERNEL32!GetLastError` at `0x18004b852`
- `KERNEL32!GetLastError` at `0x18004b852`
- `USER32!GetWindow` at `0x18004bc6e`
- `USER32!GetWindow` at `0x18004bc6e`
- `USER32!SendDlgItemMessageA` at `0x18004b01f`
- `USER32!SendDlgItemMessageA` at `0x18004bc60`
- `USER32!SendDlgItemMessageA` at `0x18004bd41`
- `USER32!SendDlgItemMessageA` at `0x18004bd72`
- `USER32!SendDlgItemMessageA` at `0x18004bda2`
- `USER32!SendDlgItemMessageA` at `0x18004bdd4`
- `USER32!SendDlgItemMessageA` at `0x18004bdfa`
- `USER32!SendDlgItemMessageA` at `0x18004b01f`
- `USER32!SendDlgItemMessageA` at `0x18004bc60`
- `USER32!SendDlgItemMessageA` at `0x18004bd41`
- `USER32!SendDlgItemMessageA` at `0x18004bd72`
- `USER32!SendDlgItemMessageA` at `0x18004bda2`
- `USER32!SendDlgItemMessageA` at `0x18004bdd4`
- `USER32!SendDlgItemMessageA` at `0x18004bdfa`
- `USER32!LoadStringA` at `0x18004b33c`
- `USER32!LoadStringA` at `0x18004b35c`
- `USER32!LoadStringA` at `0x18004b7f6`
- `USER32!LoadStringA` at `0x18004b816`
- `USER32!LoadStringA` at `0x18004b928`
- `USER32!LoadStringA` at `0x18004b945`
- `USER32!LoadStringA` at `0x18004bb2b`
- `USER32!LoadStringA` at `0x18004bb4b`
- `USER32!LoadStringA` at `0x18004bcdc`
- `USER32!LoadStringA` at `0x18004b33c`
- `USER32!LoadStringA` at `0x18004b35c`
- `USER32!LoadStringA` at `0x18004b7f6`
- `USER32!LoadStringA` at `0x18004b816`
- `USER32!LoadStringA` at `0x18004b928`
- `USER32!LoadStringA` at `0x18004b945`
- `USER32!LoadStringA` at `0x18004bb2b`
- `USER32!LoadStringA` at `0x18004bb4b`
- `USER32!LoadStringA` at `0x18004bcdc`
- `USER32!MessageBoxA` at `0x18004b393`
- `USER32!MessageBoxA` at `0x18004b847`
- `USER32!MessageBoxA` at `0x18004b978`
- `USER32!MessageBoxA` at `0x18004bbae`
- `USER32!MessageBoxA` at `0x18004b393`
- `USER32!MessageBoxA` at `0x18004b847`
- `USER32!MessageBoxA` at `0x18004b978`
- `USER32!MessageBoxA` at `0x18004bbae`
- `USER32!SetDlgItemTextA` at `0x18004bcf1`
- `USER32!SetDlgItemTextA` at `0x18004bcf1`
- `USER32!OemToCharBuffA` at `0x18004b18c`
- `USER32!OemToCharBuffA` at `0x18004b18c`
- `USER32!CharPrevA` at `0x18004b22c`
- `USER32!CharPrevA` at `0x18004b4b0`
- `USER32!CharPrevA` at `0x18004b22c`
- `USER32!CharPrevA` at `0x18004b4b0`
- `USER32!LoadStringW` at `0x18004b27d`
- `USER32!LoadStringW` at `0x18004b29b`
- `USER32!LoadStringW` at `0x18004b744`
- `USER32!LoadStringW` at `0x18004b764`
- `USER32!LoadStringW` at `0x18004b88d`
- `USER32!LoadStringW` at `0x18004b8aa`
- `USER32!LoadStringW` at `0x18004b9bc`
- `USER32!LoadStringW` at `0x18004b9da`
- `USER32!LoadStringW` at `0x18004bcad`
- `USER32!LoadStringW` at `0x18004b27d`
- `USER32!LoadStringW` at `0x18004b29b`
- `USER32!LoadStringW` at `0x18004b744`
- `USER32!LoadStringW` at `0x18004b764`
- `USER32!LoadStringW` at `0x18004b88d`
- `USER32!LoadStringW` at `0x18004b8aa`
- `USER32!LoadStringW` at `0x18004b9bc`
- `USER32!LoadStringW` at `0x18004b9da`
- `USER32!LoadStringW` at `0x18004bcad`
- `USER32!SetDlgItemTextW` at `0x18004bcc0`
- `USER32!SetDlgItemTextW` at `0x18004bcc0`
- `USER32!CharToOemA` at `0x18004be22`
- `USER32!CharToOemA` at `0x18004be22`
- `USER32!EndDialog` at `0x18004b075`
- `USER32!EndDialog` at `0x18004bc1c`
- `USER32!EndDialog` at `0x18004b075`
- `USER32!EndDialog` at `0x18004bc1c`
- `USER32!GetWindowTextA` at `0x18004b15a`
- `USER32!GetWindowTextA` at `0x18004b15a`
- `USER32!SetWindowTextA` at `0x18004bd0f`
- `USER32!SetWindowTextA` at `0x18004bd0f`
- `USER32!SetCursor` at `0x18004b3bc`
- `USER32!SetCursor` at `0x18004ba98`
- `USER32!SetCursor` at `0x18004b3bc`
- `USER32!SetCursor` at `0x18004ba98`
- `USER32!EnableWindow` at `0x18004b133`
- `USER32!EnableWindow` at `0x18004b318`
- `USER32!EnableWindow` at `0x18004b133`
- `USER32!EnableWindow` at `0x18004b318`
- `USER32!SendMessageA` at `0x18004be78`
- `USER32!SendMessageA` at `0x18004be78`
- `USER32!GetDlgItem` at `0x18004b02b`
- `USER32!GetDlgItem` at `0x18004b094`
- `USER32!GetDlgItem` at `0x18004b0ae`
- `USER32!GetDlgItem` at `0x18004b0c7`
- `USER32!GetDlgItem` at `0x18004b0d6`
- `USER32!GetDlgItem` at `0x18004b0f5`
- `USER32!GetDlgItem` at `0x18004b10f`
- `USER32!GetDlgItem` at `0x18004b128`
- `USER32!GetDlgItem` at `0x18004b141`
- `USER32!GetDlgItem` at `0x18004b30d`
- `USER32!GetDlgItem` at `0x18004bcff`
- `USER32!GetDlgItem` at `0x18004be65`
- `USER32!GetDlgItem` at `0x18004be85`
- `USER32!GetDlgItem` at `0x18004be9d`
- `USER32!GetDlgItem` at `0x18004beac`
- `USER32!GetDlgItem` at `0x18004b02b`
- `USER32!GetDlgItem` at `0x18004b094`
- `USER32!GetDlgItem` at `0x18004b0ae`
- `USER32!GetDlgItem` at `0x18004b0c7`
- `USER32!GetDlgItem` at `0x18004b0d6`
- `USER32!GetDlgItem` at `0x18004b0f5`
- `USER32!GetDlgItem` at `0x18004b10f`
- `USER32!GetDlgItem` at `0x18004b128`
- `USER32!GetDlgItem` at `0x18004b141`
- `USER32!GetDlgItem` at `0x18004b30d`
- `USER32!GetDlgItem` at `0x18004bcff`
- `USER32!GetDlgItem` at `0x18004be65`
- `USER32!GetDlgItem` at `0x18004be85`
- `USER32!GetDlgItem` at `0x18004be9d`
- `USER32!GetDlgItem` at `0x18004beac`
- `USER32!MessageBoxW` at `0x18004b2f4`
- `USER32!MessageBoxW` at `0x18004b7b5`
- `USER32!MessageBoxW` at `0x18004b8e0`
- `USER32!MessageBoxW` at `0x18004ba79`
- `USER32!MessageBoxW` at `0x18004b2f4`
- `USER32!MessageBoxW` at `0x18004b7b5`
- `USER32!MessageBoxW` at `0x18004b8e0`
- `USER32!MessageBoxW` at `0x18004ba79`
- `USER32!GetFocus` at `0x18004b09d`
- `USER32!GetFocus` at `0x18004b0fe`
- `USER32!GetFocus` at `0x18004b09d`
- `USER32!GetFocus` at `0x18004b0fe`
- `USER32!PostMessageA` at `0x18004bf05`
- `USER32!PostMessageA` at `0x18004bf05`
- `USER32!LoadCursorA` at `0x18004b3b3`
- `USER32!LoadCursorA` at `0x18004b3b3`
- `SHLWAPI!StrCmpNIA` at `0x18004b1c5`
- `SHLWAPI!StrCmpNIA` at `0x18004b1c5`
- `MPR!WNetConnectionDialog` at `0x18004afff`
- `MPR!WNetConnectionDialog` at `0x18004afff`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CSampleDialog::SampleCopyProc(
        CSampleDialog *this,
        HWND a2,
        int a3,
        int a4,
        struct tagDRAWITEMSTRUCT *a5)
{
  int v7; // r8d
  int v8; // r8d
  int v9; // r8d
  HWND v10; // rax
  HWND v11; // rbx
  HWND v12; // rax
  HWND v13; // rbx
  HWND v14; // rax
  HWND v15; // rbx
  HWND v16; // rax
  HWND v17; // rax
  HWND v18; // rax
  const CHAR *v19; // rcx
  __int64 v20; // r15
  __int64 v21; // rax
  __int64 v22; // r8
  __int64 v23; // rax
  CHAR *v24; // r10
  const char *v25; // rbx
  __int64 v26; // rax
  LPSTR v27; // rax
  HINSTANCE v28; // rax
  HINSTANCE v29; // rax
  int v30; // r9d
  int v31; // eax
  HWND v32; // rax
  HINSTANCE v34; // rax
  HINSTANCE v35; // rax
  HCURSOR CursorA; // rax
  _DWORD *v37; // r14
  const char **j; // r10
  unsigned int v39; // r11d
  const char **v40; // r10
  __int64 v41; // rax
  const CHAR *k; // rax
  HANDLE v43; // rbx
  const char *v44; // rbx
  const CHAR *v45; // rax
  int v46; // eax
  int v47; // ecx
  HANDLE v48; // rbx
  HANDLE v49; // rax
  DWORD FileAttributesA; // eax
  HINSTANCE v51; // rax
  HINSTANCE v52; // rax
  int v53; // r9d
  int v54; // eax
  int v55; // r13d
  HINSTANCE v56; // rax
  HINSTANCE v57; // rax
  HINSTANCE v58; // rax
  HINSTANCE v59; // rax
  int v60; // eax
  HINSTANCE v61; // rax
  HINSTANCE v62; // rax
  HINSTANCE v63; // rax
  HINSTANCE v64; // rax
  int v65; // r9d
  int v66; // eax
  bool v67; // sf
  int v68; // ecx
  int v69; // eax
  int v70; // eax
  const char *v71; // rcx
  __int64 v72; // rax
  const char *v73; // r9
  INT_PTR v74; // rdx
  HWND v75; // rcx
  HINSTANCE v76; // rax
  HINSTANCE v77; // rax
  __int64 v78; // rax
  int v79; // ecx
  int v80; // eax
  HWND Window; // r13
  HINSTANCE ResourceInstance; // rax
  HINSTANCE v83; // rax
  HWND DlgItem; // rax
  int i; // ebx
  int v86; // eax
  unsigned __int64 v87; // rdx
  int v88; // r8d
  HWND v89; // rax
  HWND v90; // rax
  HWND v91; // rbx
  HWND v92; // rax
  int v93; // [rsp+40h] [rbp-C0h]
  const char **v94; // [rsp+48h] [rbp-B8h]
  char v95; // [rsp+50h] [rbp-B0h] BYREF
  __int16 v96; // [rsp+51h] [rbp-AFh]
  int v97; // [rsp+54h] [rbp-ACh]
  DWORD FileSize; // [rsp+58h] [rbp-A8h]
  BOOL v99; // [rsp+5Ch] [rbp-A4h]
  int v100; // [rsp+60h] [rbp-A0h]
  struct _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+68h] [rbp-98h] BYREF
  HANDLE hObject; // [rsp+80h] [rbp-80h]
  HCURSOR hCursor; // [rsp+88h] [rbp-78h]
  CHAR v104[32]; // [rsp+90h] [rbp-70h] BYREF
  WCHAR Caption[32]; // [rsp+B0h] [rbp-50h] BYREF
  CHAR v106[64]; // [rsp+F0h] [rbp-10h] BYREF
  WCHAR v107[16]; // [rsp+130h] [rbp+30h] BYREF
  CHAR szDst[256]; // [rsp+150h] [rbp+50h] BYREF
  CHAR FileName[512]; // [rsp+250h] [rbp+150h] BYREF
  CHAR ExistingFileName[256]; // [rsp+450h] [rbp+350h] BYREF
  CHAR v111[512]; // [rsp+550h] [rbp+450h] BYREF
  char v112[256]; // [rsp+750h] [rbp+650h] BYREF
  CHAR String[512]; // [rsp+850h] [rbp+750h] BYREF
  WCHAR Buffer[512]; // [rsp+A50h] [rbp+950h] BYREF
  WCHAR v115[1092]; // [rsp+E50h] [rbp+D50h] BYREF
  const CHAR *v116; // [rsp+16D8h] [rbp+15D8h]
  WCHAR v117[512]; // [rsp+16E0h] [rbp+15E0h] BYREF
  CHAR v118[512]; // [rsp+1AE0h] [rbp+19E0h] BYREF
  WCHAR Text[512]; // [rsp+1CE0h] [rbp+1BE0h] BYREF
  WCHAR v120[512]; // [rsp+20E0h] [rbp+1FE0h] BYREF

  *(_QWORD *)&SecurityAttributes.nLength = 24;
  *(_QWORD *)&SecurityAttributes.bInheritHandle = 0;
  SecurityAttributes.lpSecurityDescriptor = 0;
  v7 = a3 - 16;
  if ( !v7 )
  {
    dword_18008C4C4 = 0;
    PostMessageA(a2, 0x111u, 2u, 0);
    return 1;
  }
  v8 = v7 - 27;
  if ( v8 )
  {
    v9 = v8 - 229;
    if ( !v9 )
    {
      if ( dword_18008C4C4 )
        return 1;
      CSampleDialog::SetAllFonts(this, a2);
      SendDlgItemMessageA(a2, 306, 0x30u, *(_QWORD *)(*((_QWORD *)this + 615) + 1216LL), 0);
      Window = GetWindow(a2, 4u);
      if ( *((_DWORD *)this + 551) )
      {
        if ( g_bWinNT5 )
        {
          ResourceInstance = CHtmlHelpModule::GetResourceInstance((CHtmlHelpModule *)&_Module);
          LoadStringW(ResourceInstance, 0x194u, Buffer, 512);
          SetDlgItemTextW(a2, 311, Buffer);
        }
        else
        {
          v83 = CHtmlHelpModule::GetResourceInstance((CHtmlHelpModule *)&_Module);
          LoadStringA(v83, 0x194u, v111, 512);
          SetDlgItemTextA(a2, 311, v111);
        }
      }
      DlgItem = GetDlgItem(a2, 304);
      SetWindowTextA(DlgItem, (LPCSTR)this + 1688);
      for ( i = 0; ; ++i )
      {
        if ( *((_DWORD *)this + 550) )
          goto LABEL_136;
        v86 = SendDlgItemMessageA(Window, 201, 0x187u, i, 0);
        if ( v86 == -1 )
          goto LABEL_141;
        if ( v86 )
        {
LABEL_136:
          if ( (unsigned int)SendDlgItemMessageA(Window, 201, 0x18Au, i, (LPARAM)szDst) >= 0x100
            || SendDlgItemMessageA(Window, 201, 0x189u, i, (LPARAM)szDst) == -1 )
          {
LABEL_141:
            if ( !*((_BYTE *)this + 1164) )
              GetSamplesDir((char *)this + 1164, v87);
            CharToOemA((LPCSTR)this + 1164, (LPSTR)this + 108);
            if ( !*((_DWORD *)this + 419) )
            {
              CatPath((char *)this + 108, (const char *)this + 1688, 0x200u);
              *((_DWORD *)this + 419) = 1;
            }
            v89 = GetDlgItem(a2, 305);
            SendMessageA(v89, 0x194u, 0, 0);
            v90 = GetDlgItem(a2, 302);
            CSampleDialog::FillDrives(this, v90);
            v91 = GetDlgItem(a2, 304);
            v92 = GetDlgItem(a2, 305);
            CSampleDialog::FillDirs(this, v92, v91);
            dword_18008C4C4 = 1;
            return 1;
          }
          if ( i )
          {
            ECSelect(a2, v87, v88);
            SendDlgItemMessageA(a2, 306, 0xC2u, 0, (LPARAM)" ");
          }
          ECSelect(a2, v87, v88);
          SendDlgItemMessageA(a2, 306, 0xC2u, 0, (LPARAM)szDst);
        }
      }
    }
    if ( v9 != 1 )
      return 0;
    if ( (unsigned __int16)a4 != 1 )
    {
      if ( (unsigned __int16)a4 == 2 )
      {
        *((_DWORD *)this + 550) = 0;
        EndDialog(a2, 0);
        dword_18008C4C4 = 0;
        return 1;
      }
      if ( (unsigned __int16)a4 != 302 )
      {
        if ( (unsigned __int16)a4 != 305 )
        {
          if ( (unsigned __int16)a4 == 308 && !WNetConnectionDialog(a2, 1u) )
          {
            SendDlgItemMessageA(a2, 302, 0x14Bu, 0, 0);
            v10 = GetDlgItem(a2, 302);
            CSampleDialog::FillDrives(this, v10);
          }
          return 1;
        }
        if ( HIWORD(a4) != 2 )
          return 1;
        goto LABEL_21;
      }
      if ( HIWORD(a4) != 1 )
        return 1;
LABEL_18:
      v12 = GetDlgItem(a2, 302);
      CSampleDialog::SelectDrive(this, v12);
LABEL_19:
      v13 = GetDlgItem(a2, 304);
      v14 = GetDlgItem(a2, 305);
      CSampleDialog::FillDirs(this, v14, v13);
      return 1;
    }
    dword_18008C4C4 = 0;
    v11 = GetDlgItem(a2, 302);
    if ( GetFocus() == v11 )
      goto LABEL_18;
    v15 = GetDlgItem(a2, 305);
    if ( GetFocus() == v15 )
    {
LABEL_21:
      v16 = GetDlgItem(a2, 305);
      CSampleDialog::SelectDirectory(this, v16);
      goto LABEL_19;
    }
    v17 = GetDlgItem(a2, 1);
    EnableWindow(v17, 0);
    v18 = GetDlgItem(a2, 304);
    GetWindowTextA(v18, String, 512);
    v19 = (char *)this + 620;
    v20 = -1;
    v21 = -1;
    do
      ++v21;
    while ( v19[v21] );
    if ( (unsigned int)(v21 + 1) > 0x100 )
      return 0;
    OemToCharBuffA(v19, szDst, v21 + 1);
    v22 = -1;
    do
      ++v22;
    while ( String[v22] );
    v23 = -1;
    do
      ++v23;
    while ( szDst[v23] );
    if ( (int)v22 > (int)v23 || StrCmpNIA(String, szDst, v22) )
    {
      StringCbCopyA((char *)this + 108, 0x200u, String);
    }
    else
    {
      StringCchCopyA(FileName, 0x200u, szDst);
      v24 = szDst;
    }
    v25 = (char *)this + 1164;
    StringCbCopyA((char *)this + 1164, 0x200u, v24);
    v26 = -1;
    do
      ++v26;
    while ( v25[v26] );
    v27 = CharPrevA((LPCSTR)this + 1164, (LPCSTR)this + v26 + 1164);
    if ( *v27 == 92 )
      *v27 = 0;
    if ( !(unsigned int)IsDirectory((const char *)this + 1164) )
    {
      if ( g_bWinNT5 )
      {
        v28 = CHtmlHelpModule::GetResourceInstance((CHtmlHelpModule *)&_Module);
        LoadStringW(v28, 0x193u, Buffer, 512);
        v29 = CHtmlHelpModule::GetResourceInstance((CHtmlHelpModule *)&_Module);
        LoadStringW(v29, 0x192u, Caption, 32);
        HHMultiByteToWideChar(0, 0, String, v30, v115, 260);
        StringCchPrintfW(Text, 0x200u, Buffer, v115);
        v31 = MessageBoxW(a2, Text, Caption, 1u);
      }
      else
      {
        v34 = CHtmlHelpModule::GetResourceInstance((CHtmlHelpModule *)&_Module);
        LoadStringA(v34, 0x193u, v111, 512);
        v35 = CHtmlHelpModule::GetResourceInstance((CHtmlHelpModule *)&_Module);
        LoadStringA(v35, 0x192u, v104, 32);
        StringCchPrintfA(v118, 0x200u, v111, String);
        v31 = MessageBoxA(a2, v118, v104, 1u);
      }
      if ( v31 == 2 )
      {
        v32 = GetDlgItem(a2, 1);
        EnableWindow(v32, 1);
        return 0;
      }
    }
    v93 = 0;
    v97 = 0;
    v100 = 0;
    CursorA = LoadCursorA(0, (LPCSTR)0x7F02);
    hCursor = SetCursor(CursorA);
    v94 = (const char **)*((_QWORD *)this + 210);
    v37 = (_DWORD *)((char *)this + 2200);
    for ( j = v94; ; v94 = j )
    {
      if ( !j )
        goto LABEL_104;
      v37 = (_DWORD *)((char *)this + 2200);
      if ( *((_DWORD *)this + 550) || *((_DWORD *)j + 3) )
        break;
LABEL_93:
      j = (const char **)j[3];
    }
    StringCchCopyA(v112, 0x100u, (const char *)this + 4292);
    CatPath(v112, *v40, v39);
    StringCchCopyA(ExistingFileName, 0x100u, v112);
    StringCchCopyA(FileName, 0x200u, v25);
    CatPath(FileName, *v94, 0x200u);
    StringCchCopyA(szDst, 0x100u, FileName);
    v41 = -1;
    do
      ++v41;
    while ( szDst[v41] );
    for ( k = &szDst[v41]; *k != 47 && k > szDst && *k != 92; k = CharPrevA(szDst, k) )
      ;
    *k = 0;
    if ( !HHCreatePath(szDst) )
    {
      if ( *((_DWORD *)this + 551) )
        BackSlashToSlash(ExistingFileName);
      while ( 1 )
      {
        while ( 1 )
        {
          v43 = CreateFileA(FileName, 0x80000000, 0, &SecurityAttributes, 3u, 0x80u, 0);
          CloseHandle(v43);
          if ( v43 != (HANDLE)-1LL && !v97 )
          {
            v44 = *v94;
            CDlg::CDlg((CDlg *)v115, a2, 0x7EDu);
            *(_QWORD *)v115 = &COverwriteDlg::`vftable';
            v45 = Class;
            if ( v44 )
              v45 = v44;
            v116 = v45;
            v46 = CDlg::DoModal((LPARAM)v115);
            if ( v46 == 7 )
            {
              CDlg::~CDlg((CDlg *)v115);
LABEL_91:
              v25 = (char *)this + 1164;
LABEL_92:
              j = v94;
              goto LABEL_93;
            }
            if ( !v46 )
            {
              v100 = 1;
              CDlg::~CDlg((CDlg *)v115);
              v25 = (char *)this + 1164;
              goto LABEL_104;
            }
            v47 = v97;
            if ( v46 == 4 )
              v47 = 1;
            v97 = v47;
            CDlg::~CDlg((CDlg *)v115);
          }
          if ( *((_DWORD *)this + 551) )
            DownloadURL(ExistingFileName, FileName);
          else
            CopyFileA(ExistingFileName, FileName, 0);
          v48 = CreateFileA(FileName, 0x80000000, 0, &SecurityAttributes, 3u, 0x80u, 0);
          FileSize = 0;
          v99 = 0;
          v96 = 58;
          v95 = FileName[0];
          if ( v48 )
            FileSize = GetFileSize(v48, 0);
          CloseHandle(v48);
          if ( !*((_DWORD *)this + 551) )
          {
            v49 = CreateFileA(ExistingFileName, 0x80000000, 0, &SecurityAttributes, 3u, 0x80u, 0);
            hObject = v49;
            if ( v49 )
            {
              v99 = GetFileSize(v49, 0) == 0;
              CloseHandle(hObject);
            }
          }
          FileAttributesA = GetFileAttributesA(FileName);
          if ( FileAttributesA != -1 )
            SetFileAttributesA(FileName, FileAttributesA & 0xFFFFFFFE);
          if ( v48 == (HANDLE)-1LL )
            break;
          if ( FileSize || v99 || (int)GetFreeDiskSpaceInKB(FileName) >= 1024 )
            goto LABEL_91;
          if ( g_bWinNT5 )
          {
            DeleteFileA(FileName);
            v51 = CHtmlHelpModule::GetResourceInstance((CHtmlHelpModule *)&_Module);
            LoadStringW(v51, 0x1A1u, v115, 128);
            v52 = CHtmlHelpModule::GetResourceInstance((CHtmlHelpModule *)&_Module);
            LoadStringW(v52, 0x192u, Caption, 32);
            HHMultiByteToWideChar(0, 0, &v95, v53, v107, 10);
            StringCbPrintfW(Buffer, 0x400u, v115, v107);
            v54 = MessageBoxW(0, Buffer, Caption, 4u);
          }
          else
          {
            DeleteFileA(FileName);
            v56 = CHtmlHelpModule::GetResourceInstance((CHtmlHelpModule *)&_Module);
            LoadStringA(v56, 0x1A1u, v106, 64);
            v57 = CHtmlHelpModule::GetResourceInstance((CHtmlHelpModule *)&_Module);
            LoadStringA(v57, 0x192u, v104, 32);
            StringCchPrintfA(v111, 0x200u, v106, &v95);
            v54 = MessageBoxA(0, v111, v104, 4u);
          }
          if ( v54 != 6 )
          {
            v55 = 1;
            v25 = (char *)this + 1164;
            goto LABEL_105;
          }
        }
        if ( GetLastError() != 32 )
          break;
        if ( g_bWinNT5 )
        {
          v58 = CHtmlHelpModule::GetResourceInstance((CHtmlHelpModule *)&_Module);
          LoadStringW(v58, 0x19Cu, v115, 128);
          v59 = CHtmlHelpModule::GetResourceInstance((CHtmlHelpModule *)&_Module);
          LoadStringW(v59, 0x192u, Caption, 32);
          StringCbPrintfW(Buffer, 0x400u, v115, v117);
          v60 = MessageBoxW(0, Buffer, Caption, 4u);
        }
        else
        {
          v61 = CHtmlHelpModule::GetResourceInstance((CHtmlHelpModule *)&_Module);
          LoadStringA(v61, 0x19Cu, v106, 64);
          v62 = CHtmlHelpModule::GetResourceInstance((CHtmlHelpModule *)&_Module);
          LoadStringA(v62, 0x192u, v104, 32);
          StringCchPrintfA(v111, 0x200u, v106, FileName);
          v60 = MessageBoxA(0, v111, v104, 4u);
        }
        if ( v60 != 6 )
        {
          v93 = 1;
          goto LABEL_91;
        }
      }
      if ( g_bWinNT5 )
      {
        v63 = CHtmlHelpModule::GetResourceInstance((CHtmlHelpModule *)&_Module);
        LoadStringW(v63, 0x19Du, v115, 128);
        v64 = CHtmlHelpModule::GetResourceInstance((CHtmlHelpModule *)&_Module);
        LoadStringW(v64, 0x192u, Caption, 32);
        HHMultiByteToWideChar(0, 0, FileName, v65, v117, 512);
        v117[511] = 0;
        v66 = lstrlenW(v115);
        v67 = 512 - v66 < 0;
        v68 = 512 - v66;
        v69 = 0;
        if ( !v67 )
          v69 = v68;
        if ( (unsigned __int64)v69 < 0x200 )
        {
          if ( (unsigned __int64)(2LL * v69) >= 0x400 )
            _report_rangecheckfailure();
          v117[v69] = 0;
        }
        v93 = 1;
        StringCbPrintfW(Buffer, 0x400u, v115, v117);
        v70 = MessageBoxW(0, Buffer, Caption, 4u);
      }
      else
      {
        v76 = CHtmlHelpModule::GetResourceInstance((CHtmlHelpModule *)&_Module);
        LoadStringA(v76, 0x19Du, v106, 64);
        v77 = CHtmlHelpModule::GetResourceInstance((CHtmlHelpModule *)&_Module);
        LoadStringA(v77, 0x192u, v104, 32);
        v78 = -1;
        do
          ++v78;
        while ( v106[v78] );
        v67 = 512 - (int)v78 < 0;
        v79 = 512 - v78;
        v80 = 0;
        if ( !v67 )
          v80 = v79;
        if ( (unsigned __int64)v80 < 0x200 )
          FileName[v80] = 0;
        v93 = 1;
        StringCchPrintfA(v111, 0x200u, v106, FileName);
        v70 = MessageBoxA(0, v111, v104, 4u);
      }
      v25 = (char *)this + 1164;
      if ( v70 != 7 )
        goto LABEL_92;
LABEL_104:
      v55 = v93;
      goto LABEL_105;
    }
    v55 = 1;
    *v25 = 0;
LABEL_105:
    SetCursor(hCursor);
    *v37 = 0;
    v71 = (char *)this + 1688;
    v72 = -1;
    do
      ++v72;
    while ( v25[v72] );
    do
      ++v20;
    while ( v71[v20] );
    v73 = (char *)this + v72 - v20 + 1164;
    if ( !strcmp(v73, v71) && *(v73 - 1) == 92 )
      *v73 = 0;
    if ( v55 )
    {
      *v25 = 0;
      v74 = 2;
      v75 = a2;
    }
    else
    {
      HHMultiByteToWideChar(0, 0, v25, (int)v73, v120, 512);
      v75 = a2;
      v74 = 3;
      if ( !v100 )
        v74 = 1;
    }
    EndDialog(v75, v74);
  }
  else if ( a5->CtlID == 305 )
  {
    CSampleDialog::DirectoryDrawItem(this, a5);
  }
  else if ( a5->CtlID == 302 )
  {
    CSampleDialog::DriveDrawItem(this, a5);
  }
  return 1;
}

```

## disassembly

```asm
0x18004af3c  mov     [rsp-8+arg_10], rbx
0x18004af41  push    rbp
0x18004af42  push    rsi
0x18004af43  push    rdi
0x18004af44  push    r12
0x18004af46  push    r13
0x18004af48  push    r14
0x18004af4a  push    r15
0x18004af4c  lea     rbp, [rsp-23F0h]
0x18004af54  mov     eax, 24F0h
0x18004af59  call    _alloca_probe
0x18004af5e  sub     rsp, rax
0x18004af61  mov     rax, cs:__security_cookie
0x18004af68  xor     rax, rsp
0x18004af6b  mov     [rbp+2420h+var_40], rax
0x18004af72  mov     rdi, rdx
0x18004af75  mov     rsi, rcx
0x18004af78  mov     rdx, [rbp+2420h+arg_20]; struct tagDRAWITEMSTRUCT *
0x18004af7f  xor     r13d, r13d
0x18004af82  mov     qword ptr [rsp+2520h+SecurityAttributes.nLength], 18h
0x18004af8b  mov     qword ptr [rsp+2520h+SecurityAttributes.bInheritHandle], r13
0x18004af90  mov     [rsp+2520h+SecurityAttributes.lpSecurityDescriptor], r13
0x18004af95  lea     r12d, [r13+1]
0x18004af99  sub     r8d, 10h
0x18004af9d  jz      loc_18004BEEF
0x18004afa3  sub     r8d, 1Bh
0x18004afa7  jz      loc_18004BEC9
0x18004afad  sub     r8d, 0E5h
0x18004afb4  jz      loc_18004BC2A
0x18004afba  cmp     r8d, r12d
0x18004afbd  jnz     loc_18004B31E
0x18004afc3  movzx   ecx, r9w
0x18004afc7  mov     r14d, 131h
0x18004afcd  lea     r15d, [r14-3]
0x18004afd1  sub     ecx, r12d
0x18004afd4  jz      loc_18004B087
0x18004afda  sub     ecx, r12d
0x18004afdd  jz      loc_18004B069
0x18004afe3  sub     ecx, 12Ch
0x18004afe9  jz      short loc_18004B05A
0x18004afeb  sub     ecx, 3
0x18004afee  jz      short loc_18004B041
0x18004aff0  cmp     ecx, 3
0x18004aff3  jnz     loc_18004BF0B
0x18004aff9  mov     edx, r12d; dwType
0x18004affc  mov     rcx, rdi; hwnd
0x18004afff  call    cs:__imp_WNetConnectionDialog
0x18004b005  test    eax, eax
0x18004b007  jnz     loc_18004BF0B
0x18004b00d  mov     [rsp+2520h+lParam], r13; lParam
0x18004b012  xor     r9d, r9d; wParam
0x18004b015  lea     r8d, [r14+1Ah]; Msg
0x18004b019  mov     edx, r15d; nIDDlgItem
0x18004b01c  mov     rcx, rdi; hDlg
0x18004b01f  call    cs:__imp_SendDlgItemMessageA
0x18004b025  mov     edx, r15d; nIDDlgItem
0x18004b028  mov     rcx, rdi; hDlg
0x18004b02b  call    cs:__imp_GetDlgItem
0x18004b031  mov     rdx, rax; HWND
0x18004b034  mov     rcx, rsi; this
0x18004b037  call    ?FillDrives@CSampleDialog@@QEAAXPEAUHWND__@@@Z; CSampleDialog::FillDrives(HWND__ *)
0x18004b03c  jmp     loc_18004BF0B
0x18004b041  shr     r9, 10h
0x18004b045  mov     r8d, 2
0x18004b04b  cmp     r9w, r8w
0x18004b04f  jz      loc_18004B109
0x18004b055  jmp     loc_18004BF0B
0x18004b05a  shr     r9, 10h
0x18004b05e  cmp     r9w, r12w
0x18004b062  jz      short loc_18004B0A8
0x18004b064  jmp     loc_18004BF0B
0x18004b069  mov     [rsi+898h], r13d
0x18004b070  xor     edx, edx; nResult
0x18004b072  mov     rcx, rdi; hDlg
0x18004b075  call    cs:__imp_EndDialog
0x18004b07b  mov     cs:dword_18008C4C4, r13d
0x18004b082  jmp     loc_18004BF0B
0x18004b087  mov     cs:dword_18008C4C4, r13d
0x18004b08e  mov     edx, r15d; nIDDlgItem
0x18004b091  mov     rcx, rdi; hDlg
0x18004b094  call    cs:__imp_GetDlgItem
0x18004b09a  mov     rbx, rax
0x18004b09d  call    cs:__imp_GetFocus
0x18004b0a3  cmp     rax, rbx
0x18004b0a6  jnz     short loc_18004B0EF
0x18004b0a8  mov     edx, r15d; nIDDlgItem
0x18004b0ab  mov     rcx, rdi; hDlg
0x18004b0ae  call    cs:__imp_GetDlgItem
0x18004b0b4  mov     rdx, rax; HWND
0x18004b0b7  mov     rcx, rsi; this
0x18004b0ba  call    ?SelectDrive@CSampleDialog@@QEAAXPEAUHWND__@@@Z; CSampleDialog::SelectDrive(HWND__ *)
0x18004b0bf  mov     edx, 130h; nIDDlgItem
0x18004b0c4  mov     rcx, rdi; hDlg
0x18004b0c7  call    cs:__imp_GetDlgItem
0x18004b0cd  mov     rbx, rax
0x18004b0d0  mov     edx, r14d; nIDDlgItem
0x18004b0d3  mov     rcx, rdi; hDlg
0x18004b0d6  call    cs:__imp_GetDlgItem
0x18004b0dc  mov     r8, rbx; HWND
0x18004b0df  mov     rdx, rax; HWND
0x18004b0e2  mov     rcx, rsi; this
0x18004b0e5  call    ?FillDirs@CSampleDialog@@QEAAXPEAUHWND__@@0@Z; CSampleDialog::FillDirs(HWND__ *,HWND__ *)
0x18004b0ea  jmp     loc_18004BF0B
0x18004b0ef  mov     edx, r14d; nIDDlgItem
0x18004b0f2  mov     rcx, rdi; hDlg
0x18004b0f5  call    cs:__imp_GetDlgItem
0x18004b0fb  mov     rbx, rax
0x18004b0fe  call    cs:__imp_GetFocus
0x18004b104  cmp     rax, rbx
0x18004b107  jnz     short loc_18004B122
0x18004b109  mov     edx, r14d; nIDDlgItem
0x18004b10c  mov     rcx, rdi; hDlg
0x18004b10f  call    cs:__imp_GetDlgItem
0x18004b115  mov     rdx, rax; HWND
0x18004b118  mov     rcx, rsi; this
0x18004b11b  call    ?SelectDirectory@CSampleDialog@@QEAAXPEAUHWND__@@@Z; CSampleDialog::SelectDirectory(HWND__ *)
0x18004b120  jmp     short loc_18004B0BF
0x18004b122  mov     edx, r12d; nIDDlgItem
0x18004b125  mov     rcx, rdi; hDlg
0x18004b128  call    cs:__imp_GetDlgItem
0x18004b12e  mov     rcx, rax; hWnd
0x18004b131  xor     edx, edx; bEnable
0x18004b133  call    cs:__imp_EnableWindow
0x18004b139  mov     edx, 130h; nIDDlgItem
0x18004b13e  mov     rcx, rdi; hDlg
0x18004b141  call    cs:__imp_GetDlgItem
0x18004b147  mov     rcx, rax; hWnd
0x18004b14a  mov     r12d, 200h
0x18004b150  mov     r8d, r12d; nMaxCount
0x18004b153  lea     rdx, [rbp+2420h+String]; lpString
0x18004b15a  call    cs:__imp_GetWindowTextA
0x18004b160  lea     rcx, [rsi+26Ch]; lpszSrc
0x18004b167  or      r15, 0FFFFFFFFFFFFFFFFh
0x18004b16b  mov     rax, r15
0x18004b16e  inc     rax
0x18004b171  cmp     [rcx+rax], r13b
0x18004b175  jnz     short loc_18004B16E
0x18004b177  lea     r8d, [rax+1]; cchDstLength
0x18004b17b  cmp     r8d, 100h
0x18004b182  ja      loc_18004B31E
0x18004b188  lea     rdx, [rbp+2420h+szDst]; lpszDst
0x18004b18c  call    cs:__imp_OemToCharBuffA
0x18004b192  lea     rax, [rbp+2420h+String]
0x18004b199  mov     r8, r15
0x18004b19c  inc     r8; nChar
0x18004b19f  cmp     [rax+r8], r13b
0x18004b1a3  jnz     short loc_18004B19C
0x18004b1a5  lea     rcx, [rbp+2420h+szDst]
0x18004b1a9  mov     rax, r15
0x18004b1ac  inc     rax
0x18004b1af  cmp     [rcx+rax], r13b
0x18004b1b3  jnz     short loc_18004B1AC
0x18004b1b5  cmp     r8d, eax
0x18004b1b8  jg      short loc_18004B1E8
0x18004b1ba  lea     rdx, [rbp+2420h+szDst]; psz2
0x18004b1be  lea     rcx, [rbp+2420h+String]; psz1
0x18004b1c5  call    cs:__imp_StrCmpNIA
0x18004b1cb  test    eax, eax
0x18004b1cd  jnz     short loc_18004B1E8
0x18004b1cf  lea     r8, [rbp+2420h+szDst]; char *
0x18004b1d3  mov     rdx, r12; unsigned __int64
0x18004b1d6  lea     rcx, [rbp+2420h+FileName]; char *
0x18004b1dd  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x18004b1e2  lea     r10, [rbp+2420h+szDst]
0x18004b1e6  jmp     short loc_18004B1FE
0x18004b1e8  lea     r10, [rsi+6Ch]
0x18004b1ec  lea     r8, [rbp+2420h+String]; char *
0x18004b1f3  mov     rdx, r12; unsigned __int64
0x18004b1f6  mov     rcx, r10; char *
0x18004b1f9  call    ?StringCbCopyA@@YAJPEAD_KPEBD@Z; StringCbCopyA(char *,unsigned __int64,char const *)
0x18004b1fe  lea     rbx, [rsi+48Ch]
0x18004b205  mov     r8, r10; char *
0x18004b208  mov     rdx, r12; unsigned __int64
0x18004b20b  mov     rcx, rbx; char *
0x18004b20e  call    ?StringCbCopyA@@YAJPEAD_KPEBD@Z; StringCbCopyA(char *,unsigned __int64,char const *)
0x18004b213  mov     rax, r15
0x18004b216  inc     rax
0x18004b219  cmp     [rbx+rax], r13b
0x18004b21d  jnz     short loc_18004B216
0x18004b21f  lea     rdx, [rsi+48Ch]
0x18004b226  add     rdx, rax; lpszCurrent
0x18004b229  mov     rcx, rbx; lpszStart
0x18004b22c  call    cs:__imp_CharPrevA
0x18004b232  cmp     byte ptr [rax], 5Ch ; '\'
0x18004b235  jnz     short loc_18004B23A
0x18004b237  mov     [rax], r13b
0x18004b23a  mov     rcx, rbx; char *
0x18004b23d  call    ?IsDirectory@@YAHPEBD@Z; IsDirectory(char const *)
0x18004b242  mov     r14d, 2
0x18004b248  lea     r13, ?_Module@@3VCHtmlHelpModule@@A; CHtmlHelpModule _Module
0x18004b24f  test    eax, eax
0x18004b251  jnz     loc_18004B39E
0x18004b257  mov     rcx, r13; this
0x18004b25a  cmp     cs:?g_bWinNT5@@3HA, eax; int g_bWinNT5
0x18004b260  jz      loc_18004B325
0x18004b266  call    ?GetResourceInstance@CHtmlHelpModule@@QEAAPEAUHINSTANCE__@@XZ; CHtmlHelpModule::GetResourceInstance(void)
0x18004b26b  mov     rcx, rax; hInstance
0x18004b26e  mov     r9d, r12d; cchBufferMax
0x18004b271  lea     r8, [rbp+2420h+Buffer]; lpBuffer
0x18004b278  mov     edx, 193h; uID
0x18004b27d  call    cs:__imp_LoadStringW
0x18004b283  mov     rcx, r13; this
0x18004b286  call    ?GetResourceInstance@CHtmlHelpModule@@QEAAPEAUHINSTANCE__@@XZ; CHtmlHelpModule::GetResourceInstance(void)
0x18004b28b  mov     rcx, rax; hInstance
0x18004b28e  lea     r9d, [r14+1Eh]; cchBufferMax
0x18004b292  lea     r8, [rbp+2420h+Caption]; lpBuffer
0x18004b296  mov     edx, 192h; uID
0x18004b29b  call    cs:__imp_LoadStringW
0x18004b2a1  mov     [rsp+2520h+dwFlagsAndAttributes], 104h; int
0x18004b2a9  lea     rax, [rbp+2420h+var_16D0]
0x18004b2b0  mov     [rsp+2520h+lParam], rax; LPWSTR
0x18004b2b5  lea     r8, [rbp+2420h+String]; char *
0x18004b2bc  xor     edx, edx; unsigned int
0x18004b2be  xor     ecx, ecx; unsigned int
0x18004b2c0  call    ?HHMultiByteToWideChar@@YAHIKPEBDHPEAGH@Z; HHMultiByteToWideChar(uint,ulong,char const *,int,ushort *,int)
0x18004b2c5  lea     r9, [rbp+2420h+var_16D0]
0x18004b2cc  lea     r8, [rbp+2420h+Buffer]; unsigned __int16 *
0x18004b2d3  mov     rdx, r12; unsigned __int64
0x18004b2d6  lea     rcx, [rbp+2420h+Text]; unsigned __int16 *
0x18004b2dd  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004b2e2  lea     r9d, [r14-1]; uType
0x18004b2e6  lea     r8, [rbp+2420h+Caption]; lpCaption
0x18004b2ea  lea     rdx, [rbp+2420h+Text]; lpText
0x18004b2f1  mov     rcx, rdi; hWnd
0x18004b2f4  call    cs:__imp_MessageBoxW
0x18004b2fa  cmp     eax, r14d
0x18004b2fd  jnz     loc_18004B39E
0x18004b303  mov     ebx, 1
0x18004b308  mov     edx, ebx; nIDDlgItem
0x18004b30a  mov     rcx, rdi; hDlg
0x18004b30d  call    cs:__imp_GetDlgItem
0x18004b313  mov     rcx, rax; hWnd
0x18004b316  mov     edx, ebx; bEnable
0x18004b318  call    cs:__imp_EnableWindow
0x18004b31e  xor     eax, eax
0x18004b320  jmp     loc_18004BF0E
0x18004b325  call    ?GetResourceInstance@CHtmlHelpModule@@QEAAPEAUHINSTANCE__@@XZ; CHtmlHelpModule::GetResourceInstance(void)
0x18004b32a  mov     rcx, rax; hInstance
0x18004b32d  mov     r9d, r12d; cchBufferMax
0x18004b330  lea     r8, [rbp+2420h+var_1FD0]; lpBuffer
0x18004b337  mov     edx, 193h; uID
0x18004b33c  call    cs:__imp_LoadStringA
0x18004b342  mov     rcx, r13; this
0x18004b345  call    ?GetResourceInstance@CHtmlHelpModule@@QEAAPEAUHINSTANCE__@@XZ; CHtmlHelpModule::GetResourceInstance(void)
0x18004b34a  mov     rcx, rax; hInstance
0x18004b34d  mov     r9d, 20h ; ' '; cchBufferMax
0x18004b353  lea     r8, [rbp+2420h+var_2490]; lpBuffer
0x18004b357  mov     edx, 192h; uID
0x18004b35c  call    cs:__imp_LoadStringA
0x18004b362  lea     r9, [rbp+2420h+String]
0x18004b369  lea     r8, [rbp+2420h+var_1FD0]; char *
0x18004b370  mov     rdx, r12; unsigned __int64
0x18004b373  lea     rcx, [rbp+2420h+var_A40]; char *
0x18004b37a  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x18004b37f  mov     r9d, 1; uType
0x18004b385  lea     r8, [rbp+2420h+var_2490]; lpCaption
0x18004b389  lea     rdx, [rbp+2420h+var_A40]; lpText
0x18004b390  mov     rcx, rdi; hWnd
0x18004b393  call    cs:__imp_MessageBoxA
0x18004b399  jmp     loc_18004B2FA
0x18004b39e  xor     eax, eax
0x18004b3a0  mov     [rsp+2520h+var_24E0], eax
0x18004b3a4  mov     [rsp+2520h+var_24CC], eax
0x18004b3a8  mov     [rsp+2520h+var_24C0], eax
0x18004b3ac  mov     edx, 7F02h; lpCursorName
0x18004b3b1  xor     ecx, ecx; hInstance
0x18004b3b3  call    cs:__imp_LoadCursorA
0x18004b3b9  mov     rcx, rax; hCursor
0x18004b3bc  call    cs:__imp_SetCursor
0x18004b3c2  mov     [rbp+2420h+hCursor], rax
0x18004b3c6  mov     r14, [rsi+690h]
0x18004b3cd  mov     [rsp+2520h+var_24D8], r14
0x18004b3d2  lea     r14, [rsi+898h]
0x18004b3d9  mov     r10, [rsp+2520h+var_24D8]
0x18004b3de  test    r10, r10
0x18004b3e1  jz      loc_18004BA8F
0x18004b3e7  lea     r14, [rsi+898h]
0x18004b3ee  cmp     dword ptr [r14], 0
0x18004b3f2  jnz     short loc_18004B3FF
0x18004b3f4  cmp     dword ptr [r10+0Ch], 0
0x18004b3f9  jz      loc_18004B903
0x18004b3ff  lea     r8, [rsi+10C4h]; char *
0x18004b406  mov     r11d, 100h
0x18004b40c  mov     edx, r11d; unsigned __int64
0x18004b40f  lea     rcx, [rbp+2420h+var_1DD0]; char *
0x18004b416  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x18004b41b  mov     r8d, r11d; unsigned __int64
0x18004b41e  mov     rdx, [r10]; char *
0x18004b421  lea     rcx, [rbp+2420h+var_1DD0]; char *
0x18004b428  call    ?CatPath@@YAPEADPEADPEBD_K@Z; CatPath(char *,char const *,unsigned __int64)
0x18004b42d  lea     r8, [rbp+2420h+var_1DD0]; char *
0x18004b434  mov     edx, 100h; unsigned __int64
0x18004b439  lea     rcx, [rbp+2420h+ExistingFileName]; char *
0x18004b440  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x18004b445  mov     r8, rbx; char *
0x18004b448  mov     rdx, r12; unsigned __int64
0x18004b44b  lea     rcx, [rbp+2420h+FileName]; char *
0x18004b452  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x18004b457  mov     r8, r12; unsigned __int64
0x18004b45a  mov     rax, [rsp+2520h+var_24D8]
  ... truncated ...
```
