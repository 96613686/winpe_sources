# Windows::Internal::WebView::Win32ProcessInfoStatics::GetProcessEnterprisePolicy(ulong,Windows::Internal::WebView::WebViewEnterpriseDataPolicies *)

- ea: `0x180027b10`
- end: `0x180027c7b`
- name: `?GetProcessEnterprisePolicy@Win32ProcessInfoStatics@WebView@Internal@Windows@@UEAAJKPEAW4WebViewEnterpriseDataPolicies@234@@Z`
- size: `363`
- prototype: `int(Windows::Internal::WebView::Win32ProcessInfoStatics *__hidden this, unsigned int, enum Windows::Internal::WebView::WebViewEnterpriseDataPolicies *)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x180027b10`
- `0x180027c84`
- `0x180027d34`
- `0x18007f268`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180027c22`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180027c22`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180027ba8`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180027ba8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027bfd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027c2c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027bfd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027c2c`
- `ntdll!RtlNtStatusToDosError` at `0x180027bc6`
- `ntdll!RtlNtStatusToDosError` at `0x180027bc6`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180027bef`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180027bef`
- `srpapi!SrpGetEnterprisePolicy` at `0x180027c4b`
- `srpapi!SrpGetEnterprisePolicy` at `0x180027c4b`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Internal::WebView::Win32ProcessInfoStatics::GetProcessEnterprisePolicy(
        Windows::Internal::WebView::Win32ProcessInfoStatics *this,
        DWORD a2,
        enum Windows::Internal::WebView::WebViewEnterpriseDataPolicies *a3)
{
  unsigned __int16 **v5; // rdx
  int CallingProcessPackageSidString; // ebx
  __int64 v7; // rdx
  const WCHAR *v8; // rcx
  NTSTATUS EdpEnforcementLevel2; // eax
  signed int v10; // eax
  HANDLE v11; // rdi
  signed int LastError; // eax
  signed int v13; // eax
  int v15; // [rsp+30h] [rbp-38h] BYREF
  void *TokenHandle; // [rsp+38h] [rbp-30h] BYREF
  LPCWCH lpString1; // [rsp+40h] [rbp-28h] BYREF
  __int64 v18; // [rsp+48h] [rbp-20h]
  __int64 v19; // [rsp+50h] [rbp-18h]
  ENTERPRISE_DATA_POLICIES policyFlags; // [rsp+B8h] [rbp+50h] BYREF

  TokenHandle = (void *)-1LL;
  policyFlags = ENTERPRISE_POLICY_NONE;
  lpString1 = 0;
  v18 = 0;
  v19 = 0;
  Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>::_Free(&lpString1);
  v18 = -1;
  v19 = -1;
  CallingProcessPackageSidString = CallerIdentity::GetCallingProcessPackageSidString((LPWSTR *)&lpString1, v5);
  if ( CallingProcessPackageSidString < 0 )
    goto LABEL_25;
  LODWORD(v7) = v18;
  if ( v18 == -1 )
  {
    if ( lpString1 )
    {
      v7 = -1;
      do
        ++v7;
      while ( lpString1[v7] );
    }
    else
    {
      LODWORD(v7) = 0;
    }
  }
  v8 = &LocaleName;
  if ( lpString1 )
    v8 = lpString1;
  if ( CompareStringOrdinal(
         v8,
         v7,
         L"S-1-15-2-1310292540-1029022339-4008023048-2190398717-53961996-4257829345-603366646",
         -1,
         1) != 2 )
  {
    CallingProcessPackageSidString = -2147024891;
    goto LABEL_25;
  }
  v15 = 0;
  EdpEnforcementLevel2 = EdpGetEdpEnforcementLevel2(&v15);
  v10 = RtlNtStatusToDosError(EdpEnforcementLevel2);
  CallingProcessPackageSidString = v10;
  if ( v10 > 0 )
    CallingProcessPackageSidString = (unsigned __int16)v10 | 0x80070000;
  if ( CallingProcessPackageSidString || !v15 )
    goto LABEL_23;
  v11 = OpenProcess(0x400u, 0, a2);
  if ( v11 != (HANDLE)-1LL )
    goto LABEL_28;
  LastError = GetLastError();
  CallingProcessPackageSidString = LastError;
  if ( LastError > 0 )
    CallingProcessPackageSidString = (unsigned __int16)LastError | 0x80070000;
  if ( CallingProcessPackageSidString >= 0 )
  {
LABEL_28:
    if ( !OpenProcessToken(v11, 8u, &TokenHandle) )
    {
      v13 = GetLastError();
      CallingProcessPackageSidString = v13;
      if ( v13 > 0 )
        CallingProcessPackageSidString = (unsigned __int16)v13 | 0x80070000;
      goto LABEL_25;
    }
    CallingProcessPackageSidString = SrpGetEnterprisePolicy(TokenHandle, &policyFlags);
    if ( CallingProcessPackageSidString < 0 )
      goto LABEL_25;
LABEL_23:
    *(_DWORD *)a3 = policyFlags;
  }
LABEL_25:
  Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>::_Free(&lpString1);
  return (unsigned int)CallingProcessPackageSidString;
}

