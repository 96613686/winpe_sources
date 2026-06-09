# WUInfo::GetWUDODownloadMode(void)

- ea: `0x180095560`
- end: `0x180095860`
- name: `?GetWUDODownloadMode@WUInfo@@AEBAIXZ`
- size: `768`
- prototype: `unsigned int __fastcall(WUInfo *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180008dc0`
- `0x18001daf0`
- `0x18001dcc8`
- `0x18002a760`
- `0x180095560`
- `0x1800d2e3c`
- `0x18018e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800955d6`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800955d6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180095624`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180095624`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180095811`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009582c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180095846`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180095811`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009582c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180095846`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x18009560f`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x18009560f`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x1800955a5`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x1800955a5`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800956ee`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800956ee`

## string_xrefs

- `0x18009561a`: `WindowsCreateStringReference`
- `0x1800955cf`: `api-ms-win-core-winrt-string-l1-1-0.dll`
- `0x1800957e5`: `SOFTWARE\Microsoft\Windows\CurrentVersion\DeliveryOptimization\Config`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall WUInfo::GetWUDODownloadMode(WUInfo *this, unsigned __int16 a2, unsigned __int16 a3)
{
  int v3; // ebx
  int v4; // eax
  __int64 v5; // rdx
  __int64 v6; // rcx
  unsigned int v7; // edi
  HMODULE Library; // rax
  FARPROC ProcAddress; // rax
  int ActivationFactory; // eax
  __int64 v11; // rcx
  signed int LastError; // eax
  int v14; // edx
  unsigned int v15; // r8d
  signed int v16; // eax
  int v17; // edx
  unsigned int v18; // r8d
  signed int v19; // eax
  int v20; // edx
  unsigned int v21; // r8d
  __int64 v22; // [rsp+30h] [rbp-39h] BYREF
  const int *v23; // [rsp+38h] [rbp-31h] BYREF
  HMODULE v24; // [rsp+40h] [rbp-29h]
  int v25; // [rsp+48h] [rbp-21h] BYREF
  __int64 v26; // [rsp+50h] [rbp-19h] BYREF
  int v27; // [rsp+58h] [rbp-11h]
  __int64 v28; // [rsp+60h] [rbp-9h] BYREF
  __int64 v29; // [rsp+68h] [rbp-1h] BYREF
  __int128 v30; // [rsp+70h] [rbp+7h]

  if ( !IsWindowsVersionOrGreaterEx((unsigned __int16)this, a2, a3, 0x4563u) )
    return (unsigned int)Utils::GetRegistryKeyDWORDOrDefault(
                           L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\DeliveryOptimization\\Config",
                           L"DODownloadMode",
                           0xFFFFFFFF);
  v3 = -2147221008;
  v27 = -2147221008;
  v4 = RoInitialize(1);
  v7 = v4;
  if ( v4 < 0 )
  {
    if ( v4 == -2147417850 )
      goto LABEL_6;
  }
  else
  {
    v3 = v4;
    v27 = v4;
  }
  if ( v4 < 0 )
    goto LABEL_8;
LABEL_6:
  v7 = -1;
  Library = LoadLibraryExW(L"api-ms-win-core-winrt-string-l1-1-0.dll", 0, 0x800u);
  v23 = &Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable';
  v24 = Library;
  v28 = 0;
  v29 = 0;
  v30 = 0;
  v22 = 0;
  if ( !Library )
  {
    v23 = &Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable';
    goto LABEL_8;
  }
  ProcAddress = GetProcAddress(Library, "WindowsCreateStringReference");
  if ( !ProcAddress )
  {
    v6 = v22;
    v23 = &Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable';
    if ( !v24 )
      goto LABEL_8;
    if ( !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(&v23) )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)LastError, v14, v15);
      __debugbreak();
    }
    goto LABEL_13;
  }
  if ( ((int (__fastcall *)(const unsigned __int16 *, __int64, __int64 *, __int64 *))ProcAddress)(
         L"Windows.ApplicationModel.Store.Preview.DeliveryOptimizationSettings",
         67,
         &v29,
         &v28) >= 0 )
  {
    ActivationFactory = RoGetActivationFactory(v28, &GUID_5c817caf_aed5_5999_b4c9_8c60898bc4f3, &v22);
    v6 = v22;
    if ( ActivationFactory >= 0 && v22 )
    {
      v26 = 0;
      if ( (*(int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v22 + 48LL))(v22, &v26) >= 0 )
      {
        if ( v26 )
        {
          v25 = 0;
          if ( (*(int (__fastcall **)(__int64, int *))(*(_QWORD *)v26 + 48LL))(v26, &v25) >= 0 )
          {
            if ( v25 )
            {
              switch ( v25 )
              {
                case 1:
                  v7 = 0;
                  break;
                case 2:
                  v7 = 1;
                  break;
                case 3:
                  v7 = 2;
                  break;
                case 4:
                  v7 = 3;
                  break;
                case 5:
                  v7 = 100;
                  break;
              }
            }
            else
            {
              v7 = 99;
            }
          }
        }
      }
      v11 = v26;
      if ( v26 )
      {
        v26 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
      }
      v6 = v22;
    }
    if ( v6 )
    {
      v22 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
    }
    v23 = &Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable';
    if ( !v24 )
      goto LABEL_8;
    if ( !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(&v23) )
    {
      v19 = GetLastError();
      if ( v19 > 0 )
        v19 = (unsigned __int16)v19 | 0x80070000;
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v19, v20, v21);
      JUMPOUT(0x18009585FLL);
    }
    goto LABEL_13;
  }
  v6 = v22;
  v23 = &Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable';
  if ( v24 )
  {
    if ( !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(&v23) )
    {
      v16 = GetLastError();
      if ( v16 > 0 )
        v16 = (unsigned __int16)v16 | 0x80070000;
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v16, v17, v18);
      __debugbreak();
    }
