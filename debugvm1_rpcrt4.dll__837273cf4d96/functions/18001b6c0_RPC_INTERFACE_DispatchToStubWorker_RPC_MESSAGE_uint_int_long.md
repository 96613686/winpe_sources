# RPC_INTERFACE::DispatchToStubWorker(_RPC_MESSAGE *,uint,int,long *)

- ea: `0x18001b6c0`
- end: `0x18001bed5`
- name: `?DispatchToStubWorker@RPC_INTERFACE@@AEAAJPEAU_RPC_MESSAGE@@IHPEAJ@Z`
- size: `2069`
- prototype: `__int64 __usercall@<rax>(RPC_INTERFACE *__hidden this@<rcx>, struct _RPC_MESSAGE *@<rdx>, unsigned int@<r8d>, int@<r9d>, int *)`
- caller_count: `4`
- callee_count: `14`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x18001b110`
- `0x1800229b0`
- `0x180027610`
- `0x1800716d8`

## callees

- `0x18001b6c0`
- `0x18001d65c`
- `0x18001d750`
- `0x180021e18`
- `0x180027d50`
- `0x180027dd4`
- `0x180027e10`
- `0x1800283bc`
- `0x18004700c`
- `0x18007a810`
- `0x18007bb40`
- `0x18008a000`
- `0x1800ca140`
- `0x1800d2010`

## import_xrefs

- `ntdll!RtlSetThreadSubProcessTag` at `0x18001b83f`
- `ntdll!RtlSetThreadSubProcessTag` at `0x18001b888`
- `ntdll!RtlSetThreadSubProcessTag` at `0x18001b83f`
- `ntdll!RtlSetThreadSubProcessTag` at `0x18001b888`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001ba7f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001ba7f`

## pseudocode

