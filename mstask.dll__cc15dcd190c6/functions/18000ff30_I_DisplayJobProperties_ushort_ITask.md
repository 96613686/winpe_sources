# I_DisplayJobProperties(ushort *,ITask *)

- ea: `0x18000ff30`
- end: `0x18001008f`
- name: `?I_DisplayJobProperties@@YAJPEAGPEAUITask@@@Z`
- size: `351`
- prototype: `__int64 __fastcall(LPCWSTR pszPath, struct ITask *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18000b710`

## callees

- `0x180001840`
- `0x18000fe24`
- `0x18000ff30`
- `0x180010478`
- `0x180012f9c`
- `0x180016dc8`
- `0x18001aa9a`
- `0x18001aac0`

## import_xrefs

- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindExtensionW` at `0x18000ffb9`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindExtensionW` at `0x18000ffb9`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x18000ff99`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x18000ff99`
- `USER32!DestroyWindow` at `0x180010063`
- `USER32!DestroyWindow` at `0x180010063`
- `COMCTL32!PropertySheetW` at `0x180010053`
- `COMCTL32!PropertySheetW` at `0x180010053`
- `COMCTL32!__imp_InitCommonControls` at `0x18000ffcf`
- `COMCTL32!__imp_InitCommonControls` at `0x18000ffcf`

## pseudocode

```c
__int64 __fastcall I_DisplayJobProperties(LPCWSTR pszPath, struct ITask *a2)
{
  __int64 v4; // rdx
  PROPSHEETHEADERW_V2 *v5; // rax
  const unsigned __int16 *FileNameW; // rax
  LPWSTR ExtensionW; // rax
  unsigned int v8; // ebx
  PROPSHEETHEADERW_V2 v10; // [rsp+20h] [rbp-E0h] BYREF
  _BYTE v11[160]; // [rsp+80h] [rbp-80h] BYREF
  WCHAR pszPatha[264]; // [rsp+120h] [rbp+20h] BYREF

  memset_0(&v10, 0, sizeof(v10));
  v4 = 96;
  v5 = &v10;
  do
  {
    LOBYTE(v5->dwSize) = 0;
    v5 = (PROPSHEETHEADERW_V2 *)((char *)v5 + 1);
    --v4;
  }
  while ( v4 );
  memset_0(pszPatha, 0, 0x20Au);
  FileNameW = PathFindFileNameW(pszPath);
  if ( FileNameW )
  {
    StringCchCopyW(pszPatha, 0x105u, FileNameW);
    ExtensionW = PathFindExtensionW(pszPatha);
    if ( ExtensionW )
      *ExtensionW = 0;
  }
  else
  {
    pszPatha[0] = 0;
  }
  InitCommonControls();
  memset_0(v11, 0, sizeof(v11));
  *(_QWORD *)&v10.dwSize = 96;
  v10.hwndParent = I_CreateStubWindow();
  v10.hInstance = g_hInstance;
  v10.pszCaption = pszPatha;
  v10.ppsp = (LPCPROPSHEETPAGEW)v11;
  AddGeneralPage(&v10, a2);
  AddSchedulePage(&v10, a2);
  v8 = AddSettingsPage(&v10, a2);
  if ( v10.nPages )
    PropertySheetW(&v10);
  else
    v8 = -2147467259;
  if ( v10.hwndParent )
    DestroyWindow(v10.hwndParent);
  return v8;
}

```

## disassembly

