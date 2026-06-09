# FTP_COMMAND::HandleQUIT(int *)

- ea: `0x18003b6a0`
- end: `0x18003b858`
- name: `?HandleQUIT@FTP_COMMAND@@QEAAXPEAH@Z`
- size: `440`
- prototype: `void __fastcall(FTP_COMMAND *__hidden this, int *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18003732c`

## callees

- `0x180009090`
- `0x18003393c`
- `0x180038ac0`
- `0x18003b6a0`
- `0x18003e3c8`
- `0x18003e564`
- `0x180047050`
- `0x180049010`

## import_xrefs

- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x18003b72a`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x18003b72a`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18003b768`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18003b78c`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18003b768`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18003b78c`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x18003b826`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x18003b826`
- `iisutil!WriteRefTraceLog` at `0x18003b804`
- `iisutil!WriteRefTraceLog` at `0x18003b804`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall FTP_COMMAND::HandleQUIT(FTP_SESSION **this, int *a2)
{
  struct FTP_SITE_CONFIG *ReferencedSiteConfig; // rbx
  FTP_SESSION *v5; // rcx
  __int64 v6; // rsi
  bool v7; // zf
  __int64 v8; // rcx
  char *v9; // rsi
  unsigned __int32 v10; // edi
  _BYTE v11[32]; // [rsp+30h] [rbp-168h] BYREF
  char *v12; // [rsp+50h] [rbp-148h]
  char v13[256]; // [rsp+70h] [rbp-128h] BYREF

  ReferencedSiteConfig = FTP_SESSION::GetReferencedSiteConfig(this[132]);
  v5 = this[132];
  v6 = 600;
  v7 = *((_DWORD *)v5 + 1197) == 65001;
  if ( *((_DWORD *)v5 + 1197) != 65001 )
    v6 = 376;
  v8 = 616;
  if ( !v7 )
    v8 = 392;
  if ( *(_DWORD *)((char *)ReferencedSiteConfig + v8) )
  {
    v9 = *(char **)((char *)ReferencedSiteConfig + v6);
    if ( *((_DWORD *)ReferencedSiteConfig + 171) )
    {
      STRA::STRA((STRA *)v11, v13, 0x100u);
      if ( (int)FTP_SESSION::ExpandMessage(this[132], v9, (struct STRA *)v11, 0) < 0 )
      {
        FTP_COMMAND::WriteResponseAndLog((FTP_COMMAND *)this, "221", "Goodbye.");
        STRA::~STRA((STRA *)v11);
        goto LABEL_13;
      }
      FTP_COMMAND::WriteResponseAndLog((FTP_COMMAND *)this, 11, "221", v12);
      STRA::~STRA((STRA *)v11);
    }
    else
    {
      FTP_COMMAND::WriteResponseAndLog((FTP_COMMAND *)this, 11, "221", v9);
    }
  }
  else
  {
    FTP_COMMAND::WriteResponseAndLog((FTP_COMMAND *)this, "221", "Goodbye.");
  }
  (*(void (__fastcall **)(FTP_SESSION *, _QWORD, _QWORD, const OLECHAR *, _DWORD))(*(_QWORD *)this[132] + 32LL))(
    this[132],
    0,
    0,
    &WideCharStr,
    0);
LABEL_13:
  v10 = _InterlockedDecrement((volatile signed __int32 *)ReferencedSiteConfig);
  if ( FTP_SITE_CONFIG::sm_pRefTraceLog )
    WriteRefTraceLog(FTP_SITE_CONFIG::sm_pRefTraceLog, v10);
  if ( !v10 && ReferencedSiteConfig )
  {
    FTP_SITE_CONFIG::~FTP_SITE_CONFIG(ReferencedSiteConfig);
    ALLOC_CACHE_HANDLER::Free((ALLOC_CACHE_HANDLER *)FTP_SITE_CONFIG::sm_pAllocHandler, ReferencedSiteConfig);
  }
  *a2 = 1;
}

