# Helper::OpenProfileSelectionDialog(HWND__ *,HINSTANCE__ *,uint,Helper::SelectedFiles * *)

- ea: `0x180014b78`
- end: `0x180015421`
- name: `?OpenProfileSelectionDialog@Helper@@YAJPEAUHWND__@@PEAUHINSTANCE__@@IPEAPEAVSelectedFiles@1@@Z`
- size: `2217`
- prototype: `__int64 __fastcall(Helper *this, HINSTANCE, HINSTANCE, Helper::SelectedFiles **)`
- caller_count: `2`
- callee_count: `11`
- tags: `file_ops, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x18000f074`
- `0x180016a70`

## callees

- `0x180001334`
- `0x18000138c`
- `0x180001cd4`
- `0x1800099f8`
- `0x180013b7c`
- `0x180013ef8`
- `0x180014b78`
- `0x18001772c`
- `0x1800179f0`
- `0x1800184c2`
- `0x180019010`

## import_xrefs

- `KERNEL32!LocalFree` at `0x180014e56`
- `KERNEL32!LocalFree` at `0x180014eb5`
- `KERNEL32!LocalFree` at `0x18001510d`
- `KERNEL32!LocalFree` at `0x180015224`
- `KERNEL32!LocalFree` at `0x1800152ed`
- `KERNEL32!LocalFree` at `0x180014e56`
- `KERNEL32!LocalFree` at `0x180014eb5`
- `KERNEL32!LocalFree` at `0x18001510d`
- `KERNEL32!LocalFree` at `0x180015224`
- `KERNEL32!LocalFree` at `0x1800152ed`
- `ole32!CoCreateInstance` at `0x180014bc4`
- `ole32!CoCreateInstance` at `0x180014bc4`
- `ole32!CoTaskMemFree` at `0x1800151cc`
- `ole32!CoTaskMemFree` at `0x1800151cc`
- `OLEAUT32!__imp_SysAllocString` at `0x180014dd7`
- `OLEAUT32!__imp_SysAllocString` at `0x180014dd7`
- `OLEAUT32!__imp_SysStringLen` at `0x180014df2`
- `OLEAUT32!__imp_SysStringLen` at `0x180014df2`

## pseudocode

