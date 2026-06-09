# W3_CONTEXT::SetupHttpRedirect(char const *,ulong,int,int)

- ea: `0x180024b80`
- end: `0x18002528b`
- name: `?SetupHttpRedirect@W3_CONTEXT@@QEAAJPEBDKHH@Z`
- size: `1803`
- prototype: `int(W3_CONTEXT *__hidden this, const char *, unsigned int, int, int)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x1800241c0`

## callees

- `0x180008280`
- `0x18000b810`
- `0x180015fd0`
- `0x180016b40`
- `0x180023100`
- `0x180024b80`
- `0x180025294`
- `0x180028f18`
- `0x18003773a`
- `0x180037790`
- `0x180038010`

## import_xrefs

- `msvcrt!_strnicmp` at `0x180024d5c`
- `msvcrt!_strnicmp` at `0x180024dc5`
- `msvcrt!_strnicmp` at `0x180024d5c`
- `msvcrt!_strnicmp` at `0x180024dc5`
- `msvcrt!strchr` at `0x180024e0c`
- `msvcrt!strchr` at `0x180024e23`
- `msvcrt!strchr` at `0x180024e0c`
- `msvcrt!strchr` at `0x180024e23`
- `api-ms-win-core-localization-l1-2-0!IdnToAscii` at `0x180024c6c`
- `api-ms-win-core-localization-l1-2-0!IdnToAscii` at `0x180024f00`
- `api-ms-win-core-localization-l1-2-0!IdnToAscii` at `0x180024c6c`
- `api-ms-win-core-localization-l1-2-0!IdnToAscii` at `0x180024f00`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180024d8e`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180024f3c`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180024d8e`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180024f3c`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x180024eca`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x180024eca`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180024edd`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180024edd`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180024d40`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180024d40`
- `iisutil!?GetString@LANG_STRING@@QEAAJPEBDKIPEAPEBGPEAK@Z` at `0x1800250e5`
- `iisutil!?GetString@LANG_STRING@@QEAAJPEBDKIPEAPEBGPEAK@Z` at `0x1800250e5`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180024bd0`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180024bef`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180024c30`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180024d12`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180024bd0`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180024bef`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180024c30`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180024d12`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180024cda`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180024cea`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180024cfb`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180024d9e`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180024f4c`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18002519a`
- `iisutil!??1STRA@@QEAA@XZ` at `0x1800251ab`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180025267`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180025278`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180024cda`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180024cea`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180024cfb`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180024d9e`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180024f4c`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18002519a`
- `iisutil!??1STRA@@QEAA@XZ` at `0x1800251ab`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180025267`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180025278`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x180024e9a`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x180025037`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x1800251e9`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x1800251fc`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x180024e9a`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x180025037`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x1800251e9`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x1800251fc`
- `iisutil!?Copy@STRA@@QEAAJPEBDK@Z` at `0x180024c92`
- `iisutil!?Copy@STRA@@QEAAJPEBDK@Z` at `0x180024f1f`
- `iisutil!?Copy@STRA@@QEAAJPEBDK@Z` at `0x180024f97`
- `iisutil!?Copy@STRA@@QEAAJPEBDK@Z` at `0x180024c92`
- `iisutil!?Copy@STRA@@QEAAJPEBDK@Z` at `0x180024f1f`
- `iisutil!?Copy@STRA@@QEAAJPEBDK@Z` at `0x180024f97`
- `iisutil!?Copy@STRA@@QEAAJPEBD@Z` at `0x180024d78`
- `iisutil!?Copy@STRA@@QEAAJPEBD@Z` at `0x180024de5`
- `iisutil!?Copy@STRA@@QEAAJPEBD@Z` at `0x180024e54`
- `iisutil!?Copy@STRA@@QEAAJPEBD@Z` at `0x180024d78`
- `iisutil!?Copy@STRA@@QEAAJPEBD@Z` at `0x180024de5`
- `iisutil!?Copy@STRA@@QEAAJPEBD@Z` at `0x180024e54`
- `iisutil!?CopyWToUTF8Unescaped@STRA@@QEAAJPEBG@Z` at `0x180025100`
- `iisutil!?CopyWToUTF8Unescaped@STRA@@QEAAJPEBG@Z` at `0x180025100`
- `iisutil!?QueryCCH@STRA@@QEBAKXZ` at `0x180024e88`
- `iisutil!?QueryCCH@STRA@@QEBAKXZ` at `0x180024f5d`
- `iisutil!?QueryCCH@STRA@@QEBAKXZ` at `0x180025024`
- `iisutil!?QueryCCH@STRA@@QEBAKXZ` at `0x180025116`
- `iisutil!?QueryCCH@STRA@@QEBAKXZ` at `0x180025129`
- `iisutil!?QueryCCH@STRA@@QEBAKXZ` at `0x180024e88`
- `iisutil!?QueryCCH@STRA@@QEBAKXZ` at `0x180024f5d`
- `iisutil!?QueryCCH@STRA@@QEBAKXZ` at `0x180025024`
- `iisutil!?QueryCCH@STRA@@QEBAKXZ` at `0x180025116`
- `iisutil!?QueryCCH@STRA@@QEBAKXZ` at `0x180025129`
- `iisutil!?Unescape@STRA@@QEAAJXZ` at `0x180024e6e`
- `iisutil!?Unescape@STRA@@QEAAJXZ` at `0x180024e6e`
- `iisutil!?CopyA@STRU@@QEAAJPEBDK@Z` at `0x180024eb0`
- `iisutil!?CopyA@STRU@@QEAAJPEBDK@Z` at `0x180024eb0`
- `iisutil!?AppendWTruncate@STRA@@QEAAJPEBG@Z` at `0x180024faf`
- `iisutil!?AppendWTruncate@STRA@@QEAAJPEBG@Z` at `0x180024faf`
- `iisutil!?Append@STRA@@QEAAJPEBD@Z` at `0x180024fd9`
- `iisutil!?Append@STRA@@QEAAJPEBD@Z` at `0x180024fd9`
- `iisutil!?HTMLEncode@STRA@@QEAAJXZ` at `0x18002508d`
- `iisutil!?HTMLEncode@STRA@@QEAAJXZ` at `0x18002508d`

