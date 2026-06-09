# CFileListener::CopyErrorFile(long)

- ea: `0x18000a638`
- end: `0x18000ab66`
- name: `?CopyErrorFile@CFileListener@@AEAAJJ@Z`
- size: `1326`
- prototype: `__int64 __fastcall(CFileListener *__hidden this, int)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18000d374`
- `0x18000e104`

## callees

- `0x180008a08`
- `0x18000a638`
- `0x18001c508`
- `0x18002056c`
- `0x180021270`
- `0x18003099a`
- `0x1800309d0`

## import_xrefs

- `msvcrt!_snwprintf_s` at `0x18000a87a`
- `msvcrt!_snwprintf_s` at `0x18000aa19`
- `msvcrt!_snwprintf_s` at `0x18000a87a`
- `msvcrt!_snwprintf_s` at `0x18000aa19`
- `msvcrt!qsort` at `0x18000a9d5`
- `msvcrt!qsort` at `0x18000a9d5`
- `msvcrt!swscanf` at `0x18000a76e`
- `msvcrt!swscanf` at `0x18000a76e`
- `KERNEL32!FindClose` at `0x18000a837`
- `KERNEL32!FindClose` at `0x18000aa94`
- `KERNEL32!FindClose` at `0x18000a837`
- `KERNEL32!FindClose` at `0x18000aa94`
- `KERNEL32!FindNextFileW` at `0x18000a824`
- `KERNEL32!FindNextFileW` at `0x18000a824`
- `KERNEL32!FindFirstFileW` at `0x18000a6e8`
- `KERNEL32!FindFirstFileW` at `0x18000a6e8`
- `KERNEL32!DeleteFileW` at `0x18000aaee`
- `KERNEL32!DeleteFileW` at `0x18000aaee`
- `KERNEL32!GetLastError` at `0x18000a6f9`
- `KERNEL32!GetLastError` at `0x18000aaf8`
- `KERNEL32!GetLastError` at `0x18000a6f9`
- `KERNEL32!GetLastError` at `0x18000aaf8`
- `IisRTL!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000a9a3`
- `IisRTL!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000a9a3`
- `IisRTL!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000a98f`
- `IisRTL!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000a98f`
- `IisRTL!PuDbgPrintW` at `0x18000a746`
- `IisRTL!PuDbgPrintW` at `0x18000a815`
- `IisRTL!PuDbgPrintW` at `0x18000a8b8`
- `IisRTL!PuDbgPrintW` at `0x18000a92e`
- `IisRTL!PuDbgPrintW` at `0x18000aa57`
- `IisRTL!PuDbgPrintW` at `0x18000ab4a`
- `IisRTL!PuDbgPrintW` at `0x18000a746`
- `IisRTL!PuDbgPrintW` at `0x18000a815`
- `IisRTL!PuDbgPrintW` at `0x18000a8b8`
- `IisRTL!PuDbgPrintW` at `0x18000a92e`
- `IisRTL!PuDbgPrintW` at `0x18000aa57`
- `IisRTL!PuDbgPrintW` at `0x18000ab4a`

## string_xrefs

- `0x18000a722`: `[CFileListener::CopyErrorFile] No error files found. hr=0x%x.\n`
- `0x18000a72d`: `CFileListener::CopyErrorFile`
- `0x18000a7f5`: `CFileListener::CopyErrorFile`
- `0x18000a89d`: `CFileListener::CopyErrorFile`
- `0x18000a90a`: `CFileListener::CopyErrorFile`
- `0x18000aa3e`: `CFileListener::CopyErrorFile`
- `0x18000ab1a`: `CFileListener::CopyErrorFile`
- `0x18000a7fc`: `[CFileListener::CopyErrorFile] Could not fetch error version number from %s - swscanf failed.\n`
- `0x18000a880`: `[CopyErrorFile] _snwprintf returned a negative value. This should never happen.\n`
- `0x18000aa37`: `[CopyErrorFile] _snwprintf returned a negative value. This should never happen.\n`
- `0x18000a91c`: `[CFileListener::CopyErrorFile] CopyFile failed with. hr=0x%x.\n`
- `0x18000ab3e`: `[CopyErrorFile] Unable to cleanup error file: %s. DeleteFileW failed with hr = 0x%x.\n`

