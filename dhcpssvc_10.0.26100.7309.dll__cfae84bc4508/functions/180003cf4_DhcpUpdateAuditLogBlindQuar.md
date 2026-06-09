# DhcpUpdateAuditLogBlindQuar

- ea: `0x180003cf4`
- end: `0x1800048b2`
- name: `DhcpUpdateAuditLogBlindQuar`
- size: `3006`
- prototype: `__int64 __fastcall(int, const size_t *, unsigned int, struct _FILETIME, unsigned int, const size_t *, int, int, int, FILETIME FileTime, unsigned __int8 *, unsigned int, __int64, const char *, const CHAR *, unsigned int cbMultiByte, const CHAR *, unsigned int, __int64, unsigned int)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, installer_update`

## callers

- `0x180004a5c`

## callees

- `0x180002854`
- `0x18000323c`
- `0x180003cf4`
- `0x1800050c8`
- `0x1800051f4`
- `0x1800052d4`
- `0x180005408`
- `0x180062964`
- `0x18006308c`
- `0x18008f3f0`
- `0x18008f478`
- `0x18008f540`
- `0x1800c85bc`
- `0x1800cc9e0`

## import_xrefs

- `msvcrt!_wstrtime` at `0x180003e16`
- `msvcrt!_wstrtime` at `0x180003e16`
- `msvcrt!_wstrdate` at `0x180003e06`
- `msvcrt!_wstrdate` at `0x180003e06`
- `KERNEL32!HeapAlloc` at `0x180003ff7`
- `KERNEL32!HeapAlloc` at `0x180003ff7`
- `KERNEL32!FileTimeToSystemTime` at `0x180004308`
- `KERNEL32!FileTimeToSystemTime` at `0x180004308`
- `KERNEL32!FileTimeToLocalFileTime` at `0x1800042e5`
- `KERNEL32!FileTimeToLocalFileTime` at `0x1800042e5`
- `KERNEL32!WriteFile` at `0x18000477d`
- `KERNEL32!WriteFile` at `0x18000477d`
- `KERNEL32!GetLastError` at `0x18000478d`
- `KERNEL32!GetLastError` at `0x18000478d`
- `KERNEL32!HeapFree` at `0x18000442a`
- `KERNEL32!HeapFree` at `0x180004447`
- `KERNEL32!HeapFree` at `0x180004464`
- `KERNEL32!HeapFree` at `0x180004481`
- `KERNEL32!HeapFree` at `0x1800047d8`
- `KERNEL32!HeapFree` at `0x1800047fc`
- `KERNEL32!HeapFree` at `0x180004814`
- `KERNEL32!HeapFree` at `0x18000482d`
- `KERNEL32!HeapFree` at `0x18000484a`
- `KERNEL32!HeapFree` at `0x180004878`
- `KERNEL32!HeapFree` at `0x18000442a`
- `KERNEL32!HeapFree` at `0x180004447`
- `KERNEL32!HeapFree` at `0x180004464`
- `KERNEL32!HeapFree` at `0x180004481`
- `KERNEL32!HeapFree` at `0x1800047d8`
- `KERNEL32!HeapFree` at `0x1800047fc`
- `KERNEL32!HeapFree` at `0x180004814`
- `KERNEL32!HeapFree` at `0x18000482d`
- `KERNEL32!HeapFree` at `0x18000484a`
- `KERNEL32!HeapFree` at `0x180004878`
- `USER32!OemToCharBuffA` at `0x18000475b`
- `USER32!OemToCharBuffA` at `0x18000475b`

## pseudocode

