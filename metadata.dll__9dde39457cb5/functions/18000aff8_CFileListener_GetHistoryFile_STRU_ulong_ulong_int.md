# CFileListener::GetHistoryFile(STRU *,ulong *,ulong *,int *)

- ea: `0x18000aff8`
- end: `0x18000b398`
- name: `?GetHistoryFile@CFileListener@@AEAAJPEAVSTRU@@PEAK1PEAH@Z`
- size: `928`
- prototype: `__int64 __fastcall(CFileListener *__hidden this, struct STRU *, unsigned int *, unsigned int *, int *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x18000d374`

## callees

- `0x180008a08`
- `0x18000aff8`
- `0x18000b7cc`
- `0x18001c3c4`
- `0x18002056c`
- `0x180021118`
- `0x18003099a`
- `0x1800309d0`

## import_xrefs

- `msvcrt!_snwprintf_s` at `0x18000b258`
- `msvcrt!_snwprintf_s` at `0x18000b258`
- `msvcrt!wcsstr` at `0x18000b2da`
- `msvcrt!wcsstr` at `0x18000b2da`
- `KERNEL32!FindClose` at `0x18000b359`
- `KERNEL32!FindClose` at `0x18000b359`
- `KERNEL32!FindNextFileW` at `0x18000b287`
- `KERNEL32!FindNextFileW` at `0x18000b287`
- `KERNEL32!FindFirstFileW` at `0x18000b16a`
- `KERNEL32!FindFirstFileW` at `0x18000b16a`
- `KERNEL32!GetLastError` at `0x18000b17d`
- `KERNEL32!GetLastError` at `0x18000b17d`
- `IisRTL!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000b338`
- `IisRTL!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000b338`
- `IisRTL!PuDbgPrintW` at `0x18000b15d`
- `IisRTL!PuDbgPrintW` at `0x18000b1f4`
- `IisRTL!PuDbgPrintW` at `0x18000b2ca`
- `IisRTL!PuDbgPrintW` at `0x18000b320`
- `IisRTL!PuDbgPrintW` at `0x18000b15d`
- `IisRTL!PuDbgPrintW` at `0x18000b1f4`
- `IisRTL!PuDbgPrintW` at `0x18000b2ca`
- `IisRTL!PuDbgPrintW` at `0x18000b320`

## pseudocode