```c
__int64 __fastcall RPC_INTERFACE::DispatchToStubWorker(
        RPC_INTERFACE *this,
        struct _RPC_MESSAGE *a2,
        unsigned int a3,
        int a4,
        int *a5)
{
  unsigned int v5; // r10d
  unsigned __int64 ReservedForNtRpc; // rbx
  unsigned int v9; // r12d
  char *v10; // r13
  __int64 v11; // rcx
  __int64 v12; // r14
  unsigned int ProcNum; // r15d
  __int64 v14; // rcx
  _DWORD *Handle; // rcx
  struct THREAD *v16; // rax
  int v17; // r8d
  _QWORD *ReservedForRuntime; // rax
  _QWORD *v19; // r14
  unsigned int v20; // ebx
  __int64 v21; // rax
  __int64 v22; // rcx
  __int64 v23; // rax
  struct ServerContextHandle *v24; // rdx
  void *Buffer; // rax
  unsigned int i; // ecx
  __int64 v28; // r13
  __int64 v29; // rdx
  unsigned int j; // ecx
  struct tagExtendedErrorInfo *ExtendedErrorInfoRecord; // rax
  struct tagExtendedErrorInfo *v32; // r14
  __int64 v33; // xmm0_8
  int v34; // eax
  __int64 v35; // xmm0_8
  int v36; // eax
  int v37; // eax
  __int64 v38; // xmm0_8
  int v39; // eax
  int v40; // eax
  __int64 v41; // xmm0_8
  int v42; // eax
  int v43; // eax
  __int64 v44; // rcx
  unsigned __int16 v45; // r8
  __int64 v46; // rax
  unsigned int v47; // ecx
  RPC_BINDING_HANDLE v48; // rcx
  signed __int32 v49[8]; // [rsp+0h] [rbp-100h] BYREF
  char v50; // [rsp+30h] [rbp-D0h] BYREF
  char v51; // [rsp+38h] [rbp-C8h] BYREF
  unsigned int v52; // [rsp+40h] [rbp-C0h]
  int *v53; // [rsp+48h] [rbp-B8h]
  struct _RPC_MESSAGE *v54; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v55; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v56; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v57; // [rsp+68h] [rbp-98h]
  __int64 v58; // [rsp+70h] [rbp-90h] BYREF
  __int64 v59; // [rsp+78h] [rbp-88h] BYREF
  __int64 v60; // [rsp+80h] [rbp-80h] BYREF
  _QWORD v61[2]; // [rsp+90h] [rbp-70h] BYREF
  __int128 v62; // [rsp+A0h] [rbp-60h]
  __int128 v63; // [rsp+B0h] [rbp-50h]
  __int64 v64; // [rsp+C0h] [rbp-40h]
  __int64 v65; // [rsp+C8h] [rbp-38h]
  __int128 v66; // [rsp+D0h] [rbp-30h]
  _DWORD v67[3]; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v68[12]; // [rsp+ECh] [rbp-14h]
  __int64 v69; // [rsp+F8h] [rbp-8h]
  __int128 v70; // [rsp+100h] [rbp+0h]
  __int64 *v71; // [rsp+110h] [rbp+10h]
  __int128 v72; // [rsp+118h] [rbp+18h]
  __int64 v73; // [rsp+128h] [rbp+28h]
  __int128 v74; // [rsp+130h] [rbp+30h]
  _BYTE v75[16]; // [rsp+140h] [rbp+40h] BYREF
  char *v76; // [rsp+150h] [rbp+50h]
  __int64 v77; // [rsp+158h] [rbp+58h]
  char *v78; // [rsp+160h] [rbp+60h]
  __int64 v79; // [rsp+168h] [rbp+68h]
  __int64 *v80; // [rsp+170h] [rbp+70h]
  __int64 v81; // [rsp+178h] [rbp+78h]
  __int64 *v82; // [rsp+180h] [rbp+80h]
  __int64 v83; // [rsp+188h] [rbp+88h]
  __int64 *v84; // [rsp+190h] [rbp+90h]
  __int64 v85; // [rsp+198h] [rbp+98h]

  v5 = a3;
  v53 = a5;
  v52 = a3;
  ReservedForNtRpc = (unsigned __int64)NtCurrentTeb()->ReservedForNtRpc;
  if ( ReservedForNtRpc )
  {
    ReservedForNtRpc ^= 0xABABABABDEDEDEDEuLL;
    if ( *(HANDLE *)(ReservedForNtRpc + 16) != NtCurrentTeb()->ClientId.UniqueThread )
      __fastfail(0x1Eu);
  }
  v9 = 0;
  v10 = (char *)this + 80;
  if ( (*((_DWORD *)this + 42) & 0x2000000) != 0 )
  {
    v11 = *((_QWORD *)this + 22) + 80LL * a4;
    a2->TransferSyntax = (PRPC_SYNTAX_IDENTIFIER)v11;
    v12 = *(_QWORD *)(v11 + 24);
    if ( v12 )
      goto LABEL_6;
  }
  else
  {
    a2->TransferSyntax = (PRPC_SYNTAX_IDENTIFIER)((char *)this + 104);
  }
  v12 = *((_QWORD *)this + 16);
LABEL_6:
  if ( (*((_DWORD *)this + 2) & 2) != 0 )
    ProcNum = 0;
  else
    ProcNum = a2->ProcNum;
  if ( !a3 )
  {
    if ( (*((_DWORD *)this + 2) & 1) == 0 )
    {
      v44 = *(_QWORD *)this;
      if ( *(_DWORD *)(*(_QWORD *)this + 336LL) )
      {
        if ( !*(_DWORD *)(v44 + 340) || _InterlockedDecrement((volatile signed __int32 *)(v44 + 120)) >= 0 )
          goto LABEL_11;
        _InterlockedIncrement((volatile signed __int32 *)(v44 + 120));
        v9 = 1723;
        v45 = 182;
      }
      else
      {
        v9 = 1715;
        v45 = 181;
      }
      RpcpErrorAddRecord(2u, v9, v45, 0, 0);
LABEL_81:
      v5 = v52;
      goto LABEL_11;
    }
    if ( *((_DWORD *)this + 51) != 1234 )
    {
      _InterlockedOr(v49, 0);
      v47 = *((_DWORD *)this + 51);
      if ( *((_DWORD *)this + 87) > v47 )
      {
        v9 = 1723;
        _InterlockedOr(v49, 0);
        RpcpErrorAddRecord(2u, 1723, 0xB4u, *((_DWORD *)this + 87), v47);
        goto LABEL_81;
      }
    }
  }
LABEL_11:
  if ( ProcNum >= *(_DWORD *)v12 )
  {
    if ( v9 != 1723 )
      RPC_INTERFACE::EndCall(this, v5, 0);
    v9 = 1745;
    RpcpErrorAddRecord(2u, 1745, 0xB7u, 0, 0);
    goto LABEL_32;
  }
  if ( v9 )
  {
LABEL_32:
    (*(void (__fastcall **)(RPC_BINDING_HANDLE, struct _RPC_MESSAGE *))(*(_QWORD *)a2->Handle + 120LL))(a2->Handle, a2);
    return v9;
  }
  v14 = *(_QWORD *)this;
  v57 = 0;
  ++*(_DWORD *)(v14 + 64);
  *((_QWORD *)a2->ReservedForRuntime + 1) = a2->Buffer;
  Handle = a2->Handle;
  a2->RpcInterfaceInformation = v10;
  if ( v5 )
    Handle[58] |= 1u;
  *((_QWORD *)Handle + 28) = a2->Buffer;
  v16 = ThreadSelf();
  if ( v16 )
  {
    *((_DWORD *)v16 + 51) = ProcNum;
    *((_OWORD *)v16 + 13) = *(_OWORD *)((char *)this + 84);
    *((_DWORD *)v16 + 56) = *((_DWORD *)this + 25);
  }
  if ( *((_QWORD *)this + 69) )
    v57 = ((__int64 (*)(void))RtlSetThreadSubProcessTag)();
  if ( (unsigned int)((__int64 (__fastcall *)(_QWORD, struct _RPC_MESSAGE *, int *))DispatchToStubInC)(
                       *(_QWORD *)(*(_QWORD *)(v12 + 8) + 8LL * ProcNum),
                       a2,
                       v53) )
  {
    if ( dword_1800F9624 )
    {
      for ( i = 0; i < 4; ++i )
      {
        if ( `LogEventToEtw'::`2'::EtwEventSubjectFilter[i] == 120 )
          goto LABEL_56;
      }
      if ( (Microsoft_Windows_RPCEnableBits & 8) != 0 )
      {
        v46 = *(_QWORD *)(v12 + 8);
        v54 = a2;
        v51 = 83;
        v50 = 120;
        v56 = *(_QWORD *)(v46 + 8LL * ProcNum);
        v69 = 1;
        *((_QWORD *)&v70 + 1) = 1;
        v55 = *v53;
        *(_QWORD *)&v68[4] = &v50;
        *(_QWORD *)&v70 = &v51;
        v71 = &v55;
        *((_QWORD *)&v72 + 1) = &v56;
        *(_QWORD *)&v74 = &v54;
        *(_QWORD *)&v72 = 8;
        v73 = 8;
        *((_QWORD *)&v74 + 1) = 8;
        McGenEventWrite_EtwEventWriteTransfer(
          (unsigned int)&RpcEtwGuid_Context,
          (unsigned int)RPCLogEvent,
          v17,
          6,
          (__int64)v67);
      }
    }
