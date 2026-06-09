# CMachineInfoV2::GetEnclosureKindPrivate(int &)

- ea: `0x1800afec8`
- end: `0x1800b0261`
- name: `?GetEnclosureKindPrivate@CMachineInfoV2@@CAJAEAH@Z`
- size: `921`
- prototype: `__int64 __fastcall(int *)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800afe90`

## callees

- `0x180008dc0`
- `0x180011ce4`
- `0x18001daf0`
- `0x18001dcc8`
- `0x180034dac`
- `0x18009f918`
- `0x1800afec8`
- `0x18018e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800aff40`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800aff40`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800aff6b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800aff6b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b01de`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b01f9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b0213`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b022d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b0247`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b01de`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b01f9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b0213`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b022d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b0247`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x1800aff24`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x1800affa5`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x1800b002a`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x1800b00e4`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x1800b015b`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x1800b01ae`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x1800aff24`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x1800affa5`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x1800b002a`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x1800b00e4`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x1800b015b`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x1800b01ae`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x1800afefe`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x1800afefe`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800affdf`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800affdf`

## string_xrefs

- `0x1800aff64`: `WindowsCreateStringReference`
- `0x1800aff39`: `api-ms-win-core-winrt-string-l1-1-0.dll`
- `0x1800b0078`: `onecore\base\appcompat\programs\devicecensus\dlls\machineinfov2.cpp`

## pseudocode

```c
__int64 __fastcall CMachineInfoV2::GetEnclosureKindPrivate(int *a1)
{
  int v2; // ebx
  int v3; // eax
  __int64 v4; // rdx
  __int64 v5; // rcx
  unsigned int v6; // esi
  __int64 v8; // rdx
  HMODULE Library; // rcx
  FARPROC ProcAddress; // rax
  Delayed::HStringReference *v11; // rax
  __int64 v12; // rdx
  int ActivationFactory; // r14d
  __int64 v14; // rcx
  int v15; // eax
  __int64 v16; // rdx
  unsigned int v17; // r14d
  __int64 v18; // rdx
  __int64 v19; // rcx
  __int64 v20; // rcx
  __int64 v21; // rcx
  __int64 v22; // rcx
  signed int v23; // eax
  int v24; // edx
  unsigned int v25; // r8d
  signed int v26; // eax
  int v27; // edx
  unsigned int v28; // r8d
  signed int v29; // eax
  int v30; // edx
  unsigned int v31; // r8d
  signed int LastError; // eax
  int v33; // edx
  unsigned int v34; // r8d
  int v35[2]; // [rsp+20h] [rbp-78h] BYREF
  HMODULE v36; // [rsp+28h] [rbp-70h]
  FARPROC v37; // [rsp+30h] [rbp-68h]
  int v38; // [rsp+38h] [rbp-60h]
  __int64 v39; // [rsp+40h] [rbp-58h] BYREF
  __int64 v40; // [rsp+48h] [rbp-50h] BYREF
  int v41; // [rsp+50h] [rbp-48h] BYREF
  _BYTE v42[32]; // [rsp+58h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]

  v2 = -2147221008;
  v38 = -2147221008;
  v3 = RoInitialize(1);
  v6 = v3;
  if ( v3 < 0 )
  {
    if ( v3 == -2147417850 )
      goto LABEL_8;
  }
  else
  {
    v2 = v3;
    v38 = v3;
  }
  if ( v3 < 0 )
  {
    if ( v2 >= 0 )
      RoUninitialize(v5, v4);
    return v6;
  }
LABEL_8:
  Library = LoadLibraryExW(L"api-ms-win-core-winrt-string-l1-1-0.dll", 0, 0x800u);
  *(_QWORD *)v35 = &Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable';
  v36 = Library;
  if ( Library )
  {
    ProcAddress = GetProcAddress(Library, "WindowsCreateStringReference");
    Library = v36;
  }
  else
  {
    ProcAddress = 0;
  }
  v37 = ProcAddress;
  if ( ProcAddress )
  {
    v40 = 0;
    v11 = Delayed::HStringReference::HStringReference(
            (Delayed::HStringReference *)v42,
            (const struct Delayed::api_ms_win_core_winrt_string_l1_1_0 *)v35,
            L"Windows.Devices.Enclosure.EnclosureInfo");
    ActivationFactory = RoGetActivationFactory(*(_QWORD *)v11, &GUID_5097bf9e_9dff_530a_b313_a5c20255d6b8, &v40);
    if ( ActivationFactory >= 0 )
    {
      v41 = 0;
      ___call_and_wait_for_completion_UIEnclosureInfoStatics_Enclosure_Devices_Windows__PEAPEAU__IAsyncOperation_PEAVEnclosureInfo_Enclosure_Devices_Windows___Foundation_4___Z__V_wil__YA_A_PPEAUIEnclosureInfoStatics_Enclosure_Devices_Windows__P81234_EAAJPEAPEAU__IAsyncOperation_PEAVEnclosureInfo_Enclosure_Devices_Windows___Foundation_4__Z_Z(
        &v39,
        v40);
      v15 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v39 + 48LL))(v39, &v41);
      v17 = v15;
      if ( v15 >= 0 )
      {
        v21 = v39;
        if ( v39 )
        {
          v39 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
        }
        *a1 = v41;
        v22 = v40;
        if ( v40 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
        *(_QWORD *)v35 = &Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable';
        if ( v36 )
        {
          if ( !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(v35) )
          {
            LastError = GetLastError();
            if ( LastError > 0 )
              LastError = (unsigned __int16)LastError | 0x80070000;
            Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)LastError, v33, v34);
            __debugbreak();
          }
          v36 = 0;
        }
        if ( v2 >= 0 )
          RoUninitialize(v22, v16);
        return 0;
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xB4,
          (unsigned int)"onecore\\base\\appcompat\\programs\\devicecensus\\dlls\\machineinfov2.cpp",
          (const char *)(unsigned int)v15,
          v35[0]);
        v19 = v39;
        if ( v39 )
        {
          v39 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
        }
        v20 = v40;
        if ( v40 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
        *(_QWORD *)v35 = &Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable';
        if ( v36 )
        {
          if ( !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(v35) )
          {
            v29 = GetLastError();
            if ( v29 > 0 )
              v29 = (unsigned __int16)v29 | 0x80070000;
            Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v29, v30, v31);
            __debugbreak();
          }
          v36 = 0;
        }
        if ( v2 >= 0 )
        {
          RoUninitialize(v20, v18);
          v38 = -2147221008;
        }
        return v17;
      }
    }
    else
    {
      v14 = v40;
      if ( v40 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
      *(_QWORD *)v35 = &Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable';
      if ( v36 )
      {
        if ( !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(v35) )
        {
          v26 = GetLastError();
          if ( v26 > 0 )
            v26 = (unsigned __int16)v26 | 0x80070000;
          Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v26, v27, v28);
          __debugbreak();
        }
        v36 = 0;
      }
      if ( v2 >= 0 )
        RoUninitialize(v14, v12);
      return (unsigned int)ActivationFactory;
    }
  }
  else
  {
    *(_QWORD *)v35 = &Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable';
    if ( Library )
    {
      if ( !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(v35) )
      {
        v23 = GetLastError();
        if ( v23 > 0 )
          v23 = (unsigned __int16)v23 | 0x80070000;
        Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v23, v24, v25);
        __debugbreak();
      }
      v36 = 0;
    }
    if ( v2 >= 0 )
      RoUninitialize(Library, v8);
    return 2147500033LL;
  }
}

