# _EncryptContent(uchar *,ulong,char const *,_CERT_CONTEXT const *,uchar * *,ulong *)

- ea: `0x180004230`
- end: `0x180004438`
- name: `?_EncryptContent@@YAJPEAEKPEBDPEBU_CERT_CONTEXT@@PEAPEAEPEAK@Z`
- size: `520`
- prototype: `__int64 __fastcall(BYTE *pbToBeEncrypted, DWORD cbToBeEncrypted, CHAR *, const struct _CERT_CONTEXT *, unsigned __int8 **, unsigned int *)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180004ed0`
- `0x180005380`

## callees

- `0x180003750`
- `0x180004230`
- `0x180007d80`

## import_xrefs

- `CRYPT32!CryptEncryptMessage` at `0x180004302`
- `CRYPT32!CryptEncryptMessage` at `0x1800043af`
- `CRYPT32!CryptEncryptMessage` at `0x180004302`
- `CRYPT32!CryptEncryptMessage` at `0x1800043af`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000434a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000434a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000430c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800043b9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000430c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800043b9`

## pseudocode

```c
__int64 __fastcall _EncryptContent(
        BYTE *pbToBeEncrypted,
        DWORD cbToBeEncrypted,
        CHAR *a3,
        const struct _CERT_CONTEXT *a4,
        unsigned __int8 **a5,
        unsigned int *a6)
{
  unsigned __int8 **v6; // rsi
  unsigned int *v7; // r14
  signed int v10; // eax
  unsigned int v11; // ebx
  BYTE *pbEncryptedBlob; // rbx
  signed int LastError; // eax
  unsigned int v15; // esi
  DWORD v16; // eax
  struct _CRYPT_ENCRYPT_MESSAGE_PARA pEncryptPara; // [rsp+40h] [rbp-68h] BYREF
  DWORD pcbEncryptedBlob; // [rsp+C0h] [rbp+18h] BYREF
  PCCERT_CONTEXT rgpRecipientCert; // [rsp+C8h] [rbp+20h] BYREF

  rgpRecipientCert = a4;
  v6 = a5;
  v7 = a6;
  pEncryptPara.ContentEncryptionAlgorithm.pszObjId = a3;
  pcbEncryptedBlob = 0;
  *a5 = 0;
  *v7 = 0;
  pEncryptPara.hCryptProv = 0;
  pEncryptPara.cbSize = 56;
  pEncryptPara.dwMsgEncodingType = 65537;
  memset(&pEncryptPara.ContentEncryptionAlgorithm.Parameters, 0, 32);
  ekTraceFmt(0x41C12C2u, 2u, "TRACE: cemp.dwMsgEncodingType=%d\n", 65537);
  ekTraceFmt(
    0x41D12C2u,
    2u,
    "TRACE: cemp.ContentEncryptionAlgorithm.pszObjId=%hs\n",
    pEncryptPara.ContentEncryptionAlgorithm.pszObjId);
  pcbEncryptedBlob = 0;
  if ( CryptEncryptMessage(&pEncryptPara, 1u, &rgpRecipientCert, pbToBeEncrypted, cbToBeEncrypted, 0, &pcbEncryptedBlob) )
  {
    pbEncryptedBlob = (BYTE *)LocalAlloc(0x40u, pcbEncryptedBlob);
    if ( !pbEncryptedBlob )
    {
      ekTraceFmt(0x43212C2u, 1u, "ERROR: MIDL_user_allocate. Hr=%x\n", -2147024882);
      return 2147942414LL;
    }
    LODWORD(a5) = pcbEncryptedBlob;
    if ( CryptEncryptMessage(
           &pEncryptPara,
           1u,
           &rgpRecipientCert,
           pbToBeEncrypted,
           cbToBeEncrypted,
           pbEncryptedBlob,
           (DWORD *)&a5) )
    {
      v16 = pcbEncryptedBlob;
      if ( pcbEncryptedBlob == (_DWORD)a5 )
      {
        *v6 = pbEncryptedBlob;
        *v7 = v16;
        return 0;
      }
      v15 = -2147024736;
      ekTraceFmt(0x44712C2u, 1u, "ERROR: cbEnveloped != cbEnvelopedT. Hr=%x\n", 2147942560LL);
    }
    else
    {
      LastError = GetLastError();
      v15 = LastError;
      if ( LastError > 0 )
        v15 = (unsigned __int16)LastError | 0x80070000;
      ekTraceFmt(0x44112C2u, 1u, "ERROR: CryptEncryptMessage. Hr=%x\n", v15);
    }
    MIDL_user_free(pbEncryptedBlob);
    return v15;
  }
  v10 = GetLastError();
  v11 = v10;
  if ( v10 > 0 )
    v11 = (unsigned __int16)v10 | 0x80070000;
  ekTraceFmt(0x42A12C2u, 1u, "ERROR: CryptEncryptMessage. Hr=%x\n", v11);
  return v11;
}

