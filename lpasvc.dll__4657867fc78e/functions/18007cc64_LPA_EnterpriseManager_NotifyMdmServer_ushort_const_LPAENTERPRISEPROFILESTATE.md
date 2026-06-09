# LPA::EnterpriseManager::NotifyMdmServer(ushort const *,LPAENTERPRISEPROFILESTATE)

- ea: `0x18007cc64`
- end: `0x18007cf19`
- name: `?NotifyMdmServer@EnterpriseManager@LPA@@AEAAXPEBGW4LPAENTERPRISEPROFILESTATE@@@Z`
- size: `693`
- prototype: ``
- caller_count: `2`
- callee_count: `12`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18007d420`
- `0x18007da00`

## callees

- `0x1800017c8`
- `0x18000df90`
- `0x18000ebd0`
- `0x18000ebf4`
- `0x180071344`
- `0x180071650`
- `0x180074140`
- `0x180074524`
- `0x180074e4c`
- `0x1800779f4`
- `0x18007cc64`
- `0x180101010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x18007cd73`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x18007cd73`

## string_xrefs

- `0x18007ce97`: `LpaServiceEnterpriseManager`
- `0x18007ccbc`: `com.microsoft.mdm.euiccs.profilestate`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall LPA::EnterpriseManager::NotifyMdmServer(__int64 a1, const char *a2, unsigned int a3)
{
  __int64 v4; // rcx
  int v5; // ebx
  int v6; // r8d
  int v7; // r9d
  __int64 v8; // rdi
  __int64 (__fastcall *v9)(__int64, _QWORD, __int64, __int64, _QWORD *, __int64 *); // rbx
  __int64 v10; // rax
  __int64 v11; // rdi
  __int64 (__fastcall *v12)(__int64, _QWORD); // rbx
  _QWORD *v13; // rax
  __int64 result; // rax
  __int16 *v15; // rdx
  __int64 v16; // rcx
  __int64 v17; // rcx
  __int64 v18; // [rsp+40h] [rbp-79h] BYREF
  __int64 v19; // [rsp+48h] [rbp-71h] BYREF
  __int64 v20; // [rsp+50h] [rbp-69h] BYREF
  const char *v21; // [rsp+58h] [rbp-61h] BYREF
  __int64 v22; // [rsp+60h] [rbp-59h] BYREF
  _QWORD v23[4]; // [rsp+70h] [rbp-49h] BYREF
  int v24; // [rsp+90h] [rbp-29h]
  __int64 v25; // [rsp+98h] [rbp-21h]
  int v26; // [rsp+A0h] [rbp-19h]
  int v27; // [rsp+A4h] [rbp-15h]
  int v28; // [rsp+A8h] [rbp-11h]
  HSTRING_HEADER hstringHeader; // [rsp+B0h] [rbp-9h] BYREF
  __int64 v30; // [rsp+C8h] [rbp+Fh]
  _BYTE v31[24]; // [rsp+D0h] [rbp+17h] BYREF
  __int64 v32; // [rsp+E8h] [rbp+2Fh]

  v21 = a2;
  v20 = 0;
  v22 = 0;
  v19 = 0x900000000LL;
  memset_0(v23, 0, 0x40u);
  v30 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"com.microsoft.mdm.euiccs.profilestate",
    0x26u,
    0x25u);
  v23[0] = v30;
  v30 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"./Device/Vendor/MSFT/eUICCs",
    0x1Cu,
    0x1Bu);
  v23[1] = v30;
  std::_Integral_to_string<unsigned short,int>(&hstringHeader, a3);
  v18 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&hstringHeader);
  v25 = *(_QWORD *)(Microsoft::WRL::Wrappers::HStringReference::HStringReference(v31, &v18) + 24);
  v32 = 0;
  std::wstring::_Tidy_deallocate(&hstringHeader);
  v24 = 0;
  v26 = 0;
  v27 = 1;
  v28 = 3;
  v30 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Internal.Management.Provision.SessionManager",
    0x35u,
    0x34u);
  v20 = 0;
  v18 = 0;
  v5 = RoActivateInstance(v30, &v18);
  if ( v5 >= 0 )
  {
    if ( !memcmp_0(&GUID_7611a5c3_7a06_4585_9149_369c349c5e79, &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90, 0x10u) )
    {
      v20 = v18;
    }
    else
    {
      v5 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v18)(
             v18,
             &GUID_7611a5c3_7a06_4585_9149_369c349c5e79,
             &v20);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
    }
  }
  if ( v5 < 0 )
    goto LABEL_12;
  v8 = v20;
  v9 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64, __int64, _QWORD *, __int64 *))(*(_QWORD *)v20 + 88LL);
  v10 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v31, &v21);
  v5 = v9(v8, *(_QWORD *)(v10 + 24), v19, 1, v23, &v22);
  if ( v5 < 0 )
    goto LABEL_12;
  v11 = v22;
  v12 = *(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v22 + 48LL);
  v13 = (_QWORD *)Microsoft::WRL::Callback_Microsoft::WRL::Implements_Microsoft::WRL::RuntimeClassFlags_2__Windows::Foundation::IAsyncOperationCompletedHandler_Windows::Internal::Management::Provision::SessionResult____Microsoft::WRL::FtmBase___LPA::EnterpriseManager::NotifyMdmServer_::_8_::_lambda_1___(&v19);
  v5 = v12(v11, *v13);
  v4 = v19;
  if ( v19 )
  {
    v19 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  }
  if ( v5 < 0 )
  {
LABEL_12:
    result = (unsigned int)CallbackContext;
    if ( (unsigned int)CallbackContext <= 2 )
      goto LABEL_15;
    v15 = (__int16 *)byte_18012B67D;
  }
  else
  {
    result = (unsigned int)CallbackContext;
    if ( (unsigned int)CallbackContext <= 4 )
      goto LABEL_15;
    v15 = &word_18012B6B6;
  }
  v21 = "LPA::EnterpriseManager::NotifyMdmServer";
  v19 = (__int64)"LpaServiceEnterpriseManager";
  LODWORD(v18) = v5;
  result = _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
             v4,
             (_DWORD)v15,
             v6,
             v7,
             (__int64)&v19,
             (__int64)&v21,
             (__int64)&v18);
