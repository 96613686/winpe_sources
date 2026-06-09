# FTP_COMMAND::HandleOPTS(int *)

- ea: `0x180039ce4`
- end: `0x180039e22`
- name: `?HandleOPTS@FTP_COMMAND@@QEAAXPEAH@Z`
- size: `318`
- prototype: `void __fastcall(FTP_COMMAND *__hidden this, int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18003732c`

## callees

- `0x180009090`
- `0x180038ac0`
- `0x180039ce4`
- `0x18003e564`

## import_xrefs

- `msvcrt!_strnicmp` at `0x180039d1d`
- `msvcrt!_strnicmp` at `0x180039d1d`
- `msvcrt!_stricmp` at `0x180039d48`
- `msvcrt!_stricmp` at `0x180039d59`
- `msvcrt!_stricmp` at `0x180039d48`
- `msvcrt!_stricmp` at `0x180039d59`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x180039e0e`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x180039e0e`
- `iisutil!WriteRefTraceLog` at `0x180039dec`
- `iisutil!WriteRefTraceLog` at `0x180039dec`

## string_xrefs

- `0x180039d8a`: `OPTS UTF8 command successful - UTF8 encoding now %s.`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall FTP_COMMAND::HandleOPTS(FTP_SESSION **this, int *a2)
{
  struct FTP_SITE_CONFIG *ReferencedSiteConfig; // rdi
  FTP_SESSION *v5; // rsi
  char v6; // al
  const char *v7; // rbp
  int v8; // ecx
  unsigned __int32 v9; // ebx

  ReferencedSiteConfig = FTP_SESSION::GetReferencedSiteConfig(this[132]);
  v5 = this[20];
  if ( _strnicmp((const char *)v5, "UTF8", 4u) || !*((_DWORD *)ReferencedSiteConfig + 19) )
    goto LABEL_12;
  v6 = *((_BYTE *)v5 + 4);
  v7 = "ON";
  if ( v6 != 32 )
  {
    if ( v6 )
      goto LABEL_12;
LABEL_8:
    v8 = 65001;
    goto LABEL_9;
  }
  if ( !_stricmp((const char *)v5 + 5, "ON") )
    goto LABEL_8;
  if ( !_stricmp((const char *)v5 + 5, "OFF") )
  {
    v8 = 0;
LABEL_9:
    *((_DWORD *)this[132] + 1197) = v8;
    if ( v8 != 65001 )
      v7 = "OFF";
    FTP_COMMAND::WriteResponseAndLog(
      (FTP_COMMAND *)this,
      "200",
      "OPTS UTF8 command successful - UTF8 encoding now %s.",
      v7);
    goto LABEL_15;
  }
LABEL_12:
  if ( !*((_DWORD *)this + 292) )
    *((_DWORD *)this + 292) = -2147024809;
  FTP_COMMAND::WriteResponseAndLog((FTP_COMMAND *)this, "501", "Option not supported.");
LABEL_15:
  *a2 = 1;
  v9 = _InterlockedDecrement((volatile signed __int32 *)ReferencedSiteConfig);
  if ( FTP_SITE_CONFIG::sm_pRefTraceLog )
    WriteRefTraceLog(FTP_SITE_CONFIG::sm_pRefTraceLog, v9);
  if ( !v9 )
  {
    if ( ReferencedSiteConfig )
    {
      FTP_SITE_CONFIG::~FTP_SITE_CONFIG(ReferencedSiteConfig);
      ALLOC_CACHE_HANDLER::Free((ALLOC_CACHE_HANDLER *)FTP_SITE_CONFIG::sm_pAllocHandler, ReferencedSiteConfig);
    }
  }
}

