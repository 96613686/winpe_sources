# CUserProfileRoamingProvider::_UploadProfileDirectory(int)

- ea: `0x180008258`
- end: `0x180008810`
- name: `?_UploadProfileDirectory@CUserProfileRoamingProvider@@AEAAJH@Z`
- size: `1464`
- prototype: `__int64 __fastcall(CUserProfileRoamingProvider *__hidden this, int)`
- caller_count: `1`
- callee_count: `22`
- tags: `file_ops, authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800159b0`

## callees

- `0x180005960`
- `0x180006a9c`
- `0x180006b18`
- `0x180008258`
- `0x180008818`
- `0x180008b1c`
- `0x180008e5c`
- `0x180008f88`
- `0x1800090e0`
- `0x18000927c`
- `0x1800092d4`
- `0x180009588`
- `0x18000a074`
- `0x18000a520`
- `0x18000aef8`
- `0x18000fca8`
- `0x1800102e0`
- `0x180013aac`
- `0x180016a1c`
- `0x180016e20`
- `0x18001dd20`
- `0x180020010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800084ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008741`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800084ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008741`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180008737`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180008737`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18000872c`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18000872c`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18000866b`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180008713`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18000866b`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180008713`
- `USERENV!__imp_CopyProfileDirectoryEx2` at `0x1800084f1`
- `USERENV!__imp_CopyProfileDirectoryEx2` at `0x1800084f1`
- `profapi!__imp_GetBasicProfileFolderPath` at `0x1800085f0`
- `profapi!__imp_GetBasicProfileFolderPath` at `0x1800085f0`

## string_xrefs

- `0x1800082b8`: `clientcore\ds\security\gina\profile\roaming\roaming.cpp`
- `0x1800082f0`: `clientcore\ds\security\gina\profile\roaming\roaming.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CUserProfileRoamingProvider::_UploadProfileDirectory(CUserProfileRoamingProvider *this, int a2)
{
  __int64 *v4; // rdi
  __int64 v5; // rbx
  __int64 v6; // rax
  int v7; // ebx
  __int64 v8; // rdx
  const unsigned __int16 *v9; // rax
  int IsBypassPathNeeded; // eax
  int v11; // ecx
  const unsigned __int16 *v12; // rax
  unsigned __int64 v13; // r8
  const unsigned __int16 *v14; // rax
  int v15; // eax
  void *v16; // rax
  int v17; // eax
  unsigned int v18; // r12d
  const unsigned __int16 *v19; // rax
  CUserProfileRoamingProvider *v20; // rcx
  int v21; // eax
  __int64 v22; // rsi
  __int64 v23; // rdi
  __int64 v24; // rbx
  __int64 v25; // rax
  CUserProfileRoamingProvider *v26; // rcx
  int v27; // ecx
  DWORD LastError; // ebx
  int v29; // r8d
  __int64 *v30; // rdx
  signed int v31; // eax
  __int64 v32; // rdx
  DWORD FileAttributesW; // eax
  const unsigned __int16 *v34; // rbx
  const unsigned __int16 *v35; // rax
  CUserProfileRoamingProvider *v36; // rcx
  __int64 v37; // rax
  DWORD v38; // eax
  int v39; // eax
  int v40; // eax
  int v41; // eax
  int v43; // [rsp+20h] [rbp-E0h]
  unsigned int v44; // [rsp+20h] [rbp-E0h]
  const int *v45; // [rsp+20h] [rbp-E0h]
  int v46; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v47; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v48; // [rsp+50h] [rbp-B0h] BYREF
  char v49; // [rsp+58h] [rbp-A8h]
  unsigned int v50[4]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR v51[264]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v52[528]; // [rsp+280h] [rbp+180h] BYREF
  WCHAR FileName[1032]; // [rsp+490h] [rbp+390h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+CE8h] [rbp+BE8h]

  v4 = (__int64 *)*((_QWORD *)this + 1);
  v5 = *v4;
  v6 = (*(__int64 (__fastcall **)(__int64 *))(*v4 + 80))(v4);
  v7 = (*(__int64 (__fastcall **)(__int64 *, __int64))(v5 + 64))(v4, v6);
  if ( v7 >= 0 )
  {
    v9 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 1) + 56LL))(*((_QWORD *)this + 1));
    if ( (unsigned int)IsUNCPath(v9) )
    {
      v46 = 0;
      IsBypassPathNeeded = CUserProfileRoamingProvider::_IsBypassPathNeeded(this, 0, &v46);
      v11 = v46;
      if ( IsBypassPathNeeded < 0 )
        v11 = 1;
      if ( v11 )
      {
        v12 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 1) + 56LL))(*((_QWORD *)this + 1));
        if ( GetCscBypassPath(v12, v51, v13) < 0 )
        {
          v14 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 1) + 56LL))(*((_QWORD *)this + 1));
          v15 = StringCchCopyW(v51, 0x104u, v14);
          if ( v15 < 0 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x9D3,
              (int)"clientcore\\ds\\security\\gina\\profile\\roaming\\roaming.cpp",
              (const char *)(unsigned int)v15);
        }
        v7 = (*(__int64 (__fastcall **)(_QWORD, WCHAR *))(**((_QWORD **)this + 1) + 96LL))(*((_QWORD *)this + 1), v51);
        if ( v7 < 0 )
        {
          v8 = 2519;
          goto LABEL_3;
        }
      }
    }
    v48 = 0;
    v49 = 0;
    v16 = (void *)(***((__int64 (__fastcall ****)(_QWORD))this + 1))(*((_QWORD *)this + 1));
    v17 = CAutoImpersonate::ImpersonateUser((CAutoImpersonate *)&v48, v16);
    v7 = v17;
    if ( v17 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x9DF,
        (unsigned int)"clientcore\\ds\\security\\gina\\profile\\roaming\\roaming.cpp",
        (const char *)(unsigned int)v17,
        v43);
