# SetFolderSecurity(ushort const *,void *)

- ea: `0x1800b3404`
- end: `0x1800b3976`
- name: `?SetFolderSecurity@@YAKPEBGPEAX@Z`
- size: `1394`
- prototype: `unsigned int __fastcall(const unsigned __int16 *, void *)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800b3404`
- `0x1800b3bd0`

## callees

- `0x18000a504`
- `0x180020520`
- `0x180075ec0`
- `0x18007d320`
- `0x18007de08`
- `0x1800b3404`
- `0x1800bf010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b35f4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b3832`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b35f4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b3832`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800b359f`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800b35d1`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800b359f`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800b35d1`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x1800b34ff`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x1800b34ff`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1800b3931`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1800b3931`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1800b38a6`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1800b38a6`
- `api-ms-win-security-base-l1-1-0!SetFileSecurityW` at `0x1800b35e6`
- `api-ms-win-security-base-l1-1-0!SetFileSecurityW` at `0x1800b3828`
- `api-ms-win-security-base-l1-1-0!SetFileSecurityW` at `0x1800b35e6`
- `api-ms-win-security-base-l1-1-0!SetFileSecurityW` at `0x1800b3828`

## string_xrefs

- `0x1800b3618`: `SetSubFolderSecurity: failed to SetFileSecurity for Folder %s with error: %d.`
- `0x1800b3641`: `SetSubFolderSecurity: failed to SetFileSecurity for Folder %s with error: %d.`
- `0x1800b368e`: `SetSubFolderSecurity: failed to do PathAppend for folder %s and subfolder %s with error: %d.`
- `0x1800b36c7`: `SetSubFolderSecurity: failed to do PathAppend for folder %s and subfolder %s with error: %d.`
- `0x1800b3704`: `SetSubFolderSecurity: failed to SetFolderSecurity for folder %s with error: %d.`
- `0x1800b372e`: `SetSubFolderSecurity: failed to SetFolderSecurity for folder %s with error: %d.`
- `0x1800b37d2`: `SetSingleFileSecurity: failed to do PathAppend on folder %s and file %s with error: %d.`
- `0x1800b380b`: `SetSingleFileSecurity: failed to do PathAppend on folder %s and file %s with error: %d.`
- `0x1800b3857`: `SetSingleFileSecurity: failed to SetFileSecurity for file %s with error: %d.`
- `0x1800b3881`: `SetSingleFileSecurity: failed to SetFileSecurity for file %s with error: %d.`
- `0x1800b34a6`: `SetFolderSecurity: failed to do PathAppend %s with error: %d.`
- `0x1800b34dc`: `SetFolderSecurity: failed to do PathAppend %s with error: %d.`
- `0x1800b352f`: `SetFolderSecurity: failed to FindFirstFile for path: %s with error: %d.`
- `0x1800b355a`: `SetFolderSecurity: failed to FindFirstFile for path: %s with error: %d.`
- `0x1800b3777`: `SetFolderSecurity: failed to SetSubFolderSecurity for folder %s and subfolder %s with error: %d.`
- `0x1800b38d0`: `SetFolderSecurity: failed to SetSubFolderSecurity for folder %s and subfolder %s with error: %d.`
- `0x1800b38f6`: `SetFolderSecurity: failed to SetSingleFileSecurity for file %s under %s with error: %d.`
- `0x1800b391c`: `SetFolderSecurity: failed to SetSingleFileSecurity for file %s under %s with error: %d.`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall SetFolderSecurity(unsigned __int16 *a1, void *a2)
{
  DWORD LastError; // edi
  void (*v5)(unsigned int, const unsigned __int16 *, ...); // rax
  LPCWSTR v6; // r8
  const wchar_t *v7; // rdx
  HANDLE FirstFileW; // r12
  void (*v9)(unsigned int, const unsigned __int16 *, ...); // rax
  LPCWSTR v10; // r8
  const wchar_t *v11; // rdx
  void (*v12)(unsigned int, const unsigned __int16 *, ...); // rax
  WCHAR *cFileName; // r9
  WCHAR *v14; // r8
  const wchar_t *v15; // rdx
  WCHAR *v16; // r9
  WCHAR *v17; // r8
  const unsigned __int16 *v18; // rdx
  PCNZWCH lpString2; // [rsp+20h] [rbp-E0h]
  LPCWSTR v21; // [rsp+30h] [rbp-D0h] BYREF
  LPCWSTR lpFileName; // [rsp+38h] [rbp-C8h] BYREF
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+40h] [rbp-C0h] BYREF

  lpFileName = 0;
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  if ( !a1 || !a2 )
  {
    LastError = 87;
    goto LABEL_77;
  }
  LastError = PathAppend(a1, &DomainName, L"\\*", (unsigned __int16 **)&lpFileName);
  if ( LastError )
  {
    if ( !*(_DWORD *)&g_dwDebugLevel )
      goto LABEL_77;
    v5 = g_lpDebugMsg;
    if ( !g_lpDebugMsg )
    {
      if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        RedirectDebugMsg(2u, L"SetFolderSecurity: failed to do PathAppend %s with error: %d.", a1, LastError);
      goto LABEL_77;
    }
    v6 = a1;
    v7 = L"SetFolderSecurity: failed to do PathAppend %s with error: %d.";
    goto LABEL_7;
  }
  FirstFileW = FindFirstFileW(lpFileName, &FindFileData);
  if ( FirstFileW == (HANDLE)-1LL )
  {
    LastError = 6;
    if ( !*(_DWORD *)&g_dwDebugLevel )
      goto LABEL_77;
    v5 = g_lpDebugMsg;
    if ( !g_lpDebugMsg )
    {
      if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        RedirectDebugMsg(2u, L"SetFolderSecurity: failed to FindFirstFile for path: %s with error: %d.", lpFileName, 6);
      goto LABEL_77;
    }
    v6 = lpFileName;
    v7 = L"SetFolderSecurity: failed to FindFirstFile for path: %s with error: %d.";
LABEL_7:
    v5(2u, v7, v6, LastError);
    goto LABEL_77;
  }
  while ( 1 )
  {
    v21 = 0;
    if ( (FindFileData.dwFileAttributes & 0x10) == 0 )
      break;
    LastError = 0;
    if ( CompareStringW(0x7Fu, 1u, FindFileData.cFileName, -1, L"..", -1) == 2 )
      goto LABEL_43;
    if ( CompareStringW(0x7Fu, 1u, FindFileData.cFileName, -1, L".", -1) == 2 )
    {
      if ( !SetFileSecurityW(a1, 4u, a2) )
      {
        LastError = GetLastError();
        if ( *(_DWORD *)&g_dwDebugLevel )
        {
          v9 = g_lpDebugMsg;
          if ( g_lpDebugMsg )
          {
            v10 = a1;
            v11 = L"SetSubFolderSecurity: failed to SetFileSecurity for Folder %s with error: %d.";
LABEL_39:
            v9(2u, v11, v10, LastError);
            goto LABEL_43;
          }
          if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
            RedirectDebugMsg(
              2u,
              L"SetSubFolderSecurity: failed to SetFileSecurity for Folder %s with error: %d.",
              a1,
              LastError);
        }
      }
    }
    else
    {
      LastError = PathAppend(a1, L"\\", FindFileData.cFileName, (unsigned __int16 **)&v21);
      if ( LastError )
      {
        if ( *(_DWORD *)&g_dwDebugLevel )
        {
          if ( g_lpDebugMsg )
          {
            LODWORD(lpString2) = LastError;
            g_lpDebugMsg(
              2u,
              L"SetSubFolderSecurity: failed to do PathAppend for folder %s and subfolder %s with error: %d.",
              a1,
              FindFileData.cFileName,
              lpString2);
          }
          else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
          {
            LODWORD(lpString2) = LastError;
            RedirectDebugMsg(
              2u,
              L"SetSubFolderSecurity: failed to do PathAppend for folder %s and subfolder %s with error: %d.",
              a1,
              FindFileData.cFileName,
              lpString2);
          }
        }
      }
      else
      {
        LastError = SetFolderSecurity(v21, a2);
        if ( LastError && *(_DWORD *)&g_dwDebugLevel )
        {
          v9 = g_lpDebugMsg;
          if ( g_lpDebugMsg )
          {
            v10 = v21;
            v11 = L"SetSubFolderSecurity: failed to SetFolderSecurity for folder %s with error: %d.";
            goto LABEL_39;
          }
          if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
            RedirectDebugMsg(
              2u,
              L"SetSubFolderSecurity: failed to SetFolderSecurity for folder %s with error: %d.",
              v21,
              LastError);
        }
      }
    }
LABEL_43:
    XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>((void **)&v21);
    if ( LastError )
    {
      if ( !*(_DWORD *)&g_dwDebugLevel )
        goto LABEL_75;
      v12 = g_lpDebugMsg;
      if ( g_lpDebugMsg )
      {
        cFileName = FindFileData.cFileName;
        v14 = a1;
        v15 = L"SetFolderSecurity: failed to SetSubFolderSecurity for folder %s and subfolder %s with error: %d.";
LABEL_47:
        v12(2u, v15, v14, cFileName, LastError);
        goto LABEL_75;
      }
      if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        v16 = FindFileData.cFileName;
        v17 = a1;
        v18 = L"SetFolderSecurity: failed to SetSubFolderSecurity for folder %s and subfolder %s with error: %d.";
LABEL_74:
        LODWORD(lpString2) = LastError;
        RedirectDebugMsg(2u, v18, v17, v16, lpString2);
        goto LABEL_75;
      }
      goto LABEL_75;
    }
LABEL_63:
    if ( !FindNextFileW(FirstFileW, &FindFileData) )
      goto LABEL_75;
  }
  LastError = PathAppend(a1, L"\\", FindFileData.cFileName, (unsigned __int16 **)&v21);
  if ( LastError )
  {
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      if ( g_lpDebugMsg )
      {
        LODWORD(lpString2) = LastError;
        g_lpDebugMsg(
          2u,
          L"SetSingleFileSecurity: failed to do PathAppend on folder %s and file %s with error: %d.",
          a1,
          FindFileData.cFileName,
          lpString2);
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        LODWORD(lpString2) = LastError;
        RedirectDebugMsg(
          2u,
          L"SetSingleFileSecurity: failed to do PathAppend on folder %s and file %s with error: %d.",
          a1,
          FindFileData.cFileName,
          lpString2);
      }
    }
  }
  else if ( !SetFileSecurityW(v21, 4u, a2) )
  {
    LastError = GetLastError();
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      if ( g_lpDebugMsg )
      {
        g_lpDebugMsg(
          2u,
          L"SetSingleFileSecurity: failed to SetFileSecurity for file %s with error: %d.",
          v21,
          LastError);
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        RedirectDebugMsg(
          2u,
          L"SetSingleFileSecurity: failed to SetFileSecurity for file %s with error: %d.",
          v21,
          LastError);
      }
    }
  }
  XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>((void **)&v21);
  if ( !LastError )
    goto LABEL_63;
  if ( *(_DWORD *)&g_dwDebugLevel )
  {
    v12 = g_lpDebugMsg;
    if ( g_lpDebugMsg )
    {
      cFileName = a1;
      v14 = FindFileData.cFileName;
      v15 = L"SetFolderSecurity: failed to SetSingleFileSecurity for file %s under %s with error: %d.";
      goto LABEL_47;
    }
    if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
    {
      v16 = a1;
      v17 = FindFileData.cFileName;
      v18 = L"SetFolderSecurity: failed to SetSingleFileSecurity for file %s under %s with error: %d.";
      goto LABEL_74;
    }
  }
LABEL_75:
  FindClose(FirstFileW);
LABEL_77:
  XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>((void **)&lpFileName);
  return LastError;
}

```

