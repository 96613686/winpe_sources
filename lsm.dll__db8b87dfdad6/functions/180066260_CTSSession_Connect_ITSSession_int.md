# CTSSession::Connect(ITSSession *,int)

- ea: `0x180066260`
- end: `0x180066907`
- name: `?Connect@CTSSession@@UEAAJPEAUITSSession@@H@Z`
- size: `1703`
- prototype: `__int64 __fastcall(CTSSession *this, struct ITSSession *, unsigned int)`
- caller_count: `0`
- callee_count: `21`
- tags: `file_ops, authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callees

- `0x1800074c0`
- `0x180008f04`
- `0x180008f64`
- `0x180009810`
- `0x1800189d4`
- `0x180018c5c`
- `0x180019838`
- `0x180019f28`
- `0x18001fd20`
- `0x18001fd70`
- `0x18002a3dc`
- `0x18004a85c`
- `0x18004b460`
- `0x18004b830`
- `0x180066040`
- `0x180066260`
- `0x180069ac0`
- `0x180069da0`
- `0x18006a4d0`
- `0x18006f948`
- `0x180097010`

## import_xrefs

- `ntdll!EtwEventActivityIdControl` at `0x180066595`
- `ntdll!EtwEventActivityIdControl` at `0x180066595`

## string_xrefs

- `0x1800664c9`: `CTSSession::Connect FAILED due to terminal incompatibility`
- `0x1800664fc`: `CTSSession::Connect FAILED due to protocol incompatibility`
- `0x18006660c`: `ptrTarget->GetSecurityDescriptor failed: 0x%x in %s`
- `0x180066675`: `this->SecurityDescriptor.GetSource failed: 0x%x in %s`
- `0x1800666cc`: `this->SecurityDescriptor.Initialize failed: 0x%x in %s`
- `0x18006670b`: `this->SecurityDescriptor.AddUserAce failed: 0x%x in %s`

## pseudocode

```c
__int64 __fastcall CTSSession::Connect(CTSSession *this, struct ITSSession *a2, unsigned int a3)
{
  int v5; // r13d
  void *v6; // r12
  unsigned __int16 *v7; // rsi
  unsigned int v8; // r14d
  int IsDescendant; // eax
  int v10; // edi
  const char *v11; // rdx
  const struct std::nothrow_t *v12; // rdx
  CTSSession *v13; // rcx
  __int64 v14; // rbx
  unsigned __int16 *v15; // rcx
  const unsigned __int16 *v16; // rdx
  unsigned __int16 *v17; // rax
  int v18; // r8d
  int v19; // r9d
  int v20; // eax
  struct IUserName *v21; // rdx
  int v22; // eax
  int v24; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v25; // [rsp+34h] [rbp-CCh] BYREF
  int v26; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v27; // [rsp+40h] [rbp-C0h] BYREF
  int v28; // [rsp+48h] [rbp-B8h]
  __int64 v29; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 *v30; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int16 *v31; // [rsp+60h] [rbp-A0h] BYREF
  int v32; // [rsp+68h] [rbp-98h] BYREF
  unsigned int v33; // [rsp+6Ch] [rbp-94h]
  __int64 v34; // [rsp+70h] [rbp-90h] BYREF
  void *v35; // [rsp+78h] [rbp-88h] BYREF
  __int64 v36; // [rsp+80h] [rbp-80h] BYREF
  UUID Uuid; // [rsp+90h] [rbp-70h] BYREF
  struct _GUID Buf1; // [rsp+A0h] [rbp-60h] BYREF
  UUID v39; // [rsp+B0h] [rbp-50h] BYREF
  struct _GUID v40; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v41[192]; // [rsp+D0h] [rbp-30h] BYREF

  v33 = a3;
  v5 = 0;
  v27 = 0;
  v34 = 0;
  v29 = 0;
  v36 = 0;
  v24 = 0;
  v26 = 0;
  v40 = 0;
  v39 = 0;
  v6 = 0;
  v7 = 0;
  v30 = 0;
  v31 = 0;
  v25 = 0;
  CTSSessionTrace::CTSSessionTrace((CTSSessionTrace *)v41, "CTSSession::Connect", this);
  v8 = *((_DWORD *)this + 436);
  v28 = v8;
  IsDescendant = (*(__int64 (__fastcall **)(struct ITSSession *, unsigned int *))(*(_QWORD *)a2 + 80LL))(a2, &v25);
  v10 = IsDescendant;
  if ( IsDescendant < 0 )
  {
    v11 = "Target session getId() failed: 0x%x in %s";
LABEL_3:
    _DbgPrintMessage(8, v11, (unsigned int)IsDescendant, "CTSSession::Connect");
    goto LABEL_67;
  }
  if ( (g_DebugTraceComponent & 4) != 0 )
    _DbgPrintMessage(2, "Connecting session %d to terminal of session %d", v8, v25);
  IsDescendant = CTSSession::IsDescendant(this, a2, &v24);
  v10 = IsDescendant;
  if ( IsDescendant < 0 )
  {
    v11 = "this->IsDescendant failed: 0x%x in %s";
    goto LABEL_3;
  }
  if ( v24 == 1 )
  {
    v10 = -2147017851;
    if ( (g_DebugTraceComponent & 4) != 0 )
      _DbgPrintMessage(2, "Target session %d is decendant of session %d", v25, v8);
    goto LABEL_67;
  }
  v24 = 0;
  IsDescendant = (*(__int64 (__fastcall **)(struct ITSSession *, CTSSession *, int *))(*(_QWORD *)a2 + 184LL))(
                   a2,
                   this,
                   &v24);
  v10 = IsDescendant;
  if ( IsDescendant < 0 )
  {
    v11 = "pTargetInterface->IsDescendant failed: 0x%x in %s";
    goto LABEL_3;
  }
  if ( v24 == 1 )
  {
    v10 = -2147017851;
    if ( (g_DebugTraceComponent & 4) != 0 )
      _DbgPrintMessage(2, "Target session %d is parent of session %d", v25, v8);
    goto LABEL_67;
  }
  CTSSession::NotifySuperfetch(v13);
  IsDescendant = (*(__int64 (__fastcall **)(_QWORD, GUID *, __int64 *))(**((_QWORD **)this + 199) + 24LL))(
                   *((_QWORD *)this + 199),
                   &IID_ITSSession,
                   &v29);
  v10 = IsDescendant;
  if ( IsDescendant < 0 )
  {
    v11 = "QI( ITSSession ) failed: 0x%x in %s";
    goto LABEL_3;
  }
  SmartPtr<ITSSession>::operator=(&v34, a2);
  IsDescendant = (*(__int64 (__fastcall **)(__int64, struct _GUID *))(*(_QWORD *)v29 + 168LL))(v29, &v40);
  v10 = IsDescendant;
  if ( IsDescendant < 0 )
  {
    v11 = "ptrSource->getSessionType failed: 0x%x in %s";
    goto LABEL_3;
  }
  IsDescendant = (*(__int64 (__fastcall **)(struct ITSSession *, UUID *))(*(_QWORD *)a2 + 168LL))(a2, &v39);
  v10 = IsDescendant;
  if ( IsDescendant < 0 )
  {
    v11 = "pTargetInterface->getSessionType failed: 0x%x in %s";
    goto LABEL_3;
  }
  Uuid = v39;
  Buf1 = v40;
  if ( !(unsigned int)CTerminalTypeHelper::IsSessionCompatible(&Buf1, &Uuid, &v26) )
  {
    if ( (g_DebugTraceComponent & 4) != 0 )
      _DbgPrintMessage(2, "CTSSession::Connect FAILED due to terminal incompatibility");
LABEL_25:
    v10 = -2147017827;
    goto LABEL_67;
  }
  if ( !(unsigned int)CTSSession::IsSessionProtocolCompatible(this, a2) )
  {
    if ( (g_DebugTraceComponent & 4) != 0 )
      _DbgPrintMessage(2, "CTSSession::Connect FAILED due to protocol incompatibility");
    goto LABEL_25;
  }
  v14 = v34;
  v10 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v34 + 56LL))(v34, 0, &v27);
  if ( v10 == -2147022646 )
  {
    v10 = -2147017872;
LABEL_32:
    _DbgPrintMessage(8, "Target->Disconnect failed: 0x%x in %s", (unsigned int)v10, "CTSSession::Connect");
    goto LABEL_67;
  }
  if ( v10 < 0 )
    goto LABEL_32;
  if ( v27 )
  {
    (*(void (__fastcall **)(__int64, char *))(*(_QWORD *)v27 + 216LL))(v27, (char *)this + 3208);
    EtwEventActivityIdControl(2, (char *)this + 3208);
    IsDescendant = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v29 + 56LL))(v29, 5);
    v10 = IsDescendant;
    if ( IsDescendant < 0 )
    {
      v11 = "Source->Disconnect failed: 0x%x in %s";
      goto LABEL_3;
    }
    (*(void (__fastcall **)(__int64, char *))(*(_QWORD *)v14 + 80LL))(v14, (char *)this + 2112);
    v35 = 0;
    v32 = 0;
    IsDescendant = (*(__int64 (__fastcall **)(__int64, unsigned __int16 **, void **, int *))(*(_QWORD *)v14 + 296LL))(
                     v14,
                     &v31,
                     &v35,
                     &v32);
    v10 = IsDescendant;
    if ( IsDescendant < 0 )
    {
      v11 = "ptrTarget->GetSecurityDescriptor failed: 0x%x in %s";
      goto LABEL_3;
    }
    v16 = (const unsigned __int16 *)*((_QWORD *)this + 740);
    if ( !v16 )
      goto LABEL_46;
    v15 = v31;
    if ( !v31 )
      goto LABEL_46;
    v17 = (unsigned __int16 *)*((_QWORD *)this + 740);
    v15 = (unsigned __int16 *)((char *)v31 - (char *)v16);
    do
    {
      v18 = *(unsigned __int16 *)((char *)v15 + (_QWORD)v17);
      v19 = *v17 - v18;
      if ( v19 )
        break;
      ++v17;
    }
    while ( v18 );
    if ( v19 )
    {
LABEL_46:
      v20 = CTSSecurityDescriptor::CopySource((CTSSecurityDescriptor *)v15, v16, &v30);
      v10 = v20;
      if ( v20 < 0 )
      {
        _DbgPrintMessage(8, "this->SecurityDescriptor.GetSource failed: 0x%x in %s", v20, "CTSSession::Connect");
        v7 = v30;
        goto LABEL_67;
      }
      v6 = CTSSessionSecurityDescriptor::DetachSD((CTSSession *)((char *)this + 5872));
      v10 = CTSSessionSecurityDescriptor::Initialize((CTSSession *)((char *)this + 5872), v31, v35);
      if ( v10 < 0 )
      {
        CTSSessionSecurityDescriptor::Attach((CTSSession *)((char *)this + 5872), v30, v6);
        v7 = 0;
        v6 = 0;
        _DbgPrintMessage(
          8,
          "this->SecurityDescriptor.Initialize failed: 0x%x in %s",
          (unsigned int)v10,
          "CTSSession::Connect");
        goto LABEL_67;
      }
      v21 = (struct IUserName *)*((_QWORD *)this + 741);
      if ( v21 )
      {
        v10 = CTSSessionSecurityDescriptor::AddUserAce((CTSSession *)((char *)this + 5872), v21);
        if ( v10 < 0 )
        {
          CTSSessionSecurityDescriptor::Attach((CTSSession *)((char *)this + 5872), v30, v6);
          v7 = 0;
          v6 = 0;
          _DbgPrintMessage(
            8,
            "this->SecurityDescriptor.AddUserAce failed: 0x%x in %s",
            (unsigned int)v10,
            "CTSSession::Connect");
          goto LABEL_67;
        }
      }
      v5 = 1;
      v7 = v30;
    }
    v22 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, _QWORD))(*(_QWORD *)v29 + 48LL))(v29, v27, v33, 0);
    v10 = v22;
    if ( v22 >= 0 )
    {
      SmartPtr<ITerminal>::operator=(&v27, 0);
      if ( v26 )
        *(UUID *)((char *)this + 5832) = v39;
    }
    else
    {
      if ( (g_DebugTraceComponent & 4) != 0 )
        _DbgPrintMessage(
          2,
          "CTSSession::Connect session %d to terminal of session %d failed with 0x%08x, trying to restore to previous terminal",
          v28,
          v25,
          v22);
      if ( v5 )
      {
        CTSSessionSecurityDescriptor::Attach((CTSSession *)((char *)this + 5872), v7, v6);
        v7 = 0;
        v6 = 0;
        v5 = 0;
      }
      (*(void (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v29 + 56LL))(v29, 0, 0);
      v28 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, _QWORD))(*(_QWORD *)v14 + 48LL))(v14, v27, 0, 0);
      v26 = 3;
      (*(void (__fastcall **)(__int64, int *))(*(_QWORD *)v14 + 88LL))(v14, &v26);
      if ( (unsigned int)IsConnectedState((unsigned int)v26) )
        SmartPtr<ITerminal>::operator=(&v27, 0);
      if ( v28 < 0 )
        _DbgPrintMessage(8, "Target->Reconnect recovery failed: 0x%x in %s", v28, "CTSSession::Connect");
    }
    if ( v5 )
    {
      CTSSessionSecurityDescriptor::Attach((CTSSession *)((char *)this + 5872), v7, v6);
      v7 = 0;
      v6 = 0;
    }
  }
  else
  {
    v10 = -2147022646;
    if ( (g_DebugTraceComponent & 4) != 0 )
      _DbgPrintMessage(2, "CTSSession::Connect because target session is in disconnected state");
  }
