# RealtimeProtection::DlpEngineUtils::GetClipboardSettingsFromEngine(ulong,ulong &)

- ea: `0x1800bca00`
- end: `0x1800bcca4`
- name: `?GetClipboardSettingsFromEngine@DlpEngineUtils@RealtimeProtection@@YAJKAEAK@Z`
- size: `676`
- prototype: `__int64 __fastcall(RealtimeProtection::DlpEngineUtils *__hidden this, unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18007a790`

## callees

- `0x18003fa60`
- `0x180040290`
- `0x180050300`
- `0x180079dc0`
- `0x18007cdd4`
- `0x1800809d0`
- `0x180089510`
- `0x1800a7df0`
- `0x1800bca00`
- `0x18010cb40`
- `0x1801ab9d4`

## import_xrefs

- `MpClient!MpConfigClose` at `0x1800bcb4b`
- `MpClient!MpConfigClose` at `0x1800bcba8`
- `MpClient!MpConfigClose` at `0x1800bcbe5`
- `MpClient!MpConfigClose` at `0x1800bcb4b`
- `MpClient!MpConfigClose` at `0x1800bcba8`
- `MpClient!MpConfigClose` at `0x1800bcbe5`
- `MpClient!MpConfigOpen` at `0x1800bcae9`
- `MpClient!MpConfigOpen` at `0x1800bcb6d`
- `MpClient!MpConfigOpen` at `0x1800bcae9`
- `MpClient!MpConfigOpen` at `0x1800bcb6d`

## string_xrefs

- `0x1800bcb66`: `Miscellaneous Configuration`

## pseudocode

```c
__int64 __fastcall RealtimeProtection::DlpEngineUtils::GetClipboardSettingsFromEngine(
        RealtimeProtection::DlpEngineUtils *this,
        struct RealtimeProtection::DlpCEngine **a2,
        unsigned int *a3)
{
  CommonUtil::CRefObject *v4; // rbx
  int v5; // eax
  int v6; // eax
  __int64 v7; // rdx
  __int64 v8; // r8
  __int64 v9; // r9
  int v10; // eax
  __int64 v11; // rdx
  __int64 v12; // r8
  __int64 v13; // r9
  unsigned int v14; // ebx
  __int64 v16; // rdx
  __int64 v17; // r8
  __int64 v18; // r9
  const wchar_t *v19; // rdx
  int ClipboardDataEventPublished; // esi
  unsigned int v21; // ebx
  _BYTE v22[4]; // [rsp+20h] [rbp-20h] BYREF
  unsigned int v23; // [rsp+24h] [rbp-1Ch] BYREF
  CommonUtil::CRefObject *v24; // [rsp+28h] [rbp-18h] BYREF

  *(_DWORD *)a2 = (_DWORD)this;
  v24 = 0;
  RealtimeProtection::DlpPlugin::GetEngine((RealtimeProtection::DlpPlugin *)&v24, a2);
  v4 = v24;
  if ( v24 )
  {
    v23 = 0;
    v5 = RealtimeProtection::DlpCEngine::QueryEngineSettings(v24, L"MpDlpClipboardSettings", &v23);
    if ( v5 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          108,
          &WPP_3f83082974eb3d6f01ade477a19bf757_Traceguids,
          (unsigned int)v5);
    }
    else
    {
      *(_DWORD *)a2 = v23;
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_12;
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 109, &WPP_3f83082974eb3d6f01ade477a19bf757_Traceguids);
  }
  if ( v4 )
    CommonUtil::CRefObject::Release(v4);
LABEL_12:
  v24 = 0;
  v6 = MpConfigOpen(L"Features", &v24);
  if ( v6 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        110,
        &WPP_3f83082974eb3d6f01ade477a19bf757_Traceguids,
        (unsigned int)v6);
  }
  else
  {
    v23 = 0;
    if ( (int)MpConfigGetValueDword(v24, L"DlpClipboardSettings", &v23, 0) >= 0 )
      *(_DWORD *)a2 = v23;
  }
  if ( v24 )
    MpConfigClose(v24, v7, v8, v9);
  if ( (*(_BYTE *)a2 & 4) != 0 )
  {
    v24 = 0;
    v10 = MpConfigOpen(L"Miscellaneous Configuration", &v24);
    v14 = v10;
    if ( v10 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          111,
          &WPP_3f83082974eb3d6f01ade477a19bf757_Traceguids,
          (unsigned int)v10);
      if ( v24 )
        MpConfigClose(v24, v11, v12, v13);
      return v14;
    }
    v23 = 0;
    if ( (int)MpConfigGetValueDword(v24, L"DlpClipboardSettings", &v23, 0) >= 0 )
      *(_DWORD *)a2 = v23;
    if ( v24 )
      MpConfigClose(v24, v16, v17, v18);
  }
  if ( (*(_BYTE *)a2 & 2) != 0 )
  {
    v22[0] = 0;
    if ( (*(_DWORD *)a2 & 0x200) != 0 )
    {
      RealtimeProtection::MpLogMessageImpl(
        (RealtimeProtection *)L"Skipping IsGetClipboardDataEventPublished by signature, settings = %lu",
        (const wchar_t *)*(unsigned int *)a2);
    }
    else
    {
      ClipboardDataEventPublished = anonymous_namespace_::IsGetClipboardDataEventPublished(v22);
      v21 = v22[0];
      if ( ClipboardDataEventPublished < 0 || !v22[0] )
      {
        if ( (unsigned int)RealtimeProtection::DlpUtils::DlpMpLookupMiscConfigFlag(
                             (RealtimeProtection::DlpUtils *)L"MpDlp_ForceBlockOnPaste",
                             v19) )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 112, &WPP_3f83082974eb3d6f01ade477a19bf757_Traceguids);
        }
        else
        {
          RealtimeProtection::MpLogMessageImpl(
            (RealtimeProtection *)L"Deactivating DlpClipboard_EnforceOnPaste in global clipboard settings. old settings = "
                                   "%lu, hr=%#lx, isEventPublished=%d.",
            (const wchar_t *)*(unsigned int *)a2,
            (unsigned int)ClipboardDataEventPublished,
            v21);
          *(_DWORD *)a2 &= ~2u;
        }
      }
    }
  }
  RealtimeProtection::MpLogMessageImpl(
    (RealtimeProtection *)L"Global clipboard settings after evaluation is %lu",
    (const wchar_t *)*(unsigned int *)a2);
  return 0;
}

```

