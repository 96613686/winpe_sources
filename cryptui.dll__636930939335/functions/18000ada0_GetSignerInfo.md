# GetSignerInfo

- ea: `0x18000ada0`
- end: `0x18000af74`
- name: `GetSignerInfo`
- size: `468`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x18000b220`

## callees

- `0x18000ada0`
- `0x180032abc`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000ae59`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000aedd`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000ae59`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000aedd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000af1d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000af27`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000af37`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000af5e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000af1d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000af27`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000af37`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000af5e`
- `CRYPT32!CryptMsgGetParam` at `0x18000ae3b`
- `CRYPT32!CryptMsgGetParam` at `0x18000ae81`
- `CRYPT32!CryptMsgGetParam` at `0x18000ae3b`
- `CRYPT32!CryptMsgGetParam` at `0x18000ae81`
- `CRYPT32!CryptMsgOpenToDecode` at `0x18000add7`
- `CRYPT32!CryptMsgOpenToDecode` at `0x18000add7`
- `CRYPT32!CryptMsgUpdate` at `0x18000ae04`
- `CRYPT32!CryptMsgUpdate` at `0x18000ae04`
- `CRYPT32!CryptMsgClose` at `0x18000ae12`
- `CRYPT32!CryptMsgClose` at `0x18000ae12`
- `CRYPT32!CryptDecodeObject` at `0x18000aec8`
- `CRYPT32!CryptDecodeObject` at `0x18000af10`
- `CRYPT32!CryptDecodeObject` at `0x18000aec8`
- `CRYPT32!CryptDecodeObject` at `0x18000af10`

## pseudocode

```c
int __fastcall GetSignerInfo(__int64 a1)
{
  struct _CERT_CONTEXT *SignersCert; // rax
  BOOL v3; // eax
  void *v4; // rcx
  struct _CERT_CONTEXT *v5; // rdi
  DWORD v6; // r9d
  HLOCAL pvStructInfo; // rax
  DWORD cbEncoded; // [rsp+50h] [rbp+8h] BYREF

  cbEncoded = 0;
  SignersCert = (struct _CERT_CONTEXT *)CryptMsgOpenToDecode(0x10001u, 0, 0, 0, 0, 0);
  *(_QWORD *)(a1 + 64) = SignersCert;
  if ( SignersCert )
  {
    v3 = CryptMsgUpdate(
           SignersCert,
           *(const BYTE **)(*(_QWORD *)(*(_QWORD *)a1 + 32LL) + 8LL),
           *(_DWORD *)(*(_QWORD *)(*(_QWORD *)a1 + 32LL) + 16LL),
           1);
    v4 = *(void **)(a1 + 64);
    if ( v3 )
    {
      CryptMsgGetParam(v4, 0x1Cu, 0, 0, &cbEncoded);
      LODWORD(SignersCert) = cbEncoded;
      if ( cbEncoded )
      {
        SignersCert = (struct _CERT_CONTEXT *)LocalAlloc(0x40u, cbEncoded);
        v5 = SignersCert;
        if ( SignersCert )
        {
          if ( CryptMsgGetParam(*(HCRYPTMSG *)(a1 + 64), 0x1Cu, 0, SignersCert, &cbEncoded)
            && (v6 = cbEncoded,
                *(_DWORD *)(a1 + 80) = 0,
                *(_DWORD *)(a1 + 48) = 0,
                CryptDecodeObject(0x10001u, (LPCSTR)0x1F4, (const BYTE *)v5, v6, 0, 0, (DWORD *)(a1 + 48)))
            && (pvStructInfo = LocalAlloc(0x40u, *(unsigned int *)(a1 + 48)), (*(_QWORD *)(a1 + 40) = pvStructInfo) != 0) )
          {
            if ( CryptDecodeObject(
                   0x10001u,
                   (LPCSTR)0x1F4,
                   (const BYTE *)v5,
                   cbEncoded,
                   0,
                   pvStructInfo,
                   (DWORD *)(a1 + 48)) )
            {
              LocalFree(v5);
              SignersCert = (struct _CERT_CONTEXT *)GetSignersCert(
                                                      *(const struct _CMSG_SIGNER_INFO **)(a1 + 40),
                                                      *(void **)(a1 + 24),
                                                      *(_DWORD *)(*(_QWORD *)a1 + 56LL),
                                                      *(void ***)(*(_QWORD *)a1 + 64LL));
              *(_QWORD *)(a1 + 32) = SignersCert;
            }
            else
            {
              LocalFree(v5);
              LODWORD(SignersCert) = (unsigned int)LocalFree(*(HLOCAL *)(a1 + 40));
              *(_QWORD *)(a1 + 40) = 0;
            }
          }
          else
          {
            LODWORD(SignersCert) = (unsigned int)LocalFree(v5);
          }
        }
      }
      else
      {
        *(_DWORD *)(a1 + 80) = 1;
      }
    }
    else
    {
      LODWORD(SignersCert) = CryptMsgClose(v4);
      *(_QWORD *)(a1 + 64) = 0;
    }
  }
  return (int)SignersCert;
}

