# LPA::EsimManager::OnWwapiAtrInfoNotification(std::shared_ptr<LPA::WwapiMessage>,_WWAN_ATR_INFO_RESULT const *)

- ea: `0x180090580`
- end: `0x180090857`
- name: `?OnWwapiAtrInfoNotification@EsimManager@LPA@@EEAAXV?$shared_ptr@VWwapiMessage@LPA@@@std@@PEBU_WWAN_ATR_INFO_RESULT@@@Z`
- size: `727`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `service_task, installer_update`

## callees

- `0x1800036bc`
- `0x180003c3c`
- `0x1800709e4`
- `0x180085810`
- `0x180089f00`
- `0x180090580`
- `0x180092f68`
- `0x180095fd0`

## import_xrefs

- `wwapi!WwanQueryInterface` at `0x180090744`
- `wwapi!WwanQueryInterface` at `0x180090744`
- `wwapi!WwanQueryInterfaceEx` at `0x1800907c2`
- `wwapi!WwanQueryInterfaceEx` at `0x1800907c2`
- `wwapi!WwanFreeMemory` at `0x180090813`
- `wwapi!WwanFreeMemory` at `0x180090827`
- `wwapi!WwanFreeMemory` at `0x180090813`
- `wwapi!WwanFreeMemory` at `0x180090827`

## string_xrefs

