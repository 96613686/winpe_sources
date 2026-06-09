# GetExternalCipherSuites

- ea: `0x18008c514`
- end: `0x18008c9f7`
- name: `GetExternalCipherSuites`
- size: `1251`
- prototype: ``
- caller_count: `2`
- callee_count: `16`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18004fd80`
- `0x18008b618`

## callees

- `0x18000e090`
- `0x180010590`
- `0x18008c274`
- `0x18008c2ec`
- `0x18008c358`
- `0x18008c514`
- `0x18008e150`
- `0x18008e184`
- `0x18008e65c`
- `0x18008ea14`
- `0x18008eac4`
- `0x18008eeb0`
- `0x18008ef28`
- `0x18008f300`
- `0x1800a4260`
- `0x1800a4380`

## import_xrefs

- `ntoskrnl!ZwEnumerateKey` at `0x18008c5f4`
- `ntoskrnl!ZwEnumerateKey` at `0x18008c5f4`
- `ntoskrnl!wcscpy_s` at `0x18008c86a`
- `ntoskrnl!wcscpy_s` at `0x18008c890`
- `ntoskrnl!wcscpy_s` at `0x18008c8b7`
- `ntoskrnl!wcscpy_s` at `0x18008c8db`
- `ntoskrnl!wcscpy_s` at `0x18008c86a`
- `ntoskrnl!wcscpy_s` at `0x18008c890`
- `ntoskrnl!wcscpy_s` at `0x18008c8b7`
- `ntoskrnl!wcscpy_s` at `0x18008c8db`

## string_xrefs

- `0x18008c571`: `\Registry\MACHINE\System\CurrentControlSet\Control\Cryptography\Providers\Microsoft SSL Protocol Provider\CipherSuite`
- `0x18008c67c`: `\Registry\MACHINE\System\CurrentControlSet\Control\Cryptography\Providers\Microsoft SSL Protocol Provider\CipherSuite`

## pseudocode

```c
__int64 GetExternalCipherSuites()
{
  __int64 result; // rax
  __int64 v1; // rdx
  _DWORD *v2; // rdi
  ULONG i; // r13d
  unsigned __int64 v4; // rax
  _WORD *v5; // rsi
  _WORD *v6; // rcx
  __int64 v7; // rdx
  _WORD *v8; // r8
  _WORD *v9; // rcx
  _DWORD *v10; // r15
  __int64 v11; // r12
  __int64 CipherInfoFromAlgorithmNameAndMode; // rax
  __int64 v13; // rdx
  _DWORD *v14; // rax
  _DWORD *v15; // rbx
  __int64 v16; // rdx
  __int64 v17; // rcx
  __int64 v18; // rdx
  __int64 v19; // rcx
  __int64 v20; // rdx
  _DWORD *v21; // r14
  __int64 v22; // rcx
  __int64 v23; // rax
  __int64 v24; // rdx
  __int64 v25; // rcx
  _DWORD *v26; // r12
  __int64 v27; // rax
  __int64 v28; // rdx
  wchar_t *v29; // rcx
  __int64 v30; // rdx
  __int64 v31; // rdx
  __int64 v32; // rdx
  __int64 v33; // rdx
  __int64 v34; // rcx
  int v35; // eax
  __int64 v36; // rcx
  int v37; // eax
  __int64 v38; // rcx
  int v39; // eax
  __int64 v40; // rcx
  _QWORD *v41; // rax
  HANDLE v42; // [rsp+38h] [rbp-C8h] BYREF
  ULONG ResultLength; // [rsp+40h] [rbp-C0h] BYREF
  HANDLE KeyHandle; // [rsp+48h] [rbp-B8h] BYREF
  __int64 HashInfoFromAlgorithmName; // [rsp+50h] [rbp-B0h]
  __int64 SignatureInfoFromAlgorithmName; // [rsp+58h] [rbp-A8h]
  __int64 v47; // [rsp+60h] [rbp-A0h]
  __int64 KeyExchangeInfoFromAlgorithmName; // [rsp+68h] [rbp-98h]
  _WORD KeyInformation[272]; // [rsp+70h] [rbp-90h] BYREF

  KeyHandle = 0;
  v42 = 0;
  result = FreeExternalCipherSuites();
  if ( (unsigned int)g_dwCipherSuiteInfoTotalCount < 0x3A )
  {
    result = TlsOpenRegKey(
               L"\\Registry\\MACHINE\\System\\CurrentControlSet\\Control\\Cryptography\\Providers\\Microsoft SSL Protocol "
                "Provider\\CipherSuite",
               0,
               &KeyHandle);
    if ( (int)result >= 0 )
    {
      result = MSCryptAlloc(1056, v1);
      v2 = (_DWORD *)result;
      if ( result )
      {
        for ( i = 0; (unsigned int)g_dwCipherSuiteInfoTotalCount < 0x3A; ++i )
        {
          memset(v2, 0, 0x420u);
          memset(KeyInformation, 0, 0x218u);
          ResultLength = 0;
          if ( ZwEnumerateKey(KeyHandle, i, KeyBasicInformation, KeyInformation, 0x218u, &ResultLength) < 0 )
            break;
          v4 = -1;
          do
            ++v4;
          while ( KeyInformation[v4 + 8] );
          v5 = v2 + 3;
          if ( v4 <= 0x7FFFFFFE )
          {
            v6 = &KeyInformation[8];
            v7 = 64;
            v8 = v2 + 3;
            do
            {
              if ( !v4 )
                break;
              if ( !*v6 )
                break;
              *v8++ = *v6++;
              --v4;
              --v7;
            }
            while ( v7 );
            v9 = v8 - 1;
            if ( v7 )
              v9 = v8;
            *v9 = 0;
            if ( v7
              && (int)TlsOpenRegKey(
                        L"\\Registry\\MACHINE\\System\\CurrentControlSet\\Control\\Cryptography\\Providers\\Microsoft SSL "
                         "Protocol Provider\\CipherSuite",
                        (PCWSTR)v2 + 6,
                        &v42) >= 0 )
            {
              if ( (int)GetCipherSuiteDetailsFromRegistry(v42) >= 0 )
              {
                TlsCloseRegKey(&v42);
                if ( *v2 == 1 )
                {
                  HashInfoFromAlgorithmName = I_GetHashInfoFromAlgorithmName((wchar_t *)v2 + 70);
                  SignatureInfoFromAlgorithmName = I_GetSignatureInfoFromAlgorithmName((wchar_t *)v2 + 334);
                  v10 = v2 + 101;
                  KeyExchangeInfoFromAlgorithmName = I_GetKeyExchangeInfoFromAlgorithmName((wchar_t *)v2 + 266);
                  v11 = KeyExchangeInfoFromAlgorithmName;
                  CipherInfoFromAlgorithmNameAndMode = I_GetCipherInfoFromAlgorithmNameAndMode(
                                                         (wchar_t *)v2 + 134,
                                                         (wchar_t *)v2 + 202);
                  v47 = CipherInfoFromAlgorithmNameAndMode;
                  if ( HashInfoFromAlgorithmName )
                  {
                    if ( SignatureInfoFromAlgorithmName )
                    {
                      if ( v11 )
                      {
                        if ( CipherInfoFromAlgorithmNameAndMode )
                        {
                          if ( (int)I_GetHashIndex((wchar_t *)v2 + 70) >= 0
                            && (int)I_GetCipherIndexFromAlgorithmNameAndMode((wchar_t *)v2 + 134, (wchar_t *)v2 + 202) >= 0 )
                          {
                            v14 = (_DWORD *)MSCryptAlloc(144, v13);
                            v15 = v14;
                            if ( v14 )
                            {
                              memset(v14, 0, 0x90u);
                              v17 = -1;
                              do
                                ++v17;
                              while ( v5[v17] );
                              *((_QWORD *)v15 + 1) = MSCryptAlloc(2 * v17 + 2, v16);
                              v19 = -1;
                              do
                                ++v19;
                              while ( *((_WORD *)v10 + v19) );
                              *((_QWORD *)v15 + 6) = MSCryptAlloc(2 * v19 + 2, v18);
                              v21 = v2 + 231;
                              v22 = -1;
                              do
                                ++v22;
                              while ( *((_WORD *)v21 + v22) );
                              v23 = MSCryptAlloc(2 * v22 + 2, v20);
                              v25 = -1;
                              *((_QWORD *)v15 + 17) = v23;
                              v26 = v2 + 199;
                              do
                                ++v25;
                              while ( *((_WORD *)v26 + v25) );
                              v27 = MSCryptAlloc(2 * v25 + 2, v24);
                              v29 = (wchar_t *)*((_QWORD *)v15 + 1);
                              *((_QWORD *)v15 + 13) = v27;
                              if ( !v29 || !*((_QWORD *)v15 + 6) || !*((_QWORD *)v15 + 17) || !v27 )
                              {
                                FreeExternalCipherSuiteInfoFields(v15, v28, 0);
                                MSCryptFree(v15);
                                break;
                              }
                              v30 = -1;
                              do
                                ++v30;
                              while ( v5[v30] );
                              wcscpy_s(v29, v30 + 1, (const wchar_t *)v2 + 6);
                              v31 = -1;
                              do
                                ++v31;
                              while ( *((_WORD *)v10 + v31) );
                              wcscpy_s(*((wchar_t **)v15 + 6), v31 + 1, (const wchar_t *)v2 + 202);
                              v32 = -1;
                              do
                                ++v32;
                              while ( *((_WORD *)v21 + v32) );
                              wcscpy_s(*((wchar_t **)v15 + 17), v32 + 1, (const wchar_t *)v2 + 462);
                              v33 = -1;
                              do
                                ++v33;
                              while ( *((_WORD *)v26 + v33) );
                              wcscpy_s(*((wchar_t **)v15 + 13), v33 + 1, (const wchar_t *)v2 + 398);
                              v34 = v47;
                              *v15 = v2[1];
                              v15[1] = v2[2];
                              *((_QWORD *)v15 + 2) = *(_QWORD *)v34;
                              v15[6] = *(_DWORD *)(v34 + 16);
                              v15[7] = v2[99];
                              v15[8] = v2[100];
                              v35 = *(_DWORD *)(v34 + 8);
                              v36 = HashInfoFromAlgorithmName;
                              v15[9] = v35;
                              v15[10] = 0;
                              *((_QWORD *)v15 + 7) = *(_QWORD *)v36;
                              v15[16] = *(_DWORD *)(v36 + 16);
                              v37 = *(_DWORD *)(v36 + 8);
                              v38 = KeyExchangeInfoFromAlgorithmName;
                              v15[17] = v37;
                              v15[18] = 0;
                              *((_QWORD *)v15 + 10) = *(_QWORD *)v38;
                              v15[22] = *(_DWORD *)(v38 + 8);
                              v15[23] = v2[165];
                              v15[24] = v2[166];
                              v15[28] = v2[263];
                              v39 = *(_DWORD *)(v38 + 16);
                              v40 = (unsigned int)g_dwCipherSuiteInfoTotalCount;
                              v15[25] = v39;
                              v41 = (_QWORD *)SignatureInfoFromAlgorithmName;
                              g_pCipherSuiteInfo[v40] = (__int64)v15;
                              g_dwCipherSuiteInfoTotalCount = v40 + 1;
                              *((_QWORD *)v15 + 15) = *v41;
                              v15[32] = 0;
                            }
                          }
                        }
                      }
                    }
                  }
                }
              }
              else
              {
                TlsCloseRegKey(&v42);
              }
            }
          }
          else
          {
            *v5 = 0;
          }
        }
        TlsCloseRegKey(&KeyHandle);
        return MSCryptFree(v2);
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x18008c514  push    rbp
0x18008c516  push    rbx
0x18008c517  push    rsi
0x18008c518  push    rdi
0x18008c519  push    r12
0x18008c51b  push    r13
0x18008c51d  push    r14
0x18008c51f  push    r15
0x18008c521  lea     rbp, [rsp-1A8h]
0x18008c529  sub     rsp, 2A8h
0x18008c530  mov     rax, cs:__security_cookie
0x18008c537  xor     rax, rsp
0x18008c53a  mov     [rbp+1E0h+var_50], rax
0x18008c541  xor     r12d, r12d
0x18008c544  mov     [rsp+2E0h+KeyHandle], r12
0x18008c549  mov     [rsp+2E0h+var_2A8], r12
0x18008c54e  mov     [rsp+2E0h+var_2B0], r12d
0x18008c553  mov     [rsp+2E0h+var_2AC], r12d
0x18008c558  call    FreeExternalCipherSuites
0x18008c55d  cmp     cs:g_dwCipherSuiteInfoTotalCount, 3Ah ; ':'
0x18008c564  jnb     loc_18008C9D3
0x18008c56a  lea     r8, [rsp+2E0h+KeyHandle]; KeyHandle
0x18008c56f  xor     edx, edx; PCWSTR
0x18008c571  lea     rcx, aRegistryMachin_13; "\\Registry\\MACHINE\\System\\CurrentCon"...
0x18008c578  call    TlsOpenRegKey
0x18008c57d  test    eax, eax
0x18008c57f  js      loc_18008C9D3
0x18008c585  mov     ecx, 420h
0x18008c58a  call    MSCryptAlloc
0x18008c58f  mov     rdi, rax
0x18008c592  test    rax, rax
0x18008c595  jz      loc_18008C9D3
0x18008c59b  mov     r13d, r12d
0x18008c59e  cmp     cs:g_dwCipherSuiteInfoTotalCount, 3Ah ; ':'
0x18008c5a5  jnb     loc_18008C9C1
0x18008c5ab  xor     edx, edx; Val
0x18008c5ad  mov     r8d, 420h; Size
0x18008c5b3  mov     rcx, rdi; void *
0x18008c5b6  call    memset
0x18008c5bb  xor     edx, edx; Val
0x18008c5bd  lea     rcx, [rsp+2E0h+KeyInformation]; void *
0x18008c5c2  mov     r8d, 218h; Size
0x18008c5c8  call    memset
0x18008c5cd  mov     rcx, [rsp+2E0h+KeyHandle]; KeyHandle
0x18008c5d2  lea     rax, [rsp+2E0h+var_2A0]
0x18008c5d7  mov     [rsp+2E0h+ResultLength], rax; ResultLength
0x18008c5dc  lea     r9, [rsp+2E0h+KeyInformation]; KeyInformation
0x18008c5e1  xor     r8d, r8d; KeyInformationClass
0x18008c5e4  mov     [rsp+2E0h+Length], 218h; Length
0x18008c5ec  mov     edx, r13d; Index
0x18008c5ef  mov     [rsp+2E0h+var_2A0], r12d
0x18008c5f4  call    cs:__imp_ZwEnumerateKey
0x18008c5fb  nop     dword ptr [rax+rax+00h]
0x18008c600  test    eax, eax
0x18008c602  js      loc_18008C9C1
0x18008c608  lea     rcx, [rbp+1E0h+var_260]
0x18008c60c  or      rax, 0FFFFFFFFFFFFFFFFh
0x18008c610  inc     rax
0x18008c613  cmp     [rcx+rax*2], r12w
0x18008c618  jnz     short loc_18008C610
0x18008c61a  lea     rsi, [rdi+0Ch]
0x18008c61e  cmp     rax, 7FFFFFFEh
0x18008c624  jbe     short loc_18008C62F
0x18008c626  mov     [rsi], r12w
0x18008c62a  jmp     loc_18008C9A9
0x18008c62f  lea     rcx, [rbp+1E0h+var_260]
0x18008c633  mov     edx, 40h ; '@'
0x18008c638  mov     r8, rsi
0x18008c63b  test    rax, rax
0x18008c63e  jz      short loc_18008C65F
0x18008c640  movzx   r9d, word ptr [rcx]
0x18008c644  test    r9w, r9w
0x18008c648  jz      short loc_18008C65F
0x18008c64a  mov     [r8], r9w
0x18008c64e  add     rcx, 2
0x18008c652  add     r8, 2
0x18008c656  dec     rax
0x18008c659  sub     rdx, 1
0x18008c65d  jnz     short loc_18008C63B
0x18008c65f  test    rdx, rdx
0x18008c662  lea     rcx, [r8-2]
0x18008c666  cmovnz  rcx, r8
0x18008c66a  mov     [rcx], r12w
0x18008c66e  jz      loc_18008C9A9
0x18008c674  lea     r8, [rsp+2E0h+var_2A8]; KeyHandle
0x18008c679  mov     rdx, rsi; PCWSTR
0x18008c67c  lea     rcx, aRegistryMachin_13; "\\Registry\\MACHINE\\System\\CurrentCon"...
0x18008c683  call    TlsOpenRegKey
0x18008c688  test    eax, eax
0x18008c68a  js      loc_18008C9A9
0x18008c690  mov     rcx, [rsp+2E0h+var_2A8]; KeyHandle
0x18008c695  mov     rdx, rdi
0x18008c698  call    GetCipherSuiteDetailsFromRegistry
0x18008c69d  lea     rcx, [rsp+2E0h+var_2A8]
0x18008c6a2  test    eax, eax
0x18008c6a4  jns     short loc_18008C6B0
0x18008c6a6  call    TlsCloseRegKey
0x18008c6ab  jmp     loc_18008C9A9
0x18008c6b0  call    TlsCloseRegKey
0x18008c6b5  cmp     dword ptr [rdi], 1
0x18008c6b8  jnz     loc_18008C9A9
0x18008c6be  lea     rbx, [rdi+8Ch]
0x18008c6c5  mov     rcx, rbx; Str1
0x18008c6c8  call    I_GetHashInfoFromAlgorithmName
0x18008c6cd  lea     rcx, [rdi+29Ch]; Str1
0x18008c6d4  mov     [rsp+2E0h+var_290], rax
0x18008c6d9  call    I_GetSignatureInfoFromAlgorithmName
0x18008c6de  lea     rcx, [rdi+214h]; Str1
0x18008c6e5  mov     [rsp+2E0h+var_288], rax
0x18008c6ea  call    I_GetKeyExchangeInfoFromAlgorithmName
0x18008c6ef  lea     r15, [rdi+194h]
0x18008c6f6  mov     [rsp+2E0h+var_278], rax
0x18008c6fb  lea     r14, [rdi+10Ch]
0x18008c702  mov     rdx, r15; wchar_t *
0x18008c705  mov     rcx, r14; Str1
0x18008c708  mov     r12, rax
0x18008c70b  call    I_GetCipherInfoFromAlgorithmNameAndMode
0x18008c710  xor     ecx, ecx
0x18008c712  mov     [rsp+2E0h+var_280], rax
0x18008c717  cmp     [rsp+2E0h+var_290], rcx
0x18008c71c  jz      loc_18008C9A6
0x18008c722  cmp     [rsp+2E0h+var_288], rcx
0x18008c727  jz      loc_18008C9A6
0x18008c72d  test    r12, r12
0x18008c730  jz      loc_18008C9A6
0x18008c736  xor     r12d, r12d
0x18008c739  test    rax, rax
0x18008c73c  jz      loc_18008C9A9
0x18008c742  lea     rdx, [rsp+2E0h+var_2AC]
0x18008c747  mov     rcx, rbx; Str1
0x18008c74a  call    I_GetHashIndex
0x18008c74f  test    eax, eax
0x18008c751  js      loc_18008C9A9
0x18008c757  lea     r8, [rsp+2E0h+var_2B0]
0x18008c75c  mov     rdx, r15; wchar_t *
0x18008c75f  mov     rcx, r14; Str1
0x18008c762  call    I_GetCipherIndexFromAlgorithmNameAndMode
0x18008c767  test    eax, eax
0x18008c769  js      loc_18008C9A9
0x18008c76f  mov     ecx, 90h
0x18008c774  call    MSCryptAlloc
0x18008c779  mov     rbx, rax
0x18008c77c  test    rax, rax
0x18008c77f  jz      loc_18008C9A9
0x18008c785  xor     edx, edx; Val
0x18008c787  mov     r8d, 90h; Size
0x18008c78d  mov     rcx, rax; void *
0x18008c790  call    memset
0x18008c795  or      r14, 0FFFFFFFFFFFFFFFFh
0x18008c799  mov     rcx, r14
0x18008c79c  inc     rcx
0x18008c79f  cmp     [rsi+rcx*2], r12w
0x18008c7a4  jnz     short loc_18008C79C
0x18008c7a6  lea     rcx, ds:2[rcx*2]
0x18008c7ae  call    MSCryptAlloc
0x18008c7b3  mov     [rbx+8], rax
0x18008c7b7  mov     rcx, r14
0x18008c7ba  inc     rcx
0x18008c7bd  cmp     [r15+rcx*2], r12w
0x18008c7c2  jnz     short loc_18008C7BA
0x18008c7c4  lea     rcx, ds:2[rcx*2]
0x18008c7cc  call    MSCryptAlloc
0x18008c7d1  mov     [rbx+30h], rax
0x18008c7d5  lea     r14, [rdi+39Ch]
0x18008c7dc  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18008c7e0  inc     rcx
0x18008c7e3  cmp     [r14+rcx*2], r12w
0x18008c7e8  jnz     short loc_18008C7E0
0x18008c7ea  lea     rcx, ds:2[rcx*2]
0x18008c7f2  call    MSCryptAlloc
0x18008c7f7  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18008c7fb  mov     [rbx+88h], rax
0x18008c802  xor     eax, eax
0x18008c804  lea     r12, [rdi+31Ch]
0x18008c80b  inc     rcx
0x18008c80e  cmp     [r12+rcx*2], ax
0x18008c813  jnz     short loc_18008C80B
0x18008c815  lea     rcx, ds:2[rcx*2]
0x18008c81d  call    MSCryptAlloc
0x18008c822  mov     rcx, [rbx+8]; Dst
0x18008c826  xor     r8d, r8d
0x18008c829  mov     [rbx+68h], rax
0x18008c82d  test    rcx, rcx
0x18008c830  jz      loc_18008C9B1
0x18008c836  cmp     [rbx+30h], r8
0x18008c83a  jz      loc_18008C9B1
0x18008c840  cmp     [rbx+88h], r8
0x18008c847  jz      loc_18008C9B1
0x18008c84d  test    rax, rax
0x18008c850  jz      loc_18008C9B1
0x18008c856  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18008c85a  inc     rdx
0x18008c85d  cmp     [rsi+rdx*2], r8w
0x18008c862  jnz     short loc_18008C85A
0x18008c864  inc     rdx; SizeInWords
0x18008c867  mov     r8, rsi; Src
0x18008c86a  call    cs:__imp_wcscpy_s
0x18008c871  nop     dword ptr [rax+rax+00h]
0x18008c876  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18008c87a  xor     esi, esi
0x18008c87c  inc     rdx
0x18008c87f  cmp     [r15+rdx*2], si
0x18008c884  jnz     short loc_18008C87C
0x18008c886  mov     rcx, [rbx+30h]; Dst
0x18008c88a  inc     rdx; SizeInWords
0x18008c88d  mov     r8, r15; Src
0x18008c890  call    cs:__imp_wcscpy_s
0x18008c897  nop     dword ptr [rax+rax+00h]
0x18008c89c  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18008c8a0  inc     rdx
0x18008c8a3  cmp     [r14+rdx*2], si
0x18008c8a8  jnz     short loc_18008C8A0
0x18008c8aa  mov     rcx, [rbx+88h]; Dst
0x18008c8b1  inc     rdx; SizeInWords
0x18008c8b4  mov     r8, r14; Src
0x18008c8b7  call    cs:__imp_wcscpy_s
0x18008c8be  nop     dword ptr [rax+rax+00h]
0x18008c8c3  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18008c8c7  inc     rdx
0x18008c8ca  cmp     [r12+rdx*2], si
0x18008c8cf  jnz     short loc_18008C8C7
0x18008c8d1  mov     rcx, [rbx+68h]; Dst
0x18008c8d5  inc     rdx; SizeInWords
0x18008c8d8  mov     r8, r12; Src
0x18008c8db  call    cs:__imp_wcscpy_s
0x18008c8e2  nop     dword ptr [rax+rax+00h]
0x18008c8e7  mov     eax, [rdi+4]
0x18008c8ea  lea     rdx, g_pCipherSuiteInfo
0x18008c8f1  mov     rcx, [rsp+2E0h+var_280]
0x18008c8f6  xor     r12d, r12d
0x18008c8f9  mov     [rbx], eax
0x18008c8fb  mov     eax, [rdi+8]
0x18008c8fe  mov     [rbx+4], eax
0x18008c901  mov     rax, [rcx]
0x18008c904  mov     [rbx+10h], rax
0x18008c908  mov     eax, [rcx+10h]
0x18008c90b  mov     [rbx+18h], eax
0x18008c90e  mov     eax, [rdi+18Ch]
0x18008c914  mov     [rbx+1Ch], eax
0x18008c917  mov     eax, [rdi+190h]
0x18008c91d  mov     [rbx+20h], eax
0x18008c920  mov     eax, [rcx+8]
0x18008c923  mov     rcx, [rsp+2E0h+var_290]
0x18008c928  mov     [rbx+24h], eax
0x18008c92b  mov     eax, [rsp+2E0h+var_2B0]
0x18008c92f  mov     [rbx+28h], eax
0x18008c932  mov     rax, [rcx]
0x18008c935  mov     [rbx+38h], rax
0x18008c939  mov     eax, [rcx+10h]
0x18008c93c  mov     [rbx+40h], eax
0x18008c93f  mov     eax, [rcx+8]
0x18008c942  mov     rcx, [rsp+2E0h+var_278]
0x18008c947  mov     [rbx+44h], eax
0x18008c94a  mov     eax, [rsp+2E0h+var_2AC]
0x18008c94e  mov     [rbx+48h], eax
0x18008c951  mov     rax, [rcx]
0x18008c954  mov     [rbx+50h], rax
0x18008c958  mov     eax, [rcx+8]
0x18008c95b  mov     [rbx+58h], eax
0x18008c95e  mov     eax, [rdi+294h]
0x18008c964  mov     [rbx+5Ch], eax
0x18008c967  mov     eax, [rdi+298h]
0x18008c96d  mov     [rbx+60h], eax
0x18008c970  mov     eax, [rdi+41Ch]
0x18008c976  mov     [rbx+70h], eax
0x18008c979  mov     eax, [rcx+10h]
0x18008c97c  mov     ecx, cs:g_dwCipherSuiteInfoTotalCount
0x18008c982  mov     [rbx+64h], eax
0x18008c985  mov     rax, [rsp+2E0h+var_288]
0x18008c98a  mov     [rdx+rcx*8], rbx
0x18008c98e  inc     ecx
0x18008c990  mov     cs:g_dwCipherSuiteInfoTotalCount, ecx
0x18008c996  mov     rax, [rax]
0x18008c999  mov     [rbx+78h], rax
0x18008c99d  mov     [rbx+80h], r12d
0x18008c9a4  jmp     short loc_18008C9A9
0x18008c9a6  xor     r12d, r12d
0x18008c9a9  inc     r13d
0x18008c9ac  jmp     loc_18008C59E
0x18008c9b1  mov     rcx, rbx
0x18008c9b4  call    FreeExternalCipherSuiteInfoFields
0x18008c9b9  mov     rcx, rbx; P
0x18008c9bc  call    MSCryptFree
0x18008c9c1  lea     rcx, [rsp+2E0h+KeyHandle]
0x18008c9c6  call    TlsCloseRegKey
0x18008c9cb  mov     rcx, rdi; P
0x18008c9ce  call    MSCryptFree
0x18008c9d3  mov     rcx, [rbp+1E0h+var_50]
0x18008c9da  xor     rcx, rsp; StackCookie
0x18008c9dd  call    __security_check_cookie
0x18008c9e2  add     rsp, 2A8h
0x18008c9e9  pop     r15
0x18008c9eb  pop     r14
0x18008c9ed  pop     r13
0x18008c9ef  pop     r12
0x18008c9f1  pop     rdi
0x18008c9f2  pop     rsi
0x18008c9f3  pop     rbx
0x18008c9f4  pop     rbp
0x18008c9f5  retn
  ... truncated ...
```
