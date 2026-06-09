# FTP_COMMAND::HandleLANG(int *)

- ea: `0x180039438`
- end: `0x180039571`
- name: `?HandleLANG@FTP_COMMAND@@QEAAXPEAH@Z`
- size: `313`
- prototype: `void __fastcall(FTP_COMMAND *__hidden this, int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18003732c`

## callees

- `0x180009090`
- `0x180038ac0`
- `0x180039438`
- `0x18003e564`

## import_xrefs

- `msvcrt!_strnicmp` at `0x1800394c9`
- `msvcrt!_strnicmp` at `0x1800394c9`
- `msvcrt!_stricmp` at `0x1800394ab`
- `msvcrt!_stricmp` at `0x1800394ab`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x180039554`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x180039554`
- `iisutil!WriteRefTraceLog` at `0x180039537`
- `iisutil!WriteRefTraceLog` at `0x180039537`

## string_xrefs

- `0x180039479`: `'%s': command not implemented.`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall FTP_COMMAND::HandleLANG(FTP_COMMAND *this, int *a2)
{
  struct FTP_SITE_CONFIG *ReferencedSiteConfig; // rdi
  unsigned __int32 v5; // ebx

  ReferencedSiteConfig = FTP_SESSION::GetReferencedSiteConfig(*((FTP_SESSION **)this + 132));
  if ( *((_DWORD *)ReferencedSiteConfig + 19) )
  {
    if ( !*((_DWORD *)this + 44)
      || !_stricmp(*((const char **)this + 20), "EN")
      || !_strnicmp(*((const char **)this + 20), "EN-", 3u) )
    {
      FTP_COMMAND::WriteResponseAndLog(this, "200", "Language is now English, UTF-8 encoding.");
      *(_DWORD *)(*((_QWORD *)this + 132) + 4788LL) = 65001;
    }
    else
    {
      if ( !*((_DWORD *)this + 292) )
        *((_DWORD *)this + 292) = -2147024776;
      FTP_COMMAND::WriteResponseAndLog(this, "502", "Language %s not supported.", *((_QWORD *)this + 20));
    }
  }
  else
  {
    if ( !*((_DWORD *)this + 292) )
      *((_DWORD *)this + 292) = -2147024776;
    FTP_COMMAND::WriteResponseAndLog(this, "502", "'%s': command not implemented.", *((_QWORD *)this + 6));
  }
  v5 = _InterlockedDecrement((volatile signed __int32 *)ReferencedSiteConfig);
  if ( FTP_SITE_CONFIG::sm_pRefTraceLog )
    WriteRefTraceLog(FTP_SITE_CONFIG::sm_pRefTraceLog, v5);
  if ( !v5 )
  {
    FTP_SITE_CONFIG::~FTP_SITE_CONFIG(ReferencedSiteConfig);
    ALLOC_CACHE_HANDLER::Free((ALLOC_CACHE_HANDLER *)FTP_SITE_CONFIG::sm_pAllocHandler, ReferencedSiteConfig);
  }
  *a2 = 1;
}

