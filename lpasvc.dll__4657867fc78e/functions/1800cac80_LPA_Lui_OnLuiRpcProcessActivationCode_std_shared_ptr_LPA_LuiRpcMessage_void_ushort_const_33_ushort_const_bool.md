# LPA::Lui::OnLuiRpcProcessActivationCode(std::shared_ptr<LPA::LuiRpcMessage>,void *,ushort const (*)[33],ushort const *,bool)

- ea: `0x1800cac80`
- end: `0x1800cb151`
- name: `?OnLuiRpcProcessActivationCode@Lui@LPA@@EEAAXV?$shared_ptr@VLuiRpcMessage@LPA@@@std@@PEAXPEAY0CB@$$CBGPEBG_N@Z`
- size: `1233`
- prototype: ``
- caller_count: `0`
- callee_count: `25`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x180001f1c`
- `0x180006cac`
- `0x180007ee0`
- `0x18000df90`
- `0x18000ebf4`
- `0x1800709e4`
- `0x180071320`
- `0x180071610`
- `0x180071ac8`
- `0x180080a28`
- `0x1800996f4`
- `0x1800a4db8`
- `0x1800c49d8`
- `0x1800c4ea8`
- `0x1800c527c`
- `0x1800c5974`
- `0x1800c6278`
- `0x1800c62b4`
- `0x1800c62d0`
- `0x1800c646c`
- `0x1800cac80`
- `0x1800ce30c`
- `0x1800d9a44`
- `0x1800eb4a0`
- `0x180101010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1800cae7f`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1800cae7f`

## string_xrefs

