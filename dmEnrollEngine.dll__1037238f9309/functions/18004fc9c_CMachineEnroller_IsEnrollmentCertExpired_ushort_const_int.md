# CMachineEnroller::IsEnrollmentCertExpired(ushort const *,int *)

- ea: `0x18004fc9c`
- end: `0x18004ff15`
- name: `?IsEnrollmentCertExpired@CMachineEnroller@@CAJPEBGPEAH@Z`
- size: `633`
- prototype: `__int64 __fastcall(const unsigned __int16 *, int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18004f260`

## callees

- `0x1800067a0`
- `0x1800140d0`
- `0x18002e1a0`
- `0x18004fc9c`
- `0x1800521b0`
- `0x18006fdd8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004fd80`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004fd80`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x18004fd67`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x18004fd67`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18004fdbd`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18004fdbd`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x18004fdda`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x18004fdda`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18004fd76`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18004fd76`
- `CRYPT32!CertCloseStore` at `0x18004fed9`
- `CRYPT32!CertCloseStore` at `0x18004fed9`
- `CRYPT32!CertFreeCertificateContext` at `0x18004fec7`
- `CRYPT32!CertFreeCertificateContext` at `0x18004fec7`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CMachineEnroller::IsEnrollmentCertExpired(const unsigned __int16 *a1, int *a2)
{
  int v3; // r14d
  int InstalledCert; // eax
  __int64 v5; // rdx
  PCCERT_CONTEXT v6; // rdi
  signed int LastError; // eax
  int v8; // esi
  int v9; // ecx
  unsigned int v10; // ebx
  unsigned int *v12; // [rsp+20h] [rbp-E0h]
  unsigned int *v13; // [rsp+20h] [rbp-E0h]
  __int64 v14; // [rsp+28h] [rbp-D8h]
  __int64 v15; // [rsp+30h] [rbp-D0h]
  __int64 v16; // [rsp+38h] [rbp-C8h]
  __int64 v17; // [rsp+40h] [rbp-C0h]
  __int64 v18; // [rsp+48h] [rbp-B8h]
  int v19; // [rsp+50h] [rbp-B0h] BYREF
  FILETIME FileTime1; // [rsp+58h] [rbp-A8h] BYREF
  PCCERT_CONTEXT pCertContext; // [rsp+60h] [rbp-A0h] BYREF
  struct _FILETIME FileTime; // [rsp+68h] [rbp-98h] BYREF
  HCERTSTORE hCertStore; // [rsp+70h] [rbp-90h] BYREF
  _QWORD v24[2]; // [rsp+78h] [rbp-88h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+88h] [rbp-78h] BYREF
  struct _SYSTEMTIME v26; // [rsp+98h] [rbp-68h] BYREF
  unsigned __int16 v27[264]; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int16 v28[264]; // [rsp+2C0h] [rbp+1C0h] BYREF

  v3 = (int)a1;
  v19 = 0;
  hCertStore = 0;
  pCertContext = 0;
  SystemTime = 0;
  FileTime = 0;
  FileTime1 = 0;
  v26 = 0;
  v24[0] = "CMachineEnroller::IsEnrollmentCertExpired";
  v24[1] = &v19;
  v28[0] = 0;
  v27[0] = 0;
  InstalledCert = GetInstalledCert(a1, &hCertStore, &pCertContext, 0, 0);
  v19 = InstalledCert;
  v6 = pCertContext;
  if ( InstalledCert >= 0 )
  {
    GetSystemTime(&SystemTime);
    if ( SystemTimeToFileTime(&SystemTime, &FileTime) )
    {
      v8 = 0;
      FileTime1 = v6->pCertInfo->NotAfter;
      if ( CompareFileTime(&FileTime1, &FileTime) != 1 )
      {
        v8 = 1;
        if ( FileTimeToSystemTime(&FileTime1, &v26) )
        {
          LODWORD(v12) = v26.wMonth;
          v19 = StringCchPrintfW(
                  v28,
                  0x104u,
                  L"%04d-%02d-%02dT%02d:%02d:%02d.%02d",
                  v26.wYear,
                  v12,
                  v26.wDay,
                  v26.wHour,
                  v26.wMinute,
                  v26.wSecond,
                  v26.wMilliseconds);
          if ( v19 >= 0 )
          {
            LODWORD(v18) = SystemTime.wMilliseconds;
            LODWORD(v17) = SystemTime.wSecond;
            LODWORD(v16) = SystemTime.wMinute;
            LODWORD(v15) = SystemTime.wHour;
            LODWORD(v14) = SystemTime.wDay;
            LODWORD(v13) = SystemTime.wMonth;
            v19 = StringCchPrintfW(
                    v27,
                    0x104u,
                    L"%04d-%02d-%02dT%02d:%02d:%02d.%02d",
                    SystemTime.wYear,
                    v13,
                    v14,
                    v15,
                    v16,
                    v17,
                    v18);
            if ( v19 >= 0 && (Microsoft_Windows_DM_Enrollment_ProviderEnableBits & 4) != 0 )
              McTemplateU0zzz_EventWriteTransfer(v9, v5, v3, (unsigned int)v28, (__int64)v27);
          }
        }
      }
      *a2 = v8;
    }
    else
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      v19 = LastError;
    }
  }
  else if ( InstalledCert == -2146885628 )
  {
    v19 = -2145910748;
  }
  if ( v6 )
    CertFreeCertificateContext(v6);
  if ( hCertStore )
    CertCloseStore(hCertStore, 0);
  v10 = v19;
  EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v24, v5);
  return v10;
}

```

