# AddFileEntry(STRA &,_WIN32_FIND_DATAW *,ulong,STRA &,ushort const *,STRA *)

- ea: `0x18000243c`
- end: `0x180002938`
- name: `?AddFileEntry@@YAJAEAVSTRA@@PEAU_WIN32_FIND_DATAW@@K0PEBGPEAV1@@Z`
- size: `1276`
- prototype: `signed int __fastcall(struct STRA *, struct _WIN32_FIND_DATAW *, char, struct STRA *, LPCWSTR lpLocaleName, struct STRA *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180002968`

## callees

- `0x18000243c`
- `0x18000377c`
- `0x180003a40`

## import_xrefs

- `msvcrt!_i64toa_s` at `0x18000278a`
- `msvcrt!_i64toa_s` at `0x18000278a`
- `api-ms-win-core-file-l1-1-0!FileTimeToLocalFileTime` at `0x1800024cb`
- `api-ms-win-core-file-l1-1-0!FileTimeToLocalFileTime` at `0x1800024cb`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x1800024e2`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x1800024e2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800026a6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800026a6`
- `api-ms-win-core-datetime-l1-1-1!GetDateFormatEx` at `0x18000252e`
- `api-ms-win-core-datetime-l1-1-1!GetDateFormatEx` at `0x18000252e`
- `api-ms-win-core-datetime-l1-1-1!GetTimeFormatEx` at `0x180002606`
- `api-ms-win-core-datetime-l1-1-1!GetTimeFormatEx` at `0x180002606`
- `iisutil!??1STRA@@QEAA@XZ` at `0x1800025d1`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18000269e`
- `iisutil!??1STRA@@QEAA@XZ` at `0x1800027a3`
- `iisutil!??1STRA@@QEAA@XZ` at `0x1800028f8`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180002906`
- `iisutil!??1STRA@@QEAA@XZ` at `0x1800025d1`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18000269e`
- `iisutil!??1STRA@@QEAA@XZ` at `0x1800027a3`
- `iisutil!??1STRA@@QEAA@XZ` at `0x1800028f8`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180002906`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x18000254b`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180002623`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x1800026ed`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x1800027b7`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x18000254b`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180002623`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x1800026ed`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x1800027b7`
- `iisutil!?CopyWToUTF8Unescaped@STRA@@QEAAJPEBGK@Z` at `0x18000256b`
- `iisutil!?CopyWToUTF8Unescaped@STRA@@QEAAJPEBGK@Z` at `0x180002643`
- `iisutil!?CopyWToUTF8Unescaped@STRA@@QEAAJPEBGK@Z` at `0x180002882`
- `iisutil!?CopyWToUTF8Unescaped@STRA@@QEAAJPEBGK@Z` at `0x18000256b`
- `iisutil!?CopyWToUTF8Unescaped@STRA@@QEAAJPEBGK@Z` at `0x180002643`
- `iisutil!?CopyWToUTF8Unescaped@STRA@@QEAAJPEBGK@Z` at `0x180002882`
- `iisutil!?Append@STRA@@QEAAJAEBV1@@Z` at `0x1800025bc`
- `iisutil!?Append@STRA@@QEAAJAEBV1@@Z` at `0x180002689`
- `iisutil!?Append@STRA@@QEAAJAEBV1@@Z` at `0x18000271d`
- `iisutil!?Append@STRA@@QEAAJAEBV1@@Z` at `0x1800027df`
- `iisutil!?Append@STRA@@QEAAJAEBV1@@Z` at `0x180002822`
- `iisutil!?Append@STRA@@QEAAJAEBV1@@Z` at `0x1800028d2`
- `iisutil!?Append@STRA@@QEAAJAEBV1@@Z` at `0x1800025bc`
- `iisutil!?Append@STRA@@QEAAJAEBV1@@Z` at `0x180002689`
- `iisutil!?Append@STRA@@QEAAJAEBV1@@Z` at `0x18000271d`
- `iisutil!?Append@STRA@@QEAAJAEBV1@@Z` at `0x1800027df`
- `iisutil!?Append@STRA@@QEAAJAEBV1@@Z` at `0x180002822`
- `iisutil!?Append@STRA@@QEAAJAEBV1@@Z` at `0x1800028d2`
- `iisutil!?Copy@STRA@@QEAAJPEBD@Z` at `0x180002705`
- `iisutil!?Copy@STRA@@QEAAJPEBD@Z` at `0x180002705`
- `iisutil!?Append@STRA@@QEAAJPEBD@Z` at `0x180002739`
- `iisutil!?Append@STRA@@QEAAJPEBD@Z` at `0x180002762`
- `iisutil!?Append@STRA@@QEAAJPEBD@Z` at `0x1800027c7`
- `iisutil!?Append@STRA@@QEAAJPEBD@Z` at `0x180002842`
- `iisutil!?Append@STRA@@QEAAJPEBD@Z` at `0x18000285c`
- `iisutil!?Append@STRA@@QEAAJPEBD@Z` at `0x1800028e8`
- `iisutil!?Append@STRA@@QEAAJPEBD@Z` at `0x180002739`
- `iisutil!?Append@STRA@@QEAAJPEBD@Z` at `0x180002762`
- `iisutil!?Append@STRA@@QEAAJPEBD@Z` at `0x1800027c7`
- `iisutil!?Append@STRA@@QEAAJPEBD@Z` at `0x180002842`
- `iisutil!?Append@STRA@@QEAAJPEBD@Z` at `0x18000285c`
- `iisutil!?Append@STRA@@QEAAJPEBD@Z` at `0x1800028e8`
- `iisutil!?CopyWToUTF8Escaped@STRA@@QEAAJPEBG@Z` at `0x1800027f7`
- `iisutil!?CopyWToUTF8Escaped@STRA@@QEAAJPEBG@Z` at `0x1800027f7`
- `iisutil!?HTMLEncode@STRA@@QEAAJXZ` at `0x18000280b`
- `iisutil!?HTMLEncode@STRA@@QEAAJXZ` at `0x180002892`
- `iisutil!?HTMLEncode@STRA@@QEAAJXZ` at `0x18000280b`
- `iisutil!?HTMLEncode@STRA@@QEAAJXZ` at `0x180002892`

