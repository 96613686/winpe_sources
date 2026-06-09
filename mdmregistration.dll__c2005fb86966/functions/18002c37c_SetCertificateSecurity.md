# SetCertificateSecurity

- ea: `0x18002c37c`
- end: `0x18002c5c4`
- name: `SetCertificateSecurity`
- size: `584`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18002c808`

## callees

- `0x1800026d0`
- `0x1800141b0`
- `0x180027e0c`
- `0x18002b0ac`
- `0x18002c37c`
- `0x18003b750`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c4cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c4cf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002c559`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002c559`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x18002c474`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x18002c474`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x18002c51a`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x18002c51a`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18002c4bf`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18002c4bf`
- `DMCmnUtils!EncodeBase64W` at `0x18002c43a`
- `DMCmnUtils!EncodeBase64W` at `0x18002c43a`
- `CRYPT32!CertFreeCertificateContext` at `0x18002c58c`
- `CRYPT32!CertFreeCertificateContext` at `0x18002c58c`
- `CRYPT32!CertCloseStore` at `0x18002c578`
- `CRYPT32!CertCloseStore` at `0x18002c578`

## string_xrefs

- `0x18002c455`: `//wsse:BinarySecurityToken`
- `0x18002c3ec`: `SetCertificateSecurity`
- `0x18002c49c`: `//wsse:Security//u:Timestamp//u:Created`
- `0x18002c542`: `//wsse:Security//u:Timestamp//u:Expires`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SetCertificateSecurity(struct IXMLDOMDocument2 *a1, const unsigned __int16 *a2, __int64 a3, int a4)
{
  struct _CERT_CONTEXT *v4; // rbx
  signed int LastError; // eax
  unsigned int v6; // ebx
  unsigned int *v8; // [rsp+20h] [rbp-89h]
  int InstalledCert; // [rsp+30h] [rbp-79h] BYREF
  struct _CERT_CONTEXT *v10; // [rsp+38h] [rbp-71h] BYREF
  struct _FILETIME FileTime; // [rsp+40h] [rbp-69h] BYREF
  HLOCAL hMem; // [rsp+48h] [rbp-61h] BYREF
  struct IXMLDOMDocument2 *v13; // [rsp+50h] [rbp-59h] BYREF
  HCERTSTORE hCertStore; // [rsp+58h] [rbp-51h] BYREF
  _QWORD v15[2]; // [rsp+60h] [rbp-49h] BYREF
  _SYSTEMTIME SystemTime; // [rsp+70h] [rbp-39h] BYREF
  struct _SYSTEMTIME v17; // [rsp+80h] [rbp-29h] BYREF
  unsigned __int16 v18[8]; // [rsp+90h] [rbp-19h] BYREF
  _BYTE v19[26]; // [rsp+A0h] [rbp-9h] BYREF
  unsigned __int16 v20[8]; // [rsp+C0h] [rbp+17h] BYREF
  _BYTE v21[26]; // [rsp+D0h] [rbp+27h] BYREF

  v13 = a1;
  InstalledCert = 0;
  hMem = 0;
  hCertStore = 0;
  v4 = 0;
  v10 = 0;
  FileTime = 0;
  SystemTime = 0;
  v17 = 0;
  *(_OWORD *)v18 = 0;
  memset(v19, 0, sizeof(v19));
  *(_OWORD *)v20 = 0;
  memset(v21, 0, sizeof(v21));
  v15[0] = "SetCertificateSecurity";
  v15[1] = &InstalledCert;
  if ( !a2 )
  {
    InstalledCert = -2147024809;
    goto LABEL_15;
  }
  InstalledCert = GetInstalledCert(a2, &hCertStore, (const struct _CERT_CONTEXT **)&v10, a4, v8);
  v4 = v10;
  if ( InstalledCert >= 0 )
  {
    InstalledCert = EncodeBase64W(v10->pbCertEncoded, v10->cbCertEncoded, (unsigned __int16 **)&hMem);
    if ( InstalledCert >= 0 )
    {
      InstalledCert = HlpSetNodeString(&v13, L"//wsse:BinarySecurityToken", (const unsigned __int16 *)hMem);
      if ( InstalledCert >= 0 )
      {
        GetSystemTime(&SystemTime);
        InstalledCert = FormatTimeStamp(&SystemTime, v18);
        if ( InstalledCert >= 0 )
        {
          InstalledCert = HlpSetNodeString(&v13, L"//wsse:Security//u:Timestamp//u:Created", v18);
          if ( InstalledCert >= 0 )
          {
            if ( SystemTimeToFileTime(&SystemTime, &FileTime)
              && (v10 = (struct _CERT_CONTEXT *)(*(_QWORD *)&FileTime + 3000000000LL),
                  *(_QWORD *)&FileTime += 3000000000LL,
                  FileTimeToSystemTime(&FileTime, &v17)) )
            {
              InstalledCert = FormatTimeStamp(&v17, v20);
              if ( InstalledCert < 0 )
                goto LABEL_15;
              LastError = HlpSetNodeString(&v13, L"//wsse:Security//u:Timestamp//u:Expires", v20);
            }
            else
            {
              LastError = GetLastError();
              if ( LastError > 0 )
                LastError = (unsigned __int16)LastError | 0x80070000;
            }
            InstalledCert = LastError;
          }
        }
      }
    }
  }
LABEL_15:
  LocalFree(hMem);
  hMem = 0;
  if ( hCertStore )
    CertCloseStore(hCertStore, 0);
  if ( v4 )
    CertFreeCertificateContext(v4);
  v6 = InstalledCert;
  EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v15);
  return v6;
}

