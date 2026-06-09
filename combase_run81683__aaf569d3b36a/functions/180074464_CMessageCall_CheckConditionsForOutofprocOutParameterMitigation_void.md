# CMessageCall::CheckConditionsForOutofprocOutParameterMitigation(void)

- ea: `0x180074464`
- end: `0x180074876`
- name: `?CheckConditionsForOutofprocOutParameterMitigation@CMessageCall@@IEAAJXZ`
- size: `1042`
- prototype: `HRESULT __fastcall(CMessageCall *this)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180074364`

## callees

- `0x18003a8bc`
- `0x18003cf8c`
- `0x180074464`
- `0x18007487c`
- `0x180074a38`
- `0x1800865f4`
- `0x18014d5f4`
- `0x1801999b0`
- `0x18019c9fc`

## import_xrefs

- `RPCRT4!RpcRevertToSelfEx` at `0x1800745e8`
- `RPCRT4!RpcRevertToSelfEx` at `0x1800745e8`
- `RPCRT4!RpcImpersonateClient2` at `0x180074573`
- `RPCRT4!RpcImpersonateClient2` at `0x180074573`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x1800744cb`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x1800744cb`
- `ntdll!RtlQueryPackageIdentity` at `0x1802486de`
- `ntdll!RtlQueryPackageIdentity` at `0x1802486de`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800747d1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800747d1`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800747c8`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180074801`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800747c8`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180074801`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800747dc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800747dc`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800747f3`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800747f3`
- `ext-ms-win-core-winrt-remote-l1-1-0!IsPackagedAppExemptFromSuspend` at `0x1802486f1`
- `ext-ms-win-core-winrt-remote-l1-1-0!IsPackagedAppExemptFromSuspend` at `0x1802486f1`

## string_xrefs

- `0x180074835`: `onecore\com\combase\inc\impersonate.hxx`
- `0x18007468d`: `onecore\com\combase\dcomrem\call.cxx`
- `0x1800746c0`: `onecore\com\combase\dcomrem\call.cxx`
- `0x18007472b`: `onecore\com\combase\dcomrem\call.cxx`
- `0x180074776`: `onecore\com\combase\dcomrem\call.cxx`

## pseudocode

