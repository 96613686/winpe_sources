# FTP_COMMAND::HandleRNTO(int *)

- ea: `0x18003bd0c`
- end: `0x18003beeb`
- name: `?HandleRNTO@FTP_COMMAND@@QEAAXPEAH@Z`
- size: `479`
- prototype: `void __fastcall(FTP_COMMAND *__hidden this, int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18003732c`

## callees

- `0x180009090`
- `0x180033c70`
- `0x180038ac0`
- `0x18003bd0c`
- `0x18003e564`
- `0x18003e980`
- `0x180049010`

## import_xrefs

- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x18003bdd5`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x18003bdd5`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18003be6a`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18003beaf`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18003be6a`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18003beaf`
- `iisutil!WriteRefTraceLog` at `0x18003bdb8`
- `iisutil!WriteRefTraceLog` at `0x18003bdb8`

## string_xrefs

- `0x18003be84`: `%s command successful.`
- `0x18003bd43`: `Bad sequence of commands.`

## pseudocode

```c
void __fastcall FTP_COMMAND::HandleRNTO(FTP_COMMAND *this, int *a2)
{
  FTP_SESSION *v4; // rcx
  int SanitizedFullVirtualPath; // edi
  __int64 v6; // r14
  struct FTP_SITE_CONFIG *ReferencedSiteConfig; // rdi
  unsigned int v8; // ebp
  unsigned __int32 v9; // esi
  const unsigned __int16 *v10; // rsi
  int v11; // eax

  v4 = (FTP_SESSION *)*((_QWORD *)this + 132);
  if ( *((_DWORD *)v4 + 1316) )
  {
    v6 = *((_QWORD *)v4 + 132);
    SanitizedFullVirtualPath = FTP_SESSION::GetSanitizedFullVirtualPath(
                                 v4,
                                 *((const unsigned __int16 **)this + 43),
                                 *((_DWORD *)this + 90),
                                 (FTP_COMMAND *)((char *)this + 624));
    if ( SanitizedFullVirtualPath >= 0 )
    {
      ReferencedSiteConfig = FTP_SESSION::GetReferencedSiteConfig(*((FTP_SESSION **)this + 132));
      v8 = *((_DWORD *)ReferencedSiteConfig + 225);
      v9 = _InterlockedDecrement((volatile signed __int32 *)ReferencedSiteConfig);
      if ( FTP_SITE_CONFIG::sm_pRefTraceLog )
        WriteRefTraceLog(FTP_SITE_CONFIG::sm_pRefTraceLog, v9);
      if ( !v9 )
      {
        FTP_SITE_CONFIG::~FTP_SITE_CONFIG(ReferencedSiteConfig);
        ALLOC_CACHE_HANDLER::Free((ALLOC_CACHE_HANDLER *)FTP_SITE_CONFIG::sm_pAllocHandler, ReferencedSiteConfig);
      }
      SanitizedFullVirtualPath = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD, _QWORD, char *, _QWORD))(*(_QWORD *)v6 + 176LL))(
                                   v6,
                                   *(_QWORD *)(*((_QWORD *)this + 132) + 5248LL),
                                   *((_QWORD *)this + 82),
                                   v8,
                                   0,
                                   (char *)this + 1184,
                                   0);
      if ( SanitizedFullVirtualPath >= 0 )
      {
        FTP_COMMAND::WriteResponseAndLog(this, "250", "%s command successful.", *((const char **)this + 6));
      }
      else
      {
        v10 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v6 + 208LL))(v6);
        v11 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v6 + 200LL))(v6);
        if ( !*((_DWORD *)this + 274) )
        {
          *((_DWORD *)this + 274) = v11;
          STRU::Copy((FTP_COMMAND *)((char *)this + 1112), v10);
          *((_QWORD *)this + 138) = *((_QWORD *)this + 143);
        }
      }
    }
  }
  else
  {
    SanitizedFullVirtualPath = 0;
    if ( !*((_DWORD *)this + 292) )
      *((_DWORD *)this + 292) = -2147024120;
    FTP_COMMAND::WriteResponseAndLog(this, "503", "Bad sequence of commands.");
  }
  STRU::Copy((STRU *)(*((_QWORD *)this + 132) + 5216LL), &WideCharStr);
  if ( SanitizedFullVirtualPath < 0 )
  {
    if ( !*((_DWORD *)this + 292) )
      *((_DWORD *)this + 292) = SanitizedFullVirtualPath;
    FTP_COMMAND::WriteResponseWithErrorTextAndLog(this, "550");
  }
  *a2 = 1;
}

```

## disassembly

