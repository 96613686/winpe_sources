# CDplUser::BackupRecoveryFileToFolder(ushort *,_WIN32_FIND_DATAW *,ushort *)

- ea: `0x1800ac1e4`
- end: `0x1800ac716`
- name: `?BackupRecoveryFileToFolder@CDplUser@@AEAAXPEAGPEAU_WIN32_FIND_DATAW@@0@Z`
- size: `1330`
- prototype: `void(CDplUser *__hidden this, unsigned __int16 *, struct _WIN32_FIND_DATAW *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800b9174`

## callees

- `0x180001a7c`
- `0x180001b48`
- `0x180005045`
- `0x18000b8c8`
- `0x180063698`
- `0x180063730`
- `0x1800637e8`
- `0x18008ae7c`
- `0x1800ac1e4`
- `0x1800dddf0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ac4fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ac5b2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ac5f0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ac62b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ac4fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ac5b2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ac5f0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ac62b`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x1800ac4f3`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x1800ac5a8`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x1800ac4f3`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x1800ac5a8`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800ac6a2`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800ac6b4`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800ac6a2`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800ac6b4`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesExW` at `0x1800ac41e`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesExW` at `0x1800ac41e`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x1800ac5e6`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x1800ac621`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x1800ac5e6`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x1800ac621`
- `ntdll!RtlDoesFileExists_U` at `0x1800ac405`
- `ntdll!RtlDoesFileExists_U` at `0x1800ac405`

## pseudocode