LABEL_51:
      CAutoImpersonate::ResetImpersonation((CAutoImpersonate *)&v48);
      return (unsigned int)v7;
    }
    v18 = (a2 != 0 ? 1059840 : 11264)
        | (((*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 1) + 8LL))(*((_QWORD *)this + 1)) & 0xC) != 0
         ? 135168
         : 16416);
    v19 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 1) + 56LL))(*((_QWORD *)this + 1));
    v21 = CUserProfileRoamingProvider::_SetNtUserPolTime(v20, v19, a2);
    if ( v21 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x9ED,
        (int)"clientcore\\ds\\security\\gina\\profile\\roaming\\roaming.cpp",
        (const char *)(unsigned int)v21);
    v47 = 0;
    (*(void (__fastcall **)(_QWORD, __int64 *))(**((_QWORD **)this + 1) + 136LL))(*((_QWORD *)this + 1), &v47);
    v22 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 1) + 168LL))(*((_QWORD *)this + 1));
    v23 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 1) + 104LL))(*((_QWORD *)this + 1));
    v24 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 1) + 80LL))(*((_QWORD *)this + 1));
    v25 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 1) + 72LL))(*((_QWORD *)this + 1));
    if ( !(unsigned int)CopyProfileDirectoryEx2(v25, v24, v18, &v47, v23, v22) )
    {
      LastError = GetLastError();
      if ( LastError == 6002 )
      {
        if ( (Microsoft_Windows_User_Profiles_ServiceEnableBits & 1) == 0 )
          goto LABEL_24;
        v30 = EVENT_PROFILEUPDATE_6002;
      }
      else
      {
        if ( (Microsoft_Windows_User_Profiles_ServiceEnableBits & 1) == 0 )
          goto LABEL_24;
        v30 = EVENT_CENTRAL_UPDATE_FAILED;
      }
      McGenEventWrite_EtwEventWriteTransfer(v27, (_DWORD)v30, v29, 1, (__int64)v50);
LABEL_24:
      (*(void (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 1) + 192LL))(*((_QWORD *)this + 1), 200);
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 1) + 208LL))(*((_QWORD *)this + 1));
      if ( LastError )
      {
        v7 = wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)0xA07,
               (unsigned int)"clientcore\\ds\\security\\gina\\profile\\roaming\\roaming.cpp",
               (const char *)LastError,
               v44);
        goto LABEL_51;
      }
