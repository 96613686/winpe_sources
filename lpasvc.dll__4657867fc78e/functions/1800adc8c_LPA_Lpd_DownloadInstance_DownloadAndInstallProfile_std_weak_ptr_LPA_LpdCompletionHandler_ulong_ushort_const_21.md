# LPA::Lpd::DownloadInstance::DownloadAndInstallProfile(std::weak_ptr<LPA::LpdCompletionHandler>,ulong &,ushort const (*)[21],bool,LPA::LPAINSTALLCHOICEINTERNAL,ushort const *,LPA_ERROR_DETAILS &)

- ea: `0x1800adc8c`
- end: `0x1800ae1d5`
- name: `?DownloadAndInstallProfile@DownloadInstance@Lpd@LPA@@QEAAJV?$weak_ptr@ULpdCompletionHandler@LPA@@@std@@AEAKPEAY0BF@$$CBG_NW4LPAINSTALLCHOICEINTERNAL@3@PEBGAEAULPA_ERROR_DETAILS@@@Z`
- size: `1353`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800ae1e0`

## callees

- `0x1800017c8`
- `0x180005d6c`
- `0x18000df90`
- `0x1800709e4`
- `0x180070a1c`
- `0x1800715d0`
- `0x180071610`
- `0x180071994`
- `0x180071a8c`
- `0x1800815e0`
- `0x1800a8ed8`
- `0x1800adc8c`
- `0x1800ae32c`
- `0x1800c12c4`
- `0x1800d96e0`
- `0x1800d972c`
- `0x180101010`

## string_xrefs

- `0x1800adcde`: `LpaServiceLpd`
- `0x1800adfea`: `LpaServiceLpd`
- `0x1800ae14a`: `LpaServiceLpd`
- `0x1800adcfb`: `OnInstallProfile`
- `0x1800adcd7`: `LPA::Lpd::DownloadInstance::DownloadAndInstallProfile`
- `0x1800adfde`: `LPA::Lpd::DownloadInstance::DownloadAndInstallProfile`
- `0x1800ae13e`: `LPA::Lpd::DownloadInstance::DownloadAndInstallProfile`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall LPA::Lpd::DownloadInstance::DownloadAndInstallProfile(
        __int64 a1,
        __int64 a2,
        const char *a3,
        _WORD *a4,
        char a5,
        int a6,
        __int64 a7,
        __int64 a8)
{
  __int64 v11; // r15
  const char *v12; // rcx
  int v13; // ebx
  const char *v14; // rax
  __int16 *v15; // rdx
  char *v16; // rdx
  int v17; // r15d
  __int64 v18; // rdi
  __int64 (__fastcall *v19)(__int64, __int64, _QWORD, __int64, int, __int64 *, __int64); // rbx
  _QWORD *v20; // rax
  __int64 *v21; // rax
  int v22; // ecx
  int v23; // r8d
  int v24; // r9d
  __int64 v25; // rdi
  __int64 (__fastcall *v26)(__int64, __int64, _QWORD, __int64, __int64, __int64, __int128 *, __int64 *, __int64); // rbx
  _QWORD *v27; // rax
  __int64 *v28; // rax
  std::_Ref_count_base *v29; // rcx
  int v31; // [rsp+60h] [rbp-99h] BYREF
  int v32; // [rsp+64h] [rbp-95h] BYREF
  int v33; // [rsp+68h] [rbp-91h] BYREF
  int v34; // [rsp+6Ch] [rbp-8Dh] BYREF
  __int64 v35[2]; // [rsp+70h] [rbp-89h] BYREF
  const char *v36; // [rsp+80h] [rbp-79h] BYREF
  std::_Ref_count_base *v37; // [rsp+88h] [rbp-71h]
  const char *v38; // [rsp+90h] [rbp-69h] BYREF
  __int64 v39; // [rsp+98h] [rbp-61h]
  const char *v40; // [rsp+A0h] [rbp-59h] BYREF
  std::_Ref_count_base *v41; // [rsp+A8h] [rbp-51h]
  __int128 v42; // [rsp+B0h] [rbp-49h] BYREF
  __int64 v43; // [rsp+C0h] [rbp-39h]
  __int64 v44; // [rsp+C8h] [rbp-31h]
  _OWORD v45[2]; // [rsp+D0h] [rbp-29h] BYREF

  v38 = a3;
  v44 = a2;
  v11 = a8;
  v39 = a8;
  v12 = "LPA::Lpd::DownloadInstance::DownloadAndInstallProfile";
  if ( (unsigned int)CallbackContext > 4 )
  {
    v32 = 0;
    v33 = 11;
    v40 = "OnInstallProfile";
    v34 = *(_DWORD *)(a1 + 912);
    v31 = 4;
    v36 = "LPA::Lpd::DownloadInstance::DownloadAndInstallProfile";
    v35[0] = (__int64)"LpaServiceLpd";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      (unsigned int)"LPA::Lpd::DownloadInstance::DownloadAndInstallProfile",
      (unsigned int)&byte_18012FD47,
      (_DWORD)a3,
      (_DWORD)a4,
      (__int64)v35,
      (__int64)&v36,
      (__int64)&v31,
      (__int64)&v34,
      (__int64)&v40,
      (__int64)&v33,
      (__int64)&v32);
  }
  if ( !*a4 )
  {
    v13 = -2147024809;
    goto LABEL_5;
  }
  if ( (unsigned int)std::wstring::compare(a1 + 464, a4) )
  {
    v13 = -2147023728;
    goto LABEL_5;
  }
  if ( !*(_BYTE *)(a1 + 873) )
  {
    v13 = -2147019873;
    goto LABEL_5;
  }
  std::weak_ptr<LPA::LpdCompletionHandler>::operator=(a1 + 64, a2);
  std::weak_ptr<LPA::Lpd::DownloadInstance>::lock(a1 + 32, &v40);
  v16 = (char *)v40;
  if ( !v40 )
    goto LABEL_19;
  if ( !a6 )
  {
    v42 = 0;
    v43 = 0;
    if ( *(_BYTE *)(a1 + 139) )
    {
      v45[0] = 0;
      v45[1] = _mm_load_si128((const __m128i *)&_xmm);
      LOBYTE(v45[0]) = 0;
      v13 = LPA::Util::ConvertUtf16ToUtf8(a7, v45);
      if ( v13 < 0
        || (v13 = LPA::Lpd::DownloadInstance::EncryptConfirmationCode((__int64)v45, a1 + 520, (PUCHAR *)&v42), v13 < 0) )
      {
        if ( (unsigned int)CallbackContext > 2 )
        {
          v31 = v13;
          v35[0] = (__int64)"LPA::Lpd::DownloadInstance::DownloadAndInstallProfile";
          v36 = "LpaServiceLpd";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
            v22,
            (unsigned int)&word_18012FCA6,
            v23,
            v24,
            (__int64)&v36,
            (__int64)v35,
            (__int64)&v31);
        }
      }
      std::string::_Tidy_deallocate(v45);
      if ( v13 < 0 )
        goto LABEL_50;
      v16 = (char *)v40;
    }
    v25 = *((_QWORD *)v16 + 7);
    v26 = *(__int64 (__fastcall **)(__int64, __int64, _QWORD, __int64, __int64, __int64, __int128 *, __int64 *, __int64))(*(_QWORD *)(v25 + 8) + 48LL);
    v27 = (_QWORD *)std::enable_shared_from_this<LPA::EnterpriseManager>::shared_from_this(a1 + 16, &v36);
    v28 = std::weak_ptr<LPA::ApduHelperEs10bCompletionHandler>::weak_ptr<LPA::ApduHelperEs10bCompletionHandler>(
            v35,
            v27);
    v13 = v26(v25 + 8, a1 + 884, *(unsigned int *)(a1 + 1036), a1 + 616, a1 + 640, a1 + 664, &v42, v28, a1 + 920);
    if ( v37 )
      std::_Ref_count_base::_Decref(v37);
    if ( v13 < 0 && ((*(_BYTE *)(a1 + 1024) & 1) == 0 || !*(_DWORD *)(a1 + 1028)) )
    {
      *(_DWORD *)(a1 + 1024) |= 1u;
      *(_DWORD *)(a1 + 1028) = 1;
    }
LABEL_50:
    std::vector<unsigned char>::_Tidy(&v42);
    goto LABEL_33;
  }
  if ( a6 != 1 && a6 != 2 && (unsigned int)(a6 - 3) >= 2 )
  {
LABEL_19:
    v13 = -2147418113;
    goto LABEL_33;
  }
  v17 = 127;
  *(_BYTE *)(a1 + 875) = a5 ^ 1;
  switch ( a6 )
  {
    case 1:
      v17 = 1;
      break;
    case 2:
      v17 = 0;
      break;
    case 3:
      v17 = 3;
      break;
  }
  v18 = *((_QWORD *)v16 + 7);
  v19 = *(__int64 (__fastcall **)(__int64, __int64, _QWORD, __int64, int, __int64 *, __int64))(*(_QWORD *)(v18 + 8) + 8LL);
  v20 = (_QWORD *)std::enable_shared_from_this<LPA::EnterpriseManager>::shared_from_this(a1 + 16, &v36);
  v21 = std::weak_ptr<LPA::ApduHelperEs10bCompletionHandler>::weak_ptr<LPA::ApduHelperEs10bCompletionHandler>(v35, v20);
  v13 = v19(v18 + 8, a1 + 884, *(unsigned int *)(a1 + 1036), a1 + 520, v17, v21, a1 + 920);
  if ( v37 )
    std::_Ref_count_base::_Decref(v37);
  if ( v13 < 0 && ((*(_BYTE *)(a1 + 1024) & 1) == 0 || !*(_DWORD *)(a1 + 1028)) )
  {
    *(_DWORD *)(a1 + 1024) |= 1u;
    *(_DWORD *)(a1 + 1028) = 1;
  }
  v11 = v39;
LABEL_33:
  LODWORD(v12) = (_DWORD)v41;
  if ( v41 )
    std::_Ref_count_base::_Decref(v41);
  if ( v13 < 0 )
  {
LABEL_5:
    *(_QWORD *)v11 = *(_QWORD *)(a1 + 1024);
    *(_DWORD *)(v11 + 8) = *(_DWORD *)(a1 + 1032);
    if ( (unsigned int)CallbackContext > 2 )
    {
      v31 = *(_DWORD *)(a1 + 920);
      v34 = 17;
      v14 = "Failure";
      v15 = word_18012FC42;
LABEL_53:
      v38 = v14;
      v33 = *(_DWORD *)(a1 + 912);
      v35[0] = (__int64)"LPA::Lpd::DownloadInstance::DownloadAndInstallProfile";
      v36 = "LpaServiceLpd";
      v32 = 4;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (_DWORD)v12,
        (_DWORD)v15,
        (_DWORD)a3,
        (_DWORD)a4,
        (__int64)&v36,
        (__int64)v35,
        (__int64)&v32,
        (__int64)&v33,
        (__int64)&v38,
        (__int64)&v34,
        (__int64)&v31);
      goto LABEL_54;
    }
    goto LABEL_54;
  }
  LPA::Util::CancelTimer((PTP_TIMER *)(a1 + 928), (struct _TP_TIMER **)v16);
  *(_DWORD *)(a1 + 912) = *(_DWORD *)v38;
  *(_WORD *)(a1 + 872) = 0;
  if ( (unsigned int)CallbackContext > 4 )
  {
    v31 = *(_DWORD *)(a1 + 920);
    v34 = (a6 != 0) + 8;
    v12 = "WaitEs10bCancelSession";
    v14 = "WaitEs10bPrepareDownload";
    if ( a6 )
      v14 = "WaitEs10bCancelSession";
    v15 = (__int16 *)byte_18012FCE3;
    goto LABEL_53;
  }
LABEL_54:
  v29 = *(std::_Ref_count_base **)(a2 + 8);
  if ( v29 )
    std::_Ref_count_base::_Decwref(v29);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x1800adc8c  push    rbp
0x1800adc8e  push    rbx
0x1800adc8f  push    rsi
0x1800adc90  push    rdi
0x1800adc91  push    r13
0x1800adc93  push    r14
0x1800adc95  push    r15
0x1800adc97  lea     rbp, [rsp-7]
0x1800adc9c  sub     rsp, 100h
0x1800adca3  mov     rax, cs:__security_cookie
0x1800adcaa  xor     rax, rsp
0x1800adcad  mov     [rbp+37h+var_40], rax
0x1800adcb1  mov     rbx, r9
0x1800adcb4  mov     [rbp+37h+var_A0], r8
0x1800adcb8  mov     r13, rdx
0x1800adcbb  mov     rsi, rcx
0x1800adcbe  mov     [rbp+37h+var_68], rdx
0x1800adcc2  mov     rdi, [rbp+37h+arg_30]
0x1800adcc6  mov     r15, [rbp+37h+arg_38]
0x1800adcca  mov     [rbp+37h+var_98], r15
0x1800adcce  mov     eax, cs:CallbackContext
0x1800adcd4  xor     r14d, r14d
0x1800adcd7  lea     rcx, aLpaLpdDownload_30; "LPA::Lpd::DownloadInstance::DownloadAnd"...
0x1800adcde  lea     rdx, aLpaservicelpd; "LpaServiceLpd"
0x1800adce5  cmp     eax, 4
0x1800adce8  jbe     loc_1800ADD71
0x1800adcee  mov     [rsp+130h+var_CC], r14d
0x1800adcf3  mov     [rsp+130h+var_C8], 0Bh
0x1800adcfb  lea     rax, aOninstallprofi; "OnInstallProfile"
0x1800add02  mov     [rbp+37h+var_90], rax
0x1800add06  mov     eax, [rsi+390h]
0x1800add0c  mov     [rsp+130h+var_C4], eax
0x1800add10  mov     [rsp+130h+var_D0], 4
0x1800add18  mov     [rbp+37h+var_B0], rcx
0x1800add1c  mov     [rsp+130h+var_C0], rdx
0x1800add21  lea     rax, [rsp+130h+var_CC]
0x1800add26  mov     [rsp+130h+var_E0], rax
0x1800add2b  lea     rax, [rsp+130h+var_C8]
0x1800add30  mov     [rsp+130h+var_E8], rax
0x1800add35  lea     rax, [rbp+37h+var_90]
0x1800add39  mov     [rsp+130h+var_F0], rax
0x1800add3e  lea     rax, [rsp+130h+var_C4]
0x1800add43  mov     [rsp+130h+var_F8], rax
0x1800add48  lea     rax, [rsp+130h+var_D0]
0x1800add4d  mov     [rsp+130h+var_100], rax
0x1800add52  lea     rax, [rbp+37h+var_B0]
0x1800add56  mov     [rsp+130h+var_108], rax
0x1800add5b  lea     rax, [rsp+130h+var_C0]
0x1800add60  mov     [rsp+130h+var_110], rax
0x1800add65  lea     rdx, byte_18012FD47
0x1800add6c  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U2@U1@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@4344@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800add71  cmp     [rbx], r14w
0x1800add75  jnz     short loc_1800ADDE6
0x1800add77  mov     ebx, 80070057h
0x1800add7c  movsd   xmm0, qword ptr [rsi+400h]
0x1800add84  movsd   qword ptr [r15], xmm0
0x1800add89  mov     eax, [rsi+408h]
0x1800add8f  mov     [r15+8], eax
0x1800add93  test    ebx, ebx
0x1800add95  js      loc_1800AE101
0x1800add9b  mov     eax, cs:CallbackContext
0x1800adda1  cmp     eax, 4
0x1800adda4  jbe     loc_1800AE1A7
0x1800addaa  mov     eax, [rsi+398h]
0x1800addb0  mov     [rsp+130h+var_D0], eax
0x1800addb4  mov     eax, [rbp+37h+arg_28]
0x1800addb7  neg     eax
0x1800addb9  sbb     ecx, ecx
0x1800addbb  neg     ecx
0x1800addbd  add     ecx, 8
0x1800addc0  mov     [rsp+130h+var_C4], ecx
0x1800addc4  lea     rcx, aWaites10bcance; "WaitEs10bCancelSession"
0x1800addcb  lea     rax, aWaites10bprepa; "WaitEs10bPrepareDownload"
0x1800addd2  cmp     [rbp+37h+arg_28], r14d
0x1800addd6  cmovnz  rax, rcx
0x1800addda  lea     rdx, byte_18012FCE3
0x1800adde1  jmp     loc_1800AE130
0x1800adde6  lea     rcx, [rsi+1D0h]
0x1800added  mov     rdx, rbx
0x1800addf0  call    ?compare@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAHQEBG@Z; std::wstring::compare(ushort const * const)
0x1800addf5  test    eax, eax
0x1800addf7  jz      short loc_1800ADE03
0x1800addf9  mov     ebx, 80070490h
0x1800addfe  jmp     loc_1800ADD7C
0x1800ade03  cmp     [rsi+369h], r14b
0x1800ade0a  jnz     short loc_1800ADE16
0x1800ade0c  mov     ebx, 8007139Fh
0x1800ade11  jmp     loc_1800ADD7C
0x1800ade16  lea     rcx, [rsi+40h]
0x1800ade1a  mov     rdx, r13
0x1800ade1d  call    ??4?$weak_ptr@ULpdCompletionHandler@LPA@@@std@@QEAAAEAV01@AEBV01@@Z; std::weak_ptr<LPA::LpdCompletionHandler>::operator=(std::weak_ptr<LPA::LpdCompletionHandler> const &)
0x1800ade22  lea     rcx, [rsi+20h]
0x1800ade26  lea     rdx, [rbp+37h+var_90]
0x1800ade2a  call    ?lock@?$weak_ptr@VDownloadInstance@Lpd@LPA@@@std@@QEBA?AV?$shared_ptr@VDownloadInstance@Lpd@LPA@@@2@XZ; std::weak_ptr<LPA::Lpd::DownloadInstance>::lock(void)
0x1800ade2f  nop
0x1800ade30  mov     rdx, [rbp+37h+var_90]
0x1800ade34  test    rdx, rdx
0x1800ade37  jz      short loc_1800ADE58
0x1800ade39  mov     ecx, [rbp+37h+arg_28]
0x1800ade3c  test    ecx, ecx
0x1800ade3e  jz      loc_1800ADF75
0x1800ade44  sub     ecx, 1
0x1800ade47  jz      short loc_1800ADE62
0x1800ade49  sub     ecx, 1
0x1800ade4c  jz      short loc_1800ADE62
0x1800ade4e  sub     ecx, 1
0x1800ade51  jz      short loc_1800ADE62
0x1800ade53  cmp     ecx, 1
0x1800ade56  jz      short loc_1800ADE62
0x1800ade58  mov     ebx, 8000FFFFh
0x1800ade5d  jmp     loc_1800ADF39
0x1800ade62  mov     r15d, 7Fh
0x1800ade68  mov     al, [rbp+37h+arg_20]
0x1800ade6b  lea     r14d, [r15-7Eh]
0x1800ade6f  xor     al, r14b
0x1800ade72  mov     [rsi+36Bh], al
0x1800ade78  mov     ecx, [rbp+37h+arg_28]
0x1800ade7b  sub     ecx, r14d
0x1800ade7e  jz      short loc_1800ADE95
0x1800ade80  sub     ecx, r14d
0x1800ade83  jz      short loc_1800ADE90
0x1800ade85  sub     ecx, r14d
0x1800ade88  jnz     short loc_1800ADE98
0x1800ade8a  lea     r15d, [r14+2]
0x1800ade8e  jmp     short loc_1800ADE98
0x1800ade90  xor     r15d, r15d
0x1800ade93  jmp     short loc_1800ADE98
0x1800ade95  mov     r15d, r14d
0x1800ade98  mov     rdi, [rdx+38h]
0x1800ade9c  mov     rax, [rdi+8]
0x1800adea0  mov     rbx, [rax+8]
0x1800adea4  lea     rcx, [rsi+10h]
0x1800adea8  lea     rdx, [rbp+37h+var_B0]
0x1800adeac  call    ?shared_from_this@?$enable_shared_from_this@VEnterpriseManager@LPA@@@std@@QEAA?AV?$shared_ptr@VEnterpriseManager@LPA@@@2@XZ; std::enable_shared_from_this<LPA::EnterpriseManager>::shared_from_this(void)
0x1800adeb1  nop
0x1800adeb2  mov     rdx, rax
0x1800adeb5  lea     rcx, [rsp+130h+var_C0]
0x1800adeba  call    ??$?0VEsimManager@LPA@@$0A@@?$weak_ptr@UApduHelperEs10bCompletionHandler@LPA@@@std@@QEAA@AEBV?$shared_ptr@VEsimManager@LPA@@@1@@Z; std::weak_ptr<LPA::ApduHelperEs10bCompletionHandler>::weak_ptr<LPA::ApduHelperEs10bCompletionHandler>(std::shared_ptr<LPA::EsimManager> const &)
0x1800adebf  lea     r8, [rsi+398h]
0x1800adec6  lea     r9, [rsi+208h]
0x1800adecd  lea     rdx, [rsi+374h]
0x1800aded4  mov     [rsp+130h+var_100], r8
0x1800aded9  mov     [rsp+130h+var_108], rax
0x1800adede  mov     dword ptr [rsp+130h+var_110], r15d
0x1800adee3  mov     r8d, [rsi+40Ch]
0x1800adeea  lea     rcx, [rdi+8]
0x1800adeee  mov     rax, rbx
0x1800adef1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800adef6  mov     ebx, eax
0x1800adef8  mov     rcx, [rbp+37h+var_A8]; this
0x1800adefc  test    rcx, rcx
0x1800adeff  jz      short loc_1800ADF06
0x1800adf01  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800adf06  test    ebx, ebx
0x1800adf08  jns     short loc_1800ADF32
0x1800adf0a  mov     ecx, [rsi+400h]
0x1800adf10  mov     eax, ecx
0x1800adf12  and     eax, r14d
0x1800adf15  test    al, al
0x1800adf17  jz      short loc_1800ADF22
0x1800adf19  cmp     dword ptr [rsi+404h], 0
0x1800adf20  jnz     short loc_1800ADF32
0x1800adf22  or      ecx, r14d
0x1800adf25  mov     [rsi+400h], ecx
0x1800adf2b  mov     [rsi+404h], r14d
0x1800adf32  mov     r15, [rbp+37h+var_98]
0x1800adf36  xor     r14d, r14d
0x1800adf39  mov     rcx, [rbp+37h+var_88]; this
0x1800adf3d  test    rcx, rcx
0x1800adf40  jz      short loc_1800ADF47
0x1800adf42  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800adf47  test    ebx, ebx
0x1800adf49  js      loc_1800ADD7C
0x1800adf4f  lea     rcx, [rsi+3A0h]; this
0x1800adf56  call    ?CancelTimer@Util@LPA@@YAXAEAPEAU_TP_TIMER@@@Z; LPA::Util::CancelTimer(_TP_TIMER * &)
0x1800adf5b  mov     rcx, [rbp+37h+var_A0]
0x1800adf5f  mov     eax, [rcx]
0x1800adf61  mov     [rsi+390h], eax
0x1800adf67  mov     word ptr [rsi+368h], 0
0x1800adf70  jmp     loc_1800ADD9B
0x1800adf75  xorps   xmm0, xmm0
0x1800adf78  movdqu  [rbp+37h+var_80], xmm0
0x1800adf7d  mov     [rbp+37h+var_70], r14
0x1800adf81  cmp     [rsi+8Bh], r14b
0x1800adf88  jz      loc_1800AE034
0x1800adf8e  movups  [rbp+37h+var_60], xmm0
0x1800adf92  movdqa  xmm1, cs:__xmm@000000000000000f0000000000000000
0x1800adf9a  movdqu  [rbp+37h+var_50], xmm1
0x1800adf9f  mov     byte ptr [rbp+37h+var_60], r14b
0x1800adfa3  lea     rdx, [rbp+37h+var_60]
0x1800adfa7  mov     rcx, rdi
0x1800adfaa  call    ?ConvertUtf16ToUtf8@Util@LPA@@YAJPEBGAEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEAV?$wstring_convert@V?$codecvt_utf8_utf16@G$0BAPPPP@$0A@@std@@GV?$allocator@G@2@V?$allocator@D@2@@4@@Z; LPA::Util::ConvertUtf16ToUtf8(ushort const *,std::string &,std::wstring_convert<std::codecvt_utf8_utf16<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>> *)
0x1800adfaf  mov     ebx, eax
0x1800adfb1  test    eax, eax
0x1800adfb3  js      short loc_1800ADFCF
0x1800adfb5  lea     rdx, [rsi+208h]
0x1800adfbc  lea     r8, [rbp+37h+var_80]
0x1800adfc0  lea     rcx, [rbp+37h+var_60]
0x1800adfc4  call    ?EncryptConfirmationCode@DownloadInstance@Lpd@LPA@@CAJAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBV?$vector@EV?$allocator@E@std@@@5@AEAV65@@Z; LPA::Lpd::DownloadInstance::EncryptConfirmationCode(std::string const &,std::vector<uchar> const &,std::vector<uchar> &)
0x1800adfc9  mov     ebx, eax
0x1800adfcb  test    eax, eax
0x1800adfcd  jns     short loc_1800AE01F
0x1800adfcf  mov     eax, cs:CallbackContext
0x1800adfd5  cmp     eax, 2
0x1800adfd8  jbe     short loc_1800AE01F
0x1800adfda  mov     [rsp+130h+var_D0], ebx
0x1800adfde  lea     rax, aLpaLpdDownload_30; "LPA::Lpd::DownloadInstance::DownloadAnd"...
0x1800adfe5  mov     [rsp+130h+var_C0], rax
0x1800adfea  lea     rax, aLpaservicelpd; "LpaServiceLpd"
0x1800adff1  mov     [rbp+37h+var_B0], rax
0x1800adff5  lea     rax, [rsp+130h+var_D0]
0x1800adffa  mov     [rsp+130h+var_100], rax
0x1800adfff  lea     rax, [rsp+130h+var_C0]
0x1800ae004  mov     [rsp+130h+var_108], rax
0x1800ae009  lea     rax, [rbp+37h+var_B0]
0x1800ae00d  mov     [rsp+130h+var_110], rax
0x1800ae012  lea     rdx, word_18012FCA6
0x1800ae019  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1800ae01e  nop
0x1800ae01f  lea     rcx, [rbp+37h+var_60]
0x1800ae023  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800ae028  test    ebx, ebx
0x1800ae02a  js      loc_1800AE0F3
0x1800ae030  mov     rdx, [rbp+37h+var_90]
0x1800ae034  mov     rdi, [rdx+38h]
0x1800ae038  mov     rax, [rdi+8]
0x1800ae03c  mov     rbx, [rax+30h]
0x1800ae040  lea     rcx, [rsi+10h]
0x1800ae044  lea     rdx, [rbp+37h+var_B0]
0x1800ae048  call    ?shared_from_this@?$enable_shared_from_this@VEnterpriseManager@LPA@@@std@@QEAA?AV?$shared_ptr@VEnterpriseManager@LPA@@@2@XZ; std::enable_shared_from_this<LPA::EnterpriseManager>::shared_from_this(void)
0x1800ae04d  nop
0x1800ae04e  mov     rdx, rax
0x1800ae051  lea     rcx, [rsp+130h+var_C0]
0x1800ae056  call    ??$?0VEsimManager@LPA@@$0A@@?$weak_ptr@UApduHelperEs10bCompletionHandler@LPA@@@std@@QEAA@AEBV?$shared_ptr@VEsimManager@LPA@@@1@@Z; std::weak_ptr<LPA::ApduHelperEs10bCompletionHandler>::weak_ptr<LPA::ApduHelperEs10bCompletionHandler>(std::shared_ptr<LPA::EsimManager> const &)
0x1800ae05b  lea     r8, [rsi+398h]
0x1800ae062  lea     r10, [rsi+298h]
0x1800ae069  lea     r11, [rsi+280h]
0x1800ae070  lea     r9, [rsi+268h]
0x1800ae077  lea     rdx, [rsi+374h]
0x1800ae07e  mov     [rsp+130h+var_F0], r8
0x1800ae083  mov     [rsp+130h+var_F8], rax
0x1800ae088  lea     rax, [rbp+37h+var_80]
0x1800ae08c  mov     [rsp+130h+var_100], rax
0x1800ae091  mov     [rsp+130h+var_108], r10
0x1800ae096  mov     [rsp+130h+var_110], r11
0x1800ae09b  mov     r8d, [rsi+40Ch]
0x1800ae0a2  lea     rcx, [rdi+8]
0x1800ae0a6  mov     rax, rbx
0x1800ae0a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ae0ae  mov     ebx, eax
0x1800ae0b0  mov     rcx, [rbp+37h+var_A8]; this
0x1800ae0b4  test    rcx, rcx
0x1800ae0b7  jz      short loc_1800AE0BE
0x1800ae0b9  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800ae0be  test    ebx, ebx
0x1800ae0c0  jns     short loc_1800AE0F3
0x1800ae0c2  mov     ecx, [rsi+400h]
0x1800ae0c8  mov     eax, ecx
0x1800ae0ca  mov     r14d, 1
0x1800ae0d0  and     eax, r14d
0x1800ae0d3  test    al, al
0x1800ae0d5  jz      short loc_1800AE0E0
0x1800ae0d7  cmp     dword ptr [rsi+404h], 0
0x1800ae0de  jnz     short loc_1800AE0F0
0x1800ae0e0  or      ecx, r14d
0x1800ae0e3  mov     [rsi+400h], ecx
0x1800ae0e9  mov     [rsi+404h], r14d
0x1800ae0f0  xor     r14d, r14d
0x1800ae0f3  lea     rcx, [rbp+37h+var_80]
0x1800ae0f7  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x1800ae0fc  jmp     loc_1800ADF39
0x1800ae101  mov     eax, cs:CallbackContext
0x1800ae107  cmp     eax, 2
0x1800ae10a  jbe     loc_1800AE1A7
0x1800ae110  mov     eax, [rsi+398h]
0x1800ae116  mov     [rsp+130h+var_D0], eax
0x1800ae11a  mov     [rsp+130h+var_C4], 11h
0x1800ae122  lea     rax, aFailure; "Failure"
0x1800ae129  lea     rdx, word_18012FC42
0x1800ae130  mov     [rbp+37h+var_A0], rax
0x1800ae134  mov     eax, [rsi+390h]
0x1800ae13a  mov     [rsp+130h+var_C8], eax
0x1800ae13e  lea     rax, aLpaLpdDownload_30; "LPA::Lpd::DownloadInstance::DownloadAnd"...
0x1800ae145  mov     [rsp+130h+var_C0], rax
0x1800ae14a  lea     rax, aLpaservicelpd; "LpaServiceLpd"
0x1800ae151  mov     [rbp+37h+var_B0], rax
0x1800ae155  lea     rax, [rsp+130h+var_D0]
0x1800ae15a  mov     [rsp+130h+var_E0], rax
0x1800ae15f  lea     rax, [rsp+130h+var_C4]
0x1800ae164  mov     [rsp+130h+var_E8], rax
0x1800ae169  lea     rax, [rbp+37h+var_A0]
0x1800ae16d  mov     [rsp+130h+var_F0], rax
0x1800ae172  lea     rax, [rsp+130h+var_C8]
0x1800ae177  mov     [rsp+130h+var_F8], rax
0x1800ae17c  lea     rax, [rsp+130h+var_CC]
0x1800ae181  mov     [rsp+130h+var_100], rax
0x1800ae186  lea     rax, [rsp+130h+var_C0]
0x1800ae18b  mov     [rsp+130h+var_108], rax
0x1800ae190  lea     rax, [rbp+37h+var_B0]
0x1800ae194  mov     [rsp+130h+var_110], rax
  ... truncated ...
```
