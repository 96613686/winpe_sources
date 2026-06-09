# RegistrationCertStatus::GetTenantId(_CERT_CONTEXT const *,ushort * *,int *)

- ea: `0x180025c90`
- end: `0x180025da8`
- name: `?GetTenantId@RegistrationCertStatus@@SAJPEBU_CERT_CONTEXT@@PEAPEAGPEAH@Z`
- size: `280`
- prototype: `__int64 __fastcall(const struct _CERT_CONTEXT *, unsigned __int16 **, int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, loader_planting`

## callers

- `0x1800246a0`

## callees

- `0x18000febc`
- `0x18000ff18`
- `0x180010218`
- `0x18001029c`
- `0x180013bd0`
- `0x180024a28`
- `0x180025c90`

## string_xrefs

- `0x180025d58`: `CopyStringW`
- `0x180025d01`: `RegistrationCertStatus::GetTenantIdExtensionValue`

## pseudocode

```c
__int64 __fastcall RegistrationCertStatus::GetTenantId(const struct _CERT_CONTEXT *a1, unsigned __int16 **a2, int *a3)
{
  __int64 ExtensionGuidValueByOid; // rbx
  const wchar_t *v6; // rbp

  if ( a3 )
    *a3 = 0;
  if ( !a2 )
  {
    LODWORD(ExtensionGuidValueByOid) = -2147024809;
    Logger::TraceError(L"%s: \"%s\" should not be null.", L"RegistrationCertStatus::GetTenantId", L"ppszOutBuffer");
    Logger::WriteNullOrEmptyParameterFailureEvent(L"RegistrationCertStatus::GetTenantId", L"ppszOutBuffer");
    goto LABEL_12;
  }
  *a2 = 0;
  v6 = L"RegistrationCertStatus::GetTenantIdExtensionValue";
  ExtensionGuidValueByOid = (unsigned int)CertificateUtil::FindExtensionGuidValueByOid(
                                            "1.2.840.113556.1.5.284.5",
                                            a1,
                                            a2);
  Logger::TraceVerbose(
    L"%s - hr: 0x%08x",
    L"RegistrationCertStatus::GetTenantIdExtensionValue",
    ExtensionGuidValueByOid);
  if ( (_DWORD)ExtensionGuidValueByOid != -2146885628 )
  {
    if ( (int)ExtensionGuidValueByOid >= 0 )
      goto LABEL_12;
LABEL_11:
    Logger::TraceError(
      L"%s: %s failed with error code: 0x%08x.",
      L"RegistrationCertStatus::GetTenantId",
      v6,
      (unsigned int)ExtensionGuidValueByOid);
    operator delete(*a2);
    *a2 = 0;
    goto LABEL_12;
  }
  if ( a3 )
    *a3 = 1;
  operator delete(*a2);
  *a2 = 0;
  LODWORD(ExtensionGuidValueByOid) = CopyStringW(L"383a3889-5bc9-47a3-846c-2b70f0b7fe0e", 36, a2);
  if ( (int)ExtensionGuidValueByOid < 0 )
  {
    v6 = L"CopyStringW";
    goto LABEL_11;
  }
LABEL_12:
  Logger::TraceVerbose(
    L"%s - hr: 0x%08x",
    L"RegistrationCertStatus::GetTenantId",
    (unsigned int)ExtensionGuidValueByOid);
  return (unsigned int)ExtensionGuidValueByOid;
}

```

## disassembly

