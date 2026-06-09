# UtilGetTempDirPath(wchar_t *,ulong)

- ea: `0x18000b90c`
- end: `0x18000bc4c`
- name: `?UtilGetTempDirPath@@YAJPEA_WK@Z`
- size: `832`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, unsigned int)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, reparse_path`

## callers

- `0x18000a154`
- `0x18003cc4c`

## callees

- `0x18000113c`
- `0x18000134c`
- `0x180002890`
- `0x1800028b4`
- `0x18000ab9c`
- `0x18000b90c`
- `0x180049304`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b984`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bb07`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b984`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bb07`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18000b97a`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18000b97a`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18000b962`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18000b962`
- `api-ms-win-core-file-l1-2-3!GetTempPath2W` at `0x18000b947`
- `api-ms-win-core-file-l1-2-3!GetTempPath2W` at `0x18000b947`

## pseudocode

```c
__int64 __fastcall UtilGetTempDirPath(WCHAR *lpFileName)
{
  DWORD FileAttributesW; // eax
  signed int v3; // eax
  int v4; // r8d
  int v5; // r9d
  signed int v6; // ebx
  unsigned __int64 v7; // rbx
  unsigned __int64 v8; // rbx
  signed int LastError; // eax
  __int64 v10; // rcx
  int v12; // [rsp+30h] [rbp-39h] BYREF
  WCHAR *v13; // [rsp+38h] [rbp-31h] BYREF
  void *Src; // [rsp+40h] [rbp-29h]
  char *v15; // [rsp+48h] [rbp-21h]
  _WORD v16[8]; // [rsp+50h] [rbp-19h] BYREF
  _BYTE v17[32]; // [rsp+60h] [rbp-9h] BYREF
  int *v18; // [rsp+80h] [rbp+17h]
  __int64 v19; // [rsp+88h] [rbp+1Fh]

  if ( lpFileName )
  {
    *lpFileName = 0;
    if ( !(unsigned int)GetTempPath2W(260, lpFileName) || !*lpFileName )
    {
      LastError = GetLastError();
      v6 = LastError;
      if ( LastError > 0 )
        v6 = (unsigned __int16)LastError | 0x80070000;
      if ( v6 >= 0 )
        v6 = -2147467259;
      if ( (unsigned int)dword_180062000 > 2 && (qword_180062010 & 8) != 0 && (qword_180062018 & 8) == qword_180062018 )
      {
        v12 = v6;
        v18 = &v12;
        v19 = 4;
        tlgWriteTransfer_EventWriteTransfer(&dword_180062000, &unk_1800574E0, 0, 0, 3, v17);
      }
      goto LABEL_36;
    }
    FileAttributesW = GetFileAttributesW(lpFileName);
    if ( (FileAttributesW == -1 || (FileAttributesW & 0x10) == 0) && !CreateDirectoryW(lpFileName, 0) )
    {
      v3 = GetLastError();
      v6 = v3;
      if ( v3 > 0 )
        v6 = (unsigned __int16)v3 | 0x80070000;
      if ( v6 >= 0 )
        v6 = -2147467259;
      if ( (unsigned int)dword_180062000 > 2 && (qword_180062010 & 8) != 0 && (qword_180062018 & 8) == qword_180062018 )
      {
        v12 = v6;
        v13 = lpFileName;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>>(
          qword_180062018,
          (unsigned int)&unk_18005749C,
          v4,
          v5,
          (__int64)&v13,
          (__int64)&v12);
      }
      *lpFileName = 0;
LABEL_36:
      if ( (unsigned int)dword_180062000 > 2 && (qword_180062010 & 8) != 0 )
      {
        v10 = qword_180062018 & 8;
        if ( v10 == qword_180062018 )
        {
          v12 = v6;
          v13 = lpFileName;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>>(
            v10,
            (unsigned int)&unk_18005742F,
            v4,
            v5,
            (__int64)&v13,
            (__int64)&v12);
        }
      }
      return (unsigned int)v6;
    }
    v16[0] = 0;
    Src = v16;
    v15 = (char *)v16;
    if ( (unsigned int)UtilGetFinalPath(lpFileName) )
    {
      v7 = (v15 - (_BYTE *)Src) >> 1;
      if ( v7 >= 0x104 )
      {
        *lpFileName = 0;
        v6 = -2147024809;
        if ( (unsigned int)dword_180062000 > 2 && (qword_180062010 & 8) != 0 && (qword_180062018 & 8) == qword_180062018 )
        {
          v12 = -2147024809;
          v18 = &v12;
          v19 = 4;
          tlgWriteTransfer_EventWriteTransfer(&dword_180062000, &unk_180057468, 0, 0, 3, v17);
        }
        if ( Src != v16 )
          operator delete(Src, (const struct std::nothrow_t *)&std::nothrow);
        goto LABEL_36;
      }
      v8 = v7;
      memcpy_0(lpFileName, Src, v8 * 2);
      lpFileName[v8] = 0;
    }
    if ( Src != v16 )
      operator delete(Src, (const struct std::nothrow_t *)&std::nothrow);
    v6 = 0;
    goto LABEL_36;
  }
  if ( (unsigned int)dword_180062000 > 2 && (qword_180062010 & 8) != 0 && (qword_180062018 & 8) == qword_180062018 )
    tlgWriteTransfer_EventWriteTransfer(&dword_180062000, &unk_180057514, 0, 0, 2, v17);
  return 2147942487LL;
}

