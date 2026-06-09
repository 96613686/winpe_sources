# GetPinForSingleCert(_CREDUI_INFOW *,_EAPTLS_USER_PROPERTIES *,ulong,uchar * *,ulong *)

- ea: `0x18006fe88`
- end: `0x180070013`
- name: `?GetPinForSingleCert@@YAKPEAU_CREDUI_INFOW@@PEAU_EAPTLS_USER_PROPERTIES@@KPEAPEAEPEAK@Z`
- size: `395`
- prototype: `unsigned int __fastcall(struct _CREDUI_INFOW *, struct _EAPTLS_USER_PROPERTIES *, unsigned int, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800702c4`

## callees

- `0x180004bd0`
- `0x1800075b0`
- `0x180035680`
- `0x180036930`
- `0x18006fe88`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006ff2f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006ff2f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006ffd6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006ffd6`
- `api-ms-win-security-credentials-l1-1-0!CredFree` at `0x18006fff2`
- `api-ms-win-security-credentials-l1-1-0!CredFree` at `0x18006fff2`
- `api-ms-win-security-credentials-l1-1-0!CredMarshalCredentialW` at `0x18006ff1e`
- `api-ms-win-security-credentials-l1-1-0!CredMarshalCredentialW` at `0x18006ff1e`
- `ext-ms-win-rastlsext-eap-l1-1-0!RasTlsExt_GetPinUserBlob` at `0x18006ff7f`
- `ext-ms-win-rastlsext-eap-l1-1-0!RasTlsExt_GetPinUserBlob` at `0x18006ff7f`

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
0x18006fe88  push    rbp
0x18006fe8a  push    rbx
0x18006fe8b  push    rsi
0x18006fe8c  push    rdi
0x18006fe8d  push    r14
0x18006fe8f  push    r15
0x18006fe91  mov     rbp, rsp
0x18006fe94  sub     rsp, 68h
0x18006fe98  mov     rax, cs:__security_cookie
0x18006fe9f  xor     rax, rsp
0x18006fea2  mov     [rbp+var_18], rax
0x18006fea6  mov     rsi, [rbp+arg_20]
0x18006feaa  xor     eax, eax
0x18006feac  xorps   xmm0, xmm0
0x18006feaf  mov     [rbp+var_20], rax
0x18006feb3  movups  [rbp+Credential], xmm0
0x18006feb7  mov     [rbp+MarshaledCredential], rax
0x18006febb  mov     rdi, r9
0x18006febe  mov     r15d, r8d
0x18006fec1  mov     rbx, rdx
0x18006fec4  mov     r14, rcx
0x18006fec7  mov     rcx, cs:WPP_GLOBAL_Control
0x18006fece  lea     rax, WPP_GLOBAL_Control
0x18006fed5  cmp     rcx, rax
0x18006fed8  jz      short loc_18006FEEF
0x18006feda  mov     rcx, [rcx+10h]
0x18006fede  lea     r8, WPP_c4e812f99669349517681909258710e2_Traceguids
0x18006fee5  mov     edx, 33h ; '3'
0x18006feea  call    WPP_SF_
0x18006feef  xorps   xmm0, xmm0
0x18006fef2  lea     r8, [rbp+MarshaledCredential]; MarshaledCredential
0x18006fef6  movups  [rbp+Credential], xmm0
0x18006fefa  xor     eax, eax
0x18006fefc  lea     rdx, [rbp+Credential]; Credential
0x18006ff00  movups  xmm0, xmmword ptr [rbx+14h]
0x18006ff04  mov     [rbp+var_20], rax
0x18006ff08  mov     ecx, 1; CredType
0x18006ff0d  mov     eax, [rbx+24h]
0x18006ff10  movups  [rbp+Credential+4], xmm0
0x18006ff14  mov     dword ptr [rbp+Credential], 18h
0x18006ff1b  mov     dword ptr [rbp+var_20+4], eax
0x18006ff1e  call    cs:__imp_CredMarshalCredentialW
0x18006ff24  test    eax, eax
0x18006ff26  jnz     short loc_18006FF64
0x18006ff28  cmp     [rbp+MarshaledCredential], 0
0x18006ff2d  jnz     short loc_18006FF64
0x18006ff2f  call    cs:__imp_GetLastError
0x18006ff35  mov     ebx, eax
0x18006ff37  mov     rcx, cs:WPP_GLOBAL_Control
0x18006ff3e  lea     rax, WPP_GLOBAL_Control
0x18006ff45  cmp     rcx, rax
0x18006ff48  jz      short loc_18006FF87
0x18006ff4a  mov     rcx, [rcx+10h]
0x18006ff4e  lea     r8, WPP_c4e812f99669349517681909258710e2_Traceguids
0x18006ff55  mov     edx, 34h ; '4'
0x18006ff5a  mov     r9d, ebx
0x18006ff5d  call    WPP_SF_d
0x18006ff62  jmp     short loc_18006FF87
0x18006ff64  call    IsRasTlsExt_GetPinUserBlobPresent
0x18006ff69  test    al, al
0x18006ff6b  jz      short loc_18006FF8D
0x18006ff6d  mov     r8, [rbp+MarshaledCredential]
0x18006ff71  mov     r9, rdi
0x18006ff74  mov     edx, r15d
0x18006ff77  mov     [rsp+68h+var_48], rsi
0x18006ff7c  mov     rcx, r14
0x18006ff7f  call    cs:__imp_RasTlsExt_GetPinUserBlob
0x18006ff85  mov     ebx, eax
0x18006ff87  test    ebx, ebx
0x18006ff89  jz      short loc_18006FFE9
0x18006ff8b  jmp     short loc_18006FFB8
0x18006ff8d  mov     ebx, 78h ; 'x'
0x18006ff92  mov     rcx, cs:WPP_GLOBAL_Control
0x18006ff99  lea     rax, WPP_GLOBAL_Control
0x18006ffa0  cmp     rcx, rax
0x18006ffa3  jz      short loc_18006FFB8
0x18006ffa5  mov     rcx, [rcx+10h]
0x18006ffa9  lea     edx, [rbx-43h]
0x18006ffac  lea     r8, WPP_c4e812f99669349517681909258710e2_Traceguids
0x18006ffb3  call    WPP_SF_
0x18006ffb8  mov     rax, [rdi]
0x18006ffbb  test    rax, rax
0x18006ffbe  jz      short loc_18006FFE9
0x18006ffc0  mov     ecx, [rsi]
0x18006ffc2  test    rcx, rcx
0x18006ffc5  jz      short loc_18006FFD3
0x18006ffc7  mov     byte ptr [rax], 0
0x18006ffca  inc     rax
0x18006ffcd  sub     rcx, 1
0x18006ffd1  jnz     short loc_18006FFC7
0x18006ffd3  mov     rcx, [rdi]; pv
0x18006ffd6  call    cs:__imp_CoTaskMemFree
0x18006ffdc  mov     qword ptr [rdi], 0
0x18006ffe3  mov     dword ptr [rsi], 0
0x18006ffe9  mov     rcx, [rbp+MarshaledCredential]; Buffer
0x18006ffed  test    rcx, rcx
0x18006fff0  jz      short loc_18006FFF8
0x18006fff2  call    cs:__imp_CredFree
0x18006fff8  mov     eax, ebx
0x18006fffa  mov     rcx, [rbp+var_18]
0x18006fffe  xor     rcx, rsp; StackCookie
0x180070001  call    __security_check_cookie
0x180070006  add     rsp, 68h
0x18007000a  pop     r15
0x18007000c  pop     r14
0x18007000e  pop     rdi
0x18007000f  pop     rsi
0x180070010  pop     rbx
0x180070011  pop     rbp
0x180070012  retn
```
