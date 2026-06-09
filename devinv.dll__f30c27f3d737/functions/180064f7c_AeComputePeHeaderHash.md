# AeComputePeHeaderHash

- ea: `0x180064f7c`
- end: `0x1800653ed`
- name: `AeComputePeHeaderHash`
- size: `1137`
- prototype: `__int64 __fastcall(BYTE *pbData)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180077298`

## callees

- `0x180063f04`
- `0x180064f7c`
- `0x180065d34`
- `0x180065d5c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006507d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800650fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180065159`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800651bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006521d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006529b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006534d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006507d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800650fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180065159`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800651bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006521d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006529b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006534d`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptAcquireContextW` at `0x180065073`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptAcquireContextW` at `0x180065073`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptReleaseContext` at `0x1800653d8`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptReleaseContext` at `0x1800653d8`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDestroyHash` at `0x1800653ba`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDestroyHash` at `0x1800653ba`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptCreateHash` at `0x1800650f1`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptCreateHash` at `0x1800650f1`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptHashData` at `0x18006514f`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptHashData` at `0x1800651b1`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptHashData` at `0x180065213`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptHashData` at `0x18006514f`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptHashData` at `0x1800651b1`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptHashData` at `0x180065213`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGetHashParam` at `0x180065291`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGetHashParam` at `0x180065343`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGetHashParam` at `0x180065291`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGetHashParam` at `0x180065343`

## pseudocode

```c
__int64 __fastcall AeComputePeHeaderHash(BYTE *pbData, unsigned __int64 a2, __int64 a3)
{
  BYTE *v5; // r8
  BYTE *v6; // rdx
  BYTE *v7; // r14
  unsigned int v8; // ebx
  BYTE *v9; // rsi
  const BYTE *v10; // r15
  signed int v11; // eax
  _QWORD *v12; // rcx
  __int64 v13; // rdx
  signed int v14; // eax
  signed int v15; // eax
  signed int v16; // eax
  signed int v17; // eax
  signed int v18; // eax
  signed int LastError; // eax
  HCRYPTPROV phProv[6]; // [rsp+38h] [rbp-30h] BYREF
  DWORD pdwDataLen; // [rsp+70h] [rbp+8h] BYREF
  unsigned __int64 pbDataa; // [rsp+78h] [rbp+10h] BYREF
  HCRYPTHASH phHash; // [rsp+88h] [rbp+20h] BYREF

  pbDataa = a2;
  phProv[0] = 0;
  phHash = 0;
  pdwDataLen = 0;
  if ( pbData && a2 >= 0x108 && a3 )
  {
    v5 = &pbData[a2];
    if ( &pbData[a2] < pbData )
      goto LABEL_64;
    v6 = &pbData[*((unsigned __int16 *)pbData + 10) + 24];
    v7 = &v6[40 * *((unsigned __int16 *)pbData + 3)];
    if ( v7 < v6 || v7 > v5 )
      goto LABEL_64;
    if ( *((_WORD *)pbData + 12) == 267 )
    {
      v9 = pbData + 52;
      v10 = pbData + 56;
    }
    else
    {
      if ( *((_WORD *)pbData + 12) != 523 )
      {
        v8 = -2147024809;
        goto LABEL_67;
      }
      v9 = pbData + 48;
      v10 = pbData + 56;
    }
    if ( v9 < pbData || v9 >= v7 || v10 < v9 || v10 >= v7 )
    {
LABEL_64:
      v8 = -805306245;
    }
    else if ( CryptAcquireContextW(phProv, 0, L"Microsoft Base Cryptographic Provider v1.0", 1u, 0xF0000000) )
    {
      if ( CryptCreateHash(phProv[0], 0x8004u, 0, 0, &phHash) )
      {
        if ( CryptHashData(phHash, pbData, (_DWORD)v9 - (_DWORD)pbData, 0) )
        {
          if ( CryptHashData(phHash, v10, (_DWORD)v7 - (_DWORD)v10, 0) )
          {
            if ( CryptHashData(phHash, (const BYTE *)&pbDataa, 8u, 0) )
            {
              pdwDataLen = 0;
              *(_OWORD *)a3 = 0;
              *(_QWORD *)(a3 + 14) = 0;
              if ( CryptGetHashParam(phHash, 2u, 0, &pdwDataLen, 0) )
              {
                if ( pdwDataLen == 20 )
                {
                  if ( CryptGetHashParam(phHash, 2u, (BYTE *)(a3 + 2), &pdwDataLen, 0) )
                  {
                    *(_BYTE *)a3 = 1;
                    v8 = 0;
                  }
                  else
                  {
                    LastError = GetLastError();
                    v8 = LastError;
                    if ( LastError > 0 )
                      v8 = (unsigned __int16)LastError | 0x80070000;
                    v12 = WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                    {
                      v13 = 54;
                      goto LABEL_22;
                    }
                  }
                }
                else
                {
                  v8 = -2147418113;
                  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                  {
                    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 53, WPP_ff13ec65e0c03369507e3b373b281b2e_Traceguids);
                  }
                }
              }
              else
              {
                v18 = GetLastError();
                v8 = v18;
                if ( v18 > 0 )
                  v8 = (unsigned __int16)v18 | 0x80070000;
                v12 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                {
                  v13 = 52;
                  goto LABEL_22;
                }
              }
            }
            else
            {
              v17 = GetLastError();
              v8 = v17;
              if ( v17 > 0 )
                v8 = (unsigned __int16)v17 | 0x80070000;
              v12 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                v13 = 51;
                goto LABEL_22;
              }
            }
          }
          else
          {
            v16 = GetLastError();
            v8 = v16;
            if ( v16 > 0 )
              v8 = (unsigned __int16)v16 | 0x80070000;
            v12 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              v13 = 50;
              goto LABEL_22;
            }
          }
        }
        else
        {
          v15 = GetLastError();
          v8 = v15;
          if ( v15 > 0 )
            v8 = (unsigned __int16)v15 | 0x80070000;
          v12 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v13 = 49;
            goto LABEL_22;
          }
        }
      }
      else
      {
        v14 = GetLastError();
        v8 = v14;
        if ( v14 > 0 )
          v8 = (unsigned __int16)v14 | 0x80070000;
        v12 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v13 = 48;
          goto LABEL_22;
        }
      }
    }
    else
    {
      v11 = GetLastError();
      v8 = v11;
      if ( v11 > 0 )
        v8 = (unsigned __int16)v11 | 0x80070000;
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v13 = 47;
LABEL_22:
        WPP_SF_D(v12[2], v13, WPP_ff13ec65e0c03369507e3b373b281b2e_Traceguids, v8);
      }
    }
  }
  else
  {
    v8 = -2147024809;
  }
LABEL_67:
  if ( phHash )
  {
    CryptDestroyHash(phHash);
    phHash = 0;
  }
  if ( phProv[0] )
    CryptReleaseContext(phProv[0], 0);
  return v8;
}

```

