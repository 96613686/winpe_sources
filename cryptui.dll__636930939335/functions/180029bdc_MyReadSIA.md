# _MyReadSIA

- ea: `0x180029bdc`
- end: `0x180029e16`
- name: `_MyReadSIA`
- size: `570`
- prototype: `__int64 __usercall@<rax>(PCCERT_CONTEXT pCertContext@<rcx>, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180029bc0`

## callees

- `0x18000590c`
- `0x180029bdc`
- `0x18003e58e`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180029c63`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180029d2e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180029c63`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180029d2e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029cf2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029dad`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029dba`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029dc4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029dcd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029ddc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029dec`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029cf2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029dad`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029dba`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029dc4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029dcd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029ddc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029dec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029c30`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029c91`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029c30`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029c91`
- `CRYPT32!CryptDecodeObjectEx` at `0x180029cdf`
- `CRYPT32!CryptDecodeObjectEx` at `0x180029cdf`
- `CRYPT32!CertGetCertificateContextProperty` at `0x180029c26`
- `CRYPT32!CertGetCertificateContextProperty` at `0x180029c87`
- `CRYPT32!CertGetCertificateContextProperty` at `0x180029c26`
- `CRYPT32!CertGetCertificateContextProperty` at `0x180029c87`

## pseudocode

```c
__int64 __fastcall MyReadSIA(PCCERT_CONTEXT pCertContext, __int64 a2, __int64 a3, _QWORD *a4, _DWORD *a5)
{
  unsigned int v5; // r12d
  _QWORD *v6; // r13
  unsigned int v8; // ebx
  signed int LastError; // eax
  _DWORD *v10; // rax
  BYTE *v11; // r14
  BYTE *v12; // rax
  _QWORD *v13; // rsi
  __int64 v14; // rdi
  unsigned int v15; // r15d
  __int64 v16; // r13
  const char *v17; // rdx
  const unsigned __int16 *v18; // rcx
  unsigned __int16 *v19; // rax
  _DWORD *v20; // rcx
  HLOCAL hMem; // [rsp+40h] [rbp-10h] BYREF
  __int64 v23; // [rsp+48h] [rbp-8h]
  DWORD pcbData; // [rsp+98h] [rbp+48h] BYREF
  DWORD pcbStructInfo; // [rsp+A0h] [rbp+50h] BYREF
  int v26; // [rsp+A4h] [rbp+54h]
  _QWORD *v27; // [rsp+A8h] [rbp+58h]

  v27 = a4;
  v26 = HIDWORD(a3);
  v5 = 0;
  v6 = a4;
  hMem = 0;
  pcbStructInfo = 0;
  pcbData = 0;
  v8 = 0;
  if ( CertGetCertificateContextProperty(pCertContext, 0x51u, 0, &pcbData) )
  {
    v12 = (BYTE *)LocalAlloc(0x40u, pcbData);
    v11 = v12;
    if ( !v12 )
    {
LABEL_7:
      v8 = -2147024882;
      goto LABEL_28;
    }
    if ( !CertGetCertificateContextProperty(pCertContext, 0x51u, v12, &pcbData)
      || !CryptDecodeObjectEx(0x10001u, (LPCSTR)0x20, v11, pcbData, 0x8000u, 0, &hMem, &pcbStructInfo) )
    {
      LastError = GetLastError();
      v8 = LastError;
      if ( LastError <= 0 )
        goto LABEL_28;
      goto LABEL_10;
    }
    v13 = 0;
    v14 = 0;
    LocalFree(v11);
    if ( *((_QWORD *)hMem + 1) )
    {
      v15 = *(_DWORD *)hMem;
      if ( *(_DWORD *)hMem )
      {
        v11 = 0;
        if ( v15 >= 0x1FFFFFFF )
          goto LABEL_7;
        v13 = LocalAlloc(0x40u, 8LL * v15);
        if ( !v13 )
          goto LABEL_7;
        while ( v5 < v15 )
        {
          v16 = 32LL * v5;
          v23 = *((_QWORD *)hMem + 1);
          v17 = *(const char **)(v23 + v16);
          if ( v17 )
          {
            if ( !strcmp_0("1.3.6.1.5.5.7.48.1", v17) && *(_DWORD *)(v23 + v16 + 8) == 7 )
            {
              v18 = *(const unsigned __int16 **)(v23 + v16 + 16);
              if ( v18 )
              {
                v19 = AllocAndCopyWStr(v18);
                v13[v14] = v19;
                if ( !v19 )
                {
                  v8 = -2147024882;
                  while ( (_DWORD)v14 )
                  {
                    LODWORD(v14) = v14 - 1;
                    LocalFree((HLOCAL)v13[(unsigned int)v14]);
                  }
                  LocalFree(v13);
                  goto LABEL_28;
                }
                v14 = (unsigned int)(v14 + 1);
              }
            }
          }
          ++v5;
        }
        if ( !(_DWORD)v14 )
        {
          LocalFree(v13);
          v13 = 0;
        }
        v6 = v27;
      }
    }
    LocalFree(hMem);
    v20 = a5;
    *v6 = v13;
    *v20 = v14;
    return v8;
  }
  LastError = GetLastError();
  if ( LastError != -2146885628 )
  {
    v11 = 0;
    if ( LastError <= 0 )
    {
      v8 = LastError;
LABEL_28:
      LocalFree(hMem);
      LocalFree(v11);
      return v8;
    }
LABEL_10:
    v8 = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_28;
  }
  v10 = a5;
  *v6 = 0;
  *v10 = 0;
  return v8;
}

