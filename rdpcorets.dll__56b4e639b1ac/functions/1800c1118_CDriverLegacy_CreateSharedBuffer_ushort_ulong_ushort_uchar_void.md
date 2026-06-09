# CDriverLegacy::CreateSharedBuffer(ushort *,ulong,ushort *,uchar * *,void * *)

- ea: `0x1800c1118`
- end: `0x1800c1541`
- name: `?CreateSharedBuffer@CDriverLegacy@@IEAAJPEAGK0PEAPEAEPEAPEAX@Z`
- size: `1065`
- prototype: `int(CDriverLegacy *__hidden this, unsigned __int16 *, unsigned int, unsigned __int16 *, unsigned __int8 **, void **)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x1800c09d8`

## callees

- `0x1800014d8`
- `0x1800015f0`
- `0x180009088`
- `0x180009628`
- `0x18000ee00`
- `0x180033da0`
- `0x180034970`
- `0x1800c1118`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c1204`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c127c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c1204`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c127c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c1516`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c1516`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x1800c126a`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x1800c126a`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x1800c11f6`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x1800c11f6`

## string_xrefs

- `0x1800c135a`: `Failed to create mapping`
- `0x1800c12a0`: `CreateSharedBuffer`
- `0x1800c132f`: `CreateSharedBuffer`
- `0x1800c141b`: `CreateSharedBuffer`
- `0x1800c14a5`: `CreateSharedBuffer`

## pseudocode

