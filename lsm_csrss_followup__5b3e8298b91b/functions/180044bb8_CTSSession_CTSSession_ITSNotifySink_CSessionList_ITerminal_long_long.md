# CTSSession::CTSSession(ITSNotifySink *,CSessionList *,ITerminal *,long *,long)

- ea: `0x180044bb8`
- end: `0x18004512d`
- name: `??0CTSSession@@QEAA@PEAUITSNotifySink@@PEAVCSessionList@@PEAUITerminal@@PEAJJ@Z`
- size: `1397`
- prototype: `CTSSession *__fastcall(CTSSession *__hidden this, struct ITSNotifySink *, struct CSessionList *, struct ITerminal *, int *, int)`
- caller_count: `1`
- callee_count: `17`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18002cf64`

## callees

- `0x1800074c0`
- `0x180011490`
- `0x18001288c`
- `0x18001fd20`
- `0x180034c24`
- `0x180044bb8`
- `0x180045134`
- `0x180045150`
- `0x180045168`
- `0x180045464`
- `0x1800455ac`
- `0x180047b24`
- `0x180047bac`
- `0x18004b460`
- `0x18004b86c`
- `0x18004bf44`
- `0x180097010`

## import_xrefs

- `ntdll!NtQuerySystemTime` at `0x180044f1d`
- `ntdll!NtQuerySystemTime` at `0x180044f1d`
- `ntdll!EtwEventActivityIdControl` at `0x180044e3a`
- `ntdll!EtwEventActivityIdControl` at `0x180045103`
- `ntdll!EtwEventActivityIdControl` at `0x180044e3a`
- `ntdll!EtwEventActivityIdControl` at `0x180045103`
- `RPCRT4!UuidCreate` at `0x1800450aa`
- `RPCRT4!UuidCreate` at `0x1800450aa`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x180044f2a`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x180044f2a`

## string_xrefs

- `0x1800450d3`: `UuidCreate failed: 0x%x in %s`

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
  *(_OWORD *)((char *)this + 5852) = xmmword_1800A4D70;
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
0x180044bb8  push    rbp
0x180044bba  push    rbx
0x180044bbb  push    rsi
0x180044bbc  push    rdi
0x180044bbd  push    r12
0x180044bbf  push    r13
0x180044bc1  push    r14
0x180044bc3  push    r15
0x180044bc5  lea     rbp, [rsp-0Fh]
0x180044bca  sub     rsp, 0A8h
0x180044bd1  mov     rax, cs:__security_cookie
0x180044bd8  xor     rax, rsp
0x180044bdb  mov     [rbp+47h+var_50], rax
0x180044bdf  mov     rsi, r9
0x180044be2  mov     [rbp+47h+var_A8], r8
0x180044be6  mov     [rbp+47h+var_A0], rdx
0x180044bea  mov     rdi, rcx
0x180044bed  mov     [rbp+47h+var_90], rcx
0x180044bf1  mov     rax, [rbp+47h+arg_20]
0x180044bf5  mov     [rbp+47h+var_98], rax
0x180044bf9  call    ??0?$CTSPrivateObject@VITSSessionPrivate@@@@QEAA@PEBD@Z; CTSPrivateObject<ITSSessionPrivate>::CTSPrivateObject<ITSSessionPrivate>(char const *)
0x180044bfe  mov     [rdi+638h], rdi
0x180044c05  lea     rax, ??_7CTSSession@@6B@; const CTSSession::`vftable'
0x180044c0c  mov     [rdi], rax
0x180044c0f  xor     r14d, r14d
0x180044c12  mov     [rdi+6A0h], r14d
0x180044c19  mov     [rdi+6A8h], r14
0x180044c20  mov     [rdi+6B0h], r14
0x180044c27  mov     [rdi+6B8h], r14d
0x180044c2e  lea     r15, [rdi+6C0h]
0x180044c35  lea     rax, ??_7CCommonSessionData@CTSSession@@6B@; const CTSSession::CCommonSessionData::`vftable'
0x180044c3c  mov     [r15], rax
0x180044c3f  mov     eax, [rbp+47h+arg_28]
0x180044c42  mov     [r15+10h], eax
0x180044c46  mov     [r15+18h], r14
0x180044c4a  mov     [r15+20h], r14d
0x180044c4e  lea     rcx, [r15+28h]; this
0x180044c52  call    ??0CShadowPipe@CCommonSessionData@CTSSession@@QEAA@XZ; CTSSession::CCommonSessionData::CShadowPipe::CShadowPipe(void)
0x180044c57  mov     [r15+38h], r14
0x180044c5b  lea     rax, ??_7CCsrEventSink@CTSSession@@6B@; const CTSSession::CCsrEventSink::`vftable'
0x180044c62  mov     [rdi+700h], rax
0x180044c69  mov     [rdi+708h], r14
0x180044c70  mov     [rdi+710h], r14d
0x180044c77  mov     [rdi+718h], r14
0x180044c7e  lea     r12, [rdi+720h]
0x180044c85  mov     [r12], r14
0x180044c89  mov     [rdi+728h], r14
0x180044c90  mov     [rdi+730h], r14
0x180044c97  mov     [rdi+738h], r14
0x180044c9e  mov     [rdi+7A0h], r14d
0x180044ca5  mov     dword ptr [rdi+7A8h], 0Ch
0x180044caf  or      ebx, 0FFFFFFFFh
0x180044cb2  mov     [rdi+810h], ebx
0x180044cb8  mov     [rdi+814h], ebx
0x180044cbe  mov     [rdi+818h], ebx
0x180044cc4  lea     rcx, [rdi+820h]
0x180044ccb  call    ??0?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::vector<std::wstring>::vector<std::wstring>(void)
0x180044cd0  nop
0x180044cd1  mov     [rdi+838h], r14
0x180044cd8  mov     [rdi+840h], ebx
0x180044cde  movups  xmm0, xmmword ptr cs:aDefaultDisplay; "Default DisplayName set by LSM"
0x180044ce5  movups  xmmword ptr [rdi+0A54h], xmm0
0x180044cec  movups  xmm1, xmmword ptr cs:aDefaultDisplay+10h; "DisplayName set by LSM"
0x180044cf3  movups  xmmword ptr [rdi+0A64h], xmm1
0x180044cfa  movups  xmm0, xmmword ptr cs:aDefaultDisplay+20h; "ame set by LSM"
0x180044d01  movups  xmmword ptr [rdi+0A74h], xmm0
0x180044d08  movups  xmm1, xmmword ptr cs:aDefaultDisplay+2Eh; " by LSM"
0x180044d0f  movups  xmmword ptr [rdi+0A82h], xmm1
0x180044d16  lea     rcx, [rdi+0A92h]; void *
0x180044d1d  xor     edx, edx; Val
0x180044d1f  mov     r8d, 1C4h; Size
0x180044d25  call    memset_0
0x180044d2a  mov     [rdi+0C5Ch], r14d
0x180044d31  mov     dword ptr [rdi+0C98h], 0FFFFFFFFh
0x180044d3b  mov     [rdi+0CA0h], r14
0x180044d42  mov     [rdi+0CA8h], r14
0x180044d49  mov     [rdi+0CB0h], r14d
0x180044d50  mov     [rdi+0CB8h], r14d
0x180044d57  mov     [rdi+0CBCh], ebx
0x180044d5d  mov     [rdi+11C0h], r14d
0x180044d64  mov     [rdi+11C4h], ebx
0x180044d6a  movups  xmm0, xmmword ptr cs:IID_IUnknown.Data1
0x180044d71  movdqu  xmmword ptr [rdi+16C8h], xmm0
0x180044d79  lea     r13, [rdi+16D8h]
0x180044d80  mov     [r13+0], r14d
0x180044d84  movups  xmm0, cs:xmmword_1800A4D70
0x180044d8b  movdqu  xmmword ptr [r13+4], xmm0
0x180044d91  lea     rax, ??_7CTSSessionSecurityDescriptor@@6B@; const CTSSessionSecurityDescriptor::`vftable'
0x180044d98  mov     [rdi+16F0h], rax
0x180044d9f  lea     rax, ??_7CTSSecurityDescriptor@@6B@; const CTSSecurityDescriptor::`vftable'
0x180044da6  mov     [rdi+16F8h], rax
0x180044dad  mov     [rdi+1700h], r14
0x180044db4  mov     [rdi+1708h], r14
0x180044dbb  mov     [rdi+1710h], rax
0x180044dc2  mov     [rdi+1718h], r14
0x180044dc9  mov     [rdi+1720h], r14
0x180044dd0  mov     [rdi+1728h], r14
0x180044dd7  mov     [rdi+1730h], r14
0x180044dde  mov     [rdi+1940h], r14
0x180044de5  mov     ebx, 80004001h
0x180044dea  mov     [rbp+47h+var_B0], ebx
0x180044ded  xorps   xmm0, xmm0
0x180044df0  movups  [rbp+47h+var_60], xmm0
0x180044df4  lea     r14, [rdi+0C88h]
0x180044dfb  xorps   xmm1, xmm1
0x180044dfe  movups  xmmword ptr [r14], xmm1
0x180044e02  test    rsi, rsi
0x180044e05  jz      short loc_180044E1C
0x180044e07  mov     rax, [rsi]
0x180044e0a  mov     rdx, r14
0x180044e0d  mov     rcx, rsi
0x180044e10  mov     rax, [rax+0D8h]
0x180044e17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044e1c  mov     [rbp+47h+var_78], 80004005h
0x180044e23  test    r14, r14
0x180044e26  jz      short loc_180044E4D
0x180044e28  movups  xmm0, xmmword ptr [r14]
0x180044e2c  movdqu  [rbp+47h+var_88], xmm0
0x180044e31  lea     rdx, [rbp+47h+var_88]
0x180044e35  mov     ecx, 4
0x180044e3a  call    cs:__imp_EtwEventActivityIdControl
0x180044e40  xor     r14d, r14d
0x180044e43  test    eax, eax
0x180044e45  jnz     short loc_180044E4D
0x180044e47  mov     [rbp+47h+var_78], r14d
0x180044e4b  jmp     short loc_180044E54
0x180044e4d  xorps   xmm0, xmm0
0x180044e50  movups  [rbp+47h+var_88], xmm0
0x180044e54  test    rsi, rsi
0x180044e57  jz      loc_180044EE8
0x180044e5d  xorps   xmm0, xmm0
0x180044e60  movups  [rbp+47h+var_70], xmm0
0x180044e64  mov     [rbp+47h+var_B0], r14d
0x180044e68  mov     rax, [rsi]
0x180044e6b  lea     rcx, [rbp+47h+var_70]
0x180044e6f  mov     [rsp+0E0h+var_C0], rcx
0x180044e74  lea     r9, [rbp+47h+var_B0]
0x180044e78  lea     r8, [rdi+0C98h]
0x180044e7f  lea     rdx, [rbp+47h+var_60]
0x180044e83  mov     rcx, rsi
0x180044e86  mov     rax, [rax+88h]
0x180044e8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044e92  mov     ebx, eax
0x180044e94  test    eax, eax
0x180044e96  jns     short loc_180044EB8
0x180044e98  lea     rdx, aGetterminaltyp; "GetTerminalType failed: 0x%x in %s"
0x180044e9f  mov     r8d, eax
0x180044ea2  lea     r9, aCtssessionCtss; "CTSSession::CTSSession"
0x180044ea9  mov     ecx, 8; int
0x180044eae  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180044eb3  jmp     loc_1800450EE
0x180044eb8  lea     r8, [rbp+47h+var_70]
0x180044ebc  mov     edx, [rbp+47h+var_B0]
0x180044ebf  mov     rcx, r13
0x180044ec2  call    ?TryApplyTerminalToSession@CSessionReconnectController@CTSSession@@QEAAJW4__MIDL___MIDL_itf_lsminterfacesdef_0000_0001_0004@@AEAU_GUID@@@Z; CTSSession::CSessionReconnectController::TryApplyTerminalToSession(__MIDL___MIDL_itf_lsminterfacesdef_0000_0001_0004,_GUID &)
0x180044ec7  mov     ebx, eax
0x180044ec9  test    eax, eax
0x180044ecb  jns     short loc_180044ED6
0x180044ecd  lea     rdx, aSessionreconne_0; "SessionReconnectController.TryApplyTerm"...
0x180044ed4  jmp     short loc_180044E9F
0x180044ed6  movups  xmm0, [rbp+47h+var_60]
0x180044eda  movdqu  xmmword ptr [rdi+16C8h], xmm0
0x180044ee2  mov     ebx, r14d
0x180044ee5  mov     [rbp+47h+var_B0], ebx
0x180044ee8  mov     [rdi+708h], rdi
0x180044eef  mov     [r15+8], rdi
0x180044ef3  mov     [r15+30h], r15
0x180044ef7  mov     rdx, rsi
0x180044efa  lea     rcx, [rdi+718h]
0x180044f01  call    ??4?$SmartPtr@UITerminal@@@@QEAAAEAV0@PEAUITerminal@@@Z; SmartPtr<ITerminal>::operator=(ITerminal *)
0x180044f06  mov     rdx, [rbp+47h+var_A8]
0x180044f0a  lea     rcx, [rdi+730h]
0x180044f11  call    ??4?$SmartPtr@VCSessionList@@@@QEAAAEAV0@PEAVCSessionList@@@Z; SmartPtr<CSessionList>::operator=(CSessionList *)
0x180044f16  lea     rcx, [rdi+7B0h]; SystemTime
0x180044f1d  call    cs:__imp_NtQuerySystemTime
0x180044f23  lea     rcx, [rdi+7D0h]; lpSystemTime
0x180044f2a  call    cs:__imp_GetSystemTime
0x180044f30  mov     [rdi+7B8h], r14
0x180044f37  mov     [rdi+7C0h], r14
0x180044f3e  mov     [rdi+7C8h], r14
0x180044f45  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180044f4c  mov     ecx, 738h; unsigned __int64
0x180044f51  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180044f56  mov     [rbp+47h+var_A8], rax
0x180044f5a  test    rax, rax
0x180044f5d  jz      short loc_180044F70
0x180044f5f  lea     rdx, [rbp+47h+var_B0]; int *
0x180044f63  mov     rcx, rax; this
0x180044f66  call    ??0CEventDispatcher@@QEAA@PEAJ@Z; CEventDispatcher::CEventDispatcher(long *)
0x180044f6b  mov     ebx, [rbp+47h+var_B0]
0x180044f6e  jmp     short loc_180044F73
0x180044f70  mov     rax, r14
0x180044f73  mov     rdx, rax
0x180044f76  mov     rcx, r12
0x180044f79  call    ??4?$SmartPtr@VCEventDispatcher@@@@QEAAAEAV0@PEAVCEventDispatcher@@@Z; SmartPtr<CEventDispatcher>::operator=(CEventDispatcher *)
0x180044f7e  mov     rcx, [r12]; this
0x180044f82  test    rcx, rcx
0x180044f85  jz      loc_1800450E9
0x180044f8b  test    ebx, ebx
0x180044f8d  jns     short loc_180044F9E
0x180044f8f  mov     r8d, ebx
0x180044f92  lea     rdx, aCeventdispatch_2; "CEventDispatcher failed: 0x%x in %s"
0x180044f99  jmp     loc_180044EA2
0x180044f9e  lea     r8, [rdi+728h]; struct IUnknown **
0x180044fa5  mov     rdx, [rbp+47h+var_A0]; struct ITSNotifySink *
0x180044fa9  call    ?Advise@CEventDispatcher@@UEAAJPEAUITSNotifySink@@PEAPEAUIUnknown@@@Z; CEventDispatcher::Advise(ITSNotifySink *,IUnknown * *)
0x180044fae  mov     ebx, eax
0x180044fb0  test    eax, eax
0x180044fb2  jns     short loc_180044FC0
0x180044fb4  lea     rdx, aAdviseFailed0x; "Advise failed: 0x%x in %s"
0x180044fbb  jmp     loc_180044E9F
0x180044fc0  lea     rcx, [rdi+740h]; this
0x180044fc7  call    ?Initialize@CResource@@QEAAJXZ; CResource::Initialize(void)
0x180044fcc  mov     ebx, eax
0x180044fce  test    eax, eax
0x180044fd0  jns     short loc_180044FDE
0x180044fd2  lea     rdx, aLockInitialize; "Lock.Initialize failed: 0x%x in %s"
0x180044fd9  jmp     loc_180044E9F
0x180044fde  lea     rcx, [rdi+844h]; void *
0x180044fe5  xor     edx, edx; Val
0x180044fe7  mov     r8d, 202h; Size
0x180044fed  call    memset_0
0x180044ff2  mov     [rdi+0A48h], r14d
0x180044ff9  lea     rcx, [rdi+640h]; this
0x180045000  call    ?Initialize@CResource@@QEAAJXZ; CResource::Initialize(void)
0x180045005  mov     ebx, eax
0x180045007  mov     [rbp+47h+var_B0], eax
0x18004500a  test    eax, eax
0x18004500c  jns     short loc_18004501A
0x18004500e  lea     rdx, aSessionattribu; "SessionAttributeArrayLock.Initialize fa"...
0x180045015  jmp     loc_180044E9F
0x18004501a  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180045021  mov     ecx, 6F0h; unsigned __int64
0x180045026  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18004502b  mov     [rbp+47h+var_A0], rax
0x18004502f  test    rax, rax
0x180045032  jz      short loc_180045051
0x180045034  lea     rcx, [rbp+47h+var_B0]
0x180045038  mov     [rsp+0E0h+var_C0], rcx; int *
0x18004503d  mov     r9d, [rbp+47h+arg_28]; int
0x180045041  mov     rcx, rax; this
0x180045044  call    ??0CTSObjectStorage@@QEAA@PEBD0JPEAJ@Z; CTSObjectStorage::CTSObjectStorage(char const *,char const *,long,long *)
0x180045049  mov     rcx, rax
0x18004504c  mov     ebx, [rbp+47h+var_B0]
0x18004504f  jmp     short loc_180045054
0x180045051  mov     rcx, r14
0x180045054  mov     rsi, [rdi+6A8h]
0x18004505b  mov     [rdi+6A8h], rcx
0x180045062  test    rcx, rcx
0x180045065  jz      short loc_180045073
0x180045067  mov     rax, [rcx]
0x18004506a  mov     rax, [rax+8]
0x18004506e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045073  test    rsi, rsi
0x180045076  jz      short loc_180045087
0x180045078  mov     rax, [rsi]
0x18004507b  mov     rcx, rsi
0x18004507e  mov     rax, [rax+10h]
0x180045082  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045087  cmp     [rdi+6A8h], r14
0x18004508e  jz      short loc_1800450E9
0x180045090  test    ebx, ebx
0x180045092  jns     short loc_1800450A3
0x180045094  mov     r8d, ebx
0x180045097  lea     rdx, aPtrsessionattr_0; "ptrSessionAttributeArray failed: 0x%x i"...
0x18004509e  jmp     loc_180044EA2
0x1800450a3  lea     rcx, [rdi+0C78h]; Uuid
0x1800450aa  call    cs:__imp_UuidCreate
0x1800450b0  test    eax, eax
0x1800450b2  jz      short loc_1800450DF
0x1800450b4  cmp     eax, 720h
0x1800450b9  jz      short loc_1800450DF
0x1800450bb  test    eax, eax
0x1800450bd  jg      short loc_1800450C3
0x1800450bf  mov     ebx, eax
0x1800450c1  jmp     short loc_1800450CC
0x1800450c3  movzx   ebx, ax
0x1800450c6  or      ebx, 80070000h
0x1800450cc  test    ebx, ebx
0x1800450ce  jns     short loc_1800450DF
0x1800450d0  mov     r8d, ebx
0x1800450d3  lea     rdx, aUuidcreateFail; "UuidCreate failed: 0x%x in %s"
0x1800450da  jmp     loc_180044EA2
0x1800450df  mov     [rdi+1738h], r14w
0x1800450e7  jmp     short loc_1800450EE
0x1800450e9  mov     ebx, 8007000Eh
0x1800450ee  mov     rax, [rbp+47h+var_98]
0x1800450f2  mov     [rax], ebx
0x1800450f4  cmp     [rbp+47h+var_78], r14d
0x1800450f8  jl      short loc_18004510A
0x1800450fa  lea     rdx, [rbp+47h+var_88]
0x1800450fe  mov     ecx, 2
0x180045103  call    cs:__imp_EtwEventActivityIdControl
0x180045109  nop
0x18004510a  mov     rax, rdi
0x18004510d  mov     rcx, [rbp+47h+var_50]
0x180045111  xor     rcx, rsp; StackCookie
0x180045114  call    __security_check_cookie
0x180045119  add     rsp, 0A8h
0x180045120  pop     r15
  ... truncated ...
```
