# RealtimeProtection::CRtpDlpEngine::RefreshSpoolerEnlightenmentState(void)

- ea: `0x180079c34`
- end: `0x180079dbf`
- name: `?RefreshSpoolerEnlightenmentState@CRtpDlpEngine@RealtimeProtection@@QEAAJXZ`
- size: `395`
- prototype: `__int64 __fastcall(RealtimeProtection::CRtpDlpEngine *__hidden this)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x18007a790`
- `0x18019d7f8`

## callees

- `0x180079c34`
- `0x180079dc0`
- `0x180079e9c`
- `0x18007b40c`
- `0x1800809d0`
- `0x180089510`
- `0x18010cb40`

## import_xrefs

- `MpClient!MpConfigSetValue` at `0x180079d19`
- `MpClient!MpConfigSetValue` at `0x180079d19`
- `MpClient!MpConfigClose` at `0x180079cf1`
- `MpClient!MpConfigClose` at `0x180079d9a`
- `MpClient!MpConfigClose` at `0x180079cf1`
- `MpClient!MpConfigClose` at `0x180079d9a`
- `MpClient!MpConfigOpen` at `0x180079cdb`
- `MpClient!MpConfigOpen` at `0x180079cdb`

## string_xrefs

- `0x180079cba`: `RefreshSpoolerEnlightenmentState: SpoolerState %d, SigConfig %d, DisablePrintDetours %d`

## pseudocode

```c
__int64 __fastcall RealtimeProtection::CRtpDlpEngine::RefreshSpoolerEnlightenmentState(
        RealtimeProtection::CRtpDlpEngine *this)
{
  RealtimeProtection::DlpEngineUtils *v2; // rcx
  RealtimeProtection *v3; // rcx
  BOOL IsSpoolerDlpEnlightenmentEnabledFromEngine; // ebx
  bool IsSpoolerDlpEnlightened; // al
  __int64 v6; // rdx
  int v7; // ebx
  __int64 v8; // r8
  __int64 v9; // r9
  __int64 v10; // rcx
  int v12; // eax
  __int64 v13; // r9
  BOOL v14; // [rsp+30h] [rbp-28h] BYREF
  __int64 v15; // [rsp+38h] [rbp-20h] BYREF

  v2 = (RealtimeProtection::DlpEngineUtils *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 42, &WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids);
  IsSpoolerDlpEnlightenmentEnabledFromEngine = RealtimeProtection::DlpEngineUtils::IsSpoolerDlpEnlightenmentEnabledFromEngine(v2);
  v14 = 0;
  IsSpoolerDlpEnlightened = 0;
  if ( IsSpoolerDlpEnlightenmentEnabledFromEngine )
  {
    IsSpoolerDlpEnlightened = RealtimeProtection::UtilsIsSpoolerDlpEnlightened(v3);
    v14 = IsSpoolerDlpEnlightened;
  }
  RealtimeProtection::MpLogMessageImpl(
    (RealtimeProtection *)L"RefreshSpoolerEnlightenmentState: SpoolerState %d, SigConfig %d, DisablePrintDetours %d",
    (const wchar_t *)IsSpoolerDlpEnlightened,
    IsSpoolerDlpEnlightenmentEnabledFromEngine);
  v15 = 0;
  v7 = MpConfigOpen(L"Features", &v15);
  v10 = v15;
  if ( v7 < 0 )
    goto LABEL_7;
  v12 = MpConfigSetValue(v15, L"DlpDisablePrintDetours", 1, 4, &v14);
  v7 = v12;
  if ( v12 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        43,
        &WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids,
        (unsigned int)v12);
    v10 = v15;
LABEL_7:
    if ( v10 )
      MpConfigClose(v10, v6, v8, v9);
    return (unsigned int)v7;
  }
  v13 = (unsigned int)!v14 + 1;
  *((_DWORD *)this + 18) = v13;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 44, &WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids, v13);
  if ( v15 )
    MpConfigClose(v15, v6, v8, v13);
  return 0;
}

```

## disassembly