```

## disassembly

```asm
0x18000ada0  mov     rax, rsp
0x18000ada3  mov     [rax+10h], rbx
0x18000ada7  mov     [rax+18h], rsi
0x18000adab  push    rdi
0x18000adac  sub     rsp, 40h
0x18000adb0  mov     rbx, rcx
0x18000adb3  mov     qword ptr [rax-20h], 0
0x18000adbb  mov     ecx, 10001h; dwMsgEncodingType
0x18000adc0  mov     dword ptr [rax+8], 0
0x18000adc7  xor     r9d, r9d; hCryptProv
0x18000adca  mov     qword ptr [rax-28h], 0
0x18000add2  xor     r8d, r8d; dwMsgType
0x18000add5  xor     edx, edx; dwFlags
0x18000add7  call    cs:__imp_CryptMsgOpenToDecode
0x18000addd  mov     [rbx+40h], rax
0x18000ade1  test    rax, rax
0x18000ade4  jz      loc_18000AF64
0x18000adea  mov     rcx, [rbx]
0x18000aded  mov     edi, 1
0x18000adf2  mov     r9d, edi; fFinal
0x18000adf5  mov     rdx, [rcx+20h]
0x18000adf9  mov     rcx, rax; hCryptMsg
0x18000adfc  mov     r8d, [rdx+10h]; cbData
0x18000ae00  mov     rdx, [rdx+8]; pbData
0x18000ae04  call    cs:__imp_CryptMsgUpdate
0x18000ae0a  mov     rcx, [rbx+40h]; hCryptMsg
0x18000ae0e  test    eax, eax
0x18000ae10  jnz     short loc_18000AE25
0x18000ae12  call    cs:__imp_CryptMsgClose
0x18000ae18  mov     qword ptr [rbx+40h], 0
0x18000ae20  jmp     loc_18000AF64
0x18000ae25  xor     r9d, r9d; pvData
0x18000ae28  lea     rax, [rsp+48h+cbEncoded]
0x18000ae2d  xor     r8d, r8d; dwIndex
0x18000ae30  mov     [rsp+48h+pcbData], rax; pcbData
0x18000ae35  lea     esi, [r9+1Ch]
0x18000ae39  mov     edx, esi; dwParamType
0x18000ae3b  call    cs:__imp_CryptMsgGetParam
0x18000ae41  mov     eax, [rsp+48h+cbEncoded]
0x18000ae45  test    eax, eax
0x18000ae47  jnz     short loc_18000AE51
0x18000ae49  mov     [rbx+50h], edi
0x18000ae4c  jmp     loc_18000AF64
0x18000ae51  mov     rdx, rax; uBytes
0x18000ae54  mov     ecx, 40h ; '@'; uFlags
0x18000ae59  call    cs:__imp_LocalAlloc
0x18000ae5f  mov     rdi, rax
0x18000ae62  test    rax, rax
0x18000ae65  jz      loc_18000AF64
0x18000ae6b  mov     rcx, [rbx+40h]; hCryptMsg
0x18000ae6f  lea     rax, [rsp+48h+cbEncoded]
0x18000ae74  mov     r9, rdi; pvData
0x18000ae77  mov     [rsp+48h+pcbData], rax; pcbData
0x18000ae7c  xor     r8d, r8d; dwIndex
0x18000ae7f  mov     edx, esi; dwParamType
0x18000ae81  call    cs:__imp_CryptMsgGetParam
0x18000ae87  test    eax, eax
0x18000ae89  jz      loc_18000AF5B
0x18000ae8f  mov     r9d, [rsp+48h+cbEncoded]; cbEncoded
0x18000ae94  lea     rsi, [rbx+30h]
0x18000ae98  mov     [rsp+48h+pcbStructInfo], rsi; pcbStructInfo
0x18000ae9d  mov     r8, rdi; pbEncoded
0x18000aea0  mov     [rsp+48h+pvStructInfo], 0; pvStructInfo
0x18000aea9  mov     edx, 1F4h; lpszStructType
0x18000aeae  mov     ecx, 10001h; dwCertEncodingType
0x18000aeb3  mov     dword ptr [rsp+48h+pcbData], 0; dwFlags
0x18000aebb  mov     dword ptr [rbx+50h], 0
0x18000aec2  mov     dword ptr [rsi], 0
0x18000aec8  call    cs:__imp_CryptDecodeObject
0x18000aece  test    eax, eax
0x18000aed0  jz      loc_18000AF5B
0x18000aed6  mov     edx, [rsi]; uBytes
0x18000aed8  mov     ecx, 40h ; '@'; uFlags
0x18000aedd  call    cs:__imp_LocalAlloc
0x18000aee3  mov     [rbx+28h], rax
0x18000aee7  test    rax, rax
0x18000aeea  jz      short loc_18000AF5B
0x18000aeec  mov     r9d, [rsp+48h+cbEncoded]; cbEncoded
0x18000aef1  mov     r8, rdi; pbEncoded
0x18000aef4  mov     [rsp+48h+pcbStructInfo], rsi; pcbStructInfo
0x18000aef9  mov     edx, 1F4h; lpszStructType
0x18000aefe  mov     [rsp+48h+pvStructInfo], rax; pvStructInfo
0x18000af03  mov     ecx, 10001h; dwCertEncodingType
0x18000af08  mov     dword ptr [rsp+48h+pcbData], 0; dwFlags
0x18000af10  call    cs:__imp_CryptDecodeObject
0x18000af16  mov     rcx, rdi; hMem
0x18000af19  test    eax, eax
0x18000af1b  jnz     short loc_18000AF37
0x18000af1d  call    cs:__imp_LocalFree
0x18000af23  mov     rcx, [rbx+28h]; hMem
0x18000af27  call    cs:__imp_LocalFree
0x18000af2d  mov     qword ptr [rbx+28h], 0
0x18000af35  jmp     short loc_18000AF64
0x18000af37  call    cs:__imp_LocalFree
0x18000af3d  mov     r8, [rbx]
0x18000af40  mov     rdx, [rbx+18h]; void *
0x18000af44  mov     rcx, [rbx+28h]; struct _CMSG_SIGNER_INFO *
0x18000af48  mov     r9, [r8+40h]; void **
0x18000af4c  mov     r8d, [r8+38h]; unsigned int
0x18000af50  call    ?GetSignersCert@@YAPEBU_CERT_CONTEXT@@PEBU_CMSG_SIGNER_INFO@@PEAXKPEAPEAX@Z; GetSignersCert(_CMSG_SIGNER_INFO const *,void *,ulong,void * *)
0x18000af55  mov     [rbx+20h], rax
0x18000af59  jmp     short loc_18000AF64
0x18000af5b  mov     rcx, rdi; hMem
0x18000af5e  call    cs:__imp_LocalFree
0x18000af64  mov     rbx, [rsp+48h+arg_8]
0x18000af69  mov     rsi, [rsp+48h+arg_10]
0x18000af6e  add     rsp, 40h
0x18000af72  pop     rdi
0x18000af73  retn
```
