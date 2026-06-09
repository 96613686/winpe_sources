# LPA::EsimManager::CompleteOperation(std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<ulong const,std::unique_ptr<LPA::EsimManager::OperationEntry,std::default_delete<LPA::EsimManager::OperationEntry>>>>>> &)

- ea: `0x180088b48`
- end: `0x180089045`
- name: `?CompleteOperation@EsimManager@LPA@@AEAAXAEAV?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKV?$unique_ptr@VOperationEntry@EsimManager@LPA@@U?$default_delete@VOperationEntry@EsimManager@LPA@@@std@@@std@@@std@@@std@@@std@@@std@@@Z`
- size: `1277`
- prototype: `__int64 __fastcall(LPA::EsimManager *this)`
- caller_count: `13`
- callee_count: `24`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800883f0`
- `0x18008b750`
- `0x18008caf0`
- `0x18008ce20`
- `0x18008d010`
- `0x18008d320`
- `0x18008d700`
- `0x18008df80`
- `0x18008f990`
- `0x180090420`
- `0x180090970`
- `0x180090ad0`
- `0x180092f68`

## callees

- `0x1800014d8`
- `0x180003d5c`
- `0x180003e68`
- `0x18000517c`
- `0x18000df90`
- `0x18006361c`
- `0x180063668`
- `0x180065170`
- `0x180071650`
- `0x180087768`
- `0x180088378`
- `0x180088b48`
- `0x18008aeb4`
- `0x18008c8d8`
- `0x18008c914`
- `0x1800925e4`
- `0x180093f80`
- `0x180094924`
- `0x180095414`
- `0x180095fd0`
- `0x18009733c`
- `0x1800d96e0`
- `0x1800dabcc`
- `0x180101010`

## string_xrefs

- `0x180088c95`: `LpaServiceEsimManager`
- `0x180088fa4`: `LpaServiceEsimManager`
- `0x180088c8e`: `LPA::EsimManager::CompleteOperation`
- `0x180088f99`: `LPA::EsimManager::CompleteOperation`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall LPA::EsimManager::CompleteOperation(LPA::EsimManager *this, _QWORD *a2)
{
  __int64 v4; // rsi
  __int64 v5; // r9
  struct _TP_TIMER **v6; // rdx
  __int64 v7; // rcx
  struct _TP_TIMER **v8; // rdx
  __int64 result; // rax
  unsigned int *v10; // rcx
  bool v11; // al
  int v12; // r8d
  int v13; // r9d
  __int64 v14; // rax
  __int64 v15; // rbx
  __int64 v16; // rdx
  __int64 v17; // rdx
  __int64 v18; // rcx
  __int64 *EsimRecordBySlotId; // rax
  __int64 EsimId; // r12
  __int64 v21; // rdi
  __int64 v22; // rdx
  struct LPA::EsimManager::EsimRecord *v23; // rcx
  int Es10bNotificationsList; // ecx
  int v25; // r8d
  int v26; // r9d
  __int64 v27; // rcx
  int v28; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v29; // [rsp+68h] [rbp-98h] BYREF
  int v30; // [rsp+70h] [rbp-90h] BYREF
  int v31; // [rsp+74h] [rbp-8Ch] BYREF
  const char *v32; // [rsp+78h] [rbp-88h] BYREF
  const char *v33; // [rsp+80h] [rbp-80h] BYREF
  int v34; // [rsp+88h] [rbp-78h] BYREF
  const char *v35; // [rsp+90h] [rbp-70h] BYREF
  unsigned int v36; // [rsp+98h] [rbp-68h]
  __int128 v37; // [rsp+A0h] [rbp-60h] BYREF
  __m128i si128; // [rsp+B0h] [rbp-50h]
  LPA::EsimManager *v39; // [rsp+C0h] [rbp-40h]
  __int64 (__fastcall **v40)(); // [rsp+D0h] [rbp-30h] BYREF
  __int128 v41; // [rsp+D8h] [rbp-28h]
  __m128i v42; // [rsp+E8h] [rbp-18h]
  LPA::EsimManager *v43; // [rsp+F8h] [rbp-8h]
  __int64 (__fastcall ***v44)(); // [rsp+108h] [rbp+8h]
  _BYTE v45[32]; // [rsp+110h] [rbp+10h] BYREF

  v4 = *a2;
  v5 = *(_QWORD *)(*a2 + 40LL);
  v34 = *(_DWORD *)(v5 + 224);
  LPA::EsimManager::TryFindEsimRecordBySlotId(this, &v29, &v34, v5);
  v7 = *(_QWORD *)(v4 + 40);
  if ( !v7 )
    return std::_Tree<std::_Tmap_traits<unsigned long,std::unique_ptr<LPA::EsimManager::OperationEntry>,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,std::unique_ptr<LPA::EsimManager::OperationEntry>>>,0>>::_Erase_unchecked(
             (char *)this + 240,
             *a2);
  LPA::Util::CancelTimer((PTP_TIMER *)(v7 + 72), v6);
  v8 = *(struct _TP_TIMER ***)(v4 + 40);
  if ( !v8[25] )
  {
LABEL_12:
    LPA::Util::CancelTimer((PTP_TIMER *)(*(_QWORD *)(v4 + 40) + 64LL), v8);
    v14 = *(_QWORD *)(v4 + 40);
    if ( *(_BYTE *)(v14 + 88) )
      return std::_Tree<std::_Tmap_traits<unsigned long,std::unique_ptr<LPA::EsimManager::OperationEntry>,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,std::unique_ptr<LPA::EsimManager::OperationEntry>>>,0>>::_Erase_unchecked(
               (char *)this + 240,
               *a2);
    v15 = v29;
    if ( *((_QWORD *)this + 26) == v29 )
    {
      if ( (unsigned int)CallbackContext > 3 )
      {
        v27 = *(_QWORD *)(v4 + 40);
        LODWORD(v29) = *(_DWORD *)(v27 + 36);
        v28 = *(_DWORD *)(v27 + 208);
        v35 = (const char *)v27;
        v33 = "LPA::EsimManager::CompleteOperation";
        v32 = "LpaServiceEsimManager";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          v27,
          (unsigned int)word_18012F1C2,
          v12,
          v13,
          (__int64)&v32,
          (__int64)&v33,
          (__int64)&v35,
          (__int64)&v28,
          (__int64)&v29);
      }
    }
    else
    {
      if ( *(_DWORD *)(*(_QWORD *)(v29 + 48) + 176LL) != *(_DWORD *)(v14 + 32) && (unsigned int)CallbackContext > 3 )
      {
        v16 = *(_QWORD *)(v4 + 40);
        v30 = *(_DWORD *)(v16 + 32);
        v31 = *(_DWORD *)(*(_QWORD *)(v29 + 48) + 176LL);
        v28 = *(_DWORD *)(v16 + 80);
        v29 = v16;
        v32 = "LPA::EsimManager::CompleteOperation";
        v33 = "LpaServiceEsimManager";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          v31,
          (unsigned int)byte_18012F2E3,
          v12,
          v13,
          (__int64)&v33,
          (__int64)&v32,
          (__int64)&v29,
          (__int64)&v28,
          (__int64)&v31,
          (__int64)&v30);
      }
      if ( (unsigned int)CallbackContext > 4 )
      {
        v17 = *(_QWORD *)(v4 + 40);
        v28 = *(_DWORD *)(v17 + 36);
        v31 = *(_DWORD *)(*(_QWORD *)(v15 + 48) + 176LL);
        v18 = *(_QWORD *)(*(_QWORD *)(v15 + 48) + 32LL);
        v30 = *(_DWORD *)(v18 + 108);
        LODWORD(v29) = *(_DWORD *)(v17 + 80);
        v33 = (const char *)v17;
        v32 = "LPA::EsimManager::CompleteOperation";
        v35 = "LpaServiceEsimManager";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          v18,
          (unsigned int)byte_18012F265,
          v12,
          v13,
          (__int64)&v35,
          (__int64)&v32,
          (__int64)&v33,
          (__int64)&v29,
          (__int64)&v30,
          (__int64)&v31,
          (__int64)&v28);
      }
      LPA::EsimManager::EsimRecord::SetOperationCompleted(
        *(_QWORD *)(v15 + 48),
        *(unsigned int *)(*(_QWORD *)(v4 + 40) + 80LL));
      LPA::EsimManager::ProcessAndBroadcastChanges(this, 0);
      EsimRecordBySlotId = (__int64 *)LPA::EsimManager::TryFindEsimRecordBySlotId(
                                        this,
                                        &v35,
                                        &v34,
                                        *(_QWORD *)(v4 + 40));
      v15 = *EsimRecordBySlotId;
      if ( *((_QWORD *)this + 26) == *EsimRecordBySlotId )
        goto LABEL_24;
      EsimId = LPA::EsimManager::EsimRecord::GetEsimId(*(_QWORD *)(v15 + 48));
      if ( EsimId
        && (*(unsigned __int8 (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 22) + 96LL))(
             *((_QWORD *)this + 22),
             EsimId) )
      {
        std::wstring::wstring(v45, EsimId);
        v21 = *((_QWORD *)this + 16);
        std::wstring::wstring(&v37, v45);
        v39 = this;
        v40 = off_180106C08;
        v41 = v37;
        v42 = si128;
        si128 = _mm_load_si128((const __m128i *)&_xmm);
        LOWORD(v37) = 0;
        v43 = this;
        v44 = &v40;
        MessageDispatcher::EnQueue(v21, &v40);
        `pplx::details::_MakeTToUnitFunc<web::json::value>'::`2'::_lambda_1_::~_lambda_1_(&v40);
        std::wstring::_Tidy_deallocate(&v37);
        std::wstring::_Tidy_deallocate(v45);
      }
      else if ( !LPA::EsimManager::EsimRecord::IsProcessingEs10bNotifications(*(LPA::EsimManager::EsimRecord **)(v15 + 48)) )
      {
        Es10bNotificationsList = LPA::EsimManager::RetrieveEs10bNotificationsList(
                                   this,
                                   *(const struct _GUID **)(v4 + 40),
                                   v23);
        if ( Es10bNotificationsList < 0 )
        {
          if ( (unsigned int)CallbackContext > 3 )
          {
            v35 = *(const char **)(v4 + 40);
            LODWORD(v29) = Es10bNotificationsList;
            v33 = "LPA::EsimManager::CompleteOperation";
            v32 = "LpaServiceEsimManager";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(
              Es10bNotificationsList,
              (unsigned int)byte_18012F219,
              v25,
              v26,
              (__int64)&v32,
              (__int64)&v33,
              (__int64)&v29,
              (__int64)&v35);
          }
        }
        else
        {
          LPA::EsimManager::CalculateNumberOfBackgroundTasks(this);
        }
      }
    }
    if ( *((_QWORD *)this + 26) != v15 )
    {
      v22 = (unsigned int)(*(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v15 + 48) + 32LL) + 112LL) != 1) + 1;
      goto LABEL_33;
    }
