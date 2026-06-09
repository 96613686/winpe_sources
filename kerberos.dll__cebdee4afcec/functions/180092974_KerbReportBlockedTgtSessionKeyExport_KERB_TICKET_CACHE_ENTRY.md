# KerbReportBlockedTgtSessionKeyExport(_KERB_TICKET_CACHE_ENTRY *)

- ea: `0x180092974`
- end: `0x180092c1e`
- name: `?KerbReportBlockedTgtSessionKeyExport@@YAXPEAU_KERB_TICKET_CACHE_ENTRY@@@Z`
- size: `682`
- prototype: `void __fastcall(struct _KERB_TICKET_CACHE_ENTRY *)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180009fe4`

## callees

- `0x1800068d0`
- `0x1800069a0`
- `0x1800087e0`
- `0x1800163a0`
- `0x180065c48`
- `0x180070680`
- `0x18007108c`
- `0x18008b2f4`
- `0x180092974`
- `0x1800938a4`
- `0x1800f5010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180092bc9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180092bc9`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180092a78`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180092a78`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x180092a94`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x180092a94`
- `SspiCli!LsaGetLogonSessionData` at `0x180092ab6`
- `SspiCli!LsaGetLogonSessionData` at `0x180092ab6`
- `SspiCli!LsaFreeReturnBuffer` at `0x180092bd9`
- `SspiCli!LsaFreeReturnBuffer` at `0x180092bd9`

## pseudocode

```c
void __fastcall KerbReportBlockedTgtSessionKeyExport(struct _KERB_INTERNAL_NAME **a1)
{
  char v1; // r14
  __m128i v3; // xmm6
  LSA_UNICODE_STRING UserName; // xmm7
  LSA_UNICODE_STRING LogonDomain; // xmm8
  char v6; // r15
  HANDLE v7; // rax
  void *v8; // rsi
  unsigned __int16 *v9; // rdi
  int v10; // eax
  char LowPart; // bl
  __int64 *CorrelationId; // rax
  int v13; // ecx
  DWORD dwSize[2]; // [rsp+68h] [rbp-A0h] BYREF
  unsigned __int16 *v15; // [rsp+70h] [rbp-98h] BYREF
  struct _LUID LogonId; // [rsp+78h] [rbp-90h] BYREF
  PSECURITY_LOGON_SESSION_DATA ppLogonSessionData; // [rsp+80h] [rbp-88h] BYREF
  struct _UNICODE_STRING v18; // [rsp+88h] [rbp-80h] BYREF
  struct _UNICODE_STRING v19; // [rsp+98h] [rbp-70h] BYREF
  __int128 v20; // [rsp+A8h] [rbp-60h] BYREF
  struct ASN1objectidentifier_s *v21; // [rsp+B8h] [rbp-50h]
  DWORD dwProcessId[4]; // [rsp+C0h] [rbp-48h] BYREF
  __int128 v23; // [rsp+D0h] [rbp-38h]
  _BYTE v24[40]; // [rsp+E0h] [rbp-28h] BYREF
  WCHAR ExeName[264]; // [rsp+108h] [rbp+0h] BYREF

  v1 = 0;
  dwSize[0] = 0;
  v3 = 0;
  v18 = 0;
  v19 = 0;
  if ( a1 )
  {
    if ( (unsigned int)KerbConvertKdcNameToString(&v18, a1[5], 0) )
      KerbFreeString((__int64)&v18);
    if ( (unsigned int)KerbConvertKdcNameToString(&v19, a1[18], 0) )
      KerbFreeString((__int64)&v19);
    v3 = *((__m128i *)a1 + 8);
  }
  LogonId = 0;
  *(_OWORD *)dwProcessId = 0;
  v23 = 0;
  memset_0(ExeName, 0, 0x20Au);
  ppLogonSessionData = 0;
  dwSize[0] = 261;
  UserName = 0;
  LogonDomain = 0;
  if ( ((int (__fastcall *)(DWORD *))LsaFunctions->GetClientInfo)(dwProcessId) < 0 )
  {
    v8 = 0;
    v6 = 0;
  }
  else
  {
    v6 = dwProcessId[2];
    LogonId = *(struct _LUID *)dwProcessId;
    v7 = OpenProcess(0x1000u, 0, dwProcessId[2]);
    v8 = v7;
    if ( v7 && !QueryFullProcessImageNameW(v7, 0, ExeName, dwSize) )
      memset_0(ExeName, 0, 0x105u);
    if ( LsaGetLogonSessionData(&LogonId, &ppLogonSessionData) >= 0 )
    {
      UserName = ppLogonSessionData->UserName;
      LogonDomain = ppLogonSessionData->LogonDomain;
    }
  }
  v21 = 0;
  v9 = 0;
  v20 = 0;
  v15 = 0;
  if ( ((unsigned __int8 (__fastcall *)(__int128 *))LsaFunctions->GetCallInfo)(&v20) )
  {
    v10 = KerbOIDToString(v21, &v15);
    v9 = v15;
    if ( !v10 )
    {
      if ( v15 )
      {
        KerbFree(v15);
        v9 = 0;
      }
    }
  }
  if ( (Microsoft_Windows_Security_KerberosEnableBits & 4) != 0 )
  {
    LowPart = LogonId.LowPart;
    CorrelationId = (__int64 *)KerbTracerT::GetCorrelationId(v24);
    v1 = 1;
    McTemplateU0zzzqzizzzz_EtwEventWriteTransfer(
      v13,
      (unsigned int)TgtSessionKeyExportBlockedByCredGuard,
      v18.Buffer,
      v19.Buffer,
      _mm_srli_si128(v3, 8).m128i_i64[0],
      v6,
      (__int64)ExeName,
      LowPart,
      _mm_srli_si128((__m128i)UserName, 8).m128i_i64[0],
      _mm_srli_si128((__m128i)LogonDomain, 8).m128i_i64[0],
      (__int64)v9,
      *CorrelationId);
  }
  if ( (v1 & 1) != 0 )
    utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v24);
  KerbFreeString((__int64)&v18);
  KerbFreeString((__int64)&v19);
  if ( v8 )
    CloseHandle(v8);
  if ( ppLogonSessionData )
    LsaFreeReturnBuffer(ppLogonSessionData);
  if ( v9 )
    KerbFree(v9);
}

```

