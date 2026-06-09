# CD3DKmThkApi::OpenFunctionPointers(DRIVER_VERSION_HELPER_FUNCTION_PTRS &)

- ea: `0x1800e4d60`
- end: `0x1800e4faf`
- name: `?OpenFunctionPointers@CD3DKmThkApi@@AEAAJAEAUDRIVER_VERSION_HELPER_FUNCTION_PTRS@@@Z`
- size: `591`
- prototype: `__int64 __fastcall(CD3DKmThkApi *__hidden this, struct DRIVER_VERSION_HELPER_FUNCTION_PTRS *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800e47c0`

## callees

- `0x1800015f0`
- `0x1800e4d60`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800e4d90`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800e4d90`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800e4e46`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800e4e9d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800e4ef2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800e4e46`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800e4e9d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800e4ef2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e4da3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e4e54`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e4eac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e4f05`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e4da3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e4e54`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e4eac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e4f05`

## string_xrefs

- `0x1800e4de4`: `OpenFunctionPointers`
- `0x1800e4f3e`: `OpenFunctionPointers`
- `0x1800e4d83`: `gdi32.dll`
- `0x1800e4e78`: `D3DKMTOpenAdapterFromLuid failed`
- `0x1800e4def`: `onecoreuap\termsrv\rdp\win\codecs\common\cd3dkmthkapi.cpp`
- `0x1800e4f49`: `onecoreuap\termsrv\rdp\win\codecs\common\cd3dkmthkapi.cpp`
- `0x1800e4e3f`: `D3DKMTOpenAdapterFromLuid`

## pseudocode

```c
__int64 __fastcall CD3DKmThkApi::OpenFunctionPointers(
        CD3DKmThkApi *this,
        struct DRIVER_VERSION_HELPER_FUNCTION_PTRS *a2)
{
  unsigned int v2; // ebx
  HMODULE Library; // rax
  signed int LastError; // eax
  int v7; // ecx
  int v8; // r8d
  int v9; // r9d
  __int16 *v10; // rdx
  const char **v11; // rax
  FARPROC ProcAddress; // rax
  signed int v13; // eax
  const char *v14; // rax
  FARPROC v15; // rax
  signed int v16; // eax
  FARPROC v17; // rax
  signed int v18; // eax
  const char **v20; // [rsp+40h] [rbp-30h]
  const char *v21; // [rsp+50h] [rbp-20h] BYREF
  const char *v22; // [rsp+58h] [rbp-18h] BYREF
  _QWORD v23[2]; // [rsp+60h] [rbp-10h] BYREF
  int v24; // [rsp+90h] [rbp+20h] BYREF
  unsigned int v25; // [rsp+A0h] [rbp+30h] BYREF
  const char *v26; // [rsp+A8h] [rbp+38h] BYREF

  v2 = 0;
  if ( *((_QWORD *)this + 6) )
    return v2;
  Library = LoadLibraryExW(L"gdi32.dll", 0, 0x800u);
  *((_QWORD *)this + 6) = Library;
  if ( Library )
    goto LABEL_8;
  LastError = GetLastError();
  v2 = LastError;
  if ( LastError > 0 )
    v2 = (unsigned __int16)LastError | 0x80070000;
  if ( (v2 & 0x80000000) == 0 )
  {
LABEL_8:
    ProcAddress = GetProcAddress(*((HMODULE *)this + 6), "D3DKMTOpenAdapterFromLuid");
    *(_QWORD *)a2 = ProcAddress;
    if ( ProcAddress )
    {
      v15 = GetProcAddress(*((HMODULE *)this + 6), "D3DKMTCloseAdapter");
      *((_QWORD *)a2 + 1) = v15;
      if ( v15 )
      {
        v17 = GetProcAddress(*((HMODULE *)this + 6), "D3DKMTQueryAdapterInfo");
        *((_QWORD *)a2 + 2) = v17;
        if ( v17 )
          return v2;
        v18 = GetLastError();
        v2 = v18;
        if ( v18 > 0 )
          v2 = (unsigned __int16)v18 | 0x80070000;
        if ( (unsigned int)dword_1801B76C8 <= 2 )
          return v2;
        v14 = "m_D3DKMTQueryAdapterInfoFn failed";
        v24 = 62;
        v10 = word_1801AAB72;
      }
      else
      {
        v16 = GetLastError();
        v2 = v16;
        if ( v16 > 0 )
          v2 = (unsigned __int16)v16 | 0x80070000;
        if ( (unsigned int)dword_1801B76C8 <= 2 )
          return v2;
        v14 = "m_D3DKMTCloseAdapterFn failed";
        v24 = 59;
        v10 = &word_1801AACCE;
      }
    }
    else
    {
      v13 = GetLastError();
      v2 = v13;
      if ( v13 > 0 )
        v2 = (unsigned __int16)v13 | 0x80070000;
      if ( (unsigned int)dword_1801B76C8 <= 2 )
        return v2;
      v14 = "D3DKMTOpenAdapterFromLuid failed";
      v24 = 56;
      v10 = (__int16 *)byte_1801AAD25;
    }
    v26 = v14;
    v23[0] = "OpenFunctionPointers";
    v22 = "onecoreuap\\termsrv\\rdp\\win\\codecs\\common\\cd3dkmthkapi.cpp";
    v21 = "Error condition failed";
    v20 = (const char **)v23;
    v11 = &v21;
    goto LABEL_24;
  }
  if ( (unsigned int)dword_1801B76C8 > 2 )
  {
    v24 = 53;
    v26 = "Failed to load gdi32 library.";
    v10 = (__int16 *)&byte_1801AAC77;
    v21 = "OpenFunctionPointers";
    v22 = "onecoreuap\\termsrv\\rdp\\win\\codecs\\common\\cd3dkmthkapi.cpp";
    v23[0] = "Error HResult failed";
    v20 = &v21;
    v11 = (const char **)v23;
LABEL_24:
    v25 = v2;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
      v7,
      (_DWORD)v10,
      v8,
      v9,
      (__int64)v11,
      (__int64)&v25,
      (__int64)&v22,
      (__int64)&v24,
      (__int64)v20,
      (__int64)&v26);
  }
  return v2;
}

```

