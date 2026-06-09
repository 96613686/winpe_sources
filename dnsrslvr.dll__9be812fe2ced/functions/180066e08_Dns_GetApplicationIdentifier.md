# Dns_GetApplicationIdentifier

- ea: `0x180066e08`
- end: `0x180067098`
- name: `Dns_GetApplicationIdentifier`
- size: `656`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180038980`

## callees

- `0x180008b00`
- `0x180046ec0`
- `0x180047818`
- `0x180066cbc`
- `0x180066e08`
- `0x1800730f0`
- `0x180073288`
- `0x180084c60`
- `0x180086b1c`
- `0x180086f24`

## import_xrefs

- `ntdll!RtlQueryPackageIdentity` at `0x180066fa3`
- `ntdll!RtlQueryPackageIdentity` at `0x180066fa3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180066f50`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180066f50`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180066fe9`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180066fe9`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180066f46`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180066f46`

## pseudocode

```c
__int64 __fastcall Dns_GetApplicationIdentifier(__int64 **a1, void *a2, DWORD *a3)
{
  const wchar_t *v6; // r14
  signed int AppContainerSidFromToken; // ebx
  __int64 v8; // rdx
  __int64 v9; // rcx
  __int64 v10; // r8
  signed int LastError; // eax
  __int64 *v12; // rax
  unsigned int v13; // ebx
  int TokenInformation; // [rsp+48h] [rbp-B8h] BYREF
  __int64 *v16; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v17; // [rsp+58h] [rbp-A8h]
  DWORD ReturnLength; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v19; // [rsp+68h] [rbp-98h] BYREF
  __int64 v20; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 v21[72]; // [rsp+80h] [rbp-80h] BYREF
  wchar_t v22[128]; // [rsp+110h] [rbp+10h] BYREF

  TokenInformation = 0;
  ReturnLength = 0;
  memset_0(v22, 0, sizeof(v22));
  v20 = 256;
  memset_0(v21, 0, 0x82u);
  v6 = (const wchar_t *)qword_18009CC30;
  v19 = 130;
  v16 = qword_18009CC30;
  v17 = 0;
  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    WPP_SF_q(1035, 17, WPP_c8767a4f47dd3eef630fa09f96ecdab4_Traceguids, a1);
  if ( a1 )
    *a1 = 0;
  if ( a3 )
    *a3 = 0;
  memset_0(a2, 0, 0x44u);
  AppContainerSidFromToken = CWxString::Set((CWxString *)&v16, L"*");
  if ( AppContainerSidFromToken >= 0 )
  {
    if ( (BYTE3(xmmword_1800AB5A0) & 0x40) != 0 )
      WPP_SF_q(1054, 18, WPP_c8767a4f47dd3eef630fa09f96ecdab4_Traceguids, -6);
    if ( GetTokenInformation((HANDLE)0xFFFFFFFFFFFFFFFALL, TokenIsAppContainer, &TokenInformation, 4u, &ReturnLength) )
    {
      AppContainerSidFromToken = 0;
      if ( TokenInformation )
      {
        if ( (int)RtlQueryPackageIdentity(-6, v22, &v20, v21, &v19, 0) >= 0 )
        {
          AppContainerSidFromToken = CWxString::Set((CWxString *)&v16, v21);
          if ( AppContainerSidFromToken < 0 )
            goto LABEL_28;
        }
        AppContainerSidFromToken = GetAppContainerSidFromToken((HANDLE)0xFFFFFFFFFFFFFFFALL, a2);
        if ( AppContainerSidFromToken < 0 )
          goto LABEL_28;
        *a3 = GetLengthSid(a2);
      }
      if ( a1 )
      {
        v12 = 0;
        v17 = 0;
        if ( v16 != qword_18009CC30 )
          v12 = v16;
        *a1 = v12;
        v16 = qword_18009CC30;
      }
      else
      {
        v6 = (const wchar_t *)v16;
      }
      if ( (BYTE3(xmmword_1800AB5A0) & 0x40) != 0 )
        WPP_SF__sid_DSS(v9, v8, v10, (char *)a2, *a3, v6, v22);
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
LABEL_28:
  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    WPP_SF_d(1035, 20, WPP_c8767a4f47dd3eef630fa09f96ecdab4_Traceguids, (unsigned int)AppContainerSidFromToken);
  v13 = WX_WIN32_FROM_HR((unsigned int)AppContainerSidFromToken);
  CWxString::_Release((CWxString *)&v16);
  return v13;
}

```

## disassembly

