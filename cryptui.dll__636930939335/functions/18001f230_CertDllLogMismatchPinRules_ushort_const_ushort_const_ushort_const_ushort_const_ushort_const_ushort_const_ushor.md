# CertDllLogMismatchPinRules(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *)

- ea: `0x18001f230`
- end: `0x18001f468`
- name: `?CertDllLogMismatchPinRules@@YAJPEBG000000@Z`
- size: `568`
- prototype: `int(const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting`

## callees

- `0x18000c754`
- `0x18001f230`
- `0x18001f470`
- `0x18003e582`
- `0x18003e5c0`

## import_xrefs

- `msvcrt!wcsrchr` at `0x18001f30a`
- `msvcrt!wcsrchr` at `0x18001f31f`
- `msvcrt!wcsrchr` at `0x18001f30a`
- `msvcrt!wcsrchr` at `0x18001f31f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001f43d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001f43d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001f2dd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001f2dd`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18001f2c7`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18001f2c7`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x18001f2f4`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x18001f2f4`
- `wer!WerReportSetParameter` at `0x18001f3ad`
- `wer!WerReportSetParameter` at `0x18001f3c7`
- `wer!WerReportSetParameter` at `0x18001f3e3`
- `wer!WerReportSetParameter` at `0x18001f3fb`
- `wer!WerReportSetParameter` at `0x18001f3ad`
- `wer!WerReportSetParameter` at `0x18001f3c7`
- `wer!WerReportSetParameter` at `0x18001f3e3`
- `wer!WerReportSetParameter` at `0x18001f3fb`
- `wer!WerReportCreate` at `0x18001f388`
- `wer!WerReportCreate` at `0x18001f388`
- `wer!WerReportAddFile` at `0x18001f415`
- `wer!WerReportAddFile` at `0x18001f415`
- `wer!WerReportSubmit` at `0x18001f42d`
- `wer!WerReportSubmit` at `0x18001f42d`

## pseudocode