- `0x1800cb0ad`: `LpaServiceLui`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall LPA::Lui::OnLuiRpcProcessActivationCode(
        __int64 a1,
        LPA::LuiRpcMessage **a2,
        __int64 a3,
        unsigned __int16 *a4,
        __int64 a5,
        char a6)
{
  LPA::LuiRpcMessage *v10; // rcx
  unsigned int v11; // r15d
  int ContextRecordForOperation; // edi
  __int64 v13; // rdi
  __int64 (__fastcall *v14)(__int64, unsigned __int16 *, __int64, __int64); // rbx
  _QWORD *v15; // rax
  LPA::Lui::LuiContextRecord *v16; // rcx
  __int64 v17; // r9
  void **v18; // rbx
  __int64 v19; // rax
  unsigned __int16 (*v20)[33]; // r8
  __int64 v21; // rcx
  __int64 v22; // r9
  int v23; // ecx
  int v24; // r8d
  int v25; // r9d
  int v26; // ecx
  int v27; // r8d
  int v28; // r9d
  std::_Ref_count_base *v29; // rcx
  unsigned int v30; // [rsp+20h] [rbp-110h]
  __int64 v31; // [rsp+B0h] [rbp-80h] BYREF
  int v32; // [rsp+B8h] [rbp-78h] BYREF
  int v33; // [rsp+BCh] [rbp-74h] BYREF
  unsigned int v34; // [rsp+C0h] [rbp-70h] BYREF
  int v35; // [rsp+C4h] [rbp-6Ch] BYREF
  __int64 v36; // [rsp+C8h] [rbp-68h] BYREF
  int v37; // [rsp+D0h] [rbp-60h] BYREF
  unsigned __int16 *v38; // [rsp+D8h] [rbp-58h] BYREF
  std::_Ref_count_base *v39[2]; // [rsp+E0h] [rbp-50h] BYREF
  int v40; // [rsp+F0h] [rbp-40h] BYREF
  int v41; // [rsp+F4h] [rbp-3Ch] BYREF
  unsigned int v42[2]; // [rsp+F8h] [rbp-38h] BYREF
  OLECHAR *v43; // [rsp+100h] [rbp-30h] BYREF
  LuiApiServer *LuiContextHandle; // [rsp+108h] [rbp-28h] BYREF
  const unsigned __int16 *v45; // [rsp+110h] [rbp-20h] BYREF
  const unsigned __int16 *v46; // [rsp+118h] [rbp-18h] BYREF
  const unsigned __int16 *v47; // [rsp+120h] [rbp-10h] BYREF
  const unsigned __int16 *v48; // [rsp+128h] [rbp-8h] BYREF
  const unsigned __int16 *v49; // [rsp+130h] [rbp+0h] BYREF
  _QWORD v50[2]; // [rsp+138h] [rbp+8h] BYREF
  int v51[2]; // [rsp+148h] [rbp+18h] BYREF
  int v52; // [rsp+150h] [rbp+20h]
  GUID pclsid; // [rsp+160h] [rbp+30h] BYREF
  _BYTE v54[32]; // [rsp+170h] [rbp+40h] BYREF
  OLECHAR sz[40]; // [rsp+190h] [rbp+60h] BYREF
  unsigned __int16 v56[33]; // [rsp+1E0h] [rbp+B0h] BYREF

  v50[1] = a2;
  v38 = a4;
  v36 = a5;
  v31 = 0;
  *(_QWORD *)v51 = 0;
  v52 = 0;
  v37 = 0;
  v33 = 11;
  v10 = *a2;
  v11 = *((_DWORD *)*a2 + 8);
  v32 = v11;
  LuiContextHandle = (LuiApiServer *)LPA::LuiRpcMessage::GetLuiContextHandle(v10);
  (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 112) + 168LL))(*(_QWORD *)(a1 + 112));
  v30 = (unsigned int)a4;
  ContextRecordForOperation = LPA::Lui::GetContextRecordForOperation(a1 - 8, LuiContextHandle, 11, a3);
  if ( ContextRecordForOperation >= 0 )
  {
    v13 = *(_QWORD *)(a1 + 112);
    v14 = *(__int64 (__fastcall **)(__int64, unsigned __int16 *, __int64, __int64))(*(_QWORD *)v13 + 176LL);
    v15 = (_QWORD *)std::enable_shared_from_this<LPA::ApduHelper::UiccOperation>::shared_from_this(a1 + 32, v39);
    std::weak_ptr<LPA::EsimManagerCompletionHandler>::weak_ptr<LPA::EsimManagerCompletionHandler>(
      (__int64 *)&pclsid,
      v15);
    LPA::Lui::LuiContextRecord::GetClientModeInternal(0);
    LPA::Lui::LuiContextRecord::GetClientTokenRef(v16);
    v30 = v11;
    LOBYTE(v17) = a6;
    ContextRecordForOperation = v14(v13, a4, v36, v17);
    if ( v39[1] )
      std::_Ref_count_base::_Decref(v39[1]);
    if ( ContextRecordForOperation >= 0 )
    {
      v18 = (void **)std::make_unique<LPA::Lui::OperationRecord,enum LPA::LPAESIMOPERATIONINTERNAL const &,void * const &,unsigned long const &,unsigned short const (* &)[33],0>(
                       (unsigned int)&v31,
                       (unsigned int)&v33,
                       (unsigned int)&LuiContextHandle,
                       (unsigned int)&v32,
                       (__int64)&v38);
      v19 = std::map<unsigned long,std::unique_ptr<LPA::Lui::OperationRecord>>::_Try_emplace<unsigned long const &,>(
              a1 + 96,
              &pclsid,
              &v37);
      std::unique_ptr<LPA::Lui::OperationRecord>::operator=<std::default_delete<LPA::Lui::OperationRecord>,0>(
        (void **)(*(_QWORD *)v19 + 40LL),
        v18);
      std::unique_ptr<LPA::Lui::OperationRecord>::~unique_ptr<LPA::Lui::OperationRecord>(&v31);
    }
  }
  sz[0] = 0;
  memset_0(&sz[1], 0, 0x4Eu);
  v56[0] = 0;
  memset_0(&v56[1], 0, 0x40u);
  std::string::string(v54, &word_180111902);
  pclsid = 0;
  LPA::Lui::TelemetryGetInterfaceGuidFromEsimId(
    (LPA::Lui *)(a1 - 8),
    (const unsigned __int16 (*)[33])a4,
    (unsigned __int16 (*)[40])sz);
  CLSIDFromString(sz, &pclsid);
  CommonUtil::WritePiiFilteredEsimIdToBuffer((CommonUtil *)a4, (const unsigned __int16 (*)[33])v56, v20);
  LPA::Util::TelemetryGetSmdpAddressFromActivationCode(v36, v54);
  if ( (unsigned int)dword_18015A5E0 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18015A5E0, 0x800000000000LL) )
  {
    v45 = &qword_1801130E8;
    v46 = &qword_1801130E8;
    v33 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int16 *))(**(_QWORD **)(a1 + 112) + 48LL))(
            *(_QWORD *)(a1 + 112),
            a4);
    v47 = &qword_1801130E8;
    v48 = &qword_1801130E8;
    v49 = &qword_1801130E8;
    v32 = (v51[0] & 1) != 0 ? v51[1] : 0;
    v40 = 255;
    v50[0] = &qword_1801130E8;
    *(_QWORD *)v42 = v56;
    v43 = sz;
    v41 = 11;
    v34 = v11;
    v35 = ContextRecordForOperation;
    LODWORD(v38) = 0;
    v21 = *(_QWORD *)(a1 + 112);
    *(GUID *)v39 = pclsid;
    LOBYTE(v22) = a6;
    LODWORD(v36) = (*(unsigned __int8 (__fastcall **)(__int64, unsigned __int16 *, std::_Ref_count_base **, __int64))(*(_QWORD *)v21 + 32LL))(
                     v21,
                     a4,
                     v39,
                     v22);
    LODWORD(v31) = (*(unsigned __int8 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 112) + 40LL))(*(_QWORD *)(a1 + 112));
    v39[0] = (std::_Ref_count_base *)std::_String_val<std::_Simple_types<char>>::_Myptr(v54);
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
      v23,
      (unsigned int)&unk_180133570,
      v24,
      v25,
      (__int64)v39,
      (__int64)&v31,
      (__int64)&v36,
      (__int64)&v38,
      (__int64)&v35,
      (__int64)&v34,
      (__int64)&v41,
      (__int64)&v43,
      (__int64)v42,
      (__int64)v50,
      (__int64)&v40,
      (__int64)&v32,
      (__int64)&v49,
      (__int64)&v48,
      (__int64)&v47,
      (__int64)&v33,
      (__int64)&v46,
      (__int64)&v45);
  }
  std::string::_Tidy_deallocate(v54);
  if ( ContextRecordForOperation < 0 )
  {
    if ( (unsigned int)CallbackContext > 4 )
    {
      LODWORD(v31) = v52;
      LODWORD(v36) = v51[1];
      LODWORD(v38) = v51[0];
      v39[0] = (std::_Ref_count_base *)"LPA_ERROR_DETAILS";
      v35 = ContextRecordForOperation;
      v34 = v11;
      v43 = (OLECHAR *)"LPA::Lui::OnLuiRpcProcessActivationCode";
      *(_QWORD *)v42 = "LpaServiceLui";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v26,
        (unsigned int)&dword_1801334F4,
        v27,
        v28,
        (__int64)v42,
        (__int64)&v43,
        (__int64)&v34,
        (__int64)&v35,
        (__int64)v39,
        (__int64)&v38,
        (__int64)&v36,
        (__int64)&v31);
    }
    LuiApiServer::_CompleteLuiApiAsyncHelper(
      LuiContextHandle,
      (void *)(unsigned int)ContextRecordForOperation,
      (int)v51,
      (const struct LPA_ERROR_DETAILS *)v11,
      v30);
  }
  v29 = a2[1];
  if ( v29 )
    std::_Ref_count_base::_Decref(v29);
}

