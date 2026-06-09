# BitsHelper::CreateDownloadJob(void *,ushort const *,ushort const *,ushort const *,ushort const *,_GUID &,wil::com_ptr_t<IBackgroundCopyJob5,wil::err_exception_policy> &)

- ea: `0x14000fa90`
- end: `0x14000ff75`
- name: `?CreateDownloadJob@BitsHelper@@AEAAJPEAXPEBG111AEAU_GUID@@AEAV?$com_ptr_t@UIBackgroundCopyJob5@@Uerr_exception_policy@wil@@@wil@@@Z`
- size: `1253`
- prototype: `__int64 __fastcall(__int64, void *, __int64, GUID *, const WCHAR *pszPath, __int64, __int64, __int64 (__fastcall ****)(__int64, GUID *, struct IBitsTokenOptions **))`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x140010ce8`

## callees

- `0x140002f40`
- `0x140003ab8`
- `0x140005320`
- `0x140005cac`
- `0x14000a49c`
- `0x14000a4bc`
- `0x14000a4e0`
- `0x14000cc54`
- `0x14000dda4`
- `0x14000df28`
- `0x14000f5b0`
- `0x14000fa90`
- `0x140011674`
- `0x1400151f8`
- `0x14001a010`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x14000fe40`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x14000fe40`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x14000fec9`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x14000ff32`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x14000fec9`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x14000ff32`
- `api-ms-win-shell-shdirectory-l1-1-0!__imp_SHCreateDirectoryExW` at `0x14000fb5b`
- `api-ms-win-shell-shdirectory-l1-1-0!__imp_SHCreateDirectoryExW` at `0x14000fb5b`

## string_xrefs

- `0x14000fb79`: `onecore\windows\directx\database\updater\exe\bitshelper.cpp`
- `0x14000fbd6`: `onecore\windows\directx\database\updater\exe\bitshelper.cpp`
- `0x14000fc4d`: `onecore\windows\directx\database\updater\exe\bitshelper.cpp`
- `0x14000fe51`: `onecore\windows\directx\database\updater\exe\bitshelper.cpp`
- `0x14000fea7`: `onecore\windows\directx\database\updater\exe\bitshelper.cpp`

## pseudocode

```c
__int64 __fastcall BitsHelper::CreateDownloadJob(
        __int64 a1,
        void *a2,
        __int64 a3,
        GUID *a4,
        const WCHAR *pszPath,
        __int64 a6,
        __int64 a7,
        __int64 (__fastcall ****a8)(__int64, GUID *, struct IBitsTokenOptions **))
{
  __int64 v11; // rax
  int v12; // edi
  unsigned int v13; // eax
  unsigned int LastError; // ebx
  int v15; // eax
  const unsigned __int16 *v16; // rdx
  bool v17; // r8
  int v18; // edi
  char v19; // al
  __int64 (__fastcall *v20)(__int64, _QWORD *, _QWORD, _QWORD); // r10
  __int64 v21; // r11
  _QWORD *v22; // rdx
  __int64 v23; // rdx
  __int64 (__fastcall ***v24)(_QWORD, GUID *, _QWORD **); // rdi
  __int64 (__fastcall *v25)(_QWORD, GUID *, _QWORD **); // r14
  __int64 (__fastcall ***v26)(__int64, GUID *, struct IBitsTokenOptions **); // rcx
  const char *v27; // r9
  __int64 (__fastcall ***v28)(__int64, GUID *, struct IBitsTokenOptions **); // rcx
  __int64 (__fastcall **v29)(__int64, GUID *, struct IBitsTokenOptions **); // rax
  int v30; // eax
  BitsHelper *v31; // rcx
  __int64 v32; // rdx
  unsigned int v34; // [rsp+20h] [rbp-E0h]
  int v35[2]; // [rsp+30h] [rbp-D0h] BYREF
  struct IBitsTokenOptions *v36; // [rsp+38h] [rbp-C8h] BYREF
  char v37; // [rsp+40h] [rbp-C0h]
  _BYTE v38[24]; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD v39[4]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v40[32]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v41[32]; // [rsp+B0h] [rbp-50h] BYREF
  WCHAR ExistingFileName[264]; // [rsp+D0h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+338h] [rbp+238h]

  *(_QWORD *)v38 = a7;
  LODWORD(v36) = 0;
  if ( a2 )
  {
    v11 = std::wstring::wstring(v40, L"DirectX_Database_Download_AsUser_");
    v12 = 2;
  }
  else
  {
    v11 = std::wstring::wstring(v41, L"DirectX_Database_Download_");
    v12 = 1;
  }
  LODWORD(v36) = v12;
  std::operator+<unsigned short>(v39, v11, a3);
  if ( (v12 & 2) != 0 )
  {
    LOBYTE(v12) = v12 & 0xFD;
    std::wstring::_Tidy_deallocate(v40);
  }
  if ( (v12 & 1) != 0 )
    std::wstring::_Tidy_deallocate(v41);
  v13 = SHCreateDirectoryExW(0, pszPath, 0);
  if ( v13 == 183 || !v13 )
  {
    memset_0(ExistingFileName, 0, 0x208u);
    v15 = StringCchPrintfW(ExistingFileName, 0x104u, L"%ws\\%ws", pszPath);
    v18 = v15;
    if ( v15 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xE7,
        (unsigned int)"onecore\\windows\\directx\\database\\updater\\exe\\bitshelper.cpp",
        (const char *)(unsigned int)v15,
        (int)L"DirectXApps.lzma");
LABEL_13:
      LastError = v18;
      goto LABEL_54;
    }
    LOBYTE(v16) = 1;
    DxDbFileCompression::DeleteFileImpl(ExistingFileName, v16, v17);
    *(_QWORD *)v35 = 0;
    v19 = std::_String_val<std::_Simple_types<unsigned short>>::_Large_mode_engaged(v39);
    v22 = v39;
    if ( v19 )
      v22 = (_QWORD *)v39[0];
    v18 = v20(v21, v22, 0, *(_QWORD *)v38);
    if ( v18 < 0 )
    {
      v23 = 237;
LABEL_18:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v23,
        (unsigned int)"onecore\\windows\\directx\\database\\updater\\exe\\bitshelper.cpp",
        (const char *)(unsigned int)v18,
        (int)v35);
      wil::com_ptr_t<IPrincipal,wil::err_exception_policy>::~com_ptr_t<IPrincipal,wil::err_exception_policy>(v35);
      goto LABEL_13;
    }
    v24 = *(__int64 (__fastcall ****)(_QWORD, GUID *, _QWORD **))v35;
    v25 = ***(__int64 (__fastcall ****)(_QWORD, GUID *, _QWORD **))v35;
    v26 = *a8;
    *a8 = 0;
    if ( v26 )
      ((void (__fastcall *)(__int64 (__fastcall ***)(__int64, GUID *, struct IBitsTokenOptions **)))(*v26)[2])(v26);
    v18 = v25(v24, &GUID_e847030c_bbba_4657_af6d_484aa42bf1fe, a8);
    if ( v18 < 0 )
    {
      v23 = 238;
      goto LABEL_18;
    }
    v18 = (**a8)[4]((__int64)*a8, a4, (struct IBitsTokenOptions **)ExistingFileName);
    if ( v18 < 0 )
    {
      v23 = 241;
      goto LABEL_18;
    }
    v18 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(__int64, GUID *, struct IBitsTokenOptions **), __int64))(**a8)[21])(
            *a8,
            2);
    if ( v18 < 0 )
    {
      v23 = 244;
      goto LABEL_18;
    }
    *(_OWORD *)v38 = 0;
    *(_DWORD *)v38 = -2147483545;
    v18 = (**a8)[53]((__int64)*a8, (GUID *)1, (struct IBitsTokenOptions **)v38);
    if ( v18 < 0 )
    {
      v23 = 248;
      goto LABEL_18;
    }
    v18 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(__int64, GUID *, struct IBitsTokenOptions **), __int64))(**a8)[27])(
            *a8,
            600);
    if ( v18 < 0 )
    {
      v23 = 251;
      goto LABEL_18;
    }
    v18 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(__int64, GUID *, struct IBitsTokenOptions **), __int64))(**a8)[29])(
            *a8,
            64800);
    if ( v18 < 0 )
    {
      v23 = 257;
      goto LABEL_18;
    }
    if ( a2 )
    {
      *(_QWORD *)v38 = 0x400000002LL;
      *(_OWORD *)&v38[8] = 0;
      v18 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(__int64, GUID *, struct IBitsTokenOptions **), _BYTE *))(**a8)[41])(
              *a8,
              v38);
      if ( v18 < 0 )
      {
        v23 = 269;
        goto LABEL_18;
      }
      *(_DWORD *)&v38[4] = 3;
      v18 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(__int64, GUID *, struct IBitsTokenOptions **), _BYTE *))(**a8)[41])(
              *a8,
              v38);
      if ( v18 < 0 )
      {
        v23 = 273;
        goto LABEL_18;
      }
      v18 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(__int64, GUID *, struct IBitsTokenOptions **), _QWORD, _QWORD, _QWORD))(**a8)[32])(
              *a8,
              0,
              0,
              0);
      if ( v18 < 0 )
      {
        v23 = 276;
        goto LABEL_18;
      }
      if ( !ImpersonateLoggedOnUser(a2) )
      {
        LastError = wil::details::in1diag3::Return_GetLastError(
                      retaddr,
                      (void *)0x117,
                      (unsigned int)"onecore\\windows\\directx\\database\\updater\\exe\\bitshelper.cpp",
                      v27);
LABEL_42:
        wil::com_ptr_t<IPrincipal,wil::err_exception_policy>::~com_ptr_t<IPrincipal,wil::err_exception_policy>(v35);
        goto LABEL_54;
      }
      v37 = 1;
      v36 = 0;
      v28 = *a8;
      v29 = **a8;
      v36 = 0;
      v30 = (*v29)((__int64)v28, &GUID_9a2584c3_f7d2_457a_9a5e_22b67bffc7d2, &v36);
      LastError = v30;
      if ( v30 < 0 )
      {
        v32 = 283;
LABEL_45:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v32,
          (unsigned int)"onecore\\windows\\directx\\database\\updater\\exe\\bitshelper.cpp",
          (const char *)(unsigned int)v30,
          (int)v35);
        wil::com_ptr_t<IPrincipal,wil::err_exception_policy>::~com_ptr_t<IPrincipal,wil::err_exception_policy>(&v36);
        RevertToSelf();
        goto LABEL_42;
      }
      v30 = BitsHelper::SetBITSProxyBlanketImpersonationLevelAndDynamicCloaking(v31, v36);
      LastError = v30;
      if ( v30 < 0 )
      {
        v32 = 285;
        goto LABEL_45;
      }
      v30 = ((__int64 (__fastcall *)(struct IBitsTokenOptions *))v36->lpVtbl->SetHelperToken)(v36);
      LastError = v30;
      if ( v30 < 0 )
      {
        v32 = 287;
        goto LABEL_45;
      }
      v30 = ((__int64 (__fastcall *)(struct IBitsTokenOptions *, __int64))v36->lpVtbl->SetHelperTokenFlags)(v36, 2);
      LastError = v30;
      if ( v30 < 0 )
      {
        v32 = 288;
        goto LABEL_45;
      }
      wil::com_ptr_t<IPrincipal,wil::err_exception_policy>::~com_ptr_t<IPrincipal,wil::err_exception_policy>(&v36);
      RevertToSelf();
    }
    wil::com_ptr_t<IPrincipal,wil::err_exception_policy>::~com_ptr_t<IPrincipal,wil::err_exception_policy>(v35);
    LastError = 0;
    goto LABEL_54;
  }
  LastError = wil::details::in1diag3::Return_Win32(
                retaddr,
                (void *)0xE1,
                (unsigned int)"onecore\\windows\\directx\\database\\updater\\exe\\bitshelper.cpp",
                (const char *)v13,
                v34);
