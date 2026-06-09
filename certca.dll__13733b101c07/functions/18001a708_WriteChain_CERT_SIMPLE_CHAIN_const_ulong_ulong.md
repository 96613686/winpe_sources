# WriteChain(_CERT_SIMPLE_CHAIN const *,ulong,ulong)

- ea: `0x18001a708`
- end: `0x18001a9db`
- name: `?WriteChain@@YAXPEBU_CERT_SIMPLE_CHAIN@@KK@Z`
- size: `723`
- prototype: `void __fastcall(const struct _CERT_SIMPLE_CHAIN *, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x18001b07c`

## callees

- `0x180008400`
- `0x180008420`
- `0x180008610`
- `0x18000a320`
- `0x18000f718`
- `0x180012450`
- `0x18001a66c`
- `0x18001a708`
- `0x18001aa28`
- `0x1800382c0`

## import_xrefs

- `msvcrt!fclose` at `0x18001a9b4`
- `msvcrt!fclose` at `0x18001a9b4`
- `msvcrt!fputws` at `0x18001a892`
- `msvcrt!fputws` at `0x18001a892`
- `msvcrt!_wfopen_s` at `0x18001a83e`
- `msvcrt!_wfopen_s` at `0x18001a83e`
- `msvcrt!fwprintf` at `0x18001a8a7`
- `msvcrt!fwprintf` at `0x18001a911`
- `msvcrt!fwprintf` at `0x18001a954`
- `msvcrt!fwprintf` at `0x18001a8a7`
- `msvcrt!fwprintf` at `0x18001a911`
- `msvcrt!fwprintf` at `0x18001a954`
- `api-ms-win-core-file-l1-2-0!GetTempPathW` at `0x18001a753`
- `api-ms-win-core-file-l1-2-0!GetTempPathW` at `0x18001a753`
- `OLEAUT32!__imp_SysFreeString` at `0x18001a99b`
- `OLEAUT32!__imp_SysFreeString` at `0x18001a9a4`
- `OLEAUT32!__imp_SysFreeString` at `0x18001a99b`
- `OLEAUT32!__imp_SysFreeString` at `0x18001a9a4`

## pseudocode

```c
void __fastcall WriteChain(const struct _CERT_SIMPLE_CHAIN *a1, unsigned int a2, int a3)
{
  int v6; // eax
  OLECHAR *v7; // r14
  OLECHAR *v8; // r15
  int v9; // eax
  unsigned int v10; // ecx
  errno_t v11; // eax
  int v12; // edx
  __int64 i; // rbx
  PCERT_CHAIN_ELEMENT v14; // rdi
  const char *v15; // rcx
  PCERT_REVOCATION_INFO pRevocationInfo; // rdi
  PCERT_REVOCATION_CRL_INFO pCrlInfo; // rdi
  const struct _CRL_CONTEXT *pBaseCrlContext; // rdx
  const struct _CRL_CONTEXT *pDeltaCrlContext; // rdx
  FILE *Stream; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int64 v21; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int16 v22[40]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Buffer[304]; // [rsp+90h] [rbp-70h] BYREF

  Stream = 0;
  Buffer[0] = 0;
  if ( GetTempPathW(0x104u, Buffer) - 1 > 0x102 )
  {
    v6 = myHLastError();
    if ( v6 )
      CSPrintErrorLineFile(0x11A901A3u, v6);
    Buffer[0] = 0;
  }
  v7 = 0;
  v21 = 0;
  v8 = 0;
  v9 = StringCchLengthW(Buffer, 0x12Du, &v21);
  if ( v9 )
  {
    v10 = 296812963;
LABEL_33:
    v12 = v9;
    goto LABEL_34;
  }
  if ( !v21 || v22[v21 + 39] != 92 )
  {
    v9 = StringCchCatW(Buffer, 301, L"\\");
    if ( v9 )
    {
      v10 = 297206179;
      goto LABEL_33;
    }
  }
  v9 = StringCchPrintfW(v22, 0x27u, aChainDDTxt, a2, a3);
  if ( v9 )
  {
    v10 = 297730467;
    goto LABEL_33;
  }
  v9 = StringCchCatW(Buffer, 301, v22);
  if ( v9 )
  {
    v10 = 297927075;
    goto LABEL_33;
  }
  v11 = _wfopen_s(&Stream, Buffer, L"w,ccs=UTF-16LE");
  if ( v11 )
  {
    CSPrintErrorLineFileData2(Buffer, 0x11CA01A3u, v11, 0);
    v12 = -2147024894;
    v10 = 298582435;
LABEL_34:
    CSPrintErrorLineFile(v10, v12);
    goto LABEL_35;
  }
  for ( i = 0; (unsigned int)i < a1->cElement; i = (unsigned int)(i + 1) )
  {
    v14 = a1->rgpElement[i];
    if ( (_DWORD)i )
      fputws(L"\n", Stream);
    fwprintf(Stream, L"Certificate %d:\n", (unsigned int)i);
    v9 = WriteBlob(Stream, v14->pCertContext->pbCertEncoded, v14->pCertContext->cbCertEncoded, 0);
    if ( v9 )
    {
      v10 = 299827619;
      goto LABEL_33;
    }
    pRevocationInfo = v14->pRevocationInfo;
    if ( pRevocationInfo )
    {
      if ( pRevocationInfo->cbSize >= 0x28 )
      {
        pCrlInfo = pRevocationInfo->pCrlInfo;
        if ( pCrlInfo )
        {
          pBaseCrlContext = pCrlInfo->pBaseCrlContext;
          if ( pBaseCrlContext )
          {
            v8 = myCRLNumber(v15, pBaseCrlContext);
            fwprintf(Stream, L"\nCRL %s:\n", v8);
            v9 = WriteBlob(Stream, pCrlInfo->pBaseCrlContext->pbCrlEncoded, pCrlInfo->pBaseCrlContext->cbCrlEncoded, 9);
            if ( v9 )
            {
              v10 = 301466019;
              goto LABEL_33;
            }
          }
          pDeltaCrlContext = pCrlInfo->pDeltaCrlContext;
          if ( pDeltaCrlContext )
          {
            v7 = myCRLNumber(v15, pDeltaCrlContext);
            fwprintf(Stream, L"\nDelta CRL %s:\n", v7);
            v9 = WriteBlob(
                   Stream,
                   pCrlInfo->pDeltaCrlContext->pbCrlEncoded,
                   pCrlInfo->pDeltaCrlContext->cbCrlEncoded,
                   9);
            if ( v9 )
            {
              v10 = 302317987;
              goto LABEL_33;
            }
          }
        }
      }
    }
  }
LABEL_35:
  SysFreeString(v8);
  SysFreeString(v7);
  if ( Stream )
    fclose(Stream);
}

```

