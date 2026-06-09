# FileSystemFileFetcher::GetFile(ulong,wchar_t const *,wchar_t const *)

- ea: `0x1800c8550`
- end: `0x1800c8fb4`
- name: `?GetFile@FileSystemFileFetcher@@UEAAJKPEB_W0@Z`
- size: `2660`
- prototype: `int(FileSystemFileFetcher *__hidden this, unsigned int, const wchar_t *, const wchar_t *)`
- caller_count: `0`
- callee_count: `21`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, installer_update`

## callees

- `0x180013250`
- `0x1800150ac`
- `0x180016d40`
- `0x180033f58`
- `0x18003404c`
- `0x180041420`
- `0x180042448`
- `0x180044cc8`
- `0x18004d90c`
- `0x180057c28`
- `0x180093c4c`
- `0x180098538`
- `0x180099390`
- `0x180099548`
- `0x18009cf78`
- `0x1800c8550`
- `0x1800c8fbc`
- `0x1800eb920`
- `0x1800ed7c8`
- `0x1800f0eac`
- `0x1802adc58`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x1800c87df`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x1800c87fe`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x1800c87df`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x1800c87fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c8b84`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c8b84`
- `api-ms-win-core-kernel32-legacy-l1-1-0!CopyFileW` at `0x1800c89e8`
- `api-ms-win-core-kernel32-legacy-l1-1-0!CopyFileW` at `0x1800c89e8`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x1800c8a7a`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x1800c8a7a`
- `api-ms-win-core-file-l2-1-0!CreateHardLinkW` at `0x1800c8b0a`
- `api-ms-win-core-file-l2-1-0!CreateHardLinkW` at `0x1800c8b0a`

## string_xrefs

- `0x1800c8cd9`: `Source: Could not copy file {} to {}`
- `0x1800c85a9`: `No file path specified`
- `0x1800c8743`: `Failed to impersonate`
- `0x1800c8da6`: `Source: Could not hard-link file {} to {}`
- `0x1800c862b`: `No target path specified`
- `0x1800c8bec`: `Exec: Not able to find {} in directory local source`
- `0x1800c8d2c`: `Source: Could not move-file file {} to {}`
- `0x1800c8838`: `Failed to create file working directory subdirectories`
- `0x1800c8b50`: `Source: Hard-linked file {} to {}`
- `0x1800c8ac4`: `Source: Moved file {} to {}`

## pseudocode

