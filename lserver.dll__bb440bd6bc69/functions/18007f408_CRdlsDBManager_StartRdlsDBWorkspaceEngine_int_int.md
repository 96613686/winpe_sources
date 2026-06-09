# CRdlsDBManager::StartRdlsDBWorkspaceEngine(int,int)

- ea: `0x18007f408`
- end: `0x18007f932`
- name: `?StartRdlsDBWorkspaceEngine@CRdlsDBManager@@QEAAKHH@Z`
- size: `1322`
- prototype: `unsigned int __fastcall(CRdlsDBManager *__hidden this, int, int)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180020790`

## callees

- `0x180005665`
- `0x18000575c`
- `0x18000bb98`
- `0x18001ad48`
- `0x18001ad74`
- `0x18001ae3c`
- `0x18001b128`
- `0x180022af0`
- `0x18007f368`
- `0x18007f408`
- `0x180084738`
- `0x1800a0fb0`

## import_xrefs

- `msvcrt!wcscat_s` at `0x18007f50d`
- `msvcrt!wcscat_s` at `0x18007f529`
- `msvcrt!wcscat_s` at `0x18007f541`
- `msvcrt!wcscat_s` at `0x18007f50d`
- `msvcrt!wcscat_s` at `0x18007f529`
- `msvcrt!wcscat_s` at `0x18007f541`
- `msvcrt!wcscpy_s` at `0x18007f4f1`
- `msvcrt!wcscpy_s` at `0x18007f4f1`
- `KERNEL32!MoveFileExW` at `0x18007f5c4`
- `KERNEL32!MoveFileExW` at `0x18007f704`
- `KERNEL32!MoveFileExW` at `0x18007f725`
- `KERNEL32!MoveFileExW` at `0x18007f7af`
- `KERNEL32!MoveFileExW` at `0x18007f84d`
- `KERNEL32!MoveFileExW` at `0x18007f5c4`
- `KERNEL32!MoveFileExW` at `0x18007f704`
- `KERNEL32!MoveFileExW` at `0x18007f725`
- `KERNEL32!MoveFileExW` at `0x18007f7af`
- `KERNEL32!MoveFileExW` at `0x18007f84d`
- `KERNEL32!DeleteFileW` at `0x18007f7e1`
- `KERNEL32!DeleteFileW` at `0x18007f7e1`
- `KERNEL32!CompareFileTime` at `0x18007f655`
- `KERNEL32!CompareFileTime` at `0x18007f655`
- `KERNEL32!GetLastError` at `0x18007f5e5`
- `KERNEL32!GetLastError` at `0x18007f60c`
- `KERNEL32!GetLastError` at `0x18007f872`
- `KERNEL32!GetLastError` at `0x18007f8b6`
- `KERNEL32!GetLastError` at `0x18007f5e5`
- `KERNEL32!GetLastError` at `0x18007f60c`
- `KERNEL32!GetLastError` at `0x18007f872`
- `KERNEL32!GetLastError` at `0x18007f8b6`

## pseudocode

