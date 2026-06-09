# wil::ProfileDataStore::CallLoadAsync$_ResumeCoro$1_Windows::Data::Security::Passkey::ScenarioKeysItemPdr_

- ea: `0x18002b230`
- end: `0x18002ba7c`
- name: `wil::ProfileDataStore::CallLoadAsync$_ResumeCoro$1_Windows::Data::Security::Passkey::ScenarioKeysItemPdr_`
- size: `2124`
- prototype: ``
- caller_count: `1`
- callee_count: `22`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18003a85c`

## callees

- `0x180003080`
- `0x180003520`
- `0x180007a5c`
- `0x18000ce74`
- `0x18000cfcc`
- `0x18000f7fc`
- `0x18001354c`
- `0x18001361c`
- `0x18002b230`
- `0x180037b84`
- `0x1800402c8`
- `0x18004280c`
- `0x180043674`
- `0x18004562c`
- `0x180045914`
- `0x180045e14`
- `0x180049238`
- `0x18004aae8`
- `0x18004d8f0`
- `0x18004eaac`
- `0x18004edec`
- `0x180061010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18002b5f6`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18002b677`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18002b700`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18002b5f6`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18002b677`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18002b700`

## pseudocode

```c
void __fastcall wil::ProfileDataStore::CallLoadAsync__ResumeCoro_1_Windows::Data::Security::Passkey::ScenarioKeysItemPdr_(
        __int64 a1)
{
  __int64 v2; // r15
  _QWORD *v3; // r8
  __int64 v4; // rdx
  signed __int32 v5; // eax
  signed __int32 v6; // ett
  __int64 v7; // r13
  __int64 v8; // rax
  __int64 v9; // r12
  __int64 v10; // rdi
  _QWORD *v11; // rax
  volatile signed __int32 *v12; // rdi
  __int64 v13; // rdx
  __int64 v14; // r8
  volatile signed __int32 *v15; // rdi
  __int64 *v16; // r12
  const char *v17; // r9
  int v18; // r8d
  int v19; // edx
  int v20; // ecx
  int v21; // edx
  int v22; // eax
  _QWORD *v23; // rax
  _QWORD *v24; // rcx
  __int64 v25; // rdx
  __int64 v26; // rax
  __int64 v27; // rdx
  __int64 v28; // rcx
  __int64 v29; // rax
  __int64 v30; // rdx
  __int64 v31; // rcx
  __int64 v32; // rax
  __int64 v33; // r8
  __int64 Async; // r8
  __int64 v35; // rdx
  __int64 v36; // r8
  __int64 v37; // rdx
  __int64 v38; // r8
  __int64 v39; // rdx
  __int64 v40; // r8
  __int64 *v41; // rax
  __int64 v42; // rdx
  _QWORD *v43; // rax
  volatile signed __int32 *v44; // rdi
  volatile signed __int32 *v45; // rdi
  int CloudStore; // [rsp+70h] [rbp-168h]
  wil::details::in1diag3 *retaddr; // [rsp+1D8h] [rbp+0h]

  v2 = a1 + 8;
  if ( (unsigned __int16)(*(_WORD *)(a1 + 8) + 1) > 4u )
  {
LABEL_78:
    __debugbreak();
  }
  else
  {
    switch ( *(_WORD *)(a1 + 8) )
    {
      case 0xFFFF:
      case 1:
      case 3:
        wil::details::coro::result_holder<std::shared_ptr<wil::ProfileDataItem<Windows::Data::Security::Passkey::RecoveryItemPdr>>>::~result_holder<std::shared_ptr<wil::ProfileDataItem<Windows::Data::Security::Passkey::RecoveryItemPdr>>>(a1 - 32);
        `wil::ProfileDataStore::CallLoadAsync<Windows::Data::Security::Passkey::ScenarioKeysItemPdr>'::`8'::_parameters_::~_parameters_(v2 + 704);
        if ( *(_WORD *)(a1 + 10) )
          operator delete((void *)(a1 - 48), 0x330u);
        return;
      case 0:
        goto LABEL_78;
      case 2:
        v3 = *(_QWORD **)(a1 + 712);
        *(_QWORD *)(a1 + 16) = 0;
        *(_QWORD *)(a1 + 24) = 0;
        v4 = v3[1];
        if ( !v4 )
          goto LABEL_74;
        v5 = *(_DWORD *)(v4 + 8);
        do
        {
          if ( !v5 )
LABEL_74:
            std::_Throw_bad_weak_ptr();
          v6 = v5;
          v5 = _InterlockedCompareExchange((volatile signed __int32 *)(v4 + 8), v5 + 1, v5);
        }
        while ( v6 != v5 );
        *(_QWORD *)(a1 + 16) = *v3;
        v7 = v3[1];
        *(_QWORD *)(a1 + 24) = v7;
        v8 = *(_QWORD *)(a1 + 752);
        if ( v8 && *(_DWORD *)(v8 + 16) )
        {
          *(_DWORD *)(a1 + 32) = 0;
          *(_DWORD *)(a1 + 36) = -2147023673;
          *(_OWORD *)(a1 + 40) = 0;
          *(_QWORD *)(a1 + 56) = 0;
          *(_QWORD *)(a1 + 64) = 7;
          *(_WORD *)(a1 + 40) = 0;
          *(_BYTE *)(a1 + 72) = 0;
          *(_BYTE *)(a1 + 73) = 0;
          *(_BYTE *)(a1 + 74) = 1;
          v9 = a1 + 80;
          *(_QWORD *)(a1 + 80) = 0;
          *(_DWORD *)(a1 + 88) = 1;
          *(_DWORD *)(a1 + 92) = 0;
          *(_DWORD *)(a1 + 96) = 0;
          *(_OWORD *)(a1 + 104) = 0;
          *(_OWORD *)(a1 + 120) = 0;
          *(_OWORD *)(a1 + 136) = 0;
          *(_QWORD *)(a1 + 120) = 0;
          *(_QWORD *)(a1 + 128) = 15;
          *(_BYTE *)(a1 + 104) = 0;
          *(_QWORD *)(a1 + 136) = 0;
          *(_QWORD *)(a1 + 144) = 0;
          *(_QWORD *)(a1 + 152) = 0;
          v10 = a1 + 40;
          v11 = (_QWORD *)std::make_shared<wil::ProfileDataItem<Windows::Data::Security::Passkey::PasskeyItemPdr>,Windows::Data::Security::Passkey::PasskeyItemPdr,wil::ProfileDataItemReference<Windows::Data::Security::Passkey::PasskeyItemPdr> &,int,enum wil::ProfileDataItemStatus,enum wil::DataDescriptionLanguage,wil::com_ptr_t<Windows::Internal::Storage::Cloud::ICloudStoreData,wil::err_exception_policy>,bool,bool,bool,std::wstring,long,int>(
                            (int)a1 + 160,
                            (int)a1 + 104,
                            *(_QWORD *)(a1 + 720),
                            (int)a1 + 96,
                            a1 + 92,
                            a1 + 88,
                            a1 + 80,
                            a1 + 74,
                            a1 + 73,
                            a1 + 72,
                            a1 + 40,
                            a1 + 36,
                            a1 + 32);
          *(_QWORD *)(a1 - 24) = 0;
          *(_QWORD *)(a1 - 16) = 0;
          *(_QWORD *)(a1 - 24) = *v11;
          *(_QWORD *)(a1 - 16) = v11[1];
          *v11 = 0;
          v11[1] = 0;
          *(_DWORD *)(a1 - 32) = 1;
          if ( *(_QWORD *)(a1 + 168) )
          {
            v12 = *(volatile signed __int32 **)(a1 + 168);
            if ( _InterlockedExchangeAdd(v12 + 2, 0xFFFFFFFF) == 1 )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v12)(v12);
              if ( _InterlockedExchangeAdd(v12 + 3, 0xFFFFFFFF) == 1 )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v12 + 8LL))(v12);
            }
            v10 = a1 + 40;
          }
          std::vector<unsigned char>::~vector<unsigned char>(a1 + 136);
          std::string::~string(a1 + 104);
          if ( *(_QWORD *)v9 )
            (*(void (**)(void))(**(_QWORD **)v9 + 16LL))();
          std::wstring::~wstring(v10, v13, v14);
          if ( v7 )
          {
            v15 = *(volatile signed __int32 **)(a1 + 24);
            if ( _InterlockedExchangeAdd(v15 + 2, 0xFFFFFFFF) == 1 )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v15)(v15);
              if ( _InterlockedExchangeAdd(v15 + 3, 0xFFFFFFFF) == 1 )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v15 + 8LL))(v15);
            }
          }
        }
        else
        {
          v16 = (__int64 *)(a1 + 176);
          *(_QWORD *)(a1 + 176) = 0;
          CloudStore = wil::details::SharedCloudStoreState::GetCloudStore(v3[2], a1 + 208);
          *(_QWORD *)(a1 + 216) = *(_QWORD *)(a1 + 760);
          *(_QWORD *)(a1 + 248) = *(_QWORD *)(a1 + 744);
          v18 = *(_DWORD *)(a1 + 736);
          v19 = v18 & 1;
          if ( (v18 & 4) != 0 )
          {
            if ( (v18 & 1) == 0 )
              wil::details::in1diag3::_FailFast_Unexpected(
                retaddr,
                (void *)0x8FE,
                (unsigned int)"onecoreuap\\internal\\sdk\\inc\\wil\\profiledatastore.h",
                v17);
            v19 |= 2u;
          }
          v20 = v19 | 4;
          if ( (v18 & 8) == 0 )
            v20 = v19;
          v21 = v20 | 8;
          if ( (v18 & 0x10) == 0 )
            v21 = v20;
          v22 = v21 | 0x10;
          if ( (v18 & 0x20) == 0 )
            v22 = v21;
          *(_DWORD *)(a1 + 280) = v22;
          v23 = (_QWORD *)wil::ProfileDataStore::GetTypeNameWideString<Windows::Data::Security::Passkey::ScenarioKeysItemPdr>(a1 + 320);
          v24 = v23;
          v25 = v23[2];
          if ( v23[3] > 7u )
            v24 = (_QWORD *)*v23;
          if ( (_DWORD)v25 )
          {
            if ( *((_WORD *)v24 + (unsigned int)v25) )
              abort();
            v26 = a1 + 296;
            *(_DWORD *)(a1 + 296) = 1;
            *(_DWORD *)(a1 + 300) = v25;
            *(_QWORD *)(a1 + 312) = v24;
          }
          else
          {
            v26 = 0;
          }
          *(_QWORD *)(a1 + 288) = v26;
          std::wstring::wstring(a1 + 384, *(_QWORD *)(a1 + 720));
          v27 = *(_QWORD *)(a1 + 400);
          if ( *(_QWORD *)(a1 + 408) <= 7u )
            v28 = a1 + 384;
          else
            v28 = *(_QWORD *)(a1 + 384);
          if ( (_DWORD)v27 )
          {
            if ( *(_WORD *)(v28 + 2LL * (unsigned int)v27) )
              abort();
            v29 = a1 + 360;
            *(_DWORD *)(a1 + 360) = 1;
            *(_DWORD *)(a1 + 364) = v27;
            *(_QWORD *)(a1 + 376) = v28;
          }
          else
          {
            v29 = 0;
          }
          *(_QWORD *)(a1 + 352) = v29;
          std::wstring::wstring(a1 + 448, *(_QWORD *)(a1 + 720) + 32LL);
          v30 = *(_QWORD *)(a1 + 464);
          if ( *(_QWORD *)(a1 + 472) <= 7u )
            v31 = a1 + 448;
          else
            v31 = *(_QWORD *)(a1 + 448);
          if ( (_DWORD)v30 )
          {
            if ( *(_WORD *)(v31 + 2LL * (unsigned int)v30) )
              abort();
            v32 = a1 + 424;
            *(_DWORD *)(a1 + 424) = 1;
            *(_DWORD *)(a1 + 428) = v30;
            *(_QWORD *)(a1 + 440) = v31;
          }
          else
          {
            v32 = 0;
          }
          *(_QWORD *)(a1 + 416) = v32;
          v33 = *(_QWORD *)(v2 + 704);
          *(_QWORD *)(a1 + 480) = *(_QWORD *)(v33 + 40);
          Async = winrt::impl::consume_Windows_Internal_Storage_Cloud_ICloudStore2<winrt::Windows::Internal::Storage::Cloud::CloudStore>::LoadAsync(
                    CloudStore,
                    (int)a1 + 512,
                    (int)v33 + 32,
                    (int)a1 + 480,
                    a1 + 416,
                    a1 + 352,
                    a1 + 288,
                    a1 + 280,
                    a1 + 248,
                    a1 + 216);
          wil::details::AsyncOpWaiter<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::Storage::Cloud::CloudStoreData>,winrt::Windows::Internal::Storage::Cloud::CloudStoreData>::AsyncOpWaiter<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::Storage::Cloud::CloudStoreData>,winrt::Windows::Internal::Storage::Cloud::CloudStoreData>(
            a1 + 184,
            a1 + 752,
            Async);
          if ( *(_QWORD *)(a1 + 512) )
            winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 512);
          std::wstring::~wstring(a1 + 448, v35, v36);
          std::wstring::~wstring(a1 + 384, v37, v38);
          std::wstring::~wstring(a1 + 320, v39, v40);
          if ( *(_QWORD *)(a1 + 208) )
            winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 208);
          v41 = (__int64 *)wil::details::AsyncOpWaiter<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::Storage::Cloud::CloudStoreData>,winrt::Windows::Internal::Storage::Cloud::CloudStoreData>::WaitForResult(
                             a1 + 184,
                             a1 + 520);
          if ( v16 != v41 )
          {
            v42 = *v41;
            *v41 = 0;
            *v16 = v42;
          }
          if ( *(_QWORD *)(a1 + 520) )
            winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 520);
          wil::details::AsyncOpWaiter<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::Storage::Cloud::CloudStoreSaveResult>,winrt::Windows::Internal::Storage::Cloud::CloudStoreSaveResult>::~AsyncOpWaiter<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::Storage::Cloud::CloudStoreSaveResult>,winrt::Windows::Internal::Storage::Cloud::CloudStoreSaveResult>(a1 + 184);
          v43 = wil::ProfileDataStore::Unmarshal<Windows::Data::Security::Passkey::ScenarioKeysItemPdr>(
                  (_QWORD *)(a1 + 672),
                  (__int64 (__fastcall ****)(_QWORD, __int64 *, _QWORD **))(a1 + 176),
                  *(_DWORD *)(a1 + 736));
          *(_QWORD *)(a1 - 24) = 0;
          *(_QWORD *)(a1 - 16) = 0;
          *(_QWORD *)(a1 - 24) = *v43;
          *(_QWORD *)(a1 - 16) = v43[1];
          *v43 = 0;
          v43[1] = 0;
          *(_DWORD *)(a1 - 32) = 1;
          if ( *(_QWORD *)(a1 + 680) )
          {
            v44 = *(volatile signed __int32 **)(a1 + 680);
            if ( _InterlockedExchangeAdd(v44 + 2, 0xFFFFFFFF) == 1 )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v44)(v44);
              if ( _InterlockedExchangeAdd(v44 + 3, 0xFFFFFFFF) == 1 )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v44 + 8LL))(v44);
            }
          }
          if ( *v16 )
            winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 176);
          if ( *(_QWORD *)(a1 + 24) )
          {
            v45 = *(volatile signed __int32 **)(a1 + 24);
            if ( _InterlockedExchangeAdd(v45 + 2, 0xFFFFFFFF) == 1 )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v45)(v45);
              if ( _InterlockedExchangeAdd(v45 + 3, 0xFFFFFFFF) == 1 )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v45 + 8LL))(v45);
            }
          }
        }
        *(_QWORD *)(a1 + 688) = a1 - 48;
        *(_WORD *)v2 = 0;
        `wil::details::coro::promise_base<std::shared_ptr<wil::ProfileDataItem<Windows::Data::Security::Passkey::RecoveryItemPdr>>>::final_suspend'::`2'::awaiter::await_suspend();
        break;
    }
  }
}

