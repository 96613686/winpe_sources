# CommitProtectPCSettingsCore(bool *,bool *,uint,OOBE_PROTECTPC_COMMIT_ENTRY const *,bool,bool)

- ea: `0x1800464fc`
- end: `0x180046bc2`
- name: `?CommitProtectPCSettingsCore@@YAJPEA_N0IPEBUOOBE_PROTECTPC_COMMIT_ENTRY@@_N2@Z`
- size: `1734`
- prototype: `__int64 __fastcall(bool *, bool *, unsigned int, const struct OOBE_PROTECTPC_COMMIT_ENTRY *, bool, bool)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180046bd0`

## callees

- `0x180003470`
- `0x18001ad08`
- `0x18001de58`
- `0x18001e9a4`
- `0x18001ea00`
- `0x1800230b0`
- `0x180023574`
- `0x1800235c8`
- `0x180040898`
- `0x180042068`
- `0x1800464fc`
- `0x180046c9c`
- `0x180046cd8`
- `0x180046de8`
- `0x1800b8834`
- `0x1800c4010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180046af9`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180046af9`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180046aa0`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180046aa0`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800466f2`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800466f2`

## string_xrefs

- `0x1800466d2`: `Windows.Internal.CapabilityAccess.Management.CapabilityConsentManager`
- `0x180046962`: `ProtectPC Task - setting %s value to (%d)`
- `0x180046a4d`: `ProtectPC Task - setting %s value for Wow64`
- `0x180046859`: `ProtectPC Task - setting %s value to (%s)`
- `0x180046814`: `ProtectPC Task - setting %s capability to value %s via CAM %s`
- `0x18004660c`: `ProtectPC Task - Encountered unexpected entryType (%d)`
- `0x180046b67`: `ProtectPC Task - Leaving default state in place for %s value`
- `0x1800466ae`: `ProtectPC Task - setting %s to value %s via custom commit function %s with 0x%d`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall CommitProtectPCSettingsCore(
        bool *a1,
        bool *a2,
        unsigned int a3,
        const struct OOBE_PROTECTPC_COMMIT_ENTRY *a4)
{
  unsigned int v4; // esi
  unsigned int v6; // r13d
  __int64 v7; // rcx
  __m128i v8; // xmm6
  __m128i v9; // xmm7
  __m128i v10; // xmm8
  __m128i v11; // xmm2
  __m128i v12; // xmm1
  __int64 (__fastcall *v13)(_QWORD); // xmm3_8
  int v14; // eax
  __int64 v15; // r15
  char v16; // di
  bool v17; // dl
  __int64 v18; // rcx
  signed int v19; // ebx
  __int64 v20; // rdx
  __int64 v21; // rdx
  const wchar_t *v22; // rax
  const wchar_t *v23; // r9
  int ActivationFactory; // eax
  char v25; // r8
  unsigned __int16 *v26; // rdi
  __int64 (__fastcall *v27)(unsigned __int16 *, PVOID, BYTE *); // rbx
  HSTRING_HEADER *v28; // rax
  int v29; // eax
  char v30; // al
  int v31; // eax
  unsigned __int8 v32; // cl
  const wchar_t *v33; // rax
  const wchar_t *v34; // r9
  const unsigned __int16 *v35; // rdi
  unsigned __int64 v36; // xmm2_8
  const unsigned __int16 *v37; // rsi
  int v38; // eax
  int RedirectionKeyPath; // eax
  wil::details::in1diag3 *v40; // rcx
  __int64 v41; // rdx
  int v42; // r9d
  int v43; // eax
  const unsigned __int16 *v44; // rsi
  int v45; // eax
  int v46; // eax
  wil::details::in1diag3 *v47; // rcx
  __int64 v48; // rdx
  LSTATUS v49; // eax
  unsigned int v50; // eax
  void (__fastcall *v51)(_QWORD, __int64); // xmm8_8
  unsigned int dwOptions; // [rsp+20h] [rbp-E0h]
  int dwOptionsa; // [rsp+20h] [rbp-E0h]
  __int64 samDesired; // [rsp+28h] [rbp-D8h]
  bool v56; // [rsp+50h] [rbp-B0h] BYREF
  BYTE Data[8]; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int16 *v58; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v59; // [rsp+68h] [rbp-98h]
  HKEY hKey; // [rsp+70h] [rbp-90h] BYREF
  const struct OOBE_PROTECTPC_COMMIT_ENTRY *v61; // [rsp+78h] [rbp-88h]
  bool *v62; // [rsp+80h] [rbp-80h]
  __m128i v63; // [rsp+90h] [rbp-70h]
  _OWORD v64[4]; // [rsp+A0h] [rbp-60h] BYREF
  __int64 (__fastcall *v65)(_QWORD); // [rsp+E0h] [rbp-20h]
  HSTRING_HEADER hstringHeader; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v67; // [rsp+108h] [rbp+8h]
  wil::details::in1diag3 *retaddr; // [rsp+188h] [rbp+88h]

  v61 = a4;
  v4 = a3;
  v59 = a3;
  v62 = a2;
  v6 = 0;
  if ( a3 )
  {
    while ( 1 )
    {
      v7 = 88LL * v6;
      v8 = *(__m128i *)((char *)a4 + v7);
      v63 = v8;
      v9 = *(__m128i *)((char *)a4 + v7 + 16);
      v64[0] = v9;
      v10 = *(__m128i *)((char *)a4 + v7 + 32);
      v64[1] = v10;
      v11 = *(__m128i *)((char *)a4 + v7 + 48);
      v64[2] = v11;
      v12 = *(__m128i *)((char *)a4 + v7 + 64);
      v64[3] = v12;
      v13 = *(__int64 (__fastcall **)(_QWORD))((char *)a4 + v7 + 80);
      v65 = v13;
      v14 = _mm_cvtsi128_si32(v8);
      v15 = v14;
      if ( a2[v14] )
      {
        v16 = _mm_cvtsi128_si32(_mm_srli_si128(v12, 8));
        if ( (v16 & 4) != 0 )
        {
          v17 = a1[v14];
          if ( v17 || (v16 & 1) == 0 )
            break;
        }
      }
      UnattendLogW(
        0,
        L"ProtectPC Task - Leaving default state in place for %s value",
        _mm_srli_si128(v9, 8).m128i_u64[0]);
LABEL_71:
      ++v6;
      a4 = v61;
      a2 = v62;
      if ( v6 >= v4 )
        return 0;
    }
    if ( v8.m128i_i32[1] )
    {
      if ( v8.m128i_i32[1] != 1 )
      {
        if ( v8.m128i_i32[1] != 2 )
        {
          v18 = (unsigned int)(v8.m128i_i32[1] - 3);
          if ( v8.m128i_i32[1] == 3 )
          {
            LODWORD(v18) = v17;
            v19 = ((__int64 (__fastcall *)(__int64))v10.m128i_i64[0])(v18);
            if ( v19 < 0 )
            {
              v21 = 297;
              goto LABEL_16;
            }
          }
          else
          {
            if ( v8.m128i_i32[1] != 4 )
            {
              v19 = 0;
              UnattendLogW(1, L"ProtectPC Task - Encountered unexpected entryType (%d)");
              goto LABEL_68;
            }
            v19 = v13(a1[v14]);
            if ( v19 < 0 )
            {
              v21 = 304;
LABEL_16:
              wil::details::in1diag3::_Log_Hr(
                retaddr,
                (void *)v21,
                (unsigned int)"onecoreuap\\internal\\shell\\inc\\oobesettingsutil.h",
                (const char *)(unsigned int)v19,
                dwOptions);
            }
          }
          v22 = L"succeeded";
          if ( v19 < 0 )
            v22 = L"failed";
          v23 = L"enabled";
          if ( !a1[v15] )
            v23 = L"disabled";
          LODWORD(samDesired) = v19;
          UnattendLogW(
            (v19 >> 31) & 2,
            L"ProtectPC Task - setting %s to value %s via custom commit function %s with 0x%d",
            `CanonicalNameFromProtectPcId'::`2'::canonicalNames[v15],
            v23,
            v22,
            samDesired);
          goto LABEL_68;
        }
        v58 = 0;
        v67 = 0;
        Microsoft::WRL::Wrappers::HStringReference::CreateReference(
          &hstringHeader,
          L"Windows.Internal.CapabilityAccess.Management.CapabilityConsentManager",
          0x46u,
          0x45u);
        ActivationFactory = RoGetActivationFactory(v67, &GUID_ef1a89c8_29b1_4ab0_94a7_851b33527a2e, &v58);
        v19 = ActivationFactory;
        if ( ActivationFactory >= 0 )
        {
          *(_QWORD *)Data = 0;
          v26 = v58;
          v27 = *(__int64 (__fastcall **)(unsigned __int16 *, PVOID, BYTE *))(*(_QWORD *)v58 + 48LL);
          *(_QWORD *)Data = 0;
          v28 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
                  &hstringHeader,
                  (const WCHAR **)v64 + 1,
                  v25);
          v29 = v27(v26, v28[1].Reserved.Reserved1, Data);
          v19 = v29;
          if ( v29 >= 0 )
          {
            v30 = 1;
          }
          else
          {
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x105,
              (unsigned int)"onecoreuap\\internal\\shell\\inc\\oobesettingsutil.h",
              (const char *)(unsigned int)v29,
              dwOptions);
            v30 = 0;
          }
          if ( v30 )
          {
            v31 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)Data + 112LL))(
                    *(_QWORD *)Data,
                    2 - (unsigned int)a1[v15]);
            v19 = v31;
            if ( v31 < 0 )
              wil::details::in1diag3::_Log_Hr(
                retaddr,
                (void *)0x10D,
                (unsigned int)"onecoreuap\\internal\\shell\\inc\\oobesettingsutil.h",
                (const char *)(unsigned int)v31,
                dwOptions);
          }
          wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(Data);
          v32 = 1;
          if ( v19 >= 0 )
            goto LABEL_32;
        }
        else
        {
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x102,
            (unsigned int)"onecoreuap\\internal\\shell\\inc\\oobesettingsutil.h",
            (const char *)(unsigned int)ActivationFactory,
            dwOptions);
        }
        v32 = 0;
