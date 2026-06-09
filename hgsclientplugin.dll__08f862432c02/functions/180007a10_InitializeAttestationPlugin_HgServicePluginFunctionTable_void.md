# InitializeAttestationPlugin(HgServicePluginFunctionTable *,void * *)

- ea: `0x180007a10`
- end: `0x180007bc8`
- name: `?InitializeAttestationPlugin@@YAJPEAUHgServicePluginFunctionTable@@PEAPEAX@Z`
- size: `440`
- prototype: `__int64 __fastcall(struct HgServicePluginFunctionTable *, void **)`
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## callees

- `0x180001f9e`
- `0x1800049f4`
- `0x180005740`
- `0x1800068ec`
- `0x1800069fc`
- `0x180007a10`
- `0x180008568`
- `0x180009f44`
- `0x18000c010`

## import_xrefs

- `mi!MI_Application_InitializeV1` at `0x180007b00`
- `mi!MI_Application_InitializeV1` at `0x180007b00`

## string_xrefs

- `0x180007af7`: `HGS_Plugin`
- `0x180007b85`: `servercommon\base\securehostingservice\common\service\plugin\hgsclientplugin.cpp`
- `0x180007b46`: `Built-in HGS plugin initialized`

## pseudocode

```c
__int64 __fastcall InitializeAttestationPlugin(struct HgServicePluginFunctionTable *a1, void **a2)
{
  MI_Result v3; // eax
  const wchar_t *v4; // rdx
  MI_Result v5; // ebx
  enum _MI_Result v6; // edx
  unsigned int v7; // ebx
  unsigned int v8; // r8d
  const char *v9; // r9
  __int64 result; // rax
  const struct wil::FailureInfo *v11; // rdx
  _OWORD v12[4]; // [rsp+20h] [rbp-E8h] BYREF
  _BYTE v13[168]; // [rsp+60h] [rbp-A8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+0h]
  MI_Instance *extendedError; // [rsp+110h] [rbp+8h] BYREF

  try
  {
    if ( a1 && *(_DWORD *)a1 == 64 )
    {
      McGenEventRegister_EventRegister();
      if ( wil::details::g_pfnLoggingCallback
        && (__int64 (__fastcall *)())wil::details::g_pfnLoggingCallback != lambda_e8e7ebfc1054336f25f124d90993409f_::_lambda_invoker_cdecl_ )
      {
        memset_0(v13, 0, 0x98u);
        wil::details::WilFailFast((wil::details *)v13, v11);
      }
      wil::details::g_pfnLoggingCallback = (__int64)lambda_e8e7ebfc1054336f25f124d90993409f_::_lambda_invoker_cdecl_;
      memset_0(v12, 0, sizeof(v12));
      *(_OWORD *)a1 = v12[0];
      *((_OWORD *)a1 + 1) = v12[1];
      *((_OWORD *)a1 + 2) = v12[2];
      *((_OWORD *)a1 + 3) = v12[3];
      *(_DWORD *)a1 = 64;
      *((_QWORD *)a1 + 1) = QueryAttestationResults;
      *((_QWORD *)a1 + 2) = RequestCAIntermediateCertificate;
      *((_QWORD *)a1 + 3) = FreeAttestationResults;
      *((_QWORD *)a1 + 4) = UnwrapKeyProtector;
      *((_QWORD *)a1 + 5) = &EncryptDataWithKeyProtector;
      *((_QWORD *)a1 + 6) = &DecryptDataWithKeyProtector;
      *((_QWORD *)a1 + 7) = &FreeBlobData;
      extendedError = 0;
      v3 = MI_Application_InitializeV1(0, L"HGS_Plugin", &extendedError, &miApplication);
      v5 = v3;
      if ( v3 )
      {
        Microsoft::HostGuardian::Client::Plugin::EventUtilities::TraceError(
          (wchar_t *)L"Failed to initialize MI application. %d.",
          (const wchar_t *)(unsigned int)v3);
        v7 = Microsoft::HostGuardian::Client::Plugin::CimUtilities::HRESULT_FROM_MIRESULT(
               (Microsoft::HostGuardian::Client::Plugin::CimUtilities *)(unsigned int)v5,
               v6);
        if ( extendedError && extendedError->ft )
          ((void (*)(void))extendedError->ft->Delete)();
        result = v7;
      }
      else
      {
        Microsoft::HostGuardian::Client::Plugin::EventUtilities::TraceInfo(
          (wchar_t *)L"Built-in HGS plugin initialized",
          v4);
        if ( extendedError && extendedError->ft )
          ((void (*)(void))extendedError->ft->Delete)();
        result = 0;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x30,
        (unsigned int)"servercommon\\base\\securehostingservice\\common\\service\\plugin\\hgsclientplugin.cpp",
        (const char *)0x80070057LL,
        v12[0]);
      result = 2147942487LL;
    }
  }
  catch ( ... )
  {
    LODWORD(extendedError) = wil::details::in1diag3::Return_CaughtException(retaddr, (void *)0x51, v8, v9);
    return (unsigned int)extendedError;
  }
  return result;
}

```

