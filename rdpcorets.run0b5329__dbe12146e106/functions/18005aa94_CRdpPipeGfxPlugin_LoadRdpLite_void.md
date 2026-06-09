# CRdpPipeGfxPlugin::LoadRdpLite(void)

- ea: `0x18005aa94`
- end: `0x18005add5`
- name: `?LoadRdpLite@CRdpPipeGfxPlugin@@AEAAJXZ`
- size: `833`
- prototype: `__int64 __fastcall(CRdpPipeGfxPlugin *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x18005af90`

## callees

- `0x1800015f0`
- `0x180010960`
- `0x18001569c`
- `0x180033da0`
- `0x180034970`
- `0x18005aa94`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18005ac86`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18005ac86`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18005ab0a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18005ab0a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18005aaed`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18005aaed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005ab1d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005abd2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005ad9a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005ab1d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005abd2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005ad9a`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18005ad88`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18005ad88`

## string_xrefs

- `0x18005ab74`: `clientcore\termsrv\rdp_bin\win\rdpcorets\umrdppipegfxplugin.cpp`
- `0x18005ac29`: `clientcore\termsrv\rdp_bin\win\rdpcorets\umrdppipegfxplugin.cpp`
- `0x18005acf0`: `clientcore\termsrv\rdp_bin\win\rdpcorets\umrdppipegfxplugin.cpp`
- `0x18005ac97`: `rdplite.dll`
- `0x18005acc5`: `StringCchCat of file path failed`
- `0x18005ad5f`: `Loading rdplite.dll: `

## pseudocode

