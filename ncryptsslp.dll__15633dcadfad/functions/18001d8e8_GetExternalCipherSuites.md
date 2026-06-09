# GetExternalCipherSuites

- ea: `0x18001d8e8`
- end: `0x18001de1b`
- name: `GetExternalCipherSuites`
- size: `1331`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180012578`

## callees

- `0x180003ef0`
- `0x180005860`
- `0x180007940`
- `0x18000fff0`
- `0x1800126f0`
- `0x180012d6c`
- `0x180014660`
- `0x1800183d0`
- `0x18001d648`
- `0x18001d6c0`
- `0x18001d72c`
- `0x18001d8e8`
- `0x180024450`
- `0x180024964`
- `0x180024d04`
- `0x180024ef0`
- `0x180025660`

## import_xrefs

- `ntdll!NtEnumerateKey` at `0x18001d9cb`
- `ntdll!NtEnumerateKey` at `0x18001d9cb`

## string_xrefs

- `0x18001d945`: `\Registry\MACHINE\System\CurrentControlSet\Control\Cryptography\Providers\Microsoft SSL Protocol Provider\CipherSuite`
- `0x18001da4d`: `\Registry\MACHINE\System\CurrentControlSet\Control\Cryptography\Providers\Microsoft SSL Protocol Provider\CipherSuite`

## pseudocode

```c
__int64 GetExternalCipherSuites()
{
  __int64 v0; // r12
  __int64 result; // rax
  _DWORD *v2; // rdi
  ULONG i; // esi
  unsigned __int64 v4; // rax
  _WORD *v5; // r14
  _WORD *v6; // rcx
  __int64 v7; // rdx
  _WORD *v8; // r8
  _WORD *v9; // rcx
  __int64 v10; // r13
  unsigned int j; // ebx
  __int64 v12; // rcx
  _DWORD *v13; // rsi
  void *v14; // rax
  __int64 v15; // rbx
  __int64 v16; // rcx
  __int64 v17; // rcx
  _DWORD *v18; // r15
  __int64 v19; // rcx
  __int64 v20; // rax
  __int64 v21; // rcx
  _DWORD *v22; // r12
  __int64 v23; // rax
  __int64 v24; // rdx
  wchar_t *v25; // rcx
  __int64 v26; // rdx
  __int64 v27; // rdx
  __int64 v28; // rdx
  __int64 v29; // rdx
  __int64 v30; // rcx
  int v31; // eax
  __int64 v32; // rcx
  __int64 v33; // rax
  ULONG v34; // [rsp+30h] [rbp-D0h]
  HANDLE v35; // [rsp+40h] [rbp-C0h] BYREF
  ULONG ResultLength; // [rsp+48h] [rbp-B8h] BYREF
  HANDLE KeyHandle; // [rsp+50h] [rbp-B0h] BYREF
  __int64 KeyExchangeInfoFromAlgorithmName; // [rsp+58h] [rbp-A8h]
  _QWORD *SignatureInfoFromAlgorithmName; // [rsp+60h] [rbp-A0h]
  __int64 HashInfoFromAlgorithmName; // [rsp+68h] [rbp-98h]
  _WORD KeyInformation[272]; // [rsp+70h] [rbp-90h] BYREF

  LODWORD(v0) = 0;
  KeyHandle = 0;
  v35 = 0;
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
      result = SafeAllocaAllocateFromHeap(1056);
      v2 = (_DWORD *)result;
      if ( result )
      {
        for ( i = 0; ; ++i )
        {
          v34 = i;
          if ( (unsigned int)g_dwCipherSuiteInfoTotalCount >= 0x3A )
            break;
          memset(v2, 0, 0x420u);
          memset(KeyInformation, 0, 0x218u);
          ResultLength = v0;
          if ( NtEnumerateKey(KeyHandle, i, KeyBasicInformation, KeyInformation, 0x218u, &ResultLength) < 0 )
            break;
          v4 = -1;
          do
            ++v4;
          while ( KeyInformation[v4 + 8] != (_WORD)v0 );
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
            *v9 = v0;
            if ( v7
              && (int)TlsOpenRegKey(
                        L"\\Registry\\MACHINE\\System\\CurrentControlSet\\Control\\Cryptography\\Providers\\Microsoft SSL "
                         "Protocol Provider\\CipherSuite",
                        (PCWSTR)v2 + 6,
                        &v35) >= 0 )
            {
              if ( (int)GetCipherSuiteDetailsFromRegistry(v35) >= 0 )
              {
                TlsCloseRegKey(&v35);
                if ( *v2 == 1 )
                {
                  HashInfoFromAlgorithmName = I_GetHashInfoFromAlgorithmName((wchar_t *)v2 + 70);
                  v0 = HashInfoFromAlgorithmName;
                  SignatureInfoFromAlgorithmName = (_QWORD *)I_GetSignatureInfoFromAlgorithmName((wchar_t *)v2 + 334);
                  v10 = 0;
                  KeyExchangeInfoFromAlgorithmName = I_GetKeyExchangeInfoFromAlgorithmName((wchar_t *)v2 + 266);
                  for ( j = 0; j < g_dwCipherInfoTotalCount; ++j )
                  {
                    v12 = g_pCipherInfo[j];
                    if ( v12
                      && *(_QWORD *)v12
                      && *(_QWORD *)(v12 + 24)
                      && !wcsnicmp((const wchar_t *)v2 + 134, *(const wchar_t **)v12, 0x40u)
                      && !wcsnicmp((const wchar_t *)v2 + 202, *(const wchar_t **)(g_pCipherInfo[j] + 24), 0x40u) )
                    {
                      v10 = g_pCipherInfo[j];
                      break;
                    }
                  }
                  if ( v0 )
                  {
                    LODWORD(v0) = 0;
                    if ( SignatureInfoFromAlgorithmName )
                    {
                      if ( KeyExchangeInfoFromAlgorithmName )
                      {
                        if ( v10 )
                        {
                          if ( (int)I_GetHashIndex((wchar_t *)v2 + 70) >= 0 )
                          {
                            v13 = v2 + 101;
                            if ( (int)I_GetCipherIndexFromAlgorithmNameAndMode((wchar_t *)v2 + 134, (wchar_t *)v2 + 202) >= 0 )
                            {
                              v14 = (void *)SafeAllocaAllocateFromHeap(144);
                              v15 = (__int64)v14;
                              if ( v14 )
                              {
                                memset(v14, 0, 0x90u);
                                v16 = -1;
                                do
                                  ++v16;
                                while ( v5[v16] );
                                *(_QWORD *)(v15 + 8) = SafeAllocaAllocateFromHeap(2 * v16 + 2);
                                v17 = -1;
                                do
                                  ++v17;
                                while ( *((_WORD *)v13 + v17) );
                                *(_QWORD *)(v15 + 48) = SafeAllocaAllocateFromHeap(2 * v17 + 2);
                                v18 = v2 + 231;
                                v19 = -1;
                                do
                                  ++v19;
                                while ( *((_WORD *)v18 + v19) );
                                v20 = SafeAllocaAllocateFromHeap(2 * v19 + 2);
                                v21 = -1;
                                *(_QWORD *)(v15 + 136) = v20;
                                v22 = v2 + 199;
                                do
                                  ++v21;
                                while ( *((_WORD *)v22 + v21) );
                                v23 = SafeAllocaAllocateFromHeap(2 * v21 + 2);
                                v25 = *(wchar_t **)(v15 + 8);
                                *(_QWORD *)(v15 + 104) = v23;
                                if ( !v25 || !*(_QWORD *)(v15 + 48) || !*(_QWORD *)(v15 + 136) || !v23 )
                                {
                                  FreeExternalCipherSuiteInfoFields(v15, v24, 0);
                                  MSCryptFree(v15);
                                  break;
                                }
                                v26 = -1;
                                do
                                  ++v26;
                                while ( v5[v26] );
                                wcscpy_s(v25, v26 + 1, (const wchar_t *)v2 + 6);
                                v27 = -1;
                                do
                                  ++v27;
                                while ( *((_WORD *)v13 + v27) );
                                wcscpy_s(*(wchar_t **)(v15 + 48), v27 + 1, (const wchar_t *)v2 + 202);
                                v28 = -1;
                                do
                                  ++v28;
                                while ( *((_WORD *)v18 + v28) );
                                wcscpy_s(*(wchar_t **)(v15 + 136), v28 + 1, (const wchar_t *)v2 + 462);
                                v29 = -1;
                                do
                                  ++v29;
                                while ( *((_WORD *)v22 + v29) );
                                wcscpy_s(*(wchar_t **)(v15 + 104), v29 + 1, (const wchar_t *)v2 + 398);
                                LODWORD(v0) = 0;
                                v30 = HashInfoFromAlgorithmName;
                                *(_DWORD *)v15 = v2[1];
                                *(_DWORD *)(v15 + 4) = v2[2];
                                *(_QWORD *)(v15 + 16) = *(_QWORD *)v10;
                                *(_DWORD *)(v15 + 24) = *(_DWORD *)(v10 + 16);
                                *(_DWORD *)(v15 + 28) = v2[99];
                                *(_DWORD *)(v15 + 32) = v2[100];
                                *(_DWORD *)(v15 + 36) = *(_DWORD *)(v10 + 8);
                                *(_DWORD *)(v15 + 40) = 0;
                                *(_QWORD *)(v15 + 56) = *(_QWORD *)v30;
                                *(_DWORD *)(v15 + 64) = *(_DWORD *)(v30 + 16);
                                v31 = *(_DWORD *)(v30 + 8);
                                v32 = KeyExchangeInfoFromAlgorithmName;
                                *(_DWORD *)(v15 + 68) = v31;
                                *(_DWORD *)(v15 + 72) = 0;
                                *(_QWORD *)(v15 + 80) = *(_QWORD *)v32;
                                *(_DWORD *)(v15 + 88) = *(_DWORD *)(v32 + 8);
                                *(_DWORD *)(v15 + 92) = v2[165];
                                *(_DWORD *)(v15 + 96) = v2[166];
                                *(_DWORD *)(v15 + 112) = v2[263];
                                *(_DWORD *)(v15 + 100) = *(_DWORD *)(v32 + 16);
                                *(_QWORD *)(v15 + 120) = *SignatureInfoFromAlgorithmName;
                                v33 = (unsigned int)g_dwCipherSuiteInfoTotalCount++;
                                *(_DWORD *)(v15 + 128) = 0;
                                g_pCipherSuiteInfo[v33] = v15;
                              }
                            }
                          }
                        }
                      }
                    }
                  }
                  i = v34;
                }
              }
              else
              {
                TlsCloseRegKey(&v35);
              }
            }
          }
          else
          {
            *v5 = v0;
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
0x18001d8e8  push    rbp
0x18001d8ea  push    rbx
0x18001d8eb  push    rsi
0x18001d8ec  push    rdi
0x18001d8ed  push    r12
0x18001d8ef  push    r13
0x18001d8f1  push    r14
0x18001d8f3  push    r15
0x18001d8f5  lea     rbp, [rsp-1A8h]
0x18001d8fd  sub     rsp, 2A8h
0x18001d904  mov     rax, cs:__security_cookie
0x18001d90b  xor     rax, rsp
0x18001d90e  mov     [rbp+1E0h+var_50], rax
0x18001d915  xor     r12d, r12d
0x18001d918  mov     [rsp+2E0h+KeyHandle], r12
0x18001d91d  mov     [rsp+2E0h+var_2A0], r12
0x18001d922  mov     [rsp+2E0h+var_2AC], r12d
0x18001d927  mov     [rsp+2E0h+var_2A8], r12d
0x18001d92c  call    FreeExternalCipherSuites
0x18001d931  cmp     cs:g_dwCipherSuiteInfoTotalCount, 3Ah ; ':'
0x18001d938  jnb     loc_18001DDF8
0x18001d93e  lea     r8, [rsp+2E0h+KeyHandle]; KeyHandle
0x18001d943  xor     edx, edx; PCWSTR
0x18001d945  lea     rcx, aRegistryMachin_3; "\\Registry\\MACHINE\\System\\CurrentCon"...
0x18001d94c  call    TlsOpenRegKey
0x18001d951  test    eax, eax
0x18001d953  js      loc_18001DDF8
0x18001d959  mov     ecx, 420h
0x18001d95e  call    SafeAllocaAllocateFromHeap
0x18001d963  mov     rdi, rax
0x18001d966  test    rax, rax
0x18001d969  jz      loc_18001DDF8
0x18001d96f  mov     esi, r12d
0x18001d972  cmp     cs:g_dwCipherSuiteInfoTotalCount, 3Ah ; ':'
0x18001d979  mov     [rsp+2E0h+var_2B0], esi
0x18001d97d  jnb     loc_18001DDE6
0x18001d983  xor     edx, edx; Val
0x18001d985  mov     r8d, 420h; Size
0x18001d98b  mov     rcx, rdi; void *
0x18001d98e  call    memset
0x18001d993  xor     edx, edx; Val
0x18001d995  lea     rcx, [rsp+2E0h+KeyInformation]; void *
0x18001d99a  mov     r8d, 218h; Size
0x18001d9a0  call    memset
0x18001d9a5  mov     rcx, [rsp+2E0h+KeyHandle]; KeyHandle
0x18001d9aa  lea     rax, [rsp+2E0h+var_298]
0x18001d9af  mov     [rsp+2E0h+ResultLength], rax; ResultLength
0x18001d9b4  lea     r9, [rsp+2E0h+KeyInformation]; KeyInformation
0x18001d9b9  xor     r8d, r8d; KeyInformationClass
0x18001d9bc  mov     [rsp+2E0h+Length], 218h; Length
0x18001d9c4  mov     edx, esi; Index
0x18001d9c6  mov     [rsp+2E0h+var_298], r12d
0x18001d9cb  call    cs:__imp_NtEnumerateKey
0x18001d9d1  test    eax, eax
0x18001d9d3  js      loc_18001DDE6
0x18001d9d9  lea     rcx, [rbp+1E0h+var_260]
0x18001d9dd  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001d9e1  inc     rax
0x18001d9e4  cmp     [rcx+rax*2], r12w
0x18001d9e9  jnz     short loc_18001D9E1
0x18001d9eb  lea     r14, [rdi+0Ch]
0x18001d9ef  cmp     rax, 7FFFFFFEh
0x18001d9f5  jbe     short loc_18001DA00
0x18001d9f7  mov     [r14], r12w
0x18001d9fb  jmp     loc_18001DDCF
0x18001da00  lea     rcx, [rbp+1E0h+var_260]
0x18001da04  mov     edx, 40h ; '@'
0x18001da09  mov     r8, r14
0x18001da0c  test    rax, rax
0x18001da0f  jz      short loc_18001DA30
0x18001da11  movzx   r9d, word ptr [rcx]
0x18001da15  test    r9w, r9w
0x18001da19  jz      short loc_18001DA30
0x18001da1b  mov     [r8], r9w
0x18001da1f  add     rcx, 2
0x18001da23  add     r8, 2
0x18001da27  dec     rax
0x18001da2a  sub     rdx, 1
0x18001da2e  jnz     short loc_18001DA0C
0x18001da30  test    rdx, rdx
0x18001da33  lea     rcx, [r8-2]
0x18001da37  cmovnz  rcx, r8
0x18001da3b  mov     [rcx], r12w
0x18001da3f  jz      loc_18001DDCF
0x18001da45  lea     r8, [rsp+2E0h+var_2A0]; KeyHandle
0x18001da4a  mov     rdx, r14; PCWSTR
0x18001da4d  lea     rcx, aRegistryMachin_3; "\\Registry\\MACHINE\\System\\CurrentCon"...
0x18001da54  call    TlsOpenRegKey
0x18001da59  test    eax, eax
0x18001da5b  js      loc_18001DDCF
0x18001da61  mov     rcx, [rsp+2E0h+var_2A0]; KeyHandle
0x18001da66  mov     rdx, rdi
0x18001da69  call    GetCipherSuiteDetailsFromRegistry
0x18001da6e  lea     rcx, [rsp+2E0h+var_2A0]
0x18001da73  test    eax, eax
0x18001da75  jns     short loc_18001DA81
0x18001da77  call    TlsCloseRegKey
0x18001da7c  jmp     loc_18001DDCF
0x18001da81  call    TlsCloseRegKey
0x18001da86  cmp     dword ptr [rdi], 1
0x18001da89  jnz     loc_18001DDCF
0x18001da8f  lea     r15, [rdi+8Ch]
0x18001da96  mov     rcx, r15; String1
0x18001da99  call    I_GetHashInfoFromAlgorithmName
0x18001da9e  lea     rcx, [rdi+29Ch]; String1
0x18001daa5  mov     [rsp+2E0h+var_278], rax
0x18001daaa  mov     r12, rax
0x18001daad  call    I_GetSignatureInfoFromAlgorithmName
0x18001dab2  lea     rcx, [rdi+214h]; String1
0x18001dab9  mov     [rsp+2E0h+var_280], rax
0x18001dabe  call    I_GetKeyExchangeInfoFromAlgorithmName
0x18001dac3  xor     r13d, r13d
0x18001dac6  mov     [rsp+2E0h+var_288], rax
0x18001dacb  mov     ebx, r13d
0x18001dace  cmp     ebx, cs:g_dwCipherInfoTotalCount
0x18001dad4  jnb     short loc_18001DB4C
0x18001dad6  mov     esi, ebx
0x18001dad8  lea     rax, __ImageBase
0x18001dadf  mov     rcx, rva g_pCipherInfo[rax+rsi*8]
0x18001dae7  test    rcx, rcx
0x18001daea  jz      short loc_18001DB39
0x18001daec  mov     rdx, [rcx]; String2
0x18001daef  test    rdx, rdx
0x18001daf2  jz      short loc_18001DB39
0x18001daf4  cmp     [rcx+18h], r13
0x18001daf8  jz      short loc_18001DB39
0x18001dafa  lea     rcx, [rdi+10Ch]; String1
0x18001db01  mov     r8d, 40h ; '@'; MaxCount
0x18001db07  call    _wcsnicmp
0x18001db0c  test    eax, eax
0x18001db0e  jnz     short loc_18001DB39
0x18001db10  lea     rax, __ImageBase
0x18001db17  mov     r8d, 40h ; '@'; MaxCount
0x18001db1d  mov     rdx, rva g_pCipherInfo[rax+rsi*8]
0x18001db25  lea     rcx, [rdi+194h]; String1
0x18001db2c  mov     rdx, [rdx+18h]; String2
0x18001db30  call    _wcsnicmp
0x18001db35  test    eax, eax
0x18001db37  jz      short loc_18001DB3D
0x18001db39  inc     ebx
0x18001db3b  jmp     short loc_18001DACE
0x18001db3d  lea     rax, __ImageBase
0x18001db44  mov     r13, rva g_pCipherInfo[rax+rsi*8]
0x18001db4c  test    r12, r12
0x18001db4f  jz      loc_18001DDCB
0x18001db55  xor     r12d, r12d
0x18001db58  cmp     [rsp+2E0h+var_280], r12
0x18001db5d  jz      loc_18001DDCB
0x18001db63  cmp     [rsp+2E0h+var_288], r12
0x18001db68  jz      loc_18001DDCB
0x18001db6e  test    r13, r13
0x18001db71  jz      loc_18001DDCB
0x18001db77  lea     rdx, [rsp+2E0h+var_2A8]
0x18001db7c  mov     rcx, r15; String1
0x18001db7f  call    I_GetHashIndex
0x18001db84  test    eax, eax
0x18001db86  js      loc_18001DDCB
0x18001db8c  lea     rsi, [rdi+194h]
0x18001db93  mov     rdx, rsi; wchar_t *
0x18001db96  lea     rcx, [rdi+10Ch]; String1
0x18001db9d  lea     r8, [rsp+2E0h+var_2AC]
0x18001dba2  call    I_GetCipherIndexFromAlgorithmNameAndMode
0x18001dba7  test    eax, eax
0x18001dba9  js      loc_18001DDCB
0x18001dbaf  mov     ecx, 90h
0x18001dbb4  call    SafeAllocaAllocateFromHeap
0x18001dbb9  mov     rbx, rax
0x18001dbbc  test    rax, rax
0x18001dbbf  jz      loc_18001DDCB
0x18001dbc5  xor     edx, edx; Val
0x18001dbc7  mov     r8d, 90h; Size
0x18001dbcd  mov     rcx, rax; void *
0x18001dbd0  call    memset
0x18001dbd5  or      r15, 0FFFFFFFFFFFFFFFFh
0x18001dbd9  mov     rcx, r15
0x18001dbdc  inc     rcx
0x18001dbdf  cmp     [r14+rcx*2], r12w
0x18001dbe4  jnz     short loc_18001DBDC
0x18001dbe6  lea     rcx, ds:2[rcx*2]
0x18001dbee  call    SafeAllocaAllocateFromHeap
0x18001dbf3  mov     [rbx+8], rax
0x18001dbf7  mov     rcx, r15
0x18001dbfa  inc     rcx
0x18001dbfd  cmp     [rsi+rcx*2], r12w
0x18001dc02  jnz     short loc_18001DBFA
0x18001dc04  lea     rcx, ds:2[rcx*2]
0x18001dc0c  call    SafeAllocaAllocateFromHeap
0x18001dc11  mov     [rbx+30h], rax
0x18001dc15  lea     r15, [rdi+39Ch]
0x18001dc1c  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18001dc20  inc     rcx
0x18001dc23  cmp     [r15+rcx*2], r12w
0x18001dc28  jnz     short loc_18001DC20
0x18001dc2a  lea     rcx, ds:2[rcx*2]
0x18001dc32  call    SafeAllocaAllocateFromHeap
0x18001dc37  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18001dc3b  mov     [rbx+88h], rax
0x18001dc42  xor     eax, eax
0x18001dc44  lea     r12, [rdi+31Ch]
0x18001dc4b  inc     rcx
0x18001dc4e  cmp     [r12+rcx*2], ax
0x18001dc53  jnz     short loc_18001DC4B
0x18001dc55  lea     rcx, ds:2[rcx*2]
0x18001dc5d  call    SafeAllocaAllocateFromHeap
0x18001dc62  mov     rcx, [rbx+8]; Destination
0x18001dc66  xor     r8d, r8d
0x18001dc69  mov     [rbx+68h], rax
0x18001dc6d  test    rcx, rcx
0x18001dc70  jz      loc_18001DDD6
0x18001dc76  cmp     [rbx+30h], r8
0x18001dc7a  jz      loc_18001DDD6
0x18001dc80  cmp     [rbx+88h], r8
0x18001dc87  jz      loc_18001DDD6
0x18001dc8d  test    rax, rax
0x18001dc90  jz      loc_18001DDD6
0x18001dc96  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18001dc9a  inc     rdx
0x18001dc9d  cmp     [r14+rdx*2], r8w
0x18001dca2  jnz     short loc_18001DC9A
0x18001dca4  inc     rdx; SizeInWords
0x18001dca7  mov     r8, r14; Source
0x18001dcaa  call    wcscpy_s
0x18001dcaf  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18001dcb3  xor     r14d, r14d
0x18001dcb6  inc     rdx
0x18001dcb9  cmp     [rsi+rdx*2], r14w
0x18001dcbe  jnz     short loc_18001DCB6
0x18001dcc0  mov     rcx, [rbx+30h]; Destination
0x18001dcc4  inc     rdx; SizeInWords
0x18001dcc7  mov     r8, rsi; Source
0x18001dcca  call    wcscpy_s
0x18001dccf  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18001dcd3  mov     rdx, rsi
0x18001dcd6  inc     rdx
0x18001dcd9  cmp     [r15+rdx*2], r14w
0x18001dcde  jnz     short loc_18001DCD6
0x18001dce0  mov     rcx, [rbx+88h]; Destination
0x18001dce7  inc     rdx; SizeInWords
0x18001dcea  mov     r8, r15; Source
0x18001dced  call    wcscpy_s
0x18001dcf2  mov     rdx, rsi
0x18001dcf5  inc     rdx
0x18001dcf8  cmp     [r12+rdx*2], r14w
0x18001dcfd  jnz     short loc_18001DCF5
0x18001dcff  mov     rcx, [rbx+68h]; Destination
0x18001dd03  inc     rdx; SizeInWords
0x18001dd06  mov     r8, r12; Source
0x18001dd09  call    wcscpy_s
0x18001dd0e  mov     eax, [rdi+4]
0x18001dd11  xor     r12d, r12d
0x18001dd14  mov     rcx, [rsp+2E0h+var_278]
0x18001dd19  mov     [rbx], eax
0x18001dd1b  mov     eax, [rdi+8]
0x18001dd1e  mov     [rbx+4], eax
0x18001dd21  mov     rax, [r13+0]
0x18001dd25  mov     [rbx+10h], rax
0x18001dd29  mov     eax, [r13+10h]
0x18001dd2d  mov     [rbx+18h], eax
0x18001dd30  mov     eax, [rdi+18Ch]
0x18001dd36  mov     [rbx+1Ch], eax
0x18001dd39  mov     eax, [rdi+190h]
0x18001dd3f  mov     [rbx+20h], eax
0x18001dd42  mov     eax, [r13+8]
0x18001dd46  mov     [rbx+24h], eax
0x18001dd49  mov     eax, [rsp+2E0h+var_2AC]
0x18001dd4d  mov     [rbx+28h], eax
0x18001dd50  mov     rax, [rcx]
0x18001dd53  mov     [rbx+38h], rax
0x18001dd57  mov     eax, [rcx+10h]
0x18001dd5a  mov     [rbx+40h], eax
0x18001dd5d  mov     eax, [rcx+8]
0x18001dd60  mov     rcx, [rsp+2E0h+var_288]
0x18001dd65  mov     [rbx+44h], eax
0x18001dd68  mov     eax, [rsp+2E0h+var_2A8]
0x18001dd6c  mov     [rbx+48h], eax
0x18001dd6f  mov     rax, [rcx]
0x18001dd72  mov     [rbx+50h], rax
0x18001dd76  mov     eax, [rcx+8]
0x18001dd79  mov     [rbx+58h], eax
0x18001dd7c  mov     eax, [rdi+294h]
0x18001dd82  mov     [rbx+5Ch], eax
0x18001dd85  mov     eax, [rdi+298h]
0x18001dd8b  mov     [rbx+60h], eax
0x18001dd8e  mov     eax, [rdi+41Ch]
0x18001dd94  mov     [rbx+70h], eax
0x18001dd97  mov     eax, [rcx+10h]
0x18001dd9a  lea     rcx, __ImageBase
0x18001dda1  mov     [rbx+64h], eax
0x18001dda4  mov     rax, [rsp+2E0h+var_280]
0x18001dda9  mov     rax, [rax]
0x18001ddac  mov     [rbx+78h], rax
0x18001ddb0  mov     eax, cs:g_dwCipherSuiteInfoTotalCount
0x18001ddb6  inc     cs:g_dwCipherSuiteInfoTotalCount
0x18001ddbc  mov     [rbx+80h], r12d
0x18001ddc3  mov     rva g_pCipherSuiteInfo[rcx+rax*8], rbx
0x18001ddcb  mov     esi, [rsp+2E0h+var_2B0]
0x18001ddcf  inc     esi
0x18001ddd1  jmp     loc_18001D972
0x18001ddd6  mov     rcx, rbx
0x18001ddd9  call    FreeExternalCipherSuiteInfoFields
  ... truncated ...
```
