# ShowToast(TOAST_MESSAGE)

- ea: `0x140006304`
- end: `0x140006765`
- name: `?ShowToast@@YAXW4TOAST_MESSAGE@@@Z`
- size: `1121`
- prototype: `__int64 __fastcall(int)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x140007018`

## callees

- `0x140001470`
- `0x140001f0e`
- `0x140001f7c`
- `0x140002098`
- `0x14000214c`
- `0x140003438`
- `0x14000356c`
- `0x140003ac8`
- `0x140006304`
- `0x140006cf8`
- `0x140006d14`
- `0x140008010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x140006420`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x14000645b`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x140006420`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x14000645b`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140006497`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140006497`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x1400065e3`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x1400065e3`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x1400063e1`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x1400063e1`
- `ext-ms-win-devmgmt-policy-l1-1-0!PolicyManager_GetPolicyInt` at `0x140006358`
- `ext-ms-win-devmgmt-policy-l1-1-0!PolicyManager_GetPolicyInt` at `0x140006358`

## string_xrefs

- `0x1400063da`: `dusmsvc.dll`
- `0x140006708`: `onecoreuap\net\dusm\task\dusmtask.cpp`
- `0x14000673e`: `onecoreuap\net\dusm\task\dusmtask.cpp`
- `0x140006753`: `onecoreuap\net\dusm\task\dusmtask.cpp`
- `0x140006502`: `launch="ms-settings:datausage" activationType="protocol"`
- `0x140006520`: ` >  <visual>    <binding template="ToastText02">      <text id="1">`

## pseudocode

```c
__int64 __fastcall ShowToast(int a1)
{
  bool v2; // di
  __int64 result; // rax
  int v4; // ebx
  int v5; // ebx
  int v6; // ebx
  int v7; // ebx
  int v8; // ebx
  int v9; // ebx
  UINT v10; // edi
  UINT v11; // ebx
  HMODULE LibraryW; // rsi
  unsigned int v13; // r8d
  const char *v14; // r9
  unsigned int v15; // r8d
  const char *v16; // r9
  unsigned int v17; // r8d
  const char *v18; // r9
  HRESULT v19; // eax
  int v20; // eax
  __int64 v21; // rdi
  __int64 v22; // rbx
  __int64 v23; // rax
  __int64 v24; // rdx
  __int64 v25; // rax
  __int64 v26; // rax
  __int64 v27; // rdx
  __int64 v28; // rax
  __int64 v29; // rdx
  const wchar_t *v30; // rdx
  int v31; // eax
  __int64 v32; // rcx
  LPVOID v33; // rcx
  int ppv; // [rsp+20h] [rbp-F0h]
  _BYTE v35[32]; // [rsp+A0h] [rbp-70h] BYREF
  _BYTE v36[32]; // [rsp+C0h] [rbp-50h] BYREF
  _BYTE v37[32]; // [rsp+E0h] [rbp-30h] BYREF
  _BYTE v38[32]; // [rsp+100h] [rbp-10h] BYREF
  _BYTE v39[32]; // [rsp+120h] [rbp+10h] BYREF
  _BYTE v40[32]; // [rsp+140h] [rbp+30h] BYREF
  _BYTE v41[32]; // [rsp+160h] [rbp+50h] BYREF
  _BYTE v42[32]; // [rsp+180h] [rbp+70h] BYREF
  _DWORD v43[2]; // [rsp+1A0h] [rbp+90h] BYREF
  __int64 v44; // [rsp+1A8h] [rbp+98h] BYREF
  LPVOID v45; // [rsp+1B0h] [rbp+A0h] BYREF
  _QWORD v46[3]; // [rsp+1B8h] [rbp+A8h] BYREF
  WCHAR v47[264]; // [rsp+1E0h] [rbp+D0h] BYREF
  WCHAR Buffer[264]; // [rsp+3F0h] [rbp+2E0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+638h] [rbp+528h]

  v2 = 0;
  result = IsPolicyManager_GetPolicyPresent();
  if ( (_BYTE)result )
  {
    v43[0] = 0;
    result = PolicyManager_GetPolicyInt(L"Wifi", L"WiFiToWlan", v43);
    if ( (int)result >= 0 )
      v2 = v43[0] != 0;
  }
  v4 = a1 - 1;
  if ( !v4 )
  {
    v10 = 101;
    goto LABEL_18;
  }
  v5 = v4 - 1;
  if ( !v5 )
  {
    v10 = 103;
    v11 = 105;
    goto LABEL_19;
  }
  v6 = v5 - 1;
  if ( !v6 )
  {
    v10 = 118;
    v11 = 119;
    goto LABEL_19;
  }
  v7 = v6 - 1;
  if ( !v7 )
  {
    v10 = v2 + 106;
    goto LABEL_18;
  }
  v8 = v7 - 1;
  if ( !v8 )
  {
    v11 = v2 + 110;
    v10 = v2 + 108;
    goto LABEL_19;
  }
  v9 = v8 - 1;
  if ( !v9 )
  {
    v10 = 112;
LABEL_18:
    v11 = 102;
    goto LABEL_19;
  }
  if ( v9 != 1 )
    return result;
  v10 = 113;
  v11 = 114;
LABEL_19:
  LibraryW = LoadLibraryW(L"dusmsvc.dll");
  if ( !LibraryW )
    wil::details::in1diag3::_Throw_GetLastError(retaddr, (void *)0x68, v13, v14);
  memset_0(Buffer, 0, 0x208u);
  if ( !LoadStringW(LibraryW, v10, Buffer, 260) )
    wil::details::in1diag3::_Throw_GetLastError(retaddr, (void *)0x6B, v15, v16);
  memset_0(v47, 0, 0x208u);
  if ( !LoadStringW(LibraryW, v11, v47, 260) )
    wil::details::in1diag3::_Throw_GetLastError(retaddr, (void *)0x6E, v17, v18);
  v45 = 0;
  v19 = CoCreateInstance(
          &GUID_0c9281f9_6da1_4006_8729_de6e6b61581c,
          0,
          4u,
          &GUID_df8e9480_ca73_448e_b8f0_da000f581428,
          &v45);
  if ( v19 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x71,
      (unsigned int)"onecoreuap\\net\\dusm\\task\\dusmtask.cpp",
      (const char *)(unsigned int)v19,
      ppv);
  v44 = 0;
  v20 = (*(__int64 (__fastcall **)(LPVOID, __int64 *))(*(_QWORD *)v45 + 24LL))(v45, &v44);
  if ( v20 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x74,
      (unsigned int)"onecoreuap\\net\\dusm\\task\\dusmtask.cpp",
      (const char *)(unsigned int)v20,
      ppv);
  v21 = std::wstring::wstring(v42, v47);
  v22 = std::wstring::wstring(v41, Buffer);
  v23 = std::wstring::wstring(v40, L"launch=\"ms-settings:datausage\" activationType=\"protocol\"");
  v25 = std::operator+<wchar_t>(v39, v24, v23);
  v26 = std::operator+<wchar_t>(v38, v25, L" >  <visual>    <binding template=\"ToastText02\">      <text id=\"1\">");
  std::wstring::wstring(v36, v27, v26, v22);
  v28 = std::operator+<wchar_t>(v37, v36, L"</text>      <text id=\"2\">");
  std::wstring::wstring(v35, v29, v28, v21);
  std::operator+<wchar_t>(v46, v35, L"</text>    </binding>  </visual></toast>");
  std::wstring::~wstring(v35);
  std::wstring::~wstring(v37);
  std::wstring::~wstring(v36);
  std::wstring::~wstring(v38);
  std::wstring::~wstring(v39);
  std::wstring::~wstring(v40);
  std::wstring::~wstring(v41);
  std::wstring::~wstring(v42);
  v43[0] = 0;
  RtlGetDeviceFamilyInfoEnum(0, v43, 0);
  v30 = L"BAEAEF15-9BAB-47FC-800B-ACECAD2AE94B_cw5n1h2txyewy!App";
  if ( v43[0] != 16 )
    v30 = L"windows.immersivecontrolpanel_cw5n1h2txyewy!microsoft.windows.immersivecontrolpanel";
  v43[1] = 0;
  v31 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, const wchar_t *, _QWORD))(*(_QWORD *)v44 + 64LL))(
          v44,
          v30,
          v30,
          0);
  if ( v31 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x9F,
      (unsigned int)"onecoreuap\\net\\dusm\\task\\dusmtask.cpp",
      (const char *)(unsigned int)v31,
      0);
  result = std::wstring::~wstring(v46);
  v32 = v44;
  if ( v44 )
  {
    v44 = 0;
    result = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
  }
  v33 = v45;
  if ( v45 )
  {
    v45 = 0;
    return (*(__int64 (__fastcall **)(LPVOID))(*(_QWORD *)v33 + 16LL))(v33);
  }
  return result;
}