LABEL_15:
  v16 = v22;
  if ( v22 )
  {
    v22 = 0;
    result = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
  }
  v17 = v20;
  if ( v20 )
  {
    v20 = 0;
    return (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
  }
  return result;
}

```

## disassembly

```asm
0x18007cc64  mov     [rsp-8+arg_0], rbx
0x18007cc69  push    rbp
0x18007cc6a  push    rsi
0x18007cc6b  push    rdi
0x18007cc6c  lea     rbp, [rsp-47h]
0x18007cc71  sub     rsp, 100h
0x18007cc78  mov     rax, cs:__security_cookie
0x18007cc7f  xor     rax, rsp
0x18007cc82  mov     [rbp+57h+var_20], rax
0x18007cc86  mov     ebx, r8d
0x18007cc89  mov     [rbp+57h+var_B8], rdx
0x18007cc8d  xor     esi, esi
0x18007cc8f  mov     [rbp+57h+var_C0], rsi
0x18007cc93  mov     [rbp+57h+var_B0], rsi
0x18007cc97  mov     dword ptr [rbp+57h+var_C8+4], 9
0x18007cc9e  mov     dword ptr [rbp+57h+var_C8], esi
0x18007cca1  xor     edx, edx; Val
0x18007cca3  lea     r8d, [rsi+40h]; Size
0x18007cca7  lea     rcx, [rbp+57h+var_A0]; void *
0x18007ccab  call    memset_0
0x18007ccb0  mov     [rbp+57h+var_48], rsi
0x18007ccb4  lea     r9d, [rsi+25h]; unsigned int
0x18007ccb8  lea     r8d, [rsi+26h]; unsigned int
0x18007ccbc  lea     rdx, sourceString; "com.microsoft.mdm.euiccs.profilestate"
0x18007ccc3  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x18007ccc7  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18007cccc  mov     rax, [rbp+57h+var_48]
0x18007ccd0  mov     [rbp+57h+var_A0], rax
0x18007ccd4  mov     [rbp+57h+var_48], rsi
0x18007ccd8  lea     r9d, [rsi+1Bh]; unsigned int
0x18007ccdc  lea     r8d, [rsi+1Ch]; unsigned int
0x18007cce0  lea     rdx, aDeviceVendorMs; "./Device/Vendor/MSFT/eUICCs"
0x18007cce7  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x18007cceb  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18007ccf0  mov     rax, [rbp+57h+var_48]
0x18007ccf4  mov     [rbp+57h+var_98], rax
0x18007ccf8  mov     edx, ebx
0x18007ccfa  lea     rcx, [rbp+57h+hstringHeader]
0x18007ccfe  call    ??$_Integral_to_string@GH@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@H@Z; std::_Integral_to_string<ushort,int>(int)
0x18007cd03  lea     rcx, [rbp+57h+hstringHeader]
0x18007cd07  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18007cd0c  mov     [rbp+57h+var_D0], rax
0x18007cd10  lea     rdx, [rbp+57h+var_D0]
0x18007cd14  lea     rcx, [rbp+57h+var_40]
0x18007cd18  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18007cd1d  mov     rcx, [rax+18h]
0x18007cd21  mov     [rbp+57h+var_78], rcx
0x18007cd25  mov     [rbp+57h+var_28], rsi
0x18007cd29  lea     rcx, [rbp+57h+hstringHeader]
0x18007cd2d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18007cd32  mov     [rbp+57h+var_80], esi
0x18007cd35  mov     [rbp+57h+var_70], esi
0x18007cd38  mov     [rbp+57h+var_6C], 1
0x18007cd3f  mov     [rbp+57h+var_68], 3
0x18007cd46  mov     [rbp+57h+var_48], rsi
0x18007cd4a  lea     r9d, [rsi+34h]; unsigned int
0x18007cd4e  lea     r8d, [rsi+35h]; unsigned int
0x18007cd52  lea     rdx, ?RuntimeClass_Windows_Internal_Management_Provision_SessionManager@@3QBGB; "Windows.Internal.Management.Provision.S"...
0x18007cd59  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x18007cd5d  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18007cd62  nop
0x18007cd63  mov     [rbp+57h+var_C0], rsi
0x18007cd67  mov     [rbp+57h+var_D0], rsi
0x18007cd6b  lea     rdx, [rbp+57h+var_D0]
0x18007cd6f  mov     rcx, [rbp+57h+var_48]
0x18007cd73  call    cs:__imp_RoActivateInstance
0x18007cd79  mov     ebx, eax
0x18007cd7b  test    eax, eax
0x18007cd7d  js      short loc_18007CDD1
0x18007cd7f  lea     r8d, [rsi+10h]; Size
0x18007cd83  lea     rdx, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90; Buf2
0x18007cd8a  lea     rcx, _GUID_7611a5c3_7a06_4585_9149_369c349c5e79; Buf1
0x18007cd91  call    memcmp_0
0x18007cd96  test    eax, eax
0x18007cd98  jnz     short loc_18007CDA4
0x18007cd9a  mov     rax, [rbp+57h+var_D0]
0x18007cd9e  mov     [rbp+57h+var_C0], rax
0x18007cda2  jmp     short loc_18007CDD1
0x18007cda4  mov     rcx, [rbp+57h+var_D0]
0x18007cda8  mov     rax, [rcx]
0x18007cdab  lea     r8, [rbp+57h+var_C0]
0x18007cdaf  lea     rdx, _GUID_7611a5c3_7a06_4585_9149_369c349c5e79
0x18007cdb6  mov     rax, [rax]
0x18007cdb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007cdbe  mov     ebx, eax
0x18007cdc0  mov     rcx, [rbp+57h+var_D0]
0x18007cdc4  mov     rax, [rcx]
0x18007cdc7  mov     rax, [rax+10h]
0x18007cdcb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007cdd0  nop
0x18007cdd1  test    ebx, ebx
0x18007cdd3  js      loc_18007CE7A
0x18007cdd9  mov     rdi, [rbp+57h+var_C0]
0x18007cddd  mov     rax, [rdi]
0x18007cde0  mov     rbx, [rax+58h]
0x18007cde4  lea     rdx, [rbp+57h+var_B8]
0x18007cde8  lea     rcx, [rbp+57h+var_40]
0x18007cdec  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18007cdf1  nop
0x18007cdf2  lea     rcx, [rbp+57h+var_B0]
0x18007cdf6  mov     [rsp+110h+var_E8], rcx
0x18007cdfb  lea     rcx, [rbp+57h+var_A0]
0x18007cdff  mov     [rsp+110h+var_F0], rcx
0x18007ce04  mov     r9d, 1
0x18007ce0a  mov     r8, [rbp+57h+var_C8]
0x18007ce0e  mov     rdx, [rax+18h]
0x18007ce12  mov     rcx, rdi
0x18007ce15  mov     rax, rbx
0x18007ce18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007ce1d  mov     ebx, eax
0x18007ce1f  test    eax, eax
0x18007ce21  js      short loc_18007CE7A
0x18007ce23  mov     rdi, [rbp+57h+var_B0]
0x18007ce27  mov     rax, [rdi]
0x18007ce2a  mov     rbx, [rax+30h]
0x18007ce2e  lea     rcx, [rbp+57h+var_C8]
0x18007ce32  call    Microsoft__WRL__Callback_Microsoft__WRL__Implements_Microsoft__WRL__RuntimeClassFlags_2__Windows__Foundation__IAsyncOperationCompletedHandler_Windows__Internal__Management__Provision__SessionResult____Microsoft__WRL__FtmBase___LPA__EnterpriseManager__NotifyMdmServer____8____lambda_1___
0x18007ce37  nop
0x18007ce38  mov     rdx, [rax]
0x18007ce3b  mov     rcx, rdi
0x18007ce3e  mov     rax, rbx
0x18007ce41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007ce46  mov     ebx, eax
0x18007ce48  mov     rcx, [rbp+57h+var_C8]
0x18007ce4c  test    rcx, rcx
0x18007ce4f  jz      short loc_18007CE62
0x18007ce51  mov     [rbp+57h+var_C8], rsi
0x18007ce55  mov     rdx, [rcx]
0x18007ce58  mov     rax, [rdx+10h]
0x18007ce5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007ce61  nop
0x18007ce62  test    ebx, ebx
0x18007ce64  js      short loc_18007CE7A
0x18007ce66  mov     eax, cs:CallbackContext
0x18007ce6c  cmp     eax, 4
0x18007ce6f  jbe     short loc_18007CEC6
0x18007ce71  lea     rdx, word_18012B6B6
0x18007ce78  jmp     short loc_18007CE8C
0x18007ce7a  mov     eax, cs:CallbackContext
0x18007ce80  cmp     eax, 2
0x18007ce83  jbe     short loc_18007CEC6
0x18007ce85  lea     rdx, byte_18012B67D
0x18007ce8c  lea     rax, aLpaEnterprisem_2; "LPA::EnterpriseManager::NotifyMdmServer"
0x18007ce93  mov     [rbp+57h+var_B8], rax
0x18007ce97  lea     rax, aLpaserviceente; "LpaServiceEnterpriseManager"
0x18007ce9e  mov     [rbp+57h+var_C8], rax
0x18007cea2  lea     rax, [rbp+57h+var_D0]
0x18007cea6  mov     [rsp+110h+var_E0], rax
0x18007ceab  lea     rax, [rbp+57h+var_B8]
0x18007ceaf  mov     [rsp+110h+var_E8], rax
0x18007ceb4  lea     rax, [rbp+57h+var_C8]
0x18007ceb8  mov     [rsp+110h+var_F0], rax
0x18007cebd  mov     dword ptr [rbp+57h+var_D0], ebx
0x18007cec0  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18007cec5  nop
0x18007cec6  mov     rcx, [rbp+57h+var_B0]
0x18007ceca  test    rcx, rcx
0x18007cecd  jz      short loc_18007CEE0
0x18007cecf  mov     [rbp+57h+var_B0], rsi
0x18007ced3  mov     rax, [rcx]
0x18007ced6  mov     rax, [rax+10h]
0x18007ceda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007cedf  nop
0x18007cee0  mov     rcx, [rbp+57h+var_C0]
0x18007cee4  test    rcx, rcx
0x18007cee7  jz      short loc_18007CEFA
0x18007cee9  mov     [rbp+57h+var_C0], rsi
0x18007ceed  mov     rax, [rcx]
0x18007cef0  mov     rax, [rax+10h]
0x18007cef4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007cef9  nop
0x18007cefa  mov     rcx, [rbp+57h+var_20]
0x18007cefe  xor     rcx, rsp; StackCookie
0x18007cf01  call    __security_check_cookie
0x18007cf06  mov     rbx, [rsp+110h+arg_0]
0x18007cf0e  add     rsp, 100h
0x18007cf15  pop     rdi
0x18007cf16  pop     rsi
0x18007cf17  pop     rbp
0x18007cf18  retn
```
