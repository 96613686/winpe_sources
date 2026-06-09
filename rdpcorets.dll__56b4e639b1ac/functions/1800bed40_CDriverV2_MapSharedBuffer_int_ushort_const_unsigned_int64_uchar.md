# CDriverV2::MapSharedBuffer(int,ushort const *,unsigned __int64,uchar * *)

- ea: `0x1800bed40`
- end: `0x1800bf0b9`
- name: `?MapSharedBuffer@CDriverV2@@UEAAJHPEBG_KPEAPEAE@Z`
- size: `889`
- prototype: `int(CDriverV2 *__hidden this, int, const unsigned __int16 *, unsigned __int64, unsigned __int8 **)`
- caller_count: `0`
- callee_count: `9`
- tags: ``

## callees

- `0x1800014d8`
- `0x1800015f0`
- `0x180009088`
- `0x180009628`
- `0x18000ee00`
- `0x180010960`
- `0x180033da0`
- `0x180034970`
- `0x1800bed40`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bef20`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bf003`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bef20`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bf003`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800beff8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800beff8`
- `api-ms-win-core-memory-l1-1-0!OpenFileMappingW` at `0x1800beeac`
- `api-ms-win-core-memory-l1-1-0!OpenFileMappingW` at `0x1800beeac`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x1800bef0e`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x1800bef0e`

## string_xrefs

- `0x1800bee18`: `Failed to create section name with StringCchPrintf`
- `0x1800beed9`: `Opened surface file mapping.`
- `0x1800bf04e`: `Failed to create mapping`

## pseudocode

```c
__int64 __fastcall CDriverV2::MapSharedBuffer(
        CDriverV2 *this,
        int a2,
        const unsigned __int16 *a3,
        SIZE_T a4,
        unsigned __int8 **a5)
{
  int v9; // ecx
  int v10; // r8d
  unsigned int v11; // ebx
  int v12; // eax
  int v13; // ecx
  int v14; // r8d
  int v15; // r9d
  HANDLE v16; // rdi
  int v17; // r8d
  int v18; // r9d
  int v19; // ecx
  unsigned __int8 *v20; // rbx
  int v21; // r8d
  int v22; // r9d
  signed int LastError; // eax
  int v24; // ecx
  int v25; // r8d
  int v26; // r9d
  signed int v27; // eax
  int v28; // ecx
  int v29; // r8d
  int v30; // r9d
  int v32; // [rsp+50h] [rbp-B0h] BYREF
  const char *v33; // [rsp+58h] [rbp-A8h] BYREF
  const char *v34; // [rsp+60h] [rbp-A0h] BYREF
  const char *v35; // [rsp+68h] [rbp-98h] BYREF
  const char *v36; // [rsp+70h] [rbp-90h] BYREF
  const char *v37; // [rsp+78h] [rbp-88h] BYREF
  WCHAR Name[512]; // [rsp+80h] [rbp-80h] BYREF

  memset_0(Name, 0, sizeof(Name));
  if ( *((_DWORD *)this + 14) == -1 )
  {
    if ( (unsigned int)dword_1801B76C8 > 4 )
    {
      v33 = "******Session ID -1 still****";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        v9,
        (unsigned int)&unk_1801A6CB8,
        v10,
        -1,
        (__int64)&v33);
    }
    return 1;
  }
  else
  {
    if ( a2 )
      v12 = StringCchPrintfW(Name, 0x200u, L"Session\\%d\\%s");
    else
      v12 = StringCchPrintfW(Name, 0x200u, L"Global\\%s", a3);
    v11 = v12;
    if ( v12 >= 0 )
    {
      v16 = OpenFileMappingW(6u, 0, Name);
      if ( v16 )
      {
        if ( (unsigned int)dword_1801B76C8 > 4 )
        {
          v34 = (const char *)Name;
          v35 = "Opened surface file mapping.";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
            dword_1801B76C8,
            (unsigned int)byte_1801A6C85,
            v17,
            v18,
            (__int64)&v35,
            (__int64)&v34);
        }
        v20 = (unsigned __int8 *)MapViewOfFile(v16, 6u, 0, 0, a4);
        if ( v20 )
        {
          if ( (unsigned int)dword_1801B76C8 > 5 )
          {
            LODWORD(v33) = a4;
            v34 = "Mapped Shared Buffer.";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
              v19,
              (unsigned int)&byte_1801A6C0F,
              v21,
              v22,
              (__int64)&v34,
              (__int64)&v33);
          }
          *a5 = v20;
          v11 = 0;
        }
        else
        {
          LastError = GetLastError();
          v11 = LastError;
          if ( LastError > 0 )
            v11 = (unsigned __int16)LastError | 0x80070000;
          if ( (unsigned int)dword_1801B76C8 > 2 )
          {
            LODWORD(v33) = 818;
            v34 = "MapSharedBuffer";
            v32 = v11;
            v35 = "clientcore\\termsrv\\rdpplatform\\gfxpipe\\gfxsource\\driverv2.cpp";
            v36 = "Could not map view of file";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
              v24,
              (unsigned int)byte_1801A6BC5,
              v25,
              v26,
              (__int64)&v36,
              (__int64)&v32,
              (__int64)&v35,
              (__int64)&v33,
              (__int64)&v34);
          }
        }
        CloseHandle(v16);
      }
      else
      {
        v27 = GetLastError();
        v11 = v27;
        if ( v27 > 0 )
          v11 = (unsigned __int16)v27 | 0x80070000;
        if ( (unsigned int)dword_1801B76C8 > 2 )
        {
          LODWORD(v33) = 804;
          v34 = "MapSharedBuffer";
          v32 = v11;
          v35 = "clientcore\\termsrv\\rdpplatform\\gfxpipe\\gfxsource\\driverv2.cpp";
          v36 = "Failed to create mapping";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
            v28,
            (unsigned int)byte_1801A6C3B,
            v29,
            v30,
            (__int64)&v36,
            (__int64)&v32,
            (__int64)&v35,
            (__int64)&v33,
            (__int64)&v34);
        }
      }
    }
    else if ( (unsigned int)dword_1801B76C8 > 2 )
    {
      v32 = 789;
      v37 = "Failed to create section name with StringCchPrintf";
      LODWORD(v33) = v12;
      v36 = "MapSharedBuffer";
      v35 = "clientcore\\termsrv\\rdpplatform\\gfxpipe\\gfxsource\\driverv2.cpp";
      v34 = "Error HResult failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v13,
        (unsigned int)&word_1801A6CDE,
        v14,
        v15,
        (__int64)&v34,
        (__int64)&v33,
        (__int64)&v35,
        (__int64)&v32,
        (__int64)&v36,
        (__int64)&v37);
    }
  }
  return v11;
}