```c
__int64 __fastcall CDriverLegacy::CreateSharedBuffer(
        CDriverLegacy *this,
        unsigned __int16 *a2,
        unsigned int a3,
        unsigned __int16 *a4,
        unsigned __int8 **a5,
        void **a6)
{
  unsigned __int16 *v6; // rbx
  SIZE_T v8; // r14
  int v10; // esi
  int v11; // ecx
  unsigned int v12; // ebx
  int v13; // r8d
  int v14; // r9d
  HANDLE FileMappingW; // rdi
  signed int LastError; // eax
  int v17; // r8d
  int v18; // r9d
  int v19; // ecx
  unsigned __int8 *v20; // rbx
  int v21; // r8d
  int v22; // r9d
  signed int v23; // eax
  int v24; // ecx
  int v25; // r8d
  int v26; // r9d
  char *v27; // rax
  __int16 *v28; // rdx
  const char **v29; // rax
  DWORD dwMaximumSizeLow[2]; // [rsp+20h] [rbp-E0h]
  LPCWSTR lpName; // [rsp+28h] [rbp-D8h]
  const char **v33; // [rsp+30h] [rbp-D0h]
  const char **v34; // [rsp+40h] [rbp-C0h]
  const char **v35; // [rsp+48h] [rbp-B8h]
  unsigned __int16 *v36; // [rsp+50h] [rbp-B0h] BYREF
  const char *v37; // [rsp+58h] [rbp-A8h] BYREF
  const char *v38; // [rsp+60h] [rbp-A0h] BYREF
  const char *v39; // [rsp+68h] [rbp-98h] BYREF
  const char *v40; // [rsp+70h] [rbp-90h] BYREF
  const char *v41; // [rsp+78h] [rbp-88h] BYREF
  WCHAR Name[264]; // [rsp+80h] [rbp-80h] BYREF

  v6 = a2;
  v8 = a3;
  v36 = a2;
  v38 = (const char *)a6;
  memset_0(Name, 0, 0x208u);
  v10 = 0;
  while ( 1 )
  {
    LODWORD(lpName) = v10;
    dwMaximumSizeLow[0] = *((_DWORD *)this + 14);
    v12 = StringCchPrintfW(a4, 0x104u, L"%s-Session%d-%d", v6, *(_QWORD *)dwMaximumSizeLow, lpName);
    if ( (v12 & 0x80000000) != 0 )
    {
      if ( (unsigned int)dword_1801B76C8 <= 2 )
        return v12;
      LODWORD(v36) = 947;
      v41 = "Failed to print shared buffer name";
      v28 = &word_1801A80C6;
      v39 = "CreateSharedBuffer";
      v38 = "clientcore\\termsrv\\rdpplatform\\gfxpipe\\gfxsource\\driverlegacy.cpp";
      v40 = "Error HResult failed";
      v35 = &v41;
      v34 = &v39;
      v33 = &v38;
      v29 = &v40;
      goto LABEL_26;
    }
    v12 = StringCchPrintfW(Name, 0x104u, L"%s%s", L"Global\\", a4);
    if ( (v12 & 0x80000000) != 0 )
    {
      if ( (unsigned int)dword_1801B76C8 <= 2 )
        return v12;
      LODWORD(v36) = 959;
      v39 = "Failed to print shared buffer name for mapping";
      v28 = (__int16 *)&dword_1801A8004;
      v38 = "CreateSharedBuffer";
      v40 = "clientcore\\termsrv\\rdpplatform\\gfxpipe\\gfxsource\\driverlegacy.cpp";
      v41 = "Error HResult failed";
      v35 = &v39;
      v34 = &v38;
      v33 = &v40;
      v29 = &v41;
LABEL_26:
      LODWORD(v37) = v12;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v11,
        (_DWORD)v28,
        v13,
        v14,
        (__int64)v29,
        (__int64)&v37,
        (__int64)v33,
        (__int64)&v36,
        (__int64)v34,
        (__int64)v35);
      return v12;
    }
    FileMappingW = CreateFileMappingW(
                     (HANDLE)0xFFFFFFFFFFFFFFFFLL,
                     *((LPSECURITY_ATTRIBUTES *)this + 93),
                     4u,
                     0,
                     v8,
                     Name);
    if ( FileMappingW )
      goto LABEL_9;
    LastError = GetLastError();
    v12 = LastError;
    if ( (unsigned int)(LastError - 5) > 1 )
      break;
    if ( (unsigned int)dword_1801B76C8 > 3 )
    {
      v37 = "Shared buffer name conflict!  Renaming";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        dword_1801B76C8,
        (unsigned int)&word_1801A8056,
        v17,
        v18,
        (__int64)&v37);
      ++v10;
      goto LABEL_8;
    }
LABEL_9:
    ++v10;
    if ( FileMappingW )
    {
      v20 = (unsigned __int8 *)MapViewOfFile(FileMappingW, 6u, 0, 0, v8);
      if ( v20 )
      {
        if ( (unsigned int)dword_1801B76C8 > 4 )
        {
          LODWORD(v36) = v8;
          v39 = "Mapped Shared Buffer";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
            v19,
            (unsigned int)word_1801A7EF2,
            v21,
            v22,
            (__int64)&v39,
            (__int64)&v36);
        }
        v27 = (char *)v38;
        *a5 = v20;
        v12 = 0;
        *(_QWORD *)v27 = FileMappingW;
      }
      else
      {
        v23 = GetLastError();
        v12 = v23;
        if ( v23 > 0 )
          v12 = (unsigned __int16)v23 | 0x80070000;
        if ( (unsigned int)dword_1801B76C8 > 2 )
        {
          LODWORD(v36) = 1000;
          v39 = "CreateSharedBuffer";
          LODWORD(v37) = v12;
          v38 = "clientcore\\termsrv\\rdpplatform\\gfxpipe\\gfxsource\\driverlegacy.cpp";
          v40 = "Could not map view of file";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
            v24,
            (unsigned int)word_1801A7FBA,
            v25,
            v26,
            (__int64)&v40,
            (__int64)&v37,
            (__int64)&v38,
            (__int64)&v36,
            (__int64)&v39);
        }
        CloseHandle(FileMappingW);
      }
      return v12;
    }
LABEL_8:
    v6 = v36;
  }
  if ( LastError > 0 )
    v12 = (unsigned __int16)LastError | 0x80070000;
  if ( (unsigned int)dword_1801B76C8 > 2 )
  {
    LODWORD(v37) = 984;
    v40 = "CreateSharedBuffer";
    LODWORD(v36) = v12;
    v38 = "clientcore\\termsrv\\rdpplatform\\gfxpipe\\gfxsource\\driverlegacy.cpp";
    v39 = "Failed to create mapping";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
      LastError - 5,
      (unsigned int)&unk_1801A7F70,
      v17,
      v18,
      (__int64)&v39,
      (__int64)&v36,
      (__int64)&v38,
      (__int64)&v37,
      (__int64)&v40);
  }
  return v12;
}

```