```

## disassembly

```asm
0x180029bdc  mov     rax, rsp
0x180029bdf  mov     [rax+8], rbx
0x180029be3  mov     [rax+20h], r9
0x180029be7  mov     [rax+18h], r8
0x180029beb  mov     [rax+10h], edx
0x180029bee  push    rbp
0x180029bef  push    rsi
0x180029bf0  push    rdi
0x180029bf1  push    r12
0x180029bf3  push    r13
0x180029bf5  push    r14
0x180029bf7  push    r15
0x180029bf9  mov     rbp, rsp
0x180029bfc  sub     rsp, 50h
0x180029c00  xor     r12d, r12d
0x180029c03  mov     r13, r9
0x180029c06  lea     r9, [rbp+pcbData]; pcbData
0x180029c0a  mov     [rbp+hMem], r12
0x180029c0e  xor     r8d, r8d; pvData
0x180029c11  mov     [rbp+arg_10], r12d
0x180029c15  mov     rdi, rcx
0x180029c18  mov     [rbp+pcbData], r12d
0x180029c1c  lea     esi, [r12+51h]
0x180029c21  mov     ebx, r12d
0x180029c24  mov     edx, esi; dwPropId
0x180029c26  call    cs:__imp_CertGetCertificateContextProperty
0x180029c2c  test    eax, eax
0x180029c2e  jnz     short loc_180029C5B
0x180029c30  call    cs:__imp_GetLastError
0x180029c36  cmp     eax, 80092004h
0x180029c3b  jnz     short loc_180029C4D
0x180029c3d  mov     rax, [rbp+arg_20]
0x180029c41  mov     [r13+0], r12
0x180029c45  mov     [rax], r12d
0x180029c48  jmp     loc_180029DFC
0x180029c4d  mov     r14, r12
0x180029c50  test    eax, eax
0x180029c52  jg      short loc_180029CA1
0x180029c54  mov     ebx, eax
0x180029c56  jmp     loc_180029DC0
0x180029c5b  mov     edx, [rbp+pcbData]; uBytes
0x180029c5e  mov     ecx, 40h ; '@'; uFlags
0x180029c63  call    cs:__imp_LocalAlloc
0x180029c69  mov     r14, rax
0x180029c6c  test    rax, rax
0x180029c6f  jnz     short loc_180029C7B
0x180029c71  mov     ebx, 8007000Eh
0x180029c76  jmp     loc_180029DC0
0x180029c7b  lea     r9, [rbp+pcbData]; pcbData
0x180029c7f  mov     r8, r14; pvData
0x180029c82  mov     edx, esi; dwPropId
0x180029c84  mov     rcx, rdi; pCertContext
0x180029c87  call    cs:__imp_CertGetCertificateContextProperty
0x180029c8d  test    eax, eax
0x180029c8f  jnz     short loc_180029CAF
0x180029c91  call    cs:__imp_GetLastError
0x180029c97  mov     ebx, eax
0x180029c99  test    eax, eax
0x180029c9b  jle     loc_180029DC0
0x180029ca1  movzx   ebx, ax
0x180029ca4  or      ebx, 80070000h
0x180029caa  jmp     loc_180029DC0
0x180029caf  mov     r9d, [rbp+pcbData]; cbEncoded
0x180029cb3  lea     rax, [rbp+arg_10]
0x180029cb7  mov     [rsp+50h+pcbStructInfo], rax; pcbStructInfo
0x180029cbc  mov     r8, r14; pbEncoded
0x180029cbf  lea     rax, [rbp+hMem]
0x180029cc3  mov     edx, 20h ; ' '; lpszStructType
0x180029cc8  mov     [rsp+50h+pvStructInfo], rax; pvStructInfo
0x180029ccd  mov     ecx, 10001h; dwCertEncodingType
0x180029cd2  mov     [rsp+50h+pDecodePara], r12; pDecodePara
0x180029cd7  mov     [rsp+50h+dwFlags], 8000h; dwFlags
0x180029cdf  call    cs:__imp_CryptDecodeObjectEx
0x180029ce5  test    eax, eax
0x180029ce7  jz      short loc_180029C91
0x180029ce9  mov     rcx, r14; hMem
0x180029cec  mov     rsi, r12
0x180029cef  mov     edi, r12d
0x180029cf2  call    cs:__imp_LocalFree
0x180029cf8  mov     r15, [rbp+hMem]
0x180029cfc  cmp     [r15+8], r12
0x180029d00  jz      loc_180029DE8
0x180029d06  mov     r15d, [r15]
0x180029d09  test    r15d, r15d
0x180029d0c  jz      loc_180029DE8
0x180029d12  mov     r14, r12
0x180029d15  cmp     r15d, 1FFFFFFFh
0x180029d1c  jnb     loc_180029C71
0x180029d22  mov     edx, r15d
0x180029d25  mov     ecx, 40h ; '@'; uFlags
0x180029d2a  shl     rdx, 3; uBytes
0x180029d2e  call    cs:__imp_LocalAlloc
0x180029d34  mov     rsi, rax
0x180029d37  test    rax, rax
0x180029d3a  jz      loc_180029C71
0x180029d40  cmp     r12d, r15d
0x180029d43  jnb     loc_180029DD5
0x180029d49  mov     rax, [rbp+hMem]
0x180029d4d  mov     r13d, r12d
0x180029d50  shl     r13, 5
0x180029d54  mov     rax, [rax+8]
0x180029d58  mov     [rbp+var_8], rax
0x180029d5c  mov     rdx, [rax+r13]; Str2
0x180029d60  test    rdx, rdx
0x180029d63  jz      short loc_180029D9B
0x180029d65  lea     rcx, a1361557481; "1.3.6.1.5.5.7.48.1"
0x180029d6c  call    strcmp_0
0x180029d71  test    eax, eax
0x180029d73  jnz     short loc_180029D9B
0x180029d75  mov     rax, [rbp+var_8]
0x180029d79  cmp     dword ptr [rax+r13+8], 7
0x180029d7f  jnz     short loc_180029D9B
0x180029d81  mov     rcx, [rax+r13+10h]; Src
0x180029d86  test    rcx, rcx
0x180029d89  jz      short loc_180029D9B
0x180029d8b  call    ?AllocAndCopyWStr@@YAPEAGPEBG@Z; AllocAndCopyWStr(ushort const *)
0x180029d90  mov     [rsi+rdi*8], rax
0x180029d94  test    rax, rax
0x180029d97  jz      short loc_180029DA0
0x180029d99  inc     edi
0x180029d9b  inc     r12d
0x180029d9e  jmp     short loc_180029D40
0x180029da0  mov     ebx, 8007000Eh
0x180029da5  jmp     short loc_180029DB3
0x180029da7  dec     edi
0x180029da9  mov     rcx, [rsi+rdi*8]; hMem
0x180029dad  call    cs:__imp_LocalFree
0x180029db3  test    edi, edi
0x180029db5  jnz     short loc_180029DA7
0x180029db7  mov     rcx, rsi; hMem
0x180029dba  call    cs:__imp_LocalFree
0x180029dc0  mov     rcx, [rbp+hMem]; hMem
0x180029dc4  call    cs:__imp_LocalFree
0x180029dca  mov     rcx, r14; hMem
0x180029dcd  call    cs:__imp_LocalFree
0x180029dd3  jmp     short loc_180029DFC
0x180029dd5  test    edi, edi
0x180029dd7  jnz     short loc_180029DE4
0x180029dd9  mov     rcx, rsi; hMem
0x180029ddc  call    cs:__imp_LocalFree
0x180029de2  xor     esi, esi
0x180029de4  mov     r13, [rbp+arg_18]
0x180029de8  mov     rcx, [rbp+hMem]; hMem
0x180029dec  call    cs:__imp_LocalFree
0x180029df2  mov     rcx, [rbp+arg_20]
0x180029df6  mov     [r13+0], rsi
0x180029dfa  mov     [rcx], edi
0x180029dfc  mov     eax, ebx
0x180029dfe  mov     rbx, [rsp+50h+arg_0]
0x180029e06  add     rsp, 50h
0x180029e0a  pop     r15
0x180029e0c  pop     r14
0x180029e0e  pop     r13
0x180029e10  pop     r12
0x180029e12  pop     rdi
0x180029e13  pop     rsi
0x180029e14  pop     rbp
0x180029e15  retn
```
