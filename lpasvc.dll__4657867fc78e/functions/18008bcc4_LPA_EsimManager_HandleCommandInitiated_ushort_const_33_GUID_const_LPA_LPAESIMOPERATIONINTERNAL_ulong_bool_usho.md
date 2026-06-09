# LPA::EsimManager::HandleCommandInitiated(ushort const (*)[33],_GUID const &,LPA::LPAESIMOPERATIONINTERNAL,ulong,bool,ushort const (*)[21],LPAPROFILESTATE *,LPA::LPACLIENTMODEINTERNAL,std::weak_ptr<LPA::EsimManagerCompletionHandler>,void (LPA::EsimManagerCompletionHandler::*)(long,LPA_ERROR_DETAILS const *,ulong),ulong,ulong &)

- ea: `0x18008bcc4`
- end: `0x18008c05a`
- name: `?HandleCommandInitiated@EsimManager@LPA@@AEAAXPEAY0CB@$$CBGAEBU_GUID@@W4LPAESIMOPERATIONINTERNAL@2@K_NPEAY0BF@$$CBGPEAW4LPAPROFILESTATE@@W4LPACLIENTMODEINTERNAL@2@V?$weak_ptr@UEsimManagerCompletionHandler@LPA@@@std@@P8EsimManagerCompletionHandler@2@EAAXJPEBULPA_ERROR_DETAILS@@K@ZKAEAK@Z`
- size: `918`
- prototype: `__int64 __usercall@<rax>(LPA::EsimManager *this@<rcx>, int, char, unsigned __int16 *, __int64, char, __int64, char, int, __int64)`
- caller_count: `13`
- callee_count: `15`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800883f0`
- `0x180089050`
- `0x1800894e0`
- `0x180089790`
- `0x180089f90`
- `0x18008a640`
- `0x180091434`
- `0x180091c7c`
- `0x1800934c0`
- `0x1800938f0`
- `0x180094250`
- `0x180095260`
- `0x180096930`

## callees

- `0x180004804`
- `0x180004948`
- `0x18005cd20`
- `0x1800709e4`
- `0x180070a1c`
- `0x180071a8c`
- `0x1800817c8`
- `0x180083a2c`
- `0x180083e78`
- `0x180085904`
- `0x18008bcc4`
- `0x1800925e4`
- `0x180094948`
- `0x180094bb4`
- `0x180095f60`

## string_xrefs

- `0x18008bd07`: `LpaServiceEsimManager`
- `0x18008bfcd`: `LpaServiceEsimManager`
- `0x18008bd00`: `LPA::EsimManager::HandleCommandInitiated`
- `0x18008bfc2`: `LPA::EsimManager::HandleCommandInitiated`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall LPA::EsimManager::HandleCommandInitiated(
        LPA::EsimManager *this,
        __int64 a2,
        __int64 a3,
        int a4,
        unsigned int a5,
        char a6,
        unsigned __int16 *a7,
        __int64 a8,
        char a9,
        __int64 a10,
        char a11,
        int a12,
        _DWORD *a13)
{
  int v17; // r8d
  int v18; // r9d
  __int64 v19; // rbx
  __int64 v20; // rdx
  int v21; // ecx
  __int64 v22; // rdx
  int v23; // edi
  int v24; // eax
  __int64 v25; // r15
  __int64 *v26; // rdi
  __int64 v27; // rax
  int v28; // r8d
  int v29; // r9d
  const unsigned __int16 *v30; // r14
  __int64 v31; // rdi
  int v32; // r11d
  __int64 v33; // rcx
  std::_Ref_count_base *v34; // rcx
  int v35; // [rsp+60h] [rbp-39h] BYREF
  int v36; // [rsp+64h] [rbp-35h] BYREF
  _QWORD v37[2]; // [rsp+68h] [rbp-31h] BYREF
  const char *v38; // [rsp+78h] [rbp-21h] BYREF
  std::_Ref_count_base *v39; // [rsp+80h] [rbp-19h]
  _QWORD v40[9]; // [rsp+88h] [rbp-11h] BYREF
  __int64 v41; // [rsp+E0h] [rbp+47h] BYREF
  int v42; // [rsp+F8h] [rbp+5Fh] BYREF

  v42 = a4;
  LPA::EsimManager::TryFindEsimRecordByEid(this, &v41, a2, a3);
  v19 = v41;
  if ( v41 != *((_QWORD *)this + 26) )
  {
    if ( a4 > 10 )
    {
      if ( a4 != 11 )
      {
        switch ( a4 )
        {
          case 13:
            v20 = 4;
            goto LABEL_11;
          case 14:
            v20 = 8;
            goto LABEL_11;
          case 15:
            v20 = 5;
            goto LABEL_11;
        }
        v21 = a4 - 16;
        if ( a4 != 16 )
          goto LABEL_9;
        goto LABEL_12;
      }
      v22 = 6;
    }
    else
    {
      if ( a4 != 10 )
      {
        if ( a4 == 2 )
        {
          LPA::EsimManager::EsimRecord::SetOperationInternal(*(_QWORD *)(v41 + 48), 6, a5);
          v20 = 7;
          goto LABEL_27;
        }
        v20 = 3;
        if ( a4 == 5 )
        {
          v20 = 5;
          goto LABEL_27;
        }
        if ( a4 == 6 )
          goto LABEL_11;
        if ( a4 != 7 )
        {
          v21 = a4 - 8;
          if ( a4 != 8 )
          {
LABEL_9:
            if ( v21 != 1 )
            {
LABEL_28:
              *(_DWORD *)(*(_QWORD *)(v19 + 48) + 176LL) = a12;
              goto LABEL_31;
            }
            v20 = 1;
LABEL_11:
            LPA::EsimManager::EsimRecord::SetOperationInternal(*(_QWORD *)(v41 + 48), v20, a5);
            goto LABEL_28;
          }
LABEL_27:
          LPA::EsimManager::EsimRecord::SetOperationSubState(*(_QWORD *)(v19 + 48), v20);
          goto LABEL_28;
        }
LABEL_12:
        v20 = 2;
        goto LABEL_11;
      }
      v22 = 7;
    }
    LPA::EsimManager::EsimRecord::SetOperationInternal(*(_QWORD *)(v41 + 48), v22, a5);
    v20 = 1;
    goto LABEL_27;
  }
  if ( (unsigned int)CallbackContext > 2 )
  {
    v37[0] = a2;
    LODWORD(v41) = *a13;
    v35 = a12;
    v36 = a4;
    v38 = "LPA::EsimManager::HandleCommandInitiated";
    v40[0] = "LpaServiceEsimManager";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
      (unsigned int)"LPA::EsimManager::HandleCommandInitiated",
      (unsigned int)byte_18012F0FB,
      v17,
      v18,
      (__int64)v40,
      (__int64)&v38,
      (__int64)&v36,
      (__int64)&v35,
      (__int64)&v41,
      (__int64)v37);
  }
LABEL_31:
  while ( _InterlockedExchangeAdd(&dword_180173B90, 1u) == -1 )
    ;
  v23 = (int)a13;
  *a13 = dword_180173B90;
  LODWORD(v41) = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v19 + 48) + 32LL) + 108LL);
  v24 = std::enable_shared_from_this<LPA::EnterpriseManager>::shared_from_this((char *)this + 88, &v38);
  v25 = a10;
  v26 = (__int64 *)std::make_unique<LPA::EsimManager::OperationEntry,std::shared_ptr<LPA::EsimManager>,unsigned long &,unsigned long &,_GUID const &,unsigned long,enum LPA::LPAESIMOPERATIONINTERNAL &,bool &,enum LPA::LPACLIENTMODEINTERNAL &,void (LPA::EsimManagerCompletionHandler::*&)(long,LPA_ERROR_DETAILS const *,unsigned long),std::weak_ptr<LPA::EsimManagerCompletionHandler> &,0>(
                     (unsigned int)v40,
                     v24,
                     (unsigned int)&a12,
                     v23,
                     a3,
                     (__int64)&v41,
                     (__int64)&v42,
                     (__int64)&a6,
                     (__int64)&a9,
                     (__int64)&a11,
                     a10);
  v27 = std::map<unsigned long,std::unique_ptr<LPA::EsimManager::OperationEntry>>::_Try_emplace<unsigned long const &,>(
          (char *)this + 240,
          v37,
          &a12);
  std::unique_ptr<LPA::EsimManager::OperationEntry>::operator=<std::default_delete<LPA::EsimManager::OperationEntry>,0>(
    (__int64 *)(*(_QWORD *)v27 + 40LL),
    v26);
  std::unique_ptr<LPA::EsimManager::OperationEntry>::~unique_ptr<LPA::EsimManager::OperationEntry>(v40);
  if ( v39 )
    std::_Ref_count_base::_Decref(v39);
  v30 = a7;
  if ( a7 )
  {
    if ( a8 )
    {
      v31 = *(_QWORD *)(*(_QWORD *)std::map<unsigned long,std::unique_ptr<LPA::EsimManager::OperationEntry>>::_Try_emplace<unsigned long const &,>(
                                     (char *)this + 240,
                                     v40,
                                     &a12)
                      + 40LL);
      StringCchCopyW((unsigned __int16 *)(v31 + 92), 0x15u, v30);
      *(_DWORD *)(v31 + 136) = v32;
    }
    v25 = a10;
  }
  if ( (unsigned int)CallbackContext > 4 )
  {
    v40[0] = a2;
    v33 = *(_QWORD *)(*(_QWORD *)(v19 + 48) + 32LL);
    LODWORD(a7) = *(_DWORD *)(v33 + 108);
    LODWORD(a13) = *a13;
    LODWORD(v41) = a12;
    v36 = a4;
    v38 = "LPA::EsimManager::HandleCommandInitiated";
    v37[0] = "LpaServiceEsimManager";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
      v33,
      (unsigned int)byte_18012F085,
      v28,
      v29,
      (__int64)v37,
      (__int64)&v38,
      (__int64)&v36,
      (__int64)&v41,
      (__int64)&a13,
      (__int64)&a7,
      (__int64)v40);
  }
  LPA::EsimManager::ProcessAndBroadcastChanges(this, 0);
  v34 = *(std::_Ref_count_base **)(v25 + 8);
  if ( v34 )
    std::_Ref_count_base::_Decwref(v34);
}

```

