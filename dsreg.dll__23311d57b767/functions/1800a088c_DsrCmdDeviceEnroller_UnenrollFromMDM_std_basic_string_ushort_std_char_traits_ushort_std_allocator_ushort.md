# DsrCmdDeviceEnroller::UnenrollFromMDM(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x1800a088c`
- end: `0x1800a0c0b`
- name: `?UnenrollFromMDM@DsrCmdDeviceEnroller@@CAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `895`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180034684`

## callees

- `0x1800084f4`
- `0x18000bac0`
- `0x180012948`
- `0x180012c7c`
- `0x1800318e8`
- `0x1800319ac`
- `0x18003e2c0`
- `0x180044300`
- `0x180046ae8`
- `0x180046b3c`
- `0x18004c840`
- `0x18009ffe4`
- `0x1800a088c`
- `0x1800bf010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a09d6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a0bc1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a09d6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a0bc1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800a0a1b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800a0b42`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800a0b78`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800a0ba1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800a0a1b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800a0b42`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800a0b78`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800a0ba1`

## string_xrefs

- `0x1800a0aa0`: `WaitForCompletionOrTimeoutNoThrow`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall DsrCmdDeviceEnroller::UnenrollFromMDM(char **a1)
{
  int v2; // eax
  unsigned int v3; // edi
  const wchar_t *v4; // r8
  __int64 (__fastcall *v5)(__int64, __int64, __int64 *); // rdi
  __int64 v6; // rdi
  __int64 (__fastcall *v7)(__int64, _QWORD, HSTRING *); // rbx
  int v8; // eax
  const wchar_t *v9; // r8
  PCWSTR StringRawBuffer; // rax
  __int64 v11; // r8
  HSTRING v12; // rbx
  __int64 v13; // rdi
  __int64 (__fastcall *v14)(__int64, HSTRING, _QWORD); // rsi
  __int64 (__fastcall ***v15)(_QWORD, GUID *, __int64 *); // rcx
  int v16; // edx
  __int64 v17; // rdx
  __int64 v18; // rcx
  __int64 v19; // rdx
  __int64 v20; // rcx
  _QWORD *CurrentRef; // rax
  __int64 v22; // rdx
  _QWORD *v23; // rax
  __int64 v24; // rdx
  __int64 v25; // rax
  PCWSTR v26; // rax
  __int64 v27; // rdx
  __int64 v28; // rcx
  _QWORD *v29; // rax
  __int64 v30; // rdx
  PCWSTR v31; // rbx
  __int64 v32; // rdx
  __int64 v33; // rcx
  __int64 v34; // rax
  PCWSTR v35; // rax
  _BYTE v37[8]; // [rsp+20h] [rbp-39h] BYREF
  HSTRING string; // [rsp+28h] [rbp-31h] BYREF
  __int64 (__fastcall ***v39)(_QWORD, GUID *, __int64 *); // [rsp+30h] [rbp-29h] BYREF
  __int64 v40; // [rsp+38h] [rbp-21h] BYREF
  __int64 v41; // [rsp+40h] [rbp-19h] BYREF
  int v42; // [rsp+48h] [rbp-11h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+50h] [rbp-9h] BYREF
  __int64 v44; // [rsp+68h] [rbp+Fh]

  v40 = 0;
  v42 = 0;
  v37[0] = 0;
  Logger::TraceVerbose((wchar_t *)L"%s started", L"DsrCmdDeviceEnroller::UnenrollFromMDM");
  v41 = 0;
  v44 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Internal.Management.Enrollment.Enroller",
    0x30u,
    0x2Fu);
  v2 = Windows::Foundation::ActivateInstance<Windows::Internal::Management::Enrollment::IEnrollment>(v44, &v41);
  v3 = v2;
  if ( v2 >= 0 )
  {
    v5 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v41 + 96LL);
    v40 = 0;
    v2 = v5(v41, 6, &v40);
    v3 = v2;
    if ( v2 < 0 )
    {
      v4 = L"GetEnrollments";
      goto LABEL_3;
    }
    v2 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v40 + 56LL))(v40, &v42);
    v3 = v2;
    if ( v2 < 0 )
    {
      v4 = L"get_Size";
      goto LABEL_3;
    }
    if ( !v42 )
      goto LABEL_32;
    string = 0;
    v39 = 0;
    v6 = v40;
    v7 = *(__int64 (__fastcall **)(__int64, _QWORD, HSTRING *))(*(_QWORD *)v40 + 48LL);
    WindowsDeleteString(0);
    string = 0;
    v8 = v7(v6, 0, &string);
    v3 = v8;
    if ( v8 >= 0 )
    {
      StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
      v11 = -1;
      do
        ++v11;
      while ( StringRawBuffer[v11] );
      std::wstring::_Assign<unsigned short>(a1, StringRawBuffer, (char *)v11);
      v12 = string;
      v13 = v41;
      v14 = *(__int64 (__fastcall **)(__int64, HSTRING, _QWORD))(*(_QWORD *)v41 + 48LL);
      v15 = v39;
      v39 = 0;
      if ( v15 )
        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*v15)[2])(v15);
      v8 = v14(v13, v12, &v39);
      v3 = v8;
      if ( v8 >= 0 )
      {
        v8 = wil::details::WaitForCompletion<Windows::Foundation::IAsyncAction *>(v39, v16, 0x33450u, v37);
        v3 = v8;
        if ( v8 >= 0 )
        {
          if ( v37[0] )
          {
            v3 = -2147024638;
            if ( **(_BYTE **)CmdOptions::GetCurrentRef(v18, v17) )
            {
              wprintf(
                L"%s: UnenrollAsync failed with timeout (error code: 0x%08x).",
                L"DsrCmdDeviceEnroller::UnenrollFromMDM",
                2147942658LL);
              CurrentRef = (_QWORD *)CmdOptions::GetCurrentRef(v20, v19);
              if ( *(_BYTE *)(*CurrentRef + 12LL) )
              {
                v23 = (_QWORD *)CmdOptions::GetCurrentRef(*CurrentRef, v22);
                if ( *(_QWORD *)(*v23 + 184LL) )
                {
                  v25 = CmdOptions::GetCurrentRef(*v23, v24);
                  fwprintf_s(
                    *(FILE *const *)(*(_QWORD *)v25 + 184LL),
                    L"%s: UnenrollAsync failed with timeout (error code: 0x%08x).",
                    L"DsrCmdDeviceEnroller::UnenrollFromMDM",
                    2147942658LL);
                }
              }
            }
            Logger::TraceError(
              L"%s: UnenrollAsync failed with timeout (error code: 0x%08x).",
              L"DsrCmdDeviceEnroller::UnenrollFromMDM",
              2147942658LL);
          }
          else
          {
            if ( **(_BYTE **)CmdOptions::GetCurrentRef(v18, v17) )
            {
              v26 = WindowsGetStringRawBuffer(string, 0);
              wprintf(L"Successfully unenrolled from MDM (enrollment ID %s).\n", v26);
              v29 = (_QWORD *)CmdOptions::GetCurrentRef(v28, v27);
              if ( *(_BYTE *)(*v29 + 12LL) )
              {
                if ( *(_QWORD *)(*(_QWORD *)CmdOptions::GetCurrentRef(*v29, v30) + 184LL) )
                {
                  v31 = WindowsGetStringRawBuffer(string, 0);
                  v34 = CmdOptions::GetCurrentRef(v33, v32);
                  fwprintf_s(
                    *(FILE *const *)(*(_QWORD *)v34 + 184LL),
                    L"Successfully unenrolled from MDM (enrollment ID %s).\n",
                    v31);
                }
              }
            }
            v35 = WindowsGetStringRawBuffer(string, 0);
            Logger::TraceInformation(L"Successfully unenrolled from MDM (enrollment ID %s).\n", v35);
          }
          goto LABEL_31;
        }
        v9 = L"WaitForCompletionOrTimeoutNoThrow";
      }
      else
      {
        v9 = L"UnenrollAsync";
      }
    }
    else
    {
      v9 = L"GetAt";
    }
    Logger::TraceError(
      L"%s: %s failed with error code: 0x%08x.",
      L"DsrCmdDeviceEnroller::UnenrollFromMDM",
      v9,
      (unsigned int)v8);
