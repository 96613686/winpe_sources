# LPA::EsimManager::ProcessWwapiSimUpdate(_GUID const &,ulong const &,bool,bool,_WWAN_READY_STATE const &,ushort const *,ushort const (&)[21])

- ea: `0x180092f68`
- end: `0x180093475`
- name: `?ProcessWwapiSimUpdate@EsimManager@LPA@@AEAAXAEBU_GUID@@AEBK_N2AEBW4_WWAN_READY_STATE@@PEBGAEAY0BF@$$CBG@Z`
- size: `1293`
- prototype: `void __usercall(LPA::EsimManager *__hidden this@<rcx>, const struct _GUID *@<rdx>, const unsigned int *@<r8>, bool@<r9b>, bool, const enum _WWAN_READY_STATE *, const unsigned __int16 *, const unsigned __int16 (*)[21])`
- caller_count: `3`
- callee_count: `21`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180090580`
- `0x180090860`
- `0x180090d80`

## callees

- `0x180004c84`
- `0x180005364`
- `0x1800709e4`
- `0x180071840`
- `0x180071a8c`
- `0x180081618`
- `0x180081678`
- `0x1800817c8`
- `0x180083a2c`
- `0x180083f60`
- `0x180085904`
- `0x180088b48`
- `0x18008b70c`
- `0x18008c060`
- `0x18008c4e0`
- `0x1800913ec`
- `0x1800925e4`
- `0x180092f68`
- `0x180095df0`
- `0x180095fd0`
- `0x180101010`

## string_xrefs

- `0x180092fbb`: `LpaServiceEsimManager`
- `0x180093337`: `LpaServiceEsimManager`
- `0x180092fb4`: `LPA::EsimManager::ProcessWwapiSimUpdate`
- `0x18009332c`: `LPA::EsimManager::ProcessWwapiSimUpdate`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall LPA::EsimManager::ProcessWwapiSimUpdate(
        LPA::EsimManager *this,
        const struct _GUID *a2,
        unsigned int *a3,
        unsigned __int8 a4,
        bool a5,
        const enum _WWAN_READY_STATE *a6,
        unsigned __int16 *a7,
        const unsigned __int16 (*a8)[21])
{
  const enum _WWAN_READY_STATE *v11; // r12
  bool v12; // si
  bool v13; // di
  __int64 v14; // rbx
  LPA::EsimManager::EsimRecord *v15; // r9
  __int64 v16; // rdx
  __int64 v17; // rdx
  int v18; // r8d
  __int64 v19; // r9
  int v20; // eax
  __int64 (__fastcall ***v21)(_QWORD, const struct _GUID *, __int64 *, __int64, unsigned int *); // rsi
  __int64 (__fastcall *v22)(_QWORD, const struct _GUID *, __int64 *, __int64, unsigned int *); // rdi
  __int64 v23; // rax
  int v24; // edi
  int v25; // eax
  __int64 *v26; // rbx
  __int64 v27; // rax
  __int64 v28; // r9
  LPA::EsimManager::EsimRecord *v29; // r8
  bool IsBusy; // al
  __int64 v31; // r8
  __int64 v32; // rsi
  __int64 (__fastcall *v33)(__int64, const struct _GUID *, _QWORD, __int64, unsigned int *); // rdi
  __int64 v34; // rax
  const struct _GUID **v35; // rsi
  int v36; // r9d
  const struct _GUID *v37; // rdi
  int v38; // eax
  __int64 *v39; // rbx
  __int64 v40; // rax
  int v41; // [rsp+38h] [rbp-91h]
  int v42; // [rsp+70h] [rbp-59h] BYREF
  int v43; // [rsp+74h] [rbp-55h] BYREF
  const struct _GUID *v44; // [rsp+78h] [rbp-51h] BYREF
  const char *v45; // [rsp+80h] [rbp-49h] BYREF
  std::_Ref_count_base *v46; // [rsp+88h] [rbp-41h]
  unsigned int v47; // [rsp+90h] [rbp-39h] BYREF
  int v48; // [rsp+94h] [rbp-35h] BYREF
  BOOL v49; // [rsp+98h] [rbp-31h] BYREF
  const char *v50; // [rsp+A0h] [rbp-29h] BYREF
  const char *v51; // [rsp+A8h] [rbp-21h] BYREF
  const char *v52; // [rsp+B0h] [rbp-19h] BYREF
  std::_Ref_count_base *v53; // [rsp+B8h] [rbp-11h]
  const struct _GUID *v54; // [rsp+C0h] [rbp-9h] BYREF
  __int64 v55; // [rsp+110h] [rbp+47h] BYREF
  unsigned int v56; // [rsp+128h] [rbp+5Fh] BYREF

  v11 = a6;
  v12 = a5;
  v13 = a4 && !a5 && *(_DWORD *)a6 != 2;
  if ( (unsigned int)CallbackContext > 4 )
  {
    v56 = *a3;
    LODWORD(v55) = *(_DWORD *)a6;
    v44 = a2;
    v42 = a5;
    v43 = a4;
    v51 = "LPA::EsimManager::ProcessWwapiSimUpdate";
    v50 = "LpaServiceEsimManager";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      (unsigned int)"LPA::EsimManager::ProcessWwapiSimUpdate",
      (unsigned int)&word_18012EC2E,
      (_DWORD)a3,
      a4,
      (__int64)&v50,
      (__int64)&v51,
      (__int64)&v43,
      (__int64)&v42,
      (__int64)&v44,
      (__int64)&v55,
      (__int64)&v56);
  }
  LPA::EsimManager::TryFindEsimRecordBySlotId(this, &v55, a3, a2);
  v14 = v55;
  if ( v55 == *((_QWORD *)this + 26) )
  {
    if ( !v13 )
      return;
    LPA::EsimManager::HandleNewEsimDetected(this, a2, a3, v11, a7, a8);
    goto LABEL_42;
  }
  if ( v12 )
    *(_BYTE *)(*(_QWORD *)(v55 + 48) + 12LL) = 1;
  v15 = *(LPA::EsimManager::EsimRecord **)(v14 + 48);
  if ( !v13 )
  {
    v16 = *((_QWORD *)v15 + 4);
    if ( (*(_BYTE *)(v16 + 4) & 1) == 0 || (*(_BYTE *)(v16 + 8) & 8) == 0 || *(_DWORD *)(v16 + 100) != 3 )
    {
      if ( LPA::EsimManager::EsimRecord::IsBusy(*(LPA::EsimManager::EsimRecord **)(v14 + 48))
        && *(_DWORD *)(v17 + 100) == v18 )
      {
        v20 = *(_DWORD *)(v19 + 180);
        if ( v20 != -1 )
          *(_DWORD *)(v19 + 180) = v20 + 1;
      }
      *(_DWORD *)(v17 + 100) = v18;
      *(_DWORD *)(*(_QWORD *)(v19 + 32) + 8LL) |= 8u;
      *(_DWORD *)(*(_QWORD *)(v19 + 32) + 4LL) |= 1u;
      *(_BYTE *)(v19 + 3) = 1;
    }
    *(_WORD *)(*(_QWORD *)(v14 + 48) + 10LL) = 0;
    *(_BYTE *)(*(_QWORD *)(v14 + 48) + 5LL) = 0;
    if ( !*(_QWORD *)(*(_QWORD *)(v14 + 48) + 64LL) )
      goto LABEL_42;
    v56 = 0;
    v21 = (__int64 (__fastcall ***)(_QWORD, const struct _GUID *, __int64 *, __int64, unsigned int *))*((_QWORD *)this + 20);
    v22 = **v21;
    std::enable_shared_from_this<LPA::EnterpriseManager>::shared_from_this((char *)this + 88, &v52);
    v23 = std::weak_ptr<LPA::LpdCompletionHandler>::weak_ptr<LPA::LpdCompletionHandler>(&v45);
    LODWORD(v55) = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v14 + 48) + 32LL) + 108LL);
    v24 = v22(v21, a2, &v55, v23, &v56);
    if ( v53 )
      std::_Ref_count_base::_Decref(v53);
    if ( v24 != -2147483638 )
      goto LABEL_42;
    LODWORD(v55) = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v14 + 48) + 32LL) + 108LL);
    v25 = std::enable_shared_from_this<LPA::EnterpriseManager>::shared_from_this((char *)this + 88, &v45);
    v26 = (__int64 *)std::make_unique<LPA::EsimManager::OperationEntry,std::shared_ptr<LPA::EsimManager>,unsigned long &,_GUID const &,unsigned long,0>(
                       (unsigned int)&v44,
                       v25,
                       (unsigned int)&v56,
                       (_DWORD)a2,
                       (__int64)&v55);
    v27 = std::map<unsigned long,std::unique_ptr<LPA::EsimManager::OperationEntry>>::_Try_emplace<unsigned long const &,>(
            (char *)this + 240,
            &v52,
            &v56);
    std::unique_ptr<LPA::EsimManager::OperationEntry>::operator=<std::default_delete<LPA::EsimManager::OperationEntry>,0>(
      (__int64 *)(*(_QWORD *)v27 + 40LL),
      v26);
    std::unique_ptr<LPA::EsimManager::OperationEntry>::~unique_ptr<LPA::EsimManager::OperationEntry>(&v44);
    goto LABEL_40;
  }
  v56 = 0;
  v42 = 3;
  LODWORD(v55) = 3;
  LPA::EsimManager::EsimRecord::GetTrueState(v15, (enum LPAESIMSTATE *)&v42);
  LPA::EsimManager::EsimRecord::ParseWwanReadyDetails(v28, *(unsigned int *)v11, (const unsigned __int16 *)a8);
  LPA::EsimManager::EsimRecord::GetTrueState(*(LPA::EsimManager::EsimRecord **)(v14 + 48), (enum LPAESIMSTATE *)&v55);
  if ( (_DWORD)v55 || !v42 )
  {
    IsBusy = LPA::EsimManager::EsimRecord::IsBusy(v29);
    if ( !*(_BYTE *)((-(__int64)IsBusy & 0xFFFFFFFFFFFFFFFDuLL) + v31 + 4) )
      goto LABEL_42;
  }
  v32 = *((_QWORD *)this + 18);
  v33 = *(__int64 (__fastcall **)(__int64, const struct _GUID *, _QWORD, __int64, unsigned int *))(*(_QWORD *)(v32 + 16)
                                                                                                 + 24LL);
  std::enable_shared_from_this<LPA::EnterpriseManager>::shared_from_this((char *)this + 88, &v52);
  v34 = std::weak_ptr<LPA::ApduHelperEs10cCompletionHandler>::weak_ptr<LPA::ApduHelperEs10cCompletionHandler>(&v45);
  LODWORD(v55) = v33(v32 + 16, a2, *a3, v34, &v56);
  if ( v53 )
    std::_Ref_count_base::_Decref(v53);
  v43 = *(_DWORD *)(*(_QWORD *)(v14 + 48) + 176LL);
  v35 = (const struct _GUID **)((char *)this + 240);
  std::_Tree<std::_Tmap_traits<unsigned long,std::shared_ptr<LPA::Lpd::DownloadInstance>,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,std::shared_ptr<LPA::Lpd::DownloadInstance>>>,0>>::find(
    (char *)this + 240,
    &v44,
    &v43);
  v37 = v44;
  if ( (unsigned int)CallbackContext > 4 )
  {
    v43 = *(_DWORD *)(*(_QWORD *)(v14 + 48) + 176LL);
    v42 = v56;
    v47 = *a3;
    v48 = v55;
    v49 = *v35 != v44;
    LODWORD(v50) = *(_DWORD *)v11;
    v54 = a2;
    LODWORD(v51) = *(_DWORD *)(*(_QWORD *)(v14 + 48) + 180LL);
    v52 = "LPA::EsimManager::ProcessWwapiSimUpdate";
    v45 = "LpaServiceEsimManager";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      (_DWORD)v51,
      (unsigned int)&byte_18012EB97,
      (_DWORD)CallbackContext,
      v36,
      (__int64)&v45,
      (__int64)&v52,
      (__int64)&v51,
      (__int64)&v54,
      (__int64)&v50,
      (__int64)&v49,
      (__int64)&v48,
      (__int64)&v47,
      (__int64)&v42,
      (__int64)&v43);
  }
  if ( *v35 != v37 )
  {
    if ( (int)v55 < 0 )
    {
      LPA::EsimManager::CompleteOperation(this, &v44);
    }
    else
    {
      LOBYTE(v41) = 0;
      LOBYTE(v36) = 1;
      LPA::EsimManager::TransferOperationToNewTransactionId(
        (_DWORD)this,
        (unsigned int)&v44,
        (_DWORD)a2,
        v36,
        0,
        0,
        0,
        v41,
        v56);
    }
    goto LABEL_42;
  }
  if ( (int)v55 >= 0 )
  {
    v38 = std::enable_shared_from_this<LPA::EnterpriseManager>::shared_from_this((char *)this + 88, &v45);
    v39 = (__int64 *)std::make_unique<LPA::EsimManager::OperationEntry,std::shared_ptr<LPA::EsimManager>,unsigned long &,_GUID const &,unsigned long,0>(
                       (unsigned int)&v55,
                       v38,
                       (unsigned int)&v56,
                       (_DWORD)a2,
                       (__int64)a3);
    v40 = std::map<unsigned long,std::unique_ptr<LPA::EsimManager::OperationEntry>>::_Try_emplace<unsigned long const &,>(
            (char *)this + 240,
            &v52,
            &v56);
    std::unique_ptr<LPA::EsimManager::OperationEntry>::operator=<std::default_delete<LPA::EsimManager::OperationEntry>,0>(
      (__int64 *)(*(_QWORD *)v40 + 40LL),
      v39);
    std::unique_ptr<LPA::EsimManager::OperationEntry>::~unique_ptr<LPA::EsimManager::OperationEntry>(&v55);
LABEL_40:
    if ( v46 )
      std::_Ref_count_base::_Decref(v46);
  }
LABEL_42:
  LPA::EsimManager::ProcessAndBroadcastChanges(this, 0);
}

```

