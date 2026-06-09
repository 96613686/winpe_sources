# CCsrMgr::HandleLpcConnectionRequest(_PORT_MESSAGE *)

- ea: `0x180036f14`
- end: `0x18003733d`
- name: `?HandleLpcConnectionRequest@CCsrMgr@@AEAAXPEAU_PORT_MESSAGE@@@Z`
- size: `1065`
- prototype: `void(CCsrMgr *__hidden this, struct _PORT_MESSAGE *)`
- caller_count: `1`
- callee_count: `18`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18004a170`

## callees

- `0x180002c64`
- `0x1800077a0`
- `0x18000c684`
- `0x1800129d0`
- `0x180012e04`
- `0x180014b20`
- `0x18001d170`
- `0x180021874`
- `0x180026198`
- `0x18002772c`
- `0x1800288ac`
- `0x180029c00`
- `0x18002f368`
- `0x18002fccc`
- `0x180036f14`
- `0x18004ec5c`
- `0x180073c98`
- `0x18009c010`

## import_xrefs

- `ntdll!NtAlpcAcceptConnectPort` at `0x1800372d8`
- `ntdll!NtAlpcAcceptConnectPort` at `0x1800372d8`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x180036fec`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x180036fec`

## string_xrefs

- `0x180037154`: `CompleteConnection failed`
- `0x1800371dd`: `CsrPipe::NotifyCompleteConnect failed`

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
    if ( (unsigned int)dword_1800DF020 > 2 )
    {
      LOWORD(Length) = a2->u1.s1.DataLength;
      v21 = "Bad CONNECTINFO length";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<2>>(
        (_DWORD)this,
        (unsigned int)byte_1800CAF75,
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
    if ( (unsigned int)dword_1800DF020 > 2 )
    {
      Length = a2[1].u1.Length;
      v21 = "Bad Version";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
        (_DWORD)this,
        (unsigned int)byte_1800CAF41,
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
        if ( (unsigned int)dword_1800DF020 > 2 )
        {
          LODWORD(Length) = v11;
          v21 = "CompleteConnection failed";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
            dword_1800DF020,
            (unsigned int)byte_1800CAF11,
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
        if ( (unsigned int)dword_1800DF020 > 2 )
        {
          LODWORD(Length) = v6;
          v21 = "CsrPipe::NotifyCompleteConnect failed";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
            v14,
            (unsigned int)byte_1800CAEE1,
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
      if ( (unsigned int)dword_1800DF020 > 4 )
      {
        LODWORD(Length) = v6;
        v23 = v7;
        v24[0] = (int)pSessionId;
        LODWORD(v21) = v8;
        v25[0] = "LPC Connection Handled";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
          (_DWORD)this,
          (unsigned int)word_1800CAE92,
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
  if ( (unsigned int)dword_1800DF020 > 2 )
  {
    LODWORD(Length) = v6;
    v29 = "Connection rejected";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v17,
      (unsigned int)word_1800CAE62,
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
0x180036f14  mov     [rsp-8+arg_0], rbx
0x180036f19  push    rbp
0x180036f1a  push    rsi
0x180036f1b  push    rdi
0x180036f1c  push    r14
0x180036f1e  push    r15
0x180036f20  lea     rbp, [rsp-37h]
0x180036f25  sub     rsp, 90h
0x180036f2c  mov     rsi, rdx
0x180036f2f  mov     r15, rcx
0x180036f32  mov     edi, 80004001h
0x180036f37  mov     [rbp+57h+var_28], 0
0x180036f3f  mov     [rbp+57h+pSessionId], 0FFFFFFFFh
0x180036f46  xor     ebx, ebx
0x180036f48  mov     [rbp+57h+var_58], rbx
0x180036f4c  mov     dword ptr [rbp+57h+arg_18], ebx
0x180036f4f  cmp     word ptr [rdx], 10h
0x180036f53  jz      short loc_180036F92
0x180036f55  mov     eax, cs:dword_1800DF020
0x180036f5b  cmp     eax, 2
0x180036f5e  jbe     short loc_180036FDD
0x180036f60  movzx   eax, word ptr [rdx]
0x180036f63  mov     word ptr [rbp+57h+arg_8], ax
0x180036f67  lea     rax, aBadConnectinfo; "Bad CONNECTINFO length"
0x180036f6e  mov     [rbp+57h+var_60], rax
0x180036f72  lea     rax, [rbp+57h+arg_8]
0x180036f76  mov     [rsp+0B0h+var_88], rax
0x180036f7b  lea     rax, [rbp+57h+var_60]
0x180036f7f  mov     [rsp+0B0h+var_90], rax
0x180036f84  lea     rdx, byte_1800CAF75
0x180036f8b  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$01@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$01@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<2>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<2> const &)
0x180036f90  jmp     short loc_180036FDD
0x180036f92  mov     r14d, 1
0x180036f98  cmp     [rdx+28h], r14d
0x180036f9c  jz      short loc_180036FE5
0x180036f9e  mov     [rdx+30h], r14d
0x180036fa2  mov     eax, cs:dword_1800DF020
0x180036fa8  cmp     eax, 2
0x180036fab  jbe     short loc_180036FDD
0x180036fad  mov     eax, [rdx+28h]
0x180036fb0  mov     [rbp+57h+arg_8], rax
0x180036fb4  lea     rax, aBadVersion; "Bad Version"
0x180036fbb  mov     [rbp+57h+var_60], rax
0x180036fbf  lea     rax, [rbp+57h+arg_8]
0x180036fc3  mov     [rsp+0B0h+var_88], rax
0x180036fc8  lea     rax, [rbp+57h+var_60]
0x180036fcc  mov     [rsp+0B0h+var_90], rax
0x180036fd1  lea     rdx, byte_1800CAF41
0x180036fd8  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &)
0x180036fdd  xor     r14d, r14d
0x180036fe0  jmp     loc_180037223
0x180036fe5  lea     rdx, [rbp+57h+pSessionId]; pSessionId
0x180036fe9  mov     ecx, [rsi+8]; dwProcessId
0x180036fec  call    cs:__imp_ProcessIdToSessionId
0x180036ff3  nop     dword ptr [rax+rax+00h]
0x180036ff8  lea     rdx, [r15+638h]; struct CResource *
0x180036fff  lea     rcx, [rbp+57h+var_48]; this
0x180037003  call    ??0CAutoExclusiveLock@@QEAA@AEAVCResource@@@Z; CAutoExclusiveLock::CAutoExclusiveLock(CResource &)
0x180037008  nop
0x180037009  lea     rdx, [r15+6B8h]; struct CResource *
0x180037010  lea     rcx, [rbp+57h+var_38]; this
0x180037014  call    ??0CAutoSharedLock@@QEAA@AEAVCResource@@@Z; CAutoSharedLock::CAutoSharedLock(CResource &)
0x180037019  nop
0x18003701a  lea     rcx, [r15+6A0h]
0x180037021  lea     r8, [rbp+57h+var_58]
0x180037025  mov     edx, [rbp+57h+pSessionId]
0x180037028  call    ?GetAt@?$SmartArray@VCCsrPipe@@J@@QEAAHJPEAPEAVCCsrPipe@@@Z; SmartArray<CCsrPipe,long>::GetAt(long,CCsrPipe * *)
0x18003702d  mov     ebx, eax
0x18003702f  neg     eax
0x180037031  sbb     edi, edi
0x180037033  not     edi
0x180037035  and     edi, 80070057h
0x18003703b  mov     dword ptr [rbp+57h+arg_8], edi
0x18003703e  lea     rcx, [rbp+57h+var_38]; this
0x180037042  call    ?Unlock@CAutoLock@@QEAAXXZ; CAutoLock::Unlock(void)
0x180037047  nop
0x180037048  test    ebx, ebx
0x18003704a  jz      loc_180037291
0x180037050  mov     rbx, [rbp+57h+var_58]
0x180037054  test    rbx, rbx
0x180037057  jz      loc_180037291
0x18003705d  cmp     dword ptr [rbx+680h], 0
0x180037064  jz      loc_180037113
0x18003706a  mov     [rbp+57h+var_60], 0
0x180037072  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180037079  mov     ecx, 750h; unsigned __int64
0x18003707e  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180037083  mov     [rbp+57h+var_38], rax
0x180037087  test    rax, rax
0x18003708a  jz      short loc_18003709E
0x18003708c  lea     r8, [rbp+57h+arg_8]; int *
0x180037090  mov     rdx, rbx; struct CCsrPipe *
0x180037093  mov     rcx, rax; this
0x180037096  call    ??0CCsrPipe@@QEAA@PEAV0@PEAJ@Z; CCsrPipe::CCsrPipe(CCsrPipe *,long *)
0x18003709b  mov     edi, dword ptr [rbp+57h+arg_8]
0x18003709e  mov     rdx, rax
0x1800370a1  lea     rcx, [rbp+57h+var_60]
0x1800370a5  call    ??4?$SmartPtr@VIWinlogonNotify@@@@QEAAAEAV0@PEAVIWinlogonNotify@@@Z; SmartPtr<IWinlogonNotify>::operator=(IWinlogonNotify *)
0x1800370aa  mov     rdx, [rbp+57h+var_60]
0x1800370ae  test    rdx, rdx
0x1800370b1  jnz     short loc_1800370D8
0x1800370b3  mov     edi, 8007000Eh
0x1800370b8  mov     dword ptr [rsi+30h], 0C0000017h
0x1800370bf  lea     rcx, [rbp+57h+var_60]
0x1800370c3  call    ??1?$SmartPtr@UITSEventDispatcher@@@@QEAA@XZ; SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(void)
0x1800370c8  nop
0x1800370c9  lea     rcx, [rbp+57h+var_48]; this
0x1800370cd  call    ?Unlock@CAutoLock@@QEAAXXZ; CAutoLock::Unlock(void)
0x1800370d2  nop
0x1800370d3  jmp     loc_1800372A2
0x1800370d8  test    edi, edi
0x1800370da  jns     short loc_1800370FC
0x1800370dc  mov     dword ptr [rsi+30h], 0C0000001h
0x1800370e3  lea     rcx, [rbp+57h+var_60]
0x1800370e7  call    ??1?$SmartPtr@UITSEventDispatcher@@@@QEAA@XZ; SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(void)
0x1800370ec  nop
0x1800370ed  lea     rcx, [rbp+57h+var_48]; this
0x1800370f1  call    ?Unlock@CAutoLock@@QEAAXXZ; CAutoLock::Unlock(void)
0x1800370f6  nop
0x1800370f7  jmp     loc_1800372A2
0x1800370fc  lea     rcx, [rbp+57h+var_58]
0x180037100  call    ??4?$SmartPtr@VIWinlogonNotify@@@@QEAAAEAV0@PEAVIWinlogonNotify@@@Z; SmartPtr<IWinlogonNotify>::operator=(IWinlogonNotify *)
0x180037105  nop
0x180037106  lea     rcx, [rbp+57h+var_60]
0x18003710a  call    ??1?$SmartPtr@UITSEventDispatcher@@@@QEAA@XZ; SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(void)
0x18003710f  mov     rbx, [rbp+57h+var_58]
0x180037113  mov     rax, [rbx]
0x180037116  mov     rcx, rbx
0x180037119  mov     rax, [rax+8]
0x18003711d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037122  lea     rax, [rbp+57h+arg_18]
0x180037126  mov     [rsp+0B0h+var_90], rax; int *
0x18003712b  mov     r9, rsi; struct _WINSTATIONAPI_CONNECT_INFO *
0x18003712e  mov     r8, rsi; struct _PORT_MESSAGE *
0x180037131  mov     rdx, [r15+720h]; void *
0x180037138  mov     rcx, rbx; this
0x18003713b  call    ?CompleteConnection@CCsrPipe@@QEAAJPEAXPEAU_PORT_MESSAGE@@PEAU_WINSTATIONAPI_CONNECT_INFO@@PEAH@Z; CCsrPipe::CompleteConnection(void *,_PORT_MESSAGE *,_WINSTATIONAPI_CONNECT_INFO *,int *)
0x180037140  mov     edi, eax
0x180037142  test    eax, eax
0x180037144  jns     short loc_1800371B8
0x180037146  mov     ecx, cs:dword_1800DF020
0x18003714c  cmp     ecx, 2
0x18003714f  jbe     short loc_18003717D
0x180037151  mov     dword ptr [rbp+57h+arg_8], eax
0x180037154  lea     rax, aCompleteconnec; "CompleteConnection failed"
0x18003715b  mov     [rbp+57h+var_60], rax
0x18003715f  lea     rax, [rbp+57h+arg_8]
0x180037163  mov     [rsp+0B0h+var_88], rax
0x180037168  lea     rax, [rbp+57h+var_60]
0x18003716c  mov     [rsp+0B0h+var_90], rax
0x180037171  lea     rdx, byte_1800CAF11
0x180037178  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18003717d  xor     r14d, r14d
0x180037180  cmp     [rbx+680h], r14d
0x180037187  jnz     short loc_1800371B8
0x180037189  lea     rdx, aPipeNotConnect; "Pipe not connected"
0x180037190  lea     ecx, [r14+8]; int
0x180037194  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180037199  mov     rax, [rbx]
0x18003719c  mov     rcx, rbx
0x18003719f  mov     rax, [rax+10h]
0x1800371a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800371a8  nop
0x1800371a9  lea     rcx, [rbp+57h+var_48]; this
0x1800371ad  call    ?Unlock@CAutoLock@@QEAAXXZ; CAutoLock::Unlock(void)
0x1800371b2  nop
0x1800371b3  jmp     loc_180037285
0x1800371b8  lea     rcx, [rbp+57h+var_48]; this
0x1800371bc  call    ?Unlock@CAutoLock@@QEAAXXZ; CAutoLock::Unlock(void)
0x1800371c1  mov     rcx, rbx; this
0x1800371c4  call    ?NotifyCompleteConnect@CCsrPipe@@QEAAJXZ; CCsrPipe::NotifyCompleteConnect(void)
0x1800371c9  mov     edi, eax
0x1800371cb  test    eax, eax
0x1800371cd  jns     short loc_180037219
0x1800371cf  mov     eax, cs:dword_1800DF020
0x1800371d5  cmp     eax, 2
0x1800371d8  jbe     short loc_180037206
0x1800371da  mov     dword ptr [rbp+57h+arg_8], edi
0x1800371dd  lea     rax, aCsrpipeNotifyc; "CsrPipe::NotifyCompleteConnect failed"
0x1800371e4  mov     [rbp+57h+var_60], rax
0x1800371e8  lea     rax, [rbp+57h+arg_8]
0x1800371ec  mov     [rsp+0B0h+var_88], rax
0x1800371f1  lea     rax, [rbp+57h+var_60]
0x1800371f5  mov     [rsp+0B0h+var_90], rax
0x1800371fa  lea     rdx, byte_1800CAEE1
0x180037201  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180037206  mov     dword ptr [rsi+30h], 0C0000022h
0x18003720d  xor     r14d, r14d
0x180037210  mov     rcx, rbx; this
0x180037213  call    ?OnConnectionClosed@CCsrPipe@@QEAAJXZ; CCsrPipe::OnConnectionClosed(void)
0x180037218  nop
0x180037219  lea     rcx, [rbp+57h+var_48]; this
0x18003721d  call    ?Unlock@CAutoLock@@QEAAXXZ; CAutoLock::Unlock(void)
0x180037222  nop
0x180037223  mov     eax, cs:dword_1800DF020
0x180037229  cmp     eax, 4
0x18003722c  jbe     short loc_180037285
0x18003722e  mov     dword ptr [rbp+57h+arg_8], edi
0x180037231  mov     [rbp+57h+var_50], rbx
0x180037235  movsxd  rax, [rbp+57h+pSessionId]
0x180037239  mov     [rbp+57h+var_48], rax
0x18003723d  mov     dword ptr [rbp+57h+var_60], r14d
0x180037241  lea     rax, aLpcConnectionH; "LPC Connection Handled"
0x180037248  mov     [rbp+57h+var_38], rax
0x18003724c  lea     rax, [rbp+57h+arg_8]
0x180037250  mov     qword ptr [rsp+0B0h+var_70], rax
0x180037255  lea     rax, [rbp+57h+var_50]
0x180037259  mov     [rsp+0B0h+var_78], rax
0x18003725e  lea     rax, [rbp+57h+var_48]
0x180037262  mov     [rsp+0B0h+var_80], rax
0x180037267  lea     rax, [rbp+57h+var_60]
0x18003726b  mov     [rsp+0B0h+var_88], rax
0x180037270  lea     rax, [rbp+57h+var_38]
0x180037274  mov     [rsp+0B0h+var_90], rax
0x180037279  lea     rdx, word_1800CAE92
0x180037280  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$07@@U3@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$07@@54@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x180037285  cmp     dword ptr [rbp+57h+arg_18], 0
0x180037289  jnz     loc_18003731C
0x18003728f  jmp     short loc_1800372A2
0x180037291  mov     dword ptr [rsi+30h], 0C00002F0h
0x180037298  lea     rcx, [rbp+57h+var_48]; this
0x18003729c  call    ?Unlock@CAutoLock@@QEAAXXZ; CAutoLock::Unlock(void)
0x1800372a1  nop
0x1800372a2  mov     byte ptr [rsp+0B0h+var_70], 0
0x1800372a7  mov     [rsp+0B0h+var_78], 0
0x1800372b0  mov     [rsp+0B0h+var_80], rsi
0x1800372b5  mov     [rsp+0B0h+var_88], 0
0x1800372be  mov     [rsp+0B0h+var_90], 0
0x1800372c7  xor     r9d, r9d
0x1800372ca  xor     r8d, r8d
0x1800372cd  mov     rdx, [r15+720h]
0x1800372d4  lea     rcx, [rbp+57h+var_28]
0x1800372d8  call    cs:__imp_NtAlpcAcceptConnectPort
0x1800372df  nop     dword ptr [rax+rax+00h]
0x1800372e4  mov     eax, cs:dword_1800DF020
0x1800372ea  cmp     eax, 2
0x1800372ed  jbe     short loc_18003731C
0x1800372ef  mov     dword ptr [rbp+57h+arg_8], edi
0x1800372f2  lea     rax, aConnectionReje; "Connection rejected"
0x1800372f9  mov     [rbp+57h+arg_18], rax
0x1800372fd  lea     rax, [rbp+57h+arg_8]
0x180037301  mov     [rsp+0B0h+var_88], rax
0x180037306  lea     rax, [rbp+57h+arg_18]
0x18003730a  mov     [rsp+0B0h+var_90], rax
0x18003730f  lea     rdx, word_1800CAE62
0x180037316  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18003731b  nop
0x18003731c  lea     rcx, [rbp+57h+var_58]
0x180037320  call    ??1?$SmartPtr@UITSEventDispatcher@@@@QEAA@XZ; SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(void)
0x180037325  mov     rbx, [rsp+0B0h+arg_0]
0x18003732d  add     rsp, 90h
0x180037334  pop     r15
0x180037336  pop     r14
0x180037338  pop     rdi
0x180037339  pop     rsi
0x18003733a  pop     rbp
0x18003733b  retn
```