```c
__int64 __fastcall FileSystemFileFetcher::GetFile(
        FileSystemFileFetcher *this,
        int a2,
        const wchar_t *a3,
        const wchar_t *a4)
{
  int v6; // ebx
  int v7; // edx
  __int64 v8; // rdx
  int v10; // edx
  int v11; // edx
  char v12; // r12
  char v13; // r13
  unsigned __int64 v14; // r14
  int v15; // eax
  int v16; // edx
  __int64 v17; // rdx
  unsigned __int64 v18; // r9
  int v19; // eax
  wchar_t *v20; // rax
  wchar_t *v21; // rdi
  wchar_t *v22; // rax
  wchar_t *v23; // r15
  int Directory; // eax
  int v25; // edx
  int v26; // r15d
  unsigned __int64 v27; // r9
  char v28; // r12
  unsigned __int64 v29; // rbx
  __int64 v30; // rdx
  int v31; // r8d
  unsigned __int64 v32; // r9
  unsigned __int64 *v33; // r10
  __int64 v34; // rdx
  int v35; // eax
  LPCWSTR v36; // rbx
  int v37; // edx
  int v38; // edx
  int v39; // edx
  unsigned __int64 v40; // rbx
  signed int LastError; // edx
  char v42; // r13
  char v43; // r12
  bool v44; // zf
  int v45; // [rsp+20h] [rbp-168h]
  char v46; // [rsp+30h] [rbp-158h]
  char v47; // [rsp+31h] [rbp-157h]
  char v48; // [rsp+32h] [rbp-156h]
  LPCWSTR lpExistingFileName; // [rsp+38h] [rbp-150h] BYREF
  int v50; // [rsp+40h] [rbp-148h]
  int v51[2]; // [rsp+48h] [rbp-140h] BYREF
  int v52; // [rsp+50h] [rbp-138h]
  wchar_t *Str; // [rsp+58h] [rbp-130h] BYREF
  __int64 v54; // [rsp+60h] [rbp-128h]
  char v55[8]; // [rsp+68h] [rbp-120h] BYREF
  int v56; // [rsp+70h] [rbp-118h]
  unsigned __int64 v57; // [rsp+78h] [rbp-110h]
  unsigned __int64 v58; // [rsp+80h] [rbp-108h]
  FileSystemFileFetcher *v59; // [rsp+88h] [rbp-100h]
  unsigned __int64 v60; // [rsp+90h] [rbp-F8h]
  int v61; // [rsp+98h] [rbp-F0h]
  int v62; // [rsp+9Ch] [rbp-ECh]
  int v63; // [rsp+A0h] [rbp-E8h]
  _BYTE v64[16]; // [rsp+A8h] [rbp-E0h] BYREF
  FileSystemFileFetcher *v65; // [rsp+B8h] [rbp-D0h] BYREF
  wchar_t *v66; // [rsp+C0h] [rbp-C8h] BYREF
  LPCWSTR v67; // [rsp+C8h] [rbp-C0h] BYREF
  wchar_t *v68; // [rsp+D0h] [rbp-B8h] BYREF
  LPCWSTR v69; // [rsp+D8h] [rbp-B0h] BYREF
  wchar_t *v70; // [rsp+E0h] [rbp-A8h] BYREF
  LPCWSTR v71; // [rsp+E8h] [rbp-A0h] BYREF
  LPCWSTR v72; // [rsp+F0h] [rbp-98h] BYREF
  wchar_t *v73; // [rsp+F8h] [rbp-90h] BYREF
  LPCWSTR v74; // [rsp+100h] [rbp-88h] BYREF
  wchar_t *v75; // [rsp+108h] [rbp-80h] BYREF
  LPCWSTR v76; // [rsp+110h] [rbp-78h] BYREF
  wchar_t *v77; // [rsp+118h] [rbp-70h] BYREF
  LPCWSTR v78; // [rsp+120h] [rbp-68h] BYREF
  char *v79; // [rsp+128h] [rbp-60h]
  unsigned __int64 *v80; // [rsp+130h] [rbp-58h]
  const wchar_t *v81; // [rsp+138h] [rbp-50h]
  int v82; // [rsp+140h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+188h] [rbp+0h]

  v52 = a2;
  v59 = this;
  v81 = a3;
  if ( !a3 )
  {
    v6 = -2147024809;
    v82 = -2147024809;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "No file path specified");
      *(_QWORD *)v51 = &v82;
      LOBYTE(v7) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v7,
        3,
        (unsigned int)": {}",
        (__int64)v51);
    }
    v8 = 522;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecore\\base\\cbs\\core\\filefetcher.cpp",
      (const char *)0x80070057LL,
      v45);
    return (unsigned int)v6;
  }
  if ( !a4 )
  {
    v6 = -2147024809;
    v82 = -2147024809;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "No target path specified");
      *(_QWORD *)v51 = &v82;
      LOBYTE(v10) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v10,
        3,
        (unsigned int)": {}",
        (__int64)v51);
    }
    v8 = 523;
    goto LABEL_5;
  }
  Windows::AutoNewPtr<CDetectUpdate>::AutoNewPtr<CDetectUpdate>(&Str);
  if ( (v11 & 0xFFFFFFC0) != 0 )
  {
    v6 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x217,
      (unsigned int)"onecore\\base\\cbs\\core\\filefetcher.cpp",
      (const char *)0x80070057LL,
      v45);
LABEL_49:
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&Str);
    return (unsigned int)v6;
  }
  if ( *((_BYTE *)this + 104) || (v11 & 4) != 0 )
  {
    v12 = 1;
    v47 = 1;
  }
  else
  {
    v12 = 0;
    v47 = 0;
    if ( (v11 & 2) != 0 )
    {
      v13 = 1;
      goto LABEL_19;
    }
  }
  v13 = 0;
LABEL_19:
  v46 = v13;
  v79 = (char *)this + 8;
  wil::srwlock::lock_shared((char *)this + 8, v55);
  v80 = (unsigned __int64 *)((char *)this + 96);
  v14 = *((_QWORD *)this + 12);
  v58 = v14;
  NestableImpersonator::NestableImpersonator((NestableImpersonator *)v64, *((void **)this + 11));
  v15 = NestableImpersonator::Impersonate((NestableImpersonator *)v64);
  v6 = v15;
  if ( v15 < 0 )
  {
    v82 = v15;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to impersonate");
      *(_QWORD *)v51 = &v82;
      LOBYTE(v16) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v16,
        3,
        (unsigned int)": {}",
        (__int64)v51);
    }
  }
  if ( v6 < 0 )
  {
    v17 = 554;
LABEL_24:
    v18 = (unsigned int)v6;
    goto LABEL_25;
  }
  v19 = SczAllocConcat2Sz(&Str, *((_QWORD *)v59 + 10), a4);
  v6 = v19;
  if ( v19 < 0 )
  {
    v18 = (unsigned int)v19;
    v17 = 556;
LABEL_25:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v17,
      (unsigned int)"onecore\\base\\cbs\\core\\filefetcher.cpp",
      (const char *)v18,
      v45);
LABEL_48:
    ImpersonatorBase::Unimpersonate((ImpersonatorBase *)v64);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(v55);
    goto LABEL_49;
  }
  v20 = wcsrchr(a4, 0x5Cu);
  v21 = Str;
  if ( v20 )
  {
    v22 = wcsrchr(Str, 0x5Cu);
    v23 = v22;
    if ( v22 )
    {
      *v22 = 0;
      Directory = RecursivelyCreateDirectory(v21, 0);
      v6 = Directory;
      if ( Directory < 0 )
      {
        v82 = Directory;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            LogAdapter::g_Logger,
            0,
            3,
            "Failed to create file working directory subdirectories");
          *(_QWORD *)v51 = &v82;
          LOBYTE(v25) = 1;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v25,
            3,
            (unsigned int)": {}",
            (__int64)v51);
        }
      }
      if ( v6 < 0 )
      {
        v17 = 567;
        goto LABEL_24;
      }
      *v23 = 92;
    }
  }
  v65 = v59;
  v26 = 0;
  v50 = 0;
  v82 = v52 & 8;
  v63 = v82;
  v56 = v52 & 0x10;
  v62 = v56;
  v52 &= 0x20u;
  v61 = v52;
  v57 = v14;
  *(_QWORD *)v51 = (char *)v59 + 40;
  v27 = *((_QWORD *)v59 + 5);
  v60 = v27;
  if ( v12 || (v28 = 1, v13) )
    v28 = 0;
  v48 = 1;
  v29 = 0;
  v54 = 0;
  while ( v29 < v27 )
  {
    Windows::AutoNewPtr<CDetectUpdate>::AutoNewPtr<CDetectUpdate>(&lpExistingFileName);
    if ( v14 >= *v33 )
      __fastfail(8u);
    v34 = *(_QWORD *)(v30 + 56);
    if ( !v31 && (**(_BYTE **)(v34 + 8 * v14) & 0x20) != 0 )
    {
      v14 = (v14 + 1) % v32;
      v58 = v14;
      goto LABEL_104;
    }
    v35 = SczAllocConcat2Sz(&lpExistingFileName, *(_QWORD *)(*(_QWORD *)(v34 + 8 * v14) + 8LL), v81);
    v6 = v35;
    if ( v35 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x250,
        (unsigned int)"onecore\\base\\cbs\\core\\filefetcher.cpp",
        (const char *)(unsigned int)v35,
        v45);
      Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpExistingFileName);
      goto LABEL_48;
    }
    v36 = lpExistingFileName;
    if ( v28 )
    {
      if ( CopyFileW(lpExistingFileName, v21, 1) )
      {
        v66 = v21;
        v67 = v36;
        if ( LogAdapter::g_Logger )
        {
          LOBYTE(v37) = 1;
          LogAdapter::Logger::LogNumObjects<wchar_t const *,wchar_t *>(
            (_DWORD)LogAdapter::g_Logger,
            v37,
            1,
            (unsigned int)"Source: Copied file {} to {}",
            (__int64)&v67,
            (__int64)&v66);
        }
LABEL_64:
        v26 = 1;
        v50 = 1;
        Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpExistingFileName);
        v40 = v57;
        goto LABEL_107;
      }
    }
    else if ( v47 )
    {
      if ( MoveFileExW(lpExistingFileName, v21, 0) )
      {
        v68 = v21;
        v69 = v36;
        if ( LogAdapter::g_Logger )
        {
          LOBYTE(v38) = 1;
          LogAdapter::Logger::LogNumObjects<wchar_t const *,wchar_t *>(
            (_DWORD)LogAdapter::g_Logger,
            v38,
            1,
            (unsigned int)"Source: Moved file {} to {}",
            (__int64)&v69,
            (__int64)&v68);
        }
        goto LABEL_64;
      }
    }
    else if ( v13 && CreateHardLinkW(v21, lpExistingFileName, 0) )
    {
      v70 = v21;
      v71 = v36;
      if ( LogAdapter::g_Logger )
      {
        LOBYTE(v39) = 1;
        LogAdapter::Logger::LogNumObjects<wchar_t const *,wchar_t *>(
          (_DWORD)LogAdapter::g_Logger,
          v39,
          1,
          (unsigned int)"Source: Hard-linked file {} to {}",
          (__int64)&v71,
          (__int64)&v70);
      }
      goto LABEL_64;
    }
    LastError = GetLastError();
    if ( (unsigned int)(LastError - 2) > 1 )
      goto LABEL_76;
    if ( v48 && (unsigned int)DoesFileExist(v21, 0) )
    {
      LastError = 183;
LABEL_76:
      if ( LastError == 183 || LastError == 80 || LastError == 698 || LastError == 5010 )
      {
        v42 = 1;
        if ( v56 )
        {
          v40 = v57;
          v14 = v57;
          v58 = v57;
          v26 = 1;
          v50 = 1;
          Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpExistingFileName);
          goto LABEL_107;
        }
      }
      else
      {
        v42 = 0;
      }
      if ( v28 )
      {
        v73 = v21;
        v74 = v36;
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
        LogAdapter::TraceAtLevelHr<long,wchar_t *,wchar_t const *>(
          1,
          LastError,
          (unsigned int)"Source: Could not copy file {} to {}",
          (unsigned int)&v74,
          (__int64)&v73);
        goto LABEL_97;
      }
      if ( v47 )
      {
        v75 = v21;
        v76 = v36;
        if ( LogAdapter::g_Logger )
        {
          LOBYTE(LastError) = 1;
          LogAdapter::Logger::LogNumObjects<wchar_t const *,wchar_t *>(
            (_DWORD)LogAdapter::g_Logger,
            LastError,
            1,
            (unsigned int)"Source: Could not move-file file {} to {}",
            (__int64)&v76,
            (__int64)&v75);
        }
        if ( !v42 )
          goto LABEL_91;
LABEL_97:
        v43 = v46;
      }
      else
      {
        v43 = v46;
        if ( v46 )
        {
          v77 = v21;
          v78 = v36;
          if ( LogAdapter::g_Logger )
          {
            LOBYTE(LastError) = 1;
            LogAdapter::Logger::LogNumObjects<wchar_t const *,wchar_t *>(
              (_DWORD)LogAdapter::g_Logger,
              LastError,
              1,
              (unsigned int)"Source: Could not hard-link file {} to {}",
              (__int64)&v78,
              (__int64)&v77);
          }
          if ( v42 )
          {
LABEL_99:
            Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpExistingFileName);
            ImpersonatorBase::Unimpersonate((ImpersonatorBase *)v64);
            wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(v55);
            Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&Str);
            return 2147942583LL;
          }
LABEL_91:
          v28 = 1;
          Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpExistingFileName);
          v29 = v54;
          goto LABEL_105;
        }
      }
      if ( v42 )
        goto LABEL_99;
      v14 = (v14 + 1) % v60;
      v58 = v14;
      if ( v47 || (v44 = v43 == 0, v28 = 1, !v44) )
        v28 = 0;
      v29 = v54;
LABEL_104:
      v54 = ++v29;
      Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpExistingFileName);
      goto LABEL_105;
    }
    v48 = 0;
    if ( !v82 )
    {
      v72 = v36;
      if ( LogAdapter::g_Logger )
      {
        LOBYTE(LastError) = 1;
        LogAdapter::Logger::LogNumObjects<wchar_t const *>(
          (_DWORD)LogAdapter::g_Logger,
          LastError,
          1,
          (unsigned int)"Exec: Not able to find {} in directory local source",
          (__int64)&v72);
      }
    }
    v14 = (v14 + 1) % v60;
    v58 = v14;
    if ( v47 || (v28 = 1, v13) )
      v28 = 0;
    v29 = ++v54;
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpExistingFileName);
LABEL_105:
    v13 = v46;
    v27 = v60;
  }
  v40 = v57;
LABEL_107:
  if ( v14 == v40 )
    v14 = 0xFFFFFFFFLL;
  ImpersonatorBase::Unimpersonate((ImpersonatorBase *)v64);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(v55);
  if ( v26 )
  {
    if ( v14 != 0xFFFFFFFF )
    {
      wil::srwlock::lock_exclusive(v79, &v65);
      if ( v14 < **(_QWORD **)v51 )
        *v80 = v14;
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&v65);
    }
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&Str);
    return 0;
  }
  else
  {
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&Str);
    return 2147942402LL;
  }
}

```