## disassembly

```asm
0x1800c1118  push    rbp
0x1800c111a  push    rbx
0x1800c111b  push    rsi
0x1800c111c  push    rdi
0x1800c111d  push    r12
0x1800c111f  push    r13
0x1800c1121  push    r14
0x1800c1123  push    r15
0x1800c1125  lea     rbp, [rsp-1A8h]
0x1800c112d  sub     rsp, 2A8h
0x1800c1134  mov     rax, cs:__security_cookie
0x1800c113b  xor     rax, rsp
0x1800c113e  mov     [rbp+1E0h+var_50], rax
0x1800c1145  mov     rax, [rbp+1E0h+arg_28]
0x1800c114c  mov     rbx, rdx
0x1800c114f  mov     r13, [rbp+1E0h+arg_20]
0x1800c1156  mov     r15, rcx
0x1800c1159  mov     r14d, r8d
0x1800c115c  lea     rcx, [rbp+1E0h+Name]; void *
0x1800c1160  mov     [rsp+2E0h+var_290], rdx
0x1800c1165  mov     r8d, 208h; Size
0x1800c116b  xor     edx, edx; Val
0x1800c116d  mov     [rsp+2E0h+var_280], rax
0x1800c1172  mov     r12, r9
0x1800c1175  xor     edi, edi
0x1800c1177  call    memset_0
0x1800c117c  xor     esi, esi
0x1800c117e  mov     eax, [r15+38h]
0x1800c1182  lea     r8, aSSessionDD; "%s-Session%d-%d"
0x1800c1189  mov     dword ptr [rsp+2E0h+lpName], esi
0x1800c118d  mov     r9, rbx
0x1800c1190  mov     edx, 104h; unsigned __int64
0x1800c1195  mov     [rsp+2E0h+dwMaximumSizeLow], eax
0x1800c1199  mov     rcx, r12; unsigned __int16 *
0x1800c119c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800c11a1  mov     ebx, eax
0x1800c11a3  test    eax, eax
0x1800c11a5  js      loc_1800C147B
0x1800c11ab  lea     r9, aGlobal; "Global\\"
0x1800c11b2  mov     qword ptr [rsp+2E0h+dwMaximumSizeLow], r12
0x1800c11b7  lea     r8, aSS_0; "%s%s"
0x1800c11be  mov     edx, 104h; unsigned __int64
0x1800c11c3  lea     rcx, [rbp+1E0h+Name]; unsigned __int16 *
0x1800c11c7  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800c11cc  mov     ebx, eax
0x1800c11ce  test    eax, eax
0x1800c11d0  js      loc_1800C13F1
0x1800c11d6  mov     rdx, [r15+2E8h]; lpFileMappingAttributes
0x1800c11dd  lea     rax, [rbp+1E0h+Name]
0x1800c11e1  xor     r9d, r9d; dwMaximumSizeHigh
0x1800c11e4  mov     [rsp+2E0h+lpName], rax; lpName
0x1800c11e9  or      rcx, 0FFFFFFFFFFFFFFFFh; hFile
0x1800c11ed  mov     [rsp+2E0h+dwMaximumSizeLow], r14d; dwMaximumSizeLow
0x1800c11f2  lea     r8d, [r9+4]; flProtect
0x1800c11f6  call    cs:__imp_CreateFileMappingW
0x1800c11fc  mov     rdi, rax
0x1800c11ff  test    rax, rax
0x1800c1202  jnz     short loc_1800C1251
0x1800c1204  call    cs:__imp_GetLastError
0x1800c120a  mov     ebx, eax
0x1800c120c  lea     ecx, [rax-5]
0x1800c120f  cmp     ecx, 1
0x1800c1212  ja      loc_1800C1313
0x1800c1218  mov     ecx, cs:dword_1801B76C8
0x1800c121e  cmp     ecx, 3
0x1800c1221  jbe     short loc_1800C1251
0x1800c1223  lea     rax, aSharedBufferNa; "Shared buffer name conflict!  Renaming"
0x1800c122a  mov     [rsp+2E0h+var_288], rax
0x1800c122f  lea     rdx, word_1801A8056
0x1800c1236  lea     rax, [rsp+2E0h+var_288]
0x1800c123b  mov     qword ptr [rsp+2E0h+dwMaximumSizeLow], rax
0x1800c1240  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x1800c1245  inc     esi
0x1800c1247  mov     rbx, [rsp+2E0h+var_290]
0x1800c124c  jmp     loc_1800C117E
0x1800c1251  inc     esi
0x1800c1253  test    rdi, rdi
0x1800c1256  jz      short loc_1800C1247
0x1800c1258  xor     r9d, r9d; dwFileOffsetLow
0x1800c125b  mov     qword ptr [rsp+2E0h+dwMaximumSizeLow], r14; dwNumberOfBytesToMap
0x1800c1260  xor     r8d, r8d; dwFileOffsetHigh
0x1800c1263  mov     rcx, rdi; hFileMappingObject
0x1800c1266  lea     edx, [r9+6]; dwDesiredAccess
0x1800c126a  call    cs:__imp_MapViewOfFile
0x1800c1270  mov     rbx, rax
0x1800c1273  test    rax, rax
0x1800c1276  jnz     loc_1800C13A2
0x1800c127c  call    cs:__imp_GetLastError
0x1800c1282  mov     ebx, eax
0x1800c1284  test    eax, eax
0x1800c1286  jle     short loc_1800C1291
0x1800c1288  movzx   ebx, ax
0x1800c128b  or      ebx, 80070000h
0x1800c1291  mov     eax, cs:dword_1801B76C8
0x1800c1297  cmp     eax, 2
0x1800c129a  jbe     loc_1800C1513
0x1800c12a0  lea     rax, aCreatesharedbu; "CreateSharedBuffer"
0x1800c12a7  mov     dword ptr [rsp+2E0h+var_290], 3E8h
0x1800c12af  mov     [rsp+2E0h+var_278], rax
0x1800c12b4  lea     rdx, word_1801A7FBA
0x1800c12bb  lea     rax, aClientcoreTerm_4; "clientcore\\termsrv\\rdpplatform\\gfxpi"...
0x1800c12c2  mov     dword ptr [rsp+2E0h+var_288], ebx
0x1800c12c6  mov     [rsp+2E0h+var_280], rax
0x1800c12cb  lea     rax, aCouldNotMapVie; "Could not map view of file"
0x1800c12d2  mov     [rsp+2E0h+var_270], rax
0x1800c12d7  lea     rax, [rsp+2E0h+var_278]
0x1800c12dc  mov     [rsp+2E0h+var_2A0], rax
0x1800c12e1  lea     rax, [rsp+2E0h+var_290]
0x1800c12e6  mov     [rsp+2E0h+var_2A8], rax
0x1800c12eb  lea     rax, [rsp+2E0h+var_280]
0x1800c12f0  mov     [rsp+2E0h+var_2B0], rax
0x1800c12f5  lea     rax, [rsp+2E0h+var_288]
0x1800c12fa  mov     [rsp+2E0h+lpName], rax
0x1800c12ff  lea     rax, [rsp+2E0h+var_270]
0x1800c1304  mov     qword ptr [rsp+2E0h+dwMaximumSizeLow], rax
0x1800c1309  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x1800c130e  jmp     loc_1800C1513
0x1800c1313  test    eax, eax
0x1800c1315  jle     short loc_1800C1320
0x1800c1317  movzx   ebx, ax
0x1800c131a  or      ebx, 80070000h
0x1800c1320  mov     eax, cs:dword_1801B76C8
0x1800c1326  cmp     eax, 2
0x1800c1329  jbe     loc_1800C151C
0x1800c132f  lea     rax, aCreatesharedbu; "CreateSharedBuffer"
0x1800c1336  mov     dword ptr [rsp+2E0h+var_288], 3D8h
0x1800c133e  mov     [rsp+2E0h+var_270], rax
0x1800c1343  lea     rdx, unk_1801A7F70
0x1800c134a  lea     rax, aClientcoreTerm_4; "clientcore\\termsrv\\rdpplatform\\gfxpi"...
0x1800c1351  mov     dword ptr [rsp+2E0h+var_290], ebx
0x1800c1355  mov     [rsp+2E0h+var_280], rax
0x1800c135a  lea     rax, aFailedToCreate_30; "Failed to create mapping"
0x1800c1361  mov     [rsp+2E0h+var_278], rax
0x1800c1366  lea     rax, [rsp+2E0h+var_270]
0x1800c136b  mov     [rsp+2E0h+var_2A0], rax
0x1800c1370  lea     rax, [rsp+2E0h+var_288]
0x1800c1375  mov     [rsp+2E0h+var_2A8], rax
0x1800c137a  lea     rax, [rsp+2E0h+var_280]
0x1800c137f  mov     [rsp+2E0h+var_2B0], rax
0x1800c1384  lea     rax, [rsp+2E0h+var_290]
0x1800c1389  mov     [rsp+2E0h+lpName], rax
0x1800c138e  lea     rax, [rsp+2E0h+var_278]
0x1800c1393  mov     qword ptr [rsp+2E0h+dwMaximumSizeLow], rax
0x1800c1398  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x1800c139d  jmp     loc_1800C151C
0x1800c13a2  mov     eax, cs:dword_1801B76C8
0x1800c13a8  cmp     eax, 4
0x1800c13ab  jbe     short loc_1800C13DE
0x1800c13ad  lea     rax, aMappedSharedBu; "Mapped Shared Buffer"
0x1800c13b4  mov     dword ptr [rsp+2E0h+var_290], r14d
0x1800c13b9  mov     [rsp+2E0h+var_278], rax
0x1800c13be  lea     rdx, word_1801A7EF2
0x1800c13c5  lea     rax, [rsp+2E0h+var_290]
0x1800c13ca  mov     [rsp+2E0h+lpName], rax
0x1800c13cf  lea     rax, [rsp+2E0h+var_278]
0x1800c13d4  mov     qword ptr [rsp+2E0h+dwMaximumSizeLow], rax
0x1800c13d9  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1800c13de  mov     rax, [rsp+2E0h+var_280]
0x1800c13e3  mov     [r13+0], rbx
0x1800c13e7  xor     ebx, ebx
0x1800c13e9  mov     [rax], rdi
0x1800c13ec  jmp     loc_1800C151C
0x1800c13f1  mov     eax, cs:dword_1801B76C8
0x1800c13f7  cmp     eax, 2
0x1800c13fa  jbe     loc_1800C150E
0x1800c1400  lea     rax, aFailedToPrintS; "Failed to print shared buffer name for "...
0x1800c1407  mov     dword ptr [rsp+2E0h+var_290], 3BFh
0x1800c140f  mov     [rsp+2E0h+var_278], rax
0x1800c1414  lea     rdx, dword_1801A8004
0x1800c141b  lea     rax, aCreatesharedbu; "CreateSharedBuffer"
0x1800c1422  mov     [rsp+2E0h+var_280], rax
0x1800c1427  lea     rax, aClientcoreTerm_4; "clientcore\\termsrv\\rdpplatform\\gfxpi"...
0x1800c142e  mov     [rsp+2E0h+var_270], rax
0x1800c1433  lea     rax, aErrorHresultFa; "Error HResult failed"
0x1800c143a  mov     [rsp+2E0h+var_268], rax
0x1800c143f  lea     rax, [rsp+2E0h+var_278]
0x1800c1444  mov     [rsp+2E0h+var_298], rax
0x1800c1449  lea     rax, [rsp+2E0h+var_280]
0x1800c144e  mov     [rsp+2E0h+var_2A0], rax
0x1800c1453  lea     rax, [rsp+2E0h+var_290]
0x1800c1458  mov     [rsp+2E0h+var_2A8], rax
0x1800c145d  lea     rax, [rsp+2E0h+var_270]
0x1800c1462  mov     [rsp+2E0h+var_2B0], rax
0x1800c1467  lea     rax, [rsp+2E0h+var_288]
0x1800c146c  mov     [rsp+2E0h+lpName], rax
0x1800c1471  lea     rax, [rsp+2E0h+var_268]
0x1800c1476  jmp     loc_1800C1500
0x1800c147b  mov     eax, cs:dword_1801B76C8
0x1800c1481  cmp     eax, 2
0x1800c1484  jbe     loc_1800C150E
0x1800c148a  lea     rax, aFailedToPrintS_0; "Failed to print shared buffer name"
0x1800c1491  mov     dword ptr [rsp+2E0h+var_290], 3B3h
0x1800c1499  mov     [rsp+2E0h+var_268], rax
0x1800c149e  lea     rdx, word_1801A80C6
0x1800c14a5  lea     rax, aCreatesharedbu; "CreateSharedBuffer"
0x1800c14ac  mov     [rsp+2E0h+var_278], rax
0x1800c14b1  lea     rax, aClientcoreTerm_4; "clientcore\\termsrv\\rdpplatform\\gfxpi"...
0x1800c14b8  mov     [rsp+2E0h+var_280], rax
0x1800c14bd  lea     rax, aErrorHresultFa; "Error HResult failed"
0x1800c14c4  mov     [rsp+2E0h+var_270], rax
0x1800c14c9  lea     rax, [rsp+2E0h+var_268]
0x1800c14ce  mov     [rsp+2E0h+var_298], rax
0x1800c14d3  lea     rax, [rsp+2E0h+var_278]
0x1800c14d8  mov     [rsp+2E0h+var_2A0], rax
0x1800c14dd  lea     rax, [rsp+2E0h+var_290]
0x1800c14e2  mov     [rsp+2E0h+var_2A8], rax
0x1800c14e7  lea     rax, [rsp+2E0h+var_280]
0x1800c14ec  mov     [rsp+2E0h+var_2B0], rax
0x1800c14f1  lea     rax, [rsp+2E0h+var_288]
0x1800c14f6  mov     [rsp+2E0h+lpName], rax
0x1800c14fb  lea     rax, [rsp+2E0h+var_270]
0x1800c1500  mov     qword ptr [rsp+2E0h+dwMaximumSizeLow], rax
0x1800c1505  mov     dword ptr [rsp+2E0h+var_288], ebx
0x1800c1509  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x1800c150e  test    rdi, rdi
0x1800c1511  jz      short loc_1800C151C
0x1800c1513  mov     rcx, rdi; hObject
0x1800c1516  call    cs:__imp_CloseHandle
0x1800c151c  mov     eax, ebx
0x1800c151e  mov     rcx, [rbp+1E0h+var_50]
0x1800c1525  xor     rcx, rsp; StackCookie
0x1800c1528  call    __security_check_cookie
0x1800c152d  add     rsp, 2A8h
0x1800c1534  pop     r15
0x1800c1536  pop     r14
0x1800c1538  pop     r13
0x1800c153a  pop     r12
0x1800c153c  pop     rdi
0x1800c153d  pop     rsi
0x1800c153e  pop     rbx
0x1800c153f  pop     rbp
0x1800c1540  retn
```
