# basessp::BaseSSP::WSTGetCspDataForCert(_CERT_CONTEXT const *,basessp::_WST_CSPDATA_DETAIL *)

- ea: `0x18001dc88`
- end: `0x18001de31`
- name: `?WSTGetCspDataForCert@BaseSSP@basessp@@AEAAJPEBU_CERT_CONTEXT@@PEAU_WST_CSPDATA_DETAIL@2@@Z`
- size: `425`
- prototype: `__int64 __fastcall(basessp::BaseSSP *__hidden this, PCCERT_CONTEXT pCert, struct basessp::_WST_CSPDATA_DETAIL *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180005bc0`

## callees

- `0x1800027e4`
- `0x180005960`
- `0x18001d668`
- `0x18001dc88`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001dd51`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001dd51`
- `ntdll!RtlFreeUnicodeString` at `0x18001de1c`
- `ntdll!RtlFreeUnicodeString` at `0x18001de1c`
- `ntdll!RtlCreateUnicodeStringFromAsciiz` at `0x18001ddb8`
- `ntdll!RtlCreateUnicodeStringFromAsciiz` at `0x18001ddb8`
- `CRYPT32!CertGetCertificateContextProperty` at `0x18001dcda`
- `CRYPT32!CertGetCertificateContextProperty` at `0x18001dd1c`
- `CRYPT32!CertGetCertificateContextProperty` at `0x18001dcda`
- `CRYPT32!CertGetCertificateContextProperty` at `0x18001dd1c`
- `CRYPT32!CryptAcquireCertificatePrivateKey` at `0x18001dd47`
- `CRYPT32!CryptAcquireCertificatePrivateKey` at `0x18001dd47`
- `CRYPTSP!CryptGetProvParam` at `0x18001dd75`
- `CRYPTSP!CryptGetProvParam` at `0x18001dda7`
- `CRYPTSP!CryptGetProvParam` at `0x18001dd75`
- `CRYPTSP!CryptGetProvParam` at `0x18001dda7`
- `CRYPTSP!CryptReleaseContext` at `0x18001de00`
- `CRYPTSP!CryptReleaseContext` at `0x18001de00`

## pseudocode

```c
__int64 __fastcall basessp::BaseSSP::WSTGetCspDataForCert(
        basessp::BaseSSP *this,
        PCCERT_CONTEXT pCert,
        struct basessp::_WST_CSPDATA_DETAIL *a3)
{
  char *v4; // r14
  void *v7; // rdi
  unsigned int v8; // ebx
  void *v9; // rax
  unsigned __int16 *v10; // rdx
  BYTE *v11; // rax
  DWORD pdwDataLen; // [rsp+40h] [rbp-38h] BYREF
  BOOL pfCallerFreeProvOrNCryptKey; // [rsp+44h] [rbp-34h] BYREF
  DWORD pdwKeySpec; // [rsp+48h] [rbp-30h] BYREF
  HCRYPTPROV_OR_NCRYPT_KEY_HANDLE phCryptProvOrNCryptKey; // [rsp+50h] [rbp-28h] BYREF
  struct _UNICODE_STRING Destination; // [rsp+58h] [rbp-20h] BYREF
  DWORD pcbData; // [rsp+C8h] [rbp+50h] BYREF

  pcbData = 0;
  v4 = 0;
  phCryptProvOrNCryptKey = 0;
  pdwKeySpec = 8;
  pfCallerFreeProvOrNCryptKey = 0;
  pdwDataLen = 0;
  Destination = 0;
  if ( !CertGetCertificateContextProperty(pCert, 2u, 0, &pcbData) )
  {
    v7 = 0;
LABEL_3:
    v8 = -1073741023;
    goto LABEL_15;
  }
  v9 = basessp::BaseSSP::WSTAllocate(this, pcbData);
  v7 = v9;
  if ( !v9 )
  {
    v8 = -1073741670;
    goto LABEL_15;
  }
  if ( !CertGetCertificateContextProperty(pCert, 2u, v9, &pcbData) )
    goto LABEL_3;
  if ( !CryptAcquireCertificatePrivateKey(
          pCert,
          0x10041u,
          0,
          &phCryptProvOrNCryptKey,
          &pdwKeySpec,
          &pfCallerFreeProvOrNCryptKey) )
  {
    GetLastError();
    goto LABEL_3;
  }
  if ( *((_DWORD *)v7 + 4) )
  {
    if ( CryptGetProvParam(phCryptProvOrNCryptKey, 0x2Bu, 0, &pdwDataLen, 0) )
    {
      v11 = (BYTE *)basessp::BaseSSP::WSTAllocate(this, pdwDataLen);
      v4 = (char *)v11;
      if ( v11 )
      {
        if ( CryptGetProvParam(phCryptProvOrNCryptKey, 0x2Bu, v11, &pdwDataLen, 0) )
          RtlCreateUnicodeStringFromAsciiz(&Destination, v4);
      }
    }
  }
  v8 = basessp::BaseSSP::WSTBuildCspDetail(
         this,
         v10,
         Destination.Buffer,
         *(unsigned __int16 **)v7,
         *((unsigned __int16 **)v7 + 1),
         *((_DWORD *)v7 + 10),
         a3);
LABEL_15:
  basessp::BaseSSP::WSTFree(this, v7);
  if ( phCryptProvOrNCryptKey && pfCallerFreeProvOrNCryptKey )
    CryptReleaseContext(phCryptProvOrNCryptKey, 0);
  basessp::BaseSSP::WSTFree(this, v4);
  if ( Destination.Buffer )
    RtlFreeUnicodeString(&Destination);
  return v8;
}

```