## disassembly

```asm
0x1800b3404  mov     [rsp-8+arg_10], rsi
0x1800b3409  mov     [rsp-8+arg_18], rdi
0x1800b340e  push    rbp
0x1800b340f  push    r12
0x1800b3411  push    r13
0x1800b3413  push    r14
0x1800b3415  push    r15
0x1800b3417  lea     rbp, [rsp-1A0h]
0x1800b341f  sub     rsp, 2A0h
0x1800b3426  mov     rax, cs:__security_cookie
0x1800b342d  xor     rax, rsp
0x1800b3430  mov     [rbp+1C0h+var_30], rax
0x1800b3437  mov     r15, rdx
0x1800b343a  mov     r14, rcx
0x1800b343d  xor     r13d, r13d
0x1800b3440  mov     [rsp+2C0h+lpFileName], r13
0x1800b3445  xor     edx, edx; Val
0x1800b3447  mov     r8d, 250h; Size
0x1800b344d  lea     rcx, [rsp+2C0h+FindFileData]; void *
0x1800b3452  call    memset_0
0x1800b3457  test    r14, r14
0x1800b345a  jz      loc_1800B3939
0x1800b3460  test    r15, r15
0x1800b3463  jz      loc_1800B3939
0x1800b3469  lea     r9, [rsp+2C0h+lpFileName]; unsigned __int16 **
0x1800b346e  lea     r8, asc_1800C3AB8; "\\*"
0x1800b3475  lea     rdx, DomainName; unsigned __int16 *
0x1800b347c  mov     rcx, r14; unsigned __int16 *
0x1800b347f  call    ?PathAppend@@YAKPEBG00PEAPEAG@Z; PathAppend(ushort const *,ushort const *,ushort const *,ushort * *)
0x1800b3484  mov     edi, eax
0x1800b3486  test    eax, eax
0x1800b3488  jz      short loc_1800B34F5
0x1800b348a  cmp     cs:?g_dwDebugLevel@@3KA, r13d; ulong g_dwDebugLevel
0x1800b3491  jz      loc_1800B393E
0x1800b3497  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x1800b349e  test    rax, rax
0x1800b34a1  jz      short loc_1800B34BF
0x1800b34a3  mov     r8, r14
0x1800b34a6  lea     rdx, aSetfoldersecur_0; "SetFolderSecurity: failed to do PathApp"...
0x1800b34ad  mov     r9d, edi
0x1800b34b0  mov     ecx, 2
0x1800b34b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b34ba  jmp     loc_1800B393E
0x1800b34bf  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r13; void * g_lpDebugMsgContextInstance
0x1800b34c6  jz      loc_1800B393E
0x1800b34cc  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r13; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x1800b34d3  jz      loc_1800B393E
0x1800b34d9  mov     r8, r14
0x1800b34dc  lea     rdx, aSetfoldersecur_0; "SetFolderSecurity: failed to do PathApp"...
0x1800b34e3  mov     r9d, edi
0x1800b34e6  mov     ecx, 2; unsigned int
0x1800b34eb  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x1800b34f0  jmp     loc_1800B393E
0x1800b34f5  lea     rdx, [rsp+2C0h+FindFileData]; lpFindFileData
0x1800b34fa  mov     rcx, [rsp+2C0h+lpFileName]; lpFileName
0x1800b34ff  call    cs:__imp_FindFirstFileW
0x1800b3505  mov     r12, rax
0x1800b3508  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800b350c  jnz     short loc_1800B3563
0x1800b350e  lea     edi, [rax+7]
0x1800b3511  cmp     cs:?g_dwDebugLevel@@3KA, r13d; ulong g_dwDebugLevel
0x1800b3518  jz      loc_1800B393E
0x1800b351e  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x1800b3525  test    rax, rax
0x1800b3528  jz      short loc_1800B353B
0x1800b352a  mov     r8, [rsp+2C0h+lpFileName]
0x1800b352f  lea     rdx, aSetfoldersecur_2; "SetFolderSecurity: failed to FindFirstF"...
0x1800b3536  jmp     loc_1800B34AD
0x1800b353b  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r13; void * g_lpDebugMsgContextInstance
0x1800b3542  jz      loc_1800B393E
0x1800b3548  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r13; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x1800b354f  jz      loc_1800B393E
0x1800b3555  mov     r8, [rsp+2C0h+lpFileName]
0x1800b355a  lea     rdx, aSetfoldersecur_2; "SetFolderSecurity: failed to FindFirstF"...
0x1800b3561  jmp     short loc_1800B34E3
0x1800b3563  mov     esi, 2
0x1800b3568  mov     [rsp+2C0h+var_290], r13
0x1800b356d  test    byte ptr [rsp+2C0h+FindFileData.dwFileAttributes], 10h
0x1800b3572  jz      loc_1800B378E
0x1800b3578  mov     edi, r13d
0x1800b357b  mov     [rsp+2C0h+cchCount2], 0FFFFFFFFh; cchCount2
0x1800b3583  lea     rax, asc_1800C3A84; ".."
0x1800b358a  mov     [rsp+2C0h+lpString2], rax; lpString2
0x1800b358f  or      r9d, 0FFFFFFFFh; cchCount1
0x1800b3593  lea     r8, [rsp+2C0h+FindFileData.cFileName]; lpString1
0x1800b3598  lea     edx, [r9+2]; dwCmpFlags
0x1800b359c  lea     ecx, [rdx+7Eh]; Locale
0x1800b359f  call    cs:__imp_CompareStringW
0x1800b35a5  cmp     eax, esi
0x1800b35a7  jz      loc_1800B3740
0x1800b35ad  mov     [rsp+2C0h+cchCount2], 0FFFFFFFFh; cchCount2
0x1800b35b5  lea     rax, asc_1800C3A80; "."
0x1800b35bc  mov     [rsp+2C0h+lpString2], rax; lpString2
0x1800b35c1  or      r9d, 0FFFFFFFFh; cchCount1
0x1800b35c5  lea     r8, [rsp+2C0h+FindFileData.cFileName]; lpString1
0x1800b35ca  lea     edx, [r9+2]; dwCmpFlags
0x1800b35ce  lea     ecx, [rdx+7Eh]; Locale
0x1800b35d1  call    cs:__imp_CompareStringW
0x1800b35d7  mov     rcx, r14; unsigned __int16 *
0x1800b35da  cmp     eax, esi
0x1800b35dc  jnz     short loc_1800B364D
0x1800b35de  mov     r8, r15; pSecurityDescriptor
0x1800b35e1  mov     edx, 4; SecurityInformation
0x1800b35e6  call    cs:__imp_SetFileSecurityW
0x1800b35ec  test    eax, eax
0x1800b35ee  jnz     loc_1800B3740
0x1800b35f4  call    cs:__imp_GetLastError
0x1800b35fa  mov     edi, eax
0x1800b35fc  cmp     cs:?g_dwDebugLevel@@3KA, r13d; ulong g_dwDebugLevel
0x1800b3603  jz      loc_1800B3740
0x1800b3609  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x1800b3610  test    rax, rax
0x1800b3613  jz      short loc_1800B3624
0x1800b3615  mov     r8, r14
0x1800b3618  lea     rdx, aSetsubfolderse; "SetSubFolderSecurity: failed to SetFile"...
0x1800b361f  jmp     loc_1800B370B
0x1800b3624  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r13; void * g_lpDebugMsgContextInstance
0x1800b362b  jz      loc_1800B3740
0x1800b3631  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r13; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x1800b3638  jz      loc_1800B3740
0x1800b363e  mov     r8, r14
0x1800b3641  lea     rdx, aSetsubfolderse; "SetSubFolderSecurity: failed to SetFile"...
0x1800b3648  jmp     loc_1800B3735
0x1800b364d  lea     r9, [rsp+2C0h+var_290]; unsigned __int16 **
0x1800b3652  lea     r8, [rsp+2C0h+FindFileData.cFileName]; unsigned __int16 *
0x1800b3657  lea     rdx, asc_1800C3A8C; "\\"
0x1800b365e  call    ?PathAppend@@YAKPEBG00PEAPEAG@Z; PathAppend(ushort const *,ushort const *,ushort const *,ushort * *)
0x1800b3663  mov     edi, eax
0x1800b3665  test    eax, eax
0x1800b3667  jz      short loc_1800B36D7
0x1800b3669  cmp     cs:?g_dwDebugLevel@@3KA, r13d; ulong g_dwDebugLevel
0x1800b3670  jz      loc_1800B3740
0x1800b3676  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x1800b367d  test    rax, rax
0x1800b3680  jz      short loc_1800B36A1
0x1800b3682  mov     dword ptr [rsp+2C0h+lpString2], edi
0x1800b3686  lea     r9, [rsp+2C0h+FindFileData.cFileName]
0x1800b368b  mov     r8, r14
0x1800b368e  lea     rdx, aSetsubfolderse_1; "SetSubFolderSecurity: failed to do Path"...
0x1800b3695  mov     ecx, esi
0x1800b3697  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b369c  jmp     loc_1800B3740
0x1800b36a1  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r13; void * g_lpDebugMsgContextInstance
0x1800b36a8  jz      loc_1800B3740
0x1800b36ae  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r13; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x1800b36b5  jz      loc_1800B3740
0x1800b36bb  mov     dword ptr [rsp+2C0h+lpString2], edi
0x1800b36bf  lea     r9, [rsp+2C0h+FindFileData.cFileName]
0x1800b36c4  mov     r8, r14
0x1800b36c7  lea     rdx, aSetsubfolderse_1; "SetSubFolderSecurity: failed to do Path"...
0x1800b36ce  mov     ecx, esi; unsigned int
0x1800b36d0  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x1800b36d5  jmp     short loc_1800B3740
0x1800b36d7  mov     rdx, r15; void *
0x1800b36da  mov     rcx, [rsp+2C0h+var_290]; unsigned __int16 *
0x1800b36df  call    ?SetFolderSecurity@@YAKPEBGPEAX@Z; SetFolderSecurity(ushort const *,void *)
0x1800b36e4  mov     edi, eax
0x1800b36e6  test    eax, eax
0x1800b36e8  jz      short loc_1800B3740
0x1800b36ea  cmp     cs:?g_dwDebugLevel@@3KA, r13d; ulong g_dwDebugLevel
0x1800b36f1  jz      short loc_1800B3740
0x1800b36f3  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x1800b36fa  test    rax, rax
0x1800b36fd  jz      short loc_1800B3717
0x1800b36ff  mov     r8, [rsp+2C0h+var_290]
0x1800b3704  lea     rdx, aSetsubfolderse_0; "SetSubFolderSecurity: failed to SetFold"...
0x1800b370b  mov     r9d, edi
0x1800b370e  mov     ecx, esi
0x1800b3710  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b3715  jmp     short loc_1800B3740
0x1800b3717  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r13; void * g_lpDebugMsgContextInstance
0x1800b371e  jz      short loc_1800B3740
0x1800b3720  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r13; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x1800b3727  jz      short loc_1800B3740
0x1800b3729  mov     r8, [rsp+2C0h+var_290]
0x1800b372e  lea     rdx, aSetsubfolderse_0; "SetSubFolderSecurity: failed to SetFold"...
0x1800b3735  mov     r9d, edi
0x1800b3738  mov     ecx, esi; unsigned int
0x1800b373a  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x1800b373f  nop
0x1800b3740  lea     rcx, [rsp+2C0h+var_290]
0x1800b3745  call    ??1?$XPtrLF@U_NOTIFYCONTEXT@@@@QEAA@XZ; XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>(void)
0x1800b374a  test    edi, edi
0x1800b374c  jz      loc_1800B389E
0x1800b3752  cmp     cs:?g_dwDebugLevel@@3KA, r13d; ulong g_dwDebugLevel
0x1800b3759  jz      loc_1800B392E
0x1800b375f  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x1800b3766  test    rax, rax
0x1800b3769  jz      loc_1800B38B6
0x1800b376f  lea     r9, [rsp+2C0h+FindFileData.cFileName]
0x1800b3774  mov     r8, r14
0x1800b3777  lea     rdx, aSetfoldersecur; "SetFolderSecurity: failed to SetSubFold"...
0x1800b377e  mov     dword ptr [rsp+2C0h+lpString2], edi
0x1800b3782  mov     ecx, esi
0x1800b3784  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b3789  jmp     loc_1800B392E
0x1800b378e  lea     r9, [rsp+2C0h+var_290]; unsigned __int16 **
0x1800b3793  lea     r8, [rsp+2C0h+FindFileData.cFileName]; unsigned __int16 *
0x1800b3798  lea     rdx, asc_1800C3A8C; "\\"
0x1800b379f  mov     rcx, r14; unsigned __int16 *
0x1800b37a2  call    ?PathAppend@@YAKPEBG00PEAPEAG@Z; PathAppend(ushort const *,ushort const *,ushort const *,ushort * *)
0x1800b37a7  mov     edi, eax
0x1800b37a9  test    eax, eax
0x1800b37ab  jz      short loc_1800B381B
0x1800b37ad  cmp     cs:?g_dwDebugLevel@@3KA, r13d; ulong g_dwDebugLevel
0x1800b37b4  jz      loc_1800B3890
0x1800b37ba  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x1800b37c1  test    rax, rax
0x1800b37c4  jz      short loc_1800B37E5
0x1800b37c6  mov     dword ptr [rsp+2C0h+lpString2], edi
0x1800b37ca  lea     r9, [rsp+2C0h+FindFileData.cFileName]
0x1800b37cf  mov     r8, r14
0x1800b37d2  lea     rdx, aSetsinglefiles; "SetSingleFileSecurity: failed to do Pat"...
0x1800b37d9  mov     ecx, esi
0x1800b37db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b37e0  jmp     loc_1800B3890
0x1800b37e5  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r13; void * g_lpDebugMsgContextInstance
0x1800b37ec  jz      loc_1800B3890
0x1800b37f2  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r13; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x1800b37f9  jz      loc_1800B3890
0x1800b37ff  mov     dword ptr [rsp+2C0h+lpString2], edi
0x1800b3803  lea     r9, [rsp+2C0h+FindFileData.cFileName]
0x1800b3808  mov     r8, r14
0x1800b380b  lea     rdx, aSetsinglefiles; "SetSingleFileSecurity: failed to do Pat"...
0x1800b3812  mov     ecx, esi; unsigned int
0x1800b3814  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x1800b3819  jmp     short loc_1800B3890
0x1800b381b  mov     r8, r15; pSecurityDescriptor
0x1800b381e  mov     edx, 4; SecurityInformation
0x1800b3823  mov     rcx, [rsp+2C0h+var_290]; lpFileName
0x1800b3828  call    cs:__imp_SetFileSecurityW
0x1800b382e  test    eax, eax
0x1800b3830  jnz     short loc_1800B3890
0x1800b3832  call    cs:__imp_GetLastError
0x1800b3838  mov     edi, eax
0x1800b383a  cmp     cs:?g_dwDebugLevel@@3KA, r13d; ulong g_dwDebugLevel
0x1800b3841  jz      short loc_1800B3890
0x1800b3843  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x1800b384a  test    rax, rax
0x1800b384d  jz      short loc_1800B3867
0x1800b384f  mov     r9d, edi
0x1800b3852  mov     r8, [rsp+2C0h+var_290]
0x1800b3857  lea     rdx, aSetsinglefiles_0; "SetSingleFileSecurity: failed to SetFil"...
0x1800b385e  mov     ecx, esi
0x1800b3860  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b3865  jmp     short loc_1800B3890
0x1800b3867  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r13; void * g_lpDebugMsgContextInstance
0x1800b386e  jz      short loc_1800B3890
0x1800b3870  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r13; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x1800b3877  jz      short loc_1800B3890
0x1800b3879  mov     r9d, edi
0x1800b387c  mov     r8, [rsp+2C0h+var_290]
0x1800b3881  lea     rdx, aSetsinglefiles_0; "SetSingleFileSecurity: failed to SetFil"...
0x1800b3888  mov     ecx, esi; unsigned int
0x1800b388a  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x1800b388f  nop
0x1800b3890  lea     rcx, [rsp+2C0h+var_290]
0x1800b3895  call    ??1?$XPtrLF@U_NOTIFYCONTEXT@@@@QEAA@XZ; XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>(void)
0x1800b389a  test    edi, edi
0x1800b389c  jnz     short loc_1800B38D9
0x1800b389e  lea     rdx, [rsp+2C0h+FindFileData]; lpFindFileData
0x1800b38a3  mov     rcx, r12; hFindFile
0x1800b38a6  call    cs:__imp_FindNextFileW
0x1800b38ac  test    eax, eax
0x1800b38ae  jnz     loc_1800B3568
0x1800b38b4  jmp     short loc_1800B392E
0x1800b38b6  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r13; void * g_lpDebugMsgContextInstance
0x1800b38bd  jz      short loc_1800B392E
0x1800b38bf  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r13; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x1800b38c6  jz      short loc_1800B392E
0x1800b38c8  lea     r9, [rsp+2C0h+FindFileData.cFileName]
0x1800b38cd  mov     r8, r14
0x1800b38d0  lea     rdx, aSetfoldersecur; "SetFolderSecurity: failed to SetSubFold"...
0x1800b38d7  jmp     short loc_1800B3923
0x1800b38d9  cmp     cs:?g_dwDebugLevel@@3KA, r13d; ulong g_dwDebugLevel
0x1800b38e0  jz      short loc_1800B392E
0x1800b38e2  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x1800b38e9  test    rax, rax
0x1800b38ec  jz      short loc_1800B3902
0x1800b38ee  mov     r9, r14
0x1800b38f1  lea     r8, [rsp+2C0h+FindFileData.cFileName]
0x1800b38f6  lea     rdx, aSetfoldersecur_1; "SetFolderSecurity: failed to SetSingleF"...
0x1800b38fd  jmp     loc_1800B377E
0x1800b3902  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r13; void * g_lpDebugMsgContextInstance
0x1800b3909  jz      short loc_1800B392E
0x1800b390b  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r13; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x1800b3912  jz      short loc_1800B392E
0x1800b3914  mov     r9, r14
0x1800b3917  lea     r8, [rsp+2C0h+FindFileData.cFileName]
0x1800b391c  lea     rdx, aSetfoldersecur_1; "SetFolderSecurity: failed to SetSingleF"...
0x1800b3923  mov     dword ptr [rsp+2C0h+lpString2], edi
0x1800b3927  mov     ecx, esi; unsigned int
0x1800b3929  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x1800b392e  mov     rcx, r12; hFindFile
0x1800b3931  call    cs:__imp_FindClose
0x1800b3937  jmp     short loc_1800B393E
0x1800b3939  mov     edi, 57h ; 'W'
0x1800b393e  lea     rcx, [rsp+2C0h+lpFileName]
0x1800b3943  call    ??1?$XPtrLF@U_NOTIFYCONTEXT@@@@QEAA@XZ; XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>(void)
0x1800b3948  mov     eax, edi
  ... truncated ...
```
