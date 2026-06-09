# InputProfileSettings::_RegisterUserPreferredProfile(uint,KeyboardInputProfile const *,bool,bool)

- ea: `0x1800836f4`
- end: `0x180083b7c`
- name: `?_RegisterUserPreferredProfile@InputProfileSettings@@AEAAJIPEBVKeyboardInputProfile@@_N1@Z`
- size: `1160`
- prototype: `int(InputProfileSettings *__hidden this, unsigned int, const struct KeyboardInputProfile *, bool, bool)`
- caller_count: `2`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180084970`
- `0x180084b8c`

## callees

- `0x18000fac0`
- `0x1800833f0`
- `0x1800836d4`
- `0x1800836f4`
- `0x1800855f0`
- `0x1800a4e04`
- `0x1800b847c`
- `0x1800cb430`
- `0x1800cb474`
- `0x1800cc7a8`
- `0x1800d128c`
- `0x1800d2b5c`
- `0x180106a60`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180083a61`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180083a61`
- `USER32!LoadKeyboardLayoutW` at `0x180083afc`
- `USER32!LoadKeyboardLayoutW` at `0x180083afc`
- `USER32!SystemParametersInfoW` at `0x180083b4a`
- `USER32!SystemParametersInfoW` at `0x180083b4a`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x180083ae3`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x180083ae3`

## pseudocode

```c
__int64 __fastcall InputProfileSettings::_RegisterUserPreferredProfile(
        InputProfileSettings *this,
        int a2,
        const struct KeyboardInputProfile *a3,
        char a4,
        bool a5)
{
  unsigned int v8; // edi
  unsigned int PreloadValue; // r15d
  int v10; // eax
  int v11; // edx
  int v12; // ecx
  int v13; // eax
  int v14; // edx
  int v15; // ecx
  int v16; // eax
  int v17; // edx
  int v18; // ecx
  int v19; // eax
  int v20; // edx
  int v21; // ecx
  int v22; // eax
  int v23; // edx
  int v24; // ecx
  int v25; // eax
  int v26; // edx
  int v27; // ecx
  unsigned __int16 v28; // dx
  __int64 v29; // rax
  unsigned int TsfImeDefaultLayout; // ecx
  const struct _GUID *v31; // r9
  int CustomString; // eax
  int v33; // edx
  int v34; // ecx
  int v35; // eax
  int v36; // edx
  int v37; // ecx
  int v38; // eax
  int v39; // edx
  int v40; // ecx
  int v41; // eax
  int v42; // edx
  int v43; // ecx
  HKEY v44; // rcx
  LSTATUS v45; // eax
  unsigned int v46; // r8d
  __int64 v47; // rax
  __int64 v48; // r9
  struct _GUID v49; // xmm1
  const struct _GUID *v50; // r8
  HKL v51; // rbx
  int v52; // edx
  int v53; // ecx
  int lpData; // [rsp+20h] [rbp-E0h]
  unsigned __int16 *cbData; // [rsp+28h] [rbp-D8h]
  BYTE Data[16]; // [rsp+30h] [rbp-D0h] BYREF
  struct _GUID v58; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 v59[12]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR ValueName[12]; // [rsp+68h] [rbp-98h] BYREF
  WCHAR SubKey[264]; // [rsp+80h] [rbp-80h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2D8h] [rbp+1D8h]

  if ( !a3 )
  {
    v8 = -2147024809;
    if ( (Microsoft_WindowsPhone_InputEnableBits & 1) != 0 )
      McTemplateU0sqq_EventWriteTransfer(
        (_DWORD)this,
        a2,
        (unsigned int)"InputProfileSettings::_RegisterUserPreferredProfile",
        1392,
        87);
    return v8;
  }
  PreloadValue = KeyboardInputProfile::GetPreloadValue(a3);
  v10 = StringCchPrintfW(v59, 9u, L"%d");
  v8 = v10;
  if ( v10 < 0 )
  {
    if ( (Microsoft_WindowsPhone_InputEnableBits & 1) != 0 )
      McTemplateU0sqq_EventWriteTransfer(
        v12,
        v11,
        (unsigned int)"InputProfileSettings::_RegisterUserPreferredProfile",
        1399,
        v10);
    return v8;
  }
  v13 = StringCchPrintfW(ValueName, 9u, L"%08X", PreloadValue);
  v8 = v13;
  if ( v13 < 0 )
  {
    if ( (Microsoft_WindowsPhone_InputEnableBits & 1) != 0 )
      McTemplateU0sqq_EventWriteTransfer(
        v15,
        v14,
        (unsigned int)"InputProfileSettings::_RegisterUserPreferredProfile",
        1400,
        v13);
    return v8;
  }
  v16 = CMyRegKey::SetValue((InputProfileSettings *)((char *)this + 16), ValueName, v59);
  v8 = v16;
  if ( v16 > 0 )
    v8 = (unsigned __int16)v16 | 0x80070000;
  if ( (v8 & 0x80000000) != 0 )
  {
    if ( (Microsoft_WindowsPhone_InputEnableBits & 1) != 0 )
      McTemplateU0sqq_EventWriteTransfer(
        v18,
        v17,
        (unsigned int)"InputProfileSettings::_RegisterUserPreferredProfile",
        1401,
        v8);
    return v8;
  }
  if ( a4 )
  {
    v19 = CMyRegKey::SetValue((InputProfileSettings *)((char *)this + 16), ValueName, 0);
    v8 = v19;
    if ( v19 > 0 )
      v8 = (unsigned __int16)v19 | 0x80070000;
    if ( (v8 & 0x80000000) != 0 )
    {
      if ( (Microsoft_WindowsPhone_InputEnableBits & 1) != 0 )
        McTemplateU0sqq_EventWriteTransfer(
          v21,
          v20,
          (unsigned int)"InputProfileSettings::_RegisterUserPreferredProfile",
          1406,
          v8);
      return v8;
    }
  }
  if ( PreloadValue != *((_DWORD *)a3 + 1) )
  {
    v22 = StringCchPrintfW(v59, 9u, L"%08X");
    v8 = v22;
    if ( v22 < 0 )
    {
      if ( (Microsoft_WindowsPhone_InputEnableBits & 1) != 0 )
        McTemplateU0sqq_EventWriteTransfer(
          v24,
          v23,
          (unsigned int)"InputProfileSettings::_RegisterUserPreferredProfile",
          1412,
          v22);
      return v8;
    }
    v25 = CMyRegKey::SetValue((InputProfileSettings *)((char *)this + 32), v59, ValueName);
    v8 = v25;
    if ( v25 > 0 )
      v8 = (unsigned __int16)v25 | 0x80070000;
    if ( (v8 & 0x80000000) != 0 )
    {
      if ( (Microsoft_WindowsPhone_InputEnableBits & 1) != 0 )
        McTemplateU0sqq_EventWriteTransfer(
          v27,
          v26,
          (unsigned int)"InputProfileSettings::_RegisterUserPreferredProfile",
          1413,
          v8);
      return v8;
    }
  }
  if ( !KeyboardInputProfile::IsCustomProfile(a3) )
    goto LABEL_73;
  v29 = *((_QWORD *)a3 + 1) - *(_QWORD *)&GUID_NULL.Data1;
  if ( !v29 )
    v29 = *((_QWORD *)a3 + 2) - *(_QWORD *)GUID_NULL.Data4;
  if ( v29 )
    TsfImeDefaultLayout = input_profile_settings::GetTsfImeDefaultLayout(
                            (input_profile_settings *)*(unsigned __int16 *)a3,
                            v28);
  else
    TsfImeDefaultLayout = *(unsigned __int16 *)a3;
  v31 = (const struct _GUID *)*((unsigned int *)a3 + 1);
  if ( (_DWORD)v31 == TsfImeDefaultLayout )
    v31 = 0;
  CustomString = input_profile_settings::MakeCustomString(
                   *((input_profile_settings **)a3 + 5),
                   (unsigned __int64)a3 + 8,
                   (const struct _GUID *)((char *)a3 + 24),
                   v31,
                   (unsigned int)SubKey,
                   cbData,
                   *(unsigned int *)Data);
  v8 = CustomString;
  if ( CustomString < 0 )
  {
    if ( (Microsoft_WindowsPhone_InputEnableBits & 1) != 0 )
      McTemplateU0sqq_EventWriteTransfer(
        v34,
        v33,
        (unsigned int)"InputProfileSettings::_RegisterUserPreferredProfile",
        1420,
        CustomString);
    return v8;
  }
  v35 = StringCchPrintfW(v59, 9u, L"%04X", *((unsigned __int16 *)a3 + 26));
  v8 = v35;
  if ( v35 < 0 )
  {
    if ( (Microsoft_WindowsPhone_InputEnableBits & 1) != 0 )
      McTemplateU0sqq_EventWriteTransfer(
        v37,
        v36,
        (unsigned int)"InputProfileSettings::_RegisterUserPreferredProfile",
        1422,
        v35);
    return v8;
  }
  v38 = CMyRegKey::SetValue((InputProfileSettings *)((char *)this + 64), SubKey, v59);
  v8 = v38;
  if ( v38 > 0 )
    v8 = (unsigned __int16)v38 | 0x80070000;
  if ( (v8 & 0x80000000) != 0 )
  {
    if ( (Microsoft_WindowsPhone_InputEnableBits & 1) != 0 )
      McTemplateU0sqq_EventWriteTransfer(
        v40,
        v39,
        (unsigned int)"InputProfileSettings::_RegisterUserPreferredProfile",
        1425,
        v8);
    return v8;
  }
  v41 = CMyRegKey::SetValue((InputProfileSettings *)((char *)this + 48), v59, ValueName);
  v8 = v41;
  if ( v41 > 0 )
    v8 = (unsigned __int16)v41 | 0x80070000;
  if ( (v8 & 0x80000000) != 0 )
  {
    if ( (Microsoft_WindowsPhone_InputEnableBits & 1) != 0 )
      McTemplateU0sqq_EventWriteTransfer(
        v43,
        v42,
        (unsigned int)"InputProfileSettings::_RegisterUserPreferredProfile",
        1428,
        v8);
  }
  else
  {
LABEL_73:
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_KeyboardSettings_InputProfileHotKeys>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_KeyboardSettings_InputProfileHotKeys>::GetImpl'::`2'::impl) )
    {
      if ( *((_DWORD *)a3 + 16) )
      {
        v44 = (HKEY)*((_QWORD *)this + 11);
        *(_DWORD *)Data = *((_DWORD *)a3 + 16);
        v45 = RegSetValueExW(v44, ValueName, 0, 4u, Data, 4u);
        if ( v45 < 0 )
          wil::details::in1diag3::_Log_NtStatus(retaddr, (void *)0x59C, v46, (const char *)(unsigned int)v45, lpData);
      }
    }
    v47 = *((_QWORD *)a3 + 1) - *(_QWORD *)&GUID_NULL.Data1;
    if ( !v47 )
      v47 = *((_QWORD *)a3 + 2) - *(_QWORD *)GUID_NULL.Data4;
    if ( v47 )
    {
      v48 = *((_QWORD *)a3 + 5);
      v49 = *(struct _GUID *)((char *)a3 + 8);
      v50 = (const struct _GUID *)*(unsigned __int16 *)a3;
      *(_OWORD *)Data = *(_OWORD *)((char *)a3 + 24);
      v58 = v49;
      if ( (int)input_profile_settings::GetCtfKeyString(
                  &v58,
                  (const struct _GUID *)Data,
                  v50,
                  v48,
                  (unsigned __int64)SubKey,
                  cbData,
                  *(unsigned int *)Data) >= 0 )
        RegDeleteKeyValueW(*((HKEY *)this + 15), SubKey, L"Enable");
    }
    if ( a5 )
    {
      *(_QWORD *)Data = LoadKeyboardLayoutW(ValueName, 0x82u);
      v51 = *(HKL *)Data;
      if ( v51 == KeyboardInputProfile::GetHkl(a3) )
      {
        if ( a4 )
          SystemParametersInfoW(0x5Au, 0, Data, 0);
      }
      else
      {
        v8 = -2147467259;
        if ( (Microsoft_WindowsPhone_InputEnableBits & 1) != 0 )
          McTemplateU0sqq_EventWriteTransfer(
            v53,
            v52,
            (unsigned int)"InputProfileSettings::_RegisterUserPreferredProfile",
            1459,
            5);
      }
    }
  }
  return v8;
}

