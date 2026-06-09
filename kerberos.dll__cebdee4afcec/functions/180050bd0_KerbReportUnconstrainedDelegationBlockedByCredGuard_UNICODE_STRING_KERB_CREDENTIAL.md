# KerbReportUnconstrainedDelegationBlockedByCredGuard(_UNICODE_STRING *,_KERB_CREDENTIAL *)

- ea: `0x180050bd0`
- end: `0x180050f67`
- name: `?KerbReportUnconstrainedDelegationBlockedByCredGuard@@YAXPEAU_UNICODE_STRING@@PEAU_KERB_CREDENTIAL@@@Z`
- size: `919`
- prototype: `void __fastcall(struct _UNICODE_STRING *, struct _KERB_CREDENTIAL *)`
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180021574`
- `0x1800cb694`

## callees

- `0x1800087e0`
- `0x180050bd0`
- `0x180070680`
- `0x180070a50`
- `0x18007108c`
- `0x1800744c3`
- `0x1800797c8`
- `0x18008bea0`
- `0x1800938a4`
- `0x1800f5010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180050f08`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180050f08`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180050d6f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180050f48`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180050d6f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180050f48`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180050ca7`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180050ca7`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x180050cc3`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x180050cc3`
- `ntdll!RtlStringFromGUID` at `0x180050e03`
- `ntdll!RtlStringFromGUID` at `0x180050e03`
- `ntdll!RtlFreeUnicodeString` at `0x180050e29`
- `ntdll!RtlFreeUnicodeString` at `0x180050e29`
- `ntdll!EtwEventActivityIdControl` at `0x180050da3`
- `ntdll!EtwEventActivityIdControl` at `0x180050da3`
- `SspiCli!LsaGetLogonSessionData` at `0x180050ce7`
- `SspiCli!LsaGetLogonSessionData` at `0x180050ce7`
- `SspiCli!LsaFreeReturnBuffer` at `0x180050f1f`
- `SspiCli!LsaFreeReturnBuffer` at `0x180050f1f`

## pseudocode