```c
__int64 __fastcall CFileListener::GetHistoryFile(
        CFileListener *this,
        struct STRU *a2,
        unsigned int *a3,
        unsigned int *a4,
        int *a5)
{
  WCHAR *v9; // rdi
  CFileListener *v10; // rcx
  int VersionNumber; // eax
  unsigned int v12; // r9d
  signed int v13; // ebx
  unsigned int v14; // r13d
  int v15; // eax
  HANDLE FirstFileW; // r15
  signed int LastError; // eax
  unsigned int v18; // r9d
  unsigned int v19; // r14d
  unsigned int v20; // ebx
  __int64 v21; // r12
  wchar_t *v22; // rax
  const unsigned __int16 *v23; // rax
  unsigned __int16 *v25; // [rsp+20h] [rbp-E0h]
  char v26[8]; // [rsp+20h] [rbp-E0h]
  unsigned __int16 *v27; // [rsp+30h] [rbp-D0h]
  unsigned __int16 *v28; // [rsp+38h] [rbp-C8h]
  unsigned __int16 *v29; // [rsp+40h] [rbp-C0h]
  unsigned __int16 *v30; // [rsp+48h] [rbp-B8h]
  unsigned int v31; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v32; // [rsp+54h] [rbp-ACh] BYREF
  unsigned int v33; // [rsp+58h] [rbp-A8h] BYREF
  LPCWSTR lpFileName; // [rsp+60h] [rbp-A0h] BYREF
  STRU *v35; // [rsp+68h] [rbp-98h]
  unsigned int *v36; // [rsp+70h] [rbp-90h]
  unsigned int *v37; // [rsp+78h] [rbp-88h]
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+80h] [rbp-80h] BYREF
  wchar_t Buffer[12]; // [rsp+2D0h] [rbp+1D0h] BYREF

  v35 = a2;
  v37 = a4;
  v36 = a3;
  v31 = 0;
  lpFileName = 0;
  memset(Buffer, 0, 22);
  v9 = 0;
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  v33 = 0;
  v32 = 0;
  if ( a2 && a3 && a4 && a5 )
  {
    VersionNumber = CFileListener::GetVersionNumber(v10, *((unsigned __int16 **)this + 27), &v31, a5);
    v13 = VersionNumber;
    if ( VersionNumber < 0 )
    {
      LogEvent(*((struct ICatalogErrorLogger2 **)this + 70), 0xC002C819, 1u, v12, VersionNumber, 0, 0, v28, v29, v30);
      return (unsigned int)v13;
    }
    v14 = v31;
    v15 = ConstructHistoryFileNameWithoutMinorVersion(
            (unsigned __int16 **)&lpFileName,
            &v33,
            *((unsigned __int16 **)this + 25),
            *((_DWORD *)this + 52),
            v25,
            *((_DWORD *)this + 24),
            v31);
    v9 = (WCHAR *)lpFileName;
    v13 = v15;
    if ( v15 >= 0 )
    {
      if ( (g_dwDebugFlags & 3) != 0 )
        PuDbgPrintW(
          g_pDebug,
          "inetsrv\\iis\\mb\\metadata\\listener.cpp",
          1482,
          "CFileListener::GetHistoryFile",
          L"[CFileListener::ProcessChanges] Searching for history files of type: %s.\n",
          lpFileName);
      FirstFileW = FindFirstFileW(v9, &FindFileData);
      if ( FirstFileW == (HANDLE)-1LL )
      {
        LastError = GetLastError();
        v13 = LastError;
        if ( LastError > 0 )
          v13 = (unsigned __int16)LastError | 0x80070000;
        LogEvent(*((struct ICatalogErrorLogger2 **)this + 70), 0xC002C812, 1u, v18, v13, v9, 0, v28, v29, v30);
        if ( (g_dwDebugFlags & 3) != 0 )
        {
          LODWORD(v27) = v13;
          PuDbgPrintW(
            g_pDebug,
            "inetsrv\\iis\\mb\\metadata\\listener.cpp",
            1506,
            "CFileListener::GetHistoryFile",
            L"[CFileListener::ProcessChanges] No history files found of type %s. FindFirstFileW failed with hr=0x%x.\n",
            v9,
            v27);
        }
        *a5 = 1;
      }
      else
      {
        v19 = 0;
        while ( 1 )
        {
          v13 = ParseVersionNumber(FindFileData.cFileName, *((_DWORD *)this + 20), &v32, 0);
          if ( v13 < 0 )
            break;
          v20 = v32;
          if ( v32 >= v19 )
          {
            v21 = v33;
            *(_DWORD *)v26 = v32;
            v9[v33] = 0;
            if ( _snwprintf_s(Buffer, 0xBu, 0xBu, L"%010lu", *(_QWORD *)v26) < 0 )
            {
              if ( (g_dwDebugFlags & 3) != 0 )
                PuDbgPrintW(
                  g_pDebug,
                  "inetsrv\\iis\\mb\\metadata\\listener.cpp",
                  1537,
                  "CFileListener::GetHistoryFile",
                  L"[ProcessChanges] _snwprintf returned a negative value. This should never happen.\n");
              v13 = -2147024883;
              break;
            }
            v19 = v20;
            *(_OWORD *)&v9[v21] = *(_OWORD *)Buffer;
            *(_DWORD *)&v9[v21 + 8] = *(_DWORD *)&Buffer[8];
          }
          if ( !FindNextFileW(FirstFileW, &FindFileData) )
          {
            if ( (g_dwDebugFlags & 3) != 0 )
              PuDbgPrintW(
                g_pDebug,
                "inetsrv\\iis\\mb\\metadata\\listener.cpp",
                1551,
                "CFileListener::GetHistoryFile",
                L"[CFileListener::ProcessChanges] History file found %s.\n",
                v9);
            v22 = wcsstr(v9, L"\\\\?\\");
            if ( v22 && v9 == v22 )
              v23 = v22 + 4;
            else
              v23 = v9;
            v13 = STRU::Copy(v35, v23);
            if ( v13 >= 0 )
            {
              v13 = 0;
              *v36 = v14;
              *v37 = v19;
            }
            break;
          }
        }
        FindClose(FirstFileW);
      }
    }
  }
  else
  {
    v13 = -2147024809;
  }
  if ( v9 )
    operator delete(v9);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x18000aff8  push    rbp
0x18000affa  push    rbx
0x18000affb  push    rsi
0x18000affc  push    rdi
0x18000affd  push    r12
0x18000afff  push    r13
0x18000b001  push    r14
0x18000b003  push    r15
0x18000b005  lea     rbp, [rsp-1F8h]
0x18000b00d  sub     rsp, 2F8h
0x18000b014  mov     rax, cs:__security_cookie
0x18000b01b  xor     rax, rsp
0x18000b01e  mov     [rbp+230h+var_48], rax
0x18000b025  mov     r14, [rbp+230h+arg_20]
0x18000b02c  mov     rbx, r8
0x18000b02f  xor     r13d, r13d
0x18000b032  mov     [rsp+330h+var_2C8], rdx
0x18000b037  xorps   xmm0, xmm0
0x18000b03a  mov     [rsp+330h+var_2B8], r9
0x18000b03f  mov     r12, rdx
0x18000b042  mov     [rsp+330h+var_2C0], rbx
0x18000b047  mov     rsi, rcx
0x18000b04a  mov     [rsp+330h+var_2E0], r13d
0x18000b04f  xor     eax, eax
0x18000b051  mov     [rsp+330h+lpFileName], r13
0x18000b056  movups  xmmword ptr [rbp+230h+Buffer], xmm0
0x18000b05d  xor     edx, edx; Val
0x18000b05f  mov     qword ptr [rbp+230h+Buffer+0Eh], rax
0x18000b066  mov     r8d, 250h; Size
0x18000b06c  lea     rcx, [rbp+230h+FindFileData]; void *
0x18000b070  mov     r15, r9
0x18000b073  mov     edi, r13d
0x18000b076  call    memset_0
0x18000b07b  mov     [rsp+330h+var_2D8], r13d
0x18000b080  mov     [rsp+330h+var_2DC], r13d
0x18000b085  test    r12, r12
0x18000b088  jz      loc_18000B361
0x18000b08e  test    rbx, rbx
0x18000b091  jz      loc_18000B361
0x18000b097  test    r15, r15
0x18000b09a  jz      loc_18000B361
0x18000b0a0  test    r14, r14
0x18000b0a3  jz      loc_18000B361
0x18000b0a9  mov     rdx, [rsi+0D8h]; unsigned __int16 *
0x18000b0b0  lea     r8, [rsp+330h+var_2E0]; unsigned int *
0x18000b0b5  mov     r9, r14; int *
0x18000b0b8  call    ?GetVersionNumber@CFileListener@@AEAAJPEAGPEAKPEAH@Z; CFileListener::GetVersionNumber(ushort *,ulong *,int *)
0x18000b0bd  mov     ebx, eax
0x18000b0bf  test    eax, eax
0x18000b0c1  jns     short loc_18000B0EB
0x18000b0c3  mov     rcx, [rsi+230h]; struct ICatalogErrorLogger2 *
0x18000b0ca  lea     r8d, [r13+1]; unsigned int
0x18000b0ce  mov     [rsp+330h+var_300], r13; unsigned __int16 *
0x18000b0d3  mov     edx, 0C002C819h; unsigned int
0x18000b0d8  mov     [rsp+330h+var_308], r13; unsigned __int16 *
0x18000b0dd  mov     dword ptr [rsp+330h+var_310], eax; char
0x18000b0e1  call    ?LogEvent@@YAJPEAUICatalogErrorLogger2@@KKKKPEAG1111@Z; LogEvent(ICatalogErrorLogger2 *,ulong,ulong,ulong,ulong,ushort *,ushort *,ushort *,ushort *,ushort *)
0x18000b0e6  jmp     loc_18000B373
0x18000b0eb  mov     eax, [rsi+60h]
0x18000b0ee  lea     rdx, [rsp+330h+var_2D8]; unsigned int *
0x18000b0f3  mov     r13d, [rsp+330h+var_2E0]
0x18000b0f8  lea     rcx, [rsp+330h+lpFileName]; unsigned __int16 **
0x18000b0fd  mov     r9d, [rsi+0D0h]; unsigned int
0x18000b104  mov     r8, [rsi+0C8h]; unsigned __int16 *
0x18000b10b  mov     dword ptr [rsp+330h+var_300], r13d; unsigned int
0x18000b110  mov     dword ptr [rsp+330h+var_308], eax; unsigned int
0x18000b114  call    ?ConstructHistoryFileNameWithoutMinorVersion@@YAJPEAPEAGPEAKPEAGK2KK@Z; ConstructHistoryFileNameWithoutMinorVersion(ushort * *,ulong *,ushort *,ulong,ushort *,ulong,ulong)
0x18000b119  mov     rdi, [rsp+330h+lpFileName]
0x18000b11e  mov     ebx, eax
0x18000b120  test    eax, eax
0x18000b122  js      loc_18000B366
0x18000b128  test    byte ptr cs:g_dwDebugFlags, 3
0x18000b12f  jz      short loc_18000B163
0x18000b131  mov     rcx, cs:g_pDebug
0x18000b138  lea     rax, aCfilelistenerP_9; "[CFileListener::ProcessChanges] Searchi"...
0x18000b13f  mov     [rsp+330h+var_308], rdi
0x18000b144  lea     r9, aCfilelistenerG_4; "CFileListener::GetHistoryFile"
0x18000b14b  mov     r8d, 5CAh
0x18000b151  mov     qword ptr [rsp+330h+var_310], rax
0x18000b156  lea     rdx, aInetsrvIisMbMe_5; "inetsrv\\iis\\mb\\metadata\\listener.cp"...
0x18000b15d  call    cs:__imp_PuDbgPrintW
0x18000b163  lea     rdx, [rbp+230h+FindFileData]; lpFindFileData
0x18000b167  mov     rcx, rdi; lpFileName
0x18000b16a  call    cs:__imp_FindFirstFileW
0x18000b170  mov     r15, rax
0x18000b173  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000b177  jnz     loc_18000B206
0x18000b17d  call    cs:__imp_GetLastError
0x18000b183  mov     ebx, eax
0x18000b185  test    eax, eax
0x18000b187  jle     short loc_18000B192
0x18000b189  movzx   ebx, ax
0x18000b18c  or      ebx, 80070000h
0x18000b192  mov     rcx, [rsi+230h]; struct ICatalogErrorLogger2 *
0x18000b199  mov     edx, 0C002C812h; unsigned int
0x18000b19e  mov     [rsp+330h+var_300], 0; unsigned __int16 *
0x18000b1a7  mov     r8d, 1; unsigned int
0x18000b1ad  mov     [rsp+330h+var_308], rdi; unsigned __int16 *
0x18000b1b2  mov     dword ptr [rsp+330h+var_310], ebx; char
0x18000b1b6  call    ?LogEvent@@YAJPEAUICatalogErrorLogger2@@KKKKPEAG1111@Z; LogEvent(ICatalogErrorLogger2 *,ulong,ulong,ulong,ulong,ushort *,ushort *,ushort *,ushort *,ushort *)
0x18000b1bb  test    byte ptr cs:g_dwDebugFlags, 3
0x18000b1c2  jz      short loc_18000B1FA
0x18000b1c4  mov     rcx, cs:g_pDebug
0x18000b1cb  lea     rax, aCfilelistenerP_1; "[CFileListener::ProcessChanges] No hist"...
0x18000b1d2  mov     dword ptr [rsp+330h+var_300], ebx
0x18000b1d6  lea     r9, aCfilelistenerG_4; "CFileListener::GetHistoryFile"
0x18000b1dd  mov     [rsp+330h+var_308], rdi
0x18000b1e2  lea     rdx, aInetsrvIisMbMe_5; "inetsrv\\iis\\mb\\metadata\\listener.cp"...
0x18000b1e9  mov     r8d, 5E2h
0x18000b1ef  mov     qword ptr [rsp+330h+var_310], rax
0x18000b1f4  call    cs:__imp_PuDbgPrintW
0x18000b1fa  mov     dword ptr [r14], 1
0x18000b201  jmp     loc_18000B366
0x18000b206  xor     r14d, r14d
0x18000b209  mov     edx, [rsi+50h]; unsigned int
0x18000b20c  lea     r8, [rsp+330h+var_2DC]; unsigned int *
0x18000b211  xor     r9d, r9d; unsigned int *
0x18000b214  lea     rcx, [rbp+230h+FindFileData.cFileName]; unsigned __int16 *
0x18000b218  call    ?ParseVersionNumber@@YAJPEAGKPEAK1@Z; ParseVersionNumber(ushort *,ulong,ulong *,ulong *)
0x18000b21d  mov     ebx, eax
0x18000b21f  test    eax, eax
0x18000b221  js      loc_18000B356
0x18000b227  mov     ebx, [rsp+330h+var_2DC]
0x18000b22b  cmp     ebx, r14d
0x18000b22e  jb      short loc_18000B280
0x18000b230  mov     r12d, [rsp+330h+var_2D8]
0x18000b235  lea     r9, a010lu; "%010lu"
0x18000b23c  xor     eax, eax
0x18000b23e  mov     dword ptr [rsp+330h+var_310], ebx
0x18000b242  lea     rcx, [rbp+230h+Buffer]; Buffer
0x18000b249  mov     [rdi+r12*2], ax
0x18000b24e  mov     eax, 0Bh
0x18000b253  mov     r8d, eax; MaxCount
0x18000b256  mov     edx, eax; BufferCount
0x18000b258  call    cs:__imp__snwprintf_s
0x18000b25e  test    eax, eax
0x18000b260  js      loc_18000B2F0
0x18000b266  movups  xmm0, xmmword ptr [rbp+230h+Buffer]
0x18000b26d  mov     r14d, ebx
0x18000b270  movups  xmmword ptr [rdi+r12*2], xmm0
0x18000b275  mov     eax, [rbp+230h+var_50]
0x18000b27b  mov     [rdi+r12*2+10h], eax
0x18000b280  lea     rdx, [rbp+230h+FindFileData]; lpFindFileData
0x18000b284  mov     rcx, r15; hFindFile
0x18000b287  call    cs:__imp_FindNextFileW
0x18000b28d  test    eax, eax
0x18000b28f  jnz     loc_18000B209
0x18000b295  test    byte ptr cs:g_dwDebugFlags, 3
0x18000b29c  jz      short loc_18000B2D0
0x18000b29e  mov     rcx, cs:g_pDebug
0x18000b2a5  lea     rax, aCfilelistenerP_10; "[CFileListener::ProcessChanges] History"...
0x18000b2ac  mov     [rsp+330h+var_308], rdi
0x18000b2b1  lea     r9, aCfilelistenerG_4; "CFileListener::GetHistoryFile"
0x18000b2b8  mov     r8d, 60Fh
0x18000b2be  mov     qword ptr [rsp+330h+var_310], rax
0x18000b2c3  lea     rdx, aInetsrvIisMbMe_5; "inetsrv\\iis\\mb\\metadata\\listener.cp"...
0x18000b2ca  call    cs:__imp_PuDbgPrintW
0x18000b2d0  lea     rdx, SubStr; "\\\\?\\"
0x18000b2d7  mov     rcx, rdi; Str
0x18000b2da  call    cs:__imp_wcsstr
0x18000b2e0  test    rax, rax
0x18000b2e3  jz      short loc_18000B32D
0x18000b2e5  cmp     rdi, rax
0x18000b2e8  jnz     short loc_18000B32D
0x18000b2ea  add     rax, 8
0x18000b2ee  jmp     short loc_18000B330
0x18000b2f0  test    byte ptr cs:g_dwDebugFlags, 3
0x18000b2f7  jz      short loc_18000B326
0x18000b2f9  mov     rcx, cs:g_pDebug
0x18000b300  lea     rax, aProcesschanges; "[ProcessChanges] _snwprintf returned a "...
0x18000b307  lea     r9, aCfilelistenerG_4; "CFileListener::GetHistoryFile"
0x18000b30e  mov     qword ptr [rsp+330h+var_310], rax
0x18000b313  mov     r8d, 601h
0x18000b319  lea     rdx, aInetsrvIisMbMe_5; "inetsrv\\iis\\mb\\metadata\\listener.cp"...
0x18000b320  call    cs:__imp_PuDbgPrintW
0x18000b326  mov     ebx, 8007000Dh
0x18000b32b  jmp     short loc_18000B356
0x18000b32d  mov     rax, rdi
0x18000b330  mov     rcx, [rsp+330h+var_2C8]
0x18000b335  mov     rdx, rax
0x18000b338  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18000b33e  mov     ebx, eax
0x18000b340  test    eax, eax
0x18000b342  js      short loc_18000B356
0x18000b344  mov     rax, [rsp+330h+var_2C0]
0x18000b349  xor     ebx, ebx
0x18000b34b  mov     [rax], r13d
0x18000b34e  mov     rax, [rsp+330h+var_2B8]
0x18000b353  mov     [rax], r14d
0x18000b356  mov     rcx, r15; hFindFile
0x18000b359  call    cs:__imp_FindClose
0x18000b35f  jmp     short loc_18000B366
0x18000b361  mov     ebx, 80070057h
0x18000b366  test    rdi, rdi
0x18000b369  jz      short loc_18000B373
0x18000b36b  mov     rcx, rdi; Block
0x18000b36e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000b373  mov     eax, ebx
0x18000b375  mov     rcx, [rbp+230h+var_48]
0x18000b37c  xor     rcx, rsp; StackCookie
0x18000b37f  call    __security_check_cookie
0x18000b384  add     rsp, 2F8h
0x18000b38b  pop     r15
0x18000b38d  pop     r14
0x18000b38f  pop     r13
0x18000b391  pop     r12
0x18000b393  pop     rdi
0x18000b394  pop     rsi
0x18000b395  pop     rbx
0x18000b396  pop     rbp
0x18000b397  retn
```
