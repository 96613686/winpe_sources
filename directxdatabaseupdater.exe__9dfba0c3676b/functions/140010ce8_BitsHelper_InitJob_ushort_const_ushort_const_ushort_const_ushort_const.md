# BitsHelper::InitJob(ushort const *,ushort const *,ushort const *,ushort const *)

- ea: `0x140010ce8`
- end: `0x140011410`
- name: `?InitJob@BitsHelper@@QEAAJPEBG000@Z`
- size: `1832`
- prototype: `__int64 __fastcall(BitsHelper *this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `20`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x14000b0cc`

## callees

- `0x140002f40`
- `0x140005680`
- `0x1400057cc`
- `0x140005cac`
- `0x140006150`
- `0x140006320`
- `0x140006a10`
- `0x14000a4bc`
- `0x14000df28`
- `0x14000fa20`
- `0x14000fa44`
- `0x14000fa90`
- `0x14000ff7c`
- `0x140010c84`
- `0x140010ce8`
- `0x140011630`
- `0x140011804`
- `0x1400136f0`
- `0x1400184b4`
- `0x14001a010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x140010f36`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x140010f36`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14001106e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14001106e`
- `api-ms-win-core-localization-l1-2-0!GetThreadLocale` at `0x140011085`
- `api-ms-win-core-localization-l1-2-0!GetThreadLocale` at `0x140011085`

## string_xrefs

- `0x140010d3f`: `onecore\windows\directx\database\updater\exe\bitshelper.cpp`
- `0x140010d71`: `onecore\windows\directx\database\updater\exe\bitshelper.cpp`
- `0x140010dc2`: `onecore\windows\directx\database\updater\exe\bitshelper.cpp`
- `0x140010e44`: `onecore\windows\directx\database\updater\exe\bitshelper.cpp`
- `0x140010e9d`: `onecore\windows\directx\database\updater\exe\bitshelper.cpp`

## pseudocode

