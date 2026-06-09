# CredpDeriveKeysAndHashFromSecret(unsigned __int64,uchar * const,uchar * const,uchar * const,uchar *,ulong,unsigned __int64 *,unsigned __int64 *,unsigned __int64 *)

- ea: `0x1800c441c`
- end: `0x1800c49e2`
- name: `?CredpDeriveKeysAndHashFromSecret@@YAK_KQEAE11PEAEKPEA_K33@Z`
- size: `1478`
- prototype: `__int64 __fastcall(HCRYPTPROV hProv, BYTE *pbData, BYTE *, BYTE *, BYTE *pbDataa, DWORD dwDataLen, unsigned __int64 *, unsigned __int64 *, unsigned __int64 *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800c4064`
- `0x1800c49e8`

## callees

- `0x180011278`
- `0x1800c441c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c4495`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c4503`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c455a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c45be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c4620`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c4678`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c46c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c4733`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c478e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c47e8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c484c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c48b0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c4922`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c4495`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c4503`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c455a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c45be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c4620`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c4678`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c46c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c4733`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c478e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c47e8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c484c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c48b0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c4922`
- `CRYPTSP!CryptSetKeyParam` at `0x1800c4610`
- `CRYPTSP!CryptSetKeyParam` at `0x1800c4668`
- `CRYPTSP!CryptSetKeyParam` at `0x1800c4610`
- `CRYPTSP!CryptSetKeyParam` at `0x1800c4668`
- `CRYPTSP!CryptDeriveKey` at `0x1800c45ae`
- `CRYPTSP!CryptDeriveKey` at `0x1800c483c`
- `CRYPTSP!CryptDeriveKey` at `0x1800c45ae`
- `CRYPTSP!CryptDeriveKey` at `0x1800c483c`
- `CRYPTSP!CryptHashData` at `0x1800c44f3`
- `CRYPTSP!CryptHashData` at `0x1800c454a`
- `CRYPTSP!CryptHashData` at `0x1800c477e`
- `CRYPTSP!CryptHashData` at `0x1800c47d8`
- `CRYPTSP!CryptHashData` at `0x1800c44f3`
- `CRYPTSP!CryptHashData` at `0x1800c454a`
- `CRYPTSP!CryptHashData` at `0x1800c477e`
- `CRYPTSP!CryptHashData` at `0x1800c47d8`
- `CRYPTSP!CryptCreateHash` at `0x1800c4485`
- `CRYPTSP!CryptCreateHash` at `0x1800c4723`
- `CRYPTSP!CryptCreateHash` at `0x1800c48a0`
- `CRYPTSP!CryptCreateHash` at `0x1800c4485`
- `CRYPTSP!CryptCreateHash` at `0x1800c4723`
- `CRYPTSP!CryptCreateHash` at `0x1800c48a0`
- `CRYPTSP!CryptDestroyHash` at `0x1800c46b8`
- `CRYPTSP!CryptDestroyHash` at `0x1800c4982`
- `CRYPTSP!CryptDestroyHash` at `0x1800c499b`
- `CRYPTSP!CryptDestroyHash` at `0x1800c46b8`
- `CRYPTSP!CryptDestroyHash` at `0x1800c4982`
- `CRYPTSP!CryptDestroyHash` at `0x1800c499b`
- `CRYPTSP!CryptDestroyKey` at `0x1800c49b0`
- `CRYPTSP!CryptDestroyKey` at `0x1800c49c5`
- `CRYPTSP!CryptDestroyKey` at `0x1800c49b0`
- `CRYPTSP!CryptDestroyKey` at `0x1800c49c5`
- `CRYPTSP!CryptSetHashParam` at `0x1800c4912`
- `CRYPTSP!CryptSetHashParam` at `0x1800c4912`

## pseudocode

```c
__int64 __fastcall CredpDeriveKeysAndHashFromSecret(
        HCRYPTPROV hProv,
        BYTE *pbData,
        BYTE *a3,
        BYTE *a4,
        BYTE *pbDataa,
        DWORD dwDataLen,
        unsigned __int64 *a7,
        unsigned __int64 *a8,
        unsigned __int64 *a9)
{
  DWORD LastError; // ebx
  LsaHandleCache *v14; // rcx
  __int64 v15; // rdx
  BYTE v17[8]; // [rsp+30h] [rbp-50h] BYREF
  HCRYPTHASH hHash; // [rsp+38h] [rbp-48h] BYREF
  HCRYPTKEY phKey; // [rsp+40h] [rbp-40h] BYREF
  HCRYPTHASH phHash; // [rsp+48h] [rbp-38h] BYREF
  HCRYPTKEY hKey; // [rsp+50h] [rbp-30h] BYREF
  BYTE v22[16]; // [rsp+58h] [rbp-28h] BYREF
  __int128 v23; // [rsp+68h] [rbp-18h]
  __int64 v24; // [rsp+78h] [rbp-8h]

  phKey = 0;
  v24 = 0;
  hKey = 0;
  phHash = 0;
  hHash = 0;
  *(_DWORD *)v17 = 0;
  *(_OWORD *)v22 = 0;
  v23 = 0;
  if ( CryptCreateHash(hProv, 0x8004u, 0, 0, &hHash) )
  {
    if ( CryptHashData(hHash, pbDataa, dwDataLen, 0) )
    {
      if ( CryptHashData(hHash, pbData, 0x10u, 0) )
      {
        if ( CryptDeriveKey(hProv, 0x6610u, hHash, 0, &phKey) )
        {
          *(_DWORD *)v17 = 1;
          if ( CryptSetKeyParam(phKey, 4u, v17, 0) )
          {
            if ( CryptSetKeyParam(phKey, 1u, a4, 0) )
            {
              if ( CryptDestroyHash(hHash) )
              {
                hHash = 0;
                if ( CryptCreateHash(hProv, 0x8004u, 0, 0, &hHash) )
                {
                  if ( CryptHashData(hHash, pbDataa, dwDataLen, 0) )
                  {
                    if ( CryptHashData(hHash, a3, 0x10u, 0) )
                    {
                      if ( CryptDeriveKey(hProv, 0x6602u, hHash, 0, &hKey) )
                      {
                        if ( CryptCreateHash(hProv, 0x8009u, hKey, 0, &phHash) )
                        {
                          *(_OWORD *)v22 = 0;
                          v24 = 0;
                          v23 = 0;
                          *(_DWORD *)v22 = 32772;
                          if ( CryptSetHashParam(phHash, 5u, v22, 0) )
                          {
                            LastError = 0;
                            *a7 = phKey;
                            *a8 = hKey;
                            *a9 = phHash;
                          }
                          else
                          {
                            LastError = GetLastError();
                            v14 = WPP_GLOBAL_Control;
                            if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control
                              && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
                            {
                              v15 = 278;
                              goto LABEL_5;
                            }
                          }
                        }
                        else
                        {
                          LastError = GetLastError();
                          v14 = WPP_GLOBAL_Control;
                          if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control
                            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
                          {
                            v15 = 277;
                            goto LABEL_5;
                          }
                        }
                      }
                      else
                      {
                        LastError = GetLastError();
                        v14 = WPP_GLOBAL_Control;
                        if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control
                          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
                        {
                          v15 = 276;
                          goto LABEL_5;
                        }
                      }
                    }
                    else
                    {
                      LastError = GetLastError();
                      v14 = WPP_GLOBAL_Control;
                      if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control
                        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
                      {
                        v15 = 275;
                        goto LABEL_5;
                      }
                    }
                  }
                  else
                  {
                    LastError = GetLastError();
                    v14 = WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control
                      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
                    {
                      v15 = 274;
                      goto LABEL_5;
                    }
                  }
                }
                else
                {
                  LastError = GetLastError();
                  v14 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control
                    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
                  {
                    v15 = 273;
                    goto LABEL_5;
                  }
                }
              }
              else
              {
                LastError = GetLastError();
                v14 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control
                  && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
                {
                  v15 = 272;
                  goto LABEL_5;
                }
              }
            }
            else
            {
              LastError = GetLastError();
              v14 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control
                && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
              {
                v15 = 271;
                goto LABEL_5;
              }
            }
          }
          else
          {
            LastError = GetLastError();
            v14 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control
              && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
            {
              v15 = 270;
              goto LABEL_5;
            }
          }
        }
        else
        {
          LastError = GetLastError();
          v14 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
          {
            v15 = 269;
            goto LABEL_5;
          }
        }
      }
      else
      {
        LastError = GetLastError();
        v14 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
        {
          v15 = 268;
          goto LABEL_5;
        }
      }
    }
    else
    {
      LastError = GetLastError();
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
      {
        v15 = 267;
        goto LABEL_5;
      }
    }
  }
  else
  {
    LastError = GetLastError();
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
    {
      v15 = 266;
LABEL_5:
      WPP_SF_d(*((_QWORD *)v14 + 2), v15, WPP_b63808fa0c5238d38dcfcce171ba8ec4_Traceguids, LastError);
    }
  }
  if ( hHash )
    CryptDestroyHash(hHash);
  if ( LastError )
  {
    if ( phHash )
      CryptDestroyHash(phHash);
    if ( phKey )
      CryptDestroyKey(phKey);
    if ( hKey )
      CryptDestroyKey(hKey);
  }
  return LastError;
}

