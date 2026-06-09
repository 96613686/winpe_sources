# Rdp::Avenc::Ic3::CDsStreamSource::WaitForShutdownReadiness(uint)

- ea: `0x180052284`
- end: `0x18005255b`
- name: `?WaitForShutdownReadiness@CDsStreamSource@Ic3@Avenc@Rdp@@QEAAJI@Z`
- size: `727`
- prototype: `__int64 __fastcall(Rdp::Avenc::Ic3::CDsStreamSource *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180044ec0`

## callees

- `0x18000406c`
- `0x180008dc0`
- `0x1800103c0`
- `0x180010bc8`
- `0x180052284`
- `0x1800527c4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800522f7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800524fe`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800522f7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800524fe`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800523f3`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800523f3`

## string_xrefs

- `0x180052542`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180052340`: `Waiting for shutdown readiness`
- `0x180052461`: `ReadyForShutdown`
- `0x18005234c`: `Rdp::Avenc::Ic3::CDsStreamSource::WaitForShutdownReadiness`
- `0x1800523d6`: `Rdp::Avenc::Ic3::CDsStreamSource::WaitForShutdownReadiness`
- `0x180052413`: `Rdp::Avenc::Ic3::CDsStreamSource::WaitForShutdownReadiness`

## pseudocode

```c
// Hidden C++ exception states: #wind=1 #try_helpers=1
__int64 __fastcall Rdp::Avenc::Ic3::CDsStreamSource::WaitForShutdownReadiness(
        Rdp::Avenc::Ic3::CDsStreamSource *this,
        int a2)
{
  char *v3; // rbx
  int v4; // r8d
  const char *v5; // r9
  int v6; // eax
  char v7; // si
  int v8; // eax
  __int64 v9; // rdx
  DWORD v10; // eax
  __int64 v12; // rdx
  const char *v14; // [rsp+60h] [rbp-48h] BYREF
  const char *v15; // [rsp+68h] [rbp-40h] BYREF
  const char *v16; // [rsp+70h] [rbp-38h] BYREF
  char v17; // [rsp+78h] [rbp-30h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+0h]
  int v19; // [rsp+B0h] [rbp+8h] BYREF
  int v20; // [rsp+B8h] [rbp+10h] BYREF
  int v21; // [rsp+C0h] [rbp+18h] BYREF
  __int64 v22; // [rsp+C8h] [rbp+20h] BYREF

  v20 = a2;
  v3 = (char *)this + 112;
  v16 = (char *)this + 112;
  v17 = 0;
  if ( (unsigned int)mtx_do_lock((char *)this + 112) )
    std::_Throw_Cpp_error(5);
  v6 = *((_DWORD *)v3 + 19);
  if ( v6 == 0x7FFFFFFF )
  {
    *((_DWORD *)v3 + 19) = 2147483646;
    std::_Throw_Cpp_error(6);
  }
  v7 = 1;
  v17 = 1;
  if ( *((_QWORD *)this + 38) )
  {
    if ( !v3 )
      std::_Throw_system_error();
    v8 = v6 - 1;
    *((_DWORD *)v3 + 19) = v8;
    if ( !v8 )
    {
      *((_DWORD *)v3 + 18) = -1;
      ReleaseSRWLockExclusive((PSRWLOCK)v3 + 2);
    }
    v7 = 0;
    if ( (unsigned int)dword_1800C1058 > 5 )
    {
      v9 = *((_QWORD *)this + 25);
      v22 = v9 + 112;
      v20 = *(_DWORD *)(*(_QWORD *)(v9 + 104) + 136LL);
      v19 = *(_DWORD *)(v9 + 128);
      v14 = "Waiting for shutdown readiness";
      v15 = "Rdp::Avenc::Ic3::CDsStreamSource::WaitForShutdownReadiness";
      v21 = 199;
      v16 = "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\ic3processor\\dsstreamsource.cpp";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(
        (unsigned int)&dword_1800C1058,
        (unsigned int)&word_1800B2B8E,
        v4,
        (_DWORD)v5,
        (__int64)&v16,
        (__int64)&v21,
        (__int64)&v15,
        (__int64)&v14,
        (__int64)&v19,
        (__int64)&v20,
        (__int64)&v22);
    }
    v10 = WaitForSingleObjectEx(*((HANDLE *)this + 38), 0x9C4u, 0);
    if ( v10 == 258 )
      return 258;
    if ( v10 )
      wil::details::in1diag3::FailFast_Unexpected(
        retaddr,
        (void *)0xB0F,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v5);
  }
  if ( (unsigned int)dword_1800C1058 > 5 )
  {
    v12 = *((_QWORD *)this + 25);
    v22 = v12 + 112;
    v20 = *(_DWORD *)(*(_QWORD *)(v12 + 104) + 136LL);
    v19 = *(_DWORD *)(v12 + 128);
    v16 = "ReadyForShutdown";
    v15 = "Rdp::Avenc::Ic3::CDsStreamSource::WaitForShutdownReadiness";
    v21 = 213;
    v14 = "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\ic3processor\\dsstreamsource.cpp";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(
      (unsigned int)&dword_1800C1058,
      (unsigned int)&word_1800B2BEE,
      v4,
      (_DWORD)v5,
      (__int64)&v14,
      (__int64)&v21,
      (__int64)&v15,
      (__int64)&v16,
      (__int64)&v19,
      (__int64)&v20,
      (__int64)&v22);
  }
  if ( v7 )
  {
    if ( (*((_DWORD *)v3 + 19))-- == 1 )
    {
      *((_DWORD *)v3 + 18) = -1;
      ReleaseSRWLockExclusive((PSRWLOCK)v3 + 2);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180052284  mov     [rsp+arg_8], edx
0x180052288  push    rbx
0x180052289  push    rsi
0x18005228a  push    rdi
0x18005228b  push    r14
0x18005228d  push    r15
0x18005228f  sub     rsp, 80h
0x180052296  mov     rdi, rcx
0x180052299  lea     rbx, [rcx+70h]
0x18005229d  mov     [rsp+0A8h+var_38], rbx
0x1800522a2  mov     [rsp+0A8h+var_30], 0
0x1800522a7  mov     rcx, rbx
0x1800522aa  call    mtx_do_lock
0x1800522af  test    eax, eax
0x1800522b1  jnz     loc_18005251E
0x1800522b7  mov     eax, [rbx+4Ch]
0x1800522ba  cmp     eax, 7FFFFFFFh
0x1800522bf  jz      loc_180052528
0x1800522c5  mov     sil, 1
0x1800522c8  mov     [rsp+0A8h+var_30], sil
0x1800522cd  cmp     qword ptr [rdi+130h], 0
0x1800522d5  jz      loc_180052413
0x1800522db  test    rbx, rbx
0x1800522de  jz      loc_180052554
0x1800522e4  sub     eax, 1
0x1800522e7  mov     [rbx+4Ch], eax
0x1800522ea  jnz     short loc_1800522FD
0x1800522ec  mov     dword ptr [rbx+48h], 0FFFFFFFFh
0x1800522f3  lea     rcx, [rbx+10h]; SRWLock
0x1800522f7  call    cs:__imp_ReleaseSRWLockExclusive
0x1800522fd  xor     sil, sil
0x180052300  mov     eax, cs:dword_1800C1058
0x180052306  cmp     eax, 5
0x180052309  jbe     loc_1800523D6
0x18005230f  mov     rdx, [rdi+0C8h]
0x180052316  lea     rax, [rdx+70h]
0x18005231a  mov     [rsp+0A8h+arg_18], rax
0x180052322  mov     rax, [rdx+68h]
0x180052326  mov     ecx, [rax+88h]
0x18005232c  mov     [rsp+0A8h+arg_8], ecx
0x180052333  mov     eax, [rdx+80h]
0x180052339  mov     [rsp+0A8h+arg_0], eax
0x180052340  lea     rax, aWaitingForShut; "Waiting for shutdown readiness"
0x180052347  mov     [rsp+0A8h+var_48], rax
0x18005234c  lea     r14, aRdpAvencIc3Cds_20; "Rdp::Avenc::Ic3::CDsStreamSource::WaitF"...
0x180052353  mov     [rsp+0A8h+var_40], r14
0x180052358  mov     [rsp+0A8h+arg_10], 0C7h
0x180052363  lea     r15, aOnecoreuapTerm_34; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x18005236a  mov     [rsp+0A8h+var_38], r15
0x18005236f  lea     rax, [rsp+0A8h+arg_18]
0x180052377  mov     [rsp+0A8h+var_58], rax
0x18005237c  lea     rax, [rsp+0A8h+arg_8]
0x180052384  mov     [rsp+0A8h+var_60], rax
0x180052389  lea     rax, [rsp+0A8h+arg_0]
0x180052391  mov     [rsp+0A8h+var_68], rax
0x180052396  lea     rax, [rsp+0A8h+var_48]
0x18005239b  mov     [rsp+0A8h+var_70], rax
0x1800523a0  lea     rax, [rsp+0A8h+var_40]
0x1800523a5  mov     [rsp+0A8h+var_78], rax
0x1800523aa  lea     rax, [rsp+0A8h+arg_10]
0x1800523b2  mov     [rsp+0A8h+var_80], rax
0x1800523b7  lea     rax, [rsp+0A8h+var_38]
0x1800523bc  mov     [rsp+0A8h+var_88], rax
0x1800523c1  lea     rdx, word_1800B2B8E
0x1800523c8  lea     rcx, dword_1800C1058
0x1800523cf  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U2@U2@U?$_tlgWrapperByRef@$0BA@@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3344AEBU?$_tlgWrapperByRef@$0BA@@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByRef<16> const &)
0x1800523d4  jmp     short loc_1800523E4
0x1800523d6  lea     r14, aRdpAvencIc3Cds_20; "Rdp::Avenc::Ic3::CDsStreamSource::WaitF"...
0x1800523dd  lea     r15, aOnecoreuapTerm_34; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x1800523e4  xor     r8d, r8d; bAlertable
0x1800523e7  mov     edx, 9C4h; dwMilliseconds
0x1800523ec  mov     rcx, [rdi+130h]; hHandle
0x1800523f3  call    cs:__imp_WaitForSingleObjectEx
0x1800523f9  mov     ecx, 102h
0x1800523fe  cmp     eax, ecx
0x180052400  jz      short loc_18005240C
0x180052402  test    eax, eax
0x180052404  jnz     loc_18005253A
0x18005240a  jmp     short loc_180052421
0x18005240c  mov     eax, ecx
0x18005240e  jmp     loc_18005250F
0x180052413  lea     r14, aRdpAvencIc3Cds_20; "Rdp::Avenc::Ic3::CDsStreamSource::WaitF"...
0x18005241a  lea     r15, aOnecoreuapTerm_34; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x180052421  mov     eax, cs:dword_1800C1058
0x180052427  cmp     eax, 5
0x18005242a  jbe     loc_1800524E8
0x180052430  mov     rdx, [rdi+0C8h]
0x180052437  lea     rax, [rdx+70h]
0x18005243b  mov     [rsp+0A8h+arg_18], rax
0x180052443  mov     rax, [rdx+68h]
0x180052447  mov     ecx, [rax+88h]
0x18005244d  mov     [rsp+0A8h+arg_8], ecx
0x180052454  mov     eax, [rdx+80h]
0x18005245a  mov     [rsp+0A8h+arg_0], eax
0x180052461  lea     rax, aReadyforshutdo; "ReadyForShutdown"
0x180052468  mov     [rsp+0A8h+var_38], rax
0x18005246d  mov     [rsp+0A8h+var_40], r14
0x180052472  mov     [rsp+0A8h+arg_10], 0D5h
0x18005247d  mov     [rsp+0A8h+var_48], r15
0x180052482  lea     rax, [rsp+0A8h+arg_18]
0x18005248a  mov     [rsp+0A8h+var_58], rax
0x18005248f  lea     rax, [rsp+0A8h+arg_8]
0x180052497  mov     [rsp+0A8h+var_60], rax
0x18005249c  lea     rax, [rsp+0A8h+arg_0]
0x1800524a4  mov     [rsp+0A8h+var_68], rax
0x1800524a9  lea     rax, [rsp+0A8h+var_38]
0x1800524ae  mov     [rsp+0A8h+var_70], rax
0x1800524b3  lea     rax, [rsp+0A8h+var_40]
0x1800524b8  mov     [rsp+0A8h+var_78], rax
0x1800524bd  lea     rax, [rsp+0A8h+arg_10]
0x1800524c5  mov     [rsp+0A8h+var_80], rax
0x1800524ca  lea     rax, [rsp+0A8h+var_48]
0x1800524cf  mov     [rsp+0A8h+var_88], rax
0x1800524d4  lea     rdx, word_1800B2BEE
0x1800524db  lea     rcx, dword_1800C1058
0x1800524e2  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U2@U2@U?$_tlgWrapperByRef@$0BA@@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3344AEBU?$_tlgWrapperByRef@$0BA@@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByRef<16> const &)
0x1800524e7  nop
0x1800524e8  test    sil, sil
0x1800524eb  jz      short loc_180052504
0x1800524ed  sub     dword ptr [rbx+4Ch], 1
0x1800524f1  jnz     short loc_180052504
0x1800524f3  mov     dword ptr [rbx+48h], 0FFFFFFFFh
0x1800524fa  lea     rcx, [rbx+10h]; SRWLock
0x1800524fe  call    cs:__imp_ReleaseSRWLockExclusive
0x180052504  xor     eax, eax
0x180052506  jmp     short loc_18005250F
0x180052508  mov     eax, [rsp+0A8h+arg_8]
0x18005250f  add     rsp, 80h
0x180052516  pop     r15
0x180052518  pop     r14
0x18005251a  pop     rdi
0x18005251b  pop     rsi
0x18005251c  pop     rbx
0x18005251d  retn
0x18005251e  mov     ecx, 5; int
0x180052523  call    ?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x180052528  mov     dword ptr [rbx+4Ch], 7FFFFFFEh
0x18005252f  mov     ecx, 6; int
0x180052534  call    ?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x18005253a  mov     rcx, [rsp+0A8h]; this
0x180052542  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180052549  mov     edx, 0B0Fh; void *
0x18005254e  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180052554  call    ?_Throw_system_error@std@@YAXW4errc@1@@Z; std::_Throw_system_error(std::errc)
```