```

## disassembly

```asm
0x180039438  mov     [rsp+arg_0], rbx
0x18003943d  mov     [rsp+arg_8], rsi
0x180039442  push    rdi
0x180039443  sub     rsp, 20h
0x180039447  mov     rsi, rdx
0x18003944a  mov     rbx, rcx
0x18003944d  mov     rcx, [rcx+420h]; this
0x180039454  call    ?GetReferencedSiteConfig@FTP_SESSION@@QEAAPEAVFTP_SITE_CONFIG@@XZ; FTP_SESSION::GetReferencedSiteConfig(void)
0x180039459  mov     rdi, rax
0x18003945c  cmp     dword ptr [rax+4Ch], 0
0x180039460  jnz     short loc_180039494
0x180039462  cmp     dword ptr [rbx+490h], 0
0x180039469  jnz     short loc_180039475
0x18003946b  mov     dword ptr [rbx+490h], 80070078h
0x180039475  mov     r9, [rbx+30h]
0x180039479  lea     r8, aSCommandNotImp_0; "'%s': command not implemented."
0x180039480  lea     rdx, a502; "502"
0x180039487  mov     rcx, rbx; this
0x18003948a  call    ?WriteResponseAndLog@FTP_COMMAND@@QEAAJPEBD0ZZ; FTP_COMMAND::WriteResponseAndLog(char const *,char const *,...)
0x18003948f  jmp     loc_18003951D
0x180039494  cmp     dword ptr [rbx+0B0h], 0
0x18003949b  jz      short loc_1800394F6
0x18003949d  lea     rdx, aEn; "EN"
0x1800394a4  mov     rcx, [rbx+0A0h]; String1
0x1800394ab  call    cs:__imp__stricmp
0x1800394b1  test    eax, eax
0x1800394b3  jz      short loc_1800394F6
0x1800394b5  mov     r8d, 3; MaxCount
0x1800394bb  lea     rdx, aEn_0; "EN-"
0x1800394c2  mov     rcx, [rbx+0A0h]; String1
0x1800394c9  call    cs:__imp__strnicmp
0x1800394cf  test    eax, eax
0x1800394d1  jz      short loc_1800394F6
0x1800394d3  cmp     dword ptr [rbx+490h], 0
0x1800394da  jnz     short loc_1800394E6
0x1800394dc  mov     dword ptr [rbx+490h], 80070078h
0x1800394e6  mov     r9, [rbx+0A0h]
0x1800394ed  lea     r8, aLanguageSNotSu; "Language %s not supported."
0x1800394f4  jmp     short loc_180039480
0x1800394f6  lea     r8, aLanguageIsNowE; "Language is now English, UTF-8 encoding"...
0x1800394fd  lea     rdx, a200; "200"
0x180039504  mov     rcx, rbx; this
0x180039507  call    ?WriteResponseAndLog@FTP_COMMAND@@QEAAJPEBD0ZZ; FTP_COMMAND::WriteResponseAndLog(char const *,char const *,...)
0x18003950c  mov     rax, [rbx+420h]
0x180039513  mov     dword ptr [rax+12B4h], 0FDE9h
0x18003951d  or      ebx, 0FFFFFFFFh
0x180039520  lock xadd [rdi], ebx
0x180039524  dec     ebx
0x180039526  mov     rcx, cs:?sm_pRefTraceLog@FTP_SITE_CONFIG@@0PEAU_TRACE_LOG@@EA; _TRACE_LOG * FTP_SITE_CONFIG::sm_pRefTraceLog
0x18003952d  test    rcx, rcx
0x180039530  jz      short loc_18003953D
0x180039532  mov     r8, rdi
0x180039535  mov     edx, ebx
0x180039537  call    cs:__imp_WriteRefTraceLog
0x18003953d  test    ebx, ebx
0x18003953f  jnz     short loc_18003955B
0x180039541  mov     rcx, rdi; this
0x180039544  call    ??1FTP_SITE_CONFIG@@QEAA@XZ; FTP_SITE_CONFIG::~FTP_SITE_CONFIG(void)
0x180039549  nop
0x18003954a  mov     rdx, rdi
0x18003954d  mov     rcx, cs:?sm_pAllocHandler@FTP_SITE_CONFIG@@0PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * FTP_SITE_CONFIG::sm_pAllocHandler
0x180039554  call    cs:__imp_?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z; ALLOC_CACHE_HANDLER::Free(void *)
0x18003955a  nop
0x18003955b  mov     dword ptr [rsi], 1
0x180039561  mov     rbx, [rsp+28h+arg_0]
0x180039566  mov     rsi, [rsp+28h+arg_8]
0x18003956b  add     rsp, 20h
0x18003956f  pop     rdi
0x180039570  retn
```