## pseudocode

```c
__int64 __fastcall W3_CONTEXT::SetupHttpRedirect(W3_CONTEXT *this, const char *a2, unsigned int a3, int a4, int a5)
{
  __int64 v9; // rsi
  bool v10; // zf
  W3_METADATA *v11; // rcx
  const unsigned __int16 *v12; // rbx
  const WCHAR *AlternateHostName; // rax
  int v14; // eax
  WCHAR *v15; // rcx
  int v16; // edi
  struct _HTTP_DATA_CHUNK *v17; // rcx
  int appended; // ebx
  const char *v20; // rbx
  char *v21; // rdi
  char *v22; // rax
  int v23; // eax
  unsigned int CCH; // ebx
  const char *Str; // rax
  int v26; // ebx
  const WCHAR *v27; // rax
  int v28; // eax
  unsigned __int16 v29; // bx
  const char *v30; // rax
  const char *Header; // rax
  unsigned int v32; // ebx
  unsigned int v33; // r14d
  char *v34; // rdi
  char *v35; // rbx
  const char *v36; // rax
  __int64 v37; // rax
  unsigned __int16 v38[2]; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v39; // [rsp+44h] [rbp-BCh] BYREF
  const unsigned __int16 *v40; // [rsp+48h] [rbp-B8h] BYREF
  W3_REQUEST *v41; // [rsp+50h] [rbp-B0h]
  _BYTE v42[56]; // [rsp+58h] [rbp-A8h] BYREF
  struct _HTTP_DATA_CHUNK v43; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v44[56]; // [rsp+C8h] [rbp-38h] BYREF
  _BYTE v45[64]; // [rsp+100h] [rbp+0h] BYREF
  char v46[256]; // [rsp+140h] [rbp+40h] BYREF
  WCHAR ASCIICharStr[264]; // [rsp+240h] [rbp+140h] BYREF
  char v48[272]; // [rsp+450h] [rbp+350h] BYREF
  unsigned __int16 v49[256]; // [rsp+560h] [rbp+460h] BYREF
  char v50[512]; // [rsp+760h] [rbp+660h] BYREF

  STRA::STRA((STRA *)v42, v48, 0x104u);
  STRA::STRA((STRA *)v45, v50, 0x200u);
  v9 = *((_QWORD *)this + 8);
  v41 = (W3_REQUEST *)*((_QWORD *)this + 6);
  v10 = *a2 == 47;
  v38[0] = 0;
  v40 = 0;
  v39 = 0;
  if ( !v10 )
  {
    STRA::STRA((STRA *)&v43, v46, 0x100u);
    memset_0(v49, 0, sizeof(v49));
    STRU::STRU((STRU *)v44, v49, 0x100u);
    if ( !_strnicmp(a2, "http://", 7u) )
    {
      appended = STRA::Copy((STRA *)v42, "http://");
      if ( appended < 0 )
      {
LABEL_13:
        STRU::~STRU((STRU *)v44);
        STRA::~STRA((STRA *)&v43);
LABEL_50:
        STRA::~STRA((STRA *)v45);
        STRA::~STRA((STRA *)v42);
        return (unsigned int)appended;
      }
      v20 = a2 + 7;
    }
    else
    {
      if ( _strnicmp(a2, "https://", 8u) )
        goto LABEL_29;
      appended = STRA::Copy((STRA *)v42, "https://");
      if ( appended < 0 )
        goto LABEL_13;
      v20 = a2 + 8;
    }
    if ( !v20 )
      goto LABEL_29;
    v21 = strchr(v20, 47);
    v22 = strchr(v20, 58);
    if ( v21 )
    {
      if ( v22 && v22 < v21 )
        v21 = v22;
    }
    else
    {
      if ( !v22 )
      {
        v23 = STRA::Copy((STRA *)&v43, v20);
LABEL_25:
        appended = v23;
        if ( v23 < 0 )
          goto LABEL_13;
        appended = STRA::Unescape((STRA *)&v43);
        if ( appended < 0 )
          goto LABEL_13;
        CCH = STRA::QueryCCH((STRA *)&v43);
        Str = STRA::QueryStr((STRA *)&v43);
        appended = STRU::CopyA((STRU *)v44, Str, CCH);
        if ( appended < 0 )
          goto LABEL_13;
        v26 = STRU::QueryCCH((STRU *)v44) + 1;
        v27 = STRU::QueryStr((STRU *)v44);
        if ( IdnToAscii(0, v27, v26, ASCIICharStr, 260) )
        {
          appended = STRA::AppendWTruncate((STRA *)v42, ASCIICharStr);
          if ( appended < 0 )
            goto LABEL_13;
          if ( !v21 )
            goto LABEL_31;
          v28 = STRA::Append((STRA *)v42, v21);
LABEL_30:
          appended = v28;
          if ( v28 < 0 )
            goto LABEL_13;
LABEL_31:
          STRU::~STRU((STRU *)v44);
          v17 = &v43;
          goto LABEL_32;
        }
LABEL_29:
        v28 = STRA::Copy((STRA *)v42, a2, a3);
        goto LABEL_30;
      }
      v21 = v22;
    }
    v23 = STRA::Copy((STRA *)&v43, v20, (_DWORD)v21 - (_DWORD)v20);
    goto LABEL_25;
  }
  STRA::STRA((STRA *)v44, v46, 0x100u);
  v11 = (W3_METADATA *)*((_QWORD *)this + 1114);
  v12 = 0;
  if ( v11 )
  {
    AlternateHostName = W3_METADATA::QueryAlternateHostName(v11);
    v12 = AlternateHostName;
    if ( AlternateHostName )
    {
      v14 = IdnToAscii(0, AlternateHostName, -1, ASCIICharStr, 260);
      v15 = ASCIICharStr;
      if ( !v14 )
        v15 = (WCHAR *)v12;
      v12 = v15;
    }
  }
  v16 = STRA::Copy((STRA *)v44, a2, a3);
  if ( v16 < 0
    || (v16 = W3_REQUEST::BuildFullUrl(*((W3_REQUEST **)this + 6), (struct STRA *)v44, (struct STRA *)v42, v12, a5),
        v16 < 0) )
  {
    STRA::~STRA((STRA *)v44);
    STRA::~STRA((STRA *)v45);
    STRA::~STRA((STRA *)v42);
    return (unsigned int)v16;
  }
  v17 = (struct _HTTP_DATA_CHUNK *)v44;
LABEL_32:
  STRA::~STRA((STRA *)v17);
  if ( STRA::QueryCCH((STRA *)v42) > 0xFFFF )
  {
    appended = -2147024809;
    goto LABEL_50;
  }
  if ( a4 )
    W3_RESPONSE::SetStatus((W3_RESPONSE *)v9, 0x12Eu, "Redirect", 0, 0, 0, 0);
  v29 = STRA::QueryCCH((STRA *)v42);
  v30 = STRA::QueryStr((STRA *)v42);
  appended = W3_RESPONSE::SetHeader((const struct _GUID **)v9, 0x17u, v30, v29, 1);
  if ( appended < 0
    || (++*(_DWORD *)(v9 + 624),
        *(_QWORD *)(v9 + 312) = "text/html; charset=UTF-8",
        *(_WORD *)(v9 + 304) = 24,
        appended = STRA::HTMLEncode((STRA *)v42),
        appended < 0)
    || (Header = W3_REQUEST::QueryHeader(v41, HttpHeaderAcceptLanguage, v38),
        appended = LANG_STRING::GetString(*((LANG_STRING **)g_pW3Server + 194), Header, v38[0], 0x2F44u, &v40, &v39),
        appended < 0)
    || (appended = STRA::CopyWToUTF8Unescaped((STRA *)v45, v40), appended < 0) )
  {
LABEL_49:
    ++*(_DWORD *)(v9 + 624);
    *(_WORD *)(v9 + 592) = 0;
    W3_RESPONSE::SetStatus((W3_RESPONSE *)v9, 0x1F4u, "Internal Server Error", 0, appended, 0, 0);
    goto LABEL_50;
  }
  v32 = STRA::QueryCCH((STRA *)v45);
  v33 = v32 + STRA::QueryCCH((STRA *)v42) + 1;
  v34 = (char *)(*(__int64 (__fastcall **)(W3_CONTEXT *, _QWORD))(*(_QWORD *)this + 144LL))(this, v33);
  if ( !v34 )
  {
    appended = -2147024888;
    goto LABEL_49;
  }
  v35 = STRA::QueryStr((STRA *)v42);
  v36 = STRA::QueryStr((STRA *)v45);
  appended = StringCchPrintfA(v34, v33, v36, v35);
  if ( appended < 0 )
    goto LABEL_49;
  *(_QWORD *)&v43.DataChunkType = 0;
  v37 = -1;
  *(ULONGLONG *)((char *)&v43.FromFragmentCacheEx.ByteRange.Length.QuadPart + 4) = 0;
  HIDWORD(v43.FromFragmentCacheEx.pFragmentName) = 0;
  v43.FromFileHandle.ByteRange.StartingOffset.QuadPart = (ULONGLONG)v34;
  do
    ++v37;
  while ( v34[v37] );
  v43.FromMemory.BufferLength = v37;
  appended = W3_RESPONSE::WriteEntityChunkByReference((W3_RESPONSE *)v9, &v43, -1);
  if ( appended < 0 )
    goto LABEL_49;
  STRA::~STRA((STRA *)v45);
  STRA::~STRA((STRA *)v42);
  return 0;
}

```