```c
__int64 __fastcall CertDllLogMismatchPinRules(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        const unsigned __int16 *a5,
        const unsigned __int16 *pwzValue,
        const unsigned __int16 *pwzPath)
{
  HANDLE CurrentProcess; // rax
  wchar_t *v10; // rax
  WCHAR *wzApplicationPath; // r8
  const unsigned __int16 *v12; // rax
  unsigned __int16 *v13; // rbx
  HRESULT v14; // edi
  HREPORT phReportHandle; // [rsp+20h] [rbp-E0h] BYREF
  DWORD dwSize; // [rsp+28h] [rbp-D8h] BYREF
  _WER_SUBMIT_RESULT pSubmitResult; // [rsp+2Ch] [rbp-D4h] BYREF
  _WER_REPORT_INFORMATION pReportInformation; // [rsp+30h] [rbp-D0h] BYREF

  phReportHandle = 0;
  memset_0(&pReportInformation.dwSize + 1, 0, 0x89Cu);
  pSubmitResult = 0;
  dwSize = 0;
  pReportInformation.dwSize = 2208;
  if ( !LoadStringW(HinstDll, 0xDDFu, pReportInformation.wzFriendlyEventName, 128) )
    pReportInformation.wzFriendlyEventName[0] = 0;
  dwSize = 260;
  CurrentProcess = GetCurrentProcess();
  if ( QueryFullProcessImageNameW(CurrentProcess, 0, pReportInformation.wzApplicationPath, &dwSize) )
  {
    v10 = wcsrchr(pReportInformation.wzApplicationPath, 0x5Cu);
    if ( v10
      || (v10 = wcsrchr(pReportInformation.wzApplicationPath, 0x3Au),
          wzApplicationPath = pReportInformation.wzApplicationPath,
          v10) )
    {
      wzApplicationPath = v10 + 1;
    }
    StringCchCopyW(pReportInformation.wzApplicationName, 0x80u, wzApplicationPath);
  }
  v12 = (const unsigned __int16 *)FormatMessageFromResource(0xDDEu);
  v13 = (unsigned __int16 *)v12;
  if ( v12 )
    StringCchCopyW(pReportInformation.wzDescription, 0x200u, v12);
  v14 = WerReportCreate(L"CertPinning", WerReportNonCritical, &pReportInformation, &phReportHandle);
  if ( v14 >= 0 )
  {
    WerReportSetParameter(phReportHandle, 0, L"ApplicationName", L"App2");
    WerReportSetParameter(phReportHandle, 1u, L"ServerName", a4);
    WerReportSetParameter(phReportHandle, 2u, L"SequenceNumber", pwzValue);
    WerReportSetParameter(phReportHandle, 3u, L"Thumbprint", a3);
    if ( pwzPath )
      WerReportAddFile(phReportHandle, pwzPath, WerFileTypeOther, 2u);
    v14 = WerReportSubmit(phReportHandle, WerConsentApproved, 4u, &pSubmitResult);
    if ( v13 )
      LocalFree(v13);
  }
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x18001f230  push    rbp
0x18001f232  push    rbx
0x18001f233  push    rsi
0x18001f234  push    rdi
0x18001f235  push    r12
0x18001f237  push    r13
0x18001f239  push    r14
0x18001f23b  push    r15
0x18001f23d  lea     rbp, [rsp-7E8h]
0x18001f245  sub     rsp, 8E8h
0x18001f24c  mov     rax, cs:__security_cookie
0x18001f253  xor     rax, rsp
0x18001f256  mov     [rbp+820h+var_50], rax
0x18001f25d  mov     r14, [rbp+820h+arg_20]
0x18001f264  mov     r15, r8
0x18001f267  mov     r13, [rbp+820h+pwzValue]
0x18001f26e  mov     rdi, rdx
0x18001f271  mov     rsi, [rbp+820h+pwzPath]
0x18001f278  mov     rbx, rcx
0x18001f27b  xor     edx, edx; Val
0x18001f27d  mov     [rsp+920h+phReportHandle], 0
0x18001f286  mov     r8d, 89Ch; Size
0x18001f28c  lea     rcx, [rsp+920h+pReportInformation+4]; void *
0x18001f291  mov     r12, r9
0x18001f294  call    memset_0
0x18001f299  mov     rcx, cs:?HinstDll@@3PEAUHINSTANCE__@@EA; hInstance
0x18001f2a0  lea     r8, [rbp+820h+pReportInformation.wzFriendlyEventName]; lpBuffer
0x18001f2a4  mov     r9d, 80h; cchBufferMax
0x18001f2aa  mov     [rsp+920h+pSubmitResult], 0
0x18001f2b2  mov     edx, 0DDFh; uID
0x18001f2b7  mov     [rsp+920h+dwSize], 0
0x18001f2bf  mov     [rsp+920h+pReportInformation.dwSize], 8A0h
0x18001f2c7  call    cs:__imp_LoadStringW
0x18001f2cd  test    eax, eax
0x18001f2cf  jnz     short loc_18001F2D5
0x18001f2d1  mov     [rbp+820h+pReportInformation.wzFriendlyEventName], ax
0x18001f2d5  mov     [rsp+920h+dwSize], 104h
0x18001f2dd  call    cs:__imp_GetCurrentProcess
0x18001f2e3  lea     r9, [rsp+920h+dwSize]; lpdwSize
0x18001f2e8  xor     edx, edx; dwFlags
0x18001f2ea  mov     rcx, rax; hProcess
0x18001f2ed  lea     r8, [rbp+820h+pReportInformation.wzApplicationPath]; lpExeName
0x18001f2f4  call    cs:__imp_QueryFullProcessImageNameW
0x18001f2fa  test    eax, eax
0x18001f2fc  jz      short loc_18001F346
0x18001f2fe  mov     edx, 5Ch ; '\'; Ch
0x18001f303  lea     rcx, [rbp+820h+pReportInformation.wzApplicationPath]; Str
0x18001f30a  call    cs:__imp_wcsrchr
0x18001f310  test    rax, rax
0x18001f313  jnz     short loc_18001F331
0x18001f315  lea     edx, [rax+3Ah]; Ch
0x18001f318  lea     rcx, [rbp+820h+pReportInformation.wzApplicationPath]; Str
0x18001f31f  call    cs:__imp_wcsrchr
0x18001f325  lea     r8, [rbp+820h+pReportInformation.wzApplicationPath]
0x18001f32c  test    rax, rax
0x18001f32f  jz      short loc_18001F335
0x18001f331  lea     r8, [rax+2]; unsigned __int16 *
0x18001f335  mov     edx, 80h; unsigned __int64
0x18001f33a  lea     rcx, [rbp+820h+pReportInformation.wzApplicationName]; unsigned __int16 *
0x18001f341  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001f346  mov     r9, r14
0x18001f349  mov     r8, rdi
0x18001f34c  mov     rdx, rbx
0x18001f34f  mov     ecx, 0DDEh; uID
0x18001f354  call    _FormatMessageFromResource
0x18001f359  mov     rbx, rax
0x18001f35c  test    rax, rax
0x18001f35f  jz      short loc_18001F375
0x18001f361  mov     r8, rax; unsigned __int16 *
0x18001f364  lea     rcx, [rbp+820h+pReportInformation.wzDescription]; unsigned __int16 *
0x18001f36b  mov     edx, 200h; unsigned __int64
0x18001f370  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001f375  lea     r9, [rsp+920h+phReportHandle]; phReportHandle
0x18001f37a  xor     edx, edx; repType
0x18001f37c  lea     r8, [rsp+920h+pReportInformation]; pReportInformation
0x18001f381  lea     rcx, pwzEventType; "CertPinning"
0x18001f388  call    cs:__imp_WerReportCreate
0x18001f38e  mov     edi, eax
0x18001f390  test    eax, eax
0x18001f392  js      loc_18001F443
0x18001f398  mov     rcx, [rsp+920h+phReportHandle]; hReportHandle
0x18001f39d  lea     r9, pwzValue; "App2"
0x18001f3a4  lea     r8, pwzName; "ApplicationName"
0x18001f3ab  xor     edx, edx; dwparamID
0x18001f3ad  call    cs:__imp_WerReportSetParameter
0x18001f3b3  mov     rcx, [rsp+920h+phReportHandle]; hReportHandle
0x18001f3b8  lea     r8, aServername; "ServerName"
0x18001f3bf  mov     r9, r12; pwzValue
0x18001f3c2  mov     edx, 1; dwparamID
0x18001f3c7  call    cs:__imp_WerReportSetParameter
0x18001f3cd  mov     rcx, [rsp+920h+phReportHandle]; hReportHandle
0x18001f3d2  lea     r8, aSequencenumber; "SequenceNumber"
0x18001f3d9  mov     edi, 2
0x18001f3de  mov     r9, r13; pwzValue
0x18001f3e1  mov     edx, edi; dwparamID
0x18001f3e3  call    cs:__imp_WerReportSetParameter
0x18001f3e9  mov     rcx, [rsp+920h+phReportHandle]; hReportHandle
0x18001f3ee  lea     r8, aThumbprint; "Thumbprint"
0x18001f3f5  mov     r9, r15; pwzValue
0x18001f3f8  lea     edx, [rdi+1]; dwparamID
0x18001f3fb  call    cs:__imp_WerReportSetParameter
0x18001f401  test    rsi, rsi
0x18001f404  jz      short loc_18001F41B
0x18001f406  mov     rcx, [rsp+920h+phReportHandle]; hReportHandle
0x18001f40b  lea     r8d, [rdi+3]; repFileType
0x18001f40f  mov     r9d, edi; dwFileFlags
0x18001f412  mov     rdx, rsi; pwzPath
0x18001f415  call    cs:__imp_WerReportAddFile
0x18001f41b  mov     rcx, [rsp+920h+phReportHandle]; hReportHandle
0x18001f420  lea     r9, [rsp+920h+pSubmitResult]; pSubmitResult
0x18001f425  mov     r8d, 4; dwFlags
0x18001f42b  mov     edx, edi; consent
0x18001f42d  call    cs:__imp_WerReportSubmit
0x18001f433  mov     edi, eax
0x18001f435  test    rbx, rbx
0x18001f438  jz      short loc_18001F443
0x18001f43a  mov     rcx, rbx; hMem
0x18001f43d  call    cs:__imp_LocalFree
0x18001f443  mov     eax, edi
0x18001f445  mov     rcx, [rbp+820h+var_50]
0x18001f44c  xor     rcx, rsp; StackCookie
0x18001f44f  call    __security_check_cookie
0x18001f454  add     rsp, 8E8h
0x18001f45b  pop     r15
0x18001f45d  pop     r14
0x18001f45f  pop     r13
0x18001f461  pop     r12
0x18001f463  pop     rdi
0x18001f464  pop     rsi
0x18001f465  pop     rbx
0x18001f466  pop     rbp
0x18001f467  retn
```