- `0x1800905f2`: `LpaServiceEsimManager`
- `0x1800906c3`: `LpaServiceEsimManager`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall LPA::EsimManager::OnWwapiAtrInfoNotification(__int64 a1, _QWORD *a2, __int64 a3)
{
  LPA::EsimManager *v6; // r12
  std::_Ref_count_base *v7; // rcx
  const struct _GUID *v8; // r14
  bool v9; // al
  int v10; // r9d
  BOOL v11; // r15d
  int v12; // ecx
  int v13; // r8d
  int v14; // r9d
  unsigned __int8 v15; // r13
  unsigned __int16 *v16; // r15
  __int64 v17; // rax
  int v18; // ebx
  enum _WWAN_READY_STATE *v19; // rcx
  __int64 v20; // rcx
  unsigned int v21; // [rsp+50h] [rbp-39h]
  BOOL v22; // [rsp+54h] [rbp-35h] BYREF
  unsigned int v23; // [rsp+58h] [rbp-31h] BYREF
  const char *v24; // [rsp+60h] [rbp-29h] BYREF
  enum _WWAN_READY_STATE *v25; // [rsp+68h] [rbp-21h] BYREF
  __int64 v26; // [rsp+70h] [rbp-19h]
  const char *v27; // [rsp+78h] [rbp-11h] BYREF
  unsigned int v28; // [rsp+80h] [rbp-9h] BYREF
  const char *v29; // [rsp+88h] [rbp-1h] BYREF
  const char *v30; // [rsp+90h] [rbp+7h] BYREF
  enum _WWAN_READY_STATE **v31; // [rsp+98h] [rbp+Fh] BYREF
  __int64 v32; // [rsp+A0h] [rbp+17h] BYREF
  char v33; // [rsp+A8h] [rbp+1Fh]
  unsigned int v34; // [rsp+F0h] [rbp+67h] BYREF
  _QWORD *v35; // [rsp+F8h] [rbp+6Fh]
  int v36; // [rsp+108h] [rbp+7Fh] BYREF

  v35 = a2;
  v6 = (LPA::EsimManager *)(a1 - 80);
  if ( *(_DWORD *)(a1 - 80 + 104) == 2 )
  {
    v36 = 0;
    v8 = (const struct _GUID *)(*a2 + 8LL);
    v21 = *(_DWORD *)(a3 + 4);
    v23 = v21;
    v9 = DoesAtrIndicateEuiccPresent((const unsigned __int8 (*)[36])(a3 + 12));
    LOBYTE(v34) = v9;
    v11 = v9;
    if ( (unsigned int)CallbackContext > 4 )
    {
      LODWORD(v27) = v21;
      v22 = v9;
      v31 = (enum _WWAN_READY_STATE **)(a3 + 12);
      LOWORD(v32) = *(_WORD *)(a3 + 8);
      v29 = (const char *)v8;
      v30 = "LPA::EsimManager::OnWwapiAtrInfoNotification";
      v24 = "LpaServiceEsimManager";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapperArray<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (unsigned __int16)v32,
        (unsigned int)&word_18012E26E,
        (unsigned int)"LpaServiceEsimManager",
        v10,
        (__int64)&v24,
        (__int64)&v30,
        (__int64)&v29,
        (__int64)&v31,
        (__int64)&v22,
        (__int64)&v27);
    }
    LPA::EsimManager::TryFindEsimRecordBySlotId(v6, &v24, &v23, v8);
    v15 = v34;
    if ( (_BYTE)v34 && v24 == *(const char **)(a1 + 128) && (unsigned int)CallbackContext > 2 )
    {
      v34 = v21;
      v22 = v11;
      v24 = (const char *)v8;
      v30 = (const char *)L"EsimManager::OnWwapiAtrInfoNotification";
      v29 = "LPA::EsimManager::OnWwapiAtrInfoNotification";
      v27 = "LpaServiceEsimManager";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v12,
        (unsigned int)byte_18012E1F5,
        v13,
        v14,
        (__int64)&v27,
        (__int64)&v29,
        (__int64)&v30,
        (__int64)&v24,
        (__int64)&v22,
        (__int64)&v34);
    }
    v26 = 0;
    v16 = 0;
    v36 = 0;
    if ( !(unsigned int)WwanQueryInterface(*(_QWORD *)(a1 + 40), v8, 7) )
    {
      v17 = v26;
      if ( v26 )
      {
        *(_WORD *)(v26 + 992) = 0;
        if ( !*(_DWORD *)(v17 + 904) )
        {
          *(_WORD *)(v17 + 686) = 0;
          v16 = (unsigned __int16 *)(v17 + 652);
        }
      }
    }
    v28 = v21;
    v25 = 0;
    v36 = 0;
    v31 = &v25;
    v32 = 0;
    v33 = 1;
    v18 = WwanQueryInterfaceEx(*(_QWORD *)(a1 + 40), v8, 36, 4, &v28, 0, &v36, &v32);
    wil::details::out_param_ptr_t<unsigned char * *,wistd::unique_ptr<_WWAN_MULTI_SIM_SLOT_MAPPING_STATUS,wil::function_deleter<void (*)(void *),&void WwanFreeMemory(void *)>>>::~out_param_ptr_t<unsigned char * *,wistd::unique_ptr<_WWAN_MULTI_SIM_SLOT_MAPPING_STATUS,wil::function_deleter<void (*)(void *),&void WwanFreeMemory(void *)>>>(&v31);
    if ( !v18 )
      LPA::EsimManager::ProcessWwapiSimUpdate(
        v6,
        v8,
        &v23,
        v15,
        0,
        v25,
        v16,
        (const unsigned __int16 (*)[21])((char *)v25 + 40));
    v19 = v25;
    v25 = 0;
    if ( v19 )
      WwanFreeMemory(v19);
    v20 = v26;
    v26 = 0;
    if ( v20 )
      WwanFreeMemory(v20);
    v7 = (std::_Ref_count_base *)a2[1];
  }
  else
  {
    v7 = (std::_Ref_count_base *)a2[1];
  }
  if ( v7 )
    std::_Ref_count_base::_Decref(v7);
}

