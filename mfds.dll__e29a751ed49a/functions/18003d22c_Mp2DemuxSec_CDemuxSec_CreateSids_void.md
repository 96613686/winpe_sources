# Mp2DemuxSec::CDemuxSec::CreateSids(void)

- ea: `0x18003d22c`
- end: `0x18003d49e`
- name: `?CreateSids@CDemuxSec@Mp2DemuxSec@@AEAAJXZ`
- size: `626`
- prototype: `__int64 __fastcall(Mp2DemuxSec::CDemuxSec *__hidden this)`
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18003d040`
- `0x18003d078`

## callees

- `0x180002820`
- `0x18000b8c0`
- `0x18002d514`
- `0x18003d22c`
- `0x180073d58`
- `0x180074a06`
- `0x18009b2fc`
- `0x1800c9010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d374`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d3d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d374`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d3d4`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18003d2f8`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18003d360`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18003d2f8`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18003d360`

## string_xrefs

- `0x18003d392`: `Mp2DemuxSec::CDemuxSec::CreateSids`
- `0x18003d3f9`: `Mp2DemuxSec::CDemuxSec::CreateSids`
- `0x18003d439`: `Mp2DemuxSec::CDemuxSec::CreateSids`

## pseudocode

```c
__int64 __fastcall Mp2DemuxSec::CDemuxSec::CreateSids(Mp2DemuxSec::CDemuxSec *this)
{
  __int64 v2; // rax
  unsigned __int64 v3; // r14
  void *v4; // rax
  unsigned int v5; // ebp
  PSID *pSid; // rbx
  DWORD v7; // edi
  struct _SID_IDENTIFIER_AUTHORITY *v8; // rax
  unsigned int v9; // ebx
  struct _SID_IDENTIFIER_AUTHORITY *v10; // rax
  signed int v11; // eax
  signed int LastError; // edi
  __int64 v13; // r8
  __int64 v14; // rdx
  char v16; // [rsp+A0h] [rbp+8h] BYREF

  if ( !*((_QWORD *)this + 6) )
  {
    v2 = *(_QWORD *)this;
    *((_BYTE *)this + 56) = 0;
    v3 = (*(unsigned __int8 (**)(void))(v2 + 8))();
    v4 = operator new[](saturated_mul(v3, 8u));
    *((_QWORD *)this + 6) = v4;
    if ( !v4 )
    {
      v9 = -2147024882;
      CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v16, "Mp2DemuxSec::CDemuxSec::CreateSids", 3216);
      if ( byte_1800EACCB )
        WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 17), 44, &WPP_ea15c8c7cf393e7e63170f2c53fa20e3_Traceguids, this);
LABEL_17:
      CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v16);
      return v9;
    }
    memset_0(v4, 0, 8 * v3);
    v5 = 0;
    *((_BYTE *)this + 56) = 0;
    while ( v5 < (unsigned int)v3 )
    {
      pSid = (PSID *)(*((_QWORD *)this + 6) + 8LL * v5);
      v7 = (**(__int64 (__fastcall ***)(Mp2DemuxSec::CDemuxSec *, _QWORD))this)(this, v5);
      v8 = (struct _SID_IDENTIFIER_AUTHORITY *)(*(__int64 (__fastcall **)(Mp2DemuxSec::CDemuxSec *))(*(_QWORD *)this + 16LL))(this);
      if ( !AllocateAndInitializeSid(v8, 1u, v7, 0, 0, 0, 0, 0, 0, 0, pSid) )
      {
        LastError = GetLastError();
        if ( LastError <= 0 )
          v9 = LastError;
        else
          v9 = (unsigned __int16)LastError | 0x80070000;
        CallStackScopeTrace::CallStackScopeTrace(
          (CallStackScopeTrace *)&v16,
          "Mp2DemuxSec::CDemuxSec::CreateSids",
          3239);
        if ( byte_1800EACCB )
        {
          v14 = 45;
          goto LABEL_13;
        }
        goto LABEL_17;
      }
      ++v5;
      ++*((_BYTE *)this + 56);
    }
  }
  v9 = 0;
  if ( !*((_QWORD *)this + 8) )
  {
    v10 = (struct _SID_IDENTIFIER_AUTHORITY *)(*(__int64 (__fastcall **)(Mp2DemuxSec::CDemuxSec *))(*(_QWORD *)this
                                                                                                  + 24LL))(this);
    if ( !AllocateAndInitializeSid(v10, 1u, 0, 0, 0, 0, 0, 0, 0, 0, (PSID *)this + 8) )
    {
      v11 = GetLastError();
      LastError = v11;
      if ( v11 > 0 )
        v9 = (unsigned __int16)v11 | 0x80070000;
      else
        v9 = v11;
      CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v16, "Mp2DemuxSec::CDemuxSec::CreateSids", 3260);
      if ( byte_1800EACCB )
      {
        v14 = 46;
LABEL_13:
        WPP_SF_qDd(*((_QWORD *)WPP_GLOBAL_Control + 17), v14, v13, this, LastError, v9);
      }
      goto LABEL_17;
    }
  }
  return v9;
}

