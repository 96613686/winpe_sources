# Details::TelemetrySettingCommitWrapper(bool)

- ea: `0x180045f40`
- end: `0x180046074`
- name: `?TelemetrySettingCommitWrapper@Details@@YAJ_N@Z`
- size: `308`
- prototype: `__int64 __fastcall(unsigned __int8)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180008524`
- `0x180008544`
- `0x180045ce8`
- `0x180045f40`
- `0x1800c4010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180045f9d`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180045f9d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180045fcb`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180046005`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180045fcb`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180046005`

## string_xrefs

- `0x180045f96`: `utcapi.dll`
- `0x180045fc1`: `UtcCreateSessionHandle`

## pseudocode

```c
__int64 __fastcall Details::TelemetrySettingCommitWrapper(unsigned __int8 a1)
{
  int v1; // edi
  HMODULE Library; // rax
  const char *v3; // r9
  __int64 v4; // rdx
  int LastError; // eax
  FARPROC ProcAddress; // rax
  unsigned int v7; // ebx
  __int64 v8; // rdx
  FARPROC v9; // rax
  const char *v10; // r9
  int v11; // eax
  __int64 v13; // [rsp+20h] [rbp-39h] BYREF
  HMODULE hModule; // [rsp+28h] [rbp-31h]
  __int64 v15; // [rsp+30h] [rbp-29h]
  __int64 v16; // [rsp+38h] [rbp-21h]
  __int64 v17; // [rsp+40h] [rbp-19h]
  __int64 v18; // [rsp+48h] [rbp-11h]
  __int64 v19; // [rsp+50h] [rbp-9h]
  __int64 v20; // [rsp+58h] [rbp-1h]
  __int64 v21; // [rsp+60h] [rbp+7h]
  INT_PTR (__stdcall *v22)(); // [rsp+68h] [rbp+Fh]
  __int64 v23; // [rsp+70h] [rbp+17h]
  __int64 v24; // [rsp+78h] [rbp+1Fh]
  __int64 v25; // [rsp+80h] [rbp+27h]
  __int64 v26; // [rsp+88h] [rbp+2Fh]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]

  v1 = a1;
  v13 = 0;
  v15 = 0;
  v16 = 0;
  v17 = 0;
  v18 = 0;
  v19 = 0;
  v20 = 0;
  v21 = 0;
  v22 = 0;
  v23 = 0;
  v24 = 0;
  v25 = 0;
  v26 = 0;
  Library = LoadLibraryExW(L"utcapi.dll", 0, 0x800u);
  hModule = Library;
  if ( !Library )
  {
    v4 = 88;
LABEL_3:
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)v4,
                  (unsigned int)"onecore\\internal\\base\\inc\\utcapiwrapperEx.h",
                  v3);
    goto LABEL_7;
  }
  ProcAddress = GetProcAddress(Library, "UtcCreateSessionHandle");
  if ( !ProcAddress )
  {
    v4 = 91;
    goto LABEL_3;
  }
  LastError = ((__int64 (__fastcall *)(__int64 *))ProcAddress)(&v13);
LABEL_7:
  v7 = LastError;
  if ( LastError >= 0 )
  {
    v9 = v22;
    if ( v22 || (v9 = GetProcAddress(hModule, "UtcSetTelemetryOptIn"), (v22 = v9) != 0) )
      v11 = ((__int64 (__fastcall *)(__int64, _QWORD))v9)(v13, (unsigned int)(2 * v1 + 1));
    else
      v11 = wil::details::in1diag3::Return_GetLastError(
              retaddr,
              (void *)0xD4,
              (unsigned int)"onecore\\internal\\base\\inc\\utcapiwrapperEx.h",
              v10);
    v7 = v11;
    if ( v11 >= 0 )
    {
      v7 = 0;
      goto LABEL_17;
    }
    v8 = 74;
  }
  else
  {
    v8 = 73;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v8,
    (unsigned int)"onecoreuap\\internal\\shell\\inc\\oobesettingsutil.h",
    (const char *)v7,
    v13);
LABEL_17:
  Microsoft::Diagnostics::UtcApiWrapper::~UtcApiWrapper((Microsoft::Diagnostics::UtcApiWrapper *)&v13);
  return v7;
}

```

## disassembly

