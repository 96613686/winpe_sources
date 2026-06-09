# W3_CONTEXT::SetupHttpRedirect(char const *,ulong,int,int)

- ea: `0x180022e70`
- end: `0x180023456`
- name: `?SetupHttpRedirect@W3_CONTEXT@@QEAAJPEBDKHH@Z`
- size: `1510`
- prototype: `int(W3_CONTEXT *__hidden this, const char *, unsigned int, int, int)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x180022540`

## callees

- `0x180007d10`
- `0x18000d340`
- `0x180014db0`
- `0x1800159e0`
- `0x180021490`
- `0x180022e70`
- `0x18002345c`
- `0x180026e68`
- `0x18003439a`
- `0x1800343f0`
- `0x180035010`

## import_xrefs

- `msvcrt!_strnicmp` at `0x180023010`
- `msvcrt!_strnicmp` at `0x180023061`
- `msvcrt!_strnicmp` at `0x180023010`
- `msvcrt!_strnicmp` at `0x180023061`
- `msvcrt!strchr` at `0x18002309c`
- `msvcrt!strchr` at `0x1800230ad`
- `msvcrt!strchr` at `0x18002309c`
- `msvcrt!strchr` at `0x1800230ad`
- `api-ms-win-core-localization-l1-2-0!IdnToAscii` at `0x180022f4a`
- `api-ms-win-core-localization-l1-2-0!IdnToAscii` at `0x18002315a`
- `api-ms-win-core-localization-l1-2-0!IdnToAscii` at `0x180022f4a`
- `api-ms-win-core-localization-l1-2-0!IdnToAscii` at `0x18002315a`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180023036`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180023186`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180023036`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180023186`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x180023130`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x180023130`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18002313d`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18002313d`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180022ffa`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180022ffa`
- `iisutil!?GetString@LANG_STRING@@QEAAJPEBDKIPEAPEBGPEAK@Z` at `0x1800232f1`
- `iisutil!?GetString@LANG_STRING@@QEAAJPEBDKIPEAPEBGPEAK@Z` at `0x1800232f1`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180022ec0`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180022ed9`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180022f14`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180022fd2`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180022ec0`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180022ed9`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180022f14`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180022fd2`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180022fac`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180022fb6`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180022fc1`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180023040`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180023190`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18002338a`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180023395`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18002343e`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180023449`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180022fac`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180022fb6`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180022fc1`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180023040`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180023190`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18002338a`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180023395`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18002343e`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180023449`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x18002310c`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x18002324f`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x1800233cc`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x1800233d9`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x18002310c`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x18002324f`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x1800233cc`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x1800233d9`
- `iisutil!?Copy@STRA@@QEAAJPEBDK@Z` at `0x180022f6a`
- `iisutil!?Copy@STRA@@QEAAJPEBDK@Z` at `0x18002316f`
- `iisutil!?Copy@STRA@@QEAAJPEBDK@Z` at `0x1800231cb`
- `iisutil!?Copy@STRA@@QEAAJPEBDK@Z` at `0x180022f6a`
- `iisutil!?Copy@STRA@@QEAAJPEBDK@Z` at `0x18002316f`
- `iisutil!?Copy@STRA@@QEAAJPEBDK@Z` at `0x1800231cb`
- `iisutil!?Copy@STRA@@QEAAJPEBD@Z` at `0x180023026`
- `iisutil!?Copy@STRA@@QEAAJPEBD@Z` at `0x18002307b`
- `iisutil!?Copy@STRA@@QEAAJPEBD@Z` at `0x1800230d8`
- `iisutil!?Copy@STRA@@QEAAJPEBD@Z` at `0x180023026`
- `iisutil!?Copy@STRA@@QEAAJPEBD@Z` at `0x18002307b`
- `iisutil!?Copy@STRA@@QEAAJPEBD@Z` at `0x1800230d8`
- `iisutil!?CopyWToUTF8Unescaped@STRA@@QEAAJPEBG@Z` at `0x180023306`
- `iisutil!?CopyWToUTF8Unescaped@STRA@@QEAAJPEBG@Z` at `0x180023306`
- `iisutil!?QueryCCH@STRA@@QEBAKXZ` at `0x180023100`
- `iisutil!?QueryCCH@STRA@@QEBAKXZ` at `0x18002319b`
- `iisutil!?QueryCCH@STRA@@QEBAKXZ` at `0x180023242`
- `iisutil!?QueryCCH@STRA@@QEBAKXZ` at `0x180023316`
- `iisutil!?QueryCCH@STRA@@QEBAKXZ` at `0x180023323`
- `iisutil!?QueryCCH@STRA@@QEBAKXZ` at `0x180023100`
- `iisutil!?QueryCCH@STRA@@QEBAKXZ` at `0x18002319b`
- `iisutil!?QueryCCH@STRA@@QEBAKXZ` at `0x180023242`
- `iisutil!?QueryCCH@STRA@@QEBAKXZ` at `0x180023316`
- `iisutil!?QueryCCH@STRA@@QEBAKXZ` at `0x180023323`
- `iisutil!?Unescape@STRA@@QEAAJXZ` at `0x1800230ec`
- `iisutil!?Unescape@STRA@@QEAAJXZ` at `0x1800230ec`
- `iisutil!?CopyA@STRU@@QEAAJPEBDK@Z` at `0x18002311c`
- `iisutil!?CopyA@STRU@@QEAAJPEBDK@Z` at `0x18002311c`
- `iisutil!?AppendWTruncate@STRA@@QEAAJPEBG@Z` at `0x1800231dd`
- `iisutil!?AppendWTruncate@STRA@@QEAAJPEBG@Z` at `0x1800231dd`
- `iisutil!?Append@STRA@@QEAAJPEBD@Z` at `0x1800231fd`
- `iisutil!?Append@STRA@@QEAAJPEBD@Z` at `0x1800231fd`
- `iisutil!?HTMLEncode@STRA@@QEAAJXZ` at `0x18002329f`
- `iisutil!?HTMLEncode@STRA@@QEAAJXZ` at `0x18002329f`

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
    || (Header = W3_REQUEST::QueryHeader(v41, 0x17u, v38),
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
0x180022e70  mov     [rsp-8+arg_18], rbx
0x180022e75  push    rbp
0x180022e76  push    rsi
0x180022e77  push    rdi
0x180022e78  push    r12
0x180022e7a  push    r13
0x180022e7c  push    r14
0x180022e7e  push    r15
0x180022e80  lea     rbp, [rsp-870h]
0x180022e88  sub     rsp, 970h
0x180022e8f  mov     rax, cs:__security_cookie
0x180022e96  xor     rax, rsp
0x180022e99  mov     [rbp+8A0h+var_40], rax
0x180022ea0  mov     r15d, r8d
0x180022ea3  mov     r14, rdx
0x180022ea6  mov     r12, rcx
0x180022ea9  lea     rdx, [rbp+8A0h+var_550]
0x180022eb0  mov     edi, 104h
0x180022eb5  lea     rcx, [rsp+9A0h+var_948]
0x180022eba  mov     r8d, edi
0x180022ebd  mov     r13d, r9d
0x180022ec0  call    cs:__imp_??0STRA@@QEAA@PEADK@Z; STRA::STRA(char *,ulong)
0x180022ec6  mov     ebx, 200h
0x180022ecb  lea     rdx, [rbp+8A0h+var_240]
0x180022ed2  mov     r8d, ebx
0x180022ed5  lea     rcx, [rbp+8A0h+var_8A0]
0x180022ed9  call    cs:__imp_??0STRA@@QEAA@PEADK@Z; STRA::STRA(char *,ulong)
0x180022edf  mov     rax, [r12+30h]
0x180022ee4  lea     r8d, [rdi-4]
0x180022ee8  mov     rsi, [r12+40h]
0x180022eed  lea     rdx, [rbp+8A0h+var_860]
0x180022ef1  mov     [rsp+9A0h+var_950], rax
0x180022ef6  xor     eax, eax
0x180022ef8  cmp     byte ptr [r14], 2Fh ; '/'
0x180022efc  mov     [rsp+9A0h+var_960], ax
0x180022f01  mov     [rsp+9A0h+var_958], rax
0x180022f06  mov     [rsp+9A0h+var_95C], eax
0x180022f0a  jnz     loc_180022FCE
0x180022f10  lea     rcx, [rbp+8A0h+var_8D8]
0x180022f14  call    cs:__imp_??0STRA@@QEAA@PEADK@Z; STRA::STRA(char *,ulong)
0x180022f1a  mov     rcx, [r12+22D0h]; this
0x180022f22  xor     ebx, ebx
0x180022f24  test    rcx, rcx
0x180022f27  jz      short loc_180022F60
0x180022f29  call    ?QueryAlternateHostName@W3_METADATA@@QEBAPEBGXZ; W3_METADATA::QueryAlternateHostName(void)
0x180022f2e  mov     rbx, rax
0x180022f31  test    rax, rax
0x180022f34  jz      short loc_180022F60
0x180022f36  lea     r9, [rbp+8A0h+ASCIICharStr]; lpASCIICharStr
0x180022f3d  mov     [rsp+9A0h+cchASCIIChar], edi; cchASCIIChar
0x180022f41  or      r8d, 0FFFFFFFFh; cchUnicodeChar
0x180022f45  mov     rdx, rax; lpUnicodeCharStr
0x180022f48  xor     ecx, ecx; dwFlags
0x180022f4a  call    cs:__imp_IdnToAscii
0x180022f50  test    eax, eax
0x180022f52  lea     rcx, [rbp+8A0h+ASCIICharStr]
0x180022f59  cmovz   rcx, rbx
0x180022f5d  mov     rbx, rcx
0x180022f60  mov     r8d, r15d
0x180022f63  lea     rcx, [rbp+8A0h+var_8D8]
0x180022f67  mov     rdx, r14
0x180022f6a  call    cs:__imp_?Copy@STRA@@QEAAJPEBDK@Z; STRA::Copy(char const *,ulong)
0x180022f70  xor     r15d, r15d
0x180022f73  mov     edi, eax
0x180022f75  test    eax, eax
0x180022f77  js      short loc_180022FA8
0x180022f79  mov     eax, [rbp+8A0h+arg_20]
0x180022f7f  lea     r8, [rsp+9A0h+var_948]; struct STRA *
0x180022f84  mov     rcx, [r12+30h]; this
0x180022f89  lea     rdx, [rbp+8A0h+var_8D8]; struct STRA *
0x180022f8d  mov     r9, rbx; unsigned __int16 *
0x180022f90  mov     [rsp+9A0h+cchASCIIChar], eax; int
0x180022f94  call    ?BuildFullUrl@W3_REQUEST@@QEAAJAEAVSTRA@@PEAV2@PEBGH@Z; W3_REQUEST::BuildFullUrl(STRA &,STRA *,ushort const *,int)
0x180022f99  mov     edi, eax
0x180022f9b  test    eax, eax
0x180022f9d  js      short loc_180022FA8
0x180022f9f  lea     rcx, [rbp+8A0h+var_8D8]
0x180022fa3  jmp     loc_180023190
0x180022fa8  lea     rcx, [rbp+8A0h+var_8D8]
0x180022fac  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x180022fb2  lea     rcx, [rbp+8A0h+var_8A0]
0x180022fb6  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x180022fbc  lea     rcx, [rsp+9A0h+var_948]
0x180022fc1  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x180022fc7  mov     eax, edi
0x180022fc9  jmp     loc_18002339D
0x180022fce  lea     rcx, [rbp+8A0h+var_910]
0x180022fd2  call    cs:__imp_??0STRA@@QEAA@PEADK@Z; STRA::STRA(char *,ulong)
0x180022fd8  mov     r8, rbx; Size
0x180022fdb  lea     rcx, [rbp+8A0h+var_440]; void *
0x180022fe2  xor     edx, edx; Val
0x180022fe4  call    memset_0
0x180022fe9  mov     r8d, 100h
0x180022fef  lea     rdx, [rbp+8A0h+var_440]
0x180022ff6  lea     rcx, [rbp+8A0h+var_8D8]
0x180022ffa  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180023000  mov     r8d, 7; MaxCount
0x180023006  lea     rdx, aHttp_0; "http://"
0x18002300d  mov     rcx, r14; String1
0x180023010  call    cs:__imp__strnicmp
0x180023016  test    eax, eax
0x180023018  jnz     short loc_180023051
0x18002301a  lea     rdx, aHttp_0; "http://"
0x180023021  lea     rcx, [rsp+9A0h+var_948]
0x180023026  call    cs:__imp_?Copy@STRA@@QEAAJPEBD@Z; STRA::Copy(char const *)
0x18002302c  mov     ebx, eax
0x18002302e  test    eax, eax
0x180023030  jns     short loc_18002304B
0x180023032  lea     rcx, [rbp+8A0h+var_8D8]
0x180023036  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18002303c  lea     rcx, [rbp+8A0h+var_910]
0x180023040  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x180023046  jmp     loc_180023386
0x18002304b  lea     rbx, [r14+7]
0x18002304f  jmp     short loc_18002308B
0x180023051  mov     r8d, 8; MaxCount
0x180023057  lea     rdx, aHttps; "https://"
0x18002305e  mov     rcx, r14; String1
0x180023061  call    cs:__imp__strnicmp
0x180023067  test    eax, eax
0x180023069  jnz     loc_180023208
0x18002306f  lea     rdx, aHttps; "https://"
0x180023076  lea     rcx, [rsp+9A0h+var_948]
0x18002307b  call    cs:__imp_?Copy@STRA@@QEAAJPEBD@Z; STRA::Copy(char const *)
0x180023081  mov     ebx, eax
0x180023083  test    eax, eax
0x180023085  js      short loc_180023032
0x180023087  lea     rbx, [r14+8]
0x18002308b  test    rbx, rbx
0x18002308e  jz      loc_180023208
0x180023094  mov     edx, 2Fh ; '/'; Val
0x180023099  mov     rcx, rbx; Str
0x18002309c  call    cs:__imp_strchr
0x1800230a2  mov     edx, 3Ah ; ':'; Val
0x1800230a7  mov     rcx, rbx; Str
0x1800230aa  mov     rdi, rax
0x1800230ad  call    cs:__imp_strchr
0x1800230b3  test    rdi, rdi
0x1800230b6  jz      loc_1800231B2
0x1800230bc  test    rax, rax
0x1800230bf  jz      short loc_1800230C8
0x1800230c1  cmp     rax, rdi
0x1800230c4  cmovb   rdi, rax
0x1800230c8  test    rdi, rdi
0x1800230cb  jnz     loc_1800231BE
0x1800230d1  mov     rdx, rbx
0x1800230d4  lea     rcx, [rbp+8A0h+var_910]
0x1800230d8  call    cs:__imp_?Copy@STRA@@QEAAJPEBD@Z; STRA::Copy(char const *)
0x1800230de  mov     ebx, eax
0x1800230e0  test    eax, eax
0x1800230e2  js      loc_180023032
0x1800230e8  lea     rcx, [rbp+8A0h+var_910]
0x1800230ec  call    cs:__imp_?Unescape@STRA@@QEAAJXZ; STRA::Unescape(void)
0x1800230f2  mov     ebx, eax
0x1800230f4  test    eax, eax
0x1800230f6  js      loc_180023032
0x1800230fc  lea     rcx, [rbp+8A0h+var_910]
0x180023100  call    cs:__imp_?QueryCCH@STRA@@QEBAKXZ; STRA::QueryCCH(void)
0x180023106  lea     rcx, [rbp+8A0h+var_910]
0x18002310a  mov     ebx, eax
0x18002310c  call    cs:__imp_?QueryStr@STRA@@QEAAPEADXZ; STRA::QueryStr(void)
0x180023112  mov     r8d, ebx
0x180023115  lea     rcx, [rbp+8A0h+var_8D8]
0x180023119  mov     rdx, rax
0x18002311c  call    cs:__imp_?CopyA@STRU@@QEAAJPEBDK@Z; STRU::CopyA(char const *,ulong)
0x180023122  lea     rcx, [rbp+8A0h+var_8D8]
0x180023126  mov     ebx, eax
0x180023128  test    eax, eax
0x18002312a  js      loc_180023036
0x180023130  call    cs:__imp_?QueryCCH@STRU@@QEBAKXZ; STRU::QueryCCH(void)
0x180023136  lea     rcx, [rbp+8A0h+var_8D8]
0x18002313a  lea     ebx, [rax+1]
0x18002313d  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180023143  lea     r9, [rbp+8A0h+ASCIICharStr]; lpASCIICharStr
0x18002314a  mov     [rsp+9A0h+cchASCIIChar], 104h; cchASCIIChar
0x180023152  mov     rdx, rax; lpUnicodeCharStr
0x180023155  mov     r8d, ebx; cchUnicodeChar
0x180023158  xor     ecx, ecx; dwFlags
0x18002315a  call    cs:__imp_IdnToAscii
0x180023160  lea     rcx, [rsp+9A0h+var_948]
0x180023165  test    eax, eax
0x180023167  jnz     short loc_1800231D6
0x180023169  mov     rdx, r14
0x18002316c  mov     r8d, r15d
0x18002316f  call    cs:__imp_?Copy@STRA@@QEAAJPEBDK@Z; STRA::Copy(char const *,ulong)
0x180023175  xor     r15d, r15d
0x180023178  mov     ebx, eax
0x18002317a  test    eax, eax
0x18002317c  js      loc_180023032
0x180023182  lea     rcx, [rbp+8A0h+var_8D8]
0x180023186  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18002318c  lea     rcx, [rbp+8A0h+var_910]
0x180023190  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x180023196  lea     rcx, [rsp+9A0h+var_948]
0x18002319b  call    cs:__imp_?QueryCCH@STRA@@QEBAKXZ; STRA::QueryCCH(void)
0x1800231a1  cmp     eax, 0FFFFh
0x1800231a6  jbe     short loc_180023212
0x1800231a8  mov     ebx, 80070057h
0x1800231ad  jmp     loc_180023386
0x1800231b2  test    rax, rax
0x1800231b5  jz      loc_1800230D1
0x1800231bb  mov     rdi, rax
0x1800231be  mov     r8d, edi
0x1800231c1  lea     rcx, [rbp+8A0h+var_910]
0x1800231c5  sub     r8d, ebx
0x1800231c8  mov     rdx, rbx
0x1800231cb  call    cs:__imp_?Copy@STRA@@QEAAJPEBDK@Z; STRA::Copy(char const *,ulong)
0x1800231d1  jmp     loc_1800230DE
0x1800231d6  lea     rdx, [rbp+8A0h+ASCIICharStr]
0x1800231dd  call    cs:__imp_?AppendWTruncate@STRA@@QEAAJPEBG@Z; STRA::AppendWTruncate(ushort const *)
0x1800231e3  xor     r15d, r15d
0x1800231e6  mov     ebx, eax
0x1800231e8  test    eax, eax
0x1800231ea  js      loc_180023032
0x1800231f0  test    rdi, rdi
0x1800231f3  jz      short loc_180023182
0x1800231f5  mov     rdx, rdi
0x1800231f8  lea     rcx, [rsp+9A0h+var_948]
0x1800231fd  call    cs:__imp_?Append@STRA@@QEAAJPEBD@Z; STRA::Append(char const *)
0x180023203  jmp     loc_180023178
0x180023208  lea     rcx, [rsp+9A0h+var_948]
0x18002320d  jmp     loc_180023169
0x180023212  test    r13d, r13d
0x180023215  jz      short loc_18002323D
0x180023217  mov     [rsp+9A0h+var_970], r15d; int
0x18002321c  lea     r8, aRedirect; "Redirect"
0x180023223  mov     [rsp+9A0h+var_978], r15; struct IAppHostConfigException *
0x180023228  xor     r9d, r9d; unsigned __int16
0x18002322b  mov     edx, 12Eh; unsigned __int16
0x180023230  mov     [rsp+9A0h+cchASCIIChar], r15d; int
0x180023235  mov     rcx, rsi; this
0x180023238  call    ?SetStatus@W3_RESPONSE@@QEAAJGPEBDGJPEAUIAppHostConfigException@@H@Z; W3_RESPONSE::SetStatus(ushort,char const *,ushort,long,IAppHostConfigException *,int)
0x18002323d  lea     rcx, [rsp+9A0h+var_948]
0x180023242  call    cs:__imp_?QueryCCH@STRA@@QEBAKXZ; STRA::QueryCCH(void)
0x180023248  lea     rcx, [rsp+9A0h+var_948]
0x18002324d  mov     ebx, eax
0x18002324f  call    cs:__imp_?QueryStr@STRA@@QEAAPEADXZ; STRA::QueryStr(void)
0x180023255  mov     edi, 17h
0x18002325a  mov     [rsp+9A0h+cchASCIIChar], 1; int
0x180023262  mov     r8, rax; char *
0x180023265  mov     edx, edi; enum _HTTP_HEADER_ID
0x180023267  movzx   r9d, bx; unsigned __int16
0x18002326b  mov     rcx, rsi; this
0x18002326e  call    ?SetHeader@W3_RESPONSE@@QEAAJW4_HTTP_HEADER_ID@@PEBDGH@Z; W3_RESPONSE::SetHeader(_HTTP_HEADER_ID,char const *,ushort,int)
0x180023273  mov     ebx, eax
0x180023275  test    eax, eax
0x180023277  js      loc_180023353
0x18002327d  inc     dword ptr [rsi+270h]
0x180023283  lea     rax, aTextHtmlCharse; "text/html; charset=UTF-8"
0x18002328a  lea     rcx, [rsp+9A0h+var_948]
0x18002328f  mov     [rsi+138h], rax
0x180023296  mov     word ptr [rsi+130h], 18h
0x18002329f  call    cs:__imp_?HTMLEncode@STRA@@QEAAJXZ; STRA::HTMLEncode(void)
0x1800232a5  mov     ebx, eax
0x1800232a7  test    eax, eax
0x1800232a9  js      loc_180023353
0x1800232af  mov     rcx, [rsp+9A0h+var_950]; this
0x1800232b4  lea     r8, [rsp+9A0h+var_960]; unsigned __int16 *
0x1800232b9  mov     edx, edi; enum _HTTP_HEADER_ID
0x1800232bb  call    ?QueryHeader@W3_REQUEST@@QEBAPEBDW4_HTTP_HEADER_ID@@PEAG@Z; W3_REQUEST::QueryHeader(_HTTP_HEADER_ID,ushort *)
0x1800232c0  movzx   r8d, [rsp+9A0h+var_960]
0x1800232c6  lea     rcx, [rsp+9A0h+var_95C]
0x1800232cb  mov     [rsp+9A0h+var_978], rcx
0x1800232d0  mov     r9d, 2F44h
0x1800232d6  lea     rcx, [rsp+9A0h+var_958]
0x1800232db  mov     rdx, rax
0x1800232de  mov     qword ptr [rsp+9A0h+cchASCIIChar], rcx
0x1800232e3  mov     rcx, cs:?g_pW3Server@@3PEAVW3_SERVER@@EA; W3_SERVER * g_pW3Server
0x1800232ea  mov     rcx, [rcx+610h]
0x1800232f1  call    cs:__imp_?GetString@LANG_STRING@@QEAAJPEBDKIPEAPEBGPEAK@Z; LANG_STRING::GetString(char const *,ulong,uint,ushort const * *,ulong *)
0x1800232f7  mov     ebx, eax
0x1800232f9  test    eax, eax
0x1800232fb  js      short loc_180023353
0x1800232fd  mov     rdx, [rsp+9A0h+var_958]
0x180023302  lea     rcx, [rbp+8A0h+var_8A0]
0x180023306  call    cs:__imp_?CopyWToUTF8Unescaped@STRA@@QEAAJPEBG@Z; STRA::CopyWToUTF8Unescaped(ushort const *)
0x18002330c  mov     ebx, eax
0x18002330e  test    eax, eax
0x180023310  js      short loc_180023353
0x180023312  lea     rcx, [rbp+8A0h+var_8A0]
0x180023316  call    cs:__imp_?QueryCCH@STRA@@QEBAKXZ; STRA::QueryCCH(void)
0x18002331c  lea     rcx, [rsp+9A0h+var_948]
0x180023321  mov     ebx, eax
0x180023323  call    cs:__imp_?QueryCCH@STRA@@QEBAKXZ; STRA::QueryCCH(void)
0x180023329  mov     rcx, r12
0x18002332c  lea     r14d, [rax+1]
0x180023330  mov     rax, [r12]
0x180023334  add     r14d, ebx
0x180023337  mov     edx, r14d
0x18002333a  mov     rax, [rax+90h]
0x180023341  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023346  mov     rdi, rax
0x180023349  test    rax, rax
0x18002334c  jnz     short loc_1800233C7
0x18002334e  mov     ebx, 80070008h
0x180023353  inc     dword ptr [rsi+270h]
0x180023359  lea     r8, aInternalServer; "Internal Server Error"
0x180023360  mov     [rsp+9A0h+var_970], r15d; int
0x180023365  xor     r9d, r9d; unsigned __int16
0x180023368  mov     [rsp+9A0h+var_978], r15; struct IAppHostConfigException *
  ... truncated ...
```
