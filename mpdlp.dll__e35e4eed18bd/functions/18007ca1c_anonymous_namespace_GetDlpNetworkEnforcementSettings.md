# _anonymous_namespace_::GetDlpNetworkEnforcementSettings

- ea: `0x18007ca1c`
- end: `0x18007cce8`
- name: `_anonymous_namespace_::GetDlpNetworkEnforcementSettings`
- size: `716`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18007c40c`

## callees

- `0x18003fa60`
- `0x180040290`
- `0x18007ca1c`
- `0x18007cdd4`
- `0x180080030`
- `0x1800809d0`
- `0x180089510`
- `0x1800a7df0`
- `0x18010cb40`

## import_xrefs

- `MpClient!MpConfigGetValue` at `0x18007cab2`
- `MpClient!MpConfigGetValue` at `0x18007cab2`
- `MpClient!MpConfigClose` at `0x18007cc54`
- `MpClient!MpConfigClose` at `0x18007ccbc`
- `MpClient!MpConfigClose` at `0x18007cc54`
- `MpClient!MpConfigClose` at `0x18007ccbc`
- `MpClient!MpConfigOpen` at `0x18007ca61`
- `MpClient!MpConfigOpen` at `0x18007cba6`
- `MpClient!MpConfigOpen` at `0x18007ca61`
- `MpClient!MpConfigOpen` at `0x18007cba6`

## string_xrefs

- `0x18007cb9f`: `Miscellaneous Configuration`

## pseudocode

```c
__int64 __fastcall anonymous_namespace_::GetDlpNetworkEnforcementSettings(char *a1)
{
  bool v2; // r15
  __int64 result; // rax
  struct RealtimeProtection::DlpCEngine **v4; // rdx
  __int64 v5; // r8
  __int64 v6; // r9
  unsigned int v7; // ebx
  char v8; // di
  CommonUtil::CRefObject *v9; // rbx
  int EngineSettings; // eax
  const wchar_t *v11; // r9
  PVOID *v12; // rcx
  CommonUtil::CRefObject *v13; // [rsp+30h] [rbp-30h] BYREF
  unsigned int v14; // [rsp+38h] [rbp-28h] BYREF
  int v15; // [rsp+3Ch] [rbp-24h] BYREF
  __int64 v16; // [rsp+40h] [rbp-20h] BYREF
  __int64 v17; // [rsp+48h] [rbp-18h] BYREF

  *a1 = 0;
  v16 = 0;
  v2 = 0;
  result = MpConfigOpen(L"Features", &v16);
  v7 = result;
  if ( (int)result < 0 )
  {
    v12 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      goto LABEL_43;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_40;
    result = WPP_SF_d(
               *((_QWORD *)WPP_GLOBAL_Control + 2),
               36,
               &WPP_3f83082974eb3d6f01ade477a19bf757_Traceguids,
               (unsigned int)result);
LABEL_39:
    v12 = (PVOID *)WPP_GLOBAL_Control;
LABEL_40:
    if ( v12 != &WPP_GLOBAL_Control && (*((_BYTE *)v12 + 28) & 2) != 0 )
      result = WPP_SF_d(v12[2], 37, &WPP_3f83082974eb3d6f01ade477a19bf757_Traceguids, v7);
    goto LABEL_43;
  }
  v14 = 0;
  LODWORD(v13) = 0;
  v15 = 4;
  result = ((__int64 (__fastcall *)(__int64, const wchar_t *, unsigned int *, int *, CommonUtil::CRefObject **, _QWORD))MpConfigGetValue)(
             v16,
             L"SenseDlpNetworkEnforcementEnabled",
             &v14,
             &v15,
             &v13,
             0);
  v7 = result;
  if ( (int)result < 0 )
    goto LABEL_39;
  v8 = 1;
  if ( v14 > 1 )
  {
    v7 = -2147023267;
    goto LABEL_39;
  }
  if ( v15 )
    result = (unsigned int)v13;
  else
    result = 0;
  if ( (_DWORD)result != 1 )
    goto LABEL_39;
  v13 = 0;
  RealtimeProtection::DlpPlugin::GetEngine((RealtimeProtection::DlpPlugin *)&v13, v4);
  v9 = v13;
  if ( v13 )
  {
    LODWORD(v13) = 0;
    EngineSettings = RealtimeProtection::DlpCEngine::QueryEngineSettings(
                       v9,
                       L"MpDlpNetworkEnforcementSettings",
                       (unsigned int *)&v13);
    if ( EngineSettings < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          38,
          &WPP_3f83082974eb3d6f01ade477a19bf757_Traceguids,
          (unsigned int)EngineSettings);
    }
    else
    {
      v2 = (_DWORD)v13 == 1;
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_20;
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, &WPP_3f83082974eb3d6f01ade477a19bf757_Traceguids);
  }
  if ( v9 )
    CommonUtil::CRefObject::Release(v9);