```

## disassembly

```asm
0x1800afec8  mov     [rsp+arg_8], rbx
0x1800afecd  mov     [rsp+arg_10], rsi
0x1800afed2  push    rdi
0x1800afed3  push    r14
0x1800afed5  push    r15
0x1800afed7  sub     rsp, 80h
0x1800afede  mov     rax, cs:__security_cookie
0x1800afee5  xor     rax, rsp
0x1800afee8  mov     [rsp+98h+var_20], rax
0x1800afeed  mov     r15, rcx
0x1800afef0  mov     ebx, 800401F0h
0x1800afef5  mov     [rsp+98h+var_60], ebx
0x1800afef9  mov     ecx, 1
0x1800afefe  call    cs:__imp_RoInitialize
0x1800aff04  mov     esi, eax
0x1800aff06  xor     edi, edi
0x1800aff08  test    eax, eax
0x1800aff0a  js      short loc_1800AFF14
0x1800aff0c  mov     ebx, eax
0x1800aff0e  mov     [rsp+98h+var_60], eax
0x1800aff12  jmp     short loc_1800AFF1C
0x1800aff14  cmp     esi, 80010106h
0x1800aff1a  jz      short loc_1800AFF31
0x1800aff1c  test    esi, esi
0x1800aff1e  jns     short loc_1800AFF31
0x1800aff20  test    ebx, ebx
0x1800aff22  js      short loc_1800AFF2A
0x1800aff24  call    cs:__imp_RoUninitialize
0x1800aff2a  mov     eax, esi
0x1800aff2c  jmp     loc_1800B01B8
0x1800aff31  xor     edx, edx; hFile
0x1800aff33  mov     r8d, 800h; dwFlags
0x1800aff39  lea     rcx, aApiMsWinCoreWi_2; "api-ms-win-core-winrt-string-l1-1-0.dll"
0x1800aff40  call    cs:__imp_LoadLibraryExW
0x1800aff46  mov     rcx, rax; hModule
0x1800aff49  lea     rsi, ??_7?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable'
0x1800aff50  mov     qword ptr [rsp+98h+var_78], rsi; int
0x1800aff55  mov     [rsp+98h+var_70], rax
0x1800aff5a  test    rax, rax
0x1800aff5d  jnz     short loc_1800AFF64
0x1800aff5f  mov     rax, rdi
0x1800aff62  jmp     short loc_1800AFF76
0x1800aff64  lea     rdx, aWindowscreates; "WindowsCreateStringReference"
0x1800aff6b  call    cs:__imp_GetProcAddress
0x1800aff71  mov     rcx, [rsp+98h+var_70]
0x1800aff76  mov     [rsp+98h+var_68], rax
0x1800aff7b  test    rax, rax
0x1800aff7e  jnz     short loc_1800AFFB5
0x1800aff80  mov     qword ptr [rsp+98h+var_78], rsi
0x1800aff85  test    rcx, rcx
0x1800aff88  jz      short loc_1800AFFA1
0x1800aff8a  lea     rcx, [rsp+98h+var_78]
0x1800aff8f  call    ?InternalClose@?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(void)
0x1800aff94  test    al, al
0x1800aff96  jz      loc_1800B01DE
0x1800aff9c  mov     [rsp+98h+var_70], rdi
0x1800affa1  test    ebx, ebx
0x1800affa3  js      short loc_1800AFFAB
0x1800affa5  call    cs:__imp_RoUninitialize
0x1800affab  mov     eax, 80004001h
0x1800affb0  jmp     loc_1800B01B8
0x1800affb5  mov     [rsp+98h+var_50], rdi
0x1800affba  lea     r8, ?RuntimeClass_Windows_Devices_Enclosure_EnclosureInfo@@3QBGB; "Windows.Devices.Enclosure.EnclosureInfo"
0x1800affc1  lea     rdx, [rsp+98h+var_78]; struct Delayed::api_ms_win_core_winrt_string_l1_1_0 *
0x1800affc6  lea     rcx, [rsp+98h+var_40]; this
0x1800affcb  call    ??0HStringReference@Delayed@@QEAA@AEBVapi_ms_win_core_winrt_string_l1_1_0@1@PEBG@Z; Delayed::HStringReference::HStringReference(Delayed::api_ms_win_core_winrt_string_l1_1_0 const &,ushort const *)
0x1800affd0  lea     r8, [rsp+98h+var_50]
0x1800affd5  lea     rdx, _GUID_5097bf9e_9dff_530a_b313_a5c20255d6b8
0x1800affdc  mov     rcx, [rax]
0x1800affdf  call    cs:__imp_RoGetActivationFactory
0x1800affe5  mov     r14d, eax
0x1800affe8  test    eax, eax
0x1800affea  jns     short loc_1800B0038
0x1800affec  mov     rcx, [rsp+98h+var_50]
0x1800afff1  test    rcx, rcx
0x1800afff4  jz      short loc_1800B0003
0x1800afff6  mov     rdx, [rcx]
0x1800afff9  mov     rax, [rdx+10h]
0x1800afffd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b0002  nop
0x1800b0003  mov     qword ptr [rsp+98h+var_78], rsi
0x1800b0008  cmp     [rsp+98h+var_70], rdi
0x1800b000d  jz      short loc_1800B0026
0x1800b000f  lea     rcx, [rsp+98h+var_78]
0x1800b0014  call    ?InternalClose@?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(void)
0x1800b0019  test    al, al
0x1800b001b  jz      loc_1800B01F9
0x1800b0021  mov     [rsp+98h+var_70], rdi
0x1800b0026  test    ebx, ebx
0x1800b0028  js      short loc_1800B0030
0x1800b002a  call    cs:__imp_RoUninitialize
0x1800b0030  mov     eax, r14d
0x1800b0033  jmp     loc_1800B01B8
0x1800b0038  mov     [rsp+98h+var_48], edi
0x1800b003c  mov     rdx, [rsp+98h+var_50]
0x1800b0041  lea     rcx, [rsp+98h+var_58]
0x1800b0046  call    ??$call_and_wait_for_completion@UIEnclosureInfoStatics@Enclosure@Devices@Windows@@PEAPEAU?$IAsyncOperation@PEAVEnclosureInfo@Enclosure@Devices@Windows@@@Foundation@4@$$Z$$V@wil@@YA?A_PPEAUIEnclosureInfoStatics@Enclosure@Devices@Windows@@P81234@EAAJPEAPEAU?$IAsyncOperation@PEAVEnclosureInfo@Enclosure@Devices@Windows@@@Foundation@4@@Z@Z
0x1800b004b  nop
0x1800b004c  mov     rcx, [rsp+98h+var_58]
0x1800b0051  mov     rax, [rcx]
0x1800b0054  lea     rdx, [rsp+98h+var_48]
0x1800b0059  mov     rax, [rax+30h]
0x1800b005d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b0062  mov     r14d, eax
0x1800b0065  test    eax, eax
0x1800b0067  jns     loc_1800B00FA
0x1800b006d  mov     rcx, [rsp+98h]; this
0x1800b0075  mov     r9d, eax; char *
0x1800b0078  lea     r8, aOnecoreBaseApp_0; "onecore\\base\\appcompat\\programs\\dev"...
0x1800b007f  mov     edx, 0B4h; void *
0x1800b0084  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b0089  nop
0x1800b008a  mov     rcx, [rsp+98h+var_58]
0x1800b008f  test    rcx, rcx
0x1800b0092  jz      short loc_1800B00A6
0x1800b0094  mov     [rsp+98h+var_58], rdi
0x1800b0099  mov     rax, [rcx]
0x1800b009c  mov     rax, [rax+10h]
0x1800b00a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b00a5  nop
0x1800b00a6  mov     rcx, [rsp+98h+var_50]
0x1800b00ab  test    rcx, rcx
0x1800b00ae  jz      short loc_1800B00BD
0x1800b00b0  mov     rax, [rcx]
0x1800b00b3  mov     rax, [rax+10h]
0x1800b00b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b00bc  nop
0x1800b00bd  mov     qword ptr [rsp+98h+var_78], rsi
0x1800b00c2  cmp     [rsp+98h+var_70], rdi
0x1800b00c7  jz      short loc_1800B00E0
0x1800b00c9  lea     rcx, [rsp+98h+var_78]
0x1800b00ce  call    ?InternalClose@?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(void)
0x1800b00d3  test    al, al
0x1800b00d5  jz      loc_1800B0213
0x1800b00db  mov     [rsp+98h+var_70], rdi
0x1800b00e0  test    ebx, ebx
0x1800b00e2  js      short loc_1800B00F2
0x1800b00e4  call    cs:__imp_RoUninitialize
0x1800b00ea  mov     [rsp+98h+var_60], 800401F0h
0x1800b00f2  mov     eax, r14d
0x1800b00f5  jmp     loc_1800B01B8
0x1800b00fa  mov     rcx, [rsp+98h+var_58]
0x1800b00ff  test    rcx, rcx
0x1800b0102  jz      short loc_1800B0116
0x1800b0104  mov     [rsp+98h+var_58], rdi
0x1800b0109  mov     rax, [rcx]
0x1800b010c  mov     rax, [rax+10h]
0x1800b0110  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b0115  nop
0x1800b0116  mov     eax, [rsp+98h+var_48]
0x1800b011a  mov     [r15], eax
0x1800b011d  mov     rcx, [rsp+98h+var_50]
0x1800b0122  test    rcx, rcx
0x1800b0125  jz      short loc_1800B0134
0x1800b0127  mov     rax, [rcx]
0x1800b012a  mov     rax, [rax+10h]
0x1800b012e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b0133  nop
0x1800b0134  mov     qword ptr [rsp+98h+var_78], rsi
0x1800b0139  cmp     [rsp+98h+var_70], rdi
0x1800b013e  jz      short loc_1800B0157
0x1800b0140  lea     rcx, [rsp+98h+var_78]
0x1800b0145  call    ?InternalClose@?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(void)
0x1800b014a  test    al, al
0x1800b014c  jz      loc_1800B022D
0x1800b0152  mov     [rsp+98h+var_70], rdi
0x1800b0157  test    ebx, ebx
0x1800b0159  js      short loc_1800B0161
0x1800b015b  call    cs:__imp_RoUninitialize
0x1800b0161  xor     eax, eax
0x1800b0163  jmp     short loc_1800B01B8
0x1800b0165  mov     rcx, [rsp+98h+var_50]
0x1800b016a  xor     edi, edi
0x1800b016c  test    rcx, rcx
0x1800b016f  jz      short loc_1800B017E
0x1800b0171  mov     rax, [rcx]
0x1800b0174  mov     rax, [rax+10h]
0x1800b0178  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b017d  nop
0x1800b017e  lea     rsi, ??_7?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable'
0x1800b0185  mov     qword ptr [rsp+98h+var_78], rsi
0x1800b018a  cmp     [rsp+98h+var_70], rdi
0x1800b018f  jz      short loc_1800B01A8
0x1800b0191  lea     rcx, [rsp+98h+var_78]
0x1800b0196  call    ?InternalClose@?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(void)
0x1800b019b  test    al, al
0x1800b019d  jz      loc_1800B0247
0x1800b01a3  mov     [rsp+98h+var_70], rdi
0x1800b01a8  cmp     [rsp+98h+var_60], edi
0x1800b01ac  jl      short loc_1800B01B4
0x1800b01ae  call    cs:__imp_RoUninitialize
0x1800b01b4  mov     eax, dword ptr [rsp+98h+var_58]
0x1800b01b8  mov     rcx, [rsp+98h+var_20]
0x1800b01bd  xor     rcx, rsp; StackCookie
0x1800b01c0  call    __security_check_cookie
0x1800b01c5  lea     r11, [rsp+98h+var_18]
0x1800b01cd  mov     rbx, [r11+28h]
0x1800b01d1  mov     rsi, [r11+30h]
0x1800b01d5  mov     rsp, r11
0x1800b01d8  pop     r15
0x1800b01da  pop     r14
0x1800b01dc  pop     rdi
0x1800b01dd  retn
0x1800b01de  call    cs:__imp_GetLastError
0x1800b01e4  nop
0x1800b01e5  test    eax, eax
0x1800b01e7  jle     short loc_1800B01F1
0x1800b01e9  movzx   eax, ax
0x1800b01ec  or      eax, 80070000h
0x1800b01f1  mov     ecx, eax; this
0x1800b01f3  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x1800b01f8  int     3; Trap to Debugger
0x1800b01f9  call    cs:__imp_GetLastError
0x1800b01ff  test    eax, eax
0x1800b0201  jle     short loc_1800B020B
0x1800b0203  movzx   eax, ax
0x1800b0206  or      eax, 80070000h
0x1800b020b  mov     ecx, eax; this
0x1800b020d  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x1800b0212  int     3; Trap to Debugger
0x1800b0213  call    cs:__imp_GetLastError
0x1800b0219  test    eax, eax
0x1800b021b  jle     short loc_1800B0225
0x1800b021d  movzx   eax, ax
0x1800b0220  or      eax, 80070000h
0x1800b0225  mov     ecx, eax; this
0x1800b0227  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x1800b022c  int     3; Trap to Debugger
0x1800b022d  call    cs:__imp_GetLastError
0x1800b0233  test    eax, eax
0x1800b0235  jle     short loc_1800B023F
0x1800b0237  movzx   eax, ax
0x1800b023a  or      eax, 80070000h
0x1800b023f  mov     ecx, eax; this
0x1800b0241  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x1800b0246  int     3; Trap to Debugger
0x1800b0247  call    cs:__imp_GetLastError
0x1800b024d  test    eax, eax
0x1800b024f  jle     short loc_1800B0259
0x1800b0251  movzx   eax, ax
0x1800b0254  or      eax, 80070000h
0x1800b0259  mov     ecx, eax; this
0x1800b025b  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