LABEL_54:
  std::wstring::_Tidy_deallocate(v39);
  return LastError;
}

```

## disassembly

```asm
0x14000fa90  push    rbp
0x14000fa92  push    rbx
0x14000fa93  push    rsi
0x14000fa94  push    rdi
0x14000fa95  push    r12
0x14000fa97  push    r13
0x14000fa99  push    r14
0x14000fa9b  push    r15
0x14000fa9d  lea     rbp, [rsp-1F8h]
0x14000faa5  sub     rsp, 2F8h
0x14000faac  mov     rax, cs:__security_cookie
0x14000fab3  xor     rax, rsp
0x14000fab6  mov     [rbp+230h+var_50], rax
0x14000fabd  mov     r12, r9
0x14000fac0  mov     r15, r8
0x14000fac3  mov     rsi, rdx
0x14000fac6  mov     r13, rcx
0x14000fac9  mov     rbx, [rbp+230h+arg_38]
0x14000fad0  mov     r14, [rbp+230h+pszPath]
0x14000fad7  mov     rax, [rbp+230h+arg_30]
0x14000fade  mov     qword ptr [rsp+330h+var_2E0], rax
0x14000fae3  mov     dword ptr [rsp+330h+var_2F8], 0
0x14000faeb  test    rdx, rdx
0x14000faee  jnz     short loc_14000FB06
0x14000faf0  lea     rdx, aDirectxDatabas; "DirectX_Database_Download_"
0x14000faf7  lea     rcx, [rbp+230h+var_280]
0x14000fafb  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x14000fb00  nop
0x14000fb01  lea     edi, [rsi+1]
0x14000fb04  jmp     short loc_14000FB1C
0x14000fb06  lea     rdx, aDirectxDatabas_0; "DirectX_Database_Download_AsUser_"
0x14000fb0d  lea     rcx, [rbp+230h+var_2A0]
0x14000fb11  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x14000fb16  nop
0x14000fb17  mov     edi, 2
0x14000fb1c  mov     dword ptr [rsp+330h+var_2F8], edi
0x14000fb20  mov     r8, r15
0x14000fb23  mov     rdx, rax
0x14000fb26  lea     rcx, [rsp+330h+var_2C0]
0x14000fb2b  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x14000fb30  nop
0x14000fb31  test    dil, 2
0x14000fb35  jz      short loc_14000FB44
0x14000fb37  and     edi, 0FFFFFFFDh
0x14000fb3a  lea     rcx, [rbp+230h+var_2A0]
0x14000fb3e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14000fb43  nop
0x14000fb44  test    dil, 1
0x14000fb48  jz      short loc_14000FB53
0x14000fb4a  lea     rcx, [rbp+230h+var_280]
0x14000fb4e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14000fb53  xor     r8d, r8d; psa
0x14000fb56  mov     rdx, r14; pszPath
0x14000fb59  xor     ecx, ecx; hwnd
0x14000fb5b  call    cs:__imp_SHCreateDirectoryExW
0x14000fb61  xor     r15d, r15d
0x14000fb64  cmp     eax, 0B7h
0x14000fb69  jz      short loc_14000FB91
0x14000fb6b  test    eax, eax
0x14000fb6d  jz      short loc_14000FB91
0x14000fb6f  mov     rcx, [rbp+238h]; this
0x14000fb76  mov     r9d, eax; char *
0x14000fb79  lea     r8, aOnecoreWindows; "onecore\\windows\\directx\\database\\up"...
0x14000fb80  mov     edx, 0E1h; void *
0x14000fb85  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x14000fb8a  mov     ebx, eax
0x14000fb8c  jmp     loc_14000FF46
0x14000fb91  xor     edx, edx; Val
0x14000fb93  mov     r8d, 208h; Size
0x14000fb99  lea     rcx, [rbp+230h+ExistingFileName]; void *
0x14000fb9d  call    memset_0
0x14000fba2  lea     rax, aDirectxappsLzm; "DirectXApps.lzma"
0x14000fba9  mov     qword ptr [rsp+330h+var_310], rax; int
0x14000fbae  mov     r9, r14
0x14000fbb1  lea     r8, aWsWs; "%ws\\%ws"
0x14000fbb8  mov     edx, 104h; unsigned __int64
0x14000fbbd  lea     rcx, [rbp+230h+ExistingFileName]; unsigned __int16 *
0x14000fbc1  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14000fbc6  mov     edi, eax
0x14000fbc8  test    eax, eax
0x14000fbca  jns     short loc_14000FBEE
0x14000fbcc  mov     rcx, [rbp+238h]; this
0x14000fbd3  mov     r9d, eax; char *
0x14000fbd6  lea     r8, aOnecoreWindows; "onecore\\windows\\directx\\database\\up"...
0x14000fbdd  mov     edx, 0E7h; void *
0x14000fbe2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000fbe7  mov     ebx, edi
0x14000fbe9  jmp     loc_14000FF46
0x14000fbee  mov     dl, 1; unsigned __int16 *
0x14000fbf0  lea     rcx, [rbp+230h+ExistingFileName]; lpExistingFileName
0x14000fbf4  call    ?DeleteFileImpl@DxDbFileCompression@@YAXPEBG_N@Z; DxDbFileCompression::DeleteFileImpl(ushort const *,bool)
0x14000fbf9  mov     qword ptr [rsp+330h+var_300], r15
0x14000fbfe  mov     r11, [r13+0]
0x14000fc02  mov     rax, [r11]
0x14000fc05  mov     r10, [rax+18h]
0x14000fc09  mov     qword ptr [rsp+330h+var_300], r15
0x14000fc0e  lea     rcx, [rsp+330h+var_2C0]
0x14000fc13  call    ?_Large_mode_engaged@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBA_NXZ; std::_String_val<std::_Simple_types<ushort>>::_Large_mode_engaged(void)
0x14000fc18  lea     rdx, [rsp+330h+var_2C0]
0x14000fc1d  test    al, al
0x14000fc1f  cmovnz  rdx, [rsp+330h+var_2C0]
0x14000fc25  lea     rax, [rsp+330h+var_300]
0x14000fc2a  mov     qword ptr [rsp+330h+var_310], rax; int
0x14000fc2f  mov     r9, qword ptr [rsp+330h+var_2E0]
0x14000fc34  xor     r8d, r8d
0x14000fc37  mov     rcx, r11
0x14000fc3a  mov     rax, r10
0x14000fc3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000fc42  mov     edi, eax
0x14000fc44  test    eax, eax
0x14000fc46  jns     short loc_14000FC73
0x14000fc48  mov     edx, 0EDh; void *
0x14000fc4d  lea     r8, aOnecoreWindows; "onecore\\windows\\directx\\database\\up"...
0x14000fc54  mov     r9d, edi; char *
0x14000fc57  mov     rcx, [rbp+238h]; this
0x14000fc5e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000fc63  nop
0x14000fc64  lea     rcx, [rsp+330h+var_300]
0x14000fc69  call    ??1?$com_ptr_t@UIPrincipal@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IPrincipal,wil::err_exception_policy>::~com_ptr_t<IPrincipal,wil::err_exception_policy>(void)
0x14000fc6e  jmp     loc_14000FBE7
0x14000fc73  mov     rdi, qword ptr [rsp+330h+var_300]
0x14000fc78  mov     rax, [rdi]
0x14000fc7b  mov     r14, [rax]
0x14000fc7e  mov     rcx, [rbx]
0x14000fc81  mov     [rbx], r15
0x14000fc84  test    rcx, rcx
0x14000fc87  jz      short loc_14000FC96
0x14000fc89  mov     rdx, [rcx]
0x14000fc8c  mov     rax, [rdx+10h]
0x14000fc90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000fc95  nop
0x14000fc96  mov     r8, rbx
0x14000fc99  lea     rdx, _GUID_e847030c_bbba_4657_af6d_484aa42bf1fe
0x14000fca0  mov     rcx, rdi
0x14000fca3  mov     rax, r14
0x14000fca6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000fcab  mov     edi, eax
0x14000fcad  test    eax, eax
0x14000fcaf  jns     short loc_14000FCB8
0x14000fcb1  mov     edx, 0EEh
0x14000fcb6  jmp     short loc_14000FC4D
0x14000fcb8  mov     rcx, [rbx]
0x14000fcbb  mov     rax, [rcx]
0x14000fcbe  lea     r8, [rbp+230h+ExistingFileName]
0x14000fcc2  mov     rdx, r12
0x14000fcc5  mov     rax, [rax+20h]
0x14000fcc9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000fcce  mov     edi, eax
0x14000fcd0  test    eax, eax
0x14000fcd2  jns     short loc_14000FCDE
0x14000fcd4  mov     edx, 0F1h
0x14000fcd9  jmp     loc_14000FC4D
0x14000fcde  mov     rcx, [rbx]
0x14000fce1  mov     rax, [rcx]
0x14000fce4  mov     r14d, 2
0x14000fcea  mov     edx, r14d
0x14000fced  mov     rax, [rax+0A8h]
0x14000fcf4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000fcf9  mov     edi, eax
0x14000fcfb  test    eax, eax
0x14000fcfd  jns     short loc_14000FD09
0x14000fcff  mov     edx, 0F4h
0x14000fd04  jmp     loc_14000FC4D
0x14000fd09  xorps   xmm0, xmm0
0x14000fd0c  movups  [rsp+330h+var_2E0], xmm0
0x14000fd11  mov     dword ptr [rsp+330h+var_2E0], 80000067h
0x14000fd19  mov     rcx, [rbx]
0x14000fd1c  movaps  xmm0, [rsp+330h+var_2E0]
0x14000fd21  movdqa  [rsp+330h+var_2E0], xmm0
0x14000fd27  mov     rax, [rcx]
0x14000fd2a  lea     r8, [rsp+330h+var_2E0]
0x14000fd2f  mov     edx, 1
0x14000fd34  mov     rax, [rax+1A8h]
0x14000fd3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000fd40  mov     edi, eax
0x14000fd42  test    eax, eax
0x14000fd44  jns     short loc_14000FD50
0x14000fd46  mov     edx, 0F8h
0x14000fd4b  jmp     loc_14000FC4D
0x14000fd50  mov     rcx, [rbx]
0x14000fd53  mov     rax, [rcx]
0x14000fd56  mov     edx, 258h
0x14000fd5b  mov     rax, [rax+0D8h]
0x14000fd62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000fd67  mov     edi, eax
0x14000fd69  test    eax, eax
0x14000fd6b  jns     short loc_14000FD77
0x14000fd6d  mov     edx, 0FBh
0x14000fd72  jmp     loc_14000FC4D
0x14000fd77  mov     rcx, [rbx]
0x14000fd7a  mov     rax, [rcx]
0x14000fd7d  mov     edx, 0FD20h
0x14000fd82  mov     rax, [rax+0E8h]
0x14000fd89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000fd8e  mov     edi, eax
0x14000fd90  test    eax, eax
0x14000fd92  jns     short loc_14000FD9E
0x14000fd94  mov     edx, 101h
0x14000fd99  jmp     loc_14000FC4D
0x14000fd9e  test    rsi, rsi
0x14000fda1  jz      loc_14000FF39
0x14000fda7  mov     dword ptr [rsp+330h+var_2E0], r14d
0x14000fdac  xorps   xmm0, xmm0
0x14000fdaf  movdqu  [rsp+330h+var_2E0+8], xmm0
0x14000fdb5  mov     dword ptr [rsp+330h+var_2E0+4], 4
0x14000fdbd  mov     rcx, [rbx]
0x14000fdc0  mov     rax, [rcx]
0x14000fdc3  lea     rdx, [rsp+330h+var_2E0]
0x14000fdc8  mov     rax, [rax+148h]
0x14000fdcf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000fdd4  mov     edi, eax
0x14000fdd6  test    eax, eax
0x14000fdd8  jns     short loc_14000FDE4
0x14000fdda  mov     edx, 10Dh
0x14000fddf  jmp     loc_14000FC4D
0x14000fde4  mov     dword ptr [rsp+330h+var_2E0+4], 3
0x14000fdec  mov     rcx, [rbx]
0x14000fdef  mov     rax, [rcx]
0x14000fdf2  lea     rdx, [rsp+330h+var_2E0]
0x14000fdf7  mov     rax, [rax+148h]
0x14000fdfe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000fe03  mov     edi, eax
0x14000fe05  test    eax, eax
0x14000fe07  jns     short loc_14000FE13
0x14000fe09  mov     edx, 111h
0x14000fe0e  jmp     loc_14000FC4D
0x14000fe13  mov     rcx, [rbx]
0x14000fe16  mov     rax, [rcx]
0x14000fe19  xor     r9d, r9d
0x14000fe1c  xor     r8d, r8d
0x14000fe1f  xor     edx, edx
0x14000fe21  mov     rax, [rax+100h]
0x14000fe28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000fe2d  mov     edi, eax
0x14000fe2f  test    eax, eax
0x14000fe31  jns     short loc_14000FE3D
0x14000fe33  mov     edx, 114h
0x14000fe38  jmp     loc_14000FC4D
0x14000fe3d  mov     rcx, rsi; hToken
0x14000fe40  call    cs:__imp_ImpersonateLoggedOnUser
0x14000fe46  test    eax, eax
0x14000fe48  jnz     short loc_14000FE73
0x14000fe4a  mov     rcx, [rbp+238h]; this
0x14000fe51  lea     r8, aOnecoreWindows; "onecore\\windows\\directx\\database\\up"...
0x14000fe58  mov     edx, 117h; void *
0x14000fe5d  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14000fe62  mov     ebx, eax
0x14000fe64  lea     rcx, [rsp+330h+var_300]
0x14000fe69  call    ??1?$com_ptr_t@UIPrincipal@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IPrincipal,wil::err_exception_policy>::~com_ptr_t<IPrincipal,wil::err_exception_policy>(void)
0x14000fe6e  jmp     loc_14000FF46
0x14000fe73  mov     [rsp+330h+var_2F0], 1
0x14000fe78  mov     [rsp+330h+var_2F8], r15
0x14000fe7d  mov     rcx, [rbx]
0x14000fe80  mov     rax, [rcx]
0x14000fe83  mov     [rsp+330h+var_2F8], r15
0x14000fe88  lea     r8, [rsp+330h+var_2F8]
0x14000fe8d  lea     rdx, _GUID_9a2584c3_f7d2_457a_9a5e_22b67bffc7d2
0x14000fe94  mov     rax, [rax]
0x14000fe97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000fe9c  mov     ebx, eax
0x14000fe9e  test    eax, eax
0x14000fea0  jns     short loc_14000FED1
0x14000fea2  mov     edx, 11Bh; void *
0x14000fea7  lea     r8, aOnecoreWindows; "onecore\\windows\\directx\\database\\up"...
0x14000feae  mov     r9d, eax; char *
0x14000feb1  mov     rcx, [rbp+238h]; this
0x14000feb8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000febd  nop
0x14000febe  lea     rcx, [rsp+330h+var_2F8]
0x14000fec3  call    ??1?$com_ptr_t@UIPrincipal@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IPrincipal,wil::err_exception_policy>::~com_ptr_t<IPrincipal,wil::err_exception_policy>(void)
0x14000fec8  nop
0x14000fec9  call    cs:__imp_RevertToSelf
0x14000fecf  jmp     short loc_14000FE64
0x14000fed1  mov     rdx, [rsp+330h+var_2F8]; struct IBitsTokenOptions *
0x14000fed6  call    ?SetBITSProxyBlanketImpersonationLevelAndDynamicCloaking@BitsHelper@@AEAAJPEAUIBitsTokenOptions@@@Z; BitsHelper::SetBITSProxyBlanketImpersonationLevelAndDynamicCloaking(IBitsTokenOptions *)
0x14000fedb  mov     ebx, eax
0x14000fedd  test    eax, eax
0x14000fedf  jns     short loc_14000FEE8
0x14000fee1  mov     edx, 11Dh
0x14000fee6  jmp     short loc_14000FEA7
0x14000fee8  mov     rcx, [rsp+330h+var_2F8]
0x14000feed  mov     rax, [rcx]
0x14000fef0  mov     rax, [rax+28h]
0x14000fef4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000fef9  mov     ebx, eax
0x14000fefb  test    eax, eax
0x14000fefd  jns     short loc_14000FF06
0x14000feff  mov     edx, 11Fh
0x14000ff04  jmp     short loc_14000FEA7
0x14000ff06  mov     rcx, [rsp+330h+var_2F8]
0x14000ff0b  mov     rax, [rcx]
0x14000ff0e  mov     edx, r14d
0x14000ff11  mov     rax, [rax+18h]
0x14000ff15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ff1a  mov     ebx, eax
0x14000ff1c  test    eax, eax
0x14000ff1e  jns     short loc_14000FF27
0x14000ff20  mov     edx, 120h
0x14000ff25  jmp     short loc_14000FEA7
0x14000ff27  lea     rcx, [rsp+330h+var_2F8]
  ... truncated ...
```