## disassembly

```asm
0x18001dc88  push    rbp
0x18001dc8a  push    rbx
0x18001dc8b  push    rsi
0x18001dc8c  push    rdi
0x18001dc8d  push    r14
0x18001dc8f  push    r15
0x18001dc91  mov     rbp, rsp
0x18001dc94  sub     rsp, 78h
0x18001dc98  mov     rbx, rdx
0x18001dc9b  mov     [rbp+pcbData], 0
0x18001dca2  xor     r14d, r14d
0x18001dca5  mov     [rbp+phCryptProvOrNCryptKey], 0
0x18001dcad  mov     r15, r8
0x18001dcb0  mov     [rbp+var_30], 8
0x18001dcb7  mov     rsi, rcx
0x18001dcba  mov     [rbp+var_34], 0
0x18001dcc1  xorps   xmm0, xmm0
0x18001dcc4  mov     [rbp+pdwDataLen], r14d
0x18001dcc8  lea     edx, [r14+2]; dwPropId
0x18001dccc  xor     r8d, r8d; pvData
0x18001dccf  lea     r9, [rbp+pcbData]; pcbData
0x18001dcd3  mov     rcx, rbx; pCertContext
0x18001dcd6  movups  xmmword ptr [rbp+Destination.Length], xmm0
0x18001dcda  call    cs:__imp_CertGetCertificateContextProperty
0x18001dce0  test    eax, eax
0x18001dce2  jnz     short loc_18001DCF0
0x18001dce4  xor     edi, edi
0x18001dce6  mov     ebx, 0C0000321h
0x18001dceb  jmp     loc_18001DDE4
0x18001dcf0  mov     edx, [rbp+pcbData]; unsigned __int64
0x18001dcf3  mov     rcx, rsi; this
0x18001dcf6  call    ?WSTAllocate@BaseSSP@basessp@@QEAAPEAX_K@Z; basessp::BaseSSP::WSTAllocate(unsigned __int64)
0x18001dcfb  mov     rdi, rax
0x18001dcfe  test    rax, rax
0x18001dd01  jnz     short loc_18001DD0D
0x18001dd03  mov     ebx, 0C000009Ah
0x18001dd08  jmp     loc_18001DDE4
0x18001dd0d  lea     r9, [rbp+pcbData]; pcbData
0x18001dd11  mov     r8, rdi; pvData
0x18001dd14  mov     edx, 2; dwPropId
0x18001dd19  mov     rcx, rbx; pCertContext
0x18001dd1c  call    cs:__imp_CertGetCertificateContextProperty
0x18001dd22  test    eax, eax
0x18001dd24  jz      short loc_18001DCE6
0x18001dd26  lea     rax, [rbp+var_34]
0x18001dd2a  xor     r8d, r8d; pvParameters
0x18001dd2d  mov     [rsp+78h+pfCallerFreeProvOrNCryptKey], rax; pfCallerFreeProvOrNCryptKey
0x18001dd32  lea     r9, [rbp+phCryptProvOrNCryptKey]; phCryptProvOrNCryptKey
0x18001dd36  lea     rax, [rbp+var_30]
0x18001dd3a  mov     edx, 10041h; dwFlags
0x18001dd3f  mov     rcx, rbx; pCert
0x18001dd42  mov     [rsp+78h+pdwKeySpec], rax; pdwKeySpec
0x18001dd47  call    cs:__imp_CryptAcquireCertificatePrivateKey
0x18001dd4d  test    eax, eax
0x18001dd4f  jnz     short loc_18001DD59
0x18001dd51  call    cs:__imp_GetLastError
0x18001dd57  jmp     short loc_18001DCE6
0x18001dd59  cmp     [rdi+10h], r14d
0x18001dd5d  jz      short loc_18001DDBE
0x18001dd5f  mov     rcx, [rbp+phCryptProvOrNCryptKey]; hProv
0x18001dd63  lea     r9, [rbp+pdwDataLen]; pdwDataLen
0x18001dd67  xor     r8d, r8d; pbData
0x18001dd6a  mov     dword ptr [rsp+78h+pdwKeySpec], r14d; dwFlags
0x18001dd6f  lea     ebx, [r8+2Bh]
0x18001dd73  mov     edx, ebx; dwParam
0x18001dd75  call    cs:__imp_CryptGetProvParam
0x18001dd7b  test    eax, eax
0x18001dd7d  jz      short loc_18001DDBE
0x18001dd7f  mov     edx, [rbp+pdwDataLen]; unsigned __int64
0x18001dd82  mov     rcx, rsi; this
0x18001dd85  call    ?WSTAllocate@BaseSSP@basessp@@QEAAPEAX_K@Z; basessp::BaseSSP::WSTAllocate(unsigned __int64)
0x18001dd8a  mov     r14, rax
0x18001dd8d  test    rax, rax
0x18001dd90  jz      short loc_18001DDBE
0x18001dd92  mov     rcx, [rbp+phCryptProvOrNCryptKey]; hProv
0x18001dd96  lea     r9, [rbp+pdwDataLen]; pdwDataLen
0x18001dd9a  mov     r8, rax; pbData
0x18001dd9d  mov     dword ptr [rsp+78h+pdwKeySpec], 0; dwFlags
0x18001dda5  mov     edx, ebx; dwParam
0x18001dda7  call    cs:__imp_CryptGetProvParam
0x18001ddad  test    eax, eax
0x18001ddaf  jz      short loc_18001DDBE
0x18001ddb1  mov     rdx, r14; Source
0x18001ddb4  lea     rcx, [rbp+Destination]; Destination
0x18001ddb8  call    cs:__imp_RtlCreateUnicodeStringFromAsciiz
0x18001ddbe  mov     eax, [rdi+28h]
0x18001ddc1  mov     rcx, rsi; this
0x18001ddc4  mov     r9, [rdi]; unsigned __int16 *
0x18001ddc7  mov     r8, [rbp+Destination.Buffer]; unsigned __int16 *
0x18001ddcb  mov     [rsp+78h+var_48], r15; struct basessp::_WST_CSPDATA_DETAIL *
0x18001ddd0  mov     dword ptr [rsp+78h+pfCallerFreeProvOrNCryptKey], eax; unsigned int
0x18001ddd4  mov     rax, [rdi+8]
0x18001ddd8  mov     [rsp+78h+pdwKeySpec], rax; unsigned __int16 *
0x18001dddd  call    ?WSTBuildCspDetail@BaseSSP@basessp@@AEAAJPEAG000KPEAU_WST_CSPDATA_DETAIL@2@@Z; basessp::BaseSSP::WSTBuildCspDetail(ushort *,ushort *,ushort *,ushort *,ulong,basessp::_WST_CSPDATA_DETAIL *)
0x18001dde2  mov     ebx, eax
0x18001dde4  mov     rdx, rdi; void *
0x18001dde7  mov     rcx, rsi; this
0x18001ddea  call    ?WSTFree@BaseSSP@basessp@@QEAAXPEAX@Z; basessp::BaseSSP::WSTFree(void *)
0x18001ddef  mov     rcx, [rbp+phCryptProvOrNCryptKey]; hProv
0x18001ddf3  test    rcx, rcx
0x18001ddf6  jz      short loc_18001DE06
0x18001ddf8  cmp     [rbp+var_34], 0
0x18001ddfc  jz      short loc_18001DE06
0x18001ddfe  xor     edx, edx; dwFlags
0x18001de00  call    cs:__imp_CryptReleaseContext
0x18001de06  mov     rdx, r14; void *
0x18001de09  mov     rcx, rsi; this
0x18001de0c  call    ?WSTFree@BaseSSP@basessp@@QEAAXPEAX@Z; basessp::BaseSSP::WSTFree(void *)
0x18001de11  cmp     [rbp+Destination.Buffer], 0
0x18001de16  jz      short loc_18001DE22
0x18001de18  lea     rcx, [rbp+Destination]; UnicodeString
0x18001de1c  call    cs:__imp_RtlFreeUnicodeString
0x18001de22  mov     eax, ebx
0x18001de24  add     rsp, 78h
0x18001de28  pop     r15
0x18001de2a  pop     r14
0x18001de2c  pop     rdi
0x18001de2d  pop     rsi
0x18001de2e  pop     rbx
0x18001de2f  pop     rbp
0x18001de30  retn
```