## disassembly

```asm
0x18004fc9c  mov     [rsp-8+arg_10], rbx
0x18004fca1  push    rbp
0x18004fca2  push    rsi
0x18004fca3  push    rdi
0x18004fca4  push    r14
0x18004fca6  push    r15
0x18004fca8  lea     rbp, [rsp-3E0h]
0x18004fcb0  sub     rsp, 4E0h
0x18004fcb7  mov     rax, cs:__security_cookie
0x18004fcbe  xor     rax, rsp
0x18004fcc1  mov     [rbp+400h+var_30], rax
0x18004fcc8  mov     r15, rdx
0x18004fccb  mov     r14, rcx
0x18004fcce  mov     [rsp+500h+var_4B0], 0
0x18004fcd6  mov     [rsp+500h+hCertStore], 0
0x18004fcdf  mov     [rsp+500h+pCertContext], 0
0x18004fce8  xorps   xmm0, xmm0
0x18004fceb  movups  xmmword ptr [rbp+400h+SystemTime.wYear], xmm0
0x18004fcef  mov     qword ptr [rsp+500h+FileTime.dwLowDateTime], 0
0x18004fcf8  mov     qword ptr [rsp+500h+FileTime1.dwLowDateTime], 0
0x18004fd01  movups  xmmword ptr [rbp+400h+var_468.wYear], xmm0
0x18004fd05  lea     rax, aCmachineenroll_9; "CMachineEnroller::IsEnrollmentCertExpir"...
0x18004fd0c  mov     [rsp+500h+var_488], rax
0x18004fd11  lea     rax, [rsp+500h+var_4B0]
0x18004fd16  mov     [rbp+400h+var_480], rax
0x18004fd1a  xor     eax, eax
0x18004fd1c  mov     [rbp+400h+var_240], ax
0x18004fd23  mov     [rbp+400h+var_450], ax
0x18004fd27  mov     [rsp+500h+var_4E0], rax; unsigned int *
0x18004fd2c  xor     r9d, r9d; int
0x18004fd2f  lea     r8, [rsp+500h+pCertContext]; struct _CERT_CONTEXT **
0x18004fd34  lea     rdx, [rsp+500h+hCertStore]; void **
0x18004fd39  call    ?GetInstalledCert@@YAJPEBGPEAPEAXPEAPEBU_CERT_CONTEXT@@HPEAK@Z; GetInstalledCert(ushort const *,void * *,_CERT_CONTEXT const * *,int,ulong *)
0x18004fd3e  mov     [rsp+500h+var_4B0], eax
0x18004fd42  mov     rdi, [rsp+500h+pCertContext]
0x18004fd47  test    eax, eax
0x18004fd49  jns     short loc_18004FD63
0x18004fd4b  cmp     eax, 80092004h
0x18004fd50  jnz     loc_18004FEBF
0x18004fd56  mov     [rsp+500h+var_4B0], 80180024h
0x18004fd5e  jmp     loc_18004FEBF
0x18004fd63  lea     rcx, [rbp+400h+SystemTime]; lpSystemTime
0x18004fd67  call    cs:__imp_GetSystemTime
0x18004fd6d  lea     rdx, [rsp+500h+FileTime]; lpFileTime
0x18004fd72  lea     rcx, [rbp+400h+SystemTime]; lpSystemTime
0x18004fd76  call    cs:__imp_SystemTimeToFileTime
0x18004fd7c  test    eax, eax
0x18004fd7e  jnz     short loc_18004FD9B
0x18004fd80  call    cs:__imp_GetLastError
0x18004fd86  test    eax, eax
0x18004fd88  jle     short loc_18004FD92
0x18004fd8a  movzx   eax, ax
0x18004fd8d  or      eax, 80070000h
0x18004fd92  mov     [rsp+500h+var_4B0], eax
0x18004fd96  jmp     loc_18004FEBF
0x18004fd9b  xor     esi, esi
0x18004fd9d  mov     rax, [rdi+18h]
0x18004fda1  mov     ecx, [rax+4Ch]
0x18004fda4  mov     [rsp+500h+FileTime1.dwHighDateTime], ecx
0x18004fda8  mov     rax, [rdi+18h]
0x18004fdac  mov     ecx, [rax+48h]
0x18004fdaf  mov     [rsp+500h+FileTime1.dwLowDateTime], ecx
0x18004fdb3  lea     rdx, [rsp+500h+FileTime]; lpFileTime2
0x18004fdb8  lea     rcx, [rsp+500h+FileTime1]; lpFileTime1
0x18004fdbd  call    cs:__imp_CompareFileTime
0x18004fdc3  cmp     eax, 1
0x18004fdc6  jz      loc_18004FEBC
0x18004fdcc  mov     esi, 1
0x18004fdd1  lea     rdx, [rbp+400h+var_468]; lpSystemTime
0x18004fdd5  lea     rcx, [rsp+500h+FileTime1]; lpFileTime
0x18004fdda  call    cs:__imp_FileTimeToSystemTime
0x18004fde0  test    eax, eax
0x18004fde2  jz      loc_18004FEBC
0x18004fde8  movzx   eax, [rbp+400h+var_468.wMilliseconds]
0x18004fdec  movzx   ecx, [rbp+400h+var_468.wSecond]
0x18004fdf0  movzx   edx, [rbp+400h+var_468.wMinute]
0x18004fdf4  movzx   r8d, [rbp+400h+var_468.wHour]
0x18004fdf9  movzx   r10d, [rbp+400h+var_468.wDay]
0x18004fdfe  movzx   r11d, [rbp+400h+var_468.wMonth]
0x18004fe03  movzx   r9d, [rbp+400h+var_468.wYear]
0x18004fe08  mov     dword ptr [rsp+500h+var_4B8], eax
0x18004fe0c  mov     dword ptr [rsp+500h+var_4C0], ecx
0x18004fe10  mov     dword ptr [rsp+500h+var_4C8], edx
0x18004fe14  mov     dword ptr [rsp+500h+var_4D0], r8d
0x18004fe19  mov     dword ptr [rsp+500h+var_4D8], r10d
0x18004fe1e  mov     dword ptr [rsp+500h+var_4E0], r11d
0x18004fe23  lea     r8, a04d02d02dt02d0; "%04d-%02d-%02dT%02d:%02d:%02d.%02d"
0x18004fe2a  mov     edx, 104h; unsigned __int64
0x18004fe2f  lea     rcx, [rbp+400h+var_240]; unsigned __int16 *
0x18004fe36  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004fe3b  mov     [rsp+500h+var_4B0], eax
0x18004fe3f  test    eax, eax
0x18004fe41  js      short loc_18004FEBC
0x18004fe43  movzx   eax, [rbp+400h+SystemTime.wMilliseconds]
0x18004fe47  movzx   ecx, [rbp+400h+SystemTime.wSecond]
0x18004fe4b  movzx   r8d, [rbp+400h+SystemTime.wMinute]
0x18004fe50  movzx   r10d, [rbp+400h+SystemTime.wHour]
0x18004fe55  movzx   r11d, [rbp+400h+SystemTime.wDay]
0x18004fe5a  movzx   ebx, [rbp+400h+SystemTime.wMonth]
0x18004fe5e  movzx   r9d, [rbp+400h+SystemTime.wYear]
0x18004fe63  mov     dword ptr [rsp+500h+var_4B8], eax
0x18004fe67  mov     dword ptr [rsp+500h+var_4C0], ecx
0x18004fe6b  mov     dword ptr [rsp+500h+var_4C8], r8d
0x18004fe70  mov     dword ptr [rsp+500h+var_4D0], r10d
0x18004fe75  mov     dword ptr [rsp+500h+var_4D8], r11d
0x18004fe7a  mov     dword ptr [rsp+500h+var_4E0], ebx
0x18004fe7e  lea     r8, a04d02d02dt02d0; "%04d-%02d-%02dT%02d:%02d:%02d.%02d"
0x18004fe85  mov     edx, 104h; unsigned __int64
0x18004fe8a  lea     rcx, [rbp+400h+var_450]; unsigned __int16 *
0x18004fe8e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004fe93  mov     [rsp+500h+var_4B0], eax
0x18004fe97  test    eax, eax
0x18004fe99  js      short loc_18004FEBC
0x18004fe9b  test    byte ptr cs:Microsoft_Windows_DM_Enrollment_ProviderEnableBits, 4
0x18004fea2  jz      short loc_18004FEBC
0x18004fea4  lea     rax, [rbp+400h+var_450]
0x18004fea8  mov     [rsp+500h+var_4E0], rax
0x18004fead  lea     r9, [rbp+400h+var_240]
0x18004feb4  mov     r8, r14
0x18004feb7  call    McTemplateU0zzz_EventWriteTransfer
0x18004febc  mov     [r15], esi
0x18004febf  test    rdi, rdi
0x18004fec2  jz      short loc_18004FECD
0x18004fec4  mov     rcx, rdi; pCertContext
0x18004fec7  call    cs:__imp_CertFreeCertificateContext
0x18004fecd  mov     rcx, [rsp+500h+hCertStore]; hCertStore
0x18004fed2  test    rcx, rcx
0x18004fed5  jz      short loc_18004FEDF
0x18004fed7  xor     edx, edx; dwFlags
0x18004fed9  call    cs:__imp_CertCloseStore
0x18004fedf  mov     ebx, [rsp+500h+var_4B0]
0x18004fee3  lea     rcx, [rsp+500h+var_488]; this
0x18004fee8  call    ??1EvtTraceScope@@QEAA@XZ; EvtTraceScope::~EvtTraceScope(void)
0x18004feed  mov     eax, ebx
0x18004feef  mov     rcx, [rbp+400h+var_30]
0x18004fef6  xor     rcx, rsp; StackCookie
0x18004fef9  call    __security_check_cookie
0x18004fefe  mov     rbx, [rsp+500h+arg_10]
0x18004ff06  add     rsp, 4E0h
0x18004ff0d  pop     r15
0x18004ff0f  pop     r14
0x18004ff11  pop     rdi
0x18004ff12  pop     rsi
0x18004ff13  pop     rbp
0x18004ff14  retn
```
