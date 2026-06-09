# UndoForUicc

- ea: `0x180035c34`
- end: `0x18003628e`
- name: `UndoForUicc`
- size: `1626`
- prototype: `__int64 __fastcall(HKEY hKey, LPCWSTR lpSubKey)`
- caller_count: `2`
- callee_count: `13`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180034c20`
- `0x180035bb0`

## callees

- `0x18000108c`
- `0x1800017c4`
- `0x1800041a4`
- `0x180004894`
- `0x18000dfb0`
- `0x18000e308`
- `0x180012390`
- `0x180012d80`
- `0x18003303c`
- `0x180034224`
- `0x180035c34`
- `0x18003b9a0`
- `0x18003f010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1800360d4`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800360d4`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180035c7d`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180035c7d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003615b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003615b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180035d2a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180035d2a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180035da5`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180035f3a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180035da5`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180035f3a`

## pseudocode

```c
// Hidden C++ exception states: #wind=17
LSTATUS __fastcall UndoForUicc(HKEY hKey, LPCWSTR lpSubKey)
{
  int v4; // r14d
  unsigned int v5; // eax
  __int64 v6; // r9
  HRESULT v7; // eax
  int v8; // eax
  _QWORD *i; // rbx
  _QWORD *v10; // rdi
  int v11; // eax
  int v12; // eax
  LPVOID v13; // rcx
  wil *v14; // rcx
  const WCHAR *v15; // rax
  HRESULT v16; // eax
  void **v17; // rdx
  int v18; // eax
  int v19; // eax
  int v20; // eax
  int v21; // eax
  int v22; // eax
  __int64 v23; // rcx
  __int64 v24; // rcx
  const WCHAR *v25; // rcx
  LPVOID v26; // rcx
  LSTATUS result; // eax
  int v28; // eax
  unsigned int phkResult; // [rsp+20h] [rbp-F8h]
  int *phkResulta; // [rsp+20h] [rbp-F8h]
  int phkResultb; // [rsp+20h] [rbp-F8h]
  LPVOID ppv; // [rsp+30h] [rbp-E8h] BYREF
  int v33; // [rsp+38h] [rbp-E0h] BYREF
  LPVOID v34; // [rsp+40h] [rbp-D8h] BYREF
  const WCHAR *v35; // [rsp+48h] [rbp-D0h] BYREF
  __int64 v36; // [rsp+50h] [rbp-C8h] BYREF
  int v37[2]; // [rsp+58h] [rbp-C0h] BYREF
  HKEY hKeya; // [rsp+60h] [rbp-B8h] BYREF
  __int128 v39; // [rsp+68h] [rbp-B0h] BYREF
  __int64 v40; // [rsp+78h] [rbp-A0h]
  const WCHAR *v41[2]; // [rsp+80h] [rbp-98h] BYREF
  char v42; // [rsp+90h] [rbp-88h]
  int v43; // [rsp+98h] [rbp-80h]
  char v44; // [rsp+9Ch] [rbp-7Ch]
  GUID v45; // [rsp+A0h] [rbp-78h] BYREF
  void *v46[3]; // [rsp+C0h] [rbp-58h] BYREF
  unsigned __int64 v47; // [rsp+D8h] [rbp-40h]
  LPVOID *p_ppv; // [rsp+E0h] [rbp-38h]
  __int64 v49; // [rsp+E8h] [rbp-30h]
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+0h]

  v4 = 0;
  v43 = 0;
  v44 = 0;
  if ( (unsigned int)dword_180052170 <= 4 )
    v45 = 0;
  else
    EventActivityIdControl(3u, &v45);
  v43 = 1;
  if ( (unsigned int)dword_180052170 > 4 )
  {
    v35 = lpSubKey;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
      (__int64)&dword_180052170,
      (__int64)byte_180049C05,
      (__int64)&v45,
      0,
      &v35);
  }
  hKeya = 0;
  v5 = RegOpenKeyExW(hKey, lpSubKey, 0, 9u, &hKeya);
  try
  {
    if ( v5 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x9F,
        (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\uicc2\\knownuicc.cpp",
        (const char *)v5,
        phkResult);
    v39 = 0;
    v40 = 0;
    ForEachRegSubKey__lambda_3ddd81ec77697d34789de4e1aa63f939_(hKeya);
    if ( (_QWORD)v39 != *((_QWORD *)&v39 + 1) )
    {
      LOBYTE(v6) = 0;
      std::_Sort_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short________int64__lambda_7d45352acf67761f3fc783ae7a961498___(
        v39,
        *((_QWORD *)&v39 + 1),
        (__int64)(*((_QWORD *)&v39 + 1) - v39) >> 5,
        v6);
      ppv = 0;
      v7 = CoCreateInstance(
             &GUID_66d0db14_5638_475f_a386_629522d8c461,
             0,
             1u,
             &GUID_56a4bdd5_835a_4dd5_95b5_44805ca37db0,
             &ppv);
      if ( v7 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xD0,
          (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\uicc2\\knownuicc.cpp",
          (const char *)(unsigned int)v7,
          (int)phkResulta);
      v8 = (*(__int64 (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 56LL))(ppv);
      if ( v8 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xD1,
          (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\uicc2\\knownuicc.cpp",
          (const char *)(unsigned int)v8,
          (int)phkResulta);
      v41[1] = (const WCHAR *)&ppv;
      v42 = 1;
      v10 = (_QWORD *)*((_QWORD *)&v39 + 1);
      for ( i = (_QWORD *)v39; i != v10; i += 4 )
      {
        v47 = 7;
        v46[2] = 0;
        LOWORD(v46[0]) = 0;
        std::wstring::assign(v46, (char *)L"./Vendor/MSFT/", 0xEu);
        std::wstring::append(v46, i, 0, 0xFFFFFFFFFFFFFFFFuLL);
        if ( (unsigned int)dword_180052170 > 5 )
        {
          v15 = (const WCHAR *)v46;
          if ( v47 >= 8 )
            v15 = (const WCHAR *)v46[0];
          v41[0] = v15;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
            (__int64)&dword_180052170,
            (__int64)&word_180049BDE,
            0,
            0,
            v41);
        }
        v34 = 0;
        v16 = CoCreateInstance(
                &GUID_50a41ef1_6bfa_4b7e_973e_798ea0bebad4,
                0,
                1u,
                &GUID_e34e5896_40b2_45c4_a9c0_8a9601c3b0a6,
                &v34);
        if ( v16 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0xE2,
            (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\uicc2\\knownuicc.cpp",
            (const char *)(unsigned int)v16,
            phkResultb);
        v17 = v46;
        if ( v47 >= 8 )
          v17 = (void **)v46[0];
        v18 = (*(__int64 (__fastcall **)(LPVOID, void **))(*(_QWORD *)v34 + 40LL))(v34, v17);
        if ( v18 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0xE3,
            (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\uicc2\\knownuicc.cpp",
            (const char *)(unsigned int)v18,
            phkResultb);
        v33 = 0;
        v19 = (*(__int64 (__fastcall **)(LPVOID, int *))(*(_QWORD *)v34 + 136LL))(v34, &v33);
        if ( v19 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0xE7,
            (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\uicc2\\knownuicc.cpp",
            (const char *)(unsigned int)v19,
            phkResultb);
        v35 = 0;
        *(_QWORD *)v37 = 0;
        phkResulta = v37;
        v20 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, _QWORD, const WCHAR **))(*(_QWORD *)v34 + 80LL))(
                v34,
                (unsigned int)(v33 - 1),
                0,
                &v35);
        if ( v20 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0xEB,
            (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\uicc2\\knownuicc.cpp",
            (const char *)(unsigned int)v20,
            (int)v37);
        v36 = 0;
        v21 = (*(__int64 (__fastcall **)(LPVOID, const WCHAR *, __int64 *))(*(_QWORD *)ppv + 88LL))(ppv, v35, &v36);
        if ( v21 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0xEF,
            (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\uicc2\\knownuicc.cpp",
            (const char *)(unsigned int)v21,
            (int)v37);
        v22 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v36 + 80LL))(v36, *(_QWORD *)v37);
        if ( v22 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0xF0,
            (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\uicc2\\knownuicc.cpp",
            (const char *)(unsigned int)v22,
            (int)v37);
        v23 = v36;
        if ( v36 )
        {
          v36 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
        }
        v24 = *(_QWORD *)v37;
        if ( *(_QWORD *)v37 )
        {
          *(_QWORD *)v37 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
        }
        v25 = v35;
        if ( v35 )
        {
          v35 = 0;
          (*(void (__fastcall **)(const WCHAR *))(*(_QWORD *)v25 + 16LL))(v25);
        }
        v26 = v34;
        if ( v34 )
        {
          v34 = 0;
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v26 + 16LL))(v26);
        }
        if ( v47 >= 8 )
          operator delete(v46[0]);
      }
      v11 = (*(__int64 (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 64LL))(ppv);
      if ( v11 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xF3,
          (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\uicc2\\knownuicc.cpp",
          (const char *)(unsigned int)v11,
          (int)phkResulta);
      v42 = 0;
      v12 = (*(__int64 (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 24LL))(ppv);
      if ( v12 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xF6,
          (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\uicc2\\knownuicc.cpp",
          (const char *)(unsigned int)v12,
          (int)phkResulta);
      v13 = ppv;
      if ( ppv )
      {
        ppv = 0;
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v13 + 16LL))(v13);
      }
    }
    std::vector<std::wstring>::_Tidy((__int64)&v39);
  }
  catch ( ... )
  {
    v28 = wil::ResultFromCaughtException(v14);
    LODWORD(ppv) = v28;
    if ( (unsigned int)dword_180052170 > 2 )
    {
      v33 = v28;
      p_ppv = (LPVOID *)&v33;
      v49 = 4;
      tlgWriteTransfer_EventWriteTransfer(&dword_180052170, &byte_180049BA7, &v45, 0, 3, v46);
    }
    v4 = (int)ppv;
  }
  v43 = 2;
  result = dword_180052170;
  if ( (unsigned int)dword_180052170 > 4 )
  {
    LODWORD(ppv) = v4;
    p_ppv = &ppv;
    v49 = 4;
    result = tlgWriteTransfer_EventWriteTransfer(&dword_180052170, &word_180049B76, &v45, 0, 3, v46);
  }
  if ( hKeya )
    result = RegCloseKey(hKeya);
  if ( v43 == 1 )
  {
    v43 = 2;
    return _tlgWriteActivityAutoStop<0,4>((unsigned int *)&dword_180052170, (__int64)&v45);
  }
  return result;
}

```

