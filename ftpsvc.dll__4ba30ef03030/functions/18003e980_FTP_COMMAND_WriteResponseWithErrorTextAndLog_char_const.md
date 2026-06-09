# FTP_COMMAND::WriteResponseWithErrorTextAndLog(char const *)

- ea: `0x18003e980`
- end: `0x18003ec18`
- name: `?WriteResponseWithErrorTextAndLog@FTP_COMMAND@@QEAAJPEBD@Z`
- size: `664`
- prototype: `__int64 __fastcall(FTP_COMMAND *__hidden this, const char *)`
- caller_count: `17`
- callee_count: `9`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18003860c`
- `0x180038ec0`
- `0x180038f98`
- `0x180039578`
- `0x1800396b0`
- `0x180039b14`
- `0x18003add4`
- `0x18003b5b0`
- `0x18003b938`
- `0x18003ba60`
- `0x18003bb70`
- `0x18003bd0c`
- `0x18003c024`
- `0x18003c19c`
- `0x18003c51c`
- `0x18003dbac`
- `0x180042dc0`

## callees

- `0x180009090`
- `0x18002b84c`
- `0x180034cb4`
- `0x1800366ec`
- `0x180036ebc`
- `0x180038ac0`
- `0x18003e708`
- `0x18003e980`
- `0x180047050`

## import_xrefs

- `KERNEL32!LocalFree` at `0x18003ebda`
- `KERNEL32!LocalFree` at `0x18003ebda`
- `KERNEL32!FormatMessageA` at `0x18003ea33`
- `KERNEL32!FormatMessageA` at `0x18003ea33`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x18003e9cc`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x18003e9cc`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18003ebe8`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18003ebe8`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x18003eb20`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x18003eb20`
- `iisutil!WriteRefTraceLog` at `0x18003eb03`
- `iisutil!WriteRefTraceLog` at `0x18003eb03`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall FTP_COMMAND::WriteResponseWithErrorTextAndLog(FTP_COMMAND *this, const char *a2)
{
  int v4; // r13d
  signed int v5; // r14d
  signed int v6; // r8d
  _WORD *v7; // rcx
  FTP_SESSION *v8; // rcx
  struct FTP_SITE_CONFIG *ReferencedSiteConfig; // rax
  volatile signed __int32 *v10; // rdi
  int v11; // r15d
  unsigned __int32 v12; // esi
  FTP_SESSION *v13; // rcx
  __int64 v14; // rdx
  CHAR Buffer[8]; // [rsp+40h] [rbp-69h] BYREF
  _BYTE v17[32]; // [rsp+48h] [rbp-61h] BYREF
  __int64 v18; // [rsp+68h] [rbp-41h]
  char v19[64]; // [rsp+80h] [rbp-29h] BYREF

  *(_QWORD *)Buffer = String;
  v4 = 0;
  STRA::STRA((STRA *)v17, v19, 0x40u);
  if ( *((_DWORD *)this + 274) == 14
    || *((_DWORD *)this + 274) == 15
    || *((_DWORD *)this + 274) == 20
    || *((_DWORD *)this + 274) == 39
    || *((_DWORD *)this + 274) == 50 )
  {
    v5 = ConvertFromUnicode(*((LPCWCH *)this + 138), *(_DWORD *)(*((_QWORD *)this + 132) + 4788LL), (struct STRA *)v17);
    if ( v5 >= 0 )
      *(_QWORD *)Buffer = v18;
  }
  else
  {
    v5 = 0;
    v6 = *((_DWORD *)this + 292);
    if ( v6 < 0 && (v6 & 0x1FFF0000) == 0x70000 )
      v6 = (unsigned __int16)v6;
    if ( FormatMessageA(0x13FFu, 0, v6, 0x409u, Buffer, 0, 0) )
      v4 = 1;
    else
      *(_QWORD *)Buffer = String;
  }
  v7 = (_WORD *)*((_QWORD *)this + 138);
  if ( !v7 )
    goto LABEL_25;
  if ( !*v7 )
    goto LABEL_25;
  v8 = (FTP_SESSION *)*((_QWORD *)this + 132);
  if ( !*((_DWORD *)v8 + 1409) )
    goto LABEL_25;
  ReferencedSiteConfig = FTP_SESSION::GetReferencedSiteConfig(v8);
  v10 = (volatile signed __int32 *)ReferencedSiteConfig;
  if ( !ReferencedSiteConfig )
    goto LABEL_25;
  v11 = 0;
  if ( *((_DWORD *)ReferencedSiteConfig + 173) )
  {
    FTP_SESSION::WriteResponseHelper(*((FTP_SESSION **)this + 132), 9u, a2, *(const char **)Buffer, 0);
    FTP_COMMAND::WriteResponseErrorDetails(this, a2);
    v11 = 1;
  }
  v12 = _InterlockedDecrement(v10);
  if ( FTP_SITE_CONFIG::sm_pRefTraceLog )
    WriteRefTraceLog(FTP_SITE_CONFIG::sm_pRefTraceLog, v12);
  if ( !v12 )
  {
    FTP_SITE_CONFIG::~FTP_SITE_CONFIG((FTP_SITE_CONFIG *)v10);
    ALLOC_CACHE_HANDLER::Free((ALLOC_CACHE_HANDLER *)FTP_SITE_CONFIG::sm_pAllocHandler, (void *)v10);
  }
  if ( !v11 )
LABEL_25:
    FTP_SESSION::WriteResponseHelper(*((FTP_SESSION **)this + 132), 0xBu, a2, *(const char **)Buffer, 0);
  v13 = (FTP_SESSION *)*((_QWORD *)this + 132);
  v14 = *((_QWORD *)v13 + 9);
  *((_QWORD *)this + 102) = *((_QWORD *)v13 + 8)
                          + *((_QWORD *)v13 + 10)
                          - *((_QWORD *)this + 106)
                          - *((_QWORD *)this + 105);
  *((_QWORD *)this + 103) = v14 + *((_QWORD *)this + 104) - *((_QWORD *)this + 107);
  FTP_SESSION::SetLastFtpCommand(v13, *((const char **)this + 6), *((_DWORD *)this + 292), *((_DWORD *)this + 274));
  FTP_SESSION::Log(
    *((FTP_SESSION **)this + 132),
    this,
    a2,
    *((_DWORD *)this + 292),
    *((_DWORD *)this + 274),
    *((const unsigned __int16 **)this + 138));
  if ( v4 )
  {
    LocalFree(*(HLOCAL *)Buffer);
    *(_QWORD *)Buffer = 0;
  }
  STRA::~STRA((STRA *)v17);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18003e980  mov     [rsp-8+arg_10], rbx
0x18003e985  push    rbp
0x18003e986  push    rsi
0x18003e987  push    rdi
0x18003e988  push    r12
0x18003e98a  push    r13
0x18003e98c  push    r14
0x18003e98e  push    r15
0x18003e990  lea     rbp, [rsp-27h]
0x18003e995  sub     rsp, 0D0h
0x18003e99c  mov     rax, cs:__security_cookie
0x18003e9a3  xor     rax, rsp
0x18003e9a6  mov     [rbp+57h+var_40], rax
0x18003e9aa  mov     r12, rdx
0x18003e9ad  mov     rbx, rcx
0x18003e9b0  lea     rdi, String
0x18003e9b7  mov     qword ptr [rbp+57h+Buffer], rdi
0x18003e9bb  xor     esi, esi
0x18003e9bd  mov     r13d, esi
0x18003e9c0  lea     r8d, [rsi+40h]
0x18003e9c4  lea     rdx, [rbp+57h+var_80]
0x18003e9c8  lea     rcx, [rbp+57h+var_B8]
0x18003e9cc  call    cs:__imp_??0STRA@@QEAA@PEADK@Z; STRA::STRA(char *,ulong)
0x18003e9d2  nop
0x18003e9d3  mov     ecx, [rbx+448h]
0x18003e9d9  sub     ecx, 0Eh
0x18003e9dc  jz      short loc_18003EA4B
0x18003e9de  sub     ecx, 1
0x18003e9e1  jz      short loc_18003EA4B
0x18003e9e3  sub     ecx, 5
0x18003e9e6  jz      short loc_18003EA4B
0x18003e9e8  sub     ecx, 13h
0x18003e9eb  jz      short loc_18003EA4B
0x18003e9ed  cmp     ecx, 0Bh
0x18003e9f0  jz      short loc_18003EA4B
0x18003e9f2  mov     r14d, esi
0x18003e9f5  mov     r8d, [rbx+490h]
0x18003e9fc  test    r8d, r8d
0x18003e9ff  jns     short loc_18003EA14
0x18003ea01  mov     eax, r8d
0x18003ea04  and     eax, 1FFF0000h
0x18003ea09  cmp     eax, 70000h
0x18003ea0e  jnz     short loc_18003EA14
0x18003ea10  movzx   r8d, r8w; dwMessageId
0x18003ea14  mov     [rsp+100h+Arguments], rsi; Arguments
0x18003ea19  mov     [rsp+100h+nSize], esi; nSize
0x18003ea1d  lea     rax, [rbp+57h+Buffer]
0x18003ea21  mov     [rsp+100h+lpBuffer], rax; lpBuffer
0x18003ea26  xor     edx, edx; lpSource
0x18003ea28  mov     ecx, 13FFh; dwFlags
0x18003ea2d  mov     r9d, 409h; dwLanguageId
0x18003ea33  call    cs:__imp_FormatMessageA
0x18003ea39  test    eax, eax
0x18003ea3b  jnz     short loc_18003EA43
0x18003ea3d  mov     qword ptr [rbp+57h+Buffer], rdi
0x18003ea41  jmp     short loc_18003EA77
0x18003ea43  mov     r13d, 1
0x18003ea49  jmp     short loc_18003EA77
0x18003ea4b  mov     rdx, [rbx+420h]
0x18003ea52  lea     r8, [rbp+57h+var_B8]; struct STRA *
0x18003ea56  mov     edx, [rdx+12B4h]; CodePage
0x18003ea5c  mov     rcx, [rbx+450h]; lpWideCharStr
0x18003ea63  call    ?ConvertFromUnicode@@YAJPEBGKPEAVSTRA@@@Z; ConvertFromUnicode(ushort const *,ulong,STRA *)
0x18003ea68  mov     r14d, eax
0x18003ea6b  test    eax, eax
0x18003ea6d  js      short loc_18003EA77
0x18003ea6f  mov     rcx, [rbp+57h+var_98]
0x18003ea73  mov     qword ptr [rbp+57h+Buffer], rcx
0x18003ea77  mov     rcx, [rbx+450h]
0x18003ea7e  test    rcx, rcx
0x18003ea81  jz      loc_18003EB2E
0x18003ea87  cmp     [rcx], si
0x18003ea8a  jz      loc_18003EB2E
0x18003ea90  mov     rcx, [rbx+420h]; this
0x18003ea97  cmp     [rcx+1604h], esi
0x18003ea9d  jz      loc_18003EB2E
0x18003eaa3  call    ?GetReferencedSiteConfig@FTP_SESSION@@QEAAPEAVFTP_SITE_CONFIG@@XZ; FTP_SESSION::GetReferencedSiteConfig(void)
0x18003eaa8  mov     rdi, rax
0x18003eaab  test    rax, rax
0x18003eaae  jz      short loc_18003EB2E
0x18003eab0  mov     r15d, esi
0x18003eab3  cmp     [rax+2B4h], esi
0x18003eab9  jz      short loc_18003EAE9
0x18003eabb  mov     [rsp+100h+lpBuffer], rsi; char *
0x18003eac0  mov     r9, qword ptr [rbp+57h+Buffer]; char *
0x18003eac4  mov     r8, r12; char *
0x18003eac7  mov     edx, 9; unsigned int
0x18003eacc  mov     rcx, [rbx+420h]; this
0x18003ead3  call    ?WriteResponseHelper@FTP_SESSION@@QEAAJKPEBD0PEAD@Z; FTP_SESSION::WriteResponseHelper(ulong,char const *,char const *,char *)
0x18003ead8  mov     rdx, r12; char *
0x18003eadb  mov     rcx, rbx; this
0x18003eade  call    ?WriteResponseErrorDetails@FTP_COMMAND@@QEAAJPEBD@Z; FTP_COMMAND::WriteResponseErrorDetails(char const *)
0x18003eae3  mov     r15d, 1
0x18003eae9  or      esi, 0FFFFFFFFh
0x18003eaec  lock xadd [rdi], esi
0x18003eaf0  dec     esi
0x18003eaf2  mov     rcx, cs:?sm_pRefTraceLog@FTP_SITE_CONFIG@@0PEAU_TRACE_LOG@@EA; _TRACE_LOG * FTP_SITE_CONFIG::sm_pRefTraceLog
0x18003eaf9  test    rcx, rcx
0x18003eafc  jz      short loc_18003EB09
0x18003eafe  mov     r8, rdi
0x18003eb01  mov     edx, esi
0x18003eb03  call    cs:__imp_WriteRefTraceLog
0x18003eb09  test    esi, esi
0x18003eb0b  jnz     short loc_18003EB27
0x18003eb0d  mov     rcx, rdi; this
0x18003eb10  call    ??1FTP_SITE_CONFIG@@QEAA@XZ; FTP_SITE_CONFIG::~FTP_SITE_CONFIG(void)
0x18003eb15  nop
0x18003eb16  mov     rdx, rdi
0x18003eb19  mov     rcx, cs:?sm_pAllocHandler@FTP_SITE_CONFIG@@0PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * FTP_SITE_CONFIG::sm_pAllocHandler
0x18003eb20  call    cs:__imp_?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z; ALLOC_CACHE_HANDLER::Free(void *)
0x18003eb26  nop
0x18003eb27  xor     esi, esi
0x18003eb29  test    r15d, r15d
0x18003eb2c  jnz     short loc_18003EB4B
0x18003eb2e  mov     [rsp+100h+lpBuffer], rsi; char *
0x18003eb33  mov     r9, qword ptr [rbp+57h+Buffer]; char *
0x18003eb37  mov     r8, r12; char *
0x18003eb3a  mov     edx, 0Bh; unsigned int
0x18003eb3f  mov     rcx, [rbx+420h]; this
0x18003eb46  call    ?WriteResponseHelper@FTP_SESSION@@QEAAJKPEBD0PEAD@Z; FTP_SESSION::WriteResponseHelper(ulong,char const *,char const *,char *)
0x18003eb4b  mov     rcx, [rbx+420h]; this
0x18003eb52  mov     rdx, [rcx+48h]
0x18003eb56  mov     rax, [rcx+50h]
0x18003eb5a  sub     rax, [rbx+350h]
0x18003eb61  sub     rax, [rbx+348h]
0x18003eb68  add     rax, [rcx+40h]
0x18003eb6c  mov     [rbx+330h], rax
0x18003eb73  mov     rax, [rbx+340h]
0x18003eb7a  sub     rax, [rbx+358h]
0x18003eb81  add     rax, rdx
0x18003eb84  mov     [rbx+338h], rax
0x18003eb8b  mov     r9d, [rbx+448h]; unsigned int
0x18003eb92  mov     r8d, [rbx+490h]; int
0x18003eb99  mov     rdx, [rbx+30h]; char *
0x18003eb9d  call    ?SetLastFtpCommand@FTP_SESSION@@QEAAXPEBDJK@Z; FTP_SESSION::SetLastFtpCommand(char const *,long,ulong)
0x18003eba2  mov     rax, [rbx+450h]
0x18003eba9  mov     qword ptr [rsp+100h+nSize], rax; unsigned __int16 *
0x18003ebae  mov     eax, [rbx+448h]
0x18003ebb4  mov     dword ptr [rsp+100h+lpBuffer], eax; unsigned int
0x18003ebb8  mov     r9d, [rbx+490h]; int
0x18003ebbf  mov     r8, r12; char *
0x18003ebc2  mov     rdx, rbx; struct FTP_COMMAND *
0x18003ebc5  mov     rcx, [rbx+420h]; this
0x18003ebcc  call    ?Log@FTP_SESSION@@QEAAXPEAVFTP_COMMAND@@PEBDJKPEBG@Z; FTP_SESSION::Log(FTP_COMMAND *,char const *,long,ulong,ushort const *)
0x18003ebd1  test    r13d, r13d
0x18003ebd4  jz      short loc_18003EBE4
0x18003ebd6  mov     rcx, qword ptr [rbp+57h+Buffer]; hMem
0x18003ebda  call    cs:__imp_LocalFree
0x18003ebe0  mov     qword ptr [rbp+57h+Buffer], rsi
0x18003ebe4  lea     rcx, [rbp+57h+var_B8]
0x18003ebe8  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x18003ebee  mov     eax, r14d
0x18003ebf1  mov     rcx, [rbp+57h+var_40]
0x18003ebf5  xor     rcx, rsp; StackCookie
0x18003ebf8  call    __security_check_cookie
0x18003ebfd  mov     rbx, [rsp+100h+arg_10]
0x18003ec05  add     rsp, 0D0h
0x18003ec0c  pop     r15
0x18003ec0e  pop     r14
0x18003ec10  pop     r13
0x18003ec12  pop     r12
0x18003ec14  pop     rdi
0x18003ec15  pop     rsi
0x18003ec16  pop     rbp
0x18003ec17  retn
```
