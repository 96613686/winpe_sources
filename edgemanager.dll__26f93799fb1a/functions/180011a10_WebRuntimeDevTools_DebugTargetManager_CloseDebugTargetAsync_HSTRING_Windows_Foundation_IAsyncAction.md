# WebRuntimeDevTools::DebugTargetManager::CloseDebugTargetAsync(HSTRING__ *,Windows::Foundation::IAsyncAction * *)

- ea: `0x180011a10`
- end: `0x180011aee`
- name: `?CloseDebugTargetAsync@DebugTargetManager@WebRuntimeDevTools@@UEAAJPEAUHSTRING__@@PEAPEAUIAsyncAction@Foundation@Windows@@@Z`
- size: `222`
- prototype: `int(WebRuntimeDevTools::DebugTargetManager *__hidden this, HSTRING, struct Windows::Foundation::IAsyncAction **)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180011a10`
- `0x180011af4`
- `0x180011b40`
- `0x180011c1c`
- `0x180035b88`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x180011a30`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x180011a30`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180011ac9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180011ad4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180011ac9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180011ad4`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall WebRuntimeDevTools::DebugTargetManager::CloseDebugTargetAsync(
        WebRuntimeDevTools::DebugTargetManager *this,
        HSTRING a2,
        struct Windows::Foundation::IAsyncAction **a3)
{
  int v3; // ebx
  int v6; // eax
  __int64 v7; // rax
  int v8; // r8d
  int v9; // r9d
  unsigned int v10; // ebx
  int v11; // [rsp+20h] [rbp-50h]
  int v12; // [rsp+30h] [rbp-40h] BYREF
  __int64 v13; // [rsp+34h] [rbp-3Ch]
  HSTRING newString; // [rsp+40h] [rbp-30h] BYREF
  char v15; // [rsp+48h] [rbp-28h]
  char *v16; // [rsp+50h] [rbp-20h] BYREF
  HSTRING string; // [rsp+58h] [rbp-18h]
  char v18; // [rsp+60h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+8h]
  HSTRING v20; // [rsp+88h] [rbp+18h] BYREF

  v20 = a2;
  v3 = (int)a3;
  if ( !WindowsGetStringLen(a2) )
    return 2147942487LL;
  newString = 0;
  v15 = 0;
  v6 = Microsoft::WRL::Wrappers::HString::Set(&newString, &v20);
  if ( v6 < 0 )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0x6A,
      (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webruntime\\webruntimediagnostics\\debugtargetmanager.cpp",
      (const char *)(unsigned int)v6,
      v11);
  v16 = (char *)this - 16;
  string = newString;
  newString = 0;
  v18 = 0;
  v15 = 1;
  v12 = 4;
  v13 = 128;
  v7 = Windows::Internal::MakeOpLambda_0_Windows::Internal::CNoResult__lambda_e064217146c35ddeeb1fb9fd0662426b___(&v16);
  v10 = Windows::Internal::MakeAsyncHelper<Windows::Foundation::IAsyncAction,Windows::Foundation::IAsyncActionCompletedHandler,Windows::Internal::INilDelegate,Windows::Internal::CNoResult,Windows::Internal::ComTaskPoolHandler,Microsoft::WRL::AsyncCausalityOptions<&unsigned short const near * const WebRuntimeDevTools::CloseDebugTargetAsyncOperationName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>(
          v3,
          (unsigned int)&v12,
          v8,
          v9,
          v7);
  WindowsDeleteString(string);
  WindowsDeleteString(newString);
  return v10;
}

```

## disassembly

