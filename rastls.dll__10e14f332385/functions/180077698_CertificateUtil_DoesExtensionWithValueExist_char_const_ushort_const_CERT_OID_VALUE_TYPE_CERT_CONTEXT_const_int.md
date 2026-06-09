# CertificateUtil::DoesExtensionWithValueExist(char const *,ushort const *,_CERT_OID_VALUE_TYPE,_CERT_CONTEXT const *,int *)

- ea: `0x180077698`
- end: `0x180077830`
- name: `?DoesExtensionWithValueExist@CertificateUtil@@SAJPEBDPEBGW4_CERT_OID_VALUE_TYPE@@PEBU_CERT_CONTEXT@@PEAH@Z`
- size: `408`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, loader_planting`

## callers

- `0x180077838`

## callees

- `0x18002c90c`
- `0x18002ce0c`
- `0x180035664`
- `0x180077698`
- `0x180077e0c`
- `0x180077fe8`

## import_xrefs

- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180077804`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180077804`

## string_xrefs

- `0x1800776c4`: `CertificateUtil::DoesExtensionWithValueExist`
- `0x1800776de`: `CertificateUtil::DoesExtensionWithValueExist`
- `0x180077700`: `CertificateUtil::DoesExtensionWithValueExist`
- `0x18007772d`: `CertificateUtil::DoesExtensionWithValueExist`
- `0x18007775f`: `CertificateUtil::DoesExtensionWithValueExist`
- `0x18007778f`: `CertificateUtil::DoesExtensionWithValueExist`
- `0x1800777e7`: `CertificateUtil::DoesExtensionWithValueExist`
- `0x1800777b6`: `CertificateUtil::FindExtensionGuidValueByOid`
- `0x1800777cc`: `CertificateUtil::FindExtensionStrValueByOid`

## pseudocode

```c
__int64 __fastcall CertificateUtil::DoesExtensionWithValueExist(
        const char *a1,
        const WCHAR *a2,
        int a3,
        const struct _CERT_CONTEXT *a4,
        _DWORD *a5)
{
  unsigned int v6; // ebx
  const unsigned __int16 *v7; // rdx
  _DWORD *v8; // rdi
  int ExtensionGuidValueByOid; // eax
  const unsigned __int16 *v10; // r8
  LPCWSTR lpString1; // [rsp+30h] [rbp+8h] BYREF

  lpString1 = 0;
  if ( !a1 )
  {
    v6 = -2147024809;
    Logger::TraceError(L"%s: \"%s\" should not be null.", L"CertificateUtil::DoesExtensionWithValueExist", L"pcszOid");
    v7 = L"pcszOid";
LABEL_3:
    Logger::WriteNullOrEmptyParameterFailureEvent(L"CertificateUtil::DoesExtensionWithValueExist", v7);
    goto LABEL_21;
  }
  if ( !a2 )
  {
    v6 = -2147024809;
    Logger::TraceError(
      L"%s: \"%s\" should not be null.",
      L"CertificateUtil::DoesExtensionWithValueExist",
      L"pcszOidValue");
    v7 = L"pcszOidValue";
    goto LABEL_3;
  }
  if ( !a4 )
  {
    v6 = -2147024809;
    Logger::TraceError(
      L"%s: \"%s\" should not be null.",
      L"CertificateUtil::DoesExtensionWithValueExist",
      &stru_180087E98);
    v7 = (const unsigned __int16 *)&stru_180087E98;
    goto LABEL_3;
  }
  v8 = a5;
  if ( !a5 )
  {
    v6 = -2147024809;
    Logger::TraceError(L"%s: \"%s\" should not be null.", L"CertificateUtil::DoesExtensionWithValueExist", L"pbResult");
    v7 = L"pbResult";
    goto LABEL_3;
  }
  *a5 = 0;
  if ( a3 )
  {
    if ( a3 != 1 )
    {
      Logger::TraceError(L"%s: Unknown CERT_OID_VALUE_TYPE: %d.", L"CertificateUtil::DoesExtensionWithValueExist");
      v6 = -2147024809;
      goto LABEL_21;
    }
    ExtensionGuidValueByOid = CertificateUtil::FindExtensionGuidValueByOid(a1, a4, (unsigned __int16 **)&lpString1);
    v10 = L"CertificateUtil::FindExtensionGuidValueByOid";
  }
  else
  {
    ExtensionGuidValueByOid = CertificateUtil::FindExtensionStrValueByOid(a1, a4, (unsigned __int16 **)&lpString1);
    v10 = L"CertificateUtil::FindExtensionStrValueByOid";
  }
  v6 = ExtensionGuidValueByOid;
  if ( ExtensionGuidValueByOid == -2146885628 )
  {
    v6 = 0;
  }
  else if ( ExtensionGuidValueByOid >= 0 )
  {
    if ( !lstrcmpiW(lpString1, a2) )
      *v8 = 1;
  }
  else
  {
    Logger::TraceError(
      L"%s: %s failed with error code: 0x%08x",
      L"CertificateUtil::DoesExtensionWithValueExist",
      v10,
      (unsigned int)ExtensionGuidValueByOid);
  }
LABEL_21:
  operator delete((void *)lpString1);
  return v6;
}