```c
__int64 __fastcall CRdpPipeGfxPlugin::LoadRdpLite(CRdpPipeGfxPlugin *this)
{
  signed int LastError; // eax
  int v3; // ecx
  int v4; // r8d
  int v5; // r9d
  signed int v6; // ebx
  signed int v7; // eax
  int v8; // ecx
  int v9; // r8d
  int v10; // r9d
  wchar_t *v11; // rax
  int v12; // ecx
  int v13; // r8d
  int v14; // r9d
  HMODULE LibraryW; // rax
  signed int v16; // eax
  int v18; // [rsp+50h] [rbp-B0h] BYREF
  int v19; // [rsp+54h] [rbp-ACh] BYREF
  const char *v20; // [rsp+58h] [rbp-A8h] BYREF
  const char *v21; // [rsp+60h] [rbp-A0h] BYREF
  const char *v22; // [rsp+68h] [rbp-98h] BYREF
  const char *v23; // [rsp+70h] [rbp-90h] BYREF
  HMODULE phModule; // [rsp+78h] [rbp-88h] BYREF
  WCHAR Filename[264]; // [rsp+80h] [rbp-80h] BYREF

  phModule = 0;
  memset_0(Filename, 0, 0x20Au);
  if ( GetModuleHandleExW(6u, (LPCWSTR)CUMRDPListenerBase::ClearGlobalObjects, &phModule) )
  {
    if ( GetModuleFileNameW(phModule, Filename, 0x105u) - 1 > 0x103 )
    {
      LastError = GetLastError();
      v6 = LastError;
      if ( LastError > 0 )
        v6 = (unsigned __int16)LastError | 0x80070000;
      if ( v6 < 0 )
      {
        if ( (unsigned int)dword_1801B76C8 > 2 )
        {
          v18 = 653;
          v22 = "Failed to get the module file name";
          v19 = v6;
          v23 = "LoadRdpLite";
          v20 = "clientcore\\termsrv\\rdp_bin\\win\\rdpcorets\\umrdppipegfxplugin.cpp";
          v21 = "Error HResult failed";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
            v3,
            (unsigned int)byte_18019AD23,
            v4,
            v5,
            (__int64)&v21,
            (__int64)&v19,
            (__int64)&v20,
            (__int64)&v18,
            (__int64)&v23,
            (__int64)&v22);
        }
        return (unsigned int)v6;
      }
    }
    goto LABEL_14;
  }
  v7 = GetLastError();
  v6 = v7;
  if ( v7 > 0 )
    v6 = (unsigned __int16)v7 | 0x80070000;
  if ( v6 >= 0 )
  {
LABEL_14:
    v11 = wcsrchr(Filename, 0x5Cu);
    if ( v11 )
      v11[1] = 0;
    v6 = StringCchCatW(Filename, 0x105u, L"rdplite.dll");
    if ( v6 >= 0 )
    {
      if ( (unsigned int)dword_1801B76C8 > 4 )
      {
        v21 = (const char *)Filename;
        v20 = "Loading rdplite.dll: ";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
          v12,
          (unsigned int)&word_18019AC56,
          v13,
          v14,
          (__int64)&v20,
          (__int64)&v21);
      }
      LibraryW = LoadLibraryW(Filename);
      *((_QWORD *)this + 18) = LibraryW;
      if ( !LibraryW )
      {
        v16 = GetLastError();
        v6 = v16;
        if ( v16 > 0 )
          return (unsigned __int16)v16 | 0x80070000;
      }
    }
    else if ( (unsigned int)dword_1801B76C8 > 2 )
    {
      v19 = 670;
      v21 = "StringCchCat of file path failed";
      v18 = v6;
      v20 = "LoadRdpLite";
      v23 = "clientcore\\termsrv\\rdp_bin\\win\\rdpcorets\\umrdppipegfxplugin.cpp";
      v22 = "Error HResult failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        dword_1801B76C8,
        (unsigned int)byte_18019AC83,
        v13,
        v14,
        (__int64)&v22,
        (__int64)&v18,
        (__int64)&v23,
        (__int64)&v19,
        (__int64)&v20,
        (__int64)&v21);
    }
    return (unsigned int)v6;
  }
  if ( (unsigned int)dword_1801B76C8 > 2 )
  {
    v19 = 659;
    v21 = "Failed to get module handle to itself";
    v18 = v6;
    v20 = "LoadRdpLite";
    v23 = "clientcore\\termsrv\\rdp_bin\\win\\rdpcorets\\umrdppipegfxplugin.cpp";
    v22 = "Error HResult failed";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
      v8,
      (unsigned int)byte_18019ACD3,
      v9,
      v10,
      (__int64)&v22,
      (__int64)&v18,
      (__int64)&v23,
      (__int64)&v19,
      (__int64)&v20,
      (__int64)&v21);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18005aa94  mov     [rsp-8+arg_8], rbx
0x18005aa99  mov     [rsp-8+arg_10], rdi
0x18005aa9e  push    rbp
0x18005aa9f  lea     rbp, [rsp-1A0h]
0x18005aaa7  sub     rsp, 2A0h
0x18005aaae  mov     rax, cs:__security_cookie
0x18005aab5  xor     rax, rsp
0x18005aab8  mov     [rbp+1A0h+var_10], rax
0x18005aabf  mov     rdi, rcx
0x18005aac2  mov     [rsp+2A0h+phModule], 0
0x18005aacb  lea     rcx, [rbp+1A0h+Filename]; void *
0x18005aacf  xor     edx, edx; Val
0x18005aad1  mov     r8d, 20Ah; Size
0x18005aad7  call    memset_0
0x18005aadc  lea     r8, [rsp+2A0h+phModule]; phModule
0x18005aae1  mov     ecx, 6; dwFlags
0x18005aae6  lea     rdx, ?ClearGlobalObjects@CUMRDPListenerBase@@SAXXZ; lpModuleName
0x18005aaed  call    cs:__imp_GetModuleHandleExW
0x18005aaf3  test    eax, eax
0x18005aaf5  jz      loc_18005ABD2
0x18005aafb  mov     rcx, [rsp+2A0h+phModule]; hModule
0x18005ab00  lea     rdx, [rbp+1A0h+Filename]; lpFilename
0x18005ab04  mov     r8d, 105h; nSize
0x18005ab0a  call    cs:__imp_GetModuleFileNameW
0x18005ab10  dec     eax
0x18005ab12  cmp     eax, 103h
0x18005ab17  jbe     loc_18005AC7D
0x18005ab1d  call    cs:__imp_GetLastError
0x18005ab23  mov     ebx, eax
0x18005ab25  test    eax, eax
0x18005ab27  jle     short loc_18005AB32
0x18005ab29  movzx   ebx, ax
0x18005ab2c  or      ebx, 80070000h
0x18005ab32  test    ebx, ebx
0x18005ab34  jns     loc_18005AC7D
0x18005ab3a  mov     eax, cs:dword_1801B76C8
0x18005ab40  cmp     eax, 2
0x18005ab43  jbe     loc_18005ADAF
0x18005ab49  lea     rax, aFailedToGetThe; "Failed to get the module file name"
0x18005ab50  mov     [rsp+2A0h+var_250], 28Dh
0x18005ab58  mov     [rsp+2A0h+var_238], rax
0x18005ab5d  lea     rdx, byte_18019AD23
0x18005ab64  lea     rax, aLoadrdplite; "LoadRdpLite"
0x18005ab6b  mov     [rsp+2A0h+var_24C], ebx
0x18005ab6f  mov     [rsp+2A0h+var_230], rax
0x18005ab74  lea     rax, aClientcoreTerm_7; "clientcore\\termsrv\\rdp_bin\\win\\rdpc"...
0x18005ab7b  mov     [rsp+2A0h+var_248], rax
0x18005ab80  lea     rax, aErrorHresultFa; "Error HResult failed"
0x18005ab87  mov     [rsp+2A0h+var_240], rax
0x18005ab8c  lea     rax, [rsp+2A0h+var_238]
0x18005ab91  mov     [rsp+2A0h+var_258], rax
0x18005ab96  lea     rax, [rsp+2A0h+var_230]
0x18005ab9b  mov     [rsp+2A0h+var_260], rax
0x18005aba0  lea     rax, [rsp+2A0h+var_250]
0x18005aba5  mov     [rsp+2A0h+var_268], rax
0x18005abaa  lea     rax, [rsp+2A0h+var_248]
0x18005abaf  mov     [rsp+2A0h+var_270], rax
0x18005abb4  lea     rax, [rsp+2A0h+var_24C]
0x18005abb9  mov     [rsp+2A0h+var_278], rax
0x18005abbe  lea     rax, [rsp+2A0h+var_240]
0x18005abc3  mov     [rsp+2A0h+var_280], rax
0x18005abc8  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x18005abcd  jmp     loc_18005ADAF
0x18005abd2  call    cs:__imp_GetLastError
0x18005abd8  mov     ebx, eax
0x18005abda  test    eax, eax
0x18005abdc  jle     short loc_18005ABE7
0x18005abde  movzx   ebx, ax
0x18005abe1  or      ebx, 80070000h
0x18005abe7  test    ebx, ebx
0x18005abe9  jns     loc_18005AC7D
0x18005abef  mov     eax, cs:dword_1801B76C8
0x18005abf5  cmp     eax, 2
0x18005abf8  jbe     loc_18005ADAF
0x18005abfe  lea     rax, aFailedToGetMod; "Failed to get module handle to itself"
0x18005ac05  mov     [rsp+2A0h+var_24C], 293h
0x18005ac0d  mov     [rsp+2A0h+var_240], rax
0x18005ac12  lea     rdx, byte_18019ACD3
0x18005ac19  lea     rax, aLoadrdplite; "LoadRdpLite"
0x18005ac20  mov     [rsp+2A0h+var_250], ebx
0x18005ac24  mov     [rsp+2A0h+var_248], rax
0x18005ac29  lea     rax, aClientcoreTerm_7; "clientcore\\termsrv\\rdp_bin\\win\\rdpc"...
0x18005ac30  mov     [rsp+2A0h+var_230], rax
0x18005ac35  lea     rax, aErrorHresultFa; "Error HResult failed"
0x18005ac3c  mov     [rsp+2A0h+var_238], rax
0x18005ac41  lea     rax, [rsp+2A0h+var_240]
0x18005ac46  mov     [rsp+2A0h+var_258], rax
0x18005ac4b  lea     rax, [rsp+2A0h+var_248]
0x18005ac50  mov     [rsp+2A0h+var_260], rax
0x18005ac55  lea     rax, [rsp+2A0h+var_24C]
0x18005ac5a  mov     [rsp+2A0h+var_268], rax
0x18005ac5f  lea     rax, [rsp+2A0h+var_230]
0x18005ac64  mov     [rsp+2A0h+var_270], rax
0x18005ac69  lea     rax, [rsp+2A0h+var_250]
0x18005ac6e  mov     [rsp+2A0h+var_278], rax
0x18005ac73  lea     rax, [rsp+2A0h+var_238]
0x18005ac78  jmp     loc_18005ABC3
0x18005ac7d  mov     edx, 5Ch ; '\'; Ch
0x18005ac82  lea     rcx, [rbp+1A0h+Filename]; Str
0x18005ac86  call    cs:__imp_wcsrchr
0x18005ac8c  test    rax, rax
0x18005ac8f  jz      short loc_18005AC97
0x18005ac91  xor     ecx, ecx
0x18005ac93  mov     [rax+2], cx
0x18005ac97  lea     r8, aRdpliteDll; "rdplite.dll"
0x18005ac9e  mov     edx, 105h; unsigned __int64
0x18005aca3  lea     rcx, [rbp+1A0h+Filename]; unsigned __int16 *
0x18005aca7  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18005acac  mov     ebx, eax
0x18005acae  test    eax, eax
0x18005acb0  jns     loc_18005AD44
0x18005acb6  mov     ecx, cs:dword_1801B76C8
0x18005acbc  cmp     ecx, 2
0x18005acbf  jbe     loc_18005ADAF
0x18005acc5  lea     rax, aStringcchcatOf; "StringCchCat of file path failed"
0x18005accc  mov     [rsp+2A0h+var_24C], 29Eh
0x18005acd4  mov     [rsp+2A0h+var_240], rax
0x18005acd9  lea     rdx, byte_18019AC83
0x18005ace0  lea     rax, aLoadrdplite; "LoadRdpLite"
0x18005ace7  mov     [rsp+2A0h+var_250], ebx
0x18005aceb  mov     [rsp+2A0h+var_248], rax
0x18005acf0  lea     rax, aClientcoreTerm_7; "clientcore\\termsrv\\rdp_bin\\win\\rdpc"...
0x18005acf7  mov     [rsp+2A0h+var_230], rax
0x18005acfc  lea     rax, aErrorHresultFa; "Error HResult failed"
0x18005ad03  mov     [rsp+2A0h+var_238], rax
0x18005ad08  lea     rax, [rsp+2A0h+var_240]
0x18005ad0d  mov     [rsp+2A0h+var_258], rax
0x18005ad12  lea     rax, [rsp+2A0h+var_248]
0x18005ad17  mov     [rsp+2A0h+var_260], rax
0x18005ad1c  lea     rax, [rsp+2A0h+var_24C]
0x18005ad21  mov     [rsp+2A0h+var_268], rax
0x18005ad26  lea     rax, [rsp+2A0h+var_230]
0x18005ad2b  mov     [rsp+2A0h+var_270], rax
0x18005ad30  lea     rax, [rsp+2A0h+var_250]
0x18005ad35  mov     [rsp+2A0h+var_278], rax
0x18005ad3a  lea     rax, [rsp+2A0h+var_238]
0x18005ad3f  jmp     loc_18005ABC3
0x18005ad44  mov     eax, cs:dword_1801B76C8
0x18005ad4a  cmp     eax, 4
0x18005ad4d  jbe     short loc_18005AD84
0x18005ad4f  lea     rax, [rbp+1A0h+Filename]
0x18005ad53  mov     [rsp+2A0h+var_240], rax
0x18005ad58  lea     rdx, word_18019AC56
0x18005ad5f  lea     rax, aLoadingRdplite; "Loading rdplite.dll: "
0x18005ad66  mov     [rsp+2A0h+var_248], rax
0x18005ad6b  lea     rax, [rsp+2A0h+var_240]
0x18005ad70  mov     [rsp+2A0h+var_278], rax
0x18005ad75  lea     rax, [rsp+2A0h+var_248]
0x18005ad7a  mov     [rsp+2A0h+var_280], rax
0x18005ad7f  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x18005ad84  lea     rcx, [rbp+1A0h+Filename]; lpLibFileName
0x18005ad88  call    cs:__imp_LoadLibraryW
0x18005ad8e  mov     [rdi+90h], rax
0x18005ad95  test    rax, rax
0x18005ad98  jnz     short loc_18005ADAF
0x18005ad9a  call    cs:__imp_GetLastError
0x18005ada0  mov     ebx, eax
0x18005ada2  test    eax, eax
0x18005ada4  jle     short loc_18005ADAF
0x18005ada6  movzx   ebx, ax
0x18005ada9  or      ebx, 80070000h
0x18005adaf  mov     eax, ebx
0x18005adb1  mov     rcx, [rbp+1A0h+var_10]
0x18005adb8  xor     rcx, rsp; StackCookie
0x18005adbb  call    __security_check_cookie
0x18005adc0  lea     r11, [rsp+2A0h+var_s0]
0x18005adc8  mov     rbx, [r11+18h]
0x18005adcc  mov     rdi, [r11+20h]
0x18005add0  mov     rsp, r11
0x18005add3  pop     rbp
0x18005add4  retn
```