```c
__int64 __fastcall Helper::OpenProfileSelectionDialog(
        Helper *this,
        HINSTANCE a2,
        HINSTANCE a3,
        Helper::SelectedFiles **a4)
{
  UINT v4; // esi
  HRESULT v7; // eax
  unsigned int v8; // ebx
  void (*v9)(void); // rax
  _DWORD *v11; // rax
  _DWORD *v12; // rbx
  unsigned int v13; // r15d
  int v14; // eax
  LPVOID v15; // rcx
  LPVOID v16; // rbx
  unsigned int v17; // r14d
  int v18; // eax
  unsigned int v19; // edi
  int StringFromRC; // eax
  OLECHAR *v21; // rax
  OLECHAR *v22; // rdi
  UINT v23; // eax
  UINT i; // ecx
  int v25; // eax
  HLOCAL v26; // rdi
  int v27; // esi
  __int64 v28; // rdx
  __int64 v29; // rdx
  int v30; // eax
  __int64 v31; // rdx
  Helper::SelectedFiles *v32; // rax
  Helper::SelectedFiles *v33; // rsi
  void *v34; // rax
  int v35; // r13d
  unsigned int v36; // r15d
  int v37; // eax
  unsigned int v38; // r12d
  unsigned __int64 v39; // r12
  size_t v40; // rax
  __int64 v41; // rcx
  void (*v42)(void); // rax
  int ppv; // [rsp+20h] [rbp-59h]
  LPVOID v44; // [rsp+30h] [rbp-49h] BYREF
  __int64 v45; // [rsp+38h] [rbp-41h] BYREF
  unsigned int v46; // [rsp+40h] [rbp-39h] BYREF
  __int64 v47; // [rsp+48h] [rbp-31h] BYREF
  int v48; // [rsp+50h] [rbp-29h] BYREF
  OLECHAR *psz; // [rsp+58h] [rbp-21h]
  HLOCAL hMem; // [rsp+60h] [rbp-19h] BYREF
  int v51; // [rsp+68h] [rbp-11h] BYREF
  unsigned __int16 *v52; // [rsp+70h] [rbp-9h]
  unsigned int v53; // [rsp+78h] [rbp-1h] BYREF
  void *Src; // [rsp+80h] [rbp+7h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  v4 = (unsigned int)a3;
  v44 = 0;
  v7 = CoCreateInstance(&CLSID_FileOpenDialog, 0, 1u, &GUID_d57c7288_d4ad_4768_be02_9d969532d960, &v44);
  v8 = v7;
  if ( v7 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x15E,
      (unsigned int)"clientcore\\windows\\core\\ntgdi\\icm\\colorui\\ui\\helper.cpp",
      (const char *)(unsigned int)v7,
      ppv);
    if ( !v44 )
      return v8;
    v9 = *(void (**)(void))(*(_QWORD *)v44 + 16LL);
LABEL_4:
    v9();
    return v8;
  }
  v53 = 0;
  v45 = 0;
  v11 = operator new(0x28u, (const struct std::nothrow_t *)&std::nothrow);
  v12 = v11;
  if ( !v11 )
  {
    v13 = -2147024882;
    goto LABEL_119;
  }
  v11[4] = 1;
  *(_QWORD *)v11 = &Helper::AddColorProfileDialogEventHandler::`vftable'{for `IFileDialogEvents'};
  *((_QWORD *)v11 + 3) = this;
  *((_QWORD *)v11 + 1) = &Helper::AddColorProfileDialogEventHandler::`vftable'{for `IFileDialogControlEvents'};
  *((_QWORD *)v11 + 4) = a2;
  v13 = ((__int64 (__fastcall *)(_DWORD *, GUID *, __int64 *))Helper::AddColorProfileDialogEventHandler::`vftable'{for `IFileDialogEvents'})(
          v11,
          &GUID_973510db_7d7f_452b_8975_74a85828d354,
          &v45);
  (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v12 + 16LL))(v12);
  if ( (v13 & 0x80000000) != 0 )
  {
LABEL_119:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x163,
      (unsigned int)"clientcore\\windows\\core\\ntgdi\\icm\\colorui\\ui\\helper.cpp",
      (const char *)v13,
      ppv);
    if ( v45 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 16LL))(v45);
    if ( !v44 )
      return v13;
    v42 = *(void (**)(void))(*(_QWORD *)v44 + 16LL);
    goto LABEL_123;
  }
  v14 = (*(__int64 (__fastcall **)(LPVOID, __int64, unsigned int *))(*(_QWORD *)v44 + 56LL))(v44, v45, &v53);
  v8 = v14;
  if ( v14 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x166,
      (unsigned int)"clientcore\\windows\\core\\ntgdi\\icm\\colorui\\ui\\helper.cpp",
      (const char *)(unsigned int)v14,
      ppv);
    if ( v45 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 16LL))(v45);
    if ( !v44 )
      return v8;
    v9 = *(void (**)(void))(*(_QWORD *)v44 + 16LL);
    goto LABEL_4;
  }
  v15 = v44;
  v16 = v44;
  if ( v44 )
  {
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v44 + 8LL))(v44);
    v15 = v44;
  }
  v17 = v53;
  v18 = (*(__int64 (__fastcall **)(LPVOID, __int64))(*(_QWORD *)v15 + 72LL))(v15, 6720);
  v19 = v18;
  if ( v18 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x16C,
      (unsigned int)"clientcore\\windows\\core\\ntgdi\\icm\\colorui\\ui\\helper.cpp",
      (const char *)(unsigned int)v18,
      ppv);
LABEL_17:
    (*(void (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)v16 + 64LL))(v16, v17);
LABEL_18:
    if ( v16 )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v16 + 16LL))(v16);
    if ( v45 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 16LL))(v45);
    if ( v44 )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v44 + 16LL))(v44);
    return v19;
  }
  v48 = 1735554163;
  psz = &NCoreLibrary::TString::gszNullState;
  StringFromRC = NCoreLibrary::TString::LoadStringFromRC((NCoreLibrary::TString *)&v48, a2, v4);
  v19 = StringFromRC;
  if ( StringFromRC < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x171,
      (unsigned int)"clientcore\\windows\\core\\ntgdi\\icm\\colorui\\ui\\helper.cpp",
      (const char *)(unsigned int)StringFromRC,
      ppv);
    NCoreLibrary::TString::~TString((NCoreLibrary::TString *)&v48);
    goto LABEL_17;
  }
  v21 = SysAllocString(psz);
  v22 = v21;
  v13 = -2147024882;
  if ( !v21 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x174,
      (unsigned int)"clientcore\\windows\\core\\ntgdi\\icm\\colorui\\ui\\helper.cpp",
      (const char *)0x8007000ELL,
      ppv);
