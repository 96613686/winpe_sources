# RdlsSecretsRegCache::StoreCHEndorsedRdlsCertificates(ulong,uchar *,ulong,uchar *)

- ea: `0x18008143c`
- end: `0x18008171d`
- name: `?StoreCHEndorsedRdlsCertificates@RdlsSecretsRegCache@@AEAAKKPEAEK0@Z`
- size: `737`
- prototype: `unsigned int(RdlsSecretsRegCache *__hidden this, unsigned int, unsigned __int8 *, unsigned int, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180080fb0`

## callees

- `0x180022910`
- `0x18008143c`

## import_xrefs

- `CRYPT32!CertNameToStrW` at `0x1800815a1`
- `CRYPT32!CertNameToStrW` at `0x1800815ee`
- `CRYPT32!CertNameToStrW` at `0x1800815a1`
- `CRYPT32!CertNameToStrW` at `0x1800815ee`
- `CRYPT32!CertCreateCertificateContext` at `0x18008156a`
- `CRYPT32!CertCreateCertificateContext` at `0x18008156a`
- `CRYPT32!CertFreeCertificateContext` at `0x1800816d8`
- `CRYPT32!CertFreeCertificateContext` at `0x1800816d8`
- `ADVAPI32!RegSetValueExW` at `0x18008150e`
- `ADVAPI32!RegSetValueExW` at `0x180081547`
- `ADVAPI32!RegSetValueExW` at `0x18008161a`
- `ADVAPI32!RegSetValueExW` at `0x18008150e`
- `ADVAPI32!RegSetValueExW` at `0x180081547`
- `ADVAPI32!RegSetValueExW` at `0x18008161a`
- `ADVAPI32!RegCreateKeyExW` at `0x1800814b1`
- `ADVAPI32!RegCreateKeyExW` at `0x1800814b1`
- `ADVAPI32!RegCloseKey` at `0x180081665`
- `ADVAPI32!RegCloseKey` at `0x1800816ed`
- `ADVAPI32!RegCloseKey` at `0x180081665`
- `ADVAPI32!RegCloseKey` at `0x1800816ed`
- `KERNEL32!LocalAlloc` at `0x1800815c2`
- `KERNEL32!LocalAlloc` at `0x1800815c2`
- `KERNEL32!LocalFree` at `0x180081689`
- `KERNEL32!LocalFree` at `0x1800816a3`
- `KERNEL32!LocalFree` at `0x1800816c4`
- `KERNEL32!LocalFree` at `0x180081689`
- `KERNEL32!LocalFree` at `0x1800816a3`
- `KERNEL32!LocalFree` at `0x1800816c4`

## pseudocode

