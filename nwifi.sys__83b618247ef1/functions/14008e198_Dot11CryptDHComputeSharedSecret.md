# Dot11CryptDHComputeSharedSecret

- ea: `0x14008e198`
- end: `0x14008e3b4`
- name: `Dot11CryptDHComputeSharedSecret`
- size: `540`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140039168`

## callees

- `0x14000599c`
- `0x14008e198`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14008e34e`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14008e34e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008e35f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008e35f`
- `ksecdd!BCryptDeriveKey` at `0x14008e278`
- `ksecdd!BCryptDeriveKey` at `0x14008e2d9`
- `ksecdd!BCryptDeriveKey` at `0x14008e278`
- `ksecdd!BCryptDeriveKey` at `0x14008e2d9`
- `ksecdd!BCryptSecretAgreement` at `0x14008e238`
- `ksecdd!BCryptSecretAgreement` at `0x14008e238`
- `ksecdd!BCryptImportKeyPair` at `0x14008e214`
- `ksecdd!BCryptImportKeyPair` at `0x14008e214`
- `ksecdd!BCryptDestroySecret` at `0x14008e374`
- `ksecdd!BCryptDestroySecret` at `0x14008e374`
- `ksecdd!BCryptDestroyKey` at `0x14008e389`
- `ksecdd!BCryptDestroyKey` at `0x14008e389`

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
0x14008e198  mov     rax, rsp
0x14008e19b  mov     [rax+10h], rbx
0x14008e19f  mov     [rax+18h], rsi
0x14008e1a3  push    rbp
0x14008e1a4  push    rdi
0x14008e1a5  push    r14
0x14008e1a7  mov     rbp, rsp
0x14008e1aa  sub     rsp, 50h
0x14008e1ae  mov     rsi, [rbp+arg_20]
0x14008e1b2  mov     rbx, rdx
0x14008e1b5  mov     r14, [rbp+arg_28]
0x14008e1b9  mov     [rbp+phKey], 0
0x14008e1c1  mov     [rbp+phAgreedSecret], 0
0x14008e1c9  mov     dword ptr [rsi], 0
0x14008e1cf  mov     qword ptr [r14], 0
0x14008e1d6  mov     [rbp+arg_0], 0
0x14008e1dd  test    rcx, rcx
0x14008e1e0  jz      loc_14008E397
0x14008e1e6  test    rdx, rdx
0x14008e1e9  jz      loc_14008E397
0x14008e1ef  test    r8d, r8d
0x14008e1f2  jz      loc_14008E397
0x14008e1f8  mov     dword ptr [rax-38h], 0
0x14008e1ff  xor     edx, edx; hImportKey
0x14008e201  mov     [rax-40h], r8d
0x14008e205  lea     r8, pszBlobType; "ECCPUBLICBLOB"
0x14008e20c  mov     [rax-48h], r9
0x14008e210  lea     r9, [rbp+phKey]; phKey
0x14008e214  call    cs:__imp_BCryptImportKeyPair
0x14008e21b  nop     dword ptr [rax+rax+00h]
0x14008e220  mov     edi, eax
0x14008e222  test    eax, eax
0x14008e224  js      loc_14008E36B
0x14008e22a  mov     rdx, [rbp+phKey]; hPubKey
0x14008e22e  lea     r8, [rbp+phAgreedSecret]; phAgreedSecret
0x14008e232  xor     r9d, r9d; dwFlags
0x14008e235  mov     rcx, rbx; hPrivKey
0x14008e238  call    cs:__imp_BCryptSecretAgreement
0x14008e23f  nop     dword ptr [rax+rax+00h]
0x14008e244  mov     edi, eax
0x14008e246  test    eax, eax
0x14008e248  js      loc_14008E36B
0x14008e24e  mov     rcx, [rbp+phAgreedSecret]; hSharedSecret
0x14008e252  lea     rax, [rbp+arg_0]
0x14008e256  mov     [rsp+50h+dwFlags], 0; dwFlags
0x14008e25e  lea     rdx, pwszKDF; "TRUNCATE"
0x14008e265  mov     [rsp+50h+pcbResult], rax; pcbResult
0x14008e26a  xor     r9d, r9d; pbDerivedKey
0x14008e26d  xor     r8d, r8d; pParameterList
0x14008e270  mov     [rsp+50h+cbDerivedKey], 0; cbDerivedKey
0x14008e278  call    cs:__imp_BCryptDeriveKey
0x14008e27f  nop     dword ptr [rax+rax+00h]
0x14008e284  mov     edi, eax
0x14008e286  test    eax, eax
0x14008e288  jns     short loc_14008E296
0x14008e28a  mov     [rbp+arg_0], 0
0x14008e291  jmp     loc_14008E36B
0x14008e296  mov     ecx, [rbp+arg_0]; unsigned __int64
0x14008e299  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x14008e29e  mov     rbx, rax
0x14008e2a1  test    rax, rax
0x14008e2a4  jnz     short loc_14008E2B0
0x14008e2a6  mov     edi, 0C0000017h
0x14008e2ab  jmp     loc_14008E36B
0x14008e2b0  mov     rcx, [rbp+phAgreedSecret]; hSharedSecret
0x14008e2b4  lea     rax, [rbp+arg_0]
0x14008e2b8  mov     [rsp+50h+dwFlags], 0; dwFlags
0x14008e2c0  lea     rdx, pwszKDF; "TRUNCATE"
0x14008e2c7  mov     [rsp+50h+pcbResult], rax; pcbResult
0x14008e2cc  mov     r9, rbx; pbDerivedKey
0x14008e2cf  mov     eax, [rbp+arg_0]
0x14008e2d2  xor     r8d, r8d; pParameterList
0x14008e2d5  mov     [rsp+50h+cbDerivedKey], eax; cbDerivedKey
0x14008e2d9  call    cs:__imp_BCryptDeriveKey
0x14008e2e0  nop     dword ptr [rax+rax+00h]
0x14008e2e5  mov     edi, eax
0x14008e2e7  test    eax, eax
0x14008e2e9  mov     eax, [rbp+arg_0]
0x14008e2ec  js      short loc_14008E328
0x14008e2ee  mov     r9d, eax
0x14008e2f1  mov     r10d, eax
0x14008e2f4  shr     r9, 1
0x14008e2f7  mov     r8d, 0
0x14008e2fd  jz      short loc_14008E321
0x14008e2ff  mov     dl, [rbx+r8]
0x14008e303  lea     rcx, [rbx-1]
0x14008e307  sub     rcx, r8
0x14008e30a  mov     al, [rcx+r10]
0x14008e30e  mov     [rbx+r8], al
0x14008e312  inc     r8
0x14008e315  mov     [rcx+r10], dl
0x14008e319  cmp     r8, r9
0x14008e31c  jb      short loc_14008E2FF
0x14008e31e  mov     eax, [rbp+arg_0]
0x14008e321  mov     [rsi], eax
0x14008e323  mov     [r14], rbx
0x14008e326  jmp     short loc_14008E36B
0x14008e328  mov     rcx, rbx
0x14008e32b  test    rax, rax
0x14008e32e  jz      short loc_14008E33C
0x14008e330  mov     byte ptr [rbx], 0
0x14008e333  inc     rbx
0x14008e336  sub     rax, 1
0x14008e33a  jnz     short loc_14008E330
0x14008e33c  add     rcx, 0FFFFFFFFFFFFFFF0h; P
0x14008e340  mov     rax, [rcx]
0x14008e343  test    rax, rax
0x14008e346  jz      short loc_14008E35C
0x14008e348  mov     rdx, rcx; Entry
0x14008e34b  mov     rcx, rax; Lookaside
0x14008e34e  call    cs:__imp_ExFreeToNPagedLookasideList
0x14008e355  nop     dword ptr [rax+rax+00h]
0x14008e35a  jmp     short loc_14008E36B
0x14008e35c  mov     edx, [rcx+8]; Tag
0x14008e35f  call    cs:__imp_ExFreePoolWithTag
0x14008e366  nop     dword ptr [rax+rax+00h]
0x14008e36b  mov     rcx, [rbp+phAgreedSecret]; hSecret
0x14008e36f  test    rcx, rcx
0x14008e372  jz      short loc_14008E380
0x14008e374  call    cs:__imp_BCryptDestroySecret
0x14008e37b  nop     dword ptr [rax+rax+00h]
0x14008e380  mov     rcx, [rbp+phKey]; hKey
0x14008e384  test    rcx, rcx
0x14008e387  jz      short loc_14008E39C
0x14008e389  call    cs:__imp_BCryptDestroyKey
0x14008e390  nop     dword ptr [rax+rax+00h]
0x14008e395  jmp     short loc_14008E39C
0x14008e397  mov     edi, 0C000000Dh
0x14008e39c  lea     r11, [rsp+50h+var_s0]
0x14008e3a1  mov     eax, edi
0x14008e3a3  mov     rbx, [r11+28h]
0x14008e3a7  mov     rsi, [r11+30h]
0x14008e3ab  mov     rsp, r11
0x14008e3ae  pop     r14
0x14008e3b0  pop     rdi
0x14008e3b1  pop     rbp
0x14008e3b2  retn
```