```c
unsigned int __fastcall CRdlsDBManager::StartRdlsDBWorkspaceEngine(CRdlsDBManager *this)
{
  wchar_t *v1; // r13
  unsigned int v2; // edx
  __int64 v3; // rax
  __int64 v4; // rcx
  DWORD LastError; // eax
  wchar_t *v6; // r8
  __int64 *v7; // rdx
  const struct _EVENT_DESCRIPTOR *v8; // rdx
  unsigned int v9; // edx
  PVOID *v11; // rcx
  __int64 v12; // rdx
  WCHAR *v13; // r9
  DWORD v14; // eax
  DWORD v15; // eax
  _BYTE v16[20]; // [rsp+38h] [rbp-D0h] BYREF
  FILETIME FileTime2; // [rsp+4Ch] [rbp-BCh] BYREF
  _BYTE v18[20]; // [rsp+288h] [rbp+180h] BYREF
  FILETIME FileTime1; // [rsp+29Ch] [rbp+194h] BYREF
  wchar_t Destination[264]; // [rsp+4D8h] [rbp+3D0h] BYREF
  WCHAR NewFileName[264]; // [rsp+6E8h] [rbp+5E0h] BYREF
  WCHAR v22[264]; // [rsp+8F8h] [rbp+7F0h] BYREF

  v1 = (wchar_t *)g_RdlsDBManager;
  memset_0(Destination, 0, 0x20Au);
  memset_0(v18, 0, 0x250u);
  memset_0(v16, 0, 0x250u);
  memset_0(NewFileName, 0, 0x20Au);
  memset_0(v22, 0, 0x20Au);
  v3 = -1;
  v4 = -1;
  do
    ++v4;
  while ( v1[v4 + 514] );
  do
    ++v3;
  while ( v1[v3 + 775] );
  if ( (unsigned __int64)(v4 + v3 + 7) > 0x104 )
    return CRdlsDBManager::StartRdlsDB((CRdlsDBManager *)v1, v2, 1);
  wcscpy_s(Destination, 0x105u, v1 + 514);
  wcscat_s(Destination, 0x105u, L"Export");
  wcscat_s(Destination, 0x105u, L"\\");
  wcscat_s(Destination, 0x105u, v1 + 775);
  if ( !(unsigned int)FileExists(Destination) )
    return CRdlsDBManager::StartRdlsDB((CRdlsDBManager *)v1, v2, 1);
  if ( !(unsigned int)FileExists(v1 + 1036) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_4505e5d286323dbdfbdc99a364b6b69a_Traceguids);
    if ( !MoveFileExW(Destination, v1 + 1036, 9u) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      {
        LastError = GetLastError();
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_4505e5d286323dbdfbdc99a364b6b69a_Traceguids, LastError);
      }
      GetLastError();
      v6 = Destination;
      v7 = TLS_W_DBRESTORE_MOVEFILE;
LABEL_53:
      CrimsonHelper::RaiseEvent<unsigned short *>(CrimsonHelper::s_instance, v7, v6);
      return CRdlsDBManager::StartRdlsDB((CRdlsDBManager *)v1, v2, 1);
    }
    v8 = &TLS_I_USE_DBRESTOREFILE;
    goto LABEL_16;
  }
  if ( CompareFileTime(&FileTime1, &FileTime2) <= 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_4505e5d286323dbdfbdc99a364b6b69a_Traceguids);
    return CRdlsDBManager::StartRdlsDB((CRdlsDBManager *)v1, v2, 1);
  }
  if ( !TlsGenerateLSDBBackupFileName(v1 + 514, NewFileName) )
    goto LABEL_50;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_4505e5d286323dbdfbdc99a364b6b69a_Traceguids, NewFileName);
  if ( !MoveFileExW(v1 + 1036, NewFileName, 9u) )
  {
LABEL_50:
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    {
      v15 = GetLastError();
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_4505e5d286323dbdfbdc99a364b6b69a_Traceguids, v15);
    }
    v6 = v1 + 1036;
    v7 = TLS_W_DBRESTORE_SAVEEXISTING;
    goto LABEL_53;
  }
  if ( MoveFileExW(Destination, v1 + 1036, 9u) && !CRdlsDBManager::StartRdlsDB((CRdlsDBManager *)v1, v9, 0) )
  {
    CrimsonHelper::RaiseEvent<unsigned short *>(CrimsonHelper::s_instance, TLS_I_OPENRESTOREDBFILE, NewFileName);
    return 0;
  }
  if ( !TlsGenerateLSDBBackupFileName(v1 + 514, v22) )
    goto LABEL_37;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_4505e5d286323dbdfbdc99a364b6b69a_Traceguids, v22);
  if ( MoveFileExW(v1 + 1036, v22, 9u) )
  {
    v11 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      {
        v12 = 18;
        v13 = v22;
LABEL_40:
        WPP_SF_S(v11[2], v12, WPP_4505e5d286323dbdfbdc99a364b6b69a_Traceguids, v13);
        v11 = (PVOID *)WPP_GLOBAL_Control;
        goto LABEL_41;
      }
      goto LABEL_41;
    }
  }
  else
  {
LABEL_37:
    DeleteFileW(v1 + 1036);
    v11 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      {
        v12 = 17;
        v13 = v1 + 1036;
        goto LABEL_40;
      }
LABEL_41:
      if ( v11 != &WPP_GLOBAL_Control && (*((_BYTE *)v11 + 28) & 0x40) != 0 )
        WPP_SF_SS(
          (unsigned int)v11[2],
          19,
          (unsigned int)WPP_4505e5d286323dbdfbdc99a364b6b69a_Traceguids,
          (unsigned int)NewFileName,
          (__int64)(v1 + 1036));
    }
  }
  if ( MoveFileExW(NewFileName, v1 + 1036, 9u) )
    return CRdlsDBManager::StartRdlsDB((CRdlsDBManager *)v1, v2, 1);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
  {
    v14 = GetLastError();
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_4505e5d286323dbdfbdc99a364b6b69a_Traceguids, v14);
  }
  v8 = (const struct _EVENT_DESCRIPTOR *)TLS_E_EXISTINGDBFILE_BKUPRESTORE_FAIL;
LABEL_16:
  CrimsonHelper::RaiseEventInternal((CrimsonHelper *)CrimsonHelper::s_instance, v8, 0, 0);
  return CRdlsDBManager::StartRdlsDB((CRdlsDBManager *)v1, v2, 1);
}

```

