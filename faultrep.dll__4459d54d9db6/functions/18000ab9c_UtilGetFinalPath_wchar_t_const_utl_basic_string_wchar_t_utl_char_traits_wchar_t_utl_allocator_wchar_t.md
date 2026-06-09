# UtilGetFinalPath(wchar_t const *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &)

- ea: `0x18000ab9c`
- end: `0x18000af3a`
- name: `?UtilGetFinalPath@@YAHPEB_WAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z`
- size: `926`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, reparse_path`

## callers

- `0x18000b90c`

## callees

- `0x18000113c`
- `0x1800011dc`
- `0x18000126c`
- `0x18000134c`
- `0x180002890`
- `0x18000ab9c`
- `0x18000af40`
- `0x18000be60`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18000ae7a`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18000ae9b`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18000ae7a`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18000ae9b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ac57`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ac57`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000af0a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000af0a`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000ac45`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000ac45`

## pseudocode

```c
__int64 __fastcall UtilGetFinalPath(int *lpFileName, int **a2, __int64 a3, __int64 a4)
{
  char *FileW; // rbx
  signed int LastError; // eax
  __int64 v8; // rcx
  __int64 v9; // rax
  WCHAR v10; // r14
  int FinalPathByHandle; // edx
  int *v12; // rax
  int *v13; // rcx
  int *v14; // rax
  __int64 v15; // r14
  int v16; // eax
  unsigned int v17; // edi
  int *v19; // [rsp+40h] [rbp-19h] BYREF
  int *v20; // [rsp+48h] [rbp-11h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v21; // [rsp+50h] [rbp-9h] BYREF
  int **v22; // [rsp+70h] [rbp+17h]
  __int64 v23; // [rsp+78h] [rbp+1Fh]

  if ( !lpFileName )
  {
    FileW = 0;
LABEL_45:
    v17 = 0;
    goto LABEL_46;
  }
  if ( (unsigned int)dword_180062000 > 4 && (qword_180062010 & 8) != 0 && (qword_180062018 & 8) == qword_180062018 )
  {
    v19 = lpFileName;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(
      qword_180062018,
      (__int64)word_180057662,
      a3,
      a4,
      &v19);
  }
  FileW = (char *)CreateFileW((LPCWSTR)lpFileName, 0x80u, 1u, 0, 3u, 0x2000080u, 0);
  if ( FileW == (char *)-1LL || FileW + 1 == (char *)1 )
  {
    LastError = GetLastError();
    v8 = (unsigned int)LastError;
    if ( LastError > 0 )
      v8 = (unsigned __int16)LastError | 0x80070000;
    if ( (int)v8 >= 0 )
      v8 = 2147500037LL;
    if ( (unsigned int)dword_180062000 > 2 && (qword_180062010 & 8) != 0 && (qword_180062018 & 8) == qword_180062018 )
    {
      LODWORD(v19) = v8;
      v20 = lpFileName;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>>(
        v8,
        (__int64)&word_180057626,
        a3,
        a4,
        &v20,
        (__int64)&v19);
    }
    goto LABEL_45;
  }
  v9 = -1;
  do
    ++v9;
  while ( *((_WORD *)lpFileName + v9) );
  v10 = *((_WORD *)lpFileName + v9 - 1);
  FinalPathByHandle = _werDetail::UtilGetFinalPathByHandle(FileW, (__int64)a2);
  if ( FinalPathByHandle < 0 )
  {
    if ( (unsigned int)dword_180062000 > 2 && (qword_180062010 & 8) != 0 && (qword_180062018 & 8) == qword_180062018 )
    {
      LODWORD(v19) = FinalPathByHandle;
      v22 = &v19;
      v23 = 4;
      tlgWriteTransfer_EventWriteTransfer((__int64)&dword_180062000, (unsigned __int8 *)byte_1800575FB, 0, 0, 3u, &v21);
    }
    goto LABEL_45;
  }
  if ( v10 == 92 )
  {
    v12 = a2[1];
    if ( (*a2 == v12 || *((_WORD *)v12 - 1) != 92)
      && !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(
                             a2,
                             92) )
    {
      v13 = *a2;
      a2[1] = *a2;
      *(_WORD *)v13 = 0;
      goto LABEL_45;
    }
  }
  v14 = *a2;
  if ( *a2 && *(_WORD *)v14 == 92 && *((_WORD *)v14 + 1) == 92 && *((_WORD *)v14 + 2) == 63 && *((_WORD *)v14 + 3) == 92 )
  {
    if ( (unsigned int)dword_180062000 > 5 && (qword_180062010 & 8) != 0 && (qword_180062018 & 8) == qword_180062018 )
    {
      v20 = *a2;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(
        qword_180062018,
        (__int64)byte_1800575BD,
        a3,
        a4,
        &v20);
    }
    v15 = 2;
  }
  else
  {
    v15 = 0;
  }
  if ( (unsigned int)dword_180062000 > 5 && (qword_180062010 & 8) != 0 && (qword_180062018 & 8) == qword_180062018 )
  {
    v20 = *a2;
    v19 = lpFileName;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>>(
      qword_180062018,
      (__int64)&unk_180057578,
      a3,
      a4,
      &v19,
      &v20);
  }
  if ( !(unsigned int)_o__wcsnicmp(lpFileName, *a2, ((char *)a2[1] - (char *)*a2) >> 1) )
    goto LABEL_45;
  v16 = _o__wcsnicmp(lpFileName, &(*a2)[v15], (((char *)a2[1] - (char *)*a2) >> 1) - v15 * 2);
  v17 = 1;
  if ( !v16 )
    goto LABEL_45;
LABEL_46:
  if ( (unsigned int)dword_180062000 > 4 && (qword_180062010 & 8) != 0 && (qword_180062018 & 8) == qword_180062018 )
  {
    v20 = *a2;
    LODWORD(v19) = v17;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>>(
      qword_180062018,
      (__int64)&word_18005753E,
      a3,
      a4,
      &v20,
      (__int64)&v19);
  }
  if ( (unsigned __int64)(FileW + 1) > 1 )
    CloseHandle(FileW);
  return v17;
}

