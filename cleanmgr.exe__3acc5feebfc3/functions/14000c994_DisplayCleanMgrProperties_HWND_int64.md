# DisplayCleanMgrProperties(HWND__ *,__int64)

- ea: `0x14000c994`
- end: `0x14000cb1c`
- name: `?DisplayCleanMgrProperties@@YAKPEAUHWND__@@_J@Z`
- size: `392`
- prototype: `__int64 __fastcall(HWND, LPARAM)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140009d34`

## callees

- `0x140003390`
- `0x14000c994`
- `0x14000eaa8`
- `0x140016d7c`

## import_xrefs

- `COMCTL32!PropertySheetW` at `0x14000caf3`
- `COMCTL32!PropertySheetW` at `0x14000caf3`
- `COMCTL32!CreatePropertySheetPageW` at `0x14000ca2d`
- `COMCTL32!CreatePropertySheetPageW` at `0x14000ca72`
- `COMCTL32!CreatePropertySheetPageW` at `0x14000ca2d`
- `COMCTL32!CreatePropertySheetPageW` at `0x14000ca72`
- `SHELL32!__imp_IsUserAnAdmin` at `0x14000ca41`
- `SHELL32!__imp_IsUserAnAdmin` at `0x14000ca41`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14000caff`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14000caff`

## pseudocode

```c
__int64 __fastcall DisplayCleanMgrProperties(HWND a1, LPARAM a2)
{
  int v4; // eax
  int v5; // edi
  HPROPSHEETPAGE v6; // rax
  bool v7; // zf
  const WCHAR *v8; // rax
  WCHAR *v9; // rdi
  unsigned int v10; // ebx
  __int128 v11; // [rsp+20h] [rbp-89h] BYREF
  PROPSHEETHEADERW_V2 v12; // [rsp+30h] [rbp-79h] BYREF
  PROPSHEETPAGEW_V4 constPropSheetPagePointer; // [rsp+90h] [rbp-19h] BYREF

  memset_0(&constPropSheetPagePointer, 0, sizeof(constPropSheetPagePointer));
  memset_0(&v12, 0, sizeof(v12));
  v11 = 0;
  if ( !a2 )
    return 0;
  constPropSheetPagePointer.hInstance = g_hInstance;
  constPropSheetPagePointer.dwSize = 104;
  constPropSheetPagePointer.dwFlags = 8;
  constPropSheetPagePointer.lParam = a2;
  v4 = ShouldUseCompactLayout();
  constPropSheetPagePointer.pszTitle = (LPCWSTR)22;
  v5 = v4;
  constPropSheetPagePointer.pfnDlgProc = DiskCleanupManagerProc;
  constPropSheetPagePointer.pszTemplate = (LPCWSTR)(v4 != 0 ? 201LL : 101LL);
  v6 = CreatePropertySheetPageW(&constPropSheetPagePointer);
  v7 = (*(_BYTE *)(a2 + 1632) & 1) == 0;
  *(_QWORD *)&v11 = v6;
  if ( v7 )
  {
    if ( IsUserAnAdmin() )
    {
      constPropSheetPagePointer.pszTitle = (LPCWSTR)23;
      constPropSheetPagePointer.pszTemplate = (LPCWSTR)(v5 != 0 ? 202LL : 110LL);
      constPropSheetPagePointer.pfnDlgProc = (DLGPROC)MoreOptionsDlgProc;
      *((_QWORD *)&v11 + 1) = CreatePropertySheetPageW(&constPropSheetPagePointer);
      v12.nPages = 2;
    }
    else
    {
      v12.nPages = 1;
    }
    v8 = SHFormatMessage(0x64u, a2 + 536, *(unsigned __int16 *)(a2 + 16));
  }
  else
  {
    v12.nPages = 1;
    v8 = SHFormatMessage(0x66u);
  }
  v9 = (WCHAR *)v8;
  v12.dwSize = 96;
  v12.hInstance = g_hInstance;
  v12.ppsp = (LPCPROPSHEETPAGEW)&v11;
  v12.dwFlags = 33554564;
  v12.hwndParent = 0;
  v12.hIcon = (HICON)104;
  v12.pszCaption = v8;
  v10 = PropertySheetW(&v12);
  LocalFree(v9);
  return v10;
}

```

## disassembly