```asm
0x180025c90  push    rbx
0x180025c92  push    rbp
0x180025c93  push    rsi
0x180025c94  push    rdi
0x180025c95  push    r15
0x180025c97  sub     rsp, 20h
0x180025c9b  mov     rsi, r8
0x180025c9e  mov     rdi, rdx
0x180025ca1  test    r8, r8
0x180025ca4  jz      short loc_180025CAD
0x180025ca6  mov     dword ptr [r8], 0
0x180025cad  lea     r15, aRegistrationce_3; "RegistrationCertStatus::GetTenantId"
0x180025cb4  test    rdi, rdi
0x180025cb7  jnz     short loc_180025CE8
0x180025cb9  lea     r8, aPpszoutbuffer; "ppszOutBuffer"
0x180025cc0  mov     rdx, r15
0x180025cc3  lea     rcx, aSSShouldNotBeN; "%s: \"%s\" should not be null."
0x180025cca  mov     ebx, 80070057h
0x180025ccf  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180025cd4  lea     rdx, aPpszoutbuffer; "ppszOutBuffer"
0x180025cdb  mov     rcx, r15; unsigned __int16 *
0x180025cde  call    ?WriteNullOrEmptyParameterFailureEvent@Logger@@SAJPEBG0@Z; Logger::WriteNullOrEmptyParameterFailureEvent(ushort const *,ushort const *)
0x180025ce3  jmp     loc_180025D89
0x180025ce8  mov     qword ptr [rdx], 0
0x180025cef  mov     r8, rdi; unsigned __int16 **
0x180025cf2  mov     rdx, rcx; struct _CERT_CONTEXT *
0x180025cf5  lea     rcx, a12840113556152; "1.2.840.113556.1.5.284.5"
0x180025cfc  call    ?FindExtensionGuidValueByOid@CertificateUtil@@SAJPEBDPEBU_CERT_CONTEXT@@PEAPEAG@Z; CertificateUtil::FindExtensionGuidValueByOid(char const *,_CERT_CONTEXT const *,ushort * *)
0x180025d01  lea     rbp, aRegistrationce; "RegistrationCertStatus::GetTenantIdExte"...
0x180025d08  mov     r8d, eax
0x180025d0b  mov     rdx, rbp
0x180025d0e  lea     rcx, aSHr0x08x; "%s - hr: 0x%08x"
0x180025d15  mov     ebx, eax
0x180025d17  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x180025d1c  cmp     ebx, 80092004h
0x180025d22  jnz     short loc_180025D61
0x180025d24  test    rsi, rsi
0x180025d27  jz      short loc_180025D2F
0x180025d29  mov     dword ptr [rsi], 1
0x180025d2f  mov     rcx, [rdi]; Block
0x180025d32  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180025d37  mov     r8, rdi; unsigned __int16 **
0x180025d3a  mov     qword ptr [rdi], 0
0x180025d41  mov     edx, 24h ; '$'; unsigned __int64
0x180025d46  lea     rcx, a383a38895bc947; "383a3889-5bc9-47a3-846c-2b70f0b7fe0e"
0x180025d4d  call    ?CopyStringW@@YAJPEBG_KPEAPEAG@Z; CopyStringW(ushort const *,unsigned __int64,ushort * *)
0x180025d52  mov     ebx, eax
0x180025d54  test    eax, eax
0x180025d56  jns     short loc_180025D89
0x180025d58  lea     rbp, aCopystringw; "CopyStringW"
0x180025d5f  jmp     short loc_180025D65
0x180025d61  test    ebx, ebx
0x180025d63  jns     short loc_180025D89
0x180025d65  mov     rdx, r15
0x180025d68  lea     rcx, aSSFailedWithEr_0; "%s: %s failed with error code: 0x%08x."
0x180025d6f  mov     r9d, ebx
0x180025d72  mov     r8, rbp
0x180025d75  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180025d7a  mov     rcx, [rdi]; Block
0x180025d7d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180025d82  mov     qword ptr [rdi], 0
0x180025d89  mov     r8d, ebx
0x180025d8c  lea     rcx, aSHr0x08x; "%s - hr: 0x%08x"
0x180025d93  mov     rdx, r15
0x180025d96  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x180025d9b  mov     eax, ebx
0x180025d9d  add     rsp, 20h
0x180025da1  pop     r15
0x180025da3  pop     rdi
0x180025da4  pop     rsi
0x180025da5  pop     rbp
0x180025da6  pop     rbx
0x180025da7  retn
```