LABEL_56:
    v9 = -1073606642;
    v28 = 3;
    LODWORD(v55) = GetCurrentThreadId();
    v67[0] = 3;
    LODWORD(v69) = 4;
    LOWORD(v70) = ProcNum;
    v29 = (unsigned int)*v53;
    LODWORD(v54) = *((_DWORD *)this + 21);
    v67[2] = (_DWORD)v54;
    LODWORD(v53) = a2->RpcFlags;
    LODWORD(v72) = (_DWORD)v53;
    LODWORD(v56) = v29;
    LODWORD(v71) = 3;
    LODWORD(v73) = 3;
    LODWORD(v74) = v55;
    if ( dword_1800F9624 )
    {
      for ( j = 0; j < 4; ++j )
      {
        if ( `LogEventToEtw'::`2'::EtwEventSubjectFilter[j] == 73 )
          goto LABEL_63;
      }
      if ( (Microsoft_Windows_RPCEnableBits & 8) != 0 )
      {
        v60 = (int)v54;
        v58 = v29;
        v76 = &v51;
        v59 = 1;
        v78 = &v50;
        v80 = &v58;
        v82 = &v59;
        v84 = &v60;
        v50 = 1;
        v51 = 73;
        v77 = 1;
        v79 = 1;
        v81 = 8;
        v83 = 8;
        v85 = 8;
        McGenEventWrite_EtwEventWriteTransfer(
          (unsigned int)&RpcEtwGuid_Context,
          (unsigned int)RPCLogEvent,
          (unsigned int)"HbBr",
          6,
          (__int64)v75);
      }
    }
LABEL_63:
    ExtendedErrorInfoRecord = AllocateExtendedErrorInfoRecord(4u);
    v32 = ExtendedErrorInfoRecord;
    if ( ExtendedErrorInfoRecord )
    {
      InitializePrivateEEInfo(ExtendedErrorInfoRecord);
      v33 = *(_QWORD *)v68;
      *((_WORD *)v32 + 28) = 1;
      *((_DWORD *)v32 + 12) = 1;
      *((_DWORD *)v32 + 13) = v56;
      *((_DWORD *)v32 + 17) = v67[1];
      *((_DWORD *)v32 + 18) = (_DWORD)v54;
      v34 = *(_DWORD *)&v68[8];
      *(_QWORD *)((char *)v32 + 76) = v33;
      v35 = *(_QWORD *)((char *)&v70 + 2);
      *((_DWORD *)v32 + 21) = v34;
      v36 = HIDWORD(v69);
      *((_DWORD *)v32 + 16) = 3;
      *((_DWORD *)v32 + 22) = 4;
      *((_DWORD *)v32 + 23) = v36;
      v37 = *(_DWORD *)((char *)&v70 + 10);
      *((_WORD *)v32 + 48) = ProcNum;
      *(_QWORD *)((char *)v32 + 98) = v35;
      v38 = *(_QWORD *)((char *)&v72 + 4);
      *(_DWORD *)((char *)v32 + 106) = v37;
      *((_WORD *)v32 + 55) = HIWORD(v70);
      v39 = HIDWORD(v71);
      *((_DWORD *)v32 + 28) = 3;
      *((_DWORD *)v32 + 29) = v39;
      *((_DWORD *)v32 + 30) = (_DWORD)v53;
      v40 = HIDWORD(v72);
      *(_QWORD *)((char *)v32 + 124) = v38;
      v41 = *(_QWORD *)((char *)&v74 + 4);
      *((_DWORD *)v32 + 33) = v40;
      v42 = HIDWORD(v73);
      *((_DWORD *)v32 + 34) = 3;
      *((_DWORD *)v32 + 35) = v42;
      *((_DWORD *)v32 + 36) = v55;
      v43 = HIDWORD(v74);
      *(_QWORD *)((char *)v32 + 148) = v41;
      *((_DWORD *)v32 + 39) = v43;
      if ( (unsigned int)AddPrivateRecord(v32) )
        FreeEEInfoRecord(v32);
    }
    else
    {
      do
        FreeEEInfoPrivateParam(&v67[6 * v28--]);
      while ( v28 != -1 );
    }
  }
  if ( *((_QWORD *)this + 69) )
    RtlSetThreadSubProcessTag(v57);
  ReservedForRuntime = a2->ReservedForRuntime;
  v61[0] = 0;
  v62 = 0;
  v61[1] = 0;
  v63 = 0;
  v65 = 0;
  v66 = 0;
  v64 = 0;
  *(_QWORD *)&v62 = ReservedForRuntime[1];
  *(_DWORD *)(ReservedForNtRpc + 120) &= ~4u;
  if ( *(_DWORD *)ReservedForNtRpc )
  {
    if ( !v9 || (void *)v62 == a2->Buffer )
      return v9;
    goto LABEL_32;
  }
  v19 = a2->Handle;
  if ( *((_DWORD *)a2->Handle + 65) )
  {
    v20 = 0;
    while ( v20 < *((_DWORD *)v19 + 64) )
    {
      v21 = v20++;
      v22 = 8 * v21;
      v23 = v19[31];
      v24 = *(struct ServerContextHandle **)(v22 + v23);
      if ( v24 )
      {
        if ( ((unsigned __int8)v24 & 1) != 0 )
        {
          --*((_DWORD *)v19 + 65);
          *(_QWORD *)(v22 + v23) = 0;
        }
        else
        {
          NDRSContextHandlePostDispatchProcessing((struct SCALL *)v19, v24);
        }
      }
    }
  }
  if ( (v19[29] & 1) != 0 )
    *((_DWORD *)v19 + 58) &= ~1u;
  Buffer = a2->Buffer;
  if ( v9 )
  {
    if ( (void *)v62 != Buffer )
      (*(void (__fastcall **)(RPC_BINDING_HANDLE, _QWORD *))(*(_QWORD *)a2->Handle + 120LL))(a2->Handle, v61);
    if ( a2->Buffer )
      (*(void (__fastcall **)(RPC_BINDING_HANDLE, struct _RPC_MESSAGE *))(*(_QWORD *)a2->Handle + 120LL))(
        a2->Handle,
        a2);
    RPC_INTERFACE::EndCall(this, v52, 0);
  }
  else
  {
    if ( (void *)v62 == Buffer )
    {
      v48 = a2->Handle;
      a2->RpcFlags = 0;
      a2->BufferLength = 0;
      (*(void (__fastcall **)(RPC_BINDING_HANDLE, struct _RPC_MESSAGE *, _QWORD))(*(_QWORD *)v48 + 112LL))(v48, a2, 0);
    }
    (*(void (__fastcall **)(RPC_BINDING_HANDLE, _QWORD *))(*(_QWORD *)a2->Handle + 120LL))(a2->Handle, v61);
    if ( !v52 && (*((_DWORD *)this + 2) & 1) == 0 && *(_DWORD *)(*(_QWORD *)this + 340LL) )
      _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)this + 120LL));
  }
  return v9;
}

