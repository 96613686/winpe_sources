# Dot11CryptDHComputeSharedSecret

- ea: `0x14008f978`
- end: `0x14008fb94`
- name: `Dot11CryptDHComputeSharedSecret`
- size: `540`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140039388`

## callees

- `0x14000599c`
- `0x14008f978`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14008fb2e`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14008fb2e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008fb3f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008fb3f`
- `ksecdd!BCryptDeriveKey` at `0x14008fa58`
- `ksecdd!BCryptDeriveKey` at `0x14008fab9`
- `ksecdd!BCryptDeriveKey` at `0x14008fa58`
- `ksecdd!BCryptDeriveKey` at `0x14008fab9`
- `ksecdd!BCryptSecretAgreement` at `0x14008fa18`
- `ksecdd!BCryptSecretAgreement` at `0x14008fa18`
- `ksecdd!BCryptImportKeyPair` at `0x14008f9f4`
- `ksecdd!BCryptImportKeyPair` at `0x14008f9f4`
- `ksecdd!BCryptDestroySecret` at `0x14008fb54`
- `ksecdd!BCryptDestroySecret` at `0x14008fb54`
- `ksecdd!BCryptDestroyKey` at `0x14008fb69`
- `ksecdd!BCryptDestroyKey` at `0x14008fb69`

## pseudocode

```c
__int64 __fastcall Dot11CryptDHComputeSharedSecret(void *a1, void *a2, ULONG a3, UCHAR *a4, _DWORD *a5, UCHAR **a6)
{
  _DWORD *v6; // rsi
  UCHAR **v8; // r14
  NTSTATUS v9; // edi
  const struct std::nothrow_t *v10; // rdx
  UCHAR *v11; // rax
  UCHAR *v12; // rbx
  __int64 v13; // rax
  unsigned __int64 v14; // r8
  UCHAR v15; // dl
  UCHAR *v16; // rcx
  UCHAR *v17; // rcx
  UCHAR *v18; // rcx
  BCRYPT_SECRET_HANDLE phAgreedSecret; // [rsp+40h] [rbp-10h] BYREF
  BCRYPT_KEY_HANDLE phKey; // [rsp+48h] [rbp-8h] BYREF
  ULONG pcbResult; // [rsp+70h] [rbp+20h] BYREF

  v6 = a5;
  v8 = a6;
  phKey = 0;
  phAgreedSecret = 0;
  *a5 = 0;
  *v8 = 0;
  pcbResult = 0;
  if ( a1 && a2 && a3 )
  {
    v9 = BCryptImportKeyPair(a1, 0, L"ECCPUBLICBLOB", &phKey, a4, a3, 0);
    if ( v9 >= 0 )
    {
      v9 = BCryptSecretAgreement(a2, phKey, &phAgreedSecret, 0);
      if ( v9 >= 0 )
      {
        v9 = BCryptDeriveKey(phAgreedSecret, L"TRUNCATE", 0, 0, 0, &pcbResult, 0);
        if ( v9 >= 0 )
        {
          v11 = (UCHAR *)operator new(pcbResult, v10);
          v12 = v11;
          if ( v11 )
          {
            v9 = BCryptDeriveKey(phAgreedSecret, L"TRUNCATE", 0, v11, pcbResult, &pcbResult, 0);
            v13 = pcbResult;
            if ( v9 < 0 )
            {
              v17 = v12;
              if ( pcbResult )
              {
                do
                {
                  *v12++ = 0;
                  --v13;
                }
                while ( v13 );
              }
              v18 = v17 - 16;
              if ( *(_QWORD *)v18 )
                ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)v18, v18);
              else
                ExFreePoolWithTag(v18, *((_DWORD *)v18 + 2));
            }
            else
            {
              v14 = 0;
              if ( (unsigned __int64)pcbResult >> 1 )
              {
                do
                {
                  v15 = v12[v14];
                  v16 = &v12[-v14 - 1];
                  v12[v14++] = v16[(unsigned int)v13];
                  v16[(unsigned int)v13] = v15;
                }
                while ( v14 < (unsigned __int64)(unsigned int)v13 >> 1 );
                LODWORD(v13) = pcbResult;
              }
              *v6 = v13;
              *v8 = v12;
            }
          }
          else
          {
            v9 = -1073741801;
          }
        }
        else
        {
          pcbResult = 0;
        }
      }
    }
    if ( phAgreedSecret )
      BCryptDestroySecret(phAgreedSecret);
    if ( phKey )
      BCryptDestroyKey(phKey);
  }
  else
  {
    return (unsigned int)-1073741811;
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x14008f978  mov     rax, rsp
0x14008f97b  mov     [rax+10h], rbx
0x14008f97f  mov     [rax+18h], rsi
0x14008f983  push    rbp
0x14008f984  push    rdi
0x14008f985  push    r14
0x14008f987  mov     rbp, rsp
0x14008f98a  sub     rsp, 50h
0x14008f98e  mov     rsi, [rbp+arg_20]
0x14008f992  mov     rbx, rdx
0x14008f995  mov     r14, [rbp+arg_28]
0x14008f999  mov     [rbp+phKey], 0
0x14008f9a1  mov     [rbp+phAgreedSecret], 0
0x14008f9a9  mov     dword ptr [rsi], 0
0x14008f9af  mov     qword ptr [r14], 0
0x14008f9b6  mov     [rbp+arg_0], 0
0x14008f9bd  test    rcx, rcx
0x14008f9c0  jz      loc_14008FB77
0x14008f9c6  test    rdx, rdx
0x14008f9c9  jz      loc_14008FB77
0x14008f9cf  test    r8d, r8d
0x14008f9d2  jz      loc_14008FB77
0x14008f9d8  mov     dword ptr [rax-38h], 0
0x14008f9df  xor     edx, edx; hImportKey
0x14008f9e1  mov     [rax-40h], r8d
0x14008f9e5  lea     r8, pszBlobType; "ECCPUBLICBLOB"
0x14008f9ec  mov     [rax-48h], r9
0x14008f9f0  lea     r9, [rbp+phKey]; phKey
0x14008f9f4  call    cs:__imp_BCryptImportKeyPair
0x14008f9fb  nop     dword ptr [rax+rax+00h]
0x14008fa00  mov     edi, eax
0x14008fa02  test    eax, eax
0x14008fa04  js      loc_14008FB4B
0x14008fa0a  mov     rdx, [rbp+phKey]; hPubKey
0x14008fa0e  lea     r8, [rbp+phAgreedSecret]; phAgreedSecret
0x14008fa12  xor     r9d, r9d; dwFlags
0x14008fa15  mov     rcx, rbx; hPrivKey
0x14008fa18  call    cs:__imp_BCryptSecretAgreement
0x14008fa1f  nop     dword ptr [rax+rax+00h]
0x14008fa24  mov     edi, eax
0x14008fa26  test    eax, eax
0x14008fa28  js      loc_14008FB4B
0x14008fa2e  mov     rcx, [rbp+phAgreedSecret]; hSharedSecret
0x14008fa32  lea     rax, [rbp+arg_0]
0x14008fa36  mov     [rsp+50h+dwFlags], 0; dwFlags
0x14008fa3e  lea     rdx, pwszKDF; "TRUNCATE"
0x14008fa45  mov     [rsp+50h+pcbResult], rax; pcbResult
0x14008fa4a  xor     r9d, r9d; pbDerivedKey
0x14008fa4d  xor     r8d, r8d; pParameterList
0x14008fa50  mov     [rsp+50h+cbDerivedKey], 0; cbDerivedKey
0x14008fa58  call    cs:__imp_BCryptDeriveKey
0x14008fa5f  nop     dword ptr [rax+rax+00h]
0x14008fa64  mov     edi, eax
0x14008fa66  test    eax, eax
0x14008fa68  jns     short loc_14008FA76
0x14008fa6a  mov     [rbp+arg_0], 0
0x14008fa71  jmp     loc_14008FB4B
0x14008fa76  mov     ecx, [rbp+arg_0]; unsigned __int64
0x14008fa79  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x14008fa7e  mov     rbx, rax
0x14008fa81  test    rax, rax
0x14008fa84  jnz     short loc_14008FA90
0x14008fa86  mov     edi, 0C0000017h
0x14008fa8b  jmp     loc_14008FB4B
0x14008fa90  mov     rcx, [rbp+phAgreedSecret]; hSharedSecret
0x14008fa94  lea     rax, [rbp+arg_0]
0x14008fa98  mov     [rsp+50h+dwFlags], 0; dwFlags
0x14008faa0  lea     rdx, pwszKDF; "TRUNCATE"
0x14008faa7  mov     [rsp+50h+pcbResult], rax; pcbResult
0x14008faac  mov     r9, rbx; pbDerivedKey
0x14008faaf  mov     eax, [rbp+arg_0]
0x14008fab2  xor     r8d, r8d; pParameterList
0x14008fab5  mov     [rsp+50h+cbDerivedKey], eax; cbDerivedKey
0x14008fab9  call    cs:__imp_BCryptDeriveKey
0x14008fac0  nop     dword ptr [rax+rax+00h]
0x14008fac5  mov     edi, eax
0x14008fac7  test    eax, eax
0x14008fac9  mov     eax, [rbp+arg_0]
0x14008facc  js      short loc_14008FB08
0x14008face  mov     r9d, eax
0x14008fad1  mov     r10d, eax
0x14008fad4  shr     r9, 1
0x14008fad7  mov     r8d, 0
0x14008fadd  jz      short loc_14008FB01
0x14008fadf  mov     dl, [rbx+r8]
0x14008fae3  lea     rcx, [rbx-1]
0x14008fae7  sub     rcx, r8
0x14008faea  mov     al, [rcx+r10]
0x14008faee  mov     [rbx+r8], al
0x14008faf2  inc     r8
0x14008faf5  mov     [rcx+r10], dl
0x14008faf9  cmp     r8, r9
0x14008fafc  jb      short loc_14008FADF
0x14008fafe  mov     eax, [rbp+arg_0]
0x14008fb01  mov     [rsi], eax
0x14008fb03  mov     [r14], rbx
0x14008fb06  jmp     short loc_14008FB4B
0x14008fb08  mov     rcx, rbx
0x14008fb0b  test    rax, rax
0x14008fb0e  jz      short loc_14008FB1C
0x14008fb10  mov     byte ptr [rbx], 0
0x14008fb13  inc     rbx
0x14008fb16  sub     rax, 1
0x14008fb1a  jnz     short loc_14008FB10
0x14008fb1c  add     rcx, 0FFFFFFFFFFFFFFF0h; P
0x14008fb20  mov     rax, [rcx]
0x14008fb23  test    rax, rax
0x14008fb26  jz      short loc_14008FB3C
0x14008fb28  mov     rdx, rcx; Entry
0x14008fb2b  mov     rcx, rax; Lookaside
0x14008fb2e  call    cs:__imp_ExFreeToNPagedLookasideList
0x14008fb35  nop     dword ptr [rax+rax+00h]
0x14008fb3a  jmp     short loc_14008FB4B
0x14008fb3c  mov     edx, [rcx+8]; Tag
0x14008fb3f  call    cs:__imp_ExFreePoolWithTag
0x14008fb46  nop     dword ptr [rax+rax+00h]
0x14008fb4b  mov     rcx, [rbp+phAgreedSecret]; hSecret
0x14008fb4f  test    rcx, rcx
0x14008fb52  jz      short loc_14008FB60
0x14008fb54  call    cs:__imp_BCryptDestroySecret
0x14008fb5b  nop     dword ptr [rax+rax+00h]
0x14008fb60  mov     rcx, [rbp+phKey]; hKey
0x14008fb64  test    rcx, rcx
0x14008fb67  jz      short loc_14008FB7C
0x14008fb69  call    cs:__imp_BCryptDestroyKey
0x14008fb70  nop     dword ptr [rax+rax+00h]
0x14008fb75  jmp     short loc_14008FB7C
0x14008fb77  mov     edi, 0C000000Dh
0x14008fb7c  lea     r11, [rsp+50h+var_s0]
0x14008fb81  mov     eax, edi
0x14008fb83  mov     rbx, [r11+28h]
0x14008fb87  mov     rsi, [r11+30h]
0x14008fb8b  mov     rsp, r11
0x14008fb8e  pop     r14
0x14008fb90  pop     rdi
0x14008fb91  pop     rbp
0x14008fb92  retn
```
