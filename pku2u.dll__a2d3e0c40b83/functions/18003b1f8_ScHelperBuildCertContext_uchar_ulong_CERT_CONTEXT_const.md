# ScHelperBuildCertContext(uchar *,ulong,_CERT_CONTEXT const * *)

- ea: `0x18003b1f8`
- end: `0x18003b286`
- name: `?ScHelperBuildCertContext@@YAJPEAEKPEAPEBU_CERT_CONTEXT@@@Z`
- size: `142`
- prototype: `DWORD __fastcall(BYTE *pbCertEncoded, DWORD cbCertEncoded, const struct _CERT_CONTEXT **)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180020238`
- `0x18002a320`
- `0x18002d5f8`

## callees

- `0x180023ce0`
- `0x18003b1f8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b233`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b258`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b26e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b233`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b258`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b267`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b26e`
- `CRYPT32!CertCreateCertificateContext` at `0x18003b20c`
- `CRYPT32!CertCreateCertificateContext` at `0x18003b20c`

## pseudocode

```c
DWORD __fastcall ScHelperBuildCertContext(BYTE *pbCertEncoded, DWORD cbCertEncoded, const struct _CERT_CONTEXT **a3)
{
  const struct _CERT_CONTEXT *CertificateContext; // rax
  DWORD LastError; // eax

  CertificateContext = CertCreateCertificateContext(0x10001u, pbCertEncoded, cbCertEncoded);
  *a3 = CertificateContext;
  if ( CertificateContext )
    return 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    LastError = GetLastError();
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_251f18e709af358bb535638a6d34bada_Traceguids, LastError);
  }
  if ( (int)GetLastError() > 0 )
    return (unsigned __int16)GetLastError() | 0xC0070000;
  else
    return GetLastError();
}

```

## disassembly

```asm
0x18003b1f8  push    rbx
0x18003b1fa  sub     rsp, 20h
0x18003b1fe  mov     rbx, r8
0x18003b201  mov     r8d, edx; cbCertEncoded
0x18003b204  mov     rdx, rcx; pbCertEncoded
0x18003b207  mov     ecx, 10001h; dwCertEncodingType
0x18003b20c  call    cs:__imp_CertCreateCertificateContext
0x18003b212  mov     [rbx], rax
0x18003b215  test    rax, rax
0x18003b218  jnz     short loc_18003B27E
0x18003b21a  mov     rax, cs:WPP_GLOBAL_Control
0x18003b221  lea     rcx, WPP_GLOBAL_Control
0x18003b228  cmp     rax, rcx
0x18003b22b  jz      short loc_18003B258
0x18003b22d  test    byte ptr [rax+1Ch], 1
0x18003b231  jz      short loc_18003B258
0x18003b233  call    cs:__imp_GetLastError
0x18003b239  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b240  lea     r8, WPP_251f18e709af358bb535638a6d34bada_Traceguids
0x18003b247  mov     edx, 0Ah
0x18003b24c  mov     r9d, eax
0x18003b24f  mov     rcx, [rcx+10h]
0x18003b253  call    WPP_SF_d
0x18003b258  call    cs:__imp_GetLastError
0x18003b25e  test    eax, eax
0x18003b260  jg      short loc_18003B26E
0x18003b262  add     rsp, 20h
0x18003b266  pop     rbx
0x18003b267  jmp     cs:__imp_GetLastError
0x18003b26e  call    cs:__imp_GetLastError
0x18003b274  movzx   eax, ax
0x18003b277  or      eax, 0C0070000h
0x18003b27c  jmp     short loc_18003B280
0x18003b27e  xor     eax, eax
0x18003b280  add     rsp, 20h
0x18003b284  pop     rbx
0x18003b285  retn
```