## disassembly

```asm
0x1800e4d60  mov     [rsp-18h+arg_8], rbx
0x1800e4d65  push    rbp
0x1800e4d66  push    rsi
0x1800e4d67  push    rdi
0x1800e4d68  mov     rbp, rsp
0x1800e4d6b  sub     rsp, 70h
0x1800e4d6f  xor     ebx, ebx
0x1800e4d71  mov     rsi, rdx
0x1800e4d74  mov     rdi, rcx
0x1800e4d77  cmp     [rcx+30h], rbx
0x1800e4d7b  jnz     loc_1800E4F9D
0x1800e4d81  xor     edx, edx; hFile
0x1800e4d83  lea     rcx, aGdi32Dll_0; "gdi32.dll"
0x1800e4d8a  mov     r8d, 800h; dwFlags
0x1800e4d90  call    cs:__imp_LoadLibraryExW
0x1800e4d96  mov     [rdi+30h], rax
0x1800e4d9a  test    rax, rax
0x1800e4d9d  jnz     loc_1800E4E3B
0x1800e4da3  call    cs:__imp_GetLastError
0x1800e4da9  mov     ebx, eax
0x1800e4dab  test    eax, eax
0x1800e4dad  jle     short loc_1800E4DB8
0x1800e4daf  movzx   ebx, ax
0x1800e4db2  or      ebx, 80070000h
0x1800e4db8  test    ebx, ebx
0x1800e4dba  jns     short loc_1800E4E3B
0x1800e4dbc  mov     eax, cs:dword_1801B76C8
0x1800e4dc2  cmp     eax, 2
0x1800e4dc5  jbe     loc_1800E4F9D
0x1800e4dcb  lea     rax, aFailedToLoadGd; "Failed to load gdi32 library."
0x1800e4dd2  mov     [rbp+arg_0], 35h ; '5'
0x1800e4dd9  mov     [rbp+arg_18], rax
0x1800e4ddd  lea     rdx, byte_1801AAC77
0x1800e4de4  lea     rax, aOpenfunctionpo_1; "OpenFunctionPointers"
0x1800e4deb  mov     [rbp+var_20], rax
0x1800e4def  lea     rax, aOnecoreuapTerm; "onecoreuap\\termsrv\\rdp\\win\\codecs\\"...
0x1800e4df6  mov     [rbp+var_18], rax
0x1800e4dfa  lea     rax, aErrorHresultFa; "Error HResult failed"
0x1800e4e01  mov     [rbp+var_10], rax
0x1800e4e05  lea     rax, [rbp+arg_18]
0x1800e4e09  mov     [rsp+70h+var_28], rax
0x1800e4e0e  lea     rax, [rbp+var_20]
0x1800e4e12  mov     [rsp+70h+var_30], rax
0x1800e4e17  lea     rax, [rbp+arg_0]
0x1800e4e1b  mov     [rsp+70h+var_38], rax
0x1800e4e20  lea     rax, [rbp+var_18]
0x1800e4e24  mov     [rsp+70h+var_40], rax
0x1800e4e29  lea     rax, [rbp+arg_10]
0x1800e4e2d  mov     [rsp+70h+var_48], rax
0x1800e4e32  lea     rax, [rbp+var_10]
0x1800e4e36  jmp     loc_1800E4F90
0x1800e4e3b  mov     rcx, [rdi+30h]; hModule
0x1800e4e3f  lea     rdx, aD3dkmtopenadap_0; "D3DKMTOpenAdapterFromLuid"
0x1800e4e46  call    cs:__imp_GetProcAddress
0x1800e4e4c  mov     [rsi], rax
0x1800e4e4f  test    rax, rax
0x1800e4e52  jnz     short loc_1800E4E92
0x1800e4e54  call    cs:__imp_GetLastError
0x1800e4e5a  mov     ebx, eax
0x1800e4e5c  test    eax, eax
0x1800e4e5e  jle     short loc_1800E4E69
0x1800e4e60  movzx   ebx, ax
0x1800e4e63  or      ebx, 80070000h
0x1800e4e69  mov     eax, cs:dword_1801B76C8
0x1800e4e6f  cmp     eax, 2
0x1800e4e72  jbe     loc_1800E4F9D
0x1800e4e78  lea     rax, aD3dkmtopenadap; "D3DKMTOpenAdapterFromLuid failed"
0x1800e4e7f  mov     [rbp+arg_0], 38h ; '8'
0x1800e4e86  lea     rdx, byte_1801AAD25
0x1800e4e8d  jmp     loc_1800E4F3A
0x1800e4e92  mov     rcx, [rdi+30h]; hModule
0x1800e4e96  lea     rdx, aD3dkmtcloseada_0; "D3DKMTCloseAdapter"
0x1800e4e9d  call    cs:__imp_GetProcAddress
0x1800e4ea3  mov     [rsi+8], rax
0x1800e4ea7  test    rax, rax
0x1800e4eaa  jnz     short loc_1800E4EE7
0x1800e4eac  call    cs:__imp_GetLastError
0x1800e4eb2  mov     ebx, eax
0x1800e4eb4  test    eax, eax
0x1800e4eb6  jle     short loc_1800E4EC1
0x1800e4eb8  movzx   ebx, ax
0x1800e4ebb  or      ebx, 80070000h
0x1800e4ec1  mov     eax, cs:dword_1801B76C8
0x1800e4ec7  cmp     eax, 2
0x1800e4eca  jbe     loc_1800E4F9D
0x1800e4ed0  lea     rax, aMD3dkmtclosead; "m_D3DKMTCloseAdapterFn failed"
0x1800e4ed7  mov     [rbp+arg_0], 3Bh ; ';'
0x1800e4ede  lea     rdx, word_1801AACCE
0x1800e4ee5  jmp     short loc_1800E4F3A
0x1800e4ee7  mov     rcx, [rdi+30h]; hModule
0x1800e4eeb  lea     rdx, aD3dkmtqueryada; "D3DKMTQueryAdapterInfo"
0x1800e4ef2  call    cs:__imp_GetProcAddress
0x1800e4ef8  mov     [rsi+10h], rax
0x1800e4efc  test    rax, rax
0x1800e4eff  jnz     loc_1800E4F9D
0x1800e4f05  call    cs:__imp_GetLastError
0x1800e4f0b  mov     ebx, eax
0x1800e4f0d  test    eax, eax
0x1800e4f0f  jle     short loc_1800E4F1A
0x1800e4f11  movzx   ebx, ax
0x1800e4f14  or      ebx, 80070000h
0x1800e4f1a  mov     eax, cs:dword_1801B76C8
0x1800e4f20  cmp     eax, 2
0x1800e4f23  jbe     short loc_1800E4F9D
0x1800e4f25  lea     rax, aMD3dkmtqueryad; "m_D3DKMTQueryAdapterInfoFn failed"
0x1800e4f2c  mov     [rbp+arg_0], 3Eh ; '>'
0x1800e4f33  lea     rdx, word_1801AAB72
0x1800e4f3a  mov     [rbp+arg_18], rax
0x1800e4f3e  lea     rax, aOpenfunctionpo_1; "OpenFunctionPointers"
0x1800e4f45  mov     [rbp+var_10], rax
0x1800e4f49  lea     rax, aOnecoreuapTerm; "onecoreuap\\termsrv\\rdp\\win\\codecs\\"...
0x1800e4f50  mov     [rbp+var_18], rax
0x1800e4f54  lea     rax, aErrorCondition; "Error condition failed"
0x1800e4f5b  mov     [rbp+var_20], rax
0x1800e4f5f  lea     rax, [rbp+arg_18]
0x1800e4f63  mov     [rsp+70h+var_28], rax
0x1800e4f68  lea     rax, [rbp+var_10]
0x1800e4f6c  mov     [rsp+70h+var_30], rax
0x1800e4f71  lea     rax, [rbp+arg_0]
0x1800e4f75  mov     [rsp+70h+var_38], rax
0x1800e4f7a  lea     rax, [rbp+var_18]
0x1800e4f7e  mov     [rsp+70h+var_40], rax
0x1800e4f83  lea     rax, [rbp+arg_10]
0x1800e4f87  mov     [rsp+70h+var_48], rax
0x1800e4f8c  lea     rax, [rbp+var_20]
0x1800e4f90  mov     [rsp+70h+var_50], rax
0x1800e4f95  mov     [rbp+arg_10], ebx
0x1800e4f98  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x1800e4f9d  mov     eax, ebx
0x1800e4f9f  mov     rbx, [rsp+70h+arg_8]
0x1800e4fa7  add     rsp, 70h
0x1800e4fab  pop     rdi
0x1800e4fac  pop     rsi
0x1800e4fad  pop     rbp
0x1800e4fae  retn
```
