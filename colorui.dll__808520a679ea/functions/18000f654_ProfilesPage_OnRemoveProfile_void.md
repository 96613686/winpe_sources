# ProfilesPage::OnRemoveProfile(void)

- ea: `0x18000f654`
- end: `0x18000f9b1`
- name: `?OnRemoveProfile@ProfilesPage@@AEAAJXZ`
- size: `861`
- prototype: `__int64 __fastcall(ProfilesPage *__hidden this)`
- caller_count: `1`
- callee_count: `18`
- tags: `file_ops`

## callers

- `0x18000ef00`

## callees

- `0x18000138c`
- `0x18000f654`
- `0x180012528`
- `0x1800125ec`
- `0x18001330c`
- `0x180013458`
- `0x180013b18`
- `0x180013b34`
- `0x180013c00`
- `0x180014284`
- `0x180014468`
- `0x1800145f4`
- `0x18001478c`
- `0x180015c5c`
- `0x180015ecc`
- `0x1800184ce`
- `0x180018500`
- `0x180019010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000f813`
- `KERNEL32!GetLastError` at `0x18000f8f7`
- `KERNEL32!GetLastError` at `0x18000f813`
- `KERNEL32!GetLastError` at `0x18000f8f7`
- `KERNEL32!GetFileAttributesW` at `0x18000f801`
- `KERNEL32!GetFileAttributesW` at `0x18000f801`
- `KERNEL32!SetFileAttributesW` at `0x18000f8ed`
- `KERNEL32!SetFileAttributesW` at `0x18000f8ed`

## pseudocode