```asm
0x180079c34  mov     [rsp+arg_8], rbx
0x180079c39  mov     [rsp+arg_10], rbp
0x180079c3e  push    rdi
0x180079c3f  sub     rsp, 50h
0x180079c43  mov     rax, cs:__security_cookie
0x180079c4a  xor     rax, rsp
0x180079c4d  mov     [rsp+58h+var_18], rax
0x180079c52  mov     rdi, rcx
0x180079c55  lea     rbp, WPP_GLOBAL_Control
0x180079c5c  mov     rcx, cs:WPP_GLOBAL_Control
0x180079c63  cmp     rcx, rbp
0x180079c66  jz      short loc_180079C83
0x180079c68  test    byte ptr [rcx+1Ch], 4
0x180079c6c  jz      short loc_180079C83
0x180079c6e  mov     edx, 2Ah ; '*'
0x180079c73  lea     r8, WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids
0x180079c7a  mov     rcx, [rcx+10h]
0x180079c7e  call    WPP_SF_
0x180079c83  call    ?IsSpoolerDlpEnlightenmentEnabledFromEngine@DlpEngineUtils@RealtimeProtection@@YA_NXZ; RealtimeProtection::DlpEngineUtils::IsSpoolerDlpEnlightenmentEnabledFromEngine(void)
0x180079c88  movzx   ebx, al
0x180079c8b  xor     r9d, r9d
0x180079c8e  mov     [rsp+58h+var_28], r9d
0x180079c93  xor     al, al
0x180079c95  test    bl, bl
0x180079c97  jz      short loc_180079CB4
0x180079c99  call    ?UtilsIsSpoolerDlpEnlightened@RealtimeProtection@@YA_NXZ; RealtimeProtection::UtilsIsSpoolerDlpEnlightened(void)
0x180079c9e  test    al, al
0x180079ca0  jz      short loc_180079CAF
0x180079ca2  mov     r9d, 1
0x180079ca8  mov     [rsp+58h+var_28], r9d
0x180079cad  jmp     short loc_180079CB4
0x180079caf  mov     r9d, [rsp+58h+var_28]
0x180079cb4  mov     r8d, ebx
0x180079cb7  movzx   edx, al; wchar_t *
0x180079cba  lea     rcx, aRefreshspooler_0; "RefreshSpoolerEnlightenmentState: Spool"...
0x180079cc1  call    ?MpLogMessageImpl@RealtimeProtection@@YAJPEB_WZZ; RealtimeProtection::MpLogMessageImpl(wchar_t const *,...)
0x180079cc6  mov     [rsp+58h+var_20], 0
0x180079ccf  lea     rdx, [rsp+58h+var_20]
0x180079cd4  lea     rcx, aFeatures_0; "Features"
0x180079cdb  call    cs:__imp_MpConfigOpen
0x180079ce1  mov     ebx, eax
0x180079ce3  mov     rcx, [rsp+58h+var_20]
0x180079ce8  test    eax, eax
0x180079cea  jns     short loc_180079CFE
0x180079cec  test    rcx, rcx
0x180079cef  jz      short loc_180079CF7
0x180079cf1  call    cs:__imp_MpConfigClose
0x180079cf7  mov     eax, ebx
0x180079cf9  jmp     loc_180079DA2
0x180079cfe  lea     rax, [rsp+58h+var_28]
0x180079d03  mov     [rsp+58h+var_38], rax
0x180079d08  mov     r9d, 4
0x180079d0e  lea     r8d, [r9-3]
0x180079d12  lea     rdx, aDlpdisableprin; "DlpDisablePrintDetours"
0x180079d19  call    cs:__imp_MpConfigSetValue
0x180079d1f  mov     ebx, eax
0x180079d21  test    eax, eax
0x180079d23  jns     short loc_180079D56
0x180079d25  mov     rcx, cs:WPP_GLOBAL_Control
0x180079d2c  cmp     rcx, rbp
0x180079d2f  jz      short loc_180079D4F
0x180079d31  test    byte ptr [rcx+1Ch], 1
0x180079d35  jz      short loc_180079D4F
0x180079d37  mov     edx, 2Bh ; '+'
0x180079d3c  mov     r9d, eax
0x180079d3f  lea     r8, WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids
0x180079d46  mov     rcx, [rcx+10h]
0x180079d4a  call    WPP_SF_d
0x180079d4f  mov     rcx, [rsp+58h+var_20]
0x180079d54  jmp     short loc_180079CEC
0x180079d56  xor     r9d, r9d
0x180079d59  cmp     [rsp+58h+var_28], 1
0x180079d5e  setnz   r9b
0x180079d62  inc     r9d
0x180079d65  mov     [rdi+48h], r9d
0x180079d69  mov     rcx, cs:WPP_GLOBAL_Control
0x180079d70  cmp     rcx, rbp
0x180079d73  jz      short loc_180079D90
0x180079d75  test    byte ptr [rcx+1Ch], 4
0x180079d79  jz      short loc_180079D90
0x180079d7b  mov     edx, 2Ch ; ','
0x180079d80  lea     r8, WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids
0x180079d87  mov     rcx, [rcx+10h]
0x180079d8b  call    WPP_SF_d
0x180079d90  mov     rcx, [rsp+58h+var_20]
0x180079d95  test    rcx, rcx
0x180079d98  jz      short loc_180079DA0
0x180079d9a  call    cs:__imp_MpConfigClose
0x180079da0  xor     eax, eax
0x180079da2  mov     rcx, [rsp+58h+var_18]
0x180079da7  xor     rcx, rsp; StackCookie
0x180079daa  call    __security_check_cookie
0x180079daf  mov     rbx, [rsp+58h+arg_8]
0x180079db4  mov     rbp, [rsp+58h+arg_10]
0x180079db9  add     rsp, 50h
0x180079dbd  pop     rdi
0x180079dbe  retn
```
