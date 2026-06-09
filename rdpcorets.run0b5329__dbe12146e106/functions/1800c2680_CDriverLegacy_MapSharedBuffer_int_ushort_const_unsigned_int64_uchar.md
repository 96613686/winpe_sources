# CDriverLegacy::MapSharedBuffer(int,ushort const *,unsigned __int64,uchar * *)

- ea: `0x1800c2680`
- end: `0x1800c29f9`
- name: `?MapSharedBuffer@CDriverLegacy@@UEAAJHPEBG_KPEAPEAE@Z`
- size: `889`
- prototype: `__int64 __fastcall(CDriverLegacy *this, int, const unsigned __int16 *, SIZE_T, unsigned __int8 **)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1800c23d0`

## callees

- `0x1800014d8`
- `0x1800015f0`
- `0x180009088`
- `0x180009628`
- `0x18000ee00`
- `0x180010960`
- `0x180033da0`
- `0x180034970`
- `0x1800c2680`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c2860`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c2943`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c2860`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c2943`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c2938`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c2938`
- `api-ms-win-core-memory-l1-1-0!OpenFileMappingW` at `0x1800c27ec`
- `api-ms-win-core-memory-l1-1-0!OpenFileMappingW` at `0x1800c27ec`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x1800c284e`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x1800c284e`

## string_xrefs

- `0x1800c2758`: `Failed to create section name with StringCchPrintf`
- `0x1800c2819`: `Opened surface file mapping.`
- `0x1800c298e`: `Failed to create mapping`

## pseudocode

