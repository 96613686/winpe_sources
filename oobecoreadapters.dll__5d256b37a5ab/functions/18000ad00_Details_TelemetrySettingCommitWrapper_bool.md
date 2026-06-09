# Details::TelemetrySettingCommitWrapper(bool)

- ea: `0x18000ad00`
- end: `0x18000ae34`
- name: `?TelemetrySettingCommitWrapper@Details@@YAJ_N@Z`
- size: `308`
- prototype: `__int64 __fastcall(bool)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800076b4`
- `0x1800076d4`
- `0x180009864`
- `0x18000ad00`
- `0x18006e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000ad8b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000adc5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000ad8b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000adc5`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000ad5d`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000ad5d`

## string_xrefs

- `0x18000ad56`: `utcapi.dll`
- `0x18000ad81`: `UtcCreateSessionHandle`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x18000ad00  push    rbp
0x18000ad02  push    rbx
0x18000ad03  push    rsi
0x18000ad04  push    rdi
0x18000ad05  lea     rbp, [rsp-3Fh]
0x18000ad0a  sub     rsp, 98h
0x18000ad11  movzx   edi, cl
0x18000ad14  xor     esi, esi
0x18000ad16  mov     [rbp+57h+var_90], rsi
0x18000ad1a  mov     [rbp+57h+hModule], rsi
0x18000ad1e  mov     [rbp+57h+var_80], rsi
0x18000ad22  mov     [rbp+57h+var_78], rsi
0x18000ad26  mov     [rbp+57h+var_70], rsi
0x18000ad2a  mov     [rbp+57h+var_68], rsi
0x18000ad2e  mov     [rbp+57h+var_60], rsi
0x18000ad32  mov     [rbp+57h+var_58], rsi
0x18000ad36  mov     [rbp+57h+var_50], rsi
0x18000ad3a  mov     [rbp+57h+var_48], rsi
0x18000ad3e  mov     [rbp+57h+var_40], rsi
0x18000ad42  mov     [rbp+57h+var_38], rsi
0x18000ad46  mov     [rbp+57h+var_30], rsi
0x18000ad4a  mov     [rbp+57h+var_28], rsi
0x18000ad4e  xor     edx, edx; hFile
0x18000ad50  mov     r8d, 800h; dwFlags
0x18000ad56  lea     rcx, LibFileName; "utcapi.dll"
0x18000ad5d  call    cs:__imp_LoadLibraryExW
0x18000ad63  mov     [rbp+57h+hModule], rax
0x18000ad67  test    rax, rax
0x18000ad6a  jnz     short loc_18000AD81
0x18000ad6c  lea     edx, [rsi+58h]; void *
0x18000ad6f  lea     r8, aOnecoreInterna_4; "onecore\\internal\\base\\inc\\utcapiwra"...
0x18000ad76  mov     rcx, [rbp+5Fh]; this
0x18000ad7a  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000ad7f  jmp     short loc_18000ADA4
0x18000ad81  lea     rdx, aUtccreatesessi; "UtcCreateSessionHandle"
0x18000ad88  mov     rcx, rax; hModule
0x18000ad8b  call    cs:__imp_GetProcAddress
0x18000ad91  test    rax, rax
0x18000ad94  jnz     short loc_18000AD9B
0x18000ad96  lea     edx, [rax+5Bh]
0x18000ad99  jmp     short loc_18000AD6F
0x18000ad9b  lea     rcx, [rbp+57h+var_90]
0x18000ad9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ada4  mov     ebx, eax
0x18000ada6  test    eax, eax
0x18000ada8  jns     short loc_18000ADB1
0x18000adaa  mov     edx, 49h ; 'I'
0x18000adaf  jmp     short loc_18000AE06
0x18000adb1  mov     rax, [rbp+57h+var_48]
0x18000adb5  test    rax, rax
0x18000adb8  jnz     short loc_18000ADEB
0x18000adba  lea     rdx, aUtcsettelemetr; "UtcSetTelemetryOptIn"
0x18000adc1  mov     rcx, [rbp+57h+hModule]; hModule
0x18000adc5  call    cs:__imp_GetProcAddress
0x18000adcb  mov     [rbp+57h+var_48], rax
0x18000adcf  test    rax, rax
0x18000add2  jnz     short loc_18000ADEB
0x18000add4  mov     rcx, [rbp+5Fh]; this
0x18000add8  lea     r8, aOnecoreInterna_4; "onecore\\internal\\base\\inc\\utcapiwra"...
0x18000addf  mov     edx, 0D4h; void *
0x18000ade4  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000ade9  jmp     short loc_18000ADFB
0x18000adeb  lea     edx, ds:1[rdi*2]
0x18000adf2  mov     rcx, [rbp+57h+var_90]
0x18000adf6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000adfb  mov     ebx, eax
0x18000adfd  test    eax, eax
0x18000adff  jns     short loc_18000AE1B
0x18000ae01  mov     edx, 4Ah ; 'J'; void *
0x18000ae06  lea     r8, aOnecoreuapInte_8; "onecoreuap\\internal\\shell\\inc\\oobes"...
0x18000ae0d  mov     r9d, ebx; char *
0x18000ae10  mov     rcx, [rbp+5Fh]; this
0x18000ae14  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ae19  jmp     short loc_18000AE1D
0x18000ae1b  mov     ebx, esi
0x18000ae1d  lea     rcx, [rbp+57h+var_90]; this
0x18000ae21  call    ??1UtcApiWrapper@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::UtcApiWrapper::~UtcApiWrapper(void)
0x18000ae26  mov     eax, ebx
0x18000ae28  add     rsp, 98h
0x18000ae2f  pop     rdi
0x18000ae30  pop     rsi
0x18000ae31  pop     rbx
0x18000ae32  pop     rbp
0x18000ae33  retn
```