```c
__int64 __fastcall RdlsSecretsRegCache::StoreCHEndorsedRdlsCertificates(
        RdlsSecretsRegCache *this,
        DWORD a2,
        unsigned __int8 *a3,
        DWORD a4,
        unsigned __int8 *lpData)
{
  const CERT_CONTEXT *v8; // rdi
  BYTE *v9; // r14
  unsigned int v10; // eax
  unsigned int v11; // ebx
  PCCERT_CONTEXT CertificateContext; // rax
  DWORD v13; // eax
  DWORD v14; // ebx
  WCHAR *v15; // rax
  unsigned int v16; // eax
  void *v17; // rcx
  void *v18; // rcx
  DWORD v20[4]; // [rsp+50h] [rbp-30h] BYREF
  struct _EVENT_DESCRIPTOR v21; // [rsp+60h] [rbp-20h] BYREF
  HKEY hKey; // [rsp+70h] [rbp-10h] BYREF

  hKey = 0;
  v20[0] = 0;
  v8 = 0;
  v9 = 0;
  v10 = RegCreateKeyExW(
          HKEY_LOCAL_MACHINE,
          L"SOFTWARE\\Microsoft\\TermServLicensing\\Certificates",
          0,
          0,
          0,
          0x20006u,
          0,
          &hKey,
          v20);
  v11 = v10;
  if ( v10 )
    goto LABEL_2;
  if ( lpData )
  {
    v10 = RegSetValueExW(hKey, L"Parm2", 0, 3u, lpData, a4);
    v11 = v10;
    if ( v10 )
      goto LABEL_2;
  }
  if ( !a3 )
    goto LABEL_15;
  v10 = RegSetValueExW(hKey, L"Parm1", 0, 3u, a3, a2);
  v11 = v10;
  if ( v10 )
  {
LABEL_2:
    v21 = (struct _EVENT_DESCRIPTOR)TLS_E_STORELSCERTIFICATE;
    TLSLogEvent(&v21, 0xC0010014, v10);
    goto LABEL_28;
  }
  CertificateContext = CertCreateCertificateContext(1u, a3, a2);
  v8 = CertificateContext;
  if ( !CertificateContext )
  {
    v11 = -2147467259;
    goto LABEL_28;
  }
  v13 = CertNameToStrW(1u, &CertificateContext->pCertInfo->Subject, 0x8000003u, 0, 0);
  v14 = v13;
  if ( v13 )
  {
    v15 = (WCHAR *)LocalAlloc(0x40u, 2LL * (v13 + 1));
    v9 = (BYTE *)v15;
    if ( v15 )
    {
      CertNameToStrW(1u, &v8->pCertInfo->Subject, 0x8000003u, v15, v14);
      v16 = RegSetValueExW(hKey, L"Parm0", 0, 3u, v9, v14 + 2);
      v11 = v16;
      if ( v16 )
      {
        v21 = (struct _EVENT_DESCRIPTOR)TLS_E_STORELSCERTIFICATE;
        TLSLogEvent(&v21, 0xC0010014, v16);
        goto LABEL_25;
      }
LABEL_15:
      if ( hKey )
      {
        RegCloseKey(hKey);
        hKey = 0;
      }
      if ( a3 && lpData )
      {
        v17 = (void *)*((_QWORD *)this + 4);
        if ( v17 )
          LocalFree(v17);
        *((_QWORD *)this + 4) = 0;
        v18 = (void *)*((_QWORD *)this + 6);
        if ( v18 )
          LocalFree(v18);
        *((_QWORD *)this + 6) = 0;
        *((_DWORD *)this + 6) = 0;
        *((_DWORD *)this + 10) = 0;
      }
      if ( !v9 )
      {
LABEL_26:
        if ( !v8 )
          goto LABEL_28;
        goto LABEL_27;
      }
LABEL_25:
      LocalFree(v9);
      goto LABEL_26;
    }
    v11 = -2147024882;
  }
  else
  {
    v11 = -2147024809;
  }
LABEL_27:
  CertFreeCertificateContext(v8);
LABEL_28:
  if ( hKey )
    RegCloseKey(hKey);
  return v11;
}

```

## disassembly