```

## disassembly

```asm
0x1800bed40  mov     [rsp-8+arg_8], rbx
0x1800bed45  push    rbp
0x1800bed46  push    rsi
0x1800bed47  push    rdi
0x1800bed48  push    r14
0x1800bed4a  push    r15
0x1800bed4c  lea     rbp, [rsp-390h]
0x1800bed54  sub     rsp, 490h
0x1800bed5b  mov     rax, cs:__security_cookie
0x1800bed62  xor     rax, rsp
0x1800bed65  mov     [rbp+3B0h+var_30], rax
0x1800bed6c  mov     r15, [rbp+3B0h+arg_20]
0x1800bed73  mov     rdi, r8
0x1800bed76  mov     esi, edx
0x1800bed78  mov     rbx, rcx
0x1800bed7b  xor     edx, edx; Val
0x1800bed7d  lea     rcx, [rbp+3B0h+Name]; void *
0x1800bed81  mov     r8d, 400h; Size
0x1800bed87  mov     r14, r9
0x1800bed8a  call    memset_0
0x1800bed8f  mov     r9d, [rbx+38h]
0x1800bed93  cmp     r9d, 0FFFFFFFFh
0x1800bed97  jnz     short loc_1800BEDD0
0x1800bed99  mov     eax, cs:dword_1801B76C8
0x1800bed9f  cmp     eax, 4
0x1800beda2  jbe     short loc_1800BEDC6
0x1800beda4  lea     rax, aSessionId1Stil; "******Session ID -1 still****"
0x1800bedab  mov     [rsp+4B0h+var_458], rax
0x1800bedb0  lea     rdx, unk_1801A6CB8
0x1800bedb7  lea     rax, [rsp+4B0h+var_458]
0x1800bedbc  mov     [rsp+4B0h+dwNumberOfBytesToMap], rax
0x1800bedc1  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x1800bedc6  mov     ebx, 1
0x1800bedcb  jmp     loc_1800BF091
0x1800bedd0  lea     rcx, [rbp+3B0h+Name]; unsigned __int16 *
0x1800bedd4  mov     edx, 200h; unsigned __int64
0x1800bedd9  test    esi, esi
0x1800beddb  jz      short loc_1800BEDF0
0x1800beddd  lea     r8, aSessionDS; "Session\\%d\\%s"
0x1800bede4  mov     [rsp+4B0h+dwNumberOfBytesToMap], rdi
0x1800bede9  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800bedee  jmp     short loc_1800BEDFF
0x1800bedf0  mov     r9, rdi
0x1800bedf3  lea     r8, aGlobalS; "Global\\%s"
0x1800bedfa  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800bedff  mov     ebx, eax
0x1800bee01  test    eax, eax
0x1800bee03  jns     loc_1800BEEA1
0x1800bee09  mov     eax, cs:dword_1801B76C8
0x1800bee0f  cmp     eax, 2
0x1800bee12  jbe     loc_1800BF091
0x1800bee18  lea     rax, aFailedToCreate_74; "Failed to create section name with Stri"...
0x1800bee1f  mov     [rsp+4B0h+var_460], 315h
0x1800bee27  mov     [rsp+4B0h+var_438], rax
0x1800bee2c  lea     rdx, word_1801A6CDE
0x1800bee33  lea     rax, aMapsharedbuffe; "MapSharedBuffer"
0x1800bee3a  mov     dword ptr [rsp+4B0h+var_458], ebx
0x1800bee3e  mov     [rsp+4B0h+var_440], rax
0x1800bee43  lea     rax, aClientcoreTerm_5; "clientcore\\termsrv\\rdpplatform\\gfxpi"...
0x1800bee4a  mov     [rsp+4B0h+var_448], rax
0x1800bee4f  lea     rax, aErrorHresultFa; "Error HResult failed"
0x1800bee56  mov     [rsp+4B0h+var_450], rax
0x1800bee5b  lea     rax, [rsp+4B0h+var_438]
0x1800bee60  mov     [rsp+4B0h+var_468], rax
0x1800bee65  lea     rax, [rsp+4B0h+var_440]
0x1800bee6a  mov     [rsp+4B0h+var_470], rax
0x1800bee6f  lea     rax, [rsp+4B0h+var_460]
0x1800bee74  mov     [rsp+4B0h+var_478], rax
0x1800bee79  lea     rax, [rsp+4B0h+var_448]
0x1800bee7e  mov     [rsp+4B0h+var_480], rax
0x1800bee83  lea     rax, [rsp+4B0h+var_458]
0x1800bee88  mov     [rsp+4B0h+var_488], rax
0x1800bee8d  lea     rax, [rsp+4B0h+var_450]
0x1800bee92  mov     [rsp+4B0h+dwNumberOfBytesToMap], rax
0x1800bee97  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x1800bee9c  jmp     loc_1800BF091
0x1800beea1  xor     edx, edx; bInheritHandle
0x1800beea3  lea     r8, [rbp+3B0h+Name]; lpName
0x1800beea7  lea     ebx, [rdx+6]
0x1800beeaa  mov     ecx, ebx; dwDesiredAccess
0x1800beeac  call    cs:__imp_OpenFileMappingW
0x1800beeb2  mov     rdi, rax
0x1800beeb5  test    rax, rax
0x1800beeb8  jz      loc_1800BF003
0x1800beebe  mov     ecx, cs:dword_1801B76C8
0x1800beec4  cmp     ecx, 4
0x1800beec7  jbe     short loc_1800BEEFE
0x1800beec9  lea     rax, [rbp+3B0h+Name]
0x1800beecd  mov     [rsp+4B0h+var_450], rax
0x1800beed2  lea     rdx, byte_1801A6C85
0x1800beed9  lea     rax, aOpenedSurfaceF; "Opened surface file mapping."
0x1800beee0  mov     [rsp+4B0h+var_448], rax
0x1800beee5  lea     rax, [rsp+4B0h+var_450]
0x1800beeea  mov     [rsp+4B0h+var_488], rax
0x1800beeef  lea     rax, [rsp+4B0h+var_448]
0x1800beef4  mov     [rsp+4B0h+dwNumberOfBytesToMap], rax
0x1800beef9  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x1800beefe  xor     r9d, r9d; dwFileOffsetLow
0x1800bef01  mov     [rsp+4B0h+dwNumberOfBytesToMap], r14; dwNumberOfBytesToMap
0x1800bef06  xor     r8d, r8d; dwFileOffsetHigh
0x1800bef09  mov     edx, ebx; dwDesiredAccess
0x1800bef0b  mov     rcx, rdi; hFileMappingObject
0x1800bef0e  call    cs:__imp_MapViewOfFile
0x1800bef14  mov     rbx, rax
0x1800bef17  test    rax, rax
0x1800bef1a  jnz     loc_1800BEFB4
0x1800bef20  call    cs:__imp_GetLastError
0x1800bef26  mov     ebx, eax
0x1800bef28  test    eax, eax
0x1800bef2a  jle     short loc_1800BEF35
0x1800bef2c  movzx   ebx, ax
0x1800bef2f  or      ebx, 80070000h
0x1800bef35  mov     eax, cs:dword_1801B76C8
0x1800bef3b  cmp     eax, 2
0x1800bef3e  jbe     loc_1800BEFF5
0x1800bef44  lea     rax, aMapsharedbuffe; "MapSharedBuffer"
0x1800bef4b  mov     dword ptr [rsp+4B0h+var_458], 332h
0x1800bef53  mov     [rsp+4B0h+var_450], rax
0x1800bef58  lea     rdx, byte_1801A6BC5
0x1800bef5f  lea     rax, aClientcoreTerm_5; "clientcore\\termsrv\\rdpplatform\\gfxpi"...
0x1800bef66  mov     [rsp+4B0h+var_460], ebx
0x1800bef6a  mov     [rsp+4B0h+var_448], rax
0x1800bef6f  lea     rax, aCouldNotMapVie; "Could not map view of file"
0x1800bef76  mov     [rsp+4B0h+var_440], rax
0x1800bef7b  lea     rax, [rsp+4B0h+var_450]
0x1800bef80  mov     [rsp+4B0h+var_470], rax
0x1800bef85  lea     rax, [rsp+4B0h+var_458]
0x1800bef8a  mov     [rsp+4B0h+var_478], rax
0x1800bef8f  lea     rax, [rsp+4B0h+var_448]
0x1800bef94  mov     [rsp+4B0h+var_480], rax
0x1800bef99  lea     rax, [rsp+4B0h+var_460]
0x1800bef9e  mov     [rsp+4B0h+var_488], rax
0x1800befa3  lea     rax, [rsp+4B0h+var_440]
0x1800befa8  mov     [rsp+4B0h+dwNumberOfBytesToMap], rax
0x1800befad  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x1800befb2  jmp     short loc_1800BEFF5
0x1800befb4  mov     eax, cs:dword_1801B76C8
0x1800befba  cmp     eax, 5
0x1800befbd  jbe     short loc_1800BEFF0
0x1800befbf  lea     rax, aMappedSharedBu_0; "Mapped Shared Buffer."
0x1800befc6  mov     dword ptr [rsp+4B0h+var_458], r14d
0x1800befcb  mov     [rsp+4B0h+var_450], rax
0x1800befd0  lea     rdx, byte_1801A6C0F
0x1800befd7  lea     rax, [rsp+4B0h+var_458]
0x1800befdc  mov     [rsp+4B0h+var_488], rax
0x1800befe1  lea     rax, [rsp+4B0h+var_450]
0x1800befe6  mov     [rsp+4B0h+dwNumberOfBytesToMap], rax
0x1800befeb  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1800beff0  mov     [r15], rbx
0x1800beff3  xor     ebx, ebx
0x1800beff5  mov     rcx, rdi; hObject
0x1800beff8  call    cs:__imp_CloseHandle
0x1800beffe  jmp     loc_1800BF091
0x1800bf003  call    cs:__imp_GetLastError
0x1800bf009  mov     ebx, eax
0x1800bf00b  test    eax, eax
0x1800bf00d  jle     short loc_1800BF018
0x1800bf00f  movzx   ebx, ax
0x1800bf012  or      ebx, 80070000h
0x1800bf018  mov     eax, cs:dword_1801B76C8
0x1800bf01e  cmp     eax, 2
0x1800bf021  jbe     short loc_1800BF091
0x1800bf023  lea     rax, aMapsharedbuffe; "MapSharedBuffer"
0x1800bf02a  mov     dword ptr [rsp+4B0h+var_458], 324h
0x1800bf032  mov     [rsp+4B0h+var_450], rax
0x1800bf037  lea     rdx, byte_1801A6C3B
0x1800bf03e  lea     rax, aClientcoreTerm_5; "clientcore\\termsrv\\rdpplatform\\gfxpi"...
0x1800bf045  mov     [rsp+4B0h+var_460], ebx
0x1800bf049  mov     [rsp+4B0h+var_448], rax
0x1800bf04e  lea     rax, aFailedToCreate_30; "Failed to create mapping"
0x1800bf055  mov     [rsp+4B0h+var_440], rax
0x1800bf05a  lea     rax, [rsp+4B0h+var_450]
0x1800bf05f  mov     [rsp+4B0h+var_470], rax
0x1800bf064  lea     rax, [rsp+4B0h+var_458]
0x1800bf069  mov     [rsp+4B0h+var_478], rax
0x1800bf06e  lea     rax, [rsp+4B0h+var_448]
0x1800bf073  mov     [rsp+4B0h+var_480], rax
0x1800bf078  lea     rax, [rsp+4B0h+var_460]
0x1800bf07d  mov     [rsp+4B0h+var_488], rax
0x1800bf082  lea     rax, [rsp+4B0h+var_440]
0x1800bf087  mov     [rsp+4B0h+dwNumberOfBytesToMap], rax
0x1800bf08c  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x1800bf091  mov     eax, ebx
0x1800bf093  mov     rcx, [rbp+3B0h+var_30]
0x1800bf09a  xor     rcx, rsp; StackCookie
0x1800bf09d  call    __security_check_cookie
0x1800bf0a2  mov     rbx, [rsp+4B0h+arg_8]
0x1800bf0aa  add     rsp, 490h
0x1800bf0b1  pop     r15
0x1800bf0b3  pop     r14
0x1800bf0b5  pop     rdi
0x1800bf0b6  pop     rsi
0x1800bf0b7  pop     rbp
0x1800bf0b8  retn
```
