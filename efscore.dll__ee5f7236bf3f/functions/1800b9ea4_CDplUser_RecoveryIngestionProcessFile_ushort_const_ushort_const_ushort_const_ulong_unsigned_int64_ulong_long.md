# CDplUser::RecoveryIngestionProcessFile(ushort const *,ushort const *,ushort const *,ulong,unsigned __int64,ulong *,long *)

- ea: `0x1800b9ea4`
- end: `0x1800ba56e`
- name: `?RecoveryIngestionProcessFile@CDplUser@@AEAAJPEBG00K_KPEAKPEAJ@Z`
- size: `1738`
- prototype: `int(CDplUser *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, unsigned int, unsigned __int64, unsigned int *, int *)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x1800ba574`

## callees

- `0x180001a7c`
- `0x1800021c8`
- `0x180005045`
- `0x1800124d8`
- `0x180063698`
- `0x180063730`
- `0x1800637e8`
- `0x18008914c`
- `0x180097238`
- `0x1800b9364`
- `0x1800b9ea4`
- `0x1800d5af8`
- `0x1800d6064`
- `0x1800dddf0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ba298`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ba371`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ba3bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ba298`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ba371`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ba3bc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ba414`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ba422`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ba414`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ba422`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800ba3b2`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800ba3b2`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800ba285`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800ba285`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x1800ba367`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x1800ba367`

## pseudocode

```c
__int64 __fastcall CDplUser::RecoveryIngestionProcessFile(
        CDplUser *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        char a5,
        unsigned __int64 a6,
        unsigned int *a7,
        int *a8)
{
  const unsigned __int16 *v8; // r12
  int v11; // r13d
  unsigned __int8 *v12; // r15
  int v13; // ecx
  int v14; // ecx
  DWORD v15; // ebx
  int v16; // r8d
  DWORD v17; // r12d
  HANDLE FileW; // rax
  void *v19; // rdi
  signed int LastError; // eax
  unsigned int DirectoryInternal; // edi
  signed int v22; // eax
  signed int v23; // eax
  int v24; // ecx
  int v25; // ecx
  int v26; // r8d
  int v27; // r9d
  int v28; // eax
  char dwCreationDisposition; // [rsp+20h] [rbp-E0h]
  const unsigned __int16 *v31; // [rsp+40h] [rbp-C0h] BYREF
  DWORD nNumberOfBytesToRead; // [rsp+48h] [rbp-B8h] BYREF
  LPVOID lpBuffer; // [rsp+50h] [rbp-B0h] BYREF
  DWORD NumberOfBytesRead; // [rsp+58h] [rbp-A8h] BYREF
  CDplUser *v35; // [rsp+60h] [rbp-A0h]
  WCHAR FileName[264]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR NewFileName[264]; // [rsp+280h] [rbp+180h] BYREF

  v8 = a3;
  v31 = a3;
  v35 = this;
  memset_0(FileName, 0, 0x208u);
  memset_0(NewFileName, 0, 0x208u);
  lpBuffer = 0;
  nNumberOfBytesToRead = 0;
  v11 = 0;
  NumberOfBytesRead = 0;
  v12 = 0;
  fnEfsLogTrace1Strings(v13, (unsigned int)EFS_TRACE_ENTER_EVENT, (unsigned int)&sourceString, 40, 138);
  v14 = 0;
  if ( a7 )
    *a7 = 0;
  if ( a8 )
    *a8 = 0;
  if ( !a2 )
  {
    dwCreationDisposition = -105;
LABEL_7:
    v15 = -2147024809;
    v16 = -2147024809;
LABEL_8:
    fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, v16, 40, dwCreationDisposition);
    goto LABEL_40;
  }
  if ( !v8 )
  {
    dwCreationDisposition = -104;
    goto LABEL_7;
  }
  if ( !a4 )
  {
    dwCreationDisposition = -103;
    goto LABEL_7;
  }
  if ( !a7 )
  {
    dwCreationDisposition = -102;
LABEL_15:
    v15 = -2147467261;
    v16 = -2147467261;
    goto LABEL_8;
  }
  if ( !a8 )
  {
    dwCreationDisposition = -101;
    goto LABEL_15;
  }
  if ( (a5 & 0x10) != 0 && *a4 == 46 && (!a4[1] || a4[1] == 46 && !a4[2]) )
  {
    v15 = 0;
    goto LABEL_39;
  }
  fnEfsLogTrace1Strings(0, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 40, 176);
  v15 = CDplService::StringCchConcat(FileName, 0x104u, a2, L"\\", a4, 0);
  if ( (int)fnEfsLogTrace1String1Dword(
              g_hPublisher,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
              (unsigned int)&sourceString,
              v15,
              40,
              176) < 0 )
    goto LABEL_39;
  fnEfsLogTrace1Strings(v14, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 40, 186);
  v15 = CDplService::StringCchConcat(NewFileName, 0x104u, v31, L"\\", a4, 0);
  if ( (int)fnEfsLogTrace1String1Dword(
              g_hPublisher,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
              (unsigned int)&sourceString,
              v15,
              40,
              186) < 0 )
    goto LABEL_39;
  v11 = 1;
  ++*a7;
  if ( (a5 & 0x10) != 0 )
  {
    v15 = -2147024560;
    fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, -2147024560, 40, 198);
    goto LABEL_39;
  }
  if ( !a6 )
  {
    v15 = -2147024883;
    fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, -2147024883, 40, 207);
    goto LABEL_39;
  }
  if ( a6 > 0x10000 )
  {
    v15 = -2147024673;
    fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, -2147024673, 40, 212);
    goto LABEL_39;
  }
  fnEfsLogTrace1Strings(v14, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 40, 215);
  v15 = ULongLongToULong(a6, &nNumberOfBytesToRead);
  if ( (int)fnEfsLogTrace1String1Dword(
              g_hPublisher,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
              (unsigned int)&sourceString,
              v15,
              40,
              215) < 0 )
    goto LABEL_39;
  fnEfsLogTrace1Strings(v14, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 40, 217);
  v17 = nNumberOfBytesToRead;
  v15 = DplibpMemAllocEx(nNumberOfBytesToRead, 0, 0, &lpBuffer);
  if ( (int)fnEfsLogTrace1String1Dword(
              g_hPublisher,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
              (unsigned int)&sourceString,
              v15,
              40,
              217) < 0 )
  {
LABEL_38:
    v12 = (unsigned __int8 *)lpBuffer;
    goto LABEL_39;
  }
  ++*a7;
  FileW = CreateFileW(FileName, 0x80000000, 1u, 0, 3u, 0, 0);
  v19 = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    v15 = LastError;
    if ( LastError > 0 )
      v15 = (unsigned __int16)LastError | 0x80070000;
    fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, v15, 40, 235);
    goto LABEL_38;
  }
  ++*a7;
  v12 = (unsigned __int8 *)lpBuffer;
  if ( ReadFile(FileW, lpBuffer, v17, &NumberOfBytesRead, 0) )
  {
    if ( v17 == NumberOfBytesRead )
    {
      CloseHandle(v19);
      ++*a7;
      fnEfsLogTrace1Strings(v24, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 40, 5);
      v15 = CDplUser::RecoveryIngestionHelper(v35, v12, v17, 0, a7);
      fnEfsLogTrace1String1Dword(
        g_hPublisher,
        (unsigned int)EFS_TRACE_COMPLETE_EVENT,
        (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
        (unsigned int)&sourceString,
        v15,
        40,
        5);
      goto LABEL_39;
    }
    v15 = -2147024865;
    fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, -2147024865, 40, 251);
  }
  else
  {
    v23 = GetLastError();
    v15 = v23;
    if ( v23 > 0 )
      v15 = (unsigned __int16)v23 | 0x80070000;
    fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, v15, 40, 246);
  }
  CloseHandle(v19);