## disassembly

```asm
0x18001a708  push    rbp
0x18001a70a  push    rbx
0x18001a70b  push    rsi
0x18001a70c  push    rdi
0x18001a70d  push    r12
0x18001a70f  push    r14
0x18001a711  push    r15
0x18001a713  lea     rbp, [rsp-200h]
0x18001a71b  sub     rsp, 300h
0x18001a722  mov     rax, cs:__security_cookie
0x18001a729  xor     rax, rsp
0x18001a72c  mov     [rbp+230h+var_40], rax
0x18001a733  mov     ebx, edx
0x18001a735  mov     [rsp+330h+Stream], 0
0x18001a73e  mov     rsi, rcx
0x18001a741  lea     rdx, [rbp+230h+Buffer]; lpBuffer
0x18001a745  xor     eax, eax
0x18001a747  mov     ecx, 104h; nBufferLength
0x18001a74c  mov     [rbp+230h+Buffer], ax
0x18001a750  mov     edi, r8d
0x18001a753  call    cs:__imp_GetTempPathW
0x18001a759  dec     eax
0x18001a75b  cmp     eax, 102h
0x18001a760  jbe     short loc_18001A77D
0x18001a762  call    ?myHLastError@@YAJXZ; myHLastError(void)
0x18001a767  test    eax, eax
0x18001a769  jz      short loc_18001A777
0x18001a76b  mov     edx, eax; int
0x18001a76d  mov     ecx, 11A901A3h; unsigned int
0x18001a772  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x18001a777  xor     eax, eax
0x18001a779  mov     [rbp+230h+Buffer], ax
0x18001a77d  mov     r12d, 12Dh
0x18001a783  lea     r8, [rsp+330h+var_2F8]; unsigned __int64 *
0x18001a788  xor     r14d, r14d
0x18001a78b  lea     rcx, [rbp+230h+Buffer]; unsigned __int16 *
0x18001a78f  mov     edx, r12d; unsigned __int64
0x18001a792  mov     [rsp+330h+var_2F8], r14
0x18001a797  xor     r15d, r15d
0x18001a79a  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18001a79f  test    eax, eax
0x18001a7a1  jz      short loc_18001A7AD
0x18001a7a3  mov     ecx, 11B101A3h
0x18001a7a8  jmp     loc_18001A991
0x18001a7ad  mov     rax, [rsp+330h+var_2F8]
0x18001a7b2  test    rax, rax
0x18001a7b5  jz      short loc_18001A7C3
0x18001a7b7  mov     ecx, 5Ch ; '\'
0x18001a7bc  cmp     cx, [rbp+rax*2+230h+var_2A2]
0x18001a7c1  jz      short loc_18001A7E4
0x18001a7c3  lea     r8, asc_180061BD4; "\\"
0x18001a7ca  mov     rdx, r12; unsigned __int64
0x18001a7cd  lea     rcx, [rbp+230h+Buffer]; unsigned __int16 *
0x18001a7d1  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18001a7d6  test    eax, eax
0x18001a7d8  jz      short loc_18001A7E4
0x18001a7da  mov     ecx, 11B701A3h
0x18001a7df  jmp     loc_18001A991
0x18001a7e4  mov     r9d, ebx
0x18001a7e7  mov     [rsp+330h+var_310], edi
0x18001a7eb  lea     r8, aChainDDTxt; "Chain%d_%d.txt"
0x18001a7f2  mov     edx, 27h ; '''; unsigned __int64
0x18001a7f7  lea     rcx, [rsp+330h+var_2F0]; unsigned __int16 *
0x18001a7fc  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001a801  test    eax, eax
0x18001a803  jz      short loc_18001A80F
0x18001a805  mov     ecx, 11BF01A3h
0x18001a80a  jmp     loc_18001A991
0x18001a80f  lea     r8, [rsp+330h+var_2F0]; unsigned __int16 *
0x18001a814  mov     rdx, r12; unsigned __int64
0x18001a817  lea     rcx, [rbp+230h+Buffer]; unsigned __int16 *
0x18001a81b  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18001a820  test    eax, eax
0x18001a822  jz      short loc_18001A82E
0x18001a824  mov     ecx, 11C201A3h
0x18001a829  jmp     loc_18001A991
0x18001a82e  lea     r8, aWCcsUtf16le; "w,ccs=UTF-16LE"
0x18001a835  lea     rdx, [rbp+230h+Buffer]; FileName
0x18001a839  lea     rcx, [rsp+330h+Stream]; Stream
0x18001a83e  call    cs:__imp__wfopen_s
0x18001a844  test    eax, eax
0x18001a846  jz      short loc_18001A86B
0x18001a848  xor     r9d, r9d; int
0x18001a84b  lea     rcx, [rbp+230h+Buffer]; unsigned __int16 *
0x18001a84f  mov     r8d, eax; int
0x18001a852  mov     edx, 11CA01A3h; unsigned int
0x18001a857  call    ?CSPrintErrorLineFileData2@@YAXPEBGKJJ@Z; CSPrintErrorLineFileData2(ushort const *,ulong,long,long)
0x18001a85c  mov     edx, 80070002h
0x18001a861  mov     ecx, 11CC01A3h
0x18001a866  jmp     loc_18001A993
0x18001a86b  xor     ebx, ebx
0x18001a86d  lea     r12d, [rbx+9]
0x18001a871  cmp     ebx, [rsi+0Ch]
0x18001a874  jnb     loc_18001A998
0x18001a87a  mov     rax, [rsi+10h]
0x18001a87e  mov     rdi, [rax+rbx*8]
0x18001a882  test    ebx, ebx
0x18001a884  jz      short loc_18001A898
0x18001a886  mov     rdx, [rsp+330h+Stream]; Stream
0x18001a88b  lea     rcx, Buffer; "\n"
0x18001a892  call    cs:__imp_fputws
0x18001a898  mov     rcx, [rsp+330h+Stream]; Stream
0x18001a89d  lea     rdx, aCertificateD; "Certificate %d:\n"
0x18001a8a4  mov     r8d, ebx
0x18001a8a7  call    cs:__imp_fwprintf
0x18001a8ad  mov     rdx, [rdi+8]
0x18001a8b1  xor     r9d, r9d; unsigned int
0x18001a8b4  mov     rcx, [rsp+330h+Stream]; Stream
0x18001a8b9  mov     r8d, [rdx+10h]; cbBinary
0x18001a8bd  mov     rdx, [rdx+8]; pbBinary
0x18001a8c1  call    ?WriteBlob@@YAJPEAU_iobuf@@PEBEKK@Z; WriteBlob(_iobuf *,uchar const *,ulong,ulong)
0x18001a8c6  test    eax, eax
0x18001a8c8  jnz     loc_18001A98C
0x18001a8ce  mov     rdi, [rdi+18h]
0x18001a8d2  test    rdi, rdi
0x18001a8d5  jz      loc_18001A977
0x18001a8db  cmp     dword ptr [rdi], 28h ; '('
0x18001a8de  jb      loc_18001A977
0x18001a8e4  mov     rdi, [rdi+20h]
0x18001a8e8  test    rdi, rdi
0x18001a8eb  jz      loc_18001A977
0x18001a8f1  mov     rdx, [rdi+8]; struct _CRL_CONTEXT *
0x18001a8f5  test    rdx, rdx
0x18001a8f8  jz      short loc_18001A934
0x18001a8fa  call    ?myCRLNumber@@YAPEAGPEBDPEBU_CRL_CONTEXT@@@Z; myCRLNumber(char const *,_CRL_CONTEXT const *)
0x18001a8ff  mov     rcx, [rsp+330h+Stream]; Stream
0x18001a904  lea     rdx, aCrlS; "\nCRL %s:\n"
0x18001a90b  mov     r8, rax
0x18001a90e  mov     r15, rax
0x18001a911  call    cs:__imp_fwprintf
0x18001a917  mov     rdx, [rdi+8]
0x18001a91b  mov     r9d, r12d; unsigned int
0x18001a91e  mov     rcx, [rsp+330h+Stream]; Stream
0x18001a923  mov     r8d, [rdx+10h]; cbBinary
0x18001a927  mov     rdx, [rdx+8]; pbBinary
0x18001a92b  call    ?WriteBlob@@YAJPEAU_iobuf@@PEBEKK@Z; WriteBlob(_iobuf *,uchar const *,ulong,ulong)
0x18001a930  test    eax, eax
0x18001a932  jnz     short loc_18001A97E
0x18001a934  mov     rdx, [rdi+10h]; struct _CRL_CONTEXT *
0x18001a938  test    rdx, rdx
0x18001a93b  jz      short loc_18001A977
0x18001a93d  call    ?myCRLNumber@@YAPEAGPEBDPEBU_CRL_CONTEXT@@@Z; myCRLNumber(char const *,_CRL_CONTEXT const *)
0x18001a942  mov     rcx, [rsp+330h+Stream]; Stream
0x18001a947  lea     rdx, aDeltaCrlS; "\nDelta CRL %s:\n"
0x18001a94e  mov     r8, rax
0x18001a951  mov     r14, rax
0x18001a954  call    cs:__imp_fwprintf
0x18001a95a  mov     rdx, [rdi+10h]
0x18001a95e  mov     r9d, r12d; unsigned int
0x18001a961  mov     rcx, [rsp+330h+Stream]; Stream
0x18001a966  mov     r8d, [rdx+10h]; cbBinary
0x18001a96a  mov     rdx, [rdx+8]; pbBinary
0x18001a96e  call    ?WriteBlob@@YAJPEAU_iobuf@@PEBEKK@Z; WriteBlob(_iobuf *,uchar const *,ulong,ulong)
0x18001a973  test    eax, eax
0x18001a975  jnz     short loc_18001A985
0x18001a977  inc     ebx
0x18001a979  jmp     loc_18001A871
0x18001a97e  mov     ecx, 11F801A3h
0x18001a983  jmp     short loc_18001A991
0x18001a985  mov     ecx, 120501A3h
0x18001a98a  jmp     short loc_18001A991
0x18001a98c  mov     ecx, 11DF01A3h; unsigned int
0x18001a991  mov     edx, eax; int
0x18001a993  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x18001a998  mov     rcx, r15; bstrString
0x18001a99b  call    cs:__imp_SysFreeString
0x18001a9a1  mov     rcx, r14; bstrString
0x18001a9a4  call    cs:__imp_SysFreeString
0x18001a9aa  mov     rcx, [rsp+330h+Stream]; Stream
0x18001a9af  test    rcx, rcx
0x18001a9b2  jz      short loc_18001A9BA
0x18001a9b4  call    cs:__imp_fclose
0x18001a9ba  mov     rcx, [rbp+230h+var_40]
0x18001a9c1  xor     rcx, rsp; StackCookie
0x18001a9c4  call    __security_check_cookie
0x18001a9c9  add     rsp, 300h
0x18001a9d0  pop     r15
0x18001a9d2  pop     r14
0x18001a9d4  pop     r12
0x18001a9d6  pop     rdi
0x18001a9d7  pop     rsi
0x18001a9d8  pop     rbx
0x18001a9d9  pop     rbp
0x18001a9da  retn
```
