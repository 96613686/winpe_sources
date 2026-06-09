# CCsrPipe::OnGetSMCommand(_WINSTATION_APIMSG *)

- ea: `0x1800351b4`
- end: `0x180035577`
- name: `?OnGetSMCommand@CCsrPipe@@QEAAJPEAU_WINSTATION_APIMSG@@@Z`
- size: `963`
- prototype: `int(CCsrPipe *__hidden this, struct _WINSTATION_APIMSG *)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800470a0`

## callees

- `0x180010fb0`
- `0x18001ce00`
- `0x180022d58`
- `0x180025070`
- `0x180025168`
- `0x1800267c4`
- `0x1800268c8`
- `0x1800351b4`
- `0x18004b830`
- `0x18009404c`
- `0x180097010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180035358`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180035358`

## string_xrefs

- `0x18003520f`: `OnGetSMCommand wait for reply`
- `0x18003525c`: `OnGetSMCommand looking up response by MessageId`
- `0x1800352df`: `OnGetSMCommand, Reply received for command`
- `0x180035372`: `OnGetSMCommand, no cmd entry for this message`
- `0x18003538e`: `OnGetSMCommand, cmd queue empty for this message`
- `0x1800353e4`: `OnGetSMCommand, sending next cmd`
- `0x18003549b`: `OnGetCMCommand is cleaning up pCommand`
- `0x180035503`: `OnGetSMCommand queue empty port`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CCsrPipe::OnGetSMCommand(CCsrPipe *this, struct _WINSTATION_APIMSG *a2)
{
  const char * near **v4; // rcx
  int v5; // r8d
  int v6; // r9d
  _DWORD *v7; // r15
  _QWORD *v8; // rsi
  _QWORD *v9; // rsi
  int v10; // ebx
  int v11; // r8d
  int v12; // r9d
  __int64 v13; // rax
  _QWORD *v14; // rcx
  const char *v15; // rax
  int *v16; // rdx
  _BYTE *v17; // rbx
  int v18; // ecx
  int v19; // r8d
  int v20; // r9d
  __int64 v21; // rax
  _QWORD *v22; // rcx
  __int64 v24; // [rsp+50h] [rbp-28h] BYREF
  const char *v25; // [rsp+58h] [rbp-20h] BYREF
  _BYTE v26[24]; // [rsp+60h] [rbp-18h] BYREF
  unsigned __int64 v27; // [rsp+B0h] [rbp+38h] BYREF
  const char *v28; // [rsp+B8h] [rbp+40h] BYREF
  const char *v29; // [rsp+C0h] [rbp+48h] BYREF
  const char * near *v30; // [rsp+C8h] [rbp+50h] BYREF

  CAutoExclusiveLock::CAutoExclusiveLock((CAutoExclusiveLock *)v26, (CCsrPipe *)((char *)this + 1688));
  if ( !*((_BYTE *)a2 + 48) )
    goto LABEL_18;
  v7 = (_DWORD *)((char *)a2 + 40);
  v4 = &CSR_LPC_NAME;
  if ( (unsigned int)dword_1800DA020 > 4 )
  {
    v27 = (unsigned int)*v7;
    v28 = (const char *)(&CSR_LPC_NAME)[*((int *)a2 + 11)];
    v29 = "OnGetSMCommand wait for reply";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
      (unsigned int)&CSR_LPC_NAME,
      (unsigned int)&dword_1800C5C94,
      v5,
      v6,
      (__int64)&v29,
      (__int64)&v28,
      (__int64)&v27);
  }
  v8 = (_QWORD *)((char *)this + 1792);
  if ( (_QWORD *)*v8 == v8 )
  {
    if ( (unsigned int)dword_1800DA020 <= 3 )
      goto LABEL_18;
    v27 = (unsigned int)*v7;
    v15 = "OnGetSMCommand, cmd queue empty for this message";
    v16 = (int *)&byte_1800C5BA7;
    goto LABEL_17;
  }
  if ( (unsigned int)dword_1800DA020 > 4 )
  {
    v27 = (unsigned __int64)"OnGetSMCommand looking up response by MessageId";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
      (_DWORD)v4,
      (unsigned int)qword_1800C5C70,
      v5,
      v6,
      (__int64)&v27);
  }
  v9 = (_QWORD *)*v8;
  v4 = (const char * near **)(v9 + 3);
  if ( *((_DWORD *)v9 + 16) != *v7 )
  {
    if ( (unsigned int)dword_1800DA020 <= 4 )
      goto LABEL_18;
    v27 = (unsigned int)*v7;
    v15 = "OnGetSMCommand, no cmd entry for this message";
    v16 = &dword_1800C5BDC;
LABEL_17:
    v28 = v15;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
      (_DWORD)v4,
      (_DWORD)v16,
      v5,
      v6,
      (__int64)&v28,
      (__int64)&v27);
    goto LABEL_18;
  }
  v10 = *((_DWORD *)v9 + 17);
  memcpy_0(v4, a2, 0x4070u);
  *((_DWORD *)v9 + 17) = v10;
  if ( (unsigned int)dword_1800DA020 > 4 )
  {
    v27 = (unsigned __int64)v9;
    v28 = (const char *)*((int *)a2 + 13);
    v29 = (const char *)(unsigned int)*v7;
    v30 = (&CSR_LPC_NAME)[*((int *)v9 + 17)];
    v24 = *((int *)this + 398);
    v25 = "OnGetSMCommand, Reply received for command";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
      (unsigned int)&CSR_LPC_NAME,
      (unsigned int)byte_1800C5C11,
      v11,
      v12,
      (__int64)&v25,
      (__int64)&v24,
      (__int64)&v30,
      (__int64)&v29,
      (__int64)&v28,
      (__int64)&v27);
  }
  v13 = *v9;
  if ( *(_QWORD **)(*v9 + 8LL) != v9 )
    goto LABEL_27;
  v14 = (_QWORD *)v9[1];
  if ( (_QWORD *)*v14 != v9 )
    goto LABEL_27;
  *v14 = v13;
  *(_QWORD *)(v13 + 8) = v14;
  *v9 = 0;
  SetEvent((HANDLE)v9[2]);
LABEL_18:
  v17 = (_BYTE *)*((_QWORD *)this + 224);
  if ( v17 == (char *)this + 1792 )
  {
    if ( (unsigned int)dword_1800DA020 > 4 )
    {
      v27 = *((_QWORD *)this + 232);
      v28 = "OnGetSMCommand queue empty port";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
        (_DWORD)v4,
        (unsigned int)byte_1800C5B09,
        v5,
        v6,
        (__int64)&v28,
        (__int64)&v27);
    }
    *((_OWORD *)this + 113) = *(_OWORD *)a2;
    *((_OWORD *)this + 114) = *((_OWORD *)a2 + 1);
    *((_QWORD *)this + 230) = *((_QWORD *)a2 + 4);
    *((_DWORD *)this + 462) = 1;
  }
  else
  {
    if ( (unsigned int)dword_1800DA020 > 4 )
    {
      v27 = *((_QWORD *)this + 224);
      v28 = (const char *)*((int *)this + 398);
      v29 = "OnGetSMCommand, sending next cmd";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
        (_DWORD)v4,
        (unsigned int)&word_1800C5B6E,
        v5,
        v6,
        (__int64)&v29,
        (__int64)&v28,
        (__int64)&v27);
    }
    *(_OWORD *)(v17 + 24) = *(_OWORD *)a2;
    *(_OWORD *)(v17 + 40) = *((_OWORD *)a2 + 1);
    *((_QWORD *)v17 + 7) = *((_QWORD *)a2 + 4);
    (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD))(**((_QWORD **)this + 209) + 16LL))(
      *((_QWORD *)this + 209),
      *((_QWORD *)this + 232),
      0);
    if ( !v17[72] )
    {
      if ( (unsigned int)dword_1800DA020 > 4 )
      {
        v27 = (unsigned __int64)v17;
        v28 = "OnGetCMCommand is cleaning up pCommand";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
          v18,
          (unsigned int)qword_1800C5B40,
          v19,
          v20,
          (__int64)&v28,
          (__int64)&v27);
      }
      v21 = *(_QWORD *)v17;
      if ( *(_BYTE **)(*(_QWORD *)v17 + 8LL) == v17 )
      {
        v22 = (_QWORD *)*((_QWORD *)v17 + 1);
        if ( (_BYTE *)*v22 == v17 )
        {
          *v22 = v21;
          *(_QWORD *)(v21 + 8) = v22;
          operator delete(v17, (const struct std::nothrow_t *)0x4088);
          goto LABEL_31;
        }
      }
LABEL_27:
      __fastfail(3u);
    }
  }
LABEL_31:
  CAutoLock::Unlock((CAutoLock *)v26);
  return 268435715;
}

```

