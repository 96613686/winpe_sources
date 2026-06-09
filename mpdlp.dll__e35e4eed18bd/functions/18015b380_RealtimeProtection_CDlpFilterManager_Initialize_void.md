# RealtimeProtection::CDlpFilterManager::Initialize(void)

- ea: `0x18015b380`
- end: `0x18015b66b`
- name: `?Initialize@CDlpFilterManager@RealtimeProtection@@UEAAXXZ`
- size: `747`
- prototype: `void __fastcall(RealtimeProtection::CDlpFilterManager *__hidden this)`
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180050300`
- `0x180079dc0`
- `0x1800809d0`
- `0x180090c70`
- `0x1800a7df0`
- `0x18010164c`
- `0x18010cb40`
- `0x180141590`
- `0x18015b380`
- `0x18015ecdc`
- `0x1801cfbf8`
- `0x18023a290`

## import_xrefs

- `MpClient!MpConfigClose` at `0x18015b3de`
- `MpClient!MpConfigClose` at `0x18015b52c`
- `MpClient!MpConfigClose` at `0x18015b63f`
- `MpClient!MpConfigClose` at `0x18015b3de`
- `MpClient!MpConfigClose` at `0x18015b52c`
- `MpClient!MpConfigClose` at `0x18015b63f`
- `MpClient!MpConfigOpen` at `0x18015b3f7`
- `MpClient!MpConfigOpen` at `0x18015b4b6`
- `MpClient!MpConfigOpen` at `0x18015b3f7`
- `MpClient!MpConfigOpen` at `0x18015b4b6`
- `KERNEL32!DebugBreak` at `0x18015b3c4`
- `KERNEL32!DebugBreak` at `0x18015b3c4`

## string_xrefs

- `0x18015b47d`: `MpDlpService.exe`
- `0x18015b43d`: `AVOnAccessScanErrorRetryCount`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall RealtimeProtection::CDlpFilterManager::Initialize(
        RealtimeProtection::CDlpFilterManager *this,
        const wchar_t *a2)
{
  __int64 v3; // rdx
  __int64 v4; // r8
  __int64 v5; // r9
  int v6; // eax
  const wchar_t *v7; // r8
  int ValueDword; // eax
  _BYTE *v9; // rbx
  __int64 v10; // rdx
  __int64 v11; // r8
  __int64 v12; // r9
  int v13; // eax
  int v14; // eax
  int v15; // eax
  RealtimeProtection::DlpDriverMessageHangDetector *v16; // rcx
  unsigned int v17; // esi
  wchar_t *v18; // rsi
  int v19; // eax
  unsigned int v20; // ebx
  PVOID v21; // rcx
  int Instance; // eax
  __int64 v23; // rdx
  __int64 v24; // r8
  __int64 v25; // r9
  int v26; // [rsp+30h] [rbp-20h] BYREF
  _BYTE v27[4]; // [rsp+34h] [rbp-1Ch] BYREF
  __int64 v28; // [rsp+38h] [rbp-18h] BYREF
  __int64 v29; // [rsp+40h] [rbp-10h] BYREF

  v28 = 0;
  if ( (unsigned int)RealtimeProtection::DlpUtils::DlpMpLookupMiscConfigFlag(
                       (RealtimeProtection::DlpUtils *)L"MpDlp_DebugFilterManager",
                       a2) )
    DebugBreak();
  *((_DWORD *)this + 26) = 1000;
  if ( v28 )
  {
    MpConfigClose(v28, v3, v4, v5);
    v28 = 0;
  }
  v6 = MpConfigOpen(L"Real-Time Protection", &v28);
  if ( v6 >= 0 )
  {
    ValueDword = MpConfigGetValueDword(v28, L"AVOnAccessScanErrorRetryCount", (char *)this + 104, 0);
    if ( ValueDword < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          11,
          WPP_19e9d8669cc731dcf661e21f97af2bd4_Traceguids,
          (unsigned int)ValueDword);
      *((_DWORD *)this + 26) = 1000;
    }
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_19e9d8669cc731dcf661e21f97af2bd4_Traceguids, (unsigned int)v6);
  }
  v27[0] = 0;
  if ( CommonUtil::UtilIsHostedInExe((CommonUtil *)v27, (bool *)L"MpDlpService.exe", v7) >= 0 && v27[0] )
  {
    v9 = (char *)this + 108;
    *((_BYTE *)this + 108) = 0;
  }
  else
  {
    v29 = 0;
    if ( (int)MpConfigOpen(L"Features", &v29) >= 0 )
    {
      v26 = 0;
      v13 = MpConfigGetValueDword(v29, L"DlpDisableKernelPort", &v26, 0);
      if ( v13 >= 0 )
      {
        v14 = v26;
      }
      else
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            12,
            WPP_19e9d8669cc731dcf661e21f97af2bd4_Traceguids,
            (unsigned int)v13);
        v14 = 1;
      }
      v9 = (char *)this + 108;
      *((_BYTE *)this + 108) = v14 != 0;
    }
    else
    {
      v9 = (char *)this + 108;
    }
    if ( v29 )
      MpConfigClose(v29, v10, v11, v12);
  }
  v15 = (*(__int64 (__fastcall **)(RealtimeProtection::CDlpFilterManager *, const wchar_t *, const wchar_t *, __int64))(*(_QWORD *)this + 8LL))(
          this,
          L"WdFilter",
          L"\\MicrosoftDataLossPreventionControlPort",
          2);
  v17 = v15;
  if ( v15 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        13,
        WPP_19e9d8669cc731dcf661e21f97af2bd4_Traceguids,
        (unsigned int)v15);
    RealtimeProtection::MpLogMessageImpl(
      (RealtimeProtection *)L"[DLP] Failed to load filter. hr: %!HRESULT!",
      (const wchar_t *)v17);
  }
  if ( !*v9 )
  {
    v18 = (wchar_t *)*((_QWORD *)this + 10);
    v19 = std::streambuf::sync(v18 + 204);
    v20 = v19;
    if ( v19 < 0 )
    {
      v21 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          10,
          WPP_d35c89b3c91e3489af9e88b19891e994_Traceguids,
          (unsigned int)v19);
      CommonUtil::CCommonThrowHR::operator=(v21, v20);
    }
    RealtimeProtection::CFilterCommunicatorBase::Initialize(v18, L"\\MicrosoftDataLossPreventionAsyncPort", 0);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)(*((_QWORD *)this + 12) + 408LL) + 8LL))(*((_QWORD *)this + 12) + 408LL);
  }
  Instance = RealtimeProtection::DlpDriverMessageHangDetector::CreateInstance(v16);
  if ( Instance < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      14,
      WPP_19e9d8669cc731dcf661e21f97af2bd4_Traceguids,
      (unsigned int)Instance);
  if ( v28 )
    MpConfigClose(v28, v23, v24, v25);
}

```