```c
__int64 __fastcall BitsHelper::InitJob(
        BitsHelper *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4)
{
  int v6; // eax
  BitsHelper *v7; // rcx
  unsigned int v8; // ebx
  int ActiveUserToken; // eax
  int IsLogonTriggerEnabled; // eax
  __int64 *v11; // rcx
  __int64 v12; // rax
  int v13; // eax
  __int64 v14; // rdx
  int v15; // r15d
  __int64 v16; // rax
  int v17; // eax
  int v18; // esi
  __int64 v19; // rax
  int v20; // eax
  wchar_t *v21; // rax
  int v22; // eax
  __int64 v23; // rdx
  __int64 v24; // r8
  __int64 *v25; // rax
  int v26; // r9d
  int v27; // r10d
  int v28; // r11d
  __int64 v29; // rax
  __int64 v30; // r14
  void (__fastcall *v31)(__int64, _QWORD, LPVOID *); // r12
  void *v32; // rsi
  unsigned __int16 ThreadLocale; // ax
  __int64 *v34; // r8
  int v35; // eax
  int DownloadJob; // eax
  BitsHelper *v37; // rcx
  const unsigned __int16 *v38; // r9
  int v39; // eax
  __int64 v40; // r9
  __int64 v41; // rdx
  int v42; // eax
  int v43; // eax
  int v45; // [rsp+20h] [rbp-E0h]
  int v46; // [rsp+20h] [rbp-E0h]
  char *v47; // [rsp+28h] [rbp-D8h]
  __int64 v48; // [rsp+30h] [rbp-D0h]
  __int64 v49; // [rsp+38h] [rbp-C8h]
  __int64 v50; // [rsp+48h] [rbp-B8h]
  __int64 v51; // [rsp+50h] [rbp-B0h]
  bool v52; // [rsp+60h] [rbp-A0h] BYREF
  __int64 *v53; // [rsp+68h] [rbp-98h] BYREF
  __int64 *v54; // [rsp+70h] [rbp-90h] BYREF
  wchar_t *String2; // [rsp+78h] [rbp-88h] BYREF
  struct IBackgroundCopyJob5 *v56; // [rsp+80h] [rbp-80h] BYREF
  int v57; // [rsp+88h] [rbp-78h] BYREF
  unsigned int v58; // [rsp+8Ch] [rbp-74h] BYREF
  LPVOID pv; // [rsp+90h] [rbp-70h] BYREF
  int v60; // [rsp+98h] [rbp-68h] BYREF
  int v61; // [rsp+9Ch] [rbp-64h] BYREF
  __int64 v62; // [rsp+A0h] [rbp-60h] BYREF
  void *v63; // [rsp+A8h] [rbp-58h] BYREF
  _OWORD v64[2]; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v65; // [rsp+D0h] [rbp-30h]
  char v66; // [rsp+D8h] [rbp-28h]
  struct IBackgroundCopyJob5 **v67; // [rsp+E0h] [rbp-20h] BYREF
  char v68; // [rsp+E8h] [rbp-18h]
  int v69[2]; // [rsp+F0h] [rbp-10h]
  const unsigned __int16 *v70; // [rsp+F8h] [rbp-8h]
  const unsigned __int16 *v71; // [rsp+100h] [rbp+0h]
  _BYTE v72[16]; // [rsp+108h] [rbp+8h] BYREF
  _BYTE v73[32]; // [rsp+118h] [rbp+18h] BYREF
  _BYTE v74[16]; // [rsp+138h] [rbp+38h] BYREF
  _BYTE v75[32]; // [rsp+148h] [rbp+48h] BYREF
  __int128 v76; // [rsp+168h] [rbp+68h] BYREF
  __int64 v77; // [rsp+178h] [rbp+78h]
  struct _GUID v78; // [rsp+180h] [rbp+80h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1E8h] [rbp+E8h]

  *(_QWORD *)v69 = a4;
  v71 = a3;
  v70 = a2;
  v6 = BitsHelper::Init(this);
  v8 = v6;
  if ( v6 >= 0 )
  {
    v63 = 0;
    ActiveUserToken = BitsHelper::GetActiveUserToken(v7, &v63);
    v8 = ActiveUserToken;
    if ( ActiveUserToken < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x42,
        (unsigned int)"onecore\\windows\\directx\\database\\updater\\exe\\bitshelper.cpp",
        (const char *)(unsigned int)ActiveUserToken,
        v45);
LABEL_70:
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v63);
      return v8;
    }
    memset(v64, 0, sizeof(v64));
    v65 = 0;
    v66 = 0;
    v52 = 0;
    IsLogonTriggerEnabled = TaskHelper::GetIsLogonTriggerEnabled((TaskHelper *)v64, &v52);
    v8 = IsLogonTriggerEnabled;
    if ( IsLogonTriggerEnabled < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x46,
        (unsigned int)"onecore\\windows\\directx\\database\\updater\\exe\\bitshelper.cpp",
        (const char *)(unsigned int)IsLogonTriggerEnabled,
        v45);
LABEL_7:
      TaskHelper::~TaskHelper((TaskHelper *)v64);
      goto LABEL_70;
    }
    if ( v52 && (((unsigned __int64)v63 + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    {
      TaskHelper::~TaskHelper((TaskHelper *)v64);
      v8 = 1;
      goto LABEL_70;
    }
    VersionInfo::VersionInfo((VersionInfo *)v72, a3);
    v54 = 0;
    v11 = *(__int64 **)this;
    v12 = **(_QWORD **)this;
    v54 = 0;
    v13 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64 **))(v12 + 40))(v11, 0, &v54);
    v8 = v13;
    if ( v13 >= 0 )
    {
      v58 = 0;
      v13 = (*(__int64 (__fastcall **)(__int64 *, unsigned int *))(*v54 + 56))(v54, &v58);
      v8 = v13;
      if ( v13 >= 0 )
      {
        v15 = 0;
        v8 = 1;
        if ( v58 )
        {
          while ( 1 )
          {
            v53 = 0;
            v16 = *v54;
            v53 = 0;
            v17 = (*(__int64 (__fastcall **)(__int64 *, __int64, __int64 **, _QWORD))(v16 + 24))(v54, 1, &v53, 0);
            v18 = v17;
            if ( v17 < 0 )
              break;
            String2 = 0;
            v19 = *v53;
            String2 = 0;
            v20 = (*(__int64 (__fastcall **)(__int64 *, wchar_t **))(v19 + 144))(v53, &String2);
            v18 = v20;
            if ( v20 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x5E,
                (unsigned int)"onecore\\windows\\directx\\database\\updater\\exe\\bitshelper.cpp",
                (const char *)(unsigned int)v20,
                v45);
              goto LABEL_58;
            }
            if ( !wcsncmp_0(L"DirectX_Database_Download_", String2, 0x1Au) )
            {
              v21 = wcsrchr(String2, 0x5Fu);
              VersionInfo::VersionInfo((VersionInfo *)v74, v21 + 1);
              v22 = VersionInfo::Compare((VersionInfo *)v72, (const struct VersionInfo *)v74);
              if ( v22 <= 0 )
              {
                if ( v22 )
                {
                  v39 = (*(__int64 (**)(void))(*v53 + 64))();
                  v8 = v39;
                  if ( v39 >= 0 )
                  {
                    v8 = -2147418113;
                    v40 = 2147549183LL;
                    v41 = 157;
                  }
                  else
                  {
                    v40 = (unsigned int)v39;
                    v41 = 156;
                  }
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)v41,
                    (unsigned int)"onecore\\windows\\directx\\database\\updater\\exe\\bitshelper.cpp",
                    (const char *)v40,
                    v45);
                  goto LABEL_50;
                }
                v57 = 0;
                v18 = (*(__int64 (__fastcall **)(__int64 *, int *))(*v53 + 112))(v53, &v57);
                if ( v18 < 0 )
                {
                  v23 = 117;
LABEL_24:
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)v23,
                    (unsigned int)"onecore\\windows\\directx\\database\\updater\\exe\\bitshelper.cpp",
                    (const char *)(unsigned int)v18,
                    v45);
LABEL_25:
                  std::wstring::_Tidy_deallocate(v75);
LABEL_58:
                  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&String2);
                  goto LABEL_60;
                }
                v76 = 0;
                v77 = 0;
                v18 = (*(__int64 (__fastcall **)(__int64 *, __int128 *))(*v53 + 96))(v53, &v76);
                if ( v18 < 0 )
                {
                  v23 = 120;
                  goto LABEL_24;
                }
                v25 = 0;
                pv = 0;
                v26 = 0;
                v60 = 0;
                v27 = 0;
                v61 = 0;
                v28 = v57;
                if ( (unsigned int)(v57 - 4) <= 1 )
                {
                  v62 = 0;
                  v29 = *v53;
                  v62 = 0;
                  if ( (*(int (__fastcall **)(__int64 *, __int64 *, __int64, _QWORD))(v29 + 120))(v53, &v62, v24, 0) >= 0
                    && (*(int (__fastcall **)(__int64, int *, int *))(*(_QWORD *)v62 + 24LL))(v62, &v60, &v61) >= 0 )
                  {
                    v30 = v62;
                    v31 = *(void (__fastcall **)(__int64, _QWORD, LPVOID *))(*(_QWORD *)v62 + 40LL);
                    v32 = pv;
                    if ( pv )
                    {
                      wil::last_error_context::last_error_context((wil::last_error_context *)&v67);
                      CoTaskMemFree(v32);
                      wil::last_error_context::~last_error_context((wil::last_error_context *)&v67);
                    }
                    pv = 0;
                    ThreadLocale = GetThreadLocale();
                    v31(v30, ThreadLocale, &pv);
                  }
                  wil::com_ptr_t<IPrincipal,wil::err_exception_policy>::~com_ptr_t<IPrincipal,wil::err_exception_policy>(&v62);
                  v28 = v57;
                  v25 = (__int64 *)pv;
                  v26 = v60;
                  v27 = v61;
                }
                v34 = &qword_14001C2F8;
                if ( v25 )
                  v34 = v25;
                LODWORD(v51) = v76;
                LODWORD(v50) = DWORD2(v76);
                LODWORD(v49) = v26;
                LODWORD(v48) = v27;
                LODWORD(v47) = v28;
                wil::details::in1diag3::Log_Win32Msg(
                  retaddr,
                  (void *)0x8C,
                  (unsigned int)"onecore\\windows\\directx\\database\\updater\\exe\\bitshelper.cpp",
                  (const char *)0x7DE,
                  (unsigned int)"State:%d, hrError:0x%X, Context:%d, Desc:%ws, Bytes:%u/%u\n",
                  v47,
                  v48,
                  v49,
                  v34,
                  v50,
                  v51);
                if ( ((v57 - 3) & 0xFFFFFFFC) != 0 || v57 == 5 )
                {
                  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pv);
LABEL_50:
                  std::wstring::_Tidy_deallocate(v75);
                  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&String2);
                  wil::com_ptr_t<IPrincipal,wil::err_exception_policy>::~com_ptr_t<IPrincipal,wil::err_exception_policy>(&v53);
                  goto LABEL_14;
                }
                v35 = (*(__int64 (__fastcall **)(__int64 *))(*v53 + 64))(v53);
                v18 = v35;
                if ( v35 < 0 )
                {
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0x91,
                    (unsigned int)"onecore\\windows\\directx\\database\\updater\\exe\\bitshelper.cpp",
                    (const char *)(unsigned int)v35,
                    v45);
                  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pv);
                  goto LABEL_25;
                }
                wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pv);
              }
              else
              {
                v18 = (*(__int64 (__fastcall **)(__int64 *))(*v53 + 64))(v53);
                if ( v18 < 0 )
                {
                  v23 = 109;
                  goto LABEL_24;
                }
              }
              std::wstring::_Tidy_deallocate(v75);
            }
            wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&String2);
            wil::com_ptr_t<IPrincipal,wil::err_exception_policy>::~com_ptr_t<IPrincipal,wil::err_exception_policy>(&v53);
            if ( ++v15 >= v58 )
              goto LABEL_44;
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x5C,
            (unsigned int)"onecore\\windows\\directx\\database\\updater\\exe\\bitshelper.cpp",
            (const char *)(unsigned int)v17,
            v45);
LABEL_60:
          wil::com_ptr_t<IPrincipal,wil::err_exception_policy>::~com_ptr_t<IPrincipal,wil::err_exception_policy>(&v53);
          wil::com_ptr_t<IPrincipal,wil::err_exception_policy>::~com_ptr_t<IPrincipal,wil::err_exception_policy>(&v54);
          std::wstring::_Tidy_deallocate(v73);
          TaskHelper::~TaskHelper((TaskHelper *)v64);
          v8 = v18;
          goto LABEL_70;
        }
LABEL_44:
        v78 = 0;
        v56 = 0;
        v67 = &v56;
        v68 = 1;
        v46 = v69[0];
        DownloadJob = BitsHelper::CreateDownloadJob(this, v63, v71, v70);
        v8 = DownloadJob;
        if ( DownloadJob >= 0 )
        {
          v42 = BitsHelper::SetCallbackExeOnJob(v37, v56, &v78, v38);
          v8 = v42;
          if ( v42 >= 0 )
          {
            v43 = ((__int64 (__fastcall *)(struct IBackgroundCopyJob5 *))v56->lpVtbl->Resume)(v56);
            v8 = v43;
            if ( v43 >= 0 )
            {
              wil::com_ptr_t<IPrincipal,wil::err_exception_policy>::~com_ptr_t<IPrincipal,wil::err_exception_policy>(&v56);
              wil::com_ptr_t<IPrincipal,wil::err_exception_policy>::~com_ptr_t<IPrincipal,wil::err_exception_policy>(&v54);
              std::wstring::_Tidy_deallocate(v73);
              TaskHelper::~TaskHelper((TaskHelper *)v64);
              v8 = 0;
              goto LABEL_70;
            }
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0xB1,
              (unsigned int)"onecore\\windows\\directx\\database\\updater\\exe\\bitshelper.cpp",
              (const char *)(unsigned int)v43,
              v46);
            if ( v56 )
              ((void (__fastcall *)(struct IBackgroundCopyJob5 *))v56->lpVtbl->Cancel)(v56);
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0xAE,
              (unsigned int)"onecore\\windows\\directx\\database\\updater\\exe\\bitshelper.cpp",
              (const char *)(unsigned int)v42,
              v46);
            if ( v56 )
              ((void (__fastcall *)(struct IBackgroundCopyJob5 *))v56->lpVtbl->Cancel)(v56);
          }
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xAB,
            (unsigned int)"onecore\\windows\\directx\\database\\updater\\exe\\bitshelper.cpp",
            (const char *)(unsigned int)DownloadJob,
            v46);
          if ( v56 )
            ((void (__fastcall *)(struct IBackgroundCopyJob5 *))v56->lpVtbl->Cancel)(v56);
        }
        wil::com_ptr_t<IPrincipal,wil::err_exception_policy>::~com_ptr_t<IPrincipal,wil::err_exception_policy>(&v56);
        goto LABEL_14;
      }
      v14 = 88;
    }
    else
    {
      v14 = 86;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v14,
      (unsigned int)"onecore\\windows\\directx\\database\\updater\\exe\\bitshelper.cpp",
      (const char *)(unsigned int)v13,
      v45);
LABEL_14:
    wil::com_ptr_t<IPrincipal,wil::err_exception_policy>::~com_ptr_t<IPrincipal,wil::err_exception_policy>(&v54);
    std::wstring::_Tidy_deallocate(v73);
    goto LABEL_7;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x3E,
    (unsigned int)"onecore\\windows\\directx\\database\\updater\\exe\\bitshelper.cpp",
    (const char *)(unsigned int)v6,
    v45);
  return v8;
}

```

