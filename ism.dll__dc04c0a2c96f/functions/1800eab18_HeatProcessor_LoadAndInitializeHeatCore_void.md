# HeatProcessor::LoadAndInitializeHeatCore(void)

- ea: `0x1800eab18`
- end: `0x1800eabaf`
- name: `?LoadAndInitializeHeatCore@HeatProcessor@@AEAAJXZ`
- size: `151`
- prototype: `__int64 __fastcall(HeatProcessor *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800ea888`

## callees

- `0x180012b74`
- `0x18008daac`
- `0x18008ead4`
- `0x1800eab18`
- `0x1801ce010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800eab43`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800eab43`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x1800eab2b`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x1800eab2b`

## string_xrefs

- `0x1800eab24`: `HeatCore.dll`

## pseudocode

```c
__int64 __fastcall HeatProcessor::LoadAndInitializeHeatCore(HeatProcessor *this)
{
  HMODULE LibraryW; // rax
  const char *v3; // r9
  HMODULE v4; // rsi
  FARPROC ProcAddress; // rdi
  int v6; // eax
  unsigned int v7; // ebx
  int v9; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  LibraryW = LoadLibraryW(L"HeatCore.dll");
  v4 = LibraryW;
  if ( !LibraryW )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x131,
             (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\inputprocessors\\devices\\heat\\lib\\heatprocessor.cpp",
             v3);
  ProcAddress = GetProcAddress(LibraryW, "InitializeHeatFramework");
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 88);
  v6 = ((__int64 (__fastcall *)(_QWORD, char *))ProcAddress)(*((_QWORD *)this + 12), (char *)this + 88);
  v7 = v6;
  if ( v6 >= 0 )
  {
    *((_QWORD *)this + 10) = v4;
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x12B,
      (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\inputprocessors\\devices\\heat\\lib\\heatprocessor.cpp",
      (const char *)(unsigned int)v6,
      v9);
    return v7;
  }
}

```

## disassembly

```asm
0x1800eab18  push    rbx
0x1800eab1a  push    rbp
0x1800eab1b  push    rsi
0x1800eab1c  push    rdi
0x1800eab1d  sub     rsp, 28h
0x1800eab21  mov     rbp, rcx
0x1800eab24  lea     rcx, aHeatcoreDll; "HeatCore.dll"
0x1800eab2b  call    cs:__imp_LoadLibraryW
0x1800eab31  mov     rsi, rax
0x1800eab34  test    rax, rax
0x1800eab37  jz      short loc_1800EAB90
0x1800eab39  lea     rdx, aInitializeheat; "InitializeHeatFramework"
0x1800eab40  mov     rcx, rax; hModule
0x1800eab43  call    cs:__imp_GetProcAddress
0x1800eab49  lea     rcx, [rbp+58h]
0x1800eab4d  mov     rdi, rax
0x1800eab50  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800eab55  mov     rcx, [rbp+60h]
0x1800eab59  lea     rdx, [rbp+58h]
0x1800eab5d  mov     rax, rdi
0x1800eab60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800eab65  mov     ebx, eax
0x1800eab67  test    eax, eax
0x1800eab69  jns     short loc_1800EAB88
0x1800eab6b  mov     rcx, [rsp+48h]; this
0x1800eab70  lea     r8, aOnecoreuapWind_117; "onecoreuap\\windows\\moderncore\\inputv"...
0x1800eab77  mov     r9d, eax; char *
0x1800eab7a  mov     edx, 12Bh; void *
0x1800eab7f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800eab84  mov     eax, ebx
0x1800eab86  jmp     short loc_1800EABA6
0x1800eab88  mov     [rbp+50h], rsi
0x1800eab8c  xor     eax, eax
0x1800eab8e  jmp     short loc_1800EABA6
0x1800eab90  mov     rcx, [rsp+48h]; this
0x1800eab95  lea     r8, aOnecoreuapWind_117; "onecoreuap\\windows\\moderncore\\inputv"...
0x1800eab9c  mov     edx, 131h; void *
0x1800eaba1  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800eaba6  add     rsp, 28h
0x1800eabaa  pop     rdi
0x1800eabab  pop     rsi
0x1800eabac  pop     rbp
0x1800eabad  pop     rbx
0x1800eabae  retn
```