LABEL_13:
    v24 = 0;
  }
LABEL_8:
  if ( v3 >= 0 )
    RoUninitialize(v6, v5);
  return v7;
}

```

## disassembly

```asm
0x180095560  push    rbp
0x180095562  push    rbx
0x180095563  push    rsi
0x180095564  push    rdi
0x180095565  push    r14
0x180095567  push    r15
0x180095569  lea     rbp, [rsp-2Fh]
0x18009556e  sub     rsp, 98h
0x180095575  mov     rax, cs:__security_cookie
0x18009557c  xor     rax, rsp
0x18009557f  mov     [rbp+57h+var_40], rax
0x180095583  mov     r9d, 4563h; unsigned __int16
0x180095589  call    ?IsWindowsVersionOrGreaterEx@@YA_NGGGG@Z; IsWindowsVersionOrGreaterEx(ushort,ushort,ushort,ushort)
0x18009558e  xor     r14d, r14d
0x180095591  test    al, al
0x180095593  jz      loc_1800957DA
0x180095599  mov     ebx, 800401F0h
0x18009559e  mov     [rbp+57h+var_68], ebx
0x1800955a1  lea     ecx, [r14+1]
0x1800955a5  call    cs:__imp_RoInitialize
0x1800955ab  mov     edi, eax
0x1800955ad  test    eax, eax
0x1800955af  js      short loc_1800955B8
0x1800955b1  mov     ebx, eax
0x1800955b3  mov     [rbp+57h+var_68], eax
0x1800955b6  jmp     short loc_1800955C0
0x1800955b8  cmp     edi, 80010106h
0x1800955be  jz      short loc_1800955C4
0x1800955c0  test    edi, edi
0x1800955c2  js      short loc_180095607
0x1800955c4  or      edi, 0FFFFFFFFh
0x1800955c7  xor     edx, edx; hFile
0x1800955c9  mov     r8d, 800h; dwFlags
0x1800955cf  lea     rcx, aApiMsWinCoreWi_2; "api-ms-win-core-winrt-string-l1-1-0.dll"
0x1800955d6  call    cs:__imp_LoadLibraryExW
0x1800955dc  lea     r15, ??_7?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable'
0x1800955e3  mov     [rbp+57h+var_88], r15
0x1800955e7  mov     [rbp+57h+var_80], rax
0x1800955eb  mov     [rbp+57h+var_60], r14
0x1800955ef  mov     [rbp+57h+var_58], r14
0x1800955f3  xorps   xmm0, xmm0
0x1800955f6  movups  [rbp+57h+var_50], xmm0
0x1800955fa  mov     [rbp+57h+var_90], r14
0x1800955fe  test    rax, rax
0x180095601  jnz     short loc_18009561A
0x180095603  mov     [rbp+57h+var_88], r15
0x180095607  test    ebx, ebx
0x180095609  js      loc_1800957F3
0x18009560f  call    cs:__imp_RoUninitialize
0x180095615  jmp     loc_1800957F3
0x18009561a  lea     rdx, aWindowscreates; "WindowsCreateStringReference"
0x180095621  mov     rcx, rax; hModule
0x180095624  call    cs:__imp_GetProcAddress
0x18009562a  test    rax, rax
0x18009562d  jnz     short loc_18009566A
0x18009562f  mov     rcx, [rbp+57h+var_90]
0x180095633  test    rcx, rcx
0x180095636  jz      short loc_180095649
0x180095638  mov     [rbp+57h+var_90], r14
0x18009563c  mov     rax, [rcx]
0x18009563f  mov     rax, [rax+10h]
0x180095643  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180095648  nop
0x180095649  mov     [rbp+57h+var_88], r15
0x18009564d  cmp     [rbp+57h+var_80], r14
0x180095651  jz      short loc_180095607
0x180095653  lea     rcx, [rbp+57h+var_88]
0x180095657  call    ?InternalClose@?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(void)
0x18009565c  test    al, al
0x18009565e  jz      loc_180095811
0x180095664  mov     [rbp+57h+var_80], r14
0x180095668  jmp     short loc_180095607
0x18009566a  lea     r9, [rbp+57h+var_60]
0x18009566e  lea     r8, [rbp+57h+var_58]
0x180095672  mov     edx, 43h ; 'C'
0x180095677  lea     rcx, ?RuntimeClass_Windows_ApplicationModel_Store_Preview_DeliveryOptimizationSettings@@3QBGB; "Windows.ApplicationModel.Store.Preview."...
0x18009567e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180095683  test    eax, eax
0x180095685  jns     short loc_1800956C2
0x180095687  mov     rcx, [rbp+57h+var_90]
0x18009568b  test    rcx, rcx
0x18009568e  jz      short loc_1800956A1
0x180095690  mov     [rbp+57h+var_90], r14
0x180095694  mov     rax, [rcx]
0x180095697  mov     rax, [rax+10h]
0x18009569b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800956a0  nop
0x1800956a1  mov     [rbp+57h+var_88], r15
0x1800956a5  cmp     [rbp+57h+var_80], r14
0x1800956a9  jz      loc_180095607
0x1800956af  lea     rcx, [rbp+57h+var_88]
0x1800956b3  call    ?InternalClose@?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(void)
0x1800956b8  test    al, al
0x1800956ba  jz      loc_18009582C
0x1800956c0  jmp     short loc_180095664
0x1800956c2  mov     rsi, [rbp+57h+var_60]
0x1800956c6  mov     rcx, [rbp+57h+var_90]
0x1800956ca  test    rcx, rcx
0x1800956cd  jz      short loc_1800956E0
0x1800956cf  mov     [rbp+57h+var_90], r14
0x1800956d3  mov     rax, [rcx]
0x1800956d6  mov     rax, [rax+10h]
0x1800956da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800956df  nop
0x1800956e0  lea     r8, [rbp+57h+var_90]
0x1800956e4  lea     rdx, _GUID_5c817caf_aed5_5999_b4c9_8c60898bc4f3
0x1800956eb  mov     rcx, rsi
0x1800956ee  call    cs:__imp_RoGetActivationFactory
0x1800956f4  mov     rcx, [rbp+57h+var_90]
0x1800956f8  test    eax, eax
0x1800956fa  js      loc_1800957A4
0x180095700  test    rcx, rcx
0x180095703  jz      loc_1800957A4
0x180095709  mov     [rbp+57h+var_70], r14
0x18009570d  mov     rax, [rcx]
0x180095710  lea     rdx, [rbp+57h+var_70]
0x180095714  mov     rax, [rax+30h]
0x180095718  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009571d  test    eax, eax
0x18009571f  js      short loc_180095786
0x180095721  mov     rcx, [rbp+57h+var_70]
0x180095725  test    rcx, rcx
0x180095728  jz      short loc_180095786
0x18009572a  mov     [rbp+57h+var_78], r14d
0x18009572e  mov     rax, [rcx]
0x180095731  lea     rdx, [rbp+57h+var_78]
0x180095735  mov     rax, [rax+30h]
0x180095739  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009573e  test    eax, eax
0x180095740  js      short loc_180095786
0x180095742  mov     ecx, [rbp+57h+var_78]
0x180095745  test    ecx, ecx
0x180095747  jz      short loc_180095781
0x180095749  sub     ecx, 1
0x18009574c  jz      short loc_18009577C
0x18009574e  sub     ecx, 1
0x180095751  jz      short loc_180095775
0x180095753  sub     ecx, 1
0x180095756  jz      short loc_18009576E
0x180095758  sub     ecx, 1
0x18009575b  jz      short loc_180095767
0x18009575d  cmp     ecx, 1
0x180095760  jnz     short loc_180095786
0x180095762  lea     edi, [rcx+63h]
0x180095765  jmp     short loc_180095786
0x180095767  mov     edi, 3
0x18009576c  jmp     short loc_180095786
0x18009576e  mov     edi, 2
0x180095773  jmp     short loc_180095786
0x180095775  mov     edi, 1
0x18009577a  jmp     short loc_180095786
0x18009577c  mov     edi, r14d
0x18009577f  jmp     short loc_180095786
0x180095781  mov     edi, 63h ; 'c'
0x180095786  mov     rcx, [rbp+57h+var_70]
0x18009578a  test    rcx, rcx
0x18009578d  jz      short loc_1800957A0
0x18009578f  mov     [rbp+57h+var_70], r14
0x180095793  mov     rax, [rcx]
0x180095796  mov     rax, [rax+10h]
0x18009579a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009579f  nop
0x1800957a0  mov     rcx, [rbp+57h+var_90]
0x1800957a4  test    rcx, rcx
0x1800957a7  jz      short loc_1800957BA
0x1800957a9  mov     [rbp+57h+var_90], r14
0x1800957ad  mov     rax, [rcx]
0x1800957b0  mov     rax, [rax+10h]
0x1800957b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800957b9  nop
0x1800957ba  mov     [rbp+57h+var_88], r15
0x1800957be  cmp     [rbp+57h+var_80], r14
0x1800957c2  jz      loc_180095607
0x1800957c8  lea     rcx, [rbp+57h+var_88]
0x1800957cc  call    ?InternalClose@?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(void)
0x1800957d1  test    al, al
0x1800957d3  jz      short loc_180095846
0x1800957d5  jmp     loc_180095664
0x1800957da  or      r8d, 0FFFFFFFFh; unsigned int
0x1800957de  lea     rdx, aDodownloadmode; "DODownloadMode"
0x1800957e5  lea     rcx, aSoftwareMicros_52; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1800957ec  call    ?GetRegistryKeyDWORDOrDefault@Utils@@SAKPEBG0K@Z; Utils::GetRegistryKeyDWORDOrDefault(ushort const *,ushort const *,ulong)
0x1800957f1  mov     edi, eax
0x1800957f3  mov     eax, edi
0x1800957f5  mov     rcx, [rbp+57h+var_40]
0x1800957f9  xor     rcx, rsp; StackCookie
0x1800957fc  call    __security_check_cookie
0x180095801  add     rsp, 98h
0x180095808  pop     r15
0x18009580a  pop     r14
0x18009580c  pop     rdi
0x18009580d  pop     rsi
0x18009580e  pop     rbx
0x18009580f  pop     rbp
0x180095810  retn
0x180095811  call    cs:__imp_GetLastError
0x180095817  nop
0x180095818  test    eax, eax
0x18009581a  jle     short loc_180095824
0x18009581c  movzx   eax, ax
0x18009581f  or      eax, 80070000h
0x180095824  mov     ecx, eax; this
0x180095826  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x18009582b  int     3; Trap to Debugger
0x18009582c  call    cs:__imp_GetLastError
0x180095832  test    eax, eax
0x180095834  jle     short loc_18009583E
0x180095836  movzx   eax, ax
0x180095839  or      eax, 80070000h
0x18009583e  mov     ecx, eax; this
0x180095840  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x180095845  int     3; Trap to Debugger
0x180095846  call    cs:__imp_GetLastError
0x18009584c  test    eax, eax
0x18009584e  jle     short loc_180095858
0x180095850  movzx   eax, ax
0x180095853  or      eax, 80070000h
0x180095858  mov     ecx, eax; this
0x18009585a  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