```c
__int64 __fastcall DhcpUpdateAuditLogBlindQuar(
        int a1,
        const size_t *a2,
        unsigned int a3,
        struct _FILETIME a4,
        unsigned int a5,
        const size_t *a6,
        int a7,
        int a8,
        int a9,
        FILETIME FileTime,
        unsigned __int8 *a11,
        int a12,
        __int64 a13,
        const char *a14,
        const CHAR *a15,
        int cbMultiByte,
        const CHAR *a17,
        int a18,
        __int64 a19,
        int a20)
{
  const size_t *v21; // r14
  void *v23; // r13
  PWSTR v24; // r12
  __int64 v25; // rbx
  const size_t *v27; // r15
  __int64 v28; // rdx
  const char *v29; // rdi
  __int64 v30; // rax
  __int64 v31; // rdx
  const char *v32; // rax
  unsigned __int64 v33; // r8
  DWORD IfPrintable; // ebx
  WCHAR *v35; // rdi
  __int64 v36; // rdx
  __int64 v37; // rax
  __int64 v38; // rdx
  __int64 v39; // rax
  __int64 v40; // rdx
  __int64 v41; // rax
  __int64 v42; // rdx
  __int64 v43; // rax
  __int64 v44; // rdx
  unsigned int v45; // r13d
  unsigned int v46; // eax
  unsigned int v47; // r12d
  __int64 v48; // rcx
  unsigned int v49; // eax
  __int64 v50; // rdx
  __int64 v51; // rax
  SIZE_T v52; // rsi
  HRESULT v53; // eax
  PWSTR v54; // r14
  int v55; // edi
  HRESULT v56; // eax
  unsigned int v57; // r14d
  int v58; // edi
  PWSTR v59; // rax
  const CHAR *v60; // rdi
  const CHAR *v61; // rdi
  WCHAR *v62; // r15
  CHAR *v63; // rdi
  SIZE_T v64; // rax
  CHAR *v65; // rcx
  __int64 v66; // rdx
  unsigned __int64 v67; // rcx
  DWORD v68; // ebx
  size_t v69; // rsi
  DWORD pszFormat; // [rsp+28h] [rbp-D8h]
  __int64 v71; // [rsp+30h] [rbp-D0h]
  __int64 v72; // [rsp+30h] [rbp-D0h]
  __int64 v73; // [rsp+30h] [rbp-D0h]
  __int64 v74; // [rsp+30h] [rbp-D0h]
  __int64 v75; // [rsp+38h] [rbp-C8h]
  __int64 v76; // [rsp+40h] [rbp-C0h]
  __int64 v77; // [rsp+48h] [rbp-B8h]
  __int64 v78; // [rsp+50h] [rbp-B0h]
  __int64 v79; // [rsp+58h] [rbp-A8h]
  size_t pcbRemaining; // [rsp+70h] [rbp-90h] BYREF
  STRSAFE_LPWSTR ppszDestEnd; // [rsp+78h] [rbp-88h] BYREF
  PWSTR v82; // [rsp+80h] [rbp-80h]
  PCWSTR v83; // [rsp+88h] [rbp-78h]
  LPVOID v84; // [rsp+90h] [rbp-70h]
  int v85; // [rsp+98h] [rbp-68h] BYREF
  struct _FILETIME LocalFileTime; // [rsp+A0h] [rbp-60h] BYREF
  LPVOID lpMem; // [rsp+A8h] [rbp-58h] BYREF
  int v88; // [rsp+B0h] [rbp-50h] BYREF
  int v89; // [rsp+B4h] [rbp-4Ch]
  DWORD NumberOfBytesWritten; // [rsp+B8h] [rbp-48h] BYREF
  unsigned __int8 *v91; // [rsp+C0h] [rbp-40h]
  PCSZ SourceString; // [rsp+C8h] [rbp-38h]
  LPCCH lpMultiByteStr; // [rsp+D0h] [rbp-30h]
  LPCCH v94; // [rsp+D8h] [rbp-28h]
  __int64 v95; // [rsp+E0h] [rbp-20h]
  struct _SYSTEMTIME SystemTime; // [rsp+E8h] [rbp-18h] BYREF
  wchar_t v97[12]; // [rsp+F8h] [rbp-8h] BYREF
  wchar_t Buffer[16]; // [rsp+110h] [rbp+10h] BYREF
  _WORD v99[280]; // [rsp+130h] [rbp+30h] BYREF

  v21 = a6;
  v91 = a11;
  lpMultiByteStr = a15;
  v94 = a17;
  v89 = a1;
  v95 = a19;
  v23 = 0;
  SourceString = a14;
  v24 = 0;
  LocalFileTime = a4;
  NumberOfBytesWritten = 0;
  v85 = 1;
  v82 = 0;
  lpMem = 0;
  v88 = 0;
  if ( !DhcpGlobalAuditLogFlag )
    return 0;
  v25 = -1;
  if ( AuditLogHandle == (HANDLE)-1LL )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, &WPP_3f918084cf8d369c2c20a8a49a789173_Traceguids);
    return 0;
  }
  if ( (unsigned int)GetUserAndDomainName(v99) )
    v99[0] = 0;
  _wstrdate(Buffer);
  _wstrtime(v97);
  v27 = &Annotation;
  if ( a2 )
    v27 = a2;
  *(_QWORD *)&SystemTime.wYear = v27;
  if ( a6 )
  {
    v28 = -1;
    do
      ++v28;
    while ( *((_WORD *)a6 + v28) );
    if ( !(unsigned int)ConvertUnicodeToWideCharPunycode(a6, (unsigned int)(v28 + 1), &lpMem, &v88) && lpMem )
      v21 = (const size_t *)lpMem;
  }
  else
  {
    v21 = &Annotation;
  }
  if ( a3 )
  {
    v30 = DhcpIpAddressToDottedString(a3);
    v29 = ::SourceString;
    if ( v30 )
      v29 = (const char *)v30;
  }
  else
  {
    v29 = ::SourceString;
  }
  v31 = 16;
  v32 = v29;
  do
  {
    if ( !*v32 )
      break;
    ++v32;
    --v31;
  }
  while ( v31 );
  v33 = (16 - v31) & -(__int64)(v31 != 0);
  if ( !v31 )
    return 87;
  if ( v33 + 1 < v33 )
  {
    IfPrintable = 534;
    goto LABEL_30;
  }
  v84 = DhcpOemToUnicodeN(v29, 0, (unsigned __int16)v33 + 1);
  v23 = v84;
  if ( !v84 )
  {
    IfPrintable = 8;
LABEL_30:
    v35 = 0;
    goto LABEL_86;
  }
  v36 = -1;
  do
    ++v36;
  while ( *((_WORD *)v27 + v36) );
  v37 = -1;
  do
    ++v37;
  while ( *((_WORD *)v21 + v37) );
  v38 = v37 + v36;
  v39 = -1;
  do
    ++v39;
  while ( v29[v39] );
  v40 = v39 + v38;
  v41 = -1;
  do
    ++v41;
  while ( v97[v41] );
  v42 = v41 + v40;
  v43 = -1;
  do
    ++v43;
  while ( Buffer[v43] );
  v44 = v43 + v42;
  do
    ++v25;
  while ( v99[v25] );
  v45 = cbMultiByte;
  v46 = 4 * cbMultiByte + 1;
  if ( !cbMultiByte )
    v46 = 1;
  v47 = a18;
  v48 = 2 * a5 + (unsigned int)(2 * a12 + 99) + v25 + v44 + v46;
  v49 = 4 * a18 + 1;
  if ( !a18 )
    v49 = 1;
  v50 = v48 + v49;
  if ( a20 )
    v51 = (unsigned int)(2 * a20 + 1);
  else
    v51 = 1;
  IfPrintable = 8;
  v52 = 2 * (v50 + v51) + 696;
  v35 = (WCHAR *)HeapAlloc(gDhcpHeap, 8u, v52);
  v83 = v35;
  if ( v35 )
  {
    ppszDestEnd = v35;
    pcbRemaining = v52;
    v53 = StringCbPrintfExW(
            v35,
            v52,
            &ppszDestEnd,
            &pcbRemaining,
            0x1000u,
            L"%.2d,%s,%s,%s,%s,%s,",
            v89,
            Buffer,
            v97,
            *(_QWORD *)&SystemTime.wYear,
            v84,
            v21);
    v54 = 0;
    if ( v53 < 0 )
    {
      IfPrintable = 13;
      v24 = 0;
      goto LABEL_85;
    }
    v55 = 0;
    if ( a5 )
    {
      while ( 1 )
      {
        LODWORD(v71) = *(unsigned __int8 *)(*(_QWORD *)&LocalFileTime)++;
        if ( StringCbPrintfExW(ppszDestEnd, pcbRemaining, &ppszDestEnd, &pcbRemaining, 0x1000u, L"%.2X", v71) < 0 )
          break;
        if ( ++v55 >= a5 )
          goto LABEL_57;
      }
      IfPrintable = 13;
      v24 = 0;
      goto LABEL_84;
    }
LABEL_57:
    if ( StringCbPrintfExW(ppszDestEnd, pcbRemaining, &ppszDestEnd, &pcbRemaining, 0x1000u, L",%s,", v99) < 0 )
      goto LABEL_58;
    LODWORD(v72) = a8;
    if ( StringCbPrintfExW(ppszDestEnd, pcbRemaining, &ppszDestEnd, &pcbRemaining, 0x1000u, L"%lu,", v72) < 0 )
      goto LABEL_58;
    LODWORD(v73) = a9;
    if ( StringCbPrintfExW(ppszDestEnd, pcbRemaining, &ppszDestEnd, &pcbRemaining, 0x1000u, L"%ld,", v73) < 0 )
      goto LABEL_58;
    if ( FileTime.dwHighDateTime || FileTime.dwLowDateTime )
    {
      LocalFileTime = 0;
      if ( !FileTimeToLocalFileTime(&FileTime, &LocalFileTime) )
        goto LABEL_66;
      SystemTime = 0;
      if ( !FileTimeToSystemTime(&LocalFileTime, &SystemTime) )
        goto LABEL_66;
      LODWORD(v79) = SystemTime.wSecond;
      LODWORD(v78) = SystemTime.wMinute;
      LODWORD(v77) = SystemTime.wHour;
      LODWORD(v76) = SystemTime.wDay;
      LODWORD(v75) = SystemTime.wMonth;
      LODWORD(v74) = SystemTime.wYear;
      v56 = StringCbPrintfExW(
              ppszDestEnd,
              pcbRemaining,
              &ppszDestEnd,
              &pcbRemaining,
              0x1000u,
              L"%d-%d-%d %d:%d:%d:%d,",
              v74,
              v75,
              v76,
              v77,
              v78,
              v79,
              SystemTime.wMilliseconds);
    }
    else
    {
      v56 = StringCbPrintfExW(ppszDestEnd, pcbRemaining, &ppszDestEnd, &pcbRemaining, 0x1000u, L",");
    }
    if ( v56 < 0 )
      goto LABEL_58;
LABEL_66:
    v57 = a12;
    v58 = 0;
    if ( a12 )
    {
      do
      {
        LODWORD(v74) = *v91++;
        if ( StringCbPrintfExW(ppszDestEnd, pcbRemaining, &ppszDestEnd, &pcbRemaining, 0x1000u, L"%.2X", v74) < 0 )
          goto LABEL_77;
      }
      while ( ++v58 < v57 );
    }
    if ( StringCbPrintfExW(ppszDestEnd, pcbRemaining, &ppszDestEnd, &pcbRemaining, 0x1000u, L",") < 0 )
    {
LABEL_77:
      IfPrintable = 13;
      v24 = 0;
      goto LABEL_84;
    }
    if ( SourceString && a13 )
    {
      v59 = DhcpOemToUnicodeN(SourceString, 0, (unsigned __int16)a13 + 1);
      v82 = v59;
      v54 = v59;
      if ( !v59 )
      {
        v24 = 0;
        goto LABEL_84;
      }
      if ( StringCbPrintfExW(ppszDestEnd, pcbRemaining, &ppszDestEnd, &pcbRemaining, 0x1000u, L"%s", v59) < 0 )
      {
LABEL_58:
        IfPrintable = 13;
        v24 = v54;
LABEL_84:
        v35 = (WCHAR *)v83;
        goto LABEL_85;
      }
    }
    else
    {
      v54 = 0;
    }
    if ( StringCbPrintfExW(ppszDestEnd, pcbRemaining, &ppszDestEnd, &pcbRemaining, 0x1000u, L",") >= 0 )
    {
      v60 = lpMultiByteStr;
      IfPrintable = PutHexStringInBufferAndFindIfPrintable(lpMultiByteStr, v45, &ppszDestEnd, &pcbRemaining, &v85);
      if ( IfPrintable )
        goto LABEL_83;
      if ( StringCbPrintfExW(ppszDestEnd, pcbRemaining, &ppszDestEnd, &pcbRemaining, 0x1000u, L",") >= 0 )
      {
        if ( v45 )
        {
          if ( v85 )
          {
            IfPrintable = PutASCIIStringInBuffer(v60, v45, &ppszDestEnd, &pcbRemaining);
            if ( IfPrintable )
              goto LABEL_83;
          }
        }
        if ( StringCbPrintfExW(ppszDestEnd, pcbRemaining, &ppszDestEnd, &pcbRemaining, 0x1000u, L",") >= 0 )
        {
          v61 = v94;
          IfPrintable = PutHexStringInBufferAndFindIfPrintable(v94, v47, &ppszDestEnd, &pcbRemaining, &v85);
          if ( IfPrintable )
            goto LABEL_83;
          if ( StringCbPrintfExW(ppszDestEnd, pcbRemaining, &ppszDestEnd, &pcbRemaining, 0x1000u, L",") >= 0 )
          {
            if ( v47 )
            {
              if ( v85 )
              {
                IfPrintable = PutASCIIStringInBuffer(v61, v47, &ppszDestEnd, &pcbRemaining);
                if ( IfPrintable )
                  goto LABEL_83;
              }
            }
            if ( StringCbPrintfExW(ppszDestEnd, pcbRemaining, &ppszDestEnd, &pcbRemaining, 0x1000u, L",") >= 0 )
            {
              IfPrintable = PutHexStringInBufferAndFindIfPrintable(
                              v95,
                              (unsigned int)a20,
                              &ppszDestEnd,
                              &pcbRemaining,
                              &v85);
              if ( IfPrintable )
                goto LABEL_83;
              if ( StringCbPrintfExW(ppszDestEnd, pcbRemaining, &ppszDestEnd, &pcbRemaining, 0x1000u, L",") >= 0
                && StringCbPrintfExW(ppszDestEnd, pcbRemaining, &ppszDestEnd, &pcbRemaining, 0x1000u, L"%ld") >= 0
                && StringCbCopyExW(ppszDestEnd, pcbRemaining, L"\r\n", 0, &pcbRemaining, pszFormat) >= 0 )
              {
                v62 = (WCHAR *)v83;
                v63 = (CHAR *)DhcpUnicodeToOem(v83);
                if ( v63 )
                {
                  if ( v52 > 0x7FFFFFFF )
                    goto LABEL_127;
                  v64 = v52;
                  v65 = v63;
                  if ( v52 )
                  {
                    v66 = IfPrintable + 1;
                    do
                    {
                      if ( !*v65 )
                        break;
                      v65 += v66;
                      v64 -= v66;
                    }
                    while ( v64 );
                  }
                  v67 = v64 ? v52 - v64 : 0LL;
                  if ( v64 )
                  {
                    v68 = -1;
                    if ( v67 <= 0xFFFFFFFF )
                      v68 = v67;
                  }
                  else
                  {
LABEL_127:
                    v68 = -1;
                    v69 = (v52 - pcbRemaining) >> 1;
                    if ( v69 <= 0xFFFFFFFF )
                      v68 = v69;
                  }
                  OemToCharBuffA(v63, v63, v68);
                  if ( !WriteFile(AuditLogHandle, v63, v68, &NumberOfBytesWritten, 0) )
                  {
                    IfPrintable = GetLastError();
                    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
                    {
                      WPP_SF_D(
                        *((_QWORD *)WPP_GLOBAL_Control + 2),
                        24,
                        &WPP_3f918084cf8d369c2c20a8a49a789173_Traceguids,
                        IfPrintable);
                    }
                    HeapFree(gDhcpHeap, 0, v63);
                    v24 = v82;
                    v35 = v62;
                    goto LABEL_85;
                  }
                  HeapFree(gDhcpHeap, 0, v63);
                }
                HeapFree(gDhcpHeap, 0, v62);
                HeapFree(gDhcpHeap, 0, v84);
                if ( v54 )
                  HeapFree(gDhcpHeap, 0, v54);
                if ( DhcpHeap && lpMem )
                  HeapFree(DhcpHeap, 0, lpMem);
                return 0;
              }
            }
          }
        }
      }
    }
    IfPrintable = 13;
LABEL_83:
    v24 = v82;
    goto LABEL_84;
  }
  v24 = 0;
LABEL_85:
  v23 = v84;
LABEL_86:
  if ( DhcpHeap && lpMem )
    HeapFree(DhcpHeap, 0, lpMem);
  if ( v23 )
    HeapFree(gDhcpHeap, 0, v23);
  if ( v24 )
    HeapFree(gDhcpHeap, 0, v24);
  if ( v35 )
    HeapFree(gDhcpHeap, 0, v35);
  if ( !AuditLogErrorLogged )
  {
    AuditLogErrorLogged = 1;
    DhcpServerEventLog(1027, 1, IfPrintable);
  }
  return IfPrintable;
}

```