LABEL_112:
    NCoreLibrary::TString::~TString((NCoreLibrary::TString *)&v48);
    (*(void (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)v16 + 64LL))(v16, v17);
    if ( v16 )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v16 + 16LL))(v16);
    if ( v45 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 16LL))(v45);
    if ( !v44 )
      return v13;
    v42 = *(void (**)(void))(*(_QWORD *)v44 + 16LL);
LABEL_123:
    v42();
    return v13;
  }
  v23 = SysStringLen(v21);
  for ( i = 0; i < v23; ++i )
  {
    if ( v22[i] == 124 )
      v22[i] = 0;
  }
  hMem = 0;
  v46 = 0;
  v25 = Helper::FilterSpecFromMultiSz(v22, &hMem, &v46);
  v19 = v25;
  if ( v25 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x181,
      (unsigned int)"clientcore\\windows\\core\\ntgdi\\icm\\colorui\\ui\\helper.cpp",
      (const char *)(unsigned int)v25,
      ppv);
    if ( hMem )
      LocalFree(hMem);
    NCoreLibrary::TString::~TString((NCoreLibrary::TString *)&v48);
    (*(void (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)v16 + 64LL))(v16, v17);
    goto LABEL_18;
  }
  v26 = hMem;
  v27 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, HLOCAL))(*(_QWORD *)v44 + 32LL))(v44, v46, hMem);
  if ( v27 < 0 )
  {
    v28 = 387;
LABEL_38:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v28,
      (unsigned int)"clientcore\\windows\\core\\ntgdi\\icm\\colorui\\ui\\helper.cpp",
      (const char *)(unsigned int)v27,
      ppv);
LABEL_39:
    if ( v26 )
      LocalFree(v26);
    NCoreLibrary::TString::~TString((NCoreLibrary::TString *)&v48);
    (*(void (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)v16 + 64LL))(v16, v17);
    if ( v16 )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v16 + 16LL))(v16);
    if ( v45 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 16LL))(v45);
    if ( v44 )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v44 + 16LL))(v44);
    return (unsigned int)v27;
  }
  v27 = (*(__int64 (__fastcall **)(LPVOID, __int64))(*(_QWORD *)v44 + 40LL))(v44, 1);
  if ( v27 < 0 )
  {
    v28 = 390;
    goto LABEL_38;
  }
  v27 = (*(__int64 (__fastcall **)(LPVOID, const wchar_t *))(*(_QWORD *)v44 + 176LL))(
          v44,
          L"*.icm;*.icc;*.gmmp;*.camp;*.cdmp");
  if ( v27 < 0 )
  {
    v28 = 393;
    goto LABEL_38;
  }
  v51 = 1735554163;
  v52 = &NCoreLibrary::TString::gszNullState;
  v27 = NCoreLibrary::TString::LoadStringFromRC((NCoreLibrary::TString *)&v51, a2, 0x712u);
  if ( v27 < 0 )
  {
    v29 = 397;
LABEL_54:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v29,
      (unsigned int)"clientcore\\windows\\core\\ntgdi\\icm\\colorui\\ui\\helper.cpp",
      (const char *)(unsigned int)v27,
      ppv);