```

## disassembly

```asm
0x18003b6a0  mov     [rsp+arg_10], rbx
0x18003b6a5  push    rsi
0x18003b6a6  push    rdi
0x18003b6a7  push    r14
0x18003b6a9  sub     rsp, 180h
0x18003b6b0  mov     rax, cs:__security_cookie
0x18003b6b7  xor     rax, rsp
0x18003b6ba  mov     [rsp+198h+var_28], rax
0x18003b6c2  mov     r14, rdx
0x18003b6c5  mov     rdi, rcx
0x18003b6c8  mov     rcx, [rcx+420h]; this
0x18003b6cf  call    ?GetReferencedSiteConfig@FTP_SESSION@@QEAAPEAVFTP_SITE_CONFIG@@XZ; FTP_SESSION::GetReferencedSiteConfig(void)
0x18003b6d4  mov     rbx, rax
0x18003b6d7  mov     rcx, [rdi+420h]
0x18003b6de  mov     esi, 258h
0x18003b6e3  mov     eax, 178h
0x18003b6e8  mov     edx, 0FDE9h
0x18003b6ed  cmp     [rcx+12B4h], edx
0x18003b6f3  cmovnz  esi, eax
0x18003b6f6  mov     ecx, 268h
0x18003b6fb  mov     eax, 188h
0x18003b700  cmovnz  ecx, eax
0x18003b703  cmp     dword ptr [rcx+rbx], 0
0x18003b707  jz      loc_18003B7AD
0x18003b70d  mov     rsi, [rsi+rbx]
0x18003b711  cmp     dword ptr [rbx+2ACh], 0
0x18003b718  jz      short loc_18003B794
0x18003b71a  mov     r8d, 100h
0x18003b720  lea     rdx, [rsp+198h+var_128]
0x18003b725  lea     rcx, [rsp+198h+var_168]
0x18003b72a  call    cs:__imp_??0STRA@@QEAA@PEADK@Z; STRA::STRA(char *,ulong)
0x18003b730  nop
0x18003b731  xor     r9d, r9d; struct STRA *
0x18003b734  lea     r8, [rsp+198h+var_168]; struct STRA *
0x18003b739  mov     rdx, rsi; char *
0x18003b73c  mov     rcx, [rdi+420h]; this
0x18003b743  call    ?ExpandMessage@FTP_SESSION@@QEAAJPEBDPEAVSTRA@@1@Z; FTP_SESSION::ExpandMessage(char const *,STRA *,STRA *)
0x18003b748  mov     rcx, rdi; this
0x18003b74b  test    eax, eax
0x18003b74d  jns     short loc_18003B770
0x18003b74f  lea     r8, aGoodbye; "Goodbye."
0x18003b756  lea     rdx, a221; "221"
0x18003b75d  call    ?WriteResponseAndLog@FTP_COMMAND@@QEAAJPEBD0ZZ; FTP_COMMAND::WriteResponseAndLog(char const *,char const *,...)
0x18003b762  nop
0x18003b763  lea     rcx, [rsp+198h+var_168]
0x18003b768  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x18003b76e  jmp     short loc_18003B7EA
0x18003b770  mov     r9, [rsp+198h+var_148]; char *
0x18003b775  lea     r8, a221; "221"
0x18003b77c  mov     edx, 0Bh; unsigned int
0x18003b781  call    ?WriteResponseAndLog@FTP_COMMAND@@QEAAJKPEBD0ZZ; FTP_COMMAND::WriteResponseAndLog(ulong,char const *,char const *,...)
0x18003b786  nop
0x18003b787  lea     rcx, [rsp+198h+var_168]
0x18003b78c  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x18003b792  jmp     short loc_18003B7C3
0x18003b794  mov     r9, rsi; char *
0x18003b797  lea     r8, a221; "221"
0x18003b79e  mov     edx, 0Bh; unsigned int
0x18003b7a3  mov     rcx, rdi; this
0x18003b7a6  call    ?WriteResponseAndLog@FTP_COMMAND@@QEAAJKPEBD0ZZ; FTP_COMMAND::WriteResponseAndLog(ulong,char const *,char const *,...)
0x18003b7ab  jmp     short loc_18003B7C3
0x18003b7ad  lea     r8, aGoodbye; "Goodbye."
0x18003b7b4  lea     rdx, a221; "221"
0x18003b7bb  mov     rcx, rdi; this
0x18003b7be  call    ?WriteResponseAndLog@FTP_COMMAND@@QEAAJPEBD0ZZ; FTP_COMMAND::WriteResponseAndLog(char const *,char const *,...)
0x18003b7c3  mov     rcx, [rdi+420h]
0x18003b7ca  mov     rax, [rcx]
0x18003b7cd  mov     [rsp+198h+var_178], 0
0x18003b7d5  lea     r9, WideCharStr
0x18003b7dc  xor     r8d, r8d
0x18003b7df  xor     edx, edx
0x18003b7e1  mov     rax, [rax+20h]
0x18003b7e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b7ea  or      edi, 0FFFFFFFFh
0x18003b7ed  lock xadd [rbx], edi
0x18003b7f1  dec     edi
0x18003b7f3  mov     rcx, cs:?sm_pRefTraceLog@FTP_SITE_CONFIG@@0PEAU_TRACE_LOG@@EA; _TRACE_LOG * FTP_SITE_CONFIG::sm_pRefTraceLog
0x18003b7fa  test    rcx, rcx
0x18003b7fd  jz      short loc_18003B80A
0x18003b7ff  mov     r8, rbx
0x18003b802  mov     edx, edi
0x18003b804  call    cs:__imp_WriteRefTraceLog
0x18003b80a  test    edi, edi
0x18003b80c  jnz     short loc_18003B82D
0x18003b80e  test    rbx, rbx
0x18003b811  jz      short loc_18003B82D
0x18003b813  mov     rcx, rbx; this
0x18003b816  call    ??1FTP_SITE_CONFIG@@QEAA@XZ; FTP_SITE_CONFIG::~FTP_SITE_CONFIG(void)
0x18003b81b  nop
0x18003b81c  mov     rdx, rbx
0x18003b81f  mov     rcx, cs:?sm_pAllocHandler@FTP_SITE_CONFIG@@0PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * FTP_SITE_CONFIG::sm_pAllocHandler
0x18003b826  call    cs:__imp_?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z; ALLOC_CACHE_HANDLER::Free(void *)
0x18003b82c  nop
0x18003b82d  mov     dword ptr [r14], 1
0x18003b834  mov     rcx, [rsp+198h+var_28]
0x18003b83c  xor     rcx, rsp; StackCookie
0x18003b83f  call    __security_check_cookie
0x18003b844  mov     rbx, [rsp+198h+arg_10]
0x18003b84c  add     rsp, 180h
0x18003b853  pop     r14
0x18003b855  pop     rdi
0x18003b856  pop     rsi
0x18003b857  retn
```
