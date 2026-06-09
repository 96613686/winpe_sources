# CDriverV2::CreateSharedBuffer(ushort *,ulong,ushort *,uchar * *,void * *)

- ea: `0x1800be544`
- end: `0x1800be970`
- name: `?CreateSharedBuffer@CDriverV2@@IEAAJPEAGK0PEAPEAEPEAPEAX@Z`
- size: `1068`
- prototype: `__int64 __fastcall(CDriverV2 *this, unsigned __int16 *, __int64, unsigned __int16 *, unsigned __int8 **, void **)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x1800be0d4`

## callees

- `0x1800014d8`
- `0x1800015f0`
- `0x180009088`
- `0x180009628`
- `0x18000ee00`
- `0x180033da0`
- `0x180034970`
- `0x1800be544`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800be62a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800be6a5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800be62a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800be6a5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800be93e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800be93e`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x1800be693`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x1800be693`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x1800be61c`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x1800be61c`

## string_xrefs

- `0x1800be5a1`: `RdpUpdateBuffer`
- `0x1800be783`: `Failed to create mapping`
- `0x1800be6c9`: `CreateSharedBuffer`
- `0x1800be758`: `CreateSharedBuffer`
- `0x1800be843`: `CreateSharedBuffer`
- `0x1800be8cd`: `CreateSharedBuffer`

## pseudocode

```c
__int64 __fastcall CDriverV2::CreateSharedBuffer(
        CDriverV2 *this,
        unsigned __int16 *a2,
        __int64 a3,
        unsigned __int16 *a4,
        unsigned __int8 **a5,
        void **a6)
{
  int i; // esi
  int v9; // ecx
  unsigned int v10; // ebx
  int v11; // r8d
  int v12; // r9d
  HANDLE FileMappingW; // rdi
  signed int v14; // eax
  int v15; // r8d
  int v16; // r9d
  int v17; // ecx
  unsigned __int8 *v18; // rbx
  int v19; // r8d
  int v20; // r9d
  signed int LastError; // eax
  int v22; // ecx
  int v23; // r8d
  int v24; // r9d
  char *v25; // rdx
  const char **v26; // rax
  DWORD dwMaximumSizeLow[2]; // [rsp+20h] [rbp-E0h]
  LPCWSTR lpName; // [rsp+28h] [rbp-D8h]
  const char **v30; // [rsp+30h] [rbp-D0h]
  const char **v31; // [rsp+40h] [rbp-C0h]
  const char **v32; // [rsp+48h] [rbp-B8h]
  int v33; // [rsp+50h] [rbp-B0h] BYREF
  const char *v34; // [rsp+58h] [rbp-A8h] BYREF
  const char *v35; // [rsp+60h] [rbp-A0h] BYREF
  const char *v36; // [rsp+68h] [rbp-98h] BYREF
  const char *v37; // [rsp+70h] [rbp-90h] BYREF
  const char *v38; // [rsp+78h] [rbp-88h] BYREF
  WCHAR Name[264]; // [rsp+80h] [rbp-80h] BYREF

  memset_0(Name, 0, 0x208u);
  for ( i = 0; ; ++i )
  {
    while ( 1 )
    {
      LODWORD(lpName) = i;
      dwMaximumSizeLow[0] = *((_DWORD *)this + 14);
      v10 = StringCchPrintfW(a4, 0x104u, L"%s-Session%d-%d", L"RdpUpdateBuffer", *(_QWORD *)dwMaximumSizeLow, lpName);
      if ( (v10 & 0x80000000) != 0 )
      {
        if ( (unsigned int)dword_1801B76C8 <= 2 )
          return v10;
        LODWORD(v34) = 901;
        v38 = "Failed to print shared buffer name";
        v25 = byte_1801A6B73;
        v35 = "CreateSharedBuffer";
        v37 = "clientcore\\termsrv\\rdpplatform\\gfxpipe\\gfxsource\\driverv2.cpp";
        v36 = "Error HResult failed";
        v32 = &v38;
        v31 = &v35;
        v30 = &v37;
        v26 = &v36;
        goto LABEL_25;
      }
      v10 = StringCchPrintfW(Name, 0x104u, L"%s%s", L"Global\\", a4);
      if ( (v10 & 0x80000000) != 0 )
      {
        if ( (unsigned int)dword_1801B76C8 <= 2 )
          return v10;
        LODWORD(v34) = 913;
        v35 = "Failed to print shared buffer name for mapping";
        v25 = byte_1801A6AB1;
        v37 = "CreateSharedBuffer";
        v36 = "clientcore\\termsrv\\rdpplatform\\gfxpipe\\gfxsource\\driverv2.cpp";
        v38 = "Error HResult failed";
        v32 = &v35;
        v31 = &v37;
        v30 = &v36;
        v26 = &v38;
LABEL_25:
        v33 = v10;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
          v9,
          (_DWORD)v25,
          v11,
          v12,
          (__int64)v26,
          (__int64)&v33,
          (__int64)v30,
          (__int64)&v34,
          (__int64)v31,
          (__int64)v32);
        return v10;
      }
      FileMappingW = CreateFileMappingW(
                       (HANDLE)0xFFFFFFFFFFFFFFFFLL,
                       (LPSECURITY_ATTRIBUTES)((char *)this + 680),
                       4u,
                       0,
                       0x100000u,
                       Name);
      if ( !FileMappingW )
        break;
LABEL_8:
      ++i;
      if ( FileMappingW )
      {
        v18 = (unsigned __int8 *)MapViewOfFile(FileMappingW, 6u, 0, 0, 0x100000u);
        if ( v18 )
        {
          if ( (unsigned int)dword_1801B76C8 > 4 )
          {
            LODWORD(v34) = 0x100000;
            v35 = "Mapped Shared Buffer";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
              v17,
              (unsigned int)&byte_1801A699F,
              v19,
              v20,
              (__int64)&v35,
              (__int64)&v34);
          }
          *a5 = v18;
          v10 = 0;
          *a6 = FileMappingW;
        }
        else
        {
          LastError = GetLastError();
          v10 = LastError;
          if ( LastError > 0 )
            v10 = (unsigned __int16)LastError | 0x80070000;
          if ( (unsigned int)dword_1801B76C8 > 2 )
          {
            LODWORD(v34) = 954;
            v35 = "CreateSharedBuffer";
            v33 = v10;
            v37 = "clientcore\\termsrv\\rdpplatform\\gfxpipe\\gfxsource\\driverv2.cpp";
            v36 = "Could not map view of file";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
              v22,
              (unsigned int)&byte_1801A6A67,
              v23,
              v24,
              (__int64)&v36,
              (__int64)&v33,
              (__int64)&v37,
              (__int64)&v34,
              (__int64)&v35);
          }
          CloseHandle(FileMappingW);
        }
        return v10;
      }
    }
    v14 = GetLastError();
    v10 = v14;
    if ( (unsigned int)(v14 - 5) > 1 )
      break;
    if ( (unsigned int)dword_1801B76C8 <= 3 )
      goto LABEL_8;
    v34 = "Shared buffer name conflict!  Renaming";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
      dword_1801B76C8,
      (unsigned int)byte_1801A6B03,
      v15,
      v16,
      (__int64)&v34);
  }
  if ( v14 > 0 )
    v10 = (unsigned __int16)v14 | 0x80070000;
  if ( (unsigned int)dword_1801B76C8 > 2 )
  {
    v33 = 938;
    v36 = "CreateSharedBuffer";
    LODWORD(v34) = v10;
    v37 = "clientcore\\termsrv\\rdpplatform\\gfxpipe\\gfxsource\\driverv2.cpp";
    v35 = "Failed to create mapping";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
      v14 - 5,
      (unsigned int)byte_1801A6A1D,
      v15,
      v16,
      (__int64)&v35,
      (__int64)&v34,
      (__int64)&v37,
      (__int64)&v33,
      (__int64)&v36);
  }
  return v10;
}