LABEL_20:
  v17 = 0;
  result = MpConfigOpen(L"Miscellaneous Configuration", &v17);
  if ( (int)result < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      result = WPP_SF_d(
                 *((_QWORD *)WPP_GLOBAL_Control + 2),
                 40,
                 &WPP_3f83082974eb3d6f01ade477a19bf757_Traceguids,
                 (unsigned int)result);
LABEL_27:
    if ( v2 )
      goto LABEL_29;
    goto LABEL_28;
  }
  LODWORD(v13) = 0;
  result = MpConfigGetValueDword(v17, L"SenseDlpNetworkEnforcementEnabled", &v13, 0);
  if ( (int)result < 0 )
    goto LABEL_27;
  if ( (_DWORD)v13 == 1 )
    goto LABEL_29;
LABEL_28:
  v8 = 0;
LABEL_29:
  *a1 = v8;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    v11 = L"TRUE";
    if ( !v8 )
      v11 = L"FALSE";
    result = WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, &WPP_3f83082974eb3d6f01ade477a19bf757_Traceguids, v11);
  }
  if ( v17 )
    result = MpConfigClose(v17, v4, v5, v6);
LABEL_43:
  if ( v16 )
    return MpConfigClose(v16, v4, v5, v6);
  return result;
}

```

## disassembly

```asm
0x18007ca1c  mov     [rsp-18h+arg_8], rbx
0x18007ca21  mov     [rsp-18h+arg_10], rsi
0x18007ca26  mov     [rsp-18h+arg_18], rdi
0x18007ca2b  push    rbp
0x18007ca2c  push    r12
0x18007ca2e  push    r15
0x18007ca30  mov     rbp, rsp
0x18007ca33  sub     rsp, 60h
0x18007ca37  mov     rax, cs:__security_cookie
0x18007ca3e  xor     rax, rsp
0x18007ca41  mov     [rbp+var_10], rax
0x18007ca45  mov     r12, rcx
0x18007ca48  mov     byte ptr [rcx], 0
0x18007ca4b  lea     rcx, aFeatures_0; "Features"
0x18007ca52  mov     [rbp+var_20], 0
0x18007ca5a  lea     rdx, [rbp+var_20]
0x18007ca5e  xor     r15b, r15b
0x18007ca61  call    cs:__imp_MpConfigOpen
0x18007ca67  lea     rsi, WPP_GLOBAL_Control
0x18007ca6e  mov     ebx, eax
0x18007ca70  test    eax, eax
0x18007ca72  js      loc_18007CC5C
0x18007ca78  mov     rcx, [rbp+var_20]
0x18007ca7c  lea     rax, [rbp+var_30]
0x18007ca80  mov     [rsp+60h+var_38], 0
0x18007ca89  lea     r9, [rbp+var_24]
0x18007ca8d  lea     r8, [rbp+var_28]
0x18007ca91  mov     [rsp+60h+var_40], rax
0x18007ca96  lea     rdx, aSensedlpnetwor; "SenseDlpNetworkEnforcementEnabled"
0x18007ca9d  mov     [rbp+var_28], 0
0x18007caa4  mov     dword ptr [rbp+var_30], 0
0x18007caab  mov     [rbp+var_24], 4
0x18007cab2  call    cs:__imp_MpConfigGetValue
0x18007cab8  mov     ebx, eax
0x18007caba  test    eax, eax
0x18007cabc  js      loc_18007CC89
0x18007cac2  mov     edi, 1
0x18007cac7  cmp     [rbp+var_28], edi
0x18007caca  jbe     short loc_18007CAD6
0x18007cacc  mov     ebx, 8007065Dh
0x18007cad1  jmp     loc_18007CC89
0x18007cad6  cmp     [rbp+var_24], 0
0x18007cada  jnz     short loc_18007CAE0
0x18007cadc  xor     eax, eax
0x18007cade  jmp     short loc_18007CAE3
0x18007cae0  mov     eax, dword ptr [rbp+var_30]
0x18007cae3  cmp     eax, edi
0x18007cae5  jnz     loc_18007CC89
0x18007caeb  lea     rcx, [rbp+var_30]; this
0x18007caef  mov     [rbp+var_30], 0
0x18007caf7  call    ?GetEngine@DlpPlugin@RealtimeProtection@@YAXPEAPEAVDlpCEngine@2@@Z; RealtimeProtection::DlpPlugin::GetEngine(RealtimeProtection::DlpCEngine * *)
0x18007cafc  mov     rbx, [rbp+var_30]
0x18007cb00  lea     rsi, WPP_GLOBAL_Control
0x18007cb07  test    rbx, rbx
0x18007cb0a  jz      short loc_18007CB5F
0x18007cb0c  lea     r8, [rbp+var_30]; unsigned int *
0x18007cb10  mov     dword ptr [rbp+var_30], 0
0x18007cb17  lea     rdx, aMpdlpnetworken; "MpDlpNetworkEnforcementSettings"
0x18007cb1e  mov     rcx, rbx; this
0x18007cb21  call    ?QueryEngineSettings@DlpCEngine@RealtimeProtection@@AEAAJPEB_WPEAK@Z; RealtimeProtection::DlpCEngine::QueryEngineSettings(wchar_t const *,ulong *)
0x18007cb26  test    eax, eax
0x18007cb28  js      short loc_18007CB33
0x18007cb2a  cmp     dword ptr [rbp+var_30], edi
0x18007cb2d  setz    r15b
0x18007cb31  jmp     short loc_18007CB86
0x18007cb33  mov     rcx, cs:WPP_GLOBAL_Control
0x18007cb3a  cmp     rcx, rsi
0x18007cb3d  jz      short loc_18007CB86
0x18007cb3f  test    [rcx+1Ch], dil
0x18007cb43  jz      short loc_18007CB86
0x18007cb45  mov     rcx, [rcx+10h]
0x18007cb49  lea     r8, WPP_3f83082974eb3d6f01ade477a19bf757_Traceguids
0x18007cb50  mov     edx, 26h ; '&'
0x18007cb55  mov     r9d, eax
0x18007cb58  call    WPP_SF_d
0x18007cb5d  jmp     short loc_18007CB86
0x18007cb5f  mov     rcx, cs:WPP_GLOBAL_Control
0x18007cb66  cmp     rcx, rsi
0x18007cb69  jz      short loc_18007CB93
0x18007cb6b  test    byte ptr [rcx+1Ch], 2
0x18007cb6f  jz      short loc_18007CB93
0x18007cb71  mov     rcx, [rcx+10h]
0x18007cb75  lea     r8, WPP_3f83082974eb3d6f01ade477a19bf757_Traceguids
0x18007cb7c  mov     edx, 27h ; '''
0x18007cb81  call    WPP_SF_
0x18007cb86  test    rbx, rbx
0x18007cb89  jz      short loc_18007CB93
0x18007cb8b  mov     rcx, rbx; this
0x18007cb8e  call    ?Release@CRefObject@CommonUtil@@QEBAJXZ; CommonUtil::CRefObject::Release(void)
0x18007cb93  lea     rdx, [rbp+var_18]
0x18007cb97  mov     [rbp+var_18], 0
0x18007cb9f  lea     rcx, aMiscellaneousC_0; "Miscellaneous Configuration"
0x18007cba6  call    cs:__imp_MpConfigOpen
0x18007cbac  test    eax, eax
0x18007cbae  js      short loc_18007CBD9
0x18007cbb0  mov     rcx, [rbp+var_18]
0x18007cbb4  lea     r8, [rbp+var_30]
0x18007cbb8  xor     r9d, r9d
0x18007cbbb  mov     dword ptr [rbp+var_30], 0
0x18007cbc2  lea     rdx, aSensedlpnetwor; "SenseDlpNetworkEnforcementEnabled"
0x18007cbc9  call    MpConfigGetValueDword
0x18007cbce  test    eax, eax
0x18007cbd0  js      short loc_18007CC03
0x18007cbd2  cmp     dword ptr [rbp+var_30], edi
0x18007cbd5  jz      short loc_18007CC0B
0x18007cbd7  jmp     short loc_18007CC08
0x18007cbd9  mov     rcx, cs:WPP_GLOBAL_Control
0x18007cbe0  cmp     rcx, rsi
0x18007cbe3  jz      short loc_18007CC03
0x18007cbe5  test    [rcx+1Ch], dil
0x18007cbe9  jz      short loc_18007CC03
0x18007cbeb  mov     rcx, [rcx+10h]
0x18007cbef  lea     r8, WPP_3f83082974eb3d6f01ade477a19bf757_Traceguids
0x18007cbf6  mov     edx, 28h ; '('
0x18007cbfb  mov     r9d, eax
0x18007cbfe  call    WPP_SF_d
0x18007cc03  test    r15b, r15b
0x18007cc06  jnz     short loc_18007CC0B
0x18007cc08  xor     dil, dil
0x18007cc0b  mov     [r12], dil
0x18007cc0f  mov     rcx, cs:WPP_GLOBAL_Control
0x18007cc16  cmp     rcx, rsi
0x18007cc19  jz      short loc_18007CC4B
0x18007cc1b  test    byte ptr [rcx+1Ch], 4
0x18007cc1f  jz      short loc_18007CC4B
0x18007cc21  mov     rcx, [rcx+10h]
0x18007cc25  lea     rax, aFalse_1; "FALSE"
0x18007cc2c  test    dil, dil
0x18007cc2f  lea     r9, aTrue_1; "TRUE"
0x18007cc36  mov     edx, 29h ; ')'
0x18007cc3b  lea     r8, WPP_3f83082974eb3d6f01ade477a19bf757_Traceguids
0x18007cc42  cmovz   r9, rax
0x18007cc46  call    WPP_SF_S
0x18007cc4b  mov     rcx, [rbp+var_18]
0x18007cc4f  test    rcx, rcx
0x18007cc52  jz      short loc_18007CCB3
0x18007cc54  call    cs:__imp_MpConfigClose
0x18007cc5a  jmp     short loc_18007CCB3
0x18007cc5c  mov     rcx, cs:WPP_GLOBAL_Control
0x18007cc63  cmp     rcx, rsi
0x18007cc66  jz      short loc_18007CCB3
0x18007cc68  mov     edi, 1
0x18007cc6d  test    [rcx+1Ch], dil
0x18007cc71  jz      short loc_18007CC90
0x18007cc73  mov     rcx, [rcx+10h]
0x18007cc77  lea     edx, [rdi+23h]
0x18007cc7a  mov     r9d, eax
0x18007cc7d  lea     r8, WPP_3f83082974eb3d6f01ade477a19bf757_Traceguids
0x18007cc84  call    WPP_SF_d
0x18007cc89  mov     rcx, cs:WPP_GLOBAL_Control
0x18007cc90  cmp     rcx, rsi
0x18007cc93  jz      short loc_18007CCB3
0x18007cc95  test    byte ptr [rcx+1Ch], 2
0x18007cc99  jz      short loc_18007CCB3
0x18007cc9b  mov     rcx, [rcx+10h]
0x18007cc9f  lea     r8, WPP_3f83082974eb3d6f01ade477a19bf757_Traceguids
0x18007cca6  mov     edx, 25h ; '%'
0x18007ccab  mov     r9d, ebx
0x18007ccae  call    WPP_SF_d
0x18007ccb3  mov     rcx, [rbp+var_20]
0x18007ccb7  test    rcx, rcx
0x18007ccba  jz      short loc_18007CCC2
0x18007ccbc  call    cs:__imp_MpConfigClose
0x18007ccc2  mov     rcx, [rbp+var_10]
0x18007ccc6  xor     rcx, rsp; StackCookie
0x18007ccc9  call    __security_check_cookie
0x18007ccce  lea     r11, [rsp+60h+var_s0]
0x18007ccd3  mov     rbx, [r11+28h]
0x18007ccd7  mov     rsi, [r11+30h]
0x18007ccdb  mov     rdi, [r11+38h]
0x18007ccdf  mov     rsp, r11
0x18007cce2  pop     r15
0x18007cce4  pop     r12
0x18007cce6  pop     rbp
0x18007cce7  retn
```
