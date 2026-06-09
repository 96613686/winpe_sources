# MachineInfo::GetEnclosureKindPrivate(int &)

- ea: `0x18003ab98`
- end: `0x18003af31`
- name: `?GetEnclosureKindPrivate@MachineInfo@@CAJAEAH@Z`
- size: `921`
- prototype: `__int64 __fastcall(int *)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18003ab60`

## callees

- `0x180008dc0`
- `0x180011ce4`
- `0x18001daf0`
- `0x18001dcc8`
- `0x180034dac`
- `0x18003ab98`
- `0x18009f918`
- `0x18018e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18003ac10`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18003ac10`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003ac3b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003ac3b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003aeae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003aec9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003aee3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003aefd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003af17`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003aeae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003aec9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003aee3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003aefd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003af17`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x18003abf4`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x18003ac75`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x18003acfa`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x18003adb4`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x18003ae2b`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x18003ae7e`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x18003abf4`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x18003ac75`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x18003acfa`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x18003adb4`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x18003ae2b`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x18003ae7e`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x18003abce`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x18003abce`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18003acaf`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18003acaf`

## string_xrefs

- `0x18003ac34`: `WindowsCreateStringReference`
- `0x18003ac09`: `api-ms-win-core-winrt-string-l1-1-0.dll`
- `0x18003ad48`: `onecore\base\appcompat\programs\devicecensus\dlls\_machineinfo.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=8 #try_helpers=1
__int64 __fastcall MachineInfo::GetEnclosureKindPrivate(int *a1)
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
  _QWORD *v14; // rcx
  int v15; // eax
  __int64 v16; // rdx
  unsigned int v17; // r14d
  __int64 v18; // rdx
  __int64 v19; // rcx
  _QWORD *v20; // rcx
  __int64 v21; // rcx
  _QWORD *v22; // rcx
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
  _QWORD *v40; // [rsp+48h] [rbp-50h] BYREF
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
        (__int64)v40);
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
          (*(void (__fastcall **)(_QWORD *))(*v40 + 16LL))(v40);
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
          (void *)0xAB,
          (unsigned int)"onecore\\base\\appcompat\\programs\\devicecensus\\dlls\\_machineinfo.cpp",
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
          (*(void (__fastcall **)(_QWORD *))(*v40 + 16LL))(v40);
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
        (*(void (__fastcall **)(_QWORD *, _QWORD))(*v40 + 16LL))(v40, *v40);
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
0x18003ab98  mov     [rsp+arg_8], rbx
0x18003ab9d  mov     [rsp+arg_10], rsi
0x18003aba2  push    rdi
0x18003aba3  push    r14
0x18003aba5  push    r15
0x18003aba7  sub     rsp, 80h
0x18003abae  mov     rax, cs:__security_cookie
0x18003abb5  xor     rax, rsp
0x18003abb8  mov     [rsp+98h+var_20], rax
0x18003abbd  mov     r15, rcx
0x18003abc0  mov     ebx, 800401F0h
0x18003abc5  mov     [rsp+98h+var_60], ebx
0x18003abc9  mov     ecx, 1
0x18003abce  call    cs:__imp_RoInitialize
0x18003abd4  mov     esi, eax
0x18003abd6  xor     edi, edi
0x18003abd8  test    eax, eax
0x18003abda  js      short loc_18003ABE4
0x18003abdc  mov     ebx, eax
0x18003abde  mov     [rsp+98h+var_60], eax
0x18003abe2  jmp     short loc_18003ABEC
0x18003abe4  cmp     esi, 80010106h
0x18003abea  jz      short loc_18003AC01
0x18003abec  test    esi, esi
0x18003abee  jns     short loc_18003AC01
0x18003abf0  test    ebx, ebx
0x18003abf2  js      short loc_18003ABFA
0x18003abf4  call    cs:__imp_RoUninitialize
0x18003abfa  mov     eax, esi
0x18003abfc  jmp     loc_18003AE88
0x18003ac01  xor     edx, edx; hFile
0x18003ac03  mov     r8d, 800h; dwFlags
0x18003ac09  lea     rcx, aApiMsWinCoreWi_2; "api-ms-win-core-winrt-string-l1-1-0.dll"
0x18003ac10  call    cs:__imp_LoadLibraryExW
0x18003ac16  mov     rcx, rax; hModule
0x18003ac19  lea     rsi, ??_7?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable'
0x18003ac20  mov     qword ptr [rsp+98h+var_78], rsi; int
0x18003ac25  mov     [rsp+98h+var_70], rax
0x18003ac2a  test    rax, rax
0x18003ac2d  jnz     short loc_18003AC34
0x18003ac2f  mov     rax, rdi
0x18003ac32  jmp     short loc_18003AC46
0x18003ac34  lea     rdx, aWindowscreates; "WindowsCreateStringReference"
0x18003ac3b  call    cs:__imp_GetProcAddress
0x18003ac41  mov     rcx, [rsp+98h+var_70]
0x18003ac46  mov     [rsp+98h+var_68], rax
0x18003ac4b  test    rax, rax
0x18003ac4e  jnz     short loc_18003AC85
0x18003ac50  mov     qword ptr [rsp+98h+var_78], rsi
0x18003ac55  test    rcx, rcx
0x18003ac58  jz      short loc_18003AC71
0x18003ac5a  lea     rcx, [rsp+98h+var_78]
0x18003ac5f  call    ?InternalClose@?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(void)
0x18003ac64  test    al, al
0x18003ac66  jz      loc_18003AEAE
0x18003ac6c  mov     [rsp+98h+var_70], rdi
0x18003ac71  test    ebx, ebx
0x18003ac73  js      short loc_18003AC7B
0x18003ac75  call    cs:__imp_RoUninitialize
0x18003ac7b  mov     eax, 80004001h
0x18003ac80  jmp     loc_18003AE88
0x18003ac85  mov     [rsp+98h+var_50], rdi
0x18003ac8a  lea     r8, ?RuntimeClass_Windows_Devices_Enclosure_EnclosureInfo@@3QBGB; "Windows.Devices.Enclosure.EnclosureInfo"
0x18003ac91  lea     rdx, [rsp+98h+var_78]; struct Delayed::api_ms_win_core_winrt_string_l1_1_0 *
0x18003ac96  lea     rcx, [rsp+98h+var_40]; this
0x18003ac9b  call    ??0HStringReference@Delayed@@QEAA@AEBVapi_ms_win_core_winrt_string_l1_1_0@1@PEBG@Z; Delayed::HStringReference::HStringReference(Delayed::api_ms_win_core_winrt_string_l1_1_0 const &,ushort const *)
0x18003aca0  lea     r8, [rsp+98h+var_50]
0x18003aca5  lea     rdx, _GUID_5097bf9e_9dff_530a_b313_a5c20255d6b8
0x18003acac  mov     rcx, [rax]
0x18003acaf  call    cs:__imp_RoGetActivationFactory
0x18003acb5  mov     r14d, eax
0x18003acb8  test    eax, eax
0x18003acba  jns     short loc_18003AD08
0x18003acbc  mov     rcx, [rsp+98h+var_50]
0x18003acc1  test    rcx, rcx
0x18003acc4  jz      short loc_18003ACD3
0x18003acc6  mov     rdx, [rcx]
0x18003acc9  mov     rax, [rdx+10h]
0x18003accd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003acd2  nop
0x18003acd3  mov     qword ptr [rsp+98h+var_78], rsi
0x18003acd8  cmp     [rsp+98h+var_70], rdi
0x18003acdd  jz      short loc_18003ACF6
0x18003acdf  lea     rcx, [rsp+98h+var_78]
0x18003ace4  call    ?InternalClose@?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(void)
0x18003ace9  test    al, al
0x18003aceb  jz      loc_18003AEC9
0x18003acf1  mov     [rsp+98h+var_70], rdi
0x18003acf6  test    ebx, ebx
0x18003acf8  js      short loc_18003AD00
0x18003acfa  call    cs:__imp_RoUninitialize
0x18003ad00  mov     eax, r14d
0x18003ad03  jmp     loc_18003AE88
0x18003ad08  mov     [rsp+98h+var_48], edi
0x18003ad0c  mov     rdx, [rsp+98h+var_50]
0x18003ad11  lea     rcx, [rsp+98h+var_58]
0x18003ad16  call    ??$call_and_wait_for_completion@UIEnclosureInfoStatics@Enclosure@Devices@Windows@@PEAPEAU?$IAsyncOperation@PEAVEnclosureInfo@Enclosure@Devices@Windows@@@Foundation@4@$$Z$$V@wil@@YA?A_PPEAUIEnclosureInfoStatics@Enclosure@Devices@Windows@@P81234@EAAJPEAPEAU?$IAsyncOperation@PEAVEnclosureInfo@Enclosure@Devices@Windows@@@Foundation@4@@Z@Z
0x18003ad1b  nop
0x18003ad1c  mov     rcx, [rsp+98h+var_58]
0x18003ad21  mov     rax, [rcx]
0x18003ad24  lea     rdx, [rsp+98h+var_48]
0x18003ad29  mov     rax, [rax+30h]
0x18003ad2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ad32  mov     r14d, eax
0x18003ad35  test    eax, eax
0x18003ad37  jns     loc_18003ADCA
0x18003ad3d  mov     rcx, [rsp+98h]; this
0x18003ad45  mov     r9d, eax; char *
0x18003ad48  lea     r8, aOnecoreBaseApp_8; "onecore\\base\\appcompat\\programs\\dev"...
0x18003ad4f  mov     edx, 0ABh; void *
0x18003ad54  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003ad59  nop
0x18003ad5a  mov     rcx, [rsp+98h+var_58]
0x18003ad5f  test    rcx, rcx
0x18003ad62  jz      short loc_18003AD76
0x18003ad64  mov     [rsp+98h+var_58], rdi
0x18003ad69  mov     rax, [rcx]
0x18003ad6c  mov     rax, [rax+10h]
0x18003ad70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ad75  nop
0x18003ad76  mov     rcx, [rsp+98h+var_50]
0x18003ad7b  test    rcx, rcx
0x18003ad7e  jz      short loc_18003AD8D
0x18003ad80  mov     rax, [rcx]
0x18003ad83  mov     rax, [rax+10h]
0x18003ad87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ad8c  nop
0x18003ad8d  mov     qword ptr [rsp+98h+var_78], rsi
0x18003ad92  cmp     [rsp+98h+var_70], rdi
0x18003ad97  jz      short loc_18003ADB0
0x18003ad99  lea     rcx, [rsp+98h+var_78]
0x18003ad9e  call    ?InternalClose@?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(void)
0x18003ada3  test    al, al
0x18003ada5  jz      loc_18003AEE3
0x18003adab  mov     [rsp+98h+var_70], rdi
0x18003adb0  test    ebx, ebx
0x18003adb2  js      short loc_18003ADC2
0x18003adb4  call    cs:__imp_RoUninitialize
0x18003adba  mov     [rsp+98h+var_60], 800401F0h
0x18003adc2  mov     eax, r14d
0x18003adc5  jmp     loc_18003AE88
0x18003adca  mov     rcx, [rsp+98h+var_58]
0x18003adcf  test    rcx, rcx
0x18003add2  jz      short loc_18003ADE6
0x18003add4  mov     [rsp+98h+var_58], rdi
0x18003add9  mov     rax, [rcx]
0x18003addc  mov     rax, [rax+10h]
0x18003ade0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ade5  nop
0x18003ade6  mov     eax, [rsp+98h+var_48]
0x18003adea  mov     [r15], eax
0x18003aded  mov     rcx, [rsp+98h+var_50]
0x18003adf2  test    rcx, rcx
0x18003adf5  jz      short loc_18003AE04
0x18003adf7  mov     rax, [rcx]
0x18003adfa  mov     rax, [rax+10h]
0x18003adfe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ae03  nop
0x18003ae04  mov     qword ptr [rsp+98h+var_78], rsi
0x18003ae09  cmp     [rsp+98h+var_70], rdi
0x18003ae0e  jz      short loc_18003AE27
0x18003ae10  lea     rcx, [rsp+98h+var_78]
0x18003ae15  call    ?InternalClose@?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(void)
0x18003ae1a  test    al, al
0x18003ae1c  jz      loc_18003AEFD
0x18003ae22  mov     [rsp+98h+var_70], rdi
0x18003ae27  test    ebx, ebx
0x18003ae29  js      short loc_18003AE31
0x18003ae2b  call    cs:__imp_RoUninitialize
0x18003ae31  xor     eax, eax
0x18003ae33  jmp     short loc_18003AE88
0x18003ae35  mov     rcx, [rsp+98h+var_50]
0x18003ae3a  xor     edi, edi
0x18003ae3c  test    rcx, rcx
0x18003ae3f  jz      short loc_18003AE4E
0x18003ae41  mov     rax, [rcx]
0x18003ae44  mov     rax, [rax+10h]
0x18003ae48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ae4d  nop
0x18003ae4e  lea     rsi, ??_7?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable'
0x18003ae55  mov     qword ptr [rsp+98h+var_78], rsi
0x18003ae5a  cmp     [rsp+98h+var_70], rdi
0x18003ae5f  jz      short loc_18003AE78
0x18003ae61  lea     rcx, [rsp+98h+var_78]
0x18003ae66  call    ?InternalClose@?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(void)
0x18003ae6b  test    al, al
0x18003ae6d  jz      loc_18003AF17
0x18003ae73  mov     [rsp+98h+var_70], rdi
0x18003ae78  cmp     [rsp+98h+var_60], edi
0x18003ae7c  jl      short loc_18003AE84
0x18003ae7e  call    cs:__imp_RoUninitialize
0x18003ae84  mov     eax, dword ptr [rsp+98h+var_58]
0x18003ae88  mov     rcx, [rsp+98h+var_20]
0x18003ae8d  xor     rcx, rsp; StackCookie
0x18003ae90  call    __security_check_cookie
0x18003ae95  lea     r11, [rsp+98h+var_18]
0x18003ae9d  mov     rbx, [r11+28h]
0x18003aea1  mov     rsi, [r11+30h]
0x18003aea5  mov     rsp, r11
0x18003aea8  pop     r15
0x18003aeaa  pop     r14
0x18003aeac  pop     rdi
0x18003aead  retn
0x18003aeae  call    cs:__imp_GetLastError
0x18003aeb4  nop
0x18003aeb5  test    eax, eax
0x18003aeb7  jle     short loc_18003AEC1
0x18003aeb9  movzx   eax, ax
0x18003aebc  or      eax, 80070000h
0x18003aec1  mov     ecx, eax; this
0x18003aec3  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x18003aec8  int     3; Trap to Debugger
0x18003aec9  call    cs:__imp_GetLastError
0x18003aecf  test    eax, eax
0x18003aed1  jle     short loc_18003AEDB
0x18003aed3  movzx   eax, ax
0x18003aed6  or      eax, 80070000h
0x18003aedb  mov     ecx, eax; this
0x18003aedd  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x18003aee2  int     3; Trap to Debugger
0x18003aee3  call    cs:__imp_GetLastError
0x18003aee9  test    eax, eax
0x18003aeeb  jle     short loc_18003AEF5
0x18003aeed  movzx   eax, ax
0x18003aef0  or      eax, 80070000h
0x18003aef5  mov     ecx, eax; this
0x18003aef7  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x18003aefc  int     3; Trap to Debugger
0x18003aefd  call    cs:__imp_GetLastError
0x18003af03  test    eax, eax
0x18003af05  jle     short loc_18003AF0F
0x18003af07  movzx   eax, ax
0x18003af0a  or      eax, 80070000h
0x18003af0f  mov     ecx, eax; this
0x18003af11  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x18003af16  int     3; Trap to Debugger
0x18003af17  call    cs:__imp_GetLastError
0x18003af1d  test    eax, eax
0x18003af1f  jle     short loc_18003AF29
0x18003af21  movzx   eax, ax
0x18003af24  or      eax, 80070000h
0x18003af29  mov     ecx, eax; this
0x18003af2b  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