## pseudocode

```c
signed int __fastcall AddFileEntry(
        struct STRA *a1,
        struct _WIN32_FIND_DATAW *a2,
        char a3,
        struct STRA *a4,
        LPCWSTR lpLocaleName,
        struct STRA *a6)
{
  FILETIME ftLastWriteTime; // rax
  __int64 v7; // r14
  const struct STRA *v8; // rsi
  __int64 v11; // r8
  int v12; // ebx
  STRA *v13; // rcx
  __int64 v14; // rcx
  int v15; // eax
  __int64 v16; // r8
  __int64 v17; // rcx
  int v18; // eax
  signed int result; // eax
  int v20; // ebx
  int v21; // eax
  __int64 v22; // rcx
  struct _FILETIME LocalFileTime; // [rsp+40h] [rbp-C0h] BYREF
  FILETIME FileTime; // [rsp+48h] [rbp-B8h] BYREF
  const struct STRA *v25; // [rsp+50h] [rbp-B0h]
  _BYTE v26[32]; // [rsp+58h] [rbp-A8h] BYREF
  char *Buffer; // [rsp+78h] [rbp-88h]
  size_t BufferCount; // [rsp+80h] [rbp-80h]
  int v29; // [rsp+88h] [rbp-78h]
  _BYTE v30[32]; // [rsp+90h] [rbp-70h] BYREF
  __int64 v31; // [rsp+B0h] [rbp-50h]
  unsigned int v32; // [rsp+B8h] [rbp-48h]
  int v33; // [rsp+C0h] [rbp-40h]
  _SYSTEMTIME SystemTime; // [rsp+C8h] [rbp-38h] BYREF
  struct STRA *v35; // [rsp+D8h] [rbp-28h] BYREF
  WCHAR TimeStr[28]; // [rsp+E8h] [rbp-18h] BYREF
  char v37[16]; // [rsp+120h] [rbp+20h] BYREF
  WCHAR DateStr[64]; // [rsp+130h] [rbp+30h] BYREF

  ftLastWriteTime = a2->ftLastWriteTime;
  v7 = -1;
  v8 = a4;
  v35 = a4;
  v25 = a1;
  FileTime = ftLastWriteTime;
  if ( (a3 & 6) == 0 || !*(_QWORD *)&ftLastWriteTime )
    goto LABEL_30;
  LocalFileTime = 0;
  SystemTime = 0;
  if ( FileTimeToLocalFileTime(&FileTime, &LocalFileTime) && FileTimeToSystemTime(&LocalFileTime, &SystemTime) )
  {
    if ( (a3 & 2) != 0 )
    {
      if ( !GetDateFormatEx(lpLocaleName, (((a3 & 0x20) != 0) + 1) | 0x80000000, &SystemTime, 0, DateStr, 50, 0) )
        goto LABEL_28;
      STRA::STRA((STRA *)v26, (char *)TimeStr, 0x32u);
      v11 = -1;
      do
        ++v11;
      while ( DateStr[v11] );
      v12 = STRA::CopyWToUTF8Unescaped((STRA *)v26, DateStr, v11);
      if ( v12 < 0 )
        goto LABEL_10;
      PadDirField(Buffer, (a3 & 0x20) != 0 ? 29 : 10);
      v14 = -1;
      do
        ++v14;
      while ( Buffer[v14] );
      if ( (unsigned int)v14 < (unsigned int)BufferCount )
      {
        Buffer[(unsigned int)v14] = 0;
        v29 = v14;
      }
      v15 = STRA::Append(a6, (const struct STRA *)v26);
      v13 = (STRA *)v26;
      v12 = v15;
      if ( v15 < 0 )
        goto LABEL_63;
      STRA::~STRA((STRA *)v26);
      v8 = v35;
    }
    if ( (a3 & 4) == 0 )
      goto LABEL_30;
    if ( GetTimeFormatEx(lpLocaleName, 0x80000002, &SystemTime, 0, TimeStr, 15) )
    {
      STRA::STRA((STRA *)v26, (char *)&v35, 0xFu);
      v16 = -1;
      do
        ++v16;
      while ( TimeStr[v16] );
      v12 = STRA::CopyWToUTF8Unescaped((STRA *)v26, TimeStr, v16);
      if ( v12 < 0 )
        goto LABEL_10;
      PadDirField(Buffer, 8);
      v17 = -1;
      do
        ++v17;
      while ( Buffer[v17] );
      if ( (unsigned int)v17 < (unsigned int)BufferCount )
      {
        Buffer[(unsigned int)v17] = 0;
        v29 = v17;
      }
      v18 = STRA::Append(a6, (const struct STRA *)v26);
      v13 = (STRA *)v26;
      v12 = v18;
      if ( v18 < 0 )
        goto LABEL_63;
      STRA::~STRA((STRA *)v26);
LABEL_30:
      LocalFileTime.dwHighDateTime = a2->nFileSizeHigh;
      LocalFileTime.dwLowDateTime = a2->nFileSizeLow;
      if ( (a3 & 8) != 0 )
      {
        STRA::STRA((STRA *)v26, (char *)DateStr, 0x80u);
        if ( (a2->dwFileAttributes & 0x10) != 0 )
        {
          v12 = STRA::Copy((STRA *)v26, "&lt;");
          if ( v12 < 0 )
            goto LABEL_10;
          v12 = STRA::Append((STRA *)v26, v8);
          if ( v12 < 0 )
            goto LABEL_10;
          v12 = STRA::Append((STRA *)v26, "&gt;");
          if ( v12 < 0 )
            goto LABEL_10;
          v20 = 18;
        }
        else
        {
          v20 = 12;
          if ( _i64toa_s(*(_QWORD *)&LocalFileTime, Buffer, (unsigned int)BufferCount, 10) )
          {
            v12 = -2147418113;
            goto LABEL_10;
          }
        }
        PadDirField(Buffer, v20);
        v21 = STRA::Append(a6, Buffer);
        if ( v21 < 0 )
        {
          v12 = v21;
LABEL_10:
          v13 = (STRA *)v26;
LABEL_63:
          STRA::~STRA(v13);
          return v12;
        }
        STRA::~STRA((STRA *)v26);
      }
      STRA::STRA((STRA *)v30, v37, 0x10u);
      v12 = STRA::Append(a6, "<A HREF=\"");
      if ( v12 >= 0 )
      {
        v12 = STRA::Append(a6, v25);
        if ( v12 >= 0 )
        {
          v12 = STRA::CopyWToUTF8Escaped((STRA *)v30, a2->cFileName);
          if ( v12 >= 0 )
          {
            v12 = STRA::HTMLEncode((STRA *)v30);
            if ( v12 >= 0 )
            {
              v12 = STRA::Append(a6, (const struct STRA *)v30);
              if ( v12 >= 0 )
              {
                if ( (a2->dwFileAttributes & 0x10) == 0 || (v12 = STRA::Append(a6, "/"), v12 >= 0) )
                {
                  v12 = STRA::Append(a6, "\">");
                  if ( v12 >= 0 )
                  {
                    do
                      ++v7;
                    while ( a2->cFileName[v7] );
                    v12 = STRA::CopyWToUTF8Unescaped((STRA *)v30, a2->cFileName, v7);
                    if ( v12 >= 0 )
                    {
                      v12 = STRA::HTMLEncode((STRA *)v30);
                      if ( v12 >= 0 )
                      {
                        if ( (a3 & 0x10) == 0 )
                        {
                          v22 = (unsigned int)(v33 - 1);
                          if ( v33 - 1 > 0 )
                          {
                            while ( *(_BYTE *)(v22 + v31) != 46 )
                            {
                              v22 = (unsigned int)(v22 - 1);
                              if ( (int)v22 <= 0 )
                                goto LABEL_59;
                            }
                            if ( (unsigned int)v22 < v32 )
                            {
                              *(_BYTE *)(v22 + v31) = 0;
                              v33 = v22;
                            }
                          }
                        }
LABEL_59:
                        v12 = STRA::Append(a6, (const struct STRA *)v30);
                        if ( v12 >= 0 )
                        {
                          v12 = STRA::Append(a6, "</A><br>");
                          if ( v12 >= 0 )
                          {
                            STRA::~STRA((STRA *)v30);
                            return 0;
                          }
                        }
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
      v13 = (STRA *)v30;
      goto LABEL_63;
    }
  }
LABEL_28:
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x18000243c  mov     [rsp-8+arg_10], rbx
0x180002441  push    rbp
0x180002442  push    rsi
0x180002443  push    rdi
0x180002444  push    r12
0x180002446  push    r13
0x180002448  push    r14
0x18000244a  push    r15
0x18000244c  lea     rbp, [rsp-0C0h]
0x180002454  sub     rsp, 1C0h
0x18000245b  mov     rax, cs:__security_cookie
0x180002462  xor     rax, rsp
0x180002465  mov     [rbp+0F0h+var_40], rax
0x18000246c  mov     rax, [rdx+14h]
0x180002470  xor     ebx, ebx
0x180002472  mov     r13, [rbp+0F0h+lpLocaleName]
0x180002479  or      r14, 0FFFFFFFFFFFFFFFFh
0x18000247d  mov     rdi, [rbp+0F0h+arg_28]
0x180002484  mov     rsi, r9
0x180002487  mov     [rbp+0F0h+var_118], r9
0x18000248b  mov     r12d, r8d
0x18000248e  mov     [rsp+1F0h+var_1A0], rcx
0x180002493  mov     r15, rdx
0x180002496  mov     qword ptr [rsp+1F0h+FileTime.dwLowDateTime], rax
0x18000249b  test    r8b, 6
0x18000249f  jz      loc_1800026C1
0x1800024a5  test    eax, eax
0x1800024a7  jnz     short loc_1800024B5
0x1800024a9  shr     rax, 20h
0x1800024ad  test    eax, eax
0x1800024af  jz      loc_1800026C1
0x1800024b5  xorps   xmm0, xmm0
0x1800024b8  mov     qword ptr [rsp+1F0h+LocalFileTime.dwLowDateTime], rbx
0x1800024bd  lea     rdx, [rsp+1F0h+LocalFileTime]; lpLocalFileTime
0x1800024c2  lea     rcx, [rsp+1F0h+FileTime]; lpFileTime
0x1800024c7  movups  xmmword ptr [rbp+0F0h+SystemTime.wYear], xmm0
0x1800024cb  call    cs:__imp_FileTimeToLocalFileTime
0x1800024d1  test    eax, eax
0x1800024d3  jz      loc_1800026A6
0x1800024d9  lea     rdx, [rbp+0F0h+SystemTime]; lpSystemTime
0x1800024dd  lea     rcx, [rsp+1F0h+LocalFileTime]; lpFileTime
0x1800024e2  call    cs:__imp_FileTimeToSystemTime
0x1800024e8  test    eax, eax
0x1800024ea  jz      loc_1800026A6
0x1800024f0  test    r12b, 2
0x1800024f4  jz      loc_1800025DB
0x1800024fa  mov     [rsp+1F0h+lpCalendar], rbx; lpCalendar
0x1800024ff  lea     r8, [rbp+0F0h+SystemTime]; lpDate
0x180002503  mov     esi, r12d
0x180002506  mov     [rsp+1F0h+cchDate], 32h ; '2'; cchDate
0x18000250e  and     esi, 20h
0x180002511  mov     rcx, r13; lpLocaleName
0x180002514  mov     eax, esi
0x180002516  neg     eax
0x180002518  lea     rax, [rbp+0F0h+DateStr]
0x18000251c  sbb     edx, edx
0x18000251e  mov     [rsp+1F0h+lpDateStr], rax; lpDateStr
0x180002523  neg     edx
0x180002525  xor     r9d, r9d; lpFormat
0x180002528  inc     edx
0x18000252a  bts     edx, 1Fh; dwFlags
0x18000252e  call    cs:__imp_GetDateFormatEx
0x180002534  test    eax, eax
0x180002536  jz      loc_1800026A6
0x18000253c  mov     r8d, 32h ; '2'
0x180002542  lea     rdx, [rbp+0F0h+TimeStr]
0x180002546  lea     rcx, [rsp+1F0h+var_198]
0x18000254b  call    cs:__imp_??0STRA@@QEAA@PEADK@Z; STRA::STRA(char *,ulong)
0x180002551  lea     rax, [rbp+0F0h+DateStr]
0x180002555  mov     r8, r14
0x180002558  inc     r8
0x18000255b  cmp     [rax+r8*2], bx
0x180002560  jnz     short loc_180002558
0x180002562  lea     rdx, [rbp+0F0h+DateStr]
0x180002566  lea     rcx, [rsp+1F0h+var_198]
0x18000256b  call    cs:__imp_?CopyWToUTF8Unescaped@STRA@@QEAAJPEBGK@Z; STRA::CopyWToUTF8Unescaped(ushort const *,ulong)
0x180002571  mov     ebx, eax
0x180002573  test    eax, eax
0x180002575  jns     short loc_180002581
0x180002577  lea     rcx, [rsp+1F0h+var_198]
0x18000257c  jmp     loc_180002906
0x180002581  mov     rcx, [rsp+1F0h+Buffer]; char *
0x180002586  neg     esi
0x180002588  sbb     edx, edx
0x18000258a  and     edx, 13h
0x18000258d  add     edx, 0Ah; int
0x180002590  call    ?PadDirField@@YAXPEADH@Z; PadDirField(char *,int)
0x180002595  mov     rdx, [rsp+1F0h+Buffer]
0x18000259a  mov     rcx, r14
0x18000259d  inc     rcx
0x1800025a0  cmp     byte ptr [rdx+rcx], 0
0x1800025a4  jnz     short loc_18000259D
0x1800025a6  cmp     ecx, dword ptr [rbp+0F0h+BufferCount]
0x1800025a9  jnb     short loc_1800025B4
0x1800025ab  mov     eax, ecx
0x1800025ad  mov     byte ptr [rax+rdx], 0
0x1800025b1  mov     [rbp+0F0h+var_168], ecx
0x1800025b4  lea     rdx, [rsp+1F0h+var_198]
0x1800025b9  mov     rcx, rdi
0x1800025bc  call    cs:__imp_?Append@STRA@@QEAAJAEBV1@@Z; STRA::Append(STRA const &)
0x1800025c2  lea     rcx, [rsp+1F0h+var_198]
0x1800025c7  mov     ebx, eax
0x1800025c9  test    eax, eax
0x1800025cb  js      loc_180002906
0x1800025d1  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x1800025d7  mov     rsi, [rbp+0F0h+var_118]
0x1800025db  test    r12b, 4
0x1800025df  jz      loc_1800026C1
0x1800025e5  lea     rax, [rbp+0F0h+TimeStr]
0x1800025e9  mov     ebx, 0Fh
0x1800025ee  mov     [rsp+1F0h+cchDate], ebx; cchTime
0x1800025f2  lea     r8, [rbp+0F0h+SystemTime]; lpTime
0x1800025f6  xor     r9d, r9d; lpFormat
0x1800025f9  mov     [rsp+1F0h+lpDateStr], rax; lpTimeStr
0x1800025fe  mov     edx, 80000002h; dwFlags
0x180002603  mov     rcx, r13; lpLocaleName
0x180002606  call    cs:__imp_GetTimeFormatEx
0x18000260c  xor     r13d, r13d
0x18000260f  test    eax, eax
0x180002611  jz      loc_1800026A6
0x180002617  mov     r8d, ebx
0x18000261a  lea     rdx, [rbp+0F0h+var_118]
0x18000261e  lea     rcx, [rsp+1F0h+var_198]
0x180002623  call    cs:__imp_??0STRA@@QEAA@PEADK@Z; STRA::STRA(char *,ulong)
0x180002629  lea     rax, [rbp+0F0h+TimeStr]
0x18000262d  mov     r8, r14
0x180002630  inc     r8
0x180002633  cmp     [rax+r8*2], r13w
0x180002638  jnz     short loc_180002630
0x18000263a  lea     rdx, [rbp+0F0h+TimeStr]
0x18000263e  lea     rcx, [rsp+1F0h+var_198]
0x180002643  call    cs:__imp_?CopyWToUTF8Unescaped@STRA@@QEAAJPEBGK@Z; STRA::CopyWToUTF8Unescaped(ushort const *,ulong)
0x180002649  mov     ebx, eax
0x18000264b  test    eax, eax
0x18000264d  js      loc_180002577
0x180002653  mov     rcx, [rsp+1F0h+Buffer]; char *
0x180002658  mov     edx, 8; int
0x18000265d  call    ?PadDirField@@YAXPEADH@Z; PadDirField(char *,int)
0x180002662  mov     rdx, [rsp+1F0h+Buffer]
0x180002667  mov     rcx, r14
0x18000266a  inc     rcx
0x18000266d  cmp     [rdx+rcx], r13b
0x180002671  jnz     short loc_18000266A
0x180002673  cmp     ecx, dword ptr [rbp+0F0h+BufferCount]
0x180002676  jnb     short loc_180002681
0x180002678  mov     eax, ecx
0x18000267a  mov     [rax+rdx], r13b
0x18000267e  mov     [rbp+0F0h+var_168], ecx
0x180002681  lea     rdx, [rsp+1F0h+var_198]
0x180002686  mov     rcx, rdi
0x180002689  call    cs:__imp_?Append@STRA@@QEAAJAEBV1@@Z; STRA::Append(STRA const &)
0x18000268f  lea     rcx, [rsp+1F0h+var_198]
0x180002694  mov     ebx, eax
0x180002696  test    eax, eax
0x180002698  js      loc_180002906
0x18000269e  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x1800026a4  jmp     short loc_1800026C4
0x1800026a6  call    cs:__imp_GetLastError
0x1800026ac  test    eax, eax
0x1800026ae  jle     loc_18000290E
0x1800026b4  movzx   eax, ax
0x1800026b7  or      eax, 80070000h
0x1800026bc  jmp     loc_18000290E
0x1800026c1  xor     r13d, r13d
0x1800026c4  mov     eax, [r15+1Ch]
0x1800026c8  mov     [rsp+1F0h+LocalFileTime.dwHighDateTime], eax
0x1800026cc  mov     eax, [r15+20h]
0x1800026d0  mov     [rsp+1F0h+LocalFileTime.dwLowDateTime], eax
0x1800026d4  test    r12b, 8
0x1800026d8  jz      loc_1800027A9
0x1800026de  mov     r8d, 80h
0x1800026e4  lea     rdx, [rbp+0F0h+DateStr]
0x1800026e8  lea     rcx, [rsp+1F0h+var_198]
0x1800026ed  call    cs:__imp_??0STRA@@QEAA@PEADK@Z; STRA::STRA(char *,ulong)
0x1800026f3  test    byte ptr [r15], 10h
0x1800026f7  jz      short loc_180002773
0x1800026f9  lea     rdx, aLt; "&lt;"
0x180002700  lea     rcx, [rsp+1F0h+var_198]
0x180002705  call    cs:__imp_?Copy@STRA@@QEAAJPEBD@Z; STRA::Copy(char const *)
0x18000270b  mov     ebx, eax
0x18000270d  test    eax, eax
0x18000270f  js      loc_180002577
0x180002715  mov     rdx, rsi
0x180002718  lea     rcx, [rsp+1F0h+var_198]
0x18000271d  call    cs:__imp_?Append@STRA@@QEAAJAEBV1@@Z; STRA::Append(STRA const &)
0x180002723  mov     ebx, eax
0x180002725  test    eax, eax
0x180002727  js      loc_180002577
0x18000272d  lea     rdx, aGt; "&gt;"
0x180002734  lea     rcx, [rsp+1F0h+var_198]
0x180002739  call    cs:__imp_?Append@STRA@@QEAAJPEBD@Z; STRA::Append(char const *)
0x18000273f  mov     ebx, eax
0x180002741  test    eax, eax
0x180002743  js      loc_180002577
0x180002749  mov     ebx, 12h
0x18000274e  mov     rcx, [rsp+1F0h+Buffer]; char *
0x180002753  mov     edx, ebx; int
0x180002755  call    ?PadDirField@@YAXPEADH@Z; PadDirField(char *,int)
0x18000275a  mov     rdx, [rsp+1F0h+Buffer]
0x18000275f  mov     rcx, rdi
0x180002762  call    cs:__imp_?Append@STRA@@QEAAJPEBD@Z; STRA::Append(char const *)
0x180002768  test    eax, eax
0x18000276a  jns     short loc_18000279E
0x18000276c  mov     ebx, eax
0x18000276e  jmp     loc_180002577
0x180002773  mov     r8d, dword ptr [rbp+0F0h+BufferCount]; BufferCount
0x180002777  mov     ebx, 0Ch
0x18000277c  mov     rdx, [rsp+1F0h+Buffer]; Buffer
0x180002781  mov     rcx, qword ptr [rsp+1F0h+LocalFileTime.dwLowDateTime]; Value
0x180002786  lea     r9d, [rbx-2]; Radix
0x18000278a  call    cs:__imp__i64toa_s
0x180002790  test    eax, eax
0x180002792  jz      short loc_18000274E
0x180002794  mov     ebx, 8000FFFFh
0x180002799  jmp     loc_180002577
0x18000279e  lea     rcx, [rsp+1F0h+var_198]
0x1800027a3  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x1800027a9  mov     r8d, 10h
0x1800027af  lea     rdx, [rbp+0F0h+var_D0]
0x1800027b3  lea     rcx, [rbp+0F0h+var_160]
0x1800027b7  call    cs:__imp_??0STRA@@QEAA@PEADK@Z; STRA::STRA(char *,ulong)
0x1800027bd  lea     rdx, aAHref; "<A HREF=\""
0x1800027c4  mov     rcx, rdi
0x1800027c7  call    cs:__imp_?Append@STRA@@QEAAJPEBD@Z; STRA::Append(char const *)
0x1800027cd  mov     ebx, eax
0x1800027cf  test    eax, eax
0x1800027d1  js      loc_180002902
0x1800027d7  mov     rdx, [rsp+1F0h+var_1A0]
0x1800027dc  mov     rcx, rdi
0x1800027df  call    cs:__imp_?Append@STRA@@QEAAJAEBV1@@Z; STRA::Append(STRA const &)
0x1800027e5  mov     ebx, eax
0x1800027e7  test    eax, eax
0x1800027e9  js      loc_180002902
0x1800027ef  lea     rdx, [r15+2Ch]
0x1800027f3  lea     rcx, [rbp+0F0h+var_160]
0x1800027f7  call    cs:__imp_?CopyWToUTF8Escaped@STRA@@QEAAJPEBG@Z; STRA::CopyWToUTF8Escaped(ushort const *)
0x1800027fd  mov     ebx, eax
0x1800027ff  test    eax, eax
0x180002801  js      loc_180002902
0x180002807  lea     rcx, [rbp+0F0h+var_160]
0x18000280b  call    cs:__imp_?HTMLEncode@STRA@@QEAAJXZ; STRA::HTMLEncode(void)
0x180002811  mov     ebx, eax
0x180002813  test    eax, eax
0x180002815  js      loc_180002902
0x18000281b  lea     rdx, [rbp+0F0h+var_160]
0x18000281f  mov     rcx, rdi
0x180002822  call    cs:__imp_?Append@STRA@@QEAAJAEBV1@@Z; STRA::Append(STRA const &)
0x180002828  mov     ebx, eax
0x18000282a  test    eax, eax
0x18000282c  js      loc_180002902
0x180002832  test    byte ptr [r15], 10h
0x180002836  jz      short loc_180002852
0x180002838  lea     rdx, asc_180005C9C; "/"
0x18000283f  mov     rcx, rdi
0x180002842  call    cs:__imp_?Append@STRA@@QEAAJPEBD@Z; STRA::Append(char const *)
0x180002848  mov     ebx, eax
0x18000284a  test    eax, eax
0x18000284c  js      loc_180002902
0x180002852  lea     rdx, asc_180005CA0; "\">"
0x180002859  mov     rcx, rdi
0x18000285c  call    cs:__imp_?Append@STRA@@QEAAJPEBD@Z; STRA::Append(char const *)
0x180002862  mov     ebx, eax
0x180002864  test    eax, eax
0x180002866  js      loc_180002902
0x18000286c  inc     r14
0x18000286f  cmp     [r15+r14*2+2Ch], r13w
0x180002875  jnz     short loc_18000286C
0x180002877  mov     r8d, r14d
0x18000287a  lea     rdx, [r15+2Ch]
0x18000287e  lea     rcx, [rbp+0F0h+var_160]
0x180002882  call    cs:__imp_?CopyWToUTF8Unescaped@STRA@@QEAAJPEBGK@Z; STRA::CopyWToUTF8Unescaped(ushort const *,ulong)
0x180002888  mov     ebx, eax
0x18000288a  test    eax, eax
0x18000288c  js      short loc_180002902
0x18000288e  lea     rcx, [rbp+0F0h+var_160]
0x180002892  call    cs:__imp_?HTMLEncode@STRA@@QEAAJXZ; STRA::HTMLEncode(void)
0x180002898  mov     ebx, eax
0x18000289a  test    eax, eax
0x18000289c  js      short loc_180002902
0x18000289e  test    r12b, 10h
0x1800028a2  jnz     short loc_1800028CB
0x1800028a4  mov     ecx, [rbp+0F0h+var_130]
0x1800028a7  dec     ecx
0x1800028a9  test    ecx, ecx
0x1800028ab  jle     short loc_1800028CB
0x1800028ad  mov     rdx, [rbp+0F0h+var_140]
0x1800028b1  cmp     byte ptr [rcx+rdx], 2Eh ; '.'
0x1800028b5  jz      short loc_1800028BF
0x1800028b7  dec     ecx
0x1800028b9  test    ecx, ecx
0x1800028bb  jg      short loc_1800028B1
0x1800028bd  jmp     short loc_1800028CB
0x1800028bf  cmp     ecx, [rbp+0F0h+var_138]
0x1800028c2  jnb     short loc_1800028CB
0x1800028c4  mov     [rcx+rdx], r13b
0x1800028c8  mov     [rbp+0F0h+var_130], ecx
0x1800028cb  lea     rdx, [rbp+0F0h+var_160]
0x1800028cf  mov     rcx, rdi
0x1800028d2  call    cs:__imp_?Append@STRA@@QEAAJAEBV1@@Z; STRA::Append(STRA const &)
0x1800028d8  mov     ebx, eax
  ... truncated ...
```
