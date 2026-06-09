# _werDetail::UtilGetFinalPathOnUnmountedVolume(void *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &)

- ea: `0x18000b2f8`
- end: `0x18000b905`
- name: `?UtilGetFinalPathOnUnmountedVolume@_werDetail@@YAJPEAXAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z`
- size: `1549`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, reparse_path, broker_com_uri`

## callers

- `0x18000af40`

## callees

- `0x18000113c`
- `0x1800011dc`
- `0x18000126c`
- `0x18000134c`
- `0x180002890`
- `0x1800028b4`
- `0x180009e04`
- `0x18000a074`
- `0x18000b2f8`
- `0x18000bc54`
- `0x18000be60`
- `0x18000bf10`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000b60f`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000b60f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b525`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b7a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b80e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b525`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b7a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b80e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b8d6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b8d6`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x18000b36f`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x18000b5c0`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x18000b36f`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x18000b5c0`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000b50f`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000b50f`

## string_xrefs

- `0x18000b456`: `StorePath`

## pseudocode

```c
__int64 __fastcall _werDetail::UtilGetFinalPathOnUnmountedVolume(void *a1, __int64 a2)
{
  char *FileW; // rbx
  DWORD FinalPathNameByHandleW; // eax
  __int64 v5; // r8
  __int64 v6; // r9
  unsigned __int64 v7; // r14
  unsigned __int64 v8; // r8
  int LastError; // edi
  char *v10; // rdx
  const WCHAR *v11; // rcx
  signed int v12; // eax
  __int64 v13; // r8
  __int64 v14; // r9
  __int64 v15; // rcx
  char *v16; // rdx
  DWORD v17; // eax
  __int64 v18; // rdx
  __int64 v19; // rcx
  __int64 v20; // r8
  __int64 v21; // r9
  DWORD hTemplateFile; // [rsp+30h] [rbp-D0h]
  int *v24; // [rsp+40h] [rbp-C0h] BYREF
  int *v25; // [rsp+48h] [rbp-B8h] BYREF
  LPCWSTR lpFileName; // [rsp+50h] [rbp-B0h] BYREF
  const WCHAR *v27; // [rsp+58h] [rbp-A8h]
  _WORD v28[8]; // [rsp+60h] [rbp-A0h] BYREF
  LPCWCH lpString1; // [rsp+70h] [rbp-90h] BYREF
  _WORD *v30; // [rsp+78h] [rbp-88h]
  _WORD v31[8]; // [rsp+80h] [rbp-80h] BYREF
  char v32[32]; // [rsp+90h] [rbp-70h] BYREF
  int **v33; // [rsp+B0h] [rbp-50h]
  __int64 v34; // [rsp+B8h] [rbp-48h]
  WCHAR szFilePath[264]; // [rsp+C0h] [rbp-40h] BYREF

  lpFileName = v28;
  v28[0] = 0;
  v27 = v28;
  v31[0] = 0;
  lpString1 = v31;
  v30 = v31;
  FileW = 0;
  FinalPathNameByHandleW = GetFinalPathNameByHandleW(a1, szFilePath, 0x104u, 2u);
  if ( !FinalPathNameByHandleW )
  {
    LastError = GetLastError();
    if ( LastError <= 0 )
    {
LABEL_69:
      if ( LastError >= 0 )
        LastError = -2147467259;
      if ( (unsigned int)dword_180062000 <= 2 || (qword_180062010 & 8) == 0 || (qword_180062018 & 8) != qword_180062018 )
        goto LABEL_77;
      v10 = &byte_180057A47;
LABEL_75:
      LODWORD(v24) = LastError;
      goto LABEL_76;
    }
LABEL_68:
    LastError = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_69;
  }
  if ( FinalPathNameByHandleW >= 0x104 )
  {
    LOWORD(LastError) = 111;
    goto LABEL_68;
  }
  if ( (unsigned int)dword_180062000 > 4 && (qword_180062010 & 8) != 0 && (qword_180062018 & 8) == qword_180062018 )
  {
    v24 = (int *)szFilePath;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(
      qword_180062018,
      (__int64)byte_180057A05,
      v5,
      v6,
      &v24);
  }
  v7 = -1;
  v8 = -1;
  do
    ++v8;
  while ( szFilePath[v8] );
  if ( !utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
          (__int64)&lpString1,
          szFilePath,
          v8) )
  {
    LastError = -2147024882;
    if ( (unsigned int)dword_180062000 > 2 && (qword_180062010 & 8) != 0 && (qword_180062018 & 8) == qword_180062018 )
    {
      LODWORD(v24) = -2147024882;
      v10 = byte_1800579C9;
LABEL_76:
      v34 = 4;
      v33 = &v24;
      tlgWriteTransfer_EventWriteTransfer(&dword_180062000, v10, 0, 0, 3, v32);
      goto LABEL_77;
    }
    goto LABEL_77;
  }
  LastError = UtilRegGetString(
                HKEY_LOCAL_MACHINE,
                L"Software\\Microsoft\\Windows\\Windows Error Reporting",
                L"StorePath",
                &dword_18004FE4C,
                &lpFileName,
                0,
                hTemplateFile);
  if ( LastError < 0 )
  {
    if ( (unsigned int)dword_180062000 <= 2 || (qword_180062010 & 8) == 0 || (qword_180062018 & 8) != qword_180062018 )
      goto LABEL_77;
    v10 = (char *)&word_180057986;
    goto LABEL_75;
  }
  v11 = lpFileName;
  if ( lpFileName == v27 || *(v27 - 1) != 92 )
  {
    if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(
                             &lpFileName,
                             92) )
    {
      LastError = -2147024882;
      goto LABEL_77;
    }
    v11 = lpFileName;
  }
  FileW = (char *)CreateFileW(v11, 0x80u, 1u, 0, 3u, 0x2000080u, 0);
  if ( FileW == (char *)-1LL || FileW + 1 == (char *)1 )
  {
    v12 = GetLastError();
    LastError = v12;
    if ( v12 > 0 )
      LastError = (unsigned __int16)v12 | 0x80070000;
    if ( LastError >= 0 )
      LastError = -2147467259;
    if ( (unsigned int)dword_180062000 <= 2 )
      goto LABEL_77;
    v15 = qword_180062018;
    if ( (qword_180062010 & 8) == 0 || (qword_180062018 & 8) != qword_180062018 )
      goto LABEL_77;
    v16 = &byte_180057937;
    goto LABEL_33;
  }
  v17 = GetFinalPathNameByHandleW(FileW, szFilePath, 0x104u, 2u);
  if ( !v17 )
  {
    LastError = GetLastError();
    if ( LastError <= 0 )
    {
LABEL_60:
      if ( LastError >= 0 )
        LastError = -2147467259;
      if ( (unsigned int)dword_180062000 <= 2 )
        goto LABEL_77;
      v15 = qword_180062018;
      if ( (qword_180062010 & 8) == 0 || (qword_180062018 & 8) != qword_180062018 )
        goto LABEL_77;
      v16 = (char *)&unk_1800578E8;
LABEL_33:
      v25 = (int *)lpFileName;
      LODWORD(v24) = LastError;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>>(
        v15,
        (__int64)v16,
        v13,
        v14,
        &v25,
        (__int64)&v24);
      goto LABEL_77;
    }
LABEL_59:
    LastError = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_60;
  }
  if ( v17 >= 0x104 )
  {
    LOWORD(LastError) = 111;
    goto LABEL_59;
  }
  do
    ++v7;
  while ( szFilePath[v7] );
  if ( v30 - lpString1 >= v7 && CompareStringOrdinal(lpString1, v7, szFilePath, v7, 1) == 2 )
  {
    if ( (unsigned int)dword_180062000 > 4 && (qword_180062010 & 8) != 0 && (qword_180062018 & 8) == qword_180062018 )
    {
      v25 = (int *)lpString1;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(
        qword_180062018,
        (__int64)word_1800578A2,
        v13,
        v14,
        &v25);
    }
    if ( (unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::replace(
                            &lpString1,
                            v18,
                            v7) )
    {
      if ( (unsigned int)dword_180062000 > 4 && (qword_180062010 & 8) != 0 && (qword_180062018 & 8) == qword_180062018 )
      {
        v25 = (int *)lpString1;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(
          v19,
          (__int64)&byte_18005781F,
          v20,
          v21,
          &v25);
      }
      utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::operator=(a2, (__int64)&lpString1);
      LastError = 0;
    }
    else
    {
      LastError = -2147024882;
      if ( (unsigned int)dword_180062000 > 2 && (qword_180062010 & 8) != 0 && (qword_180062018 & 8) == qword_180062018 )
      {
        LODWORD(v24) = -2147024882;
        v10 = (char *)&dword_180057864;
        goto LABEL_76;
      }
    }
  }
  else
  {
    LastError = -2147024735;
    if ( (unsigned int)dword_180062000 > 2 && (qword_180062010 & 8) != 0 && (qword_180062018 & 8) == qword_180062018 )
    {
      v25 = (int *)szFilePath;
      v24 = (int *)lpString1;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>>(
        qword_180062018,
        (__int64)byte_1800577CB,
        v13,
        v14,
        &v24,
        &v25);
    }
  }
LABEL_77:
  if ( lpString1 != v31 )
    operator delete((void *)lpString1, (const struct std::nothrow_t *)&std::nothrow);
  if ( lpFileName != v28 )
    operator delete((void *)lpFileName, (const struct std::nothrow_t *)&std::nothrow);
  if ( (unsigned __int64)(FileW + 1) > 1 )
    CloseHandle(FileW);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x18000b2f8  mov     [rsp-8+arg_10], rbx
0x18000b2fd  push    rbp
0x18000b2fe  push    rdi
0x18000b2ff  push    r12
0x18000b301  push    r13
0x18000b303  push    r14
0x18000b305  lea     rbp, [rsp-1E0h]
0x18000b30d  sub     rsp, 2E0h
0x18000b314  mov     rax, cs:__security_cookie
0x18000b31b  xor     rax, rsp
0x18000b31e  mov     [rbp+200h+var_30], rax
0x18000b325  xor     r13d, r13d
0x18000b328  lea     rax, [rsp+300h+var_2A0]
0x18000b32d  mov     [rsp+300h+lpFileName], rax
0x18000b332  mov     r12, rdx
0x18000b335  lea     rax, [rsp+300h+var_2A0]
0x18000b33a  mov     [rsp+300h+var_2A0], r13w
0x18000b340  mov     [rsp+300h+var_2A8], rax
0x18000b345  lea     rdx, [rbp+200h+szFilePath]; lpszFilePath
0x18000b349  lea     rax, [rbp+200h+var_280]
0x18000b34d  mov     [rbp+200h+var_280], r13w
0x18000b352  mov     [rsp+300h+lpString1], rax
0x18000b357  lea     r9d, [r13+2]; dwFlags
0x18000b35b  lea     rax, [rbp+200h+var_280]
0x18000b35f  mov     edi, 104h
0x18000b364  mov     r8d, edi; cchFilePath
0x18000b367  mov     [rsp+300h+var_288], rax
0x18000b36c  mov     ebx, r13d
0x18000b36f  call    cs:__imp_GetFinalPathNameByHandleW
0x18000b375  test    eax, eax
0x18000b377  jz      loc_18000B80E
0x18000b37d  cmp     eax, edi
0x18000b37f  jnb     loc_18000B807
0x18000b385  mov     eax, cs:dword_180062000
0x18000b38b  cmp     eax, 4
0x18000b38e  jbe     short loc_18000B3CC
0x18000b390  mov     rcx, cs:qword_180062018
0x18000b397  mov     rax, cs:qword_180062010
0x18000b39e  test    al, 8
0x18000b3a0  jz      short loc_18000B3CC
0x18000b3a2  mov     rax, rcx
0x18000b3a5  and     eax, 8
0x18000b3a8  cmp     rax, rcx
0x18000b3ab  jnz     short loc_18000B3CC
0x18000b3ad  lea     rax, [rbp+200h+szFilePath]
0x18000b3b1  mov     [rsp+300h+var_2C0], rax
0x18000b3b6  lea     rdx, byte_180057A05
0x18000b3bd  lea     rax, [rsp+300h+var_2C0]
0x18000b3c2  mov     qword ptr [rsp+300h+dwCreationDisposition], rax
0x18000b3c7  call    ??$Write@U?$_tlgWrapSz@_W@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &)
0x18000b3cc  or      r14, 0FFFFFFFFFFFFFFFFh
0x18000b3d0  lea     rax, [rbp+200h+szFilePath]
0x18000b3d4  mov     r8, r14
0x18000b3d7  inc     r8
0x18000b3da  cmp     [rax+r8*2], r13w
0x18000b3df  jnz     short loc_18000B3D7
0x18000b3e1  lea     rdx, [rbp+200h+szFilePath]
0x18000b3e5  lea     rcx, [rsp+300h+lpString1]
0x18000b3ea  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x18000b3ef  test    al, al
0x18000b3f1  jnz     short loc_18000B440
0x18000b3f3  mov     eax, cs:dword_180062000
0x18000b3f9  mov     edi, 8007000Eh
0x18000b3fe  cmp     eax, 2
0x18000b401  jbe     loc_18000B894
0x18000b407  mov     rcx, cs:qword_180062018
0x18000b40e  mov     rax, cs:qword_180062010
0x18000b415  test    al, 8
0x18000b417  jz      loc_18000B894
0x18000b41d  mov     rax, rcx
0x18000b420  and     eax, 8
0x18000b423  cmp     rax, rcx
0x18000b426  jnz     loc_18000B894
0x18000b42c  mov     dword ptr [rsp+300h+var_2C0], 8007000Eh
0x18000b434  lea     rdx, byte_1800579C9
0x18000b43b  jmp     loc_18000B860
0x18000b440  lea     rax, [rsp+300h+lpFileName]
0x18000b445  mov     byte ptr [rsp+300h+dwFlagsAndAttributes], r13b; char
0x18000b44a  lea     r9, dword_18004FE4C
0x18000b451  mov     qword ptr [rsp+300h+dwCreationDisposition], rax; __int64
0x18000b456  lea     r8, aStorepath; "StorePath"
0x18000b45d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000b464  lea     rdx, aSoftwareMicros_8; "Software\\Microsoft\\Windows\\Windows E"...
0x18000b46b  call    ?UtilRegGetString@@YAJPEAUHKEY__@@PEB_W11PEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@_N3@Z; UtilRegGetString(HKEY__ *,wchar_t const *,wchar_t const *,wchar_t const *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *,bool,bool)
0x18000b470  mov     edi, eax
0x18000b472  test    eax, eax
0x18000b474  jns     short loc_18000B4B7
0x18000b476  mov     ecx, cs:dword_180062000
0x18000b47c  cmp     ecx, 2
0x18000b47f  jbe     loc_18000B894
0x18000b485  mov     rax, cs:qword_180062018
0x18000b48c  mov     rcx, cs:qword_180062010
0x18000b493  test    cl, 8
0x18000b496  jz      loc_18000B894
0x18000b49c  mov     rcx, rax
0x18000b49f  and     ecx, 8
0x18000b4a2  cmp     rcx, rax
0x18000b4a5  jnz     loc_18000B894
0x18000b4ab  lea     rdx, word_180057986
0x18000b4b2  jmp     loc_18000B85C
0x18000b4b7  mov     rcx, [rsp+300h+lpFileName]
0x18000b4bc  mov     edx, 5Ch ; '\'
0x18000b4c1  mov     rax, [rsp+300h+var_2A8]
0x18000b4c6  cmp     rcx, rax
0x18000b4c9  jz      short loc_18000B4D1
0x18000b4cb  cmp     dx, [rax-2]
0x18000b4cf  jz      short loc_18000B4EE
0x18000b4d1  lea     rcx, [rsp+300h+lpFileName]
0x18000b4d6  call    ?push_back@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(wchar_t)
0x18000b4db  test    al, al
0x18000b4dd  jnz     short loc_18000B4E9
0x18000b4df  mov     edi, 8007000Eh
0x18000b4e4  jmp     loc_18000B894
0x18000b4e9  mov     rcx, [rsp+300h+lpFileName]; lpFileName
0x18000b4ee  xor     r9d, r9d; lpSecurityAttributes
0x18000b4f1  mov     qword ptr [rsp+300h+hTemplateFile], r13; hTemplateFile
0x18000b4f6  mov     [rsp+300h+dwFlagsAndAttributes], 2000080h; dwFlagsAndAttributes
0x18000b4fe  mov     edx, 80h; dwDesiredAccess
0x18000b503  mov     [rsp+300h+dwCreationDisposition], 3; dwCreationDisposition
0x18000b50b  lea     r8d, [r9+1]; dwShareMode
0x18000b50f  call    cs:__imp_CreateFileW
0x18000b515  mov     rbx, rax
0x18000b518  inc     rax
0x18000b51b  cmp     rax, 1
0x18000b51f  ja      loc_18000B5AB
0x18000b525  call    cs:__imp_GetLastError
0x18000b52b  mov     edi, eax
0x18000b52d  test    eax, eax
0x18000b52f  jle     short loc_18000B53A
0x18000b531  movzx   edi, ax
0x18000b534  or      edi, 80070000h
0x18000b53a  test    edi, edi
0x18000b53c  mov     eax, 80004005h
0x18000b541  cmovns  edi, eax
0x18000b544  mov     eax, cs:dword_180062000
0x18000b54a  cmp     eax, 2
0x18000b54d  jbe     loc_18000B894
0x18000b553  mov     rcx, cs:qword_180062018
0x18000b55a  mov     rax, cs:qword_180062010
0x18000b561  test    al, 8
0x18000b563  jz      loc_18000B894
0x18000b569  mov     rax, rcx
0x18000b56c  and     eax, 8
0x18000b56f  cmp     rax, rcx
0x18000b572  jnz     loc_18000B894
0x18000b578  lea     rdx, byte_180057937
0x18000b57f  mov     rax, [rsp+300h+lpFileName]
0x18000b584  mov     [rsp+300h+var_2B8], rax
0x18000b589  lea     rax, [rsp+300h+var_2C0]
0x18000b58e  mov     qword ptr [rsp+300h+dwFlagsAndAttributes], rax
0x18000b593  lea     rax, [rsp+300h+var_2B8]
0x18000b598  mov     qword ptr [rsp+300h+dwCreationDisposition], rax
0x18000b59d  mov     dword ptr [rsp+300h+var_2C0], edi
0x18000b5a1  call    ??$Write@U?$_tlgWrapSz@_W@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &)
0x18000b5a6  jmp     loc_18000B894
0x18000b5ab  mov     edi, 104h
0x18000b5b0  lea     rdx, [rbp+200h+szFilePath]; lpszFilePath
0x18000b5b4  mov     r8d, edi; cchFilePath
0x18000b5b7  mov     r9d, 2; dwFlags
0x18000b5bd  mov     rcx, rbx; hFile
0x18000b5c0  call    cs:__imp_GetFinalPathNameByHandleW
0x18000b5c6  test    eax, eax
0x18000b5c8  jz      loc_18000B7A8
0x18000b5ce  cmp     eax, edi
0x18000b5d0  jnb     loc_18000B7A1
0x18000b5d6  lea     rax, [rbp+200h+szFilePath]
0x18000b5da  inc     r14
0x18000b5dd  cmp     [rax+r14*2], r13w
0x18000b5e2  jnz     short loc_18000B5DA
0x18000b5e4  mov     rax, [rsp+300h+var_288]
0x18000b5e9  mov     rcx, [rsp+300h+lpString1]; lpString1
0x18000b5ee  sub     rax, rcx
0x18000b5f1  sar     rax, 1
0x18000b5f4  cmp     rax, r14
0x18000b5f7  jb      loc_18000B730
0x18000b5fd  mov     r9d, r14d; cchCount2
0x18000b600  mov     [rsp+300h+dwCreationDisposition], 1; bIgnoreCase
0x18000b608  lea     r8, [rbp+200h+szFilePath]; lpString2
0x18000b60c  mov     edx, r14d; cchCount1
0x18000b60f  call    cs:__imp_CompareStringOrdinal
0x18000b615  cmp     eax, 2
0x18000b618  jnz     loc_18000B730
0x18000b61e  mov     eax, cs:dword_180062000
0x18000b624  cmp     eax, 4
0x18000b627  jbe     short loc_18000B666
0x18000b629  mov     rcx, cs:qword_180062018
0x18000b630  mov     rax, cs:qword_180062010
0x18000b637  test    al, 8
0x18000b639  jz      short loc_18000B666
0x18000b63b  mov     rax, rcx
0x18000b63e  and     eax, 8
0x18000b641  cmp     rax, rcx
0x18000b644  jnz     short loc_18000B666
0x18000b646  mov     rax, [rsp+300h+lpString1]
0x18000b64b  lea     rdx, word_1800578A2
0x18000b652  mov     [rsp+300h+var_2B8], rax
0x18000b657  lea     rax, [rsp+300h+var_2B8]
0x18000b65c  mov     qword ptr [rsp+300h+dwCreationDisposition], rax
0x18000b661  call    ??$Write@U?$_tlgWrapSz@_W@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &)
0x18000b666  mov     rax, [rsp+300h+var_2A8]
0x18000b66b  lea     rcx, [rsp+300h+lpString1]
0x18000b670  mov     r9, [rsp+300h+lpFileName]
0x18000b675  mov     r8, r14
0x18000b678  sub     rax, r9
0x18000b67b  sar     rax, 1
0x18000b67e  mov     qword ptr [rsp+300h+dwCreationDisposition], rax
0x18000b683  call    ?replace@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_K0PEB_W0@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::replace(unsigned __int64,unsigned __int64,wchar_t const *,unsigned __int64)
0x18000b688  test    al, al
0x18000b68a  mov     eax, cs:dword_180062000
0x18000b690  jnz     short loc_18000B6D9
0x18000b692  mov     edi, 8007000Eh
0x18000b697  cmp     eax, 2
0x18000b69a  jbe     loc_18000B894
0x18000b6a0  mov     rcx, cs:qword_180062018
0x18000b6a7  mov     rax, cs:qword_180062010
0x18000b6ae  test    al, 8
0x18000b6b0  jz      loc_18000B894
0x18000b6b6  mov     rax, rcx
0x18000b6b9  and     eax, 8
0x18000b6bc  cmp     rax, rcx
0x18000b6bf  jnz     loc_18000B894
0x18000b6c5  mov     dword ptr [rsp+300h+var_2C0], 8007000Eh
0x18000b6cd  lea     rdx, dword_180057864
0x18000b6d4  jmp     loc_18000B860
0x18000b6d9  cmp     eax, 4
0x18000b6dc  jbe     short loc_18000B71B
0x18000b6de  mov     rdx, cs:qword_180062018
0x18000b6e5  mov     rax, cs:qword_180062010
0x18000b6ec  test    al, 8
0x18000b6ee  jz      short loc_18000B71B
0x18000b6f0  mov     rax, rdx
0x18000b6f3  and     eax, 8
0x18000b6f6  cmp     rax, rdx
0x18000b6f9  jnz     short loc_18000B71B
0x18000b6fb  mov     rax, [rsp+300h+lpString1]
0x18000b700  lea     rdx, byte_18005781F
0x18000b707  mov     [rsp+300h+var_2B8], rax
0x18000b70c  lea     rax, [rsp+300h+var_2B8]
0x18000b711  mov     qword ptr [rsp+300h+dwCreationDisposition], rax
0x18000b716  call    ??$Write@U?$_tlgWrapSz@_W@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &)
0x18000b71b  lea     rdx, [rsp+300h+lpString1]
0x18000b720  mov     rcx, r12
0x18000b723  call    ??4?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAAAEAV01@$$QEAV01@@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::operator=(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &&)
0x18000b728  mov     edi, r13d
0x18000b72b  jmp     loc_18000B894
0x18000b730  mov     eax, cs:dword_180062000
0x18000b736  mov     edi, 800700A1h
0x18000b73b  cmp     eax, 2
0x18000b73e  jbe     loc_18000B894
0x18000b744  mov     rcx, cs:qword_180062018
0x18000b74b  mov     rax, cs:qword_180062010
0x18000b752  test    al, 8
0x18000b754  jz      loc_18000B894
0x18000b75a  mov     rax, rcx
0x18000b75d  and     eax, 8
0x18000b760  cmp     rax, rcx
0x18000b763  jnz     loc_18000B894
0x18000b769  lea     rax, [rbp+200h+szFilePath]
0x18000b76d  mov     [rsp+300h+var_2B8], rax
0x18000b772  lea     rdx, byte_1800577CB
0x18000b779  mov     rax, [rsp+300h+lpString1]
0x18000b77e  mov     [rsp+300h+var_2C0], rax
0x18000b783  lea     rax, [rsp+300h+var_2B8]
0x18000b788  mov     qword ptr [rsp+300h+dwFlagsAndAttributes], rax
0x18000b78d  lea     rax, [rsp+300h+var_2C0]
0x18000b792  mov     qword ptr [rsp+300h+dwCreationDisposition], rax
0x18000b797  call    ??$Write@U?$_tlgWrapSz@_W@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<wchar_t> const &)
0x18000b79c  jmp     loc_18000B894
0x18000b7a1  mov     edi, 6Fh ; 'o'
0x18000b7a6  jmp     short loc_18000B7B4
0x18000b7a8  call    cs:__imp_GetLastError
0x18000b7ae  mov     edi, eax
0x18000b7b0  test    eax, eax
0x18000b7b2  jle     short loc_18000B7BD
0x18000b7b4  movzx   edi, di
0x18000b7b7  or      edi, 80070000h
0x18000b7bd  test    edi, edi
0x18000b7bf  mov     eax, 80004005h
0x18000b7c4  cmovns  edi, eax
0x18000b7c7  mov     eax, cs:dword_180062000
0x18000b7cd  cmp     eax, 2
0x18000b7d0  jbe     loc_18000B894
0x18000b7d6  mov     rcx, cs:qword_180062018
0x18000b7dd  mov     rax, cs:qword_180062010
0x18000b7e4  test    al, 8
0x18000b7e6  jz      loc_18000B894
0x18000b7ec  mov     rax, rcx
0x18000b7ef  and     eax, 8
0x18000b7f2  cmp     rax, rcx
0x18000b7f5  jnz     loc_18000B894
0x18000b7fb  lea     rdx, unk_1800578E8
0x18000b802  jmp     loc_18000B57F
0x18000b807  mov     edi, 6Fh ; 'o'
0x18000b80c  jmp     short loc_18000B81A
0x18000b80e  call    cs:__imp_GetLastError
0x18000b814  mov     edi, eax
0x18000b816  test    eax, eax
0x18000b818  jle     short loc_18000B823
0x18000b81a  movzx   edi, di
0x18000b81d  or      edi, 80070000h
  ... truncated ...
```