```

## disassembly

```asm
0x140006304  push    rbp
0x140006306  push    rbx
0x140006307  push    rsi
0x140006308  push    rdi
0x140006309  push    r14
0x14000630b  lea     rbp, [rsp-500h]
0x140006313  sub     rsp, 610h
0x14000631a  mov     rax, cs:__security_cookie
0x140006321  xor     rax, rsp
0x140006324  mov     [rbp+520h+var_30], rax
0x14000632b  mov     ebx, ecx
0x14000632d  xor     r14d, r14d
0x140006330  mov     dil, r14b
0x140006333  call    IsPolicyManager_GetPolicyPresent
0x140006338  test    al, al
0x14000633a  jz      short loc_14000636D
0x14000633c  mov     [rbp+520h+var_490], r14d
0x140006343  lea     r8, [rbp+520h+var_490]
0x14000634a  lea     rdx, aWifitowlan; "WiFiToWlan"
0x140006351  lea     rcx, aWifi; "Wifi"
0x140006358  call    cs:__imp_PolicyManager_GetPolicyInt
0x14000635e  test    eax, eax
0x140006360  js      short loc_14000636D
0x140006362  cmp     [rbp+520h+var_490], r14d
0x140006369  setnz   dil
0x14000636d  sub     ebx, 1
0x140006370  jz      short loc_1400063D0
0x140006372  sub     ebx, 1
0x140006375  jz      short loc_1400063C6
0x140006377  sub     ebx, 1
0x14000637a  jz      short loc_1400063BC
0x14000637c  sub     ebx, 1
0x14000637f  jz      short loc_1400063B3
0x140006381  sub     ebx, 1
0x140006384  jz      short loc_1400063A3
0x140006386  sub     ebx, 1
0x140006389  jz      short loc_14000639C
0x14000638b  cmp     ebx, 1
0x14000638e  jnz     loc_1400066E8
0x140006394  lea     edi, [rbx+70h]
0x140006397  lea     ebx, [rdi+1]
0x14000639a  jmp     short loc_1400063DA
0x14000639c  mov     edi, 70h ; 'p'
0x1400063a1  jmp     short loc_1400063D5
0x1400063a3  movzx   ebx, dil
0x1400063a7  add     ebx, 6Eh ; 'n'
0x1400063aa  movzx   edi, dil
0x1400063ae  add     edi, 6Ch ; 'l'
0x1400063b1  jmp     short loc_1400063DA
0x1400063b3  movzx   edi, dil
0x1400063b7  add     edi, 6Ah ; 'j'
0x1400063ba  jmp     short loc_1400063D5
0x1400063bc  mov     edi, 76h ; 'v'
0x1400063c1  lea     ebx, [rdi+1]
0x1400063c4  jmp     short loc_1400063DA
0x1400063c6  mov     edi, 67h ; 'g'
0x1400063cb  lea     ebx, [rdi+2]
0x1400063ce  jmp     short loc_1400063DA
0x1400063d0  mov     edi, 65h ; 'e'
0x1400063d5  mov     ebx, 66h ; 'f'
0x1400063da  lea     rcx, LibFileName; "dusmsvc.dll"
0x1400063e1  call    cs:__imp_LoadLibraryW
0x1400063e7  mov     rsi, rax
0x1400063ea  mov     rcx, [rbp+528h]; this
0x1400063f1  test    rax, rax
0x1400063f4  jz      loc_14000671A
0x1400063fa  xor     edx, edx; Val
0x1400063fc  mov     r8d, 208h; Size
0x140006402  lea     rcx, [rbp+520h+Buffer]; void *
0x140006409  call    memset_0
0x14000640e  mov     r9d, 104h; cchBufferMax
0x140006414  lea     r8, [rbp+520h+Buffer]; lpBuffer
0x14000641b  mov     edx, edi; uID
0x14000641d  mov     rcx, rsi; hInstance
0x140006420  call    cs:__imp_LoadStringW
0x140006426  mov     rcx, [rbp+528h]; this
0x14000642d  test    eax, eax
0x14000642f  jz      loc_140006725
0x140006435  xor     edx, edx; Val
0x140006437  mov     r8d, 208h; Size
0x14000643d  lea     rcx, [rbp+520h+var_450]; void *
0x140006444  call    memset_0
0x140006449  mov     r9d, 104h; cchBufferMax
0x14000644f  lea     r8, [rbp+520h+var_450]; lpBuffer
0x140006456  mov     edx, ebx; uID
0x140006458  mov     rcx, rsi; hInstance
0x14000645b  call    cs:__imp_LoadStringW
0x140006461  mov     rcx, [rbp+528h]; this
0x140006468  test    eax, eax
0x14000646a  jz      loc_140006730
0x140006470  mov     [rbp+520h+var_480], r14
0x140006477  lea     rax, [rbp+520h+var_480]
0x14000647e  mov     [rsp+630h+ppv], rax; int
0x140006483  lea     r9, _GUID_df8e9480_ca73_448e_b8f0_da000f581428; riid
0x14000648a  xor     edx, edx; pUnkOuter
0x14000648c  lea     r8d, [rdx+4]; dwClsContext
0x140006490  lea     rcx, _GUID_0c9281f9_6da1_4006_8729_de6e6b61581c; rclsid
0x140006497  call    cs:__imp_CoCreateInstance
0x14000649d  mov     rcx, [rbp+528h]; this
0x1400064a4  test    eax, eax
0x1400064a6  js      loc_14000673B
0x1400064ac  mov     [rbp+520h+var_488], r14
0x1400064b3  mov     rcx, [rbp+520h+var_480]
0x1400064ba  mov     rax, [rcx]
0x1400064bd  lea     rdx, [rbp+520h+var_488]
0x1400064c4  mov     rax, [rax+18h]
0x1400064c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400064cd  mov     rcx, [rbp+528h]; this
0x1400064d4  test    eax, eax
0x1400064d6  js      loc_140006750
0x1400064dc  lea     rdx, [rbp+520h+var_450]
0x1400064e3  lea     rcx, [rbp+520h+var_4B0]
0x1400064e7  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x1400064ec  mov     rdi, rax
0x1400064ef  lea     rdx, [rbp+520h+Buffer]
0x1400064f6  lea     rcx, [rbp+520h+var_4D0]
0x1400064fa  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x1400064ff  mov     rbx, rax
0x140006502  lea     rdx, aLaunchMsSettin; "launch=\"ms-settings:datausage\" activa"...
0x140006509  lea     rcx, [rbp+520h+var_4F0]
0x14000650d  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x140006512  nop
0x140006513  mov     r8, rax
0x140006516  lea     rcx, [rbp+520h+var_510]
0x14000651a  call    ??$?H_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@QEB_W$$QEAV10@@Z; std::operator+<wchar_t>(wchar_t const * const,std::wstring &&)
0x14000651f  nop
0x140006520  lea     r8, aVisualBindingT; " >  <visual>    <binding template=\"Toa"...
0x140006527  mov     rdx, rax
0x14000652a  lea     rcx, [rbp+520h+var_530]
0x14000652e  call    ??$?H_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@$$QEAV10@QEB_W@Z; std::operator+<wchar_t>(std::wstring &&,wchar_t const * const)
0x140006533  nop
0x140006534  mov     r9, rbx
0x140006537  mov     r8, rax
0x14000653a  lea     rcx, [rbp+520h+var_570]
0x14000653e  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEAV01@1@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring &,std::wstring &)
0x140006543  nop
0x140006544  lea     r8, aTextTextId2; "</text>      <text id=\"2\">"
0x14000654b  lea     rdx, [rbp+520h+var_570]
0x14000654f  lea     rcx, [rbp+520h+var_550]
0x140006553  call    ??$?H_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@$$QEAV10@QEB_W@Z; std::operator+<wchar_t>(std::wstring &&,wchar_t const * const)
0x140006558  nop
0x140006559  mov     r9, rdi
0x14000655c  mov     r8, rax
0x14000655f  lea     rcx, [rbp+520h+var_590]
0x140006563  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEAV01@1@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring &,std::wstring &)
0x140006568  nop
0x140006569  lea     r8, aTextBindingVis; "</text>    </binding>  </visual></toast"...
0x140006570  lea     rdx, [rbp+520h+var_590]
0x140006574  lea     rcx, [rbp+520h+var_478]
0x14000657b  call    ??$?H_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@$$QEAV10@QEB_W@Z; std::operator+<wchar_t>(std::wstring &&,wchar_t const * const)
0x140006580  nop
0x140006581  lea     rcx, [rbp+520h+var_590]
0x140006585  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14000658a  nop
0x14000658b  lea     rcx, [rbp+520h+var_550]
0x14000658f  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140006594  nop
0x140006595  lea     rcx, [rbp+520h+var_570]
0x140006599  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14000659e  nop
0x14000659f  lea     rcx, [rbp+520h+var_530]
0x1400065a3  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400065a8  nop
0x1400065a9  lea     rcx, [rbp+520h+var_510]
0x1400065ad  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400065b2  nop
0x1400065b3  lea     rcx, [rbp+520h+var_4F0]
0x1400065b7  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400065bc  nop
0x1400065bd  lea     rcx, [rbp+520h+var_4D0]
0x1400065c1  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400065c6  nop
0x1400065c7  lea     rcx, [rbp+520h+var_4B0]
0x1400065cb  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400065d0  mov     [rbp+520h+var_490], r14d
0x1400065d7  xor     r8d, r8d
0x1400065da  lea     rdx, [rbp+520h+var_490]
0x1400065e1  xor     ecx, ecx
0x1400065e3  call    cs:__imp_RtlGetDeviceFamilyInfoEnum
0x1400065e9  cmp     [rbp+520h+var_490], 10h
0x1400065f0  setz    al
0x1400065f3  lea     rcx, aWindowsImmersi; "windows.immersivecontrolpanel_cw5n1h2tx"...
0x1400065fa  lea     rdx, aBaeaef159bab47; "BAEAEF15-9BAB-47FC-800B-ACECAD2AE94B_cw"...
0x140006601  test    al, al
0x140006603  cmovz   rdx, rcx
0x140006607  xor     r9d, r9d
0x14000660a  mov     [rbp+520h+var_48C], r14d
0x140006611  mov     rcx, [rbp+520h+var_488]
0x140006618  mov     rax, [rcx]
0x14000661b  lea     r8, [rbp+520h+var_478]
0x140006622  cmp     [rbp+520h+var_460], 7
0x14000662a  cmova   r8, [rbp+520h+var_478]
0x140006632  mov     [rbp+520h+var_5A0], r9
0x140006636  mov     [rbp+520h+var_598], r9d
0x14000663a  lea     r9, [rbp+520h+var_48C]
0x140006641  mov     [rsp+630h+var_5B8], r9
0x140006646  mov     [rsp+630h+var_5C0], r14d
0x14000664b  mov     [rsp+630h+var_5C8], r14
0x140006650  mov     [rsp+630h+var_5D0], r14
0x140006655  mov     [rsp+630h+var_5D8], r14
0x14000665a  mov     [rsp+630h+var_5E0], r14d
0x14000665f  mov     [rsp+630h+var_5E8], r14d
0x140006664  lea     r9, [rbp+520h+var_5A0]
0x140006668  mov     [rsp+630h+var_5F0], r9
0x14000666d  mov     [rsp+630h+var_5F8], r14
0x140006672  mov     [rsp+630h+var_600], r14
0x140006677  mov     [rsp+630h+var_608], r8
0x14000667c  mov     dword ptr [rsp+630h+ppv], r14d; int
0x140006681  xor     r9d, r9d
0x140006684  mov     r8, rdx
0x140006687  mov     rax, [rax+40h]
0x14000668b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006690  mov     rcx, [rbp+528h]; this
0x140006697  test    eax, eax
0x140006699  js      short loc_140006705
0x14000669b  lea     rcx, [rbp+520h+var_478]
0x1400066a2  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400066a7  nop
0x1400066a8  mov     rcx, [rbp+520h+var_488]
0x1400066af  test    rcx, rcx
0x1400066b2  jz      short loc_1400066C8
0x1400066b4  mov     [rbp+520h+var_488], r14
0x1400066bb  mov     rax, [rcx]
0x1400066be  mov     rax, [rax+10h]
0x1400066c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400066c7  nop
0x1400066c8  mov     rcx, [rbp+520h+var_480]
0x1400066cf  test    rcx, rcx
0x1400066d2  jz      short loc_1400066E8
0x1400066d4  mov     [rbp+520h+var_480], r14
0x1400066db  mov     rax, [rcx]
0x1400066de  mov     rax, [rax+10h]
0x1400066e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400066e7  nop
0x1400066e8  mov     rcx, [rbp+520h+var_30]
0x1400066ef  xor     rcx, rsp; StackCookie
0x1400066f2  call    __security_check_cookie
0x1400066f7  add     rsp, 610h
0x1400066fe  pop     r14
0x140006700  pop     rdi
0x140006701  pop     rsi
0x140006702  pop     rbx
0x140006703  pop     rbp
0x140006704  retn
0x140006705  mov     r9d, eax; char *
0x140006708  lea     r8, aOnecoreuapNetD; "onecoreuap\\net\\dusm\\task\\dusmtask.c"...
0x14000670f  mov     edx, 9Fh; void *
0x140006714  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x14000671a  mov     edx, 68h ; 'h'; void *
0x14000671f  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x140006725  mov     edx, 6Bh ; 'k'; void *
0x14000672a  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x140006730  mov     edx, 6Eh ; 'n'; void *
0x140006735  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x14000673b  mov     r9d, eax; char *
0x14000673e  lea     r8, aOnecoreuapNetD; "onecoreuap\\net\\dusm\\task\\dusmtask.c"...
0x140006745  mov     edx, 71h ; 'q'; void *
0x14000674a  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x140006750  mov     r9d, eax; char *
0x140006753  lea     r8, aOnecoreuapNetD; "onecoreuap\\net\\dusm\\task\\dusmtask.c"...
0x14000675a  mov     edx, 74h ; 't'; void *
0x14000675f  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