## disassembly

```asm
0x180092974  mov     rax, rsp
0x180092977  push    rbp
0x180092978  push    rbx
0x180092979  push    rsi
0x18009297a  push    rdi
0x18009297b  push    r14
0x18009297d  push    r15
0x18009297f  lea     rbp, [rax-288h]
0x180092986  sub     rsp, 358h
0x18009298d  movaps  xmmword ptr [rax-48h], xmm6
0x180092991  movaps  xmmword ptr [rax-58h], xmm7
0x180092995  movaps  xmmword ptr [rax-68h], xmm8
0x18009299a  mov     rax, cs:__security_cookie
0x1800929a1  xor     rax, rsp
0x1800929a4  mov     [rbp+280h+var_70], rax
0x1800929ab  xor     r14d, r14d
0x1800929ae  xorps   xmm0, xmm0
0x1800929b1  mov     [rsp+380h+dwSize], r14d
0x1800929b6  xorps   xmm1, xmm1
0x1800929b9  mov     rbx, rcx
0x1800929bc  xorps   xmm6, xmm6
0x1800929bf  movups  xmmword ptr [rbp+280h+var_300.Length], xmm0
0x1800929c3  movups  xmmword ptr [rbp+280h+var_2F0.Length], xmm1
0x1800929c7  test    rcx, rcx
0x1800929ca  jz      short loc_180092A10
0x1800929cc  mov     rdx, [rcx+28h]; struct _KERB_INTERNAL_NAME *
0x1800929d0  xor     r8d, r8d; struct _UNICODE_STRING *
0x1800929d3  lea     rcx, [rbp+280h+var_300]; struct _UNICODE_STRING *
0x1800929d7  call    ?KerbConvertKdcNameToString@@YAJPEAU_UNICODE_STRING@@PEAU_KERB_INTERNAL_NAME@@0@Z; KerbConvertKdcNameToString(_UNICODE_STRING *,_KERB_INTERNAL_NAME *,_UNICODE_STRING *)
0x1800929dc  test    eax, eax
0x1800929de  jz      short loc_1800929E9
0x1800929e0  lea     rcx, [rbp+280h+var_300]
0x1800929e4  call    KerbFreeString
0x1800929e9  mov     rdx, [rbx+90h]; struct _KERB_INTERNAL_NAME *
0x1800929f0  lea     rcx, [rbp+280h+var_2F0]; struct _UNICODE_STRING *
0x1800929f4  xor     r8d, r8d; struct _UNICODE_STRING *
0x1800929f7  call    ?KerbConvertKdcNameToString@@YAJPEAU_UNICODE_STRING@@PEAU_KERB_INTERNAL_NAME@@0@Z; KerbConvertKdcNameToString(_UNICODE_STRING *,_KERB_INTERNAL_NAME *,_UNICODE_STRING *)
0x1800929fc  test    eax, eax
0x1800929fe  jz      short loc_180092A09
0x180092a00  lea     rcx, [rbp+280h+var_2F0]
0x180092a04  call    KerbFreeString
0x180092a09  movups  xmm6, xmmword ptr [rbx+80h]
0x180092a10  xorps   xmm0, xmm0
0x180092a13  mov     qword ptr [rsp+380h+LogonId.LowPart], r14
0x180092a18  xor     edx, edx; Val
0x180092a1a  lea     rcx, [rbp+280h+ExeName]; void *
0x180092a1e  mov     r8d, 20Ah; Size
0x180092a24  movups  xmmword ptr [rbp+280h+dwProcessId], xmm0
0x180092a28  movups  [rbp+280h+var_2B8], xmm0
0x180092a2c  call    memset_0
0x180092a31  mov     rax, cs:?LsaFunctions@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * LsaFunctions
0x180092a38  lea     rcx, [rbp+280h+dwProcessId]
0x180092a3c  mov     [rsp+380h+ppLogonSessionData], r14
0x180092a41  mov     ebx, 105h
0x180092a46  mov     [rsp+380h+dwSize], ebx
0x180092a4a  xorps   xmm7, xmm7
0x180092a4d  xorps   xmm8, xmm8
0x180092a51  mov     rax, [rax+80h]
0x180092a58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180092a5d  test    eax, eax
0x180092a5f  js      short loc_180092AD0
0x180092a61  mov     r15d, [rbp+280h+dwProcessId+8]
0x180092a65  xor     edx, edx; bInheritHandle
0x180092a67  mov     rax, qword ptr [rbp+280h+dwProcessId]
0x180092a6b  mov     r8d, r15d; dwProcessId
0x180092a6e  mov     ecx, 1000h; dwDesiredAccess
0x180092a73  mov     qword ptr [rsp+380h+LogonId.LowPart], rax
0x180092a78  call    cs:__imp_OpenProcess
0x180092a7e  mov     rsi, rax
0x180092a81  test    rax, rax
0x180092a84  jz      short loc_180092AAC
0x180092a86  lea     r9, [rsp+380h+dwSize]; lpdwSize
0x180092a8b  xor     edx, edx; dwFlags
0x180092a8d  lea     r8, [rbp+280h+ExeName]; lpExeName
0x180092a91  mov     rcx, rax; hProcess
0x180092a94  call    cs:__imp_QueryFullProcessImageNameW
0x180092a9a  test    eax, eax
0x180092a9c  jnz     short loc_180092AAC
0x180092a9e  mov     r8d, ebx; Size
0x180092aa1  lea     rcx, [rbp+280h+ExeName]; void *
0x180092aa5  xor     edx, edx; Val
0x180092aa7  call    memset_0
0x180092aac  lea     rdx, [rsp+380h+ppLogonSessionData]; ppLogonSessionData
0x180092ab1  lea     rcx, [rsp+380h+LogonId]; LogonId
0x180092ab6  call    cs:__imp_LsaGetLogonSessionData
0x180092abc  test    eax, eax
0x180092abe  js      short loc_180092AD5
0x180092ac0  mov     rax, [rsp+380h+ppLogonSessionData]
0x180092ac5  movups  xmm7, xmmword ptr [rax+10h]
0x180092ac9  movups  xmm8, xmmword ptr [rax+20h]
0x180092ace  jmp     short loc_180092AD5
0x180092ad0  xor     esi, esi
0x180092ad2  xor     r15d, r15d
0x180092ad5  xor     eax, eax
0x180092ad7  lea     rcx, [rbp+280h+var_2E0]
0x180092adb  mov     [rbp+280h+var_2D0], rax
0x180092adf  xorps   xmm0, xmm0
0x180092ae2  mov     rax, cs:?LsaFunctions@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * LsaFunctions
0x180092ae9  xor     edi, edi
0x180092aeb  movups  [rbp+280h+var_2E0], xmm0
0x180092aef  mov     [rsp+380h+var_318], rdi
0x180092af4  mov     rax, [rax+0C0h]
0x180092afb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180092b00  test    al, al
0x180092b02  jz      short loc_180092B2A
0x180092b04  mov     rcx, [rbp+280h+var_2D0]; struct ASN1objectidentifier_s *
0x180092b08  lea     rdx, [rsp+380h+var_318]; unsigned __int16 **
0x180092b0d  call    ?KerbOIDToString@@YAHPEAUASN1objectidentifier_s@@PEAPEAG@Z; KerbOIDToString(ASN1objectidentifier_s *,ushort * *)
0x180092b12  mov     rdi, [rsp+380h+var_318]
0x180092b17  test    eax, eax
0x180092b19  jnz     short loc_180092B2A
0x180092b1b  test    rdi, rdi
0x180092b1e  jz      short loc_180092B2A
0x180092b20  mov     rcx, rdi
0x180092b23  call    KerbFree
0x180092b28  xor     edi, edi
0x180092b2a  test    cs:Microsoft_Windows_Security_KerberosEnableBits, 4
0x180092b31  jz      short loc_180092BA0
0x180092b33  mov     rbx, qword ptr [rsp+380h+LogonId.LowPart]
0x180092b38  lea     rcx, [rbp+280h+var_2A8]
0x180092b3c  call    ?GetCorrelationId@KerbTracerT@@SA?BV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@XZ; KerbTracerT::GetCorrelationId(void)
0x180092b41  mov     r9, [rbp+280h+var_2F0.Buffer]
0x180092b45  lea     rdx, TgtSessionKeyExportBlockedByCredGuard
0x180092b4c  mov     r8, [rbp+280h+var_300.Buffer]
0x180092b50  mov     r14d, 1
0x180092b56  psrldq  xmm8, 8
0x180092b5c  mov     rax, [rax]
0x180092b5f  mov     qword ptr [rsp+380h+var_328], rax
0x180092b64  lea     rax, [rbp+280h+ExeName]
0x180092b68  mov     [rsp+380h+var_330], rdi
0x180092b6d  movq    [rsp+380h+var_338], xmm8
0x180092b74  psrldq  xmm7, 8
0x180092b79  movq    [rsp+380h+var_340], xmm7
0x180092b80  mov     [rsp+380h+var_348], rbx
0x180092b85  mov     [rsp+380h+var_350], rax
0x180092b8a  psrldq  xmm6, 8
0x180092b8f  mov     dword ptr [rsp+380h+var_358], r15d
0x180092b94  movq    qword ptr [rsp+380h+var_360], xmm6
0x180092b9b  call    McTemplateU0zzzqzizzzz_EtwEventWriteTransfer
0x180092ba0  test    r14b, 1
0x180092ba4  jz      short loc_180092BAF
0x180092ba6  lea     rcx, [rbp+280h+var_2A8]
0x180092baa  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x180092baf  lea     rcx, [rbp+280h+var_300]
0x180092bb3  call    KerbFreeString
0x180092bb8  lea     rcx, [rbp+280h+var_2F0]
0x180092bbc  call    KerbFreeString
0x180092bc1  test    rsi, rsi
0x180092bc4  jz      short loc_180092BCF
0x180092bc6  mov     rcx, rsi; hObject
0x180092bc9  call    cs:__imp_CloseHandle
0x180092bcf  mov     rcx, [rsp+380h+ppLogonSessionData]; Buffer
0x180092bd4  test    rcx, rcx
0x180092bd7  jz      short loc_180092BDF
0x180092bd9  call    cs:__imp_LsaFreeReturnBuffer
0x180092bdf  test    rdi, rdi
0x180092be2  jz      short loc_180092BEC
0x180092be4  mov     rcx, rdi
0x180092be7  call    KerbFree
0x180092bec  mov     rcx, [rbp+280h+var_70]
0x180092bf3  xor     rcx, rsp; StackCookie
0x180092bf6  call    __security_check_cookie
0x180092bfb  lea     r11, [rsp+380h+var_28]
0x180092c03  movaps  xmm6, xmmword ptr [r11-18h]
0x180092c08  movaps  xmm7, xmmword ptr [r11-28h]
0x180092c0d  movaps  xmm8, xmmword ptr [r11-38h]
0x180092c12  mov     rsp, r11
0x180092c15  pop     r15
0x180092c17  pop     r14
0x180092c19  pop     rdi
0x180092c1a  pop     rsi
0x180092c1b  pop     rbx
0x180092c1c  pop     rbp
0x180092c1d  retn
```
