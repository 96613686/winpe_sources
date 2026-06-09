# GetExternalCipherSuites

- ea: `0x180083314`
- end: `0x1800837f7`
- name: `GetExternalCipherSuites`
- size: `1251`
- prototype: ``
- caller_count: `2`
- callee_count: `16`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180046720`
- `0x180082418`

## callees

- `0x180003f70`
- `0x180006470`
- `0x180083074`
- `0x1800830ec`
- `0x180083158`
- `0x180083314`
- `0x180084f50`
- `0x180084f84`
- `0x18008545c`
- `0x18008583c`
- `0x1800858ec`
- `0x180085cd8`
- `0x180085d50`
- `0x180086128`
- `0x18009f650`
- `0x18009fa80`

## import_xrefs

- `ntoskrnl!ZwEnumerateKey` at `0x1800833f4`
- `ntoskrnl!ZwEnumerateKey` at `0x1800833f4`
- `ntoskrnl!wcscpy_s` at `0x18008366a`
- `ntoskrnl!wcscpy_s` at `0x180083690`
- `ntoskrnl!wcscpy_s` at `0x1800836b7`
- `ntoskrnl!wcscpy_s` at `0x1800836db`
- `ntoskrnl!wcscpy_s` at `0x18008366a`
- `ntoskrnl!wcscpy_s` at `0x180083690`
- `ntoskrnl!wcscpy_s` at `0x1800836b7`
- `ntoskrnl!wcscpy_s` at `0x1800836db`

## string_xrefs

- `0x180083371`: `\Registry\MACHINE\System\CurrentControlSet\Control\Cryptography\Providers\Microsoft SSL Protocol Provider\CipherSuite`
- `0x18008347c`: `\Registry\MACHINE\System\CurrentControlSet\Control\Cryptography\Providers\Microsoft SSL Protocol Provider\CipherSuite`

## pseudocode

```c
__int64 GetExternalCipherSuites()
{
  __int64 result; // rax
  __int64 v1; // r9
  __int64 v2; // rdx
  __int64 v3; // r8
  __int64 v4; // r9
  _DWORD *v5; // rdi
  ULONG i; // r13d
  __int64 v7; // r9
  unsigned __int64 v8; // rax
  _WORD *v9; // rsi
  unsigned __int16 *v10; // rcx
  __int64 v11; // rdx
  _WORD *v12; // r8
  _WORD *v13; // rcx
  _DWORD *v14; // r15
  __int64 v15; // r12
  __int64 CipherInfoFromAlgorithmNameAndMode; // rax
  __int64 v17; // rdx
  __int64 v18; // r8
  __int64 v19; // r9
  _DWORD *v20; // rax
  _DWORD *v21; // rbx
  __int64 v22; // rdx
  __int64 v23; // r8
  __int64 v24; // r9
  __int64 v25; // rcx
  __int64 v26; // rdx
  __int64 v27; // r8
  __int64 v28; // r9
  __int64 v29; // rcx
  __int64 v30; // rdx
  __int64 v31; // r8
  __int64 v32; // r9
  _DWORD *v33; // r14
  __int64 v34; // rcx
  __int64 v35; // rax
  __int64 v36; // rdx
  __int64 v37; // r8
  __int64 v38; // r9
  __int64 v39; // rcx
  _DWORD *v40; // r12
  __int64 v41; // rax
  __int64 v42; // rdx
  wchar_t *v43; // rcx
  __int64 v44; // rdx
  __int64 v45; // rdx
  __int64 v46; // rdx
  __int64 v47; // rdx
  __int64 v48; // rcx
  int v49; // eax
  __int64 v50; // rcx
  int v51; // eax
  __int64 v52; // rcx
  int v53; // eax
  __int64 v54; // rcx
  _QWORD *v55; // rax
  HANDLE v56; // [rsp+38h] [rbp-C8h] BYREF
  ULONG ResultLength; // [rsp+40h] [rbp-C0h] BYREF
  HANDLE KeyHandle; // [rsp+48h] [rbp-B8h] BYREF
  __int64 HashInfoFromAlgorithmName; // [rsp+50h] [rbp-B0h]
  __int64 SignatureInfoFromAlgorithmName; // [rsp+58h] [rbp-A8h]
  __int64 v61; // [rsp+60h] [rbp-A0h]
  __int64 KeyExchangeInfoFromAlgorithmName; // [rsp+68h] [rbp-98h]
  _WORD KeyInformation[272]; // [rsp+70h] [rbp-90h] BYREF

  KeyHandle = 0;
  v56 = 0;
  result = FreeExternalCipherSuites();
  if ( (unsigned int)g_dwCipherSuiteInfoTotalCount < 0x3A )
  {
    result = TlsOpenRegKey(
               L"\\Registry\\MACHINE\\System\\CurrentControlSet\\Control\\Cryptography\\Providers\\Microsoft SSL Protocol "
                "Provider\\CipherSuite",
               0,
               &KeyHandle,
               v1);
    if ( (int)result >= 0 )
    {
      result = MSCryptAlloc(1056, v2, v3, v4);
      v5 = (_DWORD *)result;
      if ( result )
      {
        for ( i = 0; (unsigned int)g_dwCipherSuiteInfoTotalCount < 0x3A; ++i )
        {
          memset(v5, 0, 0x420u);
          memset(KeyInformation, 0, 0x218u);
          ResultLength = 0;
          if ( ZwEnumerateKey(KeyHandle, i, KeyBasicInformation, KeyInformation, 0x218u, &ResultLength) < 0 )
            break;
          v8 = -1;
          do
            ++v8;
          while ( KeyInformation[v8 + 8] );
          v9 = v5 + 3;
          if ( v8 <= 0x7FFFFFFE )
          {
            v10 = &KeyInformation[8];
            v11 = 64;
            v12 = v5 + 3;
            do
            {
              if ( !v8 )
                break;
              v7 = *v10;
              if ( !(_WORD)v7 )
                break;
              *v12 = v7;
              ++v10;
              ++v12;
              --v8;
              --v11;
            }
            while ( v11 );
            v13 = v12 - 1;
            if ( v11 )
              v13 = v12;
            *v13 = 0;
            if ( v11
              && (int)TlsOpenRegKey(
                        L"\\Registry\\MACHINE\\System\\CurrentControlSet\\Control\\Cryptography\\Providers\\Microsoft SSL "
                         "Protocol Provider\\CipherSuite",
                        (PCWSTR)v5 + 6,
                        &v56,
                        v7) >= 0 )
            {
              if ( (int)GetCipherSuiteDetailsFromRegistry(v56) >= 0 )
              {
                TlsCloseRegKey(&v56);
                if ( *v5 == 1 )
                {
                  HashInfoFromAlgorithmName = I_GetHashInfoFromAlgorithmName((wchar_t *)v5 + 70);
                  SignatureInfoFromAlgorithmName = I_GetSignatureInfoFromAlgorithmName((wchar_t *)v5 + 334);
                  v14 = v5 + 101;
                  KeyExchangeInfoFromAlgorithmName = I_GetKeyExchangeInfoFromAlgorithmName((wchar_t *)v5 + 266);
                  v15 = KeyExchangeInfoFromAlgorithmName;
                  CipherInfoFromAlgorithmNameAndMode = I_GetCipherInfoFromAlgorithmNameAndMode(
                                                         (wchar_t *)v5 + 134,
                                                         (wchar_t *)v5 + 202);
                  v61 = CipherInfoFromAlgorithmNameAndMode;
                  if ( HashInfoFromAlgorithmName )
                  {
                    if ( SignatureInfoFromAlgorithmName )
                    {
                      if ( v15 )
                      {
                        if ( CipherInfoFromAlgorithmNameAndMode )
                        {
                          if ( (int)I_GetHashIndex((wchar_t *)v5 + 70) >= 0
                            && (int)I_GetCipherIndexFromAlgorithmNameAndMode((wchar_t *)v5 + 134, (wchar_t *)v5 + 202) >= 0 )
                          {
                            v20 = (_DWORD *)MSCryptAlloc(144, v17, v18, v19);
                            v21 = v20;
                            if ( v20 )
                            {
                              memset(v20, 0, 0x90u);
                              v25 = -1;
                              do
                                ++v25;
                              while ( v9[v25] );
                              *((_QWORD *)v21 + 1) = MSCryptAlloc(2 * v25 + 2, v22, v23, v24);
                              v29 = -1;
                              do
                                ++v29;
                              while ( *((_WORD *)v14 + v29) );
                              *((_QWORD *)v21 + 6) = MSCryptAlloc(2 * v29 + 2, v26, v27, v28);
                              v33 = v5 + 231;
                              v34 = -1;
                              do
                                ++v34;
                              while ( *((_WORD *)v33 + v34) );
                              v35 = MSCryptAlloc(2 * v34 + 2, v30, v31, v32);
                              v39 = -1;
                              *((_QWORD *)v21 + 17) = v35;
                              v40 = v5 + 199;
                              do
                                ++v39;
                              while ( *((_WORD *)v40 + v39) );
                              v41 = MSCryptAlloc(2 * v39 + 2, v36, v37, v38);
                              v43 = (wchar_t *)*((_QWORD *)v21 + 1);
                              *((_QWORD *)v21 + 13) = v41;
                              if ( !v43 || !*((_QWORD *)v21 + 6) || !*((_QWORD *)v21 + 17) || !v41 )
                              {
                                FreeExternalCipherSuiteInfoFields(v21, v42, 0);
                                MSCryptFree(v21);
                                break;
                              }
                              v44 = -1;
                              do
                                ++v44;
                              while ( v9[v44] );
                              wcscpy_s(v43, v44 + 1, (const wchar_t *)v5 + 6);
                              v45 = -1;
                              do
                                ++v45;
                              while ( *((_WORD *)v14 + v45) );
                              wcscpy_s(*((wchar_t **)v21 + 6), v45 + 1, (const wchar_t *)v5 + 202);
                              v46 = -1;
                              do
                                ++v46;
                              while ( *((_WORD *)v33 + v46) );
                              wcscpy_s(*((wchar_t **)v21 + 17), v46 + 1, (const wchar_t *)v5 + 462);
                              v47 = -1;
                              do
                                ++v47;
                              while ( *((_WORD *)v40 + v47) );
                              wcscpy_s(*((wchar_t **)v21 + 13), v47 + 1, (const wchar_t *)v5 + 398);
                              v48 = v61;
                              *v21 = v5[1];
                              v21[1] = v5[2];
                              *((_QWORD *)v21 + 2) = *(_QWORD *)v48;
                              v21[6] = *(_DWORD *)(v48 + 16);
                              v21[7] = v5[99];
                              v21[8] = v5[100];
                              v49 = *(_DWORD *)(v48 + 8);
                              v50 = HashInfoFromAlgorithmName;
                              v21[9] = v49;
                              v21[10] = 0;
                              *((_QWORD *)v21 + 7) = *(_QWORD *)v50;
                              v21[16] = *(_DWORD *)(v50 + 16);
                              v51 = *(_DWORD *)(v50 + 8);
                              v52 = KeyExchangeInfoFromAlgorithmName;
                              v21[17] = v51;
                              v21[18] = 0;
                              *((_QWORD *)v21 + 10) = *(_QWORD *)v52;
                              v21[22] = *(_DWORD *)(v52 + 8);
                              v21[23] = v5[165];
                              v21[24] = v5[166];
                              v21[28] = v5[263];
                              v53 = *(_DWORD *)(v52 + 16);
                              v54 = (unsigned int)g_dwCipherSuiteInfoTotalCount;
                              v21[25] = v53;
                              v55 = (_QWORD *)SignatureInfoFromAlgorithmName;
                              g_pCipherSuiteInfo[v54] = (__int64)v21;
                              g_dwCipherSuiteInfoTotalCount = v54 + 1;
                              *((_QWORD *)v21 + 15) = *v55;
                              v21[32] = 0;
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
                TlsCloseRegKey(&v56);
              }
            }
          }
          else
          {
            *v9 = 0;
          }
        }
        TlsCloseRegKey(&KeyHandle);
        return MSCryptFree(v5);
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x180083314  push    rbp
0x180083316  push    rbx
0x180083317  push    rsi
0x180083318  push    rdi
0x180083319  push    r12
0x18008331b  push    r13
0x18008331d  push    r14
0x18008331f  push    r15
0x180083321  lea     rbp, [rsp-1A8h]
0x180083329  sub     rsp, 2A8h
0x180083330  mov     rax, cs:__security_cookie
0x180083337  xor     rax, rsp
0x18008333a  mov     [rbp+1E0h+var_50], rax
0x180083341  xor     r12d, r12d
0x180083344  mov     [rsp+2E0h+KeyHandle], r12
0x180083349  mov     [rsp+2E0h+var_2A8], r12
0x18008334e  mov     [rsp+2E0h+var_2B0], r12d
0x180083353  mov     [rsp+2E0h+var_2AC], r12d
0x180083358  call    FreeExternalCipherSuites
0x18008335d  cmp     cs:g_dwCipherSuiteInfoTotalCount, 3Ah ; ':'
0x180083364  jnb     loc_1800837D3
0x18008336a  lea     r8, [rsp+2E0h+KeyHandle]; KeyHandle
0x18008336f  xor     edx, edx; PCWSTR
0x180083371  lea     rcx, aRegistryMachin_13; "\\Registry\\MACHINE\\System\\CurrentCon"...
0x180083378  call    TlsOpenRegKey
0x18008337d  test    eax, eax
0x18008337f  js      loc_1800837D3
0x180083385  mov     ecx, 420h
0x18008338a  call    MSCryptAlloc
0x18008338f  mov     rdi, rax
0x180083392  test    rax, rax
0x180083395  jz      loc_1800837D3
0x18008339b  mov     r13d, r12d
0x18008339e  cmp     cs:g_dwCipherSuiteInfoTotalCount, 3Ah ; ':'
0x1800833a5  jnb     loc_1800837C1
0x1800833ab  xor     edx, edx; Val
0x1800833ad  mov     r8d, 420h; Size
0x1800833b3  mov     rcx, rdi; void *
0x1800833b6  call    memset
0x1800833bb  xor     edx, edx; Val
0x1800833bd  lea     rcx, [rsp+2E0h+KeyInformation]; void *
0x1800833c2  mov     r8d, 218h; Size
0x1800833c8  call    memset
0x1800833cd  mov     rcx, [rsp+2E0h+KeyHandle]; KeyHandle
0x1800833d2  lea     rax, [rsp+2E0h+var_2A0]
0x1800833d7  mov     [rsp+2E0h+ResultLength], rax; ResultLength
0x1800833dc  lea     r9, [rsp+2E0h+KeyInformation]; KeyInformation
0x1800833e1  xor     r8d, r8d; KeyInformationClass
0x1800833e4  mov     [rsp+2E0h+Length], 218h; Length
0x1800833ec  mov     edx, r13d; Index
0x1800833ef  mov     [rsp+2E0h+var_2A0], r12d
0x1800833f4  call    cs:__imp_ZwEnumerateKey
0x1800833fb  nop     dword ptr [rax+rax+00h]
0x180083400  test    eax, eax
0x180083402  js      loc_1800837C1
0x180083408  lea     rcx, [rbp+1E0h+var_260]
0x18008340c  or      rax, 0FFFFFFFFFFFFFFFFh
0x180083410  inc     rax
0x180083413  cmp     [rcx+rax*2], r12w
0x180083418  jnz     short loc_180083410
0x18008341a  lea     rsi, [rdi+0Ch]
0x18008341e  cmp     rax, 7FFFFFFEh
0x180083424  jbe     short loc_18008342F
0x180083426  mov     [rsi], r12w
0x18008342a  jmp     loc_1800837A9
0x18008342f  lea     rcx, [rbp+1E0h+var_260]
0x180083433  mov     edx, 40h ; '@'
0x180083438  mov     r8, rsi
0x18008343b  test    rax, rax
0x18008343e  jz      short loc_18008345F
0x180083440  movzx   r9d, word ptr [rcx]
0x180083444  test    r9w, r9w
0x180083448  jz      short loc_18008345F
0x18008344a  mov     [r8], r9w
0x18008344e  add     rcx, 2
0x180083452  add     r8, 2
0x180083456  dec     rax
0x180083459  sub     rdx, 1
0x18008345d  jnz     short loc_18008343B
0x18008345f  test    rdx, rdx
0x180083462  lea     rcx, [r8-2]
0x180083466  cmovnz  rcx, r8
0x18008346a  mov     [rcx], r12w
0x18008346e  jz      loc_1800837A9
0x180083474  lea     r8, [rsp+2E0h+var_2A8]; KeyHandle
0x180083479  mov     rdx, rsi; PCWSTR
0x18008347c  lea     rcx, aRegistryMachin_13; "\\Registry\\MACHINE\\System\\CurrentCon"...
0x180083483  call    TlsOpenRegKey
0x180083488  test    eax, eax
0x18008348a  js      loc_1800837A9
0x180083490  mov     rcx, [rsp+2E0h+var_2A8]; KeyHandle
0x180083495  mov     rdx, rdi
0x180083498  call    GetCipherSuiteDetailsFromRegistry
0x18008349d  lea     rcx, [rsp+2E0h+var_2A8]
0x1800834a2  test    eax, eax
0x1800834a4  jns     short loc_1800834B0
0x1800834a6  call    TlsCloseRegKey
0x1800834ab  jmp     loc_1800837A9
0x1800834b0  call    TlsCloseRegKey
0x1800834b5  cmp     dword ptr [rdi], 1
0x1800834b8  jnz     loc_1800837A9
0x1800834be  lea     rbx, [rdi+8Ch]
0x1800834c5  mov     rcx, rbx; Str1
0x1800834c8  call    I_GetHashInfoFromAlgorithmName
0x1800834cd  lea     rcx, [rdi+29Ch]; Str1
0x1800834d4  mov     [rsp+2E0h+var_290], rax
0x1800834d9  call    I_GetSignatureInfoFromAlgorithmName
0x1800834de  lea     rcx, [rdi+214h]; Str1
0x1800834e5  mov     [rsp+2E0h+var_288], rax
0x1800834ea  call    I_GetKeyExchangeInfoFromAlgorithmName
0x1800834ef  lea     r15, [rdi+194h]
0x1800834f6  mov     [rsp+2E0h+var_278], rax
0x1800834fb  lea     r14, [rdi+10Ch]
0x180083502  mov     rdx, r15; wchar_t *
0x180083505  mov     rcx, r14; Str1
0x180083508  mov     r12, rax
0x18008350b  call    I_GetCipherInfoFromAlgorithmNameAndMode
0x180083510  xor     ecx, ecx
0x180083512  mov     [rsp+2E0h+var_280], rax
0x180083517  cmp     [rsp+2E0h+var_290], rcx
0x18008351c  jz      loc_1800837A6
0x180083522  cmp     [rsp+2E0h+var_288], rcx
0x180083527  jz      loc_1800837A6
0x18008352d  test    r12, r12
0x180083530  jz      loc_1800837A6
0x180083536  xor     r12d, r12d
0x180083539  test    rax, rax
0x18008353c  jz      loc_1800837A9
0x180083542  lea     rdx, [rsp+2E0h+var_2AC]
0x180083547  mov     rcx, rbx; Str1
0x18008354a  call    I_GetHashIndex
0x18008354f  test    eax, eax
0x180083551  js      loc_1800837A9
0x180083557  lea     r8, [rsp+2E0h+var_2B0]
0x18008355c  mov     rdx, r15; wchar_t *
0x18008355f  mov     rcx, r14; Str1
0x180083562  call    I_GetCipherIndexFromAlgorithmNameAndMode
0x180083567  test    eax, eax
0x180083569  js      loc_1800837A9
0x18008356f  mov     ecx, 90h
0x180083574  call    MSCryptAlloc
0x180083579  mov     rbx, rax
0x18008357c  test    rax, rax
0x18008357f  jz      loc_1800837A9
0x180083585  xor     edx, edx; Val
0x180083587  mov     r8d, 90h; Size
0x18008358d  mov     rcx, rax; void *
0x180083590  call    memset
0x180083595  or      r14, 0FFFFFFFFFFFFFFFFh
0x180083599  mov     rcx, r14
0x18008359c  inc     rcx
0x18008359f  cmp     [rsi+rcx*2], r12w
0x1800835a4  jnz     short loc_18008359C
0x1800835a6  lea     rcx, ds:2[rcx*2]
0x1800835ae  call    MSCryptAlloc
0x1800835b3  mov     [rbx+8], rax
0x1800835b7  mov     rcx, r14
0x1800835ba  inc     rcx
0x1800835bd  cmp     [r15+rcx*2], r12w
0x1800835c2  jnz     short loc_1800835BA
0x1800835c4  lea     rcx, ds:2[rcx*2]
0x1800835cc  call    MSCryptAlloc
0x1800835d1  mov     [rbx+30h], rax
0x1800835d5  lea     r14, [rdi+39Ch]
0x1800835dc  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800835e0  inc     rcx
0x1800835e3  cmp     [r14+rcx*2], r12w
0x1800835e8  jnz     short loc_1800835E0
0x1800835ea  lea     rcx, ds:2[rcx*2]
0x1800835f2  call    MSCryptAlloc
0x1800835f7  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800835fb  mov     [rbx+88h], rax
0x180083602  xor     eax, eax
0x180083604  lea     r12, [rdi+31Ch]
0x18008360b  inc     rcx
0x18008360e  cmp     [r12+rcx*2], ax
0x180083613  jnz     short loc_18008360B
0x180083615  lea     rcx, ds:2[rcx*2]
0x18008361d  call    MSCryptAlloc
0x180083622  mov     rcx, [rbx+8]; Dst
0x180083626  xor     r8d, r8d
0x180083629  mov     [rbx+68h], rax
0x18008362d  test    rcx, rcx
0x180083630  jz      loc_1800837B1
0x180083636  cmp     [rbx+30h], r8
0x18008363a  jz      loc_1800837B1
0x180083640  cmp     [rbx+88h], r8
0x180083647  jz      loc_1800837B1
0x18008364d  test    rax, rax
0x180083650  jz      loc_1800837B1
0x180083656  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18008365a  inc     rdx
0x18008365d  cmp     [rsi+rdx*2], r8w
0x180083662  jnz     short loc_18008365A
0x180083664  inc     rdx; SizeInWords
0x180083667  mov     r8, rsi; Src
0x18008366a  call    cs:__imp_wcscpy_s
0x180083671  nop     dword ptr [rax+rax+00h]
0x180083676  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18008367a  xor     esi, esi
0x18008367c  inc     rdx
0x18008367f  cmp     [r15+rdx*2], si
0x180083684  jnz     short loc_18008367C
0x180083686  mov     rcx, [rbx+30h]; Dst
0x18008368a  inc     rdx; SizeInWords
0x18008368d  mov     r8, r15; Src
0x180083690  call    cs:__imp_wcscpy_s
0x180083697  nop     dword ptr [rax+rax+00h]
0x18008369c  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800836a0  inc     rdx
0x1800836a3  cmp     [r14+rdx*2], si
0x1800836a8  jnz     short loc_1800836A0
0x1800836aa  mov     rcx, [rbx+88h]; Dst
0x1800836b1  inc     rdx; SizeInWords
0x1800836b4  mov     r8, r14; Src
0x1800836b7  call    cs:__imp_wcscpy_s
0x1800836be  nop     dword ptr [rax+rax+00h]
0x1800836c3  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800836c7  inc     rdx
0x1800836ca  cmp     [r12+rdx*2], si
0x1800836cf  jnz     short loc_1800836C7
0x1800836d1  mov     rcx, [rbx+68h]; Dst
0x1800836d5  inc     rdx; SizeInWords
0x1800836d8  mov     r8, r12; Src
0x1800836db  call    cs:__imp_wcscpy_s
0x1800836e2  nop     dword ptr [rax+rax+00h]
0x1800836e7  mov     eax, [rdi+4]
0x1800836ea  lea     rdx, g_pCipherSuiteInfo
0x1800836f1  mov     rcx, [rsp+2E0h+var_280]
0x1800836f6  xor     r12d, r12d
0x1800836f9  mov     [rbx], eax
0x1800836fb  mov     eax, [rdi+8]
0x1800836fe  mov     [rbx+4], eax
0x180083701  mov     rax, [rcx]
0x180083704  mov     [rbx+10h], rax
0x180083708  mov     eax, [rcx+10h]
0x18008370b  mov     [rbx+18h], eax
0x18008370e  mov     eax, [rdi+18Ch]
0x180083714  mov     [rbx+1Ch], eax
0x180083717  mov     eax, [rdi+190h]
0x18008371d  mov     [rbx+20h], eax
0x180083720  mov     eax, [rcx+8]
0x180083723  mov     rcx, [rsp+2E0h+var_290]
0x180083728  mov     [rbx+24h], eax
0x18008372b  mov     eax, [rsp+2E0h+var_2B0]
0x18008372f  mov     [rbx+28h], eax
0x180083732  mov     rax, [rcx]
0x180083735  mov     [rbx+38h], rax
0x180083739  mov     eax, [rcx+10h]
0x18008373c  mov     [rbx+40h], eax
0x18008373f  mov     eax, [rcx+8]
0x180083742  mov     rcx, [rsp+2E0h+var_278]
0x180083747  mov     [rbx+44h], eax
0x18008374a  mov     eax, [rsp+2E0h+var_2AC]
0x18008374e  mov     [rbx+48h], eax
0x180083751  mov     rax, [rcx]
0x180083754  mov     [rbx+50h], rax
0x180083758  mov     eax, [rcx+8]
0x18008375b  mov     [rbx+58h], eax
0x18008375e  mov     eax, [rdi+294h]
0x180083764  mov     [rbx+5Ch], eax
0x180083767  mov     eax, [rdi+298h]
0x18008376d  mov     [rbx+60h], eax
0x180083770  mov     eax, [rdi+41Ch]
0x180083776  mov     [rbx+70h], eax
0x180083779  mov     eax, [rcx+10h]
0x18008377c  mov     ecx, cs:g_dwCipherSuiteInfoTotalCount
0x180083782  mov     [rbx+64h], eax
0x180083785  mov     rax, [rsp+2E0h+var_288]
0x18008378a  mov     [rdx+rcx*8], rbx
0x18008378e  inc     ecx
0x180083790  mov     cs:g_dwCipherSuiteInfoTotalCount, ecx
0x180083796  mov     rax, [rax]
0x180083799  mov     [rbx+78h], rax
0x18008379d  mov     [rbx+80h], r12d
0x1800837a4  jmp     short loc_1800837A9
0x1800837a6  xor     r12d, r12d
0x1800837a9  inc     r13d
0x1800837ac  jmp     loc_18008339E
0x1800837b1  mov     rcx, rbx
0x1800837b4  call    FreeExternalCipherSuiteInfoFields
0x1800837b9  mov     rcx, rbx; P
0x1800837bc  call    MSCryptFree
0x1800837c1  lea     rcx, [rsp+2E0h+KeyHandle]
0x1800837c6  call    TlsCloseRegKey
0x1800837cb  mov     rcx, rdi; P
0x1800837ce  call    MSCryptFree
0x1800837d3  mov     rcx, [rbp+1E0h+var_50]
0x1800837da  xor     rcx, rsp; StackCookie
0x1800837dd  call    __security_check_cookie
0x1800837e2  add     rsp, 2A8h
0x1800837e9  pop     r15
0x1800837eb  pop     r14
0x1800837ed  pop     r13
0x1800837ef  pop     r12
0x1800837f1  pop     rdi
0x1800837f2  pop     rsi
0x1800837f3  pop     rbx
0x1800837f4  pop     rbp
0x1800837f5  retn
  ... truncated ...
```