LABEL_24:
    v22 = 0;
LABEL_33:
    LPA::EsimManager::OperationEntry::NotifyCompletionHandler(*(_QWORD *)(v4 + 40), v22);
    return std::_Tree<std::_Tmap_traits<unsigned long,std::unique_ptr<LPA::EsimManager::OperationEntry>,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,std::unique_ptr<LPA::EsimManager::OperationEntry>>>,0>>::_Erase_unchecked(
             (char *)this + 240,
             *a2);
  }
  v35 = 0;
  v36 = 0;
  if ( v8 != (struct _TP_TIMER **)-212LL )
  {
    v35 = *(const char **)((char *)v8 + 212);
    v36 = *((_DWORD *)v8 + 55);
  }
  result = std::_Func_class<long,long,unsigned long,LPA_ERROR_DETAILS &>::operator()(
             v8 + 18,
             *((unsigned int *)v8 + 52),
             *((unsigned int *)v8 + 8),
             &v35);
  if ( (int)result < 0 )
  {
    LPA::EsimManager::OperationEntry::SetResult(*(LPA::EsimManager::OperationEntry **)(v4 + 40), result);
    v10 = *(unsigned int **)(v4 + 40);
    v11 = 0;
    v8 = (struct _TP_TIMER **)v10[53];
    if ( ((unsigned __int8)v8 & 1) != 0 )
      v11 = v10[54] != 0;
    if ( (((unsigned __int8)v8 & 2) == 0 || !v10[55]) && !v11 )
    {
      *(_QWORD *)(v10 + 53) = v35;
      v10[55] = v36;
    }
    goto LABEL_12;
  }
  return result;
}

