# SaveSomeData(int,int,int,IIS_CRYPTO_STORAGE *,_IIS_CRYPTO_BLOB *,ushort const *,ulong,ushort const *,int)

- ea: `0x180024e90`
- end: `0x1800255bb`
- name: `?SaveSomeData@@YAJHHHPEAVIIS_CRYPTO_STORAGE@@PEFAU_IIS_CRYPTO_BLOB@@PEBGK2H@Z`
- size: `1835`
- prototype: `__int64 __fastcall(int, int, __int64, struct IIS_CRYPTO_STORAGE *, struct _IIS_CRYPTO_BLOB *, wchar_t *Str, unsigned int, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180017e90`

## callees

- `0x180002d60`
- `0x180005cd8`
- `0x180008a08`
- `0x18001e9a8`
- `0x180024388`
- `0x1800246a4`
- `0x180024e90`
- `0x18002d45c`
- `0x18002d4fc`
- `0x18002d788`
- `0x18002db80`
- `0x1800309d0`
- `0x180030a60`

## import_xrefs

- `msvcrt!wcschr` at `0x180024f1b`
- `msvcrt!wcschr` at `0x180024f1b`
- `ole32!CoRevertToSelf` at `0x18002552b`
- `ole32!CoRevertToSelf` at `0x18002552b`
- `ole32!CoImpersonateClient` at `0x1800254e0`
- `ole32!CoImpersonateClient` at `0x1800254e0`
- `KERNEL32!CreateFileW` at `0x18002504e`
- `KERNEL32!CreateFileW` at `0x18002504e`
- `KERNEL32!CloseHandle` at `0x18002545c`
- `KERNEL32!CloseHandle` at `0x1800254b5`
- `KERNEL32!CloseHandle` at `0x18002545c`
- `KERNEL32!CloseHandle` at `0x1800254b5`
- `KERNEL32!MoveFileExW` at `0x18002550f`
- `KERNEL32!MoveFileExW` at `0x18002550f`
- `KERNEL32!DeleteFileW` at `0x180025572`
- `KERNEL32!DeleteFileW` at `0x180025572`
- `KERNEL32!GetLastError` at `0x180025062`
- `KERNEL32!GetLastError` at `0x180025108`
- `KERNEL32!GetLastError` at `0x180025466`
- `KERNEL32!GetLastError` at `0x1800254bf`
- `KERNEL32!GetLastError` at `0x180025519`
- `KERNEL32!GetLastError` at `0x180025062`
- `KERNEL32!GetLastError` at `0x180025108`
- `KERNEL32!GetLastError` at `0x180025466`
- `KERNEL32!GetLastError` at `0x1800254bf`
- `KERNEL32!GetLastError` at `0x180025519`
- `IisRTL!?FreeMemory@BUFFER@@QEAAXXZ` at `0x18002557c`
- `IisRTL!?FreeMemory@BUFFER@@QEAAXXZ` at `0x18002557c`
- `IisRTL!?QueryStr@STR@@QEBAPEADXZ` at `0x180024f86`
- `IisRTL!?QueryStr@STR@@QEBAPEADXZ` at `0x180024f86`
- `IisRTL!?Resize@BUFFER@@QEAA_NK@Z` at `0x1800250fe`
- `IisRTL!?Resize@BUFFER@@QEAA_NK@Z` at `0x1800250fe`
- `IisRTL!PuDbgPrint` at `0x180024f63`
- `IisRTL!PuDbgPrint` at `0x180024fdd`
- `IisRTL!PuDbgPrint` at `0x180025203`
- `IisRTL!PuDbgPrint` at `0x180025320`
- `IisRTL!PuDbgPrint` at `0x1800254ac`
- `IisRTL!PuDbgPrint` at `0x180025569`
- `IisRTL!PuDbgPrint` at `0x180024f63`
- `IisRTL!PuDbgPrint` at `0x180024fdd`
- `IisRTL!PuDbgPrint` at `0x180025203`
- `IisRTL!PuDbgPrint` at `0x180025320`
- `IisRTL!PuDbgPrint` at `0x1800254ac`
- `IisRTL!PuDbgPrint` at `0x180025569`
- `IisRTL!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18002521a`
- `IisRTL!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180025453`
- `IisRTL!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18002521a`
- `IisRTL!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180025453`
- `IisRTL!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x180024f79`
- `IisRTL!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x180024f79`
- `IisRTL!PuDbgPrintW` at `0x18002527f`
- `IisRTL!PuDbgPrintW` at `0x18002527f`
- `IisRTL!??0BUFFER@@QEAA@XZ` at `0x180024ef9`
- `IisRTL!??0BUFFER@@QEAA@XZ` at `0x180024ef9`
- `IisRTL!??1BUFFER@@QEAA@XZ` at `0x180025590`
- `IisRTL!??1BUFFER@@QEAA@XZ` at `0x180025590`
- `IisRTL!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18002513a`
- `IisRTL!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18002518a`
- `IisRTL!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18002513a`
- `IisRTL!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18002518a`