```c
void __fastcall KerbReportUnconstrainedDelegationBlockedByCredGuard(
        struct _UNICODE_STRING *a1,
        struct _KERB_CREDENTIAL *a2)
{
  char v2; // si
  __m128i v4; // xmm6
  __m128i v5; // xmm7
  __m128i *v6; // rax
  LSA_UNICODE_STRING UserName; // xmm8
  LSA_UNICODE_STRING LogonDomain; // xmm9
  char v9; // r14
  HANDLE v10; // rax
  void *v11; // rdi
  void *v12; // rbx
  int v13; // eax
  char LowPart; // r15
  int v15; // ecx
  unsigned __int32 v16; // r9d
  PWSTR Buffer; // r8
  struct _GUID hMem_8; // [rsp+68h] [rbp-A0h] BYREF
  DWORD dwSize[2]; // [rsp+78h] [rbp-90h] BYREF
  struct _LUID LogonId; // [rsp+80h] [rbp-88h] BYREF
  PSECURITY_LOGON_SESSION_DATA ppLogonSessionData; // [rsp+88h] [rbp-80h] BYREF
  void *v22[2]; // [rsp+90h] [rbp-78h] BYREF
  _WORD v23[8]; // [rsp+A0h] [rbp-68h] BYREF
  __int128 v24; // [rsp+B0h] [rbp-58h] BYREF
  struct ASN1objectidentifier_s *v25; // [rsp+C0h] [rbp-48h]
  DWORD dwProcessId[4]; // [rsp+C8h] [rbp-40h] BYREF
  __int128 v27; // [rsp+D8h] [rbp-30h]
  GUID Guid; // [rsp+E8h] [rbp-20h] BYREF
  WCHAR ExeName[264]; // [rsp+F8h] [rbp-10h] BYREF

  v2 = 0;
  v4 = 0;
  v5 = 0;
  dwSize[0] = 0;
  if ( a2 )
  {
    v6 = (__m128i *)*((_QWORD *)a2 + 9);
    if ( v6 )
    {
      v4 = *v6;
      v5 = v6[1];
    }
  }
  LogonId = 0;
  *(_OWORD *)dwProcessId = 0;
  v27 = 0;
  memset_0(ExeName, 0, 0x20Au);
  dwSize[0] = 261;
  UserName = 0;
  ppLogonSessionData = 0;
  LogonDomain = 0;
  if ( ((int (__fastcall *)(DWORD *))LsaFunctions->GetClientInfo)(dwProcessId) < 0 )
  {
    v11 = 0;
    v9 = 0;
  }
  else
  {
    v9 = dwProcessId[2];
    LogonId = *(struct _LUID *)dwProcessId;
    v10 = OpenProcess(0x1000u, 0, dwProcessId[2]);
    v11 = v10;
    if ( v10 && !QueryFullProcessImageNameW(v10, 0, ExeName, dwSize) )
      memset_0(ExeName, 0, 0x105u);
    if ( LsaGetLogonSessionData(&LogonId, &ppLogonSessionData) >= 0 )
    {
      UserName = ppLogonSessionData->UserName;
      LogonDomain = ppLogonSessionData->LogonDomain;
    }
  }
  v25 = 0;
  v12 = 0;
  v24 = 0;
  *(_QWORD *)&hMem_8.Data1 = 0;
  if ( ((unsigned __int8 (__fastcall *)(__int128 *))LsaFunctions->GetCallInfo)(&v24) )
  {
    v13 = KerbOIDToString(v25, (unsigned __int16 **)&hMem_8);
    v12 = *(void **)&hMem_8.Data1;
    if ( !v13 )
    {
      if ( *(_QWORD *)&hMem_8.Data1 )
      {
        if ( KerbGlobalPackageState == 1 )
          ((void (__fastcall *)(_QWORD))LsaFunctions->FreeLsaHeap)(*(_QWORD *)&hMem_8.Data1);
        else
          LocalFree(*(HLOCAL *)&hMem_8.Data1);
        v12 = 0;
      }
    }
  }
  if ( (Microsoft_Windows_Security_KerberosEnableBits & 4) != 0 )
  {
    LowPart = LogonId.LowPart;
    hMem_8 = 0;
    if ( (int)EtwEventActivityIdControl(1, &hMem_8) < 0 || !memcmp_0(&hMem_8, &qword_180109F90, 0x10u) )
      KerbTracerT::SetCorrelationIdGuid(&hMem_8);
    v22[0] = v23;
    Guid = hMem_8;
    v22[1] = v23;
    v23[0] = 0;
    hMem_8 = 0;
    if ( RtlStringFromGUID(&Guid, (PUNICODE_STRING)&hMem_8) >= 0 )
      utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
        v22,
        *(_QWORD *)hMem_8.Data4,
        (unsigned __int64)LOWORD(hMem_8.Data1) >> 1);
    RtlFreeUnicodeString((PUNICODE_STRING)&hMem_8);
    v2 = 3;
    v16 = _mm_srli_si128(v4, 8).m128i_u32[0];
    if ( a1 )
      Buffer = a1->Buffer;
    else
      LODWORD(Buffer) = 0;
    McTemplateU0zzzqzizzzz_EtwEventWriteTransfer(
      v15,
      (unsigned int)UnconstrainedDelegationBlockedByCredGuard,
      (_DWORD)Buffer,
      v16,
      _mm_srli_si128(v5, 8).m128i_i64[0],
      v9,
      (__int64)ExeName,
      LowPart,
      _mm_srli_si128((__m128i)UserName, 8).m128i_i64[0],
      _mm_srli_si128((__m128i)LogonDomain, 8).m128i_i64[0],
      (__int64)v12,
      (__int64)v22[0]);
  }
  if ( (v2 & 1) != 0 && v22[0] != v23 )
    operator delete(v22[0], (const struct std::nothrow_t *)std::nothrow);
  if ( v11 )
    CloseHandle(v11);
  if ( ppLogonSessionData )
    LsaFreeReturnBuffer(ppLogonSessionData);
  if ( v12 )
  {
    if ( KerbGlobalPackageState == 1 )
      ((void (__fastcall *)(void *))LsaFunctions->FreeLsaHeap)(v12);
    else
      LocalFree(v12);
  }
}

```

## disassembly