```

## disassembly

```asm
0x180039ce4  push    rbx
0x180039ce6  push    rbp
0x180039ce7  push    rsi
0x180039ce8  push    rdi
0x180039ce9  push    r13
0x180039ceb  push    r14
0x180039ced  sub     rsp, 28h
0x180039cf1  mov     r14, rdx
0x180039cf4  mov     rbx, rcx
0x180039cf7  mov     rcx, [rcx+420h]; this
0x180039cfe  call    ?GetReferencedSiteConfig@FTP_SESSION@@QEAAPEAVFTP_SITE_CONFIG@@XZ; FTP_SESSION::GetReferencedSiteConfig(void)
0x180039d03  mov     rdi, rax
0x180039d06  mov     rsi, [rbx+0A0h]
0x180039d0d  mov     r8d, 4; MaxCount
0x180039d13  lea     rdx, aUtf8; "UTF8"
0x180039d1a  mov     rcx, rsi; String1
0x180039d1d  call    cs:__imp__strnicmp
0x180039d23  test    eax, eax
0x180039d25  jnz     short loc_180039DA2
0x180039d27  cmp     [rdi+4Ch], eax
0x180039d2a  jz      short loc_180039DA2
0x180039d2c  mov     al, [rsi+4]
0x180039d2f  lea     r13, aOff_0; "OFF"
0x180039d36  lea     rbp, aOn_0; "ON"
0x180039d3d  cmp     al, 20h ; ' '
0x180039d3f  jnz     short loc_180039D67
0x180039d41  mov     rdx, rbp; String2
0x180039d44  lea     rcx, [rsi+5]; String1
0x180039d48  call    cs:__imp__stricmp
0x180039d4e  test    eax, eax
0x180039d50  jz      short loc_180039D6B
0x180039d52  mov     rdx, r13; String2
0x180039d55  lea     rcx, [rsi+5]; String1
0x180039d59  call    cs:__imp__stricmp
0x180039d5f  test    eax, eax
0x180039d61  jnz     short loc_180039DA2
0x180039d63  xor     ecx, ecx
0x180039d65  jmp     short loc_180039D70
0x180039d67  test    al, al
0x180039d69  jnz     short loc_180039DA2
0x180039d6b  mov     ecx, 0FDE9h
0x180039d70  mov     rax, [rbx+420h]
0x180039d77  mov     [rax+12B4h], ecx
0x180039d7d  cmp     ecx, 0FDE9h
0x180039d83  cmovnz  rbp, r13
0x180039d87  mov     r9, rbp
0x180039d8a  lea     r8, aOptsUtf8Comman; "OPTS UTF8 command successful - UTF8 enc"...
0x180039d91  lea     rdx, a200; "200"
0x180039d98  mov     rcx, rbx; this
0x180039d9b  call    ?WriteResponseAndLog@FTP_COMMAND@@QEAAJPEBD0ZZ; FTP_COMMAND::WriteResponseAndLog(char const *,char const *,...)
0x180039da0  jmp     short loc_180039DCB
0x180039da2  cmp     dword ptr [rbx+490h], 0
0x180039da9  jnz     short loc_180039DB5
0x180039dab  mov     dword ptr [rbx+490h], 80070057h
0x180039db5  lea     r8, aOptionNotSuppo; "Option not supported."
0x180039dbc  lea     rdx, a501; "501"
0x180039dc3  mov     rcx, rbx; this
0x180039dc6  call    ?WriteResponseAndLog@FTP_COMMAND@@QEAAJPEBD0ZZ; FTP_COMMAND::WriteResponseAndLog(char const *,char const *,...)
0x180039dcb  mov     dword ptr [r14], 1
0x180039dd2  or      ebx, 0FFFFFFFFh
0x180039dd5  lock xadd [rdi], ebx
0x180039dd9  dec     ebx
0x180039ddb  mov     rcx, cs:?sm_pRefTraceLog@FTP_SITE_CONFIG@@0PEAU_TRACE_LOG@@EA; _TRACE_LOG * FTP_SITE_CONFIG::sm_pRefTraceLog
0x180039de2  test    rcx, rcx
0x180039de5  jz      short loc_180039DF2
0x180039de7  mov     r8, rdi
0x180039dea  mov     edx, ebx
0x180039dec  call    cs:__imp_WriteRefTraceLog
0x180039df2  test    ebx, ebx
0x180039df4  jnz     short loc_180039E15
0x180039df6  test    rdi, rdi
0x180039df9  jz      short loc_180039E15
0x180039dfb  mov     rcx, rdi; this
0x180039dfe  call    ??1FTP_SITE_CONFIG@@QEAA@XZ; FTP_SITE_CONFIG::~FTP_SITE_CONFIG(void)
0x180039e03  nop
0x180039e04  mov     rdx, rdi
0x180039e07  mov     rcx, cs:?sm_pAllocHandler@FTP_SITE_CONFIG@@0PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * FTP_SITE_CONFIG::sm_pAllocHandler
0x180039e0e  call    cs:__imp_?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z; ALLOC_CACHE_HANDLER::Free(void *)
0x180039e14  nop
0x180039e15  add     rsp, 28h
0x180039e19  pop     r14
0x180039e1b  pop     r13
0x180039e1d  pop     rdi
0x180039e1e  pop     rsi
0x180039e1f  pop     rbp
0x180039e20  pop     rbx
0x180039e21  retn
```
