# CTSSession::CTSSession(ITSNotifySink *,CSessionList *,ITerminal *,long *,long)

- ea: `0x180047dac`
- end: `0x180048340`
- name: `??0CTSSession@@QEAA@PEAUITSNotifySink@@PEAVCSessionList@@PEAUITerminal@@PEAJJ@Z`
- size: `1428`
- prototype: `CTSSession *__fastcall(CTSSession *__hidden this, struct ITSNotifySink *, struct CSessionList *, struct ITerminal *, int *, int)`
- caller_count: `1`
- callee_count: `17`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18002eeb4`

## callees

- `0x1800077a0`
- `0x1800151d0`
- `0x180016740`
- `0x180022030`
- `0x180036da4`
- `0x180047dac`
- `0x180048348`
- `0x180048368`
- `0x180048380`
- `0x180048448`
- `0x1800485a0`
- `0x18004ab8c`
- `0x18004ac14`
- `0x18004e850`
- `0x18004ec5c`
- `0x18004f354`
- `0x18009c010`

## import_xrefs

- `ntdll!NtQuerySystemTime` at `0x180048117`
- `ntdll!NtQuerySystemTime` at `0x180048117`
- `ntdll!EtwEventActivityIdControl` at `0x18004802e`
- `ntdll!EtwEventActivityIdControl` at `0x18004830f`
- `ntdll!EtwEventActivityIdControl` at `0x18004802e`
- `ntdll!EtwEventActivityIdControl` at `0x18004830f`
- `RPCRT4!UuidCreate` at `0x1800482b0`
- `RPCRT4!UuidCreate` at `0x1800482b0`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x18004812a`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x18004812a`

## string_xrefs

- `0x1800482df`: `UuidCreate failed: 0x%x in %s`

## pseudocode

```c
// Hidden C++ exception states: #wind=19
CTSSession *__fastcall CTSSession::CTSSession(
        CTSSession *this,
        struct ITSNotifySink *a2,
        struct CSessionList *a3,
        struct ITerminal *a4,
        int *a5,
        int a6)
{
  CEventDispatcher **v8; // r12
  int v9; // ebx
  CEventDispatcher *v10; // r14
  int v11; // eax
  int v12; // eax
  CEventDispatcher *v13; // rax
  CEventDispatcher *v14; // rax
  int v15; // eax
  int v16; // eax
  int v17; // eax
  struct ITSNotifySink *v18; // rax
  const char *v19; // rdx
  const char *v20; // r8
  CTSObjectStorage *v21; // rcx
  __int64 v22; // rsi
  RPC_STATUS v23; // eax
  int v25; // [rsp+30h] [rbp-69h] BYREF
  struct CSessionList *v26; // [rsp+38h] [rbp-61h]
  struct ITSNotifySink *v27; // [rsp+40h] [rbp-59h]
  int *v28; // [rsp+48h] [rbp-51h]
  CTSSession *v29; // [rsp+50h] [rbp-49h]
  __int128 v30; // [rsp+58h] [rbp-41h] BYREF
  int v31; // [rsp+68h] [rbp-31h]
  __int128 v32; // [rsp+70h] [rbp-29h] BYREF
  __int128 v33; // [rsp+80h] [rbp-19h] BYREF

  v26 = a3;
  v27 = a2;
  v29 = this;
  v28 = a5;
  CTSPrivateObject<ITSSessionPrivate>::CTSPrivateObject<ITSSessionPrivate>();
  *((_QWORD *)this + 199) = this;
  *(_QWORD *)this = &CTSSession::`vftable';
  *((_DWORD *)this + 424) = 0;
  *((_QWORD *)this + 213) = 0;
  *((_QWORD *)this + 214) = 0;
  *((_DWORD *)this + 430) = 0;
  *((_QWORD *)this + 216) = &CTSSession::CCommonSessionData::`vftable';
  *((_DWORD *)this + 436) = a6;
  *((_QWORD *)this + 219) = 0;
  *((_DWORD *)this + 440) = 0;
  CTSSession::CCommonSessionData::CShadowPipe::CShadowPipe((CTSSession *)((char *)this + 1768));
  *((_QWORD *)this + 223) = 0;
  *((_QWORD *)this + 224) = &CTSSession::CCsrEventSink::`vftable';
  *((_QWORD *)this + 225) = 0;
  *((_DWORD *)this + 452) = 0;
  *((_QWORD *)this + 227) = 0;
  v8 = (CEventDispatcher **)((char *)this + 1824);
  *((_QWORD *)this + 228) = 0;
  *((_QWORD *)this + 229) = 0;
  *((_QWORD *)this + 230) = 0;
  *((_QWORD *)this + 231) = 0;
  *((_DWORD *)this + 488) = 0;
  *((_DWORD *)this + 490) = 12;
  *((_DWORD *)this + 516) = -1;
  *((_DWORD *)this + 517) = -1;
  *((_DWORD *)this + 518) = -1;
  std::vector<std::wstring>::vector<std::wstring>((char *)this + 2080);
  *((_QWORD *)this + 263) = 0;
  *((_DWORD *)this + 528) = -1;
  *(_OWORD *)((char *)this + 2644) = *(_OWORD *)L"Default DisplayName set by LSM";
  *(_OWORD *)((char *)this + 2660) = *(_OWORD *)L"DisplayName set by LSM";
  *(_OWORD *)((char *)this + 2676) = *(_OWORD *)L"ame set by LSM";
  *(_OWORD *)((char *)this + 2690) = *(_OWORD *)L" by LSM";
  memset_0((char *)this + 2706, 0, 0x1C4u);
  *((_DWORD *)this + 791) = 0;
  *((_DWORD *)this + 806) = -1;
  *((_QWORD *)this + 404) = 0;
  *((_QWORD *)this + 405) = 0;
  *((_DWORD *)this + 812) = 0;
  *((_DWORD *)this + 814) = 0;
  *((_DWORD *)this + 815) = -1;
  *((_DWORD *)this + 1136) = 0;
  *((_DWORD *)this + 1137) = -1;
  *(GUID *)((char *)this + 5832) = IID_IUnknown;
  *((_DWORD *)this + 1462) = 0;
  *(_OWORD *)((char *)this + 5852) = xmmword_1800A9E88;
  *((_QWORD *)this + 734) = &CTSSessionSecurityDescriptor::`vftable';
  *((_QWORD *)this + 735) = &CTSSecurityDescriptor::`vftable';
  *((_QWORD *)this + 736) = 0;
  *((_QWORD *)this + 737) = 0;
  *((_QWORD *)this + 738) = &CTSSecurityDescriptor::`vftable';
  *((_QWORD *)this + 739) = 0;
  *((_QWORD *)this + 740) = 0;
  *((_QWORD *)this + 741) = 0;
  *((_QWORD *)this + 742) = 0;
  *((_QWORD *)this + 808) = 0;
  v9 = -2147467263;
  v25 = -2147467263;
  v33 = 0;
  v10 = (CTSSession *)((char *)this + 3208);
  *(_OWORD *)((char *)this + 3208) = 0;
  if ( a4 )
    (*(void (__fastcall **)(struct ITerminal *, char *))(*(_QWORD *)a4 + 216LL))(a4, (char *)this + 3208);
  v31 = -2147467259;
  if ( this == (CTSSession *)-3208LL
    || (v30 = *(_OWORD *)v10, v10 = 0, (unsigned int)EtwEventActivityIdControl(4, &v30)) )
  {
    v30 = 0;
  }
  else
  {
    v31 = 0;
  }
  if ( a4 )
  {
    v32 = 0;
    v25 = (int)v10;
    v11 = (*(__int64 (__fastcall **)(struct ITerminal *, __int128 *, char *, int *, __int128 *))(*(_QWORD *)a4 + 136LL))(
            a4,
            &v33,
            (char *)this + 3224,
            &v25,
            &v32);
    v9 = v11;
    if ( v11 < 0 )
    {
      _DbgPrintMessage(8, "GetTerminalType failed: 0x%x in %s", (unsigned int)v11, "CTSSession::CTSSession");
      goto LABEL_43;
    }
    v12 = CTSSession::CSessionReconnectController::TryApplyTerminalToSession(
            (char *)this + 5848,
            (unsigned int)v25,
            &v32);
    v9 = v12;
    if ( v12 < 0 )
    {
      _DbgPrintMessage(
        8,
        "SessionReconnectController.TryApplyTerminalToSession failed: 0x%x in %s",
        (unsigned int)v12,
        "CTSSession::CTSSession");
      goto LABEL_43;
    }
    *(_OWORD *)((char *)this + 5832) = v33;
    v9 = (int)v10;
    v25 = (int)v10;
  }
  *((_QWORD *)this + 225) = this;
  *((_QWORD *)this + 217) = this;
  *((_QWORD *)this + 222) = (char *)this + 1728;
  SmartPtr<ITerminal>::operator=((char *)this + 1816, a4);
  SmartPtr<CSessionList>::operator=((char *)this + 1840, v26);
  NtQuerySystemTime((PLARGE_INTEGER)this + 246);
  GetSystemTime((LPSYSTEMTIME)this + 125);
  *((_QWORD *)this + 247) = v10;
  *((_QWORD *)this + 248) = v10;
  *((_QWORD *)this + 249) = v10;
  v13 = (CEventDispatcher *)operator new(0x738u, (const struct std::nothrow_t *)&std::nothrow);
  v26 = v13;
  if ( v13 )
  {
    v14 = CEventDispatcher::CEventDispatcher(v13, &v25);
    v9 = v25;
  }
  else
  {
    v14 = v10;
  }
  SmartPtr<CEventDispatcher>::operator=((char *)this + 1824, v14);
  if ( *v8 )
  {
    if ( v9 < 0 )
    {
      _DbgPrintMessage(8, "CEventDispatcher failed: 0x%x in %s", (unsigned int)v9, "CTSSession::CTSSession");
      goto LABEL_43;
    }
    v15 = CEventDispatcher::Advise(*v8, v27, (struct IUnknown **)this + 229);
    v9 = v15;
    if ( v15 < 0 )
    {
      _DbgPrintMessage(8, "Advise failed: 0x%x in %s", (unsigned int)v15, "CTSSession::CTSSession");
      goto LABEL_43;
    }
    v16 = CResource::Initialize((CTSSession *)((char *)this + 1856));
    v9 = v16;
    if ( v16 < 0 )
    {
      _DbgPrintMessage(8, "Lock.Initialize failed: 0x%x in %s", (unsigned int)v16, "CTSSession::CTSSession");
      goto LABEL_43;
    }
    memset_0((char *)this + 2116, 0, 0x202u);
    *((_DWORD *)this + 658) = (_DWORD)v10;
    v17 = CResource::Initialize((CTSSession *)((char *)this + 1600));
    v9 = v17;
    v25 = v17;
    if ( v17 < 0 )
    {
      _DbgPrintMessage(
        8,
        "SessionAttributeArrayLock.Initialize failed: 0x%x in %s",
        (unsigned int)v17,
        "CTSSession::CTSSession");
      goto LABEL_43;
    }
    v18 = (struct ITSNotifySink *)operator new(0x6F0u, (const struct std::nothrow_t *)&std::nothrow);
    v27 = v18;
    if ( v18 )
    {
      v21 = CTSObjectStorage::CTSObjectStorage(v18, v19, v20, a6, &v25);
      v9 = v25;
    }
    else
    {
      v21 = v10;
    }
    v22 = *((_QWORD *)this + 213);
    *((_QWORD *)this + 213) = v21;
    if ( v21 )
      (*(void (__fastcall **)(CTSObjectStorage *))(*(_QWORD *)v21 + 8LL))(v21);
    if ( v22 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
    if ( *((CEventDispatcher **)this + 213) != v10 )
    {
      if ( v9 >= 0 )
      {
        v23 = UuidCreate((UUID *)((char *)this + 3192));
        if ( !v23 || v23 == 1824 )
        {
          *((_WORD *)this + 2972) = (_WORD)v10;
        }
        else
        {
          if ( v23 > 0 )
            v9 = (unsigned __int16)v23 | 0x80070000;
          else
            v9 = v23;
          _DbgPrintMessage(8, "UuidCreate failed: 0x%x in %s", (unsigned int)v9, "CTSSession::CTSSession");
        }
      }
      else
      {
        _DbgPrintMessage(8, "ptrSessionAttributeArray failed: 0x%x in %s", (unsigned int)v9, "CTSSession::CTSSession");
      }
      goto LABEL_43;
    }
  }
  v9 = -2147024882;
LABEL_43:
  *v28 = v9;
  if ( v31 >= (int)v10 )
    EtwEventActivityIdControl(2, &v30);
  return this;
}

```

## disassembly

```asm
0x180047dac  push    rbp
0x180047dae  push    rbx
0x180047daf  push    rsi
0x180047db0  push    rdi
0x180047db1  push    r12
0x180047db3  push    r13
0x180047db5  push    r14
0x180047db7  push    r15
0x180047db9  lea     rbp, [rsp-0Fh]
0x180047dbe  sub     rsp, 0A8h
0x180047dc5  mov     rax, cs:__security_cookie
0x180047dcc  xor     rax, rsp
0x180047dcf  mov     [rbp+47h+var_50], rax
0x180047dd3  mov     rsi, r9
0x180047dd6  mov     [rbp+47h+var_A8], r8
0x180047dda  mov     [rbp+47h+var_A0], rdx
0x180047dde  mov     rdi, rcx
0x180047de1  mov     [rbp+47h+var_90], rcx
0x180047de5  mov     rax, [rbp+47h+arg_20]
0x180047de9  mov     [rbp+47h+var_98], rax
0x180047ded  call    ??0?$CTSPrivateObject@VITSSessionPrivate@@@@QEAA@PEBD@Z; CTSPrivateObject<ITSSessionPrivate>::CTSPrivateObject<ITSSessionPrivate>(char const *)
0x180047df2  mov     [rdi+638h], rdi
0x180047df9  lea     rax, ??_7CTSSession@@6B@; const CTSSession::`vftable'
0x180047e00  mov     [rdi], rax
0x180047e03  xor     r14d, r14d
0x180047e06  mov     [rdi+6A0h], r14d
0x180047e0d  mov     [rdi+6A8h], r14
0x180047e14  mov     [rdi+6B0h], r14
0x180047e1b  mov     [rdi+6B8h], r14d
0x180047e22  lea     r15, [rdi+6C0h]
0x180047e29  lea     rax, ??_7CCommonSessionData@CTSSession@@6B@; const CTSSession::CCommonSessionData::`vftable'
0x180047e30  mov     [r15], rax
0x180047e33  mov     eax, [rbp+47h+arg_28]
0x180047e36  mov     [r15+10h], eax
0x180047e3a  mov     [r15+18h], r14
0x180047e3e  mov     [r15+20h], r14d
0x180047e42  lea     rcx, [r15+28h]; this
0x180047e46  call    ??0CShadowPipe@CCommonSessionData@CTSSession@@QEAA@XZ; CTSSession::CCommonSessionData::CShadowPipe::CShadowPipe(void)
0x180047e4b  mov     [r15+38h], r14
0x180047e4f  lea     rax, ??_7CCsrEventSink@CTSSession@@6B@; const CTSSession::CCsrEventSink::`vftable'
0x180047e56  mov     [rdi+700h], rax
0x180047e5d  mov     [rdi+708h], r14
0x180047e64  mov     [rdi+710h], r14d
0x180047e6b  mov     [rdi+718h], r14
0x180047e72  lea     r12, [rdi+720h]
0x180047e79  mov     [r12], r14
0x180047e7d  mov     [rdi+728h], r14
0x180047e84  mov     [rdi+730h], r14
0x180047e8b  mov     [rdi+738h], r14
0x180047e92  mov     [rdi+7A0h], r14d
0x180047e99  mov     dword ptr [rdi+7A8h], 0Ch
0x180047ea3  or      ebx, 0FFFFFFFFh
0x180047ea6  mov     [rdi+810h], ebx
0x180047eac  mov     [rdi+814h], ebx
0x180047eb2  mov     [rdi+818h], ebx
0x180047eb8  lea     rcx, [rdi+820h]
0x180047ebf  call    ??0?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::vector<std::wstring>::vector<std::wstring>(void)
0x180047ec4  nop
0x180047ec5  mov     [rdi+838h], r14
0x180047ecc  mov     [rdi+840h], ebx
0x180047ed2  movups  xmm0, xmmword ptr cs:aDefaultDisplay; "Default DisplayName set by LSM"
0x180047ed9  movups  xmmword ptr [rdi+0A54h], xmm0
0x180047ee0  movups  xmm1, xmmword ptr cs:aDefaultDisplay+10h; "DisplayName set by LSM"
0x180047ee7  movups  xmmword ptr [rdi+0A64h], xmm1
0x180047eee  movups  xmm0, xmmword ptr cs:aDefaultDisplay+20h; "ame set by LSM"
0x180047ef5  movups  xmmword ptr [rdi+0A74h], xmm0
0x180047efc  movups  xmm1, xmmword ptr cs:aDefaultDisplay+2Eh; " by LSM"
0x180047f03  movups  xmmword ptr [rdi+0A82h], xmm1
0x180047f0a  lea     rcx, [rdi+0A92h]; void *
0x180047f11  xor     edx, edx; Val
0x180047f13  mov     r8d, 1C4h; Size
0x180047f19  call    memset_0
0x180047f1e  mov     [rdi+0C5Ch], r14d
0x180047f25  mov     dword ptr [rdi+0C98h], 0FFFFFFFFh
0x180047f2f  mov     [rdi+0CA0h], r14
0x180047f36  mov     [rdi+0CA8h], r14
0x180047f3d  mov     [rdi+0CB0h], r14d
0x180047f44  mov     [rdi+0CB8h], r14d
0x180047f4b  mov     [rdi+0CBCh], ebx
0x180047f51  mov     [rdi+11C0h], r14d
0x180047f58  mov     [rdi+11C4h], ebx
0x180047f5e  movups  xmm0, xmmword ptr cs:IID_IUnknown.Data1
0x180047f65  movdqu  xmmword ptr [rdi+16C8h], xmm0
0x180047f6d  lea     r13, [rdi+16D8h]
0x180047f74  mov     [r13+0], r14d
0x180047f78  movups  xmm0, cs:xmmword_1800A9E88
0x180047f7f  movdqu  xmmword ptr [r13+4], xmm0
0x180047f85  lea     rax, ??_7CTSSessionSecurityDescriptor@@6B@; const CTSSessionSecurityDescriptor::`vftable'
0x180047f8c  mov     [rdi+16F0h], rax
0x180047f93  lea     rax, ??_7CTSSecurityDescriptor@@6B@; const CTSSecurityDescriptor::`vftable'
0x180047f9a  mov     [rdi+16F8h], rax
0x180047fa1  mov     [rdi+1700h], r14
0x180047fa8  mov     [rdi+1708h], r14
0x180047faf  mov     [rdi+1710h], rax
0x180047fb6  mov     [rdi+1718h], r14
0x180047fbd  mov     [rdi+1720h], r14
0x180047fc4  mov     [rdi+1728h], r14
0x180047fcb  mov     [rdi+1730h], r14
0x180047fd2  mov     [rdi+1940h], r14
0x180047fd9  mov     ebx, 80004001h
0x180047fde  mov     [rbp+47h+var_B0], ebx
0x180047fe1  xorps   xmm0, xmm0
0x180047fe4  movups  [rbp+47h+var_60], xmm0
0x180047fe8  lea     r14, [rdi+0C88h]
0x180047fef  xorps   xmm1, xmm1
0x180047ff2  movups  xmmword ptr [r14], xmm1
0x180047ff6  test    rsi, rsi
0x180047ff9  jz      short loc_180048010
0x180047ffb  mov     rax, [rsi]
0x180047ffe  mov     rdx, r14
0x180048001  mov     rcx, rsi
0x180048004  mov     rax, [rax+0D8h]
0x18004800b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048010  mov     [rbp+47h+var_78], 80004005h
0x180048017  test    r14, r14
0x18004801a  jz      short loc_180048047
0x18004801c  movups  xmm0, xmmword ptr [r14]
0x180048020  movdqu  [rbp+47h+var_88], xmm0
0x180048025  lea     rdx, [rbp+47h+var_88]
0x180048029  mov     ecx, 4
0x18004802e  call    cs:__imp_EtwEventActivityIdControl
0x180048035  nop     dword ptr [rax+rax+00h]
0x18004803a  xor     r14d, r14d
0x18004803d  test    eax, eax
0x18004803f  jnz     short loc_180048047
0x180048041  mov     [rbp+47h+var_78], r14d
0x180048045  jmp     short loc_18004804E
0x180048047  xorps   xmm0, xmm0
0x18004804a  movups  [rbp+47h+var_88], xmm0
0x18004804e  test    rsi, rsi
0x180048051  jz      loc_1800480E2
0x180048057  xorps   xmm0, xmm0
0x18004805a  movups  [rbp+47h+var_70], xmm0
0x18004805e  mov     [rbp+47h+var_B0], r14d
0x180048062  mov     rax, [rsi]
0x180048065  lea     rcx, [rbp+47h+var_70]
0x180048069  mov     [rsp+0E0h+var_C0], rcx
0x18004806e  lea     r9, [rbp+47h+var_B0]
0x180048072  lea     r8, [rdi+0C98h]
0x180048079  lea     rdx, [rbp+47h+var_60]
0x18004807d  mov     rcx, rsi
0x180048080  mov     rax, [rax+88h]
0x180048087  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004808c  mov     ebx, eax
0x18004808e  test    eax, eax
0x180048090  jns     short loc_1800480B2
0x180048092  lea     rdx, aGetterminaltyp; "GetTerminalType failed: 0x%x in %s"
0x180048099  mov     r8d, eax
0x18004809c  lea     r9, aCtssessionCtss; "CTSSession::CTSSession"
0x1800480a3  mov     ecx, 8; int
0x1800480a8  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800480ad  jmp     loc_1800482FA
0x1800480b2  lea     r8, [rbp+47h+var_70]
0x1800480b6  mov     edx, [rbp+47h+var_B0]
0x1800480b9  mov     rcx, r13
0x1800480bc  call    ?TryApplyTerminalToSession@CSessionReconnectController@CTSSession@@QEAAJW4__MIDL___MIDL_itf_lsminterfacesdef_0000_0001_0004@@AEAU_GUID@@@Z; CTSSession::CSessionReconnectController::TryApplyTerminalToSession(__MIDL___MIDL_itf_lsminterfacesdef_0000_0001_0004,_GUID &)
0x1800480c1  mov     ebx, eax
0x1800480c3  test    eax, eax
0x1800480c5  jns     short loc_1800480D0
0x1800480c7  lea     rdx, aSessionreconne_0; "SessionReconnectController.TryApplyTerm"...
0x1800480ce  jmp     short loc_180048099
0x1800480d0  movups  xmm0, [rbp+47h+var_60]
0x1800480d4  movdqu  xmmword ptr [rdi+16C8h], xmm0
0x1800480dc  mov     ebx, r14d
0x1800480df  mov     [rbp+47h+var_B0], ebx
0x1800480e2  mov     [rdi+708h], rdi
0x1800480e9  mov     [r15+8], rdi
0x1800480ed  mov     [r15+30h], r15
0x1800480f1  mov     rdx, rsi
0x1800480f4  lea     rcx, [rdi+718h]
0x1800480fb  call    ??4?$SmartPtr@UITerminal@@@@QEAAAEAV0@PEAUITerminal@@@Z; SmartPtr<ITerminal>::operator=(ITerminal *)
0x180048100  mov     rdx, [rbp+47h+var_A8]
0x180048104  lea     rcx, [rdi+730h]
0x18004810b  call    ??4?$SmartPtr@VCSessionList@@@@QEAAAEAV0@PEAVCSessionList@@@Z; SmartPtr<CSessionList>::operator=(CSessionList *)
0x180048110  lea     rcx, [rdi+7B0h]; SystemTime
0x180048117  call    cs:__imp_NtQuerySystemTime
0x18004811e  nop     dword ptr [rax+rax+00h]
0x180048123  lea     rcx, [rdi+7D0h]; lpSystemTime
0x18004812a  call    cs:__imp_GetSystemTime
0x180048131  nop     dword ptr [rax+rax+00h]
0x180048136  mov     [rdi+7B8h], r14
0x18004813d  mov     [rdi+7C0h], r14
0x180048144  mov     [rdi+7C8h], r14
0x18004814b  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180048152  mov     ecx, 738h; unsigned __int64
0x180048157  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18004815c  mov     [rbp+47h+var_A8], rax
0x180048160  test    rax, rax
0x180048163  jz      short loc_180048176
0x180048165  lea     rdx, [rbp+47h+var_B0]; int *
0x180048169  mov     rcx, rax; this
0x18004816c  call    ??0CEventDispatcher@@QEAA@PEAJ@Z; CEventDispatcher::CEventDispatcher(long *)
0x180048171  mov     ebx, [rbp+47h+var_B0]
0x180048174  jmp     short loc_180048179
0x180048176  mov     rax, r14
0x180048179  mov     rdx, rax
0x18004817c  mov     rcx, r12
0x18004817f  call    ??4?$SmartPtr@VCEventDispatcher@@@@QEAAAEAV0@PEAVCEventDispatcher@@@Z; SmartPtr<CEventDispatcher>::operator=(CEventDispatcher *)
0x180048184  mov     rcx, [r12]; this
0x180048188  test    rcx, rcx
0x18004818b  jz      loc_1800482F5
0x180048191  test    ebx, ebx
0x180048193  jns     short loc_1800481A4
0x180048195  mov     r8d, ebx
0x180048198  lea     rdx, aCeventdispatch_2; "CEventDispatcher failed: 0x%x in %s"
0x18004819f  jmp     loc_18004809C
0x1800481a4  lea     r8, [rdi+728h]; struct IUnknown **
0x1800481ab  mov     rdx, [rbp+47h+var_A0]; struct ITSNotifySink *
0x1800481af  call    ?Advise@CEventDispatcher@@UEAAJPEAUITSNotifySink@@PEAPEAUIUnknown@@@Z; CEventDispatcher::Advise(ITSNotifySink *,IUnknown * *)
0x1800481b4  mov     ebx, eax
0x1800481b6  test    eax, eax
0x1800481b8  jns     short loc_1800481C6
0x1800481ba  lea     rdx, aAdviseFailed0x; "Advise failed: 0x%x in %s"
0x1800481c1  jmp     loc_180048099
0x1800481c6  lea     rcx, [rdi+740h]; this
0x1800481cd  call    ?Initialize@CResource@@QEAAJXZ; CResource::Initialize(void)
0x1800481d2  mov     ebx, eax
0x1800481d4  test    eax, eax
0x1800481d6  jns     short loc_1800481E4
0x1800481d8  lea     rdx, aLockInitialize; "Lock.Initialize failed: 0x%x in %s"
0x1800481df  jmp     loc_180048099
0x1800481e4  lea     rcx, [rdi+844h]; void *
0x1800481eb  xor     edx, edx; Val
0x1800481ed  mov     r8d, 202h; Size
0x1800481f3  call    memset_0
0x1800481f8  mov     [rdi+0A48h], r14d
0x1800481ff  lea     rcx, [rdi+640h]; this
0x180048206  call    ?Initialize@CResource@@QEAAJXZ; CResource::Initialize(void)
0x18004820b  mov     ebx, eax
0x18004820d  mov     [rbp+47h+var_B0], eax
0x180048210  test    eax, eax
0x180048212  jns     short loc_180048220
0x180048214  lea     rdx, aSessionattribu; "SessionAttributeArrayLock.Initialize fa"...
0x18004821b  jmp     loc_180048099
0x180048220  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180048227  mov     ecx, 6F0h; unsigned __int64
0x18004822c  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180048231  mov     [rbp+47h+var_A0], rax
0x180048235  test    rax, rax
0x180048238  jz      short loc_180048257
0x18004823a  lea     rcx, [rbp+47h+var_B0]
0x18004823e  mov     [rsp+0E0h+var_C0], rcx; int *
0x180048243  mov     r9d, [rbp+47h+arg_28]; int
0x180048247  mov     rcx, rax; this
0x18004824a  call    ??0CTSObjectStorage@@QEAA@PEBD0JPEAJ@Z; CTSObjectStorage::CTSObjectStorage(char const *,char const *,long,long *)
0x18004824f  mov     rcx, rax
0x180048252  mov     ebx, [rbp+47h+var_B0]
0x180048255  jmp     short loc_18004825A
0x180048257  mov     rcx, r14
0x18004825a  mov     rsi, [rdi+6A8h]
0x180048261  mov     [rdi+6A8h], rcx
0x180048268  test    rcx, rcx
0x18004826b  jz      short loc_180048279
0x18004826d  mov     rax, [rcx]
0x180048270  mov     rax, [rax+8]
0x180048274  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048279  test    rsi, rsi
0x18004827c  jz      short loc_18004828D
0x18004827e  mov     rax, [rsi]
0x180048281  mov     rcx, rsi
0x180048284  mov     rax, [rax+10h]
0x180048288  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004828d  cmp     [rdi+6A8h], r14
0x180048294  jz      short loc_1800482F5
0x180048296  test    ebx, ebx
0x180048298  jns     short loc_1800482A9
0x18004829a  mov     r8d, ebx
0x18004829d  lea     rdx, aPtrsessionattr_0; "ptrSessionAttributeArray failed: 0x%x i"...
0x1800482a4  jmp     loc_18004809C
0x1800482a9  lea     rcx, [rdi+0C78h]; Uuid
0x1800482b0  call    cs:__imp_UuidCreate
0x1800482b7  nop     dword ptr [rax+rax+00h]
0x1800482bc  test    eax, eax
0x1800482be  jz      short loc_1800482EB
0x1800482c0  cmp     eax, 720h
0x1800482c5  jz      short loc_1800482EB
0x1800482c7  test    eax, eax
0x1800482c9  jg      short loc_1800482CF
0x1800482cb  mov     ebx, eax
0x1800482cd  jmp     short loc_1800482D8
0x1800482cf  movzx   ebx, ax
0x1800482d2  or      ebx, 80070000h
0x1800482d8  test    ebx, ebx
0x1800482da  jns     short loc_1800482EB
0x1800482dc  mov     r8d, ebx
0x1800482df  lea     rdx, aUuidcreateFail; "UuidCreate failed: 0x%x in %s"
0x1800482e6  jmp     loc_18004809C
0x1800482eb  mov     [rdi+1738h], r14w
0x1800482f3  jmp     short loc_1800482FA
0x1800482f5  mov     ebx, 8007000Eh
0x1800482fa  mov     rax, [rbp+47h+var_98]
0x1800482fe  mov     [rax], ebx
0x180048300  cmp     [rbp+47h+var_78], r14d
0x180048304  jl      short loc_18004831C
0x180048306  lea     rdx, [rbp+47h+var_88]
0x18004830a  mov     ecx, 2
0x18004830f  call    cs:__imp_EtwEventActivityIdControl
0x180048316  nop     dword ptr [rax+rax+00h]
0x18004831b  nop
0x18004831c  mov     rax, rdi
  ... truncated ...
```
