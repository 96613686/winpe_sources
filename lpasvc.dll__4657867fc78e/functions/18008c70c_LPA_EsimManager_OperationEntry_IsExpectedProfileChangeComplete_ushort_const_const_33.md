# LPA::EsimManager::OperationEntry::IsExpectedProfileChangeComplete(ushort const (* const)[33])

- ea: `0x18008c70c`
- end: `0x18008c8d1`
- name: `?IsExpectedProfileChangeComplete@OperationEntry@EsimManager@LPA@@QEBA_NQEAY0CB@$$CBG@Z`
- size: `453`
- prototype: `bool __fastcall(LPA::EsimManager::OperationEntry *__hidden this, const unsigned __int16 (*const)[33])`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x18008df80`

## callees

- `0x1800017c8`
- `0x1800018b4`
- `0x180003b24`
- `0x1800709e4`
- `0x180071994`
- `0x18008b68c`
- `0x18008c70c`
- `0x180095f60`

## string_xrefs

- `0x18008c7cc`: `LpaServiceEsimManager`
- `0x18008c82c`: `LpaServiceEsimManager`
- `0x18008c87a`: `LpaServiceEsimManager`
- `0x18008c7c1`: `LPA::EsimManager::OperationEntry::IsExpectedProfileChangeComplete`
- `0x18008c817`: `LPA::EsimManager::OperationEntry::IsExpectedProfileChangeComplete`
- `0x18008c864`: `LPA::EsimManager::OperationEntry::IsExpectedProfileChangeComplete`

## pseudocode

```c
char __fastcall LPA::EsimManager::OperationEntry::IsExpectedProfileChangeComplete(
        LPA::EsimManager::OperationEntry *this,
        const unsigned __int16 (*const a2)[33])
{
  char v4; // bl
  __int64 v5; // rsi
  int v6; // r8d
  int v7; // r9d
  int v8; // ecx
  LPA::EsimManager::EsimRecord *v9; // rcx
  int TrueProfileState; // ecx
  int v11; // r8d
  int v12; // r9d
  int v13; // ecx
  const char *v15; // [rsp+40h] [rbp-20h] BYREF
  __int64 v16; // [rsp+48h] [rbp-18h] BYREF
  std::_Ref_count_base *v17; // [rsp+50h] [rbp-10h]
  const unsigned __int16 *v18; // [rsp+A0h] [rbp+40h] BYREF
  const char *v19; // [rsp+B0h] [rbp+50h] BYREF
  const char *v20; // [rsp+B8h] [rbp+58h] BYREF

  if ( !*((_WORD *)this + 46) )
    return 1;
  v4 = 0;
  std::weak_ptr<LPA::Lpd::DownloadInstance>::lock((char *)this + 16, &v16);
  v5 = v16;
  if ( v16 )
  {
    LPA::EsimManager::TryFindEsimRecordByEid(v16, &v18, (const unsigned __int16 *)a2, this);
    v8 = (int)v18;
    if ( v18 == *(const unsigned __int16 **)(v5 + 208) )
    {
      if ( (unsigned int)CallbackContext > 3 )
      {
        v18 = (const unsigned __int16 *)a2;
        v20 = "LPA::EsimManager::OperationEntry::IsExpectedProfileChangeComplete";
        v19 = (const char *)this;
        v15 = "LpaServiceEsimManager";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>>(
          v8,
          (unsigned int)byte_18012CD5D,
          v6,
          v7,
          (__int64)&v15,
          (__int64)&v20,
          (__int64)&v19,
          (__int64)&v18);
      }
    }
    else
    {
      v9 = (LPA::EsimManager::EsimRecord *)*((_QWORD *)v18 + 6);
      LODWORD(v18) = 0;
      TrueProfileState = LPA::EsimManager::EsimRecord::GetTrueProfileState(
                           v9,
                           (const unsigned __int16 (*)[21])((char *)this + 92),
                           (enum LPAPROFILESTATE *)&v18);
      if ( TrueProfileState < 0 )
      {
        if ( (unsigned int)CallbackContext > 3 )
        {
          LODWORD(v18) = TrueProfileState;
          v19 = "LPA::EsimManager::OperationEntry::IsExpectedProfileChangeComplete";
          v20 = "LpaServiceEsimManager";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
            TrueProfileState,
            (unsigned int)&word_18012CDAE,
            v11,
            v12,
            (__int64)&v20,
            (__int64)&v19,
            (__int64)&v18);
        }
      }
      else
      {
        v13 = (int)v18;
        if ( (_DWORD)v18 == *((_DWORD *)this + 34) )
        {
          v4 = 1;
        }
        else if ( (unsigned int)CallbackContext > 3 )
        {
          LODWORD(v18) = *((_DWORD *)this + 34);
          v20 = "LPA::EsimManager::OperationEntry::IsExpectedProfileChangeComplete";
          v15 = "LpaServiceEsimManager";
          LODWORD(v19) = v13;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            v13,
            (unsigned int)byte_18012CDEB,
            v11,
            v12,
            (__int64)&v15,
            (__int64)&v20,
            (__int64)&v19,
            (__int64)&v18);
        }
      }
    }
  }
  if ( v17 )
    std::_Ref_count_base::_Decref(v17);
  return v4;
}