## disassembly

```asm
0x1800c8550  mov     r11, rsp
0x1800c8553  push    rbx
0x1800c8554  push    rsi
0x1800c8555  push    rdi
0x1800c8556  push    r12
0x1800c8558  push    r13
0x1800c855a  push    r14
0x1800c855c  push    r15
0x1800c855e  sub     rsp, 150h
0x1800c8565  mov     rax, cs:__security_cookie
0x1800c856c  xor     rax, rsp
0x1800c856f  mov     [rsp+188h+var_40], rax
0x1800c8577  mov     rdi, r9
0x1800c857a  mov     [rsp+188h+var_138], edx
0x1800c857e  mov     rbx, rcx
0x1800c8581  mov     [rsp+188h+var_100], rcx
0x1800c8589  mov     [r11-50h], r8
0x1800c858d  xor     esi, esi
0x1800c858f  test    r8, r8
0x1800c8592  jnz     short loc_1800C860E
0x1800c8594  mov     ebx, 80070057h
0x1800c8599  mov     [r11-48h], ebx
0x1800c859d  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800c85a4  test    rcx, rcx
0x1800c85a7  jz      short loc_1800C85EB
0x1800c85a9  lea     r9, aNoFilePathSpec; "No file path specified"
0x1800c85b0  xor     edx, edx
0x1800c85b2  lea     r8d, [rsi+3]
0x1800c85b6  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800c85bb  lea     rax, [rsp+188h+var_48]
0x1800c85c3  mov     qword ptr [rsp+188h+var_140], rax
0x1800c85c8  lea     rax, [rsp+188h+var_140]
0x1800c85cd  mov     qword ptr [rsp+188h+var_168], rax; int
0x1800c85d2  lea     r9, asc_1802EE7AC; ": {}"
0x1800c85d9  lea     r8d, [rsi+3]
0x1800c85dd  mov     dl, 1
0x1800c85df  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800c85e6  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800c85eb  mov     edx, 20Ah; void *
0x1800c85f0  lea     r8, aOnecoreBaseCbs_111; "onecore\\base\\cbs\\core\\filefetcher.c"...
0x1800c85f7  mov     r9d, ebx; char *
0x1800c85fa  mov     rcx, [rsp+188h]; this
0x1800c8602  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c8607  mov     eax, ebx
0x1800c8609  jmp     loc_1800C8F90
0x1800c860e  test    rdi, rdi
0x1800c8611  jnz     short loc_1800C8677
0x1800c8613  mov     ebx, 80070057h
0x1800c8618  mov     [rsp+188h+var_48], ebx
0x1800c861f  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800c8626  test    rcx, rcx
0x1800c8629  jz      short loc_1800C866D
0x1800c862b  lea     r9, aNoTargetPathSp; "No target path specified"
0x1800c8632  xor     edx, edx
0x1800c8634  lea     r8d, [rdi+3]
0x1800c8638  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800c863d  lea     rax, [rsp+188h+var_48]
0x1800c8645  mov     qword ptr [rsp+188h+var_140], rax
0x1800c864a  lea     rax, [rsp+188h+var_140]
0x1800c864f  mov     qword ptr [rsp+188h+var_168], rax
0x1800c8654  lea     r9, asc_1802EE7AC; ": {}"
0x1800c865b  lea     r8d, [rdi+3]
0x1800c865f  mov     dl, 1
0x1800c8661  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800c8668  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800c866d  mov     edx, 20Bh
0x1800c8672  jmp     loc_1800C85F0
0x1800c8677  lea     rcx, [rsp+188h+Str]
0x1800c867c  call    ??0?$AutoNewPtr@VCDetectUpdate@@@Windows@@QEAA@XZ; Windows::AutoNewPtr<CDetectUpdate>::AutoNewPtr<CDetectUpdate>(void)
0x1800c8681  test    edx, 0FFFFFFC0h
0x1800c8687  jz      short loc_1800C86AF
0x1800c8689  mov     rcx, [rsp+188h]; this
0x1800c8691  mov     ebx, 80070057h
0x1800c8696  mov     r9d, ebx; char *
0x1800c8699  lea     r8, aOnecoreBaseCbs_111; "onecore\\base\\cbs\\core\\filefetcher.c"...
0x1800c86a0  mov     edx, 217h; void *
0x1800c86a5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c86aa  jmp     loc_1800C89BF
0x1800c86af  cmp     [rbx+68h], sil
0x1800c86b3  jnz     short loc_1800C86CC
0x1800c86b5  test    dl, 4
0x1800c86b8  jnz     short loc_1800C86CC
0x1800c86ba  mov     r12b, sil
0x1800c86bd  mov     [rsp+188h+var_157], sil
0x1800c86c2  test    dl, 2
0x1800c86c5  jz      short loc_1800C86D4
0x1800c86c7  mov     r13b, 1
0x1800c86ca  jmp     short loc_1800C86D7
0x1800c86cc  mov     r12b, 1
0x1800c86cf  mov     [rsp+188h+var_157], r12b
0x1800c86d4  mov     r13b, sil
0x1800c86d7  mov     [rsp+188h+var_158], r13b
0x1800c86dc  lea     rax, [rbx+8]
0x1800c86e0  mov     [rsp+188h+var_60], rax
0x1800c86e8  lea     rdx, [rsp+188h+var_120]
0x1800c86ed  mov     rcx, rax
0x1800c86f0  call    ?lock_shared@srwlock@wil@@QEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::srwlock::lock_shared(void)
0x1800c86f5  lea     rax, [rbx+60h]
0x1800c86f9  mov     [rsp+188h+var_58], rax
0x1800c8701  mov     r14, [rax]
0x1800c8704  mov     [rsp+188h+var_108], r14
0x1800c870c  mov     rdx, [rbx+58h]; void *
0x1800c8710  lea     rcx, [rsp+188h+var_E0]; this
0x1800c8718  call    ??0NestableImpersonator@@QEAA@PEAX@Z; NestableImpersonator::NestableImpersonator(void *)
0x1800c871d  lea     rcx, [rsp+188h+var_E0]; this
0x1800c8725  call    ?Impersonate@NestableImpersonator@@QEAAJXZ; NestableImpersonator::Impersonate(void)
0x1800c872a  mov     ebx, eax
0x1800c872c  test    eax, eax
0x1800c872e  jns     short loc_1800C8787
0x1800c8730  mov     [rsp+188h+var_48], eax
0x1800c8737  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800c873e  test    rcx, rcx
0x1800c8741  jz      short loc_1800C8787
0x1800c8743  lea     r9, aFailedToImpers_3; "Failed to impersonate"
0x1800c874a  xor     edx, edx
0x1800c874c  lea     r8d, [rdx+3]
0x1800c8750  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800c8755  lea     rax, [rsp+188h+var_48]
0x1800c875d  mov     qword ptr [rsp+188h+var_140], rax
0x1800c8762  lea     rax, [rsp+188h+var_140]
0x1800c8767  mov     qword ptr [rsp+188h+var_168], rax; int
0x1800c876c  lea     r9, asc_1802EE7AC; ": {}"
0x1800c8773  mov     r8d, 3
0x1800c8779  mov     dl, 1
0x1800c877b  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800c8782  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800c8787  test    ebx, ebx
0x1800c8789  jns     short loc_1800C87AC
0x1800c878b  mov     edx, 22Ah; void *
0x1800c8790  mov     r9d, ebx; char *
0x1800c8793  mov     rcx, [rsp+188h]; this
0x1800c879b  lea     r8, aOnecoreBaseCbs_111; "onecore\\base\\cbs\\core\\filefetcher.c"...
0x1800c87a2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c87a7  jmp     loc_1800C89A8
0x1800c87ac  mov     r8, rdi
0x1800c87af  mov     rdx, [rsp+188h+var_100]
0x1800c87b7  mov     rdx, [rdx+50h]
0x1800c87bb  lea     rcx, [rsp+188h+Str]
0x1800c87c0  call    SczAllocConcat2Sz
0x1800c87c5  mov     ebx, eax
0x1800c87c7  test    eax, eax
0x1800c87c9  jns     short loc_1800C87D5
0x1800c87cb  mov     r9d, eax
0x1800c87ce  mov     edx, 22Ch
0x1800c87d3  jmp     short loc_1800C8793
0x1800c87d5  mov     ebx, 5Ch ; '\'
0x1800c87da  mov     edx, ebx; Ch
0x1800c87dc  mov     rcx, rdi; Str
0x1800c87df  call    cs:__imp_wcsrchr
0x1800c87e6  nop     dword ptr [rax+rax+00h]
0x1800c87eb  mov     rdi, [rsp+188h+Str]
0x1800c87f0  test    rax, rax
0x1800c87f3  jz      loc_1800C8890
0x1800c87f9  mov     edx, ebx; Ch
0x1800c87fb  mov     rcx, rdi; Str
0x1800c87fe  call    cs:__imp_wcsrchr
0x1800c8805  nop     dword ptr [rax+rax+00h]
0x1800c880a  mov     r15, rax
0x1800c880d  test    rax, rax
0x1800c8810  jz      short loc_1800C8890
0x1800c8812  mov     [rax], si
0x1800c8815  xor     edx, edx
0x1800c8817  mov     rcx, rdi
0x1800c881a  call    RecursivelyCreateDirectory
0x1800c881f  mov     ebx, eax
0x1800c8821  test    eax, eax
0x1800c8823  jns     short loc_1800C887C
0x1800c8825  mov     [rsp+188h+var_48], eax
0x1800c882c  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800c8833  test    rcx, rcx
0x1800c8836  jz      short loc_1800C887C
0x1800c8838  lea     r9, aFailedToCreate_65; "Failed to create file working directory"...
0x1800c883f  xor     edx, edx
0x1800c8841  lea     r8d, [rdx+3]
0x1800c8845  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800c884a  lea     rax, [rsp+188h+var_48]
0x1800c8852  mov     qword ptr [rsp+188h+var_140], rax
0x1800c8857  lea     rax, [rsp+188h+var_140]
0x1800c885c  mov     qword ptr [rsp+188h+var_168], rax; int
0x1800c8861  lea     r9, asc_1802EE7AC; ": {}"
0x1800c8868  mov     r8d, 3
0x1800c886e  mov     dl, 1
0x1800c8870  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800c8877  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800c887c  test    ebx, ebx
0x1800c887e  jns     short loc_1800C888A
0x1800c8880  mov     edx, 237h
0x1800c8885  jmp     loc_1800C8790
0x1800c888a  mov     word ptr [r15], 5Ch ; '\'
0x1800c8890  mov     rdx, [rsp+188h+var_100]
0x1800c8898  mov     [rsp+188h+var_D0], rdx
0x1800c88a0  mov     r15d, esi
0x1800c88a3  mov     [rsp+188h+var_148], esi
0x1800c88a7  mov     r8d, [rsp+188h+var_138]
0x1800c88ac  mov     eax, r8d
0x1800c88af  and     eax, 8
0x1800c88b2  mov     [rsp+188h+var_48], eax
0x1800c88b9  mov     [rsp+188h+var_E8], eax
0x1800c88c0  mov     eax, r8d
0x1800c88c3  and     eax, 10h
0x1800c88c6  mov     [rsp+188h+var_118], eax
0x1800c88ca  mov     [rsp+188h+var_EC], eax
0x1800c88d1  and     r8d, 20h
0x1800c88d5  mov     [rsp+188h+var_138], r8d
0x1800c88da  mov     [rsp+188h+var_F0], r8d
0x1800c88e2  mov     [rsp+188h+var_110], r14
0x1800c88e7  lea     r10, [rdx+28h]
0x1800c88eb  mov     qword ptr [rsp+188h+var_140], r10
0x1800c88f0  mov     r9, [r10]
0x1800c88f3  mov     [rsp+188h+var_F8], r9
0x1800c88fb  test    r12b, r12b
0x1800c88fe  jnz     short loc_1800C8908
0x1800c8900  test    r13b, r13b
0x1800c8903  mov     r12b, 1
0x1800c8906  jz      short loc_1800C890B
0x1800c8908  mov     r12b, sil
0x1800c890b  mov     [rsp+188h+var_156], 1
0x1800c8910  mov     rbx, rsi
0x1800c8913  mov     [rsp+188h+var_128], rbx
0x1800c8918  cmp     rbx, r9
0x1800c891b  jnb     loc_1800C8F05
0x1800c8921  lea     rcx, [rsp+188h+lpExistingFileName]
0x1800c8926  call    ??0?$AutoNewPtr@VCDetectUpdate@@@Windows@@QEAA@XZ; Windows::AutoNewPtr<CDetectUpdate>::AutoNewPtr<CDetectUpdate>(void)
0x1800c892b  cmp     r14, [r10]
0x1800c892e  jb      short loc_1800C8937
0x1800c8930  mov     ecx, 8
0x1800c8935  int     29h; Win8: RtlFailFast(ecx)
0x1800c8937  mov     rdx, [rdx+38h]
0x1800c893b  test    r8d, r8d
0x1800c893e  jnz     short loc_1800C8962
0x1800c8940  mov     rax, [rdx+r14*8]
0x1800c8944  test    byte ptr [rax], 20h
0x1800c8947  jz      short loc_1800C8962
0x1800c8949  lea     rax, [r14+1]
0x1800c894d  xor     edx, edx
0x1800c894f  div     r9
0x1800c8952  mov     r14, rdx
0x1800c8955  mov     [rsp+188h+var_108], rdx
0x1800c895d  jmp     loc_1800C8ECF
0x1800c8962  mov     rdx, [rdx+r14*8]
0x1800c8966  mov     r8, [rsp+188h+var_50]
0x1800c896e  mov     rdx, [rdx+8]
0x1800c8972  lea     rcx, [rsp+188h+lpExistingFileName]
0x1800c8977  call    SczAllocConcat2Sz
0x1800c897c  mov     ebx, eax
0x1800c897e  test    eax, eax
0x1800c8980  jns     short loc_1800C89CE
0x1800c8982  mov     rcx, [rsp+188h]; this
0x1800c898a  mov     r9d, eax; char *
0x1800c898d  lea     r8, aOnecoreBaseCbs_111; "onecore\\base\\cbs\\core\\filefetcher.c"...
0x1800c8994  mov     edx, 250h; void *
0x1800c8999  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c899e  lea     rcx, [rsp+188h+lpExistingFileName]
0x1800c89a3  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x1800c89a8  lea     rcx, [rsp+188h+var_E0]; this
0x1800c89b0  call    ?Unimpersonate@ImpersonatorBase@@QEAAXXZ; ImpersonatorBase::Unimpersonate(void)
0x1800c89b5  lea     rcx, [rsp+188h+var_120]
0x1800c89ba  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x1800c89bf  lea     rcx, [rsp+188h+Str]
0x1800c89c4  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x1800c89c9  jmp     loc_1800C8607
0x1800c89ce  mov     rbx, [rsp+188h+lpExistingFileName]
0x1800c89d3  test    r12b, r12b
0x1800c89d6  jz      loc_1800C8A66
0x1800c89dc  mov     r8d, 1; bFailIfExists
0x1800c89e2  mov     rdx, rdi; lpNewFileName
0x1800c89e5  mov     rcx, rbx; lpExistingFileName
0x1800c89e8  call    cs:__imp_CopyFileW
0x1800c89ef  nop     dword ptr [rax+rax+00h]
0x1800c89f4  test    eax, eax
0x1800c89f6  jz      loc_1800C8B84
0x1800c89fc  mov     [rsp+188h+var_C8], rdi
0x1800c8a04  mov     [rsp+188h+var_C0], rbx
0x1800c8a0c  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800c8a13  test    rcx, rcx
0x1800c8a16  jz      short loc_1800C8A47
0x1800c8a18  lea     rax, [rsp+188h+var_C8]
0x1800c8a20  mov     [rsp+188h+var_160], rax
0x1800c8a25  lea     rax, [rsp+188h+var_C0]
0x1800c8a2d  mov     qword ptr [rsp+188h+var_168], rax
0x1800c8a32  lea     r9, aSourceCopiedFi; "Source: Copied file {} to {}"
0x1800c8a39  mov     r8d, 1
0x1800c8a3f  mov     dl, r8b
0x1800c8a42  call    ??$LogNumObjects@PEB_WPEA_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_WAEBQEA_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *,wchar_t *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &,wchar_t * const &)
0x1800c8a47  mov     r15d, 1
0x1800c8a4d  mov     [rsp+188h+var_148], r15d
0x1800c8a52  lea     rcx, [rsp+188h+lpExistingFileName]
0x1800c8a57  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x1800c8a5c  mov     rbx, [rsp+188h+var_110]
0x1800c8a61  jmp     loc_1800C8F0A
0x1800c8a66  cmp     [rsp+188h+var_157], sil
0x1800c8a6b  jz      loc_1800C8AF8
0x1800c8a71  xor     r8d, r8d; dwFlags
0x1800c8a74  mov     rdx, rdi; lpNewFileName
0x1800c8a77  mov     rcx, rbx; lpExistingFileName
0x1800c8a7a  call    cs:__imp_MoveFileExW
0x1800c8a81  nop     dword ptr [rax+rax+00h]
0x1800c8a86  test    eax, eax
0x1800c8a88  jz      loc_1800C8B84
0x1800c8a8e  mov     [rsp+188h+var_B8], rdi
  ... truncated ...
```