```

## disassembly

```asm
0x18002c37c  mov     [rsp-8+arg_10], rbx
0x18002c381  push    rbp
0x18002c382  lea     rbp, [rsp-57h]
0x18002c387  sub     rsp, 100h
0x18002c38e  mov     rax, cs:__security_cookie
0x18002c395  xor     rax, rsp
0x18002c398  mov     [rbp+57h+var_10], rax
0x18002c39c  mov     rax, rdx
0x18002c39f  mov     [rbp+57h+var_B0], rcx
0x18002c3a3  mov     [rbp+57h+var_D0], 0
0x18002c3aa  mov     [rbp+57h+hMem], 0
0x18002c3b2  mov     [rbp+57h+hCertStore], 0
0x18002c3ba  xor     ebx, ebx
0x18002c3bc  mov     [rbp+57h+var_C8], rbx
0x18002c3c0  mov     qword ptr [rbp+57h+FileTime.dwLowDateTime], rbx
0x18002c3c4  xorps   xmm0, xmm0
0x18002c3c7  movups  xmmword ptr [rbp+57h+SystemTime.wYear], xmm0
0x18002c3cb  xorps   xmm1, xmm1
0x18002c3ce  movups  xmmword ptr [rbp+57h+var_80.wYear], xmm1
0x18002c3d2  xor     ecx, ecx
0x18002c3d4  movups  xmmword ptr [rbp+57h+var_70], xmm0
0x18002c3d8  movups  xmmword ptr [rbp+57h+var_60], xmm0
0x18002c3dc  movups  xmmword ptr [rbp+57h+var_60+0Ah], xmm0
0x18002c3e0  movups  xmmword ptr [rbp+57h+var_40], xmm1
0x18002c3e4  movups  xmmword ptr [rbp+57h+var_30], xmm1
0x18002c3e8  movups  xmmword ptr [rbp+57h+var_30+0Ah], xmm1
0x18002c3ec  lea     rcx, aSetcertificate; "SetCertificateSecurity"
0x18002c3f3  mov     [rbp+57h+var_A0], rcx
0x18002c3f7  lea     rcx, [rbp+57h+var_D0]
0x18002c3fb  mov     [rbp+57h+var_98], rcx
0x18002c3ff  test    rdx, rdx
0x18002c402  jnz     short loc_18002C410
0x18002c404  mov     [rbp+57h+var_D0], 80070057h
0x18002c40b  jmp     loc_18002C555
0x18002c410  lea     r8, [rbp+57h+var_C8]; struct _CERT_CONTEXT **
0x18002c414  lea     rdx, [rbp+57h+hCertStore]; void **
0x18002c418  mov     rcx, rax; unsigned __int16 *
0x18002c41b  call    ?GetInstalledCert@@YAJPEBGPEAPEAXPEAPEBU_CERT_CONTEXT@@HPEAK@Z; GetInstalledCert(ushort const *,void * *,_CERT_CONTEXT const * *,int,ulong *)
0x18002c420  mov     [rbp+57h+var_D0], eax
0x18002c423  mov     rbx, [rbp+57h+var_C8]
0x18002c427  test    eax, eax
0x18002c429  js      loc_18002C555
0x18002c42f  lea     r8, [rbp+57h+hMem]
0x18002c433  mov     edx, [rbx+10h]
0x18002c436  mov     rcx, [rbx+8]
0x18002c43a  call    cs:__imp_?EncodeBase64W@@YAJPEBEHPEAPEAG@Z; EncodeBase64W(uchar const *,int,ushort * *)
0x18002c441  nop     dword ptr [rax+rax+00h]
0x18002c446  mov     [rbp+57h+var_D0], eax
0x18002c449  test    eax, eax
0x18002c44b  js      loc_18002C555
0x18002c451  mov     r8, [rbp+57h+hMem]; unsigned __int16 *
0x18002c455  lea     rdx, aWsseBinarysecu; "//wsse:BinarySecurityToken"
0x18002c45c  lea     rcx, [rbp+57h+var_B0]; struct IXMLDOMDocument2 **
0x18002c460  call    ?HlpSetNodeString@@YAJPEAPEAUIXMLDOMDocument2@@PEBG1@Z; HlpSetNodeString(IXMLDOMDocument2 * *,ushort const *,ushort const *)
0x18002c465  mov     [rbp+57h+var_D0], eax
0x18002c468  test    eax, eax
0x18002c46a  js      loc_18002C555
0x18002c470  lea     rcx, [rbp+57h+SystemTime]; lpSystemTime
0x18002c474  call    cs:__imp_GetSystemTime
0x18002c47b  nop     dword ptr [rax+rax+00h]
0x18002c480  lea     rdx, [rbp+57h+var_70]
0x18002c484  lea     rcx, [rbp+57h+SystemTime]
0x18002c488  call    FormatTimeStamp
0x18002c48d  mov     [rbp+57h+var_D0], eax
0x18002c490  test    eax, eax
0x18002c492  js      loc_18002C555
0x18002c498  lea     r8, [rbp+57h+var_70]; unsigned __int16 *
0x18002c49c  lea     rdx, aWsseSecurityUT_0; "//wsse:Security//u:Timestamp//u:Created"
0x18002c4a3  lea     rcx, [rbp+57h+var_B0]; struct IXMLDOMDocument2 **
0x18002c4a7  call    ?HlpSetNodeString@@YAJPEAPEAUIXMLDOMDocument2@@PEBG1@Z; HlpSetNodeString(IXMLDOMDocument2 * *,ushort const *,ushort const *)
0x18002c4ac  mov     [rbp+57h+var_D0], eax
0x18002c4af  test    eax, eax
0x18002c4b1  js      loc_18002C555
0x18002c4b7  lea     rdx, [rbp+57h+FileTime]; lpFileTime
0x18002c4bb  lea     rcx, [rbp+57h+SystemTime]; lpSystemTime
0x18002c4bf  call    cs:__imp_SystemTimeToFileTime
0x18002c4c6  nop     dword ptr [rax+rax+00h]
0x18002c4cb  test    eax, eax
0x18002c4cd  jnz     short loc_18002C4E9
0x18002c4cf  call    cs:__imp_GetLastError
0x18002c4d6  nop     dword ptr [rax+rax+00h]
0x18002c4db  test    eax, eax
0x18002c4dd  jle     short loc_18002C552
0x18002c4df  movzx   eax, ax
0x18002c4e2  or      eax, 80070000h
0x18002c4e7  jmp     short loc_18002C552
0x18002c4e9  mov     eax, [rbp+57h+FileTime.dwHighDateTime]
0x18002c4ec  mov     dword ptr [rbp+57h+var_C8+4], eax
0x18002c4ef  mov     eax, [rbp+57h+FileTime.dwLowDateTime]
0x18002c4f2  mov     dword ptr [rbp+57h+var_C8], eax
0x18002c4f5  mov     ecx, 0B2D05E00h
0x18002c4fa  mov     rax, [rbp+57h+var_C8]
0x18002c4fe  add     rax, rcx
0x18002c501  mov     [rbp+57h+var_C8], rax
0x18002c505  shr     rax, 20h
0x18002c509  mov     [rbp+57h+FileTime.dwHighDateTime], eax
0x18002c50c  mov     eax, dword ptr [rbp+57h+var_C8]
0x18002c50f  mov     [rbp+57h+FileTime.dwLowDateTime], eax
0x18002c512  lea     rdx, [rbp+57h+var_80]; lpSystemTime
0x18002c516  lea     rcx, [rbp+57h+FileTime]; lpFileTime
0x18002c51a  call    cs:__imp_FileTimeToSystemTime
0x18002c521  nop     dword ptr [rax+rax+00h]
0x18002c526  test    eax, eax
0x18002c528  jz      short loc_18002C4CF
0x18002c52a  lea     rdx, [rbp+57h+var_40]
0x18002c52e  lea     rcx, [rbp+57h+var_80]
0x18002c532  call    FormatTimeStamp
0x18002c537  mov     [rbp+57h+var_D0], eax
0x18002c53a  test    eax, eax
0x18002c53c  js      short loc_18002C555
0x18002c53e  lea     r8, [rbp+57h+var_40]; unsigned __int16 *
0x18002c542  lea     rdx, aWsseSecurityUT; "//wsse:Security//u:Timestamp//u:Expires"
0x18002c549  lea     rcx, [rbp+57h+var_B0]; struct IXMLDOMDocument2 **
0x18002c54d  call    ?HlpSetNodeString@@YAJPEAPEAUIXMLDOMDocument2@@PEBG1@Z; HlpSetNodeString(IXMLDOMDocument2 * *,ushort const *,ushort const *)
0x18002c552  mov     [rbp+57h+var_D0], eax
0x18002c555  mov     rcx, [rbp+57h+hMem]; hMem
0x18002c559  call    cs:__imp_LocalFree
0x18002c560  nop     dword ptr [rax+rax+00h]
0x18002c565  mov     [rbp+57h+hMem], 0
0x18002c56d  mov     rcx, [rbp+57h+hCertStore]; hCertStore
0x18002c571  test    rcx, rcx
0x18002c574  jz      short loc_18002C584
0x18002c576  xor     edx, edx; dwFlags
0x18002c578  call    cs:__imp_CertCloseStore
0x18002c57f  nop     dword ptr [rax+rax+00h]
0x18002c584  test    rbx, rbx
0x18002c587  jz      short loc_18002C598
0x18002c589  mov     rcx, rbx; pCertContext
0x18002c58c  call    cs:__imp_CertFreeCertificateContext
0x18002c593  nop     dword ptr [rax+rax+00h]
0x18002c598  mov     ebx, [rbp+57h+var_D0]
0x18002c59b  lea     rcx, [rbp+57h+var_A0]; this
0x18002c59f  call    ??1EvtTraceScope@@QEAA@XZ; EvtTraceScope::~EvtTraceScope(void)
0x18002c5a4  mov     eax, ebx
0x18002c5a6  mov     rcx, [rbp+57h+var_10]
0x18002c5aa  xor     rcx, rsp; StackCookie
0x18002c5ad  call    __security_check_cookie
0x18002c5b2  mov     rbx, [rsp+100h+arg_10]
0x18002c5ba  add     rsp, 100h
0x18002c5c1  pop     rbp
0x18002c5c2  retn
```
