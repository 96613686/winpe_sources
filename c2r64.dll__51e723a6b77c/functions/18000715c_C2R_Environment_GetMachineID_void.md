# C2R::Environment::GetMachineID(void)

- ea: `0x18000715c`
- end: `0x1800075b3`
- name: `?GetMachineID@Environment@C2R@@SA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ`
- size: `1111`
- prototype: ``
- caller_count: `2`
- callee_count: `23`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800056a0`
- `0x180138e00`

## callees

- `0x180006090`
- `0x18000715c`
- `0x1800075b4`
- `0x180007778`
- `0x1800077d4`
- `0x180007838`
- `0x180007d08`
- `0x180007d40`
- `0x18000ae28`
- `0x18000c0a4`
- `0x18000c2dc`
- `0x18001c4d4`
- `0x18002437c`
- `0x18002acd8`
- `0x18003e690`
- `0x1800409e0`
- `0x18004a4f4`
- `0x18004a830`
- `0x180052b30`
- `0x18008cfc4`
- `0x180135440`
- `0x18013672c`
- `0x180138ac4`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1800073eb`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1800073eb`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18000737c`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18000737c`
- `ADVAPI32!RegOpenKeyExW` at `0x180007275`
- `ADVAPI32!RegOpenKeyExW` at `0x180007275`

## string_xrefs

- `0x1800071cb`: `SOFTWARE\Wow6432Node\Microsoft\Office\Common`
- `0x1800071b7`: `SOFTWARE\Microsoft\Office\Common`
- `0x18000748b`: `ORegistryKey.Open failure: Parent key is NULL`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall C2R::Environment::GetMachineID(__int64 a1)
{
  __int64 v1; // rsi
  __int64 v2; // r9
  __int64 v3; // r8
  __int64 v4; // r9
  HKEY v5; // r14
  REGSAM v6; // r9d
  const WCHAR *v7; // rdx
  int SubKey; // eax
  void *v9; // rcx
  struct _GUID *v11; // rdx
  __int64 v12; // r9
  int v13; // eax
  bool IsElevated; // di
  unsigned __int64 v15; // r8
  OBlob *v16; // rax
  _QWORD *Details; // rax
  _QWORD *v18; // rax
  __int64 v19; // rbx
  _QWORD *v20; // rax
  _QWORD *v21; // rax
  __int64 v22; // rbx
  bool v23; // [rsp+40h] [rbp-978h]
  __int128 v24; // [rsp+48h] [rbp-970h] BYREF
  __int64 v25; // [rsp+58h] [rbp-960h]
  int v26; // [rsp+60h] [rbp-958h]
  void **v27; // [rsp+68h] [rbp-950h] BYREF
  unsigned __int8 *v28; // [rsp+70h] [rbp-948h]
  LPCWSTR *v29; // [rsp+78h] [rbp-940h]
  __int64 v30; // [rsp+80h] [rbp-938h]
  void **v31; // [rsp+88h] [rbp-930h] BYREF
  const wchar_t *v32; // [rsp+90h] [rbp-928h]
  _QWORD *v33; // [rsp+98h] [rbp-920h]
  __int16 v34; // [rsp+A0h] [rbp-918h]
  const OException *v35; // [rsp+A8h] [rbp-910h] BYREF
  const OException *v36; // [rsp+B0h] [rbp-908h] BYREF
  unsigned __int8 v37[16]; // [rsp+B8h] [rbp-900h] BYREF
  LPCWSTR lpSubKey[2]; // [rsp+C8h] [rbp-8F0h] BYREF
  unsigned __int64 v39; // [rsp+D8h] [rbp-8E0h]
  unsigned __int64 v40; // [rsp+E0h] [rbp-8D8h]
  __int128 v41; // [rsp+E8h] [rbp-8D0h] BYREF
  __int64 v42; // [rsp+F8h] [rbp-8C0h]
  __int64 v43; // [rsp+100h] [rbp-8B8h]
  __int128 v44; // [rsp+108h] [rbp-8B0h] BYREF
  __int64 v45; // [rsp+118h] [rbp-8A0h]
  __int64 v46; // [rsp+120h] [rbp-898h]
  _QWORD v47[4]; // [rsp+128h] [rbp-890h] BYREF
  _QWORD v48[5]; // [rsp+148h] [rbp-870h] BYREF
  _BYTE v49[16]; // [rsp+170h] [rbp-848h] BYREF
  _BYTE v50[32]; // [rsp+180h] [rbp-838h] BYREF
  HKEY phkResult; // [rsp+1A0h] [rbp-818h] BYREF
  _BYTE v52[64]; // [rsp+1B0h] [rbp-808h] BYREF
  _BYTE v53[144]; // [rsp+1F0h] [rbp-7C8h] BYREF
  _BYTE pExceptionObject[912]; // [rsp+280h] [rbp-738h] BYREF
  _BYTE v55[912]; // [rsp+610h] [rbp-3A8h] BYREF

  v1 = a1;
  v30 = a1;
  v26 = 0;
  v24 = 0;
  v25 = 0;
  std::wstring::wstring(v47, L"MID");
  std::wstring::wstring(lpSubKey, L"SOFTWARE\\Microsoft\\Office\\Common");
  std::wstring::wstring(v48, L"SOFTWARE\\Wow6432Node\\Microsoft\\Office\\Common");
  try
  {
    IsElevated = OSecurity::IsElevated();
    v23 = IsElevated;
  }
  catch ( const OException *v35 )
  {
    Details = (_QWORD *)OException::get_Details(v35, v49);
    if ( Details[3] > 7u )
      Details = (_QWORD *)*Details;
    *(_QWORD *)v37 = Details;
    v18 = (_QWORD *)OString::Format<wchar_t const *>(
                      v52,
                      L"OException caught in call to IsElevated {'Error':'%s'}",
                      v37);
    if ( v18[3] > 7u )
      v18 = (_QWORD *)*v18;
    v31 = &Mso::Logging::StructuredObject<wchar_t const *,1>::`vftable';
    v32 = L"ContextData";
    v33 = v18;
    v34 = 0;
    v44 = 0;
    v45 = 0;
    v46 = 7;
    LOWORD(v44) = 0;
    v41 = 0;
    v42 = 0;
    v43 = 7;
    LOWORD(v41) = 0;
    v19 = C2R::ErrorTelemetry::ErrorTelemetry(v53, v35, &v41, &v44);
    if ( (unsigned __int8)Mso::Logging::MsoShouldTrace(23888463, 14, 15) )
    {
      *(_QWORD *)v37 = v19;
      *(_QWORD *)&v37[8] = &v31;
      v27 = &Mso::Logging::CompositeStructuredTrace::`vftable';
      v28 = v37;
      v29 = lpSubKey;
      Mso::Logging::MsoSendStructuredTraceTag(23888463, 14, 15);
    }
    C2R::ErrorTelemetry::~ErrorTelemetry((C2R::ErrorTelemetry *)v53);
    std::wstring::~wstring(&v41);
    std::wstring::~wstring(&v44);
    std::wstring::~wstring(v52);
    std::wstring::~wstring(v49);
    IsElevated = v23;
    v1 = v30;
  }
  try
  {
    ORegistryKey::ORegistryKey((ORegistryKey *)v49);
    if ( IsElevated )
    {
      LOBYTE(v2) = 1;
      SubKey = ORegistryKey::CreateSubKey(ORegistry::LocalMachine, v49, lpSubKey, v2, 1);
    }
    else
    {
      ORegistryKey::Clear((ORegistryKey *)v49);
      v5 = hKey;
      if ( !hKey )
      {
        OException::OException(pExceptionObject, 58, L"ORegistryKey.Open failure: Parent key is NULL");
        throw (OException *)pExceptionObject;
      }
      if ( v39 > 0xFF )
      {
        OException::OException((__int64)v55, 808464432, v3, v4, (__int64)lpSubKey);
        throw (OException *)v55;
      }
      v6 = (OSystem::IsWOW64Mode() << 8) + 131097;
      v7 = (const WCHAR *)lpSubKey;
      if ( v40 > 7 )
        v7 = lpSubKey[0];
      if ( RegOpenKeyExW(v5, v7, 0, v6, &phkResult) )
      {
        SubKey = 0;
      }
      else
      {
        OPath::Combine(qword_18021D990, lpSubKey, v50);
        SubKey = 1;
      }
    }
    if ( SubKey && (!(unsigned __int8)ORegistryKey::GetValue(v49, v47, &v24) || *((_QWORD *)&v24 + 1) == (_QWORD)v24) )
    {
      ORegistryKey::ORegistryKey((ORegistryKey *)v52);
      if ( OSystem::GetProcessorArchitecture() )
      {
        if ( IsElevated )
        {
          LOBYTE(v12) = 1;
          v13 = ORegistryKey::CreateSubKey(ORegistry::LocalMachine, v52, v48, v12, 1);
        }
        else
        {
          v13 = (unsigned __int8)ORegistryKey::OpenSubKey(ORegistry::LocalMachine, v52, v48, 0, 1, 0);
        }
        if ( v13 )
          ORegistryKey::GetValue(v52, v47, &v24);
      }
      if ( IsElevated )
      {
        if ( *((_QWORD *)&v24 + 1) == (_QWORD)v24 )
        {
          *(struct _GUID *)v37 = *OGuid::Create((OGuid *)&v27, v11);
          v16 = OBlob::OBlob((OBlob *)&v27, v37, v15);
          std::vector<unsigned char>::operator=(&v24, v16);
          std::vector<unsigned char>::~vector<unsigned char>(&v27);
        }
        ORegistryKey::SetValue(v49, v47, &v24);
      }
      ORegistryKey::~ORegistryKey((ORegistryKey *)v52);
    }
    ORegistryKey::~ORegistryKey((ORegistryKey *)v49);
  }
  catch ( const OException *v36 )
  {
    v20 = (_QWORD *)OException::get_Details(v36, v52);
    if ( v20[3] > 7u )
      v20 = (_QWORD *)*v20;
    *(_QWORD *)v37 = v20;
    v21 = (_QWORD *)OString::Format<wchar_t const *>(v49, L"OException caught {'Error':'%s'}", v37);
    if ( v21[3] > 7u )
      v21 = (_QWORD *)*v21;
    v31 = &Mso::Logging::StructuredObject<wchar_t const *,1>::`vftable';
    v32 = L"ContextData";
    v33 = v21;
    v34 = 0;
    v41 = 0;
    v42 = 0;
    v43 = 7;
    LOWORD(v41) = 0;
    v44 = 0;
    v45 = 0;
    v46 = 7;
    LOWORD(v44) = 0;
    v22 = C2R::ErrorTelemetry::ErrorTelemetry(v53, v36, &v44, &v41);
    if ( (unsigned __int8)Mso::Logging::MsoShouldTrace(23888464, 942, 10) )
    {
      *(_QWORD *)v37 = v22;
      *(_QWORD *)&v37[8] = &v31;
      v27 = &Mso::Logging::CompositeStructuredTrace::`vftable';
      v28 = v37;
      v29 = lpSubKey;
      Mso::Logging::MsoSendStructuredTraceTag(23888464, 942, 10);
    }
    C2R::ErrorTelemetry::~ErrorTelemetry((C2R::ErrorTelemetry *)v53);
    std::wstring::~wstring(&v44);
    std::wstring::~wstring(&v41);
    std::wstring::~wstring(v49);
    std::wstring::~wstring(v52);
    v1 = v30;
  }
  OString::ToHexString(v1, &v24);
  v26 = 1;
  std::wstring::_Tidy_deallocate(v48);
  v48[0] = 19937;
  v48[2] = 0;
  v48[3] = 15;
  std::wstring::_Tidy_deallocate(lpSubKey);
  lpSubKey[0] = (LPCWSTR)19937;
  v39 = 0;
  v40 = 15;
  std::wstring::_Tidy_deallocate(v47);
  v47[0] = 19937;
  v47[2] = 0;
  v47[3] = 15;
  v9 = (void *)v24;
  if ( (_QWORD)v24 )
  {
    if ( (unsigned __int64)(v25 - v24) >= 0x1000 )
    {
      _mm_lfence();
      v9 = *(void **)(v24 - 8);
      if ( (unsigned __int64)(v24 - (_QWORD)v9 - 8) > 0x1F )
        _invoke_watson(0, 0, 0, 0, 0);
    }
    free(v9);
  }
  return v1;
}

```

## disassembly

```asm
0x18000715c  mov     r11, rsp
0x18000715f  mov     [r11+10h], rbx
0x180007163  mov     [r11+18h], rsi
0x180007167  mov     [r11+20h], rdi
0x18000716b  push    r14
0x18000716d  sub     rsp, 9B0h
0x180007174  mov     rax, cs:__security_cookie
0x18000717b  xor     rax, rsp
0x18000717e  mov     [rsp+9B8h+var_18], rax
0x180007186  mov     rsi, rcx
0x180007189  mov     [r11-938h], rcx
0x180007190  xor     ebx, ebx
0x180007192  mov     [rsp+9B8h+var_958], ebx
0x180007196  xorps   xmm0, xmm0
0x180007199  movdqu  [rsp+9B8h+var_970], xmm0
0x18000719f  mov     [rsp+9B8h+var_960], rbx
0x1800071a4  lea     rdx, aMid; "MID"
0x1800071ab  lea     rcx, [r11-890h]
0x1800071b2  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x1800071b7  lea     rdx, aSoftwareMicros_7; "SOFTWARE\\Microsoft\\Office\\Common"
0x1800071be  lea     rcx, [rsp+9B8h+lpSubKey]
0x1800071c6  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x1800071cb  lea     rdx, aSoftwareWow643; "SOFTWARE\\Wow6432Node\\Microsoft\\Offic"...
0x1800071d2  lea     rcx, [rsp+9B8h+var_870]
0x1800071da  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x1800071df  mov     [rsp+9B8h+var_978], bl
0x1800071e3  call    ?IsElevated@OSecurity@@SA_NXZ; OSecurity::IsElevated(void)
0x1800071e8  mov     dil, al
0x1800071eb  mov     [rsp+9B8h+var_978], al
0x1800071ef  lea     rcx, [rsp+9B8h+var_848]; this
0x1800071f7  call    ??0ORegistryKey@@QEAA@XZ; ORegistryKey::ORegistryKey(void)
0x1800071fc  test    dil, dil
0x1800071ff  jnz     loc_1800073B0
0x180007205  lea     rcx, [rsp+9B8h+var_848]; this
0x18000720d  call    ?Clear@ORegistryKey@@AEAAXXZ; ORegistryKey::Clear(void)
0x180007212  mov     r14, cs:hKey
0x180007219  test    r14, r14
0x18000721c  jz      loc_18000748B
0x180007222  cmp     [rsp+9B8h+var_8E0], 0FFh
0x18000722e  ja      loc_1800074B8
0x180007234  call    ?IsWOW64Mode@OSystem@@SA_NXZ; OSystem::IsWOW64Mode(void)
0x180007239  movzx   r9d, al
0x18000723d  shl     r9d, 8
0x180007241  add     r9d, 20019h; samDesired
0x180007248  lea     rdx, [rsp+9B8h+lpSubKey]
0x180007250  cmp     [rsp+9B8h+var_8D8], 7
0x180007259  cmova   rdx, [rsp+9B8h+lpSubKey]; lpSubKey
0x180007262  lea     rax, [rsp+9B8h+var_818]
0x18000726a  mov     [rsp+9B8h+phkResult], rax; phkResult
0x18000726f  xor     r8d, r8d; ulOptions
0x180007272  mov     rcx, r14; hKey
0x180007275  call    cs:__imp_RegOpenKeyExW
0x18000727b  test    eax, eax
0x18000727d  jnz     loc_180007470
0x180007283  lea     r8, [rsp+9B8h+var_838]
0x18000728b  lea     rdx, [rsp+9B8h+lpSubKey]
0x180007293  lea     rcx, qword_18021D990
0x18000729a  call    ?Combine@OPath@@SAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0AEAV23@@Z; OPath::Combine(std::wstring const &,std::wstring const &,std::wstring &)
0x18000729f  mov     eax, 1
0x1800072a4  test    eax, eax
0x1800072a6  jnz     loc_1800073F2
0x1800072ac  lea     rcx, [rsp+9B8h+var_848]; this
0x1800072b4  call    ??1ORegistryKey@@UEAA@XZ; ORegistryKey::~ORegistryKey(void)
0x1800072b9  nop
0x1800072ba  lea     rdx, [rsp+9B8h+var_970]
0x1800072bf  mov     rcx, rsi
0x1800072c2  call    ?ToHexString@OString@@SA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBVOBlob@@@Z; OString::ToHexString(OBlob const &)
0x1800072c7  mov     [rsp+9B8h+var_958], 1
0x1800072cf  lea     rcx, [rsp+9B8h+var_870]
0x1800072d7  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800072dc  mov     r14d, 4DE1h
0x1800072e2  mov     [rsp+9B8h+var_870], r14
0x1800072ea  mov     [rsp+9B8h+var_860], rbx
0x1800072f2  mov     edi, 0Fh
0x1800072f7  mov     [rsp+9B8h+var_858], rdi
0x1800072ff  lea     rcx, [rsp+9B8h+lpSubKey]
0x180007307  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000730c  mov     [rsp+9B8h+lpSubKey], r14
0x180007314  mov     [rsp+9B8h+var_8E0], rbx
0x18000731c  mov     [rsp+9B8h+var_8D8], rdi
0x180007324  lea     rcx, [rsp+9B8h+var_890]
0x18000732c  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180007331  mov     [rsp+9B8h+var_890], r14
0x180007339  mov     [rsp+9B8h+var_880], rbx
0x180007341  mov     [rsp+9B8h+var_878], rdi
0x180007349  mov     rcx, qword ptr [rsp+9B8h+var_970]
0x18000734e  test    rcx, rcx
0x180007351  jz      short loc_180007383
0x180007353  mov     rax, [rsp+9B8h+var_960]
0x180007358  sub     rax, rcx
0x18000735b  cmp     rax, 1000h
0x180007361  jb      short loc_18000737C
0x180007363  lfence
0x180007366  mov     rax, qword ptr [rsp+9B8h+var_970]
0x18000736b  mov     rcx, [rax-8]; Block
0x18000736f  sub     rax, rcx
0x180007372  add     rax, 0FFFFFFFFFFFFFFF8h
0x180007376  cmp     rax, 1Fh
0x18000737a  ja      short loc_1800073DC
0x18000737c  call    cs:__imp_free
0x180007382  nop
0x180007383  mov     rax, rsi
0x180007386  mov     rcx, [rsp+9B8h+var_18]
0x18000738e  xor     rcx, rsp; StackCookie
0x180007391  call    __security_check_cookie
0x180007396  lea     r11, [rsp+9B8h+var_8]
0x18000739e  mov     rbx, [r11+18h]
0x1800073a2  mov     rsi, [r11+20h]
0x1800073a6  mov     rdi, [r11+28h]
0x1800073aa  mov     rsp, r11
0x1800073ad  pop     r14
0x1800073af  retn
0x1800073b0  mov     dword ptr [rsp+9B8h+phkResult], 1
0x1800073b8  mov     r9b, 1
0x1800073bb  lea     r8, [rsp+9B8h+lpSubKey]
0x1800073c3  lea     rdx, [rsp+9B8h+var_848]
0x1800073cb  lea     rcx, ?LocalMachine@ORegistry@@2VORegistryKey@@A; ORegistryKey ORegistry::LocalMachine
0x1800073d2  call    ?CreateSubKey@ORegistryKey@@QEAAKAEAV1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_NW4REGKEY_ACCESS_MODE@ORegistry@@KK@Z; ORegistryKey::CreateSubKey(ORegistryKey &,std::wstring const &,bool,ORegistry::REGKEY_ACCESS_MODE,ulong,ulong)
0x1800073d7  jmp     loc_1800072A4
0x1800073dc  mov     [rsp+9B8h+phkResult], rbx; Reserved
0x1800073e1  xor     r9d, r9d; LineNo
0x1800073e4  xor     r8d, r8d; FileName
0x1800073e7  xor     edx, edx; FunctionName
0x1800073e9  xor     ecx, ecx; Expression
0x1800073eb  call    cs:__imp__invoke_watson
0x1800073f2  lea     r8, [rsp+9B8h+var_970]
0x1800073f7  lea     rdx, [rsp+9B8h+var_890]
0x1800073ff  lea     rcx, [rsp+9B8h+var_848]
0x180007407  call    ?GetValue@ORegistryKey@@QEBA_NAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVOBlob@@@Z; ORegistryKey::GetValue(std::wstring const &,OBlob &)
0x18000740c  test    al, al
0x18000740e  jz      short loc_180007420
0x180007410  mov     rax, qword ptr [rsp+9B8h+var_970+8]
0x180007415  cmp     rax, qword ptr [rsp+9B8h+var_970]
0x18000741a  jnz     loc_1800072AC
0x180007420  lea     rcx, [rsp+9B8h+var_808]; this
0x180007428  call    ??0ORegistryKey@@QEAA@XZ; ORegistryKey::ORegistryKey(void)
0x18000742d  call    ?GetProcessorArchitecture@OSystem@@SAGXZ; OSystem::GetProcessorArchitecture(void)
0x180007432  test    ax, ax
0x180007435  jz      loc_180007526
0x18000743b  lea     r8, [rsp+9B8h+var_870]
0x180007443  lea     rdx, [rsp+9B8h+var_808]
0x18000744b  lea     rcx, ?LocalMachine@ORegistry@@2VORegistryKey@@A; ORegistryKey ORegistry::LocalMachine
0x180007452  test    dil, dil
0x180007455  jz      loc_1800074F1
0x18000745b  mov     dword ptr [rsp+9B8h+phkResult], 1
0x180007463  mov     r9b, 1
0x180007466  call    ?CreateSubKey@ORegistryKey@@QEAAKAEAV1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_NW4REGKEY_ACCESS_MODE@ORegistry@@KK@Z; ORegistryKey::CreateSubKey(ORegistryKey &,std::wstring const &,bool,ORegistry::REGKEY_ACCESS_MODE,ulong,ulong)
0x18000746b  jmp     loc_180007508
0x180007470  mov     eax, ebx
0x180007472  jmp     loc_1800072A4
0x180007477  xor     ebx, ebx
0x180007479  mov     dil, [rsp+9B8h+var_978]
0x18000747e  mov     rsi, [rsp+9B8h+var_938]
0x180007486  jmp     loc_1800071EF
0x18000748b  lea     r8, aOregistrykeyOp_1; "ORegistryKey.Open failure: Parent key i"...
0x180007492  mov     edx, 3Ah ; ':'
0x180007497  lea     rcx, [rsp+9B8h+pExceptionObject]
0x18000749f  call    ??$?0$0CO@@OException@@QEAA@W4exceptionType@et@@AEAY0CO@$$CB_W@Z; OException::OException(et::exceptionType,wchar_t const (&)[46])
0x1800074a4  lea     rdx, _TI2?AVOException@@; pThrowInfo
0x1800074ab  lea     rcx, [rsp+9B8h+pExceptionObject]; pExceptionObject
0x1800074b3  call    _CxxThrowException
0x1800074b8  lea     rax, [rsp+9B8h+lpSubKey]
0x1800074c0  mov     [rsp+9B8h+phkResult], rax
0x1800074c5  mov     edx, 30303030h
0x1800074ca  lea     rcx, [rsp+9B8h+var_3A8]
0x1800074d2  call    ??$?0$0FN@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@OException@@QEAA@Utag_t@0@W4exceptionType@et@@AEAY0FN@$$CB_WAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; OException::OException(OException::tag_t,et::exceptionType,wchar_t const (&)[93],std::wstring const &)
0x1800074d7  lea     rdx, _TI2?AVOException@@; pThrowInfo
0x1800074de  lea     rcx, [rsp+9B8h+var_3A8]; pExceptionObject
0x1800074e6  call    _CxxThrowException
0x1800074f1  mov     [rsp+9B8h+var_990], bl
0x1800074f5  mov     dword ptr [rsp+9B8h+phkResult], 1
0x1800074fd  xor     r9d, r9d
0x180007500  call    ?OpenSubKey@ORegistryKey@@QEBA_NAEAV1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_NW4REGKEY_ACCESS_MODE@ORegistry@@2@Z; ORegistryKey::OpenSubKey(ORegistryKey &,std::wstring const &,bool,ORegistry::REGKEY_ACCESS_MODE,bool)
0x180007505  movzx   eax, al
0x180007508  test    eax, eax
0x18000750a  jz      short loc_180007526
0x18000750c  lea     r8, [rsp+9B8h+var_970]
0x180007511  lea     rdx, [rsp+9B8h+var_890]
0x180007519  lea     rcx, [rsp+9B8h+var_808]
0x180007521  call    ?GetValue@ORegistryKey@@QEBA_NAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVOBlob@@@Z; ORegistryKey::GetValue(std::wstring const &,OBlob &)
0x180007526  test    dil, dil
0x180007529  jz      short loc_180007591
0x18000752b  mov     rax, qword ptr [rsp+9B8h+var_970+8]
0x180007530  cmp     rax, qword ptr [rsp+9B8h+var_970]
0x180007535  jnz     short loc_180007576
0x180007537  lea     rcx, [rsp+9B8h+var_950]; this
0x18000753c  call    ?Create@OGuid@@YA?AU_GUID@@XZ; OGuid::Create(void)
0x180007541  movups  xmm0, xmmword ptr [rax]
0x180007544  movdqu  xmmword ptr [rsp+9B8h+var_900], xmm0
0x18000754d  lea     rdx, [rsp+9B8h+var_900]; unsigned __int8 *
0x180007555  lea     rcx, [rsp+9B8h+var_950]; this
0x18000755a  call    ??0OBlob@@QEAA@PEBE_K@Z; OBlob::OBlob(uchar const *,unsigned __int64)
0x18000755f  mov     rdx, rax
0x180007562  lea     rcx, [rsp+9B8h+var_970]
0x180007567  call    ??4?$vector@EV?$allocator@E@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::vector<uchar>::operator=(std::vector<uchar> &&)
0x18000756c  lea     rcx, [rsp+9B8h+var_950]
0x180007571  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x180007576  lea     r8, [rsp+9B8h+var_970]
0x18000757b  lea     rdx, [rsp+9B8h+var_890]
0x180007583  lea     rcx, [rsp+9B8h+var_848]
0x18000758b  call    ?SetValue@ORegistryKey@@QEBAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBVOBlob@@@Z; ORegistryKey::SetValue(std::wstring const &,OBlob const &)
0x180007590  nop
0x180007591  lea     rcx, [rsp+9B8h+var_808]; this
0x180007599  call    ??1ORegistryKey@@UEAA@XZ; ORegistryKey::~ORegistryKey(void)
0x18000759e  jmp     loc_1800072AC
0x1800075a3  xor     ebx, ebx
0x1800075a5  mov     rsi, [rsp+9B8h+var_938]
0x1800075ad  jmp     loc_1800072BA
```