LABEL_39:
  v8 = v31;
LABEL_40:
  if ( v12 )
    DplibMemFree(v12);
  if ( v11 )
  {
    fnEfsLogTrace1Strings(v14, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 40, 19);
    DirectoryInternal = CDplService::CreateDirectoryInternal(v8);
    if ( (int)fnEfsLogTrace1String1Dword(
                g_hPublisher,
                (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                (unsigned int)&sourceString,
                DirectoryInternal,
                40,
                19) >= 0
      && !MoveFileExW(FileName, NewFileName, 0) )
    {
      v22 = GetLastError();
      DirectoryInternal = v22;
      if ( v22 > 0 )
        DirectoryInternal = (unsigned __int16)v22 | 0x80070000;
    }
    if ( a8 )
      *a8 = DirectoryInternal;
  }
  if ( a7
    && *a7 > 3
    && (unsigned int)dword_180114250 > 5
    && (unsigned __int8)tlgKeywordOn(&dword_180114250, 0x400000000000LL) )
  {
    nNumberOfBytesToRead = v15;
    if ( a8 )
      v28 = *a8;
    else
      v28 = 0;
    LODWORD(lpBuffer) = v28;
    LODWORD(v31) = *a7;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v25,
      (unsigned int)&dword_180103614,
      v26,
      v27,
      (__int64)&v31,
      (__int64)&lpBuffer,
      (__int64)&nNumberOfBytesToRead);
  }
  fnEfsLogTrace1String1Dword(
    g_hPublisher,
    (unsigned int)EFS_TRACE_LEAVE_HR_EVENT,
    (unsigned int)EFS_TRACE_LEAVE_HR_EVENT_ERROR,
    (unsigned int)&sourceString,
    v15,
    40,
    47);
  return v15;
}