```

## disassembly

```asm
0x18008c70c  push    rbp
0x18008c70e  push    rbx
0x18008c70f  push    rsi
0x18008c710  push    rdi
0x18008c711  push    r12
0x18008c713  push    r14
0x18008c715  push    r15
0x18008c717  mov     rbp, rsp
0x18008c71a  sub     rsp, 60h
0x18008c71e  xor     r12d, r12d
0x18008c721  mov     r15, rdx
0x18008c724  mov     rdi, rcx
0x18008c727  cmp     [rcx+5Ch], r12w
0x18008c72c  jnz     short loc_18008C735
0x18008c72e  mov     bl, 1
0x18008c730  jmp     loc_18008C8C0
0x18008c735  add     rcx, 10h
0x18008c739  lea     rdx, [rbp+var_18]
0x18008c73d  mov     bl, r12b
0x18008c740  call    ?lock@?$weak_ptr@VDownloadInstance@Lpd@LPA@@@std@@QEBA?AV?$shared_ptr@VDownloadInstance@Lpd@LPA@@@2@XZ; std::weak_ptr<LPA::Lpd::DownloadInstance>::lock(void)
0x18008c745  mov     rsi, [rbp+var_18]
0x18008c749  test    rsi, rsi
0x18008c74c  jz      loc_18008C8B2
0x18008c752  mov     r9, rdi
0x18008c755  lea     rdx, [rbp+arg_0]
0x18008c759  mov     r8, r15
0x18008c75c  mov     rcx, rsi
0x18008c75f  call    ?TryFindEsimRecordByEid@EsimManager@LPA@@AEAA?AV?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@V?$unique_ptr@VEsimRecord@EsimManager@LPA@@U?$default_delete@VEsimRecord@EsimManager@LPA@@@std@@@std@@@std@@@std@@@std@@@std@@PEAY0CB@$$CBGAEBU_GUID@@@Z; LPA::EsimManager::TryFindEsimRecordByEid(ushort const (*)[33],_GUID const &)
0x18008c764  mov     rcx, [rbp+arg_0]
0x18008c768  cmp     rcx, [rsi+0D0h]
0x18008c76f  jz      loc_18008C859
0x18008c775  mov     rcx, [rcx+30h]; this
0x18008c779  lea     r8, [rbp+arg_0]; enum LPAPROFILESTATE *
0x18008c77d  lea     rdx, [rdi+5Ch]; unsigned __int16 (*)[21]
0x18008c781  mov     dword ptr [rbp+arg_0], r12d
0x18008c785  call    ?GetTrueProfileState@EsimRecord@EsimManager@LPA@@QEBAJPEAY0BF@$$CBGAEAW4LPAPROFILESTATE@@@Z; LPA::EsimManager::EsimRecord::GetTrueProfileState(ushort const (*)[21],LPAPROFILESTATE &)
0x18008c78a  mov     ecx, eax
0x18008c78c  test    eax, eax
0x18008c78e  js      short loc_18008C808
0x18008c790  mov     ecx, dword ptr [rbp+arg_0]
0x18008c793  cmp     ecx, [rdi+88h]
0x18008c799  jnz     short loc_18008C7A2
0x18008c79b  mov     bl, 1
0x18008c79d  jmp     loc_18008C8B2
0x18008c7a2  mov     eax, cs:CallbackContext
0x18008c7a8  cmp     eax, 3
0x18008c7ab  jbe     loc_18008C8B2
0x18008c7b1  mov     eax, [rdi+88h]
0x18008c7b7  lea     rdx, byte_18012CDEB
0x18008c7be  mov     dword ptr [rbp+arg_0], eax
0x18008c7c1  lea     rax, aLpaEsimmanager_7; "LPA::EsimManager::OperationEntry::IsExp"...
0x18008c7c8  mov     [rbp+arg_18], rax
0x18008c7cc  lea     rax, aLpaserviceesim; "LpaServiceEsimManager"
0x18008c7d3  mov     [rbp+var_20], rax
0x18008c7d7  lea     rax, [rbp+arg_0]
0x18008c7db  mov     [rsp+60h+var_28], rax
0x18008c7e0  lea     rax, [rbp+arg_10]
0x18008c7e4  mov     [rsp+60h+var_30], rax
0x18008c7e9  lea     rax, [rbp+arg_18]
0x18008c7ed  mov     [rsp+60h+var_38], rax
0x18008c7f2  lea     rax, [rbp+var_20]
0x18008c7f6  mov     [rsp+60h+var_40], rax
0x18008c7fb  mov     dword ptr [rbp+arg_10], ecx
0x18008c7fe  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18008c803  jmp     loc_18008C8B2
0x18008c808  mov     eax, cs:CallbackContext
0x18008c80e  cmp     eax, 3
0x18008c811  jbe     loc_18008C8B2
0x18008c817  lea     rax, aLpaEsimmanager_7; "LPA::EsimManager::OperationEntry::IsExp"...
0x18008c81e  mov     dword ptr [rbp+arg_0], ecx
0x18008c821  mov     [rbp+arg_10], rax
0x18008c825  lea     rdx, word_18012CDAE
0x18008c82c  lea     rax, aLpaserviceesim; "LpaServiceEsimManager"
0x18008c833  mov     [rbp+arg_18], rax
0x18008c837  lea     rax, [rbp+arg_0]
0x18008c83b  mov     [rsp+60h+var_30], rax
0x18008c840  lea     rax, [rbp+arg_10]
0x18008c844  mov     [rsp+60h+var_38], rax
0x18008c849  lea     rax, [rbp+arg_18]
0x18008c84d  mov     [rsp+60h+var_40], rax
0x18008c852  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18008c857  jmp     short loc_18008C8B2
0x18008c859  mov     eax, cs:CallbackContext
0x18008c85f  cmp     eax, 3
0x18008c862  jbe     short loc_18008C8B2
0x18008c864  lea     rax, aLpaEsimmanager_7; "LPA::EsimManager::OperationEntry::IsExp"...
0x18008c86b  mov     [rbp+arg_0], r15
0x18008c86f  mov     [rbp+arg_18], rax
0x18008c873  lea     rdx, byte_18012CD5D
0x18008c87a  lea     rax, aLpaserviceesim; "LpaServiceEsimManager"
0x18008c881  mov     [rbp+arg_10], rdi
0x18008c885  mov     [rbp+var_20], rax
0x18008c889  lea     rax, [rbp+arg_0]
0x18008c88d  mov     [rsp+60h+var_28], rax
0x18008c892  lea     rax, [rbp+arg_10]
0x18008c896  mov     [rsp+60h+var_30], rax
0x18008c89b  lea     rax, [rbp+arg_18]
0x18008c89f  mov     [rsp+60h+var_38], rax
0x18008c8a4  lea     rax, [rbp+var_20]
0x18008c8a8  mov     [rsp+60h+var_40], rax
0x18008c8ad  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &,_tlgWrapSz<ushort> const &)
0x18008c8b2  mov     rcx, [rbp+var_10]; this
0x18008c8b6  test    rcx, rcx
0x18008c8b9  jz      short loc_18008C8C0
0x18008c8bb  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18008c8c0  mov     al, bl
0x18008c8c2  add     rsp, 60h
0x18008c8c6  pop     r15
0x18008c8c8  pop     r14
0x18008c8ca  pop     r12
0x18008c8cc  pop     rdi
0x18008c8cd  pop     rsi
0x18008c8ce  pop     rbx
0x18008c8cf  pop     rbp
0x18008c8d0  retn
```