```asm
0x18000ff30  mov     [rsp-8+arg_10], rbx
0x18000ff35  mov     [rsp-8+arg_18], rdi
0x18000ff3a  push    rbp
0x18000ff3b  lea     rbp, [rsp-240h]
0x18000ff43  sub     rsp, 340h
0x18000ff4a  mov     rax, cs:__security_cookie
0x18000ff51  xor     rax, rsp
0x18000ff54  mov     [rbp+240h+var_10], rax
0x18000ff5b  mov     rdi, rdx
0x18000ff5e  mov     rbx, rcx
0x18000ff61  xor     edx, edx; Val
0x18000ff63  lea     rcx, [rsp+340h+var_320]; void *
0x18000ff68  lea     r8d, [rdx+60h]; Size
0x18000ff6c  call    memset_0
0x18000ff71  mov     edx, 60h ; '`'
0x18000ff76  lea     rax, [rsp+340h+var_320]
0x18000ff7b  mov     byte ptr [rax], 0
0x18000ff7e  inc     rax
0x18000ff81  sub     rdx, 1; Val
0x18000ff85  jnz     short loc_18000FF7B
0x18000ff87  mov     r8d, 20Ah; Size
0x18000ff8d  lea     rcx, [rbp+240h+pszPath]; void *
0x18000ff91  call    memset_0
0x18000ff96  mov     rcx, rbx; pszPath
0x18000ff99  call    cs:__imp_PathFindFileNameW
0x18000ff9f  test    rax, rax
0x18000ffa2  jz      short loc_18000FFCB
0x18000ffa4  mov     r8, rax; unsigned __int16 *
0x18000ffa7  lea     rcx, [rbp+240h+pszPath]; unsigned __int16 *
0x18000ffab  mov     edx, 105h; unsigned __int64
0x18000ffb0  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000ffb5  lea     rcx, [rbp+240h+pszPath]; pszPath
0x18000ffb9  call    cs:__imp_PathFindExtensionW
0x18000ffbf  test    rax, rax
0x18000ffc2  jz      short loc_18000FFCF
0x18000ffc4  xor     ecx, ecx
0x18000ffc6  mov     [rax], cx
0x18000ffc9  jmp     short loc_18000FFCF
0x18000ffcb  mov     [rbp+240h+pszPath], ax
0x18000ffcf  call    cs:__imp_InitCommonControls
0x18000ffd5  xor     edx, edx; Val
0x18000ffd7  lea     rcx, [rbp+240h+var_2C0]; void *
0x18000ffdb  mov     r8d, 0A0h; Size
0x18000ffe1  call    memset_0
0x18000ffe6  mov     qword ptr [rsp+340h+var_320.dwSize], 60h ; '`'
0x18000ffef  call    ?I_CreateStubWindow@@YAPEAUHWND__@@XZ; I_CreateStubWindow(void)
0x18000fff4  mov     [rsp+340h+var_320.hwndParent], rax
0x18000fff9  lea     rcx, [rsp+340h+var_320]; struct _PROPSHEETHEADERW_V2 *
0x18000fffe  mov     rax, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hInstance
0x180010005  mov     rdx, rdi; struct ITask *
0x180010008  mov     [rsp+340h+var_320.hInstance], rax
0x18001000d  lea     rax, [rbp+240h+pszPath]
0x180010011  mov     [rsp+340h+var_320.pszCaption], rax
0x180010016  lea     rax, [rbp+240h+var_2C0]
0x18001001a  mov     qword ptr [rsp+340h+var_320.38h], rax
0x18001001f  call    ?AddGeneralPage@@YAJAEAU_PROPSHEETHEADERW_V2@@PEAUITask@@@Z; AddGeneralPage(_PROPSHEETHEADERW_V2 &,ITask *)
0x180010024  mov     rdx, rdi; struct ITask *
0x180010027  lea     rcx, [rsp+340h+var_320]; struct _PROPSHEETHEADERW_V2 *
0x18001002c  call    ?AddSchedulePage@@YAJAEAU_PROPSHEETHEADERW_V2@@PEAUITask@@@Z; AddSchedulePage(_PROPSHEETHEADERW_V2 &,ITask *)
0x180010031  mov     rdx, rdi; struct ITask *
0x180010034  lea     rcx, [rsp+340h+var_320]; struct _PROPSHEETHEADERW_V2 *
0x180010039  call    ?AddSettingsPage@@YAJAEAU_PROPSHEETHEADERW_V2@@PEAUITask@@@Z; AddSettingsPage(_PROPSHEETHEADERW_V2 &,ITask *)
0x18001003e  cmp     [rsp+340h+var_320.nPages], 0
0x180010043  mov     ebx, eax
0x180010045  jnz     short loc_18001004E
0x180010047  mov     ebx, 80004005h
0x18001004c  jmp     short loc_180010059
0x18001004e  lea     rcx, [rsp+340h+var_320]; LPCPROPSHEETHEADERW
0x180010053  call    cs:__imp_PropertySheetW
0x180010059  mov     rcx, [rsp+340h+var_320.hwndParent]; hWnd
0x18001005e  test    rcx, rcx
0x180010061  jz      short loc_180010069
0x180010063  call    cs:__imp_DestroyWindow
0x180010069  mov     eax, ebx
0x18001006b  mov     rcx, [rbp+240h+var_10]
0x180010072  xor     rcx, rsp; StackCookie
0x180010075  call    __security_check_cookie
0x18001007a  lea     r11, [rsp+340h+var_s0]
0x180010082  mov     rbx, [r11+20h]
0x180010086  mov     rdi, [r11+28h]
0x18001008a  mov     rsp, r11
0x18001008d  pop     rbp
0x18001008e  retn
```
