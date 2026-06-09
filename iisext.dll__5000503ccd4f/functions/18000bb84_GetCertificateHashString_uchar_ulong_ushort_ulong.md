# GetCertificateHashString(uchar *,ulong,ushort *,ulong)

- ea: `0x18000bb84`
- end: `0x18000bc9e`
- name: `?GetCertificateHashString@@YAJPEAEKPEAGK@Z`
- size: `282`
- prototype: `__int64 __fastcall(BYTE *pbCertEncoded, DWORD cbCertEncoded, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000b22c`

## callees

- `0x18000bb84`
- `0x1800111e0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000bbcb`
- `KERNEL32!GetLastError` at `0x18000bc05`
- `KERNEL32!GetLastError` at `0x18000bbcb`
- `KERNEL32!GetLastError` at `0x18000bc05`
- `CRYPT32!CertCreateCertificateContext` at `0x18000bbbd`
- `CRYPT32!CertCreateCertificateContext` at `0x18000bbbd`
- `CRYPT32!CertFreeCertificateContext` at `0x18000bc1d`
- `CRYPT32!CertFreeCertificateContext` at `0x18000bc28`
- `CRYPT32!CertFreeCertificateContext` at `0x18000bc1d`
- `CRYPT32!CertFreeCertificateContext` at `0x18000bc28`
- `CRYPT32!CertGetCertificateContextProperty` at `0x18000bbfb`
- `CRYPT32!CertGetCertificateContextProperty` at `0x18000bbfb`

## pseudocode

```c
__int64 __fastcall GetCertificateHashString(BYTE *pbCertEncoded, DWORD cbCertEncoded, unsigned __int16 *a3)
{
  const CERT_CONTEXT *CertificateContext; // rax
  const CERT_CONTEXT *v5; // rdi
  signed int v6; // eax
  unsigned int v7; // ebx
  signed int LastError; // eax
  signed int i; // r8d
  __int16 v10; // cx
  char v11; // dl
  __int16 v12; // cx
  DWORD pcbData; // [rsp+20h] [rbp-48h] BYREF
  __int128 pvData; // [rsp+28h] [rbp-40h] BYREF
  int v16; // [rsp+38h] [rbp-30h]

  pcbData = 20;
  v16 = 0;
  pvData = 0;
  CertificateContext = CertCreateCertificateContext(1u, pbCertEncoded, cbCertEncoded);
  v5 = CertificateContext;
  if ( CertificateContext )
  {
    if ( CertGetCertificateContextProperty(CertificateContext, 3u, &pvData, &pcbData) )
    {
      CertFreeCertificateContext(v5);
      v7 = 0;
      for ( i = 0; (unsigned int)i < 0x14; ++i )
      {
        v10 = 87;
        v11 = *((_BYTE *)&pvData + i);
        if ( (v11 & 0xF0u) <= 0x90 )
          v10 = 48;
        *a3 = (*((unsigned __int8 *)&pvData + i) >> 4) + v10;
        a3 += 2;
        v12 = 87;
        if ( (v11 & 0xFu) <= 9 )
          v12 = 48;
        *(a3 - 1) = (v11 & 0xF) + v12;
      }
      *a3 = 0;
    }
    else
    {
      LastError = GetLastError();
      v7 = LastError;
      if ( LastError > 0 )
        v7 = (unsigned __int16)LastError | 0x80070000;
      CertFreeCertificateContext(v5);
    }
  }
  else
  {
    v6 = GetLastError();
    v7 = v6;
    if ( v6 > 0 )
      return (unsigned __int16)v6 | 0x80070000;
  }
  return v7;
}

```

## disassembly

