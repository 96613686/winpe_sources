# GetExternalCipherSuites

- ea: `0x180082324`
- end: `0x180082807`
- name: `GetExternalCipherSuites`
- size: `1251`
- prototype: ``
- caller_count: `2`
- callee_count: `16`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180045c90`
- `0x180081428`

## callees

- `0x180003f70`
- `0x180006470`
- `0x180082084`
- `0x1800820fc`
- `0x180082168`
- `0x180082324`
- `0x180083f60`
- `0x180083f94`
- `0x18008446c`
- `0x180084824`
- `0x1800848d4`
- `0x180084cc0`
- `0x180084d38`
- `0x180085110`
- `0x18009d820`
- `0x18009dd40`

## import_xrefs

- `ntoskrnl!ZwEnumerateKey` at `0x180082404`
- `ntoskrnl!ZwEnumerateKey` at `0x180082404`
- `ntoskrnl!wcscpy_s` at `0x18008267a`
- `ntoskrnl!wcscpy_s` at `0x1800826a0`
- `ntoskrnl!wcscpy_s` at `0x1800826c7`
- `ntoskrnl!wcscpy_s` at `0x1800826eb`
- `ntoskrnl!wcscpy_s` at `0x18008267a`
- `ntoskrnl!wcscpy_s` at `0x1800826a0`
- `ntoskrnl!wcscpy_s` at `0x1800826c7`
- `ntoskrnl!wcscpy_s` at `0x1800826eb`

## string_xrefs

- `0x180082381`: `\Registry\MACHINE\System\CurrentControlSet\Control\Cryptography\Providers\Microsoft SSL Protocol Provider\CipherSuite`
- `0x18008248c`: `\Registry\MACHINE\System\CurrentControlSet\Control\Cryptography\Providers\Microsoft SSL Protocol Provider\CipherSuite`

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
0x180082324  push    rbp
0x180082326  push    rbx
0x180082327  push    rsi
0x180082328  push    rdi
0x180082329  push    r12
0x18008232b  push    r13
0x18008232d  push    r14
0x18008232f  push    r15
0x180082331  lea     rbp, [rsp-1A8h]
0x180082339  sub     rsp, 2A8h
0x180082340  mov     rax, cs:__security_cookie
0x180082347  xor     rax, rsp
0x18008234a  mov     [rbp+1E0h+var_50], rax
0x180082351  xor     r12d, r12d
0x180082354  mov     [rsp+2E0h+KeyHandle], r12
0x180082359  mov     [rsp+2E0h+var_2A8], r12
0x18008235e  mov     [rsp+2E0h+var_2B0], r12d
0x180082363  mov     [rsp+2E0h+var_2AC], r12d
0x180082368  call    FreeExternalCipherSuites
0x18008236d  cmp     cs:g_dwCipherSuiteInfoTotalCount, 3Ah ; ':'
0x180082374  jnb     loc_1800827E3
0x18008237a  lea     r8, [rsp+2E0h+KeyHandle]; KeyHandle
0x18008237f  xor     edx, edx; PCWSTR
0x180082381  lea     rcx, aRegistryMachin_13; "\\Registry\\MACHINE\\System\\CurrentCon"...
0x180082388  call    TlsOpenRegKey
0x18008238d  test    eax, eax
0x18008238f  js      loc_1800827E3
0x180082395  mov     ecx, 420h
0x18008239a  call    MSCryptAlloc
0x18008239f  mov     rdi, rax
0x1800823a2  test    rax, rax
0x1800823a5  jz      loc_1800827E3
0x1800823ab  mov     r13d, r12d
0x1800823ae  cmp     cs:g_dwCipherSuiteInfoTotalCount, 3Ah ; ':'
0x1800823b5  jnb     loc_1800827D1
0x1800823bb  xor     edx, edx; Val
0x1800823bd  mov     r8d, 420h; Size
0x1800823c3  mov     rcx, rdi; void *
0x1800823c6  call    memset
0x1800823cb  xor     edx, edx; Val
0x1800823cd  lea     rcx, [rsp+2E0h+KeyInformation]; void *
0x1800823d2  mov     r8d, 218h; Size
0x1800823d8  call    memset
0x1800823dd  mov     rcx, [rsp+2E0h+KeyHandle]; KeyHandle
0x1800823e2  lea     rax, [rsp+2E0h+var_2A0]
0x1800823e7  mov     [rsp+2E0h+ResultLength], rax; ResultLength
0x1800823ec  lea     r9, [rsp+2E0h+KeyInformation]; KeyInformation
0x1800823f1  xor     r8d, r8d; KeyInformationClass
0x1800823f4  mov     [rsp+2E0h+Length], 218h; Length
0x1800823fc  mov     edx, r13d; Index
0x1800823ff  mov     [rsp+2E0h+var_2A0], r12d
0x180082404  call    cs:__imp_ZwEnumerateKey
0x18008240b  nop     dword ptr [rax+rax+00h]
0x180082410  test    eax, eax
0x180082412  js      loc_1800827D1
0x180082418  lea     rcx, [rbp+1E0h+var_260]
0x18008241c  or      rax, 0FFFFFFFFFFFFFFFFh
0x180082420  inc     rax
0x180082423  cmp     [rcx+rax*2], r12w
0x180082428  jnz     short loc_180082420
0x18008242a  lea     rsi, [rdi+0Ch]
0x18008242e  cmp     rax, 7FFFFFFEh
0x180082434  jbe     short loc_18008243F
0x180082436  mov     [rsi], r12w
0x18008243a  jmp     loc_1800827B9
0x18008243f  lea     rcx, [rbp+1E0h+var_260]
0x180082443  mov     edx, 40h ; '@'
0x180082448  mov     r8, rsi
0x18008244b  test    rax, rax
0x18008244e  jz      short loc_18008246F
0x180082450  movzx   r9d, word ptr [rcx]
0x180082454  test    r9w, r9w
0x180082458  jz      short loc_18008246F
0x18008245a  mov     [r8], r9w
0x18008245e  add     rcx, 2
0x180082462  add     r8, 2
0x180082466  dec     rax
0x180082469  sub     rdx, 1
0x18008246d  jnz     short loc_18008244B
0x18008246f  test    rdx, rdx
0x180082472  lea     rcx, [r8-2]
0x180082476  cmovnz  rcx, r8
0x18008247a  mov     [rcx], r12w
0x18008247e  jz      loc_1800827B9
0x180082484  lea     r8, [rsp+2E0h+var_2A8]; KeyHandle
0x180082489  mov     rdx, rsi; PCWSTR
0x18008248c  lea     rcx, aRegistryMachin_13; "\\Registry\\MACHINE\\System\\CurrentCon"...
0x180082493  call    TlsOpenRegKey
0x180082498  test    eax, eax
0x18008249a  js      loc_1800827B9
0x1800824a0  mov     rcx, [rsp+2E0h+var_2A8]; KeyHandle
0x1800824a5  mov     rdx, rdi
0x1800824a8  call    GetCipherSuiteDetailsFromRegistry
0x1800824ad  lea     rcx, [rsp+2E0h+var_2A8]
0x1800824b2  test    eax, eax
0x1800824b4  jns     short loc_1800824C0
0x1800824b6  call    TlsCloseRegKey
0x1800824bb  jmp     loc_1800827B9
0x1800824c0  call    TlsCloseRegKey
0x1800824c5  cmp     dword ptr [rdi], 1
0x1800824c8  jnz     loc_1800827B9
0x1800824ce  lea     rbx, [rdi+8Ch]
0x1800824d5  mov     rcx, rbx; Str1
0x1800824d8  call    I_GetHashInfoFromAlgorithmName
0x1800824dd  lea     rcx, [rdi+29Ch]; Str1
0x1800824e4  mov     [rsp+2E0h+var_290], rax
0x1800824e9  call    I_GetSignatureInfoFromAlgorithmName
0x1800824ee  lea     rcx, [rdi+214h]; Str1
0x1800824f5  mov     [rsp+2E0h+var_288], rax
0x1800824fa  call    I_GetKeyExchangeInfoFromAlgorithmName
0x1800824ff  lea     r15, [rdi+194h]
0x180082506  mov     [rsp+2E0h+var_278], rax
0x18008250b  lea     r14, [rdi+10Ch]
0x180082512  mov     rdx, r15; wchar_t *
0x180082515  mov     rcx, r14; Str1
0x180082518  mov     r12, rax
0x18008251b  call    I_GetCipherInfoFromAlgorithmNameAndMode
0x180082520  xor     ecx, ecx
0x180082522  mov     [rsp+2E0h+var_280], rax
0x180082527  cmp     [rsp+2E0h+var_290], rcx
0x18008252c  jz      loc_1800827B6
0x180082532  cmp     [rsp+2E0h+var_288], rcx
0x180082537  jz      loc_1800827B6
0x18008253d  test    r12, r12
0x180082540  jz      loc_1800827B6
0x180082546  xor     r12d, r12d
0x180082549  test    rax, rax
0x18008254c  jz      loc_1800827B9
0x180082552  lea     rdx, [rsp+2E0h+var_2AC]
0x180082557  mov     rcx, rbx; Str1
0x18008255a  call    I_GetHashIndex
0x18008255f  test    eax, eax
0x180082561  js      loc_1800827B9
0x180082567  lea     r8, [rsp+2E0h+var_2B0]
0x18008256c  mov     rdx, r15; wchar_t *
0x18008256f  mov     rcx, r14; Str1
0x180082572  call    I_GetCipherIndexFromAlgorithmNameAndMode
0x180082577  test    eax, eax
0x180082579  js      loc_1800827B9
0x18008257f  mov     ecx, 90h
0x180082584  call    MSCryptAlloc
0x180082589  mov     rbx, rax
0x18008258c  test    rax, rax
0x18008258f  jz      loc_1800827B9
0x180082595  xor     edx, edx; Val
0x180082597  mov     r8d, 90h; Size
0x18008259d  mov     rcx, rax; void *
0x1800825a0  call    memset
0x1800825a5  or      r14, 0FFFFFFFFFFFFFFFFh
0x1800825a9  mov     rcx, r14
0x1800825ac  inc     rcx
0x1800825af  cmp     [rsi+rcx*2], r12w
0x1800825b4  jnz     short loc_1800825AC
0x1800825b6  lea     rcx, ds:2[rcx*2]
0x1800825be  call    MSCryptAlloc
0x1800825c3  mov     [rbx+8], rax
0x1800825c7  mov     rcx, r14
0x1800825ca  inc     rcx
0x1800825cd  cmp     [r15+rcx*2], r12w
0x1800825d2  jnz     short loc_1800825CA
0x1800825d4  lea     rcx, ds:2[rcx*2]
0x1800825dc  call    MSCryptAlloc
0x1800825e1  mov     [rbx+30h], rax
0x1800825e5  lea     r14, [rdi+39Ch]
0x1800825ec  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800825f0  inc     rcx
0x1800825f3  cmp     [r14+rcx*2], r12w
0x1800825f8  jnz     short loc_1800825F0
0x1800825fa  lea     rcx, ds:2[rcx*2]
0x180082602  call    MSCryptAlloc
0x180082607  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18008260b  mov     [rbx+88h], rax
0x180082612  xor     eax, eax
0x180082614  lea     r12, [rdi+31Ch]
0x18008261b  inc     rcx
0x18008261e  cmp     [r12+rcx*2], ax
0x180082623  jnz     short loc_18008261B
0x180082625  lea     rcx, ds:2[rcx*2]
0x18008262d  call    MSCryptAlloc
0x180082632  mov     rcx, [rbx+8]; Dst
0x180082636  xor     r8d, r8d
0x180082639  mov     [rbx+68h], rax
0x18008263d  test    rcx, rcx
0x180082640  jz      loc_1800827C1
0x180082646  cmp     [rbx+30h], r8
0x18008264a  jz      loc_1800827C1
0x180082650  cmp     [rbx+88h], r8
0x180082657  jz      loc_1800827C1
0x18008265d  test    rax, rax
0x180082660  jz      loc_1800827C1
0x180082666  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18008266a  inc     rdx
0x18008266d  cmp     [rsi+rdx*2], r8w
0x180082672  jnz     short loc_18008266A
0x180082674  inc     rdx; SizeInWords
0x180082677  mov     r8, rsi; Src
0x18008267a  call    cs:__imp_wcscpy_s
0x180082681  nop     dword ptr [rax+rax+00h]
0x180082686  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18008268a  xor     esi, esi
0x18008268c  inc     rdx
0x18008268f  cmp     [r15+rdx*2], si
0x180082694  jnz     short loc_18008268C
0x180082696  mov     rcx, [rbx+30h]; Dst
0x18008269a  inc     rdx; SizeInWords
0x18008269d  mov     r8, r15; Src
0x1800826a0  call    cs:__imp_wcscpy_s
0x1800826a7  nop     dword ptr [rax+rax+00h]
0x1800826ac  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800826b0  inc     rdx
0x1800826b3  cmp     [r14+rdx*2], si
0x1800826b8  jnz     short loc_1800826B0
0x1800826ba  mov     rcx, [rbx+88h]; Dst
0x1800826c1  inc     rdx; SizeInWords
0x1800826c4  mov     r8, r14; Src
0x1800826c7  call    cs:__imp_wcscpy_s
0x1800826ce  nop     dword ptr [rax+rax+00h]
0x1800826d3  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800826d7  inc     rdx
0x1800826da  cmp     [r12+rdx*2], si
0x1800826df  jnz     short loc_1800826D7
0x1800826e1  mov     rcx, [rbx+68h]; Dst
0x1800826e5  inc     rdx; SizeInWords
0x1800826e8  mov     r8, r12; Src
0x1800826eb  call    cs:__imp_wcscpy_s
0x1800826f2  nop     dword ptr [rax+rax+00h]
0x1800826f7  mov     eax, [rdi+4]
0x1800826fa  lea     rdx, g_pCipherSuiteInfo
0x180082701  mov     rcx, [rsp+2E0h+var_280]
0x180082706  xor     r12d, r12d
0x180082709  mov     [rbx], eax
0x18008270b  mov     eax, [rdi+8]
0x18008270e  mov     [rbx+4], eax
0x180082711  mov     rax, [rcx]
0x180082714  mov     [rbx+10h], rax
0x180082718  mov     eax, [rcx+10h]
0x18008271b  mov     [rbx+18h], eax
0x18008271e  mov     eax, [rdi+18Ch]
0x180082724  mov     [rbx+1Ch], eax
0x180082727  mov     eax, [rdi+190h]
0x18008272d  mov     [rbx+20h], eax
0x180082730  mov     eax, [rcx+8]
0x180082733  mov     rcx, [rsp+2E0h+var_290]
0x180082738  mov     [rbx+24h], eax
0x18008273b  mov     eax, [rsp+2E0h+var_2B0]
0x18008273f  mov     [rbx+28h], eax
0x180082742  mov     rax, [rcx]
0x180082745  mov     [rbx+38h], rax
0x180082749  mov     eax, [rcx+10h]
0x18008274c  mov     [rbx+40h], eax
0x18008274f  mov     eax, [rcx+8]
0x180082752  mov     rcx, [rsp+2E0h+var_278]
0x180082757  mov     [rbx+44h], eax
0x18008275a  mov     eax, [rsp+2E0h+var_2AC]
0x18008275e  mov     [rbx+48h], eax
0x180082761  mov     rax, [rcx]
0x180082764  mov     [rbx+50h], rax
0x180082768  mov     eax, [rcx+8]
0x18008276b  mov     [rbx+58h], eax
0x18008276e  mov     eax, [rdi+294h]
0x180082774  mov     [rbx+5Ch], eax
0x180082777  mov     eax, [rdi+298h]
0x18008277d  mov     [rbx+60h], eax
0x180082780  mov     eax, [rdi+41Ch]
0x180082786  mov     [rbx+70h], eax
0x180082789  mov     eax, [rcx+10h]
0x18008278c  mov     ecx, cs:g_dwCipherSuiteInfoTotalCount
0x180082792  mov     [rbx+64h], eax
0x180082795  mov     rax, [rsp+2E0h+var_288]
0x18008279a  mov     [rdx+rcx*8], rbx
0x18008279e  inc     ecx
0x1800827a0  mov     cs:g_dwCipherSuiteInfoTotalCount, ecx
0x1800827a6  mov     rax, [rax]
0x1800827a9  mov     [rbx+78h], rax
0x1800827ad  mov     [rbx+80h], r12d
0x1800827b4  jmp     short loc_1800827B9
0x1800827b6  xor     r12d, r12d
0x1800827b9  inc     r13d
0x1800827bc  jmp     loc_1800823AE
0x1800827c1  mov     rcx, rbx
0x1800827c4  call    FreeExternalCipherSuiteInfoFields
0x1800827c9  mov     rcx, rbx; P
0x1800827cc  call    MSCryptFree
0x1800827d1  lea     rcx, [rsp+2E0h+KeyHandle]
0x1800827d6  call    TlsCloseRegKey
0x1800827db  mov     rcx, rdi; P
0x1800827de  call    MSCryptFree
0x1800827e3  mov     rcx, [rbp+1E0h+var_50]
0x1800827ea  xor     rcx, rsp; StackCookie
0x1800827ed  call    __security_check_cookie
0x1800827f2  add     rsp, 2A8h
0x1800827f9  pop     r15
0x1800827fb  pop     r14
0x1800827fd  pop     r13
0x1800827ff  pop     r12
0x180082801  pop     rdi
0x180082802  pop     rsi
0x180082803  pop     rbx
0x180082804  pop     rbp
0x180082805  retn
  ... truncated ...
```
