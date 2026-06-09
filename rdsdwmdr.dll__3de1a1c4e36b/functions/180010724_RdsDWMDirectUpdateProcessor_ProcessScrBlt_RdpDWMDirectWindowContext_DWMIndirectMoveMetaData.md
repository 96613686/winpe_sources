# RdsDWMDirectUpdateProcessor::ProcessScrBlt(RdpDWMDirectWindowContext *,_DWMIndirectMoveMetaData *)

- ea: `0x180010724`
- end: `0x18001089f`
- name: `?ProcessScrBlt@RdsDWMDirectUpdateProcessor@@IEAAJPEAVRdpDWMDirectWindowContext@@PEAU_DWMIndirectMoveMetaData@@@Z`
- size: `379`
- prototype: `int(RdsDWMDirectUpdateProcessor *__hidden this, struct RdpDWMDirectWindowContext *, struct _DWMIndirectMoveMetaData *)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x180010a30`

## callees

- `0x180001724`
- `0x180001bfc`
- `0x18000ea10`
- `0x180010724`

## string_xrefs

- `0x180010778`: `clientcore\termsrv\rdsdwmdirect\rdsdwmdrupdateprocessor.cpp`
- `0x180010841`: `clientcore\termsrv\rdsdwmdirect\rdsdwmdrupdateprocessor.cpp`
- `0x180010754`: `No target window for ScrBlt update.`
- `0x1800107d3`: `RdsDWMDirectUpdateProcessor::ProcessScrBlt`
- `0x18001081d`: `Move region call failed`

## pseudocode