## disassembly

```asm
0x180092f68  mov     [rsp-8+arg_8], rbx
0x180092f6d  push    rbp
0x180092f6e  push    rsi
0x180092f6f  push    rdi
0x180092f70  push    r12
0x180092f72  push    r13
0x180092f74  push    r14
0x180092f76  push    r15
0x180092f78  lea     rbp, [rsp-7]
0x180092f7d  sub     rsp, 0D0h
0x180092f84  mov     r13, r8
0x180092f87  mov     r15, rdx
0x180092f8a  mov     r14, rcx
0x180092f8d  mov     r12, [rbp+37h+arg_28]
0x180092f91  movzx   esi, [rbp+37h+arg_20]
0x180092f95  test    r9b, r9b
0x180092f98  jz      short loc_180092FAB
0x180092f9a  test    sil, sil
0x180092f9d  jnz     short loc_180092FAB
0x180092f9f  cmp     dword ptr [r12], 2
0x180092fa4  jz      short loc_180092FAB
0x180092fa6  mov     dil, 1
0x180092fa9  jmp     short loc_180092FAE
0x180092fab  xor     dil, dil
0x180092fae  mov     eax, cs:CallbackContext
0x180092fb4  lea     rcx, aLpaEsimmanager_1; "LPA::EsimManager::ProcessWwapiSimUpdate"
0x180092fbb  lea     rdx, aLpaserviceesim; "LpaServiceEsimManager"
0x180092fc2  cmp     eax, 4
0x180092fc5  jbe     short loc_180093035
0x180092fc7  mov     eax, [r8]
0x180092fca  mov     [rbp+37h+arg_18], eax
0x180092fcd  mov     eax, [r12]
0x180092fd1  mov     dword ptr [rbp+37h+arg_0], eax
0x180092fd4  mov     [rbp+37h+var_88], r15
0x180092fd8  mov     [rbp+37h+var_90], esi
0x180092fdb  movzx   eax, r9b
0x180092fdf  mov     [rbp+37h+var_8C], eax
0x180092fe2  mov     [rbp+37h+var_58], rcx
0x180092fe6  mov     [rbp+37h+var_60], rdx
0x180092fea  lea     rax, [rbp+37h+arg_18]
0x180092fee  mov     [rsp+100h+var_B0], rax
0x180092ff3  lea     rax, [rbp+37h+arg_0]
0x180092ff7  mov     [rsp+100h+var_B8], rax
0x180092ffc  lea     rax, [rbp+37h+var_88]
0x180093000  mov     [rsp+100h+var_C0], rax
0x180093005  lea     rax, [rbp+37h+var_90]
0x180093009  mov     [rsp+100h+var_C8], rax
0x18009300e  lea     rax, [rbp+37h+var_8C]
0x180093012  mov     [rsp+100h+var_D0], rax
0x180093017  lea     rax, [rbp+37h+var_58]
0x18009301b  mov     [rsp+100h+var_D8], rax
0x180093020  lea     rax, [rbp+37h+var_60]
0x180093024  mov     [rsp+100h+var_E0], rax
0x180093029  lea     rdx, word_18012EC2E
0x180093030  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U2@U?$_tlgWrapperByRef@$0BA@@@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@4AEBU?$_tlgWrapperByRef@$0BA@@@44@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180093035  mov     r9, r15
0x180093038  mov     r8, r13
0x18009303b  lea     rdx, [rbp+37h+arg_0]
0x18009303f  mov     rcx, r14
0x180093042  call    ?TryFindEsimRecordBySlotId@EsimManager@LPA@@AEAA?AV?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@V?$unique_ptr@VEsimRecord@EsimManager@LPA@@U?$default_delete@VEsimRecord@EsimManager@LPA@@@std@@@std@@@std@@@std@@@std@@@std@@AEBKAEBU_GUID@@@Z; LPA::EsimManager::TryFindEsimRecordBySlotId(ulong const &,_GUID const &)
0x180093047  mov     rbx, [rbp+37h+arg_0]
0x18009304b  cmp     rbx, [r14+0D0h]
0x180093052  jnz     short loc_180093085
0x180093054  test    dil, dil
0x180093057  jz      loc_18009345A
0x18009305d  mov     rax, [rbp+37h+arg_38]
0x180093061  mov     [rsp+100h+var_D8], rax; unsigned __int16 (*)[21]
0x180093066  mov     rax, [rbp+37h+arg_30]
0x18009306a  mov     [rsp+100h+var_E0], rax; unsigned __int16 *
0x18009306f  mov     r9, r12; enum _WWAN_READY_STATE *
0x180093072  mov     r8, r13; unsigned int *
0x180093075  mov     rdx, r15; struct _GUID *
0x180093078  mov     rcx, r14; this
0x18009307b  call    ?HandleNewEsimDetected@EsimManager@LPA@@AEAAJAEBU_GUID@@AEBKAEBW4_WWAN_READY_STATE@@PEBGAEAY0BF@$$CBG@Z; LPA::EsimManager::HandleNewEsimDetected(_GUID const &,ulong const &,_WWAN_READY_STATE const &,ushort const *,ushort const (&)[21])
0x180093080  jmp     loc_180093450
0x180093085  test    sil, sil
0x180093088  jz      short loc_180093092
0x18009308a  mov     rax, [rbx+30h]
0x18009308e  mov     byte ptr [rax+0Ch], 1
0x180093092  mov     r9, [rbx+30h]
0x180093096  xor     esi, esi
0x180093098  lea     r8d, [rsi+3]
0x18009309c  test    dil, dil
0x18009309f  jnz     loc_1800931FA
0x1800930a5  mov     rdx, [r9+20h]
0x1800930a9  test    byte ptr [rdx+4], 1
0x1800930ad  jz      short loc_1800930BB
0x1800930af  test    byte ptr [rdx+8], 8
0x1800930b3  jz      short loc_1800930BB
0x1800930b5  cmp     [rdx+64h], r8d
0x1800930b9  jz      short loc_1800930FB
0x1800930bb  mov     rcx, r9; this
0x1800930be  call    ?IsBusy@EsimRecord@EsimManager@LPA@@QEBA_NXZ; LPA::EsimManager::EsimRecord::IsBusy(void)
0x1800930c3  test    al, al
0x1800930c5  jz      short loc_1800930E2
0x1800930c7  cmp     [rdx+64h], r8d
0x1800930cb  jnz     short loc_1800930E2
0x1800930cd  mov     eax, [r9+0B4h]
0x1800930d4  cmp     eax, 0FFFFFFFFh
0x1800930d7  jnb     short loc_1800930E2
0x1800930d9  inc     eax
0x1800930db  mov     [r9+0B4h], eax
0x1800930e2  mov     [rdx+64h], r8d
0x1800930e6  mov     rax, [r9+20h]
0x1800930ea  or      dword ptr [rax+8], 8
0x1800930ee  mov     rax, [r9+20h]
0x1800930f2  or      dword ptr [rax+4], 1
0x1800930f6  mov     byte ptr [r9+3], 1
0x1800930fb  mov     rax, [rbx+30h]
0x1800930ff  mov     [rax+0Ah], si
0x180093103  mov     rax, [rbx+30h]
0x180093107  mov     [rax+5], sil
0x18009310b  mov     rax, [rbx+30h]
0x18009310f  cmp     [rax+40h], rsi
0x180093113  jz      loc_180093450
0x180093119  mov     [rbp+37h+arg_18], esi
0x18009311c  mov     rsi, [r14+0A0h]
0x180093123  mov     rax, [rsi]
0x180093126  mov     rdi, [rax]
0x180093129  lea     rdx, [rbp+37h+var_50]
0x18009312d  lea     rcx, [r14+58h]
0x180093131  call    ?shared_from_this@?$enable_shared_from_this@VEnterpriseManager@LPA@@@std@@QEAA?AV?$shared_ptr@VEnterpriseManager@LPA@@@2@XZ; std::enable_shared_from_this<LPA::EnterpriseManager>::shared_from_this(void)
0x180093136  nop
0x180093137  mov     rdx, rax
0x18009313a  lea     rcx, [rbp+37h+var_80]
0x18009313e  call    ??$?0VEsimManager@LPA@@$0A@@?$weak_ptr@ULpdCompletionHandler@LPA@@@std@@QEAA@AEBV?$shared_ptr@VEsimManager@LPA@@@1@@Z; std::weak_ptr<LPA::LpdCompletionHandler>::weak_ptr<LPA::LpdCompletionHandler>(std::shared_ptr<LPA::EsimManager> const &)
0x180093143  mov     rdx, [rbx+30h]
0x180093147  mov     r8, [rdx+20h]
0x18009314b  mov     edx, [r8+6Ch]
0x18009314f  mov     dword ptr [rbp+37h+arg_0], edx
0x180093152  lea     rcx, [rbp+37h+arg_18]
0x180093156  mov     [rsp+100h+var_E0], rcx
0x18009315b  mov     r9, rax
0x18009315e  lea     r8, [rbp+37h+arg_0]
0x180093162  mov     rdx, r15
0x180093165  mov     rcx, rsi
0x180093168  mov     rax, rdi
0x18009316b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180093170  mov     edi, eax
0x180093172  mov     rcx, [rbp+37h+var_48]; this
0x180093176  test    rcx, rcx
0x180093179  jz      short loc_180093180
0x18009317b  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180093180  cmp     edi, 8000000Ah
0x180093186  jnz     loc_180093450
0x18009318c  mov     rax, [rbx+30h]
0x180093190  mov     rdx, [rax+20h]
0x180093194  mov     eax, [rdx+6Ch]
0x180093197  mov     dword ptr [rbp+37h+arg_0], eax
0x18009319a  lea     rdx, [rbp+37h+var_80]
0x18009319e  lea     rcx, [r14+58h]
0x1800931a2  call    ?shared_from_this@?$enable_shared_from_this@VEnterpriseManager@LPA@@@std@@QEAA?AV?$shared_ptr@VEnterpriseManager@LPA@@@2@XZ; std::enable_shared_from_this<LPA::EnterpriseManager>::shared_from_this(void)
0x1800931a7  nop
0x1800931a8  lea     rcx, [rbp+37h+arg_0]
0x1800931ac  mov     [rsp+100h+var_E0], rcx
0x1800931b1  mov     r9, r15
0x1800931b4  lea     r8, [rbp+37h+arg_18]
0x1800931b8  mov     rdx, rax
0x1800931bb  lea     rcx, [rbp+37h+var_88]
0x1800931bf  call    ??$make_unique@VOperationEntry@EsimManager@LPA@@V?$shared_ptr@VEsimManager@LPA@@@std@@AEAKAEBU_GUID@@K$0A@@std@@YA?AV?$unique_ptr@VOperationEntry@EsimManager@LPA@@U?$default_delete@VOperationEntry@EsimManager@LPA@@@std@@@0@$$QEAV?$shared_ptr@VEsimManager@LPA@@@0@AEAKAEBU_GUID@@$$QEAK@Z; std::make_unique<LPA::EsimManager::OperationEntry,std::shared_ptr<LPA::EsimManager>,ulong &,_GUID const &,ulong,0>(std::shared_ptr<LPA::EsimManager> &&,ulong &,_GUID const &,ulong &&)
0x1800931c4  mov     rbx, rax
0x1800931c7  lea     rcx, [r14+0F0h]
0x1800931ce  lea     r8, [rbp+37h+arg_18]
0x1800931d2  lea     rdx, [rbp+37h+var_50]
0x1800931d6  call    ??$_Try_emplace@AEBK$$V@?$map@KV?$unique_ptr@VOperationEntry@EsimManager@LPA@@U?$default_delete@VOperationEntry@EsimManager@LPA@@@std@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$unique_ptr@VOperationEntry@EsimManager@LPA@@U?$default_delete@VOperationEntry@EsimManager@LPA@@@std@@@std@@@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBKV?$unique_ptr@VOperationEntry@EsimManager@LPA@@U?$default_delete@VOperationEntry@EsimManager@LPA@@@std@@@std@@@std@@PEAX@std@@_N@1@AEBK@Z; std::map<ulong,std::unique_ptr<LPA::EsimManager::OperationEntry>>::_Try_emplace<ulong const &,>(ulong const &)
0x1800931db  mov     rcx, [rax]
0x1800931de  add     rcx, 28h ; '('
0x1800931e2  mov     rdx, rbx
0x1800931e5  call    ??$?4U?$default_delete@VOperationEntry@EsimManager@LPA@@@std@@$0A@@?$unique_ptr@VOperationEntry@EsimManager@LPA@@U?$default_delete@VOperationEntry@EsimManager@LPA@@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::unique_ptr<LPA::EsimManager::OperationEntry>::operator=<std::default_delete<LPA::EsimManager::OperationEntry>,0>(std::unique_ptr<LPA::EsimManager::OperationEntry> &&)
0x1800931ea  nop
0x1800931eb  lea     rcx, [rbp+37h+var_88]
0x1800931ef  call    ??1?$unique_ptr@VOperationEntry@EsimManager@LPA@@U?$default_delete@VOperationEntry@EsimManager@LPA@@@std@@@std@@QEAA@XZ; std::unique_ptr<LPA::EsimManager::OperationEntry>::~unique_ptr<LPA::EsimManager::OperationEntry>(void)
0x1800931f4  nop
0x1800931f5  jmp     loc_180093442
0x1800931fa  mov     [rbp+37h+arg_18], esi
0x1800931fd  mov     [rbp+37h+var_90], r8d
0x180093201  mov     dword ptr [rbp+37h+arg_0], r8d
0x180093205  lea     rdx, [rbp+37h+var_90]; enum LPAESIMSTATE *
0x180093209  mov     rcx, r9; this
0x18009320c  call    ?GetTrueState@EsimRecord@EsimManager@LPA@@QEBAJAEAW4LPAESIMSTATE@@@Z; LPA::EsimManager::EsimRecord::GetTrueState(LPAESIMSTATE &)
0x180093211  mov     r8, [rbp+37h+arg_38]
0x180093215  mov     edx, [r12]
0x180093219  mov     rcx, r9
0x18009321c  call    ?ParseWwanReadyDetails@EsimRecord@EsimManager@LPA@@QEAAXW4_WWAN_READY_STATE@@AEAY0BF@$$CBG@Z; LPA::EsimManager::EsimRecord::ParseWwanReadyDetails(_WWAN_READY_STATE,ushort const (&)[21])
0x180093221  mov     r8, [rbx+30h]
0x180093225  lea     rdx, [rbp+37h+arg_0]; enum LPAESIMSTATE *
0x180093229  mov     rcx, r8; this
0x18009322c  call    ?GetTrueState@EsimRecord@EsimManager@LPA@@QEBAJAEAW4LPAESIMSTATE@@@Z; LPA::EsimManager::EsimRecord::GetTrueState(LPAESIMSTATE &)
0x180093231  cmp     dword ptr [rbp+37h+arg_0], esi
0x180093234  jnz     short loc_18009323B
0x180093236  cmp     [rbp+37h+var_90], esi
0x180093239  jnz     short loc_180093257
0x18009323b  mov     rcx, r8; this
0x18009323e  call    ?IsBusy@EsimRecord@EsimManager@LPA@@QEBA_NXZ; LPA::EsimManager::EsimRecord::IsBusy(void)
0x180093243  neg     al
0x180093245  sbb     rcx, rcx
0x180093248  and     rcx, 0FFFFFFFFFFFFFFFDh
0x18009324c  cmp     [rcx+r8+4], sil
0x180093251  jz      loc_180093450
0x180093257  mov     rsi, [r14+90h]
0x18009325e  mov     rax, [rsi+10h]
0x180093262  mov     rdi, [rax+18h]
0x180093266  lea     rcx, [r14+58h]
0x18009326a  lea     rdx, [rbp+37h+var_50]
0x18009326e  call    ?shared_from_this@?$enable_shared_from_this@VEnterpriseManager@LPA@@@std@@QEAA?AV?$shared_ptr@VEnterpriseManager@LPA@@@2@XZ; std::enable_shared_from_this<LPA::EnterpriseManager>::shared_from_this(void)
0x180093273  nop
0x180093274  mov     rdx, rax
0x180093277  lea     rcx, [rbp+37h+var_80]
0x18009327b  call    ??$?0VEsimManager@LPA@@$0A@@?$weak_ptr@UApduHelperEs10cCompletionHandler@LPA@@@std@@QEAA@AEBV?$shared_ptr@VEsimManager@LPA@@@1@@Z; std::weak_ptr<LPA::ApduHelperEs10cCompletionHandler>::weak_ptr<LPA::ApduHelperEs10cCompletionHandler>(std::shared_ptr<LPA::EsimManager> const &)
0x180093280  lea     rcx, [rbp+37h+arg_18]
0x180093284  mov     [rsp+100h+var_E0], rcx
0x180093289  mov     r9, rax
0x18009328c  mov     r8d, [r13+0]
0x180093290  mov     rdx, r15
0x180093293  lea     rcx, [rsi+10h]
0x180093297  mov     rax, rdi
0x18009329a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009329f  mov     dword ptr [rbp+37h+arg_0], eax
0x1800932a2  mov     rcx, [rbp+37h+var_48]; this
0x1800932a6  test    rcx, rcx
0x1800932a9  jz      short loc_1800932B0
0x1800932ab  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800932b0  mov     rcx, [rbx+30h]
0x1800932b4  mov     edx, [rcx+0B0h]
0x1800932ba  mov     [rbp+37h+var_8C], edx
0x1800932bd  lea     rsi, [r14+0F0h]
0x1800932c4  lea     r8, [rbp+37h+var_8C]
0x1800932c8  lea     rdx, [rbp+37h+var_88]
0x1800932cc  mov     rcx, rsi
0x1800932cf  call    ?find@?$_Tree@V?$_Tmap_traits@KV?$shared_ptr@VDownloadInstance@Lpd@LPA@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$shared_ptr@VDownloadInstance@Lpd@LPA@@@std@@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKV?$shared_ptr@VDownloadInstance@Lpd@LPA@@@std@@@std@@@std@@@std@@@2@AEBK@Z; std::_Tree<std::_Tmap_traits<ulong,std::shared_ptr<LPA::Lpd::DownloadInstance>,std::less<ulong>,std::allocator<std::pair<ulong const,std::shared_ptr<LPA::Lpd::DownloadInstance>>>,0>>::find(ulong const &)
0x1800932d4  mov     r8d, cs:CallbackContext
0x1800932db  mov     rdi, [rbp+37h+var_88]
0x1800932df  cmp     r8d, 4
0x1800932e3  jbe     loc_1800933A8
0x1800932e9  mov     rax, [rbx+30h]
0x1800932ed  mov     ecx, [rax+0B0h]
0x1800932f3  mov     [rbp+37h+var_8C], ecx
0x1800932f6  mov     eax, [rbp+37h+arg_18]
0x1800932f9  mov     [rbp+37h+var_90], eax
0x1800932fc  mov     eax, [r13+0]
0x180093300  mov     [rbp+37h+var_70], eax
0x180093303  mov     eax, dword ptr [rbp+37h+arg_0]
0x180093306  mov     [rbp+37h+var_6C], eax
0x180093309  xor     eax, eax
0x18009330b  cmp     [rsi], rdi
0x18009330e  setnz   al
0x180093311  mov     [rbp+37h+var_68], eax
0x180093314  mov     eax, [r12]
0x180093318  mov     dword ptr [rbp+37h+var_60], eax
0x18009331b  mov     [rbp+37h+var_40], r15
0x18009331f  mov     rax, [rbx+30h]
0x180093323  mov     ecx, [rax+0B4h]
0x180093329  mov     dword ptr [rbp+37h+var_58], ecx
0x18009332c  lea     rax, aLpaEsimmanager_1; "LPA::EsimManager::ProcessWwapiSimUpdate"
0x180093333  mov     [rbp+37h+var_50], rax
0x180093337  lea     rax, aLpaserviceesim; "LpaServiceEsimManager"
0x18009333e  mov     [rbp+37h+var_80], rax
0x180093342  lea     rax, [rbp+37h+var_8C]
0x180093346  mov     [rsp+100h+var_98], rax
0x18009334b  lea     rax, [rbp+37h+var_90]
0x18009334f  mov     [rsp+100h+var_A0], rax
0x180093354  lea     rax, [rbp+37h+var_70]
0x180093358  mov     [rsp+100h+var_A8], rax
0x18009335d  lea     rax, [rbp+37h+var_6C]
0x180093361  mov     [rsp+100h+var_B0], rax
0x180093366  lea     rax, [rbp+37h+var_68]
0x18009336a  mov     [rsp+100h+var_B8], rax
0x18009336f  lea     rax, [rbp+37h+var_60]
0x180093373  mov     [rsp+100h+var_C0], rax
0x180093378  lea     rax, [rbp+37h+var_40]
0x18009337c  mov     [rsp+100h+var_C8], rax
0x180093381  lea     rax, [rbp+37h+var_58]
0x180093385  mov     [rsp+100h+var_D0], rax
0x18009338a  lea     rax, [rbp+37h+var_50]
0x18009338e  mov     [rsp+100h+var_D8], rax
0x180093393  lea     rax, [rbp+37h+var_80]
0x180093397  mov     [rsp+100h+var_E0], rax
0x18009339c  lea     rdx, byte_18012EB97
0x1800933a3  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByRef@$0BA@@@U2@U2@U2@U2@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByRef@$0BA@@@444444@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800933a8  cmp     [rsi], rdi
0x1800933ab  jz      short loc_1800933E9
0x1800933ad  xor     ecx, ecx
0x1800933af  lea     rdx, [rbp+37h+var_88]
0x1800933b3  cmp     dword ptr [rbp+37h+arg_0], ecx
0x1800933b6  jl      short loc_1800933DF
0x1800933b8  mov     eax, [rbp+37h+arg_18]
0x1800933bb  mov     dword ptr [rsp+100h+var_C0], eax
0x1800933bf  mov     byte ptr [rsp+100h+var_C8], cl
0x1800933c3  mov     byte ptr [rsp+100h+var_D0], cl
0x1800933c7  mov     byte ptr [rsp+100h+var_D8], cl
0x1800933cb  mov     byte ptr [rsp+100h+var_E0], cl
0x1800933cf  mov     r9b, 1
0x1800933d2  mov     r8, r15
0x1800933d5  mov     rcx, r14
0x1800933d8  call    ?TransferOperationToNewTransactionId@EsimManager@LPA@@AEAAXAEAV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKV?$unique_ptr@VOperationEntry@EsimManager@LPA@@U?$default_delete@VOperationEntry@EsimManager@LPA@@@std@@@std@@@std@@@std@@@std@@@std@@AEBU_GUID@@_N2222K@Z; LPA::EsimManager::TransferOperationToNewTransactionId(std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<ulong const,std::unique_ptr<LPA::EsimManager::OperationEntry>>>>> &,_GUID const &,bool,bool,bool,bool,bool,ulong)
0x1800933dd  jmp     short loc_180093450
0x1800933df  mov     rcx, r14; this
0x1800933e2  call    ?CompleteOperation@EsimManager@LPA@@AEAAXAEAV?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKV?$unique_ptr@VOperationEntry@EsimManager@LPA@@U?$default_delete@VOperationEntry@EsimManager@LPA@@@std@@@std@@@std@@@std@@@std@@@std@@@Z; LPA::EsimManager::CompleteOperation(std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<ulong const,std::unique_ptr<LPA::EsimManager::OperationEntry>>>>> &)
0x1800933e7  jmp     short loc_180093450
0x1800933e9  cmp     dword ptr [rbp+37h+arg_0], 0
  ... truncated ...
```
