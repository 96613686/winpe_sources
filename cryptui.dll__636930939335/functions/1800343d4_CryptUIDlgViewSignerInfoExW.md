# CryptUIDlgViewSignerInfoExW

- ea: `0x1800343d4`
- end: `0x180034861`
- name: `CryptUIDlgViewSignerInfoExW`
- size: `1165`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180034870`
- `0x180036160`

## callees

- `0x180001f66`
- `0x180008904`
- `0x180011860`
- `0x1800333f0`
- `0x1800335e0`
- `0x180033600`
- `0x1800343d4`
- `0x18003e582`
- `0x18003e5c0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180034508`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180034508`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180034818`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180034818`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180034446`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003480f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180034446`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003480f`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800347a3`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800347a3`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800347e7`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800347e7`
- `CRYPT32!CertOpenStore` at `0x1800344c6`
- `CRYPT32!CertOpenStore` at `0x180034686`
- `CRYPT32!CertOpenStore` at `0x1800344c6`
- `CRYPT32!CertOpenStore` at `0x180034686`
- `CRYPT32!CertCloseStore` at `0x1800347fb`
- `CRYPT32!CertCloseStore` at `0x1800347fb`
- `CRYPT32!CryptQueryObject` at `0x180034649`
- `CRYPT32!CryptQueryObject` at `0x180034649`
- `USER32!GetDesktopWindow` at `0x18003476c`
- `USER32!GetDesktopWindow` at `0x18003476c`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
_BOOL8 __fastcall CryptUIDlgViewSignerInfoExW(__int64 a1)
{
  _QWORD *v3; // rax
  _DWORD *v4; // rsi
  BOOL v5; // ebx
  unsigned int v6; // eax
  PROPSHEETPAGEW_V4 *v7; // rax
  PROPSHEETPAGEW_V4 *v8; // rdi
  HINSTANCE v9; // rbx
  unsigned int v10; // r15d
  __int64 v11; // r14
  HCERTSTORE v12; // rbx
  __int64 v13; // rcx
  UINT v14; // r14d
  HWND DesktopWindow; // rax
  WCHAR *v16; // rax
  HMODULE LibraryA; // rbx
  __int64 v18; // rsi
  void *ppvContext; // [rsp+60h] [rbp-A0h] BYREF
  HCERTSTORE v20; // [rsp+68h] [rbp-98h] BYREF
  __int64 v21; // [rsp+70h] [rbp-90h] BYREF
  struct _PROPSHEETHEADERW_V2 v22; // [rsp+80h] [rbp-80h] BYREF
  _QWORD v23[12]; // [rsp+E0h] [rbp-20h] BYREF
  int v24; // [rsp+140h] [rbp+40h]
  int v25; // [rsp+148h] [rbp+48h]
  __int64 v26; // [rsp+150h] [rbp+50h]
  int v27; // [rsp+158h] [rbp+58h]
  __int64 v28; // [rsp+160h] [rbp+60h]
  int v29; // [rsp+170h] [rbp+70h] BYREF
  char v30[28]; // [rsp+174h] [rbp+74h] BYREF
  void *v31; // [rsp+190h] [rbp+90h]
  _DWORD *v32; // [rsp+1D0h] [rbp+D0h] BYREF
  char v33[32]; // [rsp+1D8h] [rbp+D8h] BYREF
  HCERTSTORE hCertStore; // [rsp+1F8h] [rbp+F8h]
  __int64 v35; // [rsp+200h] [rbp+100h]
  int v36; // [rsp+208h] [rbp+108h]
  int v37; // [rsp+294h] [rbp+194h]
  int v38; // [rsp+298h] [rbp+198h]
  WCHAR Buffer[768]; // [rsp+2A0h] [rbp+1A0h] BYREF

  memset_0(&v32, 0, 0xD0u);
  if ( !(unsigned int)CommonInit() )
    return 0;
  v20 = 0;
  ppvContext = 0;
  v3 = *(_QWORD **)(a1 + 8);
  v4 = (_DWORD *)*v3;
  if ( *(_DWORD *)*v3 != 96 )
  {
    SetLastError(0x80070057);
    wil::details::unique_storage<wil::details::resource_policy<_CTL_CONTEXT *,int (*)(_CTL_CONTEXT const *),&int CertFreeCTLContext(_CTL_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CTL_CONTEXT *,_CTL_CONTEXT *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_CTL_CONTEXT *,int (*)(_CTL_CONTEXT const *),&int CertFreeCTLContext(_CTL_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CTL_CONTEXT *,_CTL_CONTEXT *,0,std::nullptr_t>>(&ppvContext);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CertCloseStoreNoParam_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v20);
    return 0;
  }
  memset_0(v33, 0, 0xC8u);
  v32 = v4;
  if ( (int)v4[4] >= 0 )
  {
    if ( (v4[4] & 0x40000000) != 0 )
      v38 = v4[14];
  }
  else
  {
    v35 = *((_QWORD *)v4 + 7);
  }
  v36 = 0;
  hCertStore = CertOpenStore((LPCSTR)1, 0x10001u, 0, 0, *((const void **)v4 + 5));
  if ( hCertStore )
  {
    v5 = 0;
    v6 = v4[20];
    if ( v6 <= 0xFF )
    {
      v7 = (PROPSHEETPAGEW_V4 *)LocalAlloc(0x40u, 104LL * (v6 + 3));
      v8 = v7;
      if ( v7 )
      {
        memset_0(v7, 0, 104LL * (unsigned int)(v4[20] + 3));
        *(_QWORD *)&v8->dwSize = 104;
        v9 = HinstDll;
        v8->hInstance = HinstDll;
        v8->pszTemplate = (LPCWSTR)141;
        v8->hIcon = 0;
        v8->pszTitle = 0;
        v8->pfnDlgProc = (DLGPROC)ViewPageSignerGeneral;
        v8->lParam = (LPARAM)&v32;
        v8->pfnCallback = 0;
        v8->pcRefParent = 0;
        v10 = 1;
        if ( (v4[4] & 1) == 0 && *((_QWORD *)v4 + 4) )
        {
          *(_QWORD *)&v8[1].dwSize = 104;
          v8[1].hInstance = v9;
          v8[1].pszTemplate = (LPCWSTR)142;
          v8[1].hIcon = 0;
          v8[1].pszTitle = 0;
          v8[1].pfnDlgProc = (DLGPROC)ViewPageSignerAdvanced;
          v8[1].lParam = (LPARAM)&v32;
          v8[1].pfnCallback = 0;
          v8[1].pcRefParent = 0;
          v10 = 2;
        }
        memset_0(v30, 0, 0x54u);
        v29 = 88;
        memset_0(v23, 0, 0x88u);
        if ( *(_DWORD *)a1 == 2 )
        {
          v11 = *(_QWORD *)(*(_QWORD *)(a1 + 8) + 8LL);
          if ( CryptQueryObject(
                 1u,
                 *(const void **)(*(_QWORD *)(v11 + 16) + 8LL * *(unsigned int *)(v11 + 12)),
                 4u,
                 0xEu,
                 0,
                 0,
                 0,
                 0,
                 0,
                 0,
                 (const void **)&ppvContext) )
          {
            v31 = ppvContext;
            v23[0] = &v29;
            v24 = 1;
            v12 = CertOpenStore((LPCSTR)1, 0x10001u, 0, 0, *((const void **)ppvContext + 5));
            v20 = v12;
            v21 = 0;
            __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CertCloseStoreNoParam_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v21);
            v23[3] = v12;
            v26 = *(_QWORD *)(v11 + 32);
            v25 = *(_DWORD *)(v11 + 24);
            v28 = *(_QWORD *)(v11 + 48);
            v27 = *(_DWORD *)(v11 + 40);
            v13 = v10;
            *(_QWORD *)&v8[v13].dwSize = 104;
            v9 = HinstDll;
            v8[v13].hInstance = HinstDll;
            v8[v13].pszTemplate = (LPCWSTR)149;
            v8[v13].hIcon = 0;
            v8[v13].pszTitle = 0;
            v8[v13].pfnDlgProc = (DLGPROC)ViewPageCatalogEntries;
            v8[v13].lParam = (LPARAM)v23;
            v8[v13].pfnCallback = 0;
            v8[v13].pcRefParent = 0;
            ++v10;
          }
          else
          {
            v9 = HinstDll;
          }
        }
        memcpy_0(&v8[v10], *((const void **)v4 + 11), 104LL * (unsigned int)v4[20]);
        v14 = v10 + v4[20];
        memset_0(&v22, 0, sizeof(v22));
        v22.dwSize = 96;
        v22.dwFlags = 392;
        DesktopWindow = (HWND)*((_QWORD *)v4 + 1);
        if ( !DesktopWindow )
        {
          DesktopWindow = GetDesktopWindow();
          v9 = HinstDll;
        }
        v22.hwndParent = DesktopWindow;
        v22.hInstance = v9;
        v22.hIcon = 0;
        v16 = (WCHAR *)*((_QWORD *)v4 + 3);
        if ( !v16 )
        {
          LoadStringW(v9, 0xCCBu, Buffer, 768);
          v16 = Buffer;
        }
        v22.pszCaption = v16;
        v22.nPages = v14;
        v22.nStartPage = 0;
        v22.ppsp = v8;
        v22.pfnCallback = (PFNPROPSHEETCALLBACK)HidePropSheetCancelButtonCallback;
        LibraryA = (HMODULE)IsolationAwareLoadLibraryA();
        if ( LibraryA )
        {
          v18 = CryptUIPropertySheetW(&v22);
          FreeLibrary(LibraryA);
        }
        else
        {
          v18 = 0;
        }
        CertCloseStore(hCertStore, 0);
        if ( v37 )
          SetLastError(0x4C7u);
        LocalFree(v8);
        v5 = v18 >= 1;
      }
    }
    wil::details::unique_storage<wil::details::resource_policy<_CTL_CONTEXT *,int (*)(_CTL_CONTEXT const *),&int CertFreeCTLContext(_CTL_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CTL_CONTEXT *,_CTL_CONTEXT *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_CTL_CONTEXT *,int (*)(_CTL_CONTEXT const *),&int CertFreeCTLContext(_CTL_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CTL_CONTEXT *,_CTL_CONTEXT *,0,std::nullptr_t>>(&ppvContext);
  }
  else
  {
    wil::details::unique_storage<wil::details::resource_policy<_CTL_CONTEXT *,int (*)(_CTL_CONTEXT const *),&int CertFreeCTLContext(_CTL_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CTL_CONTEXT *,_CTL_CONTEXT *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_CTL_CONTEXT *,int (*)(_CTL_CONTEXT const *),&int CertFreeCTLContext(_CTL_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CTL_CONTEXT *,_CTL_CONTEXT *,0,std::nullptr_t>>(&ppvContext);
    v5 = 0;
  }
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CertCloseStoreNoParam_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v20);
  return v5;
}

```