```c
__int64 __fastcall CDriverLegacy::MapSharedBuffer(
        CDriverLegacy *this,
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
        (unsigned int)byte_1801A820B,
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
            (unsigned int)&word_1801A818E,
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
              (unsigned int)word_1801A8162,
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
            LODWORD(v33) = 864;
            v34 = "MapSharedBuffer";
            v32 = v11;
            v35 = "clientcore\\termsrv\\rdpplatform\\gfxpipe\\gfxsource\\driverlegacy.cpp";
            v36 = "Could not map view of file";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
              v24,
              (unsigned int)&unk_1801A8118,
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
          LODWORD(v33) = 850;
          v34 = "MapSharedBuffer";
          v32 = v11;
          v35 = "clientcore\\termsrv\\rdpplatform\\gfxpipe\\gfxsource\\driverlegacy.cpp";
          v36 = "Failed to create mapping";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
            v28,
            (unsigned int)byte_1801A81C1,
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
      v32 = 835;
      v37 = "Failed to create section name with StringCchPrintf";
      LODWORD(v33) = v12;
      v36 = "MapSharedBuffer";
      v35 = "clientcore\\termsrv\\rdpplatform\\gfxpipe\\gfxsource\\driverlegacy.cpp";
      v34 = "Error HResult failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v13,
        (unsigned int)byte_1801A8231,
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
0x1800c2680  mov     [rsp-8+arg_8], rbx
0x1800c2685  push    rbp
0x1800c2686  push    rsi
0x1800c2687  push    rdi
0x1800c2688  push    r14
0x1800c268a  push    r15
0x1800c268c  lea     rbp, [rsp-390h]
0x1800c2694  sub     rsp, 490h
0x1800c269b  mov     rax, cs:__security_cookie
0x1800c26a2  xor     rax, rsp
0x1800c26a5  mov     [rbp+3B0h+var_30], rax
0x1800c26ac  mov     r15, [rbp+3B0h+arg_20]
0x1800c26b3  mov     rdi, r8
0x1800c26b6  mov     esi, edx
0x1800c26b8  mov     rbx, rcx
0x1800c26bb  xor     edx, edx; Val
0x1800c26bd  lea     rcx, [rbp+3B0h+Name]; void *
0x1800c26c1  mov     r8d, 400h; Size
0x1800c26c7  mov     r14, r9
0x1800c26ca  call    memset_0
0x1800c26cf  mov     r9d, [rbx+38h]
0x1800c26d3  cmp     r9d, 0FFFFFFFFh
0x1800c26d7  jnz     short loc_1800C2710
0x1800c26d9  mov     eax, cs:dword_1801B76C8
0x1800c26df  cmp     eax, 4
0x1800c26e2  jbe     short loc_1800C2706
0x1800c26e4  lea     rax, aSessionId1Stil; "******Session ID -1 still****"
0x1800c26eb  mov     [rsp+4B0h+var_458], rax
0x1800c26f0  lea     rdx, byte_1801A820B
0x1800c26f7  lea     rax, [rsp+4B0h+var_458]
0x1800c26fc  mov     [rsp+4B0h+dwNumberOfBytesToMap], rax
0x1800c2701  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x1800c2706  mov     ebx, 1
0x1800c270b  jmp     loc_1800C29D1
0x1800c2710  lea     rcx, [rbp+3B0h+Name]; unsigned __int16 *
0x1800c2714  mov     edx, 200h; unsigned __int64
0x1800c2719  test    esi, esi
0x1800c271b  jz      short loc_1800C2730
0x1800c271d  lea     r8, aSessionDS; "Session\\%d\\%s"
0x1800c2724  mov     [rsp+4B0h+dwNumberOfBytesToMap], rdi
0x1800c2729  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800c272e  jmp     short loc_1800C273F
0x1800c2730  mov     r9, rdi
0x1800c2733  lea     r8, aGlobalS; "Global\\%s"
0x1800c273a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800c273f  mov     ebx, eax
0x1800c2741  test    eax, eax
0x1800c2743  jns     loc_1800C27E1
0x1800c2749  mov     eax, cs:dword_1801B76C8
0x1800c274f  cmp     eax, 2
0x1800c2752  jbe     loc_1800C29D1
0x1800c2758  lea     rax, aFailedToCreate_74; "Failed to create section name with Stri"...
0x1800c275f  mov     [rsp+4B0h+var_460], 343h
0x1800c2767  mov     [rsp+4B0h+var_438], rax
0x1800c276c  lea     rdx, byte_1801A8231
0x1800c2773  lea     rax, aMapsharedbuffe; "MapSharedBuffer"
0x1800c277a  mov     dword ptr [rsp+4B0h+var_458], ebx
0x1800c277e  mov     [rsp+4B0h+var_440], rax
0x1800c2783  lea     rax, aClientcoreTerm_4; "clientcore\\termsrv\\rdpplatform\\gfxpi"...
0x1800c278a  mov     [rsp+4B0h+var_448], rax
0x1800c278f  lea     rax, aErrorHresultFa; "Error HResult failed"
0x1800c2796  mov     [rsp+4B0h+var_450], rax
0x1800c279b  lea     rax, [rsp+4B0h+var_438]
0x1800c27a0  mov     [rsp+4B0h+var_468], rax
0x1800c27a5  lea     rax, [rsp+4B0h+var_440]
0x1800c27aa  mov     [rsp+4B0h+var_470], rax
0x1800c27af  lea     rax, [rsp+4B0h+var_460]
0x1800c27b4  mov     [rsp+4B0h+var_478], rax
0x1800c27b9  lea     rax, [rsp+4B0h+var_448]
0x1800c27be  mov     [rsp+4B0h+var_480], rax
0x1800c27c3  lea     rax, [rsp+4B0h+var_458]
0x1800c27c8  mov     [rsp+4B0h+var_488], rax
0x1800c27cd  lea     rax, [rsp+4B0h+var_450]
0x1800c27d2  mov     [rsp+4B0h+dwNumberOfBytesToMap], rax
0x1800c27d7  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x1800c27dc  jmp     loc_1800C29D1
0x1800c27e1  xor     edx, edx; bInheritHandle
0x1800c27e3  lea     r8, [rbp+3B0h+Name]; lpName
0x1800c27e7  lea     ebx, [rdx+6]
0x1800c27ea  mov     ecx, ebx; dwDesiredAccess
0x1800c27ec  call    cs:__imp_OpenFileMappingW
0x1800c27f2  mov     rdi, rax
0x1800c27f5  test    rax, rax
0x1800c27f8  jz      loc_1800C2943
0x1800c27fe  mov     ecx, cs:dword_1801B76C8
0x1800c2804  cmp     ecx, 4
0x1800c2807  jbe     short loc_1800C283E
0x1800c2809  lea     rax, [rbp+3B0h+Name]
0x1800c280d  mov     [rsp+4B0h+var_450], rax
0x1800c2812  lea     rdx, word_1801A818E
0x1800c2819  lea     rax, aOpenedSurfaceF; "Opened surface file mapping."
0x1800c2820  mov     [rsp+4B0h+var_448], rax
0x1800c2825  lea     rax, [rsp+4B0h+var_450]
0x1800c282a  mov     [rsp+4B0h+var_488], rax
0x1800c282f  lea     rax, [rsp+4B0h+var_448]
0x1800c2834  mov     [rsp+4B0h+dwNumberOfBytesToMap], rax
0x1800c2839  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x1800c283e  xor     r9d, r9d; dwFileOffsetLow
0x1800c2841  mov     [rsp+4B0h+dwNumberOfBytesToMap], r14; dwNumberOfBytesToMap
0x1800c2846  xor     r8d, r8d; dwFileOffsetHigh
0x1800c2849  mov     edx, ebx; dwDesiredAccess
0x1800c284b  mov     rcx, rdi; hFileMappingObject
0x1800c284e  call    cs:__imp_MapViewOfFile
0x1800c2854  mov     rbx, rax
0x1800c2857  test    rax, rax
0x1800c285a  jnz     loc_1800C28F4
0x1800c2860  call    cs:__imp_GetLastError
0x1800c2866  mov     ebx, eax
0x1800c2868  test    eax, eax
0x1800c286a  jle     short loc_1800C2875
0x1800c286c  movzx   ebx, ax
0x1800c286f  or      ebx, 80070000h
0x1800c2875  mov     eax, cs:dword_1801B76C8
0x1800c287b  cmp     eax, 2
0x1800c287e  jbe     loc_1800C2935
0x1800c2884  lea     rax, aMapsharedbuffe; "MapSharedBuffer"
0x1800c288b  mov     dword ptr [rsp+4B0h+var_458], 360h
0x1800c2893  mov     [rsp+4B0h+var_450], rax
0x1800c2898  lea     rdx, unk_1801A8118
0x1800c289f  lea     rax, aClientcoreTerm_4; "clientcore\\termsrv\\rdpplatform\\gfxpi"...
0x1800c28a6  mov     [rsp+4B0h+var_460], ebx
0x1800c28aa  mov     [rsp+4B0h+var_448], rax
0x1800c28af  lea     rax, aCouldNotMapVie; "Could not map view of file"
0x1800c28b6  mov     [rsp+4B0h+var_440], rax
0x1800c28bb  lea     rax, [rsp+4B0h+var_450]
0x1800c28c0  mov     [rsp+4B0h+var_470], rax
0x1800c28c5  lea     rax, [rsp+4B0h+var_458]
0x1800c28ca  mov     [rsp+4B0h+var_478], rax
0x1800c28cf  lea     rax, [rsp+4B0h+var_448]
0x1800c28d4  mov     [rsp+4B0h+var_480], rax
0x1800c28d9  lea     rax, [rsp+4B0h+var_460]
0x1800c28de  mov     [rsp+4B0h+var_488], rax
0x1800c28e3  lea     rax, [rsp+4B0h+var_440]
0x1800c28e8  mov     [rsp+4B0h+dwNumberOfBytesToMap], rax
0x1800c28ed  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x1800c28f2  jmp     short loc_1800C2935
0x1800c28f4  mov     eax, cs:dword_1801B76C8
0x1800c28fa  cmp     eax, 5
0x1800c28fd  jbe     short loc_1800C2930
0x1800c28ff  lea     rax, aMappedSharedBu_0; "Mapped Shared Buffer."
0x1800c2906  mov     dword ptr [rsp+4B0h+var_458], r14d
0x1800c290b  mov     [rsp+4B0h+var_450], rax
0x1800c2910  lea     rdx, word_1801A8162
0x1800c2917  lea     rax, [rsp+4B0h+var_458]
0x1800c291c  mov     [rsp+4B0h+var_488], rax
0x1800c2921  lea     rax, [rsp+4B0h+var_450]
0x1800c2926  mov     [rsp+4B0h+dwNumberOfBytesToMap], rax
0x1800c292b  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1800c2930  mov     [r15], rbx
0x1800c2933  xor     ebx, ebx
0x1800c2935  mov     rcx, rdi; hObject
0x1800c2938  call    cs:__imp_CloseHandle
0x1800c293e  jmp     loc_1800C29D1
0x1800c2943  call    cs:__imp_GetLastError
0x1800c2949  mov     ebx, eax
0x1800c294b  test    eax, eax
0x1800c294d  jle     short loc_1800C2958
0x1800c294f  movzx   ebx, ax
0x1800c2952  or      ebx, 80070000h
0x1800c2958  mov     eax, cs:dword_1801B76C8
0x1800c295e  cmp     eax, 2
0x1800c2961  jbe     short loc_1800C29D1
0x1800c2963  lea     rax, aMapsharedbuffe; "MapSharedBuffer"
0x1800c296a  mov     dword ptr [rsp+4B0h+var_458], 352h
0x1800c2972  mov     [rsp+4B0h+var_450], rax
0x1800c2977  lea     rdx, byte_1801A81C1
0x1800c297e  lea     rax, aClientcoreTerm_4; "clientcore\\termsrv\\rdpplatform\\gfxpi"...
0x1800c2985  mov     [rsp+4B0h+var_460], ebx
0x1800c2989  mov     [rsp+4B0h+var_448], rax
0x1800c298e  lea     rax, aFailedToCreate_30; "Failed to create mapping"
0x1800c2995  mov     [rsp+4B0h+var_440], rax
0x1800c299a  lea     rax, [rsp+4B0h+var_450]
0x1800c299f  mov     [rsp+4B0h+var_470], rax
0x1800c29a4  lea     rax, [rsp+4B0h+var_458]
0x1800c29a9  mov     [rsp+4B0h+var_478], rax
0x1800c29ae  lea     rax, [rsp+4B0h+var_448]
0x1800c29b3  mov     [rsp+4B0h+var_480], rax
0x1800c29b8  lea     rax, [rsp+4B0h+var_460]
0x1800c29bd  mov     [rsp+4B0h+var_488], rax
0x1800c29c2  lea     rax, [rsp+4B0h+var_440]
0x1800c29c7  mov     [rsp+4B0h+dwNumberOfBytesToMap], rax
0x1800c29cc  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x1800c29d1  mov     eax, ebx
0x1800c29d3  mov     rcx, [rbp+3B0h+var_30]
0x1800c29da  xor     rcx, rsp; StackCookie
0x1800c29dd  call    __security_check_cookie
0x1800c29e2  mov     rbx, [rsp+4B0h+arg_8]
0x1800c29ea  add     rsp, 490h
0x1800c29f1  pop     r15
0x1800c29f3  pop     r14
0x1800c29f5  pop     rdi
0x1800c29f6  pop     rsi
0x1800c29f7  pop     rbp
0x1800c29f8  retn
```