```c
__int64 __fastcall ProfilesPage::OnRemoveProfile(ProfilesPage *this)
{
  int SelectedLParam; // eax
  int ColorProfileFullPath; // ebx
  unsigned int *v4; // r14
  int v5; // esi
  int IsDefault; // r12d
  unsigned int v7; // r13d
  int v8; // r15d
  Helper::DefaultChecker::DefaultInfo *v9; // rax
  const struct ColorDataController *v10; // rdx
  Helper::DefaultChecker::DefaultInfo *v11; // rbx
  WINBOOL v12; // eax
  enum WCS_PROFILE_MANAGEMENT_SCOPE v13; // r8d
  int v14; // eax
  unsigned __int16 *v15; // r8
  Helper *v16; // rcx
  unsigned int v17; // r13d
  int *v18; // r8
  DWORD FileAttributesW; // r15d
  signed int LastError; // eax
  int v21; // r14d
  __int64 v22; // r8
  int v23; // eax
  const struct _GUID *v24; // r8
  signed int v25; // eax
  int v26; // eax
  int v28; // [rsp+20h] [rbp-E0h]
  int *v29; // [rsp+28h] [rbp-D8h]
  WINBOOL AccessStatus; // [rsp+30h] [rbp-D0h] BYREF
  int v31; // [rsp+34h] [rbp-CCh] BYREF
  enum WCS_PROFILE_MANAGEMENT_SCOPE v32[2]; // [rsp+38h] [rbp-C8h] BYREF
  int v33; // [rsp+40h] [rbp-C0h]
  int v34; // [rsp+44h] [rbp-BCh]
  Helper::DefaultChecker::DefaultInfo *v35; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v36; // [rsp+50h] [rbp-B0h]
  __int64 v37; // [rsp+58h] [rbp-A8h]
  WCHAR FileName[264]; // [rsp+60h] [rbp-A0h] BYREF

  *(_QWORD *)v32 = 0;
  SelectedLParam = ListView::GetSelectedLParam(*((ListView **)this + 5), (struct Profile **)v32);
  ColorProfileFullPath = SelectedLParam;
  if ( SelectedLParam == 1 )
    return 0;
  if ( SelectedLParam < 0 )
    return (unsigned int)ColorProfileFullPath;
  v4 = *(unsigned int **)v32;
  v5 = 0;
  IsDefault = 0;
  v34 = 0;
  v33 = 0;
  v31 = 0;
  if ( *(_DWORD *)(*(_QWORD *)v32 + 1052LL) )
  {
    v7 = **(_DWORD **)v32;
    v37 = 0;
    v36 = 1;
    v8 = 1934772034;
    if ( v7 > 1 )
      v8 = 0;
    AccessStatus = *(_DWORD *)(*(_QWORD *)v32 + 4LL);
    v32[0] = *((enum WCS_PROFILE_MANAGEMENT_SCOPE *)this + 8);
    v9 = (Helper::DefaultChecker::DefaultInfo *)operator new[](0x18u);
    v11 = v9;
    if ( v9 )
      Helper::DefaultChecker::DefaultInfo::DefaultInfo(v9);
    else
      v11 = 0;
    v35 = v11;
    if ( v11 )
    {
      v12 = AccessStatus;
      v13 = v32[0];
      *(_DWORD *)v11 = v7;
      *((_DWORD *)v11 + 1) = v12;
      v14 = HIDWORD(v36);
      *((_DWORD *)v11 + 2) = v8;
      *((_DWORD *)v11 + 3) = v14;
      *((_QWORD *)v11 + 2) = 0;
      Helper::DefaultChecker::GetDefaults((Helper::DefaultChecker *)&v35, v10, v13);
      ColorProfileFullPath = v37;
    }
    else
    {
      ColorProfileFullPath = -2147024882;
      LODWORD(v37) = -2147024882;
    }
    if ( ColorProfileFullPath >= 0 )
      IsDefault = Helper::DefaultChecker::IsDefault((Helper::DefaultChecker *)&v35, (const struct Profile *)v4);
    Helper::DefaultChecker::~DefaultChecker((Helper::DefaultChecker *)&v35);
  }
  memset_0(FileName, 0, 0x208u);
  if ( ColorProfileFullPath < 0 )
    goto LABEL_52;
  *(_QWORD *)v32 = v4 + 133;
  ColorProfileFullPath = Helper::GetColorProfileFullPath((Helper *)(v4 + 133), FileName, v15);
  if ( ColorProfileFullPath < 0 )
    goto LABEL_52;
  v17 = 0;
  if ( !(unsigned int)Helper::IsProcessElevated(v16) && !*(_DWORD *)(*((_QWORD *)this + 3) + 8LL) )
  {
    AccessStatus = 0;
    if ( (int)Helper::CanDeleteFileWithoutElevation(FileName, &AccessStatus, v18) < 0 || !AccessStatus )
      v17 = 1;
  }
  FileAttributesW = GetFileAttributesW(FileName);
  if ( FileAttributesW == -1 )
  {
    LastError = GetLastError();
    ColorProfileFullPath = LastError;
    if ( LastError )
    {
      if ( LastError > 0 )
        ColorProfileFullPath = (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      ColorProfileFullPath = -2147467259;
    }
    if ( ColorProfileFullPath < 0 )
      goto LABEL_52;
    v21 = 0;
    goto LABEL_30;
  }
  v21 = 0;
  if ( (FileAttributesW & 1) == 0 )
  {
LABEL_30:
    v22 = IsDefault != 0 ? 5014 : 5019;
    goto LABEL_31;
  }
  v21 = 1;
  if ( IsDefault )
    v22 = 5017;
  else
    v22 = 5016;
LABEL_31:
  v23 = Helper::ShowWarningDialog(*((HINSTANCE *)this + 2), *((HINSTANCE *)this + 1), (HWND)v22, v17, (int)&v31, v29);
  v5 = v31;
  ColorProfileFullPath = v23;
  if ( v23 < 0 )
    goto LABEL_52;
  if ( !v31 )
  {
    if ( v17 )
    {
      ColorProfileFullPath = ColorDataController::RunElevated(
                               *((ColorDataController **)this + 3),
                               *((struct _GUID **)this + 1),
                               v24);
      if ( ColorProfileFullPath < 0 )
        goto LABEL_52;
      if ( *(_DWORD *)(*((_QWORD *)this + 3) + 8LL) )
        v33 = 1;
      else
        v5 = 1;
    }
    if ( !v5 && v21 && !SetFileAttributesW(FileName, FileAttributesW & 0xFFFFFFFE) )
    {
      v25 = GetLastError();
      ColorProfileFullPath = v25;
      if ( v25 )
      {
        if ( v25 > 0 )
          ColorProfileFullPath = (unsigned __int16)v25 | 0x80070000;
      }
      else
      {
        ColorProfileFullPath = -2147467259;
      }
    }
  }
  if ( ColorProfileFullPath < 0 )
  {
LABEL_52:
    if ( ColorProfileFullPath == -2147024891 )
    {
      Helper::ShowErrorDialog(*((HINSTANCE *)this + 2), *((HINSTANCE *)this + 1), (HWND)0x139D, 0, v28);
      ColorProfileFullPath = 0;
    }
    else if ( ColorProfileFullPath >= 0 && !v5 )
    {
      ColorProfileFullPath = ListView::RemoveSelectedItem(*((ListView **)this + 5));
    }
    goto LABEL_57;
  }
  if ( !v5 )
  {
    ColorProfileFullPath = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(*((_QWORD *)this + 3) + 16LL) + 40LL))(
                             *(_QWORD *)(*((_QWORD *)this + 3) + 16LL),
                             *(_QWORD *)v32);
    goto LABEL_52;
  }
LABEL_57:
  if ( v33 )
    v26 = ColorDataController::RunRestricted(*((ColorDataController **)this + 3));
  else
    v26 = v34;
  if ( ColorProfileFullPath >= 0 && v26 < 0 )
    return (unsigned int)v26;
  return (unsigned int)ColorProfileFullPath;
}

```