## disassembly

```asm
0x140010ce8  push    rbp
0x140010cea  push    rbx
0x140010ceb  push    rsi
0x140010cec  push    rdi
0x140010ced  push    r12
0x140010cef  push    r13
0x140010cf1  push    r14
0x140010cf3  push    r15
0x140010cf5  lea     rbp, [rsp-0A8h]
0x140010cfd  sub     rsp, 1A8h
0x140010d04  mov     rax, cs:__security_cookie
0x140010d0b  xor     rax, rsp
0x140010d0e  mov     [rbp+0E0h+var_50], rax
0x140010d15  mov     qword ptr [rbp+0E0h+var_F0], r9
0x140010d19  mov     rdi, r8
0x140010d1c  mov     [rbp+0E0h+var_E0], r8
0x140010d20  mov     [rbp+0E0h+var_E8], rdx
0x140010d24  mov     r13, rcx
0x140010d27  call    ?Init@BitsHelper@@AEAAJXZ; BitsHelper::Init(void)
0x140010d2c  mov     ebx, eax
0x140010d2e  xor     r14d, r14d
0x140010d31  test    eax, eax
0x140010d33  jns     short loc_140010D54
0x140010d35  mov     rcx, [rbp+0E8h]; this
0x140010d3c  mov     r9d, eax; char *
0x140010d3f  lea     r8, aOnecoreWindows; "onecore\\windows\\directx\\database\\up"...
0x140010d46  lea     edx, [r14+3Eh]; void *
0x140010d4a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140010d4f  jmp     loc_1400113EB
0x140010d54  mov     [rbp+0E0h+var_138], r14
0x140010d58  lea     rdx, [rbp+0E0h+var_138]; void **
0x140010d5c  call    ?GetActiveUserToken@BitsHelper@@AEAAJPEAPEAX@Z; BitsHelper::GetActiveUserToken(void * *)
0x140010d61  mov     ebx, eax
0x140010d63  test    eax, eax
0x140010d65  jns     short loc_140010D87
0x140010d67  mov     rcx, [rbp+0E8h]; this
0x140010d6e  mov     r9d, eax; char *
0x140010d71  lea     r8, aOnecoreWindows; "onecore\\windows\\directx\\database\\up"...
0x140010d78  mov     edx, 42h ; 'B'; void *
0x140010d7d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140010d82  jmp     loc_1400113E2
0x140010d87  xorps   xmm0, xmm0
0x140010d8a  movdqu  [rbp+0E0h+var_130], xmm0
0x140010d8f  xorps   xmm1, xmm1
0x140010d92  movdqu  [rbp+0E0h+var_120], xmm1
0x140010d97  mov     [rbp+0E0h+var_110], r14
0x140010d9b  mov     [rbp+0E0h+var_108], r14b
0x140010d9f  mov     [rsp+1E0h+var_180], r14b
0x140010da4  lea     rdx, [rsp+1E0h+var_180]; bool *
0x140010da9  lea     rcx, [rbp+0E0h+var_130]; this
0x140010dad  call    ?GetIsLogonTriggerEnabled@TaskHelper@@QEAAJAEA_N@Z; TaskHelper::GetIsLogonTriggerEnabled(bool &)
0x140010db2  mov     ebx, eax
0x140010db4  test    eax, eax
0x140010db6  jns     short loc_140010DE2
0x140010db8  mov     rcx, [rbp+0E8h]; this
0x140010dbf  mov     r9d, eax; char *
0x140010dc2  lea     r8, aOnecoreWindows; "onecore\\windows\\directx\\database\\up"...
0x140010dc9  mov     edx, 46h ; 'F'; void *
0x140010dce  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140010dd3  nop
0x140010dd4  lea     rcx, [rbp+0E0h+var_130]; this
0x140010dd8  call    ??1TaskHelper@@QEAA@XZ; TaskHelper::~TaskHelper(void)
0x140010ddd  jmp     loc_1400113E2
0x140010de2  cmp     [rsp+1E0h+var_180], r14b
0x140010de7  jz      short loc_140010E0B
0x140010de9  mov     rax, [rbp+0E0h+var_138]
0x140010ded  inc     rax
0x140010df0  test    rax, 0FFFFFFFFFFFFFFFEh
0x140010df6  jnz     short loc_140010E0B
0x140010df8  lea     rcx, [rbp+0E0h+var_130]; this
0x140010dfc  call    ??1TaskHelper@@QEAA@XZ; TaskHelper::~TaskHelper(void)
0x140010e01  mov     ebx, 1
0x140010e06  jmp     loc_1400113E2
0x140010e0b  mov     rdx, rdi; unsigned __int16 *
0x140010e0e  lea     rcx, [rbp+0E0h+var_D8]; this
0x140010e12  call    ??0VersionInfo@@QEAA@PEBG@Z; VersionInfo::VersionInfo(ushort const *)
0x140010e17  nop
0x140010e18  mov     [rsp+1E0h+var_170], r14
0x140010e1d  mov     rcx, [r13+0]
0x140010e21  mov     rax, [rcx]
0x140010e24  mov     [rsp+1E0h+var_170], r14
0x140010e29  lea     r8, [rsp+1E0h+var_170]
0x140010e2e  xor     edx, edx
0x140010e30  mov     rax, [rax+28h]
0x140010e34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010e39  mov     ebx, eax
0x140010e3b  test    eax, eax
0x140010e3d  jns     short loc_140010E74
0x140010e3f  mov     edx, 56h ; 'V'; void *
0x140010e44  lea     r8, aOnecoreWindows; "onecore\\windows\\directx\\database\\up"...
0x140010e4b  mov     r9d, eax; char *
0x140010e4e  mov     rcx, [rbp+0E8h]; this
0x140010e55  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140010e5a  nop
0x140010e5b  lea     rcx, [rsp+1E0h+var_170]
0x140010e60  call    ??1?$com_ptr_t@UIPrincipal@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IPrincipal,wil::err_exception_policy>::~com_ptr_t<IPrincipal,wil::err_exception_policy>(void)
0x140010e65  nop
0x140010e66  lea     rcx, [rbp+0E0h+var_C8]
0x140010e6a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140010e6f  jmp     loc_140010DD4
0x140010e74  mov     dword ptr [rbp+0E0h+var_158+4], r14d
0x140010e78  mov     rcx, [rsp+1E0h+var_170]
0x140010e7d  mov     rax, [rcx]
0x140010e80  lea     rdx, [rbp+0E0h+var_158+4]
0x140010e84  mov     rax, [rax+38h]
0x140010e88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010e8d  mov     ebx, eax
0x140010e8f  test    eax, eax
0x140010e91  jns     short loc_140010E9A
0x140010e93  mov     edx, 58h ; 'X'
0x140010e98  jmp     short loc_140010E44
0x140010e9a  mov     r15d, r14d
0x140010e9d  lea     rdi, aOnecoreWindows; "onecore\\windows\\directx\\database\\up"...
0x140010ea4  mov     ebx, 1
0x140010ea9  cmp     dword ptr [rbp+0E0h+var_158+4], r14d
0x140010ead  jbe     loc_14001117A
0x140010eb3  mov     [rsp+1E0h+var_178], r14
0x140010eb8  mov     rcx, [rsp+1E0h+var_170]
0x140010ebd  mov     rax, [rcx]
0x140010ec0  mov     [rsp+1E0h+var_178], r14
0x140010ec5  xor     r9d, r9d
0x140010ec8  lea     r8, [rsp+1E0h+var_178]
0x140010ecd  mov     edx, ebx
0x140010ecf  mov     rax, [rax+18h]
0x140010ed3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010ed8  mov     esi, eax
0x140010eda  test    eax, eax
0x140010edc  js      loc_1400112DD
0x140010ee2  mov     [rsp+1E0h+String2], r14
0x140010ee7  mov     rcx, [rsp+1E0h+var_178]
0x140010eec  mov     rax, [rcx]
0x140010eef  mov     [rsp+1E0h+String2], r14
0x140010ef4  lea     rdx, [rsp+1E0h+String2]
0x140010ef9  mov     rax, [rax+90h]
0x140010f00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010f05  mov     esi, eax
0x140010f07  test    eax, eax
0x140010f09  js      loc_1400112B9
0x140010f0f  mov     r8d, 1Ah; MaxCount
0x140010f15  mov     rdx, [rsp+1E0h+String2]; String2
0x140010f1a  lea     rcx, aDirectxDatabas; "DirectX_Database_Download_"
0x140010f21  call    wcsncmp_0
0x140010f26  test    eax, eax
0x140010f28  jnz     loc_140011158
0x140010f2e  lea     edx, [rax+5Fh]; Ch
0x140010f31  mov     rcx, [rsp+1E0h+String2]; Str
0x140010f36  call    cs:__imp_wcsrchr
0x140010f3c  lea     rdx, [rax+2]; unsigned __int16 *
0x140010f40  lea     rcx, [rbp+0E0h+var_A8]; this
0x140010f44  call    ??0VersionInfo@@QEAA@PEBG@Z; VersionInfo::VersionInfo(ushort const *)
0x140010f49  nop
0x140010f4a  lea     rdx, [rbp+0E0h+var_A8]; struct VersionInfo *
0x140010f4e  lea     rcx, [rbp+0E0h+var_D8]; this
0x140010f52  call    ?Compare@VersionInfo@@QEBAHAEBV1@@Z; VersionInfo::Compare(VersionInfo const &)
0x140010f57  mov     rcx, [rsp+1E0h+var_178]
0x140010f5c  test    eax, eax
0x140010f5e  jle     short loc_140010F9C
0x140010f60  mov     rax, [rcx]
0x140010f63  mov     rax, [rax+40h]
0x140010f67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010f6c  mov     esi, eax
0x140010f6e  test    eax, eax
0x140010f70  jns     loc_14001114E
0x140010f76  mov     edx, 6Dh ; 'm'; void *
0x140010f7b  mov     rcx, [rbp+0E8h]; this
0x140010f82  mov     r9d, esi; char *
0x140010f85  mov     r8, rdi; unsigned int
0x140010f88  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140010f8d  nop
0x140010f8e  lea     rcx, [rbp+0E0h+var_98]
0x140010f92  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140010f97  jmp     loc_1400112D1
0x140010f9c  jnz     loc_14001127F
0x140010fa2  mov     dword ptr [rbp+0E0h+var_158], r14d
0x140010fa6  mov     rax, [rcx]
0x140010fa9  lea     rdx, [rbp+0E0h+var_158]
0x140010fad  mov     rax, [rax+70h]
0x140010fb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010fb6  mov     esi, eax
0x140010fb8  test    eax, eax
0x140010fba  js      loc_140011275
0x140010fc0  xorps   xmm0, xmm0
0x140010fc3  xor     eax, eax
0x140010fc5  movups  [rbp+0E0h+var_78], xmm0
0x140010fc9  mov     [rbp+0E0h+var_68], rax
0x140010fcd  mov     rcx, [rsp+1E0h+var_178]
0x140010fd2  mov     rax, [rcx]
0x140010fd5  lea     rdx, [rbp+0E0h+var_78]
0x140010fd9  mov     rax, [rax+60h]
0x140010fdd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010fe2  mov     esi, eax
0x140010fe4  test    eax, eax
0x140010fe6  js      loc_14001126B
0x140010fec  mov     rax, r14
0x140010fef  mov     [rbp+0E0h+pv], rax
0x140010ff3  mov     r9d, r14d
0x140010ff6  mov     [rbp+0E0h+var_148], r14d
0x140010ffa  mov     r10d, r14d
0x140010ffd  mov     [rbp+0E0h+var_144], r14d
0x140011001  mov     r11d, dword ptr [rbp+0E0h+var_158]
0x140011005  lea     ecx, [r11-4]
0x140011009  cmp     ecx, ebx
0x14001100b  ja      loc_1400110B9
0x140011011  mov     [rbp+0E0h+var_140], r14
0x140011015  mov     rcx, [rsp+1E0h+var_178]
0x14001101a  mov     rax, [rcx]
0x14001101d  mov     [rbp+0E0h+var_140], r14
0x140011021  lea     rdx, [rbp+0E0h+var_140]
0x140011025  mov     rax, [rax+78h]
0x140011029  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001102e  test    eax, eax
0x140011030  js      short loc_1400110A0
0x140011032  mov     rcx, [rbp+0E0h+var_140]
0x140011036  mov     rax, [rcx]
0x140011039  lea     r8, [rbp+0E0h+var_144]
0x14001103d  lea     rdx, [rbp+0E0h+var_148]
0x140011041  mov     rax, [rax+18h]
0x140011045  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001104a  test    eax, eax
0x14001104c  js      short loc_1400110A0
0x14001104e  mov     r14, [rbp+0E0h+var_140]
0x140011052  mov     rax, [r14]
0x140011055  mov     r12, [rax+28h]
0x140011059  mov     rsi, [rbp+0E0h+pv]
0x14001105d  test    rsi, rsi
0x140011060  jz      short loc_14001107D
0x140011062  lea     rcx, [rbp+0E0h+var_100]; this
0x140011066  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x14001106b  mov     rcx, rsi; pv
0x14001106e  call    cs:__imp_CoTaskMemFree
0x140011074  lea     rcx, [rbp+0E0h+var_100]; this
0x140011078  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x14001107d  mov     [rbp+0E0h+pv], 0
0x140011085  call    cs:__imp_GetThreadLocale
0x14001108b  movzx   edx, ax
0x14001108e  lea     r8, [rbp+0E0h+pv]
0x140011092  mov     rcx, r14
0x140011095  mov     rax, r12
0x140011098  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001109d  xor     r14d, r14d
0x1400110a0  lea     rcx, [rbp+0E0h+var_140]
0x1400110a4  call    ??1?$com_ptr_t@UIPrincipal@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IPrincipal,wil::err_exception_policy>::~com_ptr_t<IPrincipal,wil::err_exception_policy>(void)
0x1400110a9  mov     r11d, dword ptr [rbp+0E0h+var_158]
0x1400110ad  mov     rax, [rbp+0E0h+pv]
0x1400110b1  mov     r9d, [rbp+0E0h+var_148]
0x1400110b5  mov     r10d, [rbp+0E0h+var_144]
0x1400110b9  mov     edx, dword ptr [rbp+0E0h+var_78+8]
0x1400110bc  lea     r8, qword_14001C2F8
0x1400110c3  test    rax, rax
0x1400110c6  cmovnz  r8, rax
0x1400110ca  mov     rcx, [rbp+0E8h]; this
0x1400110d1  mov     eax, dword ptr [rbp+0E0h+var_78]
0x1400110d4  mov     [rsp+1E0h+var_190], eax
0x1400110d8  mov     dword ptr [rsp+1E0h+var_198], edx
0x1400110dc  mov     [rsp+1E0h+var_1A0], r8
0x1400110e1  mov     dword ptr [rsp+1E0h+var_1A8], r9d
0x1400110e6  mov     dword ptr [rsp+1E0h+var_1B0], r10d
0x1400110eb  mov     dword ptr [rsp+1E0h+var_1B8], r11d; char *
0x1400110f0  lea     rax, aStateDHrerror0; "State:%d, hrError:0x%X, Context:%d, Des"...
0x1400110f7  mov     qword ptr [rsp+1E0h+var_1C0], rax; int
0x1400110fc  mov     r9d, 7DEh; char *
0x140011102  mov     r8, rdi; unsigned int
0x140011105  mov     edx, 8Ch; void *
0x14001110a  call    ?Log_Win32Msg@in1diag3@details@wil@@YAKPEAXIPEBDK1ZZ; wil::details::in1diag3::Log_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x14001110f  mov     ecx, dword ptr [rbp+0E0h+var_158]
0x140011112  lea     eax, [rcx-3]
0x140011115  test    eax, 0FFFFFFFCh
0x14001111a  jnz     loc_14001123D
0x140011120  cmp     ecx, 5
0x140011123  jz      loc_14001123D
0x140011129  mov     rcx, [rsp+1E0h+var_178]
0x14001112e  mov     rax, [rcx]
0x140011131  mov     rax, [rax+40h]
0x140011135  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001113a  mov     esi, eax
0x14001113c  test    eax, eax
0x14001113e  js      loc_140011217
0x140011144  lea     rcx, [rbp+0E0h+pv]
0x140011148  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x14001114d  nop
0x14001114e  lea     rcx, [rbp+0E0h+var_98]
0x140011152  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140011157  nop
0x140011158  lea     rcx, [rsp+1E0h+String2]
0x14001115d  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x140011162  nop
0x140011163  lea     rcx, [rsp+1E0h+var_178]
0x140011168  call    ??1?$com_ptr_t@UIPrincipal@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IPrincipal,wil::err_exception_policy>::~com_ptr_t<IPrincipal,wil::err_exception_policy>(void)
0x14001116d  add     r15d, ebx
0x140011170  cmp     r15d, dword ptr [rbp+0E0h+var_158+4]
0x140011174  jb      loc_140010EB3
0x14001117a  xorps   xmm0, xmm0
0x14001117d  movups  xmmword ptr [rbp+0E0h+var_60.Data1], xmm0
0x140011184  mov     [rbp+0E0h+var_160], r14
0x140011188  lea     rax, [rbp+0E0h+var_160]
0x14001118c  mov     [rbp+0E0h+var_100], rax
0x140011190  mov     [rbp+0E0h+var_F8], bl
0x140011193  lea     rax, [rbp+0E0h+var_160]
0x140011197  mov     [rsp+1E0h+var_1A8], rax
0x14001119c  lea     rax, [rbp+0E0h+var_60]
  ... truncated ...
```