## disassembly

```asm
0x180003cf4  push    rbp
0x180003cf6  push    rbx
0x180003cf7  push    rsi
0x180003cf8  push    rdi
0x180003cf9  push    r12
0x180003cfb  push    r13
0x180003cfd  push    r14
0x180003cff  push    r15
0x180003d01  lea     rbp, [rsp-278h]
0x180003d09  sub     rsp, 378h
0x180003d10  mov     rax, cs:__security_cookie
0x180003d17  xor     rax, rsp
0x180003d1a  mov     [rbp+2B0h+var_50], rax
0x180003d21  mov     rax, [rbp+2B0h+arg_50]
0x180003d28  mov     esi, r8d
0x180003d2b  mov     r14, [rbp+2B0h+arg_28]
0x180003d32  mov     rdi, rdx
0x180003d35  mov     [rbp+2B0h+var_2F0], rax
0x180003d39  mov     rax, [rbp+2B0h+arg_70]
0x180003d40  mov     [rbp+2B0h+lpMultiByteStr], rax
0x180003d44  mov     rax, [rbp+2B0h+arg_80]
0x180003d4b  mov     [rbp+2B0h+var_2D8], rax
0x180003d4f  mov     rax, [rbp+2B0h+arg_90]
0x180003d56  mov     [rbp+2B0h+var_2FC], ecx
0x180003d59  mov     rcx, [rbp+2B0h+arg_68]
0x180003d60  mov     [rbp+2B0h+var_2D0], rax
0x180003d64  xor     eax, eax
0x180003d66  cmp     cs:DhcpGlobalAuditLogFlag, eax
0x180003d6c  mov     r13d, eax
0x180003d6f  mov     [rbp+2B0h+SourceString], rcx
0x180003d73  mov     r12d, eax
0x180003d76  mov     qword ptr [rbp+2B0h+LocalFileTime.dwLowDateTime], r9
0x180003d7a  lea     ecx, [rax+1]
0x180003d7d  mov     [rbp+2B0h+NumberOfBytesWritten], eax
0x180003d80  mov     [rbp+2B0h+var_318], ecx
0x180003d83  mov     [rbp+2B0h+var_330], rax
0x180003d87  mov     [rbp+2B0h+lpMem], rax
0x180003d8b  mov     [rbp+2B0h+var_300], eax
0x180003d8e  jz      short loc_180003DC9
0x180003d90  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180003d94  cmp     cs:AuditLogHandle, rbx
0x180003d9b  jnz     short loc_180003DEF
0x180003d9d  mov     rcx, cs:WPP_GLOBAL_Control
0x180003da4  lea     rax, WPP_GLOBAL_Control
0x180003dab  cmp     rcx, rax
0x180003dae  jz      short loc_180003DC9
0x180003db0  test    byte ptr [rcx+1Ch], 10h
0x180003db4  jz      short loc_180003DC9
0x180003db6  mov     rcx, [rcx+10h]
0x180003dba  lea     edx, [rbx+18h]
0x180003dbd  lea     r8, WPP_3f918084cf8d369c2c20a8a49a789173_Traceguids
0x180003dc4  call    WPP_SF_
0x180003dc9  xor     eax, eax
0x180003dcb  mov     rcx, [rbp+2B0h+var_50]
0x180003dd2  xor     rcx, rsp; StackCookie
0x180003dd5  call    __security_check_cookie
0x180003dda  add     rsp, 378h
0x180003de1  pop     r15
0x180003de3  pop     r14
0x180003de5  pop     r13
0x180003de7  pop     r12
0x180003de9  pop     rdi
0x180003dea  pop     rsi
0x180003deb  pop     rbx
0x180003dec  pop     rbp
0x180003ded  retn
0x180003def  lea     rcx, [rbp+2B0h+var_280]
0x180003df3  call    GetUserAndDomainName
0x180003df8  xor     ecx, ecx
0x180003dfa  test    eax, eax
0x180003dfc  jz      short loc_180003E02
0x180003dfe  mov     [rbp+2B0h+var_280], cx
0x180003e02  lea     rcx, [rbp+2B0h+Buffer]; Buffer
0x180003e06  call    cs:__imp__wstrdate
0x180003e0d  nop     dword ptr [rax+rax+00h]
0x180003e12  lea     rcx, [rbp+2B0h+var_2B8]; Buffer
0x180003e16  call    cs:__imp__wstrtime
0x180003e1d  nop     dword ptr [rax+rax+00h]
0x180003e22  test    rdi, rdi
0x180003e25  lea     r15, Annotation
0x180003e2c  cmovnz  r15, rdi
0x180003e30  xor     edi, edi
0x180003e32  mov     qword ptr [rbp+2B0h+SystemTime.wYear], r15
0x180003e36  test    r14, r14
0x180003e39  jnz     short loc_180003E44
0x180003e3b  lea     r14, Annotation
0x180003e42  jmp     short loc_180003E72
0x180003e44  mov     rdx, rbx
0x180003e47  inc     rdx
0x180003e4a  cmp     [r14+rdx*2], di
0x180003e4f  jnz     short loc_180003E47
0x180003e51  inc     edx
0x180003e53  lea     r9, [rbp+2B0h+var_300]
0x180003e57  lea     r8, [rbp+2B0h+lpMem]
0x180003e5b  mov     rcx, r14
0x180003e5e  call    ConvertUnicodeToWideCharPunycode
0x180003e63  test    eax, eax
0x180003e65  jnz     short loc_180003E72
0x180003e67  mov     rax, [rbp+2B0h+lpMem]
0x180003e6b  test    rax, rax
0x180003e6e  cmovnz  r14, rax
0x180003e72  test    esi, esi
0x180003e74  jnz     short loc_180003E81
0x180003e76  lea     rdi, SourceString
0x180003e7d  xor     esi, esi
0x180003e7f  jmp     short loc_180003E98
0x180003e81  mov     ecx, esi
0x180003e83  call    DhcpIpAddressToDottedString
0x180003e88  xor     esi, esi
0x180003e8a  lea     rdi, SourceString
0x180003e91  test    rax, rax
0x180003e94  cmovnz  rdi, rax
0x180003e98  mov     edx, 10h
0x180003e9d  mov     rax, rdi
0x180003ea0  lea     ecx, [rdx-0Fh]
0x180003ea3  cmp     [rax], sil
0x180003ea6  jz      short loc_180003EB0
0x180003ea8  add     rax, rcx
0x180003eab  sub     rdx, rcx
0x180003eae  jnz     short loc_180003EA3
0x180003eb0  mov     ecx, 10h
0x180003eb5  mov     rax, rdx
0x180003eb8  sub     rcx, rdx
0x180003ebb  neg     rax
0x180003ebe  sbb     r8, r8
0x180003ec1  and     r8, rcx
0x180003ec4  test    rdx, rdx
0x180003ec7  jnz     short loc_180003ED1
0x180003ec9  lea     eax, [rdx+57h]
0x180003ecc  jmp     loc_180003DCB
0x180003ed1  lea     rax, [r8+1]
0x180003ed5  cmp     rax, r8
0x180003ed8  jb      loc_180004889
0x180003ede  movzx   r8d, ax
0x180003ee2  xor     edx, edx
0x180003ee4  mov     rcx, rdi; SourceString
0x180003ee7  call    DhcpOemToUnicodeN
0x180003eec  mov     [rbp+2B0h+var_320], rax
0x180003ef0  mov     r13, rax
0x180003ef3  test    rax, rax
0x180003ef6  jnz     short loc_180003F06
0x180003ef8  lea     ebx, [rax+8]
0x180003efb  mov     rdi, r12
0x180003efe  xor     r15d, r15d
0x180003f01  jmp     loc_180004410
0x180003f06  mov     rdx, rbx
0x180003f09  inc     rdx
0x180003f0c  cmp     [r15+rdx*2], si
0x180003f11  jnz     short loc_180003F09
0x180003f13  mov     rax, rbx
0x180003f16  inc     rax
0x180003f19  cmp     [r14+rax*2], si
0x180003f1e  jnz     short loc_180003F16
0x180003f20  add     rdx, rax
0x180003f23  mov     rax, rbx
0x180003f26  inc     rax
0x180003f29  cmp     [rdi+rax], sil
0x180003f2d  jnz     short loc_180003F26
0x180003f2f  add     rdx, rax
0x180003f32  lea     rcx, [rbp+2B0h+var_2B8]
0x180003f36  mov     rax, rbx
0x180003f39  inc     rax
0x180003f3c  cmp     [rcx+rax*2], si
0x180003f40  jnz     short loc_180003F39
0x180003f42  add     rdx, rax
0x180003f45  lea     rcx, [rbp+2B0h+Buffer]
0x180003f49  mov     rax, rbx
0x180003f4c  inc     rax
0x180003f4f  cmp     [rcx+rax*2], si
0x180003f53  jnz     short loc_180003F4C
0x180003f55  add     rdx, rax
0x180003f58  lea     rax, [rbp+2B0h+var_280]
0x180003f5c  inc     rbx
0x180003f5f  cmp     [rax+rbx*2], si
0x180003f63  jnz     short loc_180003F5C
0x180003f65  mov     eax, [rbp+2B0h+arg_58]
0x180003f6b  lea     r8, [rbx+rdx]
0x180003f6f  mov     r13d, [rbp+2B0h+cbMultiByte]
0x180003f76  mov     r9d, 1
0x180003f7c  mov     r15d, [rbp+2B0h+arg_20]
0x180003f83  lea     ecx, ds:63h[rax*2]
0x180003f8a  add     r8, rcx
0x180003f8d  lea     eax, ds:1[r13*4]
0x180003f95  lea     ecx, [r15+r15]
0x180003f99  add     r8, rcx
0x180003f9c  test    r13d, r13d
0x180003f9f  jnz     short loc_180003FA4
0x180003fa1  mov     eax, r9d
0x180003fa4  mov     r12d, [rbp+2B0h+arg_88]
0x180003fab  mov     ecx, eax
0x180003fad  add     rcx, r8
0x180003fb0  lea     eax, ds:1[r12*4]
0x180003fb8  test    r12d, r12d
0x180003fbb  jnz     short loc_180003FC0
0x180003fbd  mov     eax, r9d
0x180003fc0  mov     edx, eax
0x180003fc2  mov     eax, [rbp+2B0h+arg_98]
0x180003fc8  add     rdx, rcx
0x180003fcb  test    eax, eax
0x180003fcd  jz      short loc_180003FD8
0x180003fcf  lea     eax, ds:1[rax*2]
0x180003fd6  jmp     short loc_180003FDB
0x180003fd8  mov     eax, r9d
0x180003fdb  mov     rcx, cs:gDhcpHeap; hHeap
0x180003fe2  add     rax, rdx
0x180003fe5  mov     ebx, 8
0x180003fea  mov     edx, ebx; dwFlags
0x180003fec  lea     rsi, ds:2B8h[rax*2]
0x180003ff4  mov     r8, rsi; dwBytes
0x180003ff7  call    cs:__imp_HeapAlloc
0x180003ffe  nop     dword ptr [rax+rax+00h]
0x180004003  mov     rdi, rax
0x180004006  mov     [rbp+2B0h+var_328], rax
0x18000400a  xor     eax, eax
0x18000400c  test    rdi, rdi
0x18000400f  jnz     short loc_18000401C
0x180004011  mov     r12d, eax
0x180004014  xor     r15d, r15d
0x180004017  jmp     loc_18000440C
0x18000401c  mov     rax, [rbp+2B0h+var_320]
0x180004020  lea     r9, [rsp+3B0h+pcbRemaining]; pcbRemaining
0x180004025  mov     [rsp+3B0h+var_358], r14
0x18000402a  lea     r8, [rsp+3B0h+ppszDestEnd]; ppszDestEnd
0x18000402f  mov     [rsp+3B0h+var_360], rax
0x180004034  mov     rdx, rsi; cbDest
0x180004037  mov     rax, qword ptr [rbp+2B0h+SystemTime.wYear]
0x18000403b  mov     rcx, rdi; pszDest
0x18000403e  mov     [rsp+3B0h+var_368], rax
0x180004043  lea     rax, [rbp+2B0h+var_2B8]
0x180004047  mov     [rsp+3B0h+var_370], rax
0x18000404c  lea     rax, [rbp+2B0h+Buffer]
0x180004050  mov     [rsp+3B0h+var_378], rax
0x180004055  mov     eax, [rbp+2B0h+var_2FC]
0x180004058  mov     dword ptr [rsp+3B0h+var_380], eax
0x18000405c  lea     rax, a2dSSSSS; "%.2d,%s,%s,%s,%s,%s,"
0x180004063  mov     [rsp+3B0h+pszFormat], rax; pszFormat
0x180004068  mov     [rsp+3B0h+dwFlags], 1000h; dwFlags
0x180004070  mov     [rsp+3B0h+ppszDestEnd], rdi
0x180004075  mov     [rsp+3B0h+pcbRemaining], rsi
0x18000407a  call    StringCbPrintfExW
0x18000407f  xor     r14d, r14d
0x180004082  test    eax, eax
0x180004084  jns     short loc_18000408F
0x180004086  lea     ebx, [r14+0Dh]
0x18000408a  mov     r12d, r14d
0x18000408d  jmp     short loc_180004014
0x18000408f  lea     rdx, a2x; "%.2X"
0x180004096  mov     edi, r14d
0x180004099  test    r15d, r15d
0x18000409c  jz      short loc_1800040E8
0x18000409e  mov     rcx, qword ptr [rbp+2B0h+LocalFileTime.dwLowDateTime]
0x1800040a2  lea     r9, [rsp+3B0h+pcbRemaining]; pcbRemaining
0x1800040a7  lea     r8, [rsp+3B0h+ppszDestEnd]; ppszDestEnd
0x1800040ac  movzx   eax, byte ptr [rcx]
0x1800040af  inc     rcx
0x1800040b2  mov     dword ptr [rsp+3B0h+var_380], eax
0x1800040b6  mov     [rsp+3B0h+pszFormat], rdx; pszFormat
0x1800040bb  mov     rdx, [rsp+3B0h+pcbRemaining]; cbDest
0x1800040c0  mov     qword ptr [rbp+2B0h+LocalFileTime.dwLowDateTime], rcx
0x1800040c4  mov     rcx, [rsp+3B0h+ppszDestEnd]; pszDest
0x1800040c9  mov     [rsp+3B0h+dwFlags], 1000h; dwFlags
0x1800040d1  call    StringCbPrintfExW
0x1800040d6  test    eax, eax
0x1800040d8  js      short loc_180004133
0x1800040da  inc     edi
0x1800040dc  lea     rdx, a2x; "%.2X"
0x1800040e3  cmp     edi, r15d
0x1800040e6  jb      short loc_18000409E
0x1800040e8  mov     rdx, [rsp+3B0h+pcbRemaining]; cbDest
0x1800040ed  lea     rax, [rbp+2B0h+var_280]
0x1800040f1  mov     rcx, [rsp+3B0h+ppszDestEnd]; pszDest
0x1800040f6  lea     r9, [rsp+3B0h+pcbRemaining]; pcbRemaining
0x1800040fb  mov     [rsp+3B0h+var_380], rax
0x180004100  lea     r8, [rsp+3B0h+ppszDestEnd]; ppszDestEnd
0x180004105  lea     rax, aS_1; ",%s,"
0x18000410c  mov     edi, 1000h
0x180004111  mov     [rsp+3B0h+pszFormat], rax; pszFormat
0x180004116  mov     [rsp+3B0h+dwFlags], edi; dwFlags
0x18000411a  call    StringCbPrintfExW
0x18000411f  xor     r15d, r15d
0x180004122  test    eax, eax
0x180004124  jns     short loc_180004143
0x180004126  mov     ebx, 0Dh
0x18000412b  mov     r12, r14
0x18000412e  jmp     loc_180004408
0x180004133  mov     ebx, 0Dh
0x180004138  mov     r12, r14
0x18000413b  xor     r15d, r15d
0x18000413e  jmp     loc_180004408
0x180004143  mov     eax, [rbp+2B0h+arg_38]
0x180004149  lea     r9, [rsp+3B0h+pcbRemaining]; pcbRemaining
0x18000414e  mov     rdx, [rsp+3B0h+pcbRemaining]; cbDest
0x180004153  lea     r8, [rsp+3B0h+ppszDestEnd]; ppszDestEnd
0x180004158  mov     rcx, [rsp+3B0h+ppszDestEnd]; pszDest
0x18000415d  mov     dword ptr [rsp+3B0h+var_380], eax
0x180004161  lea     rax, aLu; "%lu,"
0x180004168  mov     [rsp+3B0h+pszFormat], rax; pszFormat
0x18000416d  mov     [rsp+3B0h+dwFlags], edi; dwFlags
0x180004171  call    StringCbPrintfExW
0x180004176  test    eax, eax
  ... truncated ...
```