```

## disassembly

```asm
0x180088b48  mov     [rsp-8+arg_10], rbx
0x180088b4d  push    rbp
0x180088b4e  push    rsi
0x180088b4f  push    rdi
0x180088b50  push    r12
0x180088b52  push    r13
0x180088b54  push    r14
0x180088b56  push    r15
0x180088b58  lea     rbp, [rsp-40h]
0x180088b5d  sub     rsp, 140h
0x180088b64  mov     rax, cs:__security_cookie
0x180088b6b  xor     rax, rsp
0x180088b6e  mov     [rbp+70h+var_40], rax
0x180088b72  mov     r13, rdx
0x180088b75  mov     r14, rcx
0x180088b78  mov     rsi, [rdx]
0x180088b7b  mov     r9, [rsi+28h]
0x180088b7f  mov     eax, [r9+0E0h]
0x180088b86  mov     [rbp+70h+var_E8], eax
0x180088b89  lea     r8, [rbp+70h+var_E8]
0x180088b8d  lea     rdx, [rsp+170h+var_108]
0x180088b92  call    ?TryFindEsimRecordBySlotId@EsimManager@LPA@@AEAA?AV?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@V?$unique_ptr@VEsimRecord@EsimManager@LPA@@U?$default_delete@VEsimRecord@EsimManager@LPA@@@std@@@std@@@std@@@std@@@std@@@std@@AEBKAEBU_GUID@@@Z; LPA::EsimManager::TryFindEsimRecordBySlotId(ulong const &,_GUID const &)
0x180088b97  mov     rcx, [rsi+28h]
0x180088b9b  test    rcx, rcx
0x180088b9e  jz      loc_18008900E
0x180088ba4  add     rcx, 48h ; 'H'; this
0x180088ba8  call    ?CancelTimer@Util@LPA@@YAXAEAPEAU_TP_TIMER@@@Z; LPA::Util::CancelTimer(_TP_TIMER * &)
0x180088bad  mov     rdx, [rsi+28h]
0x180088bb1  lea     rcx, [rdx+90h]
0x180088bb8  mov     r12d, 1
0x180088bbe  cmp     qword ptr [rcx+38h], 0
0x180088bc3  jz      loc_180088C5A
0x180088bc9  xor     eax, eax
0x180088bcb  mov     [rbp+70h+var_E0], rax
0x180088bcf  mov     [rbp+70h+var_D8], eax
0x180088bd2  lea     rax, [rdx+0D4h]
0x180088bd9  test    rax, rax
0x180088bdc  jz      short loc_180088BED
0x180088bde  movsd   xmm0, qword ptr [rax]
0x180088be2  movsd   [rbp+70h+var_E0], xmm0
0x180088be7  mov     eax, [rax+8]
0x180088bea  mov     [rbp+70h+var_D8], eax
0x180088bed  lea     r9, [rbp+70h+var_E0]
0x180088bf1  mov     r8d, [rdx+20h]
0x180088bf5  mov     edx, [rdx+0D0h]
0x180088bfb  call    ??R?$_Func_class@JJKAEAULPA_ERROR_DETAILS@@@std@@QEBAJJKAEAULPA_ERROR_DETAILS@@@Z; std::_Func_class<long,long,ulong,LPA_ERROR_DETAILS &>::operator()(long,ulong,LPA_ERROR_DETAILS &)
0x180088c00  test    eax, eax
0x180088c02  jns     loc_18008901E
0x180088c08  mov     edx, eax; int
0x180088c0a  mov     rcx, [rsi+28h]; this
0x180088c0e  call    ?SetResult@OperationEntry@EsimManager@LPA@@QEAAXJ@Z; LPA::EsimManager::OperationEntry::SetResult(long)
0x180088c13  mov     rcx, [rsi+28h]
0x180088c17  xor     al, al
0x180088c19  mov     edx, [rcx+0D4h]; struct _TP_TIMER **
0x180088c1f  test    r12b, dl
0x180088c22  jz      short loc_180088C32
0x180088c24  movzx   eax, al
0x180088c27  cmp     dword ptr [rcx+0D8h], 0
0x180088c2e  cmovnz  eax, r12d
0x180088c32  test    dl, 2
0x180088c35  jz      short loc_180088C40
0x180088c37  cmp     dword ptr [rcx+0DCh], 0
0x180088c3e  jnz     short loc_180088C5A
0x180088c40  test    al, al
0x180088c42  jnz     short loc_180088C5A
0x180088c44  movsd   xmm0, [rbp+70h+var_E0]
0x180088c49  movsd   qword ptr [rcx+0D4h], xmm0
0x180088c51  mov     eax, [rbp+70h+var_D8]
0x180088c54  mov     [rcx+0DCh], eax
0x180088c5a  mov     rcx, [rsi+28h]
0x180088c5e  add     rcx, 40h ; '@'; this
0x180088c62  call    ?CancelTimer@Util@LPA@@YAXAEAPEAU_TP_TIMER@@@Z; LPA::Util::CancelTimer(_TP_TIMER * &)
0x180088c67  mov     rax, [rsi+28h]
0x180088c6b  cmp     byte ptr [rax+58h], 0
0x180088c6f  jnz     loc_18008900E
0x180088c75  mov     rbx, [rsp+170h+var_108]
0x180088c7a  cmp     [r14+0D0h], rbx
0x180088c81  jz      loc_180088F71
0x180088c87  mov     rcx, [rbx+30h]
0x180088c8b  mov     eax, [rax+20h]
0x180088c8e  lea     rdi, aLpaEsimmanager_14; "LPA::EsimManager::CompleteOperation"
0x180088c95  lea     r15, aLpaserviceesim; "LpaServiceEsimManager"
0x180088c9c  cmp     [rcx+0B0h], eax
0x180088ca2  jz      loc_180088D28
0x180088ca8  mov     eax, cs:CallbackContext
0x180088cae  cmp     eax, 3
0x180088cb1  jbe     short loc_180088D28
0x180088cb3  mov     rdx, [rsi+28h]
0x180088cb7  mov     eax, [rdx+20h]
0x180088cba  mov     [rsp+170h+var_100], eax
0x180088cbe  mov     rax, [rbx+30h]
0x180088cc2  mov     ecx, [rax+0B0h]
0x180088cc8  mov     [rsp+170h+var_FC], ecx
0x180088ccc  mov     eax, [rdx+50h]
0x180088ccf  mov     [rsp+170h+var_110], eax
0x180088cd3  mov     [rsp+170h+var_108], rdx
0x180088cd8  mov     [rsp+170h+var_F8], rdi
0x180088cdd  mov     [rbp+70h+var_F0], r15
0x180088ce1  lea     rax, [rsp+170h+var_100]
0x180088ce6  mov     [rsp+170h+var_128], rax
0x180088ceb  lea     rax, [rsp+170h+var_FC]
0x180088cf0  mov     [rsp+170h+var_130], rax
0x180088cf5  lea     rax, [rsp+170h+var_110]
0x180088cfa  mov     [rsp+170h+var_138], rax
0x180088cff  lea     rax, [rsp+170h+var_108]
0x180088d04  mov     [rsp+170h+var_140], rax
0x180088d09  lea     rax, [rsp+170h+var_F8]
0x180088d0e  mov     [rsp+170h+var_148], rax
0x180088d13  lea     rax, [rbp+70h+var_F0]
0x180088d17  mov     [rsp+170h+var_150], rax
0x180088d1c  lea     rdx, byte_18012F2E3
0x180088d23  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U3@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@55@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180088d28  mov     eax, cs:CallbackContext
0x180088d2e  cmp     eax, 4
0x180088d31  jbe     loc_180088DC3
0x180088d37  mov     rdx, [rsi+28h]
0x180088d3b  mov     eax, [rdx+24h]
0x180088d3e  mov     [rsp+170h+var_110], eax
0x180088d42  mov     rax, [rbx+30h]
0x180088d46  mov     ecx, [rax+0B0h]
0x180088d4c  mov     [rsp+170h+var_FC], ecx
0x180088d50  mov     rax, [rbx+30h]
0x180088d54  mov     rcx, [rax+20h]
0x180088d58  mov     eax, [rcx+6Ch]
0x180088d5b  mov     [rsp+170h+var_100], eax
0x180088d5f  mov     eax, [rdx+50h]
0x180088d62  mov     dword ptr [rsp+170h+var_108], eax
0x180088d66  mov     [rbp+70h+var_F0], rdx
0x180088d6a  mov     [rsp+170h+var_F8], rdi
0x180088d6f  mov     [rbp+70h+var_E0], r15
0x180088d73  lea     rax, [rsp+170h+var_110]
0x180088d78  mov     [rsp+170h+var_120], rax
0x180088d7d  lea     rax, [rsp+170h+var_FC]
0x180088d82  mov     [rsp+170h+var_128], rax
0x180088d87  lea     rax, [rsp+170h+var_100]
0x180088d8c  mov     [rsp+170h+var_130], rax
0x180088d91  lea     rax, [rsp+170h+var_108]
0x180088d96  mov     [rsp+170h+var_138], rax
0x180088d9b  lea     rax, [rbp+70h+var_F0]
0x180088d9f  mov     [rsp+170h+var_140], rax
0x180088da4  lea     rax, [rsp+170h+var_F8]
0x180088da9  mov     [rsp+170h+var_148], rax
0x180088dae  lea     rax, [rbp+70h+var_E0]
0x180088db2  mov     [rsp+170h+var_150], rax
0x180088db7  lea     rdx, byte_18012F265
0x180088dbe  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U3@U3@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@555@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180088dc3  mov     rdx, [rsi+28h]
0x180088dc7  mov     edx, [rdx+50h]
0x180088dca  mov     rcx, [rbx+30h]
0x180088dce  call    ?SetOperationCompleted@EsimRecord@EsimManager@LPA@@QEAAXW4LPAESIMOPERATIONINTERNAL@3@J@Z; LPA::EsimManager::EsimRecord::SetOperationCompleted(LPA::LPAESIMOPERATIONINTERNAL,long)
0x180088dd3  xor     edx, edx; bool
0x180088dd5  mov     rcx, r14; this
0x180088dd8  call    ?ProcessAndBroadcastChanges@EsimManager@LPA@@AEAAX_N@Z; LPA::EsimManager::ProcessAndBroadcastChanges(bool)
0x180088ddd  mov     r9, [rsi+28h]
0x180088de1  lea     r8, [rbp+70h+var_E8]
0x180088de5  lea     rdx, [rbp+70h+var_E0]
0x180088de9  mov     rcx, r14
0x180088dec  call    ?TryFindEsimRecordBySlotId@EsimManager@LPA@@AEAA?AV?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@V?$unique_ptr@VEsimRecord@EsimManager@LPA@@U?$default_delete@VEsimRecord@EsimManager@LPA@@@std@@@std@@@std@@@std@@@std@@@std@@AEBKAEBU_GUID@@@Z; LPA::EsimManager::TryFindEsimRecordBySlotId(ulong const &,_GUID const &)
0x180088df1  mov     rbx, [rax]
0x180088df4  cmp     [r14+0D0h], rbx
0x180088dfb  jz      loc_180088EE7
0x180088e01  mov     rcx, [rbx+30h]
0x180088e05  call    ?GetEsimId@EsimRecord@EsimManager@LPA@@QEBAPEAY0CB@$$CBGXZ; LPA::EsimManager::EsimRecord::GetEsimId(void)
0x180088e0a  mov     r12, rax
0x180088e0d  test    rax, rax
0x180088e10  jz      loc_180088EEE
0x180088e16  mov     rcx, [r14+0B0h]
0x180088e1d  mov     rdx, [rcx]
0x180088e20  mov     rax, [rdx+60h]
0x180088e24  mov     rdx, r12
0x180088e27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180088e2c  test    al, al
0x180088e2e  jz      loc_180088EEE
0x180088e34  mov     rdx, r12
0x180088e37  lea     rcx, [rbp+70h+var_60]
0x180088e3b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180088e40  nop
0x180088e41  mov     rdi, [r14+80h]
0x180088e48  lea     rdx, [rbp+70h+var_60]
0x180088e4c  lea     rcx, [rbp+70h+var_D0]
0x180088e50  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180088e55  mov     [rbp+70h+var_B0], r14
0x180088e59  lea     rax, off_180106C08
0x180088e60  mov     [rbp+70h+var_A0], rax
0x180088e64  xorps   xmm0, xmm0
0x180088e67  movups  [rbp+70h+var_98], xmm0
0x180088e6b  mov     rax, qword ptr [rbp+70h+var_D0]
0x180088e6f  mov     qword ptr [rbp+70h+var_98], rax
0x180088e73  mov     rax, qword ptr [rbp+70h+var_D0+8]
0x180088e77  mov     qword ptr [rbp+70h+var_98+8], rax
0x180088e7b  mov     rax, qword ptr [rbp+70h+var_C0]
0x180088e7f  mov     qword ptr [rbp+70h+var_88], rax
0x180088e83  mov     rax, qword ptr [rbp+70h+var_C0+8]
0x180088e87  mov     qword ptr [rbp+70h+var_88+8], rax
0x180088e8b  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x180088e93  movdqu  [rbp+70h+var_C0], xmm0
0x180088e98  xor     eax, eax
0x180088e9a  mov     word ptr [rbp+70h+var_D0], ax
0x180088e9e  mov     [rbp+70h+var_78], r14
0x180088ea2  lea     rax, [rbp+70h+var_A0]
0x180088ea6  mov     [rbp+70h+var_68], rax
0x180088eaa  lea     rdx, [rbp+70h+var_A0]
0x180088eae  mov     rcx, rdi
0x180088eb1  call    ?EnQueue@MessageDispatcher@@QEAAJ$$QEAV?$function@$$A6AXXZ@std@@@Z; MessageDispatcher::EnQueue(std::function<void (void)> &&)
0x180088eb6  nop
0x180088eb7  lea     rcx, [rbp+70h+var_A0]
0x180088ebb  call    ??1_lambda_1_@?1???$_MakeTToUnitFunc@Vvalue@json@web@@@details@pplx@@YA?AV?$function@$$A6AEVvalue@json@web@@@Z@std@@AEBV?$function@$$A6AXVvalue@json@web@@@Z@4@@Z@QEAA@XZ; `pplx::details::_MakeTToUnitFunc<web::json::value>(std::function<void (web::json::value)> const &)'::`2'::_lambda_1_::~_lambda_1_(void)
0x180088ec0  nop
0x180088ec1  lea     rcx, [rbp+70h+var_D0]
0x180088ec5  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180088eca  nop
0x180088ecb  lea     rcx, [rbp+70h+var_60]
0x180088ecf  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180088ed4  mov     r12d, 1
0x180088eda  cmp     [r14+0D0h], rbx
0x180088ee1  jnz     loc_180088FF1
0x180088ee7  xor     edx, edx
0x180088ee9  jmp     loc_180089005
0x180088eee  mov     rcx, [rbx+30h]; this
0x180088ef2  call    ?IsProcessingEs10bNotifications@EsimRecord@EsimManager@LPA@@QEBA_NXZ; LPA::EsimManager::EsimRecord::IsProcessingEs10bNotifications(void)
0x180088ef7  test    al, al
0x180088ef9  jnz     short loc_180088ED4
0x180088efb  mov     r8, rcx; struct LPA::EsimManager::EsimRecord *
0x180088efe  mov     rdx, [rsi+28h]; struct _GUID *
0x180088f02  mov     rcx, r14; this
0x180088f05  call    ?RetrieveEs10bNotificationsList@EsimManager@LPA@@AEAAJAEBU_GUID@@PEAVEsimRecord@12@@Z; LPA::EsimManager::RetrieveEs10bNotificationsList(_GUID const &,LPA::EsimManager::EsimRecord *)
0x180088f0a  mov     ecx, eax
0x180088f0c  test    eax, eax
0x180088f0e  js      short loc_180088F1A
0x180088f10  mov     rcx, r14; this
0x180088f13  call    ?CalculateNumberOfBackgroundTasks@EsimManager@LPA@@AEAAXXZ; LPA::EsimManager::CalculateNumberOfBackgroundTasks(void)
0x180088f18  jmp     short loc_180088ED4
0x180088f1a  mov     eax, cs:CallbackContext
0x180088f20  cmp     eax, 3
0x180088f23  jbe     short loc_180088ED4
0x180088f25  mov     rax, [rsi+28h]
0x180088f29  mov     [rbp+70h+var_E0], rax
0x180088f2d  mov     dword ptr [rsp+170h+var_108], ecx
0x180088f31  mov     [rbp+70h+var_F0], rdi
0x180088f35  mov     [rsp+170h+var_F8], r15
0x180088f3a  lea     rax, [rbp+70h+var_E0]
0x180088f3e  mov     [rsp+170h+var_138], rax
0x180088f43  lea     rax, [rsp+170h+var_108]
0x180088f48  mov     [rsp+170h+var_140], rax
0x180088f4d  lea     rax, [rbp+70h+var_F0]
0x180088f51  mov     [rsp+170h+var_148], rax
0x180088f56  lea     rax, [rsp+170h+var_F8]
0x180088f5b  mov     [rsp+170h+var_150], rax
0x180088f60  lea     rdx, byte_18012F219
0x180088f67  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByRef@$0BA@@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByRef@$0BA@@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByRef<16> const &)
0x180088f6c  jmp     loc_180088ED4
0x180088f71  mov     eax, cs:CallbackContext
0x180088f77  cmp     eax, 3
0x180088f7a  jbe     loc_180088EDA
0x180088f80  mov     rcx, [rsi+28h]
0x180088f84  mov     eax, [rcx+24h]
0x180088f87  mov     dword ptr [rsp+170h+var_108], eax
0x180088f8b  mov     eax, [rcx+0D0h]
0x180088f91  mov     [rsp+170h+var_110], eax
0x180088f95  mov     [rbp+70h+var_E0], rcx
0x180088f99  lea     rdi, aLpaEsimmanager_14; "LPA::EsimManager::CompleteOperation"
0x180088fa0  mov     [rbp+70h+var_F0], rdi
0x180088fa4  lea     r15, aLpaserviceesim; "LpaServiceEsimManager"
0x180088fab  mov     [rsp+170h+var_F8], r15
0x180088fb0  lea     rax, [rsp+170h+var_108]
0x180088fb5  mov     [rsp+170h+var_130], rax
0x180088fba  lea     rax, [rsp+170h+var_110]
0x180088fbf  mov     [rsp+170h+var_138], rax
0x180088fc4  lea     rax, [rbp+70h+var_E0]
0x180088fc8  mov     [rsp+170h+var_140], rax
0x180088fcd  lea     rax, [rbp+70h+var_F0]
0x180088fd1  mov     [rsp+170h+var_148], rax
0x180088fd6  lea     rax, [rsp+170h+var_F8]
0x180088fdb  mov     [rsp+170h+var_150], rax
0x180088fe0  lea     rdx, word_18012F1C2
0x180088fe7  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180088fec  jmp     loc_180088EDA
0x180088ff1  mov     rax, [rbx+30h]
0x180088ff5  mov     rcx, [rax+20h]
0x180088ff9  xor     edx, edx
0x180088ffb  cmp     [rcx+70h], r12d
0x180088fff  setnz   dl
0x180089002  add     edx, r12d
0x180089005  mov     rcx, [rsi+28h]
0x180089009  call    ?NotifyCompletionHandler@OperationEntry@EsimManager@LPA@@QEBAXW4LPAESIMINSLOTINTERNAL@3@@Z; LPA::EsimManager::OperationEntry::NotifyCompletionHandler(LPA::LPAESIMINSLOTINTERNAL)
0x18008900e  lea     rcx, [r14+0F0h]
0x180089015  mov     rdx, [r13+0]
0x180089019  call    ?_Erase_unchecked@?$_Tree@V?$_Tmap_traits@KV?$unique_ptr@VOperationEntry@EsimManager@LPA@@U?$default_delete@VOperationEntry@EsimManager@LPA@@@std@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$unique_ptr@VOperationEntry@EsimManager@LPA@@U?$default_delete@VOperationEntry@EsimManager@LPA@@@std@@@std@@@std@@@2@$0A@@std@@@std@@AEAAPEAU?$_Tree_node@U?$pair@$$CBKV?$unique_ptr@VOperationEntry@EsimManager@LPA@@U?$default_delete@VOperationEntry@EsimManager@LPA@@@std@@@std@@@std@@PEAX@2@V?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKV?$unique_ptr@VOperationEntry@EsimManager@LPA@@U?$default_delete@VOperationEntry@EsimManager@LPA@@@std@@@std@@@std@@@std@@@std@@U_Iterator_base0@2@@2@@Z; std::_Tree<std::_Tmap_traits<ulong,std::unique_ptr<LPA::EsimManager::OperationEntry>,std::less<ulong>,std::allocator<std::pair<ulong const,std::unique_ptr<LPA::EsimManager::OperationEntry>>>,0>>::_Erase_unchecked(std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<ulong const,std::unique_ptr<LPA::EsimManager::OperationEntry>>>>,std::_Iterator_base0>)
0x18008901e  mov     rcx, [rbp+70h+var_40]
0x180089022  xor     rcx, rsp; StackCookie
0x180089025  call    __security_check_cookie
0x18008902a  mov     rbx, [rsp+170h+arg_10]
0x180089032  add     rsp, 140h
0x180089039  pop     r15
0x18008903b  pop     r14
0x18008903d  pop     r13
0x18008903f  pop     r12
0x180089041  pop     rdi
0x180089042  pop     rsi
0x180089043  pop     rbp
  ... truncated ...
```