LABEL_50:
      v7 = 0;
      goto LABEL_51;
    }
    if ( !(unsigned int)CUserProfileRoamingProvider::_IsSecureCachingDisabled(v26) )
    {
      memset_0(v51, 0, 0x20Au);
      memset_0(FileName, 0, 0x802u);
      memset_0(v52, 0, 0x20Au);
      if ( (int)GetBasicProfileFolderPath(4, 0, v52, 261) >= 0 )
      {
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 1) + 32LL))(*((_QWORD *)this + 1));
        v45 = (const int *)L"\\Microsoft\\GroupPolicy\\Users\\";
        v31 = StringCchPrintfW(FileName, 0x401u, L"%s%s%s%s%s", v52);
        if ( v31 < 0 )
        {
          v32 = 2585;
LABEL_42:
          wil::details::in1diag3::Log_Hr(
            retaddr,
            (void *)v32,
            (unsigned int)"clientcore\\ds\\security\\gina\\profile\\roaming\\roaming.cpp",
            (const char *)(unsigned int)v31,
            (int)v45);
          goto LABEL_43;
        }
        FileAttributesW = GetFileAttributesW(FileName);
        if ( FileAttributesW == -1 || FileAttributesW == 16 )
        {
          v37 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 1) + 80LL))(*((_QWORD *)this + 1));
          v45 = &qword_180023CF8;
          v31 = StringCchPrintfW(v51, 0x105u, L"%s%s%s", v37);
          if ( v31 >= 0 )
          {
            v38 = GetFileAttributesW(v51);
            if ( v38 == -1 )
              goto LABEL_43;
            if ( v38 == 16 )
              goto LABEL_43;
            SetFileAttributesW(v51, 0x80u);
            if ( DeleteFileW(v51) )
              goto LABEL_43;
            v31 = GetLastError();
            if ( v31 > 0 )
              v31 = (unsigned __int16)v31 | 0x80070000;
            v32 = 2615;
          }
          else
          {
            v32 = 2601;
          }
          goto LABEL_42;
        }
        v34 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 1) + 32LL))(*((_QWORD *)this + 1));
        v35 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 1) + 80LL))(*((_QWORD *)this + 1));
        v31 = CUserProfileRoamingProvider::_ProcessNtuserPol(v36, v35, v34, v18, 1);
        if ( v31 < 0 )
        {
          v32 = 2626;
          goto LABEL_42;
        }
      }
    }
LABEL_43:
    v39 = CUserProfileRoamingProvider::_SetServerNtUserIni(this);
    if ( v39 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xA4A,
        (int)"clientcore\\ds\\security\\gina\\profile\\roaming\\roaming.cpp",
        (const char *)(unsigned int)v39);
    v40 = CUserProfileRoamingProvider::_SetLocalNtUserIni(this);
    if ( v40 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xA4B,
        (int)"clientcore\\ds\\security\\gina\\profile\\roaming\\roaming.cpp",
        (const char *)(unsigned int)v40);
    if ( !a2 )
    {
      v41 = CUserProfileRoamingProvider::_SetHiveFileTime(this);
      if ( v41 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0xA57,
          (int)"clientcore\\ds\\security\\gina\\profile\\roaming\\roaming.cpp",
          (const char *)(unsigned int)v41);
    }
    goto LABEL_50;
  }
  v8 = 2498;
LABEL_3:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v8,
    (unsigned int)"clientcore\\ds\\security\\gina\\profile\\roaming\\roaming.cpp",
    (const char *)(unsigned int)v7,
    v43);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180008258  mov     [rsp-8+arg_10], rbx