```asm
0x18003bd0c  push    rbx
0x18003bd0e  push    rbp
0x18003bd0f  push    rsi
0x18003bd10  push    rdi
0x18003bd11  push    r14
0x18003bd13  push    r15
0x18003bd15  sub     rsp, 48h
0x18003bd19  mov     r15, rdx
0x18003bd1c  mov     rbx, rcx
0x18003bd1f  mov     rcx, [rcx+420h]; this
0x18003bd26  cmp     dword ptr [rcx+1490h], 0
0x18003bd2d  jnz     short loc_18003BD5E
0x18003bd2f  xor     edi, edi
0x18003bd31  cmp     [rbx+490h], edi
0x18003bd37  jnz     short loc_18003BD43
0x18003bd39  mov     dword ptr [rbx+490h], 80070308h
0x18003bd43  lea     r8, aBadSequenceOfC; "Bad sequence of commands."
0x18003bd4a  lea     rdx, a503; "503"
0x18003bd51  mov     rcx, rbx; this
0x18003bd54  call    ?WriteResponseAndLog@FTP_COMMAND@@QEAAJPEBD0ZZ; FTP_COMMAND::WriteResponseAndLog(char const *,char const *,...)
0x18003bd59  jmp     loc_18003BE9A
0x18003bd5e  mov     r14, [rcx+420h]
0x18003bd65  lea     r9, [rbx+270h]; struct STRU *
0x18003bd6c  mov     r8d, [rbx+168h]; unsigned int
0x18003bd73  mov     rdx, [rbx+158h]; unsigned __int16 *
0x18003bd7a  call    ?GetSanitizedFullVirtualPath@FTP_SESSION@@QEAAJPEBGKPEAVSTRU@@@Z; FTP_SESSION::GetSanitizedFullVirtualPath(ushort const *,ulong,STRU *)
0x18003bd7f  mov     edi, eax
0x18003bd81  test    eax, eax
0x18003bd83  js      loc_18003BE9A
0x18003bd89  mov     rcx, [rbx+420h]; this
0x18003bd90  call    ?GetReferencedSiteConfig@FTP_SESSION@@QEAAPEAVFTP_SITE_CONFIG@@XZ; FTP_SESSION::GetReferencedSiteConfig(void)
0x18003bd95  mov     rdi, rax
0x18003bd98  mov     ebp, [rax+384h]
0x18003bd9e  or      esi, 0FFFFFFFFh
0x18003bda1  lock xadd [rax], esi
0x18003bda5  dec     esi
0x18003bda7  mov     rcx, cs:?sm_pRefTraceLog@FTP_SITE_CONFIG@@0PEAU_TRACE_LOG@@EA; _TRACE_LOG * FTP_SITE_CONFIG::sm_pRefTraceLog
0x18003bdae  test    rcx, rcx
0x18003bdb1  jz      short loc_18003BDBE
0x18003bdb3  mov     r8, rax
0x18003bdb6  mov     edx, esi
0x18003bdb8  call    cs:__imp_WriteRefTraceLog
0x18003bdbe  test    esi, esi
0x18003bdc0  jnz     short loc_18003BDDC
0x18003bdc2  mov     rcx, rdi; this
0x18003bdc5  call    ??1FTP_SITE_CONFIG@@QEAA@XZ; FTP_SITE_CONFIG::~FTP_SITE_CONFIG(void)
0x18003bdca  nop
0x18003bdcb  mov     rdx, rdi
0x18003bdce  mov     rcx, cs:?sm_pAllocHandler@FTP_SITE_CONFIG@@0PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * FTP_SITE_CONFIG::sm_pAllocHandler
0x18003bdd5  call    cs:__imp_?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z; ALLOC_CACHE_HANDLER::Free(void *)
0x18003bddb  nop
0x18003bddc  mov     rax, [r14]
0x18003bddf  lea     rcx, [rbx+4A0h]
0x18003bde6  mov     rdx, [rbx+420h]
0x18003bded  mov     [rsp+78h+var_48], 0
0x18003bdf6  mov     [rsp+78h+var_50], rcx
0x18003bdfb  mov     [rsp+78h+var_58], 0
0x18003be04  mov     r9d, ebp
0x18003be07  mov     r8, [rbx+290h]
0x18003be0e  mov     rdx, [rdx+1480h]
0x18003be15  mov     rcx, r14
0x18003be18  mov     rax, [rax+0B0h]
0x18003be1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003be24  mov     edi, eax
0x18003be26  test    eax, eax
0x18003be28  jns     short loc_18003BE80
0x18003be2a  mov     rax, [r14]
0x18003be2d  mov     rcx, r14
0x18003be30  mov     rax, [rax+0D0h]
0x18003be37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003be3c  mov     rsi, rax
0x18003be3f  mov     rdx, [r14]
0x18003be42  mov     rcx, r14
0x18003be45  mov     rax, [rdx+0C8h]
0x18003be4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003be51  cmp     dword ptr [rbx+448h], 0
0x18003be58  jnz     short loc_18003BE9A
0x18003be5a  mov     [rbx+448h], eax
0x18003be60  lea     rcx, [rbx+458h]
0x18003be67  mov     rdx, rsi
0x18003be6a  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18003be70  mov     rax, [rbx+478h]
0x18003be77  mov     [rbx+450h], rax
0x18003be7e  jmp     short loc_18003BE9A
0x18003be80  mov     r9, [rbx+30h]
0x18003be84  lea     r8, aSCommandSucces; "%s command successful."
0x18003be8b  lea     rdx, a250; "250"
0x18003be92  mov     rcx, rbx; this
0x18003be95  call    ?WriteResponseAndLog@FTP_COMMAND@@QEAAJPEBD0ZZ; FTP_COMMAND::WriteResponseAndLog(char const *,char const *,...)
0x18003be9a  mov     rcx, [rbx+420h]
0x18003bea1  add     rcx, 1460h
0x18003bea8  lea     rdx, WideCharStr
0x18003beaf  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18003beb5  test    edi, edi
0x18003beb7  jns     short loc_18003BED7
0x18003beb9  cmp     dword ptr [rbx+490h], 0
0x18003bec0  jnz     short loc_18003BEC8
0x18003bec2  mov     [rbx+490h], edi
0x18003bec8  lea     rdx, a550; "550"
0x18003becf  mov     rcx, rbx; this
0x18003bed2  call    ?WriteResponseWithErrorTextAndLog@FTP_COMMAND@@QEAAJPEBD@Z; FTP_COMMAND::WriteResponseWithErrorTextAndLog(char const *)
0x18003bed7  mov     dword ptr [r15], 1
0x18003bede  add     rsp, 48h
0x18003bee2  pop     r15
0x18003bee4  pop     r14
0x18003bee6  pop     rdi
0x18003bee7  pop     rsi
0x18003bee8  pop     rbp
0x18003bee9  pop     rbx
0x18003beea  retn
```