## disassembly

```asm
0x1800343d4  push    rbp
0x1800343d6  push    rbx
0x1800343d7  push    rsi
0x1800343d8  push    rdi
0x1800343d9  push    r12
0x1800343db  push    r13
0x1800343dd  push    r14
0x1800343df  push    r15
0x1800343e1  lea     rbp, [rsp-7B8h]
0x1800343e9  sub     rsp, 8B8h
0x1800343f0  mov     rax, cs:__security_cookie
0x1800343f7  xor     rax, rsp
0x1800343fa  mov     [rbp+7F0h+var_50], rax
0x180034401  mov     r14, rcx
0x180034404  xor     edx, edx; Val
0x180034406  mov     r8d, 0D0h; Size
0x18003440c  lea     rcx, [rbp+7F0h+var_720]; void *
0x180034413  call    memset_0
0x180034418  call    CommonInit
0x18003441d  xor     r12d, r12d
0x180034420  test    eax, eax
0x180034422  jnz     short loc_18003442B
0x180034424  xor     eax, eax
0x180034426  jmp     loc_18003483E
0x18003442b  mov     [rsp+8F0h+var_888], r12
0x180034430  mov     [rsp+8F0h+var_890], r12
0x180034435  mov     rax, [r14+8]
0x180034439  mov     rsi, [rax]
0x18003443c  cmp     dword ptr [rsi], 60h ; '`'
0x18003443f  jz      short loc_180034464
0x180034441  mov     ecx, 80070057h; dwErrCode
0x180034446  call    cs:__imp_SetLastError
0x18003444c  nop
0x18003444d  lea     rcx, [rsp+8F0h+var_890]
0x180034452  call    ??1?$unique_storage@U?$resource_policy@PEAU_CTL_CONTEXT@@P6AHPEBU1@@Z$1?CertFreeCTLContext@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_CTL_CONTEXT *,int (*)(_CTL_CONTEXT const *),&CertFreeCTLContext(_CTL_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CTL_CONTEXT *,_CTL_CONTEXT *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_CTL_CONTEXT *,int (*)(_CTL_CONTEXT const *),&CertFreeCTLContext(_CTL_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CTL_CONTEXT *,_CTL_CONTEXT *,0,std::nullptr_t>>(void)
0x180034457  nop
0x180034458  lea     rcx, [rsp+8F0h+var_888]
0x18003445d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CertCloseStoreNoParam@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180034462  jmp     short loc_180034424
0x180034464  xor     edx, edx; Val
0x180034466  mov     r8d, 0C8h; Size
0x18003446c  lea     rcx, [rbp+7F0h+var_718]; void *
0x180034473  call    memset_0
0x180034478  mov     [rbp+7F0h+var_720], rsi
0x18003447f  cmp     [rsi+10h], r12d
0x180034483  jge     short loc_180034492
0x180034485  mov     rax, [rsi+38h]
0x180034489  mov     [rbp+7F0h+var_6F0], rax
0x180034490  jmp     short loc_1800344A4
0x180034492  test    dword ptr [rsi+10h], 40000000h
0x180034499  jz      short loc_1800344A4
0x18003449b  mov     eax, [rsi+38h]
0x18003449e  mov     [rbp+7F0h+var_658], eax
0x1800344a4  mov     [rbp+7F0h+var_6E8], r12d
0x1800344ab  mov     rax, [rsi+28h]
0x1800344af  mov     [rsp+8F0h+pvPara], rax; pvPara
0x1800344b4  xor     r9d, r9d; dwFlags
0x1800344b7  xor     r8d, r8d; hCryptProv
0x1800344ba  mov     edx, 10001h; dwEncodingType
0x1800344bf  lea     r13d, [r9+1]
0x1800344c3  mov     ecx, r13d; lpszStoreProvider
0x1800344c6  call    cs:__imp_CertOpenStore
0x1800344cc  mov     [rbp+7F0h+hCertStore], rax
0x1800344d3  test    rax, rax
0x1800344d6  jnz     short loc_1800344EB
0x1800344d8  lea     rcx, [rsp+8F0h+var_890]
0x1800344dd  call    ??1?$unique_storage@U?$resource_policy@PEAU_CTL_CONTEXT@@P6AHPEBU1@@Z$1?CertFreeCTLContext@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_CTL_CONTEXT *,int (*)(_CTL_CONTEXT const *),&CertFreeCTLContext(_CTL_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CTL_CONTEXT *,_CTL_CONTEXT *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_CTL_CONTEXT *,int (*)(_CTL_CONTEXT const *),&CertFreeCTLContext(_CTL_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CTL_CONTEXT *,_CTL_CONTEXT *,0,std::nullptr_t>>(void)
0x1800344e2  nop
0x1800344e3  mov     ebx, r12d
0x1800344e6  jmp     loc_180034832
0x1800344eb  mov     ebx, r12d
0x1800344ee  mov     eax, [rsi+50h]
0x1800344f1  cmp     eax, 0FFh
0x1800344f6  ja      loc_180034827
0x1800344fc  lea     ecx, [rax+3]
0x1800344ff  imul    rdx, rcx, 68h ; 'h'; uBytes
0x180034503  mov     ecx, 40h ; '@'; uFlags
0x180034508  call    cs:__imp_LocalAlloc
0x18003450e  mov     rdi, rax
0x180034511  test    rax, rax
0x180034514  jz      loc_180034827
0x18003451a  mov     ecx, [rsi+50h]
0x18003451d  add     ecx, 3
0x180034520  imul    r8, rcx, 68h ; 'h'; Size
0x180034524  xor     edx, edx; Val
0x180034526  mov     rcx, rax; void *
0x180034529  call    memset_0
0x18003452e  mov     qword ptr [rdi], 68h ; 'h'
0x180034535  mov     rbx, cs:?HinstDll@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * HinstDll
0x18003453c  mov     [rdi+8], rbx
0x180034540  mov     qword ptr [rdi+10h], 8Dh
0x180034548  mov     [rdi+18h], r12
0x18003454c  mov     [rdi+20h], r12
0x180034550  lea     rax, ?ViewPageSignerGeneral@@YA_JPEAUHWND__@@I_K_J@Z; ViewPageSignerGeneral(HWND__ *,uint,unsigned __int64,__int64)
0x180034557  mov     [rdi+28h], rax
0x18003455b  lea     rax, [rbp+7F0h+var_720]
0x180034562  mov     [rdi+30h], rax
0x180034566  mov     [rdi+38h], r12
0x18003456a  mov     [rdi+40h], r12
0x18003456e  mov     r15d, r13d
0x180034571  test    [rsi+10h], r13b
0x180034575  jnz     short loc_1800345CF
0x180034577  cmp     [rsi+20h], r12
0x18003457b  jz      short loc_1800345CF
0x18003457d  mov     qword ptr [rdi+68h], 68h ; 'h'
0x180034585  mov     [rdi+70h], rbx
0x180034589  mov     qword ptr [rdi+78h], 8Eh
0x180034591  mov     [rdi+80h], r12
0x180034598  mov     [rdi+88h], r12
0x18003459f  lea     rax, ?ViewPageSignerAdvanced@@YA_JPEAUHWND__@@I_K_J@Z; ViewPageSignerAdvanced(HWND__ *,uint,unsigned __int64,__int64)
0x1800345a6  mov     [rdi+90h], rax
0x1800345ad  lea     rax, [rbp+7F0h+var_720]
0x1800345b4  mov     [rdi+98h], rax
0x1800345bb  mov     [rdi+0A0h], r12
0x1800345c2  mov     [rdi+0A8h], r12
0x1800345c9  mov     r15d, 2
0x1800345cf  xor     edx, edx; Val
0x1800345d1  lea     r8d, [rdx+54h]; Size
0x1800345d5  lea     rcx, [rbp+7F0h+var_77C]; void *
0x1800345d9  call    memset_0
0x1800345de  mov     [rbp+7F0h+var_780], 58h ; 'X'
0x1800345e5  xor     edx, edx; Val
0x1800345e7  mov     r8d, 88h; Size
0x1800345ed  lea     rcx, [rbp+7F0h+var_810]; void *
0x1800345f1  call    memset_0
0x1800345f6  cmp     dword ptr [r14], 2
0x1800345fa  jnz     loc_180034723
0x180034600  mov     rax, [r14+8]
0x180034604  mov     r14, [rax+8]
0x180034608  mov     eax, [r14+0Ch]
0x18003460c  mov     rdx, [r14+10h]
0x180034610  lea     rcx, [rsp+8F0h+var_890]
0x180034615  mov     [rsp+8F0h+ppvContext], rcx; ppvContext
0x18003461a  mov     [rsp+8F0h+phMsg], r12; phMsg
0x18003461f  mov     [rsp+8F0h+phCertStore], r12; phCertStore
0x180034624  mov     [rsp+8F0h+pdwFormatType], r12; pdwFormatType
0x180034629  mov     [rsp+8F0h+pdwContentType], r12; pdwContentType
0x18003462e  mov     [rsp+8F0h+pdwMsgAndCertEncodingType], r12; pdwMsgAndCertEncodingType
0x180034633  mov     dword ptr [rsp+8F0h+pvPara], r12d; dwFlags
0x180034638  mov     r9d, 0Eh; dwExpectedFormatTypeFlags
0x18003463e  lea     r8d, [r9-0Ah]; dwExpectedContentTypeFlags
0x180034642  mov     rdx, [rdx+rax*8]; pvObject
0x180034646  mov     ecx, r13d; dwObjectType
0x180034649  call    cs:__imp_CryptQueryObject
0x18003464f  test    eax, eax
0x180034651  jz      loc_18003471C
0x180034657  mov     rax, [rsp+8F0h+var_890]
0x18003465c  mov     [rbp+7F0h+var_760], rax
0x180034663  lea     rcx, [rbp+7F0h+var_780]
0x180034667  mov     [rbp+7F0h+var_810], rcx
0x18003466b  mov     [rbp+7F0h+var_7B0], r13d
0x18003466f  mov     rcx, [rax+28h]
0x180034673  mov     [rsp+8F0h+pvPara], rcx; pvPara
0x180034678  xor     r9d, r9d; dwFlags
0x18003467b  xor     r8d, r8d; hCryptProv
0x18003467e  mov     edx, 10001h; dwEncodingType
0x180034683  mov     rcx, r13; lpszStoreProvider
0x180034686  call    cs:__imp_CertOpenStore
0x18003468c  mov     rbx, rax
0x18003468f  mov     [rsp+8F0h+var_880], rax
0x180034694  mov     [rsp+8F0h+var_888], rax
0x180034699  mov     [rsp+8F0h+var_880], r12
0x18003469e  lea     rcx, [rsp+8F0h+var_880]
0x1800346a3  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CertCloseStoreNoParam@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800346a8  mov     [rbp+7F0h+var_7F8], rbx
0x1800346ac  mov     rax, [r14+20h]
0x1800346b0  mov     [rbp+7F0h+var_7A0], rax
0x1800346b4  mov     eax, [r14+18h]
0x1800346b8  mov     [rbp+7F0h+var_7A8], eax
0x1800346bb  mov     rax, [r14+30h]
0x1800346bf  mov     [rbp+7F0h+var_790], rax
0x1800346c3  mov     eax, [r14+28h]
0x1800346c7  mov     [rbp+7F0h+var_798], eax
0x1800346ca  mov     eax, r15d
0x1800346cd  imul    rcx, rax, 68h ; 'h'
0x1800346d1  mov     qword ptr [rcx+rdi], 68h ; 'h'
0x1800346d9  mov     rbx, cs:?HinstDll@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * HinstDll
0x1800346e0  mov     [rcx+rdi+8], rbx
0x1800346e5  mov     qword ptr [rcx+rdi+10h], 95h
0x1800346ee  mov     [rcx+rdi+18h], r12
0x1800346f3  mov     [rcx+rdi+20h], r12
0x1800346f8  lea     rax, ?ViewPageCatalogEntries@@YA_JPEAUHWND__@@I_K_J@Z; ViewPageCatalogEntries(HWND__ *,uint,unsigned __int64,__int64)
0x1800346ff  mov     [rcx+rdi+28h], rax
0x180034704  lea     rax, [rbp+7F0h+var_810]
0x180034708  mov     [rcx+rdi+30h], rax
0x18003470d  mov     [rcx+rdi+38h], r12
0x180034712  mov     [rcx+rdi+40h], r12
0x180034717  add     r15d, r13d
0x18003471a  jmp     short loc_180034723
0x18003471c  mov     rbx, cs:?HinstDll@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * HinstDll
0x180034723  mov     eax, [rsi+50h]
0x180034726  imul    r8, rax, 68h ; 'h'; Size
0x18003472a  mov     eax, r15d
0x18003472d  imul    rcx, rax, 68h ; 'h'
0x180034731  add     rcx, rdi; void *
0x180034734  mov     rdx, [rsi+58h]; Src
0x180034738  call    memcpy_0
0x18003473d  mov     r14d, [rsi+50h]
0x180034741  add     r14d, r15d
0x180034744  mov     r15d, 60h ; '`'
0x18003474a  mov     r8d, r15d; Size
0x18003474d  xor     edx, edx; Val
0x18003474f  lea     rcx, [rbp+7F0h+var_870]; void *
0x180034753  call    memset_0
0x180034758  mov     [rbp+7F0h+var_870.dwSize], r15d
0x18003475c  mov     [rbp+7F0h+var_870.dwFlags], 188h
0x180034763  mov     rax, [rsi+8]
0x180034767  test    rax, rax
0x18003476a  jnz     short loc_180034779
0x18003476c  call    cs:__imp_GetDesktopWindow
0x180034772  mov     rbx, cs:?HinstDll@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * HinstDll
0x180034779  mov     [rbp+7F0h+var_870.hwndParent], rax
0x18003477d  mov     [rbp+7F0h+var_870.hInstance], rbx
0x180034781  mov     qword ptr [rbp+7F0h+var_870.18h], r12
0x180034785  mov     rax, [rsi+18h]
0x180034789  test    rax, rax
0x18003478c  jnz     short loc_1800347B0
0x18003478e  mov     r9d, 300h; cchBufferMax
0x180034794  lea     r8, [rbp+7F0h+Buffer]; lpBuffer
0x18003479b  mov     edx, 0CCBh; uID
0x1800347a0  mov     rcx, rbx; hInstance
0x1800347a3  call    cs:__imp_LoadStringW
0x1800347a9  lea     rax, [rbp+7F0h+Buffer]
0x1800347b0  mov     [rbp+7F0h+var_870.pszCaption], rax
0x1800347b4  mov     [rbp+7F0h+var_870.nPages], r14d
0x1800347b8  mov     dword ptr [rbp+7F0h+var_870.30h], r12d
0x1800347bc  mov     qword ptr [rbp+7F0h+var_870.38h], rdi
0x1800347c0  lea     rax, ?HidePropSheetCancelButtonCallback@@YAHPEAUHWND__@@I_J@Z; HidePropSheetCancelButtonCallback(HWND__ *,uint,__int64)
0x1800347c7  mov     [rbp+7F0h+var_870.pfnCallback], rax
0x1800347cb  call    IsolationAwareLoadLibraryA
0x1800347d0  mov     rbx, rax
0x1800347d3  test    rax, rax
0x1800347d6  jz      short loc_1800347EF
0x1800347d8  lea     rcx, [rbp+7F0h+var_870]; struct _PROPSHEETHEADERW_V2 *
0x1800347dc  call    ?CryptUIPropertySheetW@@YA_JPEBU_PROPSHEETHEADERW_V2@@@Z; CryptUIPropertySheetW(_PROPSHEETHEADERW_V2 const *)
0x1800347e1  mov     rsi, rax
0x1800347e4  mov     rcx, rbx; hLibModule
0x1800347e7  call    cs:__imp_FreeLibrary
0x1800347ed  jmp     short loc_1800347F2
0x1800347ef  mov     rsi, r12
0x1800347f2  xor     edx, edx; dwFlags
0x1800347f4  mov     rcx, [rbp+7F0h+hCertStore]; hCertStore
0x1800347fb  call    cs:__imp_CertCloseStore
0x180034801  cmp     [rbp+7F0h+var_65C], r12d
0x180034808  jz      short loc_180034815
0x18003480a  mov     ecx, 4C7h; dwErrCode
0x18003480f  call    cs:__imp_SetLastError
0x180034815  mov     rcx, rdi; hMem
0x180034818  call    cs:__imp_LocalFree
0x18003481e  mov     ebx, r12d
0x180034821  cmp     rsi, r13
0x180034824  setnl   bl
0x180034827  lea     rcx, [rsp+8F0h+var_890]
0x18003482c  call    ??1?$unique_storage@U?$resource_policy@PEAU_CTL_CONTEXT@@P6AHPEBU1@@Z$1?CertFreeCTLContext@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_CTL_CONTEXT *,int (*)(_CTL_CONTEXT const *),&CertFreeCTLContext(_CTL_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CTL_CONTEXT *,_CTL_CONTEXT *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_CTL_CONTEXT *,int (*)(_CTL_CONTEXT const *),&CertFreeCTLContext(_CTL_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CTL_CONTEXT *,_CTL_CONTEXT *,0,std::nullptr_t>>(void)
0x180034831  nop
0x180034832  lea     rcx, [rsp+8F0h+var_888]
0x180034837  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CertCloseStoreNoParam@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18003483c  mov     eax, ebx
0x18003483e  mov     rcx, [rbp+7F0h+var_50]
0x180034845  xor     rcx, rsp; StackCookie
0x180034848  call    __security_check_cookie
0x18003484d  add     rsp, 8B8h
0x180034854  pop     r15
0x180034856  pop     r14
0x180034858  pop     r13
0x18003485a  pop     r12
0x18003485c  pop     rdi
0x18003485d  pop     rsi
0x18003485e  pop     rbx
0x18003485f  pop     rbp
0x180034860  retn
```
