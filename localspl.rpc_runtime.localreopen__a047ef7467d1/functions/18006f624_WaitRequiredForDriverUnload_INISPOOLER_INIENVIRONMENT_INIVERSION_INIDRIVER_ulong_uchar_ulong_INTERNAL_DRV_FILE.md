# WaitRequiredForDriverUnload(_INISPOOLER *,_INIENVIRONMENT *,_INIVERSION *,_INIDRIVER *,ulong,uchar *,ulong,_INTERNAL_DRV_FILE *,ulong,ulong,int,int *,EMoveFileOptions)

- ea: `0x18006f624`
- end: `0x18006fb8b`
- name: `?WaitRequiredForDriverUnload@@YAHPEAU_INISPOOLER@@PEAU_INIENVIRONMENT@@PEAU_INIVERSION@@PEAU_INIDRIVER@@KPEAEKPEAU_INTERNAL_DRV_FILE@@KKHPEAHW4EMoveFileOptions@@@Z`
- size: `1383`
- prototype: `_BOOL8 __fastcall(__int64, struct _INIENVIRONMENT *, struct _INIVERSION *, __int64, unsigned int, unsigned __int8 *, unsigned int, struct _INTERNAL_DRV_FILE *, unsigned int, __int64, int, int *, int)`
- caller_count: `2`
- callee_count: `15`
- tags: `file_ops, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180028360`
- `0x1800705a0`

## callees

- `0x18000bb60`
- `0x18000d944`
- `0x18000edc4`
- `0x180030a0c`
- `0x180033674`
- `0x180034e78`
- `0x18003d0a4`
- `0x180046650`
- `0x180047330`
- `0x18006ab60`
- `0x18006d030`
- `0x18006f624`
- `0x18007348c`
- `0x18009d704`
- `0x18009d81c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006fad3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006fb30`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006fb5d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006fad3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006fb30`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006fb5d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006f88b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006f92e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006f88b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006f92e`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18006f87c`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18006f91f`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18006f87c`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18006f91f`
- `SPOOLSS!RevertToPrinterSelf` at `0x18006f6ba`
- `SPOOLSS!RevertToPrinterSelf` at `0x18006f6ba`
- `SPOOLSS!ImpersonatePrinterClient` at `0x18006f7e7`
- `SPOOLSS!ImpersonatePrinterClient` at `0x18006f7e7`

## string_xrefs

- `0x18006fb39`: `MoveNewDriverRelatedFiles`
- `0x18006fadc`: `CompleteDriverUpgrade`

## pseudocode

