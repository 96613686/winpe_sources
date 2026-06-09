# _CatDBDeleteJetFiles(int)

- ea: `0x18001d62c`
- end: `0x18001da58`
- name: `?_CatDBDeleteJetFiles@@YAHH@Z`
- size: `1068`
- prototype: `__int64 __fastcall(int)`
- caller_count: `5`
- callee_count: `9`
- tags: `file_ops, registry_config`

## callers

- `0x180002b90`
- `0x18001344c`
- `0x180018620`
- `0x18001ad58`
- `0x18001cca0`

## callees

- `0x1800015b0`
- `0x180003d48`
- `0x180004a20`
- `0x18000a59c`
- `0x18000be40`
- `0x18000c7e8`
- `0x18001cf38`
- `0x18001d4dc`
- `0x18001d62c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d7f7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d8eb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d8f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d951`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d7f7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d8eb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d8f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d951`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x18001d904`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x18001d904`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18001d7e8`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18001d7e8`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18001d943`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18001d943`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18001d76c`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18001d76c`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18001da21`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18001da21`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesExW` at `0x18001d8e1`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesExW` at `0x18001d8e1`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall _CatDBDeleteJetFiles(int a1)
{
  WCHAR *v2; // r12
  unsigned __int16 *v3; // rdi
  __int64 FirstFileW; // r15
  unsigned int v5; // r13d
  const unsigned __int16 *v6; // rax
  unsigned int v7; // edx
  unsigned __int16 *v8; // rcx
  unsigned __int16 *v9; // rsi
  WCHAR *v10; // rbx
  unsigned int v11; // r8d
  const WCHAR *v12; // rax
  unsigned int v13; // edx
  unsigned __int16 *v14; // rcx
  unsigned int v15; // edx
  unsigned __int16 *v16; // rcx
  const WCHAR *v17; // rax
  unsigned int v18; // edx
  unsigned __int16 *v19; // rcx
  unsigned int v20; // edx
  unsigned __int16 *v21; // rcx
  const WCHAR *v22; // rax
  unsigned int v23; // edx
  unsigned __int16 *v24; // rcx
  const WCHAR *v25; // rax
  unsigned int v26; // edx
  unsigned __int16 *v27; // rcx
  const WCHAR *v28; // rax
  DWORD LastError; // eax
  const unsigned __int16 *v30; // r14
  const unsigned __int16 *v31; // rax
  unsigned int v32; // edx
  unsigned __int16 *v33; // rcx
  const WCHAR *v34; // rax
  unsigned int v35; // edx
  unsigned __int16 *v36; // rcx
  const WCHAR *v37; // rax
  unsigned int v38; // edx
  unsigned __int16 *v39; // rcx
  unsigned int v40; // edx
  unsigned __int16 *v41; // rcx
  unsigned int v42; // edx
  unsigned __int16 *v43; // rcx
  int v45; // [rsp+28h] [rbp-D8h]
  const WCHAR *v46; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD v47[2]; // [rsp+38h] [rbp-C8h] BYREF
  _OWORD FileInformation[2]; // [rsp+48h] [rbp-B8h] BYREF
  int v49; // [rsp+68h] [rbp-98h]
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+70h] [rbp-90h] BYREF

  v47[1] = -2;
  v47[0] = 0;
  v2 = 0;
  v3 = 0;
  FirstFileW = -1;
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  v5 = 1;
  v6 = _CatDBGetCatrootDirW(1);
  v9 = (unsigned __int16 *)v6;
  if ( !v6 )
  {
    v10 = 0;
    v11 = 836;
LABEL_45:
    ErrLog_LogError(v8, v7, v11, 0, 0, v45);
LABEL_46:
    v5 = 0;
    if ( !v9 )
      goto LABEL_48;
    goto LABEL_47;
  }
  v12 = _CATDBConstructWSTRPath(v6, L"edb*.log");
  v10 = (WCHAR *)v12;
  if ( !v12 )
  {
    ErrLog_LogError(v14, v13, 0x350u, 0, 0, v45);
    goto LABEL_46;
  }
  if ( !(unsigned int)_CatDBDeleteFiles(v9, v12) )
  {
    ErrLog_LogError(v16, v15, 0x356u, 0, 0, v45);
    goto LABEL_46;
  }
  _CatDBFree(v10);
  v17 = _CATDBConstructWSTRPath(v9, L"res*.log");
  v10 = (WCHAR *)v17;
  if ( !v17 )
  {
    ErrLog_LogError(v19, v18, 0x361u, 0, 0, v45);
    goto LABEL_46;
  }
  if ( !(unsigned int)_CatDBDeleteFiles(v9, v17) )
  {
    ErrLog_LogError(v21, v20, 0x367u, 0, 0, v45);
    goto LABEL_46;
  }
  _CatDBFree(v10);
  v22 = _CATDBConstructWSTRPath(v9, L"edb.chk");
  v10 = (WCHAR *)v22;
  if ( !v22 )
  {
    ErrLog_LogError(v24, v23, 0x376u, 0, 0, v45);
    goto LABEL_46;
  }
  DeleteFileW(v22);
  _CatDBFree(v10);
  v25 = _CATDBConstructWSTRPath(v9, L"edb*.jrs");
  v10 = (WCHAR *)v25;
  if ( !v25 )
  {
    ErrLog_LogError(v27, v26, 0x387u, 0, 0, v45);
    goto LABEL_46;
  }
  _CatDBDeleteFiles(v9, v25);
  _CatDBFree(v10);
  v10 = 0;
  if ( !a1 )
  {
    v28 = _CATDBConstructWSTRPath(v9, L"{????????????????????????????????????}");
    v2 = (WCHAR *)v28;
    if ( !v28 )
    {
      v11 = 928;
      goto LABEL_45;
    }
    FirstFileW = (__int64)FindFirstFileW(v28, &FindFileData);
    if ( FirstFileW == -1 )
    {
      LastError = GetLastError();
      v8 = (unsigned __int16 *)(LastError - 2);
      if ( ((unsigned int)v8 & 0xFFFFFFEE) != 0 || LastError == 19 )
      {
        v11 = 953;
        goto LABEL_45;
      }
    }
    else
    {
      v30 = _CatDBGetCatrootDirW(0);
      v47[0] = v30;
      if ( !v30 )
      {
        v11 = 964;
        goto LABEL_45;
      }
      do
      {
        if ( (FindFileData.dwFileAttributes & 0x10) != 0
          && (FindFileData.cFileName[0] != 46
           || FindFileData.cFileName[1] && (FindFileData.cFileName[1] != 46 || FindFileData.cFileName[2])) )
        {
          v31 = _CATDBConstructWSTRPath(v9, FindFileData.cFileName);
          v3 = (unsigned __int16 *)v31;
          if ( !v31 )
          {
            ErrLog_LogError(v33, v32, 0x3D5u, 0, 0, v45);
            v10 = 0;
            goto LABEL_46;
          }
          v34 = _CATDBConstructWSTRPath(v31, L"catdb*");
          v10 = (WCHAR *)v34;
          if ( !v34 )
          {
            ErrLog_LogError(v36, v35, 0x3E0u, 0, 0, v45);
            goto LABEL_46;
          }
          _CatDBDeleteFiles(v3, v34);
          memset(FileInformation, 0, sizeof(FileInformation));
          v49 = 0;
          v37 = _CATDBConstructWSTRPath(v30, FindFileData.cFileName);
          v46 = v37;
          if ( !v37 )
          {
            ErrLog_LogError(v39, v38, 0x3F1u, 0, 0, v45);
            wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (void *),&void _CatDBFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (void *),&void _CatDBFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v46);
            goto LABEL_46;
          }
          if ( !GetFileAttributesExW(v37, GetFileExInfoStandard, FileInformation)
            && (GetLastError() == 2 || GetLastError() == 3)
            && !RemoveDirectoryW(v3) )
          {
            ErrLog_LogError(v41, v40, 0x3FDu, 0, 0, v45);
          }
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (void *),&void _CatDBFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (void *),&void _CatDBFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v46);
          _CatDBFree(v10);
          _CatDBFree(v3);
        }
      }
      while ( FindNextFileW((HANDLE)FirstFileW, &FindFileData) );
      if ( GetLastError() != 18 )
      {
        ErrLog_LogError(v43, v42, 0x415u, 0, 0, v45);
        v10 = 0;
        v3 = 0;
        goto LABEL_46;
      }
      v3 = 0;
      v10 = 0;
    }
  }
LABEL_47:
  _CatDBFree(v9);
LABEL_48:
  if ( v10 )
    _CatDBFree(v10);
  if ( v2 )
    _CatDBFree(v2);
  if ( v3 )
    _CatDBFree(v3);
  if ( (unsigned __int64)(FirstFileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    FindClose((HANDLE)FirstFileW);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (void *),&void _CatDBFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (void *),&void _CatDBFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(v47);
  return v5;
}

```