```

## disassembly

```asm
0x18000ab9c  mov     [rsp-8+arg_10], rbx
0x18000aba1  mov     [rsp-8+arg_18], rsi
0x18000aba6  push    rbp
0x18000aba7  push    rdi
0x18000aba8  push    r13
0x18000abaa  push    r14
0x18000abac  push    r15
0x18000abae  lea     rbp, [rsp-37h]
0x18000abb3  sub     rsp, 90h
0x18000abba  mov     rax, cs:__security_cookie
0x18000abc1  xor     rax, rsp
0x18000abc4  mov     [rbp+57h+var_30], rax
0x18000abc8  xor     r15d, r15d
0x18000abcb  mov     rsi, rdx
0x18000abce  mov     rdi, rcx
0x18000abd1  test    rcx, rcx
0x18000abd4  jnz     short loc_18000ABDE
0x18000abd6  mov     ebx, r15d
0x18000abd9  jmp     loc_18000AEAA
0x18000abde  mov     eax, cs:dword_180062000
0x18000abe4  cmp     eax, 4
0x18000abe7  jbe     short loc_18000AC1F
0x18000abe9  mov     rcx, cs:qword_180062018
0x18000abf0  mov     rax, cs:qword_180062010
0x18000abf7  test    al, 8
0x18000abf9  jz      short loc_18000AC1F
0x18000abfb  mov     rax, rcx
0x18000abfe  and     eax, 8
0x18000ac01  cmp     rax, rcx
0x18000ac04  jnz     short loc_18000AC1F
0x18000ac06  lea     rax, [rbp+57h+var_70]
0x18000ac0a  mov     [rbp+57h+var_70], rdi
0x18000ac0e  lea     rdx, word_180057662
0x18000ac15  mov     qword ptr [rsp+0B0h+dwCreationDisposition], rax
0x18000ac1a  call    ??$Write@U?$_tlgWrapSz@_W@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &)
0x18000ac1f  mov     r13d, 3
0x18000ac25  mov     [rsp+0B0h+hTemplateFile], r15; hTemplateFile
0x18000ac2a  mov     [rsp+0B0h+dwFlagsAndAttributes], 2000080h; dwFlagsAndAttributes
0x18000ac32  xor     r9d, r9d; lpSecurityAttributes
0x18000ac35  mov     rcx, rdi; lpFileName
0x18000ac38  mov     [rsp+0B0h+dwCreationDisposition], r13d; dwCreationDisposition
0x18000ac3d  lea     edx, [r13+7Dh]; dwDesiredAccess
0x18000ac41  lea     r8d, [r13-2]; dwShareMode
0x18000ac45  call    cs:__imp_CreateFileW
0x18000ac4b  mov     rbx, rax
0x18000ac4e  inc     rax
0x18000ac51  cmp     rax, 1
0x18000ac55  ja      short loc_18000ACD4
0x18000ac57  call    cs:__imp_GetLastError
0x18000ac5d  mov     ecx, eax
0x18000ac5f  test    eax, eax
0x18000ac61  jle     short loc_18000AC6C
0x18000ac63  movzx   ecx, ax
0x18000ac66  or      ecx, 80070000h
0x18000ac6c  test    ecx, ecx
0x18000ac6e  mov     eax, 80004005h
0x18000ac73  cmovns  ecx, eax
0x18000ac76  mov     eax, cs:dword_180062000
0x18000ac7c  cmp     eax, 2
0x18000ac7f  jbe     loc_18000AEAA
0x18000ac85  mov     rdx, cs:qword_180062018
0x18000ac8c  mov     rax, cs:qword_180062010
0x18000ac93  test    al, 8
0x18000ac95  jz      loc_18000AEAA
0x18000ac9b  mov     rax, rdx
0x18000ac9e  and     eax, 8
0x18000aca1  cmp     rax, rdx
0x18000aca4  jnz     loc_18000AEAA
0x18000acaa  lea     rax, [rbp+57h+var_70]
0x18000acae  mov     dword ptr [rbp+57h+var_70], ecx
0x18000acb1  mov     qword ptr [rsp+0B0h+dwFlagsAndAttributes], rax
0x18000acb6  lea     rdx, word_180057626
0x18000acbd  lea     rax, [rbp+57h+var_68]
0x18000acc1  mov     [rbp+57h+var_68], rdi
0x18000acc5  mov     qword ptr [rsp+0B0h+dwCreationDisposition], rax
0x18000acca  call    ??$Write@U?$_tlgWrapSz@_W@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &)
0x18000accf  jmp     loc_18000AEAA
0x18000acd4  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000acd8  inc     rax
0x18000acdb  cmp     [rdi+rax*2], r15w
0x18000ace0  jnz     short loc_18000ACD8
0x18000ace2  movzx   r14d, word ptr [rdi+rax*2-2]
0x18000ace8  mov     rdx, rsi
0x18000aceb  mov     rcx, rbx; hFile
0x18000acee  call    ?UtilGetFinalPathByHandle@_werDetail@@YAJPEAXAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; _werDetail::UtilGetFinalPathByHandle(void *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &)
0x18000acf3  mov     edx, eax
0x18000acf5  test    eax, eax
0x18000acf7  jns     short loc_18000AD6C
0x18000acf9  mov     eax, cs:dword_180062000
0x18000acff  cmp     eax, 2
0x18000ad02  jbe     loc_18000AEAA
0x18000ad08  mov     rcx, cs:qword_180062018
0x18000ad0f  mov     rax, cs:qword_180062010
0x18000ad16  test    al, 8
0x18000ad18  jz      loc_18000AEAA
0x18000ad1e  mov     rax, rcx
0x18000ad21  and     eax, 8
0x18000ad24  cmp     rax, rcx
0x18000ad27  jnz     loc_18000AEAA
0x18000ad2d  lea     rax, [rbp+57h+var_70]
0x18000ad31  mov     dword ptr [rbp+57h+var_70], edx
0x18000ad34  mov     [rbp+57h+var_40], rax
0x18000ad38  lea     rdx, byte_1800575FB
0x18000ad3f  lea     rax, [rbp+57h+var_60]
0x18000ad43  mov     [rbp+57h+var_38], 4
0x18000ad4b  mov     qword ptr [rsp+0B0h+dwFlagsAndAttributes], rax
0x18000ad50  lea     rcx, dword_180062000
0x18000ad57  xor     r9d, r9d
0x18000ad5a  mov     [rsp+0B0h+dwCreationDisposition], r13d
0x18000ad5f  xor     r8d, r8d
0x18000ad62  call    _tlgWriteTransfer_EventWriteTransfer
0x18000ad67  jmp     loc_18000AEAA
0x18000ad6c  mov     r13d, 5Ch ; '\'
0x18000ad72  cmp     r14w, r13w
0x18000ad76  jnz     short loc_18000ADA7
0x18000ad78  mov     rax, [rsi+8]
0x18000ad7c  cmp     [rsi], rax
0x18000ad7f  jz      short loc_18000AD88
0x18000ad81  cmp     r13w, [rax-2]
0x18000ad86  jz      short loc_18000ADA7
0x18000ad88  mov     edx, r13d
0x18000ad8b  mov     rcx, rsi
0x18000ad8e  call    ?push_back@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(wchar_t)
0x18000ad93  test    al, al
0x18000ad95  jnz     short loc_18000ADA7
0x18000ad97  mov     rcx, [rsi]
0x18000ad9a  mov     [rsi+8], rcx
0x18000ad9e  mov     [rcx], r15w
0x18000ada2  jmp     loc_18000AEAA
0x18000ada7  mov     rax, [rsi]
0x18000adaa  test    rax, rax
0x18000adad  jz      short loc_18000AE16
0x18000adaf  cmp     [rax], r13w
0x18000adb3  jnz     short loc_18000AE16
0x18000adb5  cmp     [rax+2], r13w
0x18000adba  jnz     short loc_18000AE16
0x18000adbc  cmp     word ptr [rax+4], 3Fh ; '?'
0x18000adc1  jnz     short loc_18000AE16
0x18000adc3  cmp     [rax+6], r13w
0x18000adc8  jnz     short loc_18000AE16
0x18000adca  mov     eax, cs:dword_180062000
0x18000add0  cmp     eax, 5
0x18000add3  jbe     short loc_18000AE0E
0x18000add5  mov     rcx, cs:qword_180062018
0x18000addc  mov     rax, cs:qword_180062010
0x18000ade3  test    al, 8
0x18000ade5  jz      short loc_18000AE0E
0x18000ade7  mov     rax, rcx
0x18000adea  and     eax, 8
0x18000aded  cmp     rax, rcx
0x18000adf0  jnz     short loc_18000AE0E
0x18000adf2  mov     rax, [rsi]
0x18000adf5  lea     rdx, byte_1800575BD
0x18000adfc  mov     [rbp+57h+var_68], rax
0x18000ae00  lea     rax, [rbp+57h+var_68]
0x18000ae04  mov     qword ptr [rsp+0B0h+dwCreationDisposition], rax
0x18000ae09  call    ??$Write@U?$_tlgWrapSz@_W@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &)
0x18000ae0e  mov     r14d, 4
0x18000ae14  jmp     short loc_18000AE19
0x18000ae16  mov     r14, r15
0x18000ae19  mov     eax, cs:dword_180062000
0x18000ae1f  cmp     eax, 5
0x18000ae22  jbe     short loc_18000AE6A
0x18000ae24  mov     rcx, cs:qword_180062018
0x18000ae2b  mov     rax, cs:qword_180062010
0x18000ae32  test    al, 8
0x18000ae34  jz      short loc_18000AE6A
0x18000ae36  mov     rax, rcx
0x18000ae39  and     eax, 8
0x18000ae3c  cmp     rax, rcx
0x18000ae3f  jnz     short loc_18000AE6A
0x18000ae41  mov     rax, [rsi]
0x18000ae44  lea     rdx, unk_180057578
0x18000ae4b  mov     [rbp+57h+var_68], rax
0x18000ae4f  lea     rax, [rbp+57h+var_68]
0x18000ae53  mov     qword ptr [rsp+0B0h+dwFlagsAndAttributes], rax
0x18000ae58  lea     rax, [rbp+57h+var_70]
0x18000ae5c  mov     qword ptr [rsp+0B0h+dwCreationDisposition], rax
0x18000ae61  mov     [rbp+57h+var_70], rdi
0x18000ae65  call    ??$Write@U?$_tlgWrapSz@_W@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<wchar_t> const &)
0x18000ae6a  mov     r8, [rsi+8]
0x18000ae6e  mov     rcx, rdi
0x18000ae71  sub     r8, [rsi]
0x18000ae74  mov     rdx, [rsi]
0x18000ae77  sar     r8, 1
0x18000ae7a  call    cs:__imp__o__wcsnicmp
0x18000ae80  test    eax, eax
0x18000ae82  jz      short loc_18000AEAA
0x18000ae84  mov     rax, [rsi]
0x18000ae87  mov     rcx, rdi
0x18000ae8a  mov     r8, [rsi+8]
0x18000ae8e  sub     r8, rax
0x18000ae91  sar     r8, 1
0x18000ae94  sub     r8, r14
0x18000ae97  lea     rdx, [rax+r14*2]
0x18000ae9b  call    cs:__imp__o__wcsnicmp
0x18000aea1  mov     edi, 1
0x18000aea6  test    eax, eax
0x18000aea8  jnz     short loc_18000AEAD
0x18000aeaa  mov     edi, r15d
0x18000aead  mov     eax, cs:dword_180062000
0x18000aeb3  cmp     eax, 4
0x18000aeb6  jbe     short loc_18000AEFD
0x18000aeb8  mov     rcx, cs:qword_180062018
0x18000aebf  mov     rax, cs:qword_180062010
0x18000aec6  test    al, 8
0x18000aec8  jz      short loc_18000AEFD
0x18000aeca  mov     rax, rcx
0x18000aecd  and     eax, 8
0x18000aed0  cmp     rax, rcx
0x18000aed3  jnz     short loc_18000AEFD
0x18000aed5  mov     rax, [rsi]
0x18000aed8  lea     rdx, word_18005753E
0x18000aedf  mov     [rbp+57h+var_68], rax
0x18000aee3  lea     rax, [rbp+57h+var_70]
0x18000aee7  mov     qword ptr [rsp+0B0h+dwFlagsAndAttributes], rax
0x18000aeec  lea     rax, [rbp+57h+var_68]
0x18000aef0  mov     qword ptr [rsp+0B0h+dwCreationDisposition], rax
0x18000aef5  mov     dword ptr [rbp+57h+var_70], edi
0x18000aef8  call    ??$Write@U?$_tlgWrapSz@_W@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &)
0x18000aefd  lea     rcx, [rbx+1]
0x18000af01  cmp     rcx, 1
0x18000af05  jbe     short loc_18000AF10
0x18000af07  mov     rcx, rbx; hObject
0x18000af0a  call    cs:__imp_CloseHandle
0x18000af10  mov     eax, edi
0x18000af12  mov     rcx, [rbp+57h+var_30]
0x18000af16  xor     rcx, rsp; StackCookie
0x18000af19  call    __security_check_cookie
0x18000af1e  lea     r11, [rsp+0B0h+var_20]
0x18000af26  mov     rbx, [r11+40h]
0x18000af2a  mov     rsi, [r11+48h]
0x18000af2e  mov     rsp, r11
0x18000af31  pop     r15
0x18000af33  pop     r14
0x18000af35  pop     r13
0x18000af37  pop     rdi
0x18000af38  pop     rbp
0x18000af39  retn
```