LABEL_55:
    NCoreLibrary::TString::~TString((NCoreLibrary::TString *)&v51);
    goto LABEL_39;
  }
  v27 = (*(__int64 (__fastcall **)(LPVOID, unsigned __int16 *))(*(_QWORD *)v44 + 144LL))(v44, v52);
  if ( v27 < 0 )
  {
    v29 = 398;
    goto LABEL_54;
  }
  v30 = (*(__int64 (__fastcall **)(LPVOID, Helper *))(*(_QWORD *)v44 + 24LL))(v44, this);
  v27 = v30;
  if ( v30 < 0 )
  {
    if ( v30 != -2147023673 )
    {
      v29 = 411;
      goto LABEL_54;
    }
    goto LABEL_89;
  }
  v47 = 0;
  v27 = (*(__int64 (__fastcall **)(LPVOID, __int64 *))(*(_QWORD *)v44 + 216LL))(v44, &v47);
  if ( v27 < 0 )
  {
    v31 = 418;
    goto LABEL_63;
  }
  v46 = 0;
  v27 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v47 + 56LL))(v47, &v46);
  if ( v27 < 0 )
  {
    v31 = 422;
LABEL_63:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v31,
      (unsigned int)"clientcore\\windows\\core\\ntgdi\\icm\\colorui\\ui\\helper.cpp",
      (const char *)(unsigned int)v27,
      ppv);
    if ( v47 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v47 + 16LL))(v47);
    goto LABEL_55;
  }
  v32 = (Helper::SelectedFiles *)operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
  v33 = v32;
  if ( !v32 )
  {
LABEL_70:
    if ( v47 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v47 + 16LL))(v47);
    NCoreLibrary::TString::~TString((NCoreLibrary::TString *)&v51);
    if ( v26 )
      LocalFree(v26);
    goto LABEL_112;
  }
  *(_DWORD *)v32 = 0;
  *((_QWORD *)v32 + 1) = 0;
  *((_DWORD *)v32 + 4) = 0;
  v34 = operator new[](saturated_mul(v46, 8u));
  *((_QWORD *)v33 + 1) = v34;
  if ( !v34 )
  {
    Helper::SelectedFiles::~SelectedFiles(v33);
    operator delete(v33);
    goto LABEL_70;
  }
  v35 = 0;
  v36 = 0;
  if ( !v46 )
  {
LABEL_87:
    *(_DWORD *)v33 = v35;
    v41 = v47;
    *a4 = v33;
    if ( v41 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
LABEL_89:
    NCoreLibrary::TString::~TString((NCoreLibrary::TString *)&v51);
    if ( v26 )
      LocalFree(v26);
    NCoreLibrary::TString::~TString((NCoreLibrary::TString *)&v48);
    (*(void (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)v16 + 64LL))(v16, v17);
    if ( v16 )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v16 + 16LL))(v16);
    if ( v45 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 16LL))(v45);
    if ( v44 )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v44 + 16LL))(v44);
    return 0;
  }
  while ( 1 )
  {
    hMem = 0;
    v37 = (*(__int64 (__fastcall **)(__int64, _QWORD, HLOCAL *))(*(_QWORD *)v47 + 64LL))(v47, v36, &hMem);
    v38 = v37;
    if ( v37 < 0 )
      break;
    Src = 0;
    if ( (*(int (__fastcall **)(HLOCAL, __int64, void **))(*(_QWORD *)hMem + 40LL))(hMem, 2147844096LL, &Src) >= 0 )
    {
      v39 = -1;
      do
        ++v39;
      while ( *((_WORD *)Src + v39) );
      v40 = 2 * v39;
      if ( !is_mul_ok(v39, 2u) )
        v40 = -1;
      *(_QWORD *)(*((_QWORD *)v33 + 1) + 8LL * v36) = operator new[](v40);
      memcpy_0(*(void **)(*((_QWORD *)v33 + 1) + 8LL * v36), Src, 2 * v39);
      ++v35;
    }
    if ( Src )
      CoTaskMemFree(Src);
    if ( hMem )
      (*(void (__fastcall **)(HLOCAL))(*(_QWORD *)hMem + 16LL))(hMem);
    if ( ++v36 >= v46 )
      goto LABEL_87;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x1B9,
    (unsigned int)"clientcore\\windows\\core\\ntgdi\\icm\\colorui\\ui\\helper.cpp",
    (const char *)(unsigned int)v37,
    ppv);
  if ( hMem )
    (*(void (__fastcall **)(HLOCAL))(*(_QWORD *)hMem + 16LL))(hMem);
  Helper::SelectedFiles::~SelectedFiles(v33);
  operator delete(v33);
  if ( v47 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v47 + 16LL))(v47);
  NCoreLibrary::TString::~TString((NCoreLibrary::TString *)&v51);
  if ( v26 )
    LocalFree(v26);
  NCoreLibrary::TString::~TString((NCoreLibrary::TString *)&v48);
  (*(void (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)v16 + 64LL))(v16, v17);
  if ( v16 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v16 + 16LL))(v16);
  if ( v45 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 16LL))(v45);
  if ( v44 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v44 + 16LL))(v44);
  return v38;
}

