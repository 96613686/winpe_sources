# I_OcspDebugErrorPrintfA(char const *,_CERT_CONTEXT const *)

- ea: `0x18000f004`
- end: `0x18000f0dc`
- name: `?I_OcspDebugErrorPrintfA@@YAXPEBDPEBU_CERT_CONTEXT@@@Z`
- size: `216`
- prototype: `void __fastcall(const char *, const struct _CERT_CONTEXT *)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18000dab0`
- `0x18000e610`

## callees

- `0x18000bb78`
- `0x18000f004`
- `0x18000f0e4`
- `0x1800265b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000f041`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000f041`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f02e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f02e`
- `CRYPT32!CertNameToStrW` at `0x18000f08f`
- `CRYPT32!CertNameToStrW` at `0x18000f0b5`
- `CRYPT32!CertNameToStrW` at `0x18000f08f`
- `CRYPT32!CertNameToStrW` at `0x18000f0b5`

## string_xrefs

- `0x18000f0cb`: `CRYPTNET.DLL --> OCSP ERROR:: %s for Subject: <%S> Issuer: <%S>\n`

## pseudocode

```c
void __fastcall I_OcspDebugErrorPrintfA(const char *a1, const struct _CERT_CONTEXT *a2)
{
  DWORD LastError; // ebx
  WCHAR v5[200]; // [rsp+30h] [rbp-338h] BYREF
  WCHAR psz[200]; // [rsp+1C0h] [rbp-1A8h] BYREF

  LastError = GetLastError();
  if ( (unsigned int)I_CryptNetIsDebugErrorPrintEnabled() )
  {
    CertNameToStrW(1u, &a2->pCertInfo->Subject, 0x2000003u, psz, 0xC8u);
    CertNameToStrW(1u, &a2->pCertInfo->Issuer, 0x2000003u, v5, 0xC8u);
    I_CryptNetDebugErrorPrintfA("CRYPTNET.DLL --> OCSP ERROR:: %s for Subject: <%S> Issuer: <%S>\n", a1, psz, v5);
  }
  SetLastError(LastError);
}

```

## disassembly

```asm
0x18000f004  mov     [rsp+arg_10], rbx
0x18000f009  mov     [rsp+arg_18], rsi
0x18000f00e  push    rdi
0x18000f00f  sub     rsp, 360h
0x18000f016  mov     rax, cs:__security_cookie
0x18000f01d  xor     rax, rsp
0x18000f020  mov     [rsp+368h+var_18], rax
0x18000f028  mov     rdi, rdx
0x18000f02b  mov     rsi, rcx
0x18000f02e  call    cs:__imp_GetLastError
0x18000f034  mov     ebx, eax
0x18000f036  call    ?I_CryptNetIsDebugErrorPrintEnabled@@YAHXZ; I_CryptNetIsDebugErrorPrintEnabled(void)
0x18000f03b  test    eax, eax
0x18000f03d  jnz     short loc_18000F06C
0x18000f03f  mov     ecx, ebx; dwErrCode
0x18000f041  call    cs:__imp_SetLastError
0x18000f047  mov     rcx, [rsp+368h+var_18]
0x18000f04f  xor     rcx, rsp; StackCookie
0x18000f052  call    __security_check_cookie
0x18000f057  lea     r11, [rsp+368h+var_8]
0x18000f05f  mov     rbx, [r11+20h]
0x18000f063  mov     rsi, [r11+28h]
0x18000f067  mov     rsp, r11
0x18000f06a  pop     rdi
0x18000f06b  retn
0x18000f06c  mov     rdx, [rdi+18h]
0x18000f070  lea     r9, [rsp+368h+psz]; psz
0x18000f078  add     rdx, 50h ; 'P'; pName
0x18000f07c  mov     [rsp+368h+csz], 0C8h; csz
0x18000f084  mov     ecx, 1; dwCertEncodingType
0x18000f089  mov     r8d, 2000003h; dwStrType
0x18000f08f  call    cs:__imp_CertNameToStrW
0x18000f095  mov     rdx, [rdi+18h]
0x18000f099  lea     r9, [rsp+368h+var_338]; psz
0x18000f09e  add     rdx, 30h ; '0'; pName
0x18000f0a2  mov     [rsp+368h+csz], 0C8h; csz
0x18000f0aa  mov     ecx, 1; dwCertEncodingType
0x18000f0af  mov     r8d, 2000003h; dwStrType
0x18000f0b5  call    cs:__imp_CertNameToStrW
0x18000f0bb  lea     r9, [rsp+368h+var_338]
0x18000f0c0  mov     rdx, rsi
0x18000f0c3  lea     r8, [rsp+368h+psz]
0x18000f0cb  lea     rcx, aCryptnetDllOcs_0; "CRYPTNET.DLL --> OCSP ERROR:: %s for Su"...
0x18000f0d2  call    ?I_CryptNetDebugErrorPrintfA@@YAXPEBDZZ; I_CryptNetDebugErrorPrintfA(char const *,...)
0x18000f0d7  jmp     loc_18000F03F
```
