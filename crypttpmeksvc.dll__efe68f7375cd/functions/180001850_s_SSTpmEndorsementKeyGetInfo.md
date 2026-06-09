# s_SSTpmEndorsementKeyGetInfo

- ea: `0x180001850`
- end: `0x18000195b`
- name: `s_SSTpmEndorsementKeyGetInfo`
- size: `267`
- prototype: `__int64 __fastcall(__int64, const unsigned __int16 *, DWORD, const BYTE *, unsigned __int16 *, int, unsigned int *, unsigned __int8 **, unsigned int *, unsigned __int8 **)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180001850`
- `0x180001970`
- `0x180003750`

## import_xrefs

- `CRYPT32!CertFreeCertificateContext` at `0x180001948`
- `CRYPT32!CertFreeCertificateContext` at `0x180001948`
- `CRYPT32!CertCreateCertificateContext` at `0x180001892`
- `CRYPT32!CertCreateCertificateContext` at `0x180001892`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800018a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800018a0`

## pseudocode

```c
__int64 __fastcall s_SSTpmEndorsementKeyGetInfo(
        __int64 a1,
        const unsigned __int16 *a2,
        DWORD a3,
        const BYTE *a4,
        unsigned __int16 *a5,
        int a6,
        unsigned int *a7,
        unsigned __int8 **a8,
        unsigned int *a9,
        unsigned __int8 **a10)
{
  const struct _CERT_CONTEXT *CertificateContext; // rax
  const CERT_CONTEXT *v13; // rdi
  DWORD LastError; // ebx
  unsigned int EkInfo; // eax

  if ( a1 )
  {
    CertificateContext = CertCreateCertificateContext(1u, a4, a3);
    v13 = CertificateContext;
    if ( CertificateContext )
    {
      EkInfo = _GetEkInfo(0, a2, 0, CertificateContext, a5, a6, a7, a8, a9, a10);
      LastError = EkInfo;
      if ( EkInfo )
        ekTraceFmt(0xA7812C2u, 1u, "ERROR: _GetEkInfo. Return=%x\n", EkInfo);
      else
        LastError = 0;
      CertFreeCertificateContext(v13);
    }
    else
    {
      LastError = GetLastError();
      ekTraceFmt(0xA6712C2u, 1u, "ERROR: Invalid exchange certificate. Return=%d", LastError);
    }
    return LastError;
  }
  else
  {
    ekTraceFmt(0xA5D12C2u, 1u, "ERROR: Arguments. Return=%d\n", 160);
    return 160;
  }
}

```

## disassembly

```asm
0x180001850  push    rbx
0x180001852  sub     rsp, 50h
0x180001856  mov     rbx, rdx
0x180001859  test    rcx, rcx
0x18000185c  jnz     short loc_180001885
0x18000185e  mov     r9d, 0A0h
0x180001864  lea     r8, aErrorArguments; "ERROR: Arguments. Return=%d\n"
0x18000186b  mov     edx, 1; unsigned int
0x180001870  mov     ecx, 0A5D12C2h; unsigned int
0x180001875  call    ?ekTraceFmt@@YAXKKPEBDZZ; ekTraceFmt(ulong,ulong,char const *,...)
0x18000187a  mov     eax, 0A0h
0x18000187f  add     rsp, 50h
0x180001883  pop     rbx
0x180001884  retn
0x180001885  mov     rdx, r9; pbCertEncoded
0x180001888  mov     [rsp+58h+arg_0], rdi
0x18000188d  mov     ecx, 1; dwCertEncodingType
0x180001892  call    cs:__imp_CertCreateCertificateContext
0x180001898  mov     rdi, rax
0x18000189b  test    rax, rax
0x18000189e  jnz     short loc_1800018C6
0x1800018a0  call    cs:__imp_GetLastError
0x1800018a6  lea     r8, aErrorInvalidEx; "ERROR: Invalid exchange certificate. Re"...
0x1800018ad  mov     edx, 1; unsigned int
0x1800018b2  mov     r9d, eax
0x1800018b5  mov     ecx, 0A6712C2h; unsigned int
0x1800018ba  mov     ebx, eax
0x1800018bc  call    ?ekTraceFmt@@YAXKKPEBDZZ; ekTraceFmt(ulong,ulong,char const *,...)
0x1800018c1  jmp     loc_18000194E
0x1800018c6  mov     rax, [rsp+58h+arg_48]
0x1800018ce  mov     r9, rdi; struct _CERT_CONTEXT *
0x1800018d1  mov     [rsp+58h+var_10], rax; unsigned __int8 **
0x1800018d6  xor     r8d, r8d; unsigned __int64
0x1800018d9  mov     rax, [rsp+58h+arg_40]
0x1800018e1  mov     rdx, rbx; unsigned __int16 *
0x1800018e4  mov     [rsp+58h+var_18], rax; unsigned int *
0x1800018e9  xor     ecx, ecx; bool
0x1800018eb  mov     rax, [rsp+58h+arg_38]
0x1800018f3  mov     [rsp+58h+var_20], rax; unsigned __int8 **
0x1800018f8  mov     rax, [rsp+58h+arg_30]
0x180001900  mov     [rsp+58h+var_28], rax; unsigned int *
0x180001905  mov     eax, [rsp+58h+arg_28]
0x18000190c  mov     [rsp+58h+var_30], eax; int
0x180001910  mov     rax, [rsp+58h+arg_20]
0x180001918  mov     [rsp+58h+var_38], rax; unsigned __int16 *
0x18000191d  call    ?_GetEkInfo@@YAK_NPEBG_KPEBU_CERT_CONTEXT@@1JPEAKPEAPEAE45@Z; _GetEkInfo(bool,ushort const *,unsigned __int64,_CERT_CONTEXT const *,ushort const *,long,ulong *,uchar * *,ulong *,uchar * *)
0x180001922  mov     ebx, eax
0x180001924  test    eax, eax
0x180001926  jz      short loc_180001943
0x180001928  mov     r9d, eax
0x18000192b  lea     r8, aErrorGetekinfo; "ERROR: _GetEkInfo. Return=%x\n"
0x180001932  mov     edx, 1; unsigned int
0x180001937  mov     ecx, 0A7812C2h; unsigned int
0x18000193c  call    ?ekTraceFmt@@YAXKKPEBDZZ; ekTraceFmt(ulong,ulong,char const *,...)
0x180001941  jmp     short loc_180001945
0x180001943  xor     ebx, ebx
0x180001945  mov     rcx, rdi; pCertContext
0x180001948  call    cs:__imp_CertFreeCertificateContext
0x18000194e  mov     rdi, [rsp+58h+arg_0]
0x180001953  mov     eax, ebx
0x180001955  add     rsp, 50h
0x180001959  pop     rbx
0x18000195a  retn
```
