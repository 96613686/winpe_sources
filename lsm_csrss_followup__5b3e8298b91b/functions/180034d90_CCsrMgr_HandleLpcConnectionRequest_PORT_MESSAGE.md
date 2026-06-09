# CCsrMgr::HandleLpcConnectionRequest(_PORT_MESSAGE *)

- ea: `0x180034d90`
- end: `0x1800351ac`
- name: `?HandleLpcConnectionRequest@CCsrMgr@@AEAAXPEAU_PORT_MESSAGE@@@Z`
- size: `1052`
- prototype: `void(CCsrMgr *__hidden this, struct _PORT_MESSAGE *)`
- caller_count: `1`
- callee_count: `18`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800470a0`

## callees

- `0x180002c4c`
- `0x1800074c0`
- `0x180008f64`
- `0x18000f260`
- `0x180010fb0`
- `0x18001ce00`
- `0x18001cec0`
- `0x18001f474`
- `0x180024364`
- `0x180025890`
- `0x1800267c4`
- `0x180027a38`
- `0x18002d7ac`
- `0x18002dc8c`
- `0x180034d90`
- `0x18004b86c`
- `0x18006fc58`
- `0x180097010`

## import_xrefs

- `ntdll!NtAlpcAcceptConnectPort` at `0x18003514e`
- `ntdll!NtAlpcAcceptConnectPort` at `0x18003514e`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x180034e68`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x180034e68`

## string_xrefs

- `0x180034fca`: `CompleteConnection failed`
- `0x180035053`: `CsrPipe::NotifyCompleteConnect failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
void __fastcall CCsrMgr::HandleLpcConnectionRequest(void **this, struct _PORT_MESSAGE *a2, int a3, int a4)
{
  signed int v6; // edi
  CCsrPipe *v7; // rbx
  int v8; // r14d
  int v9; // ebx
  CCsrPipe *v10; // rax
  int v11; // eax
  int v12; // r8d
  int v13; // r9d
  int v14; // ecx
  int v15; // r8d
  int v16; // r9d
  int v17; // ecx
  int v18; // r8d
  int v19; // r9d
  int v20; // [rsp+40h] [rbp-19h]
  const char *v21; // [rsp+50h] [rbp-9h] BYREF
  CCsrPipe *v22; // [rsp+58h] [rbp-1h] BYREF
  CCsrPipe *v23; // [rsp+60h] [rbp+7h] BYREF
  _QWORD v24[2]; // [rsp+68h] [rbp+Fh] BYREF
  _QWORD v25[2]; // [rsp+78h] [rbp+1Fh] BYREF
  _QWORD v26[5]; // [rsp+88h] [rbp+2Fh] BYREF
  __int64 Length; // [rsp+C8h] [rbp+6Fh] BYREF
  DWORD pSessionId; // [rsp+D0h] [rbp+77h] BYREF
  const char *v29; // [rsp+D8h] [rbp+7Fh] BYREF

  v6 = -2147467263;
  v26[0] = 0;
  pSessionId = -1;
  v7 = 0;
  v22 = 0;
  LODWORD(v29) = 0;
  if ( a2->u1.s1.DataLength != 16 )
  {
    if ( (unsigned int)dword_1800DA020 > 2 )
    {
      LOWORD(Length) = a2->u1.s1.DataLength;
      v21 = "Bad CONNECTINFO length";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<2>>(
        (_DWORD)this,
        (unsigned int)byte_1800C5DED,
        a3,
        a4,
        (__int64)&v21,
        (__int64)&Length);
    }
LABEL_7:
    v8 = 0;
    goto LABEL_28;
  }
  v8 = 1;
  if ( a2[1].u1.Length != 1 )
  {
    LODWORD(a2[1].DoNotUseThisField) = 1;
    if ( (unsigned int)dword_1800DA020 > 2 )
    {
      Length = a2[1].u1.Length;
      v21 = "Bad Version";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
        (_DWORD)this,
        (unsigned int)byte_1800C5DB9,
        a3,
        a4,
        (__int64)&v21,
        (__int64)&Length);
    }
    goto LABEL_7;
  }
  ProcessIdToSessionId(LODWORD(a2->DoNotUseThisField), &pSessionId);
  CAutoExclusiveLock::CAutoExclusiveLock((CAutoExclusiveLock *)v24, (struct CResource *)(this + 199));
  CAutoSharedLock::CAutoSharedLock((CAutoSharedLock *)v25, (struct CResource *)(this + 215));
  v9 = SmartArray<CCsrPipe,long>::GetAt(this + 212, pSessionId, &v22);
  v6 = v9 == 0 ? 0x80070057 : 0;
  LODWORD(Length) = v6;
  CAutoLock::Unlock((CAutoLock *)v25);
  if ( v9 )
  {
    v7 = v22;
    if ( v22 )
    {
      if ( *((_DWORD *)v22 + 416) )
      {
        v21 = 0;
        v10 = (CCsrPipe *)operator new(0x750u, (const struct std::nothrow_t *)&std::nothrow);
        v25[0] = v10;
        if ( v10 )
        {
          v10 = CCsrPipe::CCsrPipe(v10, v7, (int *)&Length);
          v6 = Length;
        }
        SmartPtr<IWinlogonNotify>::operator=(&v21, v10);
        if ( !v21 )
        {
          v6 = -2147024882;
          LODWORD(a2[1].DoNotUseThisField) = -1073741801;
          SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(&v21);
          CAutoLock::Unlock((CAutoLock *)v24);
          goto LABEL_33;
        }
        if ( v6 < 0 )
        {
          LODWORD(a2[1].DoNotUseThisField) = -1073741823;
          SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(&v21);
          CAutoLock::Unlock((CAutoLock *)v24);
          goto LABEL_33;
        }
        SmartPtr<IWinlogonNotify>::operator=(&v22, v21);
        SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(&v21);
        v7 = v22;
      }
      (*(void (__fastcall **)(CCsrPipe *))(*(_QWORD *)v7 + 8LL))(v7);
      v11 = CCsrPipe::CompleteConnection(v7, this[228], a2, (struct _WINSTATIONAPI_CONNECT_INFO *)a2, (int *)&v29);
      v6 = v11;
      if ( v11 < 0 )
      {
        if ( (unsigned int)dword_1800DA020 > 2 )
        {
          LODWORD(Length) = v11;
          v21 = "CompleteConnection failed";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
            dword_1800DA020,
            (unsigned int)byte_1800C5D89,
            v12,
            v13,
            (__int64)&v21,
            (__int64)&Length);
        }
        v8 = 0;
        if ( !*((_DWORD *)v7 + 416) )
        {
          _DbgPrintMessage(8, "Pipe not connected");
          (*(void (__fastcall **)(CCsrPipe *))(*(_QWORD *)v7 + 16LL))(v7);
          CAutoLock::Unlock((CAutoLock *)v24);
          goto LABEL_30;
        }
      }
      CAutoLock::Unlock((CAutoLock *)v24);
      v6 = CCsrPipe::NotifyCompleteConnect(v7);
      if ( v6 < 0 )
      {
        if ( (unsigned int)dword_1800DA020 > 2 )
        {
          LODWORD(Length) = v6;
          v21 = "CsrPipe::NotifyCompleteConnect failed";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
            v14,
            (unsigned int)byte_1800C5D59,
            v15,
            v16,
            (__int64)&v21,
            (__int64)&Length);
        }
        LODWORD(a2[1].DoNotUseThisField) = -1073741790;
        v8 = 0;
        CCsrPipe::OnConnectionClosed(v7);
      }
      CAutoLock::Unlock((CAutoLock *)v24);