## disassembly

```asm
0x180064f7c  mov     rax, rsp
0x180064f7f  mov     [rax+10h], rdx
0x180064f83  push    rbx
0x180064f84  push    rsi
0x180064f85  push    r12
0x180064f87  push    r14
0x180064f89  push    r15
0x180064f8b  sub     rsp, 40h
0x180064f8f  mov     r12, r8
0x180064f92  mov     rbx, rcx
0x180064f95  mov     qword ptr [rax-30h], 0
0x180064f9d  mov     qword ptr [rax+20h], 0
0x180064fa5  mov     dword ptr [rax+8], 0
0x180064fac  test    rcx, rcx
0x180064faf  jz      loc_1800653A8
0x180064fb5  cmp     rdx, 108h
0x180064fbc  jb      loc_1800653A8
0x180064fc2  test    r8, r8
0x180064fc5  jz      loc_1800653A8
0x180064fcb  lea     r8, [rcx+rdx]
0x180064fcf  cmp     r8, rcx
0x180064fd2  jb      loc_180065392
0x180064fd8  movzx   edx, word ptr [rcx+14h]
0x180064fdc  add     rdx, 18h
0x180064fe0  add     rdx, rcx
0x180064fe3  movzx   eax, word ptr [rcx+6]
0x180064fe7  lea     rcx, [rax+rax*4]
0x180064feb  lea     r14, [rdx+rcx*8]
0x180064fef  cmp     r14, rdx
0x180064ff2  jb      loc_180065392
0x180064ff8  cmp     r14, r8
0x180064ffb  ja      loc_180065392
0x180065001  mov     eax, 10Bh
0x180065006  cmp     [rbx+18h], ax
0x18006500a  jz      short loc_18006502B
0x18006500c  mov     eax, 20Bh
0x180065011  cmp     [rbx+18h], ax
0x180065015  jz      short loc_180065021
0x180065017  mov     ebx, 80070057h
0x18006501c  jmp     loc_180065397
0x180065021  lea     rsi, [rbx+30h]
0x180065025  lea     r15, [rsi+8]
0x180065029  jmp     short loc_180065033
0x18006502b  lea     rsi, [rbx+34h]
0x18006502f  lea     r15, [rsi+4]
0x180065033  cmp     rsi, rbx
0x180065036  jb      loc_180065392
0x18006503c  cmp     rsi, r14
0x18006503f  jnb     loc_180065392
0x180065045  cmp     r15, rsi
0x180065048  jb      loc_180065392
0x18006504e  cmp     r15, r14
0x180065051  jnb     loc_180065392
0x180065057  mov     [rsp+68h+dwFlags], 0F0000000h; dwFlags
0x18006505f  mov     r9d, 1; dwProvType
0x180065065  lea     r8, szProvider; "Microsoft Base Cryptographic Provider v"...
0x18006506c  xor     edx, edx; szContainer
0x18006506e  lea     rcx, [rsp+68h+phProv]; phProv
0x180065073  call    cs:__imp_CryptAcquireContextW
0x180065079  test    eax, eax
0x18006507b  jnz     short loc_1800650D4
0x18006507d  call    cs:__imp_GetLastError
0x180065083  mov     ebx, eax
0x180065085  test    eax, eax
0x180065087  jle     short loc_180065092
0x180065089  movzx   ebx, ax
0x18006508c  or      ebx, 80070000h
0x180065092  mov     [rsp+68h+var_38], ebx
0x180065096  lea     rax, WPP_GLOBAL_Control
0x18006509d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800650a4  cmp     rcx, rax
0x1800650a7  jz      loc_18006539B
0x1800650ad  test    byte ptr [rcx+1Ch], 1
0x1800650b1  jz      loc_18006539B
0x1800650b7  mov     edx, 2Fh ; '/'
0x1800650bc  mov     r9d, ebx
0x1800650bf  lea     r8, WPP_ff13ec65e0c03369507e3b373b281b2e_Traceguids
0x1800650c6  mov     rcx, [rcx+10h]
0x1800650ca  call    WPP_SF_D
0x1800650cf  jmp     loc_18006539B
0x1800650d4  lea     rax, [rsp+68h+phHash]
0x1800650dc  mov     qword ptr [rsp+68h+dwFlags], rax; phHash
0x1800650e1  xor     r9d, r9d; dwFlags
0x1800650e4  xor     r8d, r8d; hKey
0x1800650e7  mov     edx, 8004h; Algid
0x1800650ec  mov     rcx, [rsp+68h+phProv]; hProv
0x1800650f1  call    cs:__imp_CryptCreateHash
0x1800650f7  test    eax, eax
0x1800650f9  jnz     short loc_18006513C
0x1800650fb  call    cs:__imp_GetLastError
0x180065101  mov     ebx, eax
0x180065103  test    eax, eax
0x180065105  jle     short loc_180065110
0x180065107  movzx   ebx, ax
0x18006510a  or      ebx, 80070000h
0x180065110  mov     [rsp+68h+var_38], ebx
0x180065114  lea     rax, WPP_GLOBAL_Control
0x18006511b  mov     rcx, cs:WPP_GLOBAL_Control
0x180065122  cmp     rcx, rax
0x180065125  jz      loc_18006539B
0x18006512b  test    byte ptr [rcx+1Ch], 1
0x18006512f  jz      loc_18006539B
0x180065135  mov     edx, 30h ; '0'
0x18006513a  jmp     short loc_1800650BC
0x18006513c  sub     esi, ebx
0x18006513e  xor     r9d, r9d; dwFlags
0x180065141  mov     r8d, esi; dwDataLen
0x180065144  mov     rdx, rbx; pbData
0x180065147  mov     rcx, [rsp+68h+phHash]; hHash
0x18006514f  call    cs:__imp_CryptHashData
0x180065155  test    eax, eax
0x180065157  jnz     short loc_18006519D
0x180065159  call    cs:__imp_GetLastError
0x18006515f  mov     ebx, eax
0x180065161  test    eax, eax
0x180065163  jle     short loc_18006516E
0x180065165  movzx   ebx, ax
0x180065168  or      ebx, 80070000h
0x18006516e  mov     [rsp+68h+var_38], ebx
0x180065172  lea     rax, WPP_GLOBAL_Control
0x180065179  mov     rcx, cs:WPP_GLOBAL_Control
0x180065180  cmp     rcx, rax
0x180065183  jz      loc_18006539B
0x180065189  test    byte ptr [rcx+1Ch], 1
0x18006518d  jz      loc_18006539B
0x180065193  mov     edx, 31h ; '1'
0x180065198  jmp     loc_1800650BC
0x18006519d  sub     r14d, r15d
0x1800651a0  xor     r9d, r9d; dwFlags
0x1800651a3  mov     r8d, r14d; dwDataLen
0x1800651a6  mov     rdx, r15; pbData
0x1800651a9  mov     rcx, [rsp+68h+phHash]; hHash
0x1800651b1  call    cs:__imp_CryptHashData
0x1800651b7  test    eax, eax
0x1800651b9  jnz     short loc_1800651FF
0x1800651bb  call    cs:__imp_GetLastError
0x1800651c1  mov     ebx, eax
0x1800651c3  test    eax, eax
0x1800651c5  jle     short loc_1800651D0
0x1800651c7  movzx   ebx, ax
0x1800651ca  or      ebx, 80070000h
0x1800651d0  mov     [rsp+68h+var_38], ebx
0x1800651d4  lea     rax, WPP_GLOBAL_Control
0x1800651db  mov     rcx, cs:WPP_GLOBAL_Control
0x1800651e2  cmp     rcx, rax
0x1800651e5  jz      loc_18006539B
0x1800651eb  test    byte ptr [rcx+1Ch], 1
0x1800651ef  jz      loc_18006539B
0x1800651f5  mov     edx, 32h ; '2'
0x1800651fa  jmp     loc_1800650BC
0x1800651ff  xor     r9d, r9d; dwFlags
0x180065202  lea     r8d, [r9+8]; dwDataLen
0x180065206  lea     rdx, [rsp+68h+pbData]; pbData
0x18006520b  mov     rcx, [rsp+68h+phHash]; hHash
0x180065213  call    cs:__imp_CryptHashData
0x180065219  test    eax, eax
0x18006521b  jnz     short loc_180065261
0x18006521d  call    cs:__imp_GetLastError
0x180065223  mov     ebx, eax
0x180065225  test    eax, eax
0x180065227  jle     short loc_180065232
0x180065229  movzx   ebx, ax
0x18006522c  or      ebx, 80070000h
0x180065232  mov     [rsp+68h+var_38], ebx
0x180065236  lea     rax, WPP_GLOBAL_Control
0x18006523d  mov     rcx, cs:WPP_GLOBAL_Control
0x180065244  cmp     rcx, rax
0x180065247  jz      loc_18006539B
0x18006524d  test    byte ptr [rcx+1Ch], 1
0x180065251  jz      loc_18006539B
0x180065257  mov     edx, 33h ; '3'
0x18006525c  jmp     loc_1800650BC
0x180065261  mov     [rsp+68h+pdwDataLen], 0
0x180065269  xorps   xmm0, xmm0
0x18006526c  xor     eax, eax
0x18006526e  movups  xmmword ptr [r12], xmm0
0x180065273  mov     [r12+0Eh], rax
0x180065278  mov     [rsp+68h+dwFlags], eax; dwFlags
0x18006527c  lea     r9, [rsp+68h+pdwDataLen]; pdwDataLen
0x180065281  xor     r8d, r8d; pbData
0x180065284  lea     ebx, [rax+2]
0x180065287  mov     edx, ebx; dwParam
0x180065289  mov     rcx, [rsp+68h+phHash]; hHash
0x180065291  call    cs:__imp_CryptGetHashParam
0x180065297  test    eax, eax
0x180065299  jnz     short loc_1800652DF
0x18006529b  call    cs:__imp_GetLastError
0x1800652a1  mov     ebx, eax
0x1800652a3  test    eax, eax
0x1800652a5  jle     short loc_1800652B0
0x1800652a7  movzx   ebx, ax
0x1800652aa  or      ebx, 80070000h
0x1800652b0  mov     [rsp+68h+var_38], ebx
0x1800652b4  lea     rax, WPP_GLOBAL_Control
0x1800652bb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800652c2  cmp     rcx, rax
0x1800652c5  jz      loc_18006539B
0x1800652cb  test    byte ptr [rcx+1Ch], 1
0x1800652cf  jz      loc_18006539B
0x1800652d5  mov     edx, 34h ; '4'
0x1800652da  jmp     loc_1800650BC
0x1800652df  cmp     [rsp+68h+pdwDataLen], 14h
0x1800652e4  jz      short loc_180065327
0x1800652e6  mov     ebx, 8000FFFFh
0x1800652eb  mov     [rsp+68h+var_38], ebx
0x1800652ef  lea     rax, WPP_GLOBAL_Control
0x1800652f6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800652fd  cmp     rcx, rax
0x180065300  jz      loc_18006539B
0x180065306  test    byte ptr [rcx+1Ch], 1
0x18006530a  jz      loc_18006539B
0x180065310  mov     edx, 35h ; '5'
0x180065315  lea     r8, WPP_ff13ec65e0c03369507e3b373b281b2e_Traceguids
0x18006531c  mov     rcx, [rcx+10h]
0x180065320  call    WPP_SF_
0x180065325  jmp     short loc_18006539B
0x180065327  lea     r8, [r12+2]; pbData
0x18006532c  mov     [rsp+68h+dwFlags], 0; dwFlags
0x180065334  lea     r9, [rsp+68h+pdwDataLen]; pdwDataLen
0x180065339  mov     edx, ebx; dwParam
0x18006533b  mov     rcx, [rsp+68h+phHash]; hHash
0x180065343  call    cs:__imp_CryptGetHashParam
0x180065349  test    eax, eax
0x18006534b  jnz     short loc_180065389
0x18006534d  call    cs:__imp_GetLastError
0x180065353  mov     ebx, eax
0x180065355  test    eax, eax
0x180065357  jle     short loc_180065362
0x180065359  movzx   ebx, ax
0x18006535c  or      ebx, 80070000h
0x180065362  mov     [rsp+68h+var_38], ebx
0x180065366  lea     rax, WPP_GLOBAL_Control
0x18006536d  mov     rcx, cs:WPP_GLOBAL_Control
0x180065374  cmp     rcx, rax
0x180065377  jz      short loc_18006539B
0x180065379  test    byte ptr [rcx+1Ch], 1
0x18006537d  jz      short loc_18006539B
0x18006537f  mov     edx, 36h ; '6'
0x180065384  jmp     loc_1800650BC
0x180065389  mov     byte ptr [r12], 1
0x18006538e  xor     ebx, ebx
0x180065390  jmp     short loc_180065397
0x180065392  mov     ebx, 0D000007Bh
0x180065397  mov     [rsp+68h+var_38], ebx
0x18006539b  jmp     short loc_1800653AD
0x18006539d  mov     ebx, 80004005h
0x1800653a2  mov     [rsp+68h+var_38], ebx
0x1800653a6  jmp     short loc_1800653AD
0x1800653a8  mov     ebx, 80070057h
0x1800653ad  mov     rcx, [rsp+68h+phHash]; hHash
0x1800653b5  test    rcx, rcx
0x1800653b8  jz      short loc_1800653CC
0x1800653ba  call    cs:__imp_CryptDestroyHash
0x1800653c0  mov     [rsp+68h+phHash], 0
0x1800653cc  mov     rcx, [rsp+68h+phProv]; hProv
0x1800653d1  test    rcx, rcx
0x1800653d4  jz      short loc_1800653DE
0x1800653d6  xor     edx, edx; dwFlags
0x1800653d8  call    cs:__imp_CryptReleaseContext
0x1800653de  mov     eax, ebx
0x1800653e0  add     rsp, 40h
0x1800653e4  pop     r15
0x1800653e6  pop     r14
0x1800653e8  pop     r12
0x1800653ea  pop     rsi
0x1800653eb  pop     rbx
0x1800653ec  retn
0x180114a76  push    rbp
0x180114a78  sub     rsp, 30h
0x180114a7c  mov     rbp, rdx
0x180114a7f  call    ?PageErrorExceptionHandler@@YAKPEAU_EXCEPTION_POINTERS@@PEBDK@Z; PageErrorExceptionHandler(_EXCEPTION_POINTERS *,char const *,ulong)
0x180114a84  nop
0x180114a85  add     rsp, 30h
0x180114a89  pop     rbp
0x180114a8a  retn
```