```asm
0x180050bd0  mov     r11, rsp
0x180050bd3  push    rbp
0x180050bd4  push    rbx
0x180050bd5  lea     rbp, [r11-278h]
0x180050bdc  sub     rsp, 368h
0x180050be3  mov     rax, cs:__security_cookie
0x180050bea  xor     rax, rsp
0x180050bed  mov     [rbp+270h+var_70], rax
0x180050bf4  mov     [r11+18h], rsi
0x180050bf8  xor     esi, esi
0x180050bfa  mov     [r11+20h], rdi
0x180050bfe  mov     [r11-18h], r13
0x180050c02  mov     r13, rcx
0x180050c05  movaps  xmmword ptr [r11-38h], xmm6
0x180050c0a  xorps   xmm6, xmm6
0x180050c0d  movaps  xmmword ptr [r11-48h], xmm7
0x180050c12  xorps   xmm7, xmm7
0x180050c15  movaps  xmmword ptr [r11-58h], xmm8
0x180050c1a  movaps  xmmword ptr [r11-68h], xmm9
0x180050c1f  mov     [rsp+370h+dwSize], esi
0x180050c23  test    rdx, rdx
0x180050c26  jz      short loc_180050C38
0x180050c28  mov     rax, [rdx+48h]
0x180050c2c  test    rax, rax
0x180050c2f  jz      short loc_180050C38
0x180050c31  movups  xmm6, xmmword ptr [rax]
0x180050c34  movups  xmm7, xmmword ptr [rax+10h]
0x180050c38  xorps   xmm0, xmm0
0x180050c3b  mov     [rsp+370h+var_18], r14
0x180050c43  xor     edx, edx; Val
0x180050c45  mov     qword ptr [rsp+370h+LogonId.LowPart], rsi
0x180050c4a  mov     r8d, 20Ah; Size
0x180050c50  lea     rcx, [rbp+270h+ExeName]; void *
0x180050c54  movups  xmmword ptr [rbp+270h+dwProcessId], xmm0
0x180050c58  movups  [rbp+270h+var_2A0], xmm0
0x180050c5c  call    memset_0
0x180050c61  mov     rax, cs:?LsaFunctions@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * LsaFunctions
0x180050c68  lea     rcx, [rbp+270h+dwProcessId]
0x180050c6c  mov     [rsp+370h+dwSize], 105h
0x180050c74  xorps   xmm8, xmm8
0x180050c78  mov     [rbp+270h+ppLogonSessionData], rsi
0x180050c7c  xorps   xmm9, xmm9
0x180050c80  mov     rax, [rax+80h]
0x180050c87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050c8c  test    eax, eax
0x180050c8e  js      short loc_180050D01
0x180050c90  mov     r14d, [rbp+270h+dwProcessId+8]
0x180050c94  xor     edx, edx; bInheritHandle
0x180050c96  mov     rax, qword ptr [rbp+270h+dwProcessId]
0x180050c9a  mov     r8d, r14d; dwProcessId
0x180050c9d  mov     ecx, 1000h; dwDesiredAccess
0x180050ca2  mov     qword ptr [rsp+370h+LogonId.LowPart], rax
0x180050ca7  call    cs:__imp_OpenProcess
0x180050cad  mov     rdi, rax
0x180050cb0  test    rax, rax
0x180050cb3  jz      short loc_180050CDE
0x180050cb5  lea     r9, [rsp+370h+dwSize]; lpdwSize
0x180050cba  xor     edx, edx; dwFlags
0x180050cbc  lea     r8, [rbp+270h+ExeName]; lpExeName
0x180050cc0  mov     rcx, rax; hProcess
0x180050cc3  call    cs:__imp_QueryFullProcessImageNameW
0x180050cc9  test    eax, eax
0x180050ccb  jnz     short loc_180050CDE
0x180050ccd  xor     edx, edx; Val
0x180050ccf  lea     rcx, [rbp+270h+ExeName]; void *
0x180050cd3  mov     r8d, 105h; Size
0x180050cd9  call    memset_0
0x180050cde  lea     rdx, [rbp+270h+ppLogonSessionData]; ppLogonSessionData
0x180050ce2  lea     rcx, [rsp+370h+LogonId]; LogonId
0x180050ce7  call    cs:__imp_LsaGetLogonSessionData
0x180050ced  test    eax, eax
0x180050cef  js      short loc_180050D06
0x180050cf1  mov     rax, [rbp+270h+ppLogonSessionData]
0x180050cf5  movups  xmm8, xmmword ptr [rax+10h]
0x180050cfa  movups  xmm9, xmmword ptr [rax+20h]
0x180050cff  jmp     short loc_180050D06
0x180050d01  xor     edi, edi
0x180050d03  xor     r14d, r14d
0x180050d06  xor     eax, eax
0x180050d08  lea     rcx, [rbp+270h+var_2C8]
0x180050d0c  mov     [rbp+270h+var_2B8], rax
0x180050d10  xorps   xmm0, xmm0
0x180050d13  mov     rax, cs:?LsaFunctions@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * LsaFunctions
0x180050d1a  xor     ebx, ebx
0x180050d1c  movups  [rbp+270h+var_2C8], xmm0
0x180050d20  mov     [rsp+370h+hMem+8], rbx
0x180050d25  mov     rax, [rax+0C0h]
0x180050d2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050d31  test    al, al
0x180050d33  jz      short loc_180050D77
0x180050d35  mov     rcx, [rbp+270h+var_2B8]; struct ASN1objectidentifier_s *
0x180050d39  lea     rdx, [rsp+370h+hMem+8]; unsigned __int16 **
0x180050d3e  call    ?KerbOIDToString@@YAHPEAUASN1objectidentifier_s@@PEAPEAG@Z; KerbOIDToString(ASN1objectidentifier_s *,ushort * *)
0x180050d43  mov     rbx, [rsp+370h+hMem+8]
0x180050d48  test    eax, eax
0x180050d4a  jnz     short loc_180050D77
0x180050d4c  test    rbx, rbx
0x180050d4f  jz      short loc_180050D77
0x180050d51  cmp     cs:?KerbGlobalPackageState@@3W4KerberosState@@A, 1; KerberosState KerbGlobalPackageState
0x180050d58  mov     rcx, rbx; hMem
0x180050d5b  jnz     short loc_180050D6F
0x180050d5d  mov     rax, cs:?LsaFunctions@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * LsaFunctions
0x180050d64  mov     rax, [rax+30h]
0x180050d68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050d6d  jmp     short loc_180050D75
0x180050d6f  call    cs:__imp_LocalFree
0x180050d75  xor     ebx, ebx
0x180050d77  test    cs:Microsoft_Windows_Security_KerberosEnableBits, 4
0x180050d7e  jz      loc_180050EA7
0x180050d84  xorps   xmm0, xmm0
0x180050d87  mov     [rsp+370h+var_20], r15
0x180050d8f  mov     r15, qword ptr [rsp+370h+LogonId.LowPart]
0x180050d94  lea     rdx, [rsp+370h+hMem+8]
0x180050d99  mov     ecx, 1
0x180050d9e  movups  xmmword ptr [rsp+370h+hMem+8], xmm0
0x180050da3  call    cs:__imp_EtwEventActivityIdControl
0x180050da9  test    eax, eax
0x180050dab  js      short loc_180050DC8
0x180050dad  mov     r8d, 10h; Size
0x180050db3  lea     rdx, qword_180109F90; Buf2
0x180050dba  lea     rcx, [rsp+370h+hMem+8]; Buf1
0x180050dbf  call    memcmp_0
0x180050dc4  test    eax, eax
0x180050dc6  jnz     short loc_180050DD2
0x180050dc8  lea     rcx, [rsp+370h+hMem+8]; struct _GUID *
0x180050dcd  call    ?SetCorrelationIdGuid@KerbTracerT@@SAXAEAU_GUID@@@Z; KerbTracerT::SetCorrelationIdGuid(_GUID &)
0x180050dd2  movaps  xmm0, xmmword ptr [rsp+370h+hMem+8]
0x180050dd7  lea     rax, [rbp+270h+var_2D8]
0x180050ddb  mov     [rbp+270h+var_2E8], rax
0x180050ddf  lea     rdx, [rsp+370h+hMem+8]; GuidString
0x180050de4  lea     rax, [rbp+270h+var_2D8]
0x180050de8  movdqa  xmmword ptr [rbp+270h+Guid.Data1], xmm0
0x180050ded  mov     [rbp+270h+var_2E0], rax
0x180050df1  lea     rcx, [rbp+270h+Guid]; Guid
0x180050df5  xor     eax, eax
0x180050df7  xorps   xmm0, xmm0
0x180050dfa  mov     [rbp+270h+var_2D8], ax
0x180050dfe  movups  xmmword ptr [rsp+370h+hMem+8], xmm0
0x180050e03  call    cs:__imp_RtlStringFromGUID
0x180050e09  test    eax, eax
0x180050e0b  js      short loc_180050E24
0x180050e0d  movzx   r8d, word ptr [rsp+370h+hMem+8]
0x180050e13  lea     rcx, [rbp+270h+var_2E8]
0x180050e17  mov     rdx, qword ptr [rsp+370h+var_308]
0x180050e1c  shr     r8, 1
0x180050e1f  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x180050e24  lea     rcx, [rsp+370h+hMem+8]; UnicodeString
0x180050e29  call    cs:__imp_RtlFreeUnicodeString
0x180050e2f  mov     rax, [rbp+270h+var_2E8]
0x180050e33  mov     esi, 3
0x180050e38  psrldq  xmm6, 8
0x180050e3d  movq    r9, xmm6
0x180050e42  test    r13, r13
0x180050e45  jz      short loc_180050E4D
0x180050e47  mov     r8, [r13+8]
0x180050e4b  jmp     short loc_180050E50
0x180050e4d  xor     r8d, r8d
0x180050e50  mov     [rsp+370h+hMem], rax
0x180050e55  lea     rdx, UnconstrainedDelegationBlockedByCredGuard
0x180050e5c  mov     [rsp+370h+var_320], rbx
0x180050e61  lea     rax, [rbp+270h+ExeName]
0x180050e65  psrldq  xmm9, 8
0x180050e6b  movq    [rsp+370h+var_328], xmm9
0x180050e72  psrldq  xmm8, 8
0x180050e78  movq    [rsp+370h+var_330], xmm8
0x180050e7f  mov     [rsp+370h+var_338], r15
0x180050e84  mov     [rsp+370h+var_340], rax
0x180050e89  psrldq  xmm7, 8
0x180050e8e  mov     dword ptr [rsp+370h+var_348], r14d
0x180050e93  movq    qword ptr [rsp+370h+var_350], xmm7
0x180050e9a  call    McTemplateU0zzzqzizzzz_EtwEventWriteTransfer
0x180050e9f  mov     r15, [rsp+370h+var_20]
0x180050ea7  movaps  xmm9, [rsp+370h+var_68+8]
0x180050eb0  test    sil, 1
0x180050eb4  mov     rsi, [rsp+370h+arg_10]
0x180050ebc  movaps  xmm8, [rsp+370h+var_58+8]
0x180050ec5  movaps  xmm7, [rsp+370h+var_48+8]
0x180050ecd  movaps  xmm6, [rsp+370h+var_38+8]
0x180050ed5  mov     r14, [rsp+370h+var_18]
0x180050edd  mov     r13, [rsp+360h]
0x180050ee5  jz      short loc_180050F00
0x180050ee7  mov     rcx, [rbp+270h+var_2E8]; void *
0x180050eeb  lea     rax, [rbp+270h+var_2D8]
0x180050eef  cmp     rcx, rax
0x180050ef2  jz      short loc_180050F00
0x180050ef4  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180050efb  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180050f00  test    rdi, rdi
0x180050f03  jz      short loc_180050F0E
0x180050f05  mov     rcx, rdi; hObject
0x180050f08  call    cs:__imp_CloseHandle
0x180050f0e  mov     rcx, [rbp+270h+ppLogonSessionData]; Buffer
0x180050f12  mov     rdi, [rsp+370h+arg_18]
0x180050f1a  test    rcx, rcx
0x180050f1d  jz      short loc_180050F25
0x180050f1f  call    cs:__imp_LsaFreeReturnBuffer
0x180050f25  test    rbx, rbx
0x180050f28  jz      short loc_180050F4E
0x180050f2a  cmp     cs:?KerbGlobalPackageState@@3W4KerberosState@@A, 1; KerberosState KerbGlobalPackageState
0x180050f31  mov     rcx, rbx; hMem
0x180050f34  jnz     short loc_180050F48
0x180050f36  mov     rax, cs:?LsaFunctions@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * LsaFunctions
0x180050f3d  mov     rax, [rax+30h]
0x180050f41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050f46  jmp     short loc_180050F4E
0x180050f48  call    cs:__imp_LocalFree
0x180050f4e  mov     rcx, [rbp+270h+var_70]
0x180050f55  xor     rcx, rsp; StackCookie
0x180050f58  call    __security_check_cookie
0x180050f5d  add     rsp, 368h
0x180050f64  pop     rbx
0x180050f65  pop     rbp
0x180050f66  retn
```
