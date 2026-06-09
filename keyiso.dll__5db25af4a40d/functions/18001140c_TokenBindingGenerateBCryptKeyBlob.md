# TokenBindingGenerateBCryptKeyBlob

- ea: `0x18001140c`
- end: `0x18001159b`
- name: `TokenBindingGenerateBCryptKeyBlob`
- size: `399`
- prototype: `__int64 __fastcall(const wchar_t *, int, UCHAR **, ULONG *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800115a4`

## callees

- `0x180002d20`
- `0x180003cf0`
- `0x180006280`
- `0x18001140c`
- `0x180018904`

## import_xrefs

- `bcrypt!BCryptDestroyKey` at `0x180011564`
- `bcrypt!BCryptDestroyKey` at `0x180011564`
- `bcrypt!BCryptFinalizeKeyPair` at `0x18001147f`
- `bcrypt!BCryptFinalizeKeyPair` at `0x18001147f`
- `bcrypt!BCryptExportKey` at `0x1800114b7`
- `bcrypt!BCryptExportKey` at `0x180011513`
- `bcrypt!BCryptExportKey` at `0x1800114b7`
- `bcrypt!BCryptExportKey` at `0x180011513`
- `bcrypt!BCryptGenerateKeyPair` at `0x18001145e`
- `bcrypt!BCryptGenerateKeyPair` at `0x18001145e`

## string_xrefs

- `0x180011548`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\tokenbindingcryptoapi.c`

## pseudocode

```c
__int64 __fastcall TokenBindingGenerateBCryptKeyBlob(const wchar_t *a1, int a2, UCHAR **a3, ULONG *a4)
{
  UCHAR *v5; // rdi
  NTSTATUS v8; // ebx
  __int64 v9; // r9
  unsigned int v10; // ebx
  __int64 v11; // rcx
  UCHAR *v12; // rax
  ULONG v13; // eax
  __int64 v14; // rax
  UCHAR *v15; // rcx
  ULONG cbOutput; // [rsp+40h] [rbp-10h] BYREF
  BCRYPT_KEY_HANDLE phKey; // [rsp+48h] [rbp-8h] BYREF

  phKey = 0;
  v5 = 0;
  cbOutput = 0;
  if ( wcscmp_0(a1, L"RSA") || a2 != 2048 )
  {
    v10 = -2146893785;
    v9 = 48;
    v11 = 2148073511LL;
    goto LABEL_16;
  }
  v8 = BCryptGenerateKeyPair((BCRYPT_ALG_HANDLE)0xE1, &phKey, 0x800u, 0);
  if ( v8 >= 0 )
  {
    v8 = BCryptFinalizeKeyPair(phKey, 0);
    if ( v8 >= 0 )
    {
      v8 = BCryptExportKey(phKey, 0, L"RSAPRIVATEBLOB", 0, cbOutput, &cbOutput, 0);
      if ( v8 >= 0 )
      {
        v12 = (UCHAR *)MSCryptAlloc(cbOutput);
        v5 = v12;
        if ( !v12 )
        {
          v10 = -2146893810;
          v9 = 80;
          v11 = 2148073486LL;
          goto LABEL_16;
        }
        v8 = BCryptExportKey(phKey, 0, L"RSAPRIVATEBLOB", v12, cbOutput, &cbOutput, 0);
        if ( v8 >= 0 )
        {
          v13 = cbOutput;
          v10 = 0;
          *a3 = v5;
          v5 = 0;
          *a4 = v13;
          goto LABEL_17;
        }
        v9 = 88;
      }
      else
      {
        v9 = 72;
      }
    }
    else
    {
      v9 = 64;
    }
  }
  else
  {
    v9 = 56;
  }
  v10 = v8 | 0x10000000;
  v11 = v10;
LABEL_16:
  DebugTraceError(
    v11,
    "SecStatus",
    "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\tokenbindingcryptoapi.c",
    v9);
LABEL_17:
  if ( phKey )
    BCryptDestroyKey(phKey);
  if ( v5 )
  {
    v14 = cbOutput;
    v15 = v5;
    if ( cbOutput )
    {
      do
      {
        *v15++ = 0;
        --v14;
      }
      while ( v14 );
    }
    MSCryptFree(v5);
  }
  return v10;
}