## disassembly

```asm
0x18007f408  mov     rax, rsp
0x18007f40b  mov     [rax+8], rbx
0x18007f40f  mov     [rax+10h], rsi
0x18007f413  mov     [rax+18h], rdi
0x18007f417  push    rbp
0x18007f418  push    r12
0x18007f41a  push    r13
0x18007f41c  push    r14
0x18007f41e  push    r15
0x18007f420  lea     rbp, [rax-0A38h]
0x18007f427  sub     rsp, 0B10h
0x18007f42e  mov     rax, cs:__security_cookie
0x18007f435  xor     rax, rsp
0x18007f438  mov     [rbp+0A30h+var_30], rax
0x18007f43f  mov     r13, cs:?g_RdlsDBManager@@3PEAVCRdlsDBManager@@EA; CRdlsDBManager * g_RdlsDBManager
0x18007f446  lea     rcx, [rbp+0A30h+Destination]; void *
0x18007f44d  mov     edi, 20Ah
0x18007f452  xor     edx, edx; Val
0x18007f454  mov     r8d, edi; Size
0x18007f457  call    memset_0
0x18007f45c  lea     ebx, [rdi+46h]
0x18007f45f  xor     edx, edx; Val
0x18007f461  mov     r8d, ebx; Size
0x18007f464  lea     rcx, [rbp+0A30h+var_8B0]; void *
0x18007f46b  call    memset_0
0x18007f470  mov     r8d, ebx; Size
0x18007f473  lea     rcx, [rsp+0B30h+var_B00]; void *
0x18007f478  xor     edx, edx; Val
0x18007f47a  call    memset_0
0x18007f47f  mov     r8d, edi; Size
0x18007f482  lea     rcx, [rbp+0A30h+NewFileName]; void *
0x18007f489  xor     edx, edx; Val
0x18007f48b  call    memset_0
0x18007f490  mov     r8d, edi; Size
0x18007f493  lea     rcx, [rbp+0A30h+var_240]; void *
0x18007f49a  xor     edx, edx; Val
0x18007f49c  call    memset_0
0x18007f4a1  or      rax, 0FFFFFFFFFFFFFFFFh
0x18007f4a5  lea     rbx, [r13+60Eh]
0x18007f4ac  mov     rcx, rax
0x18007f4af  lea     r12, [r13+404h]
0x18007f4b6  xor     r15d, r15d
0x18007f4b9  inc     rcx
0x18007f4bc  cmp     [r12+rcx*2], r15w
0x18007f4c1  jnz     short loc_18007F4B9
0x18007f4c3  inc     rax
0x18007f4c6  cmp     [rbx+rax*2], r15w
0x18007f4cb  jnz     short loc_18007F4C3
0x18007f4cd  add     rax, 7
0x18007f4d1  add     rax, rcx
0x18007f4d4  cmp     rax, 104h
0x18007f4da  ja      loc_18007F8F3
0x18007f4e0  mov     edi, 105h
0x18007f4e5  lea     rcx, [rbp+0A30h+Destination]; Destination
0x18007f4ec  mov     edx, edi; SizeInWords
0x18007f4ee  mov     r8, r12; Source
0x18007f4f1  call    cs:__imp_wcscpy_s
0x18007f4f8  nop     dword ptr [rax+rax+00h]
0x18007f4fd  lea     r8, aExport; "Export"
0x18007f504  mov     edx, edi; SizeInWords
0x18007f506  lea     rcx, [rbp+0A30h+Destination]; Destination
0x18007f50d  call    cs:__imp_wcscat_s
0x18007f514  nop     dword ptr [rax+rax+00h]
0x18007f519  lea     r8, Delimiter; "\\"
0x18007f520  mov     edx, edi; SizeInWords
0x18007f522  lea     rcx, [rbp+0A30h+Destination]; Destination
0x18007f529  call    cs:__imp_wcscat_s
0x18007f530  nop     dword ptr [rax+rax+00h]
0x18007f535  mov     r8, rbx; Source
0x18007f538  lea     rcx, [rbp+0A30h+Destination]; Destination
0x18007f53f  mov     edx, edi; SizeInWords
0x18007f541  call    cs:__imp_wcscat_s
0x18007f548  nop     dword ptr [rax+rax+00h]
0x18007f54d  lea     rdx, [rbp+0A30h+var_8B0]
0x18007f554  lea     rcx, [rbp+0A30h+Destination]; lpFileName
0x18007f55b  call    FileExists
0x18007f560  test    eax, eax
0x18007f562  jz      loc_18007F8F3
0x18007f568  lea     r14, [r13+818h]
0x18007f56f  mov     rcx, r14; lpFileName
0x18007f572  lea     rdx, [rsp+0B30h+var_B00]
0x18007f577  call    FileExists
0x18007f57c  test    eax, eax
0x18007f57e  jnz     loc_18007F649
0x18007f584  mov     rcx, cs:WPP_GLOBAL_Control
0x18007f58b  lea     rdi, WPP_GLOBAL_Control
0x18007f592  lea     rsi, WPP_4505e5d286323dbdfbdc99a364b6b69a_Traceguids
0x18007f599  mov     bl, 40h ; '@'
0x18007f59b  cmp     rcx, rdi
0x18007f59e  jz      short loc_18007F5B4
0x18007f5a0  test    [rcx+1Ch], bl
0x18007f5a3  jz      short loc_18007F5B4
0x18007f5a5  mov     rcx, [rcx+10h]
0x18007f5a9  lea     edx, [rax+0Bh]
0x18007f5ac  mov     r8, rsi
0x18007f5af  call    WPP_SF_
0x18007f5b4  mov     r8d, 9; dwFlags
0x18007f5ba  lea     rcx, [rbp+0A30h+Destination]; lpExistingFileName
0x18007f5c1  mov     rdx, r14; lpNewFileName
0x18007f5c4  call    cs:__imp_MoveFileExW
0x18007f5cb  nop     dword ptr [rax+rax+00h]
0x18007f5d0  test    eax, eax
0x18007f5d2  jnz     short loc_18007F62B
0x18007f5d4  mov     rax, cs:WPP_GLOBAL_Control
0x18007f5db  cmp     rax, rdi
0x18007f5de  jz      short loc_18007F60C
0x18007f5e0  test    [rax+1Ch], bl
0x18007f5e3  jz      short loc_18007F60C
0x18007f5e5  call    cs:__imp_GetLastError
0x18007f5ec  nop     dword ptr [rax+rax+00h]
0x18007f5f1  mov     rcx, cs:WPP_GLOBAL_Control
0x18007f5f8  mov     edx, 0Ch
0x18007f5fd  mov     r9d, eax
0x18007f600  mov     r8, rsi
0x18007f603  mov     rcx, [rcx+10h]
0x18007f607  call    WPP_SF_D
0x18007f60c  call    cs:__imp_GetLastError
0x18007f613  nop     dword ptr [rax+rax+00h]
0x18007f618  lea     r8, [rbp+0A30h+Destination]
0x18007f61f  lea     rdx, TLS_W_DBRESTORE_MOVEFILE
0x18007f626  jmp     loc_18007F8E7
0x18007f62b  lea     rdx, TLS_I_USE_DBRESTOREFILE; struct _EVENT_DESCRIPTOR *
0x18007f632  xor     r9d, r9d; struct _EVENT_DATA_DESCRIPTOR *
0x18007f635  lea     rcx, ?s_instance@CrimsonHelper@@0V1@A; this
0x18007f63c  xor     r8d, r8d; unsigned int
0x18007f63f  call    ?RaiseEventInternal@CrimsonHelper@@AEAAKAEBU_EVENT_DESCRIPTOR@@KQEAU_EVENT_DATA_DESCRIPTOR@@@Z; CrimsonHelper::RaiseEventInternal(_EVENT_DESCRIPTOR const &,ulong,_EVENT_DATA_DESCRIPTOR * const)
0x18007f644  jmp     loc_18007F8F3
0x18007f649  lea     rdx, [rsp+0B30h+FileTime2]; lpFileTime2
0x18007f64e  lea     rcx, [rbp+0A30h+FileTime1]; lpFileTime1
0x18007f655  call    cs:__imp_CompareFileTime
0x18007f65c  nop     dword ptr [rax+rax+00h]
0x18007f661  test    eax, eax
0x18007f663  jg      short loc_18007F6A1
0x18007f665  mov     rcx, cs:WPP_GLOBAL_Control
0x18007f66c  lea     rdi, WPP_GLOBAL_Control
0x18007f673  cmp     rcx, rdi
0x18007f676  jz      loc_18007F8F3
0x18007f67c  mov     bl, 40h ; '@'
0x18007f67e  test    [rcx+1Ch], bl
0x18007f681  jz      loc_18007F8F3
0x18007f687  mov     rcx, [rcx+10h]
0x18007f68b  lea     r8, WPP_4505e5d286323dbdfbdc99a364b6b69a_Traceguids
0x18007f692  mov     edx, 0Dh
0x18007f697  call    WPP_SF_
0x18007f69c  jmp     loc_18007F8F3
0x18007f6a1  lea     rdx, [rbp+0A30h+NewFileName]; unsigned __int16 *
0x18007f6a8  mov     rcx, r12; unsigned __int16 *
0x18007f6ab  call    ?TlsGenerateLSDBBackupFileName@@YAHPEBGPEAG@Z; TlsGenerateLSDBBackupFileName(ushort const *,ushort *)
0x18007f6b0  lea     rdi, WPP_GLOBAL_Control
0x18007f6b7  mov     bl, 40h ; '@'
0x18007f6b9  lea     rsi, WPP_4505e5d286323dbdfbdc99a364b6b69a_Traceguids
0x18007f6c0  test    eax, eax
0x18007f6c2  jz      loc_18007F8A5
0x18007f6c8  mov     rcx, cs:WPP_GLOBAL_Control
0x18007f6cf  cmp     rcx, rdi
0x18007f6d2  jz      short loc_18007F6F1
0x18007f6d4  test    [rcx+1Ch], bl
0x18007f6d7  jz      short loc_18007F6F1
0x18007f6d9  mov     rcx, [rcx+10h]
0x18007f6dd  lea     r9, [rbp+0A30h+NewFileName]
0x18007f6e4  mov     edx, 0Eh
0x18007f6e9  mov     r8, rsi
0x18007f6ec  call    WPP_SF_S
0x18007f6f1  mov     r15d, 9
0x18007f6f7  lea     rdx, [rbp+0A30h+NewFileName]; lpNewFileName
0x18007f6fe  mov     r8d, r15d; dwFlags
0x18007f701  mov     rcx, r14; lpExistingFileName
0x18007f704  call    cs:__imp_MoveFileExW
0x18007f70b  nop     dword ptr [rax+rax+00h]
0x18007f710  test    eax, eax
0x18007f712  jz      loc_18007F8A5
0x18007f718  mov     r8d, r15d; dwFlags
0x18007f71b  lea     rcx, [rbp+0A30h+Destination]; lpExistingFileName
0x18007f722  mov     rdx, r14; lpNewFileName
0x18007f725  call    cs:__imp_MoveFileExW
0x18007f72c  nop     dword ptr [rax+rax+00h]
0x18007f731  cmp     eax, 1
0x18007f734  jnz     short loc_18007F766
0x18007f736  xor     r8d, r8d; int
0x18007f739  mov     rcx, r13; this
0x18007f73c  call    ?StartRdlsDB@CRdlsDBManager@@AEAAKKH@Z; CRdlsDBManager::StartRdlsDB(ulong,int)
0x18007f741  test    eax, eax
0x18007f743  jnz     short loc_18007F766
0x18007f745  lea     r8, [rbp+0A30h+NewFileName]
0x18007f74c  lea     rdx, TLS_I_OPENRESTOREDBFILE
0x18007f753  lea     rcx, ?s_instance@CrimsonHelper@@0V1@A; CrimsonHelper CrimsonHelper::s_instance
0x18007f75a  call    ??$RaiseEvent@PEAG@CrimsonHelper@@QEAAKAEBU_EVENT_DESCRIPTOR@@PEAG@Z; CrimsonHelper::RaiseEvent<ushort *>(_EVENT_DESCRIPTOR const &,ushort *)
0x18007f75f  xor     eax, eax
0x18007f761  jmp     loc_18007F901
0x18007f766  lea     rdx, [rbp+0A30h+var_240]; unsigned __int16 *
0x18007f76d  mov     rcx, r12; unsigned __int16 *
0x18007f770  call    ?TlsGenerateLSDBBackupFileName@@YAHPEBGPEAG@Z; TlsGenerateLSDBBackupFileName(ushort const *,ushort *)
0x18007f775  test    eax, eax
0x18007f777  jz      short loc_18007F7DE
0x18007f779  mov     rcx, cs:WPP_GLOBAL_Control
0x18007f780  cmp     rcx, rdi
0x18007f783  jz      short loc_18007F7A2
0x18007f785  test    [rcx+1Ch], bl
0x18007f788  jz      short loc_18007F7A2
0x18007f78a  mov     rcx, [rcx+10h]
0x18007f78e  lea     r9, [rbp+0A30h+var_240]
0x18007f795  mov     edx, 10h
0x18007f79a  mov     r8, rsi
0x18007f79d  call    WPP_SF_S
0x18007f7a2  mov     r8d, r15d; dwFlags
0x18007f7a5  lea     rdx, [rbp+0A30h+var_240]; lpNewFileName
0x18007f7ac  mov     rcx, r14; lpExistingFileName
0x18007f7af  call    cs:__imp_MoveFileExW
0x18007f7b6  nop     dword ptr [rax+rax+00h]
0x18007f7bb  test    eax, eax
0x18007f7bd  jz      short loc_18007F7DE
0x18007f7bf  mov     rcx, cs:WPP_GLOBAL_Control
0x18007f7c6  cmp     rcx, rdi
0x18007f7c9  jz      short loc_18007F840
0x18007f7cb  test    [rcx+1Ch], bl
0x18007f7ce  jz      short loc_18007F819
0x18007f7d0  mov     edx, 12h
0x18007f7d5  lea     r9, [rbp+0A30h+var_240]
0x18007f7dc  jmp     short loc_18007F806
0x18007f7de  mov     rcx, r14; lpFileName
0x18007f7e1  call    cs:__imp_DeleteFileW
0x18007f7e8  nop     dword ptr [rax+rax+00h]
0x18007f7ed  mov     rcx, cs:WPP_GLOBAL_Control
0x18007f7f4  cmp     rcx, rdi
0x18007f7f7  jz      short loc_18007F840
0x18007f7f9  test    [rcx+1Ch], bl
0x18007f7fc  jz      short loc_18007F819
0x18007f7fe  mov     edx, 11h
0x18007f803  mov     r9, r14
0x18007f806  mov     rcx, [rcx+10h]
0x18007f80a  mov     r8, rsi
0x18007f80d  call    WPP_SF_S
0x18007f812  mov     rcx, cs:WPP_GLOBAL_Control
0x18007f819  cmp     rcx, rdi
0x18007f81c  jz      short loc_18007F840
0x18007f81e  test    [rcx+1Ch], bl
0x18007f821  jz      short loc_18007F840
0x18007f823  mov     rcx, [rcx+10h]
0x18007f827  lea     r9, [rbp+0A30h+NewFileName]
0x18007f82e  mov     edx, 13h
0x18007f833  mov     [rsp+0B30h+var_B10], r14
0x18007f838  mov     r8, rsi
0x18007f83b  call    WPP_SF_SS
0x18007f840  mov     r8d, r15d; dwFlags
0x18007f843  lea     rcx, [rbp+0A30h+NewFileName]; lpExistingFileName
0x18007f84a  mov     rdx, r14; lpNewFileName
0x18007f84d  call    cs:__imp_MoveFileExW
0x18007f854  nop     dword ptr [rax+rax+00h]
0x18007f859  test    eax, eax
0x18007f85b  jnz     loc_18007F8F3
0x18007f861  mov     rax, cs:WPP_GLOBAL_Control
0x18007f868  cmp     rax, rdi
0x18007f86b  jz      short loc_18007F899
0x18007f86d  test    [rax+1Ch], bl
0x18007f870  jz      short loc_18007F899
0x18007f872  call    cs:__imp_GetLastError
0x18007f879  nop     dword ptr [rax+rax+00h]
0x18007f87e  mov     rcx, cs:WPP_GLOBAL_Control
0x18007f885  mov     edx, 14h
0x18007f88a  mov     r9d, eax
0x18007f88d  mov     r8, rsi
0x18007f890  mov     rcx, [rcx+10h]
0x18007f894  call    WPP_SF_D
0x18007f899  lea     rdx, TLS_E_EXISTINGDBFILE_BKUPRESTORE_FAIL
0x18007f8a0  jmp     loc_18007F632
0x18007f8a5  mov     rax, cs:WPP_GLOBAL_Control
0x18007f8ac  cmp     rax, rdi
0x18007f8af  jz      short loc_18007F8DD
0x18007f8b1  test    [rax+1Ch], bl
0x18007f8b4  jz      short loc_18007F8DD
0x18007f8b6  call    cs:__imp_GetLastError
0x18007f8bd  nop     dword ptr [rax+rax+00h]
0x18007f8c2  mov     rcx, cs:WPP_GLOBAL_Control
0x18007f8c9  mov     edx, 0Fh
0x18007f8ce  mov     r9d, eax
0x18007f8d1  mov     r8, rsi
0x18007f8d4  mov     rcx, [rcx+10h]
0x18007f8d8  call    WPP_SF_D
0x18007f8dd  mov     r8, r14
0x18007f8e0  lea     rdx, TLS_W_DBRESTORE_SAVEEXISTING
0x18007f8e7  lea     rcx, ?s_instance@CrimsonHelper@@0V1@A; CrimsonHelper CrimsonHelper::s_instance
0x18007f8ee  call    ??$RaiseEvent@PEAG@CrimsonHelper@@QEAAKAEBU_EVENT_DESCRIPTOR@@PEAG@Z; CrimsonHelper::RaiseEvent<ushort *>(_EVENT_DESCRIPTOR const &,ushort *)
0x18007f8f3  mov     r8d, 1; int
0x18007f8f9  mov     rcx, r13; this
0x18007f8fc  call    ?StartRdlsDB@CRdlsDBManager@@AEAAKKH@Z; CRdlsDBManager::StartRdlsDB(ulong,int)
0x18007f901  mov     rcx, [rbp+0A30h+var_30]
0x18007f908  xor     rcx, rsp; StackCookie
0x18007f90b  call    __security_check_cookie
0x18007f910  lea     r11, [rsp+0B30h+var_20]
0x18007f918  mov     rbx, [r11+30h]
0x18007f91c  mov     rsi, [r11+38h]
0x18007f920  mov     rdi, [r11+40h]
0x18007f924  mov     rsp, r11
0x18007f927  pop     r15
0x18007f929  pop     r14
0x18007f92b  pop     r13
0x18007f92d  pop     r12
0x18007f92f  pop     rbp
0x18007f930  retn
```