```

## disassembly

```asm
0x18001b6c0  push    rbp
0x18001b6c2  push    rbx
0x18001b6c3  push    rsi
0x18001b6c4  push    rdi
0x18001b6c5  lea     rbp, [rsp-0C8h]
0x18001b6cd  sub     rsp, 1C8h
0x18001b6d4  mov     rax, cs:__security_cookie
0x18001b6db  xor     rax, rsp
0x18001b6de  mov     [rbp+0E0h+var_40], rax
0x18001b6e5  mov     rax, [rbp+0E0h+arg_20]
0x18001b6ec  mov     r10d, r8d
0x18001b6ef  mov     [rsp+1E0h+var_198], rax
0x18001b6f4  mov     rsi, rdx
0x18001b6f7  mov     rax, gs:30h
0x18001b700  mov     rdi, rcx
0x18001b703  mov     [rsp+1E0h+var_1A0], r8d
0x18001b708  mov     rbx, [rax+1698h]
0x18001b70f  test    rbx, rbx
0x18001b712  jz      short loc_18001B738
0x18001b714  mov     rax, 0ABABABABDEDEDEDEh
0x18001b71e  xor     rbx, rax
0x18001b721  mov     rax, gs:30h
0x18001b72a  mov     rcx, [rax+48h]
0x18001b72e  cmp     [rbx+10h], rcx
0x18001b732  jnz     loc_18001B918
0x18001b738  mov     [rsp+1E0h+arg_10], r12
0x18001b740  xor     r12d, r12d
0x18001b743  mov     [rsp+1E0h+var_20], r13
0x18001b74b  lea     r13, [rdi+50h]
0x18001b74f  test    dword ptr [r13+58h], 2000000h
0x18001b757  mov     [rsp+1E0h+var_28], r14
0x18001b75f  mov     [rsp+1E0h+var_30], r15
0x18001b767  jz      loc_18001B9CF
0x18001b76d  movsxd  rax, r9d
0x18001b770  lea     rcx, [rax+rax*4]
0x18001b774  shl     rcx, 4
0x18001b778  add     rcx, [rdi+0B0h]
0x18001b77f  mov     [rdx+20h], rcx
0x18001b783  mov     r14, [rcx+18h]
0x18001b787  test    r14, r14
0x18001b78a  jnz     short loc_18001B793
0x18001b78c  mov     r14, [rdi+80h]
0x18001b793  mov     eax, [rdi+8]
0x18001b796  test    al, 2
0x18001b798  jz      loc_18001B93D
0x18001b79e  xor     r15d, r15d
0x18001b7a1  test    r8d, r8d
0x18001b7a4  jnz     short loc_18001B7C1
0x18001b7a6  mov     eax, [rdi+8]
0x18001b7a9  test    al, 1
0x18001b7ab  jz      loc_18001BC0E
0x18001b7b1  cmp     dword ptr [rdi+0CCh], 4D2h
0x18001b7bb  jnz     loc_18001BE2A
0x18001b7c1  cmp     r15d, [r14]
0x18001b7c4  jnb     loc_18001B9DC
0x18001b7ca  test    r12d, r12d
0x18001b7cd  jnz     loc_18001BA18
0x18001b7d3  mov     rcx, [rdi]
0x18001b7d6  mov     [rsp+1E0h+var_178], 0
0x18001b7df  mov     eax, [rcx+40h]
0x18001b7e2  inc     eax
0x18001b7e4  mov     [rcx+40h], eax
0x18001b7e7  mov     rcx, [rsi+30h]
0x18001b7eb  mov     rax, [rsi+10h]
0x18001b7ef  mov     [rcx+8], rax
0x18001b7f3  mov     rcx, [rsi]
0x18001b7f6  mov     [rsi+28h], r13
0x18001b7fa  test    r10d, r10d
0x18001b7fd  jnz     loc_18001BE76
0x18001b803  mov     rax, [rsi+10h]
0x18001b807  mov     [rcx+0E0h], rax
0x18001b80e  call    ?ThreadSelf@@YAPEAVTHREAD@@XZ; ThreadSelf(void)
0x18001b813  test    rax, rax
0x18001b816  jz      short loc_18001B833
0x18001b818  mov     [rax+0CCh], r15d
0x18001b81f  movups  xmm0, xmmword ptr [rdi+54h]
0x18001b823  movups  xmmword ptr [rax+0D0h], xmm0
0x18001b82a  mov     ecx, [rdi+64h]
0x18001b82d  mov     [rax+0E0h], ecx
0x18001b833  mov     rcx, [rdi+228h]
0x18001b83a  test    rcx, rcx
0x18001b83d  jz      short loc_18001B84A
0x18001b83f  call    cs:__imp_RtlSetThreadSubProcessTag
0x18001b845  mov     [rsp+1E0h+var_178], rax
0x18001b84a  mov     r8, [rsp+1E0h+var_198]
0x18001b84f  mov     rdx, rsi
0x18001b852  mov     rax, cs:DispatchToStubInC
0x18001b859  mov     ecx, r15d
0x18001b85c  lea     r13, ds:0[rcx*8]
0x18001b864  mov     rcx, [r14+8]
0x18001b868  mov     rcx, [rcx+r13]
0x18001b86c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b871  test    eax, eax
0x18001b873  jnz     loc_18001BA48
0x18001b879  cmp     qword ptr [rdi+228h], 0
0x18001b881  jz      short loc_18001B88E
0x18001b883  mov     rcx, [rsp+1E0h+var_178]
0x18001b888  call    cs:__imp_RtlSetThreadSubProcessTag
0x18001b88e  mov     rax, [rsi+30h]
0x18001b892  xor     r10d, r10d
0x18001b895  mov     [rbp+0E0h+var_150], r10
0x18001b899  xorps   xmm0, xmm0
0x18001b89c  movdqa  [rbp+0E0h+var_140], xmm0
0x18001b8a1  xorps   xmm1, xmm1
0x18001b8a4  mov     [rbp+0E0h+var_148], r10
0x18001b8a8  movdqa  [rbp+0E0h+var_130], xmm1
0x18001b8ad  mov     [rbp+0E0h+var_118], r10
0x18001b8b1  movdqa  [rbp+0E0h+var_110], xmm0
0x18001b8b6  mov     [rbp+0E0h+var_120], r10
0x18001b8ba  mov     rcx, [rax+8]
0x18001b8be  mov     qword ptr [rbp+0E0h+var_140], rcx
0x18001b8c2  and     dword ptr [rbx+78h], 0FFFFFFFBh
0x18001b8c6  cmp     [rbx], r10d
0x18001b8c9  jnz     short loc_18001B91F
0x18001b8cb  mov     r14, [rsi]
0x18001b8ce  cmp     [r14+104h], r10d
0x18001b8d5  jbe     short loc_18001B946
0x18001b8d7  mov     ebx, r10d
0x18001b8da  mov     r9d, [r14+100h]
0x18001b8e1  cmp     ebx, r9d
0x18001b8e4  jnb     short loc_18001B946
0x18001b8e6  mov     eax, ebx
0x18001b8e8  inc     ebx
0x18001b8ea  lea     rcx, ds:0[rax*8]
0x18001b8f2  mov     rax, [r14+0F8h]
0x18001b8f9  mov     rdx, [rcx+rax]; struct ServerContextHandle *
0x18001b8fd  test    rdx, rdx
0x18001b900  jz      short loc_18001B8E1
0x18001b902  test    dl, 1
0x18001b905  jz      loc_18001BBFE
0x18001b90b  dec     dword ptr [r14+104h]
0x18001b912  mov     [rcx+rax], r10
0x18001b916  jmp     short loc_18001B8DA
0x18001b918  mov     ecx, 1Eh
0x18001b91d  int     29h; Win8: RtlFailFast(ecx)
0x18001b91f  test    r12d, r12d
0x18001b922  jz      short loc_18001B991
0x18001b924  mov     rax, [rsi+10h]
0x18001b928  cmp     qword ptr [rbp+0E0h+var_140], rax
0x18001b92c  jz      short loc_18001B991
0x18001b92e  mov     rcx, [rsi]
0x18001b931  mov     rax, [rcx]
0x18001b934  mov     rax, [rax+78h]
0x18001b938  jmp     loc_18001BA22
0x18001b93d  mov     r15d, [rdx+1Ch]
0x18001b941  jmp     loc_18001B7A1
0x18001b946  mov     eax, [r14+0E8h]
0x18001b94d  test    al, 1
0x18001b94f  jnz     loc_18001BE1D
0x18001b955  mov     rax, [rsi+10h]
0x18001b959  test    r12d, r12d
0x18001b95c  jnz     loc_18001BDE6
0x18001b962  cmp     qword ptr [rbp+0E0h+var_140], rax
0x18001b966  jz      loc_18001BE9B
0x18001b96c  mov     rcx, [rsi]
0x18001b96f  lea     rdx, [rbp+0E0h+var_150]
0x18001b973  mov     rax, [rcx]
0x18001b976  mov     rax, [rax+78h]
0x18001b97a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b97f  cmp     [rsp+1E0h+var_1A0], 0
0x18001b984  jnz     short loc_18001B991
0x18001b986  mov     eax, [rdi+8]
0x18001b989  test    al, 1
0x18001b98b  jz      loc_18001BA2F
0x18001b991  mov     r14, [rsp+1E0h+var_28]
0x18001b999  mov     eax, r12d
0x18001b99c  mov     r12, [rsp+1E0h+arg_10]
0x18001b9a4  mov     r13, [rsp+1E0h+var_20]
0x18001b9ac  mov     r15, [rsp+1E0h+var_30]
0x18001b9b4  mov     rcx, [rbp+0E0h+var_40]
0x18001b9bb  xor     rcx, rsp; StackCookie
0x18001b9be  call    __security_check_cookie
0x18001b9c3  add     rsp, 1C8h
0x18001b9ca  pop     rdi
0x18001b9cb  pop     rsi
0x18001b9cc  pop     rbx
0x18001b9cd  pop     rbp
0x18001b9ce  retn
0x18001b9cf  lea     rax, [r13+18h]
0x18001b9d3  mov     [rdx+20h], rax
0x18001b9d7  jmp     loc_18001B78C
0x18001b9dc  cmp     r12d, 6BBh
0x18001b9e3  jz      short loc_18001B9F3
0x18001b9e5  xor     r8d, r8d; int
0x18001b9e8  mov     edx, r10d; unsigned int
0x18001b9eb  mov     rcx, rdi; this
0x18001b9ee  call    ?EndCall@RPC_INTERFACE@@QEAAXIH@Z; RPC_INTERFACE::EndCall(uint,int)
0x18001b9f3  mov     r12d, 6D1h
0x18001b9f9  mov     [rsp+1E0h+var_1C0], 0; struct tagParam *
0x18001ba02  mov     edx, r12d; int
0x18001ba05  mov     r8d, 0B7h; unsigned __int16
0x18001ba0b  xor     r9d, r9d; int
0x18001ba0e  mov     ecx, 2; unsigned int
0x18001ba13  call    ?RpcpErrorAddRecord@@YAXKJGHPEAUtagParam@@@Z; RpcpErrorAddRecord(ulong,long,ushort,int,tagParam *)
0x18001ba18  mov     rcx, [rsi]
0x18001ba1b  mov     r8, [rcx]
0x18001ba1e  mov     rax, [r8+78h]
0x18001ba22  mov     rdx, rsi
0x18001ba25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ba2a  jmp     loc_18001B991
0x18001ba2f  mov     rax, [rdi]
0x18001ba32  cmp     dword ptr [rax+154h], 0
0x18001ba39  jz      loc_18001B991
0x18001ba3f  lock inc dword ptr [rax+78h]
0x18001ba43  jmp     loc_18001B991
0x18001ba48  cmp     cs:dword_1800F9624, 0
0x18001ba4f  lea     rdx, ?EtwEventSubjectFilter@?1??LogEventToEtw@@YAXEE_J00@Z@4QBEB; "HbBr"
0x18001ba56  jz      short loc_18001BA79
0x18001ba58  xor     ecx, ecx
0x18001ba5a  cmp     ecx, 4
0x18001ba5d  jnb     short loc_18001BA6C
0x18001ba5f  movsxd  rax, ecx
0x18001ba62  cmp     byte ptr [rax+rdx], 78h ; 'x'
0x18001ba66  jz      short loc_18001BA79
0x18001ba68  inc     ecx
0x18001ba6a  jmp     short loc_18001BA5A
0x18001ba6c  test    cs:Microsoft_Windows_RPCEnableBits, 8
0x18001ba73  jnz     loc_18001BC6C
0x18001ba79  mov     r12d, 0C002100Eh
0x18001ba7f  call    cs:__imp_GetCurrentThreadId
0x18001ba85  cmp     cs:dword_1800F9624, 0
0x18001ba8c  mov     r13d, 3
0x18001ba92  mov     ecx, eax
0x18001ba94  mov     dword ptr [rsp+1E0h+var_188], eax
0x18001ba98  mov     rax, [rsp+1E0h+var_198]
0x18001ba9d  mov     [rbp+0E0h+var_100], r13d
0x18001baa1  mov     dword ptr [rbp+0E0h+var_E8], 4
0x18001baa8  mov     word ptr [rbp+0E0h+var_E0], r15w
0x18001baad  mov     edx, [rax]
0x18001baaf  mov     eax, [rdi+54h]
0x18001bab2  mov     dword ptr [rsp+1E0h+var_190], eax
0x18001bab6  mov     [rbp+0E0h+var_F8], eax
0x18001bab9  mov     eax, [rsi+48h]
0x18001babc  mov     dword ptr [rsp+1E0h+var_198], eax
0x18001bac0  mov     dword ptr [rbp+0E0h+var_C8], eax
0x18001bac3  mov     dword ptr [rsp+1E0h+var_180], edx
0x18001bac7  mov     dword ptr [rbp+0E0h+var_D0], r13d
0x18001bacb  mov     dword ptr [rbp+0E0h+var_B8], r13d
0x18001bacf  mov     dword ptr [rbp+0E0h+var_B0], ecx
0x18001bad2  jz      short loc_18001BAFD
0x18001bad4  xor     ecx, ecx
0x18001bad6  lea     r8, ?EtwEventSubjectFilter@?1??LogEventToEtw@@YAXEE_J00@Z@4QBEB; "HbBr"
0x18001badd  cmp     ecx, 4
0x18001bae0  jnb     short loc_18001BAF0
0x18001bae2  movsxd  rax, ecx
0x18001bae5  cmp     byte ptr [rax+r8], 49h ; 'I'
0x18001baea  jz      short loc_18001BAFD
0x18001baec  inc     ecx
0x18001baee  jmp     short loc_18001BADD
0x18001baf0  test    cs:Microsoft_Windows_RPCEnableBits, 8
0x18001baf7  jnz     loc_18001BD11
0x18001bafd  mov     ecx, 4; unsigned int
0x18001bb02  call    ?AllocateExtendedErrorInfoRecord@@YAPEAUtagExtendedErrorInfo@@K@Z; AllocateExtendedErrorInfoRecord(ulong)
0x18001bb07  mov     r14, rax
0x18001bb0a  test    rax, rax
0x18001bb0d  jz      loc_18001BDC0
0x18001bb13  mov     rcx, rax; struct tagExtendedErrorInfo *
0x18001bb16  call    ?InitializePrivateEEInfo@@YAXPEAUtagExtendedErrorInfo@@@Z; InitializePrivateEEInfo(tagExtendedErrorInfo *)
0x18001bb1b  movsd   xmm0, [rbp+0E0h+var_F4]
0x18001bb20  mov     eax, 1
0x18001bb25  mov     [r14+38h], ax
0x18001bb2a  mov     rcx, r14; struct tagExtendedErrorInfo *
0x18001bb2d  mov     [r14+30h], eax
0x18001bb31  mov     eax, dword ptr [rsp+1E0h+var_180]
0x18001bb35  mov     [r14+34h], eax
0x18001bb39  mov     eax, [rbp+0E0h+var_FC]
0x18001bb3c  mov     [r14+44h], eax
0x18001bb40  mov     eax, dword ptr [rsp+1E0h+var_190]
0x18001bb44  mov     [r14+48h], eax
0x18001bb48  mov     eax, [rbp+0E0h+var_EC]
0x18001bb4b  movsd   qword ptr [r14+4Ch], xmm0
0x18001bb51  movsd   xmm0, [rbp+0E0h+var_E0+2]
0x18001bb56  mov     [r14+54h], eax
0x18001bb5a  mov     eax, dword ptr [rbp+0E0h+var_E8+4]
0x18001bb5d  mov     [r14+40h], r13d
0x18001bb61  mov     dword ptr [r14+58h], 4
0x18001bb69  mov     [r14+5Ch], eax
0x18001bb6d  mov     eax, [rbp+0E0h+var_D6]
0x18001bb70  mov     [r14+60h], r15w
0x18001bb75  movsd   qword ptr [r14+62h], xmm0
0x18001bb7b  movsd   xmm0, [rbp+0E0h+var_C8+4]
0x18001bb80  mov     [r14+6Ah], eax
0x18001bb84  movzx   eax, [rbp+0E0h+var_D2]
0x18001bb88  mov     [r14+6Eh], ax
0x18001bb8d  mov     eax, dword ptr [rbp+0E0h+var_D0+4]
0x18001bb90  mov     [r14+70h], r13d
0x18001bb94  mov     [r14+74h], eax
0x18001bb98  mov     eax, dword ptr [rsp+1E0h+var_198]
0x18001bb9c  mov     [r14+78h], eax
0x18001bba0  mov     eax, [rbp+0E0h+var_BC]
0x18001bba3  movsd   qword ptr [r14+7Ch], xmm0
0x18001bba9  movsd   xmm0, [rbp+0E0h+var_B0+4]
0x18001bbae  mov     [r14+84h], eax
0x18001bbb5  mov     eax, dword ptr [rbp+0E0h+var_B8+4]
0x18001bbb8  mov     [r14+88h], r13d
0x18001bbbf  mov     [r14+8Ch], eax
0x18001bbc6  mov     eax, dword ptr [rsp+1E0h+var_188]
0x18001bbca  mov     [r14+90h], eax
0x18001bbd1  mov     eax, [rbp+0E0h+var_A4]
0x18001bbd4  movsd   qword ptr [r14+94h], xmm0
  ... truncated ...
```