## string_xrefs

- `0x180025273`: `[SaveSchema] Initializing writer with write file: %s bin file: %s.\n`

## pseudocode

```c
__int64 __fastcall SaveSomeData(
        int a1,
        int a2,
        __int64 a3,
        struct IIS_CRYPTO_STORAGE *a4,
        struct _IIS_CRYPTO_BLOB *a5,
        wchar_t *Str,
        unsigned int a7,
        const unsigned __int16 *a8)
{
  int v8; // r12d
  signed int j; // ebx
  __int64 v10; // rsi
  const CHAR *v11; // rax
  int UnicodeNameA; // eax
  signed int LastError; // eax
  struct CMDHandle *HandleObject; // rax
  struct CMDHandle *v15; // r15
  __int64 v16; // rdi
  signed int v17; // eax
  _DWORD *Ptr; // rax
  _DWORD *v19; // rdx
  int i; // eax
  __int64 v21; // r8
  unsigned __int16 v22; // cx
  _DWORD *v23; // rax
  __int64 v24; // rdx
  char v25; // r9
  const WCHAR *v26; // rdi
  int v27; // eax
  __int64 v28; // r8
  struct _IIS_CRYPTO_BLOB *v29; // r14
  struct IIS_CRYPTO_STORAGE *v30; // r14
  signed int v31; // eax
  signed int v32; // eax
  HRESULT v33; // eax
  signed int v34; // eax
  struct _IIS_CRYPTO_BLOB *dwCreationDispositiona; // [rsp+20h] [rbp-E0h]
  struct _IIS_CRYPTO_BLOB *dwCreationDisposition; // [rsp+20h] [rbp-E0h]
  LPCWSTR lpFileName; // [rsp+40h] [rbp-C0h] BYREF
  int v39; // [rsp+48h] [rbp-B8h]
  int v40; // [rsp+4Ch] [rbp-B4h]
  HANDLE hObject; // [rsp+50h] [rbp-B0h]
  struct _IIS_CRYPTO_BLOB *v42; // [rsp+58h] [rbp-A8h]
  struct IIS_CRYPTO_STORAGE *v43; // [rsp+60h] [rbp-A0h]
  LPCWSTR lpNewFileName; // [rsp+68h] [rbp-98h]
  struct _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v46[56]; // [rsp+88h] [rbp-78h] BYREF
  _QWORD v47[2]; // [rsp+C0h] [rbp-40h] BYREF
  int v48; // [rsp+D0h] [rbp-30h]
  __int64 v49; // [rsp+100D8h] [rbp+FFD8h]
  __int128 v50; // [rsp+100E0h] [rbp+FFE0h]
  __int64 v51; // [rsp+100F0h] [rbp+FFF0h]
  __int64 v52; // [rsp+100F8h] [rbp+FFF8h]
  __int64 v53; // [rsp+10100h] [rbp+10000h]
  __int64 v54; // [rsp+10108h] [rbp+10008h]

  v40 = a1;
  v42 = a5;
  lpNewFileName = Str;
  v43 = a4;
  v39 = a2;
  BUFFER::BUFFER((BUFFER *)v46);
  v8 = 0;
  lpFileName = 0;
  memset(&SecurityAttributes, 0, sizeof(SecurityAttributes));
  if ( wcschr(Str, 0x5Cu) )
  {
    v10 = -1;
    CReaderWriterLock3::ReadLock((CReaderWriterLock3 *)&g_LockMasterResource);
    v11 = STR::QueryStr(g_strTempFileName);
    UnicodeNameA = GetUnicodeNameA(v11, (unsigned __int16 **)&lpFileName);
    j = UnicodeNameA;
    if ( UnicodeNameA < 0 )
    {
      if ( (g_dwDebugFlags & 0xF) != 0 )
        PuDbgPrint(
          g_pDebug,
          "inetsrv\\iis\\mb\\metadata\\metasub.cxx",
          11835,
          "SaveSomeData",
          "hr=0x%x\n",
          UnicodeNameA);
LABEL_50:
      v26 = lpFileName;
      goto LABEL_51;
    }
    if ( g_bSaveDisallowed )
    {
      j = -2147023781;
      if ( (g_dwDebugFlags & 0xF) != 0 )
        PuDbgPrint(g_pDebug, "inetsrv\\iis\\mb\\metadata\\metasub.cxx", 11845, "SaveSomeData", "hr=0x%x\n", -2147023781);
      goto LABEL_50;
    }
    SecurityAttributes.lpSecurityDescriptor = qword_180048AE8;
    SecurityAttributes.nLength = 24;
    SecurityAttributes.bInheritHandle = 0;
    hObject = CreateFileW(lpFileName, 0xC0000000, 0, &SecurityAttributes, 4u, 0x8000080u, 0);
    v10 = (__int64)hObject;
    if ( hObject == (HANDLE)-1LL )
    {
      LastError = GetLastError();
      j = LastError;
      if ( LastError > 0 )
        j = (unsigned __int16)LastError | 0x80070000;
      if ( (g_dwDebugFlags & 0xF) != 0 )
        PuDbgPrint(g_pDebug, "inetsrv\\iis\\mb\\metadata\\metasub.cxx", 11870, "SaveSomeData", "hr=0x%x\n", j);
      goto LABEL_50;
    }
    v8 = 1;
    HandleObject = GetHandleObject(a7);
    v15 = HandleObject;
    if ( !HandleObject )
    {
      j = -2147024890;
      goto LABEL_22;
    }
    if ( (*((_BYTE *)HandleObject + 12) & 1) == 0 && (*((_BYTE *)HandleObject + 12) & 2) == 0 )
    {
      j = -2147024891;
      goto LABEL_22;
    }
    if ( *((_DWORD *)HandleObject + 8) )
    {
      j = -2147024846;
LABEL_22:
      if ( (g_dwDebugFlags & 0xF) != 0 )
        PuDbgPrint(g_pDebug, "inetsrv\\iis\\mb\\metadata\\metasub.cxx", 11893, "SaveSomeData", "hr=0x%x\n", j);
      goto LABEL_50;
    }
    v16 = -1;
    do
      ++v16;
    while ( a8[v16] );
    if ( !BUFFER::Resize((BUFFER *)v46, 2 * v16 + 4) )
    {
      v17 = GetLastError();
      j = v17;
      if ( v17 > 0 )
        j = (unsigned __int16)v17 | 0x80070000;
      if ( (g_dwDebugFlags & 0xF) != 0 )
        PuDbgPrint(g_pDebug, "inetsrv\\iis\\mb\\metadata\\metasub.cxx", 11905, "SaveSomeData", "hr=0x%x\n", j);
      goto LABEL_50;
    }
    Ptr = BUFFER::QueryPtr((BUFFER *)v46);
    v19 = Ptr;
    if ( *a8 )
    {
      for ( i = 0; i < (int)v16; *((_WORD *)v19 + v21) = v22 )
      {
        v21 = (unsigned int)i;
        v22 = a8[i];
        if ( v22 == 92 )
          v22 = 47;
        ++i;
      }
      *((_WORD *)v19 + i) = 0;
      v23 = BUFFER::QueryPtr((BUFFER *)v46);
      v24 = (unsigned int)(v16 - 1);
      v25 = 0;
      for ( j = -2147024773; (int)v24 >= 0; v24 = (unsigned int)(v24 - 1) )
      {
        if ( *((_WORD *)v23 + v24) == 47 )
        {
          j = 0;
          if ( v25 )
            break;
        }
        else
        {
          v25 = 1;
        }
        *((_WORD *)v23 + v24) = 0;
      }
      if ( !*(_WORD *)v23 && (int)v16 > 0 )
        *v23 = 47;
      if ( j < 0 )
      {
        if ( (g_dwDebugFlags & 0xF) != 0 )
          PuDbgPrint(g_pDebug, "inetsrv\\iis\\mb\\metadata\\metasub.cxx", 11927, "SaveSomeData", "hr=0x%x\n", j);
        v10 = (__int64)hObject;
        goto LABEL_50;
      }
    }
    else
    {
      *Ptr = 47;
    }
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrintW(
        g_pDebug,
        "inetsrv\\iis\\mb\\metadata\\metasub.cxx",
        11938,
        "SaveSomeData",
        L"[SaveSchema] Initializing writer with write file: %s bin file: %s.\n",
        g_wszTempFileName,
        *((_QWORD *)g_pGlobalISTHelper + 31));
    v10 = (__int64)hObject;
    v26 = lpFileName;
    v47[0] = 0;
    v52 = -1;
    v47[1] = 0;
    v53 = 0;
    v54 = 0;
    v48 = 0;
    v49 = 0;
    v50 = 0;
    v51 = 0;
    v27 = CWriter::Initialize((CWriter *)v47, lpFileName, g_pGlobalISTHelper, hObject);
    j = v27;
    if ( v27 >= 0 )
    {
      v27 = CWriter::BeginWrite(v47, 1, 0);
      j = v27;
      if ( v27 >= 0 )
      {
        v29 = v42;
        v27 = SaveGlobalsToXML((struct CWriter *)v47, v42, 1);
        j = v27;
        if ( v27 >= 0 )
        {
          dwCreationDispositiona = v29;
          v30 = v43;
          j = SaveTree(
                (struct CWriter *)v47,
                *((struct CMDBaseObject **)v15 + 3),
                (struct BUFFER *)v46,
                v43,
                dwCreationDispositiona,
                v39 == 0,
                0,
                0);
          if ( j < 0 )
          {
            if ( (g_dwDebugFlags & 0xF) != 0 )
              PuDbgPrint(g_pDebug, "inetsrv\\iis\\mb\\metadata\\metasub.cxx", 11981, "SaveSomeData", "hr=0x%x\n", j);
            goto LABEL_59;
          }
          if ( v40
            && (v27 = SaveInheritedOnly(
                        (struct CWriter *)v47,
                        *((struct CMDBaseObject **)v15 + 3),
                        (struct BUFFER *)v46,
                        v30,
                        dwCreationDisposition),
                j = v27,
                v27 < 0) )
          {
            if ( (g_dwDebugFlags & 0xF) == 0 )
              goto LABEL_59;
            v28 = 11995;
          }
          else
          {
            v27 = CWriter::EndWrite(v47, 1);
            j = v27;
            if ( v27 >= 0 )
            {
              CWriter::~CWriter((CWriter *)v47);
              CReaderWriterLock3::ReadUnlock((CReaderWriterLock3 *)&g_LockMasterResource);
              if ( CloseHandle((HANDLE)v10) )
              {
                v33 = CoImpersonateClient();
                j = v33;
                if ( v33 >= 0 )
                {
                  if ( !MoveFileExW(v26, lpNewFileName, 3u) )
                  {
                    v34 = GetLastError();
                    j = v34;
                    if ( v34 > 0 )
                      j = (unsigned __int16)v34 | 0x80070000;
                  }
                  CoRevertToSelf();
                  if ( j < 0 && (g_dwDebugFlags & 0xF) != 0 )
                    PuDbgPrint(
                      g_pDebug,
                      "inetsrv\\iis\\mb\\metadata\\metasub.cxx",
                      12038,
                      "SaveSomeData",
                      "hr=0x%x\n",
                      j);
                }
                else if ( (g_dwDebugFlags & 0xF) != 0 )
                {
                  PuDbgPrint(
                    g_pDebug,
                    "inetsrv\\iis\\mb\\metadata\\metasub.cxx",
                    12026,
                    "SaveSomeData",
                    "hr=0x%x\n",
                    v33);
                }
                goto LABEL_95;
              }
              v31 = GetLastError();
              j = v31;
              if ( v31 > 0 )
                j = (unsigned __int16)v31 | 0x80070000;
              if ( (g_dwDebugFlags & 0xF) != 0 )
                PuDbgPrint(g_pDebug, "inetsrv\\iis\\mb\\metadata\\metasub.cxx", 12014, "SaveSomeData", "hr=0x%x\n", j);
LABEL_81:
              CloseHandle((HANDLE)v10);
              if ( j >= 0 )
              {
                v32 = GetLastError();
                j = v32;
                if ( v32 > 0 )
                  j = (unsigned __int16)v32 | 0x80070000;
              }
LABEL_84:
              if ( v10 == -1 )
                goto LABEL_96;
LABEL_95:
              DeleteFileW(v26);
              goto LABEL_96;
            }
            if ( (g_dwDebugFlags & 0xF) == 0 )
              goto LABEL_59;
            v28 = 12002;
          }
        }
        else
        {
          if ( (g_dwDebugFlags & 0xF) == 0 )
            goto LABEL_59;
          v28 = 11968;
        }
      }
      else
      {
        if ( (g_dwDebugFlags & 0xF) == 0 )
          goto LABEL_59;
        v28 = 11958;
      }
    }
    else
    {
      if ( (g_dwDebugFlags & 0xF) == 0 )
      {
LABEL_59:
        CWriter::~CWriter((CWriter *)v47);
LABEL_51:
        CReaderWriterLock3::ReadUnlock((CReaderWriterLock3 *)&g_LockMasterResource);
        if ( !v8 )
          goto LABEL_84;
        goto LABEL_81;
      }
      v28 = 11951;
    }
    PuDbgPrint(g_pDebug, "inetsrv\\iis\\mb\\metadata\\metasub.cxx", v28, "SaveSomeData", "hr=0x%x\n", v27);
    goto LABEL_59;
  }
  j = -2147023890;
  if ( (g_dwDebugFlags & 0xF) != 0 )
    PuDbgPrint(g_pDebug, "inetsrv\\iis\\mb\\metadata\\metasub.cxx", 11825, "SaveSomeData", "hr=0x%x\n", -2147023890);
LABEL_96:
  BUFFER::FreeMemory((BUFFER *)v46);
  operator delete((void *)lpFileName);
  BUFFER::~BUFFER((BUFFER *)v46);
  return (unsigned int)j;
}

```

