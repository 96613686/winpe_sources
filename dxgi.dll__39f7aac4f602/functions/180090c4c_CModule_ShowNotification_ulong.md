# CModule::ShowNotification(ulong)

- ea: `0x180090c4c`
- end: `0x1800911e6`
- name: `?ShowNotification@CModule@@QEAAXK@Z`
- size: `1434`
- prototype: `void __fastcall(CModule *__hidden this, unsigned int)`
- caller_count: `2`
- callee_count: `16`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180071814`
- `0x18009d400`

## callees

- `0x18000c6b0`
- `0x180061f40`
- `0x180069768`
- `0x18006bae0`
- `0x180073f4c`
- `0x180075fa0`
- `0x180076f14`
- `0x180076f20`
- `0x180088468`
- `0x18008916c`
- `0x1800893b0`
- `0x1800895dc`
- `0x18008a1ec`
- `0x18008f73c`
- `0x180090b0c`
- `0x180090c4c`

## import_xrefs

- `ntdll!EtwEventRegister` at `0x1800910f7`
- `ntdll!EtwEventRegister` at `0x1800910f7`
- `ntdll!EtwEventWrite` at `0x180091183`
- `ntdll!EtwEventWrite` at `0x180091183`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18009113f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18009113f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180091081`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180091081`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!AssocQueryStringW` at `0x180090d9b`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!AssocQueryStringW` at `0x180090d9b`
- `ext-ms-win-appmodel-shellexecute-l1-1-0!ShellExecuteExW` at `0x180090fb5`
- `ext-ms-win-appmodel-shellexecute-l1-1-0!ShellExecuteExW` at `0x180090fb5`

## string_xrefs

- `0x180090fd7`: `onecoreuap\windows\directx\dxg\dxgi\dll\dxgi.cpp`
- `0x180090cfd`: `Notification already shown`
- `0x180091074`: `GraphicsFeaturesNotificationConfig`
- `0x1800910a2`: `AutoSR notifications disabled by registry`
- `0x180091196`: `Failed to write notification ETW event`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall CModule::ShowNotification(CModule *this, unsigned int a2, __int64 a3, bool a4)
{
  char v4; // si
  unsigned int v5; // edx
  unsigned int v6; // edx
  unsigned int v7; // edx
  unsigned int v8; // edx
  unsigned int v9; // edx
  unsigned int v10; // edx
  unsigned int v11; // edx
  const char *v12; // r8
  unsigned int v13; // edx
  __int64 v14; // rax
  CModule *v15; // rcx
  unsigned int v16; // r8d
  __int64 v17; // rcx
  __int64 v18; // rdx
  const WCHAR *v19; // r8
  HRESULT v20; // eax
  size_t v21; // r8
  __int64 v22; // rcx
  __int64 v23; // rdi
  const wchar_t *v24; // rdx
  HKEY *v25; // rbx
  __int64 v26; // r8
  HKEY *v27; // rcx
  HKEY *v28; // rax
  BOOL v29; // eax
  LSTATUS ValueW; // eax
  CModule *v31; // rcx
  bool v32; // r9
  bool v33; // sf
  int v34; // eax
  CModule *v35; // rcx
  bool v36; // r9
  bool v37; // sf
  const char *v38; // r8
  bool v39; // sf
  DWORD *pcchOut; // [rsp+28h] [rbp-D8h]
  unsigned int v41; // [rsp+40h] [rbp-C0h] BYREF
  DWORD pvData; // [rsp+48h] [rbp-B8h] BYREF
  char v43; // [rsp+4Ch] [rbp-B4h]
  DWORD pcbData[4]; // [rsp+50h] [rbp-B0h] BYREF
  SHELLEXECUTEINFOW pExecInfo; // [rsp+60h] [rbp-A0h] BYREF
  HKEY hkey[2]; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v47; // [rsp+E0h] [rbp-20h]
  unsigned __int64 v48; // [rsp+E8h] [rbp-18h]
  _QWORD v49[2]; // [rsp+F0h] [rbp-10h] BYREF
  _DWORD v50[4]; // [rsp+100h] [rbp+0h] BYREF
  LPCWSTR pszAssoc[4]; // [rsp+110h] [rbp+10h] BYREF
  _QWORD v52[2]; // [rsp+130h] [rbp+30h] BYREF
  WCHAR pszOut[264]; // [rsp+140h] [rbp+40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+398h] [rbp+298h]

  v41 = a2;
  v4 = 0;
  v5 = a2 - 12;
  if ( v5 )
  {
    v6 = v5 - 1;
    if ( v6 )
    {
      v7 = v6 - 1;
      if ( v7 )
      {
        v8 = v7 - 1;
        if ( v8 )
        {
          v9 = v8 - 1;
          if ( v9 )
          {
            v10 = v9 - 1;
            if ( v10 )
            {
              v11 = v10 - 1;
              if ( v11 )
              {
                if ( v11 - 1 >= 2 )
                {
                  v12 = "Unsupported notification type";
                  v13 = -2147024809;
LABEL_10:
                  CModule::RecordJournalImpl(this, v13, v12, a4);
                  return;
                }
              }
            }
          }
        }
      }
      v4 = 1;
    }
  }
  if ( std::_Tree<std::_Tmap_traits<unsigned long,bool,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,bool>>,0>>::_Find<unsigned long>(
         &qword_180109D88,
         &v41) != qword_180109D88 )
  {
    v14 = std::map<unsigned long,bool>::_Try_emplace<unsigned long,>(&qword_180109D88, hkey, &v41);
    this = *(CModule **)v14;
    if ( *(_BYTE *)(*(_QWORD *)v14 + 32LL) == 1 )
    {
      v12 = "Notification already shown";
      v13 = -2147467259;
      goto LABEL_10;
    }
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutoSR_2603>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AutoSR_2603>::GetImpl'::`2'::impl)
    && !CModule::ShouldShowNotification(v15, v41, v16) )
  {
    v12 = "Notification suppressed";
    v13 = 0;
    goto LABEL_10;
  }
  std::wstring::wstring(pszAssoc, L"ms-gamebar");
  LOBYTE(v18) = byte_180109DA0;
  if ( (byte_180109DA0 & 1) == 0 )
  {
    memset_0(pszOut, 0, 0x208u);
    pvData = 260;
    v19 = (const WCHAR *)pszAssoc;
    if ( pszAssoc[3] > (LPCWSTR)7 )
      v19 = pszAssoc[0];
    v20 = AssocQueryStringW(0x1000u, ASSOCSTR_MAX|ASSOCSTR_COMMAND, v19, 0, pszOut, &pvData);
    v18 = (unsigned int)v20 >> 31;
    LOBYTE(v17) = v43 & 0xFD;
    LOBYTE(v18) = v43 & 0xFD | (2 * (v20 >= 0)) | 1;
    byte_180109DA0 = v18;
  }
  if ( (v18 & 2) != 0 && v4 )
  {
    std::operator+<unsigned short>(hkey, pszAssoc);
    v21 = 10;
    switch ( v41 )
    {
      case 0xEu:
        v26 = v47;
        if ( v48 - v47 < 2 )
        {
          std::wstring::_Reallocate_grow_by<_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_,unsigned short const *,unsigned __int64>(
            hkey,
            2);
        }
        else
        {
          v47 += 2;
          v27 = hkey;
          if ( v48 > 7 )
            v27 = (HKEY *)hkey[0];
          *(_DWORD *)((char *)v27 + 2 * v26) = 7209071;
          *((_WORD *)v27 + v26 + 2) = 0;
        }
        break;
      case 0xFu:
        v22 = v47;
        if ( v48 - v47 >= 0xA )
        {
          v23 = v47 + 10;
          v21 = 20;
          v24 = L"resolution";
          goto LABEL_31;
        }
        std::wstring::_Reallocate_grow_by<_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_,unsigned short const *,unsigned __int64>(
          hkey,
          10);
        break;
      case 0x11u:
        v22 = v47;
        if ( v48 - v47 >= 7 )
        {
          v23 = v47 + 7;
          v21 = 14;
          v24 = L"restart";
          goto LABEL_31;
        }
        std::wstring::_Reallocate_grow_by<_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_,unsigned short const *,unsigned __int64>(
          hkey,
          7);
        break;
      case 0x12u:
        v22 = v47;
        if ( v48 - v47 >= 5 )
        {
          v23 = v47 + 5;
          v24 = L"offer";
          goto LABEL_31;
        }
        std::wstring::_Reallocate_grow_by<_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_,unsigned short const *,unsigned __int64>(
          hkey,
          5);
        break;
      default:
        if ( v41 - 19 <= 1 )
        {
          v22 = v47;
          if ( v48 - v47 >= 0xB )
          {
            v23 = v47 + 11;
            v21 = 22;
            v24 = L"unavailable";
LABEL_31:
            v25 = hkey;
            if ( v48 > 7 )
              v25 = (HKEY *)hkey[0];
            v47 = v23;
            memmove_0((char *)v25 + 2 * v22, v24, v21);
            *((_WORD *)v25 + v23) = 0;
            break;
          }
          std::wstring::_Reallocate_grow_by<_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_,unsigned short const *,unsigned __int64>(
            hkey,
            11);
        }
        break;
    }
    memset_0(&pExecInfo, 0, sizeof(pExecInfo));
    *(_QWORD *)&pExecInfo.cbSize = 112;
    pExecInfo.hwnd = 0;
    pExecInfo.lpVerb = L"open";
    v28 = hkey;
    if ( v48 > 7 )
      v28 = (HKEY *)hkey[0];
    pExecInfo.lpFile = (LPCWSTR)v28;
    *(_OWORD *)&pExecInfo.lpParameters = 0;
    pExecInfo.nShow = 10;
    v29 = ShellExecuteExW(&pExecInfo);
    wil::details::in1diag3::Log_GetLastErrorIfFalseMsg(
      retaddr,
      (void *)0xE12,
      (unsigned int)"onecoreuap\\windows\\directx\\dxg\\dxgi\\dll\\dxgi.cpp",
      (const char *)v29,
      (bool)"Failed to activate SR widget",
      (const char *)pcchOut);
    std::wstring::_Tidy_deallocate(hkey);
    LOBYTE(v18) = byte_180109DA0;
  }
  if ( !byte_180109D98 )
  {
    byte_180109D98 = 1;
    word_180109D99 = *(_WORD *)((char *)hkey + 1);
    byte_180109D9B = BYTE3(hkey[0]);
    dword_180109D9C = 0;
    if ( (v18 & 2) != 0 )
    {
      hkey[0] = 0;
      if ( (int)wil::reg::open_unique_key_nothrow(v17, v18, hkey) >= 0 )
      {
        pvData = 0;
        pcbData[0] = 4;
        ValueW = RegGetValueW(hkey[0], 0, L"GraphicsFeaturesNotificationConfig", 0x10u, 0, &pvData, pcbData);
        v33 = ValueW < 0;
        if ( ValueW > 0 )
          v33 = 1;
        if ( !v33 )
        {
          dword_180109D9C = pvData;
          if ( (pvData & 1) != 0 )
            CModule::RecordJournalImpl(v31, 0, "AutoSR notifications disabled by registry", v32);
        }
      }
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(hkey);
    }
  }
  if ( dword_180109D9C && v4 && (dword_180109D9C & 1) != 0 )
    goto LABEL_75;
  if ( qword_180109D80 )
  {
LABEL_71:
    v50[0] = 8;
    v50[1] = v41;
    v50[2] = 0;
    v50[3] = GetCurrentProcessId();
    v52[0] = v50;
    v52[1] = 16;
    v49[0] = 268435459;
    v49[1] = 0x8000000000020000uLL;
    v34 = EtwEventWrite(qword_180109D80, v49, 1, v52);
    v39 = v34 < 0;
    if ( v34 > 0 )
    {
      v34 = (unsigned __int16)v34 | 0x80070000;
      v39 = v34 < 0;
    }
    if ( v39 )
    {
      v38 = "Failed to write notification ETW event";
      goto LABEL_69;
    }
LABEL_75:
    *(_BYTE *)(*(_QWORD *)std::map<unsigned long,bool>::_Try_emplace<unsigned long,>(&qword_180109D88, hkey, &v41) + 32LL) = 1;
    goto LABEL_76;
  }
  qword_180109D80 = 0;
  v34 = EtwEventRegister(WdDiagEtwControlGuid, 0, 0, &qword_180109D80);
  v37 = v34 < 0;
  if ( v34 > 0 )
  {
    v34 = (unsigned __int16)v34 | 0x80070000;
    v37 = v34 < 0;
  }
  if ( !v37 )
  {
    if ( !qword_180109D80 )
      goto LABEL_76;
    goto LABEL_71;
  }
  v38 = "Failed to register WdDiag ETW provider";
