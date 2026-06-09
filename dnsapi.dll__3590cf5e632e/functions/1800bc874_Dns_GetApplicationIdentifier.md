# Dns_GetApplicationIdentifier

- ea: `0x1800bc874`
- end: `0x1800bcb0f`
- name: `Dns_GetApplicationIdentifier`
- size: `667`
- prototype: `__int64 __fastcall(unsigned __int16 **, PSID pDestinationSid)`
- caller_count: `2`
- callee_count: `11`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18003fe10`
- `0x1800795a0`

## callees

- `0x18003de30`
- `0x18004148c`
- `0x180041514`
- `0x18005cd64`
- `0x18008b5f0`
- `0x18008bf98`
- `0x1800bc474`
- `0x1800bc874`
- `0x1800dc9e0`
- `0x1800ddfa8`
- `0x1800df7d0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bc9c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bc9c5`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800bc9b5`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800bc9b5`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800bca6c`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800bca6c`
- `ntdll!RtlQueryPackageIdentity` at `0x1800bca1f`
- `ntdll!RtlQueryPackageIdentity` at `0x1800bca1f`

## pseudocode

```c
__int64 __fastcall Dns_GetApplicationIdentifier(unsigned __int16 **a1, PSID pDestinationSid, DWORD *a3)
{
  signed int AppContainerSidFromToken; // ebx
  signed int LastError; // eax
  __int64 v8; // rdx
  __int64 v9; // rcx
  __int64 v10; // r8
  unsigned int v11; // ebx
  _QWORD v13[2]; // [rsp+48h] [rbp-B8h] BYREF
  int TokenInformation; // [rsp+58h] [rbp-A8h] BYREF
  DWORD ReturnLength; // [rsp+5Ch] [rbp-A4h] BYREF
  __int64 v16; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v17; // [rsp+68h] [rbp-98h] BYREF
  unsigned __int16 v18[72]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v19[256]; // [rsp+100h] [rbp+0h] BYREF

  TokenInformation = 0;
  ReturnLength = 0;
  memset_0(v19, 0, sizeof(v19));
  v17 = 256;
  memset_0(v18, 0, 0x82u);
  v16 = 130;
  v13[0] = &word_1800F66E0;
  v13[1] = 0;
  if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
    WPP_SF_q(1035, 17, WPP_c8767a4f47dd3eef630fa09f96ecdab4_Traceguids, a1);
  if ( a1 )
    *a1 = 0;
  if ( a3 )
    *a3 = 0;
  memset_0(pDestinationSid, 0, 0x44u);
  AppContainerSidFromToken = CWxString::Set((CWxString *)v13, L"*");
  if ( AppContainerSidFromToken >= 0 )
  {
    if ( (BYTE3(xmmword_1801119E0) & 0x40) != 0 )
      WPP_SF_q(1054, 18, WPP_c8767a4f47dd3eef630fa09f96ecdab4_Traceguids, -6);
    if ( GetTokenInformation((HANDLE)0xFFFFFFFFFFFFFFFALL, TokenIsAppContainer, &TokenInformation, 4u, &ReturnLength) )
    {
      AppContainerSidFromToken = 0;
      if ( TokenInformation )
      {
        if ( (int)RtlQueryPackageIdentity(-6, v19, &v17, v18, &v16, 0) >= 0 )
        {
          AppContainerSidFromToken = CWxString::Set((CWxString *)v13, v18);
          if ( AppContainerSidFromToken < 0 )
            goto LABEL_23;
        }
        AppContainerSidFromToken = GetAppContainerSidFromToken((HANDLE)0xFFFFFFFFFFFFFFFALL, pDestinationSid);
        if ( AppContainerSidFromToken < 0 )
          goto LABEL_23;
        *a3 = GetLengthSid(pDestinationSid);
      }
      CWxString::Detach((CWxString *)v13, a1);
      if ( (BYTE3(xmmword_1801119E0) & 0x40) != 0 )
        WPP_SF__sid_DSS(v9, v8, v10, pDestinationSid, *a3, v13[0], v19);
    }
    else
    {
      LastError = GetLastError();
      AppContainerSidFromToken = LastError;
      if ( LastError > 0 )
        AppContainerSidFromToken = (unsigned __int16)LastError | 0x80070000;
      if ( AppContainerSidFromToken >= 0 )
        AppContainerSidFromToken = -2147418113;
    }
  }
LABEL_23:
  if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
    WPP_SF_d(1035, 20, WPP_c8767a4f47dd3eef630fa09f96ecdab4_Traceguids, (unsigned int)AppContainerSidFromToken);
  v11 = WX_WIN32_FROM_HR((unsigned int)AppContainerSidFromToken);
  CWxString::_Release((CWxString *)v13);
  return v11;
}

