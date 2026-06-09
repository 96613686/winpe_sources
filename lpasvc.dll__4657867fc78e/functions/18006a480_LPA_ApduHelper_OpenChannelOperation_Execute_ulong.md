# LPA::ApduHelper::OpenChannelOperation::Execute(ulong)

- ea: `0x18006a480`
- end: `0x18006a5ea`
- name: `?Execute@OpenChannelOperation@ApduHelper@LPA@@UEAAJK@Z`
- size: `362`
- prototype: `__int64 __fastcall(LPA::ApduHelper::OpenChannelOperation *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `9`
- tags: ``

## callees

- `0x1800013ec`
- `0x18000df90`
- `0x18005fa50`
- `0x18006a480`
- `0x18006bfa4`
- `0x1800709e4`
- `0x180070a1c`
- `0x180071994`
- `0x180071ac8`

## import_xrefs

- `wwapi!WwanUiccOpenChannel` at `0x18006a4fc`
- `wwapi!WwanUiccOpenChannel` at `0x18006a4fc`

## string_xrefs

- `0x18006a589`: `LPA::ApduHelper::OpenChannelOperation::Execute`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall LPA::ApduHelper::OpenChannelOperation::Execute(LPA::ApduHelper::OpenChannelOperation *this)
{
  char *v2; // r14
  int v3; // eax
  signed int v4; // ebx
  int v5; // r8d
  int v6; // r9d
  __int64 v7; // rax
  int v8; // ecx
  int v10; // [rsp+44h] [rbp-15h] BYREF
  const char *v11; // [rsp+48h] [rbp-11h] BYREF
  std::_Ref_count_base *v12; // [rsp+50h] [rbp-9h]
  const char *v13; // [rsp+58h] [rbp-1h] BYREF
  std::_Ref_count_base *v14; // [rsp+60h] [rbp+7h]
  char *v15; // [rsp+68h] [rbp+Fh] BYREF
  int v16; // [rsp+70h] [rbp+17h]
  int v17; // [rsp+74h] [rbp+1Bh]
  int v18; // [rsp+78h] [rbp+1Fh]
  int v19; // [rsp+7Ch] [rbp+23h]

  v16 = 83886240;
  v17 = -15724455;
  v18 = -1979711489;
  v19 = 0x10000;
  v2 = (char *)this + 32;
  v3 = WwanUiccOpenChannel(*((_QWORD *)this + 3), (char *)this + 32, 1);
  v4 = v3;
  if ( v3 > 0 )
    v4 = (unsigned __int16)v3 | 0x80070000;
  if ( v4 >= 0 )
  {
    std::weak_ptr<Concurrency::streams::details::streambuf_state_manager<char>>::weak_ptr<Concurrency::streams::details::streambuf_state_manager<char>>(
      &v11,
      (_QWORD *)this + 6);
    std::weak_ptr<LPA::Lpd::DownloadInstance>::lock(&v11, &v13);
    if ( v12 )
      std::_Ref_count_base::_Decwref(v12);
    if ( v13 )
    {
      v7 = std::enable_shared_from_this<LPA::ApduHelper::UiccOperation>::shared_from_this((char *)this + 8, &v11);
      LPA::ApduHelper::OnAsyncUiccOperationPending(v13, 0, v7);
    }
    v8 = (int)v14;
    if ( v14 )
      std::_Ref_count_base::_Decref(v14);
    if ( (unsigned int)CallbackContext > 4 )
    {
      v10 = *((_DWORD *)this + 16);
      v15 = v2;
      v13 = "LPA::ApduHelper::OpenChannelOperation::Execute";
      v11 = "LpaApduHelper";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(
        v8,
        (unsigned int)byte_18012A97D,
        v5,
        v6,
        (__int64)&v11,
        (__int64)&v13,
        (__int64)&v15,
        (__int64)&v10);
    }
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18006a480  push    rbp
0x18006a482  push    rbx
0x18006a483  push    rdi
0x18006a484  push    r14
0x18006a486  lea     rbp, [rsp-3Fh]
0x18006a48b  sub     rsp, 98h
0x18006a492  mov     rax, cs:__security_cookie
0x18006a499  xor     rax, rsp
0x18006a49c  mov     [rbp+57h+var_30], rax
0x18006a4a0  mov     rdi, rcx
0x18006a4a3  mov     [rbp+57h+var_70], 0
0x18006a4aa  mov     [rbp+57h+var_40], 50000A0h
0x18006a4b1  mov     [rbp+57h+var_3C], 0FF101059h
0x18006a4b8  mov     [rbp+57h+var_38], 89FFFFFFh
0x18006a4bf  mov     [rbp+57h+var_34], 10000h
0x18006a4c6  lea     r14, [rcx+20h]
0x18006a4ca  lea     rax, [rbp+57h+var_70]
0x18006a4ce  mov     [rsp+0B0h+var_78], rax
0x18006a4d3  mov     eax, [rcx+40h]
0x18006a4d6  mov     dword ptr [rsp+0B0h+var_80], eax
0x18006a4da  lea     rax, [rbp+57h+var_40]
0x18006a4de  mov     [rsp+0B0h+var_88], rax
0x18006a4e3  mov     dword ptr [rsp+0B0h+var_90], 10h
0x18006a4eb  mov     r9d, 0Ch
0x18006a4f1  lea     r8d, [r9-0Bh]
0x18006a4f5  mov     rdx, r14
0x18006a4f8  mov     rcx, [rcx+18h]
0x18006a4fc  call    cs:__imp_WwanUiccOpenChannel
0x18006a502  mov     ebx, eax
0x18006a504  test    eax, eax
0x18006a506  jle     short loc_18006A511
0x18006a508  movzx   ebx, ax
0x18006a50b  or      ebx, 80070000h
0x18006a511  test    ebx, ebx
0x18006a513  js      loc_18006A5CF
0x18006a519  lea     rdx, [rdi+30h]
0x18006a51d  lea     rcx, [rbp+57h+var_68]
0x18006a521  call    ??$?0V?$basic_container_buffer@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@details@streams@Concurrency@@$0A@@?$weak_ptr@V?$streambuf_state_manager@D@details@streams@Concurrency@@@std@@QEAA@AEBV?$shared_ptr@V?$basic_container_buffer@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@details@streams@Concurrency@@@1@@Z; std::weak_ptr<Concurrency::streams::details::streambuf_state_manager<char>>::weak_ptr<Concurrency::streams::details::streambuf_state_manager<char>>(std::shared_ptr<Concurrency::streams::details::basic_container_buffer<std::string>> const &)
0x18006a526  lea     rdx, [rbp+57h+var_58]
0x18006a52a  lea     rcx, [rbp+57h+var_68]
0x18006a52e  call    ?lock@?$weak_ptr@VDownloadInstance@Lpd@LPA@@@std@@QEBA?AV?$shared_ptr@VDownloadInstance@Lpd@LPA@@@2@XZ; std::weak_ptr<LPA::Lpd::DownloadInstance>::lock(void)
0x18006a533  nop
0x18006a534  mov     rcx, [rbp+57h+var_60]; this
0x18006a538  test    rcx, rcx
0x18006a53b  jz      short loc_18006A542
0x18006a53d  call    ?_Decwref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decwref(void)
0x18006a542  cmp     [rbp+57h+var_58], 0
0x18006a547  jz      short loc_18006A566
0x18006a549  lea     rcx, [rdi+8]
0x18006a54d  lea     rdx, [rbp+57h+var_68]
0x18006a551  call    ?shared_from_this@?$enable_shared_from_this@VUiccOperation@ApduHelper@LPA@@@std@@QEAA?AV?$shared_ptr@VUiccOperation@ApduHelper@LPA@@@2@XZ; std::enable_shared_from_this<LPA::ApduHelper::UiccOperation>::shared_from_this(void)
0x18006a556  mov     r8, rax
0x18006a559  mov     edx, [rbp+57h+var_70]
0x18006a55c  mov     rcx, [rbp+57h+var_58]
0x18006a560  call    ?OnAsyncUiccOperationPending@ApduHelper@LPA@@QEAAXKV?$shared_ptr@VUiccOperation@ApduHelper@LPA@@@std@@@Z; LPA::ApduHelper::OnAsyncUiccOperationPending(ulong,std::shared_ptr<LPA::ApduHelper::UiccOperation>)
0x18006a565  nop
0x18006a566  mov     rcx, [rbp+57h+var_50]; this
0x18006a56a  test    rcx, rcx
0x18006a56d  jz      short loc_18006A574
0x18006a56f  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18006a574  mov     eax, cs:CallbackContext
0x18006a57a  cmp     eax, 4
0x18006a57d  jbe     short loc_18006A5CF
0x18006a57f  mov     eax, [rdi+40h]
0x18006a582  mov     [rbp+57h+var_6C], eax
0x18006a585  mov     [rbp+57h+var_48], r14
0x18006a589  lea     rax, aLpaApduhelperO_0; "LPA::ApduHelper::OpenChannelOperation::"...
0x18006a590  mov     [rbp+57h+var_58], rax
0x18006a594  lea     rax, aLpaapduhelper; "LpaApduHelper"
0x18006a59b  mov     [rbp+57h+var_68], rax
0x18006a59f  lea     rax, [rbp+57h+var_6C]
0x18006a5a3  mov     [rsp+0B0h+var_78], rax
0x18006a5a8  lea     rax, [rbp+57h+var_48]
0x18006a5ac  mov     [rsp+0B0h+var_80], rax
0x18006a5b1  lea     rax, [rbp+57h+var_58]
0x18006a5b5  mov     [rsp+0B0h+var_88], rax
0x18006a5ba  lea     rax, [rbp+57h+var_68]
0x18006a5be  mov     [rsp+0B0h+var_90], rax
0x18006a5c3  lea     rdx, byte_18012A97D
0x18006a5ca  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &)
0x18006a5cf  mov     eax, ebx
0x18006a5d1  mov     rcx, [rbp+57h+var_30]
0x18006a5d5  xor     rcx, rsp; StackCookie
0x18006a5d8  call    __security_check_cookie
0x18006a5dd  add     rsp, 98h
0x18006a5e4  pop     r14
0x18006a5e6  pop     rdi
0x18006a5e7  pop     rbx
0x18006a5e8  pop     rbp
0x18006a5e9  retn
```