## disassembly

```asm
0x180007a10  push    rbx
0x180007a12  sub     rsp, 100h
0x180007a19  mov     rbx, rcx
0x180007a1c  test    rcx, rcx
0x180007a1f  jz      loc_180007B75
0x180007a25  cmp     dword ptr [rcx], 40h ; '@'
0x180007a28  jnz     loc_180007B75
0x180007a2e  call    McGenEventRegister_EventRegister
0x180007a33  mov     rcx, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180007a3a  lea     rax, _lambda_e8e7ebfc1054336f25f124d90993409f____lambda_invoker_cdecl_
0x180007a41  test    rcx, rcx
0x180007a44  jz      short loc_180007A4F
0x180007a46  cmp     rcx, rax
0x180007a49  jnz     loc_180007BAA
0x180007a4f  mov     cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA, rax
0x180007a56  xor     edx, edx; Val
0x180007a58  lea     r8d, [rdx+40h]; Size
0x180007a5c  lea     rcx, [rsp+108h+var_E8]; void *
0x180007a61  call    memset_0
0x180007a66  movups  xmm0, [rsp+108h+var_E8]
0x180007a6b  movups  xmmword ptr [rbx], xmm0
0x180007a6e  movups  xmm1, [rsp+108h+var_D8]
0x180007a73  movups  xmmword ptr [rbx+10h], xmm1
0x180007a77  movups  xmm0, [rsp+108h+var_C8]
0x180007a7c  movups  xmmword ptr [rbx+20h], xmm0
0x180007a80  movups  xmm1, [rsp+108h+var_B8]
0x180007a85  movups  xmmword ptr [rbx+30h], xmm1
0x180007a89  mov     dword ptr [rbx], 40h ; '@'
0x180007a8f  lea     rax, ?QueryAttestationResults@@YAJPEAXPEB_WIPEAW4AttestationResultType@@PEAW4ShsAttestationFlag@@PEAPEA_WPEAIPEAPEAUAttestationResult@@@Z; QueryAttestationResults(void *,wchar_t const *,uint,AttestationResultType *,ShsAttestationFlag *,wchar_t * *,uint *,AttestationResult * *)
0x180007a96  mov     [rbx+8], rax
0x180007a9a  lea     rax, ?RequestCAIntermediateCertificate@@YAJPEAXPEB_WQEAUHgBlob@@222PEAW4ShsAttestationFlag@@PEAPEA_WPEAIPEAPEAUAttestationResult@@@Z; RequestCAIntermediateCertificate(void *,wchar_t const *,HgBlob * const,HgBlob * const,HgBlob * const,HgBlob * const,ShsAttestationFlag *,wchar_t * *,uint *,AttestationResult * *)
0x180007aa1  mov     [rbx+10h], rax
0x180007aa5  lea     rax, ?FreeAttestationResults@@YAJPEAXPEA_WIPEAUAttestationResult@@@Z; FreeAttestationResults(void *,wchar_t *,uint,AttestationResult *)
0x180007aac  mov     [rbx+18h], rax
0x180007ab0  lea     rax, ?UnwrapKeyProtector@@YAJPEAXUHgBlob@@PEAU1@222@Z; UnwrapKeyProtector(void *,HgBlob,HgBlob *,HgBlob *,HgBlob *,HgBlob *)
0x180007ab7  mov     [rbx+20h], rax
0x180007abb  lea     rax, ?EncryptDataWithKeyProtector@@YAJPEAXUHgBlob@@I1HPEAU1@2@Z; EncryptDataWithKeyProtector(void *,HgBlob,uint,HgBlob,int,HgBlob *,HgBlob *)
0x180007ac2  mov     [rbx+28h], rax
0x180007ac6  lea     rax, ?DecryptDataWithKeyProtector@@YAJPEAXUHgBlob@@1PEAU1@@Z; DecryptDataWithKeyProtector(void *,HgBlob,HgBlob,HgBlob *)
0x180007acd  mov     [rbx+30h], rax
0x180007ad1  lea     rax, ?FreeBlobData@@YAJPEAXUHgBlob@@@Z; FreeBlobData(void *,HgBlob)
0x180007ad8  mov     [rbx+38h], rax
0x180007adc  mov     [rsp+108h+extendedError], 0
0x180007ae8  lea     r9, ?miApplication@@3U_MI_Application@@A; application
0x180007aef  lea     r8, [rsp+108h+extendedError]; extendedError
0x180007af7  lea     rdx, applicationID; "HGS_Plugin"
0x180007afe  xor     ecx, ecx; flags
0x180007b00  call    cs:__imp_MI_Application_InitializeV1
0x180007b06  mov     ebx, eax
0x180007b08  test    eax, eax
0x180007b0a  jz      short loc_180007B46
0x180007b0c  mov     edx, eax; wchar_t *
0x180007b0e  lea     rcx, aFailedToInitia; "Failed to initialize MI application. %d"...
0x180007b15  call    ?TraceError@EventUtilities@Plugin@Client@HostGuardian@Microsoft@@YAXPEB_WZZ; Microsoft::HostGuardian::Client::Plugin::EventUtilities::TraceError(wchar_t const *,...)
0x180007b1a  mov     ecx, ebx; this
0x180007b1c  call    ?HRESULT_FROM_MIRESULT@CimUtilities@Plugin@Client@HostGuardian@Microsoft@@YAJW4_MI_Result@@@Z; Microsoft::HostGuardian::Client::Plugin::CimUtilities::HRESULT_FROM_MIRESULT(_MI_Result)
0x180007b21  mov     ebx, eax
0x180007b23  mov     rcx, [rsp+108h+extendedError]
0x180007b2b  test    rcx, rcx
0x180007b2e  jz      short loc_180007B42
0x180007b30  mov     rax, [rcx]
0x180007b33  test    rax, rax
0x180007b36  jz      short loc_180007B42
0x180007b38  mov     rax, [rax+10h]
0x180007b3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007b41  nop
0x180007b42  mov     eax, ebx
0x180007b44  jmp     short loc_180007BA1
0x180007b46  lea     rcx, aBuiltInHgsPlug_0; "Built-in HGS plugin initialized"
0x180007b4d  call    ?TraceInfo@EventUtilities@Plugin@Client@HostGuardian@Microsoft@@YAXPEB_WZZ; Microsoft::HostGuardian::Client::Plugin::EventUtilities::TraceInfo(wchar_t const *,...)
0x180007b52  mov     rcx, [rsp+108h+extendedError]
0x180007b5a  test    rcx, rcx
0x180007b5d  jz      short loc_180007B71
0x180007b5f  mov     rax, [rcx]
0x180007b62  test    rax, rax
0x180007b65  jz      short loc_180007B71
0x180007b67  mov     rax, [rax+10h]
0x180007b6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007b70  nop
0x180007b71  xor     eax, eax
0x180007b73  jmp     short loc_180007BA1
0x180007b75  mov     rcx, [rsp+108h]; this
0x180007b7d  mov     ebx, 80070057h
0x180007b82  mov     r9d, ebx; char *
0x180007b85  lea     r8, aServercommonBa_1; "servercommon\\base\\securehostingservic"...
0x180007b8c  mov     edx, 30h ; '0'; void *
0x180007b91  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007b96  mov     eax, ebx
0x180007b98  jmp     short loc_180007BA1
0x180007b9a  mov     eax, dword ptr [rsp+108h+extendedError]
0x180007ba1  add     rsp, 100h
0x180007ba8  pop     rbx
0x180007ba9  retn
0x180007baa  xor     edx, edx; Val
0x180007bac  mov     r8d, 98h; Size
0x180007bb2  lea     rcx, [rsp+108h+var_A8]; void *
0x180007bb7  call    memset_0
0x180007bbc  lea     rcx, [rsp+108h+var_A8]; this
0x180007bc1  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