```asm
0x180066e08  push    rbp
0x180066e0a  push    rbx
0x180066e0b  push    rsi
0x180066e0c  push    rdi
0x180066e0d  push    r13
0x180066e0f  push    r14
0x180066e11  push    r15
0x180066e13  lea     rbp, [rsp-120h]
0x180066e1b  sub     rsp, 220h
0x180066e22  mov     rax, cs:__security_cookie
0x180066e29  xor     rax, rsp
0x180066e2c  mov     [rbp+150h+var_40], rax
0x180066e33  mov     rsi, r8
0x180066e36  mov     [rsp+250h+var_20C], 0
0x180066e3e  mov     r15, rdx
0x180066e41  mov     [rsp+250h+TokenInformation], 0
0x180066e49  mov     rdi, rcx
0x180066e4c  mov     [rsp+250h+var_1F0], 0
0x180066e54  mov     ebx, 100h
0x180066e59  lea     rcx, [rbp+150h+var_140]; void *
0x180066e5d  mov     r8d, ebx; Size
0x180066e60  xor     edx, edx; Val
0x180066e62  call    memset_0
0x180066e67  mov     [rsp+250h+var_1E0], rbx
0x180066e6c  lea     rcx, [rbp+150h+var_1D0]; void *
0x180066e70  mov     ebx, 82h
0x180066e75  xor     edx, edx; Val
0x180066e77  mov     r8d, ebx; Size
0x180066e7a  call    memset_0
0x180066e7f  lea     r14, qword_18009CC30
0x180066e86  mov     [rsp+250h+var_1E8], rbx
0x180066e8b  mov     [rsp+250h+var_200], r14
0x180066e90  mov     [rsp+250h+var_1F8], 0
0x180066e99  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180066ea0  jz      short loc_180066EB9
0x180066ea2  lea     edx, [rbx-71h]
0x180066ea5  mov     ecx, 40Bh
0x180066eaa  mov     r9, rdi
0x180066ead  lea     r8, WPP_c8767a4f47dd3eef630fa09f96ecdab4_Traceguids
0x180066eb4  call    WPP_SF_q
0x180066eb9  test    rdi, rdi
0x180066ebc  jz      short loc_180066EC5
0x180066ebe  mov     qword ptr [rdi], 0
0x180066ec5  test    rsi, rsi
0x180066ec8  jz      short loc_180066ED0
0x180066eca  mov     dword ptr [rsi], 0
0x180066ed0  xor     edx, edx; Val
0x180066ed2  mov     rcx, r15; void *
0x180066ed5  lea     r8d, [rdx+44h]; Size
0x180066ed9  call    memset_0
0x180066ede  lea     rdx, asc_18009C3E0; "*"
0x180066ee5  lea     rcx, [rsp+250h+var_200]; this
0x180066eea  call    ?Set@CWxString@@QEAAJPEBG@Z; CWxString::Set(ushort const *)
0x180066eef  mov     ebx, eax
0x180066ef1  test    eax, eax
0x180066ef3  jns     short loc_180066F02
0x180066ef5  mov     [rsp+250h+var_20C], 148h
0x180066efd  jmp     loc_180067040
0x180066f02  test    byte ptr cs:xmmword_1800AB5A0+3, 40h
0x180066f09  mov     r13, 0FFFFFFFFFFFFFFFAh
0x180066f10  jz      short loc_180066F2A
0x180066f12  lea     edx, [r13+18h]
0x180066f16  mov     ecx, 41Eh
0x180066f1b  mov     r9, r13
0x180066f1e  lea     r8, WPP_c8767a4f47dd3eef630fa09f96ecdab4_Traceguids
0x180066f25  call    WPP_SF_q
0x180066f2a  mov     r9d, 4; TokenInformationLength
0x180066f30  lea     rax, [rsp+250h+var_1F0]
0x180066f35  lea     r8, [rsp+250h+TokenInformation]; TokenInformation
0x180066f3a  mov     [rsp+250h+ReturnLength], rax; ReturnLength
0x180066f3f  mov     rcx, r13; TokenHandle
0x180066f42  lea     edx, [r9+19h]; TokenInformationClass
0x180066f46  call    cs:__imp_GetTokenInformation
0x180066f4c  test    eax, eax
0x180066f4e  jnz     short loc_180066F7C
0x180066f50  call    cs:__imp_GetLastError
0x180066f56  mov     ebx, eax
0x180066f58  test    eax, eax
0x180066f5a  jle     short loc_180066F65
0x180066f5c  movzx   ebx, ax
0x180066f5f  or      ebx, 80070000h
0x180066f65  test    ebx, ebx
0x180066f67  mov     [rsp+250h+var_20C], 155h
0x180066f6f  mov     eax, 8000FFFFh
0x180066f74  cmovns  ebx, eax
0x180066f77  jmp     loc_180067040
0x180066f7c  xor     ebx, ebx
0x180066f7e  cmp     [rsp+250h+TokenInformation], ebx
0x180066f82  jz      short loc_180066FF1
0x180066f84  lea     rax, [rsp+250h+var_1E8]
0x180066f89  mov     [rsp+250h+var_228], rbx
0x180066f8e  lea     r9, [rbp+150h+var_1D0]
0x180066f92  mov     [rsp+250h+ReturnLength], rax
0x180066f97  lea     r8, [rsp+250h+var_1E0]
0x180066f9c  mov     rcx, r13
0x180066f9f  lea     rdx, [rbp+150h+var_140]
0x180066fa3  call    cs:__imp_RtlQueryPackageIdentity
0x180066fa9  test    eax, eax
0x180066fab  js      short loc_180066FCB
0x180066fad  lea     rdx, [rbp+150h+var_1D0]; unsigned __int16 *
0x180066fb1  lea     rcx, [rsp+250h+var_200]; this
0x180066fb6  call    ?Set@CWxString@@QEAAJPEBG@Z; CWxString::Set(ushort const *)
0x180066fbb  mov     ebx, eax
0x180066fbd  test    eax, eax
0x180066fbf  jns     short loc_180066FCB
0x180066fc1  mov     [rsp+250h+var_20C], 166h
0x180066fc9  jmp     short loc_180067040
0x180066fcb  mov     rdx, r15; pDestinationSid
0x180066fce  mov     rcx, r13; TokenHandle
0x180066fd1  call    GetAppContainerSidFromToken
0x180066fd6  mov     ebx, eax
0x180066fd8  test    eax, eax
0x180066fda  jns     short loc_180066FE6
0x180066fdc  mov     [rsp+250h+var_20C], 169h
0x180066fe4  jmp     short loc_180067040
0x180066fe6  mov     rcx, r15; pSid
0x180066fe9  call    cs:__imp_GetLengthSid
0x180066fef  mov     [rsi], eax
0x180066ff1  test    rdi, rdi
0x180066ff4  jz      short loc_180067016
0x180066ff6  xor     eax, eax
0x180066ff8  mov     [rsp+250h+var_1F8], 0
0x180067001  cmp     [rsp+250h+var_200], r14
0x180067006  cmovnz  rax, [rsp+250h+var_200]
0x18006700c  mov     [rdi], rax
0x18006700f  mov     [rsp+250h+var_200], r14
0x180067014  jmp     short loc_18006701B
0x180067016  mov     r14, [rsp+250h+var_200]
0x18006701b  test    byte ptr cs:xmmword_1800AB5A0+3, 40h
0x180067022  jz      short loc_180067040
0x180067024  lea     rax, [rbp+150h+var_140]
0x180067028  mov     r9, r15
0x18006702b  mov     [rsp+250h+var_220], rax
0x180067030  mov     eax, [rsi]
0x180067032  mov     [rsp+250h+var_228], r14
0x180067037  mov     dword ptr [rsp+250h+ReturnLength], eax
0x18006703b  call    WPP_SF__sid_DSS
0x180067040  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180067047  jz      short loc_180067062
0x180067049  mov     edx, 14h
0x18006704e  lea     r8, WPP_c8767a4f47dd3eef630fa09f96ecdab4_Traceguids
0x180067055  mov     ecx, 40Bh
0x18006705a  mov     r9d, ebx
0x18006705d  call    WPP_SF_d
0x180067062  mov     ecx, ebx
0x180067064  call    WX_WIN32_FROM_HR
0x180067069  lea     rcx, [rsp+250h+var_200]; this
0x18006706e  mov     ebx, eax
0x180067070  call    ?_Release@CWxString@@AEAAXXZ; CWxString::_Release(void)
0x180067075  mov     eax, ebx
0x180067077  mov     rcx, [rbp+150h+var_40]
0x18006707e  xor     rcx, rsp; StackCookie
0x180067081  call    __security_check_cookie
0x180067086  add     rsp, 220h
0x18006708d  pop     r15
0x18006708f  pop     r14
0x180067091  pop     r13
0x180067093  pop     rdi
0x180067094  pop     rsi
0x180067095  pop     rbx
0x180067096  pop     rbp
0x180067097  retn
```