```

## disassembly

```asm
0x1800bc874  mov     [rsp-8+arg_18], rbx
0x1800bc879  push    rbp
0x1800bc87a  push    rsi
0x1800bc87b  push    rdi
0x1800bc87c  push    r12
0x1800bc87e  push    r14
0x1800bc880  lea     rbp, [rsp-110h]
0x1800bc888  sub     rsp, 210h
0x1800bc88f  mov     rax, cs:__security_cookie
0x1800bc896  xor     rax, rsp
0x1800bc899  mov     [rbp+130h+var_30], rax
0x1800bc8a0  mov     rsi, r8
0x1800bc8a3  mov     [rsp+230h+var_1EC], 0
0x1800bc8ab  mov     r14, rdx
0x1800bc8ae  mov     [rsp+230h+TokenInformation], 0
0x1800bc8b6  mov     rdi, rcx
0x1800bc8b9  mov     [rsp+230h+var_1D4], 0
0x1800bc8c1  mov     ebx, 100h
0x1800bc8c6  lea     rcx, [rbp+130h+var_130]; void *
0x1800bc8ca  mov     r8d, ebx; Size
0x1800bc8cd  xor     edx, edx; Val
0x1800bc8cf  call    memset_0
0x1800bc8d4  mov     [rsp+230h+var_1C8], rbx
0x1800bc8d9  lea     rcx, [rsp+230h+var_1C0]; void *
0x1800bc8de  mov     ebx, 82h
0x1800bc8e3  xor     edx, edx; Val
0x1800bc8e5  mov     r8d, ebx; Size
0x1800bc8e8  call    memset_0
0x1800bc8ed  lea     rax, word_1800F66E0
0x1800bc8f4  mov     [rsp+230h+var_1D0], rbx
0x1800bc8f9  mov     [rsp+230h+var_1E8], rax
0x1800bc8fe  mov     [rsp+230h+var_1E0], 0
0x1800bc907  test    byte ptr cs:xmmword_1801119E0+1, 8
0x1800bc90e  jz      short loc_1800BC927
0x1800bc910  lea     edx, [rbx-71h]
0x1800bc913  mov     ecx, 40Bh
0x1800bc918  mov     r9, rdi
0x1800bc91b  lea     r8, WPP_c8767a4f47dd3eef630fa09f96ecdab4_Traceguids
0x1800bc922  call    WPP_SF_q
0x1800bc927  test    rdi, rdi
0x1800bc92a  jz      short loc_1800BC933
0x1800bc92c  mov     qword ptr [rdi], 0
0x1800bc933  test    rsi, rsi
0x1800bc936  jz      short loc_1800BC93E
0x1800bc938  mov     dword ptr [rsi], 0
0x1800bc93e  xor     edx, edx; Val
0x1800bc940  mov     rcx, r14; void *
0x1800bc943  lea     r8d, [rdx+44h]; Size
0x1800bc947  call    memset_0
0x1800bc94c  lea     rdx, asc_1800F5998; "*"
0x1800bc953  lea     rcx, [rsp+230h+var_1E8]; this
0x1800bc958  call    ?Set@CWxString@@QEAAJPEBG@Z; CWxString::Set(ushort const *)
0x1800bc95d  mov     ebx, eax
0x1800bc95f  test    eax, eax
0x1800bc961  jns     short loc_1800BC970
0x1800bc963  mov     [rsp+230h+var_1EC], 148h
0x1800bc96b  jmp     loc_1800BCAB1
0x1800bc970  test    byte ptr cs:xmmword_1801119E0+3, 40h
0x1800bc977  mov     r12, 0FFFFFFFFFFFFFFFAh
0x1800bc97e  jz      short loc_1800BC999
0x1800bc980  lea     edx, [r12+18h]
0x1800bc985  mov     ecx, 41Eh
0x1800bc98a  mov     r9, r12
0x1800bc98d  lea     r8, WPP_c8767a4f47dd3eef630fa09f96ecdab4_Traceguids
0x1800bc994  call    WPP_SF_q
0x1800bc999  mov     r9d, 4; TokenInformationLength
0x1800bc99f  lea     rax, [rsp+230h+var_1D4]
0x1800bc9a4  lea     r8, [rsp+230h+TokenInformation]; TokenInformation
0x1800bc9a9  mov     [rsp+230h+ReturnLength], rax; ReturnLength
0x1800bc9ae  mov     rcx, r12; TokenHandle
0x1800bc9b1  lea     edx, [r9+19h]; TokenInformationClass
0x1800bc9b5  call    cs:__imp_GetTokenInformation
0x1800bc9bc  nop     dword ptr [rax+rax+00h]
0x1800bc9c1  test    eax, eax
0x1800bc9c3  jnz     short loc_1800BC9F7
0x1800bc9c5  call    cs:__imp_GetLastError
0x1800bc9cc  nop     dword ptr [rax+rax+00h]
0x1800bc9d1  mov     ebx, eax
0x1800bc9d3  test    eax, eax
0x1800bc9d5  jle     short loc_1800BC9E0
0x1800bc9d7  movzx   ebx, ax
0x1800bc9da  or      ebx, 80070000h
0x1800bc9e0  test    ebx, ebx
0x1800bc9e2  mov     [rsp+230h+var_1EC], 155h
0x1800bc9ea  mov     eax, 8000FFFFh
0x1800bc9ef  cmovns  ebx, eax
0x1800bc9f2  jmp     loc_1800BCAB1
0x1800bc9f7  xor     ebx, ebx
0x1800bc9f9  cmp     [rsp+230h+TokenInformation], ebx
0x1800bc9fd  jz      short loc_1800BCA7A
0x1800bc9ff  lea     rax, [rsp+230h+var_1D0]
0x1800bca04  mov     [rsp+230h+var_208], rbx
0x1800bca09  lea     r9, [rsp+230h+var_1C0]
0x1800bca0e  mov     [rsp+230h+ReturnLength], rax
0x1800bca13  lea     r8, [rsp+230h+var_1C8]
0x1800bca18  mov     rcx, r12
0x1800bca1b  lea     rdx, [rbp+130h+var_130]
0x1800bca1f  call    cs:__imp_RtlQueryPackageIdentity
0x1800bca26  nop     dword ptr [rax+rax+00h]
0x1800bca2b  test    eax, eax
0x1800bca2d  js      short loc_1800BCA4E
0x1800bca2f  lea     rdx, [rsp+230h+var_1C0]; unsigned __int16 *
0x1800bca34  lea     rcx, [rsp+230h+var_1E8]; this
0x1800bca39  call    ?Set@CWxString@@QEAAJPEBG@Z; CWxString::Set(ushort const *)
0x1800bca3e  mov     ebx, eax
0x1800bca40  test    eax, eax
0x1800bca42  jns     short loc_1800BCA4E
0x1800bca44  mov     [rsp+230h+var_1EC], 166h
0x1800bca4c  jmp     short loc_1800BCAB1
0x1800bca4e  mov     rdx, r14; pDestinationSid
0x1800bca51  mov     rcx, r12; TokenHandle
0x1800bca54  call    GetAppContainerSidFromToken
0x1800bca59  mov     ebx, eax
0x1800bca5b  test    eax, eax
0x1800bca5d  jns     short loc_1800BCA69
0x1800bca5f  mov     [rsp+230h+var_1EC], 169h
0x1800bca67  jmp     short loc_1800BCAB1
0x1800bca69  mov     rcx, r14; pSid
0x1800bca6c  call    cs:__imp_GetLengthSid
0x1800bca73  nop     dword ptr [rax+rax+00h]
0x1800bca78  mov     [rsi], eax
0x1800bca7a  mov     rdx, rdi; unsigned __int16 **
0x1800bca7d  lea     rcx, [rsp+230h+var_1E8]; this
0x1800bca82  call    ?Detach@CWxString@@QEAAXPEAPEAG@Z; CWxString::Detach(ushort * *)
0x1800bca87  test    byte ptr cs:xmmword_1801119E0+3, 40h
0x1800bca8e  jz      short loc_1800BCAB1
0x1800bca90  lea     rax, [rbp+130h+var_130]
0x1800bca94  mov     r9, r14
0x1800bca97  mov     [rsp+230h+var_200], rax
0x1800bca9c  mov     rax, [rsp+230h+var_1E8]
0x1800bcaa1  mov     [rsp+230h+var_208], rax
0x1800bcaa6  mov     eax, [rsi]
0x1800bcaa8  mov     dword ptr [rsp+230h+ReturnLength], eax
0x1800bcaac  call    WPP_SF__sid_DSS
0x1800bcab1  test    byte ptr cs:xmmword_1801119E0+1, 8
0x1800bcab8  jz      short loc_1800BCAD3
0x1800bcaba  mov     edx, 14h
0x1800bcabf  lea     r8, WPP_c8767a4f47dd3eef630fa09f96ecdab4_Traceguids
0x1800bcac6  mov     ecx, 40Bh
0x1800bcacb  mov     r9d, ebx
0x1800bcace  call    WPP_SF_d
0x1800bcad3  mov     ecx, ebx
0x1800bcad5  call    WX_WIN32_FROM_HR
0x1800bcada  lea     rcx, [rsp+230h+var_1E8]; this
0x1800bcadf  mov     ebx, eax
0x1800bcae1  call    ?_Release@CWxString@@AEAAXXZ; CWxString::_Release(void)
0x1800bcae6  mov     eax, ebx
0x1800bcae8  mov     rcx, [rbp+130h+var_30]
0x1800bcaef  xor     rcx, rsp; StackCookie
0x1800bcaf2  call    __security_check_cookie
0x1800bcaf7  mov     rbx, [rsp+230h+arg_18]
0x1800bcaff  add     rsp, 210h
0x1800bcb06  pop     r14
0x1800bcb08  pop     r12
0x1800bcb0a  pop     rdi
0x1800bcb0b  pop     rsi
0x1800bcb0c  pop     rbp
0x1800bcb0d  retn
```