```

## disassembly

```asm
0x1800be544  mov     [rsp-8+arg_8], rbx
0x1800be549  push    rbp
0x1800be54a  push    rsi
0x1800be54b  push    rdi
0x1800be54c  push    r12
0x1800be54e  push    r13
0x1800be550  push    r14
0x1800be552  push    r15
0x1800be554  lea     rbp, [rsp-1A0h]
0x1800be55c  sub     rsp, 2A0h
0x1800be563  mov     rax, cs:__security_cookie
0x1800be56a  xor     rax, rsp
0x1800be56d  mov     [rbp+1D0h+var_40], rax
0x1800be574  mov     r12, [rbp+1D0h+arg_20]
0x1800be57b  mov     r14, rcx
0x1800be57e  mov     r13, [rbp+1D0h+arg_28]
0x1800be585  lea     rcx, [rbp+1D0h+Name]; void *
0x1800be589  xor     edx, edx; Val
0x1800be58b  mov     r8d, 208h; Size
0x1800be591  mov     r15, r9
0x1800be594  xor     edi, edi
0x1800be596  call    memset_0
0x1800be59b  xor     esi, esi
0x1800be59d  mov     eax, [r14+38h]
0x1800be5a1  lea     r9, aRdpupdatebuffe_0; "RdpUpdateBuffer"
0x1800be5a8  mov     dword ptr [rsp+2D0h+lpName], esi
0x1800be5ac  lea     r8, aSSessionDD; "%s-Session%d-%d"
0x1800be5b3  mov     edx, 104h; unsigned __int64
0x1800be5b8  mov     [rsp+2D0h+dwMaximumSizeLow], eax
0x1800be5bc  mov     rcx, r15; unsigned __int16 *
0x1800be5bf  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800be5c4  mov     ebx, eax
0x1800be5c6  test    eax, eax
0x1800be5c8  js      loc_1800BE8A3
0x1800be5ce  lea     r9, aGlobal; "Global\\"
0x1800be5d5  mov     qword ptr [rsp+2D0h+dwMaximumSizeLow], r15
0x1800be5da  lea     r8, aSS_0; "%s%s"
0x1800be5e1  mov     edx, 104h; unsigned __int64
0x1800be5e6  lea     rcx, [rbp+1D0h+Name]; unsigned __int16 *
0x1800be5ea  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800be5ef  mov     ebx, eax
0x1800be5f1  test    eax, eax
0x1800be5f3  js      loc_1800BE819
0x1800be5f9  xor     r9d, r9d; dwMaximumSizeHigh
0x1800be5fc  lea     rax, [rbp+1D0h+Name]
0x1800be600  mov     [rsp+2D0h+lpName], rax; lpName
0x1800be605  lea     rdx, [r14+2A8h]; lpFileMappingAttributes
0x1800be60c  or      rcx, 0FFFFFFFFFFFFFFFFh; hFile
0x1800be610  mov     [rsp+2D0h+dwMaximumSizeLow], 100000h; dwMaximumSizeLow
0x1800be618  lea     r8d, [r9+4]; flProtect
0x1800be61c  call    cs:__imp_CreateFileMappingW
0x1800be622  mov     rdi, rax
0x1800be625  test    rax, rax
0x1800be628  jnz     short loc_1800BE672
0x1800be62a  call    cs:__imp_GetLastError
0x1800be630  mov     ebx, eax
0x1800be632  lea     ecx, [rax-5]
0x1800be635  cmp     ecx, 1
0x1800be638  ja      loc_1800BE73C
0x1800be63e  mov     ecx, cs:dword_1801B76C8
0x1800be644  cmp     ecx, 3
0x1800be647  jbe     short loc_1800BE672
0x1800be649  lea     rax, aSharedBufferNa; "Shared buffer name conflict!  Renaming"
0x1800be650  mov     [rsp+2D0h+var_278], rax
0x1800be655  lea     rdx, byte_1801A6B03
0x1800be65c  lea     rax, [rsp+2D0h+var_278]
0x1800be661  mov     qword ptr [rsp+2D0h+dwMaximumSizeLow], rax
0x1800be666  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x1800be66b  inc     esi
0x1800be66d  jmp     loc_1800BE59D
0x1800be672  inc     esi
0x1800be674  test    rdi, rdi
0x1800be677  jz      loc_1800BE59D
0x1800be67d  xor     r9d, r9d; dwFileOffsetLow
0x1800be680  mov     qword ptr [rsp+2D0h+dwMaximumSizeLow], 100000h; dwNumberOfBytesToMap
0x1800be689  xor     r8d, r8d; dwFileOffsetHigh
0x1800be68c  mov     rcx, rdi; hFileMappingObject
0x1800be68f  lea     edx, [r9+6]; dwDesiredAccess
0x1800be693  call    cs:__imp_MapViewOfFile
0x1800be699  mov     rbx, rax
0x1800be69c  test    rax, rax
0x1800be69f  jnz     loc_1800BE7CB
0x1800be6a5  call    cs:__imp_GetLastError
0x1800be6ab  mov     ebx, eax
0x1800be6ad  test    eax, eax
0x1800be6af  jle     short loc_1800BE6BA
0x1800be6b1  movzx   ebx, ax
0x1800be6b4  or      ebx, 80070000h
0x1800be6ba  mov     eax, cs:dword_1801B76C8
0x1800be6c0  cmp     eax, 2
0x1800be6c3  jbe     loc_1800BE93B
0x1800be6c9  lea     rax, aCreatesharedbu; "CreateSharedBuffer"
0x1800be6d0  mov     dword ptr [rsp+2D0h+var_278], 3BAh
0x1800be6d8  mov     [rsp+2D0h+var_270], rax
0x1800be6dd  lea     rdx, byte_1801A6A67
0x1800be6e4  lea     rax, aClientcoreTerm_5; "clientcore\\termsrv\\rdpplatform\\gfxpi"...
0x1800be6eb  mov     [rsp+2D0h+var_280], ebx
0x1800be6ef  mov     [rsp+2D0h+var_260], rax
0x1800be6f4  lea     rax, aCouldNotMapVie; "Could not map view of file"
0x1800be6fb  mov     [rsp+2D0h+var_268], rax
0x1800be700  lea     rax, [rsp+2D0h+var_270]
0x1800be705  mov     [rsp+2D0h+var_290], rax
0x1800be70a  lea     rax, [rsp+2D0h+var_278]
0x1800be70f  mov     [rsp+2D0h+var_298], rax
0x1800be714  lea     rax, [rsp+2D0h+var_260]
0x1800be719  mov     [rsp+2D0h+var_2A0], rax
0x1800be71e  lea     rax, [rsp+2D0h+var_280]
0x1800be723  mov     [rsp+2D0h+lpName], rax
0x1800be728  lea     rax, [rsp+2D0h+var_268]
0x1800be72d  mov     qword ptr [rsp+2D0h+dwMaximumSizeLow], rax
0x1800be732  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x1800be737  jmp     loc_1800BE93B
0x1800be73c  test    eax, eax
0x1800be73e  jle     short loc_1800BE749
0x1800be740  movzx   ebx, ax
0x1800be743  or      ebx, 80070000h
0x1800be749  mov     eax, cs:dword_1801B76C8
0x1800be74f  cmp     eax, 2
0x1800be752  jbe     loc_1800BE944
0x1800be758  lea     rax, aCreatesharedbu; "CreateSharedBuffer"
0x1800be75f  mov     [rsp+2D0h+var_280], 3AAh
0x1800be767  mov     [rsp+2D0h+var_268], rax
0x1800be76c  lea     rdx, byte_1801A6A1D
0x1800be773  lea     rax, aClientcoreTerm_5; "clientcore\\termsrv\\rdpplatform\\gfxpi"...
0x1800be77a  mov     dword ptr [rsp+2D0h+var_278], ebx
0x1800be77e  mov     [rsp+2D0h+var_260], rax
0x1800be783  lea     rax, aFailedToCreate_30; "Failed to create mapping"
0x1800be78a  mov     [rsp+2D0h+var_270], rax
0x1800be78f  lea     rax, [rsp+2D0h+var_268]
0x1800be794  mov     [rsp+2D0h+var_290], rax
0x1800be799  lea     rax, [rsp+2D0h+var_280]
0x1800be79e  mov     [rsp+2D0h+var_298], rax
0x1800be7a3  lea     rax, [rsp+2D0h+var_260]
0x1800be7a8  mov     [rsp+2D0h+var_2A0], rax
0x1800be7ad  lea     rax, [rsp+2D0h+var_278]
0x1800be7b2  mov     [rsp+2D0h+lpName], rax
0x1800be7b7  lea     rax, [rsp+2D0h+var_270]
0x1800be7bc  mov     qword ptr [rsp+2D0h+dwMaximumSizeLow], rax
0x1800be7c1  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x1800be7c6  jmp     loc_1800BE944
0x1800be7cb  mov     eax, cs:dword_1801B76C8
0x1800be7d1  cmp     eax, 4
0x1800be7d4  jbe     short loc_1800BE80A
0x1800be7d6  lea     rax, aMappedSharedBu; "Mapped Shared Buffer"
0x1800be7dd  mov     dword ptr [rsp+2D0h+var_278], 100000h
0x1800be7e5  mov     [rsp+2D0h+var_270], rax
0x1800be7ea  lea     rdx, byte_1801A699F
0x1800be7f1  lea     rax, [rsp+2D0h+var_278]
0x1800be7f6  mov     [rsp+2D0h+lpName], rax
0x1800be7fb  lea     rax, [rsp+2D0h+var_270]
0x1800be800  mov     qword ptr [rsp+2D0h+dwMaximumSizeLow], rax
0x1800be805  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1800be80a  mov     [r12], rbx
0x1800be80e  xor     ebx, ebx
0x1800be810  mov     [r13+0], rdi
0x1800be814  jmp     loc_1800BE944
0x1800be819  mov     eax, cs:dword_1801B76C8
0x1800be81f  cmp     eax, 2
0x1800be822  jbe     loc_1800BE936
0x1800be828  lea     rax, aFailedToPrintS; "Failed to print shared buffer name for "...
0x1800be82f  mov     dword ptr [rsp+2D0h+var_278], 391h
0x1800be837  mov     [rsp+2D0h+var_270], rax
0x1800be83c  lea     rdx, byte_1801A6AB1
0x1800be843  lea     rax, aCreatesharedbu; "CreateSharedBuffer"
0x1800be84a  mov     [rsp+2D0h+var_260], rax
0x1800be84f  lea     rax, aClientcoreTerm_5; "clientcore\\termsrv\\rdpplatform\\gfxpi"...
0x1800be856  mov     [rsp+2D0h+var_268], rax
0x1800be85b  lea     rax, aErrorHresultFa; "Error HResult failed"
0x1800be862  mov     [rsp+2D0h+var_258], rax
0x1800be867  lea     rax, [rsp+2D0h+var_270]
0x1800be86c  mov     [rsp+2D0h+var_288], rax
0x1800be871  lea     rax, [rsp+2D0h+var_260]
0x1800be876  mov     [rsp+2D0h+var_290], rax
0x1800be87b  lea     rax, [rsp+2D0h+var_278]
0x1800be880  mov     [rsp+2D0h+var_298], rax
0x1800be885  lea     rax, [rsp+2D0h+var_268]
0x1800be88a  mov     [rsp+2D0h+var_2A0], rax
0x1800be88f  lea     rax, [rsp+2D0h+var_280]
0x1800be894  mov     [rsp+2D0h+lpName], rax
0x1800be899  lea     rax, [rsp+2D0h+var_258]
0x1800be89e  jmp     loc_1800BE928
0x1800be8a3  mov     eax, cs:dword_1801B76C8
0x1800be8a9  cmp     eax, 2
0x1800be8ac  jbe     loc_1800BE936
0x1800be8b2  lea     rax, aFailedToPrintS_0; "Failed to print shared buffer name"
0x1800be8b9  mov     dword ptr [rsp+2D0h+var_278], 385h
0x1800be8c1  mov     [rsp+2D0h+var_258], rax
0x1800be8c6  lea     rdx, byte_1801A6B73
0x1800be8cd  lea     rax, aCreatesharedbu; "CreateSharedBuffer"
0x1800be8d4  mov     [rsp+2D0h+var_270], rax
0x1800be8d9  lea     rax, aClientcoreTerm_5; "clientcore\\termsrv\\rdpplatform\\gfxpi"...
0x1800be8e0  mov     [rsp+2D0h+var_260], rax
0x1800be8e5  lea     rax, aErrorHresultFa; "Error HResult failed"
0x1800be8ec  mov     [rsp+2D0h+var_268], rax
0x1800be8f1  lea     rax, [rsp+2D0h+var_258]
0x1800be8f6  mov     [rsp+2D0h+var_288], rax
0x1800be8fb  lea     rax, [rsp+2D0h+var_270]
0x1800be900  mov     [rsp+2D0h+var_290], rax
0x1800be905  lea     rax, [rsp+2D0h+var_278]
0x1800be90a  mov     [rsp+2D0h+var_298], rax
0x1800be90f  lea     rax, [rsp+2D0h+var_260]
0x1800be914  mov     [rsp+2D0h+var_2A0], rax
0x1800be919  lea     rax, [rsp+2D0h+var_280]
0x1800be91e  mov     [rsp+2D0h+lpName], rax
0x1800be923  lea     rax, [rsp+2D0h+var_268]
0x1800be928  mov     qword ptr [rsp+2D0h+dwMaximumSizeLow], rax
0x1800be92d  mov     [rsp+2D0h+var_280], ebx
0x1800be931  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x1800be936  test    rdi, rdi
0x1800be939  jz      short loc_1800BE944
0x1800be93b  mov     rcx, rdi; hObject
0x1800be93e  call    cs:__imp_CloseHandle
0x1800be944  mov     eax, ebx
0x1800be946  mov     rcx, [rbp+1D0h+var_40]
0x1800be94d  xor     rcx, rsp; StackCookie
0x1800be950  call    __security_check_cookie
0x1800be955  mov     rbx, [rsp+2D0h+arg_8]
0x1800be95d  add     rsp, 2A0h
0x1800be964  pop     r15
0x1800be966  pop     r14
0x1800be968  pop     r13
0x1800be96a  pop     r12
0x1800be96c  pop     rdi
0x1800be96d  pop     rsi
0x1800be96e  pop     rbp
0x1800be96f  retn
```