```c
void __fastcall CDplUser::BackupRecoveryFileToFolder(
        CDplUser *this,
        unsigned __int16 *a2,
        struct _WIN32_FIND_DATAW *a3,
        unsigned __int16 *a4)
{
  char v6; // si
  char v8; // r12
  int v9; // ecx
  int v10; // ecx
  unsigned int v11; // ebx
  int v12; // r8d
  int v13; // ecx
  DWORD v14; // ecx
  BOOLEAN DoesFileExists_U; // r15
  DWORD v16; // ebx
  int v17; // ecx
  signed int LastError; // eax
  signed int v19; // eax
  signed int v20; // eax
  signed int v21; // eax
  int v22; // r8d
  int v23; // r9d
  char v24; // [rsp+20h] [rbp-E0h]
  unsigned int v25; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE FileInformation[36]; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR FileName[264]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR TempFileName[264]; // [rsp+280h] [rbp+180h] BYREF
  WCHAR pwszExistingFileName[264]; // [rsp+490h] [rbp+390h] BYREF
  WCHAR NewFileName[264]; // [rsp+6A0h] [rbp+5A0h] BYREF

  v6 = 0;
  memset_0(pwszExistingFileName, 0, 0x208u);
  memset_0(FileName, 0, 0x208u);
  memset_0(TempFileName, 0, 0x208u);
  memset_0(NewFileName, 0, 0x208u);
  v8 = 0;
  memset(FileInformation, 0, sizeof(FileInformation));
  fnEfsLogTrace1Strings(v9, (unsigned int)EFS_TRACE_ENTER_EVENT, (unsigned int)&sourceString, 40, 79);
  *(_DWORD *)FileInformation = -1;
  if ( !a2 )
  {
    v24 = 83;
LABEL_3:
    v11 = -2147024809;
    v12 = -2147024809;
LABEL_4:
    fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, v12, 40, v24);
    goto LABEL_38;
  }
  if ( !a3 )
  {
    v24 = 84;
    goto LABEL_3;
  }
  if ( !a4 )
  {
    v24 = 85;
    goto LABEL_3;
  }
  fnEfsLogTrace1Strings(v10, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 40, 95);
  v11 = StringCchPrintfW(pwszExistingFileName, 0x104u, L"%s\\%s", a2, a3->cFileName);
  if ( (int)fnEfsLogTrace1String1Dword(
              g_hPublisher,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
              (unsigned int)&sourceString,
              v11,
              40,
              95) < 0 )
    goto LABEL_38;
  fnEfsLogTrace1Strings(v13, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 40, 105);
  v11 = StringCchPrintfW(FileName, 0x104u, L"%s\\%s", a4, a3->cFileName);
  if ( (int)fnEfsLogTrace1String1Dword(
              g_hPublisher,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
              (unsigned int)&sourceString,
              v11,
              40,
              105) < 0 )
    goto LABEL_38;
  DoesFileExists_U = RtlDoesFileExists_U(FileName);
  if ( DoesFileExists_U )
  {
    if ( GetFileAttributesExW(FileName, GetFileExInfoStandard, FileInformation) )
    {
      v14 = *(_DWORD *)FileInformation;
      if ( (FileInformation[0] & 0x10) == 0
        && *(_QWORD *)&FileInformation[20] >= *(_QWORD *)&a3->ftLastWriteTime
        && *(_QWORD *)&FileInformation[28] == *(_QWORD *)&a3->nFileSizeHigh )
      {
        v14 = a3->dwFileAttributes ^ *(_DWORD *)FileInformation;
        if ( (v14 & 0x4000) == 0 )
          goto LABEL_45;
      }
    }
  }
  v16 = (a3->dwFileAttributes & 0x4000 | 0x8000) >> 14;
  if ( !DoesFileExists_U )
  {
    fnEfsLogTrace1Strings(v14, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 40, 162);
    v11 = CDplService::EdpCopyFile(pwszExistingFileName, FileName, v16);
    fnEfsLogTrace1String1Dword(
      g_hPublisher,
      (unsigned int)EFS_TRACE_COMPLETE_EVENT,
      (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
      (unsigned int)&sourceString,
      v11,
      40,
      162);
    goto LABEL_38;
  }
  if ( !GetTempFileNameW(a4, L"New", 0, TempFileName) )
  {
    LastError = GetLastError();
    v11 = LastError;
    if ( LastError > 0 )
      v11 = (unsigned __int16)LastError | 0x80070000;
    v24 = -85;
LABEL_23:
    v12 = v11;
    goto LABEL_4;
  }
  v6 = 1;
  fnEfsLogTrace1Strings(v17, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 40, 182);
  v11 = CDplService::EdpCopyFile(pwszExistingFileName, TempFileName, v16);
  if ( (int)fnEfsLogTrace1String1Dword(
              g_hPublisher,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
              (unsigned int)&sourceString,
              v11,
              40,
              182) >= 0 )
  {
    if ( !GetTempFileNameW(a4, L"Old", 0, NewFileName) )
    {
      v19 = GetLastError();
      v11 = v19;
      if ( v19 > 0 )
        v11 = (unsigned __int16)v19 | 0x80070000;
      v24 = -67;
      goto LABEL_23;
    }
    v8 = 1;
    if ( !MoveFileExW(FileName, NewFileName, 1u) )
    {
      v20 = GetLastError();
      v11 = v20;
      if ( v20 > 0 )
        v11 = (unsigned __int16)v20 | 0x80070000;
      v24 = -57;
      goto LABEL_23;
    }
    if ( !MoveFileExW(TempFileName, FileName, 1u) )
    {
      v21 = GetLastError();
      v11 = v21;
      if ( v21 > 0 )
        v11 = (unsigned __int16)v21 | 0x80070000;
      v24 = -49;
      goto LABEL_23;
    }
    v6 = 0;
  }
LABEL_38:
  if ( (unsigned int)dword_180114250 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180114250, 0x400000000000LL) )
  {
    v25 = v11;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      (unsigned int)&dword_180114250,
      (unsigned int)byte_1801038F9,
      v22,
      v23,
      (__int64)&v25);
  }
  if ( v6 )
    DeleteFileW(TempFileName);
  if ( v8 )
    DeleteFileW(NewFileName);
LABEL_45:
  fnEfsLogTrace1String1Dword(
    g_hPublisher,
    (unsigned int)EFS_TRACE_LEAVE_HR_EVENT,
    (unsigned int)EFS_TRACE_LEAVE_HR_EVENT_ERROR,
    (unsigned int)&sourceString,
    v11,
    40,
    229);
}

```

## disassembly

