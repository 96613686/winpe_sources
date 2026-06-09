# CProvisioningNode::GetCertThumbprintsFromStore(ulong *,ushort * * *)

- ea: `0x18000f1a0`
- end: `0x18000f48a`
- name: `?GetCertThumbprintsFromStore@CProvisioningNode@@CAJPEAKPEAPEAPEAG@Z`
- size: `746`
- prototype: `__int64 __fastcall(unsigned int *, unsigned __int16 ***)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000f490`

## callees

- `0x180006954`
- `0x180006974`
- `0x180009b80`
- `0x18000f0dc`
- `0x18000f1a0`
- `0x18003586a`
- `0x1800358a0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000f269`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000f269`
- `OLEAUT32!__imp_SysAllocString` at `0x18000f342`
- `OLEAUT32!__imp_SysAllocString` at `0x18000f342`
- `CRYPT32!CertGetCertificateContextProperty` at `0x18000f2ea`
- `CRYPT32!CertGetCertificateContextProperty` at `0x18000f2ea`
- `CRYPT32!CertEnumCertificatesInStore` at `0x18000f22e`
- `CRYPT32!CertEnumCertificatesInStore` at `0x18000f24d`
- `CRYPT32!CertEnumCertificatesInStore` at `0x18000f2b9`
- `CRYPT32!CertEnumCertificatesInStore` at `0x18000f36b`
- `CRYPT32!CertEnumCertificatesInStore` at `0x18000f22e`
- `CRYPT32!CertEnumCertificatesInStore` at `0x18000f24d`
- `CRYPT32!CertEnumCertificatesInStore` at `0x18000f2b9`
- `CRYPT32!CertEnumCertificatesInStore` at `0x18000f36b`
- `CRYPT32!CryptBinaryToStringW` at `0x18000f320`
- `CRYPT32!CryptBinaryToStringW` at `0x18000f320`
- `CRYPT32!CertCloseStore` at `0x18000f20c`
- `CRYPT32!CertCloseStore` at `0x18000f3ba`
- `CRYPT32!CertCloseStore` at `0x18000f458`
- `CRYPT32!CertCloseStore` at `0x18000f20c`
- `CRYPT32!CertCloseStore` at `0x18000f3ba`
- `CRYPT32!CertCloseStore` at `0x18000f458`

## pseudocode

```c
__int64 __fastcall CProvisioningNode::GetCertThumbprintsFromStore(unsigned int *a1, unsigned __int16 ***a2)
{
  int v4; // eax
  unsigned int LastError; // edi
  HCERTSTORE v6; // rcx
  const CERT_CONTEXT *i; // rax
  unsigned __int16 **v9; // rax
  __int64 v10; // rdx
  __int64 v11; // rsi
  const CERT_CONTEXT *v12; // rdi
  const char *v13; // r9
  BSTR v14; // rax
  __int64 v15; // rdx
  int pcchString; // [rsp+20h] [rbp-A9h]
  unsigned int v17; // [rsp+30h] [rbp-99h] BYREF
  HCERTSTORE hCertStore; // [rsp+38h] [rbp-91h] BYREF
  DWORD pcbData; // [rsp+40h] [rbp-89h] BYREF
  unsigned __int16 **v20; // [rsp+48h] [rbp-81h] BYREF
  DWORD v21; // [rsp+50h] [rbp-79h] BYREF
  _QWORD v22[2]; // [rsp+58h] [rbp-71h] BYREF
  char v23; // [rsp+68h] [rbp-61h]
  BYTE pvData[32]; // [rsp+70h] [rbp-59h] BYREF
  WCHAR pszString[48]; // [rsp+90h] [rbp-39h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+5Fh]

  hCertStore = 0;
  v4 = CProvisioningNode::OpenProvisioningCertStore(&hCertStore);
  LastError = v4;
  if ( v4 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x28,
      (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\getchildnodenames.cpp",
      (const char *)(unsigned int)v4,
      pcchString);
    v6 = hCertStore;
    if ( !hCertStore )
      return LastError;
LABEL_3:
    CertCloseStore(v6, 1u);
    return LastError;
  }
  v17 = 0;
  for ( i = CertEnumCertificatesInStore(hCertStore, 0); i; i = CertEnumCertificatesInStore(hCertStore, i) )
    ++v17;
  v9 = (unsigned __int16 **)CoTaskMemAlloc(8LL * v17);
  v23 = 1;
  v22[0] = &v20;
  v22[1] = &v17;
  v20 = v9;
  if ( v9 )
  {
    memset_0(v9, 0, 8LL * v17);
    v11 = 0;
    v12 = CertEnumCertificatesInStore(hCertStore, 0);
    if ( v12 )
    {
      while ( 1 )
      {
        pcbData = 20;
        if ( !CertGetCertificateContextProperty(v12, 3u, pvData, &pcbData) )
          break;
        v21 = 41;
        if ( !CryptBinaryToStringW(pvData, pcbData, 0x4000000Cu, pszString, &v21) )
        {
          v15 = 71;
          goto LABEL_24;
        }
        if ( (unsigned int)v11 >= v17 )
        {
          LastError = -2147418113;
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x49,
            (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\getchildnodenames.cpp",
            (const char *)0x8000FFFFLL,
            pcchString);
          goto LABEL_25;
        }
        v14 = SysAllocString(pszString);
        v20[v11] = v14;
        if ( !v20[v11] )
        {
          v10 = 75;
          goto LABEL_18;
        }
        v12 = CertEnumCertificatesInStore(hCertStore, v12);
        if ( !v12 )
          goto LABEL_27;
        v11 = (unsigned int)(v11 + 1);
      }
      v15 = 66;
LABEL_24:
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)v15,
                    (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\getchildnodenames.cpp",
                    v13);
LABEL_25:
      wil::details::ScopeExitFn__lambda_6ac91ad683576d74491c09be03af3e5e___::_ScopeExitFn__lambda_6ac91ad683576d74491c09be03af3e5e___(v22);
      v6 = hCertStore;
      if ( !hCertStore )
        return LastError;
      goto LABEL_3;
    }
LABEL_27:
    *a1 = v17;
    *a2 = v20;
    v20 = 0;
    wil::details::ScopeExitFn__lambda_6ac91ad683576d74491c09be03af3e5e___::_ScopeExitFn__lambda_6ac91ad683576d74491c09be03af3e5e___(v22);
    if ( hCertStore )
      CertCloseStore(hCertStore, 1u);
    return 0;
  }
  else
  {
    v10 = 56;
LABEL_18:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\getchildnodenames.cpp",
      (const char *)0x8007000ELL,
      pcchString);
    wil::details::ScopeExitFn__lambda_6ac91ad683576d74491c09be03af3e5e___::_ScopeExitFn__lambda_6ac91ad683576d74491c09be03af3e5e___(v22);
    if ( hCertStore )
      CertCloseStore(hCertStore, 1u);
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x18000f1a0  mov     [rsp-8+arg_10], rbx
0x18000f1a5  push    rbp
0x18000f1a6  push    rsi
0x18000f1a7  push    rdi
0x18000f1a8  push    r14
0x18000f1aa  push    r15
0x18000f1ac  lea     rbp, [rsp-37h]
0x18000f1b1  sub     rsp, 100h
0x18000f1b8  mov     rax, cs:__security_cookie
0x18000f1bf  xor     rax, rsp
0x18000f1c2  mov     [rbp+57h+var_30], rax
0x18000f1c6  mov     r14, rcx
0x18000f1c9  mov     [rsp+120h+hCertStore], 0
0x18000f1d2  lea     rcx, [rsp+120h+hCertStore]; void **
0x18000f1d7  mov     r15, rdx
0x18000f1da  call    ?OpenProvisioningCertStore@CProvisioningNode@@CAJPEAPEAX@Z; CProvisioningNode::OpenProvisioningCertStore(void * *)
0x18000f1df  mov     edi, eax
0x18000f1e1  test    eax, eax
0x18000f1e3  jns     short loc_18000F21F
0x18000f1e5  mov     rcx, [rbp+5Fh]; this
0x18000f1e9  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\prov\\provcsp\\getch"...
0x18000f1f0  mov     r9d, eax; char *
0x18000f1f3  mov     edx, 28h ; '('; void *
0x18000f1f8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000f1fd  mov     rcx, [rsp+120h+hCertStore]; hCertStore
0x18000f202  test    rcx, rcx
0x18000f205  jz      short loc_18000F218
0x18000f207  mov     edx, 1; dwFlags
0x18000f20c  call    cs:__imp_CertCloseStore
0x18000f213  nop     dword ptr [rax+rax+00h]
0x18000f218  mov     eax, edi
0x18000f21a  jmp     loc_18000F466
0x18000f21f  mov     rcx, [rsp+120h+hCertStore]; hCertStore
0x18000f224  xor     edx, edx; pPrevCertContext
0x18000f226  mov     [rsp+120h+var_F0], 0
0x18000f22e  call    cs:__imp_CertEnumCertificatesInStore
0x18000f235  nop     dword ptr [rax+rax+00h]
0x18000f23a  mov     ebx, 1
0x18000f23f  jmp     short loc_18000F259
0x18000f241  add     [rsp+120h+var_F0], ebx
0x18000f245  mov     rdx, rdi; pPrevCertContext
0x18000f248  mov     rcx, [rsp+120h+hCertStore]; hCertStore
0x18000f24d  call    cs:__imp_CertEnumCertificatesInStore
0x18000f254  nop     dword ptr [rax+rax+00h]
0x18000f259  mov     rdi, rax
0x18000f25c  test    rax, rax
0x18000f25f  jnz     short loc_18000F241
0x18000f261  mov     ecx, [rsp+120h+var_F0]
0x18000f265  shl     rcx, 3; cb
0x18000f269  call    cs:__imp_CoTaskMemAlloc
0x18000f270  nop     dword ptr [rax+rax+00h]
0x18000f275  lea     rcx, [rsp+120h+var_D8]
0x18000f27a  mov     [rbp+57h+var_B8], bl
0x18000f27d  mov     [rbp+57h+var_C8], rcx
0x18000f281  lea     rcx, [rsp+120h+var_F0]
0x18000f286  mov     [rbp+57h+var_C0], rcx
0x18000f28a  mov     [rsp+120h+var_D8], rax
0x18000f28f  test    rax, rax
0x18000f292  jnz     short loc_18000F29C
0x18000f294  lea     edx, [rax+38h]
0x18000f297  jmp     loc_18000F38F
0x18000f29c  mov     r8d, [rsp+120h+var_F0]
0x18000f2a1  xor     edx, edx; Val
0x18000f2a3  shl     r8, 3; Size
0x18000f2a7  mov     rcx, rax; void *
0x18000f2aa  call    memset_0
0x18000f2af  mov     rcx, [rsp+120h+hCertStore]; hCertStore
0x18000f2b4  mov     rdx, rdi; pPrevCertContext
0x18000f2b7  xor     esi, esi
0x18000f2b9  call    cs:__imp_CertEnumCertificatesInStore
0x18000f2c0  nop     dword ptr [rax+rax+00h]
0x18000f2c5  mov     rdi, rax
0x18000f2c8  test    rax, rax
0x18000f2cb  jz      loc_18000F42B
0x18000f2d1  lea     r9, [rsp+120h+pcbData]; pcbData
0x18000f2d6  mov     [rsp+120h+pcbData], 14h
0x18000f2de  lea     r8, [rbp+57h+pvData]; pvData
0x18000f2e2  mov     edx, 3; dwPropId
0x18000f2e7  mov     rcx, rdi; pCertContext
0x18000f2ea  call    cs:__imp_CertGetCertificateContextProperty
0x18000f2f1  nop     dword ptr [rax+rax+00h]
0x18000f2f6  test    eax, eax
0x18000f2f8  jz      loc_18000F3F6
0x18000f2fe  mov     edx, [rsp+120h+pcbData]; cbBinary
0x18000f302  lea     rax, [rbp+57h+var_D0]
0x18000f306  lea     r9, [rbp+57h+pszString]; pszString
0x18000f30a  mov     qword ptr [rsp+120h+pcchString], rax; int
0x18000f30f  mov     r8d, 4000000Ch; dwFlags
0x18000f315  mov     [rbp+57h+var_D0], 29h ; ')'
0x18000f31c  lea     rcx, [rbp+57h+pvData]; pbBinary
0x18000f320  call    cs:__imp_CryptBinaryToStringW
0x18000f327  nop     dword ptr [rax+rax+00h]
0x18000f32c  test    eax, eax
0x18000f32e  jz      loc_18000F3EF
0x18000f334  cmp     esi, [rsp+120h+var_F0]
0x18000f338  jnb     loc_18000F3D0
0x18000f33e  lea     rcx, [rbp+57h+pszString]; psz
0x18000f342  call    cs:__imp_SysAllocString
0x18000f349  nop     dword ptr [rax+rax+00h]
0x18000f34e  mov     rcx, [rsp+120h+var_D8]
0x18000f353  mov     [rcx+rsi*8], rax
0x18000f357  mov     rax, [rsp+120h+var_D8]
0x18000f35c  cmp     qword ptr [rax+rsi*8], 0
0x18000f361  jz      short loc_18000F38A
0x18000f363  mov     rcx, [rsp+120h+hCertStore]; hCertStore
0x18000f368  mov     rdx, rdi; pPrevCertContext
0x18000f36b  call    cs:__imp_CertEnumCertificatesInStore
0x18000f372  nop     dword ptr [rax+rax+00h]
0x18000f377  mov     rdi, rax
0x18000f37a  test    rax, rax
0x18000f37d  jz      loc_18000F42B
0x18000f383  add     esi, ebx
0x18000f385  jmp     loc_18000F2D1
0x18000f38a  mov     edx, 4Bh ; 'K'; void *
0x18000f38f  mov     rcx, [rbp+5Fh]; this
0x18000f393  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\prov\\provcsp\\getch"...
0x18000f39a  mov     r9d, 8007000Eh; char *
0x18000f3a0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000f3a5  lea     rcx, [rbp+57h+var_C8]
0x18000f3a9  call    wil__details__ScopeExitFn__lambda_6ac91ad683576d74491c09be03af3e5e______ScopeExitFn__lambda_6ac91ad683576d74491c09be03af3e5e___
0x18000f3ae  mov     rcx, [rsp+120h+hCertStore]; hCertStore
0x18000f3b3  test    rcx, rcx
0x18000f3b6  jz      short loc_18000F3C6
0x18000f3b8  mov     edx, ebx; dwFlags
0x18000f3ba  call    cs:__imp_CertCloseStore
0x18000f3c1  nop     dword ptr [rax+rax+00h]
0x18000f3c6  mov     eax, 8007000Eh
0x18000f3cb  jmp     loc_18000F466
0x18000f3d0  mov     rcx, [rbp+5Fh]; this
0x18000f3d4  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\prov\\provcsp\\getch"...
0x18000f3db  mov     edi, 8000FFFFh
0x18000f3e0  mov     edx, 49h ; 'I'; void *
0x18000f3e5  mov     r9d, edi; char *
0x18000f3e8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000f3ed  jmp     short loc_18000F40D
0x18000f3ef  mov     edx, 47h ; 'G'
0x18000f3f4  jmp     short loc_18000F3FB
0x18000f3f6  mov     edx, 42h ; 'B'; void *
0x18000f3fb  mov     rcx, [rbp+5Fh]; this
0x18000f3ff  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\prov\\provcsp\\getch"...
0x18000f406  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000f40b  mov     edi, eax
0x18000f40d  lea     rcx, [rbp+57h+var_C8]
0x18000f411  call    wil__details__ScopeExitFn__lambda_6ac91ad683576d74491c09be03af3e5e______ScopeExitFn__lambda_6ac91ad683576d74491c09be03af3e5e___
0x18000f416  mov     rcx, [rsp+120h+hCertStore]
0x18000f41b  test    rcx, rcx
0x18000f41e  jz      loc_18000F218
0x18000f424  mov     edx, ebx
0x18000f426  jmp     loc_18000F20C
0x18000f42b  mov     eax, [rsp+120h+var_F0]
0x18000f42f  lea     rcx, [rbp+57h+var_C8]
0x18000f433  mov     [r14], eax
0x18000f436  mov     rax, [rsp+120h+var_D8]
0x18000f43b  mov     [r15], rax
0x18000f43e  mov     [rsp+120h+var_D8], 0
0x18000f447  call    wil__details__ScopeExitFn__lambda_6ac91ad683576d74491c09be03af3e5e______ScopeExitFn__lambda_6ac91ad683576d74491c09be03af3e5e___
0x18000f44c  mov     rcx, [rsp+120h+hCertStore]; hCertStore
0x18000f451  test    rcx, rcx
0x18000f454  jz      short loc_18000F464
0x18000f456  mov     edx, ebx; dwFlags
0x18000f458  call    cs:__imp_CertCloseStore
0x18000f45f  nop     dword ptr [rax+rax+00h]
0x18000f464  xor     eax, eax
0x18000f466  mov     rcx, [rbp+57h+var_30]
0x18000f46a  xor     rcx, rsp; StackCookie
0x18000f46d  call    __security_check_cookie
0x18000f472  mov     rbx, [rsp+120h+arg_10]
0x18000f47a  add     rsp, 100h
0x18000f481  pop     r15
0x18000f483  pop     r14
0x18000f485  pop     rdi
0x18000f486  pop     rsi
0x18000f487  pop     rbp
0x18000f488  retn
```