```c
_BOOL8 __fastcall WaitRequiredForDriverUnload(
        __int64 a1,
        struct _INIENVIRONMENT *a2,
        struct _INIVERSION *a3,
        __int64 a4,
        unsigned int a5,
        unsigned __int8 *a6,
        unsigned int a7,
        struct _INTERNAL_DRV_FILE *a8,
        unsigned int a9,
        __int64 a10,
        int a11,
        int *a12,
        int a13)
{
  HANDLE v16; // rax
  __int64 v17; // r8
  int v18; // edi
  HANDLE FileW; // rax
  unsigned __int16 *v21; // r15
  unsigned int v22; // edi
  HANDLE v23; // rax
  unsigned __int16 *v24; // r8
  _BYTE *v25; // rcx
  struct _INIENVIRONMENT *v26; // r15
  int v27; // eax
  __int64 v28; // rcx
  DWORD v29; // eax
  struct _INIENVIRONMENT *v30; // rbx
  DWORD v31; // eax
  DWORD LastError; // eax
  unsigned int v33; // [rsp+48h] [rbp-B8h]
  int v34; // [rsp+80h] [rbp-80h] BYREF
  int v35; // [rsp+84h] [rbp-7Ch] BYREF
  struct _INIENVIRONMENT *MustForceUpdateDriverList; // [rsp+88h] [rbp-78h] BYREF
  struct _INISPOOLER *v37; // [rsp+90h] [rbp-70h]
  unsigned __int8 *v38; // [rsp+98h] [rbp-68h]
  HANDLE hToken; // [rsp+A0h] [rbp-60h]
  unsigned __int16 v40; // [rsp+A8h] [rbp-58h] BYREF
  _BYTE v41[528]; // [rsp+B0h] [rbp-50h] BYREF
  WCHAR PathName[264]; // [rsp+2C0h] [rbp+1C0h] BYREF
  WCHAR FileName[264]; // [rsp+4D0h] [rbp+3D0h] BYREF
  _BYTE v44[528]; // [rsp+6E0h] [rbp+5E0h] BYREF
  _BYTE v45[528]; // [rsp+8F0h] [rbp+7F0h] BYREF
  _BYTE v46[528]; // [rsp+B00h] [rbp+A00h] BYREF
  unsigned __int16 v47[264]; // [rsp+D10h] [rbp+C10h] BYREF

  MustForceUpdateDriverList = a2;
  v37 = (struct _INISPOOLER *)a1;
  v38 = a6;
  v35 = 0;
  v34 = 0;
  memset_0(v46, 0, 0x208u);
  memset_0(v45, 0, 0x208u);
  v16 = RevertToPrinterSelf();
  *a12 = 0;
  v17 = *(_QWORD *)(a1 + 32);
  hToken = v16;
  if ( (unsigned int)StrNCatBuff(v41, 260, v17, L"\\drivers\\") )
    goto LABEL_8;
  if ( (unsigned int)StrNCatBuff(PathName, 260, v41, L"\\Old") )
    goto LABEL_8;
  if ( (unsigned int)StrNCatBuff(v44, 260, v41, L"\\New") )
    goto LABEL_8;
  if ( a9 )
  {
    FindFileName(*(_QWORD *)a8);
    if ( (unsigned int)StrNCatBuff(v47, 260, v41, L"\\") )
      goto LABEL_8;
  }
  if ( a9 <= 1 )
  {
    if ( !a9 )
      goto LABEL_14;
  }
  else
  {
    FindFileName(*((_QWORD *)a8 + 4));
    if ( (unsigned int)StrNCatBuff(v45, 260, v41, L"\\") )
    {
LABEL_8:
      v18 = 1;
      goto LABEL_9;
    }
  }
  FindFileName(*(_QWORD *)a8);
  if ( (unsigned int)StrNCatBuff(FileName, 260, v44, L"\\") )
    goto LABEL_8;
LABEL_14:
  FileW = CreateFileW(FileName, 0x80000000, 0, 0, 3u, 0x80u, 0);
  if ( FileW == (HANDLE)-1LL )
  {
    v22 = 0;
    v21 = 0;
  }
  else
  {
    CloseHandle(FileW);
    v21 = v47;
    if ( a4 )
      v22 = *(_DWORD *)(a4 + 232);
    else
      v22 = 2;
  }
  if ( a9 > 1 )
  {
    FindFileName(*((_QWORD *)a8 + 4));
    if ( (unsigned int)StrNCatBuff(FileName, 260, v44, L"\\") )
      goto LABEL_8;
  }
  v23 = CreateFileW(FileName, 0x80000000, 0, 0, 3u, 0x80u, 0);
  if ( v23 == (HANDLE)-1LL )
  {
    v24 = 0;
  }
  else
  {
    CloseHandle(v23);
    v24 = (unsigned __int16 *)v45;
  }
  v18 = FilesUnloaded(MustForceUpdateDriverList, v21, v24, v22);
  if ( !v18 )
  {
    if ( a4 )
      a4 = *(_QWORD *)(a4 + 24);
    LastError = GetLastError();
    SplLogGenericEvent(&LOCAL_ADDDRV_FAILED, L"FilesUnloaded", LastError, (const unsigned __int16 *)a4);
    *a12 = a11;
    goto LABEL_9;
  }
  if ( !(unsigned int)DirectoryExists(PathName) && !(unsigned int)CreateDirectoryWithoutImpersonatingUser(PathName) )
    goto LABEL_8;
  if ( a13 )
  {
    if ( (unsigned int)(a13 - 1) > 1
      || !*(_DWORD *)(a4 + 240)
      || StringCchPrintfW(&v40, 4u, L"%d") < 0
      || (unsigned int)StrNCatBuff(v46, 260, v41, L"\\") )
    {
      goto LABEL_44;
    }
    v25 = v46;
  }
  else
  {
    v25 = v44;
  }
  if ( !(unsigned int)MoveNewDriverRelatedFiles(
                        (_DWORD)v25,
                        (unsigned int)v41,
                        (unsigned int)PathName,
                        (_DWORD)a8,
                        a9,
                        (__int64)&v35,
                        (__int64)&v34,
                        0) )
  {
LABEL_44:
    if ( a4 )
      a4 = *(_QWORD *)(a4 + 24);
    v31 = GetLastError();
    SplLogGenericEvent(&LOCAL_ADDDRV_FAILED, L"MoveNewDriverRelatedFiles", v31, (const unsigned __int16 *)a4);
    goto LABEL_9;
  }
  v26 = MustForceUpdateDriverList;
  MustForceUpdateDriverList = (struct _INIENVIRONMENT *)BuildTheMustForceUpdateDriverList(
                                                          (_DWORD)v37,
                                                          (_DWORD)MustForceUpdateDriverList,
                                                          (_DWORD)a3,
                                                          (_DWORD)a8,
                                                          a9);
  v27 = CompleteDriverUpgrade(
          v37,
          v26,
          a3,
          (struct _INIDRIVER *)a4,
          a5,
          v38,
          a7,
          a8,
          a9,
          v33,
          0,
          a11,
          v35,
          v34,
          &MustForceUpdateDriverList);
  *a12 = v27;
  if ( !v27 )
  {
    if ( a4 )
      a4 = *(_QWORD *)(a4 + 24);
    v29 = GetLastError();
    SplLogGenericEvent(&LOCAL_ADDDRV_FAILED, L"CompleteDriverUpgrade", v29, (const unsigned __int16 *)a4);
  }
  v30 = MustForceUpdateDriverList;
  if ( *a12 )
  {
    if ( !MustForceUpdateDriverList )
      goto LABEL_9;
    ForceDriverUpdateList(v28, a3, MustForceUpdateDriverList);
  }
  if ( v30 )
    FreeTheMustForceUpdateDriverList(v30);
LABEL_9:
  if ( hToken )
    ImpersonatePrinterClient(hToken);
  return v18 == 0;
}

```