## disassembly

```asm
0x180024e90  push    rbp
0x180024e92  push    rbx
0x180024e93  push    rsi
0x180024e94  push    rdi
0x180024e95  push    r12
0x180024e97  push    r13
0x180024e99  push    r14
0x180024e9b  push    r15
0x180024e9d  lea     rbp, [rsp-10028h]
0x180024ea5  mov     eax, 10128h
0x180024eaa  call    _alloca_probe
0x180024eaf  sub     rsp, rax
0x180024eb2  mov     rax, cs:__security_cookie
0x180024eb9  xor     rax, rsp
0x180024ebc  mov     [rbp+10060h+var_50], rax
0x180024ec3  mov     rax, [rbp+10060h+arg_20]
0x180024eca  mov     rbx, [rbp+10060h+Str]
0x180024ed1  mov     edi, [rbp+10060h+arg_30]
0x180024ed7  mov     r14, [rbp+10060h+arg_38]
0x180024ede  mov     [rsp+10160h+var_10114], ecx
0x180024ee2  lea     rcx, [rbp+10060h+var_100D8]
0x180024ee6  mov     [rsp+10160h+var_10108], rax
0x180024eeb  mov     [rsp+10160h+lpNewFileName], rbx
0x180024ef0  mov     [rsp+10160h+var_10100], r9
0x180024ef5  mov     [rsp+10160h+var_10118], edx
0x180024ef9  call    cs:__imp_??0BUFFER@@QEAA@XZ; BUFFER::BUFFER(void)
0x180024eff  xor     eax, eax
0x180024f01  xorps   xmm0, xmm0
0x180024f04  xor     r12d, r12d
0x180024f07  mov     qword ptr [rbp+10060h+SecurityAttributes.bInheritHandle], rax
0x180024f0b  mov     rcx, rbx; Str
0x180024f0e  mov     [rsp+10160h+lpFileName], r12
0x180024f13  movups  xmmword ptr [rsp+10160h+SecurityAttributes.nLength], xmm0
0x180024f18  lea     edx, [rax+5Ch]; Ch
0x180024f1b  call    cs:__imp_wcschr
0x180024f21  test    rax, rax
0x180024f24  jnz     short loc_180024F6E
0x180024f26  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180024f2d  mov     ebx, 800703EEh
0x180024f32  jz      loc_180025578
0x180024f38  mov     rcx, cs:g_pDebug
0x180024f3f  lea     rax, aHr0xX; "hr=0x%x\n"
0x180024f46  mov     [rsp+10160h+dwFlagsAndAttributes], ebx
0x180024f4a  lea     r9, aSavesomedata; "SaveSomeData"
0x180024f51  mov     r8d, 2E31h
0x180024f57  mov     qword ptr [rsp+10160h+dwCreationDisposition], rax
0x180024f5c  lea     rdx, aInetsrvIisMbMe; "inetsrv\\iis\\mb\\metadata\\metasub.cxx"
0x180024f63  call    cs:__imp_PuDbgPrint
0x180024f69  jmp     loc_180025578
0x180024f6e  lea     rcx, ?g_LockMasterResource@@3VCReaderWriterLock3@@A; CReaderWriterLock3 g_LockMasterResource
0x180024f75  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180024f79  call    cs:__imp_?ReadLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadLock(void)
0x180024f7f  mov     rcx, cs:?g_strTempFileName@@3PEAVSTR@@EA; STR * g_strTempFileName
0x180024f86  call    cs:__imp_?QueryStr@STR@@QEBAPEADXZ; STR::QueryStr(void)
0x180024f8c  mov     rcx, rax; lpMultiByteStr
0x180024f8f  lea     rdx, [rsp+10160h+lpFileName]; unsigned __int16 **
0x180024f94  call    ?GetUnicodeNameA@@YAJPEADPEAPEAG@Z; GetUnicodeNameA(char *,ushort * *)
0x180024f99  mov     ebx, eax
0x180024f9b  mov     r13d, 80070000h
0x180024fa1  test    eax, eax
0x180024fa3  jns     short loc_180024FE8
0x180024fa5  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180024fac  jz      loc_18002520E
0x180024fb2  mov     [rsp+10160h+dwFlagsAndAttributes], eax
0x180024fb6  mov     r8d, 2E3Bh
0x180024fbc  mov     rcx, cs:g_pDebug
0x180024fc3  lea     rax, aHr0xX; "hr=0x%x\n"
0x180024fca  lea     r9, aSavesomedata; "SaveSomeData"
0x180024fd1  mov     qword ptr [rsp+10160h+dwCreationDisposition], rax
0x180024fd6  lea     rdx, aInetsrvIisMbMe; "inetsrv\\iis\\mb\\metadata\\metasub.cxx"
0x180024fdd  call    cs:__imp_PuDbgPrint
0x180024fe3  jmp     loc_18002520E
0x180024fe8  xor     ebx, ebx
0x180024fea  cmp     cs:?g_bSaveDisallowed@@3HA, ebx; int g_bSaveDisallowed
0x180024ff0  jz      short loc_180025010
0x180024ff2  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180024ff9  mov     ebx, 8007045Bh
0x180024ffe  jz      loc_18002520E
0x180025004  mov     [rsp+10160h+dwFlagsAndAttributes], ebx
0x180025008  mov     r8d, 2E45h
0x18002500e  jmp     short loc_180024FBC
0x180025010  mov     rcx, [rsp+10160h+lpFileName]; lpFileName
0x180025015  lea     rax, qword_180048AE8
0x18002501c  mov     [rsp+10160h+hTemplateFile], rbx; hTemplateFile
0x180025021  lea     r9, [rsp+10160h+SecurityAttributes]; lpSecurityAttributes
0x180025026  mov     [rsp+10160h+dwFlagsAndAttributes], 8000080h; dwFlagsAndAttributes
0x18002502e  xor     r8d, r8d; dwShareMode
0x180025031  mov     edx, 0C0000000h; dwDesiredAccess
0x180025036  mov     [rsp+10160h+SecurityAttributes.lpSecurityDescriptor], rax
0x18002503b  mov     [rsp+10160h+dwCreationDisposition], 4; dwCreationDisposition
0x180025043  mov     [rsp+10160h+SecurityAttributes.nLength], 18h
0x18002504b  mov     [rbp+10060h+SecurityAttributes.bInheritHandle], ebx
0x18002504e  call    cs:__imp_CreateFileW
0x180025054  mov     [rsp+10160h+hObject], rax
0x180025059  mov     rsi, rax
0x18002505c  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180025060  jnz     short loc_180025090
0x180025062  call    cs:__imp_GetLastError
0x180025068  mov     ebx, eax
0x18002506a  test    eax, eax
0x18002506c  jle     short loc_180025074
0x18002506e  movzx   ebx, ax
0x180025071  or      ebx, r13d
0x180025074  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18002507b  jz      loc_18002520E
0x180025081  mov     [rsp+10160h+dwFlagsAndAttributes], ebx
0x180025085  mov     r8d, 2E5Eh
0x18002508b  jmp     loc_180024FBC
0x180025090  mov     ecx, edi; unsigned int
0x180025092  mov     r12d, 1
0x180025098  call    ?GetHandleObject@@YAPEAVCMDHandle@@K@Z; GetHandleObject(ulong)
0x18002509d  mov     r15, rax
0x1800250a0  test    rax, rax
0x1800250a3  jnz     short loc_1800250AC
0x1800250a5  mov     ebx, 80070006h
0x1800250aa  jmp     short loc_1800250C9
0x1800250ac  test    [rax+0Ch], r12b
0x1800250b0  jnz     short loc_1800250BF
0x1800250b2  test    byte ptr [rax+0Ch], 2
0x1800250b6  jnz     short loc_1800250BF
0x1800250b8  mov     ebx, 80070005h
0x1800250bd  jmp     short loc_1800250C9
0x1800250bf  cmp     [rax+20h], ebx
0x1800250c2  jz      short loc_1800250E5
0x1800250c4  mov     ebx, 80070032h
0x1800250c9  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x1800250d0  jz      loc_18002520E
0x1800250d6  mov     [rsp+10160h+dwFlagsAndAttributes], ebx
0x1800250da  mov     r8d, 2E75h
0x1800250e0  jmp     loc_180024FBC
0x1800250e5  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800250e9  inc     rdi
0x1800250ec  cmp     [r14+rdi*2], bx
0x1800250f1  jnz     short loc_1800250E9
0x1800250f3  lea     edx, ds:4[rdi*2]
0x1800250fa  lea     rcx, [rbp+10060h+var_100D8]
0x1800250fe  call    cs:__imp_?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x180025104  test    al, al
0x180025106  jnz     short loc_180025136
0x180025108  call    cs:__imp_GetLastError
0x18002510e  mov     ebx, eax
0x180025110  test    eax, eax
0x180025112  jle     short loc_18002511A
0x180025114  movzx   ebx, ax
0x180025117  or      ebx, r13d
0x18002511a  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180025121  jz      loc_18002520E
0x180025127  mov     [rsp+10160h+dwFlagsAndAttributes], ebx
0x18002512b  mov     r8d, 2E81h
0x180025131  jmp     loc_180024FBC
0x180025136  lea     rcx, [rbp+10060h+var_100D8]
0x18002513a  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180025140  mov     rdx, rax
0x180025143  cmp     [r14], bx
0x180025147  jnz     short loc_180025154
0x180025149  mov     dword ptr [rax], 2Fh ; '/'
0x18002514f  jmp     loc_180025230
0x180025154  mov     eax, ebx
0x180025156  mov     esi, 2Fh ; '/'
0x18002515b  test    edi, edi
0x18002515d  jle     short loc_18002517F
0x18002515f  lea     r9d, [rsi+2Dh]
0x180025163  mov     r8d, eax
0x180025166  movzx   ecx, word ptr [r14+r8*2]
0x18002516b  cmp     cx, r9w
0x18002516f  jnz     short loc_180025173
0x180025171  mov     ecx, esi
0x180025173  add     eax, r12d
0x180025176  mov     [rdx+r8*2], cx
0x18002517b  cmp     eax, edi
0x18002517d  jl      short loc_180025163
0x18002517f  movsxd  rcx, eax
0x180025182  mov     [rdx+rcx*2], bx
0x180025186  lea     rcx, [rbp+10060h+var_100D8]
0x18002518a  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180025190  lea     edx, [rdi-1]
0x180025193  xor     r10d, r10d
0x180025196  mov     r9b, bl
0x180025199  mov     ebx, 8007007Bh
0x18002519e  test    edx, edx
0x1800251a0  js      short loc_1800251BF
0x1800251a2  cmp     [rax+rdx*2], si
0x1800251a6  jnz     short loc_1800251B2
0x1800251a8  mov     ebx, r10d
0x1800251ab  test    r9b, r9b
0x1800251ae  jnz     short loc_1800251BF
0x1800251b0  jmp     short loc_1800251B5
0x1800251b2  mov     r9b, r12b
0x1800251b5  mov     [rax+rdx*2], r10w
0x1800251ba  sub     edx, r12d
0x1800251bd  jns     short loc_1800251A2
0x1800251bf  cmp     [rax], r10w
0x1800251c3  jnz     short loc_1800251CB
0x1800251c5  test    edi, edi
0x1800251c7  jle     short loc_1800251CB
0x1800251c9  mov     [rax], esi
0x1800251cb  test    ebx, ebx
0x1800251cd  jns     short loc_18002522E
0x1800251cf  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x1800251d6  jz      short loc_180025209
0x1800251d8  mov     rcx, cs:g_pDebug
0x1800251df  lea     rax, aHr0xX; "hr=0x%x\n"
0x1800251e6  mov     [rsp+10160h+dwFlagsAndAttributes], ebx
0x1800251ea  lea     r9, aSavesomedata; "SaveSomeData"
0x1800251f1  mov     r8d, 2E97h
0x1800251f7  mov     qword ptr [rsp+10160h+dwCreationDisposition], rax
0x1800251fc  lea     rdx, aInetsrvIisMbMe; "inetsrv\\iis\\mb\\metadata\\metasub.cxx"
0x180025203  call    cs:__imp_PuDbgPrint
0x180025209  mov     rsi, [rsp+10160h+hObject]
0x18002520e  mov     rdi, [rsp+10160h+lpFileName]
0x180025213  lea     rcx, ?g_LockMasterResource@@3VCReaderWriterLock3@@A; CReaderWriterLock3 g_LockMasterResource
0x18002521a  call    cs:__imp_?ReadUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadUnlock(void)
0x180025220  test    r12d, r12d
0x180025223  jz      loc_1800254D1
0x180025229  jmp     loc_1800254B2
0x18002522e  xor     ebx, ebx
0x180025230  test    byte ptr cs:g_dwDebugFlags, 3
0x180025237  jz      short loc_180025285
0x180025239  mov     rax, cs:?g_pGlobalISTHelper@@3PEAVCWriterGlobalHelper@@EA; CWriterGlobalHelper * g_pGlobalISTHelper
0x180025240  lea     r9, aSavesomedata; "SaveSomeData"
0x180025247  mov     r8d, 2EA2h
0x18002524d  lea     rdx, aInetsrvIisMbMe; "inetsrv\\iis\\mb\\metadata\\metasub.cxx"
0x180025254  mov     rcx, [rax+0F8h]
0x18002525b  mov     rax, cs:?g_wszTempFileName@@3PEAGEA; ushort * g_wszTempFileName
0x180025262  mov     [rsp+10160h+hTemplateFile], rcx
0x180025267  mov     rcx, cs:g_pDebug
0x18002526e  mov     qword ptr [rsp+10160h+dwFlagsAndAttributes], rax
0x180025273  lea     rax, aSaveschemaInit; "[SaveSchema] Initializing writer with w"...
0x18002527a  mov     qword ptr [rsp+10160h+dwCreationDisposition], rax
0x18002527f  call    cs:__imp_PuDbgPrintW
0x180025285  mov     rsi, [rsp+10160h+hObject]
0x18002528a  lea     rcx, [rbp+10060h+var_100A0]; this
0x18002528e  mov     rdi, [rsp+10160h+lpFileName]
0x180025293  xorps   xmm0, xmm0
0x180025296  mov     r8, cs:?g_pGlobalISTHelper@@3PEAVCWriterGlobalHelper@@EA; struct CWriterGlobalHelper *
0x18002529d  mov     r9, rsi; void *
0x1800252a0  mov     rdx, rdi; unsigned __int16 *
0x1800252a3  mov     [rbp+10060h+var_100A0], rbx
0x1800252a7  mov     [rbp+10060h+var_68], 0FFFFFFFFFFFFFFFFh
0x1800252b2  mov     [rbp+10060h+var_10098], 0
0x1800252ba  mov     [rbp+10060h+var_60], rbx
0x1800252c1  mov     [rbp+10060h+var_58], rbx
0x1800252c8  mov     [rbp+10060h+var_10090], ebx
0x1800252cb  mov     [rbp+10060h+var_88], rbx
0x1800252d2  movdqa  [rbp+10060h+var_80], xmm0
0x1800252da  mov     [rbp+10060h+var_70], rbx
0x1800252e1  call    ?Initialize@CWriter@@QEAAJPEBGPEAVCWriterGlobalHelper@@PEAX@Z; CWriter::Initialize(ushort const *,CWriterGlobalHelper *,void *)
0x1800252e6  mov     ebx, eax
0x1800252e8  test    eax, eax
0x1800252ea  jns     short loc_180025334
0x1800252ec  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x1800252f3  jz      short loc_180025326
0x1800252f5  mov     r8d, 2EAFh
0x1800252fb  mov     [rsp+10160h+dwFlagsAndAttributes], eax
0x1800252ff  mov     rcx, cs:g_pDebug
0x180025306  lea     rax, aHr0xX; "hr=0x%x\n"
0x18002530d  lea     r9, aSavesomedata; "SaveSomeData"
0x180025314  mov     qword ptr [rsp+10160h+dwCreationDisposition], rax
0x180025319  lea     rdx, aInetsrvIisMbMe; "inetsrv\\iis\\mb\\metadata\\metasub.cxx"
0x180025320  call    cs:__imp_PuDbgPrint
0x180025326  lea     rcx, [rbp+10060h+var_100A0]; this
0x18002532a  call    ??1CWriter@@QEAA@XZ; CWriter::~CWriter(void)
0x18002532f  jmp     loc_180025213
0x180025334  xor     r8d, r8d
0x180025337  lea     rcx, [rbp+10060h+var_100A0]
0x18002533b  mov     edx, r12d
0x18002533e  call    ?BeginWrite@CWriter@@QEAAJW4eWriter@@PEAU_SECURITY_ATTRIBUTES@@@Z; CWriter::BeginWrite(eWriter,_SECURITY_ATTRIBUTES *)
0x180025343  mov     ebx, eax
0x180025345  test    eax, eax
0x180025347  jns     short loc_18002535A
0x180025349  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180025350  jz      short loc_180025326
0x180025352  mov     r8d, 2EB6h
0x180025358  jmp     short loc_1800252FB
0x18002535a  mov     r14, [rsp+10160h+var_10108]
0x18002535f  lea     rcx, [rbp+10060h+var_100A0]; struct CWriter *
0x180025363  mov     rdx, r14; struct _IIS_CRYPTO_BLOB *
0x180025366  mov     r8b, r12b; bool
0x180025369  call    ?SaveGlobalsToXML@@YAJPEAVCWriter@@PEFAU_IIS_CRYPTO_BLOB@@_N@Z; SaveGlobalsToXML(CWriter *,_IIS_CRYPTO_BLOB *,bool)
0x18002536e  xor     ecx, ecx
0x180025370  mov     ebx, eax
0x180025372  test    eax, eax
0x180025374  jns     short loc_18002538A
0x180025376  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18002537d  jz      short loc_180025326
0x18002537f  mov     r8d, 2EC0h
0x180025385  jmp     loc_1800252FB
0x18002538a  cmp     [rsp+10160h+var_10118], ecx
0x18002538e  lea     r8, [rbp+10060h+var_100D8]; struct BUFFER *
0x180025392  mov     rdx, [r15+18h]; struct CMDBaseObject *
0x180025396  mov     eax, ecx
0x180025398  mov     [rsp+10160h+var_10128], ecx; int
0x18002539c  setz    al
0x18002539f  mov     dword ptr [rsp+10160h+hTemplateFile], ecx; int
0x1800253a3  lea     rcx, [rbp+10060h+var_100A0]; struct CWriter *
0x1800253a7  mov     [rsp+10160h+dwFlagsAndAttributes], eax; int
0x1800253ab  mov     qword ptr [rsp+10160h+dwCreationDisposition], r14; struct _IIS_CRYPTO_BLOB *
0x1800253b0  mov     r14, [rsp+10160h+var_10100]
0x1800253b5  mov     r9, r14; struct IIS_CRYPTO_STORAGE *
0x1800253b8  call    ?SaveTree@@YAJPEAVCWriter@@PEAVCMDBaseObject@@PEAVBUFFER@@PEAVIIS_CRYPTO_STORAGE@@PEFAU_IIS_CRYPTO_BLOB@@HHH@Z; SaveTree(CWriter *,CMDBaseObject *,BUFFER *,IIS_CRYPTO_STORAGE *,_IIS_CRYPTO_BLOB *,int,int,int)
  ... truncated ...
```