## disassembly

```asm
0x18008bcc4  mov     [rsp-8+arg_8], rbx
0x18008bcc9  mov     [rsp-8+arg_18], r9d
0x18008bcce  push    rbp
0x18008bccf  push    rsi
0x18008bcd0  push    rdi
0x18008bcd1  push    r12
0x18008bcd3  push    r13
0x18008bcd5  push    r14
0x18008bcd7  push    r15
0x18008bcd9  lea     rbp, [rsp-7]
0x18008bcde  sub     rsp, 0A0h
0x18008bce5  mov     esi, r9d
0x18008bce8  mov     r14, r8
0x18008bceb  mov     r12, rdx
0x18008bcee  mov     r13, rcx
0x18008bcf1  mov     r9, r8
0x18008bcf4  mov     r8, rdx
0x18008bcf7  lea     rdx, [rbp+37h+arg_0]
0x18008bcfb  call    ?TryFindEsimRecordByEid@EsimManager@LPA@@AEAA?AV?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@V?$unique_ptr@VEsimRecord@EsimManager@LPA@@U?$default_delete@VEsimRecord@EsimManager@LPA@@@std@@@std@@@std@@@std@@@std@@@std@@PEAY0CB@$$CBGAEBU_GUID@@@Z; LPA::EsimManager::TryFindEsimRecordByEid(ushort const (*)[33],_GUID const &)
0x18008bd00  lea     rcx, aLpaEsimmanager_5; "LPA::EsimManager::HandleCommandInitiate"...
0x18008bd07  lea     rdx, aLpaserviceesim; "LpaServiceEsimManager"
0x18008bd0e  mov     edi, 1
0x18008bd13  mov     rbx, [rbp+37h+arg_0]
0x18008bd17  cmp     rbx, [r13+0D0h]
0x18008bd1e  jz      loc_18008BDEE
0x18008bd24  cmp     esi, 0Ah
0x18008bd27  jg      short loc_18008BD90
0x18008bd29  jz      short loc_18008BD89
0x18008bd2b  mov     ecx, esi
0x18008bd2d  sub     ecx, 2
0x18008bd30  jz      short loc_18008BD70
0x18008bd32  lea     edx, [rdi+2]
0x18008bd35  sub     ecx, edx
0x18008bd37  jz      short loc_18008BD69
0x18008bd39  sub     ecx, edi
0x18008bd3b  jz      short loc_18008BD53
0x18008bd3d  sub     ecx, edi
0x18008bd3f  jz      short loc_18008BD62
0x18008bd41  sub     ecx, edi
0x18008bd43  jz      loc_18008BDD3
0x18008bd49  cmp     ecx, edi
0x18008bd4b  jnz     loc_18008BDDC
0x18008bd51  mov     edx, edi
0x18008bd53  mov     r8d, [rbp+37h+arg_20]
0x18008bd57  mov     rcx, [rbx+30h]
0x18008bd5b  call    ?SetOperationInternal@EsimRecord@EsimManager@LPA@@AEAAXW4LPAESIMOPERATION@@K@Z; LPA::EsimManager::EsimRecord::SetOperationInternal(LPAESIMOPERATION,ulong)
0x18008bd60  jmp     short loc_18008BDDC
0x18008bd62  mov     edx, 2
0x18008bd67  jmp     short loc_18008BD53
0x18008bd69  mov     edx, 5
0x18008bd6e  jmp     short loc_18008BDD3
0x18008bd70  mov     r8d, [rbp+37h+arg_20]
0x18008bd74  mov     edx, 6
0x18008bd79  mov     rcx, [rbx+30h]
0x18008bd7d  call    ?SetOperationInternal@EsimRecord@EsimManager@LPA@@AEAAXW4LPAESIMOPERATION@@K@Z; LPA::EsimManager::EsimRecord::SetOperationInternal(LPAESIMOPERATION,ulong)
0x18008bd82  mov     edx, 7
0x18008bd87  jmp     short loc_18008BDD3
0x18008bd89  mov     edx, 7
0x18008bd8e  jmp     short loc_18008BDC4
0x18008bd90  mov     ecx, esi
0x18008bd92  sub     ecx, 0Bh
0x18008bd95  jz      short loc_18008BDBF
0x18008bd97  sub     ecx, 2
0x18008bd9a  jz      short loc_18008BDB8
0x18008bd9c  sub     ecx, edi
0x18008bd9e  jz      short loc_18008BDB1
0x18008bda0  sub     ecx, edi
0x18008bda2  jz      short loc_18008BDAA
0x18008bda4  sub     ecx, edi
0x18008bda6  jz      short loc_18008BD62
0x18008bda8  jmp     short loc_18008BD49
0x18008bdaa  mov     edx, 5
0x18008bdaf  jmp     short loc_18008BD53
0x18008bdb1  mov     edx, 8
0x18008bdb6  jmp     short loc_18008BD53
0x18008bdb8  mov     edx, 4
0x18008bdbd  jmp     short loc_18008BD53
0x18008bdbf  mov     edx, 6
0x18008bdc4  mov     r8d, [rbp+37h+arg_20]
0x18008bdc8  mov     rcx, [rbx+30h]
0x18008bdcc  call    ?SetOperationInternal@EsimRecord@EsimManager@LPA@@AEAAXW4LPAESIMOPERATION@@K@Z; LPA::EsimManager::EsimRecord::SetOperationInternal(LPAESIMOPERATION,ulong)
0x18008bdd1  mov     edx, edi
0x18008bdd3  mov     rcx, [rbx+30h]
0x18008bdd7  call    ?SetOperationSubState@EsimRecord@EsimManager@LPA@@QEAAXW4LPAESIMOPERATIONSUBSTATE@@@Z; LPA::EsimManager::EsimRecord::SetOperationSubState(LPAESIMOPERATIONSUBSTATE)
0x18008bddc  mov     rcx, [rbx+30h]
0x18008bde0  mov     eax, [rbp+37h+arg_58]
0x18008bde6  mov     [rcx+0B0h], eax
0x18008bdec  jmp     short loc_18008BE5F
0x18008bdee  mov     eax, cs:CallbackContext
0x18008bdf4  cmp     eax, 2
0x18008bdf7  jbe     short loc_18008BE5F
0x18008bdf9  mov     [rbp+37h+var_68], r12
0x18008bdfd  mov     rax, [rbp+37h+arg_60]
0x18008be04  mov     eax, [rax]
0x18008be06  mov     dword ptr [rbp+37h+arg_0], eax
0x18008be09  mov     eax, [rbp+37h+arg_58]
0x18008be0f  mov     [rbp+37h+var_70], eax
0x18008be12  mov     [rbp+37h+var_6C], esi
0x18008be15  mov     [rbp+37h+var_58], rcx
0x18008be19  mov     [rbp+37h+var_48], rdx
0x18008be1d  lea     rax, [rbp+37h+var_68]
0x18008be21  mov     [rsp+0D0h+var_88], rax
0x18008be26  lea     rax, [rbp+37h+arg_0]
0x18008be2a  mov     [rsp+0D0h+var_90], rax
0x18008be2f  lea     rax, [rbp+37h+var_70]
0x18008be33  mov     [rsp+0D0h+var_98], rax
0x18008be38  lea     rax, [rbp+37h+var_6C]
0x18008be3c  mov     [rsp+0D0h+var_A0], rax
0x18008be41  lea     rax, [rbp+37h+var_58]
0x18008be45  mov     [rsp+0D0h+var_A8], rax
0x18008be4a  lea     rax, [rbp+37h+var_48]
0x18008be4e  mov     [rsp+0D0h+var_B0], rax
0x18008be53  lea     rdx, byte_18012F0FB
0x18008be5a  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U2@U2@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@44AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &)
0x18008be5f  mov     eax, edi
0x18008be61  lock xadd cs:dword_180173B90, eax
0x18008be69  add     eax, edi
0x18008be6b  jz      short loc_18008BE5F
0x18008be6d  mov     eax, cs:dword_180173B90
0x18008be73  mov     rdi, [rbp+37h+arg_60]
0x18008be7a  mov     [rdi], eax
0x18008be7c  mov     rax, [rbx+30h]
0x18008be80  mov     rcx, [rax+20h]
0x18008be84  mov     eax, [rcx+6Ch]
0x18008be87  mov     dword ptr [rbp+37h+arg_0], eax
0x18008be8a  lea     rcx, [r13+58h]
0x18008be8e  lea     rdx, [rbp+37h+var_58]
0x18008be92  call    ?shared_from_this@?$enable_shared_from_this@VEnterpriseManager@LPA@@@std@@QEAA?AV?$shared_ptr@VEnterpriseManager@LPA@@@2@XZ; std::enable_shared_from_this<LPA::EnterpriseManager>::shared_from_this(void)
0x18008be97  nop
0x18008be98  mov     r15, [rbp+37h+arg_48]
0x18008be9f  mov     [rsp+0D0h+var_80], r15
0x18008bea4  lea     rcx, [rbp+37h+arg_50]
0x18008beab  mov     [rsp+0D0h+var_88], rcx
0x18008beb0  lea     rcx, [rbp+37h+arg_40]
0x18008beb7  mov     [rsp+0D0h+var_90], rcx
0x18008bebc  lea     rcx, [rbp+37h+arg_28]
0x18008bec0  mov     [rsp+0D0h+var_98], rcx
0x18008bec5  lea     rcx, [rbp+37h+arg_18]
0x18008bec9  mov     [rsp+0D0h+var_A0], rcx
0x18008bece  lea     rcx, [rbp+37h+arg_0]
0x18008bed2  mov     [rsp+0D0h+var_A8], rcx
0x18008bed7  mov     [rsp+0D0h+var_B0], r14
0x18008bedc  mov     r9, rdi
0x18008bedf  lea     r8, [rbp+37h+arg_58]
0x18008bee6  mov     rdx, rax
0x18008bee9  lea     rcx, [rbp+37h+var_48]
0x18008beed  call    ??$make_unique@VOperationEntry@EsimManager@LPA@@V?$shared_ptr@VEsimManager@LPA@@@std@@AEAKAEAKAEBU_GUID@@KAEAW4LPAESIMOPERATIONINTERNAL@3@AEA_NAEAW4LPACLIENTMODEINTERNAL@3@AEAP8EsimManagerCompletionHandler@3@EAAXJPEBULPA_ERROR_DETAILS@@K@ZAEAV?$weak_ptr@UEsimManagerCompletionHandler@LPA@@@5@$0A@@std@@YA?AV?$unique_ptr@VOperationEntry@EsimManager@LPA@@U?$default_delete@VOperationEntry@EsimManager@LPA@@@std@@@0@$$QEAV?$shared_ptr@VEsimManager@LPA@@@0@AEAK1AEBU_GUID@@$$QEAKAEAW4LPAESIMOPERATIONINTERNAL@LPA@@AEA_NAEAW4LPACLIENTMODEINTERNAL@5@AEAP8EsimManagerCompletionHandler@5@EAAXJPEBULPA_ERROR_DETAILS@@K@ZAEAV?$weak_ptr@UEsimManagerCompletionHandler@LPA@@@0@@Z; std::make_unique<LPA::EsimManager::OperationEntry,std::shared_ptr<LPA::EsimManager>,ulong &,ulong &,_GUID const &,ulong,LPA::LPAESIMOPERATIONINTERNAL &,bool &,LPA::LPACLIENTMODEINTERNAL &,void (LPA::EsimManagerCompletionHandler::*&)(long,LPA_ERROR_DETAILS const *,ulong),std::weak_ptr<LPA::EsimManagerCompletionHandler> &,0>(std::shared_ptr<LPA::EsimManager> &&,ulong &,ulong &,_GUID const &,ulong &&,LPA::LPAESIMOPERATIONINTERNAL &,bool &,LPA::LPACLIENTMODEINTERNAL &,void (LPA::EsimManagerCompletionHandler::*&)(long,LPA_ERROR_DETAILS const *,ulong),std::weak_ptr<LPA::EsimManagerCompletionHandler> &)
0x18008bef2  mov     rdi, rax
0x18008bef5  lea     rcx, [r13+0F0h]
0x18008befc  lea     r8, [rbp+37h+arg_58]
0x18008bf03  lea     rdx, [rbp+37h+var_68]
0x18008bf07  call    ??$_Try_emplace@AEBK$$V@?$map@KV?$unique_ptr@VOperationEntry@EsimManager@LPA@@U?$default_delete@VOperationEntry@EsimManager@LPA@@@std@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$unique_ptr@VOperationEntry@EsimManager@LPA@@U?$default_delete@VOperationEntry@EsimManager@LPA@@@std@@@std@@@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBKV?$unique_ptr@VOperationEntry@EsimManager@LPA@@U?$default_delete@VOperationEntry@EsimManager@LPA@@@std@@@std@@@std@@PEAX@std@@_N@1@AEBK@Z; std::map<ulong,std::unique_ptr<LPA::EsimManager::OperationEntry>>::_Try_emplace<ulong const &,>(ulong const &)
0x18008bf0c  mov     rcx, [rax]
0x18008bf0f  add     rcx, 28h ; '('
0x18008bf13  mov     rdx, rdi
0x18008bf16  call    ??$?4U?$default_delete@VOperationEntry@EsimManager@LPA@@@std@@$0A@@?$unique_ptr@VOperationEntry@EsimManager@LPA@@U?$default_delete@VOperationEntry@EsimManager@LPA@@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::unique_ptr<LPA::EsimManager::OperationEntry>::operator=<std::default_delete<LPA::EsimManager::OperationEntry>,0>(std::unique_ptr<LPA::EsimManager::OperationEntry> &&)
0x18008bf1b  nop
0x18008bf1c  lea     rcx, [rbp+37h+var_48]
0x18008bf20  call    ??1?$unique_ptr@VOperationEntry@EsimManager@LPA@@U?$default_delete@VOperationEntry@EsimManager@LPA@@@std@@@std@@QEAA@XZ; std::unique_ptr<LPA::EsimManager::OperationEntry>::~unique_ptr<LPA::EsimManager::OperationEntry>(void)
0x18008bf25  nop
0x18008bf26  mov     rcx, [rbp+37h+var_50]; this
0x18008bf2a  test    rcx, rcx
0x18008bf2d  jz      short loc_18008BF34
0x18008bf2f  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18008bf34  mov     r14, [rbp+37h+arg_30]
0x18008bf38  test    r14, r14
0x18008bf3b  jz      short loc_18008BF86
0x18008bf3d  mov     r15, [rbp+37h+arg_38]
0x18008bf41  test    r15, r15
0x18008bf44  jz      short loc_18008BF7F
0x18008bf46  lea     r8, [rbp+37h+arg_58]
0x18008bf4d  lea     rdx, [rbp+37h+var_48]
0x18008bf51  lea     rcx, [r13+0F0h]
0x18008bf58  call    ??$_Try_emplace@AEBK$$V@?$map@KV?$unique_ptr@VOperationEntry@EsimManager@LPA@@U?$default_delete@VOperationEntry@EsimManager@LPA@@@std@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$unique_ptr@VOperationEntry@EsimManager@LPA@@U?$default_delete@VOperationEntry@EsimManager@LPA@@@std@@@std@@@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBKV?$unique_ptr@VOperationEntry@EsimManager@LPA@@U?$default_delete@VOperationEntry@EsimManager@LPA@@@std@@@std@@@std@@PEAX@std@@_N@1@AEBK@Z; std::map<ulong,std::unique_ptr<LPA::EsimManager::OperationEntry>>::_Try_emplace<ulong const &,>(ulong const &)
0x18008bf5d  mov     rcx, [rax]
0x18008bf60  mov     rdi, [rcx+28h]
0x18008bf64  mov     r11d, [r15]
0x18008bf67  lea     rcx, [rdi+5Ch]; unsigned __int16 *
0x18008bf6b  mov     r8, r14; unsigned __int16 *
0x18008bf6e  mov     edx, 15h; unsigned __int64
0x18008bf73  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18008bf78  mov     [rdi+88h], r11d
0x18008bf7f  mov     r15, [rbp+37h+arg_48]
0x18008bf86  mov     eax, cs:CallbackContext
0x18008bf8c  cmp     eax, 4
0x18008bf8f  jbe     loc_18008C026
0x18008bf95  mov     [rbp+37h+var_48], r12
0x18008bf99  mov     rax, [rbx+30h]
0x18008bf9d  mov     rcx, [rax+20h]
0x18008bfa1  mov     eax, [rcx+6Ch]
0x18008bfa4  mov     dword ptr [rbp+37h+arg_30], eax
0x18008bfa7  mov     rax, [rbp+37h+arg_60]
0x18008bfae  mov     eax, [rax]
0x18008bfb0  mov     dword ptr [rbp+37h+arg_60], eax
0x18008bfb6  mov     eax, [rbp+37h+arg_58]
0x18008bfbc  mov     dword ptr [rbp+37h+arg_0], eax
0x18008bfbf  mov     [rbp+37h+var_6C], esi
0x18008bfc2  lea     rax, aLpaEsimmanager_5; "LPA::EsimManager::HandleCommandInitiate"...
0x18008bfc9  mov     [rbp+37h+var_58], rax
0x18008bfcd  lea     rax, aLpaserviceesim; "LpaServiceEsimManager"
0x18008bfd4  mov     [rbp+37h+var_68], rax
0x18008bfd8  lea     rax, [rbp+37h+var_48]
0x18008bfdc  mov     [rsp+0D0h+var_80], rax
0x18008bfe1  lea     rax, [rbp+37h+arg_30]
0x18008bfe5  mov     [rsp+0D0h+var_88], rax
0x18008bfea  lea     rax, [rbp+37h+arg_60]
0x18008bff1  mov     [rsp+0D0h+var_90], rax
0x18008bff6  lea     rax, [rbp+37h+arg_0]
0x18008bffa  mov     [rsp+0D0h+var_98], rax
0x18008bfff  lea     rax, [rbp+37h+var_6C]
0x18008c003  mov     [rsp+0D0h+var_A0], rax
0x18008c008  lea     rax, [rbp+37h+var_58]
0x18008c00c  mov     [rsp+0D0h+var_A8], rax
0x18008c011  lea     rax, [rbp+37h+var_68]
0x18008c015  mov     [rsp+0D0h+var_B0], rax
0x18008c01a  lea     rdx, byte_18012F085
0x18008c021  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U2@U2@U2@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@444AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &)
0x18008c026  xor     edx, edx; bool
0x18008c028  mov     rcx, r13; this
0x18008c02b  call    ?ProcessAndBroadcastChanges@EsimManager@LPA@@AEAAX_N@Z; LPA::EsimManager::ProcessAndBroadcastChanges(bool)
0x18008c030  nop
0x18008c031  mov     rcx, [r15+8]; this
0x18008c035  test    rcx, rcx
0x18008c038  jz      short loc_18008C03F
0x18008c03a  call    ?_Decwref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decwref(void)
0x18008c03f  mov     rbx, [rsp+0D0h+arg_8]
0x18008c047  add     rsp, 0A0h
0x18008c04e  pop     r15
0x18008c050  pop     r14
0x18008c052  pop     r13
0x18008c054  pop     r12
0x18008c056  pop     rdi
0x18008c057  pop     rsi
0x18008c058  pop     rbp
0x18008c059  retn
```