## disassembly

```asm
0x1800bca00  mov     [rsp-18h+arg_0], rbx
0x1800bca05  mov     [rsp-18h+arg_10], rsi
0x1800bca0a  mov     [rsp-18h+arg_18], rdi
0x1800bca0f  push    rbp
0x1800bca10  push    r12
0x1800bca12  push    r15
0x1800bca14  mov     rbp, rsp
0x1800bca17  sub     rsp, 40h
0x1800bca1b  mov     rax, cs:__security_cookie
0x1800bca22  xor     rax, rsp
0x1800bca25  mov     [rbp+var_10], rax
0x1800bca29  mov     rdi, rdx
0x1800bca2c  mov     [rdx], ecx
0x1800bca2e  mov     [rbp+var_18], 0
0x1800bca36  lea     rcx, [rbp+var_18]; this
0x1800bca3a  call    ?GetEngine@DlpPlugin@RealtimeProtection@@YAXPEAPEAVDlpCEngine@2@@Z; RealtimeProtection::DlpPlugin::GetEngine(RealtimeProtection::DlpCEngine * *)
0x1800bca3f  mov     sil, 1
0x1800bca42  lea     r12, WPP_3f83082974eb3d6f01ade477a19bf757_Traceguids
0x1800bca49  lea     r15, WPP_GLOBAL_Control
0x1800bca50  mov     rbx, [rbp+var_18]
0x1800bca54  test    rbx, rbx
0x1800bca57  jz      short loc_1800BCAA6
0x1800bca59  mov     [rbp+var_1C], 0
0x1800bca60  lea     r8, [rbp+var_1C]; unsigned int *
0x1800bca64  lea     rdx, aMpdlpclipboard; "MpDlpClipboardSettings"
0x1800bca6b  mov     rcx, rbx; this
0x1800bca6e  call    ?QueryEngineSettings@DlpCEngine@RealtimeProtection@@AEAAJPEB_WPEAK@Z; RealtimeProtection::DlpCEngine::QueryEngineSettings(wchar_t const *,ulong *)
0x1800bca73  test    eax, eax
0x1800bca75  js      short loc_1800BCA7E
0x1800bca77  mov     eax, [rbp+var_1C]
0x1800bca7a  mov     [rdi], eax
0x1800bca7c  jmp     short loc_1800BCAC9
0x1800bca7e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bca85  cmp     rcx, r15
0x1800bca88  jz      short loc_1800BCAC9
0x1800bca8a  test    [rcx+1Ch], sil
0x1800bca8e  jz      short loc_1800BCAC9
0x1800bca90  mov     edx, 6Ch ; 'l'
0x1800bca95  mov     r9d, eax
0x1800bca98  mov     r8, r12
0x1800bca9b  mov     rcx, [rcx+10h]
0x1800bca9f  call    WPP_SF_d
0x1800bcaa4  jmp     short loc_1800BCAC9
0x1800bcaa6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bcaad  cmp     rcx, r15
0x1800bcab0  jz      short loc_1800BCAD6
0x1800bcab2  test    byte ptr [rcx+1Ch], 2
0x1800bcab6  jz      short loc_1800BCAD6
0x1800bcab8  mov     edx, 6Dh ; 'm'
0x1800bcabd  mov     r8, r12
0x1800bcac0  mov     rcx, [rcx+10h]
0x1800bcac4  call    WPP_SF_
0x1800bcac9  test    rbx, rbx
0x1800bcacc  jz      short loc_1800BCAD6
0x1800bcace  mov     rcx, rbx; this
0x1800bcad1  call    ?Release@CRefObject@CommonUtil@@QEBAJXZ; CommonUtil::CRefObject::Release(void)
0x1800bcad6  mov     [rbp+var_18], 0
0x1800bcade  lea     rdx, [rbp+var_18]
0x1800bcae2  lea     rcx, aFeatures_0; "Features"
0x1800bcae9  call    cs:__imp_MpConfigOpen
0x1800bcaef  test    eax, eax
0x1800bcaf1  js      short loc_1800BCB1C
0x1800bcaf3  mov     [rbp+var_1C], 0
0x1800bcafa  xor     r9d, r9d
0x1800bcafd  lea     r8, [rbp+var_1C]
0x1800bcb01  lea     rdx, aDlpclipboardse; "DlpClipboardSettings"
0x1800bcb08  mov     rcx, [rbp+var_18]
0x1800bcb0c  call    MpConfigGetValueDword
0x1800bcb11  test    eax, eax
0x1800bcb13  js      short loc_1800BCB42
0x1800bcb15  mov     eax, [rbp+var_1C]
0x1800bcb18  mov     [rdi], eax
0x1800bcb1a  jmp     short loc_1800BCB42
0x1800bcb1c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bcb23  cmp     rcx, r15
0x1800bcb26  jz      short loc_1800BCB42
0x1800bcb28  test    [rcx+1Ch], sil
0x1800bcb2c  jz      short loc_1800BCB42
0x1800bcb2e  mov     edx, 6Eh ; 'n'
0x1800bcb33  mov     r9d, eax
0x1800bcb36  mov     r8, r12
0x1800bcb39  mov     rcx, [rcx+10h]
0x1800bcb3d  call    WPP_SF_d
0x1800bcb42  mov     rcx, [rbp+var_18]
0x1800bcb46  test    rcx, rcx
0x1800bcb49  jz      short loc_1800BCB51
0x1800bcb4b  call    cs:__imp_MpConfigClose
0x1800bcb51  test    byte ptr [rdi], 4
0x1800bcb54  jz      loc_1800BCBEB
0x1800bcb5a  mov     [rbp+var_18], 0
0x1800bcb62  lea     rdx, [rbp+var_18]
0x1800bcb66  lea     rcx, aMiscellaneousC_0; "Miscellaneous Configuration"
0x1800bcb6d  call    cs:__imp_MpConfigOpen
0x1800bcb73  mov     ebx, eax
0x1800bcb75  test    eax, eax
0x1800bcb77  jns     short loc_1800BCBB5
0x1800bcb79  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bcb80  cmp     rcx, r15
0x1800bcb83  jz      short loc_1800BCB9F
0x1800bcb85  test    [rcx+1Ch], sil
0x1800bcb89  jz      short loc_1800BCB9F
0x1800bcb8b  mov     edx, 6Fh ; 'o'
0x1800bcb90  mov     r9d, eax
0x1800bcb93  mov     r8, r12
0x1800bcb96  mov     rcx, [rcx+10h]
0x1800bcb9a  call    WPP_SF_d
0x1800bcb9f  mov     rcx, [rbp+var_18]
0x1800bcba3  test    rcx, rcx
0x1800bcba6  jz      short loc_1800BCBAE
0x1800bcba8  call    cs:__imp_MpConfigClose
0x1800bcbae  mov     eax, ebx
0x1800bcbb0  jmp     loc_1800BCC7F
0x1800bcbb5  mov     [rbp+var_1C], 0
0x1800bcbbc  xor     r9d, r9d
0x1800bcbbf  lea     r8, [rbp+var_1C]
0x1800bcbc3  lea     rdx, aDlpclipboardse; "DlpClipboardSettings"
0x1800bcbca  mov     rcx, [rbp+var_18]
0x1800bcbce  call    MpConfigGetValueDword
0x1800bcbd3  test    eax, eax
0x1800bcbd5  js      short loc_1800BCBDC
0x1800bcbd7  mov     eax, [rbp+var_1C]
0x1800bcbda  mov     [rdi], eax
0x1800bcbdc  mov     rcx, [rbp+var_18]
0x1800bcbe0  test    rcx, rcx
0x1800bcbe3  jz      short loc_1800BCBEB
0x1800bcbe5  call    cs:__imp_MpConfigClose
0x1800bcbeb  test    byte ptr [rdi], 2
0x1800bcbee  jz      short loc_1800BCC6F
0x1800bcbf0  mov     [rbp+var_20], 0
0x1800bcbf4  test    dword ptr [rdi], 200h
0x1800bcbfa  jz      short loc_1800BCC0C
0x1800bcbfc  mov     edx, [rdi]; wchar_t *
0x1800bcbfe  lea     rcx, aSkippingIsgetc; "Skipping IsGetClipboardDataEventPublish"...
0x1800bcc05  call    ?MpLogMessageImpl@RealtimeProtection@@YAJPEB_WZZ; RealtimeProtection::MpLogMessageImpl(wchar_t const *,...)
0x1800bcc0a  jmp     short loc_1800BCC6F
0x1800bcc0c  lea     rcx, [rbp+var_20]
0x1800bcc10  call    _anonymous_namespace___IsGetClipboardDataEventPublished
0x1800bcc15  mov     esi, eax
0x1800bcc17  movzx   ebx, [rbp+var_20]
0x1800bcc1b  test    eax, eax
0x1800bcc1d  js      short loc_1800BCC23
0x1800bcc1f  test    bl, bl
0x1800bcc21  jnz     short loc_1800BCC6F
0x1800bcc23  lea     rcx, aMpdlpForcebloc; "MpDlp_ForceBlockOnPaste"
0x1800bcc2a  call    ?DlpMpLookupMiscConfigFlag@DlpUtils@RealtimeProtection@@YAHPEB_W@Z; RealtimeProtection::DlpUtils::DlpMpLookupMiscConfigFlag(wchar_t const *)
0x1800bcc2f  test    eax, eax
0x1800bcc31  jnz     short loc_1800BCC4C
0x1800bcc33  mov     r9d, ebx
0x1800bcc36  mov     r8d, esi
0x1800bcc39  mov     edx, [rdi]; wchar_t *
0x1800bcc3b  lea     rcx, aDeactivatingDl; "Deactivating DlpClipboard_EnforceOnPast"...
0x1800bcc42  call    ?MpLogMessageImpl@RealtimeProtection@@YAJPEB_WZZ; RealtimeProtection::MpLogMessageImpl(wchar_t const *,...)
0x1800bcc47  and     dword ptr [rdi], 0FFFFFFFDh
0x1800bcc4a  jmp     short loc_1800BCC6F
0x1800bcc4c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bcc53  cmp     rcx, r15
0x1800bcc56  jz      short loc_1800BCC6F
0x1800bcc58  test    byte ptr [rcx+1Ch], 4
0x1800bcc5c  jz      short loc_1800BCC6F
0x1800bcc5e  mov     edx, 70h ; 'p'
0x1800bcc63  mov     r8, r12
0x1800bcc66  mov     rcx, [rcx+10h]
0x1800bcc6a  call    WPP_SF_
0x1800bcc6f  mov     edx, [rdi]; wchar_t *
0x1800bcc71  lea     rcx, aGlobalClipboar; "Global clipboard settings after evaluat"...
0x1800bcc78  call    ?MpLogMessageImpl@RealtimeProtection@@YAJPEB_WZZ; RealtimeProtection::MpLogMessageImpl(wchar_t const *,...)
0x1800bcc7d  xor     eax, eax
0x1800bcc7f  mov     rcx, [rbp+var_10]
0x1800bcc83  xor     rcx, rsp; StackCookie
0x1800bcc86  call    __security_check_cookie
0x1800bcc8b  mov     rbx, [rsp+40h+arg_0]
0x1800bcc90  mov     rsi, [rsp+40h+arg_10]
0x1800bcc95  mov     rdi, [rsp+40h+arg_18]
0x1800bcc9a  add     rsp, 40h
0x1800bcc9e  pop     r15
0x1800bcca0  pop     r12
0x1800bcca2  pop     rbp
0x1800bcca3  retn
```
