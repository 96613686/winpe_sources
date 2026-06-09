# GetPinForSingleCert(_CREDUI_INFOW *,_EAPTLS_USER_PROPERTIES *,ulong,uchar * *,ulong *)

- ea: `0x180074a84`
- end: `0x180074c2e`
- name: `?GetPinForSingleCert@@YAKPEAU_CREDUI_INFOW@@PEAU_EAPTLS_USER_PROPERTIES@@KPEAPEAEPEAK@Z`
- size: `426`
- prototype: `unsigned int __fastcall(struct _CREDUI_INFOW *, struct _EAPTLS_USER_PROPERTIES *, unsigned int, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x180074f94`

## callees

- `0x180005010`
- `0x180007d00`
- `0x180038270`
- `0x180039540`
- `0x180074a84`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180074b31`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180074b31`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180074be4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180074be4`
- `api-ms-win-security-credentials-l1-1-0!CredFree` at `0x180074c06`
- `api-ms-win-security-credentials-l1-1-0!CredFree` at `0x180074c06`
- `api-ms-win-security-credentials-l1-1-0!CredMarshalCredentialW` at `0x180074b1a`
- `api-ms-win-security-credentials-l1-1-0!CredMarshalCredentialW` at `0x180074b1a`
- `ext-ms-win-rastlsext-eap-l1-1-0!RasTlsExt_GetPinUserBlob` at `0x180074b87`
- `ext-ms-win-rastlsext-eap-l1-1-0!RasTlsExt_GetPinUserBlob` at `0x180074b87`

## pseudocode

```c
__int64 __fastcall GetPinForSingleCert(
        struct _CREDUI_INFOW *a1,
        struct _EAPTLS_USER_PROPERTIES *a2,
        unsigned int a3,
        LPVOID *a4,
        unsigned int *a5)
{
  int v9; // eax
  DWORD LastError; // ebx
  _BYTE *v11; // rax
  __int64 v12; // rcx
  LPWSTR MarshaledCredential; // [rsp+30h] [rbp-38h] BYREF
  _BYTE Credential[24]; // [rsp+38h] [rbp-30h] BYREF

  memset(Credential, 0, sizeof(Credential));
  MarshaledCredential = 0;
  if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 51, &WPP_c4e812f99669349517681909258710e2_Traceguids);
  memset(Credential, 0, sizeof(Credential));
  v9 = *((_DWORD *)a2 + 9);
  *(_OWORD *)&Credential[4] = *(_OWORD *)((char *)a2 + 20);
  *(_DWORD *)Credential = 24;
  *(_DWORD *)&Credential[20] = v9;
  if ( !CredMarshalCredentialW(CertCredential, Credential, &MarshaledCredential) && !MarshaledCredential )
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 52, &WPP_c4e812f99669349517681909258710e2_Traceguids, LastError);
LABEL_9:
    if ( !LastError )
      goto LABEL_17;
    goto LABEL_13;
  }
  if ( (unsigned __int8)IsRasTlsExt_GetPinUserBlobPresent() )
  {
    LastError = RasTlsExt_GetPinUserBlob(a1, a3, MarshaledCredential, a4, a5);
    goto LABEL_9;
  }
  LastError = 120;
  if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 53, &WPP_c4e812f99669349517681909258710e2_Traceguids);
LABEL_13:
  v11 = *a4;
  if ( *a4 )
  {
    v12 = *a5;
    if ( *a5 )
    {
      do
      {
        *v11++ = 0;
        --v12;
      }
      while ( v12 );
    }
    CoTaskMemFree(*a4);
    *a4 = 0;
    *a5 = 0;
  }
LABEL_17:
  if ( MarshaledCredential )
    CredFree(MarshaledCredential);
  return LastError;
}

