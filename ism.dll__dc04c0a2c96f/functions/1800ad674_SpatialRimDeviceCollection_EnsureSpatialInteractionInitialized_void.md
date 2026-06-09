# SpatialRimDeviceCollection::EnsureSpatialInteractionInitialized(void)

- ea: `0x1800ad674`
- end: `0x1800ad7ee`
- name: `?EnsureSpatialInteractionInitialized@SpatialRimDeviceCollection@@AEAAJXZ`
- size: `378`
- prototype: `__int64 __fastcall(SpatialRimDeviceCollection *__hidden this)`
- caller_count: `2`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800ad5c0`
- `0x1800e68c0`

## callees

- `0x180012b74`
- `0x1800ad674`
- `0x1800ad7f4`
- `0x1800ad860`
- `0x18011814c`
- `0x180118848`
- `0x1801192c4`
- `0x18011a090`
- `0x18011bf1c`
- `0x1801ce010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800ad757`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800ad757`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ad707`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ad765`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ad707`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ad765`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800ad693`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800ad693`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800ad6c3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800ad7d3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800ad6c3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800ad7d3`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x1800ad6e1`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x1800ad6e1`

## string_xrefs

- `0x1800ad6da`: `SpatialInteraction.dll`
- `0x1800ad749`: `CreateSpatialInteractionSourceCollection`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SpatialRimDeviceCollection::EnsureSpatialInteractionInitialized(SpatialRimDeviceCollection *this)
{
  struct _RTL_CRITICAL_SECTION *v2; // rdi
  signed int v3; // ebx
  unsigned __int64 v5; // rdx
  unsigned __int8 v6; // cl
  HMODULE LibraryW; // rbx
  signed int v8; // eax
  __int64 v9; // rcx
  RawInputProvidersTracing *v10; // rcx
  FARPROC ProcAddress; // rbx
  signed int LastError; // eax
  signed int v13; // [rsp+40h] [rbp+8h] BYREF
  struct _RTL_CRITICAL_SECTION *v14; // [rsp+48h] [rbp+10h]

  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 2768);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 2768));
  v14 = v2;
  if ( *((_QWORD *)this + 354) )
  {
    v3 = 0;
LABEL_23:
    if ( v2 )
      LeaveCriticalSection(v2);
    return (unsigned int)v3;
  }
  if ( !*((_BYTE *)this + 2808) )
  {
    LibraryW = LoadLibraryW(L"SpatialInteraction.dll");
    if ( LibraryW == *((HMODULE *)this + 353) )
    {
      LibraryW = (HMODULE)*((_QWORD *)this + 353);
    }
    else
    {
      Microsoft::WRL::Wrappers::HandleT<SpatialRimDeviceCollection::HMODULETraits>::Close((char *)this + 2816);
      *((_QWORD *)this + 353) = LibraryW;
    }
    if ( LibraryW )
    {
      if ( RawInputProvidersTracing::IsEnabled(v6, v5) )
      {
        wil::details::static_lazy<RawInputProvidersTracing>::get(
          v9,
          _lambda_260b9137d63ddd75627644ad4182c2ea_::_lambda_invoker_cdecl_);
        RawInputProvidersTracing::SpatialInteractionDLL_Loaded_(v10);
      }
      ProcAddress = GetProcAddress(*((HMODULE *)this + 353), "CreateSpatialInteractionSourceCollection");
      if ( ProcAddress )
      {
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 2832);
        v3 = ((__int64 (__fastcall *)(char *))ProcAddress)((char *)this + 2832);
        v13 = v3;
        if ( v3 >= 0 )
          v3 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 354) + 96LL))(
                 *((_QWORD *)this + 354),
                 *((_QWORD *)this + 372));
        else
          RawInputProvidersTracing::SpatialInteractionDLL_FailedToCreateCollection<long &>(&v13);
      }
      else
      {
        LastError = GetLastError();
        v3 = LastError;
        if ( LastError > 0 )
          v3 = (unsigned __int16)LastError | 0x80070000;
        v13 = v3;
        RawInputProvidersTracing::SpatialInteractionDLL_EntryPointNotFound<long &>(&v13);
      }
    }
    else
    {
      v8 = GetLastError();
      v3 = v8;
      if ( v8 > 0 )
        v3 = (unsigned __int16)v8 | 0x80070000;
      v13 = v3;
      RawInputProvidersTracing::SpatialInteractionDLL_LoadFailure<long &>(&v13);
    }
    goto LABEL_23;
  }
  if ( v2 )
    LeaveCriticalSection(v2);
  return 2147549183LL;
}

```

