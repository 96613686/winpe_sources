# LPA::Lui::OnLuiRpcOpenHandle(std::shared_ptr<LPA::LuiRpcMessage>,LPALUICLIENTMODE,void *,void *)

- ea: `0x1800caa60`
- end: `0x1800cac6e`
- name: `?OnLuiRpcOpenHandle@Lui@LPA@@EEAAXV?$shared_ptr@VLuiRpcMessage@LPA@@@std@@W4LPALUICLIENTMODE@@PEAX2@Z`
- size: `526`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `loader_planting, service_task`

## callees

- `0x180001010`
- `0x18000e46c`
- `0x1800709e4`
- `0x1800c4f70`
- `0x1800c5534`
- `0x1800c5958`
- `0x1800c5b98`
- `0x1800c646c`
- `0x1800caa60`
- `0x1800cf300`
- `0x1800cf388`
- `0x1800d7ee4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800cab29`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800cab29`

## string_xrefs

- `0x1800caaf1`: `LpaServiceLui`
- `0x1800cac2c`: `LpaServiceLui`
- `0x1800caae6`: `LPA::Lui::OnLuiRpcOpenHandle`
- `0x1800cac21`: `LPA::Lui::OnLuiRpcOpenHandle`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall LPA::Lui::OnLuiRpcOpenHandle(__int64 a1, __int64 a2, unsigned int a3, __int64 a4)
{
  int v8; // r15d
  int v9; // ecx
  int v10; // r8d
  int v11; // r9d
  _DWORD *v12; // rbx
  char *v13; // rdx
  _DWORD *v14; // rcx
  void *v15; // rcx
  __int64 v16; // rbx
  __int64 v17; // rcx
  __int64 v18; // rdx
  std::_Ref_count_base *v19; // rcx
  const char *v20; // [rsp+30h] [rbp-28h] BYREF
  _DWORD *LuiContextHandle; // [rsp+38h] [rbp-20h] BYREF
  _BYTE v22[24]; // [rsp+40h] [rbp-18h] BYREF
  const char *v23; // [rsp+A8h] [rbp+50h] BYREF

  v23 = (const char *)a2;
  v8 = 0;
  LuiContextHandle = LPA::LuiRpcMessage::GetLuiContextHandle(*(LPA::LuiRpcMessage **)a2);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Lpasvc_Fix_OpenHandleOnStopping>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Lpasvc_Fix_OpenHandleOnStopping>::GetImpl'::`2'::impl) )
  {
    v12 = LuiContextHandle;
    if ( !LuiContextHandle )
    {
      if ( (unsigned int)CallbackContext <= 4 )
        goto LABEL_25;
      v13 = byte_180134153;
      goto LABEL_24;
    }
    if ( !*(_DWORD *)(a1 + 48) || *(_DWORD *)(a1 + 48) == 3 )
    {
      if ( (unsigned int)CallbackContext > 4 )
      {
        v23 = "LPA::Lui::OnLuiRpcOpenHandle";
        v20 = "LpaServiceLui";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>>(
          v9,
          (unsigned int)byte_1801340E9,
          v10,
          v11,
          (__int64)&v20,
          (__int64)&v23);
      }
      v14 = LuiContextHandle;
      LuiContextHandle[10] = -2147019873;
      v15 = (void *)*((_QWORD *)v14 + 4);
LABEL_10:
      SetEvent(v15);
      goto LABEL_25;
    }
LABEL_16:
    std::_Tree<std::_Tmap_traits<void *,std::unique_ptr<LPA::Lui::LuiContextRecord>,std::less<void *>,std::allocator<std::pair<void * const,std::unique_ptr<LPA::Lui::LuiContextRecord>>>,0>>::find(
      a1 + 144,
      &v20,
      &LuiContextHandle);
    if ( *(const char **)(a1 + 144) == v20 )
    {
      v20 = (const char *)operator new(0x38u);
      v16 = LPA::Lui::LuiContextRecord::LuiContextRecord(v20, LuiContextHandle, a4, a3);
      v20 = (const char *)v16;
      v17 = *(_QWORD *)std::map<void *,std::unique_ptr<LPA::Lui::LuiContextRecord>>::_Try_emplace<void * const &,>(
                         a1 + 144,
                         v22,
                         &LuiContextHandle);
      v20 = 0;
      v18 = *(_QWORD *)(v17 + 40);
      *(_QWORD *)(v17 + 40) = v16;
      if ( v18 )
        std::default_delete<LPA::Lui::LuiContextRecord>::operator()();
      std::unique_ptr<LPA::Lui::LuiContextRecord>::~unique_ptr<LPA::Lui::LuiContextRecord>(&v20);
      ServiceHandler::SetRpcClientCount(*(_QWORD *)(a1 + 152));
      v12 = LuiContextHandle;
    }
    else
    {
      v8 = -2147024713;
    }
    v12[10] = v8;
    v15 = (void *)*((_QWORD *)v12 + 4);
    goto LABEL_10;
  }
  if ( *(_DWORD *)(a1 + 48) && *(_DWORD *)(a1 + 48) != 3 )
  {
    v12 = LuiContextHandle;
    if ( !LuiContextHandle )
    {
      if ( (unsigned int)CallbackContext <= 4 )
        goto LABEL_25;
      v13 = byte_180134085;
      goto LABEL_24;
    }
    goto LABEL_16;
  }
  if ( (unsigned int)CallbackContext <= 4 )
    goto LABEL_25;
  v13 = (char *)&word_18013411E;