LABEL_32:
        v33 = L"succeeded";
        if ( !v32 )
          v33 = L"failed";
        v34 = L"Allow";
        if ( !a1[v15] )
          v34 = L"Deny";
        UnattendLogW(
          2 * (v32 ^ 1u),
          L"ProtectPC Task - setting %s capability to value %s via CAM %s",
          _mm_srli_si128(v9, 8).m128i_u64[0],
          v34,
          v33);
        wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(&v58);
        goto LABEL_68;
      }
      v35 = (const unsigned __int16 *)v12.m128i_i64[0];
      v36 = _mm_srli_si128(v11, 8).m128i_u64[0];
      if ( v17 )
        v35 = (const unsigned __int16 *)v36;
      v37 = (const unsigned __int16 *)_mm_srli_si128(v9, 8).m128i_u64[0];
      UnattendLogW(0, L"ProtectPC Task - setting %s value to (%s)", v37, v35);
      v38 = SHRegSetString(HKEY_LOCAL_MACHINE, (const unsigned __int16 *)v9.m128i_i64[0], v37, v35);
      if ( v38 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0xE9,
          (unsigned int)"onecoreuap\\internal\\shell\\inc\\oobesettingsutil.h",
          (const char *)(unsigned int)v38,
          dwOptions);
      *(_QWORD *)Data = 0;
      v56 = 0;
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        Data,
        0);
      RedirectionKeyPath = Details::TryGetRedirectionKeyPath(
                             (const unsigned __int16 *)_mm_srli_si128(v8, 8).m128i_i64[0],
                             (const unsigned __int16 *)v9.m128i_i64[0],
                             (LPCWCH *)Data,
                             &v56);
      v19 = RedirectionKeyPath;
      v40 = retaddr;
      if ( RedirectionKeyPath >= 0 )
      {
        if ( !v56 )
          goto LABEL_47;
        RedirectionKeyPath = SHRegSetString(HKEY_LOCAL_MACHINE, *(const unsigned __int16 **)Data, v37, v35);
        v19 = RedirectionKeyPath;
        v40 = retaddr;
        if ( RedirectionKeyPath >= 0 )
          goto LABEL_47;
        v41 = 246;
      }
      else
      {
        v41 = 242;
      }
      wil::details::in1diag3::_Log_Hr(
        v40,
        (void *)v41,
        (unsigned int)"onecoreuap\\internal\\shell\\inc\\oobesettingsutil.h",
        (const char *)(unsigned int)RedirectionKeyPath,
        dwOptions);
