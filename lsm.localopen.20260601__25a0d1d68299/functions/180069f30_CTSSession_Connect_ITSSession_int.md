# CTSSession::Connect(ITSSession *,int)

- ea: `0x180069f30`
- end: `0x18006a5de`
- name: `?Connect@CTSSession@@UEAAJPEAUITSSession@@H@Z`
- size: `1710`
- prototype: `__int64 __fastcall(CTSSession *__hidden this, struct ITSSession *, int)`
- caller_count: `0`
- callee_count: `21`
- tags: `file_ops, authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callees

- `0x1800077a0`
- `0x1800095f8`
- `0x1800098b4`
- `0x18000a5e0`
- `0x18000acec`
- `0x18000c684`
- `0x180011e6c`
- `0x180012194`
- `0x180022030`
- `0x180022200`
- `0x18002c434`
- `0x18004dbfc`
- `0x18004e850`
- `0x18004ec20`
- `0x180069d00`
- `0x180069f30`
- `0x18006d8e0`
- `0x18006dbd0`
- `0x18006e300`
- `0x18007395c`
- `0x18009c010`

## import_xrefs

- `ntdll!EtwEventActivityIdControl` at `0x18006a265`
- `ntdll!EtwEventActivityIdControl` at `0x18006a265`

## string_xrefs

- `0x18006a199`: `CTSSession::Connect FAILED due to terminal incompatibility`
- `0x18006a1cc`: `CTSSession::Connect FAILED due to protocol incompatibility`
- `0x18006a2e2`: `ptrTarget->GetSecurityDescriptor failed: 0x%x in %s`
- `0x18006a34b`: `this->SecurityDescriptor.GetSource failed: 0x%x in %s`
- `0x18006a3a2`: `this->SecurityDescriptor.Initialize failed: 0x%x in %s`
- `0x18006a3e1`: `this->SecurityDescriptor.AddUserAce failed: 0x%x in %s`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
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
0x180069f30  mov     [rsp-8+arg_18], rbx
0x180069f35  push    rbp
0x180069f36  push    rsi
0x180069f37  push    rdi
0x180069f38  push    r12
0x180069f3a  push    r13
0x180069f3c  push    r14
0x180069f3e  push    r15
0x180069f40  lea     rbp, [rsp-0A0h]
0x180069f48  sub     rsp, 1A0h
0x180069f4f  mov     rax, cs:__security_cookie
0x180069f56  xor     rax, rsp
0x180069f59  mov     [rbp+0D0h+var_40], rax
0x180069f60  mov     [rsp+1D0h+var_164], r8d
0x180069f65  mov     rbx, rdx
0x180069f68  mov     r15, rcx
0x180069f6b  xor     r13d, r13d
0x180069f6e  mov     [rsp+1D0h+var_190], r13
0x180069f73  mov     [rsp+1D0h+var_160], r13
0x180069f78  mov     [rsp+1D0h+var_180], r13
0x180069f7d  mov     [rbp+0D0h+var_150], r13
0x180069f81  mov     [rsp+1D0h+var_1A0], r13d
0x180069f86  mov     [rsp+1D0h+var_198], r13d
0x180069f8b  xorps   xmm0, xmm0
0x180069f8e  movups  [rbp+0D0h+var_110], xmm0
0x180069f92  xorps   xmm1, xmm1
0x180069f95  movups  [rbp+0D0h+var_120], xmm1
0x180069f99  mov     r12d, r13d
0x180069f9c  mov     esi, r13d
0x180069f9f  mov     [rsp+1D0h+var_178], r13
0x180069fa4  mov     [rsp+1D0h+var_170], r13
0x180069fa9  mov     [rsp+1D0h+var_19C], r13d
0x180069fae  mov     r8, rcx; struct ITSSession *
0x180069fb1  lea     rdx, aCtssessionConn_1; "CTSSession::Connect"
0x180069fb8  lea     rcx, [rbp+0D0h+var_100]; this
0x180069fbc  call    ??0CTSSessionTrace@@QEAA@PEBDPEAUITSSession@@@Z; CTSSessionTrace::CTSSessionTrace(char const *,ITSSession *)
0x180069fc1  nop
0x180069fc2  mov     r14d, [r15+6D0h]
0x180069fc9  mov     [rsp+1D0h+var_188], r14d
0x180069fce  mov     rax, [rbx]
0x180069fd1  lea     rdx, [rsp+1D0h+var_19C]
0x180069fd6  mov     rcx, rbx
0x180069fd9  mov     rax, [rax+50h]
0x180069fdd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069fe2  mov     edi, eax
0x180069fe4  test    eax, eax
0x180069fe6  jns     short loc_18006A008
0x180069fe8  lea     rdx, aTargetSessionG; "Target session getId() failed: 0x%x in "...
0x180069fef  mov     r8d, eax
0x180069ff2  lea     r9, aCtssessionConn_1; "CTSSession::Connect"
0x180069ff9  mov     ecx, 8; int
0x180069ffe  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18006a003  jmp     loc_18006A532
0x18006a008  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 4; ulong g_DebugTraceComponent
0x18006a00f  jz      short loc_18006A02A
0x18006a011  mov     r9d, [rsp+1D0h+var_19C]
0x18006a016  mov     r8d, r14d
0x18006a019  lea     rdx, aConnectingSess; "Connecting session %d to terminal of se"...
0x18006a020  mov     ecx, 2; int
0x18006a025  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18006a02a  lea     r8, [rsp+1D0h+var_1A0]; int *
0x18006a02f  mov     rdx, rbx; struct ITSSession *
0x18006a032  mov     rcx, r15; this
0x18006a035  call    ?IsDescendant@CTSSession@@UEAAJPEAUITSSession@@PEAH@Z; CTSSession::IsDescendant(ITSSession *,int *)
0x18006a03a  mov     edi, eax
0x18006a03c  test    eax, eax
0x18006a03e  jns     short loc_18006A049
0x18006a040  lea     rdx, aThisIsdescenda; "this->IsDescendant failed: 0x%x in %s"
0x18006a047  jmp     short loc_180069FEF
0x18006a049  cmp     [rsp+1D0h+var_1A0], 1
0x18006a04e  jnz     short loc_18006A080
0x18006a050  mov     edi, 80071B85h
0x18006a055  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 4; ulong g_DebugTraceComponent
0x18006a05c  jz      loc_18006A532
0x18006a062  lea     rdx, aTargetSessionD; "Target session %d is decendant of sessi"...
0x18006a069  mov     r8d, [rsp+1D0h+var_19C]
0x18006a06e  mov     r9d, r14d
0x18006a071  mov     ecx, 2; int
0x18006a076  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18006a07b  jmp     loc_18006A532
0x18006a080  mov     [rsp+1D0h+var_1A0], r13d
0x18006a085  mov     rax, [rbx]
0x18006a088  lea     r8, [rsp+1D0h+var_1A0]
0x18006a08d  mov     rdx, r15
0x18006a090  mov     rcx, rbx
0x18006a093  mov     rax, [rax+0B8h]
0x18006a09a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a09f  mov     edi, eax
0x18006a0a1  test    eax, eax
0x18006a0a3  jns     short loc_18006A0B1
0x18006a0a5  lea     rdx, aPtargetinterfa; "pTargetInterface->IsDescendant failed: "...
0x18006a0ac  jmp     loc_180069FEF
0x18006a0b1  cmp     [rsp+1D0h+var_1A0], 1
0x18006a0b6  jnz     short loc_18006A0D3
0x18006a0b8  mov     edi, 80071B85h
0x18006a0bd  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 4; ulong g_DebugTraceComponent
0x18006a0c4  jz      loc_18006A532
0x18006a0ca  lea     rdx, aTargetSessionD_1; "Target session %d is parent of session "...
0x18006a0d1  jmp     short loc_18006A069
0x18006a0d3  call    ?NotifySuperfetch@CTSSession@@AEAAJXZ; CTSSession::NotifySuperfetch(void)
0x18006a0d8  mov     rcx, [r15+638h]
0x18006a0df  mov     rax, [rcx]
0x18006a0e2  lea     r8, [rsp+1D0h+var_180]
0x18006a0e7  lea     rdx, IID_ITSSession
0x18006a0ee  mov     rax, [rax+18h]
0x18006a0f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a0f7  mov     edi, eax
0x18006a0f9  test    eax, eax
0x18006a0fb  jns     short loc_18006A109
0x18006a0fd  lea     rdx, aQiItssessionFa; "QI( ITSSession ) failed: 0x%x in %s"
0x18006a104  jmp     loc_180069FEF
0x18006a109  mov     rdx, rbx
0x18006a10c  lea     rcx, [rsp+1D0h+var_160]
0x18006a111  call    ??4?$SmartPtr@UITSSession@@@@QEAAAEAV0@PEAUITSSession@@@Z; SmartPtr<ITSSession>::operator=(ITSSession *)
0x18006a116  mov     rcx, [rsp+1D0h+var_180]
0x18006a11b  mov     rax, [rcx]
0x18006a11e  lea     rdx, [rbp+0D0h+var_110]
0x18006a122  mov     rax, [rax+0A8h]
0x18006a129  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a12e  mov     edi, eax
0x18006a130  test    eax, eax
0x18006a132  jns     short loc_18006A140
0x18006a134  lea     rdx, aPtrsourceGetse; "ptrSource->getSessionType failed: 0x%x "...
0x18006a13b  jmp     loc_180069FEF
0x18006a140  mov     rax, [rbx]
0x18006a143  lea     rdx, [rbp+0D0h+var_120]
0x18006a147  mov     rcx, rbx
0x18006a14a  mov     rax, [rax+0A8h]
0x18006a151  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a156  mov     edi, eax
0x18006a158  test    eax, eax
0x18006a15a  jns     short loc_18006A168
0x18006a15c  lea     rdx, aPtargetinterfa_0; "pTargetInterface->getSessionType failed"...
0x18006a163  jmp     loc_180069FEF
0x18006a168  movaps  xmm0, [rbp+0D0h+var_120]
0x18006a16c  movdqa  xmmword ptr [rbp+0D0h+Uuid.Data1], xmm0
0x18006a171  movaps  xmm1, [rbp+0D0h+var_110]
0x18006a175  movdqa  xmmword ptr [rbp+0D0h+Buf1.Data1], xmm1
0x18006a17a  lea     r8, [rsp+1D0h+var_198]; int *
0x18006a17f  lea     rdx, [rbp+0D0h+Uuid]; Uuid
0x18006a183  lea     rcx, [rbp+0D0h+Buf1]; Buf1
0x18006a187  call    ?IsSessionCompatible@CTerminalTypeHelper@@SAHU_GUID@@0PEAH@Z; CTerminalTypeHelper::IsSessionCompatible(_GUID,_GUID,int *)
0x18006a18c  test    eax, eax
0x18006a18e  jnz     short loc_18006A1B4
0x18006a190  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 4; ulong g_DebugTraceComponent
0x18006a197  jz      short loc_18006A1AA
0x18006a199  lea     rdx, aCtssessionConn_2; "CTSSession::Connect FAILED due to termi"...
0x18006a1a0  mov     ecx, 2; int
0x18006a1a5  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18006a1aa  mov     edi, 80071B9Dh
0x18006a1af  jmp     loc_18006A532
0x18006a1b4  mov     rdx, rbx; struct ITSSession *
0x18006a1b7  mov     rcx, r15; this
0x18006a1ba  call    ?IsSessionProtocolCompatible@CTSSession@@UEAAHPEAUITSSession@@@Z; CTSSession::IsSessionProtocolCompatible(ITSSession *)
0x18006a1bf  test    eax, eax
0x18006a1c1  jnz     short loc_18006A1D5
0x18006a1c3  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 4; ulong g_DebugTraceComponent
0x18006a1ca  jz      short loc_18006A1AA
0x18006a1cc  lea     rdx, aCtssessionConn_4; "CTSSession::Connect FAILED due to proto"...
0x18006a1d3  jmp     short loc_18006A1A0
0x18006a1d5  mov     rbx, [rsp+1D0h+var_160]
0x18006a1da  mov     rax, [rbx]
0x18006a1dd  lea     r8, [rsp+1D0h+var_190]
0x18006a1e2  xor     edx, edx
0x18006a1e4  mov     rcx, rbx
0x18006a1e7  mov     rax, [rax+38h]
0x18006a1eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a1f0  mov     edi, eax
0x18006a1f2  mov     eax, 800708CAh
0x18006a1f7  cmp     edi, eax
0x18006a1f9  jnz     short loc_18006A202
0x18006a1fb  mov     edi, 80071B70h
0x18006a200  jmp     short loc_18006A206
0x18006a202  test    edi, edi
0x18006a204  jns     short loc_18006A215
0x18006a206  mov     r8d, edi
0x18006a209  lea     rdx, aTargetDisconne; "Target->Disconnect failed: 0x%x in %s"
0x18006a210  jmp     loc_180069FF2
0x18006a215  mov     rcx, [rsp+1D0h+var_190]
0x18006a21a  test    rcx, rcx
0x18006a21d  jnz     short loc_18006A244
0x18006a21f  mov     edi, eax
0x18006a221  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 4; ulong g_DebugTraceComponent
0x18006a228  jz      loc_18006A532
0x18006a22e  lea     rdx, aCtssessionConn; "CTSSession::Connect because target sess"...
0x18006a235  mov     ecx, 2; int
0x18006a23a  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18006a23f  jmp     loc_18006A532
0x18006a244  lea     rdi, [r15+0C88h]
0x18006a24b  mov     rax, [rcx]
0x18006a24e  mov     rdx, rdi
0x18006a251  mov     rax, [rax+0D8h]
0x18006a258  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a25d  mov     rdx, rdi
0x18006a260  mov     ecx, 2
0x18006a265  call    cs:__imp_EtwEventActivityIdControl
0x18006a26c  nop     dword ptr [rax+rax+00h]
0x18006a271  mov     rcx, [rsp+1D0h+var_180]
0x18006a276  mov     rax, [rcx]
0x18006a279  xor     r8d, r8d
0x18006a27c  lea     edx, [r8+5]
0x18006a280  mov     rax, [rax+38h]
0x18006a284  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a289  mov     edi, eax
0x18006a28b  test    eax, eax
0x18006a28d  jns     short loc_18006A29B
0x18006a28f  lea     rdx, aSourceDisconne; "Source->Disconnect failed: 0x%x in %s"
0x18006a296  jmp     loc_180069FEF
0x18006a29b  mov     rax, [rbx]
0x18006a29e  lea     rdx, [r15+840h]
0x18006a2a5  mov     rcx, rbx
0x18006a2a8  mov     rax, [rax+50h]
0x18006a2ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a2b1  mov     [rsp+1D0h+var_158], r13
0x18006a2b6  mov     [rsp+1D0h+var_168], r13d
0x18006a2bb  mov     rax, [rbx]
0x18006a2be  lea     r9, [rsp+1D0h+var_168]
0x18006a2c3  lea     r8, [rsp+1D0h+var_158]
0x18006a2c8  lea     rdx, [rsp+1D0h+var_170]
0x18006a2cd  mov     rcx, rbx
0x18006a2d0  mov     rax, [rax+128h]
0x18006a2d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a2dc  mov     edi, eax
0x18006a2de  test    eax, eax
0x18006a2e0  jns     short loc_18006A2EE
0x18006a2e2  lea     rdx, aPtrtargetGetse; "ptrTarget->GetSecurityDescriptor failed"...
0x18006a2e9  jmp     loc_180069FEF
0x18006a2ee  lea     r14, [r15+16F0h]
0x18006a2f5  mov     rdx, [r14+30h]; unsigned __int16 *
0x18006a2f9  test    rdx, rdx
0x18006a2fc  jz      short loc_18006A331
0x18006a2fe  mov     rcx, [rsp+1D0h+var_170]
0x18006a303  test    rcx, rcx
0x18006a306  jz      short loc_18006A331
0x18006a308  mov     rax, rdx
0x18006a30b  sub     rcx, rdx; this
0x18006a30e  movzx   r9d, word ptr [rax]
0x18006a312  movzx   r8d, word ptr [rax+rcx]
0x18006a317  sub     r9d, r8d
0x18006a31a  jnz     short loc_18006A325
0x18006a31c  add     rax, 2
0x18006a320  test    r8d, r8d
0x18006a323  jnz     short loc_18006A30E
0x18006a325  test    r9d, r9d
0x18006a328  jz      loc_18006A3F8
0x18006a32e  xor     r13d, r13d
0x18006a331  lea     r8, [rsp+1D0h+var_178]; unsigned __int16 **
0x18006a336  call    ?CopySource@CTSSecurityDescriptor@@IEAAJPEBGPEAPEAG@Z; CTSSecurityDescriptor::CopySource(ushort const *,ushort * *)
0x18006a33b  mov     edi, eax
0x18006a33d  test    eax, eax
0x18006a33f  jns     short loc_18006A366
0x18006a341  lea     r9, aCtssessionConn_1; "CTSSession::Connect"
0x18006a348  mov     r8d, eax
0x18006a34b  lea     rdx, aThisSecurityde_0; "this->SecurityDescriptor.GetSource fail"...
0x18006a352  mov     ecx, 8; int
0x18006a357  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18006a35c  mov     rsi, [rsp+1D0h+var_178]
0x18006a361  jmp     loc_18006A532
0x18006a366  mov     rcx, r14; this
0x18006a369  call    ?DetachSD@CTSSessionSecurityDescriptor@@QEAAPEAXXZ; CTSSessionSecurityDescriptor::DetachSD(void)
0x18006a36e  mov     r12, rax
0x18006a371  mov     r8, [rsp+1D0h+var_158]; void *
0x18006a376  mov     rdx, [rsp+1D0h+var_170]; unsigned __int16 *
0x18006a37b  mov     rcx, r14; this
0x18006a37e  call    ?Initialize@CTSSessionSecurityDescriptor@@QEAAJPEBGPEAX@Z; CTSSessionSecurityDescriptor::Initialize(ushort const *,void *)
0x18006a383  mov     edi, eax
0x18006a385  test    eax, eax
0x18006a387  jns     short loc_18006A3AE
0x18006a389  mov     r8, r12; void *
0x18006a38c  mov     rdx, [rsp+1D0h+var_178]; unsigned __int16 *
0x18006a391  mov     rcx, r14; this
0x18006a394  call    ?Attach@CTSSessionSecurityDescriptor@@QEAAXPEAGPEAX@Z; CTSSessionSecurityDescriptor::Attach(ushort *,void *)
0x18006a399  mov     rsi, r13
0x18006a39c  mov     r12, r13
0x18006a39f  mov     r8d, edi
0x18006a3a2  lea     rdx, aThisSecurityde; "this->SecurityDescriptor.Initialize fai"...
0x18006a3a9  jmp     loc_180069FF2
0x18006a3ae  mov     rdx, [r15+1728h]; struct IUserName *
0x18006a3b5  test    rdx, rdx
0x18006a3b8  jz      short loc_18006A3ED
0x18006a3ba  mov     rcx, r14; this
0x18006a3bd  call    ?AddUserAce@CTSSessionSecurityDescriptor@@QEAAJPEAUIUserName@@@Z; CTSSessionSecurityDescriptor::AddUserAce(IUserName *)
0x18006a3c2  mov     edi, eax
0x18006a3c4  test    eax, eax
0x18006a3c6  jns     short loc_18006A3ED
0x18006a3c8  mov     r8, r12; void *
0x18006a3cb  mov     rdx, [rsp+1D0h+var_178]; unsigned __int16 *
0x18006a3d0  mov     rcx, r14; this
0x18006a3d3  call    ?Attach@CTSSessionSecurityDescriptor@@QEAAXPEAGPEAX@Z; CTSSessionSecurityDescriptor::Attach(ushort *,void *)
0x18006a3d8  mov     rsi, r13
0x18006a3db  mov     r12, r13
0x18006a3de  mov     r8d, edi
0x18006a3e1  lea     rdx, aThisSecurityde_1; "this->SecurityDescriptor.AddUserAce fai"...
0x18006a3e8  jmp     loc_180069FF2
0x18006a3ed  mov     r13d, 1
0x18006a3f3  mov     rsi, [rsp+1D0h+var_178]
0x18006a3f8  mov     rcx, [rsp+1D0h+var_180]
0x18006a3fd  mov     rax, [rcx]
0x18006a400  xor     r9d, r9d
0x18006a403  mov     r8d, [rsp+1D0h+var_164]
  ... truncated ...
```
