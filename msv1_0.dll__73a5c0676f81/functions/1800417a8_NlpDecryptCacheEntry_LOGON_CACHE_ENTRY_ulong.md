# NlpDecryptCacheEntry(_LOGON_CACHE_ENTRY *,ulong)

- ea: `0x1800417a8`
- end: `0x180041baf`
- name: `?NlpDecryptCacheEntry@@YAJPEAU_LOGON_CACHE_ENTRY@@K@Z`
- size: `1031`
- prototype: `__int64 __fastcall(struct _LOGON_CACHE_ENTRY *, unsigned int)`
- caller_count: `3`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180042424`
- `0x180042ccc`
- `0x180042dac`

## callees

- `0x18002ee7c`
- `0x18002fb50`
- `0x1800417a8`
- `0x18006bd68`

## import_xrefs

- `bcrypt!BCryptFinishHash` at `0x1800418ca`
- `bcrypt!BCryptFinishHash` at `0x180041aae`
- `bcrypt!BCryptFinishHash` at `0x1800418ca`
- `bcrypt!BCryptFinishHash` at `0x180041aae`
- `bcrypt!BCryptDestroyHash` at `0x180041b5a`
- `bcrypt!BCryptDestroyHash` at `0x180041b5a`
- `bcrypt!BCryptHashData` at `0x180041885`
- `bcrypt!BCryptHashData` at `0x180041a66`
- `bcrypt!BCryptHashData` at `0x180041885`
- `bcrypt!BCryptHashData` at `0x180041a66`
- `bcrypt!BCryptCreateHash` at `0x18004182a`
- `bcrypt!BCryptCreateHash` at `0x180041a1f`
- `bcrypt!BCryptCreateHash` at `0x18004182a`
- `bcrypt!BCryptCreateHash` at `0x180041a1f`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x18004194c`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x18004194c`
- `bcrypt!BCryptDestroyKey` at `0x1800419f3`
- `bcrypt!BCryptDestroyKey` at `0x180041b4b`
- `bcrypt!BCryptDestroyKey` at `0x1800419f3`
- `bcrypt!BCryptDestroyKey` at `0x180041b4b`
- `bcrypt!BCryptEncrypt` at `0x1800419b5`
- `bcrypt!BCryptEncrypt` at `0x1800419b5`
- `cryptdll!HMACwithSHA` at `0x180041b27`
- `cryptdll!HMACwithSHA` at `0x180041b27`
- `cryptdll!aesCTSDecryptMsg` at `0x180041b00`
- `cryptdll!aesCTSDecryptMsg` at `0x180041b00`

## pseudocode

```c
__int64 __fastcall NlpDecryptCacheEntry(struct _LOGON_CACHE_ENTRY *a1, int a2)
{
  struct _LOGON_CACHE_ENTRY *v3; // rdi
  int v4; // ebx
  _QWORD *v5; // rcx
  __int64 v6; // rdx
  ULONG cbOutput; // r14d
  __int64 v8; // rcx
  UCHAR *v9; // rax
  ULONG dwFlags[2]; // [rsp+30h] [rbp-49h]
  BCRYPT_HASH_HANDLE phHash; // [rsp+50h] [rbp-29h] BYREF
  BCRYPT_KEY_HANDLE phKey; // [rsp+58h] [rbp-21h] BYREF
  ULONG pcbResult; // [rsp+60h] [rbp-19h] BYREF
  UCHAR pbOutput[16]; // [rsp+68h] [rbp-11h] BYREF
  UCHAR Buf1[16]; // [rsp+78h] [rbp-1h] BYREF
  __int128 v17; // [rsp+88h] [rbp+Fh] BYREF

  v3 = a1;
  phHash = 0;
  phKey = 0;
  pcbResult = 0;
  if ( !*((_BYTE *)a1 + 48) )
    return 3221225581LL;
  if ( *((_WORD *)a1 + 25) )
  {
    *(_OWORD *)pbOutput = *(_OWORD *)&NlpCacheEncryptionKey;
LABEL_18:
    cbOutput = a2 - 96;
    if ( *((_WORD *)v3 + 25) )
    {
      v17 = *((_OWORD *)a1 + 4);
      v4 = aesCTSDecryptMsg(16, pbOutput, cbOutput, (char *)v3 + 96, &v17);
      if ( v4 >= 0 )
        v4 = HMACwithSHA(pbOutput, 16, (char *)v3 + 96, cbOutput, Buf1, 16, *(_QWORD *)dwFlags);
      goto LABEL_41;
    }
    v4 = BCryptGenerateSymmetricKey((BCRYPT_ALG_HANDLE)0x71, &phKey, 0, 0, pbOutput, 0x10u, 0);
    if ( v4 >= 0 )
    {
      v4 = BCryptEncrypt(phKey, (PUCHAR)v3 + 96, cbOutput, 0, 0, 0, (PUCHAR)v3 + 96, cbOutput, &pcbResult, 0);
      if ( v4 >= 0 )
      {
        BCryptDestroyKey(phKey);
        phKey = 0;
        v4 = BCryptCreateHash((BCRYPT_ALG_HANDLE)0x91, &phHash, 0, 0, pbOutput, 0x10u, 0);
        if ( v4 >= 0 )
        {
          v4 = BCryptHashData(phHash, (PUCHAR)v3 + 96, cbOutput, 0);
          if ( v4 >= 0 )
          {
            v4 = BCryptFinishHash(phHash, Buf1, 0x10u, 0);
            if ( v4 >= 0 )
              goto LABEL_41;
            v5 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
              || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x4000) == 0 )
            {
              goto LABEL_41;
            }
            v6 = 41;
          }
          else
          {
            v5 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
              || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x4000) == 0 )
            {
              goto LABEL_41;
            }
            v6 = 40;
          }
        }
        else
        {
          v5 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
            || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x4000) == 0 )
          {
            goto LABEL_41;
          }
          v6 = 39;
        }
      }
      else
      {
        v5 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x4000) == 0 )
        {
          goto LABEL_41;
        }
        v6 = 38;
      }
    }
    else
    {
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x4000) == 0 )
        goto LABEL_41;
      v6 = 37;
    }
    goto LABEL_7;
  }
  v4 = BCryptCreateHash((BCRYPT_ALG_HANDLE)0x91, &phHash, 0, 0, &NlpCacheEncryptionKey, 0x40u, 0);
  if ( v4 >= 0 )
  {
    v4 = BCryptHashData(phHash, (PUCHAR)v3 + 64, 0x10u, 0);
    if ( v4 < 0 )
    {
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x4000) == 0 )
        goto LABEL_41;
      v6 = 35;
      goto LABEL_7;
    }
    v4 = BCryptFinishHash(phHash, pbOutput, 0x10u, 0);
    if ( v4 < 0 )
    {
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x4000) == 0 )
        goto LABEL_41;
      v6 = 36;
      goto LABEL_7;
    }
    a1 = v3;
    goto LABEL_18;
  }
  v5 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x4000) == 0 )
    goto LABEL_41;
  v6 = 34;
