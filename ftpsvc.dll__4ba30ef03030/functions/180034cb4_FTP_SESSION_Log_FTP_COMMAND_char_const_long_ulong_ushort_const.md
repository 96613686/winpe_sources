# FTP_SESSION::Log(FTP_COMMAND *,char const *,long,ulong,ushort const *)

- ea: `0x180034cb4`
- end: `0x180035238`
- name: `?Log@FTP_SESSION@@QEAAXPEAVFTP_COMMAND@@PEBDJKPEBG@Z`
- size: `1412`
- prototype: `void __usercall(FTP_SESSION *__hidden this@<rcx>, struct FTP_COMMAND *@<rdx>, const char *@<r8>, int@<r9d>, unsigned int, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `8`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18003e3c8`
- `0x18003e564`
- `0x18003e980`

## callees

- `0x180026fdc`
- `0x18002747c`
- `0x18002b84c`
- `0x180033398`
- `0x180034cb4`
- `0x180035dcc`
- `0x180047050`
- `0x180049010`

## import_xrefs

- `msvcrt!atol` at `0x180034e1a`
- `msvcrt!atol` at `0x180034e1a`
- `msvcrt!_wcsicmp` at `0x180034ee8`
- `msvcrt!_wcsicmp` at `0x180034f00`
- `msvcrt!_wcsicmp` at `0x180034ee8`
- `msvcrt!_wcsicmp` at `0x180034f00`
- `KERNEL32!GetTickCount` at `0x180034f7c`
- `KERNEL32!GetTickCount` at `0x180035061`
- `KERNEL32!GetTickCount` at `0x180034f7c`
- `KERNEL32!GetTickCount` at `0x180035061`
- `WS2_32!__imp_ntohs` at `0x1800350cb`
- `WS2_32!__imp_ntohs` at `0x1800350e9`
- `WS2_32!__imp_ntohs` at `0x1800350cb`
- `WS2_32!__imp_ntohs` at `0x1800350e9`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180034d1b`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180034d33`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180034d4f`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180034d64`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180034d7c`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180034d8f`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180034dfd`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180034d1b`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180034d33`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180034d4f`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180034d64`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180034d7c`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180034d8f`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180034dfd`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18003519e`
- `iisutil!??1STRA@@QEAA@XZ` at `0x1800351c5`
- `iisutil!??1STRA@@QEAA@XZ` at `0x1800351d3`
- `iisutil!??1STRA@@QEAA@XZ` at `0x1800351de`
- `iisutil!??1STRA@@QEAA@XZ` at `0x1800351ec`
- `iisutil!??1STRA@@QEAA@XZ` at `0x1800351fa`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180035208`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18003519e`
- `iisutil!??1STRA@@QEAA@XZ` at `0x1800351c5`
- `iisutil!??1STRA@@QEAA@XZ` at `0x1800351d3`
- `iisutil!??1STRA@@QEAA@XZ` at `0x1800351de`
- `iisutil!??1STRA@@QEAA@XZ` at `0x1800351ec`
- `iisutil!??1STRA@@QEAA@XZ` at `0x1800351fa`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180035208`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180034dbc`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180034de5`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180034dbc`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180034de5`
- `iisutil!PuDbgPrintError` at `0x180034e71`
- `iisutil!PuDbgPrintError` at `0x180034e71`
- `iisutil!?Copy@STRA@@QEAAJPEBD@Z` at `0x180034f15`
- `iisutil!?Copy@STRA@@QEAAJPEBD@Z` at `0x180034f15`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800351ac`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800351ba`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800351ac`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800351ba`

## string_xrefs