## disassembly

```asm
0x180024b80  mov     [rsp-8+arg_18], rbx
0x180024b85  push    rbp
0x180024b86  push    rsi
0x180024b87  push    rdi
0x180024b88  push    r12
0x180024b8a  push    r13
0x180024b8c  push    r14
0x180024b8e  push    r15
0x180024b90  lea     rbp, [rsp-870h]
0x180024b98  sub     rsp, 970h
0x180024b9f  mov     rax, cs:__security_cookie
0x180024ba6  xor     rax, rsp
0x180024ba9  mov     [rbp+8A0h+var_40], rax
0x180024bb0  mov     r15d, r8d
0x180024bb3  mov     r14, rdx
0x180024bb6  mov     r12, rcx
0x180024bb9  lea     rdx, [rbp+8A0h+var_550]
0x180024bc0  mov     edi, 104h
0x180024bc5  lea     rcx, [rsp+9A0h+var_948]
0x180024bca  mov     r8d, edi
0x180024bcd  mov     r13d, r9d
0x180024bd0  call    cs:__imp_??0STRA@@QEAA@PEADK@Z; STRA::STRA(char *,ulong)
0x180024bd7  nop     dword ptr [rax+rax+00h]
0x180024bdc  mov     ebx, 200h
0x180024be1  lea     rdx, [rbp+8A0h+var_240]
0x180024be8  mov     r8d, ebx
0x180024beb  lea     rcx, [rbp+8A0h+var_8A0]
0x180024bef  call    cs:__imp_??0STRA@@QEAA@PEADK@Z; STRA::STRA(char *,ulong)
0x180024bf6  nop     dword ptr [rax+rax+00h]
0x180024bfb  mov     rax, [r12+30h]
0x180024c00  lea     r8d, [rdi-4]
0x180024c04  mov     rsi, [r12+40h]
0x180024c09  lea     rdx, [rbp+8A0h+var_860]
0x180024c0d  mov     [rsp+9A0h+var_950], rax
0x180024c12  xor     eax, eax
0x180024c14  cmp     byte ptr [r14], 2Fh ; '/'
0x180024c18  mov     [rsp+9A0h+var_960], ax
0x180024c1d  mov     [rsp+9A0h+var_958], rax
0x180024c22  mov     [rsp+9A0h+var_95C], eax
0x180024c26  jnz     loc_180024D0E
0x180024c2c  lea     rcx, [rbp+8A0h+var_8D8]
0x180024c30  call    cs:__imp_??0STRA@@QEAA@PEADK@Z; STRA::STRA(char *,ulong)
0x180024c37  nop     dword ptr [rax+rax+00h]
0x180024c3c  mov     rcx, [r12+22D0h]; this
0x180024c44  xor     ebx, ebx
0x180024c46  test    rcx, rcx
0x180024c49  jz      short loc_180024C88
0x180024c4b  call    ?QueryAlternateHostName@W3_METADATA@@QEBAPEBGXZ; W3_METADATA::QueryAlternateHostName(void)
0x180024c50  mov     rbx, rax
0x180024c53  test    rax, rax
0x180024c56  jz      short loc_180024C88
0x180024c58  lea     r9, [rbp+8A0h+ASCIICharStr]; lpASCIICharStr
0x180024c5f  mov     [rsp+9A0h+cchASCIIChar], edi; cchASCIIChar
0x180024c63  or      r8d, 0FFFFFFFFh; cchUnicodeChar
0x180024c67  mov     rdx, rax; lpUnicodeCharStr
0x180024c6a  xor     ecx, ecx; dwFlags
0x180024c6c  call    cs:__imp_IdnToAscii
0x180024c73  nop     dword ptr [rax+rax+00h]
0x180024c78  test    eax, eax
0x180024c7a  lea     rcx, [rbp+8A0h+ASCIICharStr]
0x180024c81  cmovz   rcx, rbx
0x180024c85  mov     rbx, rcx
0x180024c88  mov     r8d, r15d
0x180024c8b  lea     rcx, [rbp+8A0h+var_8D8]
0x180024c8f  mov     rdx, r14
0x180024c92  call    cs:__imp_?Copy@STRA@@QEAAJPEBDK@Z; STRA::Copy(char const *,ulong)
0x180024c99  nop     dword ptr [rax+rax+00h]
0x180024c9e  xor     r15d, r15d
0x180024ca1  mov     edi, eax
0x180024ca3  test    eax, eax
0x180024ca5  js      short loc_180024CD6
0x180024ca7  mov     eax, [rbp+8A0h+arg_20]
0x180024cad  lea     r8, [rsp+9A0h+var_948]; struct STRA *
0x180024cb2  mov     rcx, [r12+30h]; this
0x180024cb7  lea     rdx, [rbp+8A0h+var_8D8]; struct STRA *
0x180024cbb  mov     r9, rbx; unsigned __int16 *
0x180024cbe  mov     [rsp+9A0h+cchASCIIChar], eax; int
0x180024cc2  call    ?BuildFullUrl@W3_REQUEST@@QEAAJAEAVSTRA@@PEAV2@PEBGH@Z; W3_REQUEST::BuildFullUrl(STRA &,STRA *,ushort const *,int)
0x180024cc7  mov     edi, eax
0x180024cc9  test    eax, eax
0x180024ccb  js      short loc_180024CD6
0x180024ccd  lea     rcx, [rbp+8A0h+var_8D8]
0x180024cd1  jmp     loc_180024F4C
0x180024cd6  lea     rcx, [rbp+8A0h+var_8D8]
0x180024cda  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x180024ce1  nop     dword ptr [rax+rax+00h]
0x180024ce6  lea     rcx, [rbp+8A0h+var_8A0]
0x180024cea  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x180024cf1  nop     dword ptr [rax+rax+00h]
0x180024cf6  lea     rcx, [rsp+9A0h+var_948]
0x180024cfb  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x180024d02  nop     dword ptr [rax+rax+00h]
0x180024d07  mov     eax, edi
0x180024d09  jmp     loc_1800251B9
0x180024d0e  lea     rcx, [rbp+8A0h+var_910]
0x180024d12  call    cs:__imp_??0STRA@@QEAA@PEADK@Z; STRA::STRA(char *,ulong)
0x180024d19  nop     dword ptr [rax+rax+00h]
0x180024d1e  mov     r8, rbx; Size
0x180024d21  lea     rcx, [rbp+8A0h+var_440]; void *
0x180024d28  xor     edx, edx; Val
0x180024d2a  call    memset_0
0x180024d2f  mov     r8d, 100h
0x180024d35  lea     rdx, [rbp+8A0h+var_440]
0x180024d3c  lea     rcx, [rbp+8A0h+var_8D8]
0x180024d40  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180024d47  nop     dword ptr [rax+rax+00h]
0x180024d4c  mov     r8d, 7; MaxCount
0x180024d52  lea     rdx, aHttp_0; "http://"
0x180024d59  mov     rcx, r14; String1
0x180024d5c  call    cs:__imp__strnicmp
0x180024d63  nop     dword ptr [rax+rax+00h]
0x180024d68  test    eax, eax
0x180024d6a  jnz     short loc_180024DB5
0x180024d6c  lea     rdx, aHttp_0; "http://"
0x180024d73  lea     rcx, [rsp+9A0h+var_948]
0x180024d78  call    cs:__imp_?Copy@STRA@@QEAAJPEBD@Z; STRA::Copy(char const *)
0x180024d7f  nop     dword ptr [rax+rax+00h]
0x180024d84  mov     ebx, eax
0x180024d86  test    eax, eax
0x180024d88  jns     short loc_180024DAF
0x180024d8a  lea     rcx, [rbp+8A0h+var_8D8]
0x180024d8e  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180024d95  nop     dword ptr [rax+rax+00h]
0x180024d9a  lea     rcx, [rbp+8A0h+var_910]
0x180024d9e  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x180024da5  nop     dword ptr [rax+rax+00h]
0x180024daa  jmp     loc_180025196
0x180024daf  lea     rbx, [r14+7]
0x180024db3  jmp     short loc_180024DFB
0x180024db5  mov     r8d, 8; MaxCount
0x180024dbb  lea     rdx, aHttps; "https://"
0x180024dc2  mov     rcx, r14; String1
0x180024dc5  call    cs:__imp__strnicmp
0x180024dcc  nop     dword ptr [rax+rax+00h]
0x180024dd1  test    eax, eax
0x180024dd3  jnz     loc_180024FEA
0x180024dd9  lea     rdx, aHttps; "https://"
0x180024de0  lea     rcx, [rsp+9A0h+var_948]
0x180024de5  call    cs:__imp_?Copy@STRA@@QEAAJPEBD@Z; STRA::Copy(char const *)
0x180024dec  nop     dword ptr [rax+rax+00h]
0x180024df1  mov     ebx, eax
0x180024df3  test    eax, eax
0x180024df5  js      short loc_180024D8A
0x180024df7  lea     rbx, [r14+8]
0x180024dfb  test    rbx, rbx
0x180024dfe  jz      loc_180024FEA
0x180024e04  mov     edx, 2Fh ; '/'; Val
0x180024e09  mov     rcx, rbx; Str
0x180024e0c  call    cs:__imp_strchr
0x180024e13  nop     dword ptr [rax+rax+00h]
0x180024e18  mov     edx, 3Ah ; ':'; Val
0x180024e1d  mov     rcx, rbx; Str
0x180024e20  mov     rdi, rax
0x180024e23  call    cs:__imp_strchr
0x180024e2a  nop     dword ptr [rax+rax+00h]
0x180024e2f  test    rdi, rdi
0x180024e32  jz      loc_180024F7E
0x180024e38  test    rax, rax
0x180024e3b  jz      short loc_180024E44
0x180024e3d  cmp     rax, rdi
0x180024e40  cmovb   rdi, rax
0x180024e44  test    rdi, rdi
0x180024e47  jnz     loc_180024F8A
0x180024e4d  mov     rdx, rbx
0x180024e50  lea     rcx, [rbp+8A0h+var_910]
0x180024e54  call    cs:__imp_?Copy@STRA@@QEAAJPEBD@Z; STRA::Copy(char const *)
0x180024e5b  nop     dword ptr [rax+rax+00h]
0x180024e60  mov     ebx, eax
0x180024e62  test    eax, eax
0x180024e64  js      loc_180024D8A
0x180024e6a  lea     rcx, [rbp+8A0h+var_910]
0x180024e6e  call    cs:__imp_?Unescape@STRA@@QEAAJXZ; STRA::Unescape(void)
0x180024e75  nop     dword ptr [rax+rax+00h]
0x180024e7a  mov     ebx, eax
0x180024e7c  test    eax, eax
0x180024e7e  js      loc_180024D8A
0x180024e84  lea     rcx, [rbp+8A0h+var_910]
0x180024e88  call    cs:__imp_?QueryCCH@STRA@@QEBAKXZ; STRA::QueryCCH(void)
0x180024e8f  nop     dword ptr [rax+rax+00h]
0x180024e94  lea     rcx, [rbp+8A0h+var_910]
0x180024e98  mov     ebx, eax
0x180024e9a  call    cs:__imp_?QueryStr@STRA@@QEAAPEADXZ; STRA::QueryStr(void)
0x180024ea1  nop     dword ptr [rax+rax+00h]
0x180024ea6  mov     r8d, ebx
0x180024ea9  lea     rcx, [rbp+8A0h+var_8D8]
0x180024ead  mov     rdx, rax
0x180024eb0  call    cs:__imp_?CopyA@STRU@@QEAAJPEBDK@Z; STRU::CopyA(char const *,ulong)
0x180024eb7  nop     dword ptr [rax+rax+00h]
0x180024ebc  lea     rcx, [rbp+8A0h+var_8D8]
0x180024ec0  mov     ebx, eax
0x180024ec2  test    eax, eax
0x180024ec4  js      loc_180024D8E
0x180024eca  call    cs:__imp_?QueryCCH@STRU@@QEBAKXZ; STRU::QueryCCH(void)
0x180024ed1  nop     dword ptr [rax+rax+00h]
0x180024ed6  lea     rcx, [rbp+8A0h+var_8D8]
0x180024eda  lea     ebx, [rax+1]
0x180024edd  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180024ee4  nop     dword ptr [rax+rax+00h]
0x180024ee9  lea     r9, [rbp+8A0h+ASCIICharStr]; lpASCIICharStr
0x180024ef0  mov     [rsp+9A0h+cchASCIIChar], 104h; cchASCIIChar
0x180024ef8  mov     rdx, rax; lpUnicodeCharStr
0x180024efb  mov     r8d, ebx; cchUnicodeChar
0x180024efe  xor     ecx, ecx; dwFlags
0x180024f00  call    cs:__imp_IdnToAscii
0x180024f07  nop     dword ptr [rax+rax+00h]
0x180024f0c  lea     rcx, [rsp+9A0h+var_948]
0x180024f11  test    eax, eax
0x180024f13  jnz     loc_180024FA8
0x180024f19  mov     rdx, r14
0x180024f1c  mov     r8d, r15d
0x180024f1f  call    cs:__imp_?Copy@STRA@@QEAAJPEBDK@Z; STRA::Copy(char const *,ulong)
0x180024f26  nop     dword ptr [rax+rax+00h]
0x180024f2b  xor     r15d, r15d
0x180024f2e  mov     ebx, eax
0x180024f30  test    eax, eax
0x180024f32  js      loc_180024D8A
0x180024f38  lea     rcx, [rbp+8A0h+var_8D8]
0x180024f3c  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180024f43  nop     dword ptr [rax+rax+00h]
0x180024f48  lea     rcx, [rbp+8A0h+var_910]
0x180024f4c  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x180024f53  nop     dword ptr [rax+rax+00h]
0x180024f58  lea     rcx, [rsp+9A0h+var_948]
0x180024f5d  call    cs:__imp_?QueryCCH@STRA@@QEBAKXZ; STRA::QueryCCH(void)
0x180024f64  nop     dword ptr [rax+rax+00h]
0x180024f69  cmp     eax, 0FFFFh
0x180024f6e  jbe     loc_180024FF4
0x180024f74  mov     ebx, 80070057h
0x180024f79  jmp     loc_180025196
0x180024f7e  test    rax, rax
0x180024f81  jz      loc_180024E4D
0x180024f87  mov     rdi, rax
0x180024f8a  mov     r8d, edi
0x180024f8d  lea     rcx, [rbp+8A0h+var_910]
0x180024f91  sub     r8d, ebx
0x180024f94  mov     rdx, rbx
0x180024f97  call    cs:__imp_?Copy@STRA@@QEAAJPEBDK@Z; STRA::Copy(char const *,ulong)
0x180024f9e  nop     dword ptr [rax+rax+00h]
0x180024fa3  jmp     loc_180024E60
0x180024fa8  lea     rdx, [rbp+8A0h+ASCIICharStr]
0x180024faf  call    cs:__imp_?AppendWTruncate@STRA@@QEAAJPEBG@Z; STRA::AppendWTruncate(ushort const *)
0x180024fb6  nop     dword ptr [rax+rax+00h]
0x180024fbb  xor     r15d, r15d
0x180024fbe  mov     ebx, eax
0x180024fc0  test    eax, eax
0x180024fc2  js      loc_180024D8A
0x180024fc8  test    rdi, rdi
0x180024fcb  jz      loc_180024F38
0x180024fd1  mov     rdx, rdi
0x180024fd4  lea     rcx, [rsp+9A0h+var_948]
0x180024fd9  call    cs:__imp_?Append@STRA@@QEAAJPEBD@Z; STRA::Append(char const *)
0x180024fe0  nop     dword ptr [rax+rax+00h]
0x180024fe5  jmp     loc_180024F2E
0x180024fea  lea     rcx, [rsp+9A0h+var_948]
0x180024fef  jmp     loc_180024F19
0x180024ff4  test    r13d, r13d
0x180024ff7  jz      short loc_18002501F
0x180024ff9  mov     [rsp+9A0h+var_970], r15d; int
0x180024ffe  lea     r8, aRedirect; "Redirect"
0x180025005  mov     [rsp+9A0h+var_978], r15; struct IAppHostConfigException *
0x18002500a  xor     r9d, r9d; unsigned __int16
0x18002500d  mov     edx, 12Eh; unsigned __int16
0x180025012  mov     [rsp+9A0h+cchASCIIChar], r15d; int
0x180025017  mov     rcx, rsi; this
0x18002501a  call    ?SetStatus@W3_RESPONSE@@QEAAJGPEBDGJPEAUIAppHostConfigException@@H@Z; W3_RESPONSE::SetStatus(ushort,char const *,ushort,long,IAppHostConfigException *,int)
0x18002501f  lea     rcx, [rsp+9A0h+var_948]
0x180025024  call    cs:__imp_?QueryCCH@STRA@@QEBAKXZ; STRA::QueryCCH(void)
0x18002502b  nop     dword ptr [rax+rax+00h]
0x180025030  lea     rcx, [rsp+9A0h+var_948]
0x180025035  mov     ebx, eax
0x180025037  call    cs:__imp_?QueryStr@STRA@@QEAAPEADXZ; STRA::QueryStr(void)
0x18002503e  nop     dword ptr [rax+rax+00h]
0x180025043  mov     edi, 17h
0x180025048  mov     [rsp+9A0h+cchASCIIChar], 1; int
0x180025050  mov     r8, rax; char *
0x180025053  mov     edx, edi; enum _HTTP_HEADER_ID
0x180025055  movzx   r9d, bx; unsigned __int16
0x180025059  mov     rcx, rsi; this
0x18002505c  call    ?SetHeader@W3_RESPONSE@@QEAAJW4_HTTP_HEADER_ID@@PEBDGH@Z; W3_RESPONSE::SetHeader(_HTTP_HEADER_ID,char const *,ushort,int)
0x180025061  mov     ebx, eax
0x180025063  test    eax, eax
0x180025065  js      loc_180025163
0x18002506b  inc     dword ptr [rsi+270h]
0x180025071  lea     rax, aTextHtmlCharse; "text/html; charset=UTF-8"
0x180025078  lea     rcx, [rsp+9A0h+var_948]
0x18002507d  mov     [rsi+138h], rax
0x180025084  mov     word ptr [rsi+130h], 18h
0x18002508d  call    cs:__imp_?HTMLEncode@STRA@@QEAAJXZ; STRA::HTMLEncode(void)
0x180025094  nop     dword ptr [rax+rax+00h]
0x180025099  mov     ebx, eax
0x18002509b  test    eax, eax
0x18002509d  js      loc_180025163
0x1800250a3  mov     rcx, [rsp+9A0h+var_950]; this
0x1800250a8  lea     r8, [rsp+9A0h+var_960]; unsigned __int16 *
0x1800250ad  mov     edx, edi; enum _HTTP_HEADER_ID
0x1800250af  call    ?QueryHeader@W3_REQUEST@@QEBAPEBDW4_HTTP_HEADER_ID@@PEAG@Z; W3_REQUEST::QueryHeader(_HTTP_HEADER_ID,ushort *)
0x1800250b4  movzx   r8d, [rsp+9A0h+var_960]
0x1800250ba  lea     rcx, [rsp+9A0h+var_95C]
0x1800250bf  mov     [rsp+9A0h+var_978], rcx
0x1800250c4  mov     r9d, 2F44h
  ... truncated ...
```