LABEL_67:
  if ( v31 )
  {
    operator delete(v31, v12);
    v31 = 0;
  }
  if ( v7 )
    operator delete(v7, v12);
  CUtils::CleanupSD(v6);
  *((_DWORD *)this + 528) = -1;
  if ( v27 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 48LL))(v27);
  CTSSessionTrace::~CTSSessionTrace((CTSSessionTrace *)v41);
  SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(&v36);
  SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(&v29);
  SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(&v34);
  SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(&v27);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180066260  mov     [rsp-8+arg_18], rbx
0x180066265  push    rbp
0x180066266  push    rsi
0x180066267  push    rdi
0x180066268  push    r12
0x18006626a  push    r13
0x18006626c  push    r14
0x18006626e  push    r15
0x180066270  lea     rbp, [rsp-0A0h]
0x180066278  sub     rsp, 1A0h
0x18006627f  mov     rax, cs:__security_cookie
0x180066286  xor     rax, rsp
0x180066289  mov     [rbp+0D0h+var_40], rax
0x180066290  mov     [rsp+1D0h+var_164], r8d
0x180066295  mov     rbx, rdx
0x180066298  mov     r15, rcx
0x18006629b  xor     r13d, r13d
0x18006629e  mov     [rsp+1D0h+var_190], r13
0x1800662a3  mov     [rsp+1D0h+var_160], r13
0x1800662a8  mov     [rsp+1D0h+var_180], r13
0x1800662ad  mov     [rbp+0D0h+var_150], r13
0x1800662b1  mov     [rsp+1D0h+var_1A0], r13d
0x1800662b6  mov     [rsp+1D0h+var_198], r13d
0x1800662bb  xorps   xmm0, xmm0
0x1800662be  movups  [rbp+0D0h+var_110], xmm0
0x1800662c2  xorps   xmm1, xmm1
0x1800662c5  movups  [rbp+0D0h+var_120], xmm1
0x1800662c9  mov     r12d, r13d
0x1800662cc  mov     esi, r13d
0x1800662cf  mov     [rsp+1D0h+var_178], r13
0x1800662d4  mov     [rsp+1D0h+var_170], r13
0x1800662d9  mov     [rsp+1D0h+var_19C], r13d
0x1800662de  mov     r8, rcx; struct ITSSession *
0x1800662e1  lea     rdx, aCtssessionConn_1; "CTSSession::Connect"
0x1800662e8  lea     rcx, [rbp+0D0h+var_100]; this
0x1800662ec  call    ??0CTSSessionTrace@@QEAA@PEBDPEAUITSSession@@@Z; CTSSessionTrace::CTSSessionTrace(char const *,ITSSession *)
0x1800662f1  nop
0x1800662f2  mov     r14d, [r15+6D0h]
0x1800662f9  mov     [rsp+1D0h+var_188], r14d
0x1800662fe  mov     rax, [rbx]
0x180066301  lea     rdx, [rsp+1D0h+var_19C]
0x180066306  mov     rcx, rbx
0x180066309  mov     rax, [rax+50h]
0x18006630d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066312  mov     edi, eax
0x180066314  test    eax, eax
0x180066316  jns     short loc_180066338
0x180066318  lea     rdx, aTargetSessionG; "Target session getId() failed: 0x%x in "...
0x18006631f  mov     r8d, eax
0x180066322  lea     r9, aCtssessionConn_1; "CTSSession::Connect"
0x180066329  mov     ecx, 8; int
0x18006632e  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180066333  jmp     loc_18006685C
0x180066338  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 4; ulong g_DebugTraceComponent
0x18006633f  jz      short loc_18006635A
0x180066341  mov     r9d, [rsp+1D0h+var_19C]
0x180066346  mov     r8d, r14d
0x180066349  lea     rdx, aConnectingSess; "Connecting session %d to terminal of se"...
0x180066350  mov     ecx, 2; int
0x180066355  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18006635a  lea     r8, [rsp+1D0h+var_1A0]; int *
0x18006635f  mov     rdx, rbx; struct ITSSession *
0x180066362  mov     rcx, r15; this
0x180066365  call    ?IsDescendant@CTSSession@@UEAAJPEAUITSSession@@PEAH@Z; CTSSession::IsDescendant(ITSSession *,int *)
0x18006636a  mov     edi, eax
0x18006636c  test    eax, eax
0x18006636e  jns     short loc_180066379
0x180066370  lea     rdx, aThisIsdescenda; "this->IsDescendant failed: 0x%x in %s"
0x180066377  jmp     short loc_18006631F
0x180066379  cmp     [rsp+1D0h+var_1A0], 1
0x18006637e  jnz     short loc_1800663B0
0x180066380  mov     edi, 80071B85h
0x180066385  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 4; ulong g_DebugTraceComponent
0x18006638c  jz      loc_18006685C
0x180066392  lea     rdx, aTargetSessionD; "Target session %d is decendant of sessi"...
0x180066399  mov     r8d, [rsp+1D0h+var_19C]
0x18006639e  mov     r9d, r14d
0x1800663a1  mov     ecx, 2; int
0x1800663a6  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800663ab  jmp     loc_18006685C
0x1800663b0  mov     [rsp+1D0h+var_1A0], r13d
0x1800663b5  mov     rax, [rbx]
0x1800663b8  lea     r8, [rsp+1D0h+var_1A0]
0x1800663bd  mov     rdx, r15
0x1800663c0  mov     rcx, rbx
0x1800663c3  mov     rax, [rax+0B8h]
0x1800663ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800663cf  mov     edi, eax
0x1800663d1  test    eax, eax
0x1800663d3  jns     short loc_1800663E1
0x1800663d5  lea     rdx, aPtargetinterfa; "pTargetInterface->IsDescendant failed: "...
0x1800663dc  jmp     loc_18006631F
0x1800663e1  cmp     [rsp+1D0h+var_1A0], 1
0x1800663e6  jnz     short loc_180066403
0x1800663e8  mov     edi, 80071B85h
0x1800663ed  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 4; ulong g_DebugTraceComponent
0x1800663f4  jz      loc_18006685C
0x1800663fa  lea     rdx, aTargetSessionD_1; "Target session %d is parent of session "...
0x180066401  jmp     short loc_180066399
0x180066403  call    ?NotifySuperfetch@CTSSession@@AEAAJXZ; CTSSession::NotifySuperfetch(void)
0x180066408  mov     rcx, [r15+638h]
0x18006640f  mov     rax, [rcx]
0x180066412  lea     r8, [rsp+1D0h+var_180]
0x180066417  lea     rdx, IID_ITSSession
0x18006641e  mov     rax, [rax+18h]
0x180066422  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066427  mov     edi, eax
0x180066429  test    eax, eax
0x18006642b  jns     short loc_180066439
0x18006642d  lea     rdx, aQiItssessionFa; "QI( ITSSession ) failed: 0x%x in %s"
0x180066434  jmp     loc_18006631F
0x180066439  mov     rdx, rbx
0x18006643c  lea     rcx, [rsp+1D0h+var_160]
0x180066441  call    ??4?$SmartPtr@UITSSession@@@@QEAAAEAV0@PEAUITSSession@@@Z; SmartPtr<ITSSession>::operator=(ITSSession *)
0x180066446  mov     rcx, [rsp+1D0h+var_180]
0x18006644b  mov     rax, [rcx]
0x18006644e  lea     rdx, [rbp+0D0h+var_110]
0x180066452  mov     rax, [rax+0A8h]
0x180066459  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006645e  mov     edi, eax
0x180066460  test    eax, eax
0x180066462  jns     short loc_180066470
0x180066464  lea     rdx, aPtrsourceGetse; "ptrSource->getSessionType failed: 0x%x "...
0x18006646b  jmp     loc_18006631F
0x180066470  mov     rax, [rbx]
0x180066473  lea     rdx, [rbp+0D0h+var_120]
0x180066477  mov     rcx, rbx
0x18006647a  mov     rax, [rax+0A8h]
0x180066481  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066486  mov     edi, eax
0x180066488  test    eax, eax
0x18006648a  jns     short loc_180066498
0x18006648c  lea     rdx, aPtargetinterfa_0; "pTargetInterface->getSessionType failed"...
0x180066493  jmp     loc_18006631F
0x180066498  movaps  xmm0, [rbp+0D0h+var_120]
0x18006649c  movdqa  xmmword ptr [rbp+0D0h+Uuid.Data1], xmm0
0x1800664a1  movaps  xmm1, [rbp+0D0h+var_110]
0x1800664a5  movdqa  xmmword ptr [rbp+0D0h+Buf1.Data1], xmm1
0x1800664aa  lea     r8, [rsp+1D0h+var_198]; int *
0x1800664af  lea     rdx, [rbp+0D0h+Uuid]; Uuid
0x1800664b3  lea     rcx, [rbp+0D0h+Buf1]; Buf1
0x1800664b7  call    ?IsSessionCompatible@CTerminalTypeHelper@@SAHU_GUID@@0PEAH@Z; CTerminalTypeHelper::IsSessionCompatible(_GUID,_GUID,int *)
0x1800664bc  test    eax, eax
0x1800664be  jnz     short loc_1800664E4
0x1800664c0  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 4; ulong g_DebugTraceComponent
0x1800664c7  jz      short loc_1800664DA
0x1800664c9  lea     rdx, aCtssessionConn_2; "CTSSession::Connect FAILED due to termi"...
0x1800664d0  mov     ecx, 2; int
0x1800664d5  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800664da  mov     edi, 80071B9Dh
0x1800664df  jmp     loc_18006685C
0x1800664e4  mov     rdx, rbx; struct ITSSession *
0x1800664e7  mov     rcx, r15; this
0x1800664ea  call    ?IsSessionProtocolCompatible@CTSSession@@UEAAHPEAUITSSession@@@Z; CTSSession::IsSessionProtocolCompatible(ITSSession *)
0x1800664ef  test    eax, eax
0x1800664f1  jnz     short loc_180066505
0x1800664f3  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 4; ulong g_DebugTraceComponent
0x1800664fa  jz      short loc_1800664DA
0x1800664fc  lea     rdx, aCtssessionConn_4; "CTSSession::Connect FAILED due to proto"...
0x180066503  jmp     short loc_1800664D0
0x180066505  mov     rbx, [rsp+1D0h+var_160]
0x18006650a  mov     rax, [rbx]
0x18006650d  lea     r8, [rsp+1D0h+var_190]
0x180066512  xor     edx, edx
0x180066514  mov     rcx, rbx
0x180066517  mov     rax, [rax+38h]
0x18006651b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066520  mov     edi, eax
0x180066522  mov     eax, 800708CAh
0x180066527  cmp     edi, eax
0x180066529  jnz     short loc_180066532
0x18006652b  mov     edi, 80071B70h
0x180066530  jmp     short loc_180066536
0x180066532  test    edi, edi
0x180066534  jns     short loc_180066545
0x180066536  mov     r8d, edi
0x180066539  lea     rdx, aTargetDisconne; "Target->Disconnect failed: 0x%x in %s"
0x180066540  jmp     loc_180066322
0x180066545  mov     rcx, [rsp+1D0h+var_190]
0x18006654a  test    rcx, rcx
0x18006654d  jnz     short loc_180066574
0x18006654f  mov     edi, eax
0x180066551  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 4; ulong g_DebugTraceComponent
0x180066558  jz      loc_18006685C
0x18006655e  lea     rdx, aCtssessionConn; "CTSSession::Connect because target sess"...
0x180066565  mov     ecx, 2; int
0x18006656a  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18006656f  jmp     loc_18006685C
0x180066574  lea     rdi, [r15+0C88h]
0x18006657b  mov     rax, [rcx]
0x18006657e  mov     rdx, rdi
0x180066581  mov     rax, [rax+0D8h]
0x180066588  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006658d  mov     rdx, rdi
0x180066590  mov     ecx, 2
0x180066595  call    cs:__imp_EtwEventActivityIdControl
0x18006659b  mov     rcx, [rsp+1D0h+var_180]
0x1800665a0  mov     rax, [rcx]
0x1800665a3  xor     r8d, r8d
0x1800665a6  lea     edx, [r8+5]
0x1800665aa  mov     rax, [rax+38h]
0x1800665ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800665b3  mov     edi, eax
0x1800665b5  test    eax, eax
0x1800665b7  jns     short loc_1800665C5
0x1800665b9  lea     rdx, aSourceDisconne; "Source->Disconnect failed: 0x%x in %s"
0x1800665c0  jmp     loc_18006631F
0x1800665c5  mov     rax, [rbx]
0x1800665c8  lea     rdx, [r15+840h]
0x1800665cf  mov     rcx, rbx
0x1800665d2  mov     rax, [rax+50h]
0x1800665d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800665db  mov     [rsp+1D0h+var_158], r13
0x1800665e0  mov     [rsp+1D0h+var_168], r13d
0x1800665e5  mov     rax, [rbx]
0x1800665e8  lea     r9, [rsp+1D0h+var_168]
0x1800665ed  lea     r8, [rsp+1D0h+var_158]
0x1800665f2  lea     rdx, [rsp+1D0h+var_170]
0x1800665f7  mov     rcx, rbx
0x1800665fa  mov     rax, [rax+128h]
0x180066601  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066606  mov     edi, eax
0x180066608  test    eax, eax
0x18006660a  jns     short loc_180066618
0x18006660c  lea     rdx, aPtrtargetGetse; "ptrTarget->GetSecurityDescriptor failed"...
0x180066613  jmp     loc_18006631F
0x180066618  lea     r14, [r15+16F0h]
0x18006661f  mov     rdx, [r14+30h]; unsigned __int16 *
0x180066623  test    rdx, rdx
0x180066626  jz      short loc_18006665B
0x180066628  mov     rcx, [rsp+1D0h+var_170]
0x18006662d  test    rcx, rcx
0x180066630  jz      short loc_18006665B
0x180066632  mov     rax, rdx
0x180066635  sub     rcx, rdx; this
0x180066638  movzx   r9d, word ptr [rax]
0x18006663c  movzx   r8d, word ptr [rax+rcx]
0x180066641  sub     r9d, r8d
0x180066644  jnz     short loc_18006664F
0x180066646  add     rax, 2
0x18006664a  test    r8d, r8d
0x18006664d  jnz     short loc_180066638
0x18006664f  test    r9d, r9d
0x180066652  jz      loc_180066722
0x180066658  xor     r13d, r13d
0x18006665b  lea     r8, [rsp+1D0h+var_178]; unsigned __int16 **
0x180066660  call    ?CopySource@CTSSecurityDescriptor@@IEAAJPEBGPEAPEAG@Z; CTSSecurityDescriptor::CopySource(ushort const *,ushort * *)
0x180066665  mov     edi, eax
0x180066667  test    eax, eax
0x180066669  jns     short loc_180066690
0x18006666b  lea     r9, aCtssessionConn_1; "CTSSession::Connect"
0x180066672  mov     r8d, eax
0x180066675  lea     rdx, aThisSecurityde_0; "this->SecurityDescriptor.GetSource fail"...
0x18006667c  mov     ecx, 8; int
0x180066681  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180066686  mov     rsi, [rsp+1D0h+var_178]
0x18006668b  jmp     loc_18006685C
0x180066690  mov     rcx, r14; this
0x180066693  call    ?DetachSD@CTSSessionSecurityDescriptor@@QEAAPEAXXZ; CTSSessionSecurityDescriptor::DetachSD(void)
0x180066698  mov     r12, rax
0x18006669b  mov     r8, [rsp+1D0h+var_158]; void *
0x1800666a0  mov     rdx, [rsp+1D0h+var_170]; unsigned __int16 *
0x1800666a5  mov     rcx, r14; this
0x1800666a8  call    ?Initialize@CTSSessionSecurityDescriptor@@QEAAJPEBGPEAX@Z; CTSSessionSecurityDescriptor::Initialize(ushort const *,void *)
0x1800666ad  mov     edi, eax
0x1800666af  test    eax, eax
0x1800666b1  jns     short loc_1800666D8
0x1800666b3  mov     r8, r12; void *
0x1800666b6  mov     rdx, [rsp+1D0h+var_178]; unsigned __int16 *
0x1800666bb  mov     rcx, r14; this
0x1800666be  call    ?Attach@CTSSessionSecurityDescriptor@@QEAAXPEAGPEAX@Z; CTSSessionSecurityDescriptor::Attach(ushort *,void *)
0x1800666c3  mov     rsi, r13
0x1800666c6  mov     r12, r13
0x1800666c9  mov     r8d, edi
0x1800666cc  lea     rdx, aThisSecurityde; "this->SecurityDescriptor.Initialize fai"...
0x1800666d3  jmp     loc_180066322
0x1800666d8  mov     rdx, [r15+1728h]; struct IUserName *
0x1800666df  test    rdx, rdx
0x1800666e2  jz      short loc_180066717
0x1800666e4  mov     rcx, r14; this
0x1800666e7  call    ?AddUserAce@CTSSessionSecurityDescriptor@@QEAAJPEAUIUserName@@@Z; CTSSessionSecurityDescriptor::AddUserAce(IUserName *)
0x1800666ec  mov     edi, eax
0x1800666ee  test    eax, eax
0x1800666f0  jns     short loc_180066717
0x1800666f2  mov     r8, r12; void *
0x1800666f5  mov     rdx, [rsp+1D0h+var_178]; unsigned __int16 *
0x1800666fa  mov     rcx, r14; this
0x1800666fd  call    ?Attach@CTSSessionSecurityDescriptor@@QEAAXPEAGPEAX@Z; CTSSessionSecurityDescriptor::Attach(ushort *,void *)
0x180066702  mov     rsi, r13
0x180066705  mov     r12, r13
0x180066708  mov     r8d, edi
0x18006670b  lea     rdx, aThisSecurityde_1; "this->SecurityDescriptor.AddUserAce fai"...
0x180066712  jmp     loc_180066322
0x180066717  mov     r13d, 1
0x18006671d  mov     rsi, [rsp+1D0h+var_178]
0x180066722  mov     rcx, [rsp+1D0h+var_180]
0x180066727  mov     rax, [rcx]
0x18006672a  xor     r9d, r9d
0x18006672d  mov     r8d, [rsp+1D0h+var_164]
0x180066732  mov     rdx, [rsp+1D0h+var_190]
  ... truncated ...
```