LABEL_47:
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(Data);
LABEL_67:
      v4 = v59;
LABEL_68:
      v51 = (void (__fastcall *)(_QWORD, __int64))_mm_srli_si128(v10, 8).m128i_u64[0];
      if ( v51 )
      {
        LOBYTE(v20) = a1[v15];
        v51((unsigned int)v19, v20);
      }
      goto LABEL_71;
    }
    v42 = _mm_cvtsi128_si32(_mm_srli_si128(v11, 4));
    v43 = _mm_cvtsi128_si32(v11);
    if ( v17 )
      v42 = v43;
    *(_DWORD *)Data = v42;
    v44 = (const unsigned __int16 *)_mm_srli_si128(v9, 8).m128i_u64[0];
    UnattendLogW(0, L"ProtectPC Task - setting %s value to (%d)", v44);
    v45 = SHRegSetDWORD(HKEY_LOCAL_MACHINE, (const unsigned __int16 *)v9.m128i_i64[0], v44, *(unsigned int *)Data);
    if ( v45 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xC6,
        (unsigned int)"onecoreuap\\internal\\shell\\inc\\oobesettingsutil.h",
        (const char *)(unsigned int)v45,
        dwOptions);
    v58 = 0;
    v56 = 0;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &v58,
      0);
    v46 = Details::TryGetRedirectionKeyPath(
            (const unsigned __int16 *)_mm_srli_si128(v8, 8).m128i_i64[0],
            (const unsigned __int16 *)v9.m128i_i64[0],
            (LPCWCH *)&v58,
            &v56);
    v19 = v46;
    v47 = retaddr;
    if ( v46 >= 0 )
    {
      if ( !v56
        || (v46 = SHRegSetDWORD(HKEY_LOCAL_MACHINE, v58, v44, *(unsigned int *)Data), v19 = v46, v47 = retaddr, v46 >= 0) )
      {
LABEL_58:
        wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v58);
        if ( (v16 & 2) != 0 )
        {
          UnattendLogW(0, L"ProtectPC Task - setting %s value for Wow64", v44);
          hKey = 0;
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
            &hKey,
            0);
          v49 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, (LPCWSTR)v9.m128i_i64[0], 0, 0, 0, 0x202u, 0, &hKey, 0);
          v19 = v49;
          if ( v49 > 0 )
            v19 = (unsigned __int16)v49 | 0x80070000;
          if ( v19 >= 0 )
          {
            v50 = RegSetValueExW(hKey, v44, 0, 4u, Data, 4u);
            v19 = v50;
            if ( v50 )
            {
              wil::details::in1diag3::_Log_Win32(
                retaddr,
                (void *)0xDE,
                (unsigned int)"onecoreuap\\internal\\shell\\inc\\oobesettingsutil.h",
                (const char *)v50,
                dwOptions);
              if ( v19 > 0 )
                v19 = (unsigned __int16)v19 | 0x80070000;
            }
          }
          else
          {
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0xDC,
              (unsigned int)"onecoreuap\\internal\\shell\\inc\\oobesettingsutil.h",
              (const char *)(unsigned int)v19,
              dwOptionsa);
          }
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
        }
        goto LABEL_67;
      }
      v48 = 211;
    }
    else
    {
      v48 = 207;
    }
    wil::details::in1diag3::_Log_Hr(
      v47,
      (void *)v48,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\oobesettingsutil.h",
      (const char *)(unsigned int)v46,
      dwOptions);
    goto LABEL_58;
  }
  return 0;
}