```

## disassembly

```asm
0x18000b90c  push    rbp
0x18000b90e  push    rbx
0x18000b90f  push    rdi
0x18000b910  push    r14
0x18000b912  lea     rbp, [rsp-3Fh]
0x18000b917  sub     rsp, 0A8h
0x18000b91e  mov     rax, cs:__security_cookie
0x18000b925  xor     rax, rsp
0x18000b928  mov     [rbp+57h+var_30], rax
0x18000b92c  xor     r14d, r14d
0x18000b92f  mov     rdi, rcx
0x18000b932  test    rcx, rcx
0x18000b935  jz      loc_18000BBDC
0x18000b93b  mov     [rcx], r14w
0x18000b93f  mov     rdx, rcx
0x18000b942  mov     ecx, 104h
0x18000b947  call    cs:__imp_GetTempPath2W
0x18000b94d  test    eax, eax
0x18000b94f  jz      loc_18000BB07
0x18000b955  cmp     [rdi], r14w
0x18000b959  jz      loc_18000BB07
0x18000b95f  mov     rcx, rdi; lpFileName
0x18000b962  call    cs:__imp_GetFileAttributesW
0x18000b968  cmp     eax, 0FFFFFFFFh
0x18000b96b  jz      short loc_18000B975
0x18000b96d  test    al, 10h
0x18000b96f  jnz     loc_18000B9F9
0x18000b975  xor     edx, edx; lpSecurityAttributes
0x18000b977  mov     rcx, rdi; lpPathName
0x18000b97a  call    cs:__imp_CreateDirectoryW
0x18000b980  test    eax, eax
0x18000b982  jnz     short loc_18000B9F9
0x18000b984  call    cs:__imp_GetLastError
0x18000b98a  mov     ebx, eax
0x18000b98c  test    eax, eax
0x18000b98e  jle     short loc_18000B999
0x18000b990  movzx   ebx, ax
0x18000b993  or      ebx, 80070000h
0x18000b999  test    ebx, ebx
0x18000b99b  mov     eax, 80004005h
0x18000b9a0  cmovns  ebx, eax
0x18000b9a3  mov     eax, cs:dword_180062000
0x18000b9a9  cmp     eax, 2
0x18000b9ac  jbe     short loc_18000B9F0
0x18000b9ae  mov     rcx, cs:qword_180062018
0x18000b9b5  mov     rax, cs:qword_180062010
0x18000b9bc  test    al, 8
0x18000b9be  jz      short loc_18000B9F0
0x18000b9c0  mov     rax, rcx
0x18000b9c3  and     eax, 8
0x18000b9c6  cmp     rax, rcx
0x18000b9c9  jnz     short loc_18000B9F0
0x18000b9cb  lea     rax, [rbp+57h+var_90]
0x18000b9cf  mov     [rbp+57h+var_90], ebx
0x18000b9d2  mov     [rsp+0C0h+var_98], rax
0x18000b9d7  lea     rdx, unk_18005749C
0x18000b9de  lea     rax, [rbp+57h+var_88]
0x18000b9e2  mov     [rbp+57h+var_88], rdi
0x18000b9e6  mov     [rsp+0C0h+var_A0], rax
0x18000b9eb  call    ??$Write@U?$_tlgWrapSz@_W@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &)
0x18000b9f0  mov     [rdi], r14w
0x18000b9f4  jmp     loc_18000BB8B
0x18000b9f9  lea     rax, [rbp+57h+var_70]
0x18000b9fd  mov     [rbp+57h+var_70], r14w
0x18000ba02  mov     [rbp+57h+Src], rax
0x18000ba06  lea     rdx, [rbp+57h+Src]
0x18000ba0a  lea     rax, [rbp+57h+var_70]
0x18000ba0e  mov     rcx, rdi; lpFileName
0x18000ba11  mov     [rbp+57h+var_78], rax
0x18000ba15  call    ?UtilGetFinalPath@@YAHPEB_WAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; UtilGetFinalPath(wchar_t const *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &)
0x18000ba1a  test    eax, eax
0x18000ba1c  jz      loc_18000BAE5
0x18000ba22  mov     rbx, [rbp+57h+var_78]
0x18000ba26  sub     rbx, [rbp+57h+Src]
0x18000ba2a  sar     rbx, 1
0x18000ba2d  cmp     rbx, 104h
0x18000ba34  jb      loc_18000BACE
0x18000ba3a  mov     [rdi], r14w
0x18000ba3e  mov     ebx, 80070057h
0x18000ba43  mov     eax, cs:dword_180062000
0x18000ba49  cmp     eax, 2
0x18000ba4c  jbe     short loc_18000BAAC
0x18000ba4e  mov     rcx, cs:qword_180062018
0x18000ba55  mov     rax, cs:qword_180062010
0x18000ba5c  test    al, 8
0x18000ba5e  jz      short loc_18000BAAC
0x18000ba60  mov     rax, rcx
0x18000ba63  and     eax, 8
0x18000ba66  cmp     rax, rcx
0x18000ba69  jnz     short loc_18000BAAC
0x18000ba6b  lea     rax, [rbp+57h+var_90]
0x18000ba6f  mov     [rbp+57h+var_90], 80070057h
0x18000ba76  mov     [rbp+57h+var_40], rax
0x18000ba7a  lea     rdx, unk_180057468
0x18000ba81  lea     rax, [rbp+57h+var_60]
0x18000ba85  mov     [rbp+57h+var_38], 4
0x18000ba8d  mov     [rsp+0C0h+var_98], rax
0x18000ba92  lea     rcx, dword_180062000
0x18000ba99  xor     r9d, r9d
0x18000ba9c  mov     dword ptr [rsp+0C0h+var_A0], 3
0x18000baa4  xor     r8d, r8d
0x18000baa7  call    _tlgWriteTransfer_EventWriteTransfer
0x18000baac  mov     rcx, [rbp+57h+Src]; void *
0x18000bab0  lea     rax, [rbp+57h+var_70]
0x18000bab4  cmp     rcx, rax
0x18000bab7  jz      loc_18000BB8B
0x18000babd  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000bac4  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000bac9  jmp     loc_18000BB8B
0x18000bace  mov     rdx, [rbp+57h+Src]; Src
0x18000bad2  add     rbx, rbx
0x18000bad5  mov     r8, rbx; Size
0x18000bad8  mov     rcx, rdi; void *
0x18000badb  call    memcpy_0
0x18000bae0  mov     [rbx+rdi], r14w
0x18000bae5  lea     rax, [rbp+57h+var_70]
0x18000bae9  cmp     [rbp+57h+Src], rax
0x18000baed  jz      short loc_18000BAFF
0x18000baef  mov     rcx, [rbp+57h+Src]; void *
0x18000baf3  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000bafa  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000baff  mov     ebx, r14d
0x18000bb02  jmp     loc_18000BB8B
0x18000bb07  call    cs:__imp_GetLastError
0x18000bb0d  mov     ebx, eax
0x18000bb0f  test    eax, eax
0x18000bb11  jle     short loc_18000BB1C
0x18000bb13  movzx   ebx, ax
0x18000bb16  or      ebx, 80070000h
0x18000bb1c  test    ebx, ebx
0x18000bb1e  mov     eax, 80004005h
0x18000bb23  cmovns  ebx, eax
0x18000bb26  mov     eax, cs:dword_180062000
0x18000bb2c  cmp     eax, 2
0x18000bb2f  jbe     short loc_18000BB8B
0x18000bb31  mov     rcx, cs:qword_180062018
0x18000bb38  mov     rax, cs:qword_180062010
0x18000bb3f  test    al, 8
0x18000bb41  jz      short loc_18000BB8B
0x18000bb43  mov     rax, rcx
0x18000bb46  and     eax, 8
0x18000bb49  cmp     rax, rcx
0x18000bb4c  jnz     short loc_18000BB8B
0x18000bb4e  lea     rax, [rbp+57h+var_90]
0x18000bb52  mov     [rbp+57h+var_90], ebx
0x18000bb55  mov     [rbp+57h+var_40], rax
0x18000bb59  lea     rdx, unk_1800574E0
0x18000bb60  lea     rax, [rbp+57h+var_60]
0x18000bb64  mov     [rbp+57h+var_38], 4
0x18000bb6c  mov     [rsp+0C0h+var_98], rax
0x18000bb71  lea     rcx, dword_180062000
0x18000bb78  xor     r9d, r9d
0x18000bb7b  mov     dword ptr [rsp+0C0h+var_A0], 3
0x18000bb83  xor     r8d, r8d
0x18000bb86  call    _tlgWriteTransfer_EventWriteTransfer
0x18000bb8b  mov     eax, cs:dword_180062000
0x18000bb91  cmp     eax, 2
0x18000bb94  jbe     short loc_18000BBD8
0x18000bb96  mov     rdx, cs:qword_180062018
0x18000bb9d  mov     rax, cs:qword_180062010
0x18000bba4  test    al, 8
0x18000bba6  jz      short loc_18000BBD8
0x18000bba8  mov     rcx, rdx
0x18000bbab  and     ecx, 8
0x18000bbae  cmp     rcx, rdx
0x18000bbb1  jnz     short loc_18000BBD8
0x18000bbb3  lea     rax, [rbp+57h+var_90]
0x18000bbb7  mov     [rbp+57h+var_90], ebx
0x18000bbba  mov     [rsp+0C0h+var_98], rax
0x18000bbbf  lea     rdx, unk_18005742F
0x18000bbc6  lea     rax, [rbp+57h+var_88]
0x18000bbca  mov     [rbp+57h+var_88], rdi
0x18000bbce  mov     [rsp+0C0h+var_A0], rax
0x18000bbd3  call    ??$Write@U?$_tlgWrapSz@_W@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &)
0x18000bbd8  mov     eax, ebx
0x18000bbda  jmp     short loc_18000BC33
0x18000bbdc  mov     eax, cs:dword_180062000
0x18000bbe2  cmp     eax, 2
0x18000bbe5  jbe     short loc_18000BC2E
0x18000bbe7  mov     rcx, cs:qword_180062018
0x18000bbee  mov     rax, cs:qword_180062010
0x18000bbf5  test    al, 8
0x18000bbf7  jz      short loc_18000BC2E
0x18000bbf9  mov     rax, rcx
0x18000bbfc  and     eax, 8
0x18000bbff  cmp     rax, rcx
0x18000bc02  jnz     short loc_18000BC2E
0x18000bc04  lea     rax, [rbp+57h+var_60]
0x18000bc08  xor     r9d, r9d
0x18000bc0b  mov     [rsp+0C0h+var_98], rax
0x18000bc10  lea     rdx, unk_180057514
0x18000bc17  xor     r8d, r8d
0x18000bc1a  mov     dword ptr [rsp+0C0h+var_A0], 2
0x18000bc22  lea     rcx, dword_180062000
0x18000bc29  call    _tlgWriteTransfer_EventWriteTransfer
0x18000bc2e  mov     eax, 80070057h
0x18000bc33  mov     rcx, [rbp+57h+var_30]
0x18000bc37  xor     rcx, rsp; StackCookie
0x18000bc3a  call    __security_check_cookie
0x18000bc3f  add     rsp, 0A8h
0x18000bc46  pop     r14
0x18000bc48  pop     rdi
0x18000bc49  pop     rbx
0x18000bc4a  pop     rbp
0x18000bc4b  retn
```