## pseudocode

```c
__int64 __fastcall CFileListener::CopyErrorFile(CFileListener *this, int a2)
{
  _BYTE *v3; // rdi
  unsigned int v4; // eax
  __int64 v5; // rcx
  unsigned int v6; // esi
  unsigned int v7; // r13d
  __int64 v8; // rax
  unsigned int v9; // r12d
  signed int LastError; // eax
  unsigned int v11; // ebx
  int v12; // eax
  __int64 v13; // rdx
  __int64 v14; // r12
  __int64 v15; // rcx
  int v16; // eax
  unsigned int v17; // r9d
  unsigned int v18; // r12d
  unsigned int v19; // r13d
  unsigned int v20; // r12d
  unsigned int v21; // r13d
  unsigned int v22; // eax
  __int64 v24; // rcx
  __int64 v25; // rdx
  signed int v26; // eax
  char v27[8]; // [rsp+20h] [rbp-E0h]
  char v28[8]; // [rsp+20h] [rbp-E0h]
  unsigned __int16 *v29; // [rsp+28h] [rbp-D8h]
  unsigned __int16 *v30; // [rsp+30h] [rbp-D0h]
  unsigned __int16 *v31; // [rsp+38h] [rbp-C8h]
  unsigned __int16 *v32; // [rsp+40h] [rbp-C0h]
  unsigned __int16 *v33; // [rsp+48h] [rbp-B8h]
  unsigned int v34; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v35; // [rsp+54h] [rbp-ACh] BYREF
  unsigned int NumOfElements; // [rsp+58h] [rbp-A8h]
  unsigned int NumOfElements_4; // [rsp+5Ch] [rbp-A4h]
  HANDLE hFindFile; // [rsp+60h] [rbp-A0h]
  int v39; // [rsp+68h] [rbp-98h] BYREF
  char v40[4]; // [rsp+6Ch] [rbp-94h]
  void *Block; // [rsp+70h] [rbp-90h] BYREF
  _WIN32_FIND_DATAW FindFileData; // [rsp+80h] [rbp-80h] BYREF
  _BYTE Base[320]; // [rsp+2D0h] [rbp+1D0h] BYREF
  wchar_t Buffer[8]; // [rsp+410h] [rbp+310h] BYREF
  int v45; // [rsp+420h] [rbp+320h]

  *(_DWORD *)v40 = a2;
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  v3 = Base;
  v4 = *((_DWORD *)this + 44) - *((_DWORD *)this + 24) - 11;
  Block = Base;
  v5 = v4;
  v6 = 0;
  v35 = 0;
  v7 = 0;
  NumOfElements_4 = v4;
  v8 = *((_QWORD *)this + 21);
  v9 = 20;
  v39 = 0;
  v34 = 20;
  NumOfElements = 0;
  *(_OWORD *)(v8 + 2 * v5) = *(_OWORD *)L"_??????????";
  *(_QWORD *)(v8 + 2 * v5 + 14) = *(_QWORD *)L"????";
  hFindFile = FindFirstFileW(*((LPCWSTR *)this + 21), &FindFileData);
  if ( hFindFile == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    v11 = LastError;
    if ( LastError > 0 )
      v11 = (unsigned __int16)LastError | 0x80070000;
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrintW(
        g_pDebug,
        "inetsrv\\iis\\mb\\metadata\\listener.cpp",
        2807,
        "CFileListener::CopyErrorFile",
        L"[CFileListener::CopyErrorFile] No error files found. hr=0x%x.\n",
        v11);
  }
  else
  {
    v11 = 0;
    do
    {
      if ( (unsigned int)(swscanf(&FindFileData.cFileName[*((_DWORD *)this + 20) + 5], L"_%lu", &v35) + 1) <= 1 )
      {
        if ( (g_dwDebugFlags & 3) != 0 )
          PuDbgPrintW(
            g_pDebug,
            "inetsrv\\iis\\mb\\metadata\\listener.cpp",
            2827,
            "CFileListener::CopyErrorFile",
            L"[CFileListener::CopyErrorFile] Could not fetch error version number from %s - swscanf failed.\n",
            FindFileData.cFileName);
      }
      else
      {
        if ( v35 >= v6 )
          v6 = v35;
        if ( v7 >= v9 )
        {
          v12 = ReAllocateFileData(v7, (struct _METABASE_FILE_DATA **)&Block, &v34, &v39);
          v3 = Block;
          v11 = v12;
          if ( v12 < 0 )
            goto LABEL_37;
          v9 = v34;
        }
        v13 = 2LL * v7++;
        NumOfElements = v7;
        *(_DWORD *)&v3[8 * v13] = 0;
        *(_DWORD *)&v3[8 * v13 + 4] = v35;
        *(FILETIME *)&v3[8 * v13 + 8] = FindFileData.ftLastWriteTime;
      }
    }
    while ( FindNextFileW(hFindFile, &FindFileData) );
    FindClose(hFindFile);
    hFindFile = (HANDLE)-1LL;
    if ( v6 == -1 )
      v6 = 0;
    else
      ++v6;
  }
  *(_DWORD *)v27 = v6;
  v14 = ++NumOfElements_4;
  if ( _snwprintf_s(Buffer, 0xBu, 0xBu, L"%010lu", *(_QWORD *)v27) >= 0 )
  {
    v15 = *((_QWORD *)this + 21);
    *(_OWORD *)(v15 + 2 * v14) = *(_OWORD *)Buffer;
    *(_DWORD *)(v15 + 2 * v14 + 16) = v45;
    v16 = CopyFileWithSecurityDescriptor(*((unsigned __int16 **)this + 27), *((unsigned __int16 **)this + 21));
    v11 = v16;
    if ( v16 >= 0 )
    {
      LogEvent(
        *((struct ICatalogErrorLogger2 **)this + 70),
        0xC002C813,
        1u,
        v17,
        v40[0],
        *((unsigned __int16 **)this + 21),
        0,
        v31,
        v32,
        v33);
    }
    else
    {
      if ( (g_dwDebugFlags & 3) != 0 )
      {
        LODWORD(v29) = v16;
        PuDbgPrintW(
          g_pDebug,
          "inetsrv\\iis\\mb\\metadata\\listener.cpp",
          2907,
          "CFileListener::CopyErrorFile",
          L"[CFileListener::CopyErrorFile] CopyFile failed with. hr=0x%x.\n",
          v29);
      }
      LogEvent(
        *((struct ICatalogErrorLogger2 **)this + 70),
        0xC002C81B,
        1u,
        v17,
        v11,
        *((unsigned __int16 **)this + 21),
        0,
        v31,
        v32,
        v33);
    }
  }
  else if ( (g_dwDebugFlags & 3) != 0 )
  {
    PuDbgPrintW(
      g_pDebug,
      "inetsrv\\iis\\mb\\metadata\\listener.cpp",
      2891,
      "CFileListener::CopyErrorFile",
      L"[CopyErrorFile] _snwprintf returned a negative value. This should never happen.\n");
  }
  CReaderWriterLock3::ReadLock((CReaderWriterLock3 *)&g_LockMasterResource);
  v18 = g_dwMaxErrorFiles;
  CReaderWriterLock3::ReadUnlock((CReaderWriterLock3 *)&g_LockMasterResource);
  if ( v7 + 1 > v18 )
  {
    v34 = 0;
    v19 = v7 - v18;
    qsort(v3, NumOfElements, 0x10u, MyCompareFileData);
    v20 = 0;
    v21 = v19 + 1;
    if ( v21 )
    {
      do
      {
        if ( v20 >= NumOfElements )
          break;
        if ( *(_DWORD *)&v3[16 * v20 + 4] != v6 )
        {
          *(_DWORD *)v28 = *(_DWORD *)&v3[16 * v20 + 4];
          if ( _snwprintf_s(Buffer, 0xBu, 0xBu, L"%010lu", *(_QWORD *)v28) >= 0 )
          {
            v24 = *((_QWORD *)this + 21);
            v25 = NumOfElements_4;
            *(_OWORD *)(v24 + 2LL * NumOfElements_4) = *(_OWORD *)Buffer;
            *(_DWORD *)(v24 + 2 * v25 + 16) = v45;
            if ( DeleteFileW(*((LPCWSTR *)this + 21)) )
            {
              v22 = ++v34;
              goto LABEL_36;
            }
            v26 = GetLastError();
            if ( v26 > 0 )
              v26 = (unsigned __int16)v26 | 0x80070000;
            if ( (g_dwDebugFlags & 3) != 0 )
            {
              LODWORD(v30) = v26;
              PuDbgPrintW(
                g_pDebug,
                "inetsrv\\iis\\mb\\metadata\\listener.cpp",
                2990,
                "CFileListener::CopyErrorFile",
                L"[CopyErrorFile] Unable to cleanup error file: %s. DeleteFileW failed with hr = 0x%x.\n",
                *((_QWORD *)this + 21),
                v30);
            }
            v11 = 0;
          }
          else if ( (g_dwDebugFlags & 3) != 0 )
          {
            PuDbgPrintW(
              g_pDebug,
              "inetsrv\\iis\\mb\\metadata\\listener.cpp",
              2976,
              "CFileListener::CopyErrorFile",
              L"[CopyErrorFile] _snwprintf returned a negative value. This should never happen.\n");
          }
        }
        v22 = v34;
LABEL_36:
        ++v20;
      }
      while ( v22 < v21 );
    }
  }
LABEL_37:
  if ( Base != v3 && v3 )
    operator delete(v3);
  if ( hFindFile != (HANDLE)-1LL )
    FindClose(hFindFile);
  return v11;
}

```