- `0x180034e63`: `inetsrv\iis\iisrearc\ftp\server\ftp_protocol\ftp_session.cxx`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
void __fastcall FTP_SESSION::Log(
        const wchar_t **this,
        struct FTP_COMMAND *a2,
        char *a3,
        int a4,
        unsigned int a5,
        unsigned __int16 *a6)
{
  __int64 v9; // r15
  int v10; // eax
  struct FTP_LOGGING *v11; // rsi
  UINT v12; // ebx
  const WCHAR *v13; // rax
  wchar_t **v14; // r13
  int v15; // ebx
  unsigned int v16; // r8d
  __int64 v17; // rax
  int v18; // edx
  int v19; // ebx
  const unsigned __int16 *v20; // r12
  wchar_t *v21; // r13
  const unsigned __int16 *v22; // r15
  __int64 v23; // rbx
  unsigned int v24; // esi
  const unsigned __int16 *v25; // r14
  const unsigned __int16 *v26; // rdi
  const unsigned __int16 *v27; // rax
  unsigned int v30; // [rsp+A8h] [rbp-78h]
  int v31; // [rsp+B0h] [rbp-70h]
  struct FTP_LOGGING *v32; // [rsp+B8h] [rbp-68h] BYREF
  unsigned __int16 *v33; // [rsp+C0h] [rbp-60h]
  FTP_SESSION *v34; // [rsp+C8h] [rbp-58h]
  char v35[8]; // [rsp+D0h] [rbp-50h] BYREF
  __int64 v36; // [rsp+D8h] [rbp-48h]
  wchar_t *String1; // [rsp+E0h] [rbp-40h]
  unsigned __int64 v38; // [rsp+E8h] [rbp-38h]
  unsigned __int64 v39; // [rsp+F0h] [rbp-30h]
  unsigned __int16 *v40; // [rsp+F8h] [rbp-28h]
  _BYTE v41[32]; // [rsp+100h] [rbp-20h] BYREF
  const char *v42; // [rsp+120h] [rbp+0h]
  _BYTE v43[32]; // [rsp+138h] [rbp+18h] BYREF
  const char *v44; // [rsp+158h] [rbp+38h]
  _BYTE v45[32]; // [rsp+170h] [rbp+50h] BYREF
  const char *v46; // [rsp+190h] [rbp+70h]
  _BYTE v47[32]; // [rsp+1A8h] [rbp+88h] BYREF
  const char *v48; // [rsp+1C8h] [rbp+A8h]
  _BYTE v49[32]; // [rsp+1E0h] [rbp+C0h] BYREF
  const char *v50; // [rsp+200h] [rbp+E0h]
  _BYTE v51[32]; // [rsp+218h] [rbp+F8h] BYREF
  const char *v52; // [rsp+238h] [rbp+118h]
  _BYTE v53[32]; // [rsp+250h] [rbp+130h] BYREF
  char *v54; // [rsp+270h] [rbp+150h]
  _BYTE v55[56]; // [rsp+288h] [rbp+168h] BYREF
  _BYTE v56[56]; // [rsp+2C0h] [rbp+1A0h] BYREF
  _OWORD v57[2]; // [rsp+2F8h] [rbp+1D8h] BYREF
  _OWORD v58[2]; // [rsp+318h] [rbp+1F8h] BYREF
  char v59[32]; // [rsp+338h] [rbp+218h] BYREF
  char v60[32]; // [rsp+358h] [rbp+238h] BYREF
  char v61[40]; // [rsp+378h] [rbp+258h] BYREF
  char v62[64]; // [rsp+3A0h] [rbp+280h] BYREF
  char v63[64]; // [rsp+3E0h] [rbp+2C0h] BYREF
  char v64[160]; // [rsp+420h] [rbp+300h] BYREF

  v34 = (FTP_SESSION *)this;
  v33 = a6;
  STRA::STRA((STRA *)v53, v59, 0x20u);
  STRA::STRA((STRA *)v51, v60, 0x20u);
  STRA::STRA((STRA *)v49, v62, 0x40u);
  STRA::STRA((STRA *)v41, v61, 0x20u);
  STRA::STRA((STRA *)v47, v63, 0x40u);
  STRA::STRA((STRA *)v45, v35, 4u);
  memset(v57, 0, sizeof(v57));
  STRU::STRU((STRU *)v56, (unsigned __int16 *)v57, 0x10u);
  memset(v58, 0, sizeof(v58));
  STRU::STRU((STRU *)v55, (unsigned __int16 *)v58, 0x10u);
  STRA::STRA((STRA *)v43, v64, 0xA0u);
  v32 = 0;
  v9 = *((_QWORD *)a2 + 132);
  v36 = v9;
  v31 = atol(a3);
  *((_DWORD *)a2 + 273) = v31;
  v10 = FTP_SESSION::QueryFtpLogging((FTP_SESSION *)this, &v32);
  if ( v10 >= 0 )
  {
    v11 = v32;
    v12 = *(_DWORD *)(*((_QWORD *)v32 + 1) + 156LL) != 0 ? 0xFDE9 : 0;
    ConvertFromUnicode(*((LPCWCH *)this[12] + 6), v12, (struct STRA *)v53);
    v13 = (const WCHAR *)(*(__int64 (__fastcall **)(const wchar_t *))(*(_QWORD *)this[132] + 48LL))(this[132]);
    ConvertFromUnicode(v13, v12, (struct STRA *)v51);
    ConvertFromUnicode(*((LPCWCH *)a2 + 13), v12, (struct STRA *)v45);
    if ( _wcsicmp(*((const wchar_t **)a2 + 13), L"PASS") || !_wcsicmp(this[52], L"Anonymous") )
    {
      v14 = (wchar_t **)((char *)a2 + 344);
      ConvertFromUnicode(*((LPCWCH *)a2 + 43), v12, (struct STRA *)v41);
    }
    else
    {
      STRA::Copy((STRA *)v41, "***");
      v14 = (wchar_t **)((char *)a2 + 344);
    }
    ConvertFromUnicode(*((LPCWCH *)a2 + 82), v12, (struct STRA *)v47);
    ConvertFromUnicode(*(LPCWCH *)(v9 + 904), v12, (struct STRA *)v49);
    ConvertFromUnicode(*((LPCWCH *)a2 + 152), v12, (struct STRA *)v43);
    v15 = *((_DWORD *)a2 + 270);
    v16 = GetTickCount() - v15;
    v17 = *((_QWORD *)a2 + 101);
    if ( v17 )
      v18 = *(_DWORD *)(v17 + 36);
    else
      v18 = 2;
    FTP_LOGGING::Log(
      (__int64)v11,
      v18,
      *(const char **)(v9 + 304),
      (const struct sockaddr *)(*(_QWORD *)(v9 + 1080) + 448LL),
      (struct sockaddr *)(*(_QWORD *)(v9 + 1080) + 320LL),
      v54,
      v52,
      v50,
      *((_QWORD *)a2 + 102),
      *((_QWORD *)a2 + 103),
      v46,
      v42,
      v48,
      v44,
      a3,
      v16,
      a4,
      a5,
      v33);
    v19 = *((_DWORD *)a2 + 270);
    v30 = GetTickCount() - v19;
    v20 = (const unsigned __int16 *)*((_QWORD *)a2 + 82);
    v21 = *v14;
    String1 = (wchar_t *)*((_QWORD *)a2 + 13);
    v38 = *((_QWORD *)a2 + 103);
    v39 = *((_QWORD *)a2 + 102);
    v40 = *(unsigned __int16 **)(v9 + 904);
    v22 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(const wchar_t *))(*(_QWORD *)this[132] + 48LL))(this[132]);
    v23 = v36;
    v24 = ntohs(*(_WORD *)(*(_QWORD *)(v36 + 1080) + 322LL));
    v25 = this[717];
    LODWORD(v23) = ntohs(*(_WORD *)(*(_QWORD *)(v23 + 1080) + 450LL));
    v26 = (const unsigned __int16 *)*((_QWORD *)v34 + 728);
    v27 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(FTP_SESSION *))(*(_QWORD *)v34 + 64LL))(v34);
    FTP_SESSION::CallLogProvider(
      v34,
      v27,
      v26,
      v23,
      v25,
      v24,
      v22,
      v40,
      v39,
      v38,
      String1,
      v21,
      v20,
      v31,
      v30,
      a4,
      a5,
      v33);
  }
  else if ( (g_dwDebugFlags & 0xF) != 0 )
  {
    PuDbgPrintError(
      g_pDebug,
      "inetsrv\\iis\\iisrearc\\ftp\\server\\ftp_protocol\\ftp_session.cxx",
      2841,
      "FTP_SESSION::Log",
      v10,
      "Failed to acquire logging object.\n");
  }
  if ( v32 )
    FTP_LOGGING::DereferenceFtpLogging(v32);
  STRA::~STRA((STRA *)v43);
  STRU::~STRU(v55);
  STRU::~STRU(v56);
  STRA::~STRA((STRA *)v45);
  STRA::~STRA((STRA *)v47);
  STRA::~STRA((STRA *)v41);
  STRA::~STRA((STRA *)v49);
  STRA::~STRA((STRA *)v51);
  STRA::~STRA((STRA *)v53);
}