LABEL_24:
  v23 = "LPA::Lui::OnLuiRpcOpenHandle";
  v20 = "LpaServiceLui";
  _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>>(
    v9,
    (_DWORD)v13,
    v10,
    v11,
    (__int64)&v20,
    (__int64)&v23);
LABEL_25:
  v19 = *(std::_Ref_count_base **)(a2 + 8);
  if ( v19 )
    std::_Ref_count_base::_Decref(v19);
}

```

## disassembly

```asm
0x1800caa60  mov     [rsp-40h+arg_8], rdx
0x1800caa65  push    rbp
0x1800caa66  push    rbx
0x1800caa67  push    rsi
0x1800caa68  push    rdi
0x1800caa69  push    r12
0x1800caa6b  push    r13
0x1800caa6d  push    r14
0x1800caa6f  push    r15
0x1800caa71  mov     rbp, rsp
0x1800caa74  sub     rsp, 58h
0x1800caa78  mov     r12, r9
0x1800caa7b  mov     r13d, r8d
0x1800caa7e  mov     rdi, rdx
0x1800caa81  mov     rsi, rcx
0x1800caa84  xor     r15d, r15d
0x1800caa87  mov     rcx, [rdx]; this
0x1800caa8a  call    ?GetLuiContextHandle@LuiRpcMessage@LPA@@QEBAPEAXXZ; LPA::LuiRpcMessage::GetLuiContextHandle(void)
0x1800caa8f  mov     [rbp+var_20], rax
0x1800caa93  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Lpasvc_Fix_OpenHandleOnStopping@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Lpasvc_Fix_OpenHandleOnStopping@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Lpasvc_Fix_OpenHandleOnStopping> `wil::Feature<__WilFeatureTraits_Feature_Lpasvc_Fix_OpenHandleOnStopping>::GetImpl(void)'::`2'::impl
0x1800caa9a  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Lpasvc_Fix_OpenHandleOnStopping@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Lpasvc_Fix_OpenHandleOnStopping>::__private_IsEnabled(void)
0x1800caa9f  test    al, al
0x1800caaa1  jz      loc_1800CAB34
0x1800caaa7  mov     rbx, [rbp+var_20]
0x1800caaab  test    rbx, rbx
0x1800caaae  jnz     short loc_1800CAACB
0x1800caab0  mov     eax, cs:CallbackContext
0x1800caab6  cmp     eax, 4
0x1800caab9  jbe     loc_1800CAC4F
0x1800caabf  lea     rdx, byte_180134153
0x1800caac6  jmp     loc_1800CAC21
0x1800caacb  cmp     [rsi+30h], r15d
0x1800caacf  jz      short loc_1800CAADB
0x1800caad1  cmp     dword ptr [rsi+30h], 3
0x1800caad5  jnz     loc_1800CAB6C
0x1800caadb  mov     eax, cs:CallbackContext
0x1800caae1  cmp     eax, 4
0x1800caae4  jbe     short loc_1800CAB1A
0x1800caae6  lea     rax, aLpaLuiOnluirpc_21; "LPA::Lui::OnLuiRpcOpenHandle"
0x1800caaed  mov     [rbp+arg_8], rax
0x1800caaf1  lea     rax, aLpaservicelui; "LpaServiceLui"
0x1800caaf8  mov     [rbp+var_28], rax
0x1800caafc  lea     rax, [rbp+arg_8]
0x1800cab00  mov     [rsp+58h+var_30], rax
0x1800cab05  lea     rax, [rbp+var_28]
0x1800cab09  mov     [rsp+58h+var_38], rax
0x1800cab0e  lea     rdx, byte_1801340E9
0x1800cab15  call    ??$Write@U?$_tlgWrapSz@D@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x1800cab1a  mov     rcx, [rbp+var_20]
0x1800cab1e  mov     dword ptr [rcx+28h], 8007139Fh
0x1800cab25  mov     rcx, [rcx+20h]; hEvent
0x1800cab29  call    cs:__imp_SetEvent
0x1800cab2f  jmp     loc_1800CAC4F
0x1800cab34  cmp     [rsi+30h], r15d
0x1800cab38  jz      loc_1800CAC0F
0x1800cab3e  cmp     dword ptr [rsi+30h], 3
0x1800cab42  jz      loc_1800CAC0F
0x1800cab48  mov     rbx, [rbp+var_20]
0x1800cab4c  test    rbx, rbx
0x1800cab4f  jnz     short loc_1800CAB6C
0x1800cab51  mov     eax, cs:CallbackContext
0x1800cab57  cmp     eax, 4
0x1800cab5a  jbe     loc_1800CAC4F
0x1800cab60  lea     rdx, byte_180134085
0x1800cab67  jmp     loc_1800CAC21
0x1800cab6c  lea     r14, [rsi+90h]
0x1800cab73  lea     r8, [rbp+var_20]
0x1800cab77  lea     rdx, [rbp+var_28]
0x1800cab7b  mov     rcx, r14
0x1800cab7e  call    ?find@?$_Tree@V?$_Tmap_traits@PEAXV?$unique_ptr@VLuiContextRecord@Lui@LPA@@U?$default_delete@VLuiContextRecord@Lui@LPA@@@std@@@std@@U?$less@PEAX@2@V?$allocator@U?$pair@QEAXV?$unique_ptr@VLuiContextRecord@Lui@LPA@@U?$default_delete@VLuiContextRecord@Lui@LPA@@@std@@@std@@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEAXV?$unique_ptr@VLuiContextRecord@Lui@LPA@@U?$default_delete@VLuiContextRecord@Lui@LPA@@@std@@@std@@@std@@@std@@@std@@@2@AEBQEAX@Z; std::_Tree<std::_Tmap_traits<void *,std::unique_ptr<LPA::Lui::LuiContextRecord>,std::less<void *>,std::allocator<std::pair<void * const,std::unique_ptr<LPA::Lui::LuiContextRecord>>>,0>>::find(void * const &)
0x1800cab83  mov     r8, [rbp+var_28]
0x1800cab87  cmp     [r14], r8
0x1800cab8a  jnz     short loc_1800CABFC
0x1800cab8c  mov     ecx, 38h ; '8'; Size
0x1800cab91  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800cab96  mov     [rbp+var_28], rax
0x1800cab9a  mov     r9d, r13d
0x1800cab9d  mov     r8, r12
0x1800caba0  mov     rdx, [rbp+var_20]
0x1800caba4  mov     rcx, rax
0x1800caba7  call    ??0LuiContextRecord@Lui@LPA@@QEAA@PEAX0W4LPALUICLIENTMODE@@@Z; LPA::Lui::LuiContextRecord::LuiContextRecord(void *,void *,LPALUICLIENTMODE)
0x1800cabac  mov     rbx, rax
0x1800cabaf  mov     [rbp+var_28], rax
0x1800cabb3  lea     r8, [rbp+var_20]
0x1800cabb7  lea     rdx, [rbp+var_18]
0x1800cabbb  mov     rcx, r14
0x1800cabbe  call    ??$_Try_emplace@AEBQEAX$$V@?$map@PEAXV?$unique_ptr@VLuiContextRecord@Lui@LPA@@U?$default_delete@VLuiContextRecord@Lui@LPA@@@std@@@std@@U?$less@PEAX@2@V?$allocator@U?$pair@QEAXV?$unique_ptr@VLuiContextRecord@Lui@LPA@@U?$default_delete@VLuiContextRecord@Lui@LPA@@@std@@@std@@@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@QEAXV?$unique_ptr@VLuiContextRecord@Lui@LPA@@U?$default_delete@VLuiContextRecord@Lui@LPA@@@std@@@std@@@std@@PEAX@std@@_N@1@AEBQEAX@Z; std::map<void *,std::unique_ptr<LPA::Lui::LuiContextRecord>>::_Try_emplace<void * const &,>(void * const &)
0x1800cabc3  mov     rcx, [rax]
0x1800cabc6  mov     [rbp+var_28], 0
0x1800cabce  mov     rdx, [rcx+28h]
0x1800cabd2  mov     [rcx+28h], rbx
0x1800cabd6  test    rdx, rdx
0x1800cabd9  jz      short loc_1800CABE1
0x1800cabdb  call    ??R?$default_delete@VLuiContextRecord@Lui@LPA@@@std@@QEBAXPEAVLuiContextRecord@Lui@LPA@@@Z; std::default_delete<LPA::Lui::LuiContextRecord>::operator()(LPA::Lui::LuiContextRecord *)
0x1800cabe0  nop
0x1800cabe1  lea     rcx, [rbp+var_28]
0x1800cabe5  call    ??1?$unique_ptr@VLuiContextRecord@Lui@LPA@@U?$default_delete@VLuiContextRecord@Lui@LPA@@@std@@@std@@QEAA@XZ; std::unique_ptr<LPA::Lui::LuiContextRecord>::~unique_ptr<LPA::Lui::LuiContextRecord>(void)
0x1800cabea  mov     rcx, [rsi+98h]; unsigned __int64
0x1800cabf1  call    ?SetRpcClientCount@ServiceHandler@@SAX_K@Z; ServiceHandler::SetRpcClientCount(unsigned __int64)
0x1800cabf6  mov     rbx, [rbp+var_20]
0x1800cabfa  jmp     short loc_1800CAC02
0x1800cabfc  mov     r15d, 800700B7h
0x1800cac02  mov     [rbx+28h], r15d
0x1800cac06  mov     rcx, [rbx+20h]
0x1800cac0a  jmp     loc_1800CAB29
0x1800cac0f  mov     eax, cs:CallbackContext
0x1800cac15  cmp     eax, 4
0x1800cac18  jbe     short loc_1800CAC4F
0x1800cac1a  lea     rdx, word_18013411E
0x1800cac21  lea     rax, aLpaLuiOnluirpc_21; "LPA::Lui::OnLuiRpcOpenHandle"
0x1800cac28  mov     [rbp+arg_8], rax
0x1800cac2c  lea     rax, aLpaservicelui; "LpaServiceLui"
0x1800cac33  mov     [rbp+var_28], rax
0x1800cac37  lea     rax, [rbp+arg_8]
0x1800cac3b  mov     [rsp+58h+var_30], rax
0x1800cac40  lea     rax, [rbp+var_28]
0x1800cac44  mov     [rsp+58h+var_38], rax
0x1800cac49  call    ??$Write@U?$_tlgWrapSz@D@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x1800cac4e  nop
0x1800cac4f  mov     rcx, [rdi+8]; this
0x1800cac53  test    rcx, rcx
0x1800cac56  jz      short loc_1800CAC5D
0x1800cac58  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800cac5d  add     rsp, 58h
0x1800cac61  pop     r15
0x1800cac63  pop     r14
0x1800cac65  pop     r13
0x1800cac67  pop     r12
0x1800cac69  pop     rdi
0x1800cac6a  pop     rsi
0x1800cac6b  pop     rbx
0x1800cac6c  pop     rbp
0x1800cac6d  retn
```