## disassembly

```asm
0x18000a638  mov     [rsp-8+arg_8], rbx
0x18000a63d  mov     [rsp-8+arg_10], rsi
0x18000a642  push    rbp
0x18000a643  push    rdi
0x18000a644  push    r12
0x18000a646  push    r13
0x18000a648  push    r14
0x18000a64a  lea     rbp, [rsp-330h]
0x18000a652  sub     rsp, 430h
0x18000a659  mov     rax, cs:__security_cookie
0x18000a660  xor     rax, rsp
0x18000a663  mov     [rbp+350h+var_28], rax
0x18000a66a  mov     dword ptr [rsp+450h+var_3E4], edx
0x18000a66e  mov     r14, rcx
0x18000a671  xor     edx, edx; Val
0x18000a673  lea     rcx, [rbp+350h+FindFileData]; void *
0x18000a677  mov     r8d, 250h; Size
0x18000a67d  call    memset_0
0x18000a682  mov     eax, [r14+0B0h]
0x18000a689  lea     rdi, [rbp+350h+Base]
0x18000a690  sub     eax, [r14+60h]
0x18000a694  lea     rdx, [rbp+350h+FindFileData]; lpFindFileData
0x18000a698  movups  xmm0, xmmword ptr cs:asc_180035180; "_??????????"
0x18000a69f  add     eax, 0FFFFFFF5h
0x18000a6a2  mov     [rsp+450h+Block], rdi
0x18000a6a7  mov     ecx, eax
0x18000a6a9  xor     esi, esi
0x18000a6ab  mov     [rsp+450h+var_3FC], esi
0x18000a6af  xor     r13d, r13d
0x18000a6b2  mov     dword ptr [rsp+450h+NumOfElements+4], eax
0x18000a6b6  mov     rax, [r14+0A8h]
0x18000a6bd  lea     r12d, [rsi+14h]
0x18000a6c1  mov     [rsp+450h+var_3E8], esi
0x18000a6c5  mov     [rsp+450h+var_400], r12d
0x18000a6ca  mov     dword ptr [rsp+450h+NumOfElements], r13d
0x18000a6cf  movups  xmmword ptr [rax+rcx*2], xmm0
0x18000a6d3  movsd   xmm1, qword ptr cs:asc_180035180+0Eh; "????"
0x18000a6db  movsd   qword ptr [rax+rcx*2+0Eh], xmm1
0x18000a6e1  mov     rcx, [r14+0A8h]; lpFileName
0x18000a6e8  call    cs:__imp_FindFirstFileW
0x18000a6ee  mov     [rsp+450h+hFindFile], rax
0x18000a6f3  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000a6f7  jnz     short loc_18000A751
0x18000a6f9  call    cs:__imp_GetLastError
0x18000a6ff  mov     ebx, eax
0x18000a701  test    eax, eax
0x18000a703  jle     short loc_18000A70E
0x18000a705  movzx   ebx, ax
0x18000a708  or      ebx, 80070000h
0x18000a70e  test    byte ptr cs:g_dwDebugFlags, 3
0x18000a715  jz      loc_18000A851
0x18000a71b  mov     rcx, cs:g_pDebug
0x18000a722  lea     rax, aCfilelistenerC_0; "[CFileListener::CopyErrorFile] No error"...
0x18000a729  mov     dword ptr [rsp+450h+var_428], ebx
0x18000a72d  lea     r9, aCfilelistenerC_1; "CFileListener::CopyErrorFile"
0x18000a734  mov     r8d, 0AF7h
0x18000a73a  mov     qword ptr [rsp+450h+var_430], rax
0x18000a73f  lea     rdx, aInetsrvIisMbMe_5; "inetsrv\\iis\\mb\\metadata\\listener.cp"...
0x18000a746  call    cs:__imp_PuDbgPrintW
0x18000a74c  jmp     loc_18000A851
0x18000a751  xor     ebx, ebx
0x18000a753  mov     eax, [r14+50h]
0x18000a757  lea     rcx, [rbp+350h+FindFileData.cFileName]
0x18000a75b  add     eax, 5
0x18000a75e  lea     r8, [rsp+450h+var_3FC]
0x18000a763  lea     rdx, aLu; "_%lu"
0x18000a76a  lea     rcx, [rcx+rax*2]; Buffer
0x18000a76e  call    cs:__imp_swscanf
0x18000a774  inc     eax
0x18000a776  cmp     eax, 1
0x18000a779  jbe     short loc_18000A7DC
0x18000a77b  cmp     [rsp+450h+var_3FC], esi
0x18000a77f  cmovnb  esi, [rsp+450h+var_3FC]
0x18000a784  cmp     r13d, r12d
0x18000a787  jb      short loc_18000A7B4
0x18000a789  lea     r9, [rsp+450h+var_3E8]; int *
0x18000a78e  mov     ecx, r13d; unsigned int
0x18000a791  lea     r8, [rsp+450h+var_400]; unsigned int *
0x18000a796  lea     rdx, [rsp+450h+Block]; struct _METABASE_FILE_DATA **
0x18000a79b  call    ?ReAllocateFileData@@YAJKPEAPEAU_METABASE_FILE_DATA@@PEAKPEAH@Z; ReAllocateFileData(ulong,_METABASE_FILE_DATA * *,ulong *,int *)
0x18000a7a0  mov     rdi, [rsp+450h+Block]
0x18000a7a5  mov     ebx, eax
0x18000a7a7  test    eax, eax
0x18000a7a9  js      loc_18000AA6D
0x18000a7af  mov     r12d, [rsp+450h+var_400]
0x18000a7b4  mov     edx, r13d
0x18000a7b7  add     rdx, rdx
0x18000a7ba  inc     r13d
0x18000a7bd  mov     dword ptr [rsp+450h+NumOfElements], r13d
0x18000a7c2  mov     dword ptr [rdi+rdx*8], 0
0x18000a7c9  mov     ecx, [rsp+450h+var_3FC]
0x18000a7cd  mov     [rdi+rdx*8+4], ecx
0x18000a7d1  mov     rcx, qword ptr [rbp+350h+FindFileData.ftLastWriteTime.dwLowDateTime]
0x18000a7d5  mov     [rdi+rdx*8+8], rcx
0x18000a7da  jmp     short loc_18000A81B
0x18000a7dc  test    byte ptr cs:g_dwDebugFlags, 3
0x18000a7e3  jz      short loc_18000A81B
0x18000a7e5  mov     rcx, cs:g_pDebug
0x18000a7ec  lea     rax, [rbp+350h+FindFileData.cFileName]
0x18000a7f0  mov     [rsp+450h+var_428], rax
0x18000a7f5  lea     r9, aCfilelistenerC_1; "CFileListener::CopyErrorFile"
0x18000a7fc  lea     rax, aCfilelistenerC_2; "[CFileListener::CopyErrorFile] Could no"...
0x18000a803  mov     r8d, 0B0Bh
0x18000a809  lea     rdx, aInetsrvIisMbMe_5; "inetsrv\\iis\\mb\\metadata\\listener.cp"...
0x18000a810  mov     qword ptr [rsp+450h+var_430], rax
0x18000a815  call    cs:__imp_PuDbgPrintW
0x18000a81b  mov     rcx, [rsp+450h+hFindFile]; hFindFile
0x18000a820  lea     rdx, [rbp+350h+FindFileData]; lpFindFileData
0x18000a824  call    cs:__imp_FindNextFileW
0x18000a82a  test    eax, eax
0x18000a82c  jnz     loc_18000A753
0x18000a832  mov     rcx, [rsp+450h+hFindFile]; hFindFile
0x18000a837  call    cs:__imp_FindClose
0x18000a83d  mov     [rsp+450h+hFindFile], 0FFFFFFFFFFFFFFFFh
0x18000a846  cmp     esi, 0FFFFFFFFh
0x18000a849  jnz     short loc_18000A84F
0x18000a84b  xor     esi, esi
0x18000a84d  jmp     short loc_18000A851
0x18000a84f  inc     esi
0x18000a851  mov     r12d, dword ptr [rsp+450h+NumOfElements+4]
0x18000a856  lea     r9, a010lu; "%010lu"
0x18000a85d  mov     eax, 0Bh
0x18000a862  mov     dword ptr [rsp+450h+var_430], esi
0x18000a866  inc     r12d
0x18000a869  lea     rcx, [rbp+350h+Buffer]; Buffer
0x18000a870  mov     r8d, eax; MaxCount
0x18000a873  mov     dword ptr [rsp+450h+NumOfElements+4], r12d
0x18000a878  mov     edx, eax; BufferCount
0x18000a87a  call    cs:__imp__snwprintf_s
0x18000a880  lea     rcx, aCopyerrorfileS; "[CopyErrorFile] _snwprintf returned a n"...
0x18000a887  test    eax, eax
0x18000a889  jns     short loc_18000A8C3
0x18000a88b  test    byte ptr cs:g_dwDebugFlags, 3
0x18000a892  jz      loc_18000A988
0x18000a898  mov     qword ptr [rsp+450h+var_430], rcx
0x18000a89d  lea     r9, aCfilelistenerC_1; "CFileListener::CopyErrorFile"
0x18000a8a4  mov     rcx, cs:g_pDebug
0x18000a8ab  lea     rdx, aInetsrvIisMbMe_5; "inetsrv\\iis\\mb\\metadata\\listener.cp"...
0x18000a8b2  mov     r8d, 0B4Bh
0x18000a8b8  call    cs:__imp_PuDbgPrintW
0x18000a8be  jmp     loc_18000A988
0x18000a8c3  mov     rcx, [r14+0A8h]
0x18000a8ca  movups  xmm0, xmmword ptr [rbp+350h+Buffer]
0x18000a8d1  movups  xmmword ptr [rcx+r12*2], xmm0
0x18000a8d6  mov     eax, [rbp+350h+var_30]
0x18000a8dc  mov     [rcx+r12*2+10h], eax
0x18000a8e1  mov     rdx, [r14+0A8h]; unsigned __int16 *
0x18000a8e8  mov     rcx, [r14+0D8h]; unsigned __int16 *
0x18000a8ef  call    ?CopyFileWithSecurityDescriptor@@YAJPEAG0@Z; CopyFileWithSecurityDescriptor(ushort *,ushort *)
0x18000a8f4  mov     ebx, eax
0x18000a8f6  test    eax, eax
0x18000a8f8  jns     short loc_18000A954
0x18000a8fa  test    byte ptr cs:g_dwDebugFlags, 3
0x18000a901  jz      short loc_18000A934
0x18000a903  mov     rcx, cs:g_pDebug
0x18000a90a  lea     r9, aCfilelistenerC_1; "CFileListener::CopyErrorFile"
0x18000a911  mov     dword ptr [rsp+450h+var_428], eax
0x18000a915  lea     rdx, aInetsrvIisMbMe_5; "inetsrv\\iis\\mb\\metadata\\listener.cp"...
0x18000a91c  lea     rax, aCfilelistenerC; "[CFileListener::CopyErrorFile] CopyFile"...
0x18000a923  mov     r8d, 0B5Bh
0x18000a929  mov     qword ptr [rsp+450h+var_430], rax
0x18000a92e  call    cs:__imp_PuDbgPrintW
0x18000a934  mov     rax, [r14+0A8h]
0x18000a93b  mov     edx, 0C002C81Bh
0x18000a940  mov     [rsp+450h+var_420], 0
0x18000a949  mov     [rsp+450h+var_428], rax
0x18000a94e  mov     dword ptr [rsp+450h+var_430], ebx
0x18000a952  jmp     short loc_18000A976
0x18000a954  mov     rax, [r14+0A8h]
0x18000a95b  mov     edx, 0C002C813h; unsigned int
0x18000a960  mov     [rsp+450h+var_420], 0; unsigned __int16 *
0x18000a969  mov     [rsp+450h+var_428], rax; unsigned __int16 *
0x18000a96e  mov     eax, dword ptr [rsp+450h+var_3E4]
0x18000a972  mov     dword ptr [rsp+450h+var_430], eax; char
0x18000a976  mov     rcx, [r14+230h]; struct ICatalogErrorLogger2 *
0x18000a97d  mov     r8d, 1; unsigned int
0x18000a983  call    ?LogEvent@@YAJPEAUICatalogErrorLogger2@@KKKKPEAG1111@Z; LogEvent(ICatalogErrorLogger2 *,ulong,ulong,ulong,ulong,ushort *,ushort *,ushort *,ushort *,ushort *)
0x18000a988  lea     rcx, ?g_LockMasterResource@@3VCReaderWriterLock3@@A; CReaderWriterLock3 g_LockMasterResource
0x18000a98f  call    cs:__imp_?ReadLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadLock(void)
0x18000a995  mov     r12d, cs:?g_dwMaxErrorFiles@@3KA; ulong g_dwMaxErrorFiles
0x18000a99c  lea     rcx, ?g_LockMasterResource@@3VCReaderWriterLock3@@A; CReaderWriterLock3 g_LockMasterResource
0x18000a9a3  call    cs:__imp_?ReadUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadUnlock(void)
0x18000a9a9  lea     eax, [r13+1]
0x18000a9ad  cmp     eax, r12d
0x18000a9b0  jbe     loc_18000AA6D
0x18000a9b6  mov     edx, dword ptr [rsp+450h+NumOfElements]; NumOfElements
0x18000a9ba  lea     r9, ?MyCompareFileData@@YAHPEBX0@Z; CompareFunction
0x18000a9c1  mov     r8d, 10h; SizeOfElements
0x18000a9c7  mov     [rsp+450h+var_400], 0
0x18000a9cf  mov     rcx, rdi; Base
0x18000a9d2  sub     r13d, r12d
0x18000a9d5  call    cs:__imp_qsort
0x18000a9db  xor     r12d, r12d
0x18000a9de  add     r13d, 1
0x18000a9e2  jz      loc_18000AA6D
0x18000a9e8  cmp     r12d, dword ptr [rsp+450h+NumOfElements]
0x18000a9ed  jnb     short loc_18000AA6D
0x18000a9ef  mov     eax, r12d
0x18000a9f2  add     rax, rax
0x18000a9f5  mov     ecx, [rdi+rax*8+4]
0x18000a9f9  cmp     ecx, esi
0x18000a9fb  jz      short loc_18000AA5D
0x18000a9fd  mov     eax, 0Bh
0x18000aa02  mov     dword ptr [rsp+450h+var_430], ecx
0x18000aa06  mov     r8d, eax; MaxCount
0x18000aa09  lea     r9, a010lu; "%010lu"
0x18000aa10  mov     edx, eax; BufferCount
0x18000aa12  lea     rcx, [rbp+350h+Buffer]; Buffer
0x18000aa19  call    cs:__imp__snwprintf_s
0x18000aa1f  test    eax, eax
0x18000aa21  jns     loc_18000AAC7
0x18000aa27  test    byte ptr cs:g_dwDebugFlags, 3
0x18000aa2e  jz      short loc_18000AA5D
0x18000aa30  mov     rcx, cs:g_pDebug
0x18000aa37  lea     rax, aCopyerrorfileS; "[CopyErrorFile] _snwprintf returned a n"...
0x18000aa3e  lea     r9, aCfilelistenerC_1; "CFileListener::CopyErrorFile"
0x18000aa45  mov     qword ptr [rsp+450h+var_430], rax
0x18000aa4a  mov     r8d, 0BA0h
0x18000aa50  lea     rdx, aInetsrvIisMbMe_5; "inetsrv\\iis\\mb\\metadata\\listener.cp"...
0x18000aa57  call    cs:__imp_PuDbgPrintW
0x18000aa5d  mov     eax, [rsp+450h+var_400]
0x18000aa61  inc     r12d
0x18000aa64  cmp     eax, r13d
0x18000aa67  jb      loc_18000A9E8
0x18000aa6d  lea     rax, [rbp+350h+Base]
0x18000aa74  cmp     rax, rdi
0x18000aa77  jz      short loc_18000AA86
0x18000aa79  test    rdi, rdi
0x18000aa7c  jz      short loc_18000AA86
0x18000aa7e  mov     rcx, rdi; Block
0x18000aa81  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000aa86  mov     rax, [rsp+450h+hFindFile]
0x18000aa8b  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000aa8f  jz      short loc_18000AA9A
0x18000aa91  mov     rcx, rax; hFindFile
0x18000aa94  call    cs:__imp_FindClose
0x18000aa9a  mov     eax, ebx
0x18000aa9c  mov     rcx, [rbp+350h+var_28]
0x18000aaa3  xor     rcx, rsp; StackCookie
0x18000aaa6  call    __security_check_cookie
0x18000aaab  lea     r11, [rsp+450h+var_20]
0x18000aab3  mov     rbx, [r11+38h]
0x18000aab7  mov     rsi, [r11+40h]
0x18000aabb  mov     rsp, r11
0x18000aabe  pop     r14
0x18000aac0  pop     r13
0x18000aac2  pop     r12
0x18000aac4  pop     rdi
0x18000aac5  pop     rbp
0x18000aac6  retn
0x18000aac7  mov     rcx, [r14+0A8h]
0x18000aace  mov     edx, dword ptr [rsp+450h+NumOfElements+4]
0x18000aad2  movups  xmm0, xmmword ptr [rbp+350h+Buffer]
0x18000aad9  movups  xmmword ptr [rcx+rdx*2], xmm0
0x18000aadd  mov     eax, [rbp+350h+var_30]
0x18000aae3  mov     [rcx+rdx*2+10h], eax
0x18000aae7  mov     rcx, [r14+0A8h]; lpFileName
0x18000aaee  call    cs:__imp_DeleteFileW
0x18000aaf4  test    eax, eax
0x18000aaf6  jnz     short loc_18000AB57
0x18000aaf8  call    cs:__imp_GetLastError
0x18000aafe  test    eax, eax
0x18000ab00  jle     short loc_18000AB0A
0x18000ab02  movzx   eax, ax
0x18000ab05  or      eax, 80070000h
0x18000ab0a  test    byte ptr cs:g_dwDebugFlags, 3
0x18000ab11  jz      short loc_18000AB50
0x18000ab13  mov     rcx, cs:g_pDebug
0x18000ab1a  lea     r9, aCfilelistenerC_1; "CFileListener::CopyErrorFile"
0x18000ab21  mov     dword ptr [rsp+450h+var_420], eax
0x18000ab25  lea     rdx, aInetsrvIisMbMe_5; "inetsrv\\iis\\mb\\metadata\\listener.cp"...
0x18000ab2c  mov     rax, [r14+0A8h]
0x18000ab33  mov     r8d, 0BAEh
0x18000ab39  mov     [rsp+450h+var_428], rax
0x18000ab3e  lea     rax, aCopyerrorfileU; "[CopyErrorFile] Unable to cleanup error"...
0x18000ab45  mov     qword ptr [rsp+450h+var_430], rax
0x18000ab4a  call    cs:__imp_PuDbgPrintW
0x18000ab50  xor     ebx, ebx
0x18000ab52  jmp     loc_18000AA5D
0x18000ab57  mov     eax, [rsp+450h+var_400]
0x18000ab5b  inc     eax
0x18000ab5d  mov     [rsp+450h+var_400], eax
0x18000ab61  jmp     loc_18000AA61
```
