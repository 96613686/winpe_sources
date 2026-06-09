# FTP_COMMAND::CheckDataChannelPolicyBeforeDataTransfer(void)

- ea: `0x1800384cc`
- end: `0x180038606`
- name: `?CheckDataChannelPolicyBeforeDataTransfer@FTP_COMMAND@@QEAAJXZ`
- size: `314`
- prototype: `__int64 __fastcall(FTP_COMMAND *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18003c51c`
- `0x180043258`

## callees

- `0x180009090`
- `0x1800384cc`
- `0x180038ac0`
- `0x18003e564`

## import_xrefs

- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x1800385f4`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x1800385f4`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18003852a`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18003858e`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18003852a`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18003858e`
- `iisutil!WriteRefTraceLog` at `0x1800385d2`
- `iisutil!WriteRefTraceLog` at `0x1800385d2`

## string_xrefs

- `0x180038523`: `Protection negotiation failed. PROT command with recognized parameter must precede this command.`

## pseudocode

```c
__int64 __fastcall FTP_COMMAND::CheckDataChannelPolicyBeforeDataTransfer(FTP_COMMAND *this)
{
  FTP_SESSION *v2; // rsi
  struct FTP_SITE_CONFIG *ReferencedSiteConfig; // rax
  volatile signed __int32 *v4; // rdi
  unsigned int v5; // ebp
  unsigned __int32 v6; // ebx

  v2 = (FTP_SESSION *)*((_QWORD *)this + 132);
  ReferencedSiteConfig = FTP_SESSION::GetReferencedSiteConfig(v2);
  v4 = (volatile signed __int32 *)ReferencedSiteConfig;
  if ( *((_DWORD *)v2 + 1424) )
  {
    v5 = -2147024891;
    if ( !*((_DWORD *)this + 292) )
      *((_DWORD *)this + 292) = -2147024891;
    if ( !*((_DWORD *)this + 274) )
    {
      *((_DWORD *)this + 274) = 43;
      STRU::Copy(
        (FTP_COMMAND *)((char *)this + 1112),
        L"Protection negotiation failed. PROT command with recognized parameter must precede this command.");
      *((_QWORD *)this + 138) = *((_QWORD *)this + 143);
    }
    FTP_COMMAND::WriteResponseAndLog(this, "534", "Protection level negotiation failed.");
  }
  else
  {
    v5 = 0;
    if ( *((_DWORD *)ReferencedSiteConfig + 29) == 1 && !*((_DWORD *)v2 + 531) )
    {
      v5 = -2147024891;
      if ( !*((_DWORD *)this + 292) )
        *((_DWORD *)this + 292) = -2147024891;
      if ( !*((_DWORD *)this + 274) )
      {
        *((_DWORD *)this + 274) = 24;
        STRU::Copy((FTP_COMMAND *)((char *)this + 1112), L"SSL policy requires SSL for data channel.");
        *((_QWORD *)this + 138) = *((_QWORD *)this + 143);
      }
      FTP_COMMAND::WriteResponseAndLog(this, "534", "Policy requires SSL.");
    }
  }
  v6 = _InterlockedDecrement(v4);
  if ( FTP_SITE_CONFIG::sm_pRefTraceLog )
    WriteRefTraceLog(FTP_SITE_CONFIG::sm_pRefTraceLog, v6);
  if ( !v6 && v4 )
  {
    FTP_SITE_CONFIG::~FTP_SITE_CONFIG((FTP_SITE_CONFIG *)v4);
    ALLOC_CACHE_HANDLER::Free((ALLOC_CACHE_HANDLER *)FTP_SITE_CONFIG::sm_pAllocHandler, (void *)v4);
  }
  return v5;
}

```

## disassembly