LABEL_31:
    wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>((__int64 *)&v39);
    WindowsDeleteString(string);
    goto LABEL_32;
  }
  v4 = L"ActivateInstance";
LABEL_3:
  Logger::TraceError(
    L"%s: %s failed with error code: 0x%08x.",
    L"DsrCmdDeviceEnroller::UnenrollFromMDM",
    v4,
    (unsigned int)v2);
LABEL_32:
  Logger::TraceVerbose((wchar_t *)L"%s - hr: 0x%08x", L"DsrCmdDeviceEnroller::UnenrollFromMDM", v3);
  wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>(&v40);
  wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>(&v41);
  return v3;
}

```

## disassembly

```asm
0x1800a088c  push    rbp
0x1800a088e  push    rbx
0x1800a088f  push    rsi
0x1800a0890  push    rdi
0x1800a0891  push    r14
0x1800a0893  push    r15
0x1800a0895  lea     rbp, [rsp-2Fh]
0x1800a089a  sub     rsp, 88h
0x1800a08a1  mov     rax, cs:__security_cookie
0x1800a08a8  xor     rax, rsp
0x1800a08ab  mov     [rbp+57h+var_40], rax
0x1800a08af  mov     rsi, rcx
0x1800a08b2  xor     r14d, r14d
0x1800a08b5  mov     [rbp+57h+var_70], r14
0x1800a08b9  mov     [rbp+57h+var_78], r14
0x1800a08bd  mov     [rbp+57h+var_68], r14d
0x1800a08c1  mov     [rbp+57h+var_90], r14b
0x1800a08c5  lea     r15, aDsrcmddeviceen_2; "DsrCmdDeviceEnroller::UnenrollFromMDM"
0x1800a08cc  mov     rdx, r15
0x1800a08cf  lea     rcx, aSStarted; "%s started"
0x1800a08d6  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x1800a08db  nop
0x1800a08dc  mov     rcx, [rbp+57h+var_70]
0x1800a08e0  mov     [rbp+57h+var_70], r14
0x1800a08e4  test    rcx, rcx
0x1800a08e7  jz      short loc_1800A08F6
0x1800a08e9  mov     rax, [rcx]
0x1800a08ec  mov     rax, [rax+10h]
0x1800a08f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a08f5  nop
0x1800a08f6  mov     [rbp+57h+var_48], r14
0x1800a08fa  mov     r9d, 2Fh ; '/'; unsigned int
0x1800a0900  lea     r8d, [r9+1]; unsigned int
0x1800a0904  lea     rdx, ?RuntimeClass_Windows_Internal_Management_Enrollment_Enroller@@3QBGB; "Windows.Internal.Management.Enrollment."...
0x1800a090b  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x1800a090f  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800a0914  nop
0x1800a0915  lea     rdx, [rbp+57h+var_70]
0x1800a0919  mov     rcx, [rbp+57h+var_48]
0x1800a091d  call    ??$ActivateInstance@UIEnrollment@Enrollment@Management@Internal@Windows@@@Foundation@Windows@@YAJPEAUHSTRING__@@PEAPEAUIEnrollment@Enrollment@Management@Internal@1@@Z; Windows::Foundation::ActivateInstance<Windows::Internal::Management::Enrollment::IEnrollment>(HSTRING__ *,Windows::Internal::Management::Enrollment::IEnrollment * *)
0x1800a0922  mov     edi, eax
0x1800a0924  test    eax, eax
0x1800a0926  jns     short loc_1800A0946
0x1800a0928  lea     r8, aActivateinstan; "ActivateInstance"
0x1800a092f  mov     r9d, eax
0x1800a0932  mov     rdx, r15
0x1800a0935  lea     rcx, aSSFailedWithEr_2; "%s: %s failed with error code: 0x%08x."
0x1800a093c  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800a0941  jmp     loc_1800A0BC7
0x1800a0946  mov     rbx, [rbp+57h+var_70]
0x1800a094a  mov     rax, [rbx]
0x1800a094d  mov     rdi, [rax+60h]
0x1800a0951  mov     rdx, [rbp+57h+var_78]
0x1800a0955  mov     [rbp+57h+var_78], r14
0x1800a0959  test    rdx, rdx
0x1800a095c  jz      short loc_1800A096E
0x1800a095e  mov     rcx, [rdx]
0x1800a0961  mov     rax, [rcx+10h]
0x1800a0965  mov     rcx, rdx
0x1800a0968  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a096d  nop
0x1800a096e  lea     r8, [rbp+57h+var_78]
0x1800a0972  mov     edx, 6
0x1800a0977  mov     rcx, rbx
0x1800a097a  mov     rax, rdi
0x1800a097d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a0982  mov     edi, eax
0x1800a0984  test    eax, eax
0x1800a0986  jns     short loc_1800A0991
0x1800a0988  lea     r8, aGetenrollments; "GetEnrollments"
0x1800a098f  jmp     short loc_1800A092F
0x1800a0991  mov     rcx, [rbp+57h+var_78]
0x1800a0995  mov     rax, [rcx]
0x1800a0998  lea     rdx, [rbp+57h+var_68]
0x1800a099c  mov     rax, [rax+38h]
0x1800a09a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a09a5  mov     edi, eax
0x1800a09a7  test    eax, eax
0x1800a09a9  jns     short loc_1800A09B7
0x1800a09ab  lea     r8, aGetSize; "get_Size"
0x1800a09b2  jmp     loc_1800A092F
0x1800a09b7  cmp     [rbp+57h+var_68], r14d
0x1800a09bb  jbe     loc_1800A0BC7
0x1800a09c1  mov     [rbp+57h+string], r14
0x1800a09c5  mov     [rbp+57h+var_80], r14
0x1800a09c9  mov     rdi, [rbp+57h+var_78]
0x1800a09cd  mov     rax, [rdi]
0x1800a09d0  mov     rbx, [rax+30h]
0x1800a09d4  xor     ecx, ecx; string
0x1800a09d6  call    cs:__imp_WindowsDeleteString
0x1800a09dc  mov     [rbp+57h+string], r14
0x1800a09e0  lea     r8, [rbp+57h+string]
0x1800a09e4  xor     edx, edx
0x1800a09e6  mov     rcx, rdi
0x1800a09e9  mov     rax, rbx
0x1800a09ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a09f1  mov     edi, eax
0x1800a09f3  test    eax, eax
0x1800a09f5  jns     short loc_1800A0A15
0x1800a09f7  lea     r8, aGetat; "GetAt"
0x1800a09fe  mov     r9d, eax
0x1800a0a01  mov     rdx, r15
0x1800a0a04  lea     rcx, aSSFailedWithEr_2; "%s: %s failed with error code: 0x%08x."
0x1800a0a0b  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800a0a10  jmp     loc_1800A0BB3
0x1800a0a15  xor     edx, edx; length
0x1800a0a17  mov     rcx, [rbp+57h+string]; string
0x1800a0a1b  call    cs:__imp_WindowsGetStringRawBuffer
0x1800a0a21  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800a0a25  inc     r8
0x1800a0a28  cmp     [rax+r8*2], r14w
0x1800a0a2d  jnz     short loc_1800A0A25
0x1800a0a2f  mov     rdx, rax
0x1800a0a32  mov     rcx, rsi
0x1800a0a35  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1800a0a3a  mov     rbx, [rbp+57h+string]
0x1800a0a3e  mov     rdi, [rbp+57h+var_70]
0x1800a0a42  mov     rax, [rdi]
0x1800a0a45  mov     rsi, [rax+30h]
0x1800a0a49  mov     rcx, [rbp+57h+var_80]
0x1800a0a4d  mov     [rbp+57h+var_80], r14
0x1800a0a51  test    rcx, rcx
0x1800a0a54  jz      short loc_1800A0A63
0x1800a0a56  mov     rdx, [rcx]
0x1800a0a59  mov     rax, [rdx+10h]
0x1800a0a5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a0a62  nop
0x1800a0a63  lea     r8, [rbp+57h+var_80]
0x1800a0a67  mov     rdx, rbx
0x1800a0a6a  mov     rcx, rdi
0x1800a0a6d  mov     rax, rsi
0x1800a0a70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a0a75  mov     edi, eax
0x1800a0a77  test    eax, eax
0x1800a0a79  jns     short loc_1800A0A87
0x1800a0a7b  lea     r8, aUnenrollasync; "UnenrollAsync"
0x1800a0a82  jmp     loc_1800A09FE
0x1800a0a87  lea     r9, [rbp+57h+var_90]
0x1800a0a8b  mov     r8d, 33450h
0x1800a0a91  mov     rcx, [rbp+57h+var_80]
0x1800a0a95  call    ??$WaitForCompletion@PEAUIAsyncAction@Foundation@Windows@@@details@wil@@YAJPEAUIAsyncAction@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z; wil::details::WaitForCompletion<Windows::Foundation::IAsyncAction *>(Windows::Foundation::IAsyncAction *,tagCOWAIT_FLAGS,ulong,bool *)
0x1800a0a9a  mov     edi, eax
0x1800a0a9c  test    eax, eax
0x1800a0a9e  jns     short loc_1800A0AAC
0x1800a0aa0  lea     r8, aWaitforcomplet_1; "WaitForCompletionOrTimeoutNoThrow"
0x1800a0aa7  jmp     loc_1800A09FE
0x1800a0aac  cmp     [rbp+57h+var_90], r14b
0x1800a0ab0  jz      short loc_1800A0B28
0x1800a0ab2  mov     edi, 80070102h
0x1800a0ab7  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x1800a0abc  mov     rcx, [rax]
0x1800a0abf  lea     rbx, aSUnenrollasync; "%s: UnenrollAsync failed with timeout ("...
0x1800a0ac6  cmp     [rcx], r14b
0x1800a0ac9  jz      short loc_1800A0B15
0x1800a0acb  mov     r8d, edi
0x1800a0ace  mov     rdx, r15
0x1800a0ad1  mov     rcx, rbx; Format
0x1800a0ad4  call    wprintf
0x1800a0ad9  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x1800a0ade  mov     rcx, [rax]
0x1800a0ae1  cmp     [rcx+0Ch], r14b
0x1800a0ae5  jz      short loc_1800A0B15
0x1800a0ae7  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x1800a0aec  mov     rcx, [rax]
0x1800a0aef  cmp     [rcx+0B8h], r14
0x1800a0af6  jz      short loc_1800A0B15
0x1800a0af8  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x1800a0afd  mov     rcx, [rax]
0x1800a0b00  mov     r9d, edi
0x1800a0b03  mov     r8, r15
0x1800a0b06  mov     rdx, rbx; Format
0x1800a0b09  mov     rcx, [rcx+0B8h]; Stream
0x1800a0b10  call    fwprintf_s
0x1800a0b15  mov     r8d, edi
0x1800a0b18  mov     rdx, r15
0x1800a0b1b  mov     rcx, rbx; unsigned __int16 *
0x1800a0b1e  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800a0b23  jmp     loc_1800A0BB3
0x1800a0b28  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x1800a0b2d  mov     rcx, [rax]
0x1800a0b30  lea     rsi, aSuccessfullyUn; "Successfully unenrolled from MDM (enrol"...
0x1800a0b37  cmp     [rcx], r14b
0x1800a0b3a  jz      short loc_1800A0B9B
0x1800a0b3c  xor     edx, edx; length
0x1800a0b3e  mov     rcx, [rbp+57h+string]; string
0x1800a0b42  call    cs:__imp_WindowsGetStringRawBuffer
0x1800a0b48  mov     rdx, rax
0x1800a0b4b  mov     rcx, rsi; Format
0x1800a0b4e  call    wprintf
0x1800a0b53  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x1800a0b58  mov     rcx, [rax]
0x1800a0b5b  cmp     [rcx+0Ch], r14b
0x1800a0b5f  jz      short loc_1800A0B9B
0x1800a0b61  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x1800a0b66  mov     rcx, [rax]
0x1800a0b69  cmp     [rcx+0B8h], r14
0x1800a0b70  jz      short loc_1800A0B9B
0x1800a0b72  xor     edx, edx; length
0x1800a0b74  mov     rcx, [rbp+57h+string]; string
0x1800a0b78  call    cs:__imp_WindowsGetStringRawBuffer
0x1800a0b7e  mov     rbx, rax
0x1800a0b81  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x1800a0b86  mov     rcx, [rax]
0x1800a0b89  mov     r8, rbx
0x1800a0b8c  mov     rdx, rsi; Format
0x1800a0b8f  mov     rcx, [rcx+0B8h]; Stream
0x1800a0b96  call    fwprintf_s
0x1800a0b9b  xor     edx, edx; length
0x1800a0b9d  mov     rcx, [rbp+57h+string]; string
0x1800a0ba1  call    cs:__imp_WindowsGetStringRawBuffer
0x1800a0ba7  mov     rdx, rax
0x1800a0baa  mov     rcx, rsi; unsigned __int16 *
0x1800a0bad  call    ?TraceInformation@Logger@@SAJPEBGZZ; Logger::TraceInformation(ushort const *,...)
0x1800a0bb2  nop
0x1800a0bb3  lea     rcx, [rbp+57h+var_80]
0x1800a0bb7  call    ??1?$com_ptr_t@UIWebProviderError@Core@Web@Authentication@Security@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>(void)
0x1800a0bbc  nop
0x1800a0bbd  mov     rcx, [rbp+57h+string]; string
0x1800a0bc1  call    cs:__imp_WindowsDeleteString
0x1800a0bc7  mov     r8d, edi
0x1800a0bca  mov     rdx, r15
0x1800a0bcd  lea     rcx, aSHr0x08x; "%s - hr: 0x%08x"
0x1800a0bd4  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x1800a0bd9  nop
0x1800a0bda  lea     rcx, [rbp+57h+var_78]
0x1800a0bde  call    ??1?$com_ptr_t@UIWebProviderError@Core@Web@Authentication@Security@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>(void)
0x1800a0be3  nop
0x1800a0be4  lea     rcx, [rbp+57h+var_70]
0x1800a0be8  call    ??1?$com_ptr_t@UIWebProviderError@Core@Web@Authentication@Security@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>(void)
0x1800a0bed  mov     eax, edi
0x1800a0bef  mov     rcx, [rbp+57h+var_40]
0x1800a0bf3  xor     rcx, rsp; StackCookie
0x1800a0bf6  call    __security_check_cookie
0x1800a0bfb  add     rsp, 88h
0x1800a0c02  pop     r15
0x1800a0c04  pop     r14
0x1800a0c06  pop     rdi
0x1800a0c07  pop     rsi
0x1800a0c08  pop     rbx
0x1800a0c09  pop     rbp
0x1800a0c0a  retn
```