```

## disassembly

```asm
0x1800cac80  push    rbp
0x1800cac82  push    rbx
0x1800cac83  push    rsi
0x1800cac84  push    rdi
0x1800cac85  push    r12
0x1800cac87  push    r13
0x1800cac89  push    r14
0x1800cac8b  push    r15
0x1800cac8d  lea     rbp, [rsp-118h]
0x1800cac95  sub     rsp, 248h
0x1800cac9c  mov     rax, cs:__security_cookie
0x1800caca3  xor     rax, rsp
0x1800caca6  mov     [rbp+150h+var_50], rax
0x1800cacad  mov     rsi, r9
0x1800cacb0  mov     rbx, r8
0x1800cacb3  mov     r12, rdx
0x1800cacb6  mov     r14, rcx
0x1800cacb9  mov     [rbp+150h+var_140], rdx
0x1800cacbd  mov     [rbp+150h+var_1A8], r9
0x1800cacc1  mov     rax, [rbp+150h+arg_20]
0x1800cacc8  mov     [rbp+150h+var_1B8], rax
0x1800caccc  mov     [rbp+150h+var_1D0], 0
0x1800cacd4  xor     eax, eax
0x1800cacd6  mov     qword ptr [rbp+150h+var_138], rax
0x1800cacda  mov     [rbp+150h+var_130], eax
0x1800cacdd  mov     [rbp+150h+var_1B0], eax
0x1800cace0  mov     [rbp+150h+var_1C4], 0Bh
0x1800cace7  mov     rcx, [rdx]; this
0x1800cacea  mov     r15d, [rcx+20h]
0x1800cacee  mov     [rbp+150h+var_1C8], r15d
0x1800cacf2  call    ?GetLuiContextHandle@LuiRpcMessage@LPA@@QEBAPEAXXZ; LPA::LuiRpcMessage::GetLuiContextHandle(void)
0x1800cacf7  mov     rdi, rax
0x1800cacfa  mov     [rbp+150h+var_178], rax
0x1800cacfe  mov     rcx, [r14+70h]
0x1800cad02  mov     rdx, [rcx]
0x1800cad05  mov     rax, [rdx+0A8h]
0x1800cad0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cad11  lea     rcx, [rbp+150h+var_1D0]
0x1800cad15  mov     [rsp+280h+var_250], rcx
0x1800cad1a  mov     byte ptr [rsp+280h+var_258], al
0x1800cad1e  mov     qword ptr [rsp+280h+var_260], rsi
0x1800cad23  mov     r9, rbx
0x1800cad26  mov     r8d, 0Bh
0x1800cad2c  mov     rdx, rdi
0x1800cad2f  lea     rcx, [r14-8]
0x1800cad33  call    ?GetContextRecordForOperation@Lui@LPA@@AEAAJQEAXW4LPAESIMOPERATIONINTERNAL@2@PEAXPEAY0CB@$$CBG_NAEAPEAVLuiContextRecord@12@@Z; LPA::Lui::GetContextRecordForOperation(void * const,LPA::LPAESIMOPERATIONINTERNAL,void *,ushort const (*)[33],bool,LPA::Lui::LuiContextRecord * &)
0x1800cad38  mov     edi, eax
0x1800cad3a  mov     r13, [rbp+150h+var_1D0]
0x1800cad3e  test    eax, eax
0x1800cad40  js      loc_1800CAE1F
0x1800cad46  mov     rdi, [r14+70h]
0x1800cad4a  mov     rax, [rdi]
0x1800cad4d  mov     rbx, [rax+0B0h]
0x1800cad54  lea     rcx, [r14+20h]
0x1800cad58  lea     rdx, [rbp+150h+var_1A0]
0x1800cad5c  call    ?shared_from_this@?$enable_shared_from_this@VUiccOperation@ApduHelper@LPA@@@std@@QEAA?AV?$shared_ptr@VUiccOperation@ApduHelper@LPA@@@2@XZ; std::enable_shared_from_this<LPA::ApduHelper::UiccOperation>::shared_from_this(void)
0x1800cad61  nop
0x1800cad62  mov     rdx, rax
0x1800cad65  lea     rcx, [rbp+150h+pclsid]
0x1800cad69  call    ??$?0VLui@LPA@@$0A@@?$weak_ptr@UEsimManagerCompletionHandler@LPA@@@std@@QEAA@AEBV?$shared_ptr@VLui@LPA@@@1@@Z; std::weak_ptr<LPA::EsimManagerCompletionHandler>::weak_ptr<LPA::EsimManagerCompletionHandler>(std::shared_ptr<LPA::Lui> const &)
0x1800cad6e  mov     r10, rax
0x1800cad71  mov     rcx, r13
0x1800cad74  call    ?GetClientModeInternal@LuiContextRecord@Lui@LPA@@QEBA?AW4LPACLIENTMODEINTERNAL@3@XZ; LPA::Lui::LuiContextRecord::GetClientModeInternal(void)
0x1800cad79  mov     r9d, eax
0x1800cad7c  call    ?GetClientTokenRef@LuiContextRecord@Lui@LPA@@QEBAPEBQEAXXZ; LPA::Lui::LuiContextRecord::GetClientTokenRef(void)
0x1800cad81  lea     rcx, [rbp+150h+var_1B0]
0x1800cad85  mov     [rsp+280h+var_238], rcx
0x1800cad8a  lea     rcx, [rbp+150h+var_138]
0x1800cad8e  mov     [rsp+280h+var_240], rcx
0x1800cad93  mov     [rsp+280h+var_248], r10
0x1800cad98  mov     dword ptr [rsp+280h+var_250], r9d
0x1800cad9d  mov     [rsp+280h+var_258], rax
0x1800cada2  mov     [rsp+280h+var_260], r15d
0x1800cada7  mov     r9b, [rbp+150h+arg_28]
0x1800cadae  mov     r8, [rbp+150h+var_1B8]
0x1800cadb2  mov     rdx, rsi
0x1800cadb5  mov     rcx, rdi
0x1800cadb8  mov     rax, rbx
0x1800cadbb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cadc0  mov     edi, eax
0x1800cadc2  mov     rcx, [rbp+150h+var_1A0+8]; this
0x1800cadc6  test    rcx, rcx
0x1800cadc9  jz      short loc_1800CADD0
0x1800cadcb  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800cadd0  test    edi, edi
0x1800cadd2  js      short loc_1800CAE1F
0x1800cadd4  lea     rax, [rbp+150h+var_1A8]
0x1800cadd8  mov     qword ptr [rsp+280h+var_260], rax
0x1800caddd  lea     r9, [rbp+150h+var_1C8]
0x1800cade1  lea     r8, [rbp+150h+var_178]
0x1800cade5  lea     rdx, [rbp+150h+var_1C4]
0x1800cade9  lea     rcx, [rbp+150h+var_1D0]
0x1800caded  call    ??$make_unique@VOperationRecord@Lui@LPA@@AEBW4LPAESIMOPERATIONINTERNAL@3@AEBQEAXAEBKAEAPEAY0CB@$$CBG$0A@@std@@YA?AV?$unique_ptr@VOperationRecord@Lui@LPA@@U?$default_delete@VOperationRecord@Lui@LPA@@@std@@@0@AEBW4LPAESIMOPERATIONINTERNAL@LPA@@AEBQEAXAEBKAEAPEAY0CB@$$CBG@Z; std::make_unique<LPA::Lui::OperationRecord,LPA::LPAESIMOPERATIONINTERNAL const &,void * const &,ulong const &,ushort const (* &)[33],0>(LPA::LPAESIMOPERATIONINTERNAL const &,void * const &,ulong const &,ushort const (* &)[33])
0x1800cadf2  mov     rbx, rax
0x1800cadf5  lea     rcx, [r14+60h]
0x1800cadf9  lea     r8, [rbp+150h+var_1B0]
0x1800cadfd  lea     rdx, [rbp+150h+pclsid]
0x1800cae01  call    ??$_Try_emplace@AEBK$$V@?$map@KV?$unique_ptr@VOperationRecord@Lui@LPA@@U?$default_delete@VOperationRecord@Lui@LPA@@@std@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$unique_ptr@VOperationRecord@Lui@LPA@@U?$default_delete@VOperationRecord@Lui@LPA@@@std@@@std@@@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBKV?$unique_ptr@VOperationRecord@Lui@LPA@@U?$default_delete@VOperationRecord@Lui@LPA@@@std@@@std@@@std@@PEAX@std@@_N@1@AEBK@Z; std::map<ulong,std::unique_ptr<LPA::Lui::OperationRecord>>::_Try_emplace<ulong const &,>(ulong const &)
0x1800cae06  mov     rcx, [rax]
0x1800cae09  add     rcx, 28h ; '('
0x1800cae0d  mov     rdx, rbx
0x1800cae10  call    ??$?4U?$default_delete@VOperationRecord@Lui@LPA@@@std@@$0A@@?$unique_ptr@VOperationRecord@Lui@LPA@@U?$default_delete@VOperationRecord@Lui@LPA@@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::unique_ptr<LPA::Lui::OperationRecord>::operator=<std::default_delete<LPA::Lui::OperationRecord>,0>(std::unique_ptr<LPA::Lui::OperationRecord> &&)
0x1800cae15  nop
0x1800cae16  lea     rcx, [rbp+150h+var_1D0]
0x1800cae1a  call    ??1?$unique_ptr@VOperationRecord@Lui@LPA@@U?$default_delete@VOperationRecord@Lui@LPA@@@std@@@std@@QEAA@XZ; std::unique_ptr<LPA::Lui::OperationRecord>::~unique_ptr<LPA::Lui::OperationRecord>(void)
0x1800cae1f  xor     eax, eax
0x1800cae21  mov     [rbp+150h+sz], ax
0x1800cae25  xor     edx, edx; Val
0x1800cae27  lea     r8d, [rax+4Eh]; Size
0x1800cae2b  lea     rcx, [rbp+150h+var_EE]; void *
0x1800cae2f  call    memset_0
0x1800cae34  xor     eax, eax
0x1800cae36  mov     [rbp+150h+var_A0], ax
0x1800cae3d  xor     edx, edx; Val
0x1800cae3f  lea     r8d, [rax+40h]; Size
0x1800cae43  lea     rcx, [rbp+150h+var_A0+2]; void *
0x1800cae4a  call    memset_0
0x1800cae4f  lea     rdx, word_180111902
0x1800cae56  lea     rcx, [rbp+150h+var_110]
0x1800cae5a  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1800cae5f  nop
0x1800cae60  xorps   xmm0, xmm0
0x1800cae63  movups  xmmword ptr [rbp+150h+pclsid.Data1], xmm0
0x1800cae67  lea     r8, [rbp+150h+sz]; unsigned __int16 (*)[40]
0x1800cae6b  mov     rdx, rsi; unsigned __int16 (*)[33]
0x1800cae6e  lea     rcx, [r14-8]; this
0x1800cae72  call    ?TelemetryGetInterfaceGuidFromEsimId@Lui@LPA@@AEAAXPEAY0CB@$$CBGAEAY0CI@G@Z; LPA::Lui::TelemetryGetInterfaceGuidFromEsimId(ushort const (*)[33],ushort (&)[40])
0x1800cae77  lea     rdx, [rbp+150h+pclsid]; pclsid
0x1800cae7b  lea     rcx, [rbp+150h+sz]; lpsz
0x1800cae7f  call    cs:__imp_CLSIDFromString
0x1800cae85  lea     rdx, [rbp+150h+var_A0]; unsigned __int16 (*)[33]
0x1800cae8c  mov     rcx, rsi; this
0x1800cae8f  call    ?WritePiiFilteredEsimIdToBuffer@CommonUtil@@YAXPEAY0CB@$$CBGAEAY0CB@G@Z; CommonUtil::WritePiiFilteredEsimIdToBuffer(ushort const (*)[33],ushort (&)[33])
0x1800cae94  lea     rdx, [rbp+150h+var_110]
0x1800cae98  mov     rcx, [rbp+150h+var_1B8]
0x1800cae9c  call    ?TelemetryGetSmdpAddressFromActivationCode@Util@LPA@@YAJPEBGAEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; LPA::Util::TelemetryGetSmdpAddressFromActivationCode(ushort const *,std::string &)
0x1800caea1  mov     eax, cs:dword_18015A5E0
0x1800caea7  cmp     eax, 5
0x1800caeaa  jbe     loc_1800CB05E
0x1800caeb0  mov     rdx, 800000000000h
0x1800caeba  lea     rcx, dword_18015A5E0
0x1800caec1  call    _tlgKeywordOn
0x1800caec6  test    al, al
0x1800caec8  jz      loc_1800CB05E
0x1800caece  lea     rbx, qword_1801130E8
0x1800caed5  mov     [rbp+150h+var_170], rbx
0x1800caed9  mov     [rbp+150h+var_168], rbx
0x1800caedd  mov     rcx, [r14+70h]
0x1800caee1  mov     rax, [rcx]
0x1800caee4  mov     rdx, rsi
0x1800caee7  mov     rax, [rax+30h]
0x1800caeeb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800caef0  mov     [rbp+150h+var_1C4], eax
0x1800caef3  mov     [rbp+150h+var_160], rbx
0x1800caef7  mov     [rbp+150h+var_158], rbx
0x1800caefb  mov     [rbp+150h+var_150], rbx
0x1800caeff  mov     al, byte ptr [rbp+150h+var_138]
0x1800caf02  and     al, 1
0x1800caf04  neg     al
0x1800caf06  sbb     ecx, ecx
0x1800caf08  and     ecx, [rbp+150h+var_138+4]
0x1800caf0b  mov     [rbp+150h+var_1C8], ecx
0x1800caf0e  test    r13, r13
0x1800caf11  jz      short loc_1800CAF19
0x1800caf13  mov     eax, [r13+10h]
0x1800caf17  jmp     short loc_1800CAF1E
0x1800caf19  mov     eax, 0FFh
0x1800caf1e  mov     [rbp+150h+var_190], eax
0x1800caf21  mov     [rbp+150h+var_148], rbx
0x1800caf25  lea     rax, [rbp+150h+var_A0]
0x1800caf2c  mov     qword ptr [rbp+150h+var_188], rax
0x1800caf30  lea     rax, [rbp+150h+sz]
0x1800caf34  mov     [rbp+150h+var_180], rax
0x1800caf38  mov     [rbp+150h+var_18C], 0Bh
0x1800caf3f  mov     [rbp+150h+var_1C0], r15d
0x1800caf43  mov     [rbp+150h+var_1BC], edi
0x1800caf46  mov     dword ptr [rbp+150h+var_1A8], 0
0x1800caf4d  mov     rcx, [r14+70h]
0x1800caf51  movaps  xmm0, xmmword ptr [rbp+150h+pclsid.Data1]
0x1800caf55  movdqa  xmmword ptr [rbp+150h+var_1A0], xmm0
0x1800caf5a  mov     rax, [rcx]
0x1800caf5d  mov     r9b, [rbp+150h+arg_28]
0x1800caf64  lea     r8, [rbp+150h+var_1A0]
0x1800caf68  mov     rdx, rsi
0x1800caf6b  mov     rax, [rax+20h]
0x1800caf6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800caf74  movzx   eax, al
0x1800caf77  mov     dword ptr [rbp+150h+var_1B8], eax
0x1800caf7a  mov     rcx, [r14+70h]
0x1800caf7e  mov     rax, [rcx]
0x1800caf81  mov     rax, [rax+28h]
0x1800caf85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800caf8a  movzx   eax, al
0x1800caf8d  mov     dword ptr [rbp+150h+var_1D0], eax
0x1800caf90  lea     rcx, [rbp+150h+var_110]
0x1800caf94  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x1800caf99  mov     [rbp+150h+var_1A0], rax
0x1800caf9d  lea     rax, [rbp+150h+var_170]
0x1800cafa1  mov     [rsp+280h+var_1D8], rax
0x1800cafa9  lea     rax, [rbp+150h+var_168]
0x1800cafad  mov     [rsp+280h+var_1E0], rax
0x1800cafb5  lea     rax, [rbp+150h+var_1C4]
0x1800cafb9  mov     [rsp+280h+var_1E8], rax
0x1800cafc1  lea     rax, [rbp+150h+var_160]
0x1800cafc5  mov     [rsp+280h+var_1F0], rax
0x1800cafcd  lea     rax, [rbp+150h+var_158]
0x1800cafd1  mov     [rsp+280h+var_1F8], rax
0x1800cafd9  lea     rax, [rbp+150h+var_150]
0x1800cafdd  mov     [rsp+280h+var_200], rax
0x1800cafe5  lea     rax, [rbp+150h+var_1C8]
0x1800cafe9  mov     [rsp+280h+var_208], rax
0x1800cafee  lea     rax, [rbp+150h+var_190]
0x1800caff2  mov     [rsp+280h+var_210], rax
0x1800caff7  lea     rax, [rbp+150h+var_148]
0x1800caffb  mov     [rsp+280h+var_218], rax
0x1800cb000  lea     rax, [rbp+150h+var_188]
0x1800cb004  mov     [rsp+280h+var_220], rax
0x1800cb009  lea     rax, [rbp+150h+var_180]
0x1800cb00d  mov     [rsp+280h+var_228], rax
0x1800cb012  lea     rax, [rbp+150h+var_18C]
0x1800cb016  mov     [rsp+280h+var_230], rax
0x1800cb01b  lea     rax, [rbp+150h+var_1C0]
0x1800cb01f  mov     [rsp+280h+var_238], rax
0x1800cb024  lea     rax, [rbp+150h+var_1BC]
0x1800cb028  mov     [rsp+280h+var_240], rax
0x1800cb02d  lea     rax, [rbp+150h+var_1A8]
0x1800cb031  mov     [rsp+280h+var_248], rax
0x1800cb036  lea     rax, [rbp+150h+var_1B8]
0x1800cb03a  mov     [rsp+280h+var_250], rax
0x1800cb03f  lea     rax, [rbp+150h+var_1D0]
0x1800cb043  mov     [rsp+280h+var_258], rax
0x1800cb048  lea     rax, [rbp+150h+var_1A0]
0x1800cb04c  mov     qword ptr [rsp+280h+var_260], rax
0x1800cb051  lea     rdx, unk_180133570
0x1800cb058  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@U2@U2@U2@U2@U?$_tlgWrapSz@G@@U3@U3@U2@U2@U3@U3@U3@U2@U3@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@44444AEBU?$_tlgWrapSz@G@@5544555455@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x1800cb05d  nop
0x1800cb05e  lea     rcx, [rbp+150h+var_110]
0x1800cb062  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800cb067  test    edi, edi
0x1800cb069  jns     loc_1800CB11F
0x1800cb06f  mov     eax, cs:CallbackContext
0x1800cb075  cmp     eax, 4
0x1800cb078  jbe     loc_1800CB10C
0x1800cb07e  mov     eax, [rbp+150h+var_130]
0x1800cb081  mov     dword ptr [rbp+150h+var_1D0], eax
0x1800cb084  mov     eax, [rbp+150h+var_138+4]
0x1800cb087  mov     dword ptr [rbp+150h+var_1B8], eax
0x1800cb08a  mov     eax, [rbp+150h+var_138]
0x1800cb08d  mov     dword ptr [rbp+150h+var_1A8], eax
0x1800cb090  lea     rax, aLpaErrorDetail; "LPA_ERROR_DETAILS"
0x1800cb097  mov     [rbp+150h+var_1A0], rax
0x1800cb09b  mov     [rbp+150h+var_1BC], edi
0x1800cb09e  mov     [rbp+150h+var_1C0], r15d
0x1800cb0a2  lea     rax, aLpaLuiOnluirpc_18; "LPA::Lui::OnLuiRpcProcessActivationCode"
0x1800cb0a9  mov     [rbp+150h+var_180], rax
0x1800cb0ad  lea     rax, aLpaservicelui; "LpaServiceLui"
0x1800cb0b4  mov     qword ptr [rbp+150h+var_188], rax
0x1800cb0b8  lea     rax, [rbp+150h+var_1D0]
0x1800cb0bc  mov     [rsp+280h+var_228], rax
0x1800cb0c1  lea     rax, [rbp+150h+var_1B8]
0x1800cb0c5  mov     [rsp+280h+var_230], rax
0x1800cb0ca  lea     rax, [rbp+150h+var_1A8]
0x1800cb0ce  mov     [rsp+280h+var_238], rax
0x1800cb0d3  lea     rax, [rbp+150h+var_1A0]
0x1800cb0d7  mov     [rsp+280h+var_240], rax
0x1800cb0dc  lea     rax, [rbp+150h+var_1BC]
0x1800cb0e0  mov     [rsp+280h+var_248], rax
0x1800cb0e5  lea     rax, [rbp+150h+var_1C0]
0x1800cb0e9  mov     [rsp+280h+var_250], rax
0x1800cb0ee  lea     rax, [rbp+150h+var_180]
0x1800cb0f2  mov     [rsp+280h+var_258], rax
0x1800cb0f7  lea     rax, [rbp+150h+var_188]
0x1800cb0fb  mov     qword ptr [rsp+280h+var_260], rax; unsigned int
0x1800cb100  lea     rdx, dword_1801334F4
0x1800cb107  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U2@U1@U2@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@43444@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800cb10c  mov     r9d, r15d; struct LPA_ERROR_DETAILS *
0x1800cb10f  lea     r8, [rbp+150h+var_138]; int
0x1800cb113  mov     edx, edi; void *
0x1800cb115  mov     rcx, [rbp+150h+var_178]; this
0x1800cb119  call    ?_CompleteLuiApiAsyncHelper@LuiApiServer@@YAXPEAXJPEBULPA_ERROR_DETAILS@@K@Z; LuiApiServer::_CompleteLuiApiAsyncHelper(void *,long,LPA_ERROR_DETAILS const *,ulong)
0x1800cb11e  nop
0x1800cb11f  mov     rcx, [r12+8]; this
0x1800cb124  test    rcx, rcx
0x1800cb127  jz      short loc_1800CB12E
0x1800cb129  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800cb12e  mov     rcx, [rbp+150h+var_50]
0x1800cb135  xor     rcx, rsp; StackCookie
0x1800cb138  call    __security_check_cookie
0x1800cb13d  add     rsp, 248h
0x1800cb144  pop     r15
0x1800cb146  pop     r14
0x1800cb148  pop     r13
0x1800cb14a  pop     r12
0x1800cb14c  pop     rdi
0x1800cb14d  pop     rsi
0x1800cb14e  pop     rbx
0x1800cb14f  pop     rbp
0x1800cb150  retn
```