```asm
0x1800384cc  push    rbx
0x1800384ce  push    rbp
0x1800384cf  push    rsi
0x1800384d0  push    rdi
0x1800384d1  sub     rsp, 28h
0x1800384d5  mov     rbx, rcx
0x1800384d8  mov     rsi, [rcx+420h]
0x1800384df  mov     rcx, rsi; this
0x1800384e2  call    ?GetReferencedSiteConfig@FTP_SESSION@@QEAAPEAVFTP_SITE_CONFIG@@XZ; FTP_SESSION::GetReferencedSiteConfig(void)
0x1800384e7  mov     rdi, rax
0x1800384ea  cmp     dword ptr [rsi+1640h], 0
0x1800384f1  jz      short loc_180038547
0x1800384f3  mov     eax, 80070005h
0x1800384f8  mov     ebp, eax
0x1800384fa  cmp     dword ptr [rbx+490h], 0
0x180038501  jnz     short loc_180038509
0x180038503  mov     [rbx+490h], eax
0x180038509  cmp     dword ptr [rbx+448h], 0
0x180038510  jnz     short loc_18003853E
0x180038512  mov     dword ptr [rbx+448h], 2Bh ; '+'
0x18003851c  lea     rcx, [rbx+458h]
0x180038523  lea     rdx, aProtectionNego; "Protection negotiation failed. PROT com"...
0x18003852a  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180038530  mov     rax, [rbx+478h]
0x180038537  mov     [rbx+450h], rax
0x18003853e  lea     r8, aProtectionLeve; "Protection level negotiation failed."
0x180038545  jmp     short loc_1800385A9
0x180038547  xor     ebp, ebp
0x180038549  cmp     dword ptr [rax+74h], 1
0x18003854d  jnz     short loc_1800385B8
0x18003854f  cmp     [rsi+84Ch], ebp
0x180038555  jnz     short loc_1800385B8
0x180038557  mov     eax, 80070005h
0x18003855c  mov     ebp, eax
0x18003855e  cmp     dword ptr [rbx+490h], 0
0x180038565  jnz     short loc_18003856D
0x180038567  mov     [rbx+490h], eax
0x18003856d  cmp     dword ptr [rbx+448h], 0
0x180038574  jnz     short loc_1800385A2
0x180038576  mov     dword ptr [rbx+448h], 18h
0x180038580  lea     rcx, [rbx+458h]
0x180038587  lea     rdx, aSslPolicyRequi_3; "SSL policy requires SSL for data channe"...
0x18003858e  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180038594  mov     rax, [rbx+478h]
0x18003859b  mov     [rbx+450h], rax
0x1800385a2  lea     r8, aPolicyRequires_1; "Policy requires SSL."
0x1800385a9  lea     rdx, a534; "534"
0x1800385b0  mov     rcx, rbx; this
0x1800385b3  call    ?WriteResponseAndLog@FTP_COMMAND@@QEAAJPEBD0ZZ; FTP_COMMAND::WriteResponseAndLog(char const *,char const *,...)
0x1800385b8  or      ebx, 0FFFFFFFFh
0x1800385bb  lock xadd [rdi], ebx
0x1800385bf  dec     ebx
0x1800385c1  mov     rcx, cs:?sm_pRefTraceLog@FTP_SITE_CONFIG@@0PEAU_TRACE_LOG@@EA; _TRACE_LOG * FTP_SITE_CONFIG::sm_pRefTraceLog
0x1800385c8  test    rcx, rcx
0x1800385cb  jz      short loc_1800385D8
0x1800385cd  mov     r8, rdi
0x1800385d0  mov     edx, ebx
0x1800385d2  call    cs:__imp_WriteRefTraceLog
0x1800385d8  test    ebx, ebx
0x1800385da  jnz     short loc_1800385FB
0x1800385dc  test    rdi, rdi
0x1800385df  jz      short loc_1800385FB
0x1800385e1  mov     rcx, rdi; this
0x1800385e4  call    ??1FTP_SITE_CONFIG@@QEAA@XZ; FTP_SITE_CONFIG::~FTP_SITE_CONFIG(void)
0x1800385e9  nop
0x1800385ea  mov     rdx, rdi
0x1800385ed  mov     rcx, cs:?sm_pAllocHandler@FTP_SITE_CONFIG@@0PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * FTP_SITE_CONFIG::sm_pAllocHandler
0x1800385f4  call    cs:__imp_?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z; ALLOC_CACHE_HANDLER::Free(void *)
0x1800385fa  nop
0x1800385fb  mov     eax, ebp
0x1800385fd  add     rsp, 28h
0x180038601  pop     rdi
0x180038602  pop     rsi
0x180038603  pop     rbp
0x180038604  pop     rbx
0x180038605  retn
```