```

## disassembly

```asm
0x18003d22c  push    rbx
0x18003d22e  push    rbp
0x18003d22f  push    rsi
0x18003d230  push    rdi
0x18003d231  push    r14
0x18003d233  push    r15
0x18003d235  sub     rsp, 68h
0x18003d239  xor     r15d, r15d
0x18003d23c  mov     rsi, rcx
0x18003d23f  cmp     [rcx+30h], r15
0x18003d243  jnz     loc_18003D313
0x18003d249  mov     rax, [rcx]
0x18003d24c  mov     [rcx+38h], r15b
0x18003d250  mov     rax, [rax+8]
0x18003d254  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d259  movzx   r14d, al
0x18003d25d  lea     rcx, [r15-1]
0x18003d261  lea     eax, [r15+8]
0x18003d265  mul     r14
0x18003d268  cmovb   rax, rcx
0x18003d26c  mov     rcx, rax; unsigned __int64
0x18003d26f  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18003d274  mov     [rsi+30h], rax
0x18003d278  test    rax, rax
0x18003d27b  jz      loc_18003D433
0x18003d281  lea     r8, ds:0[r14*8]; Size
0x18003d289  xor     edx, edx; Val
0x18003d28b  mov     rcx, rax; void *
0x18003d28e  call    memset_0
0x18003d293  mov     ebp, r15d
0x18003d296  mov     [rsi+38h], r15b
0x18003d29a  cmp     ebp, r14d
0x18003d29d  jnb     short loc_18003D313
0x18003d29f  mov     rax, [rsi+30h]
0x18003d2a3  mov     edx, ebp
0x18003d2a5  mov     ecx, ebp
0x18003d2a7  lea     rbx, [rax+rcx*8]
0x18003d2ab  mov     rax, [rsi]
0x18003d2ae  mov     rcx, rsi
0x18003d2b1  mov     rax, [rax]
0x18003d2b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d2b9  mov     rcx, [rsi]
0x18003d2bc  mov     edi, eax
0x18003d2be  mov     rax, [rcx+10h]
0x18003d2c2  mov     rcx, rsi
0x18003d2c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d2ca  mov     [rsp+98h+pSid], rbx; pSid
0x18003d2cf  xor     r9d, r9d; nSubAuthority1
0x18003d2d2  mov     [rsp+98h+nSubAuthority7], r15d; nSubAuthority7
0x18003d2d7  mov     r8d, edi; nSubAuthority0
0x18003d2da  mov     [rsp+98h+nSubAuthority6], r15d; nSubAuthority6
0x18003d2df  mov     dl, 1; nSubAuthorityCount
0x18003d2e1  mov     [rsp+98h+nSubAuthority5], r15d; nSubAuthority5
0x18003d2e6  mov     rcx, rax; pIdentifierAuthority
0x18003d2e9  mov     [rsp+98h+nSubAuthority4], r15d; nSubAuthority4
0x18003d2ee  mov     [rsp+98h+nSubAuthority3], r15d; nSubAuthority3
0x18003d2f3  mov     [rsp+98h+nSubAuthority2], r15d; nSubAuthority2
0x18003d2f8  call    cs:__imp_AllocateAndInitializeSid
0x18003d2ff  nop     dword ptr [rax+rax+00h]
0x18003d304  test    eax, eax
0x18003d306  jz      loc_18003D3D4
0x18003d30c  inc     ebp
0x18003d30e  inc     byte ptr [rsi+38h]
0x18003d311  jmp     short loc_18003D29A
0x18003d313  lea     rdi, [rsi+40h]
0x18003d317  mov     ebx, r15d
0x18003d31a  cmp     [rdi], r15
0x18003d31d  jnz     loc_18003D423
0x18003d323  mov     rax, [rsi]
0x18003d326  mov     rcx, rsi
0x18003d329  mov     rax, [rax+18h]
0x18003d32d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d332  mov     [rsp+98h+pSid], rdi; pSid
0x18003d337  mov     rcx, rax; pIdentifierAuthority
0x18003d33a  mov     [rsp+98h+nSubAuthority7], r15d; nSubAuthority7
0x18003d33f  xor     r9d, r9d; nSubAuthority1
0x18003d342  mov     [rsp+98h+nSubAuthority6], r15d; nSubAuthority6
0x18003d347  xor     r8d, r8d; nSubAuthority0
0x18003d34a  mov     [rsp+98h+nSubAuthority5], r15d; nSubAuthority5
0x18003d34f  mov     dl, 1; nSubAuthorityCount
0x18003d351  mov     [rsp+98h+nSubAuthority4], r15d; nSubAuthority4
0x18003d356  mov     [rsp+98h+nSubAuthority3], r15d; nSubAuthority3
0x18003d35b  mov     [rsp+98h+nSubAuthority2], r15d; nSubAuthority2
0x18003d360  call    cs:__imp_AllocateAndInitializeSid
0x18003d367  nop     dword ptr [rax+rax+00h]
0x18003d36c  test    eax, eax
0x18003d36e  jnz     loc_18003D423
0x18003d374  call    cs:__imp_GetLastError
0x18003d37b  nop     dword ptr [rax+rax+00h]
0x18003d380  mov     edi, eax
0x18003d382  test    eax, eax
0x18003d384  jg      loc_18003D486
0x18003d38a  mov     ebx, eax
0x18003d38c  mov     r8d, 0CBCh; int
0x18003d392  lea     rdx, aMp2demuxsecCde_0; "Mp2DemuxSec::CDemuxSec::CreateSids"
0x18003d399  lea     rcx, [rsp+98h+arg_0]; this
0x18003d3a1  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18003d3a6  cmp     cs:byte_1800EACCB, 1
0x18003d3ad  jb      short loc_18003D416
0x18003d3af  mov     edx, 2Eh ; '.'
0x18003d3b4  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d3bb  mov     r9, rsi
0x18003d3be  mov     [rsp+98h+nSubAuthority3], ebx
0x18003d3c2  mov     [rsp+98h+nSubAuthority2], edi
0x18003d3c6  mov     rcx, [rcx+88h]
0x18003d3cd  call    WPP_SF_qDd
0x18003d3d2  jmp     short loc_18003D416
0x18003d3d4  call    cs:__imp_GetLastError
0x18003d3db  nop     dword ptr [rax+rax+00h]
0x18003d3e0  mov     edi, eax
0x18003d3e2  test    eax, eax
0x18003d3e4  jle     loc_18003D47F
0x18003d3ea  movzx   ebx, di
0x18003d3ed  or      ebx, 80070000h
0x18003d3f3  mov     r8d, 0CA7h; int
0x18003d3f9  lea     rdx, aMp2demuxsecCde_0; "Mp2DemuxSec::CDemuxSec::CreateSids"
0x18003d400  lea     rcx, [rsp+98h+arg_0]; this
0x18003d408  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18003d40d  cmp     cs:byte_1800EACCB, 1
0x18003d414  jnb     short loc_18003D494
0x18003d416  lea     rcx, [rsp+98h+arg_0]; this
0x18003d41e  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18003d423  mov     eax, ebx
0x18003d425  add     rsp, 68h
0x18003d429  pop     r15
0x18003d42b  pop     r14
0x18003d42d  pop     rdi
0x18003d42e  pop     rsi
0x18003d42f  pop     rbp
0x18003d430  pop     rbx
0x18003d431  retn
0x18003d433  mov     r8d, 0C90h; int
0x18003d439  lea     rdx, aMp2demuxsecCde_0; "Mp2DemuxSec::CDemuxSec::CreateSids"
0x18003d440  lea     rcx, [rsp+98h+arg_0]; this
0x18003d448  mov     ebx, 8007000Eh
0x18003d44d  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18003d452  cmp     cs:byte_1800EACCB, 1
0x18003d459  jb      short loc_18003D416
0x18003d45b  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d462  lea     r8, WPP_ea15c8c7cf393e7e63170f2c53fa20e3_Traceguids
0x18003d469  mov     edx, 2Ch ; ','
0x18003d46e  mov     r9, rsi
0x18003d471  mov     rcx, [rcx+88h]
0x18003d478  call    WPP_SF_q
0x18003d47d  jmp     short loc_18003D416
0x18003d47f  mov     ebx, edi
0x18003d481  jmp     loc_18003D3F3
0x18003d486  movzx   ebx, di
0x18003d489  or      ebx, 80070000h
0x18003d48f  jmp     loc_18003D38C
0x18003d494  mov     edx, 2Dh ; '-'
0x18003d499  jmp     loc_18003D3B4
```
