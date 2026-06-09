# ConsumerControlManager::Initialize(void)

- ea: `0x1800ded84`
- end: `0x1800dee7d`
- name: `?Initialize@ConsumerControlManager@@AEAAJXZ`
- size: `249`
- prototype: `__int64 __fastcall(ULONG_PTR dwData)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18009dc2c`

## callees

- `0x180012b74`
- `0x18008daac`
- `0x18008ead4`
- `0x1800ded84`
- `0x1800dee90`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800dee25`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800dee25`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x1800dede2`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x1800dede2`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800dee51`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800dee51`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800dee39`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800dee39`
- `CoreMessaging!CoreUICreate` at `0x1800deda3`
- `CoreMessaging!CoreUICreate` at `0x1800deda3`

## pseudocode

```c
__int64 __fastcall ConsumerControlManager::Initialize(ULONG_PTR dwData)
{
  int v2; // eax
  unsigned int v3; // ebx
  HMODULE *v5; // rsi
  const char *v6; // r9
  signed int LastError; // eax
  DWORD dwCreationFlags; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(dwData + 120);
  v2 = CoreUICreate(dwData + 120);
  v3 = v2;
  if ( v2 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2B,
      (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\rawinputproviders\\lamparray\\lib\\consumercontrolmanager.cpp",
      (const char *)(unsigned int)v2,
      dwCreationFlags);
    return v3;
  }
  v5 = (HMODULE *)(dwData + 88);
  if ( !GetModuleHandleExW(4u, (LPCWSTR)ConsumerControlManager::WorkerThreadProcThunk, (HMODULE *)(dwData + 88)) )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x33,
             (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\rawinputproviders\\lamparray\\lib\\consumercontrolmanager.cpp",
             v6);
  _InterlockedIncrement((volatile signed __int32 *)(dwData + 8));
  _InterlockedExchange64(
    (volatile __int64 *)(dwData + 96),
    (__int64)CreateThread(0, 0, ConsumerControlManager::WorkerThreadProcThunk, (LPVOID)dwData, 0, 0));
  if ( !*(_QWORD *)(dwData + 96) )
  {
    LastError = GetLastError();
    v3 = LastError;
    if ( LastError > 0 )
      v3 = (unsigned __int16)LastError | 0x80070000;
    FreeLibrary(*v5);
    *v5 = 0;
    ConsumerControlManager::Release(dwData);
    return v3;
  }
  return 0;
}

```

## disassembly

```asm
0x1800ded84  mov     [rsp+arg_0], rbx
0x1800ded89  mov     [rsp+arg_8], rsi
0x1800ded8e  push    rdi
0x1800ded8f  sub     rsp, 30h
0x1800ded93  mov     rdi, rcx
0x1800ded96  add     rcx, 78h ; 'x'
0x1800ded9a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800ded9f  lea     rcx, [rdi+78h]
0x1800deda3  call    cs:__imp_CoreUICreate
0x1800deda9  mov     ebx, eax
0x1800dedab  test    eax, eax
0x1800dedad  jns     short loc_1800DEDCF
0x1800dedaf  mov     rcx, [rsp+38h]; this
0x1800dedb4  mov     r9d, eax; char *
0x1800dedb7  lea     r8, aOnecoreuapWind_51; "onecoreuap\\windows\\moderncore\\inputv"...
0x1800dedbe  mov     edx, 2Bh ; '+'; void *
0x1800dedc3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800dedc8  mov     eax, ebx
0x1800dedca  jmp     loc_1800DEE6D
0x1800dedcf  lea     rsi, [rdi+58h]
0x1800dedd3  mov     r8, rsi; phModule
0x1800dedd6  lea     rdx, ?WorkerThreadProcThunk@ConsumerControlManager@@CAKPEAX@Z; lpModuleName
0x1800deddd  mov     ecx, 4; dwFlags
0x1800dede2  call    cs:__imp_GetModuleHandleExW
0x1800dede8  test    eax, eax
0x1800dedea  jnz     short loc_1800DEE02
0x1800dedec  mov     rcx, [rsp+38h]; this
0x1800dedf1  lea     r8, aOnecoreuapWind_51; "onecoreuap\\windows\\moderncore\\inputv"...
0x1800dedf8  lea     edx, [rax+33h]; void *
0x1800dedfb  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800dee00  jmp     short loc_1800DEE6D
0x1800dee02  lock inc dword ptr [rdi+8]
0x1800dee06  mov     [rsp+38h+lpThreadId], 0; lpThreadId
0x1800dee0f  mov     [rsp+38h+dwCreationFlags], 0; dwCreationFlags
0x1800dee17  mov     r9, rdi; lpParameter
0x1800dee1a  lea     r8, ?WorkerThreadProcThunk@ConsumerControlManager@@CAKPEAX@Z; lpStartAddress
0x1800dee21  xor     edx, edx; dwStackSize
0x1800dee23  xor     ecx, ecx; lpThreadAttributes
0x1800dee25  call    cs:__imp_CreateThread
0x1800dee2b  xchg    rax, [rdi+60h]
0x1800dee2f  mov     rax, [rdi+60h]
0x1800dee33  nop
0x1800dee34  test    rax, rax
0x1800dee37  jnz     short loc_1800DEE6B
0x1800dee39  call    cs:__imp_GetLastError
0x1800dee3f  mov     ebx, eax
0x1800dee41  test    eax, eax
0x1800dee43  jle     short loc_1800DEE4E
0x1800dee45  movzx   ebx, ax
0x1800dee48  or      ebx, 80070000h
0x1800dee4e  mov     rcx, [rsi]; hLibModule
0x1800dee51  call    cs:__imp_FreeLibrary
0x1800dee57  mov     qword ptr [rsi], 0
0x1800dee5e  mov     rcx, rdi; dwData
0x1800dee61  call    ?Release@ConsumerControlManager@@UEAAKXZ; ConsumerControlManager::Release(void)
0x1800dee66  jmp     loc_1800DEDC8
0x1800dee6b  xor     eax, eax
0x1800dee6d  mov     rbx, [rsp+38h+arg_0]
0x1800dee72  mov     rsi, [rsp+38h+arg_8]
0x1800dee77  add     rsp, 30h
0x1800dee7b  pop     rdi
0x1800dee7c  retn
```
