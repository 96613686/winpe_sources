# LPA::EsimManager::OnEs10aGetEuiccConfiguredDataComplete(long,_GUID const &,ulong,std::vector<uchar,std::allocator<uchar>> const &,std::vector<uchar,std::allocator<uchar>> const &,std::vector<uchar,std::allocator<uchar>> const &,std::vector<std::vector<uchar,std::allocator<uchar>>,std::allocator<std::vector<uchar,std::allocator<uchar>>>> const &)

- ea: `0x18008caf0`
- end: `0x18008cddb`
- name: `?OnEs10aGetEuiccConfiguredDataComplete@EsimManager@LPA@@EEAAXJAEBU_GUID@@KAEBV?$vector@EV?$allocator@E@std@@@std@@11AEBV?$vector@V?$vector@EV?$allocator@E@std@@@std@@V?$allocator@V?$vector@EV?$allocator@E@std@@@std@@@2@@5@@Z`
- size: `747`
- prototype: `__int64 __usercall@<rax>(LPA::EsimManager *this@<rcx>, int, __int64)`
- caller_count: `0`
- callee_count: `18`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180003a34`
- `0x180004a7c`
- `0x18000517c`
- `0x180005268`
- `0x18000df90`
- `0x18005cd20`
- `0x18005f8a0`
- `0x180063668`
- `0x180071320`
- `0x180071344`
- `0x180071610`
- `0x180071650`
- `0x180071840`
- `0x180088b48`
- `0x18008caf0`
- `0x180095550`
- `0x180095fd0`
- `0x1800d97c8`

## string_xrefs

- `0x18008cb77`: `LpaServiceEsimManager`
- `0x18008cc03`: `LpaServiceEsimManager`
- `0x18008cd63`: `LpaServiceEsimManager`
- `0x18008cb6b`: `LPA::EsimManager::OnEs10aGetEuiccConfiguredDataComplete`
- `0x18008cbfc`: `LPA::EsimManager::OnEs10aGetEuiccConfiguredDataComplete`
- `0x18008cd57`: `LPA::EsimManager::OnEs10aGetEuiccConfiguredDataComplete`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall LPA::EsimManager::OnEs10aGetEuiccConfiguredDataComplete(
        const char **this,
        int a2,
        const char *a3,
        int a4,
        int a5,
        _QWORD *a6)
{
  const char **v10; // rbx
  int v11; // ecx
  int v12; // r8d
  int v13; // r9d
  __int64 result; // rax
  __int64 v15; // rcx
  int v16; // edx
  __int64 v17; // r8
  __int64 v18; // rax
  int v19; // ecx
  int v20; // r8d
  int v21; // r9d
  int v22; // ecx
  int v23; // r8d
  int v24; // r9d
  const char *v25; // rbx
  const unsigned __int16 *v26; // rax
  int v27; // [rsp+50h] [rbp-B0h] BYREF
  int v28; // [rsp+54h] [rbp-ACh] BYREF
  const char *v29; // [rsp+58h] [rbp-A8h] BYREF
  const char *v30; // [rsp+60h] [rbp-A0h] BYREF
  const char *v31; // [rsp+68h] [rbp-98h] BYREF
  const char *v32; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v33[32]; // [rsp+78h] [rbp-88h] BYREF
  _BYTE v34[40]; // [rsp+98h] [rbp-68h] BYREF
  unsigned __int16 v35[260]; // [rsp+C0h] [rbp-40h] BYREF
  int v36; // [rsp+338h] [rbp+238h] BYREF

  v36 = a4;
  v10 = this + 30;
  std::_Tree<std::_Tmap_traits<unsigned long,std::shared_ptr<LPA::Lpd::DownloadInstance>,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,std::shared_ptr<LPA::Lpd::DownloadInstance>>>,0>>::find(
    this + 30,
    &v32,
    &v36);
  if ( *v10 == v32 )
  {
    result = (unsigned int)CallbackContext;
    if ( (unsigned int)CallbackContext > 3 )
    {
      v32 = a3;
      v27 = a4;
      v28 = a2;
      v29 = "LPA::EsimManager::OnEs10aGetEuiccConfiguredDataComplete";
      v30 = "LpaServiceEsimManager";
      return _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(
               v11,
               (unsigned int)word_18012E012,
               v12,
               v13,
               (__int64)&v30,
               (__int64)&v29,
               (__int64)&v28,
               (__int64)&v27,
               (__int64)&v32);
    }
  }
  else
  {
    v15 = *((_QWORD *)v32 + 5);
    v16 = *(_DWORD *)(v15 + 224);
    v27 = v16;
    if ( a2 < 0 )
    {
      if ( (unsigned int)CallbackContext > 2 )
      {
        v28 = v16;
        v31 = a3;
        v27 = a2;
        v30 = "LPA::EsimManager::OnEs10aGetEuiccConfiguredDataComplete";
        v29 = "LpaServiceEsimManager";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(
          v15,
          (unsigned int)&dword_18012DF2C,
          v12,
          v13,
          (__int64)&v29,
          (__int64)&v30,
          (__int64)&v27,
          (__int64)&v31,
          (__int64)&v28);
      }
    }
    else
    {
      std::wstring::wstring(v33, &qword_1801130E8);
      v17 = a6[1];
      if ( v17 != *a6 )
      {
        std::string::string(v34, *a6, v17);
        v18 = std::_String_val<std::_Simple_types<char>>::_Myptr(v34);
        a2 = LPA::Util::ConvertUtf8ToUtf16(v18, v33);
        if ( a2 < 0 && (unsigned int)CallbackContext > 2 )
        {
          v30 = a3;
          v28 = a2;
          v29 = "LPA::EsimManager::OnEs10aGetEuiccConfiguredDataComplete";
          v31 = "LpaServiceEsimManager";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(
            v19,
            (unsigned int)&word_18012DFC6,
            v20,
            v21,
            (__int64)&v31,
            (__int64)&v29,
            (__int64)&v28,
            (__int64)&v30);
        }
        std::string::_Tidy_deallocate(v34);
      }
      if ( a2 >= 0 )
      {
        LPA::EsimManager::TryFindEsimRecordBySlotId(this, &v31, &v27, a3);
        v25 = v31;
        if ( this[26] == v31
          || (v26 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v33),
              StringCchCopyW(v35, 0x104u, v26) < 0) )
        {
          if ( (unsigned int)CallbackContext > 2 )
          {
            v31 = a3;
            v30 = "LPA::EsimManager::OnEs10aGetEuiccConfiguredDataComplete";
            v29 = "LpaServiceEsimManager";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByRef<16>>(
              v22,
              (unsigned int)&unk_18012DF80,
              v23,
              v24,
              (__int64)&v29,
              (__int64)&v30,
              (__int64)&v31);
          }
        }
        else
        {
          LPA::EsimManager::EsimRecord::SetSmdpAddress(
            *((LPA::EsimManager::EsimRecord **)v25 + 6),
            (const unsigned __int16 (*const)[260])v35);
        }
      }
      std::wstring::_Tidy_deallocate(v33);
    }
    return LPA::EsimManager::CompleteOperation((LPA::EsimManager *)this);
  }
  return result;
}

```

