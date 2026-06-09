# LPA::Lpd::DownloadInstance::OnEs10aVerifyEventListComplete(long,_GUID const &,ulong)

- ea: `0x1800b2d30`
- end: `0x1800b3107`
- name: `?OnEs10aVerifyEventListComplete@DownloadInstance@Lpd@LPA@@UEAAXJAEBU_GUID@@K@Z`
- size: `983`
- prototype: `void __fastcall(LPA::Lpd::DownloadInstance *__hidden this, int, const struct _GUID *, unsigned int)`
- caller_count: `0`
- callee_count: `16`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x180001010`
- `0x180005d6c`
- `0x18000df90`
- `0x18005fb20`
- `0x1800602e0`
- `0x180071610`
- `0x18008222c`
- `0x180085868`
- `0x180099598`
- `0x1800a2d18`
- `0x1800a50d0`
- `0x1800a73b4`
- `0x1800b1768`
- `0x1800b2d30`
- `0x1800b7e04`
- `0x180101010`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1800b2f7a`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1800b2f7a`

## string_xrefs

- `0x1800b2d75`: `LpaServiceLpd`
- `0x1800b3076`: `LpaServiceLpd`
- `0x1800b2d91`: `OnEs10aVerifyEventListComplete`
- `0x1800b304e`: `OnEs10aVerifyEventListComplete`
- `0x1800b2d6e`: `LPA::Lpd::DownloadInstance::OnEs10aVerifyEventListComplete`
- `0x1800b306b`: `LPA::Lpd::DownloadInstance::OnEs10aVerifyEventListComplete`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall LPA::Lpd::DownloadInstance::OnEs10aVerifyEventListComplete(
        LPA::Lpd::DownloadInstance *this,
        __int64 a2,
        const struct _GUID *a3,
        int a4)
{
  int v4; // esi
  int v6; // ecx
  int v7; // r8d
  int v8; // r9d
  __int64 v9; // rdi
  int v10; // r15d
  __m128i si128; // xmm6
  __int64 v12; // rcx
  __int64 v13; // rax
  __int64 v14; // rax
  char *v15; // rbx
  char *v16; // rcx
  char **v17; // rax
  char *v18; // rcx
  _QWORD *v19; // rdx
  _QWORD *v20; // rbx
  __int64 v21; // [rsp+68h] [rbp-A0h] BYREF
  int v22; // [rsp+70h] [rbp-98h] BYREF
  int v23; // [rsp+74h] [rbp-94h] BYREF
  __int64 v24; // [rsp+78h] [rbp-90h] BYREF
  char *v25; // [rsp+80h] [rbp-88h] BYREF
  __int64 v26; // [rsp+88h] [rbp-80h]
  const char *v27; // [rsp+90h] [rbp-78h] BYREF
  char **v28; // [rsp+98h] [rbp-70h]
  const char *v29; // [rsp+A0h] [rbp-68h] BYREF
  _OWORD v30[2]; // [rsp+A8h] [rbp-60h] BYREF
  _OWORD v31[2]; // [rsp+C8h] [rbp-40h] BYREF
  _BYTE v32[64]; // [rsp+E8h] [rbp-20h] BYREF

  v4 = a2;
  if ( (int)a2 < 0 )
  {
    if ( (unsigned int)CallbackContext > 2 )
    {
      LODWORD(v21) = a2;
      LODWORD(v24) = 10;
      v27 = "OnEs10aVerifyEventListComplete";
      v23 = *((_DWORD *)this + 228);
      v22 = 2;
      v29 = "LPA::Lpd::DownloadInstance::OnEs10aVerifyEventListComplete";
      v25 = "LpaServiceLpd";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (_DWORD)this,
        (unsigned int)byte_180130C51,
        (_DWORD)a3,
        a4,
        (__int64)&v25,
        (__int64)&v29,
        (__int64)&v22,
        (__int64)&v23,
        (__int64)&v27,
        (__int64)&v24,
        (__int64)&v21);
    }
    goto LABEL_30;
  }
  if ( (unsigned int)CallbackContext > 4 )
  {
    v22 = a2;
    v23 = 10;
    v25 = "OnEs10aVerifyEventListComplete";
    LODWORD(v24) = *((_DWORD *)this + 228);
    LODWORD(v21) = 2;
    v29 = "LPA::Lpd::DownloadInstance::OnEs10aVerifyEventListComplete";
    v27 = "LpaServiceLpd";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      (_DWORD)this,
      (unsigned int)&word_180130CB6,
      (_DWORD)a3,
      a4,
      (__int64)&v27,
      (__int64)&v29,
      (__int64)&v21,
      (__int64)&v24,
      (__int64)&v25,
      (__int64)&v23,
      (__int64)&v22);
  }
  std::list<std::tuple<std::string,std::string>>::list<std::tuple<std::string,std::string>>(&v25, a2, a3);
  v21 = 0;
  if ( *(_DWORD *)off_180154C08(
                    (int)&v27,
                    0,
                    (int)asn_DEF_SmdsSigned2,
                    (int)&v21,
                    *((_QWORD *)this + 86),
                    *((_QWORD *)this + 87) - *((_QWORD *)this + 86),
                    0) )
  {
    if ( (unsigned int)CallbackContext > 2 )
    {
      v27 = "LPA::Lpd::DownloadInstance::OnEs10aVerifyEventListComplete";
      v29 = "LpaServiceLpd";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v6,
        (unsigned int)byte_180130C19,
        v7,
        v8,
        (__int64)&v29,
        (__int64)&v27);
    }
    v4 = -2147024809;
    goto LABEL_19;
  }
  v9 = v21;
  if ( *(_DWORD *)(v21 + 40) == 1 )
  {
    v10 = 0;
    if ( *(int *)(v21 + 56) > 0 )
    {
      si128 = _mm_load_si128((const __m128i *)&_xmm);
      do
      {
        v31[0] = 0;
        v31[1] = si128;
        LOBYTE(v31[0]) = 0;
        v30[0] = 0;
        v30[1] = si128;
        LOBYTE(v30[0]) = 0;
        v12 = *(_QWORD *)(*(_QWORD *)(v9 + 48) + 8LL * v10);
        if ( *(int *)(v12 + 8) > 0 )
          LPA::Util::Asn1ByteBufferToStdBuffer<OCTET_STRING,std::string>(v12, v31);
        v13 = *(_QWORD *)(v9 + 48);
        if ( *(int *)(*(_QWORD *)(v13 + 8LL * v10) + 48LL) > 0 )
          LPA::Util::Asn1ByteBufferToStdBuffer<OCTET_STRING,std::string>(*(_QWORD *)(v13 + 8LL * v10) + 40LL, v30);
        v14 = std::make_tuple<std::string &,std::string &>(v32, v31, v30);
        if ( v26 == 0x333333333333333LL )
          std::_Xlength_error("list too long");
        v15 = v25;
        std::_List_node_emplace_op2<std::allocator<std::_List_node<std::tuple<std::string,std::string>,void *>>>::_List_node_emplace_op2<std::allocator<std::_List_node<std::tuple<std::string,std::string>,void *>>>(
          &v27,
          &v25,
          v14);
        ++v26;
        v16 = (char *)*((_QWORD *)v15 + 1);
        *v28 = v15;
        v28[1] = v16;
        v17 = v28;
        v28 = 0;
        *((_QWORD *)v15 + 1) = v17;
        *(_QWORD *)v16 = v17;
        std::_List_node_emplace_op2<std::allocator<std::_List_node<std::tuple<std::string,std::string>,void *>>>::~_List_node_emplace_op2<std::allocator<std::_List_node<std::tuple<std::string,std::string>,void *>>>(&v27);
        std::tuple<std::string,std::string>::~tuple<std::string,std::string>(v32);
        std::string::_Tidy_deallocate(v30);
        std::string::_Tidy_deallocate(v31);
        ++v10;
      }
      while ( v10 < *(_DWORD *)(v9 + 56) );
LABEL_19:
      v9 = v21;
    }
  }
  if ( v9 )
  {
    ((void (__fastcall *)(char **, __int64, _QWORD))off_180154BF0)(asn_DEF_SmdsSigned2, v9, 0);
    v21 = 0;
  }
  if ( v4 >= 0 )
    LPA::Lpd::DownloadInstance::ProcessEventRecords(this, &v25);
  v18 = v25;
  **((_QWORD **)v25 + 1) = 0;
  v19 = *(_QWORD **)v18;
  if ( *(_QWORD *)v18 )
  {
    do
    {
      v20 = (_QWORD *)*v19;
      std::_List_node<std::tuple<std::string,std::string>,void *>::_Freenode<std::allocator<std::_List_node<std::tuple<std::string,std::string>,void *>>>();
      v19 = v20;
    }
    while ( v20 );
  }
  std::_Deallocate<16>(v25, (struct std::nothrow_t *)0x50);
  if ( v4 < 0 )
LABEL_30:
    LPA::Lpd::DownloadInstance::OnCmaOrInstallCompleted((__int64)this, v4, 0);
}

```