LABEL_7:
  WPP_SF_d(v5[2], v6, WPP_905305d962583d6f838b30057de84013_Traceguids, (unsigned int)v4);
LABEL_41:
  v8 = 16;
  v9 = pbOutput;
  do
  {
    *v9++ = 0;
    --v8;
  }
  while ( v8 );
  if ( phKey )
    BCryptDestroyKey(phKey);
  if ( phHash )
    BCryptDestroyHash(phHash);
  if ( v4 >= 0 )
    return memcmp_0(Buf1, (char *)v3 + 80, 0x10u) != 0 ? 0xC000006D : 0;
  else
    return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800417a8  mov     [rsp-8+arg_10], rbx
0x1800417ad  push    rbp
0x1800417ae  push    rsi
0x1800417af  push    rdi
0x1800417b0  push    r12
0x1800417b2  push    r13
0x1800417b4  push    r14
0x1800417b6  push    r15
0x1800417b8  lea     rbp, [rsp-27h]
0x1800417bd  sub     rsp, 0A0h
0x1800417c4  mov     rax, cs:__security_cookie
0x1800417cb  xor     rax, rsp
0x1800417ce  mov     [rbp+57h+var_38], rax
0x1800417d2  xor     r12d, r12d
0x1800417d5  mov     r14d, edx
0x1800417d8  mov     rdi, rcx
0x1800417db  mov     [rbp+57h+phHash], r12
0x1800417df  mov     [rbp+57h+phKey], r12
0x1800417e3  mov     [rbp+57h+var_70], r12d
0x1800417e7  cmp     [rcx+30h], r12b
0x1800417eb  jz      loc_180041B83
0x1800417f1  lea     r13d, [r12+10h]
0x1800417f6  lea     r15d, [r12+40h]
0x1800417fb  cmp     [rcx+32h], r12w
0x180041800  jnz     loc_180041909
0x180041806  mov     [rsp+0D0h+dwFlags], r12d; dwFlags
0x18004180b  lea     rax, ?NlpCacheEncryptionKey@@3PADA; char near * NlpCacheEncryptionKey
0x180041812  mov     [rsp+0D0h+cbSecret], r15d; cbSecret
0x180041817  lea     rdx, [rbp+57h+phHash]; phHash
0x18004181b  xor     r9d, r9d; cbHashObject
0x18004181e  mov     [rsp+0D0h+pbSecret], rax; pbSecret
0x180041823  xor     r8d, r8d; pbHashObject
0x180041826  lea     ecx, [r15+51h]; hAlgorithm
0x18004182a  call    cs:__imp_BCryptCreateHash
0x180041830  mov     ebx, eax
0x180041832  test    eax, eax
0x180041834  jns     short loc_180041877
0x180041836  mov     rcx, cs:WPP_GLOBAL_Control
0x18004183d  lea     rax, WPP_GLOBAL_Control
0x180041844  cmp     rcx, rax
0x180041847  jz      loc_180041B2F
0x18004184d  test    dword ptr [rcx+1Ch], 4000h
0x180041854  jz      loc_180041B2F
0x18004185a  lea     edx, [r12+22h]
0x18004185f  mov     rcx, [rcx+10h]
0x180041863  lea     r8, WPP_905305d962583d6f838b30057de84013_Traceguids
0x18004186a  mov     r9d, ebx
0x18004186d  call    WPP_SF_d
0x180041872  jmp     loc_180041B2F
0x180041877  mov     rcx, [rbp+57h+phHash]; hHash
0x18004187b  lea     rdx, [rdi+40h]; pbInput
0x18004187f  xor     r9d, r9d; dwFlags
0x180041882  mov     r8d, r13d; cbInput
0x180041885  call    cs:__imp_BCryptHashData
0x18004188b  mov     ebx, eax
0x18004188d  test    eax, eax
0x18004188f  jns     short loc_1800418BC
0x180041891  mov     rcx, cs:WPP_GLOBAL_Control
0x180041898  lea     rax, WPP_GLOBAL_Control
0x18004189f  cmp     rcx, rax
0x1800418a2  jz      loc_180041B2F
0x1800418a8  test    dword ptr [rcx+1Ch], 4000h
0x1800418af  jz      loc_180041B2F
0x1800418b5  mov     edx, 23h ; '#'
0x1800418ba  jmp     short loc_18004185F
0x1800418bc  mov     rcx, [rbp+57h+phHash]; hHash
0x1800418c0  lea     rdx, [rbp+57h+pbOutput]; pbOutput
0x1800418c4  xor     r9d, r9d; dwFlags
0x1800418c7  mov     r8d, r13d; cbOutput
0x1800418ca  call    cs:__imp_BCryptFinishHash
0x1800418d0  mov     ebx, eax
0x1800418d2  test    eax, eax
0x1800418d4  jns     short loc_180041904
0x1800418d6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800418dd  lea     rax, WPP_GLOBAL_Control
0x1800418e4  cmp     rcx, rax
0x1800418e7  jz      loc_180041B2F
0x1800418ed  test    dword ptr [rcx+1Ch], 4000h
0x1800418f4  jz      loc_180041B2F
0x1800418fa  mov     edx, 24h ; '$'
0x1800418ff  jmp     loc_18004185F
0x180041904  mov     rcx, rdi
0x180041907  jmp     short loc_180041915
0x180041909  movaps  xmm0, cs:?NlpCacheEncryptionKey@@3PADA; char near * NlpCacheEncryptionKey
0x180041910  movdqu  xmmword ptr [rbp+57h+pbOutput], xmm0
0x180041915  lea     rsi, [rdi+60h]
0x180041919  mov     eax, edi
0x18004191b  sub     eax, esi
0x18004191d  add     r14d, eax
0x180041920  cmp     [rdi+32h], r12w
0x180041925  jnz     loc_180041AE0
0x18004192b  xor     r9d, r9d; cbKeyObject
0x18004192e  mov     [rsp+0D0h+dwFlags], r12d; dwFlags
0x180041933  lea     rax, [rbp+57h+pbOutput]
0x180041937  mov     [rsp+0D0h+cbSecret], r13d; cbSecret
0x18004193c  xor     r8d, r8d; pbKeyObject
0x18004193f  mov     [rsp+0D0h+pbSecret], rax; pbSecret
0x180041944  lea     rdx, [rbp+57h+phKey]; phKey
0x180041948  lea     ecx, [r9+71h]; hAlgorithm
0x18004194c  call    cs:__imp_BCryptGenerateSymmetricKey
0x180041952  mov     ebx, eax
0x180041954  test    eax, eax
0x180041956  jns     short loc_180041986
0x180041958  mov     rcx, cs:WPP_GLOBAL_Control
0x18004195f  lea     rax, WPP_GLOBAL_Control
0x180041966  cmp     rcx, rax
0x180041969  jz      loc_180041B2F
0x18004196f  test    dword ptr [rcx+1Ch], 4000h
0x180041976  jz      loc_180041B2F
0x18004197c  mov     edx, 25h ; '%'
0x180041981  jmp     loc_18004185F
0x180041986  mov     rcx, [rbp+57h+phKey]; hKey
0x18004198a  lea     rax, [rbp+57h+var_70]
0x18004198e  mov     [rsp+0D0h+var_88], r12d; dwFlags
0x180041993  xor     r9d, r9d; pPaddingInfo
0x180041996  mov     [rsp+0D0h+pcbResult], rax; pcbResult
0x18004199b  mov     r8d, r14d; cbInput
0x18004199e  mov     [rsp+0D0h+cbOutput], r14d; cbOutput
0x1800419a3  mov     rdx, rsi; pbInput
0x1800419a6  mov     qword ptr [rsp+0D0h+dwFlags], rsi; pbOutput
0x1800419ab  mov     [rsp+0D0h+cbSecret], r12d; cbIV
0x1800419b0  mov     [rsp+0D0h+pbSecret], r12; pbIV
0x1800419b5  call    cs:__imp_BCryptEncrypt
0x1800419bb  mov     ebx, eax
0x1800419bd  test    eax, eax
0x1800419bf  jns     short loc_1800419EF
0x1800419c1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800419c8  lea     rax, WPP_GLOBAL_Control
0x1800419cf  cmp     rcx, rax
0x1800419d2  jz      loc_180041B2F
0x1800419d8  test    dword ptr [rcx+1Ch], 4000h
0x1800419df  jz      loc_180041B2F
0x1800419e5  mov     edx, 26h ; '&'
0x1800419ea  jmp     loc_18004185F
0x1800419ef  mov     rcx, [rbp+57h+phKey]; hKey
0x1800419f3  call    cs:__imp_BCryptDestroyKey
0x1800419f9  lea     rax, [rbp+57h+pbOutput]
0x1800419fd  mov     [rsp+0D0h+dwFlags], r12d; dwFlags
0x180041a02  mov     [rsp+0D0h+cbSecret], r13d; cbSecret
0x180041a07  lea     rdx, [rbp+57h+phHash]; phHash
0x180041a0b  xor     r9d, r9d; cbHashObject
0x180041a0e  mov     [rsp+0D0h+pbSecret], rax; pbSecret
0x180041a13  xor     r8d, r8d; pbHashObject
0x180041a16  mov     [rbp+57h+phKey], r12
0x180041a1a  mov     ecx, 91h; hAlgorithm
0x180041a1f  call    cs:__imp_BCryptCreateHash
0x180041a25  mov     ebx, eax
0x180041a27  test    eax, eax
0x180041a29  jns     short loc_180041A59
0x180041a2b  mov     rcx, cs:WPP_GLOBAL_Control
0x180041a32  lea     rax, WPP_GLOBAL_Control
0x180041a39  cmp     rcx, rax
0x180041a3c  jz      loc_180041B2F
0x180041a42  test    dword ptr [rcx+1Ch], 4000h
0x180041a49  jz      loc_180041B2F
0x180041a4f  mov     edx, 27h ; '''
0x180041a54  jmp     loc_18004185F
0x180041a59  mov     rcx, [rbp+57h+phHash]; hHash
0x180041a5d  xor     r9d, r9d; dwFlags
0x180041a60  mov     r8d, r14d; cbInput
0x180041a63  mov     rdx, rsi; pbInput
0x180041a66  call    cs:__imp_BCryptHashData
0x180041a6c  mov     ebx, eax
0x180041a6e  test    eax, eax
0x180041a70  jns     short loc_180041AA0
0x180041a72  mov     rcx, cs:WPP_GLOBAL_Control
0x180041a79  lea     rax, WPP_GLOBAL_Control
0x180041a80  cmp     rcx, rax
0x180041a83  jz      loc_180041B2F
0x180041a89  test    dword ptr [rcx+1Ch], 4000h
0x180041a90  jz      loc_180041B2F
0x180041a96  mov     edx, 28h ; '('
0x180041a9b  jmp     loc_18004185F
0x180041aa0  mov     rcx, [rbp+57h+phHash]; hHash
0x180041aa4  lea     rdx, [rbp+57h+Buf1]; pbOutput
0x180041aa8  xor     r9d, r9d; dwFlags
0x180041aab  mov     r8d, r13d; cbOutput
0x180041aae  call    cs:__imp_BCryptFinishHash
0x180041ab4  mov     ebx, eax
0x180041ab6  test    eax, eax
0x180041ab8  jns     short loc_180041B2F
0x180041aba  mov     rcx, cs:WPP_GLOBAL_Control
0x180041ac1  lea     rax, WPP_GLOBAL_Control
0x180041ac8  cmp     rcx, rax
0x180041acb  jz      short loc_180041B2F
0x180041acd  test    dword ptr [rcx+1Ch], 4000h
0x180041ad4  jz      short loc_180041B2F
0x180041ad6  mov     edx, 29h ; ')'
0x180041adb  jmp     loc_18004185F
0x180041ae0  movups  xmm0, xmmword ptr [rcx+r15]
0x180041ae5  lea     rax, [rbp+57h+var_48]
0x180041ae9  mov     r9, rsi
0x180041aec  mov     r8d, r14d
0x180041aef  mov     [rsp+0D0h+pbSecret], rax
0x180041af4  lea     rdx, [rbp+57h+pbOutput]
0x180041af8  mov     ecx, r13d
0x180041afb  movdqu  [rbp+57h+var_48], xmm0
0x180041b00  call    cs:__imp_aesCTSDecryptMsg
0x180041b06  mov     ebx, eax
0x180041b08  test    eax, eax
0x180041b0a  js      short loc_180041B2F
0x180041b0c  lea     rax, [rbp+57h+Buf1]
0x180041b10  mov     [rsp+0D0h+cbSecret], r13d
0x180041b15  mov     r9d, r14d
0x180041b18  mov     [rsp+0D0h+pbSecret], rax
0x180041b1d  mov     r8, rsi
0x180041b20  lea     rcx, [rbp+57h+pbOutput]
0x180041b24  mov     edx, r13d
0x180041b27  call    cs:__imp_HMACwithSHA
0x180041b2d  mov     ebx, eax
0x180041b2f  mov     rcx, r13
0x180041b32  lea     rax, [rbp+57h+pbOutput]
0x180041b36  mov     [rax], r12b
0x180041b39  inc     rax
0x180041b3c  sub     rcx, 1
0x180041b40  jnz     short loc_180041B36
0x180041b42  mov     rcx, [rbp+57h+phKey]; hKey
0x180041b46  test    rcx, rcx
0x180041b49  jz      short loc_180041B51
0x180041b4b  call    cs:__imp_BCryptDestroyKey
0x180041b51  mov     rcx, [rbp+57h+phHash]; hHash
0x180041b55  test    rcx, rcx
0x180041b58  jz      short loc_180041B60
0x180041b5a  call    cs:__imp_BCryptDestroyHash
0x180041b60  test    ebx, ebx
0x180041b62  jns     short loc_180041B68
0x180041b64  mov     eax, ebx
0x180041b66  jmp     short loc_180041B88
0x180041b68  lea     rdx, [rdi+50h]; Buf2
0x180041b6c  mov     r8, r13; Size
0x180041b6f  lea     rcx, [rbp+57h+Buf1]; Buf1
0x180041b73  call    memcmp_0
0x180041b78  neg     eax
0x180041b7a  sbb     eax, eax
0x180041b7c  and     eax, 0C000006Dh
0x180041b81  jmp     short loc_180041B88
0x180041b83  mov     eax, 0C000006Dh
0x180041b88  mov     rcx, [rbp+57h+var_38]
0x180041b8c  xor     rcx, rsp; StackCookie
0x180041b8f  call    __security_check_cookie
0x180041b94  mov     rbx, [rsp+0D0h+arg_10]
0x180041b9c  add     rsp, 0A0h
0x180041ba3  pop     r15
0x180041ba5  pop     r14
0x180041ba7  pop     r13
0x180041ba9  pop     r12
0x180041bab  pop     rdi
0x180041bac  pop     rsi
0x180041bad  pop     rbp
0x180041bae  retn
```