## disassembly

```asm
0x18008caf0  mov     [rsp-8+arg_18], r9d
0x18008caf5  push    rbp
0x18008caf6  push    rbx
0x18008caf7  push    rsi
0x18008caf8  push    rdi
0x18008caf9  push    r13
0x18008cafb  push    r14
0x18008cafd  push    r15
0x18008caff  lea     rbp, [rsp-1E0h]
0x18008cb07  sub     rsp, 2E0h
0x18008cb0e  mov     rax, cs:__security_cookie
0x18008cb15  xor     rax, rsp
0x18008cb18  mov     [rbp+210h+var_40], rax
0x18008cb1f  mov     esi, r9d
0x18008cb22  mov     r15, r8
0x18008cb25  mov     edi, edx
0x18008cb27  mov     r13, rcx
0x18008cb2a  lea     rbx, [rcx+0F0h]
0x18008cb31  lea     r8, [rbp+210h+arg_18]
0x18008cb38  lea     rdx, [rsp+310h+var_2A0]
0x18008cb3d  mov     rcx, rbx
0x18008cb40  call    ?find@?$_Tree@V?$_Tmap_traits@KV?$shared_ptr@VDownloadInstance@Lpd@LPA@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$shared_ptr@VDownloadInstance@Lpd@LPA@@@std@@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKV?$shared_ptr@VDownloadInstance@Lpd@LPA@@@std@@@std@@@std@@@std@@@2@AEBK@Z; std::_Tree<std::_Tmap_traits<ulong,std::shared_ptr<LPA::Lpd::DownloadInstance>,std::less<ulong>,std::allocator<std::pair<ulong const,std::shared_ptr<LPA::Lpd::DownloadInstance>>>,0>>::find(ulong const &)
0x18008cb45  mov     rax, [rsp+310h+var_2A0]
0x18008cb4a  cmp     [rbx], rax
0x18008cb4d  jnz     short loc_18008CBC6
0x18008cb4f  mov     eax, cs:CallbackContext
0x18008cb55  cmp     eax, 3
0x18008cb58  jbe     loc_18008CDBA
0x18008cb5e  mov     [rsp+310h+var_2A0], r15
0x18008cb63  mov     [rsp+310h+var_2C0], esi
0x18008cb67  mov     [rsp+310h+var_2BC], edi
0x18008cb6b  lea     rsi, aLpaEsimmanager_21; "LPA::EsimManager::OnEs10aGetEuiccConfig"...
0x18008cb72  mov     [rsp+310h+var_2B8], rsi
0x18008cb77  lea     r14, aLpaserviceesim; "LpaServiceEsimManager"
0x18008cb7e  mov     [rsp+310h+var_2B0], r14
0x18008cb83  lea     rax, [rsp+310h+var_2A0]
0x18008cb88  mov     [rsp+310h+var_2D0], rax
0x18008cb8d  lea     rax, [rsp+310h+var_2C0]
0x18008cb92  mov     [rsp+310h+var_2D8], rax
0x18008cb97  lea     rax, [rsp+310h+var_2BC]
0x18008cb9c  mov     [rsp+310h+var_2E0], rax
0x18008cba1  lea     rax, [rsp+310h+var_2B8]
0x18008cba6  mov     [rsp+310h+var_2E8], rax
0x18008cbab  lea     rax, [rsp+310h+var_2B0]
0x18008cbb0  mov     [rsp+310h+var_2F0], rax
0x18008cbb5  lea     rdx, word_18012E012
0x18008cbbc  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U2@U?$_tlgWrapperByRef@$0BA@@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@4AEBU?$_tlgWrapperByRef@$0BA@@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByRef<16> const &)
0x18008cbc1  jmp     loc_18008CDBA
0x18008cbc6  mov     rcx, [rax+28h]
0x18008cbca  mov     edx, [rcx+0E0h]
0x18008cbd0  mov     [rsp+310h+var_2C0], edx
0x18008cbd4  test    edi, edi
0x18008cbd6  js      loc_18008CD3F
0x18008cbdc  lea     rdx, qword_1801130E8
0x18008cbe3  lea     rcx, [rsp+310h+var_298]
0x18008cbe8  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18008cbed  nop
0x18008cbee  mov     rax, [rbp+210h+arg_28]
0x18008cbf5  mov     rdx, [rax]
0x18008cbf8  mov     r8, [rax+8]
0x18008cbfc  lea     rsi, aLpaEsimmanager_21; "LPA::EsimManager::OnEs10aGetEuiccConfig"...
0x18008cc03  lea     r14, aLpaserviceesim; "LpaServiceEsimManager"
0x18008cc0a  cmp     r8, rdx
0x18008cc0d  jz      loc_18008CC95
0x18008cc13  lea     rcx, [rbp+210h+var_278]
0x18008cc17  call    ??$?0PEAE$0A@@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@PEAE0AEBV?$allocator@D@1@@Z; std::string::string(uchar *,uchar *,std::allocator<char> const &)
0x18008cc1c  nop
0x18008cc1d  lea     rcx, [rbp+210h+var_278]
0x18008cc21  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x18008cc26  mov     rcx, rax
0x18008cc29  lea     rdx, [rsp+310h+var_298]
0x18008cc2e  call    ?ConvertUtf8ToUtf16@Util@LPA@@YAJPEBDAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAV?$wstring_convert@V?$codecvt_utf8_utf16@G$0BAPPPP@$0A@@std@@GV?$allocator@G@2@V?$allocator@D@2@@4@@Z; LPA::Util::ConvertUtf8ToUtf16(char const *,std::wstring &,std::wstring_convert<std::codecvt_utf8_utf16<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>> *)
0x18008cc33  mov     edi, eax
0x18008cc35  test    eax, eax
0x18008cc37  jns     short loc_18008CC8C
0x18008cc39  mov     eax, cs:CallbackContext
0x18008cc3f  cmp     eax, 2
0x18008cc42  jbe     short loc_18008CC8C
0x18008cc44  mov     [rsp+310h+var_2B0], r15
0x18008cc49  mov     [rsp+310h+var_2BC], edi
0x18008cc4d  mov     [rsp+310h+var_2B8], rsi
0x18008cc52  mov     [rsp+310h+var_2A8], r14
0x18008cc57  lea     rax, [rsp+310h+var_2B0]
0x18008cc5c  mov     [rsp+310h+var_2D8], rax
0x18008cc61  lea     rax, [rsp+310h+var_2BC]
0x18008cc66  mov     [rsp+310h+var_2E0], rax
0x18008cc6b  lea     rax, [rsp+310h+var_2B8]
0x18008cc70  mov     [rsp+310h+var_2E8], rax
0x18008cc75  lea     rax, [rsp+310h+var_2A8]
0x18008cc7a  mov     [rsp+310h+var_2F0], rax
0x18008cc7f  lea     rdx, word_18012DFC6
0x18008cc86  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByRef@$0BA@@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByRef@$0BA@@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByRef<16> const &)
0x18008cc8b  nop
0x18008cc8c  lea     rcx, [rbp+210h+var_278]
0x18008cc90  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18008cc95  test    edi, edi
0x18008cc97  js      loc_18008CD33
0x18008cc9d  mov     r9, r15
0x18008cca0  lea     r8, [rsp+310h+var_2C0]
0x18008cca5  lea     rdx, [rsp+310h+var_2A8]
0x18008ccaa  mov     rcx, r13
0x18008ccad  call    ?TryFindEsimRecordBySlotId@EsimManager@LPA@@AEAA?AV?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@V?$unique_ptr@VEsimRecord@EsimManager@LPA@@U?$default_delete@VEsimRecord@EsimManager@LPA@@@std@@@std@@@std@@@std@@@std@@@std@@AEBKAEBU_GUID@@@Z; LPA::EsimManager::TryFindEsimRecordBySlotId(ulong const &,_GUID const &)
0x18008ccb2  mov     rbx, [rsp+310h+var_2A8]
0x18008ccb7  cmp     [r13+0D0h], rbx
0x18008ccbe  jz      short loc_18008CCEE
0x18008ccc0  lea     rcx, [rsp+310h+var_298]
0x18008ccc5  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18008ccca  mov     r8, rax; unsigned __int16 *
0x18008cccd  mov     edx, 104h; unsigned __int64
0x18008ccd2  lea     rcx, [rbp+210h+var_250]; unsigned __int16 *
0x18008ccd6  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18008ccdb  test    eax, eax
0x18008ccdd  js      short loc_18008CCEE
0x18008ccdf  lea     rdx, [rbp+210h+var_250]; unsigned __int16 (*)[260]
0x18008cce3  mov     rcx, [rbx+30h]; this
0x18008cce7  call    ?SetSmdpAddress@EsimRecord@EsimManager@LPA@@QEAAXQEAY0BAE@$$CBG@Z; LPA::EsimManager::EsimRecord::SetSmdpAddress(ushort const (* const)[260])
0x18008ccec  jmp     short loc_18008CD33
0x18008ccee  mov     eax, cs:CallbackContext
0x18008ccf4  cmp     eax, 2
0x18008ccf7  jbe     short loc_18008CD33
0x18008ccf9  mov     [rsp+310h+var_2A8], r15
0x18008ccfe  mov     [rsp+310h+var_2B0], rsi
0x18008cd03  mov     [rsp+310h+var_2B8], r14
0x18008cd08  lea     rax, [rsp+310h+var_2A8]
0x18008cd0d  mov     [rsp+310h+var_2E0], rax
0x18008cd12  lea     rax, [rsp+310h+var_2B0]
0x18008cd17  mov     [rsp+310h+var_2E8], rax
0x18008cd1c  lea     rax, [rsp+310h+var_2B8]
0x18008cd21  mov     [rsp+310h+var_2F0], rax
0x18008cd26  lea     rdx, unk_18012DF80
0x18008cd2d  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByRef@$0BA@@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByRef@$0BA@@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByRef<16>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &)
0x18008cd32  nop
0x18008cd33  lea     rcx, [rsp+310h+var_298]
0x18008cd38  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18008cd3d  jmp     short loc_18008CDAD
0x18008cd3f  mov     eax, cs:CallbackContext
0x18008cd45  cmp     eax, 2
0x18008cd48  jbe     short loc_18008CDAD
0x18008cd4a  mov     [rsp+310h+var_2BC], edx
0x18008cd4e  mov     [rsp+310h+var_2A8], r15
0x18008cd53  mov     [rsp+310h+var_2C0], edi
0x18008cd57  lea     rsi, aLpaEsimmanager_21; "LPA::EsimManager::OnEs10aGetEuiccConfig"...
0x18008cd5e  mov     [rsp+310h+var_2B0], rsi
0x18008cd63  lea     r14, aLpaserviceesim; "LpaServiceEsimManager"
0x18008cd6a  mov     [rsp+310h+var_2B8], r14
0x18008cd6f  lea     rax, [rsp+310h+var_2BC]
0x18008cd74  mov     [rsp+310h+var_2D0], rax
0x18008cd79  lea     rax, [rsp+310h+var_2A8]
0x18008cd7e  mov     [rsp+310h+var_2D8], rax
0x18008cd83  lea     rax, [rsp+310h+var_2C0]
0x18008cd88  mov     [rsp+310h+var_2E0], rax
0x18008cd8d  lea     rax, [rsp+310h+var_2B0]
0x18008cd92  mov     [rsp+310h+var_2E8], rax
0x18008cd97  lea     rax, [rsp+310h+var_2B8]
0x18008cd9c  mov     [rsp+310h+var_2F0], rax
0x18008cda1  lea     rdx, dword_18012DF2C
0x18008cda8  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByRef@$0BA@@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByRef@$0BA@@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &)
0x18008cdad  lea     rdx, [rsp+310h+var_2A0]
0x18008cdb2  mov     rcx, r13; this
0x18008cdb5  call    ?CompleteOperation@EsimManager@LPA@@AEAAXAEAV?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKV?$unique_ptr@VOperationEntry@EsimManager@LPA@@U?$default_delete@VOperationEntry@EsimManager@LPA@@@std@@@std@@@std@@@std@@@std@@@std@@@Z; LPA::EsimManager::CompleteOperation(std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<ulong const,std::unique_ptr<LPA::EsimManager::OperationEntry>>>>> &)
0x18008cdba  mov     rcx, [rbp+210h+var_40]
0x18008cdc1  xor     rcx, rsp; StackCookie
0x18008cdc4  call    __security_check_cookie
0x18008cdc9  add     rsp, 2E0h
0x18008cdd0  pop     r15
0x18008cdd2  pop     r14
0x18008cdd4  pop     r13
0x18008cdd6  pop     rdi
0x18008cdd7  pop     rsi
0x18008cdd8  pop     rbx
0x18008cdd9  pop     rbp
0x18008cdda  retn
```