0x18000825d  push    rbp
0x18000825e  push    rsi
0x18000825f  push    rdi
0x180008260  push    r12
0x180008262  push    r13
0x180008264  push    r14
0x180008266  push    r15
0x180008268  lea     rbp, [rsp-0BB0h]
0x180008270  sub     rsp, 0CB0h
0x180008277  mov     rax, cs:__security_cookie
0x18000827e  xor     rax, rsp
0x180008281  mov     [rbp+0BE0h+var_40], rax
0x180008288  mov     r13d, edx
0x18000828b  mov     r14, rcx
0x18000828e  mov     rdi, [rcx+8]
0x180008292  mov     rbx, [rdi]
0x180008295  mov     rcx, rdi
0x180008298  mov     rax, [rbx+50h]
0x18000829c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800082a1  mov     rdx, rax
0x1800082a4  mov     rcx, rdi
0x1800082a7  mov     rax, [rbx+40h]
0x1800082ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800082b0  mov     ebx, eax
0x1800082b2  xor     edi, edi
0x1800082b4  test    eax, eax
0x1800082b6  jns     short loc_1800082D8
0x1800082b8  lea     r8, aClientcoreDsSe_1; "clientcore\\ds\\security\\gina\\profile"...
0x1800082bf  mov     edx, 9C2h; void *
0x1800082c4  mov     r9d, ebx; char *
0x1800082c7  mov     rcx, [rbp+0BE8h]; this
0x1800082ce  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800082d3  jmp     loc_1800087E4
0x1800082d8  mov     rcx, [r14+8]
0x1800082dc  mov     rax, [rcx]
0x1800082df  mov     rax, [rax+38h]
0x1800082e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800082e8  mov     rcx, rax; unsigned __int16 *
0x1800082eb  call    ?IsUNCPath@@YAHPEBG@Z; IsUNCPath(ushort const *)
0x1800082f0  lea     r15, aClientcoreDsSe_1; "clientcore\\ds\\security\\gina\\profile"...
0x1800082f7  mov     ebx, 1
0x1800082fc  test    eax, eax
0x1800082fe  jz      loc_1800083AE
0x180008304  mov     [rsp+0CE0h+var_CA0], edi
0x180008308  lea     r8, [rsp+0CE0h+var_CA0]; int *
0x18000830d  xor     edx, edx; int
0x18000830f  mov     rcx, r14; this
0x180008312  call    ?_IsBypassPathNeeded@CUserProfileRoamingProvider@@AEAAJHPEAH@Z; CUserProfileRoamingProvider::_IsBypassPathNeeded(int,int *)
0x180008317  mov     ecx, [rsp+0CE0h+var_CA0]
0x18000831b  test    eax, eax
0x18000831d  cmovs   ecx, ebx
0x180008320  test    ecx, ecx
0x180008322  jz      loc_1800083AE
0x180008328  mov     rcx, [r14+8]
0x18000832c  mov     rax, [rcx]
0x18000832f  mov     rax, [rax+38h]
0x180008333  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008338  mov     rcx, rax; unsigned __int16 *
0x18000833b  lea     rdx, [rsp+0CE0h+var_C70]; unsigned __int16 *
0x180008340  call    ?GetCscBypassPath@@YAJPEBGPEAG_K@Z; GetCscBypassPath(ushort const *,ushort *,unsigned __int64)
0x180008345  test    eax, eax
0x180008347  jns     short loc_180008386
0x180008349  mov     rcx, [r14+8]
0x18000834d  mov     rax, [rcx]
0x180008350  mov     rax, [rax+38h]
0x180008354  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008359  mov     r8, rax; unsigned __int16 *
0x18000835c  mov     edx, 104h; unsigned __int64
0x180008361  lea     rcx, [rsp+0CE0h+var_C70]; unsigned __int16 *
0x180008366  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000836b  mov     rcx, [rbp+0BE8h]; this
0x180008372  test    eax, eax
0x180008374  jns     short loc_180008386
0x180008376  mov     r9d, eax; char *
0x180008379  mov     r8, r15; unsigned int
0x18000837c  mov     edx, 9D3h; void *
0x180008381  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180008386  mov     rcx, [r14+8]
0x18000838a  mov     rax, [rcx]
0x18000838d  lea     rdx, [rsp+0CE0h+var_C70]
0x180008392  mov     rax, [rax+60h]
0x180008396  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000839b  mov     ebx, eax
0x18000839d  test    eax, eax
0x18000839f  jns     short loc_1800083AE
0x1800083a1  mov     r8, r15
0x1800083a4  mov     edx, 9D7h
0x1800083a9  jmp     loc_1800082C4
0x1800083ae  mov     [rsp+0CE0h+var_C90], rdi
0x1800083b3  mov     [rsp+0CE0h+var_C88], dil
0x1800083b8  mov     rcx, [r14+8]
0x1800083bc  mov     rax, [rcx]
0x1800083bf  mov     rax, [rax]
0x1800083c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800083c7  mov     rdx, rax; void *
0x1800083ca  lea     rcx, [rsp+0CE0h+var_C90]; this
0x1800083cf  call    ?ImpersonateUser@CAutoImpersonate@@QEAAJPEAX@Z; CAutoImpersonate::ImpersonateUser(void *)
0x1800083d4  mov     ebx, eax
0x1800083d6  test    eax, eax
0x1800083d8  jns     short loc_1800083F6
0x1800083da  mov     rcx, [rbp+0BE8h]; this
0x1800083e1  mov     r9d, eax; char *
0x1800083e4  mov     r8, r15; unsigned int
0x1800083e7  mov     edx, 9DFh; void *
0x1800083ec  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800083f1  jmp     loc_1800087DA
0x1800083f6  mov     rcx, [r14+8]
0x1800083fa  mov     rax, [rcx]
0x1800083fd  mov     rax, [rax+8]
0x180008401  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008406  and     al, 0Ch
0x180008408  neg     al
0x18000840a  sbb     r12d, r12d
0x18000840d  and     r12d, 1CFE0h
0x180008414  add     r12d, 4020h
0x18000841b  mov     eax, r13d
0x18000841e  neg     eax
0x180008420  sbb     ecx, ecx
0x180008422  and     ecx, 100000h
0x180008428  add     ecx, 2C00h
0x18000842e  or      r12d, ecx
0x180008431  mov     rcx, [r14+8]
0x180008435  mov     rax, [rcx]
0x180008438  mov     rax, [rax+38h]
0x18000843c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008441  mov     rdx, rax; unsigned __int16 *
0x180008444  mov     r8d, r13d; int
0x180008447  call    ?_SetNtUserPolTime@CUserProfileRoamingProvider@@AEAAJPEBGH@Z; CUserProfileRoamingProvider::_SetNtUserPolTime(ushort const *,int)
0x18000844c  mov     rcx, [rbp+0BE8h]; this
0x180008453  test    eax, eax
0x180008455  jns     short loc_180008467
0x180008457  mov     r9d, eax; char *
0x18000845a  mov     r8, r15; unsigned int
0x18000845d  mov     edx, 9EDh; void *
0x180008462  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180008467  mov     [rsp+0CE0h+var_C98], rdi
0x18000846c  mov     rcx, [r14+8]
0x180008470  mov     rax, [rcx]
0x180008473  lea     rdx, [rsp+0CE0h+var_C98]
0x180008478  mov     rax, [rax+88h]
0x18000847f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008484  mov     rcx, [r14+8]
0x180008488  mov     rax, [rcx]
0x18000848b  mov     rax, [rax+0A8h]
0x180008492  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008497  mov     rsi, rax
0x18000849a  mov     rdx, [r14+8]
0x18000849e  mov     rcx, [rdx]
0x1800084a1  mov     rax, [rcx+68h]
0x1800084a5  mov     rcx, rdx
0x1800084a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800084ad  mov     rdi, rax
0x1800084b0  mov     rdx, [r14+8]
0x1800084b4  mov     rcx, [rdx]
0x1800084b7  mov     rax, [rcx+50h]
0x1800084bb  mov     rcx, rdx
0x1800084be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800084c3  mov     rbx, rax
0x1800084c6  mov     rdx, [r14+8]
0x1800084ca  mov     rcx, [rdx]
0x1800084cd  mov     rax, [rcx+48h]
0x1800084d1  mov     rcx, rdx
0x1800084d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800084d9  mov     [rsp+0CE0h+var_CB8], rsi
0x1800084de  mov     qword ptr [rsp+0CE0h+var_CC0], rdi
0x1800084e3  lea     r9, [rsp+0CE0h+var_C98]
0x1800084e8  mov     r8d, r12d
0x1800084eb  mov     rdx, rbx
0x1800084ee  mov     rcx, rax
0x1800084f1  call    cs:__imp_CopyProfileDirectoryEx2
0x1800084f7  test    eax, eax
0x1800084f9  jnz     loc_180008596
0x1800084ff  call    cs:__imp_GetLastError
0x180008505  mov     ebx, eax
0x180008507  cmp     eax, 1772h
0x18000850c  jnz     short loc_180008520
0x18000850e  test    cs:Microsoft_Windows_User_Profiles_ServiceEnableBits, 1
0x180008515  jz      short loc_180008545
0x180008517  lea     rdx, EVENT_PROFILEUPDATE_6002
0x18000851e  jmp     short loc_180008530
0x180008520  test    cs:Microsoft_Windows_User_Profiles_ServiceEnableBits, 1
0x180008527  jz      short loc_180008545
0x180008529  lea     rdx, EVENT_CENTRAL_UPDATE_FAILED
0x180008530  lea     rax, [rsp+0CE0h+var_C80]
0x180008535  mov     qword ptr [rsp+0CE0h+var_CC0], rax; unsigned int
0x18000853a  mov     r9d, 1
0x180008540  call    McGenEventWrite_EtwEventWriteTransfer
0x180008545  mov     rcx, [r14+8]
0x180008549  mov     rax, [rcx]
0x18000854c  mov     edx, 0C8h
0x180008551  mov     rax, [rax+0C0h]
0x180008558  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000855d  mov     rcx, [r14+8]
0x180008561  mov     rax, [rcx]
0x180008564  mov     rax, [rax+0D0h]
0x18000856b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008570  test    ebx, ebx
0x180008572  jz      loc_1800087D8
0x180008578  mov     rcx, [rbp+0BE8h]; this
0x18000857f  mov     r9d, ebx; char *
0x180008582  mov     r8, r15; unsigned int
0x180008585  mov     edx, 0A07h; void *
0x18000858a  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18000858f  mov     ebx, eax
0x180008591  jmp     loc_1800087DA
0x180008596  call    ?_IsSecureCachingDisabled@CUserProfileRoamingProvider@@AEAAHXZ; CUserProfileRoamingProvider::_IsSecureCachingDisabled(void)
0x18000859b  test    eax, eax
0x18000859d  jnz     loc_18000876A
0x1800085a3  mov     ebx, 20Ah
0x1800085a8  mov     r8d, ebx; Size
0x1800085ab  xor     edx, edx; Val
0x1800085ad  lea     rcx, [rsp+0CE0h+var_C70]; void *
0x1800085b2  call    memset_0
0x1800085b7  xor     edx, edx; Val
0x1800085b9  mov     r8d, 802h; Size
0x1800085bf  lea     rcx, [rbp+0BE0h+FileName]; void *
0x1800085c6  call    memset_0
0x1800085cb  mov     r8d, ebx; Size
0x1800085ce  xor     edx, edx; Val
0x1800085d0  lea     rcx, [rbp+0BE0h+var_A60]; void *
0x1800085d7  call    memset_0
0x1800085dc  mov     edi, 105h
0x1800085e1  mov     r9d, edi
0x1800085e4  lea     r8, [rbp+0BE0h+var_A60]
0x1800085eb  xor     edx, edx
0x1800085ed  lea     ecx, [rdx+4]
0x1800085f0  call    cs:__imp_GetBasicProfileFolderPath
0x1800085f6  test    eax, eax
0x1800085f8  js      loc_18000876A
0x1800085fe  mov     rcx, [r14+8]
0x180008602  mov     rax, [rcx]
0x180008605  mov     rax, [rax+20h]
0x180008609  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000860e  lea     rsi, ?c_szNTUserPol@@3QBGB; "ntuser.pol"
0x180008615  mov     [rsp+0CE0h+var_CA8], rsi
0x18000861a  lea     rcx, qword_180023CF8
0x180008621  mov     [rsp+0CE0h+var_CB0], rcx
0x180008626  mov     [rsp+0CE0h+var_CB8], rax
0x18000862b  lea     rax, aMicrosoftGroup; "\\Microsoft\\GroupPolicy\\Users\\"
0x180008632  mov     qword ptr [rsp+0CE0h+var_CC0], rax
0x180008637  lea     r9, [rbp+0BE0h+var_A60]
0x18000863e  lea     r8, aSSSSS; "%s%s%s%s%s"
0x180008645  mov     edx, 401h; unsigned __int64
0x18000864a  lea     rcx, [rbp+0BE0h+FileName]; unsigned __int16 *
0x180008651  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180008656  test    eax, eax
0x180008658  jns     short loc_180008664
0x18000865a  mov     edx, 0A19h
0x18000865f  jmp     loc_180008758
0x180008664  lea     rcx, [rbp+0BE0h+FileName]; lpFileName
0x18000866b  call    cs:__imp_GetFileAttributesW
0x180008671  or      ebx, 0FFFFFFFFh
0x180008674  cmp     eax, ebx
0x180008676  jz      short loc_1800086CB
0x180008678  cmp     eax, 10h
0x18000867b  jz      short loc_1800086CB
0x18000867d  mov     rcx, [r14+8]
0x180008681  mov     rax, [rcx]
0x180008684  mov     rax, [rax+20h]
0x180008688  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000868d  mov     rbx, rax
0x180008690  mov     rdx, [r14+8]
0x180008694  mov     rcx, [rdx]
0x180008697  mov     rax, [rcx+50h]
0x18000869b  mov     rcx, rdx
0x18000869e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800086a3  mov     [rsp+0CE0h+var_CC0], 1; int
0x1800086ab  mov     r9d, r12d; unsigned int
0x1800086ae  mov     r8, rbx; unsigned __int16 *
0x1800086b1  mov     rdx, rax; unsigned __int16 *
0x1800086b4  call    ?_ProcessNtuserPol@CUserProfileRoamingProvider@@AEAAJPEBG0KH@Z; CUserProfileRoamingProvider::_ProcessNtuserPol(ushort const *,ushort const *,ulong,int)
0x1800086b9  test    eax, eax
0x1800086bb  jns     loc_18000876A
0x1800086c1  mov     edx, 0A42h
0x1800086c6  jmp     loc_180008758
0x1800086cb  mov     rcx, [r14+8]
0x1800086cf  mov     rax, [rcx]
0x1800086d2  mov     rax, [rax+50h]
0x1800086d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800086db  mov     r9, rax
0x1800086de  mov     [rsp+0CE0h+var_CB8], rsi
0x1800086e3  lea     rax, qword_180023CF8
0x1800086ea  mov     qword ptr [rsp+0CE0h+var_CC0], rax; int
0x1800086ef  lea     r8, aSSS; "%s%s%s"
0x1800086f6  mov     rdx, rdi; unsigned __int64
0x1800086f9  lea     rcx, [rsp+0CE0h+var_C70]; unsigned __int16 *
0x1800086fe  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180008703  test    eax, eax
0x180008705  jns     short loc_18000870E
0x180008707  mov     edx, 0A29h
0x18000870c  jmp     short loc_180008758
0x18000870e  lea     rcx, [rsp+0CE0h+var_C70]; lpFileName
0x180008713  call    cs:__imp_GetFileAttributesW
0x180008719  cmp     eax, ebx
0x18000871b  jz      short loc_18000876A
0x18000871d  cmp     eax, 10h
0x180008720  jz      short loc_18000876A
0x180008722  mov     edx, 80h; dwFileAttributes
0x180008727  lea     rcx, [rsp+0CE0h+var_C70]; lpFileName
  ... truncated ...
```
