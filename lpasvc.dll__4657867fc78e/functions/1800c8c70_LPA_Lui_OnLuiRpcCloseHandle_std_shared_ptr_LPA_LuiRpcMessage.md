# LPA::Lui::OnLuiRpcCloseHandle(std::shared_ptr<LPA::LuiRpcMessage>)

- ea: `0x1800c8c70`
- end: `0x1800c8f29`
- name: `?OnLuiRpcCloseHandle@Lui@LPA@@EEAAXV?$shared_ptr@VLuiRpcMessage@LPA@@@std@@@Z`
- size: `697`
- prototype: ``
- caller_count: `0`
- callee_count: `20`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180001010`
- `0x1800017c8`
- `0x18000df90`
- `0x18000ebf4`
- `0x18005cd20`
- `0x1800602e0`
- `0x180065bd4`
- `0x1800709e4`
- `0x180070d40`
- `0x180071344`
- `0x180071ac8`
- `0x1800996f4`
- `0x1800c5958`
- `0x1800c6278`
- `0x1800c646c`
- `0x1800c8c70`
- `0x1800cf388`
- `0x1800d7ee4`
- `0x1800ee218`
- `0x180101010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800c8ede`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800c8ede`

## string_xrefs

- `0x1800c8cdd`: `LpaServiceLui`
- `0x1800c8d54`: `LpaServiceLui`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall LPA::Lui::OnLuiRpcCloseHandle(__int64 a1, LPA::LuiRpcMessage **a2)
{
  LPA::LuiRpcMessage **v2; // r15
  __int64 v3; // rdx
  int v4; // ecx
  int v5; // r8d
  int v6; // r9d
  void *LuiContextHandle; // r14
  const char **v8; // rsi
  const char *v9; // rbx
  int v10; // edi
  const char *v11; // rax
  __int64 v12; // r15
  const char *v13; // rdi
  const unsigned __int16 *v14; // rax
  int v15; // ecx
  int v16; // r8d
  int v17; // r9d
  __int64 v18; // rsi
  __int64 (__fastcall *v19)(__int64, unsigned __int16 *, _QWORD, _QWORD, int, __int64, char *, __int64 *, __int64 *); // rdi
  _QWORD *v20; // rax
  int ClientModeInternal; // eax
  __int64 v22; // r9
  char *v23; // rbx
  std::_Ref_count_base *v24; // rcx
  char v25[8]; // [rsp+50h] [rbp-B0h] BYREF
  const char *v26; // [rsp+58h] [rbp-A8h] BYREF
  const char *v27; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v28; // [rsp+68h] [rbp-98h] BYREF
  const char *v29; // [rsp+70h] [rbp-90h] BYREF
  const char *v30; // [rsp+78h] [rbp-88h] BYREF
  LPA::LuiRpcMessage **v31; // [rsp+80h] [rbp-80h]
  LPA::LuiRpcMessage **v32; // [rsp+88h] [rbp-78h]
  __int64 v33; // [rsp+90h] [rbp-70h] BYREF
  char v34[8]; // [rsp+A0h] [rbp-60h] BYREF
  std::_Ref_count_base *v35; // [rsp+A8h] [rbp-58h]
  __int64 v36; // [rsp+B0h] [rbp-50h] BYREF
  int v37; // [rsp+B8h] [rbp-48h]
  unsigned __int16 v38[40]; // [rsp+C0h] [rbp-40h] BYREF

  v2 = a2;
  v31 = a2;
  v28 = a1;
  v32 = a2;
  LuiContextHandle = LPA::LuiRpcMessage::GetLuiContextHandle(*a2);
  v27 = (const char *)LuiContextHandle;
  if ( LuiContextHandle )
  {
    v8 = (const char **)(v3 + 144);
    std::_Tree<std::_Tmap_traits<void *,std::unique_ptr<LPA::Lui::LuiContextRecord>,std::less<void *>,std::allocator<std::pair<void * const,std::unique_ptr<LPA::Lui::LuiContextRecord>>>,0>>::find(
      v3 + 144,
      &v26,
      &v27);
    v9 = v26;
    if ( *v8 == v26 )
    {
      v10 = -2147023728;
    }
    else
    {
      v10 = 0;
      v11 = **(const char ***)(*((_QWORD *)v26 + 5) + 40LL);
      v27 = v11;
      v12 = v28;
      while ( !v11[25] )
      {
        v13 = v11 + 32;
        v26 = v11 + 32;
        memset_0(v38, 0, 0x42u);
        v36 = 0;
        v37 = 0;
        v25[0] = 0;
        LODWORD(v28) = 0;
        v14 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v13);
        v10 = StringCchCopyW(v38, 0x21u, v14);
        if ( v10 < 0 )
          goto LABEL_12;
        v18 = *(_QWORD *)(v12 + 112);
        v19 = *(__int64 (__fastcall **)(__int64, unsigned __int16 *, _QWORD, _QWORD, int, __int64, char *, __int64 *, __int64 *))(*(_QWORD *)v18 + 192LL);
        v20 = (_QWORD *)std::enable_shared_from_this<LPA::ApduHelper::UiccOperation>::shared_from_this(v12 + 32, v34);
        std::weak_ptr<LPA::EsimManagerCompletionHandler>::weak_ptr<LPA::EsimManagerCompletionHandler>(&v33, v20);
        ClientModeInternal = LPA::Lui::LuiContextRecord::GetClientModeInternal(*((_QWORD *)v9 + 5));
        v10 = v19(v18, v38, *((unsigned int *)v26 + 8), 0, ClientModeInternal, v22, v25, &v36, &v28);
        v15 = (int)v35;
        if ( v35 )
          std::_Ref_count_base::_Decref(v35);
        if ( v10 < 0 )
        {
LABEL_12:
          if ( (unsigned int)CallbackContext > 3 )
          {
            LODWORD(v26) = v10;
            v30 = "LPA::Lui::OnLuiRpcCloseHandle";
            v29 = "LpaServiceLui";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
              v15,
              (unsigned int)byte_18013403D,
              v16,
              v17,
              (__int64)&v29,
              (__int64)&v30,
              (__int64)&v26);
          }
        }
        std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,unsigned long>>>,std::_Iterator_base0>::operator++(&v27);
        v11 = v27;
      }
      v23 = (char *)std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned long const,std::unique_ptr<LPA::EnterpriseManager::OperationEntry>>>>::_Extract(
                      v12 + 144,
                      v9);
      std::unique_ptr<LPA::Lui::LuiContextRecord>::~unique_ptr<LPA::Lui::LuiContextRecord>(v23 + 40);
      std::_Deallocate<16>(v23, (struct std::nothrow_t *)0x30);
      ServiceHandler::SetRpcClientCount(*(_QWORD *)(v12 + 152));
      v2 = v31;
    }
    LuiContext::UnbindPipe((LuiContext *)LuiContextHandle);
    *((_DWORD *)LuiContextHandle + 10) = v10;
    SetEvent(*((HANDLE *)LuiContextHandle + 4));
    (*(void (__fastcall **)(void *))(*(_QWORD *)LuiContextHandle + 16LL))(LuiContextHandle);
  }
  else if ( (unsigned int)CallbackContext > 4 )
  {
    v27 = "LPA::Lui::OnLuiRpcCloseHandle";
    v26 = "LpaServiceLui";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>>(
      v4,
      (unsigned int)&byte_1801340B7,
      v5,
      v6,
      (__int64)&v26,
      (__int64)&v27);
  }
  v24 = v2[1];
  if ( v24 )
    std::_Ref_count_base::_Decref(v24);
}