```

## disassembly

```asm
0x180090580  mov     [rsp-8+arg_10], rbx
0x180090585  mov     [rsp-8+arg_8], rdx
0x18009058a  push    rbp
0x18009058b  push    rsi
0x18009058c  push    rdi
0x18009058d  push    r12
0x18009058f  push    r13
0x180090591  push    r14
0x180090593  push    r15
0x180090595  lea     rbp, [rsp-27h]
0x18009059a  sub     rsp, 0B0h
0x1800905a1  mov     r13, r8
0x1800905a4  mov     rsi, rdx
0x1800905a7  mov     rbx, rcx
0x1800905aa  lea     r12, [rcx-50h]
0x1800905ae  cmp     dword ptr [r12+68h], 2
0x1800905b4  jz      short loc_1800905BF
0x1800905b6  mov     rcx, [rdx+8]
0x1800905ba  jmp     loc_180090832
0x1800905bf  xor     edi, edi
0x1800905c1  mov     [rbp+57h+arg_18], edi
0x1800905c4  mov     r14, [rdx]
0x1800905c7  add     r14, 8
0x1800905cb  mov     eax, [r8+4]
0x1800905cf  mov     [rbp+57h+var_90], eax
0x1800905d2  mov     [rbp+57h+var_88], eax
0x1800905d5  lea     rcx, [r8+0Ch]; unsigned __int8 (*)[36]
0x1800905d9  call    ?DoesAtrIndicateEuiccPresent@@YA_NAEAY0CE@$$CBE@Z; DoesAtrIndicateEuiccPresent(uchar const (&)[36])
0x1800905de  mov     byte ptr [rbp+57h+arg_0], al
0x1800905e1  mov     ecx, cs:CallbackContext
0x1800905e7  movzx   r15d, al
0x1800905eb  lea     rdx, aLpaEsimmanager_57; "LPA::EsimManager::OnWwapiAtrInfoNotific"...
0x1800905f2  lea     r8, aLpaserviceesim; "LpaServiceEsimManager"
0x1800905f9  cmp     ecx, 4
0x1800905fc  jbe     short loc_180090667
0x1800905fe  mov     eax, [rbp+57h+var_90]
0x180090601  mov     dword ptr [rbp+57h+var_68], eax
0x180090604  mov     [rbp+57h+var_8C], r15d
0x180090608  lea     rax, [r13+0Ch]
0x18009060c  mov     [rbp+57h+var_48], rax
0x180090610  movzx   ecx, word ptr [r13+8]
0x180090615  mov     word ptr [rbp+57h+var_40], cx
0x180090619  mov     [rbp+57h+var_58], r14
0x18009061d  mov     [rbp+57h+var_50], rdx
0x180090621  mov     [rbp+57h+var_80], r8
0x180090625  lea     rax, [rbp+57h+var_68]
0x180090629  mov     [rsp+0E0h+var_98], rax
0x18009062e  lea     rax, [rbp+57h+var_8C]
0x180090632  mov     [rsp+0E0h+var_A0], rax
0x180090637  lea     rax, [rbp+57h+var_48]
0x18009063b  mov     [rsp+0E0h+var_A8], rax
0x180090640  lea     rax, [rbp+57h+var_58]
0x180090644  mov     [rsp+0E0h+var_B0], rax
0x180090649  lea     rax, [rbp+57h+var_50]
0x18009064d  mov     [rsp+0E0h+var_B8], rax
0x180090652  lea     rax, [rbp+57h+var_80]
0x180090656  mov     qword ptr [rsp+0E0h+var_C0], rax
0x18009065b  lea     rdx, word_18012E26E
0x180090662  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperArray@$00@@U?$_tlgWrapperByVal@$03@@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperArray@$00@@AEBU?$_tlgWrapperByVal@$03@@6@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapperArray<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180090667  mov     r9, r14
0x18009066a  lea     r8, [rbp+57h+var_88]
0x18009066e  lea     rdx, [rbp+57h+var_80]
0x180090672  mov     rcx, r12
0x180090675  call    ?TryFindEsimRecordBySlotId@EsimManager@LPA@@AEAA?AV?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@V?$unique_ptr@VEsimRecord@EsimManager@LPA@@U?$default_delete@VEsimRecord@EsimManager@LPA@@@std@@@std@@@std@@@std@@@std@@@std@@AEBKAEBU_GUID@@@Z; LPA::EsimManager::TryFindEsimRecordBySlotId(ulong const &,_GUID const &)
0x18009067a  mov     r13b, byte ptr [rbp+57h+arg_0]
0x18009067e  test    r13b, r13b
0x180090681  jz      loc_180090710
0x180090687  mov     rax, [rbx+80h]
0x18009068e  cmp     [rbp+57h+var_80], rax
0x180090692  jnz     short loc_180090710
0x180090694  mov     eax, cs:CallbackContext
0x18009069a  cmp     eax, 2
0x18009069d  jbe     short loc_180090710
0x18009069f  mov     eax, [rbp+57h+var_90]
0x1800906a2  mov     [rbp+57h+arg_0], eax
0x1800906a5  mov     [rbp+57h+var_8C], r15d
0x1800906a9  mov     [rbp+57h+var_80], r14
0x1800906ad  lea     rax, aEsimmanagerOnw; "EsimManager::OnWwapiAtrInfoNotification"
0x1800906b4  mov     [rbp+57h+var_50], rax
0x1800906b8  lea     rax, aLpaEsimmanager_57; "LPA::EsimManager::OnWwapiAtrInfoNotific"...
0x1800906bf  mov     [rbp+57h+var_58], rax
0x1800906c3  lea     rax, aLpaserviceesim; "LpaServiceEsimManager"
0x1800906ca  mov     [rbp+57h+var_68], rax
0x1800906ce  lea     rax, [rbp+57h+arg_0]
0x1800906d2  mov     [rsp+0E0h+var_98], rax
0x1800906d7  lea     rax, [rbp+57h+var_8C]
0x1800906db  mov     [rsp+0E0h+var_A0], rax
0x1800906e0  lea     rax, [rbp+57h+var_80]
0x1800906e4  mov     [rsp+0E0h+var_A8], rax
0x1800906e9  lea     rax, [rbp+57h+var_50]
0x1800906ed  mov     [rsp+0E0h+var_B0], rax
0x1800906f2  lea     rax, [rbp+57h+var_58]
0x1800906f6  mov     [rsp+0E0h+var_B8], rax
0x1800906fb  lea     rax, [rbp+57h+var_68]
0x1800906ff  mov     qword ptr [rsp+0E0h+var_C0], rax
0x180090704  lea     rdx, byte_18012E1F5
0x18009070b  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapSz@G@@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@6@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180090710  mov     [rbp+57h+var_70], rdi
0x180090714  mov     r15, rdi
0x180090717  mov     [rbp+57h+arg_18], edi
0x18009071a  mov     [rsp+0E0h+var_A8], rdi
0x18009071f  mov     [rsp+0E0h+var_B0], rdi
0x180090724  lea     rax, [rbp+57h+var_70]
0x180090728  mov     [rsp+0E0h+var_B8], rax
0x18009072d  lea     rax, [rbp+57h+arg_18]
0x180090731  mov     qword ptr [rsp+0E0h+var_C0], rax
0x180090736  xor     r9d, r9d
0x180090739  lea     r8d, [r9+7]
0x18009073d  mov     rdx, r14
0x180090740  mov     rcx, [rbx+28h]
0x180090744  call    cs:__imp_WwanQueryInterface
0x18009074a  test    eax, eax
0x18009074c  jnz     short loc_180090774
0x18009074e  mov     rax, [rbp+57h+var_70]
0x180090752  test    rax, rax
0x180090755  jz      short loc_180090774
0x180090757  mov     [rax+3E0h], di
0x18009075e  cmp     [rax+388h], edi
0x180090764  jnz     short loc_180090774
0x180090766  mov     [rax+2AEh], di
0x18009076d  lea     r15, [rax+28Ch]
0x180090774  mov     eax, [rbp+57h+var_90]
0x180090777  mov     [rbp+57h+var_60], eax
0x18009077a  mov     [rbp+57h+var_78], rdi
0x18009077e  mov     [rbp+57h+arg_18], edi
0x180090781  lea     rax, [rbp+57h+var_78]
0x180090785  mov     [rbp+57h+var_48], rax
0x180090789  mov     [rbp+57h+var_40], rdi
0x18009078d  mov     [rbp+57h+var_38], 1
0x180090791  lea     rax, [rbp+57h+var_40]
0x180090795  mov     [rsp+0E0h+var_A8], rax
0x18009079a  lea     rax, [rbp+57h+arg_18]
0x18009079e  mov     [rsp+0E0h+var_B0], rax
0x1800907a3  mov     [rsp+0E0h+var_B8], rdi
0x1800907a8  lea     rax, [rbp+57h+var_60]
0x1800907ac  mov     qword ptr [rsp+0E0h+var_C0], rax
0x1800907b1  mov     r9d, 4
0x1800907b7  lea     r8d, [r9+20h]
0x1800907bb  mov     rdx, r14
0x1800907be  mov     rcx, [rbx+28h]
0x1800907c2  call    cs:__imp_WwanQueryInterfaceEx
0x1800907c8  mov     ebx, eax
0x1800907ca  lea     rcx, [rbp+57h+var_48]
0x1800907ce  call    ??1?$out_param_ptr_t@PEAPEAEV?$unique_ptr@U_WWAN_MULTI_SIM_SLOT_MAPPING_STATUS@@U?$function_deleter@P6AXPEAX@Z$1?WwanFreeMemory@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_ptr_t<uchar * *,wistd::unique_ptr<_WWAN_MULTI_SIM_SLOT_MAPPING_STATUS,wil::function_deleter<void (*)(void *),&WwanFreeMemory(void *)>>>::~out_param_ptr_t<uchar * *,wistd::unique_ptr<_WWAN_MULTI_SIM_SLOT_MAPPING_STATUS,wil::function_deleter<void (*)(void *),&WwanFreeMemory(void *)>>>(void)
0x1800907d3  test    ebx, ebx
0x1800907d5  jnz     short loc_180090806
0x1800907d7  mov     rax, [rbp+57h+var_78]
0x1800907db  lea     r8, [rax+28h]
0x1800907df  mov     [rsp+0E0h+var_A8], r8; unsigned __int16 (*)[21]
0x1800907e4  mov     [rsp+0E0h+var_B0], r15; unsigned __int16 *
0x1800907e9  mov     [rsp+0E0h+var_B8], rax; enum _WWAN_READY_STATE *
0x1800907ee  mov     [rsp+0E0h+var_C0], dil; bool
0x1800907f3  mov     r9b, r13b; bool
0x1800907f6  lea     r8, [rbp+57h+var_88]; unsigned int *
0x1800907fa  mov     rdx, r14; struct _GUID *
0x1800907fd  mov     rcx, r12; this
0x180090800  call    ?ProcessWwapiSimUpdate@EsimManager@LPA@@AEAAXAEBU_GUID@@AEBK_N2AEBW4_WWAN_READY_STATE@@PEBGAEAY0BF@$$CBG@Z; LPA::EsimManager::ProcessWwapiSimUpdate(_GUID const &,ulong const &,bool,bool,_WWAN_READY_STATE const &,ushort const *,ushort const (&)[21])
0x180090805  nop
0x180090806  mov     rcx, [rbp+57h+var_78]
0x18009080a  mov     [rbp+57h+var_78], rdi
0x18009080e  test    rcx, rcx
0x180090811  jz      short loc_18009081A
0x180090813  call    cs:__imp_WwanFreeMemory
0x180090819  nop
0x18009081a  mov     rcx, [rbp+57h+var_70]
0x18009081e  mov     [rbp+57h+var_70], rdi
0x180090822  test    rcx, rcx
0x180090825  jz      short loc_18009082E
0x180090827  call    cs:__imp_WwanFreeMemory
0x18009082d  nop
0x18009082e  mov     rcx, [rsi+8]; this
0x180090832  test    rcx, rcx
0x180090835  jz      short loc_18009083C
0x180090837  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18009083c  mov     rbx, [rsp+0E0h+arg_10]
0x180090844  add     rsp, 0B0h
0x18009084b  pop     r15
0x18009084d  pop     r14
0x18009084f  pop     r13
0x180090851  pop     r12
0x180090853  pop     rdi
0x180090854  pop     rsi
0x180090855  pop     rbp
0x180090856  retn
```