LABEL_28:
      if ( (unsigned int)dword_1800DA020 > 4 )
      {
        LODWORD(Length) = v6;
        v23 = v7;
        v24[0] = (int)pSessionId;
        LODWORD(v21) = v8;
        v25[0] = "LPC Connection Handled";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
          (_DWORD)this,
          (unsigned int)word_1800C5D0A,
          a3,
          a4,
          (__int64)v25,
          (__int64)&v21,
          (__int64)v24,
          (__int64)&v23,
          (__int64)&Length);
      }
LABEL_30:
      if ( (_DWORD)v29 )
        goto LABEL_35;
      goto LABEL_33;
    }
  }
  LODWORD(a2[1].DoNotUseThisField) = -1073741072;
  CAutoLock::Unlock((CAutoLock *)v24);
LABEL_33:
  LOBYTE(v20) = 0;
  NtAlpcAcceptConnectPort(v26, this[228], 0, 0, 0, 0, a2, 0, v20);
  if ( (unsigned int)dword_1800DA020 > 2 )
  {
    LODWORD(Length) = v6;
    v29 = "Connection rejected";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v17,
      (unsigned int)word_1800C5CDA,
      v18,
      v19,
      (__int64)&v29,
      (__int64)&Length);
  }
LABEL_35:
  SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(&v22);
}