```

## disassembly

```asm
0x1800c8c70  mov     [rsp-8+arg_10], rbx
0x1800c8c75  push    rbp
0x1800c8c76  push    rsi
0x1800c8c77  push    rdi
0x1800c8c78  push    r12
0x1800c8c7a  push    r13
0x1800c8c7c  push    r14
0x1800c8c7e  push    r15
0x1800c8c80  lea     rbp, [rsp-20h]
0x1800c8c85  sub     rsp, 120h
0x1800c8c8c  mov     rax, cs:__security_cookie
0x1800c8c93  xor     rax, rsp
0x1800c8c96  mov     [rbp+50h+var_40], rax
0x1800c8c9a  mov     r15, rdx
0x1800c8c9d  mov     [rbp+50h+var_D0], rdx
0x1800c8ca1  mov     rdx, rcx
0x1800c8ca4  mov     [rsp+150h+var_E8], rcx
0x1800c8ca9  mov     [rbp+50h+var_C8], r15
0x1800c8cad  mov     rcx, [r15]; this
0x1800c8cb0  call    ?GetLuiContextHandle@LuiRpcMessage@LPA@@QEBAPEAXXZ; LPA::LuiRpcMessage::GetLuiContextHandle(void)
0x1800c8cb5  mov     r14, rax
0x1800c8cb8  mov     [rsp+150h+var_F0], rax
0x1800c8cbd  test    rax, rax
0x1800c8cc0  jnz     short loc_1800C8D0E
0x1800c8cc2  mov     eax, cs:CallbackContext
0x1800c8cc8  cmp     eax, 4
0x1800c8ccb  jbe     loc_1800C8EF4
0x1800c8cd1  lea     r12, aLpaLuiOnluirpc_7; "LPA::Lui::OnLuiRpcCloseHandle"
0x1800c8cd8  mov     [rsp+150h+var_F0], r12
0x1800c8cdd  lea     r13, aLpaservicelui; "LpaServiceLui"
0x1800c8ce4  mov     [rsp+150h+var_F8], r13
0x1800c8ce9  lea     rax, [rsp+150h+var_F0]
0x1800c8cee  mov     [rsp+150h+var_128], rax
0x1800c8cf3  lea     rax, [rsp+150h+var_F8]
0x1800c8cf8  mov     [rsp+150h+var_130], rax
0x1800c8cfd  lea     rdx, byte_1801340B7
0x1800c8d04  call    ??$Write@U?$_tlgWrapSz@D@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x1800c8d09  jmp     loc_1800C8EF4
0x1800c8d0e  lea     rsi, [rdx+90h]
0x1800c8d15  lea     r8, [rsp+150h+var_F0]
0x1800c8d1a  lea     rdx, [rsp+150h+var_F8]
0x1800c8d1f  mov     rcx, rsi
0x1800c8d22  call    ?find@?$_Tree@V?$_Tmap_traits@PEAXV?$unique_ptr@VLuiContextRecord@Lui@LPA@@U?$default_delete@VLuiContextRecord@Lui@LPA@@@std@@@std@@U?$less@PEAX@2@V?$allocator@U?$pair@QEAXV?$unique_ptr@VLuiContextRecord@Lui@LPA@@U?$default_delete@VLuiContextRecord@Lui@LPA@@@std@@@std@@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEAXV?$unique_ptr@VLuiContextRecord@Lui@LPA@@U?$default_delete@VLuiContextRecord@Lui@LPA@@@std@@@std@@@std@@@std@@@std@@@2@AEBQEAX@Z; std::_Tree<std::_Tmap_traits<void *,std::unique_ptr<LPA::Lui::LuiContextRecord>,std::less<void *>,std::allocator<std::pair<void * const,std::unique_ptr<LPA::Lui::LuiContextRecord>>>,0>>::find(void * const &)
0x1800c8d27  mov     rbx, [rsp+150h+var_F8]
0x1800c8d2c  cmp     [rsi], rbx
0x1800c8d2f  jnz     short loc_1800C8D3B
0x1800c8d31  mov     edi, 80070490h
0x1800c8d36  jmp     loc_1800C8ECE
0x1800c8d3b  xor     edi, edi
0x1800c8d3d  mov     rax, [rbx+28h]
0x1800c8d41  mov     rax, [rax+28h]
0x1800c8d45  mov     rax, [rax]
0x1800c8d48  mov     [rsp+150h+var_F0], rax
0x1800c8d4d  lea     r12, aLpaLuiOnluirpc_7; "LPA::Lui::OnLuiRpcCloseHandle"
0x1800c8d54  lea     r13, aLpaservicelui; "LpaServiceLui"
0x1800c8d5b  mov     r15, [rsp+150h+var_E8]
0x1800c8d60  cmp     byte ptr [rax+19h], 0
0x1800c8d64  jnz     loc_1800C8E96
0x1800c8d6a  lea     rdi, [rax+20h]
0x1800c8d6e  mov     [rsp+150h+var_F8], rdi
0x1800c8d73  xor     edx, edx; Val
0x1800c8d75  lea     r8d, [rdx+42h]; Size
0x1800c8d79  lea     rcx, [rbp+50h+var_90]; void *
0x1800c8d7d  call    memset_0
0x1800c8d82  xor     eax, eax
0x1800c8d84  mov     [rbp+50h+var_A0], rax
0x1800c8d88  mov     [rbp+50h+var_98], eax
0x1800c8d8b  mov     [rsp+150h+var_100], al
0x1800c8d8f  mov     dword ptr [rsp+150h+var_E8], eax
0x1800c8d93  mov     rcx, rdi
0x1800c8d96  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800c8d9b  mov     r8, rax; unsigned __int16 *
0x1800c8d9e  mov     edx, 21h ; '!'; unsigned __int64
0x1800c8da3  lea     rcx, [rbp+50h+var_90]; unsigned __int16 *
0x1800c8da7  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800c8dac  mov     edi, eax
0x1800c8dae  test    eax, eax
0x1800c8db0  js      loc_1800C8E3F
0x1800c8db6  mov     rsi, [r15+70h]
0x1800c8dba  mov     rax, [rsi]
0x1800c8dbd  mov     rdi, [rax+0C0h]
0x1800c8dc4  lea     rcx, [r15+20h]
0x1800c8dc8  lea     rdx, [rbp+50h+var_B0]
0x1800c8dcc  call    ?shared_from_this@?$enable_shared_from_this@VUiccOperation@ApduHelper@LPA@@@std@@QEAA?AV?$shared_ptr@VUiccOperation@ApduHelper@LPA@@@2@XZ; std::enable_shared_from_this<LPA::ApduHelper::UiccOperation>::shared_from_this(void)
0x1800c8dd1  nop
0x1800c8dd2  mov     rdx, rax
0x1800c8dd5  lea     rcx, [rbp+50h+var_C0]
0x1800c8dd9  call    ??$?0VLui@LPA@@$0A@@?$weak_ptr@UEsimManagerCompletionHandler@LPA@@@std@@QEAA@AEBV?$shared_ptr@VLui@LPA@@@1@@Z; std::weak_ptr<LPA::EsimManagerCompletionHandler>::weak_ptr<LPA::EsimManagerCompletionHandler>(std::shared_ptr<LPA::Lui> const &)
0x1800c8dde  mov     r9, rax
0x1800c8de1  mov     rcx, [rbx+28h]
0x1800c8de5  call    ?GetClientModeInternal@LuiContextRecord@Lui@LPA@@QEBA?AW4LPACLIENTMODEINTERNAL@3@XZ; LPA::Lui::LuiContextRecord::GetClientModeInternal(void)
0x1800c8dea  lea     rcx, [rsp+150h+var_E8]
0x1800c8def  mov     [rsp+150h+var_110], rcx
0x1800c8df4  lea     rcx, [rbp+50h+var_A0]
0x1800c8df8  mov     [rsp+150h+var_118], rcx
0x1800c8dfd  lea     rcx, [rsp+150h+var_100]
0x1800c8e02  mov     [rsp+150h+var_120], rcx
0x1800c8e07  mov     [rsp+150h+var_128], r9
0x1800c8e0c  mov     dword ptr [rsp+150h+var_130], eax
0x1800c8e10  xor     r9d, r9d
0x1800c8e13  mov     r8, [rsp+150h+var_F8]
0x1800c8e18  mov     r8d, [r8+20h]
0x1800c8e1c  lea     rdx, [rbp+50h+var_90]
0x1800c8e20  mov     rcx, rsi
0x1800c8e23  mov     rax, rdi
0x1800c8e26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c8e2b  mov     edi, eax
0x1800c8e2d  mov     rcx, [rbp+50h+var_A8]; this
0x1800c8e31  test    rcx, rcx
0x1800c8e34  jz      short loc_1800C8E3B
0x1800c8e36  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800c8e3b  test    edi, edi
0x1800c8e3d  jns     short loc_1800C8E82
0x1800c8e3f  mov     eax, cs:CallbackContext
0x1800c8e45  cmp     eax, 3
0x1800c8e48  jbe     short loc_1800C8E82
0x1800c8e4a  mov     dword ptr [rsp+150h+var_F8], edi
0x1800c8e4e  mov     [rsp+150h+var_D8], r12
0x1800c8e53  mov     [rsp+150h+var_E0], r13
0x1800c8e58  lea     rax, [rsp+150h+var_F8]
0x1800c8e5d  mov     [rsp+150h+var_120], rax
0x1800c8e62  lea     rax, [rsp+150h+var_D8]
0x1800c8e67  mov     [rsp+150h+var_128], rax
0x1800c8e6c  lea     rax, [rsp+150h+var_E0]
0x1800c8e71  mov     [rsp+150h+var_130], rax
0x1800c8e76  lea     rdx, byte_18013403D
0x1800c8e7d  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1800c8e82  lea     rcx, [rsp+150h+var_F0]
0x1800c8e87  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,ulong>>>,std::_Iterator_base0>::operator++(void)
0x1800c8e8c  mov     rax, [rsp+150h+var_F0]
0x1800c8e91  jmp     loc_1800C8D60
0x1800c8e96  mov     rdx, rbx
0x1800c8e99  lea     rcx, [r15+90h]
0x1800c8ea0  call    ?_Extract@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKV?$unique_ptr@VOperationEntry@EnterpriseManager@LPA@@U?$default_delete@VOperationEntry@EnterpriseManager@LPA@@@std@@@std@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBKV?$unique_ptr@VOperationEntry@EnterpriseManager@LPA@@U?$default_delete@VOperationEntry@EnterpriseManager@LPA@@@std@@@std@@@std@@PEAX@2@V?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKV?$unique_ptr@VOperationEntry@EnterpriseManager@LPA@@U?$default_delete@VOperationEntry@EnterpriseManager@LPA@@@std@@@std@@@std@@@std@@@std@@U_Iterator_base0@2@@2@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<ulong const,std::unique_ptr<LPA::EnterpriseManager::OperationEntry>>>>::_Extract(std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<ulong const,std::unique_ptr<LPA::EnterpriseManager::OperationEntry>>>>,std::_Iterator_base0>)
0x1800c8ea5  mov     rbx, rax
0x1800c8ea8  lea     rcx, [rax+28h]
0x1800c8eac  call    ??1?$unique_ptr@VLuiContextRecord@Lui@LPA@@U?$default_delete@VLuiContextRecord@Lui@LPA@@@std@@@std@@QEAA@XZ; std::unique_ptr<LPA::Lui::LuiContextRecord>::~unique_ptr<LPA::Lui::LuiContextRecord>(void)
0x1800c8eb1  mov     edx, 30h ; '0'
0x1800c8eb6  mov     rcx, rbx
0x1800c8eb9  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800c8ebe  mov     rcx, [r15+98h]; unsigned __int64
0x1800c8ec5  call    ?SetRpcClientCount@ServiceHandler@@SAX_K@Z; ServiceHandler::SetRpcClientCount(unsigned __int64)
0x1800c8eca  mov     r15, [rbp+50h+var_D0]
0x1800c8ece  mov     rcx, r14; this
0x1800c8ed1  call    ?UnbindPipe@LuiContext@@QEAAXXZ; LuiContext::UnbindPipe(void)
0x1800c8ed6  mov     [r14+28h], edi
0x1800c8eda  mov     rcx, [r14+20h]; hEvent
0x1800c8ede  call    cs:__imp_SetEvent
0x1800c8ee4  mov     rax, [r14]
0x1800c8ee7  mov     rcx, r14
0x1800c8eea  mov     rax, [rax+10h]
0x1800c8eee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c8ef3  nop
0x1800c8ef4  mov     rcx, [r15+8]; this
0x1800c8ef8  test    rcx, rcx
0x1800c8efb  jz      short loc_1800C8F02
0x1800c8efd  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800c8f02  mov     rcx, [rbp+50h+var_40]
0x1800c8f06  xor     rcx, rsp; StackCookie
0x1800c8f09  call    __security_check_cookie
0x1800c8f0e  mov     rbx, [rsp+150h+arg_10]
0x1800c8f16  add     rsp, 120h
0x1800c8f1d  pop     r15
0x1800c8f1f  pop     r14
0x1800c8f21  pop     r13
0x1800c8f23  pop     r12
0x1800c8f25  pop     rdi
0x1800c8f26  pop     rsi
0x1800c8f27  pop     rbp
0x1800c8f28  retn
```