```

## disassembly

```asm
0x18002b230  mov     r11, rsp
0x18002b233  mov     [r11+10h], rbx
0x18002b237  mov     [r11+18h], rsi
0x18002b23b  mov     [r11+8], rcx
0x18002b23f  push    rdi
0x18002b240  push    r12
0x18002b242  push    r13
0x18002b244  push    r14
0x18002b246  push    r15
0x18002b248  sub     rsp, 1B0h
0x18002b24f  mov     rax, cs:__security_cookie
0x18002b256  xor     rax, rsp
0x18002b259  mov     [rsp+1D8h+var_38], rax
0x18002b261  mov     rsi, rcx
0x18002b264  mov     [rsp+1D8h+var_160], rcx
0x18002b269  lea     r15, [rsi+8]
0x18002b26d  movzx   eax, word ptr [r15]
0x18002b271  mov     [rsp+1D8h+var_158], ax
0x18002b279  mov     ebx, 1
0x18002b27e  add     ax, bx
0x18002b281  lea     ecx, [rbx+3]
0x18002b284  cmp     ax, cx
0x18002b287  ja      loc_18002BA36; jumptable 000000018002B2AA case 1
0x18002b28d  mov     [rsp+1D8h+var_150], r15
0x18002b295  movsx   rax, ax
0x18002b299  lea     rdx, __ImageBase
0x18002b2a0  mov     ecx, ds:(jpt_18002B2AA - 180000000h)[rdx+rax*4]; switch 5 cases
0x18002b2a7  add     rcx, rdx
0x18002b2aa  jmp     rcx; switch jump
0x18002b2ac  jmp     loc_18002BA07; jumptable 000000018002B2AA case 4
0x18002b2b1  xor     r14d, r14d; jumptable 000000018002B2AA case 3
0x18002b2b4  mov     r8, [r15+2C0h]
0x18002b2bb  mov     [rsi+10h], r14
0x18002b2bf  lea     r9, [rsi+18h]
0x18002b2c3  mov     [r9], r14
0x18002b2c6  mov     rdx, [r8+8]
0x18002b2ca  test    rdx, rdx
0x18002b2cd  jz      loc_18002B9D9
0x18002b2d3  mov     eax, [rdx+8]
0x18002b2d6  jmp     short loc_18002B2E2
0x18002b2d8  lea     ecx, [rax+1]
0x18002b2db  lock cmpxchg [rdx+8], ecx
0x18002b2e0  jz      short loc_18002B2EB
0x18002b2e2  test    eax, eax
0x18002b2e4  jnz     short loc_18002B2D8
0x18002b2e6  jmp     loc_18002B9D9
0x18002b2eb  mov     [rsp+1D8h+var_128], r9
0x18002b2f3  mov     rax, [r8]
0x18002b2f6  mov     [rsi+10h], rax
0x18002b2fa  mov     r13, [r8+8]
0x18002b2fe  mov     [r9], r13
0x18002b301  mov     rax, [rsi+2F0h]
0x18002b308  test    rax, rax
0x18002b30b  jz      loc_18002B51D
0x18002b311  mov     eax, [rax+10h]
0x18002b314  nop
0x18002b315  test    eax, eax
0x18002b317  jz      loc_18002B51D
0x18002b31d  mov     [rsi+20h], r14d
0x18002b321  lea     rbx, [rsi+24h]
0x18002b325  mov     dword ptr [rbx], 800704C7h
0x18002b32b  xorps   xmm0, xmm0
0x18002b32e  movups  xmmword ptr [rsi+28h], xmm0
0x18002b332  mov     [rsi+38h], r14
0x18002b336  mov     qword ptr [rsi+40h], 7
0x18002b33e  xor     ecx, ecx
0x18002b340  mov     [rsi+28h], cx
0x18002b344  lea     r11, [rsi+48h]
0x18002b348  mov     [r11], r14b
0x18002b34b  lea     r10, [rsi+49h]
0x18002b34f  mov     [r10], r14b
0x18002b352  lea     r8, [rsi+4Ah]
0x18002b356  mov     byte ptr [r8], 1
0x18002b35a  lea     r12, [rsi+50h]
0x18002b35e  mov     [r12], r14
0x18002b362  lea     rdx, [rsi+58h]
0x18002b366  mov     dword ptr [rdx], 1
0x18002b36c  lea     rax, [rsi+5Ch]
0x18002b370  mov     [rax], r14d
0x18002b373  lea     r9, [rsi+60h]
0x18002b377  mov     [r9], r14d
0x18002b37a  movups  xmmword ptr [rsi+68h], xmm0
0x18002b37e  movups  xmmword ptr [rsi+78h], xmm0
0x18002b382  movups  xmmword ptr [rsi+88h], xmm0
0x18002b389  mov     [rsi+78h], r14
0x18002b38d  mov     qword ptr [rsi+80h], 0Fh
0x18002b398  mov     [rsi+68h], r14b
0x18002b39c  mov     [rsi+88h], r14
0x18002b3a3  mov     [rsi+90h], r14
0x18002b3aa  mov     [rsi+98h], r14
0x18002b3b1  lea     rcx, [rsi+0A0h]
0x18002b3b8  lea     rdi, [rsi+20h]
0x18002b3bc  mov     [rsp+1D8h+var_178], rdi
0x18002b3c1  mov     [rsp+1D8h+var_180], rbx
0x18002b3c6  lea     rdi, [rsi+28h]
0x18002b3ca  mov     [rsp+1D8h+var_188], rdi
0x18002b3cf  mov     [rsp+1D8h+var_190], r11
0x18002b3d4  mov     [rsp+1D8h+var_198], r10
0x18002b3d9  mov     [rsp+1D8h+var_1A0], r8
0x18002b3de  mov     [rsp+1D8h+var_1A8], r12
0x18002b3e3  mov     [rsp+1D8h+var_1B0], rdx
0x18002b3e8  mov     [rsp+1D8h+var_1B8], rax
0x18002b3ed  mov     r8, [rsi+2D0h]
0x18002b3f4  lea     rdx, [rsi+68h]
0x18002b3f8  call    ??$make_shared@V?$ProfileDataItem@UPasskeyItemPdr@Passkey@Security@Data@Windows@@@wil@@UPasskeyItemPdr@Passkey@Security@Data@Windows@@AEAV?$ProfileDataItemReference@UPasskeyItemPdr@Passkey@Security@Data@Windows@@@2@HW4ProfileDataItemStatus@2@W4DataDescriptionLanguage@2@V?$com_ptr_t@UICloudStoreData@Cloud@Storage@Internal@Windows@@Uerr_exception_policy@wil@@@2@_N_N_NV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@JH@std@@YA?AV?$shared_ptr@V?$ProfileDataItem@UPasskeyItemPdr@Passkey@Security@Data@Windows@@@wil@@@0@$$QEAUPasskeyItemPdr@Passkey@Security@Data@Windows@@AEAV?$ProfileDataItemReference@UPasskeyItemPdr@Passkey@Security@Data@Windows@@@wil@@$$QEAH$$QEAW4ProfileDataItemStatus@8@$$QEAW4DataDescriptionLanguage@8@$$QEAV?$com_ptr_t@UICloudStoreData@Cloud@Storage@Internal@Windows@@Uerr_exception_policy@wil@@@8@$$QEA_N66$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAJ2@Z; std::make_shared<wil::ProfileDataItem<Windows::Data::Security::Passkey::PasskeyItemPdr>,Windows::Data::Security::Passkey::PasskeyItemPdr,wil::ProfileDataItemReference<Windows::Data::Security::Passkey::PasskeyItemPdr> &,int,wil::ProfileDataItemStatus,wil::DataDescriptionLanguage,wil::com_ptr_t<Windows::Internal::Storage::Cloud::ICloudStoreData,wil::err_exception_policy>,bool,bool,bool,std::wstring,long,int>(Windows::Data::Security::Passkey::PasskeyItemPdr &&,wil::ProfileDataItemReference<Windows::Data::Security::Passkey::PasskeyItemPdr> &,int &&,wil::ProfileDataItemStatus &&,wil::DataDescriptionLanguage &&,wil::com_ptr_t<Windows::Internal::Storage::Cloud::ICloudStoreData,wil::err_exception_policy> &&,bool &&,bool &&,bool &&,std::wstring &&,long &&,int &&)
0x18002b3fd  mov     [rsi-18h], r14
0x18002b401  mov     [rsi-10h], r14
0x18002b405  mov     rcx, [rax]
0x18002b408  mov     [rsi-18h], rcx
0x18002b40c  mov     rcx, [rax+8]
0x18002b410  mov     [rsi-10h], rcx
0x18002b414  mov     [rax], r14
0x18002b417  mov     [rax+8], r14
0x18002b41b  mov     dword ptr [rsi-20h], 1
0x18002b422  mov     rax, [rsi+0A8h]
0x18002b429  mov     [rsp+1D8h+var_110], rax
0x18002b431  or      ebx, 0FFFFFFFFh
0x18002b434  test    rax, rax
0x18002b437  jz      short loc_18002B47F
0x18002b439  mov     rdi, [rsi+0A8h]
0x18002b440  mov     [rsp+1D8h+var_110], rdi
0x18002b448  mov     eax, ebx
0x18002b44a  lock xadd [rdi+8], eax
0x18002b44f  add     eax, ebx
0x18002b451  jnz     short loc_18002B47B
0x18002b453  mov     rax, [rdi]
0x18002b456  mov     rcx, rdi
0x18002b459  mov     rax, [rax]
0x18002b45c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b461  mov     eax, ebx
0x18002b463  lock xadd [rdi+0Ch], eax
0x18002b468  add     eax, ebx
0x18002b46a  jnz     short loc_18002B47B
0x18002b46c  mov     rax, [rdi]
0x18002b46f  mov     rcx, rdi
0x18002b472  mov     rax, [rax+8]
0x18002b476  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b47b  lea     rdi, [rsi+28h]
0x18002b47f  lea     rcx, [rsi+88h]
0x18002b486  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x18002b48b  lea     rcx, [rsi+68h]
0x18002b48f  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18002b494  nop
0x18002b495  mov     rax, [r12]
0x18002b499  mov     [rsp+1D8h+var_168], rax
0x18002b49e  test    rax, rax
0x18002b4a1  jz      short loc_18002B4C2
0x18002b4a3  mov     rax, [r12]
0x18002b4a7  mov     [rsp+1D8h+var_168], rax
0x18002b4ac  mov     rcx, [rax]
0x18002b4af  mov     rax, [rcx+10h]
0x18002b4b3  mov     rcx, [r12]
0x18002b4b7  mov     [rsp+1D8h+var_168], rcx
0x18002b4bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b4c1  nop
0x18002b4c2  mov     rcx, rdi
0x18002b4c5  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002b4ca  nop
0x18002b4cb  mov     [rsp+1D8h+var_140], r13
0x18002b4d3  test    r13, r13
0x18002b4d6  jz      short loc_18002B518
0x18002b4d8  mov     rdi, [rsi+18h]
0x18002b4dc  mov     [rsp+1D8h+var_140], rdi
0x18002b4e4  mov     eax, ebx
0x18002b4e6  lock xadd [rdi+8], eax
0x18002b4eb  add     eax, ebx
0x18002b4ed  jnz     short loc_18002B518
0x18002b4ef  mov     rax, [rdi]
0x18002b4f2  mov     rcx, rdi
0x18002b4f5  mov     rax, [rax]
0x18002b4f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b4fd  mov     eax, ebx
0x18002b4ff  lock xadd [rdi+0Ch], eax
0x18002b504  add     eax, ebx
0x18002b506  jnz     short loc_18002B518
0x18002b508  mov     rax, [rdi]
0x18002b50b  mov     rcx, rdi
0x18002b50e  mov     rax, [rax+8]
0x18002b512  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b517  nop
0x18002b518  jmp     loc_18002B9EC
0x18002b51d  lea     r12, [rsi+0B0h]
0x18002b524  mov     [rsp+1D8h+var_138], r12
0x18002b52c  mov     [r12], r14
0x18002b530  lea     rdx, [rsi+0D0h]
0x18002b537  mov     rcx, [r8+10h]
0x18002b53b  call    ?GetCloudStore@SharedCloudStoreState@details@wil@@QEAA?BUCloudStore@Cloud@Storage@Internal@Windows@winrt@@XZ; wil::details::SharedCloudStoreState::GetCloudStore(void)
0x18002b540  mov     [rsp+1D8h+var_168], rax
0x18002b545  lea     rdi, [rsi+0D8h]
0x18002b54c  mov     rcx, [rsi+2F8h]
0x18002b553  mov     [rdi], rcx
0x18002b556  mov     rcx, [rsi+2E8h]
0x18002b55d  mov     [rsi+0F8h], rcx
0x18002b564  mov     r8d, [rsi+2E0h]
0x18002b56b  mov     edx, r8d
0x18002b56e  and     edx, ebx
0x18002b570  bt      r8d, 2
0x18002b575  jnb     short loc_18002B59A
0x18002b577  mov     rcx, [rsp+1D8h]; this
0x18002b57f  mov     al, dl
0x18002b581  xor     al, bl
0x18002b583  jz      short loc_18002B597
0x18002b585  lea     r8, aOnecoreuapInte_0; "onecoreuap\\internal\\sdk\\inc\\wil\\pr"...
0x18002b58c  mov     edx, 8FEh; void *
0x18002b591  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18002b597  or      edx, 2
0x18002b59a  mov     ecx, edx
0x18002b59c  or      ecx, 4
0x18002b59f  bt      r8d, 3
0x18002b5a4  cmovnb  ecx, edx
0x18002b5a7  mov     edx, ecx
0x18002b5a9  or      edx, 8
0x18002b5ac  bt      r8d, 4
0x18002b5b1  cmovnb  edx, ecx
0x18002b5b4  mov     eax, edx
0x18002b5b6  or      eax, 10h
0x18002b5b9  bt      r8d, 5
0x18002b5be  cmovnb  eax, edx
0x18002b5c1  mov     [rsi+118h], eax
0x18002b5c7  lea     rcx, [rsi+140h]
0x18002b5ce  call    ??$GetTypeNameWideString@UScenarioKeysItemPdr@Passkey@Security@Data@Windows@@@ProfileDataStore@wil@@CA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; wil::ProfileDataStore::GetTypeNameWideString<Windows::Data::Security::Passkey::ScenarioKeysItemPdr>(void)
0x18002b5d3  mov     rcx, rax
0x18002b5d6  mov     rdx, [rax+10h]
0x18002b5da  cmp     qword ptr [rax+18h], 7
0x18002b5df  jbe     short loc_18002B5E4
0x18002b5e1  mov     rcx, [rax]
0x18002b5e4  test    edx, edx
0x18002b5e6  jnz     short loc_18002B5ED
0x18002b5e8  mov     rax, r14
0x18002b5eb  jmp     short loc_18002B613
0x18002b5ed  mov     eax, edx
0x18002b5ef  cmp     [rcx+rax*2], r14w
0x18002b5f4  jz      short loc_18002B5FD
0x18002b5f6  call    cs:__imp_abort
0x18002b5fd  lea     rax, [rsi+128h]
0x18002b604  mov     [rax], ebx
0x18002b606  mov     [rsi+12Ch], edx
0x18002b60c  mov     [rsi+138h], rcx
0x18002b613  mov     [rsi+120h], rax
0x18002b61a  lea     rbx, [rsi+180h]
0x18002b621  mov     rdx, [rsi+2D0h]
0x18002b628  mov     rcx, rbx
0x18002b62b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18002b630  nop
0x18002b631  mov     rdx, [rsi+190h]
0x18002b638  mov     [rsp+1D8h+var_D8], rdx
0x18002b640  mov     rax, [rsi+198h]
0x18002b647  mov     [rsp+1D8h+var_D0], rax
0x18002b64f  cmp     rax, 7
0x18002b653  jbe     short loc_18002B662
0x18002b655  mov     rcx, [rbx]
0x18002b658  mov     [rsp+1D8h+var_E8], rcx
0x18002b660  jmp     short loc_18002B665
0x18002b662  mov     rcx, rbx
0x18002b665  test    edx, edx
0x18002b667  jnz     short loc_18002B66E
0x18002b669  mov     rax, r14
0x18002b66c  jmp     short loc_18002B698
0x18002b66e  mov     eax, edx
0x18002b670  cmp     [rcx+rax*2], r14w
0x18002b675  jz      short loc_18002B67E
0x18002b677  call    cs:__imp_abort
0x18002b67e  lea     rax, [rsi+168h]
0x18002b685  mov     dword ptr [rax], 1
0x18002b68b  mov     [rsi+16Ch], edx
0x18002b691  mov     [rsi+178h], rcx
0x18002b698  mov     [rsi+160h], rax
0x18002b69f  lea     rbx, [rsi+1C0h]
0x18002b6a6  mov     rdx, [rsi+2D0h]
0x18002b6ad  add     rdx, 20h ; ' '
0x18002b6b1  mov     rcx, rbx
0x18002b6b4  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18002b6b9  nop
0x18002b6ba  mov     rdx, [rsi+1D0h]
0x18002b6c1  mov     [rsp+1D8h+var_B8], rdx
0x18002b6c9  mov     rax, [rsi+1D8h]
0x18002b6d0  mov     [rsp+1D8h+var_B0], rax
0x18002b6d8  cmp     rax, 7
0x18002b6dc  jbe     short loc_18002B6EB
0x18002b6de  mov     rcx, [rbx]
0x18002b6e1  mov     [rsp+1D8h+var_C8], rcx
0x18002b6e9  jmp     short loc_18002B6EE
0x18002b6eb  mov     rcx, rbx
0x18002b6ee  test    edx, edx
0x18002b6f0  jnz     short loc_18002B6F7
0x18002b6f2  mov     rax, r14
0x18002b6f5  jmp     short loc_18002B721
0x18002b6f7  mov     eax, edx
0x18002b6f9  cmp     [rcx+rax*2], r14w
0x18002b6fe  jz      short loc_18002B707
0x18002b700  call    cs:__imp_abort
0x18002b707  lea     rax, [rsi+1A8h]
0x18002b70e  mov     dword ptr [rax], 1
0x18002b714  mov     [rsi+1ACh], edx
0x18002b71a  mov     [rsi+1B8h], rcx
0x18002b721  mov     [rsi+1A0h], rax
0x18002b728  mov     r8, [r15+2C0h]
0x18002b72f  lea     r9, [rsi+1E0h]
0x18002b736  mov     rax, [r8+28h]
0x18002b73a  mov     [r9], rax
  ... truncated ...
```