## disassembly

```asm
0x1800b2d30  mov     rax, rsp
0x1800b2d33  mov     [rax+18h], rbx
0x1800b2d37  push    rbp
0x1800b2d38  push    rsi
0x1800b2d39  push    rdi
0x1800b2d3a  push    r14
0x1800b2d3c  push    r15
0x1800b2d3e  lea     rbp, [rax-68h]
0x1800b2d42  sub     rsp, 140h
0x1800b2d49  movaps  xmmword ptr [rax-38h], xmm6
0x1800b2d4d  mov     rax, cs:__security_cookie
0x1800b2d54  xor     rax, rsp
0x1800b2d57  mov     [rbp+60h+var_40], rax
0x1800b2d5b  mov     esi, edx
0x1800b2d5d  mov     r14, rcx
0x1800b2d60  mov     eax, cs:CallbackContext
0x1800b2d66  test    edx, edx
0x1800b2d68  js      loc_1800B3039
0x1800b2d6e  lea     rbx, aLpaLpdDownload_36; "LPA::Lpd::DownloadInstance::OnEs10aVeri"...
0x1800b2d75  lea     rdi, aLpaservicelpd; "LpaServiceLpd"
0x1800b2d7c  cmp     eax, 4
0x1800b2d7f  jbe     loc_1800B2E07
0x1800b2d85  mov     [rsp+160h+var_F8], edx
0x1800b2d89  mov     [rsp+160h+var_F4], 0Ah
0x1800b2d91  lea     rax, aOnes10averifye; "OnEs10aVerifyEventListComplete"
0x1800b2d98  mov     [rsp+160h+var_E8], rax
0x1800b2d9d  mov     eax, [rcx+390h]
0x1800b2da3  mov     dword ptr [rsp+160h+var_F0], eax
0x1800b2da7  mov     dword ptr [rsp+160h+var_100], 2
0x1800b2daf  mov     [rbp+60h+var_C8], rbx
0x1800b2db3  mov     [rbp+60h+var_D8], rdi
0x1800b2db7  lea     rax, [rsp+160h+var_F8]
0x1800b2dbc  mov     [rsp+160h+var_110], rax
0x1800b2dc1  lea     rax, [rsp+160h+var_F4]
0x1800b2dc6  mov     [rsp+160h+var_118], rax
0x1800b2dcb  lea     rax, [rsp+160h+var_E8]
0x1800b2dd0  mov     [rsp+160h+var_120], rax
0x1800b2dd5  lea     rax, [rsp+160h+var_F0]
0x1800b2dda  mov     [rsp+160h+var_128], rax
0x1800b2ddf  lea     rax, [rsp+160h+var_100]
0x1800b2de4  mov     [rsp+160h+var_130], rax
0x1800b2de9  lea     rax, [rbp+60h+var_C8]
0x1800b2ded  mov     [rsp+160h+var_138], rax
0x1800b2df2  lea     rax, [rbp+60h+var_D8]
0x1800b2df6  mov     [rsp+160h+var_140], rax
0x1800b2dfb  lea     rdx, word_180130CB6
0x1800b2e02  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U2@U1@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@4344@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800b2e07  lea     rcx, [rsp+160h+var_E8]
0x1800b2e0c  call    ??0?$list@V?$tuple@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@std@@V?$allocator@V?$tuple@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@std@@@2@@std@@QEAA@XZ; std::list<std::tuple<std::string,std::string>>::list<std::tuple<std::string,std::string>>(void)
0x1800b2e11  nop
0x1800b2e12  mov     [rsp+160h+var_100], 0
0x1800b2e1b  mov     rdx, [r14+2B0h]
0x1800b2e22  mov     rcx, [r14+2B8h]
0x1800b2e29  sub     rcx, rdx
0x1800b2e2c  mov     dword ptr [rsp+160h+var_130], 0
0x1800b2e34  mov     [rsp+160h+var_138], rcx
0x1800b2e39  mov     [rsp+160h+var_140], rdx
0x1800b2e3e  lea     r9, [rsp+160h+var_100]
0x1800b2e43  lea     r8, asn_DEF_SmdsSigned2
0x1800b2e4a  xor     edx, edx
0x1800b2e4c  lea     rcx, [rbp+60h+var_D8]
0x1800b2e50  mov     rax, cs:off_180154C08
0x1800b2e57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b2e5c  cmp     dword ptr [rax], 0
0x1800b2e5f  jnz     loc_1800B2F81
0x1800b2e65  mov     rdi, [rsp+160h+var_100]
0x1800b2e6a  cmp     dword ptr [rdi+28h], 1
0x1800b2e6e  jnz     loc_1800B2FBC
0x1800b2e74  xor     r15d, r15d
0x1800b2e77  cmp     [rdi+38h], r15d
0x1800b2e7b  jle     loc_1800B2FBC
0x1800b2e81  movdqa  xmm6, cs:__xmm@000000000000000f0000000000000000
0x1800b2e89  xorps   xmm0, xmm0
0x1800b2e8c  movups  [rbp+60h+var_A0], xmm0
0x1800b2e90  movdqu  [rbp+60h+var_90], xmm6
0x1800b2e95  mov     byte ptr [rbp+60h+var_A0], 0
0x1800b2e99  movups  [rbp+60h+var_C0], xmm0
0x1800b2e9d  movdqu  [rbp+60h+var_B0], xmm6
0x1800b2ea2  mov     byte ptr [rbp+60h+var_C0], 0
0x1800b2ea6  movsxd  rbx, r15d
0x1800b2ea9  mov     rax, [rdi+30h]
0x1800b2ead  mov     rcx, [rax+rbx*8]
0x1800b2eb1  cmp     dword ptr [rcx+8], 0
0x1800b2eb5  jle     short loc_1800B2EC0
0x1800b2eb7  lea     rdx, [rbp+60h+var_A0]
0x1800b2ebb  call    ??$Asn1ByteBufferToStdBuffer@UOCTET_STRING@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Util@LPA@@YAXAEBUOCTET_STRING@@AEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; LPA::Util::Asn1ByteBufferToStdBuffer<OCTET_STRING,std::string>(OCTET_STRING const &,std::string &)
0x1800b2ec0  mov     rax, [rdi+30h]
0x1800b2ec4  mov     rcx, [rax+rbx*8]
0x1800b2ec8  add     rcx, 28h ; '('
0x1800b2ecc  cmp     dword ptr [rcx+8], 0
0x1800b2ed0  jle     short loc_1800B2EDB
0x1800b2ed2  lea     rdx, [rbp+60h+var_C0]
0x1800b2ed6  call    ??$Asn1ByteBufferToStdBuffer@UOCTET_STRING@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Util@LPA@@YAXAEBUOCTET_STRING@@AEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; LPA::Util::Asn1ByteBufferToStdBuffer<OCTET_STRING,std::string>(OCTET_STRING const &,std::string &)
0x1800b2edb  lea     r8, [rbp+60h+var_C0]
0x1800b2edf  lea     rdx, [rbp+60h+var_A0]
0x1800b2ee3  lea     rcx, [rbp+60h+var_80]
0x1800b2ee7  call    ??$make_tuple@AEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAV12@@std@@YA?AV?$tuple@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@0@AEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@0@Z; std::make_tuple<std::string &,std::string &>(std::string &,std::string &)
0x1800b2eec  nop
0x1800b2eed  mov     rcx, 333333333333333h
0x1800b2ef7  cmp     [rbp+60h+var_E0], rcx
0x1800b2efb  jz      short loc_1800B2F73
0x1800b2efd  mov     rbx, [rsp+160h+var_E8]
0x1800b2f02  mov     r8, rax
0x1800b2f05  lea     rdx, [rsp+160h+var_E8]
0x1800b2f0a  lea     rcx, [rbp+60h+var_D8]
0x1800b2f0e  call    ??$?0V?$tuple@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@std@@@?$_List_node_emplace_op2@V?$allocator@U?$_List_node@V?$tuple@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@std@@PEAX@std@@@std@@@std@@QEAA@AEAV?$allocator@U?$_List_node@V?$tuple@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@std@@PEAX@std@@@1@$$QEAV?$tuple@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@1@@Z; std::_List_node_emplace_op2<std::allocator<std::_List_node<std::tuple<std::string,std::string>,void *>>>::_List_node_emplace_op2<std::allocator<std::_List_node<std::tuple<std::string,std::string>,void *>>>(std::allocator<std::_List_node<std::tuple<std::string,std::string>,void *>> &,std::tuple<std::string,std::string> &&)
0x1800b2f13  inc     [rbp+60h+var_E0]
0x1800b2f17  mov     rcx, [rbx+8]
0x1800b2f1b  mov     rax, [rbp+60h+var_D0]
0x1800b2f1f  mov     [rax], rbx
0x1800b2f22  mov     rax, [rbp+60h+var_D0]
0x1800b2f26  mov     [rax+8], rcx
0x1800b2f2a  mov     rax, [rbp+60h+var_D0]
0x1800b2f2e  mov     [rbp+60h+var_D0], 0
0x1800b2f36  mov     [rbx+8], rax
0x1800b2f3a  mov     [rcx], rax
0x1800b2f3d  lea     rcx, [rbp+60h+var_D8]
0x1800b2f41  call    ??1?$_List_node_emplace_op2@V?$allocator@U?$_List_node@V?$tuple@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@std@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_List_node_emplace_op2<std::allocator<std::_List_node<std::tuple<std::string,std::string>,void *>>>::~_List_node_emplace_op2<std::allocator<std::_List_node<std::tuple<std::string,std::string>,void *>>>(void)
0x1800b2f46  nop
0x1800b2f47  lea     rcx, [rbp+60h+var_80]
0x1800b2f4b  call    ??1?$tuple@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@std@@QEAA@XZ; std::tuple<std::string,std::string>::~tuple<std::string,std::string>(void)
0x1800b2f50  nop
0x1800b2f51  lea     rcx, [rbp+60h+var_C0]
0x1800b2f55  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800b2f5a  nop
0x1800b2f5b  lea     rcx, [rbp+60h+var_A0]
0x1800b2f5f  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800b2f64  inc     r15d
0x1800b2f67  cmp     r15d, [rdi+38h]
0x1800b2f6b  jl      loc_1800B2E89
0x1800b2f71  jmp     short loc_1800B2FB7
0x1800b2f73  lea     rcx, aListTooLong; "list too long"
0x1800b2f7a  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x1800b2f81  mov     eax, cs:CallbackContext
0x1800b2f87  cmp     eax, 2
0x1800b2f8a  jbe     short loc_1800B2FB2
0x1800b2f8c  mov     [rbp+60h+var_D8], rbx
0x1800b2f90  mov     [rbp+60h+var_C8], rdi
0x1800b2f94  lea     rax, [rbp+60h+var_D8]
0x1800b2f98  mov     [rsp+160h+var_138], rax
0x1800b2f9d  lea     rax, [rbp+60h+var_C8]
0x1800b2fa1  mov     [rsp+160h+var_140], rax
0x1800b2fa6  lea     rdx, byte_180130C19
0x1800b2fad  call    ??$Write@U?$_tlgWrapSz@D@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x1800b2fb2  mov     esi, 80070057h
0x1800b2fb7  mov     rdi, [rsp+160h+var_100]
0x1800b2fbc  test    rdi, rdi
0x1800b2fbf  jz      short loc_1800B2FE3
0x1800b2fc1  xor     r8d, r8d
0x1800b2fc4  mov     rdx, rdi
0x1800b2fc7  lea     rcx, asn_DEF_SmdsSigned2
0x1800b2fce  mov     rax, cs:off_180154BF0
0x1800b2fd5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b2fda  mov     [rsp+160h+var_100], 0
0x1800b2fe3  test    esi, esi
0x1800b2fe5  js      short loc_1800B2FF5
0x1800b2fe7  lea     rdx, [rsp+160h+var_E8]
0x1800b2fec  mov     rcx, r14
0x1800b2fef  call    ?ProcessEventRecords@DownloadInstance@Lpd@LPA@@AEAAXAEBV?$list@V?$tuple@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@std@@V?$allocator@V?$tuple@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@std@@@2@@std@@@Z; LPA::Lpd::DownloadInstance::ProcessEventRecords(std::list<std::tuple<std::string,std::string>> const &)
0x1800b2ff4  nop
0x1800b2ff5  mov     rcx, [rsp+160h+var_E8]
0x1800b2ffa  mov     rax, [rcx+8]
0x1800b2ffe  mov     qword ptr [rax], 0
0x1800b3005  mov     rdx, [rcx]
0x1800b3008  test    rdx, rdx
0x1800b300b  jz      short loc_1800B301D
0x1800b300d  mov     rbx, [rdx]
0x1800b3010  call    ??$_Freenode@V?$allocator@U?$_List_node@V?$tuple@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@std@@PEAX@std@@@std@@@?$_List_node@V?$tuple@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@std@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@V?$tuple@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@std@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<std::tuple<std::string,std::string>,void *>::_Freenode<std::allocator<std::_List_node<std::tuple<std::string,std::string>,void *>>>(std::allocator<std::_List_node<std::tuple<std::string,std::string>,void *>> &,std::_List_node<std::tuple<std::string,std::string>,void *> *)
0x1800b3015  mov     rdx, rbx
0x1800b3018  test    rbx, rbx
0x1800b301b  jnz     short loc_1800B300D
0x1800b301d  mov     edx, 50h ; 'P'
0x1800b3022  mov     rcx, [rsp+160h+var_E8]
0x1800b3027  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800b302c  test    esi, esi
0x1800b302e  jns     loc_1800B30DF
0x1800b3034  jmp     loc_1800B30D2
0x1800b3039  cmp     eax, 2
0x1800b303c  jbe     loc_1800B30D2
0x1800b3042  mov     dword ptr [rsp+160h+var_100], edx
0x1800b3046  mov     dword ptr [rsp+160h+var_F0], 0Ah
0x1800b304e  lea     rax, aOnes10averifye; "OnEs10aVerifyEventListComplete"
0x1800b3055  mov     [rbp+60h+var_D8], rax
0x1800b3059  mov     eax, [rcx+390h]
0x1800b305f  mov     [rsp+160h+var_F4], eax
0x1800b3063  mov     [rsp+160h+var_F8], 2
0x1800b306b  lea     rbx, aLpaLpdDownload_36; "LPA::Lpd::DownloadInstance::OnEs10aVeri"...
0x1800b3072  mov     [rbp+60h+var_C8], rbx
0x1800b3076  lea     rdi, aLpaservicelpd; "LpaServiceLpd"
0x1800b307d  mov     [rsp+160h+var_E8], rdi
0x1800b3082  lea     rax, [rsp+160h+var_100]
0x1800b3087  mov     [rsp+160h+var_110], rax
0x1800b308c  lea     rax, [rsp+160h+var_F0]
0x1800b3091  mov     [rsp+160h+var_118], rax
0x1800b3096  lea     rax, [rbp+60h+var_D8]
0x1800b309a  mov     [rsp+160h+var_120], rax
0x1800b309f  lea     rax, [rsp+160h+var_F4]
0x1800b30a4  mov     [rsp+160h+var_128], rax
0x1800b30a9  lea     rax, [rsp+160h+var_F8]
0x1800b30ae  mov     [rsp+160h+var_130], rax
0x1800b30b3  lea     rax, [rbp+60h+var_C8]
0x1800b30b7  mov     [rsp+160h+var_138], rax
0x1800b30bc  lea     rax, [rsp+160h+var_E8]
0x1800b30c1  mov     [rsp+160h+var_140], rax
0x1800b30c6  lea     rdx, byte_180130C51
0x1800b30cd  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U2@U1@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@4344@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800b30d2  xor     r8d, r8d
0x1800b30d5  mov     edx, esi
0x1800b30d7  mov     rcx, r14
0x1800b30da  call    ?OnCmaOrInstallCompleted@DownloadInstance@Lpd@LPA@@AEAAXJW4CmaOrInstallCompletion@123@@Z; LPA::Lpd::DownloadInstance::OnCmaOrInstallCompleted(long,LPA::Lpd::DownloadInstance::CmaOrInstallCompletion)
0x1800b30df  mov     rcx, [rbp+60h+var_40]
0x1800b30e3  xor     rcx, rsp; StackCookie
0x1800b30e6  call    __security_check_cookie
0x1800b30eb  lea     r11, [rsp+160h+var_20]
0x1800b30f3  mov     rbx, [r11+40h]
0x1800b30f7  movaps  xmm6, xmmword ptr [r11-10h]
0x1800b30fc  mov     rsp, r11
0x1800b30ff  pop     r15
0x1800b3101  pop     r14
0x1800b3103  pop     rdi
0x1800b3104  pop     rsi
0x1800b3105  pop     rbp
0x1800b3106  retn
```