```asm
0x180045f40  push    rbp
0x180045f42  push    rbx
0x180045f43  push    rsi
0x180045f44  push    rdi
0x180045f45  lea     rbp, [rsp-3Fh]
0x180045f4a  sub     rsp, 98h
0x180045f51  movzx   edi, cl
0x180045f54  xor     esi, esi
0x180045f56  mov     [rbp+57h+var_90], rsi
0x180045f5a  mov     [rbp+57h+hModule], rsi
0x180045f5e  mov     [rbp+57h+var_80], rsi
0x180045f62  mov     [rbp+57h+var_78], rsi
0x180045f66  mov     [rbp+57h+var_70], rsi
0x180045f6a  mov     [rbp+57h+var_68], rsi
0x180045f6e  mov     [rbp+57h+var_60], rsi
0x180045f72  mov     [rbp+57h+var_58], rsi
0x180045f76  mov     [rbp+57h+var_50], rsi
0x180045f7a  mov     [rbp+57h+var_48], rsi
0x180045f7e  mov     [rbp+57h+var_40], rsi
0x180045f82  mov     [rbp+57h+var_38], rsi
0x180045f86  mov     [rbp+57h+var_30], rsi
0x180045f8a  mov     [rbp+57h+var_28], rsi
0x180045f8e  xor     edx, edx; hFile
0x180045f90  mov     r8d, 800h; dwFlags
0x180045f96  lea     rcx, aUtcapiDll; "utcapi.dll"
0x180045f9d  call    cs:__imp_LoadLibraryExW
0x180045fa3  mov     [rbp+57h+hModule], rax
0x180045fa7  test    rax, rax
0x180045faa  jnz     short loc_180045FC1
0x180045fac  lea     edx, [rsi+58h]; void *
0x180045faf  lea     r8, aOnecoreInterna_3; "onecore\\internal\\base\\inc\\utcapiwra"...
0x180045fb6  mov     rcx, [rbp+5Fh]; this
0x180045fba  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180045fbf  jmp     short loc_180045FE4
0x180045fc1  lea     rdx, aUtccreatesessi; "UtcCreateSessionHandle"
0x180045fc8  mov     rcx, rax; hModule
0x180045fcb  call    cs:__imp_GetProcAddress
0x180045fd1  test    rax, rax
0x180045fd4  jnz     short loc_180045FDB
0x180045fd6  lea     edx, [rax+5Bh]
0x180045fd9  jmp     short loc_180045FAF
0x180045fdb  lea     rcx, [rbp+57h+var_90]
0x180045fdf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045fe4  mov     ebx, eax
0x180045fe6  test    eax, eax
0x180045fe8  jns     short loc_180045FF1
0x180045fea  mov     edx, 49h ; 'I'
0x180045fef  jmp     short loc_180046046
0x180045ff1  mov     rax, [rbp+57h+var_48]
0x180045ff5  test    rax, rax
0x180045ff8  jnz     short loc_18004602B
0x180045ffa  lea     rdx, aUtcsettelemetr; "UtcSetTelemetryOptIn"
0x180046001  mov     rcx, [rbp+57h+hModule]; hModule
0x180046005  call    cs:__imp_GetProcAddress
0x18004600b  mov     [rbp+57h+var_48], rax
0x18004600f  test    rax, rax
0x180046012  jnz     short loc_18004602B
0x180046014  mov     rcx, [rbp+5Fh]; this
0x180046018  lea     r8, aOnecoreInterna_3; "onecore\\internal\\base\\inc\\utcapiwra"...
0x18004601f  mov     edx, 0D4h; void *
0x180046024  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180046029  jmp     short loc_18004603B
0x18004602b  lea     edx, ds:1[rdi*2]
0x180046032  mov     rcx, [rbp+57h+var_90]
0x180046036  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004603b  mov     ebx, eax
0x18004603d  test    eax, eax
0x18004603f  jns     short loc_18004605B
0x180046041  mov     edx, 4Ah ; 'J'; void *
0x180046046  lea     r8, aOnecoreuapInte_7; "onecoreuap\\internal\\shell\\inc\\oobes"...
0x18004604d  mov     r9d, ebx; char *
0x180046050  mov     rcx, [rbp+5Fh]; this
0x180046054  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180046059  jmp     short loc_18004605D
0x18004605b  mov     ebx, esi
0x18004605d  lea     rcx, [rbp+57h+var_90]; this
0x180046061  call    ??1UtcApiWrapper@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::UtcApiWrapper::~UtcApiWrapper(void)
0x180046066  mov     eax, ebx
0x180046068  add     rsp, 98h
0x18004606f  pop     rdi
0x180046070  pop     rsi
0x180046071  pop     rbx
0x180046072  pop     rbp
0x180046073  retn
```