```asm
0x1800ac1e4  mov     [rsp-8+arg_0], rbx
0x1800ac1e9  push    rbp
0x1800ac1ea  push    rsi
0x1800ac1eb  push    rdi
0x1800ac1ec  push    r12
0x1800ac1ee  push    r13
0x1800ac1f0  push    r14
0x1800ac1f2  push    r15
0x1800ac1f4  lea     rbp, [rsp-7C0h]
0x1800ac1fc  sub     rsp, 8C0h
0x1800ac203  mov     rax, cs:__security_cookie
0x1800ac20a  xor     rax, rsp
0x1800ac20d  mov     [rbp+7F0h+var_40], rax
0x1800ac214  mov     rdi, r8
0x1800ac217  lea     rcx, [rbp+7F0h+pwszExistingFileName]; void *
0x1800ac21e  mov     rbx, rdx
0x1800ac221  mov     esi, 208h
0x1800ac226  mov     r8d, esi; Size
0x1800ac229  xor     edx, edx; Val
0x1800ac22b  mov     r14, r9
0x1800ac22e  call    memset_0
0x1800ac233  mov     r8d, esi; Size
0x1800ac236  lea     rcx, [rsp+8F0h+FileName]; void *
0x1800ac23b  xor     edx, edx; Val
0x1800ac23d  call    memset_0
0x1800ac242  mov     r8d, esi; Size
0x1800ac245  lea     rcx, [rbp+7F0h+TempFileName]; void *
0x1800ac24c  xor     edx, edx; Val
0x1800ac24e  call    memset_0
0x1800ac253  mov     r8d, esi; Size
0x1800ac256  lea     rcx, [rbp+7F0h+NewFileName]; void *
0x1800ac25d  xor     edx, edx; Val
0x1800ac25f  call    memset_0
0x1800ac264  xor     eax, eax
0x1800ac266  mov     dword ptr [rsp+8F0h+var_8D0], 264Fh
0x1800ac26e  xorps   xmm0, xmm0
0x1800ac271  mov     dword ptr [rsp+8F0h+var_898+10h], eax
0x1800ac275  lea     r8, sourceString
0x1800ac27c  xor     sil, sil
0x1800ac27f  lea     rdx, EFS_TRACE_ENTER_EVENT
0x1800ac286  xor     r12b, r12b
0x1800ac289  lea     r13d, [rax+28h]
0x1800ac28d  mov     r9d, r13d
0x1800ac290  movups  [rsp+8F0h+FileInformation], xmm0
0x1800ac295  movups  xmmword ptr [rsp+8F0h+var_898], xmm0
0x1800ac29a  call    fnEfsLogTrace1Strings
0x1800ac29f  mov     dword ptr [rsp+8F0h+FileInformation], 0FFFFFFFFh
0x1800ac2a7  test    rbx, rbx
0x1800ac2aa  jnz     short loc_1800AC2DA
0x1800ac2ac  mov     dword ptr [rsp+8F0h+var_8D0], 2653h
0x1800ac2b4  mov     ebx, 80070057h
0x1800ac2b9  mov     r8d, 80070057h
0x1800ac2bf  mov     rcx, cs:g_hPublisher
0x1800ac2c6  lea     rdx, EFS_TRACE_ERROR
0x1800ac2cd  mov     r9d, r13d
0x1800ac2d0  call    fnEfsLogTrace1
0x1800ac2d5  jmp     loc_1800AC650
0x1800ac2da  test    rdi, rdi
0x1800ac2dd  jnz     short loc_1800AC2E9
0x1800ac2df  mov     dword ptr [rsp+8F0h+var_8D0], 2654h
0x1800ac2e7  jmp     short loc_1800AC2B4
0x1800ac2e9  test    r14, r14
0x1800ac2ec  jnz     short loc_1800AC2F8
0x1800ac2ee  mov     dword ptr [rsp+8F0h+var_8D0], 2655h
0x1800ac2f6  jmp     short loc_1800AC2B4
0x1800ac2f8  mov     r13d, 265Fh
0x1800ac2fe  lea     r8, sourceString
0x1800ac305  mov     r9d, 28h ; '('
0x1800ac30b  mov     dword ptr [rsp+8F0h+var_8D0], r13d
0x1800ac310  lea     rdx, EFS_TRACE_START_EVENT
0x1800ac317  call    fnEfsLogTrace1Strings
0x1800ac31c  lea     r15, [rdi+2Ch]
0x1800ac320  mov     r9, rbx
0x1800ac323  lea     r8, aSS; "%s\\%s"
0x1800ac32a  mov     [rsp+8F0h+var_8D0], r15
0x1800ac32f  mov     edx, 104h; unsigned __int64
0x1800ac334  lea     rcx, [rbp+7F0h+pwszExistingFileName]; unsigned __int16 *
0x1800ac33b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800ac340  mov     rcx, cs:g_hPublisher
0x1800ac347  lea     r9, sourceString
0x1800ac34e  mov     [rsp+8F0h+var_8C0], r13d
0x1800ac353  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x1800ac35a  mov     r13d, 28h ; '('
0x1800ac360  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x1800ac367  mov     [rsp+8F0h+var_8C8], r13d
0x1800ac36c  mov     ebx, eax
0x1800ac36e  mov     dword ptr [rsp+8F0h+var_8D0], eax
0x1800ac372  call    fnEfsLogTrace1String1Dword
0x1800ac377  test    eax, eax
0x1800ac379  js      loc_1800AC650
0x1800ac37f  mov     r13d, 2669h
0x1800ac385  lea     r8, sourceString
0x1800ac38c  mov     r9d, 28h ; '('
0x1800ac392  mov     dword ptr [rsp+8F0h+var_8D0], r13d
0x1800ac397  lea     rdx, EFS_TRACE_START_EVENT
0x1800ac39e  call    fnEfsLogTrace1Strings
0x1800ac3a3  mov     r9, r14
0x1800ac3a6  mov     [rsp+8F0h+var_8D0], r15
0x1800ac3ab  lea     r8, aSS; "%s\\%s"
0x1800ac3b2  mov     edx, 104h; unsigned __int64
0x1800ac3b7  lea     rcx, [rsp+8F0h+FileName]; unsigned __int16 *
0x1800ac3bc  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800ac3c1  mov     rcx, cs:g_hPublisher
0x1800ac3c8  lea     r9, sourceString
0x1800ac3cf  mov     [rsp+8F0h+var_8C0], r13d
0x1800ac3d4  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x1800ac3db  mov     r13d, 28h ; '('
0x1800ac3e1  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x1800ac3e8  mov     [rsp+8F0h+var_8C8], r13d
0x1800ac3ed  mov     ebx, eax
0x1800ac3ef  mov     dword ptr [rsp+8F0h+var_8D0], eax
0x1800ac3f3  call    fnEfsLogTrace1String1Dword
0x1800ac3f8  test    eax, eax
0x1800ac3fa  js      loc_1800AC650
0x1800ac400  lea     rcx, [rsp+8F0h+FileName]; FileName
0x1800ac405  call    cs:__imp_RtlDoesFileExists_U
0x1800ac40b  mov     r15b, al
0x1800ac40e  test    al, al
0x1800ac410  jz      short loc_1800AC463
0x1800ac412  lea     r8, [rsp+8F0h+FileInformation]; lpFileInformation
0x1800ac417  xor     edx, edx; fInfoLevelId
0x1800ac419  lea     rcx, [rsp+8F0h+FileName]; lpFileName
0x1800ac41e  call    cs:__imp_GetFileAttributesExW
0x1800ac424  test    eax, eax
0x1800ac426  jz      short loc_1800AC463
0x1800ac428  mov     ecx, dword ptr [rsp+8F0h+FileInformation]
0x1800ac42c  test    cl, 10h
0x1800ac42f  jnz     short loc_1800AC463
0x1800ac431  mov     eax, dword ptr [rsp+8F0h+var_898+8]
0x1800ac435  cmp     eax, [rdi+18h]
0x1800ac438  ja      short loc_1800AC445
0x1800ac43a  jnz     short loc_1800AC463
0x1800ac43c  mov     eax, [rdi+14h]
0x1800ac43f  cmp     dword ptr [rsp+8F0h+var_898+4], eax
0x1800ac443  jb      short loc_1800AC463
0x1800ac445  mov     eax, [rdi+1Ch]
0x1800ac448  cmp     dword ptr [rsp+8F0h+var_898+0Ch], eax
0x1800ac44c  jnz     short loc_1800AC463
0x1800ac44e  mov     eax, [rdi+20h]
0x1800ac451  cmp     dword ptr [rsp+8F0h+var_898+10h], eax
0x1800ac455  jnz     short loc_1800AC463
0x1800ac457  xor     ecx, [rdi]
0x1800ac459  bt      ecx, 0Eh
0x1800ac45d  jnb     loc_1800AC6BA
0x1800ac463  mov     ebx, [rdi]
0x1800ac465  and     ebx, 4000h
0x1800ac46b  bts     ebx, 0Fh
0x1800ac46f  shr     ebx, 0Eh
0x1800ac472  test    r15b, r15b
0x1800ac475  jnz     short loc_1800AC4DF
0x1800ac477  mov     edi, 26A2h
0x1800ac47c  lea     r8, sourceString
0x1800ac483  mov     r9d, r13d
0x1800ac486  mov     dword ptr [rsp+8F0h+var_8D0], edi
0x1800ac48a  lea     rdx, EFS_TRACE_START_EVENT
0x1800ac491  call    fnEfsLogTrace1Strings
0x1800ac496  mov     r8d, ebx; unsigned int
0x1800ac499  lea     rdx, [rsp+8F0h+FileName]; pwszNewFileName
0x1800ac49e  lea     rcx, [rbp+7F0h+pwszExistingFileName]; pwszExistingFileName
0x1800ac4a5  call    ?EdpCopyFile@CDplService@@SAJPEBG0K@Z; CDplService::EdpCopyFile(ushort const *,ushort const *,ulong)
0x1800ac4aa  mov     rcx, cs:g_hPublisher
0x1800ac4b1  lea     r9, sourceString
0x1800ac4b8  mov     [rsp+8F0h+var_8C0], edi
0x1800ac4bc  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x1800ac4c3  mov     [rsp+8F0h+var_8C8], r13d
0x1800ac4c8  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x1800ac4cf  mov     dword ptr [rsp+8F0h+var_8D0], eax
0x1800ac4d3  mov     ebx, eax
0x1800ac4d5  call    fnEfsLogTrace1String1Dword
0x1800ac4da  jmp     loc_1800AC650
0x1800ac4df  lea     r9, [rbp+7F0h+TempFileName]; lpTempFileName
0x1800ac4e6  xor     r8d, r8d; uUnique
0x1800ac4e9  lea     rdx, PrefixString; "New"
0x1800ac4f0  mov     rcx, r14; lpPathName
0x1800ac4f3  call    cs:__imp_GetTempFileNameW
0x1800ac4f9  test    eax, eax
0x1800ac4fb  jnz     short loc_1800AC522
0x1800ac4fd  call    cs:__imp_GetLastError
0x1800ac503  mov     ebx, eax
0x1800ac505  test    eax, eax
0x1800ac507  jle     short loc_1800AC512
0x1800ac509  movzx   ebx, ax
0x1800ac50c  or      ebx, 80070000h
0x1800ac512  mov     dword ptr [rsp+8F0h+var_8D0], 26ABh
0x1800ac51a  mov     r8d, ebx
0x1800ac51d  jmp     loc_1800AC2BF
0x1800ac522  mov     edi, 26B6h
0x1800ac527  lea     r8, sourceString
0x1800ac52e  mov     r9d, r13d
0x1800ac531  mov     dword ptr [rsp+8F0h+var_8D0], edi
0x1800ac535  lea     rdx, EFS_TRACE_START_EVENT
0x1800ac53c  mov     esi, 1
0x1800ac541  call    fnEfsLogTrace1Strings
0x1800ac546  mov     r8d, ebx; unsigned int
0x1800ac549  lea     rdx, [rbp+7F0h+TempFileName]; pwszNewFileName
0x1800ac550  lea     rcx, [rbp+7F0h+pwszExistingFileName]; pwszExistingFileName
0x1800ac557  call    ?EdpCopyFile@CDplService@@SAJPEBG0K@Z; CDplService::EdpCopyFile(ushort const *,ushort const *,ulong)
0x1800ac55c  mov     rcx, cs:g_hPublisher
0x1800ac563  lea     r9, sourceString
0x1800ac56a  mov     [rsp+8F0h+var_8C0], edi
0x1800ac56e  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x1800ac575  mov     [rsp+8F0h+var_8C8], r13d
0x1800ac57a  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x1800ac581  mov     dword ptr [rsp+8F0h+var_8D0], eax
0x1800ac585  mov     ebx, eax
0x1800ac587  call    fnEfsLogTrace1String1Dword
0x1800ac58c  test    eax, eax
0x1800ac58e  js      loc_1800AC650
0x1800ac594  lea     r9, [rbp+7F0h+NewFileName]; lpTempFileName
0x1800ac59b  xor     r8d, r8d; uUnique
0x1800ac59e  lea     rdx, aOld; "Old"
0x1800ac5a5  mov     rcx, r14; lpPathName
0x1800ac5a8  call    cs:__imp_GetTempFileNameW
0x1800ac5ae  test    eax, eax
0x1800ac5b0  jnz     short loc_1800AC5D4
0x1800ac5b2  call    cs:__imp_GetLastError
0x1800ac5b8  mov     ebx, eax
0x1800ac5ba  test    eax, eax
0x1800ac5bc  jle     short loc_1800AC5C7
0x1800ac5be  movzx   ebx, ax
0x1800ac5c1  or      ebx, 80070000h
0x1800ac5c7  mov     dword ptr [rsp+8F0h+var_8D0], 26BDh
0x1800ac5cf  jmp     loc_1800AC51A
0x1800ac5d4  mov     r8d, esi; dwFlags
0x1800ac5d7  lea     rdx, [rbp+7F0h+NewFileName]; lpNewFileName
0x1800ac5de  lea     rcx, [rsp+8F0h+FileName]; lpExistingFileName
0x1800ac5e3  mov     r12b, sil
0x1800ac5e6  call    cs:__imp_MoveFileExW
0x1800ac5ec  test    eax, eax
0x1800ac5ee  jnz     short loc_1800AC612
0x1800ac5f0  call    cs:__imp_GetLastError
0x1800ac5f6  mov     ebx, eax
0x1800ac5f8  test    eax, eax
0x1800ac5fa  jle     short loc_1800AC605
0x1800ac5fc  movzx   ebx, ax
0x1800ac5ff  or      ebx, 80070000h
0x1800ac605  mov     dword ptr [rsp+8F0h+var_8D0], 26C7h
0x1800ac60d  jmp     loc_1800AC51A
0x1800ac612  mov     r8d, esi; dwFlags
0x1800ac615  lea     rdx, [rsp+8F0h+FileName]; lpNewFileName
0x1800ac61a  lea     rcx, [rbp+7F0h+TempFileName]; lpExistingFileName
0x1800ac621  call    cs:__imp_MoveFileExW
0x1800ac627  test    eax, eax
0x1800ac629  jnz     short loc_1800AC64D
0x1800ac62b  call    cs:__imp_GetLastError
0x1800ac631  mov     ebx, eax
0x1800ac633  test    eax, eax
0x1800ac635  jle     short loc_1800AC640
0x1800ac637  movzx   ebx, ax
0x1800ac63a  or      ebx, 80070000h
0x1800ac640  mov     dword ptr [rsp+8F0h+var_8D0], 26CFh
0x1800ac648  jmp     loc_1800AC51A
0x1800ac64d  xor     sil, sil
0x1800ac650  mov     eax, cs:dword_180114250
0x1800ac656  cmp     eax, 5
0x1800ac659  jbe     short loc_1800AC696
0x1800ac65b  mov     rdx, 400000000000h
0x1800ac665  lea     rcx, dword_180114250
0x1800ac66c  call    _tlgKeywordOn
0x1800ac671  test    al, al
0x1800ac673  jz      short loc_1800AC696
0x1800ac675  lea     rax, [rsp+8F0h+var_8B0]
0x1800ac67a  mov     [rsp+8F0h+var_8B0], ebx
0x1800ac67e  lea     rdx, byte_1801038F9
0x1800ac685  mov     [rsp+8F0h+var_8D0], rax
0x1800ac68a  lea     rcx, dword_180114250
0x1800ac691  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x1800ac696  test    sil, sil
0x1800ac699  jz      short loc_1800AC6A8
0x1800ac69b  lea     rcx, [rbp+7F0h+TempFileName]; lpFileName
0x1800ac6a2  call    cs:__imp_DeleteFileW
0x1800ac6a8  test    r12b, r12b
0x1800ac6ab  jz      short loc_1800AC6BA
0x1800ac6ad  lea     rcx, [rbp+7F0h+NewFileName]; lpFileName
0x1800ac6b4  call    cs:__imp_DeleteFileW
0x1800ac6ba  mov     rcx, cs:g_hPublisher
0x1800ac6c1  lea     r9, sourceString
0x1800ac6c8  mov     [rsp+8F0h+var_8C0], 26E5h
0x1800ac6d0  lea     r8, EFS_TRACE_LEAVE_HR_EVENT_ERROR
0x1800ac6d7  mov     [rsp+8F0h+var_8C8], r13d
0x1800ac6dc  lea     rdx, EFS_TRACE_LEAVE_HR_EVENT
0x1800ac6e3  mov     dword ptr [rsp+8F0h+var_8D0], ebx
0x1800ac6e7  call    fnEfsLogTrace1String1Dword
0x1800ac6ec  mov     rcx, [rbp+7F0h+var_40]
0x1800ac6f3  xor     rcx, rsp; StackCookie
0x1800ac6f6  call    __security_check_cookie
0x1800ac6fb  mov     rbx, [rsp+8F0h+arg_0]
0x1800ac703  add     rsp, 8C0h
0x1800ac70a  pop     r15
0x1800ac70c  pop     r14
0x1800ac70e  pop     r13
0x1800ac710  pop     r12
0x1800ac712  pop     rdi
0x1800ac713  pop     rsi
0x1800ac714  pop     rbp
0x1800ac715  retn
```