## disassembly

```asm
0x18000f654  push    rbp
0x18000f656  push    rbx
0x18000f657  push    rsi
0x18000f658  push    rdi
0x18000f659  push    r12
0x18000f65b  push    r13
0x18000f65d  push    r14
0x18000f65f  push    r15
0x18000f661  lea     rbp, [rsp-188h]
0x18000f669  sub     rsp, 288h
0x18000f670  mov     rax, cs:__security_cookie
0x18000f677  xor     rax, rsp
0x18000f67a  mov     [rbp+1C0h+var_50], rax
0x18000f681  mov     rdi, rcx
0x18000f684  mov     qword ptr [rsp+2C0h+var_288], 0
0x18000f68d  mov     rcx, [rcx+28h]; this
0x18000f691  lea     rdx, [rsp+2C0h+var_288]; struct Profile **
0x18000f696  call    ?GetSelectedLParam@ListView@@QEBAJPEAPEAUProfile@@@Z; ListView::GetSelectedLParam(Profile * *)
0x18000f69b  mov     ebx, eax
0x18000f69d  cmp     eax, 1
0x18000f6a0  jnz     short loc_18000F6A9
0x18000f6a2  xor     ebx, ebx
0x18000f6a4  jmp     loc_18000F98C
0x18000f6a9  test    eax, eax
0x18000f6ab  js      loc_18000F98C
0x18000f6b1  mov     r14, qword ptr [rsp+2C0h+var_288]
0x18000f6b6  xor     esi, esi
0x18000f6b8  xor     r12d, r12d
0x18000f6bb  mov     [rsp+2C0h+var_27C], 0
0x18000f6c3  mov     [rsp+2C0h+var_280], 0
0x18000f6cb  mov     [rsp+2C0h+var_28C], esi
0x18000f6cf  cmp     [r14+41Ch], esi
0x18000f6d6  jz      loc_18000F787
0x18000f6dc  mov     r13d, [r14]
0x18000f6df  lea     ecx, [rsi+18h]; unsigned __int64
0x18000f6e2  xor     eax, eax
0x18000f6e4  mov     [rsp+2C0h+var_268], rsi
0x18000f6e9  cmp     r13d, 1
0x18000f6ed  mov     [rsp+2C0h+var_270], 1
0x18000f6f6  mov     r15d, 73524742h
0x18000f6fc  cmova   r15d, eax
0x18000f700  mov     eax, [r14+4]
0x18000f704  mov     [rsp+2C0h+AccessStatus], eax
0x18000f708  mov     eax, [rdi+20h]
0x18000f70b  mov     [rsp+2C0h+var_288], eax
0x18000f70f  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000f714  mov     rbx, rax
0x18000f717  test    rax, rax
0x18000f71a  jz      short loc_18000F726
0x18000f71c  mov     rcx, rax; this
0x18000f71f  call    ??0DefaultInfo@DefaultChecker@Helper@@QEAA@XZ; Helper::DefaultChecker::DefaultInfo::DefaultInfo(void)
0x18000f724  jmp     short loc_18000F728
0x18000f726  xor     ebx, ebx
0x18000f728  mov     [rsp+2C0h+var_278], rbx
0x18000f72d  test    rbx, rbx
0x18000f730  jnz     short loc_18000F73D
0x18000f732  mov     ebx, 8007000Eh
0x18000f737  mov     dword ptr [rsp+2C0h+var_268], ebx
0x18000f73b  jmp     short loc_18000F769
0x18000f73d  mov     eax, [rsp+2C0h+AccessStatus]
0x18000f741  lea     rcx, [rsp+2C0h+var_278]; this
0x18000f746  mov     r8d, [rsp+2C0h+var_288]; enum WCS_PROFILE_MANAGEMENT_SCOPE
0x18000f74b  mov     [rbx], r13d
0x18000f74e  mov     [rbx+4], eax
0x18000f751  mov     eax, dword ptr [rsp+2C0h+var_270+4]
0x18000f755  mov     [rbx+8], r15d
0x18000f759  mov     [rbx+0Ch], eax
0x18000f75c  mov     [rbx+10h], rsi
0x18000f760  call    ?GetDefaults@DefaultChecker@Helper@@AEAAXAEBVColorDataController@@W4WCS_PROFILE_MANAGEMENT_SCOPE@@@Z; Helper::DefaultChecker::GetDefaults(ColorDataController const &,WCS_PROFILE_MANAGEMENT_SCOPE)
0x18000f765  mov     ebx, dword ptr [rsp+2C0h+var_268]
0x18000f769  test    ebx, ebx
0x18000f76b  js      short loc_18000F77D
0x18000f76d  mov     rdx, r14; struct Profile *
0x18000f770  lea     rcx, [rsp+2C0h+var_278]; this
0x18000f775  call    ?IsDefault@DefaultChecker@Helper@@QEBAHAEBUProfile@@@Z; Helper::DefaultChecker::IsDefault(Profile const &)
0x18000f77a  mov     r12d, eax
0x18000f77d  lea     rcx, [rsp+2C0h+var_278]; this
0x18000f782  call    ??1DefaultChecker@Helper@@QEAA@XZ; Helper::DefaultChecker::~DefaultChecker(void)
0x18000f787  xor     edx, edx; Val
0x18000f789  lea     rcx, [rsp+2C0h+FileName]; void *
0x18000f78e  mov     r8d, 208h; Size
0x18000f794  call    memset_0
0x18000f799  test    ebx, ebx
0x18000f79b  js      loc_18000F938
0x18000f7a1  lea     rax, [r14+214h]
0x18000f7a8  mov     rcx, rax; this
0x18000f7ab  mov     qword ptr [rsp+2C0h+var_288], rax
0x18000f7b0  lea     rdx, [rsp+2C0h+FileName]; unsigned __int16 *
0x18000f7b5  call    ?GetColorProfileFullPath@Helper@@YAJPEBGPEAGK@Z; Helper::GetColorProfileFullPath(ushort const *,ushort *,ulong)
0x18000f7ba  mov     ebx, eax
0x18000f7bc  test    eax, eax
0x18000f7be  js      loc_18000F938
0x18000f7c4  xor     r13d, r13d
0x18000f7c7  call    ?IsProcessElevated@Helper@@YAHXZ; Helper::IsProcessElevated(void)
0x18000f7cc  test    eax, eax
0x18000f7ce  jnz     short loc_18000F7FC
0x18000f7d0  mov     rax, [rdi+18h]
0x18000f7d4  cmp     [rax+8], esi
0x18000f7d7  jnz     short loc_18000F7FC
0x18000f7d9  lea     rdx, [rsp+2C0h+AccessStatus]; AccessStatus
0x18000f7de  mov     [rsp+2C0h+AccessStatus], esi
0x18000f7e2  lea     rcx, [rsp+2C0h+FileName]; lpFileName
0x18000f7e7  call    ?CanDeleteFileWithoutElevation@Helper@@YAJPEAGPEAH@Z; Helper::CanDeleteFileWithoutElevation(ushort *,int *)
0x18000f7ec  test    eax, eax
0x18000f7ee  js      short loc_18000F7F6
0x18000f7f0  cmp     [rsp+2C0h+AccessStatus], esi
0x18000f7f4  jnz     short loc_18000F7FC
0x18000f7f6  mov     r13d, 1
0x18000f7fc  lea     rcx, [rsp+2C0h+FileName]; lpFileName
0x18000f801  call    cs:__imp_GetFileAttributesW
0x18000f807  mov     r15d, eax
0x18000f80a  cmp     eax, 0FFFFFFFFh
0x18000f80d  jnz     loc_18000F8AC
0x18000f813  call    cs:__imp_GetLastError
0x18000f819  mov     ebx, eax
0x18000f81b  test    eax, eax
0x18000f81d  jz      short loc_18000F82C
0x18000f81f  jle     short loc_18000F831
0x18000f821  movzx   ebx, ax
0x18000f824  or      ebx, 80070000h
0x18000f82a  jmp     short loc_18000F831
0x18000f82c  mov     ebx, 80004005h
0x18000f831  test    ebx, ebx
0x18000f833  js      loc_18000F938
0x18000f839  xor     r14d, r14d
0x18000f83c  neg     r12d
0x18000f83f  sbb     r8d, r8d
0x18000f842  and     r8d, 0FFFFFFFBh
0x18000f846  add     r8d, 139Bh; HWND
0x18000f84d  mov     rdx, [rdi+8]; HINSTANCE
0x18000f851  lea     rax, [rsp+2C0h+var_28C]
0x18000f856  mov     rcx, [rdi+10h]; this
0x18000f85a  mov     r9d, r13d; unsigned int
0x18000f85d  mov     qword ptr [rsp+2C0h+var_2A0], rax; int
0x18000f862  call    ?ShowWarningDialog@Helper@@YAJPEAUHINSTANCE__@@PEAUHWND__@@IHPEAH@Z; Helper::ShowWarningDialog(HINSTANCE__ *,HWND__ *,uint,int,int *)
0x18000f867  mov     esi, [rsp+2C0h+var_28C]
0x18000f86b  mov     ebx, eax
0x18000f86d  test    eax, eax
0x18000f86f  js      loc_18000F938
0x18000f875  test    esi, esi
0x18000f877  jnz     loc_18000F915
0x18000f87d  test    r13d, r13d
0x18000f880  jz      short loc_18000F8D8
0x18000f882  mov     rdx, [rdi+8]; HWND
0x18000f886  mov     rcx, [rdi+18h]; this
0x18000f88a  call    ?RunElevated@ColorDataController@@QEAAJPEAUHWND__@@@Z; ColorDataController::RunElevated(HWND__ *)
0x18000f88f  mov     ebx, eax
0x18000f891  test    eax, eax
0x18000f893  js      loc_18000F938
0x18000f899  mov     rax, [rdi+18h]
0x18000f89d  cmp     [rax+8], esi
0x18000f8a0  jz      short loc_18000F8D3
0x18000f8a2  mov     [rsp+2C0h+var_280], 1
0x18000f8aa  jmp     short loc_18000F8D8
0x18000f8ac  xor     r14d, r14d
0x18000f8af  test    r15b, 1
0x18000f8b3  jz      short loc_18000F83C
0x18000f8b5  mov     r14d, 1
0x18000f8bb  test    r12d, r12d
0x18000f8be  jz      short loc_18000F8C8
0x18000f8c0  mov     r8d, 1399h
0x18000f8c6  jmp     short loc_18000F84D
0x18000f8c8  mov     r8d, 1398h
0x18000f8ce  jmp     loc_18000F84D
0x18000f8d3  mov     esi, 1
0x18000f8d8  test    esi, esi
0x18000f8da  jnz     short loc_18000F915
0x18000f8dc  test    r14d, r14d
0x18000f8df  jz      short loc_18000F915
0x18000f8e1  and     r15d, 0FFFFFFFEh
0x18000f8e5  lea     rcx, [rsp+2C0h+FileName]; lpFileName
0x18000f8ea  mov     edx, r15d; dwFileAttributes
0x18000f8ed  call    cs:__imp_SetFileAttributesW
0x18000f8f3  test    eax, eax
0x18000f8f5  jnz     short loc_18000F915
0x18000f8f7  call    cs:__imp_GetLastError
0x18000f8fd  mov     ebx, eax
0x18000f8ff  test    eax, eax
0x18000f901  jz      short loc_18000F910
0x18000f903  jle     short loc_18000F915
0x18000f905  movzx   ebx, ax
0x18000f908  or      ebx, 80070000h
0x18000f90e  jmp     short loc_18000F915
0x18000f910  mov     ebx, 80004005h
0x18000f915  test    ebx, ebx
0x18000f917  js      short loc_18000F938
0x18000f919  test    esi, esi
0x18000f91b  jnz     short loc_18000F96D
0x18000f91d  mov     rax, [rdi+18h]
0x18000f921  mov     rdx, qword ptr [rsp+2C0h+var_288]
0x18000f926  mov     rcx, [rax+10h]
0x18000f92a  mov     rax, [rcx]
0x18000f92d  mov     rax, [rax+28h]
0x18000f931  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f936  mov     ebx, eax
0x18000f938  cmp     ebx, 80070005h
0x18000f93e  jnz     short loc_18000F95A
0x18000f940  mov     rdx, [rdi+8]; HINSTANCE
0x18000f944  xor     r9d, r9d; unsigned int
0x18000f947  mov     rcx, [rdi+10h]; this
0x18000f94b  mov     r8d, 139Dh; HWND
0x18000f951  call    ?ShowErrorDialog@Helper@@YAJPEAUHINSTANCE__@@PEAUHWND__@@IJ@Z; Helper::ShowErrorDialog(HINSTANCE__ *,HWND__ *,uint,long)
0x18000f956  xor     ebx, ebx
0x18000f958  jmp     short loc_18000F96D
0x18000f95a  test    ebx, ebx
0x18000f95c  js      short loc_18000F96D
0x18000f95e  test    esi, esi
0x18000f960  jnz     short loc_18000F96D
0x18000f962  mov     rcx, [rdi+28h]; this
0x18000f966  call    ?RemoveSelectedItem@ListView@@QEAAJXZ; ListView::RemoveSelectedItem(void)
0x18000f96b  mov     ebx, eax
0x18000f96d  cmp     [rsp+2C0h+var_280], 0
0x18000f972  jz      short loc_18000F97F
0x18000f974  mov     rcx, [rdi+18h]; this
0x18000f978  call    ?RunRestricted@ColorDataController@@QEAAJXZ; ColorDataController::RunRestricted(void)
0x18000f97d  jmp     short loc_18000F983
0x18000f97f  mov     eax, [rsp+2C0h+var_27C]
0x18000f983  test    ebx, ebx
0x18000f985  js      short loc_18000F98C
0x18000f987  test    eax, eax
0x18000f989  cmovs   ebx, eax
0x18000f98c  mov     eax, ebx
0x18000f98e  mov     rcx, [rbp+1C0h+var_50]
0x18000f995  xor     rcx, rsp; StackCookie
0x18000f998  call    __security_check_cookie
0x18000f99d  add     rsp, 288h
0x18000f9a4  pop     r15
0x18000f9a6  pop     r14
0x18000f9a8  pop     r13
0x18000f9aa  pop     r12
0x18000f9ac  pop     rdi
0x18000f9ad  pop     rsi
0x18000f9ae  pop     rbx
0x18000f9af  pop     rbp
0x18000f9b0  retn
```