```

## disassembly

```asm
0x18001140c  push    rbp
0x18001140e  push    rbx
0x18001140f  push    rsi
0x180011410  push    rdi
0x180011411  push    r14
0x180011413  mov     rbp, rsp
0x180011416  sub     rsp, 50h
0x18001141a  mov     ebx, edx
0x18001141c  mov     [rbp+phKey], 0
0x180011424  xor     edi, edi
0x180011426  lea     rdx, aRsa; "RSA"
0x18001142d  mov     [rbp+var_10], edi
0x180011430  mov     rsi, r9
0x180011433  mov     r14, r8
0x180011436  call    wcscmp_0
0x18001143b  test    eax, eax
0x18001143d  jnz     loc_180011538
0x180011443  mov     r8d, 800h; dwLength
0x180011449  cmp     ebx, r8d
0x18001144c  jnz     loc_180011538
0x180011452  xor     r9d, r9d; dwFlags
0x180011455  lea     rdx, [rbp+phKey]; phKey
0x180011459  mov     ecx, 0E1h; hAlgorithm
0x18001145e  call    cs:__imp_BCryptGenerateKeyPair
0x180011464  mov     ebx, eax
0x180011466  test    eax, eax
0x180011468  jns     short loc_180011479
0x18001146a  lea     r9d, [rdi+38h]
0x18001146e  bts     ebx, 1Ch
0x180011472  mov     ecx, ebx
0x180011474  jmp     loc_180011548
0x180011479  mov     rcx, [rbp+phKey]; hKey
0x18001147d  xor     edx, edx; dwFlags
0x18001147f  call    cs:__imp_BCryptFinalizeKeyPair
0x180011485  mov     ebx, eax
0x180011487  test    eax, eax
0x180011489  jns     short loc_180011493
0x18001148b  mov     r9d, 40h ; '@'
0x180011491  jmp     short loc_18001146E
0x180011493  mov     rcx, [rbp+phKey]; hKey
0x180011497  lea     rax, [rbp+var_10]
0x18001149b  mov     [rsp+50h+dwFlags], edi; dwFlags
0x18001149f  lea     r8, pszBlobType; "RSAPRIVATEBLOB"
0x1800114a6  mov     [rsp+50h+pcbResult], rax; pcbResult
0x1800114ab  xor     r9d, r9d; pbOutput
0x1800114ae  mov     eax, [rbp+var_10]
0x1800114b1  xor     edx, edx; hExportKey
0x1800114b3  mov     [rsp+50h+cbOutput], eax; cbOutput
0x1800114b7  call    cs:__imp_BCryptExportKey
0x1800114bd  mov     ebx, eax
0x1800114bf  test    eax, eax
0x1800114c1  jns     short loc_1800114CB
0x1800114c3  mov     r9d, 48h ; 'H'
0x1800114c9  jmp     short loc_18001146E
0x1800114cb  mov     ecx, [rbp+var_10]
0x1800114ce  call    MSCryptAlloc
0x1800114d3  mov     rdi, rax
0x1800114d6  test    rax, rax
0x1800114d9  jnz     short loc_1800114EB
0x1800114db  mov     ebx, 8009000Eh
0x1800114e0  lea     r9d, [rax+50h]
0x1800114e4  mov     ecx, 8009000Eh
0x1800114e9  jmp     short loc_180011548
0x1800114eb  mov     rcx, [rbp+phKey]; hKey
0x1800114ef  lea     rax, [rbp+var_10]
0x1800114f3  mov     [rsp+50h+dwFlags], 0; dwFlags
0x1800114fb  lea     r8, pszBlobType; "RSAPRIVATEBLOB"
0x180011502  mov     [rsp+50h+pcbResult], rax; pcbResult
0x180011507  mov     r9, rdi; pbOutput
0x18001150a  mov     eax, [rbp+var_10]
0x18001150d  xor     edx, edx; hExportKey
0x18001150f  mov     [rsp+50h+cbOutput], eax; cbOutput
0x180011513  call    cs:__imp_BCryptExportKey
0x180011519  mov     ebx, eax
0x18001151b  test    eax, eax
0x18001151d  jns     short loc_18001152A
0x18001151f  mov     r9d, 58h ; 'X'
0x180011525  jmp     loc_18001146E
0x18001152a  mov     eax, [rbp+var_10]
0x18001152d  xor     ebx, ebx
0x18001152f  mov     [r14], rdi
0x180011532  xor     edi, edi
0x180011534  mov     [rsi], eax
0x180011536  jmp     short loc_18001155B
0x180011538  mov     ebx, 80090027h
0x18001153d  mov     r9d, 30h ; '0'
0x180011543  mov     ecx, 80090027h
0x180011548  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18001154f  lea     rdx, aSecstatus; "SecStatus"
0x180011556  call    DebugTraceError
0x18001155b  mov     rcx, [rbp+phKey]; hKey
0x18001155f  test    rcx, rcx
0x180011562  jz      short loc_18001156A
0x180011564  call    cs:__imp_BCryptDestroyKey
0x18001156a  test    rdi, rdi
0x18001156d  jz      short loc_18001158E
0x18001156f  mov     eax, [rbp+var_10]
0x180011572  mov     rcx, rdi
0x180011575  test    rax, rax
0x180011578  jz      short loc_180011586
0x18001157a  mov     byte ptr [rcx], 0
0x18001157d  inc     rcx
0x180011580  sub     rax, 1
0x180011584  jnz     short loc_18001157A
0x180011586  mov     rcx, rdi
0x180011589  call    MSCryptFree
0x18001158e  mov     eax, ebx
0x180011590  add     rsp, 50h
0x180011594  pop     r14
0x180011596  pop     rdi
0x180011597  pop     rsi
0x180011598  pop     rbx
0x180011599  pop     rbp
0x18001159a  retn
```