```

## disassembly

```asm
0x1800b9ea4  push    rbp
0x1800b9ea6  push    rbx
0x1800b9ea7  push    rsi
0x1800b9ea8  push    rdi
0x1800b9ea9  push    r12
0x1800b9eab  push    r13
0x1800b9ead  push    r14
0x1800b9eaf  push    r15
0x1800b9eb1  lea     rbp, [rsp-3A8h]
0x1800b9eb9  sub     rsp, 4A8h
0x1800b9ec0  mov     rax, cs:__security_cookie
0x1800b9ec7  xor     rax, rsp
0x1800b9eca  mov     [rbp+3E0h+var_50], rax
0x1800b9ed1  mov     rsi, [rbp+3E0h+arg_30]
0x1800b9ed8  mov     r12, r8
0x1800b9edb  mov     r14, [rbp+3E0h+arg_38]
0x1800b9ee2  mov     rbx, rdx
0x1800b9ee5  mov     [rsp+4E0h+var_4A0], r8
0x1800b9eea  mov     r15d, 208h
0x1800b9ef0  mov     [rsp+4E0h+var_480], rcx
0x1800b9ef5  mov     r8d, r15d; Size
0x1800b9ef8  xor     edx, edx; Val
0x1800b9efa  lea     rcx, [rsp+4E0h+FileName]; void *
0x1800b9eff  mov     rdi, r9
0x1800b9f02  call    memset_0
0x1800b9f07  mov     r8d, r15d; Size
0x1800b9f0a  lea     rcx, [rbp+3E0h+NewFileName]; void *
0x1800b9f11  xor     edx, edx; Val
0x1800b9f13  call    memset_0
0x1800b9f18  xor     eax, eax
0x1800b9f1a  mov     [rsp+4E0h+dwCreationDisposition], 2C8Ah
0x1800b9f22  lea     r8, sourceString
0x1800b9f29  mov     [rsp+4E0h+lpBuffer], rax
0x1800b9f2e  lea     rdx, EFS_TRACE_ENTER_EVENT
0x1800b9f35  mov     [rsp+4E0h+nNumberOfBytesToRead], eax
0x1800b9f39  mov     r13d, eax
0x1800b9f3c  mov     [rsp+4E0h+NumberOfBytesRead], eax
0x1800b9f40  lea     r9d, [rax+28h]
0x1800b9f44  mov     r15d, eax
0x1800b9f47  call    fnEfsLogTrace1Strings
0x1800b9f4c  xor     ecx, ecx
0x1800b9f4e  test    rsi, rsi
0x1800b9f51  jz      short loc_1800B9F57
0x1800b9f53  xor     eax, eax
0x1800b9f55  mov     [rsi], eax
0x1800b9f57  test    r14, r14
0x1800b9f5a  jz      short loc_1800B9F61
0x1800b9f5c  xor     eax, eax
0x1800b9f5e  mov     [r14], eax
0x1800b9f61  test    rbx, rbx
0x1800b9f64  jnz     short loc_1800B9F97
0x1800b9f66  mov     [rsp+4E0h+dwCreationDisposition], 2C97h
0x1800b9f6e  mov     ebx, 80070057h
0x1800b9f73  mov     r8d, 80070057h
0x1800b9f79  mov     rcx, cs:g_hPublisher
0x1800b9f80  lea     rdx, EFS_TRACE_ERROR
0x1800b9f87  mov     r9d, 28h ; '('
0x1800b9f8d  call    fnEfsLogTrace1
0x1800b9f92  jmp     loc_1800BA2DB
0x1800b9f97  test    r12, r12
0x1800b9f9a  jnz     short loc_1800B9FA6
0x1800b9f9c  mov     [rsp+4E0h+dwCreationDisposition], 2C98h
0x1800b9fa4  jmp     short loc_1800B9F6E
0x1800b9fa6  test    rdi, rdi
0x1800b9fa9  jnz     short loc_1800B9FB5
0x1800b9fab  mov     [rsp+4E0h+dwCreationDisposition], 2C99h
0x1800b9fb3  jmp     short loc_1800B9F6E
0x1800b9fb5  test    rsi, rsi
0x1800b9fb8  jnz     short loc_1800B9FCF
0x1800b9fba  mov     [rsp+4E0h+dwCreationDisposition], 2C9Ah
0x1800b9fc2  mov     ebx, 80004003h
0x1800b9fc7  mov     r8d, 80004003h
0x1800b9fcd  jmp     short loc_1800B9F79
0x1800b9fcf  test    r14, r14
0x1800b9fd2  jnz     short loc_1800B9FDE
0x1800b9fd4  mov     [rsp+4E0h+dwCreationDisposition], 2C9Bh
0x1800b9fdc  jmp     short loc_1800B9FC2
0x1800b9fde  mov     r12d, dword ptr [rbp+3E0h+arg_20]
0x1800b9fe5  and     r12d, 10h
0x1800b9fe9  jz      short loc_1800BA00B
0x1800b9feb  cmp     word ptr [rdi], 2Eh ; '.'
0x1800b9fef  jnz     short loc_1800BA00B
0x1800b9ff1  cmp     [rdi+2], cx
0x1800b9ff5  jz      short loc_1800BA004
0x1800b9ff7  cmp     word ptr [rdi+2], 2Eh ; '.'
0x1800b9ffc  jnz     short loc_1800BA00B
0x1800b9ffe  cmp     [rdi+4], cx
0x1800ba002  jnz     short loc_1800BA00B
0x1800ba004  xor     ebx, ebx
0x1800ba006  jmp     loc_1800BA2D6
0x1800ba00b  mov     r9d, 28h ; '('
0x1800ba011  mov     [rsp+4E0h+dwCreationDisposition], 2CB0h
0x1800ba019  lea     r8, sourceString
0x1800ba020  lea     rdx, EFS_TRACE_START_EVENT
0x1800ba027  call    fnEfsLogTrace1Strings
0x1800ba02c  lea     r9, Source; "\\"
0x1800ba033  mov     qword ptr [rsp+4E0h+dwFlagsAndAttributes], r13
0x1800ba038  mov     r8, rbx
0x1800ba03b  mov     qword ptr [rsp+4E0h+dwCreationDisposition], rdi
0x1800ba040  mov     edx, 104h; unsigned int
0x1800ba045  lea     rcx, [rsp+4E0h+FileName]; unsigned __int16 *
0x1800ba04a  call    ?StringCchConcat@CDplService@@SAJPEAGKZZ; CDplService::StringCchConcat(ushort *,ulong,...)
0x1800ba04f  mov     rcx, cs:g_hPublisher
0x1800ba056  lea     r9, sourceString
0x1800ba05d  mov     dword ptr [rsp+4E0h+hTemplateFile], 2CB0h
0x1800ba065  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x1800ba06c  mov     [rsp+4E0h+dwFlagsAndAttributes], 28h ; '('
0x1800ba074  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x1800ba07b  mov     [rsp+4E0h+dwCreationDisposition], eax
0x1800ba07f  mov     ebx, eax
0x1800ba081  call    fnEfsLogTrace1String1Dword
0x1800ba086  test    eax, eax
0x1800ba088  js      loc_1800BA2D6
0x1800ba08e  mov     r9d, 28h ; '('
0x1800ba094  mov     [rsp+4E0h+dwCreationDisposition], 2CBAh
0x1800ba09c  lea     r8, sourceString
0x1800ba0a3  lea     rdx, EFS_TRACE_START_EVENT
0x1800ba0aa  call    fnEfsLogTrace1Strings
0x1800ba0af  mov     r8, [rsp+4E0h+var_4A0]
0x1800ba0b4  lea     r9, Source; "\\"
0x1800ba0bb  mov     edx, 104h; unsigned int
0x1800ba0c0  mov     qword ptr [rsp+4E0h+dwFlagsAndAttributes], r13
0x1800ba0c5  lea     rcx, [rbp+3E0h+NewFileName]; unsigned __int16 *
0x1800ba0cc  mov     qword ptr [rsp+4E0h+dwCreationDisposition], rdi
0x1800ba0d1  call    ?StringCchConcat@CDplService@@SAJPEAGKZZ; CDplService::StringCchConcat(ushort *,ulong,...)
0x1800ba0d6  mov     rcx, cs:g_hPublisher
0x1800ba0dd  lea     r9, sourceString
0x1800ba0e4  mov     dword ptr [rsp+4E0h+hTemplateFile], 2CBAh
0x1800ba0ec  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x1800ba0f3  mov     [rsp+4E0h+dwFlagsAndAttributes], 28h ; '('
0x1800ba0fb  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x1800ba102  mov     [rsp+4E0h+dwCreationDisposition], eax
0x1800ba106  mov     ebx, eax
0x1800ba108  call    fnEfsLogTrace1String1Dword
0x1800ba10d  test    eax, eax
0x1800ba10f  js      loc_1800BA2D6
0x1800ba115  mov     r13d, 1
0x1800ba11b  add     [rsi], r13d
0x1800ba11e  lea     r9d, [r13+27h]
0x1800ba122  test    r12d, r12d
0x1800ba125  jz      short loc_1800BA152
0x1800ba127  mov     ebx, 80070150h
0x1800ba12c  mov     [rsp+4E0h+dwCreationDisposition], 2CC6h
0x1800ba134  mov     r8d, 80070150h
0x1800ba13a  mov     rcx, cs:g_hPublisher
0x1800ba141  lea     rdx, EFS_TRACE_ERROR
0x1800ba148  call    fnEfsLogTrace1
0x1800ba14d  jmp     loc_1800BA2D6
0x1800ba152  mov     rbx, [rbp+3E0h+arg_28]
0x1800ba159  test    rbx, rbx
0x1800ba15c  jnz     short loc_1800BA173
0x1800ba15e  mov     ebx, 8007000Dh
0x1800ba163  mov     [rsp+4E0h+dwCreationDisposition], 2CCFh
0x1800ba16b  mov     r8d, 8007000Dh
0x1800ba171  jmp     short loc_1800BA13A
0x1800ba173  cmp     rbx, 10000h
0x1800ba17a  jbe     short loc_1800BA191
0x1800ba17c  mov     ebx, 800700DFh
0x1800ba181  mov     [rsp+4E0h+dwCreationDisposition], 2CD4h
0x1800ba189  mov     r8d, 800700DFh
0x1800ba18f  jmp     short loc_1800BA13A
0x1800ba191  lea     r12, sourceString
0x1800ba198  mov     edi, 2CD7h
0x1800ba19d  mov     r8, r12
0x1800ba1a0  mov     [rsp+4E0h+dwCreationDisposition], edi
0x1800ba1a4  lea     rdx, EFS_TRACE_START_EVENT
0x1800ba1ab  call    fnEfsLogTrace1Strings
0x1800ba1b0  lea     rdx, [rsp+4E0h+nNumberOfBytesToRead]; unsigned int *
0x1800ba1b5  mov     rcx, rbx; unsigned __int64
0x1800ba1b8  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x1800ba1bd  mov     rcx, cs:g_hPublisher
0x1800ba1c4  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x1800ba1cb  mov     dword ptr [rsp+4E0h+hTemplateFile], edi
0x1800ba1cf  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x1800ba1d6  mov     [rsp+4E0h+dwFlagsAndAttributes], 28h ; '('
0x1800ba1de  mov     r9, r12
0x1800ba1e1  mov     [rsp+4E0h+dwCreationDisposition], eax
0x1800ba1e5  mov     ebx, eax
0x1800ba1e7  call    fnEfsLogTrace1String1Dword
0x1800ba1ec  test    eax, eax
0x1800ba1ee  js      loc_1800BA2D6
0x1800ba1f4  mov     edi, 2CD9h
0x1800ba1f9  lea     rdx, EFS_TRACE_START_EVENT
0x1800ba200  mov     r9d, 28h ; '('
0x1800ba206  mov     [rsp+4E0h+dwCreationDisposition], edi
0x1800ba20a  mov     r8, r12
0x1800ba20d  call    fnEfsLogTrace1Strings
0x1800ba212  mov     r12d, [rsp+4E0h+nNumberOfBytesToRead]
0x1800ba217  lea     r9, [rsp+4E0h+lpBuffer]
0x1800ba21c  mov     ecx, r12d
0x1800ba21f  xor     r8d, r8d
0x1800ba222  xor     edx, edx
0x1800ba224  call    ?DplibpMemAllocEx@@YAJ_KW4_DPLIB_ALLOC_QOS_LEVEL@@HPEAPEAX@Z; DplibpMemAllocEx(unsigned __int64,_DPLIB_ALLOC_QOS_LEVEL,int,void * *)
0x1800ba229  mov     rcx, cs:g_hPublisher
0x1800ba230  lea     r9, sourceString
0x1800ba237  mov     dword ptr [rsp+4E0h+hTemplateFile], edi
0x1800ba23b  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x1800ba242  mov     [rsp+4E0h+dwFlagsAndAttributes], 28h ; '('
0x1800ba24a  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x1800ba251  mov     [rsp+4E0h+dwCreationDisposition], eax
0x1800ba255  mov     ebx, eax
0x1800ba257  call    fnEfsLogTrace1String1Dword
0x1800ba25c  test    eax, eax
0x1800ba25e  js      short loc_1800BA2D1
0x1800ba260  add     [rsi], r13d
0x1800ba263  lea     rcx, [rsp+4E0h+FileName]; lpFileName
0x1800ba268  mov     [rsp+4E0h+hTemplateFile], r15; hTemplateFile
0x1800ba26d  xor     r9d, r9d; lpSecurityAttributes
0x1800ba270  mov     [rsp+4E0h+dwFlagsAndAttributes], r15d; dwFlagsAndAttributes
0x1800ba275  mov     r8d, r13d; dwShareMode
0x1800ba278  mov     edx, 80000000h; dwDesiredAccess
0x1800ba27d  mov     [rsp+4E0h+dwCreationDisposition], 3; dwCreationDisposition
0x1800ba285  call    cs:__imp_CreateFileW
0x1800ba28b  mov     rdi, rax
0x1800ba28e  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800ba292  jnz     loc_1800BA397
0x1800ba298  call    cs:__imp_GetLastError
0x1800ba29e  mov     ebx, eax
0x1800ba2a0  test    eax, eax
0x1800ba2a2  jle     short loc_1800BA2AD
0x1800ba2a4  movzx   ebx, ax
0x1800ba2a7  or      ebx, 80070000h
0x1800ba2ad  mov     rcx, cs:g_hPublisher
0x1800ba2b4  lea     rdx, EFS_TRACE_ERROR
0x1800ba2bb  mov     r9d, 28h ; '('
0x1800ba2c1  mov     [rsp+4E0h+dwCreationDisposition], 2CEBh
0x1800ba2c9  mov     r8d, ebx
0x1800ba2cc  call    fnEfsLogTrace1
0x1800ba2d1  mov     r15, [rsp+4E0h+lpBuffer]
0x1800ba2d6  mov     r12, [rsp+4E0h+var_4A0]
0x1800ba2db  test    r15, r15
0x1800ba2de  jz      short loc_1800BA2E8
0x1800ba2e0  mov     rcx, r15; void *
0x1800ba2e3  call    ?DplibMemFree@@YAJPEAX@Z; DplibMemFree(void *)
0x1800ba2e8  test    r13d, r13d
0x1800ba2eb  jz      loc_1800BA49D
0x1800ba2f1  mov     r15d, 2D13h
0x1800ba2f7  lea     r8, sourceString
0x1800ba2fe  mov     r9d, 28h ; '('
0x1800ba304  mov     [rsp+4E0h+dwCreationDisposition], r15d
0x1800ba309  lea     rdx, EFS_TRACE_START_EVENT
0x1800ba310  call    fnEfsLogTrace1Strings
0x1800ba315  mov     rcx, r12; unsigned __int16 *
0x1800ba318  call    ?CreateDirectoryInternal@CDplService@@SAJPEBG@Z; CDplService::CreateDirectoryInternal(ushort const *)
0x1800ba31d  mov     rcx, cs:g_hPublisher
0x1800ba324  lea     r9, sourceString
0x1800ba32b  mov     dword ptr [rsp+4E0h+hTemplateFile], r15d
0x1800ba330  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x1800ba337  mov     [rsp+4E0h+dwFlagsAndAttributes], 28h ; '('
0x1800ba33f  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x1800ba346  mov     [rsp+4E0h+dwCreationDisposition], eax
0x1800ba34a  mov     edi, eax
0x1800ba34c  call    fnEfsLogTrace1String1Dword
0x1800ba351  xor     r12d, r12d
0x1800ba354  test    eax, eax
0x1800ba356  js      short loc_1800BA386
0x1800ba358  xor     r8d, r8d; dwFlags
0x1800ba35b  lea     rdx, [rbp+3E0h+NewFileName]; lpNewFileName
0x1800ba362  lea     rcx, [rsp+4E0h+FileName]; lpExistingFileName
0x1800ba367  call    cs:__imp_MoveFileExW
0x1800ba36d  test    eax, eax
0x1800ba36f  jnz     short loc_1800BA386
0x1800ba371  call    cs:__imp_GetLastError
0x1800ba377  mov     edi, eax
0x1800ba379  test    eax, eax
0x1800ba37b  jle     short loc_1800BA386
0x1800ba37d  movzx   edi, ax
0x1800ba380  or      edi, 80070000h
0x1800ba386  test    r14, r14
0x1800ba389  jz      loc_1800BA4A0
0x1800ba38f  mov     [r14], edi
0x1800ba392  jmp     loc_1800BA4A0
0x1800ba397  add     [rsi], r13d
0x1800ba39a  lea     r9, [rsp+4E0h+NumberOfBytesRead]; lpNumberOfBytesRead
0x1800ba39f  mov     qword ptr [rsp+4E0h+dwCreationDisposition], r15; lpOverlapped
0x1800ba3a4  mov     r8d, r12d; nNumberOfBytesToRead
0x1800ba3a7  mov     r15, [rsp+4E0h+lpBuffer]
0x1800ba3ac  mov     rcx, rdi; hFile
0x1800ba3af  mov     rdx, r15; lpBuffer
0x1800ba3b2  call    cs:__imp_ReadFile
0x1800ba3b8  test    eax, eax
0x1800ba3ba  jnz     short loc_1800BA3DE
0x1800ba3bc  call    cs:__imp_GetLastError
0x1800ba3c2  mov     ebx, eax
0x1800ba3c4  test    eax, eax
0x1800ba3c6  jle     short loc_1800BA3D1
0x1800ba3c8  movzx   ebx, ax
0x1800ba3cb  or      ebx, 80070000h
0x1800ba3d1  mov     [rsp+4E0h+dwCreationDisposition], 2CF6h
0x1800ba3d9  mov     r8d, ebx
0x1800ba3dc  jmp     short loc_1800BA3F8
0x1800ba3de  cmp     r12d, [rsp+4E0h+NumberOfBytesRead]
0x1800ba3e3  jz      short loc_1800BA41F
0x1800ba3e5  mov     ebx, 8007001Fh
0x1800ba3ea  mov     [rsp+4E0h+dwCreationDisposition], 2CFBh
0x1800ba3f2  mov     r8d, 8007001Fh
0x1800ba3f8  mov     rcx, cs:g_hPublisher
0x1800ba3ff  lea     rdx, EFS_TRACE_ERROR
0x1800ba406  mov     r9d, 28h ; '('
0x1800ba40c  call    fnEfsLogTrace1
  ... truncated ...
```
