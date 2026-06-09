# FTP_COMMAND::WriteResponseErrorDetails(char const *)

- ea: `0x18003e708`
- end: `0x18003e977`
- name: `?WriteResponseErrorDetails@FTP_COMMAND@@QEAAJPEBD@Z`
- size: `623`
- prototype: `int(FTP_COMMAND *__hidden this, const char *)`
- caller_count: `3`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18003e3c8`
- `0x18003e564`
- `0x18003e980`

## callees

- `0x180009090`
- `0x18002b84c`
- `0x180036ebc`
- `0x180038ac0`
- `0x18003e708`
- `0x180047050`

## import_xrefs

- `KERNEL32!LocalFree` at `0x18003e926`
- `KERNEL32!LocalFree` at `0x18003e926`
- `KERNEL32!FormatMessageA` at `0x18003e7d5`
- `KERNEL32!FormatMessageA` at `0x18003e7d5`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x18003e75d`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x18003e76f`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x18003e75d`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x18003e76f`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18003e939`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18003e945`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18003e939`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18003e945`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x18003e8ec`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x18003e8ec`
- `iisutil!WriteRefTraceLog` at `0x18003e8cf`
- `iisutil!WriteRefTraceLog` at `0x18003e8cf`
- `iisutil!?Append@STRA@@QEAAJPEBD@Z` at `0x18003e7ff`
- `iisutil!?Append@STRA@@QEAAJPEBD@Z` at `0x18003e819`
- `iisutil!?Append@STRA@@QEAAJPEBD@Z` at `0x18003e835`
- `iisutil!?Append@STRA@@QEAAJPEBD@Z` at `0x18003e86d`
- `iisutil!?Append@STRA@@QEAAJPEBD@Z` at `0x18003e885`
- `iisutil!?Append@STRA@@QEAAJPEBD@Z` at `0x18003e7ff`
- `iisutil!?Append@STRA@@QEAAJPEBD@Z` at `0x18003e819`
- `iisutil!?Append@STRA@@QEAAJPEBD@Z` at `0x18003e835`
- `iisutil!?Append@STRA@@QEAAJPEBD@Z` at `0x18003e86d`
- `iisutil!?Append@STRA@@QEAAJPEBD@Z` at `0x18003e885`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall FTP_COMMAND::WriteResponseErrorDetails(FTP_COMMAND *this, const char *a2)
{
  signed int v4; // ebx
  int v5; // r15d
  int v6; // r12d
  struct FTP_SITE_CONFIG *ReferencedSiteConfig; // rsi
  signed int v8; // r8d
  unsigned __int32 v9; // edi
  CHAR Buffer[8]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v12[32]; // [rsp+48h] [rbp-B8h] BYREF
  char *v13; // [rsp+68h] [rbp-98h]
  _BYTE v14[32]; // [rsp+80h] [rbp-80h] BYREF
  const char *v15; // [rsp+A0h] [rbp-60h]
  char v16[128]; // [rsp+C0h] [rbp-40h] BYREF
  char v17[128]; // [rsp+140h] [rbp+40h] BYREF

  *(_QWORD *)Buffer = 0;
  v4 = 0;
  v5 = 0;
  STRA::STRA((STRA *)v12, v16, 0x80u);
  STRA::STRA((STRA *)v14, v17, 0x80u);
  v6 = 0;
  ReferencedSiteConfig = FTP_SESSION::GetReferencedSiteConfig(*((FTP_SESSION **)this + 132));
  if ( *((_DWORD *)ReferencedSiteConfig + 173) )
  {
    v8 = *((_DWORD *)this + 292);
    if ( v8 < 0 && (v8 & 0x1FFF0000) == 0x70000 )
      v8 = (unsigned __int16)v8;
    if ( FormatMessageA(0x13FFu, 0, v8, 0x409u, Buffer, 0, 0) )
      v5 = 1;
    else
      *(_QWORD *)Buffer = String;
    v4 = STRA::Append((STRA *)v12, "Win32 error:   ");
    if ( v4 >= 0 )
    {
      v4 = STRA::Append((STRA *)v12, *(const char **)Buffer);
      if ( v4 >= 0 )
      {
        v4 = STRA::Append((STRA *)v12, "\r\nError details: ");
        if ( v4 >= 0 )
        {
          v4 = ConvertFromUnicode(
                 *((LPCWCH *)this + 138),
                 *(_DWORD *)(*((_QWORD *)this + 132) + 4788LL),
                 (struct STRA *)v14);
          if ( v4 >= 0 )
          {
            v4 = STRA::Append((STRA *)v12, v15);
            if ( v4 >= 0 )
            {
              v4 = STRA::Append((STRA *)v12, "\r\nEnd");
              if ( v4 >= 0 )
              {
                FTP_SESSION::WriteResponseHelper(*((FTP_SESSION **)this + 132), 26, a2, v13, 0);
                v6 = 1;
              }
            }
          }
        }
      }
    }
  }
  v9 = _InterlockedDecrement((volatile signed __int32 *)ReferencedSiteConfig);
  if ( FTP_SITE_CONFIG::sm_pRefTraceLog )
    WriteRefTraceLog(FTP_SITE_CONFIG::sm_pRefTraceLog, v9);
  if ( !v9 )
  {
    FTP_SITE_CONFIG::~FTP_SITE_CONFIG(ReferencedSiteConfig);
    ALLOC_CACHE_HANDLER::Free((ALLOC_CACHE_HANDLER *)FTP_SITE_CONFIG::sm_pAllocHandler, ReferencedSiteConfig);
  }
  if ( !v6 )
    FTP_SESSION::WriteResponseHelper(*((FTP_SESSION **)this + 132), 26, a2, "End", 0);
  if ( v5 )
  {
    LocalFree(*(HLOCAL *)Buffer);
    *(_QWORD *)Buffer = 0;
  }
  STRA::~STRA((STRA *)v14);
  STRA::~STRA((STRA *)v12);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18003e708  mov     [rsp-8+arg_10], rbx
0x18003e70d  push    rbp
0x18003e70e  push    rsi
0x18003e70f  push    rdi
0x18003e710  push    r12
0x18003e712  push    r13
0x18003e714  push    r14
0x18003e716  push    r15
0x18003e718  lea     rbp, [rsp-0D0h]
0x18003e720  sub     rsp, 1D0h
0x18003e727  mov     rax, cs:__security_cookie
0x18003e72e  xor     rax, rsp
0x18003e731  mov     [rbp+100h+var_40], rax
0x18003e738  mov     r13, rdx
0x18003e73b  mov     r14, rcx
0x18003e73e  mov     qword ptr [rsp+200h+Buffer], 0
0x18003e747  xor     ebx, ebx
0x18003e749  xor     r15d, r15d
0x18003e74c  mov     edi, 80h
0x18003e751  mov     r8d, edi
0x18003e754  lea     rdx, [rbp+100h+var_140]
0x18003e758  lea     rcx, [rsp+200h+var_1B8]
0x18003e75d  call    cs:__imp_??0STRA@@QEAA@PEADK@Z; STRA::STRA(char *,ulong)
0x18003e763  nop
0x18003e764  mov     r8d, edi
0x18003e767  lea     rdx, [rbp+100h+var_C0]
0x18003e76b  lea     rcx, [rbp+100h+var_180]
0x18003e76f  call    cs:__imp_??0STRA@@QEAA@PEADK@Z; STRA::STRA(char *,ulong)
0x18003e775  nop
0x18003e776  xor     edi, edi
0x18003e778  mov     r12d, edi
0x18003e77b  mov     rcx, [r14+420h]; this
0x18003e782  call    ?GetReferencedSiteConfig@FTP_SESSION@@QEAAPEAVFTP_SITE_CONFIG@@XZ; FTP_SESSION::GetReferencedSiteConfig(void)
0x18003e787  mov     rsi, rax
0x18003e78a  cmp     [rax+2B4h], edi
0x18003e790  jz      loc_18003E8B5
0x18003e796  mov     r8d, [r14+490h]
0x18003e79d  test    r8d, r8d
0x18003e7a0  jns     short loc_18003E7B5
0x18003e7a2  mov     eax, r8d
0x18003e7a5  and     eax, 1FFF0000h
0x18003e7aa  cmp     eax, 70000h
0x18003e7af  jnz     short loc_18003E7B5
0x18003e7b1  movzx   r8d, r8w; dwMessageId
0x18003e7b5  mov     [rsp+200h+Arguments], rdi; Arguments
0x18003e7ba  mov     [rsp+200h+nSize], edi; nSize
0x18003e7be  lea     rax, [rsp+200h+Buffer]
0x18003e7c3  mov     [rsp+200h+lpBuffer], rax; lpBuffer
0x18003e7c8  xor     edx, edx; lpSource
0x18003e7ca  mov     ecx, 13FFh; dwFlags
0x18003e7cf  mov     r9d, 409h; dwLanguageId
0x18003e7d5  call    cs:__imp_FormatMessageA
0x18003e7db  test    eax, eax
0x18003e7dd  jnz     short loc_18003E7ED
0x18003e7df  lea     rax, String
0x18003e7e6  mov     qword ptr [rsp+200h+Buffer], rax
0x18003e7eb  jmp     short loc_18003E7F3
0x18003e7ed  mov     r15d, 1
0x18003e7f3  lea     rdx, aWin32Error; "Win32 error:   "
0x18003e7fa  lea     rcx, [rsp+200h+var_1B8]
0x18003e7ff  call    cs:__imp_?Append@STRA@@QEAAJPEBD@Z; STRA::Append(char const *)
0x18003e805  mov     ebx, eax
0x18003e807  test    eax, eax
0x18003e809  js      loc_18003E8B5
0x18003e80f  mov     rdx, qword ptr [rsp+200h+Buffer]
0x18003e814  lea     rcx, [rsp+200h+var_1B8]
0x18003e819  call    cs:__imp_?Append@STRA@@QEAAJPEBD@Z; STRA::Append(char const *)
0x18003e81f  mov     ebx, eax
0x18003e821  test    eax, eax
0x18003e823  js      loc_18003E8B5
0x18003e829  lea     rdx, aErrorDetails; "\r\nError details: "
0x18003e830  lea     rcx, [rsp+200h+var_1B8]
0x18003e835  call    cs:__imp_?Append@STRA@@QEAAJPEBD@Z; STRA::Append(char const *)
0x18003e83b  mov     ebx, eax
0x18003e83d  test    eax, eax
0x18003e83f  js      short loc_18003E8B5
0x18003e841  mov     rdx, [r14+420h]
0x18003e848  lea     r8, [rbp+100h+var_180]; struct STRA *
0x18003e84c  mov     edx, [rdx+12B4h]; CodePage
0x18003e852  mov     rcx, [r14+450h]; lpWideCharStr
0x18003e859  call    ?ConvertFromUnicode@@YAJPEBGKPEAVSTRA@@@Z; ConvertFromUnicode(ushort const *,ulong,STRA *)
0x18003e85e  mov     ebx, eax
0x18003e860  test    eax, eax
0x18003e862  js      short loc_18003E8B5
0x18003e864  mov     rdx, [rbp+100h+var_160]
0x18003e868  lea     rcx, [rsp+200h+var_1B8]
0x18003e86d  call    cs:__imp_?Append@STRA@@QEAAJPEBD@Z; STRA::Append(char const *)
0x18003e873  mov     ebx, eax
0x18003e875  test    eax, eax
0x18003e877  js      short loc_18003E8B5
0x18003e879  lea     rdx, aEnd; "\r\nEnd"
0x18003e880  lea     rcx, [rsp+200h+var_1B8]
0x18003e885  call    cs:__imp_?Append@STRA@@QEAAJPEBD@Z; STRA::Append(char const *)
0x18003e88b  mov     ebx, eax
0x18003e88d  test    eax, eax
0x18003e88f  js      short loc_18003E8B5
0x18003e891  mov     [rsp+200h+lpBuffer], rdi; char *
0x18003e896  mov     r9, [rsp+200h+var_198]; char *
0x18003e89b  mov     r8, r13; char *
0x18003e89e  mov     edx, 1Ah; unsigned int
0x18003e8a3  mov     rcx, [r14+420h]; this
0x18003e8aa  call    ?WriteResponseHelper@FTP_SESSION@@QEAAJKPEBD0PEAD@Z; FTP_SESSION::WriteResponseHelper(ulong,char const *,char const *,char *)
0x18003e8af  mov     r12d, 1
0x18003e8b5  or      edi, 0FFFFFFFFh
0x18003e8b8  lock xadd [rsi], edi
0x18003e8bc  dec     edi
0x18003e8be  mov     rcx, cs:?sm_pRefTraceLog@FTP_SITE_CONFIG@@0PEAU_TRACE_LOG@@EA; _TRACE_LOG * FTP_SITE_CONFIG::sm_pRefTraceLog
0x18003e8c5  test    rcx, rcx
0x18003e8c8  jz      short loc_18003E8D5
0x18003e8ca  mov     r8, rsi
0x18003e8cd  mov     edx, edi
0x18003e8cf  call    cs:__imp_WriteRefTraceLog
0x18003e8d5  test    edi, edi
0x18003e8d7  jnz     short loc_18003E8F3
0x18003e8d9  mov     rcx, rsi; this
0x18003e8dc  call    ??1FTP_SITE_CONFIG@@QEAA@XZ; FTP_SITE_CONFIG::~FTP_SITE_CONFIG(void)
0x18003e8e1  nop
0x18003e8e2  mov     rdx, rsi
0x18003e8e5  mov     rcx, cs:?sm_pAllocHandler@FTP_SITE_CONFIG@@0PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * FTP_SITE_CONFIG::sm_pAllocHandler
0x18003e8ec  call    cs:__imp_?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z; ALLOC_CACHE_HANDLER::Free(void *)
0x18003e8f2  nop
0x18003e8f3  test    r12d, r12d
0x18003e8f6  jnz     short loc_18003E91C
0x18003e8f8  mov     [rsp+200h+lpBuffer], 0; char *
0x18003e901  lea     r9, aEnd_0; "End"
0x18003e908  mov     r8, r13; char *
0x18003e90b  lea     edx, [r12+1Ah]; unsigned int
0x18003e910  mov     rcx, [r14+420h]; this
0x18003e917  call    ?WriteResponseHelper@FTP_SESSION@@QEAAJKPEBD0PEAD@Z; FTP_SESSION::WriteResponseHelper(ulong,char const *,char const *,char *)
0x18003e91c  test    r15d, r15d
0x18003e91f  jz      short loc_18003E935
0x18003e921  mov     rcx, qword ptr [rsp+200h+Buffer]; hMem
0x18003e926  call    cs:__imp_LocalFree
0x18003e92c  mov     qword ptr [rsp+200h+Buffer], 0
0x18003e935  lea     rcx, [rbp+100h+var_180]
0x18003e939  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x18003e93f  nop
0x18003e940  lea     rcx, [rsp+200h+var_1B8]
0x18003e945  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x18003e94b  mov     eax, ebx
0x18003e94d  mov     rcx, [rbp+100h+var_40]
0x18003e954  xor     rcx, rsp; StackCookie
0x18003e957  call    __security_check_cookie
0x18003e95c  mov     rbx, [rsp+200h+arg_10]
0x18003e964  add     rsp, 1D0h
0x18003e96b  pop     r15
0x18003e96d  pop     r14
0x18003e96f  pop     r13
0x18003e971  pop     r12
0x18003e973  pop     rdi
0x18003e974  pop     rsi
0x18003e975  pop     rbp
0x18003e976  retn
```