## disassembly

```asm
0x18001d62c  push    rbp
0x18001d62e  push    rbx
0x18001d62f  push    rsi
0x18001d630  push    rdi
0x18001d631  push    r12
0x18001d633  push    r13
0x18001d635  push    r14
0x18001d637  push    r15
0x18001d639  lea     rbp, [rsp-1D8h]
0x18001d641  sub     rsp, 2D8h
0x18001d648  mov     [rsp+310h+var_2D0], 0FFFFFFFFFFFFFFFEh
0x18001d651  mov     rax, cs:__security_cookie
0x18001d658  xor     rax, rsp
0x18001d65b  mov     [rbp+210h+var_50], rax
0x18001d662  mov     r14d, ecx
0x18001d665  mov     [rsp+310h+var_2D8], 0
0x18001d66e  xor     r12d, r12d
0x18001d671  xor     edi, edi
0x18001d673  or      r15, 0FFFFFFFFFFFFFFFFh
0x18001d677  xor     edx, edx; Val
0x18001d679  mov     r8d, 250h; Size
0x18001d67f  lea     rcx, [rsp+310h+FindFileData]; void *
0x18001d684  call    memset_0
0x18001d689  lea     r13d, [r12+1]
0x18001d68e  mov     ecx, r13d; int
0x18001d691  call    ?_CatDBGetCatrootDirW@@YAPEAGH@Z; _CatDBGetCatrootDirW(int)
0x18001d696  mov     rsi, rax
0x18001d699  test    rax, rax
0x18001d69c  jnz     short loc_18001D6AB
0x18001d69e  xor     ebx, ebx
0x18001d6a0  mov     r8d, 344h
0x18001d6a6  jmp     loc_18001D9D1
0x18001d6ab  lea     rdx, aEdbLog; "edb*.log"
0x18001d6b2  mov     rcx, rsi; unsigned __int16 *
0x18001d6b5  call    ?_CATDBConstructWSTRPath@@YAPEAGPEBG0@Z; _CATDBConstructWSTRPath(ushort const *,ushort const *)
0x18001d6ba  mov     rbx, rax
0x18001d6bd  test    rax, rax
0x18001d6c0  jnz     short loc_18001D6D1
0x18001d6c2  mov     [rsp+310h+var_2F0], edi
0x18001d6c6  mov     r8d, 350h
0x18001d6cc  jmp     loc_18001D9D5
0x18001d6d1  mov     rdx, rbx; lpFileName
0x18001d6d4  mov     rcx, rsi; unsigned __int16 *
0x18001d6d7  call    ?_CatDBDeleteFiles@@YAHPEBG0@Z; _CatDBDeleteFiles(ushort const *,ushort const *)
0x18001d6dc  test    eax, eax
0x18001d6de  jnz     short loc_18001D6EF
0x18001d6e0  mov     [rsp+310h+var_2F0], edi
0x18001d6e4  mov     r8d, 356h
0x18001d6ea  jmp     loc_18001D9D5
0x18001d6ef  mov     rcx, rbx; void *
0x18001d6f2  call    ?_CatDBFree@@YAXPEAX@Z; _CatDBFree(void *)
0x18001d6f7  lea     rdx, aResLog; "res*.log"
0x18001d6fe  mov     rcx, rsi; unsigned __int16 *
0x18001d701  call    ?_CATDBConstructWSTRPath@@YAPEAGPEBG0@Z; _CATDBConstructWSTRPath(ushort const *,ushort const *)
0x18001d706  mov     rbx, rax
0x18001d709  test    rax, rax
0x18001d70c  jnz     short loc_18001D71D
0x18001d70e  mov     [rsp+310h+var_2F0], edi
0x18001d712  mov     r8d, 361h
0x18001d718  jmp     loc_18001D9D5
0x18001d71d  mov     rdx, rbx; lpFileName
0x18001d720  mov     rcx, rsi; unsigned __int16 *
0x18001d723  call    ?_CatDBDeleteFiles@@YAHPEBG0@Z; _CatDBDeleteFiles(ushort const *,ushort const *)
0x18001d728  test    eax, eax
0x18001d72a  jnz     short loc_18001D73B
0x18001d72c  mov     [rsp+310h+var_2F0], edi
0x18001d730  mov     r8d, 367h
0x18001d736  jmp     loc_18001D9D5
0x18001d73b  mov     rcx, rbx; void *
0x18001d73e  call    ?_CatDBFree@@YAXPEAX@Z; _CatDBFree(void *)
0x18001d743  lea     rdx, aEdbChk; "edb.chk"
0x18001d74a  mov     rcx, rsi; unsigned __int16 *
0x18001d74d  call    ?_CATDBConstructWSTRPath@@YAPEAGPEBG0@Z; _CATDBConstructWSTRPath(ushort const *,ushort const *)
0x18001d752  mov     rbx, rax
0x18001d755  test    rax, rax
0x18001d758  jnz     short loc_18001D769
0x18001d75a  mov     [rsp+310h+var_2F0], edi
0x18001d75e  mov     r8d, 376h
0x18001d764  jmp     loc_18001D9D5
0x18001d769  mov     rcx, rbx; lpFileName
0x18001d76c  call    cs:__imp_DeleteFileW
0x18001d772  mov     rcx, rbx; void *
0x18001d775  call    ?_CatDBFree@@YAXPEAX@Z; _CatDBFree(void *)
0x18001d77a  lea     rdx, aEdbJrs; "edb*.jrs"
0x18001d781  mov     rcx, rsi; unsigned __int16 *
0x18001d784  call    ?_CATDBConstructWSTRPath@@YAPEAGPEBG0@Z; _CATDBConstructWSTRPath(ushort const *,ushort const *)
0x18001d789  mov     rbx, rax
0x18001d78c  test    rax, rax
0x18001d78f  jnz     short loc_18001D7A0
0x18001d791  mov     [rsp+310h+var_2F0], edi
0x18001d795  mov     r8d, 387h
0x18001d79b  jmp     loc_18001D9D5
0x18001d7a0  mov     rdx, rbx; lpFileName
0x18001d7a3  mov     rcx, rsi; unsigned __int16 *
0x18001d7a6  call    ?_CatDBDeleteFiles@@YAHPEBG0@Z; _CatDBDeleteFiles(ushort const *,ushort const *)
0x18001d7ab  mov     rcx, rbx; void *
0x18001d7ae  call    ?_CatDBFree@@YAXPEAX@Z; _CatDBFree(void *)
0x18001d7b3  xor     ebx, ebx
0x18001d7b5  test    r14d, r14d
0x18001d7b8  jnz     loc_18001D9E5
0x18001d7be  lea     rdx, asc_180024D90; "{????????????????????????????????????}"
0x18001d7c5  mov     rcx, rsi; unsigned __int16 *
0x18001d7c8  call    ?_CATDBConstructWSTRPath@@YAPEAGPEBG0@Z; _CATDBConstructWSTRPath(ushort const *,ushort const *)
0x18001d7cd  mov     r12, rax
0x18001d7d0  test    rax, rax
0x18001d7d3  jnz     short loc_18001D7E0
0x18001d7d5  mov     r8d, 3A0h
0x18001d7db  jmp     loc_18001D9D1
0x18001d7e0  lea     rdx, [rsp+310h+FindFileData]; lpFindFileData
0x18001d7e5  mov     rcx, rax; lpFileName
0x18001d7e8  call    cs:__imp_FindFirstFileW
0x18001d7ee  mov     r15, rax
0x18001d7f1  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001d7f5  jnz     short loc_18001D81C
0x18001d7f7  call    cs:__imp_GetLastError
0x18001d7fd  lea     ecx, [rax-2]
0x18001d800  test    ecx, 0FFFFFFEEh
0x18001d806  jnz     short loc_18001D811
0x18001d808  cmp     eax, 13h
0x18001d80b  jnz     loc_18001D9E5
0x18001d811  mov     r8d, 3B9h
0x18001d817  jmp     loc_18001D9D1
0x18001d81c  xor     ecx, ecx; int
0x18001d81e  call    ?_CatDBGetCatrootDirW@@YAPEAGH@Z; _CatDBGetCatrootDirW(int)
0x18001d823  mov     r14, rax
0x18001d826  mov     [rsp+310h+var_2D8], rax
0x18001d82b  test    rax, rax
0x18001d82e  jz      loc_18001D9CB
0x18001d834  mov     ecx, 2Eh ; '.'
0x18001d839  test    byte ptr [rsp+310h+FindFileData.dwFileAttributes], 10h
0x18001d83e  jz      loc_18001D93B
0x18001d844  cmp     cx, [rbp+210h+FindFileData.cFileName]
0x18001d848  jnz     short loc_18001D86C
0x18001d84a  xor     eax, eax
0x18001d84c  cmp     ax, [rbp+210h+FindFileData.cFileName+2]
0x18001d850  jz      loc_18001D93B
0x18001d856  cmp     cx, [rbp+210h+FindFileData.cFileName]
0x18001d85a  jnz     short loc_18001D86C
0x18001d85c  cmp     cx, [rbp+210h+FindFileData.cFileName+2]
0x18001d860  jnz     short loc_18001D86C
0x18001d862  cmp     ax, [rbp+210h+FindFileData.cFileName+4]
0x18001d866  jz      loc_18001D93B
0x18001d86c  lea     rdx, [rbp+210h+FindFileData.cFileName]; unsigned __int16 *
0x18001d870  mov     rcx, rsi; unsigned __int16 *
0x18001d873  call    ?_CATDBConstructWSTRPath@@YAPEAGPEBG0@Z; _CATDBConstructWSTRPath(ushort const *,ushort const *)
0x18001d878  mov     rdi, rax
0x18001d87b  test    rax, rax
0x18001d87e  jz      loc_18001D9AB
0x18001d884  lea     rdx, aCatdb; "catdb*"
0x18001d88b  mov     rcx, rax; unsigned __int16 *
0x18001d88e  call    ?_CATDBConstructWSTRPath@@YAPEAGPEBG0@Z; _CATDBConstructWSTRPath(ushort const *,ushort const *)
0x18001d893  mov     rbx, rax
0x18001d896  test    rax, rax
0x18001d899  jz      loc_18001D99B
0x18001d89f  mov     rdx, rax; lpFileName
0x18001d8a2  mov     rcx, rdi; unsigned __int16 *
0x18001d8a5  call    ?_CatDBDeleteFiles@@YAHPEBG0@Z; _CatDBDeleteFiles(ushort const *,ushort const *)
0x18001d8aa  xorps   xmm0, xmm0
0x18001d8ad  xor     eax, eax
0x18001d8af  movups  [rsp+310h+FileInformation], xmm0
0x18001d8b4  movups  [rsp+310h+var_2B8], xmm0
0x18001d8b9  mov     [rsp+310h+var_2A8], eax
0x18001d8bd  lea     rdx, [rbp+210h+FindFileData.cFileName]; unsigned __int16 *
0x18001d8c1  mov     rcx, r14; unsigned __int16 *
0x18001d8c4  call    ?_CATDBConstructWSTRPath@@YAPEAGPEBG0@Z; _CATDBConstructWSTRPath(ushort const *,ushort const *)
0x18001d8c9  mov     [rsp+310h+var_2E0], rax
0x18001d8ce  test    rax, rax
0x18001d8d1  jz      loc_18001D978
0x18001d8d7  lea     r8, [rsp+310h+FileInformation]; lpFileInformation
0x18001d8dc  xor     edx, edx; fInfoLevelId
0x18001d8de  mov     rcx, rax; lpFileName
0x18001d8e1  call    cs:__imp_GetFileAttributesExW
0x18001d8e7  test    eax, eax
0x18001d8e9  jnz     short loc_18001D921
0x18001d8eb  call    cs:__imp_GetLastError
0x18001d8f1  cmp     eax, 2
0x18001d8f4  jz      short loc_18001D901
0x18001d8f6  call    cs:__imp_GetLastError
0x18001d8fc  cmp     eax, 3
0x18001d8ff  jnz     short loc_18001D921
0x18001d901  mov     rcx, rdi; lpPathName
0x18001d904  call    cs:__imp_RemoveDirectoryW
0x18001d90a  test    eax, eax
0x18001d90c  jnz     short loc_18001D921
0x18001d90e  mov     [rsp+310h+var_2F0], eax; int
0x18001d912  xor     r9d, r9d; unsigned int
0x18001d915  mov     r8d, 3FDh; unsigned int
0x18001d91b  call    ?ErrLog_LogError@@YAXPEAGKKKHH@Z; ErrLog_LogError(ushort *,ulong,ulong,ulong,int,int)
0x18001d920  nop
0x18001d921  lea     rcx, [rsp+310h+var_2E0]
0x18001d926  call    ??1?$unique_storage@U?$resource_policy@PEAG$$A6AXPEAX@Z$1?_CatDBFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (void *),&_CatDBFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (void *),&_CatDBFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18001d92b  mov     rcx, rbx; void *
0x18001d92e  call    ?_CatDBFree@@YAXPEAX@Z; _CatDBFree(void *)
0x18001d933  mov     rcx, rdi; void *
0x18001d936  call    ?_CatDBFree@@YAXPEAX@Z; _CatDBFree(void *)
0x18001d93b  lea     rdx, [rsp+310h+FindFileData]; lpFindFileData
0x18001d940  mov     rcx, r15; hFindFile
0x18001d943  call    cs:__imp_FindNextFileW
0x18001d949  test    eax, eax
0x18001d94b  jnz     loc_18001D834
0x18001d951  call    cs:__imp_GetLastError
0x18001d957  cmp     eax, 12h
0x18001d95a  jz      short loc_18001D9C5
0x18001d95c  mov     [rsp+310h+var_2F0], 0; int
0x18001d964  xor     r9d, r9d; unsigned int
0x18001d967  mov     r8d, 415h; unsigned int
0x18001d96d  call    ?ErrLog_LogError@@YAXPEAGKKKHH@Z; ErrLog_LogError(ushort *,ulong,ulong,ulong,int,int)
0x18001d972  xor     ebx, ebx
0x18001d974  xor     edi, edi
0x18001d976  jmp     short loc_18001D9DD
0x18001d978  mov     [rsp+310h+var_2F0], 0; int
0x18001d980  xor     r9d, r9d; unsigned int
0x18001d983  mov     r8d, 3F1h; unsigned int
0x18001d989  call    ?ErrLog_LogError@@YAXPEAGKKKHH@Z; ErrLog_LogError(ushort *,ulong,ulong,ulong,int,int)
0x18001d98e  nop
0x18001d98f  lea     rcx, [rsp+310h+var_2E0]
0x18001d994  call    ??1?$unique_storage@U?$resource_policy@PEAG$$A6AXPEAX@Z$1?_CatDBFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (void *),&_CatDBFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (void *),&_CatDBFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18001d999  jmp     short loc_18001D9DD
0x18001d99b  mov     [rsp+310h+var_2F0], 0
0x18001d9a3  mov     r8d, 3E0h
0x18001d9a9  jmp     short loc_18001D9D5
0x18001d9ab  mov     [rsp+310h+var_2F0], 0; int
0x18001d9b3  xor     r9d, r9d; unsigned int
0x18001d9b6  mov     r8d, 3D5h; unsigned int
0x18001d9bc  call    ?ErrLog_LogError@@YAXPEAGKKKHH@Z; ErrLog_LogError(ushort *,ulong,ulong,ulong,int,int)
0x18001d9c1  xor     ebx, ebx
0x18001d9c3  jmp     short loc_18001D9DD
0x18001d9c5  xor     edi, edi
0x18001d9c7  xor     ebx, ebx
0x18001d9c9  jmp     short loc_18001D9E5
0x18001d9cb  mov     r8d, 3C4h; unsigned int
0x18001d9d1  mov     [rsp+310h+var_2F0], ebx; int
0x18001d9d5  xor     r9d, r9d; unsigned int
0x18001d9d8  call    ?ErrLog_LogError@@YAXPEAGKKKHH@Z; ErrLog_LogError(ushort *,ulong,ulong,ulong,int,int)
0x18001d9dd  xor     r13d, r13d
0x18001d9e0  test    rsi, rsi
0x18001d9e3  jz      short loc_18001D9ED
0x18001d9e5  mov     rcx, rsi; void *
0x18001d9e8  call    ?_CatDBFree@@YAXPEAX@Z; _CatDBFree(void *)
0x18001d9ed  test    rbx, rbx
0x18001d9f0  jz      short loc_18001D9FA
0x18001d9f2  mov     rcx, rbx; void *
0x18001d9f5  call    ?_CatDBFree@@YAXPEAX@Z; _CatDBFree(void *)
0x18001d9fa  test    r12, r12
0x18001d9fd  jz      short loc_18001DA07
0x18001d9ff  mov     rcx, r12; void *
0x18001da02  call    ?_CatDBFree@@YAXPEAX@Z; _CatDBFree(void *)
0x18001da07  test    rdi, rdi
0x18001da0a  jz      short loc_18001DA14
0x18001da0c  mov     rcx, rdi; void *
0x18001da0f  call    ?_CatDBFree@@YAXPEAX@Z; _CatDBFree(void *)
0x18001da14  lea     rcx, [r15-1]
0x18001da18  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x18001da1c  ja      short loc_18001DA28
0x18001da1e  mov     rcx, r15; hFindFile
0x18001da21  call    cs:__imp_FindClose
0x18001da27  nop
0x18001da28  lea     rcx, [rsp+310h+var_2D8]
0x18001da2d  call    ??1?$unique_storage@U?$resource_policy@PEAG$$A6AXPEAX@Z$1?_CatDBFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (void *),&_CatDBFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (void *),&_CatDBFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18001da32  mov     eax, r13d
0x18001da35  mov     rcx, [rbp+210h+var_50]
0x18001da3c  xor     rcx, rsp; StackCookie
0x18001da3f  call    __security_check_cookie
0x18001da44  add     rsp, 2D8h
0x18001da4b  pop     r15
0x18001da4d  pop     r14
0x18001da4f  pop     r13
0x18001da51  pop     r12
0x18001da53  pop     rdi
0x18001da54  pop     rsi
0x18001da55  pop     rbx
0x18001da56  pop     rbp
0x18001da57  retn
```
