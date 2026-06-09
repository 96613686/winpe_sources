# LPA::EsimManager::OnEs10bGetUiccInfo2Complete(long,_GUID const &,ulong,std::vector<uchar,std::allocator<uchar>> const &,std::vector<uchar,std::allocator<uchar>> const &,ulong *,std::vector<uchar,std::allocator<uchar>> const &)

- ea: `0x18008d010`
- end: `0x18008d2fb`
- name: `?OnEs10bGetUiccInfo2Complete@EsimManager@LPA@@EEAAXJAEBU_GUID@@KAEBV?$vector@EV?$allocator@E@std@@@std@@1PEAK1@Z`
- size: `747`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800013ec`
- `0x1800017c8`
- `0x180004a7c`
- `0x180005268`
- `0x18000df90`
- `0x180071840`
- `0x180084030`
- `0x180088a58`
- `0x180088b48`
- `0x18008d010`
- `0x180094620`
- `0x180095fd0`

## string_xrefs

- `0x18008d086`: `LpaServiceEsimManager`
- `0x18008d119`: `LpaServiceEsimManager`
- `0x18008d227`: `LpaServiceEsimManager`
- `0x18008d281`: `LpaServiceEsimManager`
- `0x18008d078`: `LPA::EsimManager::OnEs10bGetUiccInfo2Complete`
- `0x18008d16a`: `LPA::EsimManager::OnEs10bGetUiccInfo2Complete`
- `0x18008d219`: `LPA::EsimManager::OnEs10bGetUiccInfo2Complete`
- `0x18008d273`: `LPA::EsimManager::OnEs10bGetUiccInfo2Complete`

## pseudocode

```c
__int64 __fastcall LPA::EsimManager::OnEs10bGetUiccInfo2Complete(
        __int64 a1,
        int a2,
        __int64 a3,
        int a4,
        int a5,
        __int64 a6,
        int *a7)
{
  __int64 v7; // r12
  _QWORD *v8; // rbx
  int v13; // ecx
  int v14; // r9d
  int v15; // r8d
  __int64 result; // rax
  int v17; // edi
  LPA::EsimManager *v18; // r15
  int v19; // ecx
  int v20; // r8d
  int v21; // r9d
  __int64 v22; // rbx
  int *v23; // rdx
  __int64 v24; // r8
  int v25; // r9d
  __int64 v26; // rax
  _DWORD *v27; // rcx
  unsigned __int8 *v28; // rax
  char *v29; // [rsp+20h] [rbp-79h]
  unsigned __int16 *v30; // [rsp+28h] [rbp-71h]
  int v31; // [rsp+50h] [rbp-49h] BYREF
  unsigned __int16 v32[4]; // [rsp+58h] [rbp-41h] BYREF
  const char *v33; // [rsp+60h] [rbp-39h] BYREF
  const char *v34; // [rsp+68h] [rbp-31h] BYREF
  __int64 v35; // [rsp+70h] [rbp-29h] BYREF
  const char *v36; // [rsp+78h] [rbp-21h] BYREF
  unsigned __int16 v37[12]; // [rsp+80h] [rbp-19h] BYREF
  int v38; // [rsp+F8h] [rbp+5Fh] BYREF

  v38 = a4;
  v7 = a6;
  v8 = (_QWORD *)(a1 + 232);
  std::_Tree<std::_Tmap_traits<unsigned long,std::shared_ptr<LPA::Lpd::DownloadInstance>,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,std::shared_ptr<LPA::Lpd::DownloadInstance>>>,0>>::find(
    a1 + 232,
    &v35,
    &v38);
  v15 = v35;
  if ( *v8 == v35 )
  {
    result = (unsigned int)CallbackContext;
    if ( (unsigned int)CallbackContext > 3 )
    {
      LODWORD(v34) = a4;
      v33 = "LPA::EsimManager::OnEs10bGetUiccInfo2Complete";
      v35 = a3;
      v31 = a2;
      *(_QWORD *)v32 = "LpaServiceEsimManager";
      return _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(
               v13,
               (unsigned int)&unk_18012DDD0,
               v15,
               v14,
               (__int64)v32,
               (__int64)&v33,
               (__int64)&v31,
               (__int64)&v34,
               (__int64)&v35);
    }
  }
  else
  {
    v17 = *(_DWORD *)(*(_QWORD *)(v35 + 40) + 224LL);
    v31 = v17;
    if ( a2 < 0 )
    {
      if ( (unsigned int)CallbackContext > 3 )
      {
        v31 = v17;
        v33 = "LPA::EsimManager::OnEs10bGetUiccInfo2Complete";
        *(_QWORD *)v32 = a3;
        LODWORD(v34) = a2;
        v36 = "LpaServiceEsimManager";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(
          v13,
          (unsigned int)byte_18012DC8D,
          v35,
          v14,
          (__int64)&v36,
          (__int64)&v33,
          (__int64)&v34,
          (__int64)v32,
          (__int64)&v31);
      }
      v18 = (LPA::EsimManager *)(a1 - 8);
    }
    else
    {
      v18 = (LPA::EsimManager *)(a1 - 8);
      LPA::EsimManager::TryFindEsimRecordBySlotId(a1 - 8, v32, &v31, a3);
      v22 = *(_QWORD *)v32;
      if ( *(_QWORD *)(a1 + 200) == *(_QWORD *)v32 )
      {
        if ( (unsigned int)CallbackContext > 2 )
        {
          v31 = v17;
          v33 = "LPA::EsimManager::OnEs10bGetUiccInfo2Complete";
          *(_QWORD *)v32 = a3;
          v34 = "LpaServiceEsimManager";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(
            v19,
            (unsigned int)byte_18012DCE1,
            v20,
            v21,
            (__int64)&v34,
            (__int64)&v33,
            (__int64)v32,
            (__int64)&v31);
        }
      }
      else
      {
        v23 = a7;
        if ( a7 )
        {
          v24 = *(_QWORD *)(*(_QWORD *)v32 + 48LL);
          v25 = *a7;
          v26 = *(_QWORD *)(v24 + 32);
          v27 = (_DWORD *)(v26 + 692);
          if ( *(char *)(v26 + 4) >= 0 || *v27 != v25 )
          {
            *v27 = v25;
            *(_DWORD *)(*(_QWORD *)(v24 + 32) + 4LL) |= 0x80u;
            *(_BYTE *)(v24 + 4) = 1;
          }
          if ( (unsigned int)CallbackContext > 3 )
          {
            v31 = *v23;
            *(_QWORD *)v32 = "LPA::EsimManager::OnEs10bGetUiccInfo2Complete";
            v33 = "LpaServiceEsimManager";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
              (_DWORD)v27,
              (unsigned int)&dword_18012DD7C,
              v24,
              v25,
              (__int64)&v33,
              (__int64)v32,
              (__int64)&v31);
          }
        }
        if ( (int)LPA::Util::CheckSizeAgainstRange(
                    (LPA::Util *)(*(_QWORD *)(v7 + 8) - *(_QWORD *)v7),
                    3u,
                    3u,
                    (unsigned __int64)"LpaServiceEsimManager",
                    L"euiccFirmwareVersion",
                    v30) >= 0 )
        {
          v28 = *(unsigned __int8 **)v7;
          memset(v37, 0, sizeof(v37));
          LODWORD(v29) = v28[2];
          swprintf_s<12>(v37, L"%u.%u.%u", *v28, v28[1], v29);
          LPA::EsimManager::EsimRecord::SetFirmwareVersion(
            *(LPA::EsimManager::EsimRecord **)(v22 + 48),
            (const unsigned __int16 (*)[12])v37);
        }
      }
    }
    return LPA::EsimManager::CompleteOperation(v18);
  }
  return result;
}