```

## disassembly

```asm
0x1800464fc  mov     rax, rsp
0x1800464ff  mov     [rax+10h], rbx
0x180046503  push    rbp
0x180046504  push    rsi
0x180046505  push    rdi
0x180046506  push    r12
0x180046508  push    r13
0x18004650a  push    r14
0x18004650c  push    r15
0x18004650e  lea     rbp, [rsp-50h]
0x180046513  sub     rsp, 150h
0x18004651a  movaps  xmmword ptr [rax-48h], xmm6
0x18004651e  movaps  xmmword ptr [rax-58h], xmm7
0x180046522  movaps  xmmword ptr [rax-68h], xmm8
0x180046527  mov     rax, cs:__security_cookie
0x18004652e  xor     rax, rsp
0x180046531  mov     [rbp+80h+var_70], rax
0x180046535  mov     [rsp+180h+var_108], r9
0x18004653a  mov     esi, r8d
0x18004653d  mov     [rsp+180h+var_118], r8d
0x180046542  mov     [rbp+80h+var_100], rdx
0x180046546  mov     r12, rcx
0x180046549  xor     r14d, r14d
0x18004654c  mov     r13d, r14d
0x18004654f  test    r8d, r8d
0x180046552  jz      loc_180046B8A
0x180046558  mov     eax, r13d
0x18004655b  imul    rcx, rax, 58h ; 'X'
0x18004655f  movups  xmm6, xmmword ptr [rcx+r9]
0x180046564  movaps  [rbp+80h+var_F0], xmm6
0x180046568  movups  xmm7, xmmword ptr [rcx+r9+10h]
0x18004656e  movaps  [rbp+80h+var_E0], xmm7
0x180046572  movups  xmm8, xmmword ptr [rcx+r9+20h]
0x180046578  movaps  [rbp+80h+var_D0], xmm8
0x18004657d  movups  xmm2, xmmword ptr [rcx+r9+30h]
0x180046583  movaps  [rbp+80h+var_C0], xmm2
0x180046587  movups  xmm1, xmmword ptr [rcx+r9+40h]
0x18004658d  movaps  [rbp+80h+var_B0], xmm1
0x180046591  movsd   xmm3, qword ptr [rcx+r9+50h]
0x180046598  movsd   [rbp+80h+var_A0], xmm3
0x18004659d  movd    eax, xmm6
0x1800465a1  movsxd  r15, eax
0x1800465a4  cmp     [r15+rdx], r14b
0x1800465a8  jz      loc_180046B5D
0x1800465ae  movdqa  xmm0, xmm1
0x1800465b2  psrldq  xmm0, 8
0x1800465b7  movd    edi, xmm0
0x1800465bb  test    dil, 4
0x1800465bf  jz      loc_180046B5D
0x1800465c5  movzx   edx, byte ptr [r15+r12]
0x1800465ca  test    dl, dl
0x1800465cc  jnz     short loc_1800465D8
0x1800465ce  test    dil, 1
0x1800465d2  jnz     loc_180046B5D
0x1800465d8  movq    r8, xmm6
0x1800465dd  shr     r8, 20h
0x1800465e1  mov     ecx, r8d
0x1800465e4  test    r8d, r8d
0x1800465e7  jz      loc_180046934
0x1800465ed  sub     ecx, 1
0x1800465f0  jz      loc_180046830
0x1800465f6  sub     ecx, 1
0x1800465f9  jz      loc_1800466BF
0x1800465ff  sub     ecx, 1
0x180046602  jz      short loc_18004663B
0x180046604  cmp     ecx, 1
0x180046607  jz      short loc_180046622
0x180046609  mov     ebx, r14d
0x18004660c  lea     rdx, aProtectpcTaskE; "ProtectPC Task - Encountered unexpected"...
0x180046613  mov     ecx, 1
0x180046618  call    UnattendLogW
0x18004661d  jmp     loc_180046B40
0x180046622  mov     ecx, edx
0x180046624  movq    rax, xmm3
0x180046629  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004662e  mov     ebx, eax
0x180046630  test    eax, eax
0x180046632  jns     short loc_180046668
0x180046634  mov     edx, 130h
0x180046639  jmp     short loc_180046652
0x18004663b  movq    rax, xmm8
0x180046640  mov     cl, dl
0x180046642  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046647  mov     ebx, eax
0x180046649  test    eax, eax
0x18004664b  jns     short loc_180046668
0x18004664d  mov     edx, 129h; void *
0x180046652  lea     r8, aOnecoreuapInte_7; "onecoreuap\\internal\\shell\\inc\\oobes"...
0x180046659  mov     r9d, ebx; char *
0x18004665c  mov     rcx, [rbp+88h]; this
0x180046663  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180046668  lea     rax, aSucceeded; "succeeded"
0x18004666f  test    ebx, ebx
0x180046671  lea     rcx, aFailed; "failed"
0x180046678  cmovs   rax, rcx
0x18004667c  lea     r9, aEnabled_0; "enabled"
0x180046683  cmp     [r15+r12], r14b
0x180046687  lea     rcx, aDisabled; "disabled"
0x18004668e  cmovz   r9, rcx
0x180046692  mov     ecx, ebx
0x180046694  sar     ecx, 1Fh
0x180046697  and     ecx, 2
0x18004669a  mov     dword ptr [rsp+180h+samDesired], ebx
0x18004669e  mov     qword ptr [rsp+180h+dwOptions], rax
0x1800466a3  lea     rax, ?canonicalNames@?1??CanonicalNameFromProtectPcId@@YAQEBGW4OOBE_PROTECTPC_BOOLEAN_SETTING@@@Z@4QBQEBGB; ushort const * const near * const `CanonicalNameFromProtectPcId(OOBE_PROTECTPC_BOOLEAN_SETTING)'::`2'::canonicalNames
0x1800466aa  mov     r8, [rax+r15*8]
0x1800466ae  lea     rdx, aProtectpcTaskS_0; "ProtectPC Task - setting %s to value %s"...
0x1800466b5  call    UnattendLogW
0x1800466ba  jmp     loc_180046B40
0x1800466bf  mov     [rsp+180h+var_120], r14
0x1800466c4  mov     [rbp+80h+var_78], r14
0x1800466c8  mov     r9d, 45h ; 'E'; unsigned int
0x1800466ce  lea     r8d, [r9+1]; unsigned int
0x1800466d2  lea     rdx, ?RuntimeClass_Windows_Internal_CapabilityAccess_Management_CapabilityConsentManager@@3QBGB; "Windows.Internal.CapabilityAccess.Manag"...
0x1800466d9  lea     rcx, [rbp+80h+hstringHeader]; hstringHeader
0x1800466dd  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800466e2  lea     r8, [rsp+180h+var_120]
0x1800466e7  lea     rdx, _GUID_ef1a89c8_29b1_4ab0_94a7_851b33527a2e
0x1800466ee  mov     rcx, [rbp+80h+var_78]
0x1800466f2  call    cs:__imp_RoGetActivationFactory
0x1800466f8  mov     ebx, eax
0x1800466fa  mov     rcx, [rbp+88h]; this
0x180046701  test    eax, eax
0x180046703  jns     short loc_18004671E
0x180046705  mov     r9d, eax; char *
0x180046708  lea     r8, aOnecoreuapInte_7; "onecoreuap\\internal\\shell\\inc\\oobes"...
0x18004670f  mov     edx, 102h; void *
0x180046714  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180046719  jmp     loc_1800467D0
0x18004671e  mov     qword ptr [rsp+180h+Data], r14
0x180046723  mov     rdi, [rsp+180h+var_120]
0x180046728  mov     rax, [rdi]
0x18004672b  mov     rbx, [rax+30h]
0x18004672f  mov     qword ptr [rsp+180h+Data], r14
0x180046734  lea     rdx, [rbp+80h+var_E0+8]
0x180046738  lea     rcx, [rbp+80h+hstringHeader]
0x18004673c  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180046741  nop
0x180046742  lea     r8, [rsp+180h+Data]
0x180046747  mov     rdx, [rax+18h]
0x18004674b  mov     rcx, rdi
0x18004674e  mov     rax, rbx
0x180046751  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046756  mov     ebx, eax
0x180046758  mov     rcx, [rbp+88h]; this
0x18004675f  test    eax, eax
0x180046761  jns     short loc_18004677C
0x180046763  mov     r9d, eax; char *
0x180046766  lea     r8, aOnecoreuapInte_7; "onecoreuap\\internal\\shell\\inc\\oobes"...
0x18004676d  mov     edx, 105h; void *
0x180046772  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180046777  mov     al, r14b
0x18004677a  jmp     short loc_18004677E
0x18004677c  mov     al, 1
0x18004677e  test    al, al
0x180046780  jz      short loc_1800467C0
0x180046782  mov     rcx, qword ptr [rsp+180h+Data]
0x180046787  mov     r8, [rcx]
0x18004678a  mov     al, [r15+r12]
0x18004678e  neg     al
0x180046790  sbb     edx, edx
0x180046792  add     edx, 2
0x180046795  mov     rax, [r8+70h]
0x180046799  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004679e  mov     ebx, eax
0x1800467a0  mov     rcx, [rbp+88h]; this
0x1800467a7  test    eax, eax
0x1800467a9  jns     short loc_1800467C0
0x1800467ab  mov     r9d, eax; char *
0x1800467ae  lea     r8, aOnecoreuapInte_7; "onecoreuap\\internal\\shell\\inc\\oobes"...
0x1800467b5  mov     edx, 10Dh; void *
0x1800467ba  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800467bf  nop
0x1800467c0  lea     rcx, [rsp+180h+Data]
0x1800467c5  call    ??1?$com_ptr_t@UIUsoCallback@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(void)
0x1800467ca  test    ebx, ebx
0x1800467cc  mov     cl, 1
0x1800467ce  jns     short loc_1800467D3
0x1800467d0  mov     cl, r14b
0x1800467d3  lea     rax, aSucceeded; "succeeded"
0x1800467da  test    cl, cl
0x1800467dc  lea     rdx, aFailed; "failed"
0x1800467e3  cmovz   rax, rdx
0x1800467e7  lea     rdx, aDeny; "Deny"
0x1800467ee  lea     r9, aAllow; "Allow"
0x1800467f5  cmp     [r15+r12], r14b
0x1800467f9  cmovz   r9, rdx
0x1800467fd  movzx   ecx, cl
0x180046800  xor     ecx, 1
0x180046803  add     ecx, ecx
0x180046805  mov     qword ptr [rsp+180h+dwOptions], rax
0x18004680a  psrldq  xmm7, 8
0x18004680f  movq    r8, xmm7
0x180046814  lea     rdx, aProtectpcTaskS_3; "ProtectPC Task - setting %s capability "...
0x18004681b  call    UnattendLogW
0x180046820  nop
0x180046821  lea     rcx, [rsp+180h+var_120]
0x180046826  call    ??1?$com_ptr_t@UIUsoCallback@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(void)
0x18004682b  jmp     loc_180046B40
0x180046830  movq    rdi, xmm1
0x180046835  psrldq  xmm2, 8
0x18004683a  movq    rax, xmm2
0x18004683f  test    dl, dl
0x180046841  cmovnz  rdi, rax
0x180046845  mov     r9, rdi
0x180046848  movdqa  xmm0, xmm7
0x18004684c  psrldq  xmm0, 8
0x180046851  movq    rsi, xmm0
0x180046856  mov     r8, rsi
0x180046859  lea     rdx, aProtectpcTaskS_2; "ProtectPC Task - setting %s value to (%"...
0x180046860  xor     ecx, ecx
0x180046862  call    UnattendLogW
0x180046867  mov     r9, rdi; unsigned __int16 *
0x18004686a  mov     r8, rsi; unsigned __int16 *
0x18004686d  movq    rdx, xmm7; unsigned __int16 *
0x180046872  mov     rcx, 0FFFFFFFF80000002h; HKEY
0x180046879  call    ?SHRegSetString@@YAJPEAUHKEY__@@PEBG11@Z; SHRegSetString(HKEY__ *,ushort const *,ushort const *,ushort const *)
0x18004687e  mov     rcx, [rbp+88h]; this
0x180046885  test    eax, eax
0x180046887  jns     short loc_18004689D
0x180046889  mov     r9d, eax; char *
0x18004688c  lea     r8, aOnecoreuapInte_7; "onecoreuap\\internal\\shell\\inc\\oobes"...
0x180046893  mov     edx, 0E9h; void *
0x180046898  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18004689d  mov     qword ptr [rsp+180h+Data], r14
0x1800468a2  mov     [rsp+180h+var_130], r14b
0x1800468a7  xor     edx, edx
0x1800468a9  lea     rcx, [rsp+180h+Data]
0x1800468ae  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800468b3  lea     r9, [rsp+180h+var_130]; bool *
0x1800468b8  lea     r8, [rsp+180h+Data]; unsigned __int16 **
0x1800468bd  movq    rdx, xmm7; unsigned __int16 *
0x1800468c2  psrldq  xmm6, 8
0x1800468c7  movq    rcx, xmm6; unsigned __int16 *
0x1800468cc  call    ?TryGetRedirectionKeyPath@Details@@YAJPEBG0PEAPEAGPEA_N@Z; Details::TryGetRedirectionKeyPath(ushort const *,ushort const *,ushort * *,bool *)
0x1800468d1  mov     ebx, eax
0x1800468d3  mov     rcx, [rbp+88h]
0x1800468da  test    eax, eax
0x1800468dc  jns     short loc_1800468E5
0x1800468de  mov     edx, 0F2h
0x1800468e3  jmp     short loc_180046915
0x1800468e5  cmp     [rsp+180h+var_130], r14b
0x1800468ea  jz      short loc_180046925
0x1800468ec  mov     r9, rdi; unsigned __int16 *
0x1800468ef  mov     r8, rsi; unsigned __int16 *
0x1800468f2  mov     rdx, qword ptr [rsp+180h+Data]; unsigned __int16 *
0x1800468f7  mov     rcx, 0FFFFFFFF80000002h; HKEY
0x1800468fe  call    ?SHRegSetString@@YAJPEAUHKEY__@@PEBG11@Z; SHRegSetString(HKEY__ *,ushort const *,ushort const *,ushort const *)
0x180046903  mov     ebx, eax
0x180046905  mov     rcx, [rbp+88h]; this
0x18004690c  test    eax, eax
0x18004690e  jns     short loc_180046925
0x180046910  mov     edx, 0F6h; void *
0x180046915  mov     r9d, eax; char *
0x180046918  lea     r8, aOnecoreuapInte_7; "onecoreuap\\internal\\shell\\inc\\oobes"...
0x18004691f  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180046924  nop
0x180046925  lea     rcx, [rsp+180h+Data]
0x18004692a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18004692f  jmp     loc_180046B3C
0x180046934  movdqa  xmm0, xmm2
0x180046938  psrldq  xmm0, 4
0x18004693d  movd    r9d, xmm0
0x180046942  movd    eax, xmm2
0x180046946  test    dl, dl
0x180046948  cmovnz  r9d, eax
0x18004694c  mov     dword ptr [rsp+180h+Data], r9d
0x180046951  movdqa  xmm0, xmm7
0x180046955  psrldq  xmm0, 8
0x18004695a  movq    rsi, xmm0
0x18004695f  mov     r8, rsi
0x180046962  lea     rdx, aProtectpcTaskS_1; "ProtectPC Task - setting %s value to (%"...
0x180046969  xor     ecx, ecx
0x18004696b  call    UnattendLogW
0x180046970  mov     r9d, dword ptr [rsp+180h+Data]; unsigned int
0x180046975  mov     r8, rsi; unsigned __int16 *
0x180046978  movq    rdx, xmm7; unsigned __int16 *
0x18004697d  mov     rcx, 0FFFFFFFF80000002h; HKEY
0x180046984  call    ?SHRegSetDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; SHRegSetDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x180046989  mov     rcx, [rbp+88h]; this
0x180046990  test    eax, eax
0x180046992  jns     short loc_1800469A8
0x180046994  mov     r9d, eax; char *
0x180046997  lea     r8, aOnecoreuapInte_7; "onecoreuap\\internal\\shell\\inc\\oobes"...
0x18004699e  mov     edx, 0C6h; void *
0x1800469a3  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800469a8  mov     [rsp+180h+var_120], 0
0x1800469b1  mov     [rsp+180h+var_130], 0
0x1800469b6  xor     edx, edx
0x1800469b8  lea     rcx, [rsp+180h+var_120]
0x1800469bd  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800469c2  lea     r9, [rsp+180h+var_130]; bool *
0x1800469c7  lea     r8, [rsp+180h+var_120]; unsigned __int16 **
0x1800469cc  movq    rdx, xmm7; unsigned __int16 *
0x1800469d1  psrldq  xmm6, 8
0x1800469d6  movq    rcx, xmm6; unsigned __int16 *
0x1800469db  call    ?TryGetRedirectionKeyPath@Details@@YAJPEBG0PEAPEAGPEA_N@Z; Details::TryGetRedirectionKeyPath(ushort const *,ushort const *,ushort * *,bool *)
0x1800469e0  mov     ebx, eax
0x1800469e2  mov     rcx, [rbp+88h]
0x1800469e9  test    eax, eax
  ... truncated ...
```