```

## disassembly

```asm
0x180004230  mov     rax, rsp
0x180004233  mov     [rax+8], rbx
0x180004237  mov     [rax+10h], rbp
0x18000423b  mov     [rax+20h], r9
0x18000423f  push    rsi
0x180004240  push    rdi
0x180004241  push    r12
0x180004243  push    r14
0x180004245  push    r15
0x180004247  sub     rsp, 80h
0x18000424e  mov     rsi, [rsp+0A8h+arg_20]
0x180004256  xor     r12d, r12d
0x180004259  mov     r14, [rsp+0A8h+arg_28]
0x180004261  mov     ebp, edx
0x180004263  mov     r15, rcx
0x180004266  mov     [rax-58h], r8
0x18000426a  xorps   xmm0, xmm0
0x18000426d  mov     [rax+18h], r12d
0x180004271  xorps   xmm1, xmm1
0x180004274  mov     [rsi], r12
0x180004277  mov     r9d, 10001h
0x18000427d  mov     [r14], r12d
0x180004280  lea     r8, aTraceCempDwmsg; "TRACE: cemp.dwMsgEncodingType=%d\n"
0x180004287  mov     [rax-60h], r12
0x18000428b  mov     edx, 2; unsigned int
0x180004290  mov     dword ptr [rax-68h], 38h ; '8'
0x180004297  mov     ecx, 41C12C2h; unsigned int
0x18000429c  mov     dword ptr [rax-64h], 10001h
0x1800042a3  movdqu  xmmword ptr [rax-50h], xmm0
0x1800042a8  movdqu  xmmword ptr [rax-40h], xmm1
0x1800042ad  call    ?ekTraceFmt@@YAXKKPEBDZZ; ekTraceFmt(ulong,ulong,char const *,...)
0x1800042b2  mov     r9, [rsp+0A8h+pEncryptPara.ContentEncryptionAlgorithm.pszObjId]
0x1800042b7  lea     r8, aTraceCempConte; "TRACE: cemp.ContentEncryptionAlgorithm."...
0x1800042be  mov     edx, 2; unsigned int
0x1800042c3  mov     ecx, 41D12C2h; unsigned int
0x1800042c8  call    ?ekTraceFmt@@YAXKKPEBDZZ; ekTraceFmt(ulong,ulong,char const *,...)
0x1800042cd  lea     rax, [rsp+0A8h+arg_10]
0x1800042d5  mov     [rsp+0A8h+arg_10], r12d
0x1800042dd  mov     [rsp+0A8h+pcbEncryptedBlob], rax; pcbEncryptedBlob
0x1800042e2  lea     r8, [rsp+0A8h+rgpRecipientCert]; rgpRecipientCert
0x1800042ea  mov     edi, 1
0x1800042ef  mov     [rsp+0A8h+pbEncryptedBlob], r12; pbEncryptedBlob
0x1800042f4  mov     r9, r15; pbToBeEncrypted
0x1800042f7  mov     [rsp+0A8h+cbToBeEncrypted], ebp; cbToBeEncrypted
0x1800042fb  mov     edx, edi; cRecipientCert
0x1800042fd  lea     rcx, [rsp+0A8h+pEncryptPara]; pEncryptPara
0x180004302  call    cs:__imp_CryptEncryptMessage
0x180004308  test    eax, eax
0x18000430a  jnz     short loc_18000433E
0x18000430c  call    cs:__imp_GetLastError
0x180004312  mov     ebx, eax
0x180004314  test    eax, eax
0x180004316  jle     short loc_180004321
0x180004318  movzx   ebx, ax
0x18000431b  or      ebx, 80070000h
0x180004321  mov     r9d, ebx
0x180004324  lea     r8, aErrorCryptencr; "ERROR: CryptEncryptMessage. Hr=%x\n"
0x18000432b  mov     edx, edi; unsigned int
0x18000432d  mov     ecx, 42A12C2h; unsigned int
0x180004332  call    ?ekTraceFmt@@YAXKKPEBDZZ; ekTraceFmt(ulong,ulong,char const *,...)
0x180004337  mov     eax, ebx
0x180004339  jmp     loc_18000441C
0x18000433e  mov     edx, [rsp+0A8h+arg_10]; uBytes
0x180004345  mov     ecx, 40h ; '@'; uFlags
0x18000434a  call    cs:__imp_LocalAlloc
0x180004350  mov     rbx, rax
0x180004353  mov     edx, edi; unsigned int
0x180004355  test    rax, rax
0x180004358  jnz     short loc_18000437B
0x18000435a  mov     r9d, 8007000Eh
0x180004360  lea     r8, aErrorMidlUserA; "ERROR: MIDL_user_allocate. Hr=%x\n"
0x180004367  mov     ecx, 43212C2h; unsigned int
0x18000436c  call    ?ekTraceFmt@@YAXKKPEBDZZ; ekTraceFmt(ulong,ulong,char const *,...)
0x180004371  mov     eax, 8007000Eh
0x180004376  jmp     loc_18000441C
0x18000437b  mov     eax, [rsp+0A8h+arg_10]
0x180004382  lea     r8, [rsp+0A8h+rgpRecipientCert]; rgpRecipientCert
0x18000438a  mov     dword ptr [rsp+0A8h+arg_20], eax
0x180004391  lea     rcx, [rsp+0A8h+pEncryptPara]; pEncryptPara
0x180004396  lea     rax, [rsp+0A8h+arg_20]
0x18000439e  mov     r9, r15; pbToBeEncrypted
0x1800043a1  mov     [rsp+0A8h+pcbEncryptedBlob], rax; pcbEncryptedBlob
0x1800043a6  mov     [rsp+0A8h+pbEncryptedBlob], rbx; pbEncryptedBlob
0x1800043ab  mov     [rsp+0A8h+cbToBeEncrypted], ebp; cbToBeEncrypted
0x1800043af  call    cs:__imp_CryptEncryptMessage
0x1800043b5  test    eax, eax
0x1800043b7  jnz     short loc_1800043DC
0x1800043b9  call    cs:__imp_GetLastError
0x1800043bf  mov     esi, eax
0x1800043c1  test    eax, eax
0x1800043c3  jle     short loc_1800043CE
0x1800043c5  movzx   esi, ax
0x1800043c8  or      esi, 80070000h
0x1800043ce  mov     ecx, 44112C2h
0x1800043d3  lea     r8, aErrorCryptencr; "ERROR: CryptEncryptMessage. Hr=%x\n"
0x1800043da  jmp     short loc_1800043FD
0x1800043dc  mov     eax, [rsp+0A8h+arg_10]
0x1800043e3  cmp     eax, dword ptr [rsp+0A8h+arg_20]
0x1800043ea  jz      short loc_180004413
0x1800043ec  mov     esi, 800700A0h
0x1800043f1  lea     r8, aErrorCbenvelop; "ERROR: cbEnveloped != cbEnvelopedT. Hr="...
0x1800043f8  mov     ecx, 44712C2h; unsigned int
0x1800043fd  mov     r9d, esi
0x180004400  mov     edx, edi; unsigned int
0x180004402  call    ?ekTraceFmt@@YAXKKPEBDZZ; ekTraceFmt(ulong,ulong,char const *,...)
0x180004407  mov     rcx, rbx; void *
0x18000440a  call    MIDL_user_free
0x18000440f  mov     eax, esi
0x180004411  jmp     short loc_18000441C
0x180004413  mov     [rsi], rbx
0x180004416  mov     [r14], eax
0x180004419  mov     eax, r12d
0x18000441c  lea     r11, [rsp+0A8h+var_28]
0x180004424  mov     rbx, [r11+30h]
0x180004428  mov     rbp, [r11+38h]
0x18000442c  mov     rsp, r11
0x18000442f  pop     r15
0x180004431  pop     r14
0x180004433  pop     r12
0x180004435  pop     rdi
0x180004436  pop     rsi
0x180004437  retn
```
