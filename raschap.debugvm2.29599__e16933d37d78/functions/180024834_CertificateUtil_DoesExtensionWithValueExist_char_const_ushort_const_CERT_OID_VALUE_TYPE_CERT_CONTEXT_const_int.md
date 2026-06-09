# CertificateUtil::DoesExtensionWithValueExist(char const *,ushort const *,_CERT_OID_VALUE_TYPE,_CERT_CONTEXT const *,int *)

- ea: `0x180024834`
- end: `0x1800249cc`
- name: `?DoesExtensionWithValueExist@CertificateUtil@@SAJPEBDPEBGW4_CERT_OID_VALUE_TYPE@@PEBU_CERT_CONTEXT@@PEAH@Z`
- size: `408`
- prototype: `static int __high(const char *, const unsigned __int16 *, enum _CERT_OID_VALUE_TYPE, const struct _CERT_CONTEXT *, int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, loader_planting`

## callers

- `0x180013084`

## callees

- `0x18000febc`
- `0x180010218`
- `0x180013bd0`
- `0x180024834`
- `0x180024a28`
- `0x180024c04`

## import_xrefs

- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800249a0`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800249a0`

## string_xrefs

- `0x180024860`: `CertificateUtil::DoesExtensionWithValueExist`
- `0x18002487a`: `CertificateUtil::DoesExtensionWithValueExist`
- `0x18002489c`: `CertificateUtil::DoesExtensionWithValueExist`
- `0x1800248c9`: `CertificateUtil::DoesExtensionWithValueExist`
- `0x1800248fb`: `CertificateUtil::DoesExtensionWithValueExist`
- `0x18002492b`: `CertificateUtil::DoesExtensionWithValueExist`
- `0x180024983`: `CertificateUtil::DoesExtensionWithValueExist`
- `0x180024968`: `CertificateUtil::FindExtensionStrValueByOid`
- `0x180024952`: `CertificateUtil::FindExtensionGuidValueByOid`

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
      &stru_18002C008);
    v7 = (const unsigned __int16 *)&stru_18002C008;
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
0x180024834  mov     [rsp+arg_8], rbx
0x180024839  mov     [rsp+arg_10], rsi
0x18002483e  push    rdi
0x18002483f  sub     rsp, 20h
0x180024843  mov     [rsp+28h+lpString1], 0
0x18002484c  mov     rsi, rdx
0x18002484f  test    rcx, rcx
0x180024852  jnz     short loc_18002488B
0x180024854  lea     r8, aPcszoid; "pcszOid"
0x18002485b  mov     ebx, 80070057h
0x180024860  lea     rdx, aCertificateuti_6; "CertificateUtil::DoesExtensionWithValue"...
0x180024867  lea     rcx, aSSShouldNotBeN; "%s: \"%s\" should not be null."
0x18002486e  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180024873  lea     rdx, aPcszoid; "pcszOid"
0x18002487a  lea     rcx, aCertificateuti_6; "CertificateUtil::DoesExtensionWithValue"...
0x180024881  call    ?WriteNullOrEmptyParameterFailureEvent@Logger@@SAJPEBG0@Z; Logger::WriteNullOrEmptyParameterFailureEvent(ushort const *,ushort const *)
0x180024886  jmp     loc_1800249B0
0x18002488b  test    rsi, rsi
0x18002488e  jnz     short loc_1800248B8
0x180024890  lea     r8, aPcszoidvalue; "pcszOidValue"
0x180024897  mov     ebx, 80070057h
0x18002489c  lea     rdx, aCertificateuti_6; "CertificateUtil::DoesExtensionWithValue"...
0x1800248a3  lea     rcx, aSSShouldNotBeN; "%s: \"%s\" should not be null."
0x1800248aa  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800248af  lea     rdx, aPcszoidvalue; "pcszOidValue"
0x1800248b6  jmp     short loc_18002487A
0x1800248b8  test    r9, r9
0x1800248bb  jnz     short loc_1800248E5
0x1800248bd  lea     r8, stru_18002C008
0x1800248c4  mov     ebx, 80070057h
0x1800248c9  lea     rdx, aCertificateuti_6; "CertificateUtil::DoesExtensionWithValue"...
0x1800248d0  lea     rcx, aSSShouldNotBeN; "%s: \"%s\" should not be null."
0x1800248d7  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800248dc  lea     rdx, stru_18002C008
0x1800248e3  jmp     short loc_18002487A
0x1800248e5  mov     rdi, [rsp+28h+arg_20]
0x1800248ea  test    rdi, rdi
0x1800248ed  jnz     short loc_18002491A
0x1800248ef  lea     r8, aPbresult; "pbResult"
0x1800248f6  mov     ebx, 80070057h
0x1800248fb  lea     rdx, aCertificateuti_6; "CertificateUtil::DoesExtensionWithValue"...
0x180024902  lea     rcx, aSSShouldNotBeN; "%s: \"%s\" should not be null."
0x180024909  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18002490e  lea     rdx, aPbresult; "pbResult"
0x180024915  jmp     loc_18002487A
0x18002491a  mov     dword ptr [rdi], 0
0x180024920  test    r8d, r8d
0x180024923  jz      short loc_18002495B
0x180024925  cmp     r8d, 1
0x180024929  jz      short loc_180024945
0x18002492b  lea     rdx, aCertificateuti_6; "CertificateUtil::DoesExtensionWithValue"...
0x180024932  lea     rcx, aSUnknownCertOi; "%s: Unknown CERT_OID_VALUE_TYPE: %d."
0x180024939  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18002493e  mov     ebx, 80070057h
0x180024943  jmp     short loc_1800249B0
0x180024945  lea     r8, [rsp+28h+lpString1]; unsigned __int16 **
0x18002494a  mov     rdx, r9; struct _CERT_CONTEXT *
0x18002494d  call    ?FindExtensionGuidValueByOid@CertificateUtil@@SAJPEBDPEBU_CERT_CONTEXT@@PEAPEAG@Z; CertificateUtil::FindExtensionGuidValueByOid(char const *,_CERT_CONTEXT const *,ushort * *)
0x180024952  lea     r8, aCertificateuti_4; "CertificateUtil::FindExtensionGuidValue"...
0x180024959  jmp     short loc_18002496F
0x18002495b  lea     r8, [rsp+28h+lpString1]; unsigned __int16 **
0x180024960  mov     rdx, r9; struct _CERT_CONTEXT *
0x180024963  call    ?FindExtensionStrValueByOid@CertificateUtil@@SAJPEBDPEBU_CERT_CONTEXT@@PEAPEAG@Z; CertificateUtil::FindExtensionStrValueByOid(char const *,_CERT_CONTEXT const *,ushort * *)
0x180024968  lea     r8, aCertificateuti_5; "CertificateUtil::FindExtensionStrValueB"...
0x18002496f  mov     ebx, eax
0x180024971  cmp     eax, 80092004h
0x180024976  jnz     short loc_18002497C
0x180024978  xor     ebx, ebx
0x18002497a  jmp     short loc_1800249B0
0x18002497c  test    ebx, ebx
0x18002497e  jns     short loc_180024998
0x180024980  mov     r9d, ebx
0x180024983  lea     rdx, aCertificateuti_6; "CertificateUtil::DoesExtensionWithValue"...
0x18002498a  lea     rcx, aSSFailedWithEr; "%s: %s failed with error code: 0x%08x"
0x180024991  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180024996  jmp     short loc_1800249B0
0x180024998  mov     rcx, [rsp+28h+lpString1]; lpString1
0x18002499d  mov     rdx, rsi; lpString2
0x1800249a0  call    cs:__imp_lstrcmpiW
0x1800249a6  test    eax, eax
0x1800249a8  jnz     short loc_1800249B0
0x1800249aa  mov     dword ptr [rdi], 1
0x1800249b0  mov     rcx, [rsp+28h+lpString1]; Block
0x1800249b5  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800249ba  mov     rsi, [rsp+28h+arg_10]
0x1800249bf  mov     eax, ebx
0x1800249c1  mov     rbx, [rsp+28h+arg_8]
0x1800249c6  add     rsp, 20h
0x1800249ca  pop     rdi
0x1800249cb  retn
```