LABEL_69:
  CModule::RecordJournalImpl(v35, v34, v38, v36);
LABEL_76:
  std::wstring::_Tidy_deallocate(pszAssoc);
}

```

## disassembly

```asm
0x180090c4c  push    rbp
0x180090c4e  push    rbx
0x180090c4f  push    rsi
0x180090c50  push    rdi
0x180090c51  push    r12
0x180090c53  push    r14
0x180090c55  lea     rbp, [rsp-268h]
0x180090c5d  sub     rsp, 368h
0x180090c64  mov     rax, cs:__security_cookie
0x180090c6b  xor     rax, rsp
0x180090c6e  mov     [rbp+290h+var_40], rax
0x180090c75  mov     [rsp+390h+var_350], edx
0x180090c79  xor     r14d, r14d
0x180090c7c  mov     sil, r14b
0x180090c7f  sub     edx, 0Ch
0x180090c82  jz      short loc_180090CC5
0x180090c84  sub     edx, 1
0x180090c87  jz      short loc_180090CC5
0x180090c89  sub     edx, 1
0x180090c8c  jz      short loc_180090CC2
0x180090c8e  sub     edx, 1
0x180090c91  jz      short loc_180090CC2
0x180090c93  sub     edx, 1
0x180090c96  jz      short loc_180090CC2
0x180090c98  sub     edx, 1
0x180090c9b  jz      short loc_180090CC2
0x180090c9d  sub     edx, 1
0x180090ca0  jz      short loc_180090CC2
0x180090ca2  sub     edx, 1
0x180090ca5  jz      short loc_180090CC2
0x180090ca7  cmp     edx, 1
0x180090caa  jz      short loc_180090CC2
0x180090cac  lea     r8, aUnsupportedNot; "Unsupported notification type"
0x180090cb3  mov     edx, 80070057h; unsigned int
0x180090cb8  call    ?RecordJournalImpl@CModule@@QEAAXIPEBD_N@Z; CModule::RecordJournalImpl(uint,char const *,bool)
0x180090cbd  jmp     loc_1800911C7
0x180090cc2  mov     sil, 1
0x180090cc5  lea     rdx, [rsp+390h+var_350]
0x180090cca  lea     rcx, qword_180109D88
0x180090cd1  call    ??$_Find@K@?$_Tree@V?$_Tmap_traits@K_NU?$less@K@std@@V?$allocator@U?$pair@$$CBK_N@std@@@2@$0A@@std@@@std@@AEBAPEAU?$_Tree_node@U?$pair@$$CBK_N@std@@PEAX@1@AEBK@Z; std::_Tree<std::_Tmap_traits<ulong,bool,std::less<ulong>,std::allocator<std::pair<ulong const,bool>>,0>>::_Find<ulong>(ulong const &)
0x180090cd6  cmp     rax, cs:qword_180109D88
0x180090cdd  jz      short loc_180090D0B
0x180090cdf  lea     r8, [rsp+390h+var_350]
0x180090ce4  lea     rdx, [rbp+290h+hkey]
0x180090ce8  lea     rcx, qword_180109D88
0x180090cef  call    ??$_Try_emplace@K$$V@?$map@K_NU?$less@K@std@@V?$allocator@U?$pair@$$CBK_N@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBK_N@std@@PEAX@std@@_N@1@$$QEAK@Z; std::map<ulong,bool>::_Try_emplace<ulong,>(ulong &&)
0x180090cf4  mov     rcx, [rax]
0x180090cf7  cmp     byte ptr [rcx+20h], 1
0x180090cfb  jnz     short loc_180090D0B
0x180090cfd  lea     r8, aNotificationAl; "Notification already shown"
0x180090d04  mov     edx, 80004005h
0x180090d09  jmp     short loc_180090CB8
0x180090d0b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AutoSR_2603@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AutoSR_2603@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutoSR_2603> `wil::Feature<__WilFeatureTraits_Feature_AutoSR_2603>::GetImpl(void)'::`2'::impl
0x180090d12  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AutoSR_2603@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutoSR_2603>::__private_IsEnabled(void)
0x180090d17  test    al, al
0x180090d19  jz      short loc_180090D33
0x180090d1b  mov     edx, [rsp+390h+var_350]; unsigned int
0x180090d1f  call    ?ShouldShowNotification@CModule@@QEAA_NKK@Z; CModule::ShouldShowNotification(ulong,ulong)
0x180090d24  test    al, al
0x180090d26  jnz     short loc_180090D33
0x180090d28  lea     r8, aNotificationSu; "Notification suppressed"
0x180090d2f  xor     edx, edx
0x180090d31  jmp     short loc_180090CB8
0x180090d33  lea     rdx, aMsGamebar; "ms-gamebar"
0x180090d3a  lea     rcx, [rbp+290h+pszAssoc]
0x180090d3e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180090d43  nop
0x180090d44  mov     dl, cs:byte_180109DA0
0x180090d4a  mov     r12d, 7
0x180090d50  test    dl, 1
0x180090d53  jnz     short loc_180090DBD
0x180090d55  xor     edx, edx; Val
0x180090d57  mov     r8d, 208h; Size
0x180090d5d  lea     rcx, [rbp+290h+var_250]; void *
0x180090d61  call    memset_0
0x180090d66  mov     [rsp+390h+pvData], 104h
0x180090d6e  lea     r8, [rbp+290h+pszAssoc]
0x180090d72  cmp     [rbp+290h+var_268], r12
0x180090d76  cmova   r8, [rbp+290h+pszAssoc]; pszAssoc
0x180090d7b  lea     rax, [rsp+390h+pvData]
0x180090d80  mov     [rsp+390h+pcchOut], rax; char *
0x180090d85  lea     rax, [rbp+290h+var_250]
0x180090d89  mov     [rsp+390h+pszOut], rax; pszOut
0x180090d8e  xor     r9d, r9d; pszExtra
0x180090d91  lea     edx, [r12+0Eh]; str
0x180090d96  mov     ecx, 1000h; flags
0x180090d9b  call    cs:__imp_AssocQueryStringW
0x180090da1  mov     edx, eax
0x180090da3  shr     edx, 1Fh
0x180090da6  xor     dl, 1
0x180090da9  add     dl, dl
0x180090dab  mov     cl, [rsp+390h+var_344]
0x180090daf  and     cl, 0FDh
0x180090db2  or      dl, cl
0x180090db4  or      dl, 1
0x180090db7  mov     cs:byte_180109DA0, dl
0x180090dbd  test    dl, 2
0x180090dc0  jz      loc_180090FF8
0x180090dc6  test    sil, sil
0x180090dc9  jz      loc_180090FF8
0x180090dcf  lea     rdx, [rbp+290h+pszAssoc]
0x180090dd3  lea     rcx, [rbp+290h+hkey]
0x180090dd7  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@QEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const * const)
0x180090ddc  nop
0x180090ddd  mov     eax, [rsp+390h+var_350]
0x180090de1  mov     r8d, 0Ah
0x180090de7  sub     eax, 0Eh
0x180090dea  jz      loc_180090F12
0x180090df0  sub     eax, 1
0x180090df3  jz      loc_180090EDB
0x180090df9  sub     eax, 2
0x180090dfc  jz      loc_180090EA1
0x180090e02  sub     eax, 1
0x180090e05  jz      short loc_180090E6E
0x180090e07  sub     eax, 1
0x180090e0a  jz      short loc_180090E15
0x180090e0c  cmp     eax, 1
0x180090e0f  jnz     loc_180090F65
0x180090e15  mov     rcx, [rbp+290h+var_2B0]
0x180090e19  mov     rax, [rbp+290h+var_2A8]
0x180090e1d  sub     rax, rcx
0x180090e20  mov     edx, 0Bh
0x180090e25  cmp     rax, rdx
0x180090e28  jb      short loc_180090E5D
0x180090e2a  lea     rdi, [rcx+0Bh]
0x180090e2e  lea     r8d, [rdx+0Bh]; Size
0x180090e32  lea     rdx, aUnavailable; "unavailable"
0x180090e39  lea     rbx, [rbp+290h+hkey]
0x180090e3d  cmp     [rbp+290h+var_2A8], r12
0x180090e41  cmova   rbx, [rbp+290h+hkey]
0x180090e46  lea     rcx, [rbx+rcx*2]; void *
0x180090e4a  mov     [rbp+290h+var_2B0], rdi
0x180090e4e  call    memmove_0
0x180090e53  mov     [rbx+rdi*2], r14w
0x180090e58  jmp     loc_180090F65
0x180090e5d  mov     [rsp+390h+pszOut], rdx
0x180090e62  lea     r9, aUnavailable; "unavailable"
0x180090e69  jmp     loc_180090F5C
0x180090e6e  mov     rcx, [rbp+290h+var_2B0]
0x180090e72  mov     rax, [rbp+290h+var_2A8]
0x180090e76  sub     rax, rcx
0x180090e79  mov     edx, 5
0x180090e7e  cmp     rax, rdx
0x180090e81  jb      short loc_180090E90
0x180090e83  lea     rdi, [rcx+5]
0x180090e87  lea     rdx, aOffer; "offer"
0x180090e8e  jmp     short loc_180090E39
0x180090e90  mov     [rsp+390h+pszOut], rdx
0x180090e95  lea     r9, aOffer; "offer"
0x180090e9c  jmp     loc_180090F5C
0x180090ea1  mov     rcx, [rbp+290h+var_2B0]
0x180090ea5  mov     rax, [rbp+290h+var_2A8]
0x180090ea9  sub     rax, rcx
0x180090eac  cmp     rax, r12
0x180090eaf  jb      short loc_180090EC7
0x180090eb1  lea     rdi, [rcx+7]
0x180090eb5  mov     r8d, 0Eh
0x180090ebb  lea     rdx, aRestart; "restart"
0x180090ec2  jmp     loc_180090E39
0x180090ec7  mov     [rsp+390h+pszOut], r12
0x180090ecc  lea     r9, aRestart; "restart"
0x180090ed3  mov     rdx, r12
0x180090ed6  jmp     loc_180090F5C
0x180090edb  mov     rcx, [rbp+290h+var_2B0]
0x180090edf  mov     rax, [rbp+290h+var_2A8]
0x180090ee3  sub     rax, rcx
0x180090ee6  cmp     rax, r8
0x180090ee9  jb      short loc_180090F01
0x180090eeb  lea     rdi, [rcx+0Ah]
0x180090eef  mov     r8d, 14h
0x180090ef5  lea     rdx, aResolution; "resolution"
0x180090efc  jmp     loc_180090E39
0x180090f01  mov     [rsp+390h+pszOut], r8
0x180090f06  lea     r9, aResolution; "resolution"
0x180090f0d  mov     rdx, r8
0x180090f10  jmp     short loc_180090F5C
0x180090f12  mov     r8, [rbp+290h+var_2B0]
0x180090f16  mov     rax, [rbp+290h+var_2A8]
0x180090f1a  sub     rax, r8
0x180090f1d  cmp     rax, 2
0x180090f21  jb      short loc_180090F47
0x180090f23  lea     rdx, [r8+2]
0x180090f27  mov     [rbp+290h+var_2B0], rdx
0x180090f2b  lea     rcx, [rbp+290h+hkey]
0x180090f2f  cmp     [rbp+290h+var_2A8], r12
0x180090f33  cmova   rcx, [rbp+290h+hkey]
0x180090f38  mov     dword ptr [rcx+r8*2], 6E006Fh
0x180090f40  mov     [rcx+rdx*2], r14w
0x180090f45  jmp     short loc_180090F65
0x180090f47  mov     [rsp+390h+pszOut], 2; __int64
0x180090f50  lea     r9, aOn; "on"
0x180090f57  mov     edx, 2
0x180090f5c  lea     rcx, [rbp+290h+hkey]; Src
0x180090f60  call    ??$_Reallocate_grow_by@V_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_@@PEBG_K@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_@@PEBG_K@Z; std::wstring::_Reallocate_grow_by<_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_,ushort const *,unsigned __int64>(unsigned __int64,_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_,ushort const *,unsigned __int64)
0x180090f65  mov     ebx, 70h ; 'p'
0x180090f6a  mov     r8d, ebx; Size
0x180090f6d  xor     edx, edx; Val
0x180090f6f  lea     rcx, [rsp+390h+pExecInfo]; void *
0x180090f74  call    memset_0
0x180090f79  mov     qword ptr [rsp+390h+pExecInfo.cbSize], rbx
0x180090f7e  mov     [rsp+390h+pExecInfo.hwnd], r14
0x180090f83  lea     rax, aOpen; "open"
0x180090f8a  mov     [rsp+390h+pExecInfo.lpVerb], rax
0x180090f8f  lea     rax, [rbp+290h+hkey]
0x180090f93  cmp     [rbp+290h+var_2A8], r12
0x180090f97  cmova   rax, [rbp+290h+hkey]
0x180090f9c  mov     [rsp+390h+pExecInfo.lpFile], rax
0x180090fa1  xorps   xmm0, xmm0
0x180090fa4  movdqa  xmmword ptr [rbp+290h+pExecInfo.lpParameters], xmm0
0x180090fa9  mov     [rbp+290h+pExecInfo.nShow], 0Ah
0x180090fb0  lea     rcx, [rsp+390h+pExecInfo]; pExecInfo
0x180090fb5  call    cs:__imp_ShellExecuteExW
0x180090fbb  test    eax, eax
0x180090fbd  setnz   al
0x180090fc0  mov     rcx, [rbp+298h]; this
0x180090fc7  lea     rdx, aFailedToActiva; "Failed to activate SR widget"
0x180090fce  mov     [rsp+390h+pszOut], rdx; bool
0x180090fd3  movzx   r9d, al; char *
0x180090fd7  lea     r8, aOnecoreuapWind_6; "onecoreuap\\windows\\directx\\dxg\\dxgi"...
0x180090fde  mov     edx, 0E12h; void *
0x180090fe3  call    ?Log_GetLastErrorIfFalseMsg@in1diag3@details@wil@@YA_NPEAXIPEBD_N1ZZ; wil::details::in1diag3::Log_GetLastErrorIfFalseMsg(void *,uint,char const *,bool,char const *,...)
0x180090fe8  nop
0x180090fe9  lea     rcx, [rbp+290h+hkey]
0x180090fed  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180090ff2  mov     dl, cs:byte_180109DA0
0x180090ff8  mov     edi, 10h
0x180090ffd  mov     ebx, 80070000h
0x180091002  cmp     cs:byte_180109D98, r14b
0x180091009  jnz     loc_1800910BA
0x18009100f  mov     cs:byte_180109D98, 1
0x180091016  movzx   eax, word ptr [rbp+290h+hkey+1]
0x18009101a  mov     cs:word_180109D99, ax
0x180091021  mov     al, byte ptr [rbp+290h+hkey+3]
0x180091024  mov     cs:byte_180109D9B, al
0x18009102a  mov     cs:dword_180109D9C, r14d
0x180091031  test    dl, 2
0x180091034  jz      loc_1800910BA
0x18009103a  mov     [rbp+290h+hkey], r14
0x18009103e  lea     r8, [rbp+290h+hkey]
0x180091042  call    ?open_unique_key_nothrow@reg@wil@@YAJPEAUHKEY__@@PEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@W4key_access@12@@Z; wil::reg::open_unique_key_nothrow(HKEY__ *,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &,wil::reg::key_access)
0x180091047  test    eax, eax
0x180091049  js      short loc_1800910B1
0x18009104b  mov     [rsp+390h+pvData], r14d
0x180091050  mov     [rsp+390h+var_340], 4
0x180091058  lea     rax, [rsp+390h+var_340]
0x18009105d  mov     [rsp+390h+pcbData], rax; pcbData
0x180091062  lea     rax, [rsp+390h+pvData]
0x180091067  mov     [rsp+390h+pcchOut], rax; pvData
0x18009106c  mov     [rsp+390h+pszOut], r14; pdwType
0x180091071  mov     r9d, edi; dwFlags
0x180091074  lea     r8, aGraphicsfeatur; "GraphicsFeaturesNotificationConfig"
0x18009107b  xor     edx, edx; lpSubKey
0x18009107d  mov     rcx, [rbp+290h+hkey]; hkey
0x180091081  call    cs:__imp_RegGetValueW
0x180091087  test    eax, eax
0x180091089  jle     short loc_180091092
0x18009108b  movzx   eax, ax
0x18009108e  or      eax, ebx
0x180091090  test    eax, eax
0x180091092  js      short loc_1800910B1
0x180091094  mov     eax, [rsp+390h+pvData]
0x180091098  mov     cs:dword_180109D9C, eax
0x18009109e  test    al, 1
0x1800910a0  jz      short loc_1800910B1
0x1800910a2  lea     r8, aAutosrNotifica; "AutoSR notifications disabled by regist"...
0x1800910a9  xor     edx, edx; unsigned int
0x1800910ab  call    ?RecordJournalImpl@CModule@@QEAAXIPEBD_N@Z; CModule::RecordJournalImpl(uint,char const *,bool)
0x1800910b0  nop
0x1800910b1  lea     rcx, [rbp+290h+hkey]
0x1800910b5  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800910ba  mov     eax, cs:dword_180109D9C
0x1800910c0  test    eax, eax
0x1800910c2  jz      short loc_1800910D1
0x1800910c4  test    sil, sil
0x1800910c7  jz      short loc_1800910D1
0x1800910c9  test    al, 1
0x1800910cb  jnz     loc_1800911A2
0x1800910d1  mov     rax, cs:qword_180109D80
0x1800910d8  test    rax, rax
0x1800910db  jnz     short loc_18009112D
0x1800910dd  mov     cs:qword_180109D80, r14
0x1800910e4  lea     r9, qword_180109D80
0x1800910eb  xor     r8d, r8d
0x1800910ee  xor     edx, edx
0x1800910f0  lea     rcx, WdDiagEtwControlGuid
0x1800910f7  call    cs:__imp_EtwEventRegister
0x1800910fd  test    eax, eax
0x1800910ff  jle     short loc_180091108
0x180091101  movzx   eax, ax
0x180091104  or      eax, ebx
0x180091106  test    eax, eax
0x180091108  jns     short loc_18009111D
0x18009110a  lea     r8, aFailedToRegist; "Failed to register WdDiag ETW provider"
0x180091111  mov     edx, eax; unsigned int
0x180091113  call    ?RecordJournalImpl@CModule@@QEAAXIPEBD_N@Z; CModule::RecordJournalImpl(uint,char const *,bool)
0x180091118  jmp     loc_1800911BE
0x18009111d  mov     rax, cs:qword_180109D80
0x180091124  test    rax, rax
0x180091127  jz      loc_1800911BE
0x18009112d  mov     [rbp+290h+var_290], 8
  ... truncated ...
```
