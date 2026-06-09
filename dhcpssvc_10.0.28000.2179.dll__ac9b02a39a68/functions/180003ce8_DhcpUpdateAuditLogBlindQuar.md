# DhcpUpdateAuditLogBlindQuar

- ea: `0x180003ce8`
- end: `0x1800048ae`
- name: `DhcpUpdateAuditLogBlindQuar`
- size: `3014`
- prototype: `__int64 __fastcall(int, int, int, int, int, __int64, int, int, int, FILETIME FileTime, __int64, int, __int64, __int64, __int64, int cbMultiByte, __int64, int, __int64, int)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, installer_update`

## callers

- `0x180004a5c`

## callees

- `0x18000282c`
- `0x180003228`
- `0x180003ce8`
- `0x1800050c8`
- `0x1800051f4`
- `0x1800052d4`
- `0x180005410`
- `0x1800626dc`
- `0x180062e10`
- `0x18008f58c`
- `0x18008f614`
- `0x18008f6d8`
- `0x1800c9618`
- `0x1800cdac0`

## import_xrefs

- `msvcrt!_wstrtime` at `0x180003e0a`
- `msvcrt!_wstrtime` at `0x180003e0a`
- `msvcrt!_wstrdate` at `0x180003dfa`
- `msvcrt!_wstrdate` at `0x180003dfa`
- `KERNEL32!HeapAlloc` at `0x180003ff0`
- `KERNEL32!HeapAlloc` at `0x180003ff0`
- `KERNEL32!FileTimeToSystemTime` at `0x180004301`
- `KERNEL32!FileTimeToSystemTime` at `0x180004301`
- `KERNEL32!FileTimeToLocalFileTime` at `0x1800042de`
- `KERNEL32!FileTimeToLocalFileTime` at `0x1800042de`
- `KERNEL32!WriteFile` at `0x180004776`
- `KERNEL32!WriteFile` at `0x180004776`
- `KERNEL32!GetLastError` at `0x180004786`
- `KERNEL32!GetLastError` at `0x180004786`
- `KERNEL32!HeapFree` at `0x180004423`
- `KERNEL32!HeapFree` at `0x180004440`
- `KERNEL32!HeapFree` at `0x18000445d`
- `KERNEL32!HeapFree` at `0x18000447a`
- `KERNEL32!HeapFree` at `0x1800047d1`
- `KERNEL32!HeapFree` at `0x1800047f5`
- `KERNEL32!HeapFree` at `0x18000480d`
- `KERNEL32!HeapFree` at `0x180004826`
- `KERNEL32!HeapFree` at `0x180004843`
- `KERNEL32!HeapFree` at `0x180004871`
- `KERNEL32!HeapFree` at `0x180004423`
- `KERNEL32!HeapFree` at `0x180004440`
- `KERNEL32!HeapFree` at `0x18000445d`
- `KERNEL32!HeapFree` at `0x18000447a`
- `KERNEL32!HeapFree` at `0x1800047d1`
- `KERNEL32!HeapFree` at `0x1800047f5`
- `KERNEL32!HeapFree` at `0x18000480d`
- `KERNEL32!HeapFree` at `0x180004826`
- `KERNEL32!HeapFree` at `0x180004843`
- `KERNEL32!HeapFree` at `0x180004871`
- `USER32!OemToCharBuffA` at `0x180004754`
- `USER32!OemToCharBuffA` at `0x180004754`

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
        unsigned int a12,
        __int64 a13,
        const char *a14,
        const CHAR *a15,
        unsigned int cbMultiByte,
        const CHAR *a17,
        unsigned int a18,
        __int64 a19,
        unsigned int a20)
{
  const size_t *v21; // r14
  void *v23; // r13
  void *v24; // r12
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
  __int64 v36; // rsi
  __int64 v37; // r11
  __int64 v38; // r10
  __int64 v39; // r9
  __int64 v40; // r8
  unsigned int v41; // r13d
  __int64 v42; // rax
  unsigned int v43; // r12d
  __int64 v44; // rcx
  unsigned int v45; // eax
  __int64 v46; // rdx
  __int64 v47; // rax
  SIZE_T v48; // rsi
  WCHAR *v49; // rax
  HRESULT v50; // eax
  void *v51; // r14
  int v52; // edi
  HRESULT v53; // eax
  unsigned int v54; // r14d
  int v55; // edi
  __int64 v56; // rax
  const CHAR *v57; // rdi
  const CHAR *v58; // rdi
  WCHAR *v59; // r15
  CHAR *v60; // rdi
  SIZE_T v61; // rax
  CHAR *v62; // rcx
  __int64 v63; // rdx
  unsigned __int64 v64; // rcx
  DWORD v65; // ebx
  size_t v66; // rsi
  DWORD pszFormat; // [rsp+28h] [rbp-D8h]
  __int64 v68; // [rsp+30h] [rbp-D0h]
  __int64 v69; // [rsp+30h] [rbp-D0h]
  __int64 v70; // [rsp+30h] [rbp-D0h]
  __int64 v71; // [rsp+30h] [rbp-D0h]
  __int64 v72; // [rsp+38h] [rbp-C8h]
  __int64 v73; // [rsp+40h] [rbp-C0h]
  __int64 v74; // [rsp+48h] [rbp-B8h]
  __int64 v75; // [rsp+50h] [rbp-B0h]
  __int64 v76; // [rsp+58h] [rbp-A8h]
  size_t pcbRemaining; // [rsp+70h] [rbp-90h] BYREF
  STRSAFE_LPWSTR ppszDestEnd; // [rsp+78h] [rbp-88h] BYREF
  void *v79; // [rsp+80h] [rbp-80h]
  PCWSTR v80; // [rsp+88h] [rbp-78h]
  LPVOID v81; // [rsp+90h] [rbp-70h]
  int v82; // [rsp+98h] [rbp-68h] BYREF
  struct _FILETIME LocalFileTime; // [rsp+A0h] [rbp-60h] BYREF
  LPVOID lpMem; // [rsp+A8h] [rbp-58h] BYREF
  int v85; // [rsp+B0h] [rbp-50h] BYREF
  int v86; // [rsp+B4h] [rbp-4Ch]
  DWORD NumberOfBytesWritten; // [rsp+B8h] [rbp-48h] BYREF
  unsigned __int8 *v88; // [rsp+C0h] [rbp-40h]
  PCSZ SourceString; // [rsp+C8h] [rbp-38h]
  LPCCH lpMultiByteStr; // [rsp+D0h] [rbp-30h]
  LPCCH v91; // [rsp+D8h] [rbp-28h]
  __int64 v92; // [rsp+E0h] [rbp-20h]
  struct _SYSTEMTIME SystemTime; // [rsp+E8h] [rbp-18h] BYREF
  wchar_t v94[12]; // [rsp+F8h] [rbp-8h] BYREF
  wchar_t Buffer[16]; // [rsp+110h] [rbp+10h] BYREF
  _WORD v96[280]; // [rsp+130h] [rbp+30h] BYREF

  v21 = a6;
  v88 = a11;
  lpMultiByteStr = a15;
  v91 = a17;
  v86 = a1;
  v92 = a19;
  v23 = 0;
  SourceString = a14;
  v24 = 0;
  LocalFileTime = a4;
  NumberOfBytesWritten = 0;
  v82 = 1;
  v79 = 0;
  lpMem = 0;
  v85 = 0;
  if ( !DhcpGlobalAuditLogFlag )
    return 0;
  v25 = -1;
  if ( AuditLogHandle == (HANDLE)-1LL )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, &WPP_3f918084cf8d369c2c20a8a49a789173_Traceguids);
    return 0;
  }
  if ( (unsigned int)GetUserAndDomainName(v96) )
    v96[0] = 0;
  _wstrdate(Buffer);
  _wstrtime(v94);
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
    if ( !(unsigned int)ConvertUnicodeToWideCharPunycode(a6, (unsigned int)(v28 + 1), &lpMem, &v85) && lpMem )
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
  if ( !v31 )
    return 87;
  v33 = (16 - v31) & -(__int64)(v31 != 0);
  if ( v33 + 1 >= v33 )
  {
    v23 = (void *)DhcpOemToUnicodeN(v29);
    v81 = v23;
    if ( !v23 )
    {
      IfPrintable = 8;
      v35 = 0;
      goto LABEL_85;
    }
    v36 = -1;
    do
      ++v36;
    while ( v96[v36] );
    v37 = -1;
    do
      ++v37;
    while ( Buffer[v37] );
    v38 = -1;
    do
      ++v38;
    while ( v94[v38] );
    v39 = -1;
    do
      ++v39;
    while ( v29[v39] );
    v40 = -1;
    do
      ++v40;
    while ( *((_WORD *)v27 + v40) );
    do
      ++v25;
    while ( *((_WORD *)v21 + v25) );
    v41 = cbMultiByte;
    if ( cbMultiByte )
      v42 = 4 * cbMultiByte + 1;
    else
      v42 = 1;
    v43 = a18;
    v44 = v42 + v39 + v25 + v40 + v36 + v37 + 2 * a5 + v38 + 2 * a12 + 99;
    v45 = 4 * a18 + 1;
    if ( !a18 )
      v45 = 1;
    v46 = v44 + v45;
    if ( a20 )
      v47 = 2 * a20 + 1;
    else
      v47 = 1;
    IfPrintable = 8;
    v48 = 2 * (v46 + v47) + 696;
    v49 = (WCHAR *)HeapAlloc(gDhcpHeap, 8u, v48);
    v80 = v49;
    v35 = v49;
    if ( !v49 )
    {
      v24 = 0;
LABEL_84:
      v23 = v81;
      goto LABEL_85;
    }
    ppszDestEnd = v49;
    pcbRemaining = v48;
    v50 = StringCbPrintfExW(
            v49,
            v48,
            &ppszDestEnd,
            &pcbRemaining,
            0x1000u,
            L"%.2d,%s,%s,%s,%s,%s,",
            v86,
            Buffer,
            v94,
            *(_QWORD *)&SystemTime.wYear,
            v81,
            v21);
    v51 = 0;
    if ( v50 < 0 )
    {
      IfPrintable = 13;
      v24 = 0;
      goto LABEL_84;
    }
    v52 = 0;
    if ( a5 )
    {
      while ( 1 )
      {
        LODWORD(v68) = *(unsigned __int8 *)(*(_QWORD *)&LocalFileTime)++;
        if ( StringCbPrintfExW(ppszDestEnd, pcbRemaining, &ppszDestEnd, &pcbRemaining, 0x1000u, L"%.2X", v68) < 0 )
          break;
        if ( ++v52 >= a5 )
          goto LABEL_56;
      }
      IfPrintable = 13;
      v24 = 0;
      goto LABEL_83;
    }
LABEL_56:
    if ( StringCbPrintfExW(ppszDestEnd, pcbRemaining, &ppszDestEnd, &pcbRemaining, 0x1000u, L",%s,", v96) < 0 )
      goto LABEL_57;
    LODWORD(v69) = a8;
    if ( StringCbPrintfExW(ppszDestEnd, pcbRemaining, &ppszDestEnd, &pcbRemaining, 0x1000u, L"%lu,", v69) < 0 )
      goto LABEL_57;
    LODWORD(v70) = a9;
    if ( StringCbPrintfExW(ppszDestEnd, pcbRemaining, &ppszDestEnd, &pcbRemaining, 0x1000u, L"%ld,", v70) < 0 )
      goto LABEL_57;
    if ( FileTime.dwHighDateTime || FileTime.dwLowDateTime )
    {
      LocalFileTime = 0;
      if ( !FileTimeToLocalFileTime(&FileTime, &LocalFileTime) )
        goto LABEL_65;
      SystemTime = 0;
      if ( !FileTimeToSystemTime(&LocalFileTime, &SystemTime) )
        goto LABEL_65;
      LODWORD(v76) = SystemTime.wSecond;
      LODWORD(v75) = SystemTime.wMinute;
      LODWORD(v74) = SystemTime.wHour;
      LODWORD(v73) = SystemTime.wDay;
      LODWORD(v72) = SystemTime.wMonth;
      LODWORD(v71) = SystemTime.wYear;
      v53 = StringCbPrintfExW(
              ppszDestEnd,
              pcbRemaining,
              &ppszDestEnd,
              &pcbRemaining,
              0x1000u,
              L"%d-%d-%d %d:%d:%d:%d,",
              v71,
              v72,
              v73,
              v74,
              v75,
              v76,
              SystemTime.wMilliseconds);
    }
    else
    {
      v53 = StringCbPrintfExW(ppszDestEnd, pcbRemaining, &ppszDestEnd, &pcbRemaining, 0x1000u, L",");
    }
    if ( v53 < 0 )
      goto LABEL_57;
LABEL_65:
    v54 = a12;
    v55 = 0;
    if ( a12 )
    {
      do
      {
        LODWORD(v71) = *v88++;
        if ( StringCbPrintfExW(ppszDestEnd, pcbRemaining, &ppszDestEnd, &pcbRemaining, 0x1000u, L"%.2X", v71) < 0 )
          goto LABEL_76;
      }
      while ( ++v55 < v54 );
    }
    if ( StringCbPrintfExW(ppszDestEnd, pcbRemaining, &ppszDestEnd, &pcbRemaining, 0x1000u, L",") < 0 )
    {
LABEL_76:
      IfPrintable = 13;
      v24 = 0;
      goto LABEL_83;
    }
    if ( SourceString && a13 )
    {
      v56 = DhcpOemToUnicodeN(SourceString);
      v79 = (void *)v56;
      v51 = (void *)v56;
      if ( !v56 )
      {
        v24 = 0;
        goto LABEL_83;
      }
      if ( StringCbPrintfExW(ppszDestEnd, pcbRemaining, &ppszDestEnd, &pcbRemaining, 0x1000u, L"%s", v56) < 0 )
      {
LABEL_57:
        IfPrintable = 13;
        v24 = v51;
LABEL_83:
        v35 = (WCHAR *)v80;
        goto LABEL_84;
      }
    }
    else
    {
      v51 = 0;
    }
    if ( StringCbPrintfExW(ppszDestEnd, pcbRemaining, &ppszDestEnd, &pcbRemaining, 0x1000u, L",") >= 0 )
    {
      v57 = lpMultiByteStr;
      IfPrintable = PutHexStringInBufferAndFindIfPrintable(lpMultiByteStr, v41, &ppszDestEnd, &pcbRemaining, &v82);
      if ( IfPrintable )
        goto LABEL_82;
      if ( StringCbPrintfExW(ppszDestEnd, pcbRemaining, &ppszDestEnd, &pcbRemaining, 0x1000u, L",") >= 0 )
      {
        if ( v41 )
        {
          if ( v82 )
          {
            IfPrintable = PutASCIIStringInBuffer(v57, v41, &ppszDestEnd, &pcbRemaining);
            if ( IfPrintable )
              goto LABEL_82;
          }
        }
        if ( StringCbPrintfExW(ppszDestEnd, pcbRemaining, &ppszDestEnd, &pcbRemaining, 0x1000u, L",") >= 0 )
        {
          v58 = v91;
          IfPrintable = PutHexStringInBufferAndFindIfPrintable(v91, v43, &ppszDestEnd, &pcbRemaining, &v82);
          if ( IfPrintable )
            goto LABEL_82;
          if ( StringCbPrintfExW(ppszDestEnd, pcbRemaining, &ppszDestEnd, &pcbRemaining, 0x1000u, L",") >= 0 )
          {
            if ( v43 )
            {
              if ( v82 )
              {
                IfPrintable = PutASCIIStringInBuffer(v58, v43, &ppszDestEnd, &pcbRemaining);
                if ( IfPrintable )
                  goto LABEL_82;
              }
            }
            if ( StringCbPrintfExW(ppszDestEnd, pcbRemaining, &ppszDestEnd, &pcbRemaining, 0x1000u, L",") >= 0 )
            {
              IfPrintable = PutHexStringInBufferAndFindIfPrintable(v92, a20, &ppszDestEnd, &pcbRemaining, &v82);
              if ( IfPrintable )
                goto LABEL_82;
              if ( StringCbPrintfExW(ppszDestEnd, pcbRemaining, &ppszDestEnd, &pcbRemaining, 0x1000u, L",") >= 0
                && StringCbPrintfExW(ppszDestEnd, pcbRemaining, &ppszDestEnd, &pcbRemaining, 0x1000u, L"%ld") >= 0
                && StringCbCopyExW(ppszDestEnd, pcbRemaining, L"\r\n", 0, &pcbRemaining, pszFormat) >= 0 )
              {
                v59 = (WCHAR *)v80;
                v60 = (CHAR *)DhcpUnicodeToOem(v80);
                if ( v60 )
                {
                  if ( v48 > 0x7FFFFFFF )
                    goto LABEL_126;
                  v61 = v48;
                  v62 = v60;
                  if ( v48 )
                  {
                    v63 = IfPrintable + 1;
                    do
                    {
                      if ( !*v62 )
                        break;
                      v62 += v63;
                      v61 -= v63;
                    }
                    while ( v61 );
                  }
                  v64 = v61 ? v48 - v61 : 0LL;
                  if ( v61 )
                  {
                    v65 = -1;
                    if ( v64 <= 0xFFFFFFFF )
                      v65 = v64;
                  }
                  else
                  {
LABEL_126:
                    v65 = -1;
                    v66 = (v48 - pcbRemaining) >> 1;
                    if ( v66 <= 0xFFFFFFFF )
                      v65 = v66;
                  }
                  OemToCharBuffA(v60, v60, v65);
                  if ( !WriteFile(AuditLogHandle, v60, v65, &NumberOfBytesWritten, 0) )
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
                    HeapFree(gDhcpHeap, 0, v60);
                    v24 = v79;
                    v35 = v59;
                    goto LABEL_84;
                  }
                  HeapFree(gDhcpHeap, 0, v60);
                }
                HeapFree(gDhcpHeap, 0, v59);
                HeapFree(gDhcpHeap, 0, v81);
                if ( v51 )
                  HeapFree(gDhcpHeap, 0, v51);
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
LABEL_82:
    v24 = v79;
    goto LABEL_83;
  }
  IfPrintable = 534;
  v35 = 0;
LABEL_85:
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
0x180003ce8  push    rbp
0x180003cea  push    rbx
0x180003ceb  push    rsi
0x180003cec  push    rdi
0x180003ced  push    r12
0x180003cef  push    r13
0x180003cf1  push    r14
0x180003cf3  push    r15
0x180003cf5  lea     rbp, [rsp-278h]
0x180003cfd  sub     rsp, 378h
0x180003d04  mov     rax, cs:__security_cookie
0x180003d0b  xor     rax, rsp
0x180003d0e  mov     [rbp+2B0h+var_50], rax
0x180003d15  mov     rax, [rbp+2B0h+arg_50]
0x180003d1c  mov     esi, r8d
0x180003d1f  mov     r14, [rbp+2B0h+arg_28]
0x180003d26  mov     rdi, rdx
0x180003d29  mov     [rbp+2B0h+var_2F0], rax
0x180003d2d  mov     rax, [rbp+2B0h+arg_70]
0x180003d34  mov     [rbp+2B0h+lpMultiByteStr], rax
0x180003d38  mov     rax, [rbp+2B0h+arg_80]
0x180003d3f  mov     [rbp+2B0h+var_2D8], rax
0x180003d43  mov     rax, [rbp+2B0h+arg_90]
0x180003d4a  mov     [rbp+2B0h+var_2FC], ecx
0x180003d4d  mov     rcx, [rbp+2B0h+arg_68]
0x180003d54  mov     [rbp+2B0h+var_2D0], rax
0x180003d58  xor     eax, eax
0x180003d5a  cmp     cs:DhcpGlobalAuditLogFlag, eax
0x180003d60  mov     r13d, eax
0x180003d63  mov     [rbp+2B0h+SourceString], rcx
0x180003d67  mov     r12d, eax
0x180003d6a  mov     qword ptr [rbp+2B0h+LocalFileTime.dwLowDateTime], r9
0x180003d6e  lea     ecx, [rax+1]
0x180003d71  mov     [rbp+2B0h+NumberOfBytesWritten], eax
0x180003d74  mov     [rbp+2B0h+var_318], ecx
0x180003d77  mov     [rbp+2B0h+var_330], rax
0x180003d7b  mov     [rbp+2B0h+lpMem], rax
0x180003d7f  mov     [rbp+2B0h+var_300], eax
0x180003d82  jz      short loc_180003DBD
0x180003d84  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180003d88  cmp     cs:AuditLogHandle, rbx
0x180003d8f  jnz     short loc_180003DE3
0x180003d91  mov     rcx, cs:WPP_GLOBAL_Control
0x180003d98  lea     rax, WPP_GLOBAL_Control
0x180003d9f  cmp     rcx, rax
0x180003da2  jz      short loc_180003DBD
0x180003da4  test    byte ptr [rcx+1Ch], 10h
0x180003da8  jz      short loc_180003DBD
0x180003daa  mov     rcx, [rcx+10h]
0x180003dae  lea     edx, [rbx+18h]
0x180003db1  lea     r8, WPP_3f918084cf8d369c2c20a8a49a789173_Traceguids
0x180003db8  call    WPP_SF_
0x180003dbd  xor     eax, eax
0x180003dbf  mov     rcx, [rbp+2B0h+var_50]
0x180003dc6  xor     rcx, rsp; StackCookie
0x180003dc9  call    __security_check_cookie
0x180003dce  add     rsp, 378h
0x180003dd5  pop     r15
0x180003dd7  pop     r14
0x180003dd9  pop     r13
0x180003ddb  pop     r12
0x180003ddd  pop     rdi
0x180003dde  pop     rsi
0x180003ddf  pop     rbx
0x180003de0  pop     rbp
0x180003de1  retn
0x180003de3  lea     rcx, [rbp+2B0h+var_280]
0x180003de7  call    GetUserAndDomainName
0x180003dec  xor     ecx, ecx
0x180003dee  test    eax, eax
0x180003df0  jz      short loc_180003DF6
0x180003df2  mov     [rbp+2B0h+var_280], cx
0x180003df6  lea     rcx, [rbp+2B0h+Buffer]; Buffer
0x180003dfa  call    cs:__imp__wstrdate
0x180003e01  nop     dword ptr [rax+rax+00h]
0x180003e06  lea     rcx, [rbp+2B0h+var_2B8]; Buffer
0x180003e0a  call    cs:__imp__wstrtime
0x180003e11  nop     dword ptr [rax+rax+00h]
0x180003e16  xor     r9d, r9d
0x180003e19  lea     r15, Annotation
0x180003e20  test    rdi, rdi
0x180003e23  cmovnz  r15, rdi
0x180003e27  mov     qword ptr [rbp+2B0h+SystemTime.wYear], r15
0x180003e2b  test    r14, r14
0x180003e2e  jnz     short loc_180003E39
0x180003e30  lea     r14, Annotation
0x180003e37  jmp     short loc_180003E6A
0x180003e39  mov     rdx, rbx
0x180003e3c  inc     rdx
0x180003e3f  cmp     [r14+rdx*2], r9w
0x180003e44  jnz     short loc_180003E3C
0x180003e46  inc     edx
0x180003e48  lea     r9, [rbp+2B0h+var_300]
0x180003e4c  lea     r8, [rbp+2B0h+lpMem]
0x180003e50  mov     rcx, r14
0x180003e53  call    ConvertUnicodeToWideCharPunycode
0x180003e58  xor     r9d, r9d
0x180003e5b  test    eax, eax
0x180003e5d  jnz     short loc_180003E6A
0x180003e5f  mov     rax, [rbp+2B0h+lpMem]
0x180003e63  test    rax, rax
0x180003e66  cmovnz  r14, rax
0x180003e6a  test    esi, esi
0x180003e6c  jnz     short loc_180003E77
0x180003e6e  lea     rdi, SourceString
0x180003e75  jmp     short loc_180003E8F
0x180003e77  mov     ecx, esi
0x180003e79  call    DhcpIpAddressToDottedString
0x180003e7e  xor     r9d, r9d
0x180003e81  lea     rdi, SourceString
0x180003e88  test    rax, rax
0x180003e8b  cmovnz  rdi, rax
0x180003e8f  mov     edx, 10h
0x180003e94  mov     rax, rdi
0x180003e97  lea     ecx, [rdx-0Fh]
0x180003e9a  cmp     [rax], r9b
0x180003e9d  jz      short loc_180003EA7
0x180003e9f  add     rax, rcx
0x180003ea2  sub     rdx, rcx
0x180003ea5  jnz     short loc_180003E9A
0x180003ea7  mov     ecx, 10h
0x180003eac  mov     rax, rdx
0x180003eaf  sub     rcx, rdx
0x180003eb2  neg     rax
0x180003eb5  sbb     r8, r8
0x180003eb8  and     r8, rcx
0x180003ebb  test    rdx, rdx
0x180003ebe  jnz     short loc_180003EC8
0x180003ec0  lea     eax, [rdx+57h]
0x180003ec3  jmp     loc_180003DBF
0x180003ec8  lea     rax, [r8+1]
0x180003ecc  cmp     rax, r8
0x180003ecf  jb      loc_180004882
0x180003ed5  movzx   r8d, ax
0x180003ed9  xor     edx, edx
0x180003edb  mov     rcx, rdi; SourceString
0x180003ede  call    DhcpOemToUnicodeN
0x180003ee3  mov     r13, rax
0x180003ee6  mov     [rbp+2B0h+var_320], rax
0x180003eea  xor     eax, eax
0x180003eec  test    r13, r13
0x180003eef  jnz     short loc_180003EFE
0x180003ef1  lea     ebx, [rax+8]
0x180003ef4  mov     edi, eax
0x180003ef6  xor     r15d, r15d
0x180003ef9  jmp     loc_180004409
0x180003efe  lea     rcx, [rbp+2B0h+var_280]
0x180003f02  mov     rsi, rbx
0x180003f05  inc     rsi
0x180003f08  cmp     [rcx+rsi*2], ax
0x180003f0c  jnz     short loc_180003F05
0x180003f0e  lea     rcx, [rbp+2B0h+Buffer]
0x180003f12  mov     r11, rbx
0x180003f15  inc     r11
0x180003f18  cmp     [rcx+r11*2], ax
0x180003f1d  jnz     short loc_180003F15
0x180003f1f  lea     rcx, [rbp+2B0h+var_2B8]
0x180003f23  mov     r10, rbx
0x180003f26  inc     r10
0x180003f29  cmp     [rcx+r10*2], ax
0x180003f2e  jnz     short loc_180003F26
0x180003f30  mov     r9, rbx
0x180003f33  inc     r9
0x180003f36  cmp     [rdi+r9], al
0x180003f3a  jnz     short loc_180003F33
0x180003f3c  mov     r8, rbx
0x180003f3f  inc     r8
0x180003f42  cmp     [r15+r8*2], ax
0x180003f47  jnz     short loc_180003F3F
0x180003f49  inc     rbx
0x180003f4c  cmp     [r14+rbx*2], ax
0x180003f51  jnz     short loc_180003F49
0x180003f53  mov     eax, [rbp+2B0h+arg_58]
0x180003f59  mov     r15d, [rbp+2B0h+arg_20]
0x180003f60  mov     r13d, [rbp+2B0h+cbMultiByte]
0x180003f67  lea     ecx, ds:63h[rax*2]
0x180003f6e  add     rcx, r10
0x180003f71  lea     edx, [r15+r15]
0x180003f75  add     rcx, rdx
0x180003f78  add     rcx, r11
0x180003f7b  add     rcx, rsi
0x180003f7e  add     rcx, r8
0x180003f81  add     rcx, rbx
0x180003f84  add     rcx, r9
0x180003f87  mov     r9d, 1
0x180003f8d  test    r13d, r13d
0x180003f90  jz      short loc_180003F9C
0x180003f92  lea     eax, ds:1[r13*4]
0x180003f9a  jmp     short loc_180003F9F
0x180003f9c  mov     eax, r9d
0x180003f9f  mov     r12d, [rbp+2B0h+arg_88]
0x180003fa6  add     rcx, rax
0x180003fa9  lea     eax, ds:1[r12*4]
0x180003fb1  test    r12d, r12d
0x180003fb4  jnz     short loc_180003FB9
0x180003fb6  mov     eax, r9d
0x180003fb9  mov     edx, eax
0x180003fbb  mov     eax, [rbp+2B0h+arg_98]
0x180003fc1  add     rdx, rcx
0x180003fc4  test    eax, eax
0x180003fc6  jz      short loc_180003FD1
0x180003fc8  lea     eax, ds:1[rax*2]
0x180003fcf  jmp     short loc_180003FD4
0x180003fd1  mov     eax, r9d
0x180003fd4  mov     rcx, cs:gDhcpHeap; hHeap
0x180003fdb  add     rax, rdx
0x180003fde  mov     ebx, 8
0x180003fe3  mov     edx, ebx; dwFlags
0x180003fe5  lea     rsi, ds:2B8h[rax*2]
0x180003fed  mov     r8, rsi; dwBytes
0x180003ff0  call    cs:__imp_HeapAlloc
0x180003ff7  nop     dword ptr [rax+rax+00h]
0x180003ffc  xor     ecx, ecx
0x180003ffe  mov     [rbp+2B0h+var_328], rax
0x180004002  mov     rdi, rax
0x180004005  test    rax, rax
0x180004008  jnz     short loc_180004015
0x18000400a  mov     r12d, ecx
0x18000400d  xor     r15d, r15d
0x180004010  jmp     loc_180004405
0x180004015  mov     rax, [rbp+2B0h+var_320]
0x180004019  lea     r9, [rsp+3B0h+pcbRemaining]; pcbRemaining
0x18000401e  mov     [rsp+3B0h+var_358], r14
0x180004023  lea     r8, [rsp+3B0h+ppszDestEnd]; ppszDestEnd
0x180004028  mov     [rsp+3B0h+var_360], rax
0x18000402d  mov     rdx, rsi; cbDest
0x180004030  mov     rax, qword ptr [rbp+2B0h+SystemTime.wYear]
0x180004034  mov     rcx, rdi; pszDest
0x180004037  mov     [rsp+3B0h+var_368], rax
0x18000403c  lea     rax, [rbp+2B0h+var_2B8]
0x180004040  mov     [rsp+3B0h+var_370], rax
0x180004045  lea     rax, [rbp+2B0h+Buffer]
0x180004049  mov     [rsp+3B0h+var_378], rax
0x18000404e  mov     eax, [rbp+2B0h+var_2FC]
0x180004051  mov     dword ptr [rsp+3B0h+var_380], eax
0x180004055  lea     rax, a2dSSSSS; "%.2d,%s,%s,%s,%s,%s,"
0x18000405c  mov     [rsp+3B0h+pszFormat], rax; pszFormat
0x180004061  mov     [rsp+3B0h+dwFlags], 1000h; dwFlags
0x180004069  mov     [rsp+3B0h+ppszDestEnd], rdi
0x18000406e  mov     [rsp+3B0h+pcbRemaining], rsi
0x180004073  call    StringCbPrintfExW
0x180004078  xor     r14d, r14d
0x18000407b  test    eax, eax
0x18000407d  jns     short loc_180004088
0x18000407f  lea     ebx, [r14+0Dh]
0x180004083  mov     r12d, r14d
0x180004086  jmp     short loc_18000400D
0x180004088  lea     r8, a2x; "%.2X"
0x18000408f  mov     edi, r14d
0x180004092  test    r15d, r15d
0x180004095  jz      short loc_1800040E1
0x180004097  mov     rcx, qword ptr [rbp+2B0h+LocalFileTime.dwLowDateTime]
0x18000409b  lea     r9, [rsp+3B0h+pcbRemaining]; pcbRemaining
0x1800040a0  mov     rdx, [rsp+3B0h+pcbRemaining]; cbDest
0x1800040a5  movzx   eax, byte ptr [rcx]
0x1800040a8  inc     rcx
0x1800040ab  mov     dword ptr [rsp+3B0h+var_380], eax
0x1800040af  mov     [rsp+3B0h+pszFormat], r8; pszFormat
0x1800040b4  lea     r8, [rsp+3B0h+ppszDestEnd]; ppszDestEnd
0x1800040b9  mov     qword ptr [rbp+2B0h+LocalFileTime.dwLowDateTime], rcx
0x1800040bd  mov     rcx, [rsp+3B0h+ppszDestEnd]; pszDest
0x1800040c2  mov     [rsp+3B0h+dwFlags], 1000h; dwFlags
0x1800040ca  call    StringCbPrintfExW
0x1800040cf  test    eax, eax
0x1800040d1  js      short loc_18000412C
0x1800040d3  inc     edi
0x1800040d5  lea     r8, a2x; "%.2X"
0x1800040dc  cmp     edi, r15d
0x1800040df  jb      short loc_180004097
0x1800040e1  mov     rdx, [rsp+3B0h+pcbRemaining]; cbDest
0x1800040e6  lea     rax, [rbp+2B0h+var_280]
0x1800040ea  mov     rcx, [rsp+3B0h+ppszDestEnd]; pszDest
0x1800040ef  lea     r9, [rsp+3B0h+pcbRemaining]; pcbRemaining
0x1800040f4  mov     [rsp+3B0h+var_380], rax
0x1800040f9  lea     r8, [rsp+3B0h+ppszDestEnd]; ppszDestEnd
0x1800040fe  lea     rax, aS_1; ",%s,"
0x180004105  mov     edi, 1000h
0x18000410a  mov     [rsp+3B0h+pszFormat], rax; pszFormat
0x18000410f  mov     [rsp+3B0h+dwFlags], edi; dwFlags
0x180004113  call    StringCbPrintfExW
0x180004118  xor     r15d, r15d
0x18000411b  test    eax, eax
0x18000411d  jns     short loc_18000413C
0x18000411f  mov     ebx, 0Dh
0x180004124  mov     r12, r14
0x180004127  jmp     loc_180004401
0x18000412c  mov     ebx, 0Dh
0x180004131  mov     r12, r14
0x180004134  xor     r15d, r15d
0x180004137  jmp     loc_180004401
0x18000413c  mov     eax, [rbp+2B0h+arg_38]
0x180004142  lea     r9, [rsp+3B0h+pcbRemaining]; pcbRemaining
0x180004147  mov     rdx, [rsp+3B0h+pcbRemaining]; cbDest
0x18000414c  lea     r8, [rsp+3B0h+ppszDestEnd]; ppszDestEnd
0x180004151  mov     rcx, [rsp+3B0h+ppszDestEnd]; pszDest
0x180004156  mov     dword ptr [rsp+3B0h+var_380], eax
0x18000415a  lea     rax, aLu; "%lu,"
0x180004161  mov     [rsp+3B0h+pszFormat], rax; pszFormat
0x180004166  mov     [rsp+3B0h+dwFlags], edi; dwFlags
0x18000416a  call    StringCbPrintfExW
  ... truncated ...
```
