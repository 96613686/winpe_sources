# CCsrPipe::OnGetSMCommand(_WINSTATION_APIMSG *)

- ea: `0x180037344`
- end: `0x18003770e`
- name: `?OnGetSMCommand@CCsrPipe@@QEAAJPEAU_WINSTATION_APIMSG@@@Z`
- size: `970`
- prototype: `int(CCsrPipe *__hidden this, struct _WINSTATION_APIMSG *)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18004a170`

## callees

- `0x1800129d0`
- `0x180014b20`
- `0x180026238`
- `0x18002701c`
- `0x18002712c`
- `0x1800288ac`
- `0x1800289e0`
- `0x180037344`
- `0x18004ec20`
- `0x18009959c`
- `0x18009c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800374e8`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800374e8`

## string_xrefs

- `0x18003739f`: `OnGetSMCommand wait for reply`
- `0x1800373ec`: `OnGetSMCommand looking up response by MessageId`
- `0x18003746f`: `OnGetSMCommand, Reply received for command`
- `0x180037508`: `OnGetSMCommand, no cmd entry for this message`
- `0x180037524`: `OnGetSMCommand, cmd queue empty for this message`
- `0x18003757a`: `OnGetSMCommand, sending next cmd`
- `0x180037631`: `OnGetCMCommand is cleaning up pCommand`
- `0x180037699`: `OnGetSMCommand queue empty port`

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
  if ( (unsigned int)dword_1800DF020 > 4 )
  {
    v27 = (unsigned int)*v7;
    v28 = (const char *)(&CSR_LPC_NAME)[*((int *)a2 + 11)];
    v29 = "OnGetSMCommand wait for reply";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
      (unsigned int)&CSR_LPC_NAME,
      (unsigned int)&dword_1800CAE1C,
      v5,
      v6,
      (__int64)&v29,
      (__int64)&v28,
      (__int64)&v27);
  }
  v8 = (_QWORD *)((char *)this + 1792);
  if ( (_QWORD *)*v8 == v8 )
  {
    if ( (unsigned int)dword_1800DF020 <= 3 )
      goto LABEL_18;
    v27 = (unsigned int)*v7;
    v15 = "OnGetSMCommand, cmd queue empty for this message";
    v16 = (int *)&byte_1800CAD2F;
    goto LABEL_17;
  }
  if ( (unsigned int)dword_1800DF020 > 4 )
  {
    v27 = (unsigned __int64)"OnGetSMCommand looking up response by MessageId";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
      (_DWORD)v4,
      (unsigned int)qword_1800CADF8,
      v5,
      v6,
      (__int64)&v27);
  }
  v9 = (_QWORD *)*v8;
  v4 = (const char * near **)(v9 + 3);
  if ( *((_DWORD *)v9 + 16) != *v7 )
  {
    if ( (unsigned int)dword_1800DF020 <= 4 )
      goto LABEL_18;
    v27 = (unsigned int)*v7;
    v15 = "OnGetSMCommand, no cmd entry for this message";
    v16 = &dword_1800CAD64;
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
  if ( (unsigned int)dword_1800DF020 > 4 )
  {
    v27 = (unsigned __int64)v9;
    v28 = (const char *)*((int *)a2 + 13);
    v29 = (const char *)(unsigned int)*v7;
    v30 = (&CSR_LPC_NAME)[*((int *)v9 + 17)];
    v24 = *((int *)this + 398);
    v25 = "OnGetSMCommand, Reply received for command";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
      (unsigned int)&CSR_LPC_NAME,
      (unsigned int)byte_1800CAD99,
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
    if ( (unsigned int)dword_1800DF020 > 4 )
    {
      v27 = *((_QWORD *)this + 232);
      v28 = "OnGetSMCommand queue empty port";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
        (_DWORD)v4,
        (unsigned int)byte_1800CAC91,
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
    if ( (unsigned int)dword_1800DF020 > 4 )
    {
      v27 = *((_QWORD *)this + 224);
      v28 = (const char *)*((int *)this + 398);
      v29 = "OnGetSMCommand, sending next cmd";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
        (_DWORD)v4,
        (unsigned int)&word_1800CACF6,
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
      if ( (unsigned int)dword_1800DF020 > 4 )
      {
        v27 = (unsigned __int64)v17;
        v28 = "OnGetCMCommand is cleaning up pCommand";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
          v18,
          (unsigned int)qword_1800CACC8,
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
0x180037344  push    rbp
0x180037346  push    rbx
0x180037347  push    rsi
0x180037348  push    rdi
0x180037349  push    r14
0x18003734b  push    r15
0x18003734d  mov     rbp, rsp
0x180037350  sub     rsp, 78h
0x180037354  mov     r14, rdx
0x180037357  mov     rdi, rcx
0x18003735a  lea     rdx, [rcx+698h]; struct CResource *
0x180037361  lea     rcx, [rbp+var_18]; this
0x180037365  call    ??0CAutoExclusiveLock@@QEAA@AEAVCResource@@@Z; CAutoExclusiveLock::CAutoExclusiveLock(CResource &)
0x18003736a  nop
0x18003736b  cmp     byte ptr [r14+30h], 0
0x180037370  jz      loc_18003754D
0x180037376  mov     eax, cs:dword_1800DF020
0x18003737c  lea     r15, [r14+28h]
0x180037380  lea     rcx, ?CSR_LPC_NAME@@3PAPEBDA; char const * near * CSR_LPC_NAME
0x180037387  cmp     eax, 4
0x18003738a  jbe     short loc_1800373D1
0x18003738c  mov     eax, [r15]
0x18003738f  mov     [rbp+arg_0], rax
0x180037393  movsxd  rax, dword ptr [r14+2Ch]
0x180037397  mov     rax, [rcx+rax*8]
0x18003739b  mov     [rbp+arg_8], rax
0x18003739f  lea     rax, aOngetsmcommand_1; "OnGetSMCommand wait for reply"
0x1800373a6  mov     [rbp+arg_10], rax
0x1800373aa  lea     rax, [rbp+arg_0]
0x1800373ae  mov     [rsp+78h+var_48], rax
0x1800373b3  lea     rax, [rbp+arg_8]
0x1800373b7  mov     [rsp+78h+var_50], rax
0x1800373bc  lea     rax, [rbp+arg_10]
0x1800373c0  mov     [rsp+78h+var_58], rax
0x1800373c5  lea     rdx, dword_1800CAE1C
0x1800373cc  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &)
0x1800373d1  lea     rsi, [rdi+700h]
0x1800373d8  cmp     [rsi], rsi
0x1800373db  mov     eax, cs:dword_1800DF020
0x1800373e1  jz      loc_180037518
0x1800373e7  cmp     eax, 4
0x1800373ea  jbe     short loc_18003740C
0x1800373ec  lea     rax, aOngetsmcommand_4; "OnGetSMCommand looking up response by M"...
0x1800373f3  mov     [rbp+arg_0], rax
0x1800373f7  lea     rax, [rbp+arg_0]
0x1800373fb  mov     [rsp+78h+var_58], rax
0x180037400  lea     rdx, qword_1800CADF8
0x180037407  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18003740c  mov     rsi, [rsi]
0x18003740f  lea     rcx, [rsi+18h]; void *
0x180037413  mov     eax, [r15]
0x180037416  cmp     [rcx+28h], eax
0x180037419  jnz     loc_1800374F6
0x18003741f  mov     ebx, [rsi+44h]
0x180037422  mov     r8d, 4070h; Size
0x180037428  mov     rdx, r14; Src
0x18003742b  call    memcpy_0
0x180037430  mov     [rsi+44h], ebx
0x180037433  mov     eax, cs:dword_1800DF020
0x180037439  cmp     eax, 4
0x18003743c  jbe     short loc_1800374BC
0x18003743e  mov     [rbp+arg_0], rsi
0x180037442  movsxd  rax, dword ptr [r14+34h]
0x180037446  mov     [rbp+arg_8], rax
0x18003744a  mov     eax, [r15]
0x18003744d  mov     [rbp+arg_10], rax
0x180037451  movsxd  rax, dword ptr [rsi+44h]
0x180037455  lea     rcx, ?CSR_LPC_NAME@@3PAPEBDA; char const * near * CSR_LPC_NAME
0x18003745c  mov     rax, [rcx+rax*8]
0x180037460  mov     [rbp+arg_18], rax
0x180037464  movsxd  rax, dword ptr [rdi+638h]
0x18003746b  mov     [rbp+var_28], rax
0x18003746f  lea     rax, aOngetsmcommand_3; "OnGetSMCommand, Reply received for comm"...
0x180037476  mov     [rbp+var_20], rax
0x18003747a  lea     rax, [rbp+arg_0]
0x18003747e  mov     [rsp+78h+var_30], rax
0x180037483  lea     rax, [rbp+arg_8]
0x180037487  mov     [rsp+78h+var_38], rax
0x18003748c  lea     rax, [rbp+arg_10]
0x180037490  mov     [rsp+78h+var_40], rax
0x180037495  lea     rax, [rbp+arg_18]
0x180037499  mov     [rsp+78h+var_48], rax
0x18003749e  lea     rax, [rbp+var_28]
0x1800374a2  mov     [rsp+78h+var_50], rax
0x1800374a7  lea     rax, [rbp+var_20]
0x1800374ab  mov     [rsp+78h+var_58], rax
0x1800374b0  lea     rdx, byte_1800CAD99
0x1800374b7  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U1@U2@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@3444@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &)
0x1800374bc  mov     rax, [rsi]
0x1800374bf  cmp     [rax+8], rsi
0x1800374c3  jnz     loc_180037682
0x1800374c9  mov     rcx, [rsi+8]
0x1800374cd  cmp     [rcx], rsi
0x1800374d0  jnz     loc_180037682
0x1800374d6  mov     [rcx], rax
0x1800374d9  mov     [rax+8], rcx
0x1800374dd  mov     qword ptr [rsi], 0
0x1800374e4  mov     rcx, [rsi+10h]; hEvent
0x1800374e8  call    cs:__imp_SetEvent
0x1800374ef  nop     dword ptr [rax+rax+00h]
0x1800374f4  jmp     short loc_18003754D
0x1800374f6  mov     eax, cs:dword_1800DF020
0x1800374fc  cmp     eax, 4
0x1800374ff  jbe     short loc_18003754D
0x180037501  mov     eax, [r15]
0x180037504  mov     [rbp+arg_0], rax
0x180037508  lea     rax, aOngetsmcommand_5; "OnGetSMCommand, no cmd entry for this m"...
0x18003750f  lea     rdx, dword_1800CAD64
0x180037516  jmp     short loc_180037532
0x180037518  cmp     eax, 3
0x18003751b  jbe     short loc_18003754D
0x18003751d  mov     eax, [r15]
0x180037520  mov     [rbp+arg_0], rax
0x180037524  lea     rax, aOngetsmcommand_2; "OnGetSMCommand, cmd queue empty for thi"...
0x18003752b  lea     rdx, byte_1800CAD2F
0x180037532  mov     [rbp+arg_8], rax
0x180037536  lea     rax, [rbp+arg_0]
0x18003753a  mov     [rsp+78h+var_50], rax
0x18003753f  lea     rax, [rbp+arg_8]
0x180037543  mov     [rsp+78h+var_58], rax
0x180037548  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &)
0x18003754d  lea     rax, [rdi+700h]
0x180037554  mov     rbx, [rax]
0x180037557  cmp     rbx, rax
0x18003755a  mov     eax, cs:dword_1800DF020
0x180037560  jz      loc_180037689
0x180037566  cmp     eax, 4
0x180037569  jbe     short loc_1800375AC
0x18003756b  mov     [rbp+arg_0], rbx
0x18003756f  movsxd  rax, dword ptr [rdi+638h]
0x180037576  mov     [rbp+arg_8], rax
0x18003757a  lea     rax, aOngetsmcommand; "OnGetSMCommand, sending next cmd"
0x180037581  mov     [rbp+arg_10], rax
0x180037585  lea     rax, [rbp+arg_0]
0x180037589  mov     [rsp+78h+var_48], rax
0x18003758e  lea     rax, [rbp+arg_8]
0x180037592  mov     [rsp+78h+var_50], rax
0x180037597  lea     rax, [rbp+arg_10]
0x18003759b  mov     [rsp+78h+var_58], rax
0x1800375a0  lea     rdx, word_1800CACF6
0x1800375a7  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &)
0x1800375ac  lea     r9, [rbx+18h]
0x1800375b0  movups  xmm0, xmmword ptr [r14]
0x1800375b4  movups  xmmword ptr [r9], xmm0
0x1800375b8  movups  xmm1, xmmword ptr [r14+10h]
0x1800375bd  movups  xmmword ptr [r9+10h], xmm1
0x1800375c2  movsd   xmm0, qword ptr [r14+20h]
0x1800375c8  movsd   qword ptr [r9+20h], xmm0
0x1800375ce  mov     rcx, [rdi+688h]
0x1800375d5  mov     rax, [rcx]
0x1800375d8  mov     [rsp+78h+var_38], 0
0x1800375e1  mov     [rsp+78h+var_40], 0
0x1800375ea  mov     [rsp+78h+var_48], 0
0x1800375f3  mov     [rsp+78h+var_50], 0
0x1800375fc  mov     [rsp+78h+var_58], 0
0x180037605  xor     r8d, r8d
0x180037608  mov     rdx, [rdi+740h]
0x18003760f  mov     rax, [rax+10h]
0x180037613  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037618  cmp     byte ptr [rbx+48h], 0
0x18003761c  jnz     loc_1800376F1
0x180037622  mov     eax, cs:dword_1800DF020
0x180037628  cmp     eax, 4
0x18003762b  jbe     short loc_18003765A
0x18003762d  mov     [rbp+arg_0], rbx
0x180037631  lea     rax, aOngetcmcommand; "OnGetCMCommand is cleaning up pCommand"
0x180037638  mov     [rbp+arg_8], rax
0x18003763c  lea     rax, [rbp+arg_0]
0x180037640  mov     [rsp+78h+var_50], rax
0x180037645  lea     rax, [rbp+arg_8]
0x180037649  mov     [rsp+78h+var_58], rax
0x18003764e  lea     rdx, qword_1800CACC8
0x180037655  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &)
0x18003765a  mov     rax, [rbx]
0x18003765d  cmp     [rax+8], rbx
0x180037661  jnz     short loc_180037682
0x180037663  mov     rcx, [rbx+8]
0x180037667  cmp     [rcx], rbx
0x18003766a  jnz     short loc_180037682
0x18003766c  mov     [rcx], rax
0x18003766f  mov     [rax+8], rcx
0x180037673  mov     edx, 4088h; struct std::nothrow_t *
0x180037678  mov     rcx, rbx; void *
0x18003767b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180037680  jmp     short loc_1800376F1
0x180037682  mov     ecx, 3
0x180037687  int     29h; Win8: RtlFailFast(ecx)
0x180037689  cmp     eax, 4
0x18003768c  jbe     short loc_1800376C2
0x18003768e  mov     rax, [rdi+740h]
0x180037695  mov     [rbp+arg_0], rax
0x180037699  lea     rax, aOngetsmcommand_0; "OnGetSMCommand queue empty port"
0x1800376a0  mov     [rbp+arg_8], rax
0x1800376a4  lea     rax, [rbp+arg_0]
0x1800376a8  mov     [rsp+78h+var_50], rax
0x1800376ad  lea     rax, [rbp+arg_8]
0x1800376b1  mov     [rsp+78h+var_58], rax
0x1800376b6  lea     rdx, byte_1800CAC91
0x1800376bd  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &)
0x1800376c2  movups  xmm0, xmmword ptr [r14]
0x1800376c6  movups  xmmword ptr [rdi+710h], xmm0
0x1800376cd  movups  xmm1, xmmword ptr [r14+10h]
0x1800376d2  movups  xmmword ptr [rdi+720h], xmm1
0x1800376d9  movsd   xmm0, qword ptr [r14+20h]
0x1800376df  movsd   qword ptr [rdi+730h], xmm0
0x1800376e7  mov     dword ptr [rdi+738h], 1
0x1800376f1  lea     rcx, [rbp+var_18]; this
0x1800376f5  call    ?Unlock@CAutoLock@@QEAAXXZ; CAutoLock::Unlock(void)
0x1800376fa  nop
0x1800376fb  mov     eax, 10000103h
0x180037700  add     rsp, 78h
0x180037704  pop     r15
0x180037706  pop     r14
0x180037708  pop     rdi
0x180037709  pop     rsi
0x18003770a  pop     rbx
0x18003770b  pop     rbp
0x18003770c  retn
```