```

## disassembly

```asm
0x180074a84  push    rbp
0x180074a86  push    rbx
0x180074a87  push    rsi
0x180074a88  push    rdi
0x180074a89  push    r14
0x180074a8b  push    r15
0x180074a8d  mov     rbp, rsp
0x180074a90  sub     rsp, 68h
0x180074a94  mov     rax, cs:__security_cookie
0x180074a9b  xor     rax, rsp
0x180074a9e  mov     [rbp+var_18], rax
0x180074aa2  mov     rsi, [rbp+arg_20]
0x180074aa6  xor     eax, eax
0x180074aa8  xorps   xmm0, xmm0
0x180074aab  mov     [rbp+var_20], rax
0x180074aaf  movups  [rbp+Credential], xmm0
0x180074ab3  mov     [rbp+MarshaledCredential], rax
0x180074ab7  mov     rdi, r9
0x180074aba  mov     r15d, r8d
0x180074abd  mov     rbx, rdx
0x180074ac0  mov     r14, rcx
0x180074ac3  mov     rcx, cs:WPP_GLOBAL_Control
0x180074aca  lea     rax, WPP_GLOBAL_Control
0x180074ad1  cmp     rcx, rax
0x180074ad4  jz      short loc_180074AEB
0x180074ad6  mov     rcx, [rcx+10h]
0x180074ada  lea     r8, WPP_c4e812f99669349517681909258710e2_Traceguids
0x180074ae1  mov     edx, 33h ; '3'
0x180074ae6  call    WPP_SF_
0x180074aeb  xorps   xmm0, xmm0
0x180074aee  lea     r8, [rbp+MarshaledCredential]; MarshaledCredential
0x180074af2  movups  [rbp+Credential], xmm0
0x180074af6  xor     eax, eax
0x180074af8  lea     rdx, [rbp+Credential]; Credential
0x180074afc  movups  xmm0, xmmword ptr [rbx+14h]
0x180074b00  mov     [rbp+var_20], rax
0x180074b04  mov     ecx, 1; CredType
0x180074b09  mov     eax, [rbx+24h]
0x180074b0c  movups  [rbp+Credential+4], xmm0
0x180074b10  mov     dword ptr [rbp+Credential], 18h
0x180074b17  mov     dword ptr [rbp+var_20+4], eax
0x180074b1a  call    cs:__imp_CredMarshalCredentialW
0x180074b21  nop     dword ptr [rax+rax+00h]
0x180074b26  test    eax, eax
0x180074b28  jnz     short loc_180074B6C
0x180074b2a  cmp     [rbp+MarshaledCredential], 0
0x180074b2f  jnz     short loc_180074B6C
0x180074b31  call    cs:__imp_GetLastError
0x180074b38  nop     dword ptr [rax+rax+00h]
0x180074b3d  mov     ebx, eax
0x180074b3f  mov     rcx, cs:WPP_GLOBAL_Control
0x180074b46  lea     rax, WPP_GLOBAL_Control
0x180074b4d  cmp     rcx, rax
0x180074b50  jz      short loc_180074B95
0x180074b52  mov     rcx, [rcx+10h]
0x180074b56  lea     r8, WPP_c4e812f99669349517681909258710e2_Traceguids
0x180074b5d  mov     edx, 34h ; '4'
0x180074b62  mov     r9d, ebx
0x180074b65  call    WPP_SF_d
0x180074b6a  jmp     short loc_180074B95
0x180074b6c  call    IsRasTlsExt_GetPinUserBlobPresent
0x180074b71  test    al, al
0x180074b73  jz      short loc_180074B9B
0x180074b75  mov     r8, [rbp+MarshaledCredential]
0x180074b79  mov     r9, rdi
0x180074b7c  mov     edx, r15d
0x180074b7f  mov     [rsp+68h+var_48], rsi
0x180074b84  mov     rcx, r14
0x180074b87  call    cs:__imp_RasTlsExt_GetPinUserBlob
0x180074b8e  nop     dword ptr [rax+rax+00h]
0x180074b93  mov     ebx, eax
0x180074b95  test    ebx, ebx
0x180074b97  jz      short loc_180074BFD
0x180074b99  jmp     short loc_180074BC6
0x180074b9b  mov     ebx, 78h ; 'x'
0x180074ba0  mov     rcx, cs:WPP_GLOBAL_Control
0x180074ba7  lea     rax, WPP_GLOBAL_Control
0x180074bae  cmp     rcx, rax
0x180074bb1  jz      short loc_180074BC6
0x180074bb3  mov     rcx, [rcx+10h]
0x180074bb7  lea     edx, [rbx-43h]
0x180074bba  lea     r8, WPP_c4e812f99669349517681909258710e2_Traceguids
0x180074bc1  call    WPP_SF_
0x180074bc6  mov     rax, [rdi]
0x180074bc9  test    rax, rax
0x180074bcc  jz      short loc_180074BFD
0x180074bce  mov     ecx, [rsi]
0x180074bd0  test    rcx, rcx
0x180074bd3  jz      short loc_180074BE1
0x180074bd5  mov     byte ptr [rax], 0
0x180074bd8  inc     rax
0x180074bdb  sub     rcx, 1
0x180074bdf  jnz     short loc_180074BD5
0x180074be1  mov     rcx, [rdi]; pv
0x180074be4  call    cs:__imp_CoTaskMemFree
0x180074beb  nop     dword ptr [rax+rax+00h]
0x180074bf0  mov     qword ptr [rdi], 0
0x180074bf7  mov     dword ptr [rsi], 0
0x180074bfd  mov     rcx, [rbp+MarshaledCredential]; Buffer
0x180074c01  test    rcx, rcx
0x180074c04  jz      short loc_180074C12
0x180074c06  call    cs:__imp_CredFree
0x180074c0d  nop     dword ptr [rax+rax+00h]
0x180074c12  mov     eax, ebx
0x180074c14  mov     rcx, [rbp+var_18]
0x180074c18  xor     rcx, rsp; StackCookie
0x180074c1b  call    __security_check_cookie
0x180074c20  add     rsp, 68h
0x180074c24  pop     r15
0x180074c26  pop     r14
0x180074c28  pop     rdi
0x180074c29  pop     rsi
0x180074c2a  pop     rbx
0x180074c2b  pop     rbp
0x180074c2c  retn
```