```asm
0x18000bb84  push    rbx
0x18000bb86  push    rsi
0x18000bb87  push    rdi
0x18000bb88  sub     rsp, 50h
0x18000bb8c  mov     rax, cs:__security_cookie
0x18000bb93  xor     rax, rsp
0x18000bb96  mov     [rsp+68h+var_28], rax
0x18000bb9b  xor     eax, eax
0x18000bb9d  mov     [rsp+68h+pcbData], 14h
0x18000bba5  mov     rsi, r8
0x18000bba8  mov     [rsp+68h+var_30], eax
0x18000bbac  mov     r8d, edx; cbCertEncoded
0x18000bbaf  xorps   xmm0, xmm0
0x18000bbb2  mov     rdx, rcx; pbCertEncoded
0x18000bbb5  lea     ecx, [rax+1]; dwCertEncodingType
0x18000bbb8  movups  [rsp+68h+pvData], xmm0
0x18000bbbd  call    cs:__imp_CertCreateCertificateContext
0x18000bbc3  mov     rdi, rax
0x18000bbc6  test    rax, rax
0x18000bbc9  jnz     short loc_18000BBE9
0x18000bbcb  call    cs:__imp_GetLastError
0x18000bbd1  mov     ebx, eax
0x18000bbd3  test    eax, eax
0x18000bbd5  jle     loc_18000BC87
0x18000bbdb  movzx   ebx, ax
0x18000bbde  or      ebx, 80070000h
0x18000bbe4  jmp     loc_18000BC87
0x18000bbe9  lea     r9, [rsp+68h+pcbData]; pcbData
0x18000bbee  mov     edx, 3; dwPropId
0x18000bbf3  lea     r8, [rsp+68h+pvData]; pvData
0x18000bbf8  mov     rcx, rdi; pCertContext
0x18000bbfb  call    cs:__imp_CertGetCertificateContextProperty
0x18000bc01  test    eax, eax
0x18000bc03  jnz     short loc_18000BC25
0x18000bc05  call    cs:__imp_GetLastError
0x18000bc0b  mov     ebx, eax
0x18000bc0d  test    eax, eax
0x18000bc0f  jle     short loc_18000BC1A
0x18000bc11  movzx   ebx, ax
0x18000bc14  or      ebx, 80070000h
0x18000bc1a  mov     rcx, rdi; pCertContext
0x18000bc1d  call    cs:__imp_CertFreeCertificateContext
0x18000bc23  jmp     short loc_18000BC87
0x18000bc25  mov     rcx, rdi; pCertContext
0x18000bc28  call    cs:__imp_CertFreeCertificateContext
0x18000bc2e  xor     ebx, ebx
0x18000bc30  xor     r8d, r8d
0x18000bc33  lea     r9d, [rbx+57h]
0x18000bc37  lea     r10d, [rbx+30h]
0x18000bc3b  movsxd  rax, r8d
0x18000bc3e  mov     ecx, r9d
0x18000bc41  movzx   edx, byte ptr [rsp+rax+68h+pvData]
0x18000bc46  mov     al, dl
0x18000bc48  and     al, 0F0h
0x18000bc4a  cmp     al, 90h
0x18000bc4c  mov     eax, edx
0x18000bc4e  cmovbe  cx, r10w
0x18000bc53  shr     eax, 4
0x18000bc56  add     cx, ax
0x18000bc59  mov     al, dl
0x18000bc5b  mov     [rsi], cx
0x18000bc5e  and     al, 0Fh
0x18000bc60  cmp     al, 9
0x18000bc62  lea     rsi, [rsi+4]
0x18000bc66  mov     ecx, r9d
0x18000bc69  cmovbe  cx, r10w
0x18000bc6e  and     dx, 0Fh
0x18000bc72  add     cx, dx
0x18000bc75  inc     r8d
0x18000bc78  mov     [rsi-2], cx
0x18000bc7c  cmp     r8d, 14h
0x18000bc80  jb      short loc_18000BC3B
0x18000bc82  xor     ecx, ecx
0x18000bc84  mov     [rsi], cx
0x18000bc87  mov     eax, ebx
0x18000bc89  mov     rcx, [rsp+68h+var_28]
0x18000bc8e  xor     rcx, rsp; StackCookie
0x18000bc91  call    __security_check_cookie
0x18000bc96  add     rsp, 50h
0x18000bc9a  pop     rdi
0x18000bc9b  pop     rsi
0x18000bc9c  pop     rbx
0x18000bc9d  retn
```