```c
__int64 __fastcall RdsDWMDirectUpdateProcessor::ProcessScrBlt(
        __int64 this,
        struct RdpDWMDirectWindowContext *a2,
        struct _DWMIndirectMoveMetaData *a3,
        __int64 a4)
{
  int v6; // ebx
  __int16 *v7; // rdx
  const unsigned __int16 **v8; // rax
  const unsigned __int16 **v10; // [rsp+40h] [rbp-30h]
  const char *v11; // [rsp+50h] [rbp-20h] BYREF
  const char *v12; // [rsp+58h] [rbp-18h] BYREF
  _QWORD v13[2]; // [rsp+60h] [rbp-10h] BYREF
  __int64 v14; // [rsp+90h] [rbp+20h] BYREF
  const char *v15; // [rsp+98h] [rbp+28h] BYREF
  const char *v16; // [rsp+A8h] [rbp+38h] BYREF

  v14 = this;
  if ( a2 )
  {
    if ( (unsigned int)dword_180044008 > 5 )
    {
      v14 = *((_QWORD *)a2 + 8);
      v15 = "RdsDWMDirectUpdateProcessor::ProcessScrBlt";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
        this,
        (__int64)byte_18003AD33,
        (__int64)a3,
        a4,
        (const unsigned __int16 **)&v15,
        (__int64)&v14);
    }
    v6 = RdpDWMDirectWindowContext::MoveRegion(
           (HDC *)a2,
           *((HRGN *)a3 + 3),
           (struct tagRECT *)a3,
           (struct tagPOINT *)a3 + 2);
    if ( v6 < 0 )
    {
      this = (unsigned int)dword_180044008;
      if ( (unsigned int)dword_180044008 > 2 )
      {
        LODWORD(v14) = 899;
        v16 = "Move region call failed";
        v7 = &word_18003ACE6;
        v13[0] = "ProcessScrBlt";
        v12 = "clientcore\\termsrv\\rdsdwmdirect\\rdsdwmdrupdateprocessor.cpp";
        v11 = "Error HResult failed";
        v10 = (const unsigned __int16 **)v13;
        v8 = (const unsigned __int16 **)&v11;
        goto LABEL_9;
      }
    }
  }
  else
  {
    v6 = -2147418113;
    if ( (unsigned int)dword_180044008 > 2 )
    {
      LODWORD(v14) = 886;
      v16 = "No target window for ScrBlt update.";
      v7 = &word_18003AD5E;
      v11 = "ProcessScrBlt";
      v12 = "clientcore\\termsrv\\rdsdwmdirect\\rdsdwmdrupdateprocessor.cpp";
      v13[0] = "Error condition failed";
      v10 = (const unsigned __int16 **)&v11;
      v8 = (const unsigned __int16 **)v13;
LABEL_9:
      LODWORD(v15) = v6;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        this,
        (__int64)v7,
        (__int64)a3,
        a4,
        v8,
        (__int64)&v15,
        (const unsigned __int16 **)&v12,
        (__int64)&v14,
        v10,
        (const unsigned __int16 **)&v16);
    }
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180010724  mov     r11, rsp
0x180010727  mov     [r11+8], rcx
0x18001072b  push    rbp
0x18001072c  push    rbx
0x18001072d  push    rdi
0x18001072e  mov     rbp, rsp
0x180010731  sub     rsp, 70h
0x180010735  mov     eax, cs:dword_180044008
0x18001073b  mov     rdi, r8
0x18001073e  mov     rbx, rdx
0x180010741  test    rdx, rdx
0x180010744  jnz     short loc_1800107BF
0x180010746  mov     ebx, 8000FFFFh
0x18001074b  cmp     eax, 2
0x18001074e  jbe     loc_180010895
0x180010754  lea     rax, aNoTargetWindow_3; "No target window for ScrBlt update."
0x18001075b  mov     dword ptr [rbp+arg_0], 376h
0x180010762  mov     [rbp+arg_18], rax
0x180010766  lea     rdx, word_18003AD5E
0x18001076d  lea     rax, aProcessscrblt; "ProcessScrBlt"
0x180010774  mov     [rbp+var_20], rax
0x180010778  lea     rax, aClientcoreTerm_2; "clientcore\\termsrv\\rdsdwmdirect\\rdsd"...
0x18001077f  mov     [rbp+var_18], rax
0x180010783  lea     rax, aErrorCondition; "Error condition failed"
0x18001078a  mov     [rbp+var_10], rax
0x18001078e  lea     rax, [rbp+arg_18]
0x180010792  mov     [r11-40h], rax
0x180010796  lea     rax, [rbp+var_20]
0x18001079a  mov     [r11-48h], rax
0x18001079e  lea     rax, [rbp+arg_0]
0x1800107a2  mov     [r11-50h], rax
0x1800107a6  lea     rax, [rbp+var_18]
0x1800107aa  mov     [r11-58h], rax
0x1800107ae  lea     rax, [rbp+arg_8]
0x1800107b2  mov     [r11-60h], rax
0x1800107b6  lea     rax, [rbp+var_10]
0x1800107ba  jmp     loc_180010888
0x1800107bf  cmp     eax, 5
0x1800107c2  jbe     short loc_1800107F5
0x1800107c4  mov     rax, [rdx+40h]
0x1800107c8  lea     rdx, byte_18003AD33
0x1800107cf  mov     [rbp+arg_0], rax
0x1800107d3  lea     rax, aRdsdwmdirectup_3; "RdsDWMDirectUpdateProcessor::ProcessScr"...
0x1800107da  mov     [rbp+arg_8], rax
0x1800107de  lea     rax, [rbp+arg_0]
0x1800107e2  mov     [rsp+70h+var_48], rax
0x1800107e7  lea     rax, [rbp+arg_8]
0x1800107eb  mov     [rsp+70h+var_50], rax
0x1800107f0  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &)
0x1800107f5  mov     rdx, [rdi+18h]; hrgn
0x1800107f9  lea     r9, [rdi+10h]; struct tagPOINT *
0x1800107fd  mov     r8, rdi; struct tagRECT *
0x180010800  mov     rcx, rbx; this
0x180010803  call    ?MoveRegion@RdpDWMDirectWindowContext@@QEAAJPEAUHRGN__@@PEAUtagRECT@@PEAUtagPOINT@@@Z; RdpDWMDirectWindowContext::MoveRegion(HRGN__ *,tagRECT *,tagPOINT *)
0x180010808  mov     ebx, eax
0x18001080a  test    eax, eax
0x18001080c  jns     loc_180010895
0x180010812  mov     ecx, cs:dword_180044008
0x180010818  cmp     ecx, 2
0x18001081b  jbe     short loc_180010895
0x18001081d  lea     rax, aMoveRegionCall; "Move region call failed"
0x180010824  mov     dword ptr [rbp+arg_0], 383h
0x18001082b  mov     [rbp+arg_18], rax
0x18001082f  lea     rdx, word_18003ACE6
0x180010836  lea     rax, aProcessscrblt; "ProcessScrBlt"
0x18001083d  mov     [rbp+var_10], rax
0x180010841  lea     rax, aClientcoreTerm_2; "clientcore\\termsrv\\rdsdwmdirect\\rdsd"...
0x180010848  mov     [rbp+var_18], rax
0x18001084c  lea     rax, aErrorHresultFa; "Error HResult failed"
0x180010853  mov     [rbp+var_20], rax
0x180010857  lea     rax, [rbp+arg_18]
0x18001085b  mov     [rsp+70h+var_28], rax
0x180010860  lea     rax, [rbp+var_10]
0x180010864  mov     [rsp+70h+var_30], rax
0x180010869  lea     rax, [rbp+arg_0]
0x18001086d  mov     [rsp+70h+var_38], rax
0x180010872  lea     rax, [rbp+var_18]
0x180010876  mov     [rsp+70h+var_40], rax
0x18001087b  lea     rax, [rbp+arg_8]
0x18001087f  mov     [rsp+70h+var_48], rax
0x180010884  lea     rax, [rbp+var_20]
0x180010888  mov     [rsp+70h+var_50], rax
0x18001088d  mov     dword ptr [rbp+arg_8], ebx
0x180010890  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x180010895  mov     eax, ebx
0x180010897  add     rsp, 70h
0x18001089b  pop     rdi
0x18001089c  pop     rbx
0x18001089d  pop     rbp
0x18001089e  retn
```