```

## disassembly

```asm
0x1800836f4  mov     [rsp-8+arg_18], rbx
0x1800836f9  push    rbp
0x1800836fa  push    rsi
0x1800836fb  push    rdi
0x1800836fc  push    r12
0x1800836fe  push    r13
0x180083700  push    r14
0x180083702  push    r15
0x180083704  lea     rbp, [rsp-1A0h]
0x18008370c  sub     rsp, 2A0h
0x180083713  mov     rax, cs:__security_cookie
0x18008371a  xor     rax, rsp
0x18008371d  mov     [rbp+1D0h+var_40], rax
0x180083724  mov     r12b, r9b
0x180083727  mov     r9d, edx
0x18008372a  mov     rsi, r8
0x18008372d  mov     rbx, rcx
0x180083730  test    r8, r8
0x180083733  jnz     short loc_180083766
0x180083735  test    cs:Microsoft_WindowsPhone_InputEnableBits, 1
0x18008373c  mov     edi, 80070057h
0x180083741  jz      loc_180083B50
0x180083747  mov     dword ptr [rsp+2D0h+lpData], 80070057h
0x18008374f  mov     r9d, 570h
0x180083755  lea     r8, aInputprofilese_8; "InputProfileSettings::_RegisterUserPref"...
0x18008375c  call    McTemplateU0sqq_EventWriteTransfer
0x180083761  jmp     loc_180083B50
0x180083766  mov     rcx, rsi; this
0x180083769  call    ?GetPreloadValue@KeyboardInputProfile@@QEBAIXZ; KeyboardInputProfile::GetPreloadValue(void)
0x18008376e  mov     r14d, 9
0x180083774  lea     r8, aD; "%d"
0x18008377b  mov     edx, r14d; unsigned __int64
0x18008377e  lea     rcx, [rsp+2D0h+var_280]; unsigned __int16 *
0x180083783  mov     r15d, eax
0x180083786  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18008378b  mov     edi, eax
0x18008378d  test    eax, eax
0x18008378f  jns     short loc_1800837AA
0x180083791  test    cs:Microsoft_WindowsPhone_InputEnableBits, 1
0x180083798  jz      loc_180083B50
0x18008379e  mov     dword ptr [rsp+2D0h+lpData], eax
0x1800837a2  mov     r9d, 577h
0x1800837a8  jmp     short loc_180083755
0x1800837aa  mov     r9d, r15d
0x1800837ad  lea     r8, a08x; "%08X"
0x1800837b4  mov     rdx, r14; unsigned __int64
0x1800837b7  lea     rcx, [rsp+2D0h+ValueName]; unsigned __int16 *
0x1800837bc  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800837c1  mov     edi, eax
0x1800837c3  test    eax, eax
0x1800837c5  jns     short loc_1800837E3
0x1800837c7  test    cs:Microsoft_WindowsPhone_InputEnableBits, 1
0x1800837ce  jz      loc_180083B50
0x1800837d4  mov     dword ptr [rsp+2D0h+lpData], eax
0x1800837d8  mov     r9d, 578h
0x1800837de  jmp     loc_180083755
0x1800837e3  lea     r8, [rsp+2D0h+var_280]; unsigned __int16 *
0x1800837e8  lea     rdx, [rsp+2D0h+ValueName]; unsigned __int16 *
0x1800837ed  lea     rcx, [rbx+10h]; this
0x1800837f1  call    ?SetValue@CMyRegKey@@QEAAJPEBG0@Z; CMyRegKey::SetValue(ushort const *,ushort const *)
0x1800837f6  mov     edi, eax
0x1800837f8  mov     r13d, 80070000h
0x1800837fe  test    eax, eax
0x180083800  jle     short loc_180083808
0x180083802  movzx   edi, ax
0x180083805  or      edi, r13d
0x180083808  test    edi, edi
0x18008380a  jns     short loc_180083828
0x18008380c  test    cs:Microsoft_WindowsPhone_InputEnableBits, 1
0x180083813  jz      loc_180083B50
0x180083819  mov     dword ptr [rsp+2D0h+lpData], edi
0x18008381d  mov     r9d, 579h
0x180083823  jmp     loc_180083755
0x180083828  test    r12b, r12b
0x18008382b  jz      short loc_18008386A
0x18008382d  xor     r8d, r8d; unsigned __int16 *
0x180083830  lea     rdx, [rsp+2D0h+ValueName]; unsigned __int16 *
0x180083835  lea     rcx, [rbx+10h]; this
0x180083839  call    ?SetValue@CMyRegKey@@QEAAJPEBG0@Z; CMyRegKey::SetValue(ushort const *,ushort const *)
0x18008383e  mov     edi, eax
0x180083840  test    eax, eax
0x180083842  jle     short loc_18008384A
0x180083844  movzx   edi, ax
0x180083847  or      edi, r13d
0x18008384a  test    edi, edi
0x18008384c  jns     short loc_18008386A
0x18008384e  test    cs:Microsoft_WindowsPhone_InputEnableBits, 1
0x180083855  jz      loc_180083B50
0x18008385b  mov     dword ptr [rsp+2D0h+lpData], edi
0x18008385f  mov     r9d, 57Eh
0x180083865  jmp     loc_180083755
0x18008386a  mov     r9d, [rsi+4]
0x18008386e  cmp     r15d, r9d
0x180083871  jz      short loc_1800838E8
0x180083873  lea     r8, a08x; "%08X"
0x18008387a  mov     rdx, r14; unsigned __int64
0x18008387d  lea     rcx, [rsp+2D0h+var_280]; unsigned __int16 *
0x180083882  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180083887  mov     edi, eax
0x180083889  test    eax, eax
0x18008388b  jns     short loc_1800838A9
0x18008388d  test    cs:Microsoft_WindowsPhone_InputEnableBits, 1
0x180083894  jz      loc_180083B50
0x18008389a  mov     dword ptr [rsp+2D0h+lpData], eax
0x18008389e  mov     r9d, 584h
0x1800838a4  jmp     loc_180083755
0x1800838a9  lea     rcx, [rbx+20h]; this
0x1800838ad  lea     r8, [rsp+2D0h+ValueName]; unsigned __int16 *
0x1800838b2  lea     rdx, [rsp+2D0h+var_280]; unsigned __int16 *
0x1800838b7  call    ?SetValue@CMyRegKey@@QEAAJPEBG0@Z; CMyRegKey::SetValue(ushort const *,ushort const *)
0x1800838bc  mov     edi, eax
0x1800838be  test    eax, eax
0x1800838c0  jle     short loc_1800838C8
0x1800838c2  movzx   edi, ax
0x1800838c5  or      edi, r13d
0x1800838c8  test    edi, edi
0x1800838ca  jns     short loc_1800838E8
0x1800838cc  test    cs:Microsoft_WindowsPhone_InputEnableBits, 1
0x1800838d3  jz      loc_180083B50
0x1800838d9  mov     dword ptr [rsp+2D0h+lpData], edi
0x1800838dd  mov     r9d, 585h
0x1800838e3  jmp     loc_180083755
0x1800838e8  mov     rcx, rsi; this
0x1800838eb  call    ?IsCustomProfile@KeyboardInputProfile@@QEBA_NXZ; KeyboardInputProfile::IsCustomProfile(void)
0x1800838f0  test    al, al
0x1800838f2  jz      loc_180083A25
0x1800838f8  mov     rax, [rsi+8]
0x1800838fc  sub     rax, qword ptr cs:GUID_NULL.Data1
0x180083903  jnz     short loc_180083910
0x180083905  mov     rax, [rsi+10h]
0x180083909  sub     rax, qword ptr cs:GUID_NULL.Data4
0x180083910  test    rax, rax
0x180083913  jz      short loc_180083921
0x180083915  movzx   ecx, word ptr [rsi]; this
0x180083918  call    ?GetTsfImeDefaultLayout@input_profile_settings@@YAIG@Z; input_profile_settings::GetTsfImeDefaultLayout(ushort)
0x18008391d  mov     ecx, eax
0x18008391f  jmp     short loc_180083924
0x180083921  movzx   ecx, word ptr [rsi]
0x180083924  mov     r9d, [rsi+4]
0x180083928  lea     r8, [rsi+18h]; struct _GUID *
0x18008392c  xor     eax, eax
0x18008392e  lea     rdx, [rsi+8]; unsigned __int64
0x180083932  cmp     r9d, ecx
0x180083935  mov     rcx, [rsi+28h]; this
0x180083939  cmovz   r9d, eax; struct _GUID *
0x18008393d  lea     rax, [rbp+1D0h+SubKey]
0x180083941  mov     [rsp+2D0h+lpData], rax; unsigned int
0x180083946  call    ?MakeCustomString@input_profile_settings@@YAJ_KAEBU_GUID@@1IPEAGI@Z; input_profile_settings::MakeCustomString(unsigned __int64,_GUID const &,_GUID const &,uint,ushort *,uint)
0x18008394b  mov     edi, eax
0x18008394d  test    eax, eax
0x18008394f  jns     short loc_18008396D
0x180083951  test    cs:Microsoft_WindowsPhone_InputEnableBits, 1
0x180083958  jz      loc_180083B50
0x18008395e  mov     dword ptr [rsp+2D0h+lpData], eax
0x180083962  mov     r9d, 58Ch
0x180083968  jmp     loc_180083755
0x18008396d  movzx   r9d, word ptr [rsi+34h]
0x180083972  lea     r8, a04x; "%04X"
0x180083979  mov     rdx, r14; unsigned __int64
0x18008397c  lea     rcx, [rsp+2D0h+var_280]; unsigned __int16 *
0x180083981  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180083986  mov     edi, eax
0x180083988  test    eax, eax
0x18008398a  jns     short loc_1800839A8
0x18008398c  test    cs:Microsoft_WindowsPhone_InputEnableBits, 1
0x180083993  jz      loc_180083B50
0x180083999  mov     dword ptr [rsp+2D0h+lpData], eax
0x18008399d  mov     r9d, 58Eh
0x1800839a3  jmp     loc_180083755
0x1800839a8  lea     rcx, [rbx+40h]; this
0x1800839ac  lea     r8, [rsp+2D0h+var_280]; unsigned __int16 *
0x1800839b1  lea     rdx, [rbp+1D0h+SubKey]; unsigned __int16 *
0x1800839b5  call    ?SetValue@CMyRegKey@@QEAAJPEBG0@Z; CMyRegKey::SetValue(ushort const *,ushort const *)
0x1800839ba  mov     edi, eax
0x1800839bc  test    eax, eax
0x1800839be  jle     short loc_1800839C6
0x1800839c0  movzx   edi, ax
0x1800839c3  or      edi, r13d
0x1800839c6  test    edi, edi
0x1800839c8  jns     short loc_1800839E6
0x1800839ca  test    cs:Microsoft_WindowsPhone_InputEnableBits, 1
0x1800839d1  jz      loc_180083B50
0x1800839d7  mov     dword ptr [rsp+2D0h+lpData], edi
0x1800839db  mov     r9d, 591h
0x1800839e1  jmp     loc_180083755
0x1800839e6  lea     rcx, [rbx+30h]; this
0x1800839ea  lea     r8, [rsp+2D0h+ValueName]; unsigned __int16 *
0x1800839ef  lea     rdx, [rsp+2D0h+var_280]; unsigned __int16 *
0x1800839f4  call    ?SetValue@CMyRegKey@@QEAAJPEBG0@Z; CMyRegKey::SetValue(ushort const *,ushort const *)
0x1800839f9  mov     edi, eax
0x1800839fb  test    eax, eax
0x1800839fd  jle     short loc_180083A05
0x1800839ff  movzx   edi, ax
0x180083a02  or      edi, r13d
0x180083a05  test    edi, edi
0x180083a07  jns     short loc_180083A25
0x180083a09  test    cs:Microsoft_WindowsPhone_InputEnableBits, 1
0x180083a10  jz      loc_180083B50
0x180083a16  mov     dword ptr [rsp+2D0h+lpData], edi
0x180083a1a  mov     r9d, 594h
0x180083a20  jmp     loc_180083755
0x180083a25  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_KeyboardSettings_InputProfileHotKeys@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_KeyboardSettings_InputProfileHotKeys@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_KeyboardSettings_InputProfileHotKeys> `wil::Feature<__WilFeatureTraits_Feature_KeyboardSettings_InputProfileHotKeys>::GetImpl(void)'::`2'::impl
0x180083a2c  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_KeyboardSettings_InputProfileHotKeys@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_KeyboardSettings_InputProfileHotKeys>::__private_IsEnabled(void)
0x180083a31  test    al, al
0x180083a33  jz      short loc_180083A7F
0x180083a35  mov     eax, [rsi+40h]
0x180083a38  test    eax, eax
0x180083a3a  jz      short loc_180083A7F
0x180083a3c  mov     rcx, [rbx+58h]; hKey
0x180083a40  lea     rdx, [rsp+2D0h+ValueName]; lpValueName
0x180083a45  mov     dword ptr [rsp+2D0h+Data], eax
0x180083a49  mov     r9d, 4; dwType
0x180083a4f  lea     rax, [rsp+2D0h+Data]
0x180083a54  mov     dword ptr [rsp+2D0h+cbData], r9d; unsigned __int16 *
0x180083a59  xor     r8d, r8d; Reserved
0x180083a5c  mov     [rsp+2D0h+lpData], rax; int
0x180083a61  call    cs:__imp_RegSetValueExW
0x180083a67  test    eax, eax
0x180083a69  jns     short loc_180083A7F
0x180083a6b  mov     rcx, [rbp+1D8h]; this
0x180083a72  mov     r9d, eax; char *
0x180083a75  mov     edx, 59Ch; void *
0x180083a7a  call    ?_Log_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_NtStatus(void *,uint,char const *,long)
0x180083a7f  mov     rax, [rsi+8]
0x180083a83  sub     rax, qword ptr cs:GUID_NULL.Data1
0x180083a8a  jnz     short loc_180083A97
0x180083a8c  mov     rax, [rsi+10h]
0x180083a90  sub     rax, qword ptr cs:GUID_NULL.Data4
0x180083a97  test    rax, rax
0x180083a9a  jz      short loc_180083AE9
0x180083a9c  movups  xmm0, xmmword ptr [rsi+18h]
0x180083aa0  mov     r9, [rsi+28h]; unsigned __int16
0x180083aa4  lea     rax, [rbp+1D0h+SubKey]
0x180083aa8  movups  xmm1, xmmword ptr [rsi+8]
0x180083aac  movzx   r8d, word ptr [rsi]; struct _GUID *
0x180083ab0  lea     rdx, [rsp+2D0h+Data]; struct _GUID *
0x180083ab5  lea     rcx, [rsp+2D0h+var_290]; this
0x180083aba  mov     [rsp+2D0h+lpData], rax; unsigned __int64
0x180083abf  movdqu  xmmword ptr [rsp+2D0h+Data], xmm0; unsigned int
0x180083ac5  movdqu  xmmword ptr [rsp+2D0h+var_290.Data1], xmm1
0x180083acb  call    ?GetCtfKeyString@input_profile_settings@@YAJAEBU_GUID@@0G_KPEAGI@Z; input_profile_settings::GetCtfKeyString(_GUID const &,_GUID const &,ushort,unsigned __int64,ushort *,uint)
0x180083ad0  test    eax, eax
0x180083ad2  js      short loc_180083AE9
0x180083ad4  mov     rcx, [rbx+78h]; hKey
0x180083ad8  lea     r8, ?c_szEnable@@3QBGB; "Enable"
0x180083adf  lea     rdx, [rbp+1D0h+SubKey]; lpSubKey
0x180083ae3  call    cs:__imp_RegDeleteKeyValueW
0x180083ae9  cmp     [rbp+1D0h+arg_20], 0
0x180083af0  jz      short loc_180083B50
0x180083af2  mov     edx, 82h; Flags
0x180083af7  lea     rcx, [rsp+2D0h+ValueName]; pwszKLID
0x180083afc  call    cs:__imp_LoadKeyboardLayoutW
0x180083b02  mov     rcx, rsi; this
0x180083b05  mov     qword ptr [rsp+2D0h+Data], rax
0x180083b0a  mov     rbx, rax
0x180083b0d  call    ?GetHkl@KeyboardInputProfile@@QEBAPEAUHKL__@@XZ; KeyboardInputProfile::GetHkl(void)
0x180083b12  cmp     rbx, rax
0x180083b15  jz      short loc_180083B38
0x180083b17  test    cs:Microsoft_WindowsPhone_InputEnableBits, 1
0x180083b1e  mov     edi, 80004005h
0x180083b23  jz      short loc_180083B50
0x180083b25  mov     dword ptr [rsp+2D0h+lpData], 80004005h
0x180083b2d  mov     r9d, 5B3h
0x180083b33  jmp     loc_180083755
0x180083b38  test    r12b, r12b
0x180083b3b  jz      short loc_180083B50
0x180083b3d  xor     edx, edx; uiParam
0x180083b3f  lea     r8, [rsp+2D0h+Data]; pvParam
0x180083b44  xor     r9d, r9d; fWinIni
0x180083b47  lea     ecx, [rdx+5Ah]; uiAction
0x180083b4a  call    cs:__imp_SystemParametersInfoW
0x180083b50  mov     eax, edi
0x180083b52  mov     rcx, [rbp+1D0h+var_40]
0x180083b59  xor     rcx, rsp; StackCookie
0x180083b5c  call    __security_check_cookie
0x180083b61  mov     rbx, [rsp+2D0h+arg_18]
0x180083b69  add     rsp, 2A0h
0x180083b70  pop     r15
0x180083b72  pop     r14
0x180083b74  pop     r13
0x180083b76  pop     r12
0x180083b78  pop     rdi
0x180083b79  pop     rsi
0x180083b7a  pop     rbp
0x180083b7b  retn
```