```

## disassembly

```asm
0x180014b78  mov     [rsp-8+arg_18], r9
0x180014b7d  push    rbp
0x180014b7e  push    rbx
0x180014b7f  push    rsi
0x180014b80  push    rdi
0x180014b81  push    r12
0x180014b83  push    r13
0x180014b85  push    r14
0x180014b87  push    r15
0x180014b89  lea     rbp, [rsp-1Fh]
0x180014b8e  sub     rsp, 98h
0x180014b95  xor     edi, edi
0x180014b97  lea     rax, [rbp+57h+var_A0]
0x180014b9b  mov     esi, r8d
0x180014b9e  mov     [rbp+57h+var_A0], rdi
0x180014ba2  mov     r12, rdx
0x180014ba5  mov     qword ptr [rsp+0D0h+ppv], rax; int
0x180014baa  mov     r13, rcx
0x180014bad  lea     r9, _GUID_d57c7288_d4ad_4768_be02_9d969532d960; riid
0x180014bb4  lea     r14d, [rdi+1]
0x180014bb8  xor     edx, edx; pUnkOuter
0x180014bba  mov     r8d, r14d; dwClsContext
0x180014bbd  lea     rcx, CLSID_FileOpenDialog; rclsid
0x180014bc4  call    cs:__imp_CoCreateInstance
0x180014bca  mov     ebx, eax
0x180014bcc  test    eax, eax
0x180014bce  jns     short loc_180014C04
0x180014bd0  mov     rcx, [rbp+5Fh]; this
0x180014bd4  lea     r8, aClientcoreWind; "clientcore\\windows\\core\\ntgdi\\icm\\"...
0x180014bdb  mov     r9d, eax; char *
0x180014bde  mov     edx, 15Eh; void *
0x180014be3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014be8  mov     rcx, [rbp+57h+var_A0]
0x180014bec  test    rcx, rcx
0x180014bef  jz      short loc_180014BFD
0x180014bf1  mov     rdx, [rcx]
0x180014bf4  mov     rax, [rdx+10h]
0x180014bf8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014bfd  mov     eax, ebx
0x180014bff  jmp     loc_18001540D
0x180014c04  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180014c0b  mov     [rbp+57h+var_58], edi
0x180014c0e  mov     ecx, 28h ; '('; unsigned __int64
0x180014c13  mov     [rbp+57h+var_98], rdi
0x180014c17  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180014c1c  mov     rbx, rax
0x180014c1f  test    rax, rax
0x180014c22  jz      loc_1800153C2
0x180014c28  lea     r9, ??_7AddColorProfileDialogEventHandler@Helper@@6BIFileDialogEvents@@@; const Helper::AddColorProfileDialogEventHandler::`vftable'{for `IFileDialogEvents'}
0x180014c2f  mov     [rbx+10h], r14d
0x180014c33  mov     [rax], r9
0x180014c36  lea     r8, [rbp+57h+var_98]
0x180014c3a  lea     rax, ??_7AddColorProfileDialogEventHandler@Helper@@6BIFileDialogControlEvents@@@; const Helper::AddColorProfileDialogEventHandler::`vftable'{for `IFileDialogControlEvents'}
0x180014c41  mov     [rbx+18h], r13
0x180014c45  mov     [rbx+8], rax
0x180014c49  lea     rdx, _GUID_973510db_7d7f_452b_8975_74a85828d354
0x180014c50  mov     rax, [r9]
0x180014c53  mov     rcx, rbx
0x180014c56  mov     [rbx+20h], r12
0x180014c5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014c5f  mov     r15d, eax
0x180014c62  mov     rcx, rbx
0x180014c65  mov     rax, [rbx]
0x180014c68  mov     rax, [rax+10h]
0x180014c6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014c71  test    r15d, r15d
0x180014c74  js      loc_1800153C8
0x180014c7a  mov     rcx, [rbp+57h+var_A0]
0x180014c7e  lea     r8, [rbp+57h+var_58]
0x180014c82  mov     rdx, [rbp+57h+var_98]
0x180014c86  mov     rax, [rcx]
0x180014c89  mov     rax, [rax+38h]
0x180014c8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014c92  mov     ebx, eax
0x180014c94  test    eax, eax
0x180014c96  jns     short loc_180014CDE
0x180014c98  mov     rcx, [rbp+5Fh]; this
0x180014c9c  lea     r8, aClientcoreWind; "clientcore\\windows\\core\\ntgdi\\icm\\"...
0x180014ca3  mov     r9d, eax; char *
0x180014ca6  mov     edx, 166h; void *
0x180014cab  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014cb0  mov     rcx, [rbp+57h+var_98]
0x180014cb4  test    rcx, rcx
0x180014cb7  jz      short loc_180014CC5
0x180014cb9  mov     rdx, [rcx]
0x180014cbc  mov     rax, [rdx+10h]
0x180014cc0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014cc5  mov     rcx, [rbp+57h+var_A0]
0x180014cc9  test    rcx, rcx
0x180014ccc  jz      loc_180014BFD
0x180014cd2  mov     rax, [rcx]
0x180014cd5  mov     rax, [rax+10h]
0x180014cd9  jmp     loc_180014BF8
0x180014cde  mov     rcx, [rbp+57h+var_A0]
0x180014ce2  mov     rbx, rcx
0x180014ce5  test    rcx, rcx
0x180014ce8  jz      short loc_180014CFA
0x180014cea  mov     rax, [rcx]
0x180014ced  mov     rax, [rax+8]
0x180014cf1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014cf6  mov     rcx, [rbp+57h+var_A0]
0x180014cfa  mov     rax, [rcx]
0x180014cfd  mov     edx, 1A40h
0x180014d02  mov     r14d, [rbp+57h+var_58]
0x180014d06  mov     rax, [rax+48h]
0x180014d0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014d0f  mov     edi, eax
0x180014d11  test    eax, eax
0x180014d13  jns     short loc_180014D84
0x180014d15  mov     rcx, [rbp+5Fh]; this
0x180014d19  lea     r8, aClientcoreWind; "clientcore\\windows\\core\\ntgdi\\icm\\"...
0x180014d20  mov     r9d, eax; char *
0x180014d23  mov     edx, 16Ch; void *
0x180014d28  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014d2d  mov     rcx, [rbx]
0x180014d30  mov     rax, [rcx+40h]
0x180014d34  mov     edx, r14d
0x180014d37  mov     rcx, rbx
0x180014d3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014d3f  test    rbx, rbx
0x180014d42  jz      short loc_180014D53
0x180014d44  mov     rax, [rbx]
0x180014d47  mov     rcx, rbx
0x180014d4a  mov     rax, [rax+10h]
0x180014d4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014d53  mov     rcx, [rbp+57h+var_98]
0x180014d57  test    rcx, rcx
0x180014d5a  jz      short loc_180014D68
0x180014d5c  mov     rax, [rcx]
0x180014d5f  mov     rax, [rax+10h]
0x180014d63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014d68  mov     rcx, [rbp+57h+var_A0]
0x180014d6c  test    rcx, rcx
0x180014d6f  jz      short loc_180014D7D
0x180014d71  mov     rax, [rcx]
0x180014d74  mov     rax, [rax+10h]
0x180014d78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014d7d  mov     eax, edi
0x180014d7f  jmp     loc_18001540D
0x180014d84  lea     rax, ?gszNullState@TString@NCoreLibrary@@0PAGA; ushort near * NCoreLibrary::TString::gszNullState
0x180014d8b  mov     [rbp+57h+var_80], 67727473h
0x180014d92  mov     r8d, esi; unsigned int
0x180014d95  mov     [rbp+57h+psz], rax
0x180014d99  mov     rdx, r12; HINSTANCE
0x180014d9c  lea     rcx, [rbp+57h+var_80]; this
0x180014da0  call    ?LoadStringFromRC@TString@NCoreLibrary@@QEAAJPEAUHINSTANCE__@@I@Z; NCoreLibrary::TString::LoadStringFromRC(HINSTANCE__ *,uint)
0x180014da5  xor     esi, esi
0x180014da7  mov     edi, eax
0x180014da9  test    eax, eax
0x180014dab  jns     short loc_180014DD3
0x180014dad  mov     rcx, [rbp+5Fh]; this
0x180014db1  lea     r8, aClientcoreWind; "clientcore\\windows\\core\\ntgdi\\icm\\"...
0x180014db8  mov     r9d, eax; char *
0x180014dbb  mov     edx, 171h; void *
0x180014dc0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014dc5  lea     rcx, [rbp+57h+var_80]; this
0x180014dc9  call    ??1TString@NCoreLibrary@@QEAA@XZ; NCoreLibrary::TString::~TString(void)
0x180014dce  jmp     loc_180014D2D
0x180014dd3  mov     rcx, [rbp+57h+psz]; psz
0x180014dd7  call    cs:__imp_SysAllocString
0x180014ddd  mov     rdi, rax
0x180014de0  mov     r15d, 8007000Eh
0x180014de6  test    rax, rax
0x180014de9  jz      loc_180015354
0x180014def  mov     rcx, rax; pbstr
0x180014df2  call    cs:__imp_SysStringLen
0x180014df8  mov     ecx, esi
0x180014dfa  test    eax, eax
0x180014dfc  jz      short loc_180014E18
0x180014dfe  mov     r8d, ecx
0x180014e01  mov     edx, 7Ch ; '|'
0x180014e06  cmp     dx, [rdi+r8*2]
0x180014e0b  jnz     short loc_180014E12
0x180014e0d  mov     [rdi+r8*2], si
0x180014e12  inc     ecx
0x180014e14  cmp     ecx, eax
0x180014e16  jb      short loc_180014DFE
0x180014e18  lea     r8, [rbp+57h+var_90]
0x180014e1c  mov     [rbp+57h+hMem], rsi
0x180014e20  lea     rdx, [rbp+57h+hMem]
0x180014e24  mov     [rbp+57h+var_90], esi
0x180014e27  mov     rcx, rdi
0x180014e2a  call    ?FilterSpecFromMultiSz@Helper@@YAJPEBGAEAV?$unique_ptr@$$BY0A@U_COMDLG_FILTERSPEC@@U?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@PEAI@Z; Helper::FilterSpecFromMultiSz(ushort const *,wistd::unique_ptr<_COMDLG_FILTERSPEC [0],wil::function_deleter<void * (*)(void *),&LocalFree(void *)>> &,uint *)
0x180014e2f  mov     edi, eax
0x180014e31  test    eax, eax
0x180014e33  jns     short loc_180014E71
0x180014e35  mov     rcx, [rbp+5Fh]; this
0x180014e39  lea     r8, aClientcoreWind; "clientcore\\windows\\core\\ntgdi\\icm\\"...
0x180014e40  mov     r9d, eax; char *
0x180014e43  mov     edx, 181h; void *
0x180014e48  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014e4d  mov     rcx, [rbp+57h+hMem]; hMem
0x180014e51  test    rcx, rcx
0x180014e54  jz      short loc_180014E5C
0x180014e56  call    cs:__imp_LocalFree
0x180014e5c  lea     rcx, [rbp+57h+var_80]; this
0x180014e60  call    ??1TString@NCoreLibrary@@QEAA@XZ; NCoreLibrary::TString::~TString(void)
0x180014e65  mov     rax, [rbx]
0x180014e68  mov     rax, [rax+40h]
0x180014e6c  jmp     loc_180014D34
0x180014e71  mov     rcx, [rbp+57h+var_A0]
0x180014e75  mov     rdi, [rbp+57h+hMem]
0x180014e79  mov     edx, [rbp+57h+var_90]
0x180014e7c  mov     r8, rdi
0x180014e7f  mov     rax, [rcx]
0x180014e82  mov     rax, [rax+20h]
0x180014e86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014e8b  mov     esi, eax
0x180014e8d  test    eax, eax
0x180014e8f  jns     loc_180014F1B
0x180014e95  mov     edx, 183h; void *
0x180014e9a  mov     rcx, [rbp+5Fh]; this
0x180014e9e  lea     r8, aClientcoreWind; "clientcore\\windows\\core\\ntgdi\\icm\\"...
0x180014ea5  mov     r9d, esi; char *
0x180014ea8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014ead  test    rdi, rdi
0x180014eb0  jz      short loc_180014EBB
0x180014eb2  mov     rcx, rdi; hMem
0x180014eb5  call    cs:__imp_LocalFree
0x180014ebb  lea     rcx, [rbp+57h+var_80]; this
0x180014ebf  call    ??1TString@NCoreLibrary@@QEAA@XZ; NCoreLibrary::TString::~TString(void)
0x180014ec4  mov     rax, [rbx]
0x180014ec7  mov     edx, r14d
0x180014eca  mov     rcx, rbx
0x180014ecd  mov     rax, [rax+40h]
0x180014ed1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014ed6  test    rbx, rbx
0x180014ed9  jz      short loc_180014EEA
0x180014edb  mov     rax, [rbx]
0x180014ede  mov     rcx, rbx
0x180014ee1  mov     rax, [rax+10h]
0x180014ee5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014eea  mov     rcx, [rbp+57h+var_98]
0x180014eee  test    rcx, rcx
0x180014ef1  jz      short loc_180014EFF
0x180014ef3  mov     rax, [rcx]
0x180014ef6  mov     rax, [rax+10h]
0x180014efa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014eff  mov     rcx, [rbp+57h+var_A0]
0x180014f03  test    rcx, rcx
0x180014f06  jz      short loc_180014F14
0x180014f08  mov     rax, [rcx]
0x180014f0b  mov     rax, [rax+10h]
0x180014f0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014f14  mov     eax, esi
0x180014f16  jmp     loc_18001540D
0x180014f1b  mov     rcx, [rbp+57h+var_A0]
0x180014f1f  mov     edx, 1
0x180014f24  mov     rax, [rcx]
0x180014f27  mov     rax, [rax+28h]
0x180014f2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014f30  mov     esi, eax
0x180014f32  test    eax, eax
0x180014f34  jns     short loc_180014F40
0x180014f36  mov     edx, 186h
0x180014f3b  jmp     loc_180014E9A
0x180014f40  mov     rcx, [rbp+57h+var_A0]
0x180014f44  lea     rdx, aIcmIccGmmpCamp; "*.icm;*.icc;*.gmmp;*.camp;*.cdmp"
0x180014f4b  mov     rax, [rcx]
0x180014f4e  mov     rax, [rax+0B0h]
0x180014f55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014f5a  mov     esi, eax
0x180014f5c  test    eax, eax
0x180014f5e  jns     short loc_180014F6A
0x180014f60  mov     edx, 189h
0x180014f65  jmp     loc_180014E9A
0x180014f6a  lea     rax, ?gszNullState@TString@NCoreLibrary@@0PAGA; ushort near * NCoreLibrary::TString::gszNullState
0x180014f71  mov     [rbp+57h+var_68], 67727473h
0x180014f78  mov     r8d, 712h; unsigned int
0x180014f7e  mov     [rbp+57h+var_60], rax
0x180014f82  mov     rdx, r12; HINSTANCE
0x180014f85  lea     rcx, [rbp+57h+var_68]; this
0x180014f89  call    ?LoadStringFromRC@TString@NCoreLibrary@@QEAAJPEAUHINSTANCE__@@I@Z; NCoreLibrary::TString::LoadStringFromRC(HINSTANCE__ *,uint)
0x180014f8e  xor     r12d, r12d
0x180014f91  mov     esi, eax
0x180014f93  test    eax, eax
0x180014f95  jns     short loc_180014FBD
0x180014f97  mov     edx, 18Dh; void *
0x180014f9c  mov     rcx, [rbp+5Fh]; this
0x180014fa0  lea     r8, aClientcoreWind; "clientcore\\windows\\core\\ntgdi\\icm\\"...
0x180014fa7  mov     r9d, esi; char *
0x180014faa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014faf  lea     rcx, [rbp+57h+var_68]; this
0x180014fb3  call    ??1TString@NCoreLibrary@@QEAA@XZ; NCoreLibrary::TString::~TString(void)
0x180014fb8  jmp     loc_180014EAD
0x180014fbd  mov     rcx, [rbp+57h+var_A0]
0x180014fc1  mov     rdx, [rbp+57h+var_60]
0x180014fc5  mov     rax, [rcx]
0x180014fc8  mov     rax, [rax+90h]
0x180014fcf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014fd4  mov     esi, eax
0x180014fd6  test    eax, eax
0x180014fd8  jns     short loc_180014FE1
0x180014fda  mov     edx, 18Eh
0x180014fdf  jmp     short loc_180014F9C
0x180014fe1  mov     rcx, [rbp+57h+var_A0]
0x180014fe5  mov     rdx, r13
0x180014fe8  mov     rax, [rcx]
0x180014feb  mov     rax, [rax+18h]
0x180014fef  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