```asm
0x14000c994  mov     [rsp-8+arg_0], rbx
0x14000c999  mov     [rsp-8+arg_8], rdi
0x14000c99e  push    rbp
0x14000c99f  lea     rbp, [rsp-57h]
0x14000c9a4  sub     rsp, 100h
0x14000c9ab  mov     rbx, rdx
0x14000c9ae  lea     rcx, [rbp+57h+constPropSheetPagePointer]; void *
0x14000c9b2  xor     edx, edx; Val
0x14000c9b4  lea     r8d, [rdx+68h]; Size
0x14000c9b8  call    memset_0
0x14000c9bd  xor     edx, edx; Val
0x14000c9bf  lea     rcx, [rbp+57h+var_D0]; void *
0x14000c9c3  lea     r8d, [rdx+60h]; Size
0x14000c9c7  call    memset_0
0x14000c9cc  xorps   xmm0, xmm0
0x14000c9cf  movups  [rsp+100h+var_E0], xmm0
0x14000c9d4  test    rbx, rbx
0x14000c9d7  jnz     short loc_14000C9E0
0x14000c9d9  xor     eax, eax
0x14000c9db  jmp     loc_14000CB07
0x14000c9e0  mov     rax, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hInstance
0x14000c9e7  mov     [rbp+57h+constPropSheetPagePointer.hInstance], rax
0x14000c9eb  mov     [rbp+57h+constPropSheetPagePointer.dwSize], 68h ; 'h'
0x14000c9f2  mov     [rbp+57h+constPropSheetPagePointer.dwFlags], 8
0x14000c9f9  mov     [rbp+57h+constPropSheetPagePointer.lParam], rbx
0x14000c9fd  call    ?ShouldUseCompactLayout@@YAHXZ; ShouldUseCompactLayout(void)
0x14000ca02  mov     ecx, eax
0x14000ca04  mov     [rbp+57h+constPropSheetPagePointer.pszTitle], 16h
0x14000ca0c  neg     ecx
0x14000ca0e  mov     edi, eax
0x14000ca10  lea     rax, ?DiskCleanupManagerProc@@YA_JPEAUHWND__@@I_K_J@Z; DiskCleanupManagerProc(HWND__ *,uint,unsigned __int64,__int64)
0x14000ca17  sbb     rdx, rdx
0x14000ca1a  mov     [rbp+57h+constPropSheetPagePointer.pfnDlgProc], rax
0x14000ca1e  and     edx, 64h
0x14000ca21  lea     rcx, [rbp+57h+constPropSheetPagePointer]; constPropSheetPagePointer
0x14000ca25  add     rdx, 65h ; 'e'
0x14000ca29  mov     qword ptr [rbp+57h+constPropSheetPagePointer.10h], rdx
0x14000ca2d  call    cs:__imp_CreatePropertySheetPageW
0x14000ca33  test    byte ptr [rbx+660h], 1
0x14000ca3a  mov     qword ptr [rsp+100h+var_E0], rax
0x14000ca3f  jnz     short loc_14000CAA5
0x14000ca41  call    cs:__imp_IsUserAnAdmin
0x14000ca47  test    eax, eax
0x14000ca49  jz      short loc_14000CA86
0x14000ca4b  neg     edi
0x14000ca4d  mov     [rbp+57h+constPropSheetPagePointer.pszTitle], 17h
0x14000ca55  lea     rcx, [rbp+57h+constPropSheetPagePointer]; constPropSheetPagePointer
0x14000ca59  sbb     rax, rax
0x14000ca5c  and     eax, 5Ch
0x14000ca5f  add     rax, 6Eh ; 'n'
0x14000ca63  mov     qword ptr [rbp+57h+constPropSheetPagePointer.10h], rax
0x14000ca67  lea     rax, ?MoreOptionsDlgProc@@YA_JPEAUHWND__@@I_K_J@Z; MoreOptionsDlgProc(HWND__ *,uint,unsigned __int64,__int64)
0x14000ca6e  mov     [rbp+57h+constPropSheetPagePointer.pfnDlgProc], rax
0x14000ca72  call    cs:__imp_CreatePropertySheetPageW
0x14000ca78  mov     qword ptr [rsp+100h+var_E0+8], rax
0x14000ca7d  mov     [rbp+57h+var_D0.nPages], 2
0x14000ca84  jmp     short loc_14000CA8D
0x14000ca86  mov     [rbp+57h+var_D0.nPages], 1
0x14000ca8d  movzx   r8d, word ptr [rbx+10h]
0x14000ca92  lea     rdx, [rbx+218h]
0x14000ca99  mov     ecx, 64h ; 'd'; dwMessageId
0x14000ca9e  call    ?SHFormatMessage@@YAPEAGKZZ; SHFormatMessage(ulong,...)
0x14000caa3  jmp     short loc_14000CAB6
0x14000caa5  mov     ecx, 66h ; 'f'; dwMessageId
0x14000caaa  mov     [rbp+57h+var_D0.nPages], 1
0x14000cab1  call    ?SHFormatMessage@@YAPEAGKZZ; SHFormatMessage(ulong,...)
0x14000cab6  mov     rdi, rax
0x14000cab9  mov     [rbp+57h+var_D0.dwSize], 60h ; '`'
0x14000cac0  mov     rax, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hInstance
0x14000cac7  lea     rcx, [rbp+57h+var_D0]; LPCPROPSHEETHEADERW
0x14000cacb  mov     [rbp+57h+var_D0.hInstance], rax
0x14000cacf  lea     rax, [rsp+100h+var_E0]
0x14000cad4  mov     qword ptr [rbp+57h+var_D0.38h], rax
0x14000cad8  mov     [rbp+57h+var_D0.dwFlags], 2000084h
0x14000cadf  mov     [rbp+57h+var_D0.hwndParent], 0
0x14000cae7  mov     qword ptr [rbp+57h+var_D0.18h], 68h ; 'h'
0x14000caef  mov     [rbp+57h+var_D0.pszCaption], rdi
0x14000caf3  call    cs:__imp_PropertySheetW
0x14000caf9  mov     rcx, rdi; hMem
0x14000cafc  mov     rbx, rax
0x14000caff  call    cs:__imp_LocalFree
0x14000cb05  mov     eax, ebx
0x14000cb07  lea     r11, [rsp+100h+var_s0]
0x14000cb0f  mov     rbx, [r11+10h]
0x14000cb13  mov     rdi, [r11+18h]
0x14000cb17  mov     rsp, r11
0x14000cb1a  pop     rbp
0x14000cb1b  retn
```