## disassembly

```asm
0x1800ad674  mov     [rsp+arg_10], rbx
0x1800ad679  mov     [rsp+arg_18], rbp
0x1800ad67e  push    rsi
0x1800ad67f  push    rdi
0x1800ad680  push    r14
0x1800ad682  sub     rsp, 20h
0x1800ad686  mov     rsi, rcx
0x1800ad689  lea     rdi, [rcx+0AD0h]
0x1800ad690  mov     rcx, rdi; lpCriticalSection
0x1800ad693  call    cs:__imp_EnterCriticalSection
0x1800ad699  mov     [rsp+38h+arg_8], rdi
0x1800ad69e  lea     r14, [rsi+0B10h]
0x1800ad6a5  cmp     qword ptr [r14], 0
0x1800ad6a9  jz      short loc_1800AD6B2
0x1800ad6ab  xor     ebx, ebx
0x1800ad6ad  jmp     loc_1800AD7CB
0x1800ad6b2  cmp     byte ptr [rsi+0AF8h], 0
0x1800ad6b9  jz      short loc_1800AD6D3
0x1800ad6bb  test    rdi, rdi
0x1800ad6be  jz      short loc_1800AD6C9
0x1800ad6c0  mov     rcx, rdi; lpCriticalSection
0x1800ad6c3  call    cs:__imp_LeaveCriticalSection
0x1800ad6c9  mov     eax, 8000FFFFh
0x1800ad6ce  jmp     loc_1800AD7DB
0x1800ad6d3  lea     rbp, [rsi+0B00h]
0x1800ad6da  lea     rcx, aSpatialinterac; "SpatialInteraction.dll"
0x1800ad6e1  call    cs:__imp_LoadLibraryW
0x1800ad6e7  mov     rbx, rax
0x1800ad6ea  cmp     rax, [rbp+8]
0x1800ad6ee  jz      short loc_1800AD6FE
0x1800ad6f0  mov     rcx, rbp
0x1800ad6f3  call    ?Close@?$HandleT@UHMODULETraits@SpatialRimDeviceCollection@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<SpatialRimDeviceCollection::HMODULETraits>::Close(void)
0x1800ad6f8  mov     [rbp+8], rbx
0x1800ad6fc  jmp     short loc_1800AD702
0x1800ad6fe  mov     rbx, [rbp+8]
0x1800ad702  test    rbx, rbx
0x1800ad705  jnz     short loc_1800AD72F
0x1800ad707  call    cs:__imp_GetLastError
0x1800ad70d  mov     ebx, eax
0x1800ad70f  test    eax, eax
0x1800ad711  jle     short loc_1800AD71C
0x1800ad713  movzx   ebx, ax
0x1800ad716  or      ebx, 80070000h
0x1800ad71c  mov     [rsp+38h+arg_0], ebx
0x1800ad720  lea     rcx, [rsp+38h+arg_0]
0x1800ad725  call    ??$SpatialInteractionDLL_LoadFailure@AEAJ@RawInputProvidersTracing@@SAXAEAJ@Z; RawInputProvidersTracing::SpatialInteractionDLL_LoadFailure<long &>(long &)
0x1800ad72a  jmp     loc_1800AD7CB
0x1800ad72f  call    ?IsEnabled@RawInputProvidersTracing@@SA_NE_K@Z; RawInputProvidersTracing::IsEnabled(uchar,unsigned __int64)
0x1800ad734  test    al, al
0x1800ad736  jz      short loc_1800AD749
0x1800ad738  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_260b9137d63ddd75627644ad4182c2ea_@@CA@XZ; _lambda_260b9137d63ddd75627644ad4182c2ea_::_lambda_invoker_cdecl_(void)
0x1800ad73f  call    ?get@?$static_lazy@VRawInputProvidersTracing@@@details@wil@@QEAAPEAVRawInputProvidersTracing@@P6AXXZ@Z; wil::details::static_lazy<RawInputProvidersTracing>::get(void (*)(void))
0x1800ad744  call    ?SpatialInteractionDLL_Loaded_@RawInputProvidersTracing@@QEAAXXZ; RawInputProvidersTracing::SpatialInteractionDLL_Loaded_(void)
0x1800ad749  lea     rdx, aCreatespatiali; "CreateSpatialInteractionSourceCollectio"...
0x1800ad750  mov     rcx, [rsi+0B08h]; hModule
0x1800ad757  call    cs:__imp_GetProcAddress
0x1800ad75d  mov     rbx, rax
0x1800ad760  test    rax, rax
0x1800ad763  jnz     short loc_1800AD78A
0x1800ad765  call    cs:__imp_GetLastError
0x1800ad76b  mov     ebx, eax
0x1800ad76d  test    eax, eax
0x1800ad76f  jle     short loc_1800AD77A
0x1800ad771  movzx   ebx, ax
0x1800ad774  or      ebx, 80070000h
0x1800ad77a  mov     [rsp+38h+arg_0], ebx
0x1800ad77e  lea     rcx, [rsp+38h+arg_0]
0x1800ad783  call    ??$SpatialInteractionDLL_EntryPointNotFound@AEAJ@RawInputProvidersTracing@@SAXAEAJ@Z; RawInputProvidersTracing::SpatialInteractionDLL_EntryPointNotFound<long &>(long &)
0x1800ad788  jmp     short loc_1800AD7CB
0x1800ad78a  mov     rcx, r14
0x1800ad78d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800ad792  mov     rcx, r14
0x1800ad795  mov     rax, rbx
0x1800ad798  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ad79d  mov     ebx, eax
0x1800ad79f  mov     [rsp+38h+arg_0], eax
0x1800ad7a3  test    eax, eax
0x1800ad7a5  jns     short loc_1800AD7B3
0x1800ad7a7  lea     rcx, [rsp+38h+arg_0]
0x1800ad7ac  call    ??$SpatialInteractionDLL_FailedToCreateCollection@AEAJ@RawInputProvidersTracing@@SAXAEAJ@Z; RawInputProvidersTracing::SpatialInteractionDLL_FailedToCreateCollection<long &>(long &)
0x1800ad7b1  jmp     short loc_1800AD7CB
0x1800ad7b3  mov     rcx, [r14]
0x1800ad7b6  mov     rax, [rcx]
0x1800ad7b9  mov     rdx, [rsi+0BA0h]
0x1800ad7c0  mov     rax, [rax+60h]
0x1800ad7c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ad7c9  mov     ebx, eax
0x1800ad7cb  test    rdi, rdi
0x1800ad7ce  jz      short loc_1800AD7D9
0x1800ad7d0  mov     rcx, rdi; lpCriticalSection
0x1800ad7d3  call    cs:__imp_LeaveCriticalSection
0x1800ad7d9  mov     eax, ebx
0x1800ad7db  mov     rbx, [rsp+38h+arg_10]
0x1800ad7e0  mov     rbp, [rsp+38h+arg_18]
0x1800ad7e5  add     rsp, 20h
0x1800ad7e9  pop     r14
0x1800ad7eb  pop     rdi
0x1800ad7ec  pop     rsi
0x1800ad7ed  retn
```