```asm
0x18008143c  mov     r11, rsp
0x18008143f  mov     [r11+8], rbx
0x180081443  mov     [r11+10h], rsi
0x180081447  mov     [r11+18h], rdi
0x18008144b  mov     [r11+20h], r9d
0x18008144f  push    rbp
0x180081450  push    r12
0x180081452  push    r13
0x180081454  push    r14
0x180081456  push    r15
0x180081458  mov     rbp, rsp
0x18008145b  sub     rsp, 80h
0x180081462  xor     r12d, r12d
0x180081465  lea     rax, [rbp+var_30]
0x180081469  mov     [r11-68h], rax
0x18008146d  mov     r15, r8
0x180081470  lea     rax, [rbp+hKey]
0x180081474  mov     [rbp+hKey], r12
0x180081478  mov     [r11-70h], rax
0x18008147c  mov     r13d, edx
0x18008147f  mov     [r11-78h], r12
0x180081483  lea     rdx, aSoftwareMicros_7; "SOFTWARE\\Microsoft\\TermServLicensing"...
0x18008148a  mov     rsi, rcx
0x18008148d  mov     [rsp+80h+samDesired], 20006h; samDesired
0x180081495  xor     r9d, r9d; lpClass
0x180081498  mov     [rsp+80h+dwOptions], r12d; dwOptions
0x18008149d  xor     r8d, r8d; Reserved
0x1800814a0  mov     [rbp+var_30], r12d
0x1800814a4  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800814ab  mov     edi, r12d
0x1800814ae  mov     r14d, r12d
0x1800814b1  call    cs:__imp_RegCreateKeyExW
0x1800814b8  nop     dword ptr [rax+rax+00h]
0x1800814bd  mov     ebx, eax
0x1800814bf  test    eax, eax
0x1800814c1  jz      short loc_1800814E5
0x1800814c3  movups  xmm0, cs:TLS_E_STORELSCERTIFICATE
0x1800814ca  mov     r8d, eax
0x1800814cd  lea     rcx, [rbp+var_20]; struct _EVENT_DESCRIPTOR
0x1800814d1  mov     edx, 0C0010014h; unsigned int
0x1800814d6  movdqu  xmmword ptr [rbp+var_20.Id], xmm0
0x1800814db  call    ?TLSLogEvent@@YAXU_EVENT_DESCRIPTOR@@KZZ; TLSLogEvent(_EVENT_DESCRIPTOR,ulong,...)
0x1800814e0  jmp     loc_1800816E4
0x1800814e5  mov     r12, [rbp+lpData]
0x1800814e9  test    r12, r12
0x1800814ec  jz      short loc_180081520
0x1800814ee  mov     eax, [rbp+cbData]
0x1800814f1  lea     rdx, aParm2; "Parm2"
0x1800814f8  mov     rcx, [rbp+hKey]; hKey
0x1800814fc  mov     r9d, 3; dwType
0x180081502  mov     [rsp+80h+samDesired], eax; cbData
0x180081506  xor     r8d, r8d; Reserved
0x180081509  mov     qword ptr [rsp+80h+dwOptions], r12; lpData
0x18008150e  call    cs:__imp_RegSetValueExW
0x180081515  nop     dword ptr [rax+rax+00h]
0x18008151a  mov     ebx, eax
0x18008151c  test    eax, eax
0x18008151e  jnz     short loc_1800814C3
0x180081520  test    r15, r15
0x180081523  jz      loc_18008165C
0x180081529  mov     rcx, [rbp+hKey]; hKey
0x18008152d  lea     rdx, aParm1; "Parm1"
0x180081534  mov     [rsp+80h+samDesired], r13d; cbData
0x180081539  mov     r9d, 3; dwType
0x18008153f  xor     r8d, r8d; Reserved
0x180081542  mov     qword ptr [rsp+80h+dwOptions], r15; csz
0x180081547  call    cs:__imp_RegSetValueExW
0x18008154e  nop     dword ptr [rax+rax+00h]
0x180081553  mov     ebx, eax
0x180081555  test    eax, eax
0x180081557  jnz     loc_1800814C3
0x18008155d  mov     r8d, r13d; cbCertEncoded
0x180081560  mov     rdx, r15; pbCertEncoded
0x180081563  lea     r13d, [rax+1]
0x180081567  mov     ecx, r13d; dwCertEncodingType
0x18008156a  call    cs:__imp_CertCreateCertificateContext
0x180081571  nop     dword ptr [rax+rax+00h]
0x180081576  mov     rdi, rax
0x180081579  test    rax, rax
0x18008157c  jnz     short loc_180081588
0x18008157e  mov     ebx, 80004005h
0x180081583  jmp     loc_1800816E4
0x180081588  mov     rdx, [rax+18h]
0x18008158c  xor     r9d, r9d; psz
0x18008158f  and     [rsp+80h+dwOptions], r14d
0x180081594  add     rdx, 50h ; 'P'; pName
0x180081598  mov     r8d, 8000003h; dwStrType
0x18008159e  mov     ecx, r13d; dwCertEncodingType
0x1800815a1  call    cs:__imp_CertNameToStrW
0x1800815a8  nop     dword ptr [rax+rax+00h]
0x1800815ad  mov     ebx, eax
0x1800815af  test    eax, eax
0x1800815b1  jz      loc_180081655
0x1800815b7  lea     edx, [rax+1]
0x1800815ba  mov     ecx, 40h ; '@'; uFlags
0x1800815bf  add     rdx, rdx; uBytes
0x1800815c2  call    cs:__imp_LocalAlloc
0x1800815c9  nop     dword ptr [rax+rax+00h]
0x1800815ce  mov     r14, rax
0x1800815d1  test    rax, rax
0x1800815d4  jz      short loc_18008164B
0x1800815d6  mov     rdx, [rdi+18h]
0x1800815da  mov     r9, rax; psz
0x1800815dd  add     rdx, 50h ; 'P'; pName
0x1800815e1  mov     [rsp+80h+dwOptions], ebx; csz
0x1800815e5  mov     r8d, 8000003h; dwStrType
0x1800815eb  mov     ecx, r13d; dwCertEncodingType
0x1800815ee  call    cs:__imp_CertNameToStrW
0x1800815f5  nop     dword ptr [rax+rax+00h]
0x1800815fa  lea     ecx, [rbx+2]
0x1800815fd  mov     r9d, 3; dwType
0x180081603  mov     [rsp+80h+samDesired], ecx; cbData
0x180081607  lea     rdx, aParm0; "Parm0"
0x18008160e  mov     rcx, [rbp+hKey]; hKey
0x180081612  xor     r8d, r8d; Reserved
0x180081615  mov     qword ptr [rsp+80h+dwOptions], r14; lpData
0x18008161a  call    cs:__imp_RegSetValueExW
0x180081621  nop     dword ptr [rax+rax+00h]
0x180081626  mov     ebx, eax
0x180081628  test    eax, eax
0x18008162a  jz      short loc_18008165C
0x18008162c  movups  xmm0, cs:TLS_E_STORELSCERTIFICATE
0x180081633  mov     r8d, eax
0x180081636  lea     rcx, [rbp+var_20]; struct _EVENT_DESCRIPTOR
0x18008163a  mov     edx, 0C0010014h; unsigned int
0x18008163f  movdqu  xmmword ptr [rbp+var_20.Id], xmm0
0x180081644  call    ?TLSLogEvent@@YAXU_EVENT_DESCRIPTOR@@KZZ; TLSLogEvent(_EVENT_DESCRIPTOR,ulong,...)
0x180081649  jmp     short loc_1800816C1
0x18008164b  mov     ebx, 8007000Eh
0x180081650  jmp     loc_1800816D5
0x180081655  mov     ebx, 80070057h
0x18008165a  jmp     short loc_1800816D5
0x18008165c  mov     rcx, [rbp+hKey]; hKey
0x180081660  test    rcx, rcx
0x180081663  jz      short loc_180081676
0x180081665  call    cs:__imp_RegCloseKey
0x18008166c  nop     dword ptr [rax+rax+00h]
0x180081671  and     [rbp+hKey], 0
0x180081676  test    r15, r15
0x180081679  jz      short loc_1800816BC
0x18008167b  test    r12, r12
0x18008167e  jz      short loc_1800816BC
0x180081680  mov     rcx, [rsi+20h]; hMem
0x180081684  test    rcx, rcx
0x180081687  jz      short loc_180081695
0x180081689  call    cs:__imp_LocalFree
0x180081690  nop     dword ptr [rax+rax+00h]
0x180081695  and     qword ptr [rsi+20h], 0
0x18008169a  mov     rcx, [rsi+30h]; hMem
0x18008169e  test    rcx, rcx
0x1800816a1  jz      short loc_1800816AF
0x1800816a3  call    cs:__imp_LocalFree
0x1800816aa  nop     dword ptr [rax+rax+00h]
0x1800816af  and     qword ptr [rsi+30h], 0
0x1800816b4  and     dword ptr [rsi+18h], 0
0x1800816b8  and     dword ptr [rsi+28h], 0
0x1800816bc  test    r14, r14
0x1800816bf  jz      short loc_1800816D0
0x1800816c1  mov     rcx, r14; hMem
0x1800816c4  call    cs:__imp_LocalFree
0x1800816cb  nop     dword ptr [rax+rax+00h]
0x1800816d0  test    rdi, rdi
0x1800816d3  jz      short loc_1800816E4
0x1800816d5  mov     rcx, rdi; pCertContext
0x1800816d8  call    cs:__imp_CertFreeCertificateContext
0x1800816df  nop     dword ptr [rax+rax+00h]
0x1800816e4  mov     rcx, [rbp+hKey]; hKey
0x1800816e8  test    rcx, rcx
0x1800816eb  jz      short loc_1800816F9
0x1800816ed  call    cs:__imp_RegCloseKey
0x1800816f4  nop     dword ptr [rax+rax+00h]
0x1800816f9  lea     r11, [rsp+80h+var_s0]
0x180081701  mov     eax, ebx
0x180081703  mov     rbx, [r11+30h]
0x180081707  mov     rsi, [r11+38h]
0x18008170b  mov     rdi, [r11+40h]
0x18008170f  mov     rsp, r11
0x180081712  pop     r15
0x180081714  pop     r14
0x180081716  pop     r13
0x180081718  pop     r12
0x18008171a  pop     rbp
0x18008171b  retn
```