## disassembly

```asm
0x180035c34  mov     r11, rsp
0x180035c37  mov     [r11+18h], rbx
0x180035c3b  push    rsi
0x180035c3c  push    rdi
0x180035c3d  push    r14
0x180035c3f  sub     rsp, 100h
0x180035c46  mov     rax, cs:__security_cookie
0x180035c4d  xor     rax, rsp
0x180035c50  mov     [rsp+118h+var_28], rax
0x180035c58  mov     rbx, rdx
0x180035c5b  mov     rdi, rcx
0x180035c5e  xor     esi, esi
0x180035c60  mov     r14d, esi
0x180035c63  mov     [r11-80h], esi
0x180035c67  mov     [r11-7Ch], sil
0x180035c6b  mov     eax, cs:dword_180052170
0x180035c71  cmp     eax, 4
0x180035c74  jbe     short loc_180035C85
0x180035c76  lea     rdx, [r11-78h]; ActivityId
0x180035c7a  lea     ecx, [rsi+3]; ControlCode
0x180035c7d  call    cs:__imp_EventActivityIdControl
0x180035c83  jmp     short loc_180035C90
0x180035c85  xorps   xmm0, xmm0
0x180035c88  movups  [rsp+118h+var_78], xmm0
0x180035c90  mov     [rsp+118h+var_80], 1
0x180035c9b  mov     eax, cs:dword_180052170
0x180035ca1  cmp     eax, 4
0x180035ca4  jbe     short loc_180035D0C
0x180035ca6  mov     [rsp+118h+var_D0], rbx
0x180035cab  cmp     [rsp+118h+var_7C], sil
0x180035cb3  jz      short loc_180035CE3
0x180035cb5  cmp     [rsp+118h+var_68], esi
0x180035cbc  jnz     short loc_180035CD9
0x180035cbe  cmp     [rsp+118h+var_64], esi
0x180035cc5  jnz     short loc_180035CD9
0x180035cc7  cmp     [rsp+118h+var_60], esi
0x180035cce  jnz     short loc_180035CD9
0x180035cd0  cmp     [rsp+118h+var_5C], esi
0x180035cd7  jz      short loc_180035CE3
0x180035cd9  lea     r9, [rsp+118h+var_68]
0x180035ce1  jmp     short loc_180035CE6
0x180035ce3  mov     r9, rsi
0x180035ce6  lea     rax, [rsp+118h+var_D0]
0x180035ceb  mov     [rsp+118h+phkResult], rax
0x180035cf0  lea     r8, [rsp+118h+var_78]
0x180035cf8  lea     rdx, byte_180049C05
0x180035cff  lea     rcx, dword_180052170
0x180035d06  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x180035d0b  nop
0x180035d0c  mov     [rsp+118h+hKey], rsi
0x180035d11  lea     rax, [rsp+118h+hKey]
0x180035d16  mov     [rsp+118h+phkResult], rax; unsigned int
0x180035d1b  mov     r9d, 9; samDesired
0x180035d21  xor     r8d, r8d; ulOptions
0x180035d24  mov     rdx, rbx; lpSubKey
0x180035d27  mov     rcx, rdi; hKey
0x180035d2a  call    cs:__imp_RegOpenKeyExW
0x180035d30  mov     rcx, [rsp+118h]; this
0x180035d38  test    eax, eax
0x180035d3a  jnz     loc_1800361AB
0x180035d40  xorps   xmm0, xmm0
0x180035d43  movdqu  [rsp+118h+var_B0], xmm0
0x180035d49  mov     [rsp+118h+var_A0], rsi
0x180035d4e  lea     rdx, [rsp+118h+var_B0]
0x180035d53  mov     rcx, [rsp+118h+hKey]; hKey
0x180035d58  call    ForEachRegSubKey__lambda_3ddd81ec77697d34789de4e1aa63f939___; ForEachRegSubKey__lambda_3ddd81ec77697d34789de4e1aa63f939_
0x180035d5d  mov     rcx, qword ptr [rsp+118h+var_B0]
0x180035d62  mov     rdx, qword ptr [rsp+118h+var_B0+8]
0x180035d67  cmp     rcx, rdx
0x180035d6a  jz      loc_180035E66
0x180035d70  mov     r8, rdx
0x180035d73  sub     r8, rcx
0x180035d76  sar     r8, 5
0x180035d7a  mov     r9b, sil
0x180035d7d  call    std___Sort_std__basic_string_unsigned_short_std__char_traits_unsigned_short__std__allocator_unsigned_short________int64__lambda_7d45352acf67761f3fc783ae7a961498___
0x180035d82  mov     [rsp+118h+ppv], rsi
0x180035d87  lea     rax, [rsp+118h+ppv]
0x180035d8c  mov     [rsp+118h+phkResult], rax; int
0x180035d91  lea     r9, _GUID_56a4bdd5_835a_4dd5_95b5_44805ca37db0; riid
0x180035d98  xor     edx, edx; pUnkOuter
0x180035d9a  lea     r8d, [rdx+1]; dwClsContext
0x180035d9e  lea     rcx, _GUID_66d0db14_5638_475f_a386_629522d8c461; rclsid
0x180035da5  call    cs:__imp_CoCreateInstance
0x180035dab  mov     rcx, [rsp+118h]; this
0x180035db3  test    eax, eax
0x180035db5  js      loc_1800361C0
0x180035dbb  mov     rcx, [rsp+118h+ppv]
0x180035dc0  mov     rax, [rcx]
0x180035dc3  mov     rax, [rax+38h]
0x180035dc7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035dcc  mov     rcx, [rsp+118h]; this
0x180035dd4  test    eax, eax
0x180035dd6  js      loc_1800361D4
0x180035ddc  lea     rax, [rsp+118h+ppv]
0x180035de1  mov     [rsp+118h+var_90], rax
0x180035de9  mov     [rsp+118h+var_88], 1
0x180035df1  mov     rbx, qword ptr [rsp+118h+var_B0]
0x180035df6  mov     rdi, qword ptr [rsp+118h+var_B0+8]
0x180035dfb  cmp     rbx, rdi
0x180035dfe  jnz     short loc_180035E76
0x180035e00  mov     rcx, [rsp+118h+ppv]
0x180035e05  mov     rax, [rcx]
0x180035e08  mov     rax, [rax+40h]
0x180035e0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035e11  mov     rcx, [rsp+118h]; this
0x180035e19  test    eax, eax
0x180035e1b  js      loc_1800361E9
0x180035e21  mov     [rsp+118h+var_88], sil
0x180035e29  mov     rcx, [rsp+118h+ppv]
0x180035e2e  mov     rax, [rcx]
0x180035e31  mov     rax, [rax+18h]
0x180035e35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035e3a  mov     rcx, [rsp+118h]; this
0x180035e42  test    eax, eax
0x180035e44  js      loc_1800361FD
0x180035e4a  mov     rcx, [rsp+118h+ppv]
0x180035e4f  test    rcx, rcx
0x180035e52  jz      short loc_180035E66
0x180035e54  mov     [rsp+118h+ppv], rsi
0x180035e59  mov     rax, [rcx]
0x180035e5c  mov     rax, [rax+10h]
0x180035e60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035e65  nop
0x180035e66  lea     rcx, [rsp+118h+var_B0]
0x180035e6b  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@IEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x180035e70  nop
0x180035e71  jmp     loc_1800360E8
0x180035e76  mov     [rsp+118h+var_40], 7
0x180035e82  mov     [rsp+118h+var_48], rsi
0x180035e8a  mov     word ptr [rsp+118h+var_58], si
0x180035e92  mov     r8d, 0Eh
0x180035e98  lea     rdx, aVendorMsft; "./Vendor/MSFT/"
0x180035e9f  lea     rcx, [rsp+118h+var_58]; void *
0x180035ea7  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x180035eac  nop
0x180035ead  or      r9, 0FFFFFFFFFFFFFFFFh
0x180035eb1  xor     r8d, r8d
0x180035eb4  mov     rdx, rbx
0x180035eb7  lea     rcx, [rsp+118h+var_58]
0x180035ebf  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::append(std::wstring const &,unsigned __int64,unsigned __int64)
0x180035ec4  mov     eax, cs:dword_180052170
0x180035eca  cmp     eax, 5
0x180035ecd  jbe     short loc_180035F17
0x180035ecf  lea     rax, [rsp+118h+var_58]
0x180035ed7  cmp     [rsp+118h+var_40], 8
0x180035ee0  cmovnb  rax, [rsp+118h+var_58]
0x180035ee9  mov     [rsp+118h+var_98], rax
0x180035ef1  lea     rax, [rsp+118h+var_98]
0x180035ef9  mov     [rsp+118h+phkResult], rax
0x180035efe  xor     r9d, r9d
0x180035f01  xor     r8d, r8d
0x180035f04  lea     rdx, word_180049BDE
0x180035f0b  lea     rcx, dword_180052170
0x180035f12  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x180035f17  mov     [rsp+118h+var_D8], rsi
0x180035f1c  lea     rax, [rsp+118h+var_D8]
0x180035f21  mov     [rsp+118h+phkResult], rax; int
0x180035f26  lea     r9, _GUID_e34e5896_40b2_45c4_a9c0_8a9601c3b0a6; riid
0x180035f2d  xor     edx, edx; pUnkOuter
0x180035f2f  lea     r8d, [rdx+1]; dwClsContext
0x180035f33  lea     rcx, _GUID_50a41ef1_6bfa_4b7e_973e_798ea0bebad4; rclsid
0x180035f3a  call    cs:__imp_CoCreateInstance
0x180035f40  mov     rcx, [rsp+118h]; this
0x180035f48  test    eax, eax
0x180035f4a  js      loc_180036212
0x180035f50  mov     rcx, [rsp+118h+var_D8]
0x180035f55  mov     rax, [rcx]
0x180035f58  lea     rdx, [rsp+118h+var_58]
0x180035f60  cmp     [rsp+118h+var_40], 8
0x180035f69  cmovnb  rdx, [rsp+118h+var_58]
0x180035f72  mov     rax, [rax+28h]
0x180035f76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035f7b  mov     rcx, [rsp+118h]; this
0x180035f83  test    eax, eax
0x180035f85  js      loc_180036226
0x180035f8b  mov     [rsp+118h+var_E0], esi
0x180035f8f  mov     rcx, [rsp+118h+var_D8]
0x180035f94  mov     rax, [rcx]
0x180035f97  lea     rdx, [rsp+118h+var_E0]
0x180035f9c  mov     rax, [rax+88h]
0x180035fa3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035fa8  mov     rcx, [rsp+118h]; this
0x180035fb0  test    eax, eax
0x180035fb2  js      loc_18003623A
0x180035fb8  mov     [rsp+118h+var_D0], rsi
0x180035fbd  mov     qword ptr [rsp+118h+var_C0], rsi
0x180035fc2  mov     rcx, [rsp+118h+var_D8]
0x180035fc7  mov     rax, [rcx]
0x180035fca  mov     edx, [rsp+118h+var_E0]
0x180035fce  dec     edx
0x180035fd0  lea     r8, [rsp+118h+var_C0]
0x180035fd5  mov     [rsp+118h+phkResult], r8; int
0x180035fda  lea     r9, [rsp+118h+var_D0]
0x180035fdf  xor     r8d, r8d
0x180035fe2  mov     rax, [rax+50h]
0x180035fe6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035feb  mov     rcx, [rsp+118h]; this
0x180035ff3  test    eax, eax
0x180035ff5  js      loc_18003624F
0x180035ffb  mov     [rsp+118h+var_C8], rsi
0x180036000  mov     rcx, [rsp+118h+ppv]
0x180036005  mov     rax, [rcx]
0x180036008  lea     r8, [rsp+118h+var_C8]
0x18003600d  mov     rdx, [rsp+118h+var_D0]
0x180036012  mov     rax, [rax+58h]
0x180036016  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003601b  mov     rcx, [rsp+118h]; this
0x180036023  test    eax, eax
0x180036025  js      loc_180036264
0x18003602b  mov     rcx, [rsp+118h+var_C8]
0x180036030  mov     rax, [rcx]
0x180036033  mov     rdx, qword ptr [rsp+118h+var_C0]
0x180036038  mov     rax, [rax+50h]
0x18003603c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036041  mov     rcx, [rsp+118h]; this
0x180036049  test    eax, eax
0x18003604b  js      loc_180036278
0x180036051  mov     rcx, [rsp+118h+var_C8]
0x180036056  test    rcx, rcx
0x180036059  jz      short loc_18003606D
0x18003605b  mov     [rsp+118h+var_C8], rsi
0x180036060  mov     rax, [rcx]
0x180036063  mov     rax, [rax+10h]
0x180036067  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003606c  nop
0x18003606d  mov     rcx, qword ptr [rsp+118h+var_C0]
0x180036072  test    rcx, rcx
0x180036075  jz      short loc_180036089
0x180036077  mov     qword ptr [rsp+118h+var_C0], rsi
0x18003607c  mov     rax, [rcx]
0x18003607f  mov     rax, [rax+10h]
0x180036083  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036088  nop
0x180036089  mov     rcx, [rsp+118h+var_D0]
0x18003608e  test    rcx, rcx
0x180036091  jz      short loc_1800360A5
0x180036093  mov     [rsp+118h+var_D0], rsi
0x180036098  mov     rax, [rcx]
0x18003609b  mov     rax, [rax+10h]
0x18003609f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800360a4  nop
0x1800360a5  mov     rcx, [rsp+118h+var_D8]
0x1800360aa  test    rcx, rcx
0x1800360ad  jz      short loc_1800360C1
0x1800360af  mov     [rsp+118h+var_D8], rsi
0x1800360b4  mov     rax, [rcx]
0x1800360b7  mov     rax, [rax+10h]
0x1800360bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800360c0  nop
0x1800360c1  cmp     [rsp+118h+var_40], 8
0x1800360ca  jb      short loc_1800360DA
0x1800360cc  mov     rcx, [rsp+118h+var_58]
0x1800360d4  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800360da  add     rbx, 20h ; ' '
0x1800360de  jmp     loc_180035DFB
0x1800360e3  mov     r14d, dword ptr [rsp+118h+ppv]
0x1800360e8  mov     ebx, 2
0x1800360ed  mov     [rsp+118h+var_80], ebx
0x1800360f4  mov     eax, cs:dword_180052170
0x1800360fa  cmp     eax, 4
0x1800360fd  jbe     short loc_180036151
0x1800360ff  mov     dword ptr [rsp+118h+ppv], r14d
0x180036104  lea     rax, [rsp+118h+ppv]
0x180036109  mov     [rsp+118h+var_38], rax
0x180036111  mov     [rsp+118h+var_30], 4
0x18003611d  lea     rax, [rsp+118h+var_58]
0x180036125  mov     [rsp+118h+var_F0], rax
0x18003612a  mov     dword ptr [rsp+118h+phkResult], 3
0x180036132  xor     r9d, r9d
0x180036135  lea     r8, [rsp+118h+var_78]
0x18003613d  lea     rdx, word_180049B76
0x180036144  lea     rcx, dword_180052170
0x18003614b  call    _tlgWriteTransfer_EventWriteTransfer
0x180036150  nop
0x180036151  mov     rcx, [rsp+118h+hKey]; hKey
0x180036156  test    rcx, rcx
0x180036159  jz      short loc_180036162
0x18003615b  call    cs:__imp_RegCloseKey
0x180036161  nop
0x180036162  cmp     [rsp+118h+var_80], 1
0x18003616a  jnz     short loc_180036187
0x18003616c  mov     [rsp+118h+var_80], ebx
0x180036173  lea     rdx, [rsp+118h+var_78]
0x18003617b  lea     rcx, dword_180052170
0x180036182  call    ??$_tlgWriteActivityAutoStop@$0A@$03@@YAXPEBU_tlgProvider_t@@PEBU_GUID@@@Z; _tlgWriteActivityAutoStop<0,4>(_tlgProvider_t const *,_GUID const *)
0x180036187  mov     rcx, [rsp+118h+var_28]
0x18003618f  xor     rcx, rsp; StackCookie
0x180036192  call    __security_check_cookie
0x180036197  mov     rbx, [rsp+118h+arg_10]
0x18003619f  add     rsp, 100h
0x1800361a6  pop     r14
0x1800361a8  pop     rdi
0x1800361a9  pop     rsi
0x1800361aa  retn
0x1800361ab  mov     r9d, eax; char *
0x1800361ae  lea     r8, aOnecoreuapAdmi_15; "onecoreuap\\admin\\prov\\multivariant\\"...
0x1800361b5  mov     edx, 9Fh; void *
0x1800361ba  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1800361c0  mov     r9d, eax; char *
0x1800361c3  lea     r8, aOnecoreuapAdmi_15; "onecoreuap\\admin\\prov\\multivariant\\"...
  ... truncated ...
```