```asm
0x180011a10  mov     [rsp-8+arg_0], rbx
0x180011a15  mov     [rsp-8+arg_10], rdi
0x180011a1a  mov     [rsp-8+arg_8], rdx
0x180011a1f  push    rbp
0x180011a20  mov     rbp, rsp
0x180011a23  sub     rsp, 70h
0x180011a27  mov     rbx, r8
0x180011a2a  mov     rdi, rcx
0x180011a2d  mov     rcx, rdx; string
0x180011a30  call    cs:__imp_WindowsGetStringLen
0x180011a36  test    eax, eax
0x180011a38  jnz     short loc_180011A44
0x180011a3a  mov     eax, 80070057h
0x180011a3f  jmp     loc_180011ADC
0x180011a44  mov     [rbp+newString], 0
0x180011a4c  mov     [rbp+var_28], 0
0x180011a50  lea     rdx, [rbp+arg_8]; HSTRING *
0x180011a54  lea     rcx, [rbp+newString]; newString
0x180011a58  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAUHSTRING__@@@Z; Microsoft::WRL::Wrappers::HString::Set(HSTRING__ * const &)
0x180011a5d  mov     rcx, [rbp+8]; this
0x180011a61  test    eax, eax
0x180011a63  jns     short loc_180011A7A
0x180011a65  mov     r9d, eax; char *
0x180011a68  lea     r8, aOnecoreuapInet_2; "onecoreuap\\inetcore\\edgemanager\\webr"...
0x180011a6f  mov     edx, 6Ah ; 'j'; void *
0x180011a74  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x180011a7a  lea     rax, [rdi-10h]
0x180011a7e  mov     [rbp+var_20], rax
0x180011a82  mov     rax, [rbp+newString]
0x180011a86  mov     [rbp+string], rax
0x180011a8a  mov     [rbp+newString], 0
0x180011a92  mov     [rbp+var_10], 0
0x180011a96  mov     [rbp+var_28], 1
0x180011a9a  mov     [rbp+var_40], 4
0x180011aa1  mov     [rbp+var_3C], 80h
0x180011aa9  lea     rcx, [rbp+var_20]
0x180011aad  call    Windows__Internal__MakeOpLambda_0_Windows__Internal__CNoResult__lambda_e064217146c35ddeeb1fb9fd0662426b___
0x180011ab2  mov     qword ptr [rsp+70h+var_50], rax
0x180011ab7  lea     rdx, [rbp+var_40]
0x180011abb  mov     rcx, rbx
0x180011abe  call    ??$MakeAsyncHelper@UIAsyncAction@Foundation@Windows@@UIAsyncActionCompletedHandler@23@UINilDelegate@Internal@3@VCNoResult@63@VComTaskPoolHandler@63@U?$AsyncCausalityOptions@$1?CloseDebugTargetAsyncOperationName@WebRuntimeDevTools@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@YAJPEAPEAUIAsyncAction@Foundation@1@$$QEAVComTaskPoolHandler@01@QEBGW4TrustLevel@@PEAV?$AsyncCallbackBase@VCNoResult@Internal@Windows@@@01@@Z; Windows::Internal::MakeAsyncHelper<Windows::Foundation::IAsyncAction,Windows::Foundation::IAsyncActionCompletedHandler,Windows::Internal::INilDelegate,Windows::Internal::CNoResult,Windows::Internal::ComTaskPoolHandler,Microsoft::WRL::AsyncCausalityOptions<&ushort const near * const WebRuntimeDevTools::CloseDebugTargetAsyncOperationName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>(Windows::Foundation::IAsyncAction * *,Windows::Internal::ComTaskPoolHandler &&,ushort const * const,TrustLevel,Windows::Internal::AsyncCallbackBase<Windows::Internal::CNoResult> *)
0x180011ac3  mov     ebx, eax
0x180011ac5  mov     rcx, [rbp+string]; string
0x180011ac9  call    cs:__imp_WindowsDeleteString
0x180011acf  nop
0x180011ad0  mov     rcx, [rbp+newString]; string
0x180011ad4  call    cs:__imp_WindowsDeleteString
0x180011ada  mov     eax, ebx
0x180011adc  lea     r11, [rsp+70h+var_s0]
0x180011ae1  mov     rbx, [r11+10h]
0x180011ae5  mov     rdi, [r11+20h]
0x180011ae9  mov     rsp, r11
0x180011aec  pop     rbp
0x180011aed  retn
```