```c
__int64 __fastcall CMessageCall::CheckConditionsForOutofprocOutParameterMitigation(CMessageCall *this)
{
  char v1; // al
  CMessageCall *v2; // rsi
  char v3; // al
  HRESULT v4; // ebx
  void *hRpc; // rcx
  RPC_STATUS v6; // eax
  bool v7; // al
  bool v8; // di
  char v9; // al
  int LastError; // ebx
  char v11; // r14
  void *v12; // r15
  RPC_STATUS v13; // eax
  int Policy_Internal; // eax
  HANDLE v15; // r15
  HRESULT v16; // r14d
  bool v17; // dl
  BOOL v19; // r14d
  HANDLE CurrentThread; // rax
  bool CanProcessBeSuspendedByAnyLifecycleManager; // al
  unsigned int Pid; // [rsp+30h] [rbp-D0h] BYREF
  HANDLE Token; // [rsp+38h] [rbp-C8h] BYREF
  _PS_PKG_CLAIM PkgClaim; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int64 AttributesPresent; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v26[256]; // [rsp+50h] [rbp-B0h] BYREF
  void *retaddr; // [rsp+198h] [rbp+98h]

  v1 = *((_BYTE *)this + 320);
  v2 = this;
  if ( (v1 & 2) != 0 )
    return (v1 & 4) == 0 ? 0x80004021 : 0;
  v3 = *((_BYTE *)this + 240);
  if ( (v3 & 8) != 0 )
  {
    v7 = (v3 & 0x10) != 0;
  }
  else
  {
    v4 = 0;
    if ( (this->gap8[12] & 0x20) == 0 && this->_destObj._dwDestCtx != 2 && this->_destObj._dwDestCtx != 5 )
    {
      hRpc = this->_hRpc;
      Pid = 0;
      v6 = I_RpcBindingInqLocalClientPID(hRpc, &Pid);
      v4 = v6;
      if ( v6 )
      {
        if ( v6 > 0 )
          v4 = (unsigned __int16)v6 | 0x80070000;
        if ( v4 < 0 )
          goto LABEL_35;
      }
    }
    v7 = 0;
    LOBYTE(this) = *((_BYTE *)v2 + 240) & 0xE7 | 8;
    *((_BYTE *)v2 + 240) = (_BYTE)this;
    if ( v4 < 0 )
    {
LABEL_35:
      wil::details::in1diag3::Return_Hr(retaddr, 0xF55u, "onecore\\com\\combase\\dcomrem\\call.cxx", v4);
      return (unsigned int)v4;
    }
  }
  v8 = 0;
  if ( v7 )
  {
LABEL_33:
    v1 = (4 * v8) | *((_BYTE *)v2 + 320) & 0xFB | 2;
    *((_BYTE *)v2 + 320) = v1;
    return (v1 & 4) == 0 ? 0x80004021 : 0;
  }
  if ( s_outofprocOutParameterMitigationStatus )
  {
    if ( s_outofprocOutParameterMitigationStatus == OutofprocOutParameterMitigationEnabledAlways )
      goto LABEL_46;
  }
  else
  {
    CanProcessBeSuspendedByAnyLifecycleManager = ProcessToken::CanProcessBeSuspendedByAnyLifecycleManager((ProcessToken *)this);
    this = (CMessageCall *)CanProcessBeSuspendedByAnyLifecycleManager;
    s_outofprocOutParameterMitigationStatus = !CanProcessBeSuspendedByAnyLifecycleManager + 1;
    if ( CanProcessBeSuspendedByAnyLifecycleManager )
      goto LABEL_46;
  }
  if ( (*((_BYTE *)v2 + 320) & 8) != 0 || v2->_destObj._dwDestCtx == 5 )
  {
LABEL_46:
    v8 = 1;
    if ( gfEnableTracing && (WPP_GLOBAL_Control->ReserveSpace[28] & 0x10) != 0 )
      ComTraceMessage(
        -1,
        "onecore\\com\\combase\\dcomrem\\call.cxx",
        "CMessageCall::CheckConditionsForOutofprocOutParameterMitigation",
        3935,
        CHATTY,
        L"Enabling outofproc out parameter mitigation");
    goto LABEL_33;
  }
  v9 = *((_BYTE *)v2 + 240);
  if ( (v9 & 0x20) != 0 )
  {
    v8 = (v9 & 0x40) != 0;
    LastError = 0;
    goto LABEL_27;
  }
  LastError = 0;
  if ( (v2->gap8[12] & 0x20) != 0 )
  {
    v11 = ProcessToken::CanProcessBeSuspendedByAnyLifecycleManager((ProcessToken *)this);
    goto LABEL_26;
  }
  v11 = 0;
  if ( v2->_destObj._dwDestCtx == 2 )
  {
LABEL_26:
    v8 = v11;
    *((_BYTE *)v2 + 240) = (v11 << 6) | *((_BYTE *)v2 + 240) & 0xBF | 0x20;
    goto LABEL_27;
  }
  v12 = v2->_hRpc;
  Token = 0;
  if ( NtCurrentTeb()->IsImpersonating )
  {
    CurrentThread = GetCurrentThread();
    if ( OpenThreadToken(CurrentThread, 4u, 1, &Token) )
    {
      SetThreadToken(0, 0);
    }
    else
    {
      Token = 0;
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    0x3Du,
                    "onecore\\com\\combase\\inc\\impersonate.hxx");
      if ( LastError < 0 )
        goto LABEL_25;
    }
  }
  v13 = RpcImpersonateClient2(v12);
  LastError = v13;
  if ( v13 )
  {
    if ( v13 > 0 )
      LastError = (unsigned __int16)v13 | 0x80070000;
    goto LABEL_23;
  }
  Pid = 0;
  AttributesPresent = 0;
  PkgClaim = 0;
  Policy_Internal = AppModelPolicy_GetPolicy_Internal(
                      (void *)0xFFFFFFFFFFFFFFFBLL,
                      AppModelPolicy_Type_LifecycleManager,
                      (AppModelPolicy_PolicyValue *)&Pid,
                      &PkgClaim,
                      &AttributesPresent);
  LastError = Policy_Internal | 0x10000000;
  if ( Policy_Internal >= 0 )
  {
    if ( Pid == 65537 )
    {
      v19 = 1;
      if ( IsGetEndPointMapperCrossVmPipeNamespacePresent() )
      {
        PkgClaim = (_PS_PKG_CLAIM)256LL;
        if ( (int)RtlQueryPackageIdentity(-5, v26, &PkgClaim) >= 0 )
          v19 = IsPackagedAppExemptFromSuspend(v26) == 0;
      }
      if ( v19 )
        goto LABEL_21;
    }
    else if ( Pid == 65538 )
    {
LABEL_21:
      v11 = 1;
      goto LABEL_22;
    }
    v11 = 0;
  }
LABEL_22:
  RpcRevertToSelfEx(v12);
LABEL_23:
  v15 = Token;
  if ( Token )
  {
    SetThreadToken(0, Token);
    CloseHandle(v15);
  }
LABEL_25:
  if ( LastError >= 0 )
    goto LABEL_26;
LABEL_27:
  v16 = 0;
  if ( LastError != -805306202 )
    v16 = LastError;
  v17 = 0;
  if ( LastError != -805306202 )
    v17 = v8;
  v8 = v17;
  if ( v16 >= 0 )
  {
    if ( v17 && gfEnableTracing && (WPP_GLOBAL_Control->ReserveSpace[28] & 0x10) != 0 )
      ComTraceMessageT<>(
        "onecore\\com\\combase\\dcomrem\\call.cxx",
        "CMessageCall::CheckConditionsForOutofprocOutParameterMitigation",
        3961,
        CHATTY,
        L"Enabling outofproc out parameter mitigation because caller is suspendable");
    goto LABEL_33;
  }
  wil::details::in1diag3::Return_Hr(retaddr, 0xF75u, "onecore\\com\\combase\\dcomrem\\call.cxx", v16);
  return (unsigned int)v16;
}

```