```

## disassembly

```asm
0x180077698  mov     [rsp+arg_8], rbx
0x18007769d  mov     [rsp+arg_10], rsi
0x1800776a2  push    rdi
0x1800776a3  sub     rsp, 20h
0x1800776a7  mov     [rsp+28h+lpString1], 0
0x1800776b0  mov     rsi, rdx
0x1800776b3  test    rcx, rcx
0x1800776b6  jnz     short loc_1800776EF
0x1800776b8  lea     r8, aPcszoid; "pcszOid"
0x1800776bf  mov     ebx, 80070057h
0x1800776c4  lea     rdx, aCertificateuti_6; "CertificateUtil::DoesExtensionWithValue"...
0x1800776cb  lea     rcx, aSSShouldNotBeN; "%s: \"%s\" should not be null."
0x1800776d2  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800776d7  lea     rdx, aPcszoid; "pcszOid"
0x1800776de  lea     rcx, aCertificateuti_6; "CertificateUtil::DoesExtensionWithValue"...
0x1800776e5  call    ?WriteNullOrEmptyParameterFailureEvent@Logger@@SAJPEBG0@Z; Logger::WriteNullOrEmptyParameterFailureEvent(ushort const *,ushort const *)
0x1800776ea  jmp     loc_180077814
0x1800776ef  test    rsi, rsi
0x1800776f2  jnz     short loc_18007771C
0x1800776f4  lea     r8, aPcszoidvalue; "pcszOidValue"
0x1800776fb  mov     ebx, 80070057h
0x180077700  lea     rdx, aCertificateuti_6; "CertificateUtil::DoesExtensionWithValue"...
0x180077707  lea     rcx, aSSShouldNotBeN; "%s: \"%s\" should not be null."
0x18007770e  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180077713  lea     rdx, aPcszoidvalue; "pcszOidValue"
0x18007771a  jmp     short loc_1800776DE
0x18007771c  test    r9, r9
0x18007771f  jnz     short loc_180077749
0x180077721  lea     r8, stru_180087E98
0x180077728  mov     ebx, 80070057h
0x18007772d  lea     rdx, aCertificateuti_6; "CertificateUtil::DoesExtensionWithValue"...
0x180077734  lea     rcx, aSSShouldNotBeN; "%s: \"%s\" should not be null."
0x18007773b  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180077740  lea     rdx, stru_180087E98
0x180077747  jmp     short loc_1800776DE
0x180077749  mov     rdi, [rsp+28h+arg_20]
0x18007774e  test    rdi, rdi
0x180077751  jnz     short loc_18007777E
0x180077753  lea     r8, aPbresult; "pbResult"
0x18007775a  mov     ebx, 80070057h
0x18007775f  lea     rdx, aCertificateuti_6; "CertificateUtil::DoesExtensionWithValue"...
0x180077766  lea     rcx, aSSShouldNotBeN; "%s: \"%s\" should not be null."
0x18007776d  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180077772  lea     rdx, aPbresult; "pbResult"
0x180077779  jmp     loc_1800776DE
0x18007777e  mov     dword ptr [rdi], 0
0x180077784  test    r8d, r8d
0x180077787  jz      short loc_1800777BF
0x180077789  cmp     r8d, 1
0x18007778d  jz      short loc_1800777A9
0x18007778f  lea     rdx, aCertificateuti_6; "CertificateUtil::DoesExtensionWithValue"...
0x180077796  lea     rcx, aSUnknownCertOi; "%s: Unknown CERT_OID_VALUE_TYPE: %d."
0x18007779d  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800777a2  mov     ebx, 80070057h
0x1800777a7  jmp     short loc_180077814
0x1800777a9  lea     r8, [rsp+28h+lpString1]; unsigned __int16 **
0x1800777ae  mov     rdx, r9; struct _CERT_CONTEXT *
0x1800777b1  call    ?FindExtensionGuidValueByOid@CertificateUtil@@SAJPEBDPEBU_CERT_CONTEXT@@PEAPEAG@Z; CertificateUtil::FindExtensionGuidValueByOid(char const *,_CERT_CONTEXT const *,ushort * *)
0x1800777b6  lea     r8, aCertificateuti_4; "CertificateUtil::FindExtensionGuidValue"...
0x1800777bd  jmp     short loc_1800777D3
0x1800777bf  lea     r8, [rsp+28h+lpString1]; unsigned __int16 **
0x1800777c4  mov     rdx, r9; struct _CERT_CONTEXT *
0x1800777c7  call    ?FindExtensionStrValueByOid@CertificateUtil@@SAJPEBDPEBU_CERT_CONTEXT@@PEAPEAG@Z; CertificateUtil::FindExtensionStrValueByOid(char const *,_CERT_CONTEXT const *,ushort * *)
0x1800777cc  lea     r8, aCertificateuti_5; "CertificateUtil::FindExtensionStrValueB"...
0x1800777d3  mov     ebx, eax
0x1800777d5  cmp     eax, 80092004h
0x1800777da  jnz     short loc_1800777E0
0x1800777dc  xor     ebx, ebx
0x1800777de  jmp     short loc_180077814
0x1800777e0  test    ebx, ebx
0x1800777e2  jns     short loc_1800777FC
0x1800777e4  mov     r9d, ebx
0x1800777e7  lea     rdx, aCertificateuti_6; "CertificateUtil::DoesExtensionWithValue"...
0x1800777ee  lea     rcx, aSSFailedWithEr; "%s: %s failed with error code: 0x%08x"
0x1800777f5  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800777fa  jmp     short loc_180077814
0x1800777fc  mov     rcx, [rsp+28h+lpString1]; lpString1
0x180077801  mov     rdx, rsi; lpString2
0x180077804  call    cs:__imp_lstrcmpiW
0x18007780a  test    eax, eax
0x18007780c  jnz     short loc_180077814
0x18007780e  mov     dword ptr [rdi], 1
0x180077814  mov     rcx, [rsp+28h+lpString1]; Block
0x180077819  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18007781e  mov     rsi, [rsp+28h+arg_10]
0x180077823  mov     eax, ebx
0x180077825  mov     rbx, [rsp+28h+arg_8]
0x18007782a  add     rsp, 20h
0x18007782e  pop     rdi
0x18007782f  retn
```