```

## disassembly

```asm
0x180027b10  push    rbp
0x180027b12  push    rbx
0x180027b13  push    rsi
0x180027b14  push    rdi
0x180027b15  push    r14
0x180027b17  push    r15
0x180027b19  mov     rbp, rsp
0x180027b1c  sub     rsp, 68h
0x180027b20  mov     rsi, r8
0x180027b23  mov     edi, edx
0x180027b25  or      r15, 0FFFFFFFFFFFFFFFFh
0x180027b29  mov     [rbp+TokenHandle], r15
0x180027b2d  xor     r14d, r14d
0x180027b30  mov     [rbp+policyFlags], r14d
0x180027b34  mov     [rbp+lpString1], r14
0x180027b38  mov     [rbp+var_20], r14
0x180027b3c  mov     [rbp+var_18], r14
0x180027b40  lea     rcx, [rbp+lpString1]
0x180027b44  call    ?_Free@?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>>::_Free(void)
0x180027b49  mov     [rbp+var_20], r15
0x180027b4d  mov     [rbp+var_18], r15
0x180027b51  lea     rcx, [rbp+lpString1]; StringSid
0x180027b55  call    ?GetCallingProcessPackageSidString@CallerIdentity@@YAJPEAPEAG@Z; CallerIdentity::GetCallingProcessPackageSidString(ushort * *)
0x180027b5a  mov     ebx, eax
0x180027b5c  test    eax, eax
0x180027b5e  js      loc_180027C63
0x180027b64  mov     rdx, [rbp+var_20]
0x180027b68  mov     rax, [rbp+lpString1]
0x180027b6c  cmp     rdx, r15
0x180027b6f  jnz     short loc_180027B88
0x180027b71  test    rax, rax
0x180027b74  jz      short loc_180027B85
0x180027b76  mov     rdx, r15
0x180027b79  inc     rdx
0x180027b7c  cmp     [rax+rdx*2], r14w
0x180027b81  jnz     short loc_180027B79
0x180027b83  jmp     short loc_180027B88
0x180027b85  mov     rdx, r14; cchCount1
0x180027b88  lea     rcx, LocaleName
0x180027b8f  test    rax, rax
0x180027b92  cmovnz  rcx, rax; lpString1
0x180027b96  mov     [rsp+68h+bIgnoreCase], 1; bIgnoreCase
0x180027b9e  mov     r9d, r15d; cchCount2
0x180027ba1  lea     r8, aS1152131029254; "S-1-15-2-1310292540-1029022339-40080230"...
0x180027ba8  call    cs:__imp_CompareStringOrdinal
0x180027bae  cmp     eax, 2
0x180027bb1  jnz     loc_180027C5E
0x180027bb7  mov     [rbp+var_38], r14d
0x180027bbb  lea     rcx, [rbp+var_38]
0x180027bbf  call    EdpGetEdpEnforcementLevel2
0x180027bc4  mov     ecx, eax; Status
0x180027bc6  call    cs:__imp_RtlNtStatusToDosError
0x180027bcc  mov     ebx, eax
0x180027bce  test    eax, eax
0x180027bd0  jle     short loc_180027BDB
0x180027bd2  movzx   ebx, ax
0x180027bd5  or      ebx, 80070000h
0x180027bdb  test    ebx, ebx
0x180027bdd  jnz     short loc_180027C57
0x180027bdf  cmp     [rbp+var_38], r14d
0x180027be3  jz      short loc_180027C57
0x180027be5  mov     r8d, edi; dwProcessId
0x180027be8  xor     edx, edx; bInheritHandle
0x180027bea  mov     ecx, 400h; dwDesiredAccess
0x180027bef  call    cs:__imp_OpenProcess
0x180027bf5  mov     rdi, rax
0x180027bf8  cmp     rax, r15
0x180027bfb  jnz     short loc_180027C16
0x180027bfd  call    cs:__imp_GetLastError
0x180027c03  mov     ebx, eax
0x180027c05  test    eax, eax
0x180027c07  jle     short loc_180027C12
0x180027c09  movzx   ebx, ax
0x180027c0c  or      ebx, 80070000h
0x180027c12  test    ebx, ebx
0x180027c14  js      short loc_180027C63
0x180027c16  lea     r8, [rbp+TokenHandle]; TokenHandle
0x180027c1a  mov     edx, 8; DesiredAccess
0x180027c1f  mov     rcx, rdi; ProcessHandle
0x180027c22  call    cs:__imp_OpenProcessToken
0x180027c28  test    eax, eax
0x180027c2a  jnz     short loc_180027C43
0x180027c2c  call    cs:__imp_GetLastError
0x180027c32  mov     ebx, eax
0x180027c34  test    eax, eax
0x180027c36  jle     short loc_180027C63
0x180027c38  movzx   ebx, ax
0x180027c3b  or      ebx, 80070000h
0x180027c41  jmp     short loc_180027C63
0x180027c43  lea     rdx, [rbp+policyFlags]; policyFlags
0x180027c47  mov     rcx, [rbp+TokenHandle]; tokenHandle
0x180027c4b  call    cs:__imp_SrpGetEnterprisePolicy
0x180027c51  mov     ebx, eax
0x180027c53  test    eax, eax
0x180027c55  js      short loc_180027C63
0x180027c57  mov     eax, [rbp+policyFlags]
0x180027c5a  mov     [rsi], eax
0x180027c5c  jmp     short loc_180027C63
0x180027c5e  mov     ebx, 80070005h
0x180027c63  lea     rcx, [rbp+lpString1]
0x180027c67  call    ?_Free@?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>>::_Free(void)
0x180027c6c  mov     eax, ebx
0x180027c6e  add     rsp, 68h
0x180027c72  pop     r15
0x180027c74  pop     r14
0x180027c76  pop     rdi
0x180027c77  pop     rsi
0x180027c78  pop     rbx
0x180027c79  pop     rbp
0x180027c7a  retn
```