## disassembly

```asm
0x180074464  push    rbp
0x180074466  push    rbx
0x180074467  push    rsi
0x180074468  push    rdi
0x180074469  push    r14
0x18007446b  push    r15
0x18007446d  lea     rbp, [rsp-68h]
0x180074472  sub     rsp, 168h
0x180074479  mov     rax, cs:__security_cookie
0x180074480  xor     rax, rsp
0x180074483  mov     [rbp+90h+var_40], rax
0x180074487  mov     al, [this+140h]
0x18007448d  mov     rsi, this
0x180074490  test    al, 2
0x180074492  jnz     loc_18007465D
0x180074498  mov     al, [this+0F0h]
0x18007449e  mov     r14b, 8
0x1800744a1  test    r14b, al
0x1800744a4  jnz     loc_18007486C
0x1800744aa  xor     ebx, ebx
0x1800744ac  test    byte ptr [this+14h], 20h
0x1800744b0  jnz     short loc_1800744DB
0x1800744b2  cmp     dword ptr [this+40h], 2
0x1800744b6  jz      short loc_1800744DB
0x1800744b8  cmp     dword ptr [this+40h], 5
0x1800744bc  jz      short loc_1800744DB
0x1800744be  mov     this, [this+68h]; Binding
0x1800744c2  lea     rdx, [rsp+190h+Pid]; Pid
0x1800744c7  mov     [rsp+190h+Pid], ebx
0x1800744cb  call    cs:__imp_I_RpcBindingInqLocalClientPID
0x1800744d1  mov     ebx, eax
0x1800744d3  test    eax, eax
0x1800744d5  jnz     loc_1800746D9
0x1800744db  mov     cl, [rsi+0F0h]
0x1800744e1  xor     al, al
0x1800744e3  and     cl, 0EFh
0x1800744e6  or      cl, r14b; this
0x1800744e9  mov     [rsi+0F0h], cl
0x1800744ef  test    ebx, ebx
0x1800744f1  js      loc_180074686
0x1800744f7  xor     dil, dil
0x1800744fa  test    al, al
0x1800744fc  jnz     loc_180074646
0x180074502  mov     eax, cs:s_outofprocOutParameterMitigationStatus
0x180074508  test    eax, eax
0x18007450a  jz      loc_18007480C
0x180074510  cmp     eax, 1
0x180074513  jz      loc_18007473C
0x180074519  test    [rsi+140h], r14b
0x180074520  jnz     loc_18007473C
0x180074526  cmp     dword ptr [rsi+40h], 5
0x18007452a  jz      loc_18007473C
0x180074530  mov     al, [rsi+0F0h]
0x180074536  test    al, 20h
0x180074538  jnz     loc_18007485A
0x18007453e  xor     ebx, ebx
0x180074540  test    byte ptr [rsi+14h], 20h
0x180074544  jnz     loc_1800747B6
0x18007454a  xor     r14b, r14b
0x18007454d  cmp     dword ptr [rsi+40h], 2
0x180074551  jz      loc_180074600
0x180074557  mov     r15, [rsi+68h]
0x18007455b  mov     [rsp+190h+Token], rbx
0x180074560  mov     eax, gs:179Ch
0x180074568  test    eax, eax
0x18007456a  jnz     loc_1800747DC
0x180074570  mov     this, r15; BindingHandle
0x180074573  call    cs:__imp_RpcImpersonateClient2
0x180074579  mov     ebx, eax
0x18007457b  test    eax, eax
0x18007457d  jnz     loc_1800746A5
0x180074583  mov     [rsp+190h+Pid], eax
0x180074587  lea     r9, [rsp+190h+PkgClaim]; PkgClaim
0x18007458c  lea     rax, [rsp+190h+var_148]
0x180074591  mov     [rsp+190h+var_148], 0
0x18007459a  lea     r8, [rsp+190h+Pid]; policyValue
0x18007459f  mov     [rsp+190h+AttributesPresent], rax; AttributesPresent
0x1800745a4  lea     edx, [rbx+1]; policyType
0x1800745a7  mov     qword ptr [rsp+190h+PkgClaim.Flags], 0
0x1800745b0  mov     this, 0FFFFFFFFFFFFFFFBh; token
0x1800745b7  call    ?AppModelPolicy_GetPolicy_Internal@@YAJPEAXW4AppModelPolicy_Type@@PEAW4AppModelPolicy_PolicyValue@@PEAU_PS_PKG_CLAIM@@PEA_K@Z; AppModelPolicy_GetPolicy_Internal(void *,AppModelPolicy_Type,AppModelPolicy_PolicyValue *,_PS_PKG_CLAIM *,unsigned __int64 *)
0x1800745bc  mov     ebx, eax
0x1800745be  or      ebx, 10000000h
0x1800745c4  jl      short loc_1800745E5
0x1800745c6  cmp     [rsp+190h+Pid], 10001h
0x1800745ce  jz      loc_180074792
0x1800745d4  cmp     [rsp+190h+Pid], 10002h
0x1800745dc  jnz     loc_1800747AE
0x1800745e2  mov     r14b, 1
0x1800745e5  mov     this, r15; BindingHandle
0x1800745e8  call    cs:__imp_RpcRevertToSelfEx
0x1800745ee  mov     r15, [rsp+190h+Token]
0x1800745f3  test    r15, r15
0x1800745f6  jnz     loc_1800747C3
0x1800745fc  test    ebx, ebx
0x1800745fe  js      short loc_18007461D
0x180074600  mov     cl, [rsi+0F0h]
0x180074606  mov     al, r14b
0x180074609  and     cl, 0BFh
0x18007460c  shl     al, 6
0x18007460f  or      cl, al
0x180074611  mov     dil, r14b
0x180074614  or      cl, 20h
0x180074617  mov     [rsi+0F0h], cl
0x18007461d  xor     r14d, r14d
0x180074620  movzx   ecx, dil
0x180074624  mov     eax, 0D00000A6h
0x180074629  cmp     ebx, eax
0x18007462b  cmovnz  r14d, ebx
0x18007462f  xor     edx, edx
0x180074631  cmp     ebx, eax
0x180074633  cmovnz  edx, ecx
0x180074636  mov     dil, dl
0x180074639  test    r14d, r14d
0x18007463c  js      short loc_1800746B9
0x18007463e  test    dl, dl
0x180074640  jnz     loc_1800746EE
0x180074646  mov     al, [rsi+140h]
0x18007464c  and     al, 0FBh
0x18007464e  shl     dil, 2
0x180074652  or      al, dil
0x180074655  or      al, 2
0x180074657  mov     [rsi+140h], al
0x18007465d  and     al, 4
0x18007465f  neg     al
0x180074661  sbb     eax, eax
0x180074663  not     eax
0x180074665  and     eax, 80004021h
0x18007466a  mov     this, [rbp+90h+var_40]
0x18007466e  xor     this, rsp; StackCookie
0x180074671  call    __security_check_cookie
0x180074676  add     rsp, 168h
0x18007467d  pop     r15
0x18007467f  pop     r14
0x180074681  pop     rdi
0x180074682  pop     rsi
0x180074683  pop     rbx
0x180074684  pop     rbp
0x180074685  retn
0x180074686  mov     this, [rbp+98h]; callerReturnAddress
0x18007468d  lea     r8, pszFile; "onecore\\com\\combase\\dcomrem\\call.cx"...
0x180074694  mov     r9d, ebx; hr
0x180074697  mov     edx, 0F55h; lineNumber
0x18007469c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800746a1  mov     eax, ebx
0x1800746a3  jmp     short loc_18007466A
0x1800746a5  jle     loc_1800745EE
0x1800746ab  movzx   ebx, ax
0x1800746ae  or      ebx, 80070000h
0x1800746b4  jmp     loc_1800745EE
0x1800746b9  mov     this, [rbp+98h]; callerReturnAddress
0x1800746c0  lea     r8, pszFile; "onecore\\com\\combase\\dcomrem\\call.cx"...
0x1800746c7  mov     r9d, r14d; hr
0x1800746ca  mov     edx, 0F75h; lineNumber
0x1800746cf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800746d4  mov     eax, r14d
0x1800746d7  jmp     short loc_18007466A
0x1800746d9  jle     short loc_1800746E4
0x1800746db  movzx   ebx, ax
0x1800746de  or      ebx, 80070000h
0x1800746e4  test    ebx, ebx
0x1800746e6  jns     loc_1800744DB
0x1800746ec  jmp     short loc_180074686
0x1800746ee  cmp     cs:?gfEnableTracing@@3HA, 0; int gfEnableTracing
0x1800746f5  jz      loc_180074646
0x1800746fb  mov     rax, cs:WPP_GLOBAL_Control
0x180074702  test    byte ptr [rax+1Ch], 10h
0x180074706  jz      loc_180074646
0x18007470c  lea     rax, aEnablingOutofp; "Enabling outofproc out parameter mitiga"...
0x180074713  mov     r9d, 4; level
0x180074719  mov     r8d, 0F79h; line
0x18007471f  mov     [rsp+190h+AttributesPresent], rax; format
0x180074724  lea     rdx, aCmessagecallCh; "CMessageCall::CheckConditionsForOutofpr"...
0x18007472b  lea     this, pszFile; "onecore\\com\\combase\\dcomrem\\call.cx"...
0x180074732  call    ??$ComTraceMessageT@$$V@@YAXPEBD0HW4TraceLevel@@PEBG@Z; ComTraceMessageT<>(char const *,char const *,int,TraceLevel,ushort const *)
0x180074737  jmp     loc_180074646
0x18007473c  cmp     cs:?gfEnableTracing@@3HA, 0; int gfEnableTracing
0x180074743  mov     dil, 1
0x180074746  jz      loc_180074646
0x18007474c  mov     rax, cs:WPP_GLOBAL_Control
0x180074753  test    byte ptr [rax+1Ch], 10h
0x180074757  jz      loc_180074646
0x18007475d  lea     rax, aEnablingOutofp_0; "Enabling outofproc out parameter mitiga"...
0x180074764  mov     r9d, 0F5Fh; line
0x18007476a  mov     [rsp+190h+format], rax; format
0x18007476f  lea     r8, aCmessagecallCh; "CMessageCall::CheckConditionsForOutofpr"...
0x180074776  lea     rdx, pszFile; "onecore\\com\\combase\\dcomrem\\call.cx"...
0x18007477d  mov     dword ptr [rsp+190h+AttributesPresent], 4; level
0x180074785  or      ecx, 0FFFFFFFFh; hr
0x180074788  call    ?ComTraceMessage@@YAXJPEBD0HW4TraceLevel@@PEBGZZ; ComTraceMessage(long,char const *,char const *,int,TraceLevel,ushort const *,...)
0x18007478d  jmp     loc_180074646
0x180074792  mov     r14d, 1
0x180074798  call    IsGetEndPointMapperCrossVmPipeNamespacePresent
0x18007479d  test    al, al
0x18007479f  jnz     loc_1802486B2
0x1800747a5  test    r14d, r14d
0x1800747a8  jnz     loc_1800745E2
0x1800747ae  xor     r14b, r14b
0x1800747b1  jmp     loc_1800745E5
0x1800747b6  call    ?CanProcessBeSuspendedByAnyLifecycleManager@ProcessToken@@QEAA_NXZ; ProcessToken::CanProcessBeSuspendedByAnyLifecycleManager(void)
0x1800747bb  mov     r14b, al
0x1800747be  jmp     loc_180074600
0x1800747c3  mov     rdx, r15; Token
0x1800747c6  xor     ecx, ecx; Thread
0x1800747c8  call    cs:__imp_SetThreadToken
0x1800747ce  mov     this, r15; hObject
0x1800747d1  call    cs:__imp_CloseHandle
0x1800747d7  jmp     loc_1800745FC
0x1800747dc  call    cs:__imp_GetCurrentThread
0x1800747e2  mov     edx, 4; DesiredAccess
0x1800747e7  lea     r9, [rsp+190h+Token]; TokenHandle
0x1800747ec  mov     this, rax; ThreadHandle
0x1800747ef  lea     r8d, [rdx-3]; OpenAsSelf
0x1800747f3  call    cs:__imp_OpenThreadToken
0x1800747f9  test    eax, eax
0x1800747fb  jz      short loc_18007482E
0x1800747fd  xor     edx, edx; Token
0x1800747ff  xor     ecx, ecx; Thread
0x180074801  call    cs:__imp_SetThreadToken
0x180074807  jmp     loc_180074570
0x18007480c  call    ?CanProcessBeSuspendedByAnyLifecycleManager@ProcessToken@@QEAA_NXZ; ProcessToken::CanProcessBeSuspendedByAnyLifecycleManager(void)
0x180074811  movzx   ecx, al
0x180074814  mov     eax, ecx
0x180074816  xor     eax, 1
0x180074819  inc     eax
0x18007481b  mov     cs:s_outofprocOutParameterMitigationStatus, eax
0x180074821  test    cl, cl
0x180074823  jz      loc_180074519
0x180074829  jmp     loc_18007473C
0x18007482e  mov     this, [rbp+98h]; callerReturnAddress
0x180074835  lea     r8, aOnecoreComComb_182; "onecore\\com\\combase\\inc\\impersonate"...
0x18007483c  mov     edx, 3Dh ; '='; lineNumber
0x180074841  mov     [rsp+190h+Token], rbx
0x180074846  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18007484b  mov     ebx, eax
0x18007484d  test    eax, eax
0x18007484f  jns     loc_180074570
0x180074855  jmp     loc_1800745FC
0x18007485a  mov     dil, al
0x18007485d  shr     dil, 6
0x180074861  and     dil, 1
0x180074865  xor     ebx, ebx
0x180074867  jmp     loc_18007461D
0x18007486c  shr     al, 4
0x18007486f  and     al, 1
0x180074871  jmp     loc_1800744F7
0x1802486b2  xor     r9d, r9d
0x1802486b5  mov     [rsp+190h+format], 0
0x1802486be  lea     r8, [rsp+190h+PkgClaim]
0x1802486c3  mov     qword ptr [rsp+190h+PkgClaim.Flags], 100h
0x1802486cc  lea     rdx, [rsp+190h+var_140]
0x1802486d1  mov     [rsp+190h+AttributesPresent], 0
0x1802486da  lea     rcx, [r9-5]
0x1802486de  call    cs:__imp_RtlQueryPackageIdentity
0x1802486e4  test    eax, eax
0x1802486e6  js      loc_1800747A5
0x1802486ec  lea     rcx, [rsp+190h+var_140]
0x1802486f1  call    cs:__imp_IsPackagedAppExemptFromSuspend
0x1802486f7  test    eax, eax
0x1802486f9  jz      loc_1800747A5
0x1802486ff  xor     r14d, r14d
0x180248702  jmp     loc_1800747A5
```