```

## disassembly

```asm
0x180034d90  mov     [rsp-8+arg_0], rbx
0x180034d95  push    rbp
0x180034d96  push    rsi
0x180034d97  push    rdi
0x180034d98  push    r14
0x180034d9a  push    r15
0x180034d9c  lea     rbp, [rsp-37h]
0x180034da1  sub     rsp, 90h
0x180034da8  mov     rsi, rdx
0x180034dab  mov     r15, rcx
0x180034dae  mov     edi, 80004001h
0x180034db3  mov     [rbp+57h+var_28], 0
0x180034dbb  mov     [rbp+57h+pSessionId], 0FFFFFFFFh
0x180034dc2  xor     ebx, ebx
0x180034dc4  mov     [rbp+57h+var_58], rbx
0x180034dc8  mov     dword ptr [rbp+57h+arg_18], ebx
0x180034dcb  cmp     word ptr [rdx], 10h
0x180034dcf  jz      short loc_180034E0E
0x180034dd1  mov     eax, cs:dword_1800DA020
0x180034dd7  cmp     eax, 2
0x180034dda  jbe     short loc_180034E59
0x180034ddc  movzx   eax, word ptr [rdx]
0x180034ddf  mov     word ptr [rbp+57h+arg_8], ax
0x180034de3  lea     rax, aBadConnectinfo; "Bad CONNECTINFO length"
0x180034dea  mov     [rbp+57h+var_60], rax
0x180034dee  lea     rax, [rbp+57h+arg_8]
0x180034df2  mov     [rsp+0B0h+var_88], rax
0x180034df7  lea     rax, [rbp+57h+var_60]
0x180034dfb  mov     [rsp+0B0h+var_90], rax
0x180034e00  lea     rdx, byte_1800C5DED
0x180034e07  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$01@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$01@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<2>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<2> const &)
0x180034e0c  jmp     short loc_180034E59
0x180034e0e  mov     r14d, 1
0x180034e14  cmp     [rdx+28h], r14d
0x180034e18  jz      short loc_180034E61
0x180034e1a  mov     [rdx+30h], r14d
0x180034e1e  mov     eax, cs:dword_1800DA020
0x180034e24  cmp     eax, 2
0x180034e27  jbe     short loc_180034E59
0x180034e29  mov     eax, [rdx+28h]
0x180034e2c  mov     [rbp+57h+arg_8], rax
0x180034e30  lea     rax, aBadVersion; "Bad Version"
0x180034e37  mov     [rbp+57h+var_60], rax
0x180034e3b  lea     rax, [rbp+57h+arg_8]
0x180034e3f  mov     [rsp+0B0h+var_88], rax
0x180034e44  lea     rax, [rbp+57h+var_60]
0x180034e48  mov     [rsp+0B0h+var_90], rax
0x180034e4d  lea     rdx, byte_1800C5DB9
0x180034e54  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &)
0x180034e59  xor     r14d, r14d
0x180034e5c  jmp     loc_180035099
0x180034e61  lea     rdx, [rbp+57h+pSessionId]; pSessionId
0x180034e65  mov     ecx, [rsi+8]; dwProcessId
0x180034e68  call    cs:__imp_ProcessIdToSessionId
0x180034e6e  lea     rdx, [r15+638h]; struct CResource *
0x180034e75  lea     rcx, [rbp+57h+var_48]; this
0x180034e79  call    ??0CAutoExclusiveLock@@QEAA@AEAVCResource@@@Z; CAutoExclusiveLock::CAutoExclusiveLock(CResource &)
0x180034e7e  nop
0x180034e7f  lea     rdx, [r15+6B8h]; struct CResource *
0x180034e86  lea     rcx, [rbp+57h+var_38]; this
0x180034e8a  call    ??0CAutoSharedLock@@QEAA@AEAVCResource@@@Z; CAutoSharedLock::CAutoSharedLock(CResource &)
0x180034e8f  nop
0x180034e90  lea     rcx, [r15+6A0h]
0x180034e97  lea     r8, [rbp+57h+var_58]
0x180034e9b  mov     edx, [rbp+57h+pSessionId]
0x180034e9e  call    ?GetAt@?$SmartArray@VCCsrPipe@@J@@QEAAHJPEAPEAVCCsrPipe@@@Z; SmartArray<CCsrPipe,long>::GetAt(long,CCsrPipe * *)
0x180034ea3  mov     ebx, eax
0x180034ea5  neg     eax
0x180034ea7  sbb     edi, edi
0x180034ea9  not     edi
0x180034eab  and     edi, 80070057h
0x180034eb1  mov     dword ptr [rbp+57h+arg_8], edi
0x180034eb4  lea     rcx, [rbp+57h+var_38]; this
0x180034eb8  call    ?Unlock@CAutoLock@@QEAAXXZ; CAutoLock::Unlock(void)
0x180034ebd  nop
0x180034ebe  test    ebx, ebx
0x180034ec0  jz      loc_180035107
0x180034ec6  mov     rbx, [rbp+57h+var_58]
0x180034eca  test    rbx, rbx
0x180034ecd  jz      loc_180035107
0x180034ed3  cmp     dword ptr [rbx+680h], 0
0x180034eda  jz      loc_180034F89
0x180034ee0  mov     [rbp+57h+var_60], 0
0x180034ee8  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180034eef  mov     ecx, 750h; unsigned __int64
0x180034ef4  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180034ef9  mov     [rbp+57h+var_38], rax
0x180034efd  test    rax, rax
0x180034f00  jz      short loc_180034F14
0x180034f02  lea     r8, [rbp+57h+arg_8]; int *
0x180034f06  mov     rdx, rbx; struct CCsrPipe *
0x180034f09  mov     rcx, rax; this
0x180034f0c  call    ??0CCsrPipe@@QEAA@PEAV0@PEAJ@Z; CCsrPipe::CCsrPipe(CCsrPipe *,long *)
0x180034f11  mov     edi, dword ptr [rbp+57h+arg_8]
0x180034f14  mov     rdx, rax
0x180034f17  lea     rcx, [rbp+57h+var_60]
0x180034f1b  call    ??4?$SmartPtr@VIWinlogonNotify@@@@QEAAAEAV0@PEAVIWinlogonNotify@@@Z; SmartPtr<IWinlogonNotify>::operator=(IWinlogonNotify *)
0x180034f20  mov     rdx, [rbp+57h+var_60]
0x180034f24  test    rdx, rdx
0x180034f27  jnz     short loc_180034F4E
0x180034f29  mov     edi, 8007000Eh
0x180034f2e  mov     dword ptr [rsi+30h], 0C0000017h
0x180034f35  lea     rcx, [rbp+57h+var_60]
0x180034f39  call    ??1?$SmartPtr@UITSEventDispatcher@@@@QEAA@XZ; SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(void)
0x180034f3e  nop
0x180034f3f  lea     rcx, [rbp+57h+var_48]; this
0x180034f43  call    ?Unlock@CAutoLock@@QEAAXXZ; CAutoLock::Unlock(void)
0x180034f48  nop
0x180034f49  jmp     loc_180035118
0x180034f4e  test    edi, edi
0x180034f50  jns     short loc_180034F72
0x180034f52  mov     dword ptr [rsi+30h], 0C0000001h
0x180034f59  lea     rcx, [rbp+57h+var_60]
0x180034f5d  call    ??1?$SmartPtr@UITSEventDispatcher@@@@QEAA@XZ; SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(void)
0x180034f62  nop
0x180034f63  lea     rcx, [rbp+57h+var_48]; this
0x180034f67  call    ?Unlock@CAutoLock@@QEAAXXZ; CAutoLock::Unlock(void)
0x180034f6c  nop
0x180034f6d  jmp     loc_180035118
0x180034f72  lea     rcx, [rbp+57h+var_58]
0x180034f76  call    ??4?$SmartPtr@VIWinlogonNotify@@@@QEAAAEAV0@PEAVIWinlogonNotify@@@Z; SmartPtr<IWinlogonNotify>::operator=(IWinlogonNotify *)
0x180034f7b  nop
0x180034f7c  lea     rcx, [rbp+57h+var_60]
0x180034f80  call    ??1?$SmartPtr@UITSEventDispatcher@@@@QEAA@XZ; SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(void)
0x180034f85  mov     rbx, [rbp+57h+var_58]
0x180034f89  mov     rax, [rbx]
0x180034f8c  mov     rcx, rbx
0x180034f8f  mov     rax, [rax+8]
0x180034f93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034f98  lea     rax, [rbp+57h+arg_18]
0x180034f9c  mov     [rsp+0B0h+var_90], rax; int *
0x180034fa1  mov     r9, rsi; struct _WINSTATIONAPI_CONNECT_INFO *
0x180034fa4  mov     r8, rsi; struct _PORT_MESSAGE *
0x180034fa7  mov     rdx, [r15+720h]; void *
0x180034fae  mov     rcx, rbx; this
0x180034fb1  call    ?CompleteConnection@CCsrPipe@@QEAAJPEAXPEAU_PORT_MESSAGE@@PEAU_WINSTATIONAPI_CONNECT_INFO@@PEAH@Z; CCsrPipe::CompleteConnection(void *,_PORT_MESSAGE *,_WINSTATIONAPI_CONNECT_INFO *,int *)
0x180034fb6  mov     edi, eax
0x180034fb8  test    eax, eax
0x180034fba  jns     short loc_18003502E
0x180034fbc  mov     ecx, cs:dword_1800DA020
0x180034fc2  cmp     ecx, 2
0x180034fc5  jbe     short loc_180034FF3
0x180034fc7  mov     dword ptr [rbp+57h+arg_8], eax
0x180034fca  lea     rax, aCompleteconnec; "CompleteConnection failed"
0x180034fd1  mov     [rbp+57h+var_60], rax
0x180034fd5  lea     rax, [rbp+57h+arg_8]
0x180034fd9  mov     [rsp+0B0h+var_88], rax
0x180034fde  lea     rax, [rbp+57h+var_60]
0x180034fe2  mov     [rsp+0B0h+var_90], rax
0x180034fe7  lea     rdx, byte_1800C5D89
0x180034fee  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180034ff3  xor     r14d, r14d
0x180034ff6  cmp     [rbx+680h], r14d
0x180034ffd  jnz     short loc_18003502E
0x180034fff  lea     rdx, aPipeNotConnect; "Pipe not connected"
0x180035006  lea     ecx, [r14+8]; int
0x18003500a  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18003500f  mov     rax, [rbx]
0x180035012  mov     rcx, rbx
0x180035015  mov     rax, [rax+10h]
0x180035019  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003501e  nop
0x18003501f  lea     rcx, [rbp+57h+var_48]; this
0x180035023  call    ?Unlock@CAutoLock@@QEAAXXZ; CAutoLock::Unlock(void)
0x180035028  nop
0x180035029  jmp     loc_1800350FB
0x18003502e  lea     rcx, [rbp+57h+var_48]; this
0x180035032  call    ?Unlock@CAutoLock@@QEAAXXZ; CAutoLock::Unlock(void)
0x180035037  mov     rcx, rbx; this
0x18003503a  call    ?NotifyCompleteConnect@CCsrPipe@@QEAAJXZ; CCsrPipe::NotifyCompleteConnect(void)
0x18003503f  mov     edi, eax
0x180035041  test    eax, eax
0x180035043  jns     short loc_18003508F
0x180035045  mov     eax, cs:dword_1800DA020
0x18003504b  cmp     eax, 2
0x18003504e  jbe     short loc_18003507C
0x180035050  mov     dword ptr [rbp+57h+arg_8], edi
0x180035053  lea     rax, aCsrpipeNotifyc; "CsrPipe::NotifyCompleteConnect failed"
0x18003505a  mov     [rbp+57h+var_60], rax
0x18003505e  lea     rax, [rbp+57h+arg_8]
0x180035062  mov     [rsp+0B0h+var_88], rax
0x180035067  lea     rax, [rbp+57h+var_60]
0x18003506b  mov     [rsp+0B0h+var_90], rax
0x180035070  lea     rdx, byte_1800C5D59
0x180035077  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18003507c  mov     dword ptr [rsi+30h], 0C0000022h
0x180035083  xor     r14d, r14d
0x180035086  mov     rcx, rbx; this
0x180035089  call    ?OnConnectionClosed@CCsrPipe@@QEAAJXZ; CCsrPipe::OnConnectionClosed(void)
0x18003508e  nop
0x18003508f  lea     rcx, [rbp+57h+var_48]; this
0x180035093  call    ?Unlock@CAutoLock@@QEAAXXZ; CAutoLock::Unlock(void)
0x180035098  nop
0x180035099  mov     eax, cs:dword_1800DA020
0x18003509f  cmp     eax, 4
0x1800350a2  jbe     short loc_1800350FB
0x1800350a4  mov     dword ptr [rbp+57h+arg_8], edi
0x1800350a7  mov     [rbp+57h+var_50], rbx
0x1800350ab  movsxd  rax, [rbp+57h+pSessionId]
0x1800350af  mov     [rbp+57h+var_48], rax
0x1800350b3  mov     dword ptr [rbp+57h+var_60], r14d
0x1800350b7  lea     rax, aLpcConnectionH; "LPC Connection Handled"
0x1800350be  mov     [rbp+57h+var_38], rax
0x1800350c2  lea     rax, [rbp+57h+arg_8]
0x1800350c6  mov     qword ptr [rsp+0B0h+var_70], rax
0x1800350cb  lea     rax, [rbp+57h+var_50]
0x1800350cf  mov     [rsp+0B0h+var_78], rax
0x1800350d4  lea     rax, [rbp+57h+var_48]
0x1800350d8  mov     [rsp+0B0h+var_80], rax
0x1800350dd  lea     rax, [rbp+57h+var_60]
0x1800350e1  mov     [rsp+0B0h+var_88], rax
0x1800350e6  lea     rax, [rbp+57h+var_38]
0x1800350ea  mov     [rsp+0B0h+var_90], rax
0x1800350ef  lea     rdx, word_1800C5D0A
0x1800350f6  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$07@@U3@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$07@@54@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x1800350fb  cmp     dword ptr [rbp+57h+arg_18], 0
0x1800350ff  jnz     loc_18003518C
0x180035105  jmp     short loc_180035118
0x180035107  mov     dword ptr [rsi+30h], 0C00002F0h
0x18003510e  lea     rcx, [rbp+57h+var_48]; this
0x180035112  call    ?Unlock@CAutoLock@@QEAAXXZ; CAutoLock::Unlock(void)
0x180035117  nop
0x180035118  mov     byte ptr [rsp+0B0h+var_70], 0
0x18003511d  mov     [rsp+0B0h+var_78], 0
0x180035126  mov     [rsp+0B0h+var_80], rsi
0x18003512b  mov     [rsp+0B0h+var_88], 0
0x180035134  mov     [rsp+0B0h+var_90], 0
0x18003513d  xor     r9d, r9d
0x180035140  xor     r8d, r8d
0x180035143  mov     rdx, [r15+720h]
0x18003514a  lea     rcx, [rbp+57h+var_28]
0x18003514e  call    cs:__imp_NtAlpcAcceptConnectPort
0x180035154  mov     eax, cs:dword_1800DA020
0x18003515a  cmp     eax, 2
0x18003515d  jbe     short loc_18003518C
0x18003515f  mov     dword ptr [rbp+57h+arg_8], edi
0x180035162  lea     rax, aConnectionReje; "Connection rejected"
0x180035169  mov     [rbp+57h+arg_18], rax
0x18003516d  lea     rax, [rbp+57h+arg_8]
0x180035171  mov     [rsp+0B0h+var_88], rax
0x180035176  lea     rax, [rbp+57h+arg_18]
0x18003517a  mov     [rsp+0B0h+var_90], rax
0x18003517f  lea     rdx, word_1800C5CDA
0x180035186  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18003518b  nop
0x18003518c  lea     rcx, [rbp+57h+var_58]
0x180035190  call    ??1?$SmartPtr@UITSEventDispatcher@@@@QEAA@XZ; SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(void)
0x180035195  mov     rbx, [rsp+0B0h+arg_0]
0x18003519d  add     rsp, 90h
0x1800351a4  pop     r15
0x1800351a6  pop     r14
0x1800351a8  pop     rdi
0x1800351a9  pop     rsi
0x1800351aa  pop     rbp
0x1800351ab  retn
```