```

## disassembly

```asm
0x180034cb4  mov     [rsp-8+arg_18], rbx
0x180034cb9  push    rbp
0x180034cba  push    rsi
0x180034cbb  push    rdi
0x180034cbc  push    r12
0x180034cbe  push    r13
0x180034cc0  push    r14
0x180034cc2  push    r15
0x180034cc4  lea     rbp, [rsp-3B0h]
0x180034ccc  sub     rsp, 4D0h
0x180034cd3  mov     rax, cs:__security_cookie
0x180034cda  xor     rax, rsp
0x180034cdd  mov     [rbp+3E0h+var_40], rax
0x180034ce4  mov     [rbp+3E0h+var_460], r9d
0x180034ce8  mov     rbx, r8
0x180034ceb  mov     qword ptr [rbp+3E0h+var_458], rbx
0x180034cef  mov     rdi, rdx
0x180034cf2  mov     r14, rcx
0x180034cf5  mov     [rbp+3E0h+var_438], rcx
0x180034cf9  mov     rax, [rbp+3E0h+arg_28]
0x180034d00  mov     [rbp+3E0h+var_440], rax
0x180034d04  mov     r15d, 20h ; ' '
0x180034d0a  mov     r8d, r15d
0x180034d0d  lea     rdx, [rbp+3E0h+var_1C8]
0x180034d14  lea     rcx, [rbp+3E0h+var_2B0]
0x180034d1b  call    cs:__imp_??0STRA@@QEAA@PEADK@Z; STRA::STRA(char *,ulong)
0x180034d21  nop
0x180034d22  mov     r8d, r15d
0x180034d25  lea     rdx, [rbp+3E0h+var_1A8]
0x180034d2c  lea     rcx, [rbp+3E0h+var_2E8]
0x180034d33  call    cs:__imp_??0STRA@@QEAA@PEADK@Z; STRA::STRA(char *,ulong)
0x180034d39  nop
0x180034d3a  lea     esi, [r15+20h]
0x180034d3e  mov     r8d, esi
0x180034d41  lea     rdx, [rbp+3E0h+var_160]
0x180034d48  lea     rcx, [rbp+3E0h+var_320]
0x180034d4f  call    cs:__imp_??0STRA@@QEAA@PEADK@Z; STRA::STRA(char *,ulong)
0x180034d55  nop
0x180034d56  mov     r8d, r15d
0x180034d59  lea     rdx, [rbp+3E0h+var_188]
0x180034d60  lea     rcx, [rbp+3E0h+var_400]
0x180034d64  call    cs:__imp_??0STRA@@QEAA@PEADK@Z; STRA::STRA(char *,ulong)
0x180034d6a  nop
0x180034d6b  mov     r8d, esi
0x180034d6e  lea     rdx, [rbp+3E0h+var_120]
0x180034d75  lea     rcx, [rbp+3E0h+var_358]
0x180034d7c  call    cs:__imp_??0STRA@@QEAA@PEADK@Z; STRA::STRA(char *,ulong)
0x180034d82  nop
0x180034d83  lea     r8d, [r15-1Ch]
0x180034d87  lea     rdx, [rbp+3E0h+var_430]
0x180034d8b  lea     rcx, [rbp+3E0h+var_390]
0x180034d8f  call    cs:__imp_??0STRA@@QEAA@PEADK@Z; STRA::STRA(char *,ulong)
0x180034d95  nop
0x180034d96  xorps   xmm0, xmm0
0x180034d99  movups  [rbp+3E0h+var_208], xmm0
0x180034da0  movups  [rbp+3E0h+var_1F8], xmm0
0x180034da7  lea     esi, [r15-10h]
0x180034dab  mov     r8d, esi
0x180034dae  lea     rdx, [rbp+3E0h+var_208]
0x180034db5  lea     rcx, [rbp+3E0h+var_240]
0x180034dbc  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180034dc2  nop
0x180034dc3  xorps   xmm0, xmm0
0x180034dc6  movups  [rbp+3E0h+var_1E8], xmm0
0x180034dcd  movups  [rbp+3E0h+var_1D8], xmm0
0x180034dd4  mov     r8d, esi
0x180034dd7  lea     rdx, [rbp+3E0h+var_1E8]
0x180034dde  lea     rcx, [rbp+3E0h+var_278]
0x180034de5  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180034deb  nop
0x180034dec  mov     r8d, 0A0h
0x180034df2  lea     rdx, [rbp+3E0h+var_E0]
0x180034df9  lea     rcx, [rbp+3E0h+var_3C8]
0x180034dfd  call    cs:__imp_??0STRA@@QEAA@PEADK@Z; STRA::STRA(char *,ulong)
0x180034e03  nop
0x180034e04  mov     [rbp+3E0h+var_448], 0
0x180034e0c  mov     r15, [rdi+420h]
0x180034e13  mov     [rbp+3E0h+var_428], r15
0x180034e17  mov     rcx, rbx; String
0x180034e1a  call    cs:__imp_atol
0x180034e20  mov     [rbp+3E0h+var_450], eax
0x180034e23  mov     [rdi+444h], eax
0x180034e29  lea     rdx, [rbp+3E0h+var_448]; struct FTP_LOGGING **
0x180034e2d  mov     rcx, r14; this
0x180034e30  call    ?QueryFtpLogging@FTP_SESSION@@AEAAJPEAPEAVFTP_LOGGING@@@Z; FTP_SESSION::QueryFtpLogging(FTP_LOGGING * *)
0x180034e35  test    eax, eax
0x180034e37  jns     short loc_180034E7C
0x180034e39  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180034e40  jz      loc_180035188
0x180034e46  lea     rcx, aFailedToAcquir; "Failed to acquire logging object.\n"
0x180034e4d  mov     qword ptr [rsp+500h+var_4D8], rcx
0x180034e52  mov     dword ptr [rsp+500h+var_4E0], eax
0x180034e56  lea     r9, aFtpSessionLog; "FTP_SESSION::Log"
0x180034e5d  mov     r8d, 0B19h
0x180034e63  lea     rdx, aInetsrvIisIisr_30; "inetsrv\\iis\\iisrearc\\ftp\\server\\ft"...
0x180034e6a  mov     rcx, cs:g_pDebug
0x180034e71  call    cs:__imp_PuDbgPrintError
0x180034e77  jmp     loc_180035188
0x180034e7c  mov     rsi, [rbp+3E0h+var_448]
0x180034e80  mov     rax, [rsi+8]
0x180034e84  mov     ecx, [rax+9Ch]
0x180034e8a  neg     ecx
0x180034e8c  sbb     ebx, ebx
0x180034e8e  and     ebx, 0FDE9h
0x180034e94  mov     rcx, [r14+60h]
0x180034e98  lea     r8, [rbp+3E0h+var_2B0]; struct STRA *
0x180034e9f  mov     edx, ebx; CodePage
0x180034ea1  mov     rcx, [rcx+30h]; lpWideCharStr
0x180034ea5  call    ?ConvertFromUnicode@@YAJPEBGKPEAVSTRA@@@Z; ConvertFromUnicode(ushort const *,ulong,STRA *)
0x180034eaa  mov     rcx, [r14+420h]
0x180034eb1  mov     rax, [rcx]
0x180034eb4  mov     rax, [rax+30h]
0x180034eb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034ebd  mov     rcx, rax; lpWideCharStr
0x180034ec0  lea     r8, [rbp+3E0h+var_2E8]; struct STRA *
0x180034ec7  mov     edx, ebx; CodePage
0x180034ec9  call    ?ConvertFromUnicode@@YAJPEBGKPEAVSTRA@@@Z; ConvertFromUnicode(ushort const *,ulong,STRA *)
0x180034ece  lea     r8, [rbp+3E0h+var_390]; struct STRA *
0x180034ed2  mov     edx, ebx; CodePage
0x180034ed4  mov     rcx, [rdi+68h]; lpWideCharStr
0x180034ed8  call    ?ConvertFromUnicode@@YAJPEBGKPEAVSTRA@@@Z; ConvertFromUnicode(ushort const *,ulong,STRA *)
0x180034edd  lea     rdx, aPass_0; "PASS"
0x180034ee4  mov     rcx, [rdi+68h]; String1
0x180034ee8  call    cs:__imp__wcsicmp
0x180034eee  test    eax, eax
0x180034ef0  jnz     short loc_180034F24
0x180034ef2  lea     rdx, aAnonymous; "Anonymous"
0x180034ef9  mov     rcx, [r14+1A0h]; String1
0x180034f00  call    cs:__imp__wcsicmp
0x180034f06  test    eax, eax
0x180034f08  jz      short loc_180034F24
0x180034f0a  lea     rdx, asc_180053DFC; "***"
0x180034f11  lea     rcx, [rbp+3E0h+var_400]
0x180034f15  call    cs:__imp_?Copy@STRA@@QEAAJPEBD@Z; STRA::Copy(char const *)
0x180034f1b  lea     r13, [rdi+158h]
0x180034f22  jmp     short loc_180034F3A
0x180034f24  lea     r13, [rdi+158h]
0x180034f2b  lea     r8, [rbp+3E0h+var_400]; struct STRA *
0x180034f2f  mov     edx, ebx; CodePage
0x180034f31  mov     rcx, [r13+0]; lpWideCharStr
0x180034f35  call    ?ConvertFromUnicode@@YAJPEBGKPEAVSTRA@@@Z; ConvertFromUnicode(ushort const *,ulong,STRA *)
0x180034f3a  lea     r8, [rbp+3E0h+var_358]; struct STRA *
0x180034f41  mov     edx, ebx; CodePage
0x180034f43  mov     rcx, [rdi+290h]; lpWideCharStr
0x180034f4a  call    ?ConvertFromUnicode@@YAJPEBGKPEAVSTRA@@@Z; ConvertFromUnicode(ushort const *,ulong,STRA *)
0x180034f4f  lea     r8, [rbp+3E0h+var_320]; struct STRA *
0x180034f56  mov     edx, ebx; CodePage
0x180034f58  mov     rcx, [r15+388h]; lpWideCharStr
0x180034f5f  call    ?ConvertFromUnicode@@YAJPEBGKPEAVSTRA@@@Z; ConvertFromUnicode(ushort const *,ulong,STRA *)
0x180034f64  lea     r8, [rbp+3E0h+var_3C8]; struct STRA *
0x180034f68  mov     edx, ebx; CodePage
0x180034f6a  mov     rcx, [rdi+4C0h]; lpWideCharStr
0x180034f71  call    ?ConvertFromUnicode@@YAJPEBGKPEAVSTRA@@@Z; ConvertFromUnicode(ushort const *,ulong,STRA *)
0x180034f76  mov     ebx, [rdi+438h]
0x180034f7c  call    cs:__imp_GetTickCount
0x180034f82  mov     r8d, eax
0x180034f85  sub     r8d, ebx
0x180034f88  mov     r10, [rbp+3E0h+var_3A8]
0x180034f8c  mov     r11, [rbp+3E0h+var_338]
0x180034f93  mov     rbx, [rbp+3E0h+var_3E0]
0x180034f97  mov     r12, [rbp+3E0h+var_370]
0x180034f9b  mov     r9, [r15+438h]
0x180034fa2  mov     rax, [rdi+328h]
0x180034fa9  test    rax, rax
0x180034fac  jz      short loc_180034FB3
0x180034fae  mov     edx, [rax+24h]
0x180034fb1  jmp     short loc_180034FB8
0x180034fb3  mov     edx, 2
0x180034fb8  lea     rax, [r9+140h]
0x180034fbf  add     r9, 1C0h
0x180034fc6  mov     rcx, [rbp+3E0h+var_440]
0x180034fca  mov     [rsp+500h+var_470], rcx
0x180034fd2  mov     ecx, [rbp+3E0h+arg_20]
0x180034fd8  mov     dword ptr [rsp+500h+var_478], ecx
0x180034fdf  mov     ecx, [rbp+3E0h+var_460]
0x180034fe2  mov     [rsp+500h+var_480], ecx
0x180034fe9  mov     [rsp+500h+var_488], r8d
0x180034fee  mov     rcx, qword ptr [rbp+3E0h+var_458]
0x180034ff2  mov     qword ptr [rsp+500h+var_490], rcx
0x180034ff7  mov     qword ptr [rsp+500h+var_498], r10
0x180034ffc  mov     [rsp+500h+var_4A0], r11
0x180035001  mov     [rsp+500h+var_4A8], rbx
0x180035006  mov     [rsp+500h+String1], r12
0x18003500b  mov     rcx, [rdi+338h]
0x180035012  mov     [rsp+500h+var_4B8], rcx
0x180035017  mov     rcx, [rdi+330h]
0x18003501e  mov     [rsp+500h+var_4C0], rcx
0x180035023  mov     rcx, [rbp+3E0h+var_300]
0x18003502a  mov     [rsp+500h+var_4C8], rcx
0x18003502f  mov     rcx, [rbp+3E0h+var_2C8]
0x180035036  mov     [rsp+500h+var_4D0], rcx
0x18003503b  mov     rcx, [rbp+3E0h+var_290]
0x180035042  mov     qword ptr [rsp+500h+var_4D8], rcx
0x180035047  mov     [rsp+500h+var_4E0], rax
0x18003504c  mov     r8, [r15+130h]
0x180035053  mov     rcx, rsi
0x180035056  call    ?Log@FTP_LOGGING@@QEAAJW4_LOG_ENTRY_TYPE@@PEBDPEBUsockaddr@@2111_K311111KJKPEBG@Z; FTP_LOGGING::Log(_LOG_ENTRY_TYPE,char const *,sockaddr const *,sockaddr const *,char const *,char const *,char const *,unsigned __int64,unsigned __int64,char const *,char const *,char const *,char const *,char const *,ulong,long,ulong,ushort const *)
0x18003505b  mov     ebx, [rdi+438h]
0x180035061  call    cs:__imp_GetTickCount
0x180035067  sub     eax, ebx
0x180035069  mov     [rbp+3E0h+var_458], eax
0x18003506c  mov     r12, [rdi+290h]
0x180035073  mov     r13, [r13+0]
0x180035077  mov     rax, [rdi+68h]
0x18003507b  mov     [rbp+3E0h+var_420], rax
0x18003507f  mov     rax, [rdi+338h]
0x180035086  mov     [rbp+3E0h+var_418], rax
0x18003508a  mov     rax, [rdi+330h]
0x180035091  mov     [rbp+3E0h+var_410], rax
0x180035095  mov     rax, [r15+388h]
0x18003509c  mov     [rbp+3E0h+var_408], rax
0x1800350a0  mov     rdx, [r14+420h]
0x1800350a7  mov     rcx, [rdx]
0x1800350aa  mov     rax, [rcx+30h]
0x1800350ae  mov     rcx, rdx
0x1800350b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800350b6  mov     r15, rax
0x1800350b9  mov     rbx, [rbp+3E0h+var_428]
0x1800350bd  mov     rcx, [rbx+438h]
0x1800350c4  movzx   ecx, word ptr [rcx+142h]; netshort
0x1800350cb  call    cs:__imp_ntohs
0x1800350d1  movzx   esi, ax
0x1800350d4  mov     r14, [r14+1668h]
0x1800350db  mov     rcx, [rbx+438h]
0x1800350e2  movzx   ecx, word ptr [rcx+1C2h]; netshort
0x1800350e9  call    cs:__imp_ntohs
0x1800350ef  movzx   ebx, ax
0x1800350f2  mov     rdx, [rbp+3E0h+var_438]
0x1800350f6  mov     rdi, [rdx+16C0h]
0x1800350fd  mov     rcx, [rdx]
0x180035100  mov     rax, [rcx+40h]
0x180035104  mov     rcx, rdx
0x180035107  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003510c  mov     rcx, [rbp+3E0h+var_440]
0x180035110  mov     [rsp+500h+var_478], rcx; unsigned __int16 *
0x180035118  mov     ecx, [rbp+3E0h+arg_20]
0x18003511e  mov     [rsp+500h+var_480], ecx; unsigned int
0x180035125  mov     ecx, [rbp+3E0h+var_460]
0x180035128  mov     [rsp+500h+var_488], ecx; int
0x18003512c  mov     edx, [rbp+3E0h+var_458]
0x18003512f  mov     [rsp+500h+var_490], edx; unsigned int
0x180035133  mov     ecx, [rbp+3E0h+var_450]
0x180035136  mov     [rsp+500h+var_498], ecx; unsigned int
0x18003513a  mov     [rsp+500h+var_4A0], r12; unsigned __int16 *
0x18003513f  mov     [rsp+500h+var_4A8], r13; wchar_t *
0x180035144  mov     rdx, [rbp+3E0h+var_420]
0x180035148  mov     [rsp+500h+String1], rdx; String1
0x18003514d  mov     rdx, [rbp+3E0h+var_418]
0x180035151  mov     [rsp+500h+var_4B8], rdx; unsigned __int64
0x180035156  mov     rdx, [rbp+3E0h+var_410]
0x18003515a  mov     [rsp+500h+var_4C0], rdx; unsigned __int64
0x18003515f  mov     rdx, [rbp+3E0h+var_408]
0x180035163  mov     [rsp+500h+var_4C8], rdx; unsigned __int16 *
0x180035168  mov     [rsp+500h+var_4D0], r15; unsigned __int16 *
0x18003516d  mov     [rsp+500h+var_4D8], esi; unsigned int
0x180035171  mov     [rsp+500h+var_4E0], r14; unsigned __int16 *
0x180035176  mov     r9d, ebx; unsigned int
0x180035179  mov     r8, rdi; unsigned __int16 *
0x18003517c  mov     rdx, rax; unsigned __int16 *
0x18003517f  mov     rcx, [rbp+3E0h+var_438]; this
0x180035183  call    ?CallLogProvider@FTP_SESSION@@QEAAJPEBG0K0K00_K1000KKJK0@Z; FTP_SESSION::CallLogProvider(ushort const *,ushort const *,ulong,ushort const *,ulong,ushort const *,ushort const *,unsigned __int64,unsigned __int64,ushort const *,ushort const *,ushort const *,ulong,ulong,long,ulong,ushort const *)
0x180035188  mov     rax, [rbp+3E0h+var_448]
0x18003518c  test    rax, rax
0x18003518f  jz      short loc_18003519A
0x180035191  mov     rcx, rax; this
0x180035194  call    ?DereferenceFtpLogging@FTP_LOGGING@@QEAAXXZ; FTP_LOGGING::DereferenceFtpLogging(void)
0x180035199  nop
0x18003519a  lea     rcx, [rbp+3E0h+var_3C8]
0x18003519e  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x1800351a4  nop
0x1800351a5  lea     rcx, [rbp+3E0h+var_278]
0x1800351ac  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x1800351b2  nop
0x1800351b3  lea     rcx, [rbp+3E0h+var_240]
0x1800351ba  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x1800351c0  nop
0x1800351c1  lea     rcx, [rbp+3E0h+var_390]
0x1800351c5  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x1800351cb  nop
0x1800351cc  lea     rcx, [rbp+3E0h+var_358]
0x1800351d3  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x1800351d9  nop
0x1800351da  lea     rcx, [rbp+3E0h+var_400]
0x1800351de  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x1800351e4  nop
0x1800351e5  lea     rcx, [rbp+3E0h+var_320]
0x1800351ec  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x1800351f2  nop
0x1800351f3  lea     rcx, [rbp+3E0h+var_2E8]
0x1800351fa  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x180035200  nop
0x180035201  lea     rcx, [rbp+3E0h+var_2B0]
0x180035208  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x18003520e  mov     rcx, [rbp+3E0h+var_40]
0x180035215  xor     rcx, rsp; StackCookie
0x180035218  call    __security_check_cookie
0x18003521d  mov     rbx, [rsp+500h+arg_18]
0x180035225  add     rsp, 4D0h
0x18003522c  pop     r15
0x18003522e  pop     r14
  ... truncated ...
```