```

## disassembly

```asm
0x1800c441c  push    rbp
0x1800c441e  push    rbx
0x1800c441f  push    rsi
0x1800c4420  push    rdi
0x1800c4421  push    r14
0x1800c4423  mov     rbp, rsp
0x1800c4426  sub     rsp, 80h
0x1800c442d  xor     eax, eax
0x1800c442f  mov     [rbp+phKey], 0
0x1800c4437  xorps   xmm0, xmm0
0x1800c443a  mov     [rbp+var_8], rax
0x1800c443e  lea     rax, [rbp+hHash]
0x1800c4442  mov     [rbp+hKey], 0
0x1800c444a  mov     rsi, r9
0x1800c444d  mov     [rsp+80h+phHash], rax; phHash
0x1800c4452  mov     r14, r8
0x1800c4455  mov     [rbp+var_38], 0
0x1800c445d  mov     rdi, rdx
0x1800c4460  mov     [rbp+hHash], 0
0x1800c4468  xor     r9d, r9d; dwFlags
0x1800c446b  mov     dword ptr [rbp+var_50], 0
0x1800c4472  xor     r8d, r8d; hKey
0x1800c4475  mov     edx, 8004h; Algid
0x1800c447a  mov     rbx, rcx
0x1800c447d  movups  xmmword ptr [rbp+var_28], xmm0
0x1800c4481  movups  [rbp+var_18], xmm0
0x1800c4485  call    cs:__imp_CryptCreateHash
0x1800c448c  nop     dword ptr [rax+rax+00h]
0x1800c4491  test    eax, eax
0x1800c4493  jnz     short loc_1800C44E4
0x1800c4495  call    cs:__imp_GetLastError
0x1800c449c  nop     dword ptr [rax+rax+00h]
0x1800c44a1  mov     ebx, eax
0x1800c44a3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c44aa  lea     rax, WPP_GLOBAL_Control
0x1800c44b1  cmp     rcx, rax
0x1800c44b4  jz      loc_1800C4979
0x1800c44ba  test    dword ptr [rcx+1Ch], 200h
0x1800c44c1  jz      loc_1800C4979
0x1800c44c7  mov     edx, 10Ah
0x1800c44cc  mov     rcx, [rcx+10h]
0x1800c44d0  lea     r8, WPP_b63808fa0c5238d38dcfcce171ba8ec4_Traceguids
0x1800c44d7  mov     r9d, ebx
0x1800c44da  call    WPP_SF_d
0x1800c44df  jmp     loc_1800C4979
0x1800c44e4  mov     r8d, [rbp+dwDataLen]; dwDataLen
0x1800c44e8  xor     r9d, r9d; dwFlags
0x1800c44eb  mov     rdx, [rbp+pbData]; pbData
0x1800c44ef  mov     rcx, [rbp+hHash]; hHash
0x1800c44f3  call    cs:__imp_CryptHashData
0x1800c44fa  nop     dword ptr [rax+rax+00h]
0x1800c44ff  test    eax, eax
0x1800c4501  jnz     short loc_1800C453C
0x1800c4503  call    cs:__imp_GetLastError
0x1800c450a  nop     dword ptr [rax+rax+00h]
0x1800c450f  mov     ebx, eax
0x1800c4511  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c4518  lea     rax, WPP_GLOBAL_Control
0x1800c451f  cmp     rcx, rax
0x1800c4522  jz      loc_1800C4979
0x1800c4528  test    dword ptr [rcx+1Ch], 200h
0x1800c452f  jz      loc_1800C4979
0x1800c4535  mov     edx, 10Bh
0x1800c453a  jmp     short loc_1800C44CC
0x1800c453c  mov     rcx, [rbp+hHash]; hHash
0x1800c4540  xor     r9d, r9d; dwFlags
0x1800c4543  mov     rdx, rdi; pbData
0x1800c4546  lea     r8d, [r9+10h]; dwDataLen
0x1800c454a  call    cs:__imp_CryptHashData
0x1800c4551  nop     dword ptr [rax+rax+00h]
0x1800c4556  test    eax, eax
0x1800c4558  jnz     short loc_1800C4596
0x1800c455a  call    cs:__imp_GetLastError
0x1800c4561  nop     dword ptr [rax+rax+00h]
0x1800c4566  mov     ebx, eax
0x1800c4568  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c456f  lea     rax, WPP_GLOBAL_Control
0x1800c4576  cmp     rcx, rax
0x1800c4579  jz      loc_1800C4979
0x1800c457f  test    dword ptr [rcx+1Ch], 200h
0x1800c4586  jz      loc_1800C4979
0x1800c458c  mov     edx, 10Ch
0x1800c4591  jmp     loc_1800C44CC
0x1800c4596  mov     r8, [rbp+hHash]; hBaseData
0x1800c459a  lea     rax, [rbp+phKey]
0x1800c459e  xor     r9d, r9d; dwFlags
0x1800c45a1  mov     [rsp+80h+phHash], rax; phKey
0x1800c45a6  mov     edx, 6610h; Algid
0x1800c45ab  mov     rcx, rbx; hProv
0x1800c45ae  call    cs:__imp_CryptDeriveKey
0x1800c45b5  nop     dword ptr [rax+rax+00h]
0x1800c45ba  test    eax, eax
0x1800c45bc  jnz     short loc_1800C45FA
0x1800c45be  call    cs:__imp_GetLastError
0x1800c45c5  nop     dword ptr [rax+rax+00h]
0x1800c45ca  mov     ebx, eax
0x1800c45cc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c45d3  lea     rax, WPP_GLOBAL_Control
0x1800c45da  cmp     rcx, rax
0x1800c45dd  jz      loc_1800C4979
0x1800c45e3  test    dword ptr [rcx+1Ch], 200h
0x1800c45ea  jz      loc_1800C4979
0x1800c45f0  mov     edx, 10Dh
0x1800c45f5  jmp     loc_1800C44CC
0x1800c45fa  mov     rcx, [rbp+phKey]; hKey
0x1800c45fe  lea     r8, [rbp+var_50]; pbData
0x1800c4602  mov     edi, 1
0x1800c4607  xor     r9d, r9d; dwFlags
0x1800c460a  mov     dword ptr [rbp+var_50], edi
0x1800c460d  lea     edx, [rdi+3]; dwParam
0x1800c4610  call    cs:__imp_CryptSetKeyParam
0x1800c4617  nop     dword ptr [rax+rax+00h]
0x1800c461c  test    eax, eax
0x1800c461e  jnz     short loc_1800C465C
0x1800c4620  call    cs:__imp_GetLastError
0x1800c4627  nop     dword ptr [rax+rax+00h]
0x1800c462c  mov     ebx, eax
0x1800c462e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c4635  lea     rax, WPP_GLOBAL_Control
0x1800c463c  cmp     rcx, rax
0x1800c463f  jz      loc_1800C4979
0x1800c4645  test    dword ptr [rcx+1Ch], 200h
0x1800c464c  jz      loc_1800C4979
0x1800c4652  mov     edx, 10Eh
0x1800c4657  jmp     loc_1800C44CC
0x1800c465c  mov     rcx, [rbp+phKey]; hKey
0x1800c4660  xor     r9d, r9d; dwFlags
0x1800c4663  mov     r8, rsi; pbData
0x1800c4666  mov     edx, edi; dwParam
0x1800c4668  call    cs:__imp_CryptSetKeyParam
0x1800c466f  nop     dword ptr [rax+rax+00h]
0x1800c4674  test    eax, eax
0x1800c4676  jnz     short loc_1800C46B4
0x1800c4678  call    cs:__imp_GetLastError
0x1800c467f  nop     dword ptr [rax+rax+00h]
0x1800c4684  mov     ebx, eax
0x1800c4686  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c468d  lea     rax, WPP_GLOBAL_Control
0x1800c4694  cmp     rcx, rax
0x1800c4697  jz      loc_1800C4979
0x1800c469d  test    dword ptr [rcx+1Ch], 200h
0x1800c46a4  jz      loc_1800C4979
0x1800c46aa  mov     edx, 10Fh
0x1800c46af  jmp     loc_1800C44CC
0x1800c46b4  mov     rcx, [rbp+hHash]; hHash
0x1800c46b8  call    cs:__imp_CryptDestroyHash
0x1800c46bf  nop     dword ptr [rax+rax+00h]
0x1800c46c4  test    eax, eax
0x1800c46c6  jnz     short loc_1800C4704
0x1800c46c8  call    cs:__imp_GetLastError
0x1800c46cf  nop     dword ptr [rax+rax+00h]
0x1800c46d4  mov     ebx, eax
0x1800c46d6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c46dd  lea     rax, WPP_GLOBAL_Control
0x1800c46e4  cmp     rcx, rax
0x1800c46e7  jz      loc_1800C4979
0x1800c46ed  test    dword ptr [rcx+1Ch], 200h
0x1800c46f4  jz      loc_1800C4979
0x1800c46fa  mov     edx, 110h
0x1800c46ff  jmp     loc_1800C44CC
0x1800c4704  lea     rax, [rbp+hHash]
0x1800c4708  mov     [rbp+hHash], 0
0x1800c4710  xor     r9d, r9d; dwFlags
0x1800c4713  mov     [rsp+80h+phHash], rax; phHash
0x1800c4718  xor     r8d, r8d; hKey
0x1800c471b  mov     edx, 8004h; Algid
0x1800c4720  mov     rcx, rbx; hProv
0x1800c4723  call    cs:__imp_CryptCreateHash
0x1800c472a  nop     dword ptr [rax+rax+00h]
0x1800c472f  test    eax, eax
0x1800c4731  jnz     short loc_1800C476F
0x1800c4733  call    cs:__imp_GetLastError
0x1800c473a  nop     dword ptr [rax+rax+00h]
0x1800c473f  mov     ebx, eax
0x1800c4741  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c4748  lea     rax, WPP_GLOBAL_Control
0x1800c474f  cmp     rcx, rax
0x1800c4752  jz      loc_1800C4979
0x1800c4758  test    dword ptr [rcx+1Ch], 200h
0x1800c475f  jz      loc_1800C4979
0x1800c4765  mov     edx, 111h
0x1800c476a  jmp     loc_1800C44CC
0x1800c476f  mov     r8d, [rbp+dwDataLen]; dwDataLen
0x1800c4773  xor     r9d, r9d; dwFlags
0x1800c4776  mov     rdx, [rbp+pbData]; pbData
0x1800c477a  mov     rcx, [rbp+hHash]; hHash
0x1800c477e  call    cs:__imp_CryptHashData
0x1800c4785  nop     dword ptr [rax+rax+00h]
0x1800c478a  test    eax, eax
0x1800c478c  jnz     short loc_1800C47CA
0x1800c478e  call    cs:__imp_GetLastError
0x1800c4795  nop     dword ptr [rax+rax+00h]
0x1800c479a  mov     ebx, eax
0x1800c479c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c47a3  lea     rax, WPP_GLOBAL_Control
0x1800c47aa  cmp     rcx, rax
0x1800c47ad  jz      loc_1800C4979
0x1800c47b3  test    dword ptr [rcx+1Ch], 200h
0x1800c47ba  jz      loc_1800C4979
0x1800c47c0  mov     edx, 112h
0x1800c47c5  jmp     loc_1800C44CC
0x1800c47ca  mov     rcx, [rbp+hHash]; hHash
0x1800c47ce  xor     r9d, r9d; dwFlags
0x1800c47d1  mov     rdx, r14; pbData
0x1800c47d4  lea     r8d, [r9+10h]; dwDataLen
0x1800c47d8  call    cs:__imp_CryptHashData
0x1800c47df  nop     dword ptr [rax+rax+00h]
0x1800c47e4  test    eax, eax
0x1800c47e6  jnz     short loc_1800C4824
0x1800c47e8  call    cs:__imp_GetLastError
0x1800c47ef  nop     dword ptr [rax+rax+00h]
0x1800c47f4  mov     ebx, eax
0x1800c47f6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c47fd  lea     rax, WPP_GLOBAL_Control
0x1800c4804  cmp     rcx, rax
0x1800c4807  jz      loc_1800C4979
0x1800c480d  test    dword ptr [rcx+1Ch], 200h
0x1800c4814  jz      loc_1800C4979
0x1800c481a  mov     edx, 113h
0x1800c481f  jmp     loc_1800C44CC
0x1800c4824  mov     r8, [rbp+hHash]; hBaseData
0x1800c4828  lea     rax, [rbp+hKey]
0x1800c482c  xor     r9d, r9d; dwFlags
0x1800c482f  mov     [rsp+80h+phHash], rax; phKey
0x1800c4834  mov     edx, 6602h; Algid
0x1800c4839  mov     rcx, rbx; hProv
0x1800c483c  call    cs:__imp_CryptDeriveKey
0x1800c4843  nop     dword ptr [rax+rax+00h]
0x1800c4848  test    eax, eax
0x1800c484a  jnz     short loc_1800C4888
0x1800c484c  call    cs:__imp_GetLastError
0x1800c4853  nop     dword ptr [rax+rax+00h]
0x1800c4858  mov     ebx, eax
0x1800c485a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c4861  lea     rax, WPP_GLOBAL_Control
0x1800c4868  cmp     rcx, rax
0x1800c486b  jz      loc_1800C4979
0x1800c4871  test    dword ptr [rcx+1Ch], 200h
0x1800c4878  jz      loc_1800C4979
0x1800c487e  mov     edx, 114h
0x1800c4883  jmp     loc_1800C44CC
0x1800c4888  mov     r8, [rbp+hKey]; hKey
0x1800c488c  lea     rax, [rbp+var_38]
0x1800c4890  xor     r9d, r9d; dwFlags
0x1800c4893  mov     [rsp+80h+phHash], rax; phHash
0x1800c4898  mov     edx, 8009h; Algid
0x1800c489d  mov     rcx, rbx; hProv
0x1800c48a0  call    cs:__imp_CryptCreateHash
0x1800c48a7  nop     dword ptr [rax+rax+00h]
0x1800c48ac  test    eax, eax
0x1800c48ae  jnz     short loc_1800C48EC
0x1800c48b0  call    cs:__imp_GetLastError
0x1800c48b7  nop     dword ptr [rax+rax+00h]
0x1800c48bc  mov     ebx, eax
0x1800c48be  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c48c5  lea     rax, WPP_GLOBAL_Control
0x1800c48cc  cmp     rcx, rax
0x1800c48cf  jz      loc_1800C4979
0x1800c48d5  test    dword ptr [rcx+1Ch], 200h
0x1800c48dc  jz      loc_1800C4979
0x1800c48e2  mov     edx, 115h
0x1800c48e7  jmp     loc_1800C44CC
0x1800c48ec  mov     rcx, [rbp+var_38]; hHash
0x1800c48f0  lea     r8, [rbp+var_28]; pbData
0x1800c48f4  xor     eax, eax
0x1800c48f6  xorps   xmm0, xmm0
0x1800c48f9  movups  xmmword ptr [rbp+var_28], xmm0
0x1800c48fd  xor     r9d, r9d; dwFlags
0x1800c4900  mov     [rbp+var_8], rax
0x1800c4904  movups  [rbp+var_18], xmm0
0x1800c4908  lea     edx, [rax+5]; dwParam
0x1800c490b  mov     dword ptr [rbp+var_28], 8004h
0x1800c4912  call    cs:__imp_CryptSetHashParam
0x1800c4919  nop     dword ptr [rax+rax+00h]
0x1800c491e  test    eax, eax
0x1800c4920  jnz     short loc_1800C4956
0x1800c4922  call    cs:__imp_GetLastError
0x1800c4929  nop     dword ptr [rax+rax+00h]
0x1800c492e  mov     ebx, eax
0x1800c4930  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c4937  lea     rax, WPP_GLOBAL_Control
0x1800c493e  cmp     rcx, rax
0x1800c4941  jz      short loc_1800C4979
0x1800c4943  test    dword ptr [rcx+1Ch], 200h
0x1800c494a  jz      short loc_1800C4979
0x1800c494c  mov     edx, 116h
0x1800c4951  jmp     loc_1800C44CC
0x1800c4956  mov     rax, [rbp+arg_30]
0x1800c495a  xor     ebx, ebx
0x1800c495c  mov     rcx, [rbp+phKey]
0x1800c4960  mov     [rax], rcx
0x1800c4963  mov     rax, [rbp+arg_38]
0x1800c4967  mov     rcx, [rbp+hKey]
0x1800c496b  mov     [rax], rcx
0x1800c496e  mov     rax, [rbp+arg_40]
0x1800c4972  mov     rcx, [rbp+var_38]
0x1800c4976  mov     [rax], rcx
0x1800c4979  mov     rcx, [rbp+hHash]; hHash
0x1800c497d  test    rcx, rcx
0x1800c4980  jz      short loc_1800C498E
  ... truncated ...
```