```

## disassembly

```asm
0x18008d010  mov     [rsp-8+arg_18], r9d
0x18008d015  push    rbp
0x18008d016  push    rbx
0x18008d017  push    rsi
0x18008d018  push    rdi
0x18008d019  push    r12
0x18008d01b  push    r14
0x18008d01d  push    r15
0x18008d01f  lea     rbp, [rsp-7]
0x18008d024  sub     rsp, 0A0h
0x18008d02b  mov     rax, cs:__security_cookie
0x18008d032  xor     rax, rsp
0x18008d035  mov     [rbp+37h+var_38], rax
0x18008d039  mov     r12, [rbp+37h+arg_28]
0x18008d03d  lea     rbx, [rcx+0E8h]
0x18008d044  mov     r15d, edx
0x18008d047  mov     rsi, rcx
0x18008d04a  mov     r14, r8
0x18008d04d  lea     rdx, [rbp+37h+var_60]
0x18008d051  mov     rcx, rbx
0x18008d054  lea     r8, [rbp+37h+arg_18]
0x18008d058  mov     edi, r9d
0x18008d05b  call    ?find@?$_Tree@V?$_Tmap_traits@KV?$shared_ptr@VDownloadInstance@Lpd@LPA@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$shared_ptr@VDownloadInstance@Lpd@LPA@@@std@@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKV?$shared_ptr@VDownloadInstance@Lpd@LPA@@@std@@@std@@@std@@@std@@@2@AEBK@Z; std::_Tree<std::_Tmap_traits<ulong,std::shared_ptr<LPA::Lpd::DownloadInstance>,std::less<ulong>,std::allocator<std::pair<ulong const,std::shared_ptr<LPA::Lpd::DownloadInstance>>>,0>>::find(ulong const &)
0x18008d060  mov     r8, [rbp+37h+var_60]
0x18008d064  cmp     [rbx], r8
0x18008d067  jnz     short loc_18008D0D7
0x18008d069  mov     eax, cs:CallbackContext
0x18008d06f  cmp     eax, 3
0x18008d072  jbe     loc_18008D2DD
0x18008d078  lea     rax, aLpaEsimmanager_43; "LPA::EsimManager::OnEs10bGetUiccInfo2Co"...
0x18008d07f  mov     dword ptr [rbp+37h+var_68], edi
0x18008d082  mov     [rbp+37h+var_70], rax
0x18008d086  lea     rdi, aLpaserviceesim; "LpaServiceEsimManager"
0x18008d08d  lea     rax, [rbp+37h+var_60]
0x18008d091  mov     [rbp+37h+var_60], r14
0x18008d095  mov     [rsp+0D0h+var_90], rax
0x18008d09a  lea     rdx, unk_18012DDD0
0x18008d0a1  lea     rax, [rbp+37h+var_68]
0x18008d0a5  mov     [rbp+37h+var_80], r15d
0x18008d0a9  mov     [rsp+0D0h+var_98], rax
0x18008d0ae  lea     rax, [rbp+37h+var_80]
0x18008d0b2  mov     [rsp+0D0h+var_A0], rax
0x18008d0b7  lea     rax, [rbp+37h+var_70]
0x18008d0bb  mov     [rsp+0D0h+var_A8], rax
0x18008d0c0  lea     rax, [rbp+37h+var_78]
0x18008d0c4  mov     [rsp+0D0h+var_B0], rax
0x18008d0c9  mov     qword ptr [rbp+37h+var_78], rdi
0x18008d0cd  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U2@U?$_tlgWrapperByRef@$0BA@@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@4AEBU?$_tlgWrapperByRef@$0BA@@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByRef<16> const &)
0x18008d0d2  jmp     loc_18008D2DD
0x18008d0d7  mov     rax, [r8+28h]
0x18008d0db  mov     edi, [rax+0E0h]
0x18008d0e1  mov     [rbp+37h+var_80], edi
0x18008d0e4  test    r15d, r15d
0x18008d0e7  js      loc_18008D268
0x18008d0ed  lea     r15, [rsi-8]
0x18008d0f1  mov     r9, r14
0x18008d0f4  mov     rcx, r15
0x18008d0f7  lea     r8, [rbp+37h+var_80]
0x18008d0fb  lea     rdx, [rbp+37h+var_78]
0x18008d0ff  call    ?TryFindEsimRecordBySlotId@EsimManager@LPA@@AEAA?AV?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@V?$unique_ptr@VEsimRecord@EsimManager@LPA@@U?$default_delete@VEsimRecord@EsimManager@LPA@@@std@@@std@@@std@@@std@@@std@@@std@@AEBKAEBU_GUID@@@Z; LPA::EsimManager::TryFindEsimRecordBySlotId(ulong const &,_GUID const &)
0x18008d104  mov     rbx, qword ptr [rbp+37h+var_78]
0x18008d108  cmp     [rsi+0C8h], rbx
0x18008d10f  jz      loc_18008D20A
0x18008d115  mov     rdx, [rbp+37h+arg_30]
0x18008d119  lea     rdi, aLpaserviceesim; "LpaServiceEsimManager"
0x18008d120  test    rdx, rdx
0x18008d123  jz      short loc_18008D199
0x18008d125  mov     r8, [rbx+30h]
0x18008d129  mov     r9d, [rdx]
0x18008d12c  mov     rax, [r8+20h]
0x18008d130  test    byte ptr [rax+4], 80h
0x18008d134  lea     rcx, [rax+2B4h]
0x18008d13b  jz      short loc_18008D142
0x18008d13d  cmp     [rcx], r9d
0x18008d140  jz      short loc_18008D153
0x18008d142  mov     [rcx], r9d
0x18008d145  mov     rax, [r8+20h]
0x18008d149  bts     dword ptr [rax+4], 7
0x18008d14e  mov     byte ptr [r8+4], 1
0x18008d153  mov     eax, cs:CallbackContext
0x18008d159  cmp     eax, 3
0x18008d15c  jbe     short loc_18008D199
0x18008d15e  mov     eax, [rdx]
0x18008d160  lea     rdx, dword_18012DD7C
0x18008d167  mov     [rbp+37h+var_80], eax
0x18008d16a  lea     rax, aLpaEsimmanager_43; "LPA::EsimManager::OnEs10bGetUiccInfo2Co"...
0x18008d171  mov     qword ptr [rbp+37h+var_78], rax
0x18008d175  lea     rax, [rbp+37h+var_80]
0x18008d179  mov     [rsp+0D0h+var_A0], rax
0x18008d17e  lea     rax, [rbp+37h+var_78]
0x18008d182  mov     [rsp+0D0h+var_A8], rax; unsigned __int16 *
0x18008d187  lea     rax, [rbp+37h+var_70]
0x18008d18b  mov     [rsp+0D0h+var_B0], rax
0x18008d190  mov     [rbp+37h+var_70], rdi
0x18008d194  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18008d199  mov     rcx, [r12+8]
0x18008d19e  lea     rax, aEuiccfirmwarev; "euiccFirmwareVersion"
0x18008d1a5  sub     rcx, [r12]; this
0x18008d1a9  mov     edx, 3; unsigned __int64
0x18008d1ae  mov     r8d, edx; unsigned __int64
0x18008d1b1  mov     [rsp+0D0h+var_B0], rax; char *
0x18008d1b6  mov     r9, rdi; unsigned __int64
0x18008d1b9  call    ?CheckSizeAgainstRange@Util@LPA@@YAJ_K00PEBDPEBG@Z; LPA::Util::CheckSizeAgainstRange(unsigned __int64,unsigned __int64,unsigned __int64,char const *,ushort const *)
0x18008d1be  test    eax, eax
0x18008d1c0  js      loc_18008D2D1
0x18008d1c6  xor     eax, eax
0x18008d1c8  lea     rdx, aUUU; "%u.%u.%u"
0x18008d1cf  mov     qword ptr [rbp+37h+var_50+10h], rax
0x18008d1d3  xorps   xmm0, xmm0
0x18008d1d6  mov     rax, [r12]
0x18008d1da  movups  xmmword ptr [rbp+37h+var_50], xmm0
0x18008d1de  movzx   ecx, byte ptr [rax+2]
0x18008d1e2  movzx   r9d, byte ptr [rax+1]
0x18008d1e7  movzx   r8d, byte ptr [rax]
0x18008d1eb  mov     dword ptr [rsp+0D0h+var_B0], ecx
0x18008d1ef  lea     rcx, [rbp+37h+var_50]
0x18008d1f3  call    ??$swprintf_s@$0M@@@YAHAEAY0M@GPEBGZZ; swprintf_s<12>(ushort (&)[12],ushort const *,...)
0x18008d1f8  mov     rcx, [rbx+30h]; this
0x18008d1fc  lea     rdx, [rbp+37h+var_50]; unsigned __int16 (*)[12]
0x18008d200  call    ?SetFirmwareVersion@EsimRecord@EsimManager@LPA@@QEAAXAEAY0M@$$CBG@Z; LPA::EsimManager::EsimRecord::SetFirmwareVersion(ushort const (&)[12])
0x18008d205  jmp     loc_18008D2D1
0x18008d20a  mov     eax, cs:CallbackContext
0x18008d210  cmp     eax, 2
0x18008d213  jbe     loc_18008D2D1
0x18008d219  lea     rax, aLpaEsimmanager_43; "LPA::EsimManager::OnEs10bGetUiccInfo2Co"...
0x18008d220  mov     [rbp+37h+var_80], edi
0x18008d223  mov     [rbp+37h+var_70], rax
0x18008d227  lea     rdi, aLpaserviceesim; "LpaServiceEsimManager"
0x18008d22e  lea     rax, [rbp+37h+var_80]
0x18008d232  mov     qword ptr [rbp+37h+var_78], r14
0x18008d236  mov     [rsp+0D0h+var_98], rax
0x18008d23b  lea     rdx, byte_18012DCE1
0x18008d242  lea     rax, [rbp+37h+var_78]
0x18008d246  mov     [rbp+37h+var_68], rdi
0x18008d24a  mov     [rsp+0D0h+var_A0], rax
0x18008d24f  lea     rax, [rbp+37h+var_70]
0x18008d253  mov     [rsp+0D0h+var_A8], rax
0x18008d258  lea     rax, [rbp+37h+var_68]
0x18008d25c  mov     [rsp+0D0h+var_B0], rax
0x18008d261  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &)
0x18008d266  jmp     short loc_18008D2D1
0x18008d268  mov     eax, cs:CallbackContext
0x18008d26e  cmp     eax, 3
0x18008d271  jbe     short loc_18008D2CD
0x18008d273  lea     rax, aLpaEsimmanager_43; "LPA::EsimManager::OnEs10bGetUiccInfo2Co"...
0x18008d27a  mov     [rbp+37h+var_80], edi
0x18008d27d  mov     [rbp+37h+var_70], rax
0x18008d281  lea     rdi, aLpaserviceesim; "LpaServiceEsimManager"
0x18008d288  lea     rax, [rbp+37h+var_80]
0x18008d28c  mov     qword ptr [rbp+37h+var_78], r14
0x18008d290  mov     [rsp+0D0h+var_90], rax
0x18008d295  lea     rdx, byte_18012DC8D
0x18008d29c  lea     rax, [rbp+37h+var_78]
0x18008d2a0  mov     dword ptr [rbp+37h+var_68], r15d
0x18008d2a4  mov     [rsp+0D0h+var_98], rax
0x18008d2a9  lea     rax, [rbp+37h+var_68]
0x18008d2ad  mov     [rsp+0D0h+var_A0], rax
0x18008d2b2  lea     rax, [rbp+37h+var_70]
0x18008d2b6  mov     [rsp+0D0h+var_A8], rax
0x18008d2bb  lea     rax, [rbp+37h+var_58]
0x18008d2bf  mov     [rsp+0D0h+var_B0], rax
0x18008d2c4  mov     [rbp+37h+var_58], rdi
0x18008d2c8  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByRef@$0BA@@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByRef@$0BA@@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &)
0x18008d2cd  lea     r15, [rsi-8]
0x18008d2d1  lea     rdx, [rbp+37h+var_60]
0x18008d2d5  mov     rcx, r15; this
0x18008d2d8  call    ?CompleteOperation@EsimManager@LPA@@AEAAXAEAV?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKV?$unique_ptr@VOperationEntry@EsimManager@LPA@@U?$default_delete@VOperationEntry@EsimManager@LPA@@@std@@@std@@@std@@@std@@@std@@@std@@@Z; LPA::EsimManager::CompleteOperation(std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<ulong const,std::unique_ptr<LPA::EsimManager::OperationEntry>>>>> &)
0x18008d2dd  mov     rcx, [rbp+37h+var_38]
0x18008d2e1  xor     rcx, rsp; StackCookie
0x18008d2e4  call    __security_check_cookie
0x18008d2e9  add     rsp, 0A0h
0x18008d2f0  pop     r15
0x18008d2f2  pop     r14
0x18008d2f4  pop     r12
0x18008d2f6  pop     rdi
0x18008d2f7  pop     rsi
0x18008d2f8  pop     rbx
0x18008d2f9  pop     rbp
0x18008d2fa  retn
```