## disassembly

```asm
0x1800351b4  push    rbp
0x1800351b6  push    rbx
0x1800351b7  push    rsi
0x1800351b8  push    rdi
0x1800351b9  push    r14
0x1800351bb  push    r15
0x1800351bd  mov     rbp, rsp
0x1800351c0  sub     rsp, 78h
0x1800351c4  mov     r14, rdx
0x1800351c7  mov     rdi, rcx
0x1800351ca  lea     rdx, [rcx+698h]; struct CResource *
0x1800351d1  lea     rcx, [rbp+var_18]; this
0x1800351d5  call    ??0CAutoExclusiveLock@@QEAA@AEAVCResource@@@Z; CAutoExclusiveLock::CAutoExclusiveLock(CResource &)
0x1800351da  nop
0x1800351db  cmp     byte ptr [r14+30h], 0
0x1800351e0  jz      loc_1800353B7
0x1800351e6  mov     eax, cs:dword_1800DA020
0x1800351ec  lea     r15, [r14+28h]
0x1800351f0  lea     rcx, ?CSR_LPC_NAME@@3PAPEBDA; char const * near * CSR_LPC_NAME
0x1800351f7  cmp     eax, 4
0x1800351fa  jbe     short loc_180035241
0x1800351fc  mov     eax, [r15]
0x1800351ff  mov     [rbp+arg_0], rax
0x180035203  movsxd  rax, dword ptr [r14+2Ch]
0x180035207  mov     rax, [rcx+rax*8]
0x18003520b  mov     [rbp+arg_8], rax
0x18003520f  lea     rax, aOngetsmcommand_1; "OnGetSMCommand wait for reply"
0x180035216  mov     [rbp+arg_10], rax
0x18003521a  lea     rax, [rbp+arg_0]
0x18003521e  mov     [rsp+78h+var_48], rax
0x180035223  lea     rax, [rbp+arg_8]
0x180035227  mov     [rsp+78h+var_50], rax
0x18003522c  lea     rax, [rbp+arg_10]
0x180035230  mov     [rsp+78h+var_58], rax
0x180035235  lea     rdx, dword_1800C5C94
0x18003523c  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &)
0x180035241  lea     rsi, [rdi+700h]
0x180035248  cmp     [rsi], rsi
0x18003524b  mov     eax, cs:dword_1800DA020
0x180035251  jz      loc_180035382
0x180035257  cmp     eax, 4
0x18003525a  jbe     short loc_18003527C
0x18003525c  lea     rax, aOngetsmcommand_4; "OnGetSMCommand looking up response by M"...
0x180035263  mov     [rbp+arg_0], rax
0x180035267  lea     rax, [rbp+arg_0]
0x18003526b  mov     [rsp+78h+var_58], rax
0x180035270  lea     rdx, qword_1800C5C70
0x180035277  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18003527c  mov     rsi, [rsi]
0x18003527f  lea     rcx, [rsi+18h]; void *
0x180035283  mov     eax, [r15]
0x180035286  cmp     [rcx+28h], eax
0x180035289  jnz     loc_180035360
0x18003528f  mov     ebx, [rsi+44h]
0x180035292  mov     r8d, 4070h; Size
0x180035298  mov     rdx, r14; Src
0x18003529b  call    memcpy_0
0x1800352a0  mov     [rsi+44h], ebx
0x1800352a3  mov     eax, cs:dword_1800DA020
0x1800352a9  cmp     eax, 4
0x1800352ac  jbe     short loc_18003532C
0x1800352ae  mov     [rbp+arg_0], rsi
0x1800352b2  movsxd  rax, dword ptr [r14+34h]
0x1800352b6  mov     [rbp+arg_8], rax
0x1800352ba  mov     eax, [r15]
0x1800352bd  mov     [rbp+arg_10], rax
0x1800352c1  movsxd  rax, dword ptr [rsi+44h]
0x1800352c5  lea     rcx, ?CSR_LPC_NAME@@3PAPEBDA; char const * near * CSR_LPC_NAME
0x1800352cc  mov     rax, [rcx+rax*8]
0x1800352d0  mov     [rbp+arg_18], rax
0x1800352d4  movsxd  rax, dword ptr [rdi+638h]
0x1800352db  mov     [rbp+var_28], rax
0x1800352df  lea     rax, aOngetsmcommand_3; "OnGetSMCommand, Reply received for comm"...
0x1800352e6  mov     [rbp+var_20], rax
0x1800352ea  lea     rax, [rbp+arg_0]
0x1800352ee  mov     [rsp+78h+var_30], rax
0x1800352f3  lea     rax, [rbp+arg_8]
0x1800352f7  mov     [rsp+78h+var_38], rax
0x1800352fc  lea     rax, [rbp+arg_10]
0x180035300  mov     [rsp+78h+var_40], rax
0x180035305  lea     rax, [rbp+arg_18]
0x180035309  mov     [rsp+78h+var_48], rax
0x18003530e  lea     rax, [rbp+var_28]
0x180035312  mov     [rsp+78h+var_50], rax
0x180035317  lea     rax, [rbp+var_20]
0x18003531b  mov     [rsp+78h+var_58], rax
0x180035320  lea     rdx, byte_1800C5C11
0x180035327  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U1@U2@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@3444@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &)
0x18003532c  mov     rax, [rsi]
0x18003532f  cmp     [rax+8], rsi
0x180035333  jnz     loc_1800354EC
0x180035339  mov     rcx, [rsi+8]
0x18003533d  cmp     [rcx], rsi
0x180035340  jnz     loc_1800354EC
0x180035346  mov     [rcx], rax
0x180035349  mov     [rax+8], rcx
0x18003534d  mov     qword ptr [rsi], 0
0x180035354  mov     rcx, [rsi+10h]; hEvent
0x180035358  call    cs:__imp_SetEvent
0x18003535e  jmp     short loc_1800353B7
0x180035360  mov     eax, cs:dword_1800DA020
0x180035366  cmp     eax, 4
0x180035369  jbe     short loc_1800353B7
0x18003536b  mov     eax, [r15]
0x18003536e  mov     [rbp+arg_0], rax
0x180035372  lea     rax, aOngetsmcommand_5; "OnGetSMCommand, no cmd entry for this m"...
0x180035379  lea     rdx, dword_1800C5BDC
0x180035380  jmp     short loc_18003539C
0x180035382  cmp     eax, 3
0x180035385  jbe     short loc_1800353B7
0x180035387  mov     eax, [r15]
0x18003538a  mov     [rbp+arg_0], rax
0x18003538e  lea     rax, aOngetsmcommand_2; "OnGetSMCommand, cmd queue empty for thi"...
0x180035395  lea     rdx, byte_1800C5BA7
0x18003539c  mov     [rbp+arg_8], rax
0x1800353a0  lea     rax, [rbp+arg_0]
0x1800353a4  mov     [rsp+78h+var_50], rax
0x1800353a9  lea     rax, [rbp+arg_8]
0x1800353ad  mov     [rsp+78h+var_58], rax
0x1800353b2  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &)
0x1800353b7  lea     rax, [rdi+700h]
0x1800353be  mov     rbx, [rax]
0x1800353c1  cmp     rbx, rax
0x1800353c4  mov     eax, cs:dword_1800DA020
0x1800353ca  jz      loc_1800354F3
0x1800353d0  cmp     eax, 4
0x1800353d3  jbe     short loc_180035416
0x1800353d5  mov     [rbp+arg_0], rbx
0x1800353d9  movsxd  rax, dword ptr [rdi+638h]
0x1800353e0  mov     [rbp+arg_8], rax
0x1800353e4  lea     rax, aOngetsmcommand; "OnGetSMCommand, sending next cmd"
0x1800353eb  mov     [rbp+arg_10], rax
0x1800353ef  lea     rax, [rbp+arg_0]
0x1800353f3  mov     [rsp+78h+var_48], rax
0x1800353f8  lea     rax, [rbp+arg_8]
0x1800353fc  mov     [rsp+78h+var_50], rax
0x180035401  lea     rax, [rbp+arg_10]
0x180035405  mov     [rsp+78h+var_58], rax
0x18003540a  lea     rdx, word_1800C5B6E
0x180035411  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &)
0x180035416  lea     r9, [rbx+18h]
0x18003541a  movups  xmm0, xmmword ptr [r14]
0x18003541e  movups  xmmword ptr [r9], xmm0
0x180035422  movups  xmm1, xmmword ptr [r14+10h]
0x180035427  movups  xmmword ptr [r9+10h], xmm1
0x18003542c  movsd   xmm0, qword ptr [r14+20h]
0x180035432  movsd   qword ptr [r9+20h], xmm0
0x180035438  mov     rcx, [rdi+688h]
0x18003543f  mov     rax, [rcx]
0x180035442  mov     [rsp+78h+var_38], 0
0x18003544b  mov     [rsp+78h+var_40], 0
0x180035454  mov     [rsp+78h+var_48], 0
0x18003545d  mov     [rsp+78h+var_50], 0
0x180035466  mov     [rsp+78h+var_58], 0
0x18003546f  xor     r8d, r8d
0x180035472  mov     rdx, [rdi+740h]
0x180035479  mov     rax, [rax+10h]
0x18003547d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035482  cmp     byte ptr [rbx+48h], 0
0x180035486  jnz     loc_18003555B
0x18003548c  mov     eax, cs:dword_1800DA020
0x180035492  cmp     eax, 4
0x180035495  jbe     short loc_1800354C4
0x180035497  mov     [rbp+arg_0], rbx
0x18003549b  lea     rax, aOngetcmcommand; "OnGetCMCommand is cleaning up pCommand"
0x1800354a2  mov     [rbp+arg_8], rax
0x1800354a6  lea     rax, [rbp+arg_0]
0x1800354aa  mov     [rsp+78h+var_50], rax
0x1800354af  lea     rax, [rbp+arg_8]
0x1800354b3  mov     [rsp+78h+var_58], rax
0x1800354b8  lea     rdx, qword_1800C5B40
0x1800354bf  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &)
0x1800354c4  mov     rax, [rbx]
0x1800354c7  cmp     [rax+8], rbx
0x1800354cb  jnz     short loc_1800354EC
0x1800354cd  mov     rcx, [rbx+8]
0x1800354d1  cmp     [rcx], rbx
0x1800354d4  jnz     short loc_1800354EC
0x1800354d6  mov     [rcx], rax
0x1800354d9  mov     [rax+8], rcx
0x1800354dd  mov     edx, 4088h; struct std::nothrow_t *
0x1800354e2  mov     rcx, rbx; void *
0x1800354e5  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800354ea  jmp     short loc_18003555B
0x1800354ec  mov     ecx, 3
0x1800354f1  int     29h; Win8: RtlFailFast(ecx)
0x1800354f3  cmp     eax, 4
0x1800354f6  jbe     short loc_18003552C
0x1800354f8  mov     rax, [rdi+740h]
0x1800354ff  mov     [rbp+arg_0], rax
0x180035503  lea     rax, aOngetsmcommand_0; "OnGetSMCommand queue empty port"
0x18003550a  mov     [rbp+arg_8], rax
0x18003550e  lea     rax, [rbp+arg_0]
0x180035512  mov     [rsp+78h+var_50], rax
0x180035517  lea     rax, [rbp+arg_8]
0x18003551b  mov     [rsp+78h+var_58], rax
0x180035520  lea     rdx, byte_1800C5B09
0x180035527  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &)
0x18003552c  movups  xmm0, xmmword ptr [r14]
0x180035530  movups  xmmword ptr [rdi+710h], xmm0
0x180035537  movups  xmm1, xmmword ptr [r14+10h]
0x18003553c  movups  xmmword ptr [rdi+720h], xmm1
0x180035543  movsd   xmm0, qword ptr [r14+20h]
0x180035549  movsd   qword ptr [rdi+730h], xmm0
0x180035551  mov     dword ptr [rdi+738h], 1
0x18003555b  lea     rcx, [rbp+var_18]; this
0x18003555f  call    ?Unlock@CAutoLock@@QEAAXXZ; CAutoLock::Unlock(void)
0x180035564  nop
0x180035565  mov     eax, 10000103h
0x18003556a  add     rsp, 78h
0x18003556e  pop     r15
0x180035570  pop     r14
0x180035572  pop     rdi
0x180035573  pop     rsi
0x180035574  pop     rbx
0x180035575  pop     rbp
0x180035576  retn
```