## disassembly

```asm
0x18015b380  mov     [rsp-18h+arg_8], rbx
0x18015b385  mov     [rsp-18h+arg_10], rsi
0x18015b38a  mov     [rsp-18h+arg_18], rdi
0x18015b38f  push    rbp
0x18015b390  push    r12
0x18015b392  push    r13
0x18015b394  mov     rbp, rsp
0x18015b397  sub     rsp, 50h
0x18015b39b  mov     rax, cs:__security_cookie
0x18015b3a2  xor     rax, rsp
0x18015b3a5  mov     [rbp+var_8], rax
0x18015b3a9  mov     rdi, rcx
0x18015b3ac  mov     [rbp+var_18], 0
0x18015b3b4  lea     rcx, aMpdlpDebugfilt; "MpDlp_DebugFilterManager"
0x18015b3bb  call    ?DlpMpLookupMiscConfigFlag@DlpUtils@RealtimeProtection@@YAHPEB_W@Z; RealtimeProtection::DlpUtils::DlpMpLookupMiscConfigFlag(wchar_t const *)
0x18015b3c0  test    eax, eax
0x18015b3c2  jz      short loc_18015B3CA
0x18015b3c4  call    cs:__imp_DebugBreak
0x18015b3ca  lea     rbx, [rdi+68h]
0x18015b3ce  mov     esi, 3E8h
0x18015b3d3  mov     [rbx], esi
0x18015b3d5  mov     rcx, [rbp+var_18]
0x18015b3d9  test    rcx, rcx
0x18015b3dc  jz      short loc_18015B3EC
0x18015b3de  call    cs:__imp_MpConfigClose
0x18015b3e4  mov     [rbp+var_18], 0
0x18015b3ec  lea     rdx, [rbp+var_18]
0x18015b3f0  lea     rcx, aRealTimeProtec; "Real-Time Protection"
0x18015b3f7  call    cs:__imp_MpConfigOpen
0x18015b3fd  lea     r13, WPP_19e9d8669cc731dcf661e21f97af2bd4_Traceguids
0x18015b404  lea     r12, WPP_GLOBAL_Control
0x18015b40b  test    eax, eax
0x18015b40d  jns     short loc_18015B437
0x18015b40f  mov     rcx, cs:WPP_GLOBAL_Control
0x18015b416  cmp     rcx, r12
0x18015b419  jz      short loc_18015B479
0x18015b41b  test    byte ptr [rcx+1Ch], 1
0x18015b41f  jz      short loc_18015B479
0x18015b421  mov     edx, 0Ah
0x18015b426  mov     r9d, eax
0x18015b429  mov     r8, r13
0x18015b42c  mov     rcx, [rcx+10h]
0x18015b430  call    WPP_SF_d
0x18015b435  jmp     short loc_18015B479
0x18015b437  xor     r9d, r9d
0x18015b43a  mov     r8, rbx
0x18015b43d  lea     rdx, aAvonaccessscan; "AVOnAccessScanErrorRetryCount"
0x18015b444  mov     rcx, [rbp+var_18]
0x18015b448  call    MpConfigGetValueDword
0x18015b44d  test    eax, eax
0x18015b44f  jns     short loc_18015B479
0x18015b451  mov     rcx, cs:WPP_GLOBAL_Control
0x18015b458  cmp     rcx, r12
0x18015b45b  jz      short loc_18015B477
0x18015b45d  test    byte ptr [rcx+1Ch], 1
0x18015b461  jz      short loc_18015B477
0x18015b463  mov     edx, 0Bh
0x18015b468  mov     r9d, eax
0x18015b46b  mov     r8, r13
0x18015b46e  mov     rcx, [rcx+10h]
0x18015b472  call    WPP_SF_d
0x18015b477  mov     [rbx], esi
0x18015b479  mov     [rbp+var_1C], 0
0x18015b47d  lea     rdx, aMpdlpserviceEx_0; "MpDlpService.exe"
0x18015b484  lea     rcx, [rbp+var_1C]; this
0x18015b488  call    ?UtilIsHostedInExe@CommonUtil@@YAJPEA_NPEB_W@Z; CommonUtil::UtilIsHostedInExe(bool *,wchar_t const *)
0x18015b48d  test    eax, eax
0x18015b48f  js      short loc_18015B4A3
0x18015b491  cmp     [rbp+var_1C], 0
0x18015b495  jz      short loc_18015B4A3
0x18015b497  lea     rbx, [rdi+6Ch]
0x18015b49b  mov     byte ptr [rbx], 0
0x18015b49e  jmp     loc_18015B532
0x18015b4a3  mov     [rbp+var_10], 0
0x18015b4ab  lea     rdx, [rbp+var_10]
0x18015b4af  lea     rcx, aFeatures_0; "Features"
0x18015b4b6  call    cs:__imp_MpConfigOpen
0x18015b4bc  test    eax, eax
0x18015b4be  jns     short loc_18015B4C6
0x18015b4c0  lea     rbx, [rdi+6Ch]
0x18015b4c4  jmp     short loc_18015B523
0x18015b4c6  mov     [rbp+var_20], 0
0x18015b4cd  xor     r9d, r9d
0x18015b4d0  lea     r8, [rbp+var_20]
0x18015b4d4  lea     rdx, aDlpdisablekern; "DlpDisableKernelPort"
0x18015b4db  mov     rcx, [rbp+var_10]
0x18015b4df  call    MpConfigGetValueDword
0x18015b4e4  test    eax, eax
0x18015b4e6  jns     short loc_18015B515
0x18015b4e8  mov     rcx, cs:WPP_GLOBAL_Control
0x18015b4ef  cmp     rcx, r12
0x18015b4f2  jz      short loc_18015B50E
0x18015b4f4  test    byte ptr [rcx+1Ch], 1
0x18015b4f8  jz      short loc_18015B50E
0x18015b4fa  mov     edx, 0Ch
0x18015b4ff  mov     r9d, eax
0x18015b502  mov     r8, r13
0x18015b505  mov     rcx, [rcx+10h]
0x18015b509  call    WPP_SF_d
0x18015b50e  mov     eax, 1
0x18015b513  jmp     short loc_18015B518
0x18015b515  mov     eax, [rbp+var_20]
0x18015b518  test    eax, eax
0x18015b51a  setnz   al
0x18015b51d  lea     rbx, [rdi+6Ch]
0x18015b521  mov     [rbx], al
0x18015b523  mov     rcx, [rbp+var_10]
0x18015b527  test    rcx, rcx
0x18015b52a  jz      short loc_18015B532
0x18015b52c  call    cs:__imp_MpConfigClose
0x18015b532  mov     rax, [rdi]
0x18015b535  mov     r9d, 2
0x18015b53b  lea     r8, aMicrosoftdatal_1; "\\MicrosoftDataLossPreventionControlPor"...
0x18015b542  lea     rdx, aWdfilter; "WdFilter"
0x18015b549  mov     rcx, rdi
0x18015b54c  mov     rax, [rax+8]
0x18015b550  call    cs:__guard_dispatch_icall_fptr
0x18015b556  mov     esi, eax
0x18015b558  test    eax, eax
0x18015b55a  jns     short loc_18015B590
0x18015b55c  mov     rcx, cs:WPP_GLOBAL_Control
0x18015b563  cmp     rcx, r12
0x18015b566  jz      short loc_18015B582
0x18015b568  test    byte ptr [rcx+1Ch], 1
0x18015b56c  jz      short loc_18015B582
0x18015b56e  mov     edx, 0Dh
0x18015b573  mov     r9d, eax
0x18015b576  mov     r8, r13
0x18015b579  mov     rcx, [rcx+10h]
0x18015b57d  call    WPP_SF_d
0x18015b582  mov     edx, esi; wchar_t *
0x18015b584  lea     rcx, aDlpFailedToLoa; "[DLP] Failed to load filter. hr: %!HRES"...
0x18015b58b  call    ?MpLogMessageImpl@RealtimeProtection@@YAJPEB_WZZ; RealtimeProtection::MpLogMessageImpl(wchar_t const *,...)
0x18015b590  cmp     byte ptr [rbx], 0
0x18015b593  jnz     short loc_18015B606
0x18015b595  mov     rsi, [rdi+50h]
0x18015b599  lea     rcx, [rsi+198h]
0x18015b5a0  call    ?sync@?$basic_streambuf@DU?$char_traits@D@std@@@std@@MEAAHXZ; std::streambuf::sync(void)
0x18015b5a5  mov     ebx, eax
0x18015b5a7  test    eax, eax
0x18015b5a9  jns     short loc_18015B5DC
0x18015b5ab  mov     rcx, cs:WPP_GLOBAL_Control
0x18015b5b2  cmp     rcx, r12
0x18015b5b5  jz      short loc_18015B5D5
0x18015b5b7  test    byte ptr [rcx+1Ch], 1
0x18015b5bb  jz      short loc_18015B5D5
0x18015b5bd  mov     edx, 0Ah
0x18015b5c2  mov     r9d, eax
0x18015b5c5  lea     r8, WPP_d35c89b3c91e3489af9e88b19891e994_Traceguids
0x18015b5cc  mov     rcx, [rcx+10h]
0x18015b5d0  call    WPP_SF_d
0x18015b5d5  mov     edx, ebx
0x18015b5d7  call    ??4CCommonThrowHR@CommonUtil@@QEAAXJ@Z; CommonUtil::CCommonThrowHR::operator=(long)
0x18015b5dc  xor     r8d, r8d; wchar_t *
0x18015b5df  lea     rdx, aMicrosoftdatal_3; "\\MicrosoftDataLossPreventionAsyncPort"
0x18015b5e6  mov     rcx, rsi; this
0x18015b5e9  call    ?Initialize@CFilterCommunicatorBase@RealtimeProtection@@QEAAXPEB_W0@Z; RealtimeProtection::CFilterCommunicatorBase::Initialize(wchar_t const *,wchar_t const *)
0x18015b5ee  mov     rcx, [rdi+60h]
0x18015b5f2  add     rcx, 198h
0x18015b5f9  mov     rax, [rcx]
0x18015b5fc  mov     rax, [rax+8]
0x18015b600  call    cs:__guard_dispatch_icall_fptr
0x18015b606  call    ?CreateInstance@DlpDriverMessageHangDetector@RealtimeProtection@@YAJXZ; RealtimeProtection::DlpDriverMessageHangDetector::CreateInstance(void)
0x18015b60b  test    eax, eax
0x18015b60d  jns     short loc_18015B636
0x18015b60f  mov     rcx, cs:WPP_GLOBAL_Control
0x18015b616  cmp     rcx, r12
0x18015b619  jz      short loc_18015B636
0x18015b61b  test    byte ptr [rcx+1Ch], 1
0x18015b61f  jz      short loc_18015B636
0x18015b621  mov     edx, 0Eh
0x18015b626  mov     r9d, eax
0x18015b629  mov     r8, r13
0x18015b62c  mov     rcx, [rcx+10h]
0x18015b630  call    WPP_SF_d
0x18015b635  nop
0x18015b636  mov     rcx, [rbp+var_18]
0x18015b63a  test    rcx, rcx
0x18015b63d  jz      short loc_18015B645
0x18015b63f  call    cs:__imp_MpConfigClose
0x18015b645  mov     rcx, [rbp+var_8]
0x18015b649  xor     rcx, rsp; StackCookie
0x18015b64c  call    __security_check_cookie
0x18015b651  lea     r11, [rsp+50h+var_s0]
0x18015b656  mov     rbx, [r11+28h]
0x18015b65a  mov     rsi, [r11+30h]
0x18015b65e  mov     rdi, [r11+38h]
0x18015b662  mov     rsp, r11
0x18015b665  pop     r13
0x18015b667  pop     r12
0x18015b669  pop     rbp
0x18015b66a  retn
```