## disassembly

```asm
0x18006f624  push    rbp
0x18006f626  push    rbx
0x18006f627  push    rsi
0x18006f628  push    rdi
0x18006f629  push    r12
0x18006f62b  push    r13
0x18006f62d  push    r14
0x18006f62f  push    r15
0x18006f631  lea     rbp, [rsp-0E38h]
0x18006f639  sub     rsp, 0F38h
0x18006f640  mov     rax, cs:__security_cookie
0x18006f647  xor     rax, rsp
0x18006f64a  mov     [rbp+0E70h+var_50], rax
0x18006f651  mov     rax, [rbp+0E70h+arg_28]
0x18006f658  mov     r13, r8
0x18006f65b  mov     r14, [rbp+0E70h+arg_38]
0x18006f662  mov     rdi, rdx
0x18006f665  mov     esi, [rbp+0E70h+arg_40]
0x18006f66b  mov     r15, rcx
0x18006f66e  mov     r12, [rbp+0E70h+arg_58]
0x18006f675  mov     r8d, 208h; Size
0x18006f67b  mov     [rbp+0E70h+var_EE8], rdx
0x18006f67f  mov     rbx, r9
0x18006f682  mov     [rbp+0E70h+var_EE0], rcx
0x18006f686  xor     edx, edx; Val
0x18006f688  lea     rcx, [rbp+0E70h+var_470]; void *
0x18006f68f  mov     [rbp+0E70h+var_ED8], rax
0x18006f693  mov     [rbp+0E70h+var_EEC], 0
0x18006f69a  mov     [rbp+0E70h+var_EF0], 0
0x18006f6a1  call    memset_0
0x18006f6a6  xor     edx, edx; Val
0x18006f6a8  lea     rcx, [rbp+0E70h+var_680]; void *
0x18006f6af  mov     r8d, 208h; Size
0x18006f6b5  call    memset_0
0x18006f6ba  call    cs:__imp_RevertToPrinterSelf
0x18006f6c0  mov     dword ptr [r12], 0
0x18006f6c8  lea     r9, aDrivers; "\\drivers\\"
0x18006f6cf  mov     rcx, [r13+18h]
0x18006f6d3  mov     r8, [r15+20h]
0x18006f6d7  mov     [rsp+0F70h+var_F38], 0
0x18006f6e0  mov     [rsp+0F70h+hTemplateFile], rcx
0x18006f6e5  mov     rcx, [rdi+28h]
0x18006f6e9  mov     edi, 104h
0x18006f6ee  mov     [rbp+0E70h+hToken], rax
0x18006f6f2  mov     edx, edi
0x18006f6f4  lea     rax, SubBlock; "\\"
0x18006f6fb  mov     qword ptr [rsp+0F70h+dwFlagsAndAttributes], rax
0x18006f700  mov     qword ptr [rsp+0F70h+dwCreationDisposition], rcx
0x18006f705  lea     rcx, [rbp+0E70h+var_EC0]
0x18006f709  call    StrNCatBuff
0x18006f70e  test    eax, eax
0x18006f710  jnz     loc_18006F7D6
0x18006f716  lea     r9, aOld; "\\Old"
0x18006f71d  mov     qword ptr [rsp+0F70h+dwCreationDisposition], 0
0x18006f726  lea     r8, [rbp+0E70h+var_EC0]
0x18006f72a  mov     edx, edi
0x18006f72c  lea     rcx, [rbp+0E70h+PathName]
0x18006f733  call    StrNCatBuff
0x18006f738  test    eax, eax
0x18006f73a  jnz     loc_18006F7D6
0x18006f740  lea     r9, aNew; "\\New"
0x18006f747  mov     qword ptr [rsp+0F70h+dwCreationDisposition], 0
0x18006f750  lea     r8, [rbp+0E70h+var_EC0]
0x18006f754  mov     edx, edi
0x18006f756  lea     rcx, [rbp+0E70h+var_890]
0x18006f75d  call    StrNCatBuff
0x18006f762  test    eax, eax
0x18006f764  jnz     short loc_18006F7D6
0x18006f766  test    esi, esi
0x18006f768  jz      short loc_18006F79D
0x18006f76a  mov     rcx, [r14]
0x18006f76d  call    FindFileName
0x18006f772  lea     r9, SubBlock; "\\"
0x18006f779  mov     qword ptr [rsp+0F70h+dwFlagsAndAttributes], 0
0x18006f782  lea     r8, [rbp+0E70h+var_EC0]
0x18006f786  mov     qword ptr [rsp+0F70h+dwCreationDisposition], rax
0x18006f78b  mov     edx, edi
0x18006f78d  lea     rcx, [rbp+0E70h+var_260]
0x18006f794  call    StrNCatBuff
0x18006f799  test    eax, eax
0x18006f79b  jnz     short loc_18006F7D6
0x18006f79d  cmp     esi, 1
0x18006f7a0  jbe     short loc_18006F817
0x18006f7a2  mov     rcx, [r14+20h]
0x18006f7a6  call    FindFileName
0x18006f7ab  lea     r9, SubBlock; "\\"
0x18006f7b2  mov     qword ptr [rsp+0F70h+dwFlagsAndAttributes], 0
0x18006f7bb  lea     r8, [rbp+0E70h+var_EC0]
0x18006f7bf  mov     qword ptr [rsp+0F70h+dwCreationDisposition], rax
0x18006f7c4  mov     edx, edi
0x18006f7c6  lea     rcx, [rbp+0E70h+var_680]
0x18006f7cd  call    StrNCatBuff
0x18006f7d2  test    eax, eax
0x18006f7d4  jz      short loc_18006F81B
0x18006f7d6  mov     edi, 1
0x18006f7db  mov     rax, [rbp+0E70h+hToken]
0x18006f7df  test    rax, rax
0x18006f7e2  jz      short loc_18006F7ED
0x18006f7e4  mov     rcx, rax; hToken
0x18006f7e7  call    cs:__imp_ImpersonatePrinterClient
0x18006f7ed  xor     eax, eax
0x18006f7ef  test    edi, edi
0x18006f7f1  setz    al
0x18006f7f4  mov     rcx, [rbp+0E70h+var_50]
0x18006f7fb  xor     rcx, rsp; StackCookie
0x18006f7fe  call    __security_check_cookie
0x18006f803  add     rsp, 0F38h
0x18006f80a  pop     r15
0x18006f80c  pop     r14
0x18006f80e  pop     r13
0x18006f810  pop     r12
0x18006f812  pop     rdi
0x18006f813  pop     rsi
0x18006f814  pop     rbx
0x18006f815  pop     rbp
0x18006f816  retn
0x18006f817  test    esi, esi
0x18006f819  jz      short loc_18006F851
0x18006f81b  mov     rcx, [r14]
0x18006f81e  call    FindFileName
0x18006f823  lea     r9, SubBlock; "\\"
0x18006f82a  mov     qword ptr [rsp+0F70h+dwFlagsAndAttributes], 0
0x18006f833  lea     r8, [rbp+0E70h+var_890]
0x18006f83a  mov     qword ptr [rsp+0F70h+dwCreationDisposition], rax
0x18006f83f  mov     edx, edi
0x18006f841  lea     rcx, [rbp+0E70h+FileName]
0x18006f848  call    StrNCatBuff
0x18006f84d  test    eax, eax
0x18006f84f  jnz     short loc_18006F7D6
0x18006f851  mov     [rsp+0F70h+hTemplateFile], 0; hTemplateFile
0x18006f85a  lea     rcx, [rbp+0E70h+FileName]; lpFileName
0x18006f861  mov     [rsp+0F70h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18006f869  xor     r9d, r9d; lpSecurityAttributes
0x18006f86c  xor     r8d, r8d; dwShareMode
0x18006f86f  mov     [rsp+0F70h+dwCreationDisposition], 3; dwCreationDisposition
0x18006f877  mov     edx, 80000000h; dwDesiredAccess
0x18006f87c  call    cs:__imp_CreateFileW
0x18006f882  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18006f886  jz      short loc_18006F8AC
0x18006f888  mov     rcx, rax; hObject
0x18006f88b  call    cs:__imp_CloseHandle
0x18006f891  lea     r15, [rbp+0E70h+var_260]
0x18006f898  test    rbx, rbx
0x18006f89b  jz      short loc_18006F8A5
0x18006f89d  mov     edi, [rbx+0E8h]
0x18006f8a3  jmp     short loc_18006F8B1
0x18006f8a5  mov     edi, 2
0x18006f8aa  jmp     short loc_18006F8B1
0x18006f8ac  xor     edi, edi
0x18006f8ae  xor     r15d, r15d
0x18006f8b1  cmp     esi, 1
0x18006f8b4  jbe     short loc_18006F8F4
0x18006f8b6  mov     rcx, [r14+20h]
0x18006f8ba  call    FindFileName
0x18006f8bf  lea     r9, SubBlock; "\\"
0x18006f8c6  mov     qword ptr [rsp+0F70h+dwFlagsAndAttributes], 0
0x18006f8cf  lea     r8, [rbp+0E70h+var_890]
0x18006f8d6  mov     qword ptr [rsp+0F70h+dwCreationDisposition], rax
0x18006f8db  mov     edx, 104h
0x18006f8e0  lea     rcx, [rbp+0E70h+FileName]
0x18006f8e7  call    StrNCatBuff
0x18006f8ec  test    eax, eax
0x18006f8ee  jnz     loc_18006F7D6
0x18006f8f4  mov     [rsp+0F70h+hTemplateFile], 0; hTemplateFile
0x18006f8fd  lea     rcx, [rbp+0E70h+FileName]; lpFileName
0x18006f904  mov     [rsp+0F70h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18006f90c  xor     r9d, r9d; lpSecurityAttributes
0x18006f90f  xor     r8d, r8d; dwShareMode
0x18006f912  mov     [rsp+0F70h+dwCreationDisposition], 3; dwCreationDisposition
0x18006f91a  mov     edx, 80000000h; dwDesiredAccess
0x18006f91f  call    cs:__imp_CreateFileW
0x18006f925  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18006f929  jz      short loc_18006F93D
0x18006f92b  mov     rcx, rax; hObject
0x18006f92e  call    cs:__imp_CloseHandle
0x18006f934  lea     r8, [rbp+0E70h+var_680]
0x18006f93b  jmp     short loc_18006F940
0x18006f93d  xor     r8d, r8d; unsigned __int16 *
0x18006f940  mov     rcx, [rbp+0E70h+var_EE8]; struct _INIENVIRONMENT *
0x18006f944  mov     r9d, edi; unsigned int
0x18006f947  mov     rdx, r15; unsigned __int16 *
0x18006f94a  call    ?FilesUnloaded@@YAHPEAU_INIENVIRONMENT@@PEAG1K@Z; FilesUnloaded(_INIENVIRONMENT *,ushort *,ushort *,ulong)
0x18006f94f  mov     edi, eax
0x18006f951  test    eax, eax
0x18006f953  jz      loc_18006FB54
0x18006f959  lea     rcx, [rbp+0E70h+PathName]
0x18006f960  call    DirectoryExists
0x18006f965  test    eax, eax
0x18006f967  jnz     short loc_18006F97D
0x18006f969  lea     rcx, [rbp+0E70h+PathName]; lpPathName
0x18006f970  call    CreateDirectoryWithoutImpersonatingUser
0x18006f975  test    eax, eax
0x18006f977  jz      loc_18006F7D6
0x18006f97d  mov     ecx, [rbp+0E70h+arg_60]
0x18006f983  test    ecx, ecx
0x18006f985  jz      short loc_18006FA01
0x18006f987  sub     ecx, 1
0x18006f98a  jz      short loc_18006F995
0x18006f98c  cmp     ecx, 1
0x18006f98f  jnz     loc_18006FB27
0x18006f995  mov     r9d, [rbx+0F0h]
0x18006f99c  test    r9d, r9d
0x18006f99f  jz      loc_18006FB27
0x18006f9a5  lea     r8, aD; "%d"
0x18006f9ac  mov     edx, 4; unsigned __int64
0x18006f9b1  lea     rcx, [rbp+0E70h+var_EC8]; unsigned __int16 *
0x18006f9b5  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18006f9ba  test    eax, eax
0x18006f9bc  js      loc_18006FB27
0x18006f9c2  lea     rax, [rbp+0E70h+var_EC8]
0x18006f9c6  mov     qword ptr [rsp+0F70h+dwFlagsAndAttributes], 0
0x18006f9cf  lea     r9, SubBlock; "\\"
0x18006f9d6  mov     qword ptr [rsp+0F70h+dwCreationDisposition], rax
0x18006f9db  lea     r8, [rbp+0E70h+var_EC0]
0x18006f9df  mov     edx, 104h
0x18006f9e4  lea     rcx, [rbp+0E70h+var_470]
0x18006f9eb  call    StrNCatBuff
0x18006f9f0  test    eax, eax
0x18006f9f2  jnz     loc_18006FB27
0x18006f9f8  lea     rcx, [rbp+0E70h+var_470]
0x18006f9ff  jmp     short loc_18006FA08
0x18006fa01  lea     rcx, [rbp+0E70h+var_890]
0x18006fa08  lea     r11, [rbp+0E70h+var_EF0]
0x18006fa0c  mov     eax, esi
0x18006fa0e  lea     r10, [rbp+0E70h+var_EEC]
0x18006fa12  xor     r15d, r15d
0x18006fa15  mov     dword ptr [rsp+0F70h+var_F38], r15d
0x18006fa1a  lea     r8, [rbp+0E70h+PathName]
0x18006fa21  mov     [rsp+0F70h+hTemplateFile], r11
0x18006fa26  lea     rdx, [rbp+0E70h+var_EC0]
0x18006fa2a  mov     qword ptr [rsp+0F70h+dwFlagsAndAttributes], r10
0x18006fa2f  mov     r9, r14
0x18006fa32  mov     [rsp+0F70h+dwCreationDisposition], eax
0x18006fa36  call    MoveNewDriverRelatedFiles
0x18006fa3b  test    eax, eax
0x18006fa3d  jz      loc_18006FB27
0x18006fa43  mov     r15, [rbp+0E70h+var_EE8]
0x18006fa47  mov     r9, r14
0x18006fa4a  mov     rcx, [rbp+0E70h+var_EE0]
0x18006fa4e  mov     rdx, r15
0x18006fa51  mov     r8, r13
0x18006fa54  mov     [rsp+0F70h+dwCreationDisposition], esi
0x18006fa58  call    BuildTheMustForceUpdateDriverList
0x18006fa5d  mov     rcx, [rbp+0E70h+var_EE0]; struct _INISPOOLER *
0x18006fa61  mov     r9, rbx; struct _INIDRIVER *
0x18006fa64  mov     [rbp+0E70h+var_EE8], rax
0x18006fa68  mov     r8, r13; struct _INIVERSION *
0x18006fa6b  lea     rax, [rbp+0E70h+var_EE8]
0x18006fa6f  mov     rdx, r15; struct _INIENVIRONMENT *
0x18006fa72  mov     [rsp+0F70h+var_F00], rax; struct _INIDRIVERTOUPDATE **
0x18006fa77  mov     eax, [rbp+0E70h+var_EF0]
0x18006fa7a  mov     [rsp+0F70h+var_F08], eax; int
0x18006fa7e  mov     eax, [rbp+0E70h+var_EEC]
0x18006fa81  mov     [rsp+0F70h+var_F10], eax; int
0x18006fa85  mov     eax, [rbp+0E70h+arg_50]
0x18006fa8b  mov     [rsp+0F70h+var_F18], eax; int
0x18006fa8f  mov     eax, [rbp+0E70h+arg_30]
0x18006fa95  mov     [rsp+0F70h+var_F20], 0; unsigned int
0x18006fa9d  mov     [rsp+0F70h+var_F30], esi; unsigned int
0x18006faa1  mov     [rsp+0F70h+var_F38], r14; struct _INTERNAL_DRV_FILE *
0x18006faa6  mov     dword ptr [rsp+0F70h+hTemplateFile], eax; unsigned int
0x18006faaa  mov     rax, [rbp+0E70h+var_ED8]
0x18006faae  mov     qword ptr [rsp+0F70h+dwFlagsAndAttributes], rax; unsigned __int8 *
0x18006fab3  mov     eax, [rbp+0E70h+arg_20]
0x18006fab9  mov     [rsp+0F70h+dwCreationDisposition], eax; unsigned int
0x18006fabd  call    ?CompleteDriverUpgrade@@YAHPEAU_INISPOOLER@@PEAU_INIENVIRONMENT@@PEAU_INIVERSION@@PEAU_INIDRIVER@@KPEAEKPEAU_INTERNAL_DRV_FILE@@KKKHHHPEAPEAU_INIDRIVERTOUPDATE@@@Z; CompleteDriverUpgrade(_INISPOOLER *,_INIENVIRONMENT *,_INIVERSION *,_INIDRIVER *,ulong,uchar *,ulong,_INTERNAL_DRV_FILE *,ulong,ulong,ulong,int,int,int,_INIDRIVERTOUPDATE * *)
0x18006fac2  mov     [r12], eax
0x18006fac6  test    eax, eax
0x18006fac8  jnz     short loc_18006FAF2
0x18006faca  test    rbx, rbx
0x18006facd  jz      short loc_18006FAD3
0x18006facf  mov     rbx, [rbx+18h]
0x18006fad3  call    cs:__imp_GetLastError
0x18006fad9  mov     r9, rbx; unsigned __int16 *
0x18006fadc  lea     rdx, aCompletedriver; "CompleteDriverUpgrade"
0x18006fae3  mov     r8d, eax; unsigned int
0x18006fae6  lea     rcx, LOCAL_ADDDRV_FAILED; struct _EVENT_DESCRIPTOR *
0x18006faed  call    ?SplLogGenericEvent@@YAXPEBU_EVENT_DESCRIPTOR@@PEBGK1@Z; SplLogGenericEvent(_EVENT_DESCRIPTOR const *,ushort const *,ulong,ushort const *)
0x18006faf2  cmp     dword ptr [r12], 0
0x18006faf7  mov     rbx, [rbp+0E70h+var_EE8]
0x18006fafb  jz      short loc_18006FB11
0x18006fafd  test    rbx, rbx
0x18006fb00  jz      loc_18006F7DB
0x18006fb06  mov     r8, rbx
0x18006fb09  mov     rdx, r13
0x18006fb0c  call    ForceDriverUpdateList
0x18006fb11  test    rbx, rbx
0x18006fb14  jz      loc_18006F7DB
0x18006fb1a  mov     rcx, rbx
0x18006fb1d  call    FreeTheMustForceUpdateDriverList
0x18006fb22  jmp     loc_18006F7DB
0x18006fb27  test    rbx, rbx
0x18006fb2a  jz      short loc_18006FB30
0x18006fb2c  mov     rbx, [rbx+18h]
0x18006fb30  call    cs:__imp_GetLastError
0x18006fb36  mov     r9, rbx; unsigned __int16 *
0x18006fb39  lea     rdx, aMovenewdriverr; "MoveNewDriverRelatedFiles"
0x18006fb40  mov     r8d, eax; unsigned int
0x18006fb43  lea     rcx, LOCAL_ADDDRV_FAILED; struct _EVENT_DESCRIPTOR *
0x18006fb4a  call    ?SplLogGenericEvent@@YAXPEBU_EVENT_DESCRIPTOR@@PEBGK1@Z; SplLogGenericEvent(_EVENT_DESCRIPTOR const *,ushort const *,ulong,ushort const *)
  ... truncated ...
```
