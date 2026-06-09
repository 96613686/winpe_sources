# CertificateUtil::DoesExtensionWithValueExist(char const *,ushort const *,_CERT_OID_VALUE_TYPE,_CERT_CONTEXT const *,int *)

- ea: `0x18007ca8c`
- end: `0x18007cc2b`
- name: `?DoesExtensionWithValueExist@CertificateUtil@@SAJPEBDPEBGW4_CERT_OID_VALUE_TYPE@@PEBU_CERT_CONTEXT@@PEAH@Z`
- size: `415`
- prototype: `static int __high(const char *, const unsigned __int16 *, enum _CERT_OID_VALUE_TYPE, const struct _CERT_CONTEXT *, int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, loader_planting`

## callers

- `0x18007cc34`

## callees

- `0x18002ee04`
- `0x18002f324`
- `0x180038254`
- `0x18007ca8c`
- `0x18007d25c`
- `0x18007d448`

## import_xrefs

- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18007cbf8`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18007cbf8`

## string_xrefs

- `0x18007cab8`: `CertificateUtil::DoesExtensionWithValueExist`
- `0x18007cad2`: `CertificateUtil::DoesExtensionWithValueExist`
- `0x18007caf4`: `CertificateUtil::DoesExtensionWithValueExist`
- `0x18007cb21`: `CertificateUtil::DoesExtensionWithValueExist`
- `0x18007cb53`: `CertificateUtil::DoesExtensionWithValueExist`
- `0x18007cb83`: `CertificateUtil::DoesExtensionWithValueExist`
- `0x18007cbdb`: `CertificateUtil::DoesExtensionWithValueExist`
- `0x18007cbc0`: `CertificateUtil::FindExtensionStrValueByOid`
- `0x18007cbaa`: `CertificateUtil::FindExtensionGuidValueByOid`

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
      &stru_18008DE98);
    v7 = (const unsigned __int16 *)&stru_18008DE98;
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
0x18007ca8c  mov     [rsp+arg_8], rbx
0x18007ca91  mov     [rsp+arg_10], rsi
0x18007ca96  push    rdi
0x18007ca97  sub     rsp, 20h
0x18007ca9b  mov     [rsp+28h+lpString1], 0
0x18007caa4  mov     rsi, rdx
0x18007caa7  test    rcx, rcx
0x18007caaa  jnz     short loc_18007CAE3
0x18007caac  lea     r8, aPcszoid; "pcszOid"
0x18007cab3  mov     ebx, 80070057h
0x18007cab8  lea     rdx, aCertificateuti_6; "CertificateUtil::DoesExtensionWithValue"...
0x18007cabf  lea     rcx, aSSShouldNotBeN; "%s: \"%s\" should not be null."
0x18007cac6  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18007cacb  lea     rdx, aPcszoid; "pcszOid"
0x18007cad2  lea     rcx, aCertificateuti_6; "CertificateUtil::DoesExtensionWithValue"...
0x18007cad9  call    ?WriteNullOrEmptyParameterFailureEvent@Logger@@SAJPEBG0@Z; Logger::WriteNullOrEmptyParameterFailureEvent(ushort const *,ushort const *)
0x18007cade  jmp     loc_18007CC0E
0x18007cae3  test    rsi, rsi
0x18007cae6  jnz     short loc_18007CB10
0x18007cae8  lea     r8, aPcszoidvalue; "pcszOidValue"
0x18007caef  mov     ebx, 80070057h
0x18007caf4  lea     rdx, aCertificateuti_6; "CertificateUtil::DoesExtensionWithValue"...
0x18007cafb  lea     rcx, aSSShouldNotBeN; "%s: \"%s\" should not be null."
0x18007cb02  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18007cb07  lea     rdx, aPcszoidvalue; "pcszOidValue"
0x18007cb0e  jmp     short loc_18007CAD2
0x18007cb10  test    r9, r9
0x18007cb13  jnz     short loc_18007CB3D
0x18007cb15  lea     r8, stru_18008DE98
0x18007cb1c  mov     ebx, 80070057h
0x18007cb21  lea     rdx, aCertificateuti_6; "CertificateUtil::DoesExtensionWithValue"...
0x18007cb28  lea     rcx, aSSShouldNotBeN; "%s: \"%s\" should not be null."
0x18007cb2f  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18007cb34  lea     rdx, stru_18008DE98
0x18007cb3b  jmp     short loc_18007CAD2
0x18007cb3d  mov     rdi, [rsp+28h+arg_20]
0x18007cb42  test    rdi, rdi
0x18007cb45  jnz     short loc_18007CB72
0x18007cb47  lea     r8, aPbresult; "pbResult"
0x18007cb4e  mov     ebx, 80070057h
0x18007cb53  lea     rdx, aCertificateuti_6; "CertificateUtil::DoesExtensionWithValue"...
0x18007cb5a  lea     rcx, aSSShouldNotBeN; "%s: \"%s\" should not be null."
0x18007cb61  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18007cb66  lea     rdx, aPbresult; "pbResult"
0x18007cb6d  jmp     loc_18007CAD2
0x18007cb72  mov     dword ptr [rdi], 0
0x18007cb78  test    r8d, r8d
0x18007cb7b  jz      short loc_18007CBB3
0x18007cb7d  cmp     r8d, 1
0x18007cb81  jz      short loc_18007CB9D
0x18007cb83  lea     rdx, aCertificateuti_6; "CertificateUtil::DoesExtensionWithValue"...
0x18007cb8a  lea     rcx, aSUnknownCertOi; "%s: Unknown CERT_OID_VALUE_TYPE: %d."
0x18007cb91  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18007cb96  mov     ebx, 80070057h
0x18007cb9b  jmp     short loc_18007CC0E
0x18007cb9d  lea     r8, [rsp+28h+lpString1]; unsigned __int16 **
0x18007cba2  mov     rdx, r9; struct _CERT_CONTEXT *
0x18007cba5  call    ?FindExtensionGuidValueByOid@CertificateUtil@@SAJPEBDPEBU_CERT_CONTEXT@@PEAPEAG@Z; CertificateUtil::FindExtensionGuidValueByOid(char const *,_CERT_CONTEXT const *,ushort * *)
0x18007cbaa  lea     r8, aCertificateuti_4; "CertificateUtil::FindExtensionGuidValue"...
0x18007cbb1  jmp     short loc_18007CBC7
0x18007cbb3  lea     r8, [rsp+28h+lpString1]; unsigned __int16 **
0x18007cbb8  mov     rdx, r9; struct _CERT_CONTEXT *
0x18007cbbb  call    ?FindExtensionStrValueByOid@CertificateUtil@@SAJPEBDPEBU_CERT_CONTEXT@@PEAPEAG@Z; CertificateUtil::FindExtensionStrValueByOid(char const *,_CERT_CONTEXT const *,ushort * *)
0x18007cbc0  lea     r8, aCertificateuti_5; "CertificateUtil::FindExtensionStrValueB"...
0x18007cbc7  mov     ebx, eax
0x18007cbc9  cmp     eax, 80092004h
0x18007cbce  jnz     short loc_18007CBD4
0x18007cbd0  xor     ebx, ebx
0x18007cbd2  jmp     short loc_18007CC0E
0x18007cbd4  test    ebx, ebx
0x18007cbd6  jns     short loc_18007CBF0
0x18007cbd8  mov     r9d, ebx
0x18007cbdb  lea     rdx, aCertificateuti_6; "CertificateUtil::DoesExtensionWithValue"...
0x18007cbe2  lea     rcx, aSSFailedWithEr; "%s: %s failed with error code: 0x%08x"
0x18007cbe9  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18007cbee  jmp     short loc_18007CC0E
0x18007cbf0  mov     rcx, [rsp+28h+lpString1]; lpString1
0x18007cbf5  mov     rdx, rsi; lpString2
0x18007cbf8  call    cs:__imp_lstrcmpiW
0x18007cbff  nop     dword ptr [rax+rax+00h]
0x18007cc04  test    eax, eax
0x18007cc06  jnz     short loc_18007CC0E
0x18007cc08  mov     dword ptr [rdi], 1
0x18007cc0e  mov     rcx, [rsp+28h+lpString1]; Block
0x18007cc13  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18007cc18  mov     rsi, [rsp+28h+arg_10]
0x18007cc1d  mov     eax, ebx
0x18007cc1f  mov     rbx, [rsp+28h+arg_8]
0x18007cc24  add     rsp, 20h
0x18007cc28  pop     rdi
0x18007cc29  retn
```
