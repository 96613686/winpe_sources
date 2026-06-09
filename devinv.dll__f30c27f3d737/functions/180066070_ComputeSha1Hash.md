# ComputeSha1Hash

- ea: `0x180066070`
- end: `0x18006634c`
- name: `ComputeSha1Hash`
- size: `732`
- prototype: `__int64 __fastcall(BYTE *pbData, DWORD dwDataLen, BYTE *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800640b4`

## callees

- `0x180065d34`
- `0x180065d5c`
- `0x180066070`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800660d5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006614a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006619e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180066201`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800662a6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800660d5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006614a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006619e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180066201`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800662a6`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptAcquireContextW` at `0x1800660cb`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptAcquireContextW` at `0x1800660cb`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptReleaseContext` at `0x180066337`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptReleaseContext` at `0x180066337`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDestroyHash` at `0x18006631e`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDestroyHash` at `0x18006631e`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptCreateHash` at `0x180066140`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptCreateHash` at `0x180066140`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptHashData` at `0x180066194`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptHashData` at `0x180066194`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGetHashParam` at `0x1800661f7`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGetHashParam` at `0x18006629c`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGetHashParam` at `0x1800661f7`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGetHashParam` at `0x18006629c`

## pseudocode

```c
__int64 __fastcall ComputeSha1Hash(BYTE *pbData, DWORD dwDataLen, BYTE *a3)
{
  signed int v6; // eax
  unsigned int v7; // ebx
  _QWORD *v8; // rcx
  __int64 v9; // rdx
  signed int v10; // eax
  signed int v11; // eax
  signed int v12; // eax
  signed int LastError; // eax
  HCRYPTPROV phProv[2]; // [rsp+30h] [rbp-10h] BYREF
  DWORD pdwDataLen; // [rsp+60h] [rbp+20h] BYREF
  HCRYPTHASH phHash; // [rsp+78h] [rbp+38h] BYREF

  phProv[0] = 0;
  phHash = 0;
  pdwDataLen = 0;
  if ( pbData && a3 )
  {
    if ( CryptAcquireContextW(phProv, 0, L"Microsoft Base Cryptographic Provider v1.0", 1u, 0xF0000000) )
    {
      if ( CryptCreateHash(phProv[0], 0x8004u, 0, 0, &phHash) )
      {
        if ( CryptHashData(phHash, pbData, dwDataLen, 0) )
        {
          if ( CryptGetHashParam(phHash, 2u, 0, &pdwDataLen, 0) )
          {
            if ( pdwDataLen <= 0x14 )
            {
              if ( CryptGetHashParam(phHash, 2u, a3, &pdwDataLen, 0) )
              {
                v7 = 0;
              }
              else
              {
                LastError = GetLastError();
                v7 = LastError;
                if ( LastError > 0 )
                  v7 = (unsigned __int16)LastError | 0x80070000;
                v8 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                {
                  v9 = 16;
                  goto LABEL_9;
                }
              }
            }
            else
            {
              v7 = -2147418113;
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_18864a23d0283f6b832131a6e90b37b9_Traceguids);
              }
            }
          }
          else
          {
            v12 = GetLastError();
            v7 = v12;
            if ( v12 > 0 )
              v7 = (unsigned __int16)v12 | 0x80070000;
            v8 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              v9 = 14;
              goto LABEL_9;
            }
          }
        }
        else
        {
          v11 = GetLastError();
          v7 = v11;
          if ( v11 > 0 )
            v7 = (unsigned __int16)v11 | 0x80070000;
          v8 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v9 = 13;
            goto LABEL_9;
          }
        }
      }
      else
      {
        v10 = GetLastError();
        v7 = v10;
        if ( v10 > 0 )
          v7 = (unsigned __int16)v10 | 0x80070000;
        v8 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v9 = 12;
          goto LABEL_9;
        }
      }
    }
    else
    {
      v6 = GetLastError();
      v7 = v6;
      if ( v6 > 0 )
        v7 = (unsigned __int16)v6 | 0x80070000;
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v9 = 11;
LABEL_9:
        WPP_SF_D(v8[2], v9, WPP_18864a23d0283f6b832131a6e90b37b9_Traceguids, v7);
      }
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_18864a23d0283f6b832131a6e90b37b9_Traceguids);
    v7 = -2147024809;
  }
  if ( phHash )
  {
    CryptDestroyHash(phHash);
    phHash = 0;
  }
  if ( phProv[0] )
    CryptReleaseContext(phProv[0], 0);
  return v7;
}

```

## disassembly

```asm
0x180066070  mov     [rsp-18h+arg_8], rbx
0x180066075  push    rbp
0x180066076  push    rsi
0x180066077  push    rdi
0x180066078  mov     rbp, rsp
0x18006607b  sub     rsp, 40h
0x18006607f  mov     [rbp+phProv], 0
0x180066087  mov     rbx, r8
0x18006608a  mov     [rbp+phHash], 0
0x180066092  mov     esi, edx
0x180066094  mov     [rbp+pdwDataLen], 0
0x18006609b  mov     rdi, rcx
0x18006609e  test    rcx, rcx
0x1800660a1  jz      loc_1800662E2
0x1800660a7  test    rbx, rbx
0x1800660aa  jz      loc_1800662E2
0x1800660b0  mov     r9d, 1; dwProvType
0x1800660b6  mov     [rsp+40h+dwFlags], 0F0000000h; dwFlags
0x1800660be  lea     r8, szProvider; "Microsoft Base Cryptographic Provider v"...
0x1800660c5  xor     edx, edx; szContainer
0x1800660c7  lea     rcx, [rbp+phProv]; phProv
0x1800660cb  call    cs:__imp_CryptAcquireContextW
0x1800660d1  test    eax, eax
0x1800660d3  jnz     short loc_180066128
0x1800660d5  call    cs:__imp_GetLastError
0x1800660db  mov     ebx, eax
0x1800660dd  test    eax, eax
0x1800660df  jle     short loc_1800660EA
0x1800660e1  movzx   ebx, ax
0x1800660e4  or      ebx, 80070000h
0x1800660ea  mov     rcx, cs:WPP_GLOBAL_Control
0x1800660f1  lea     rax, WPP_GLOBAL_Control
0x1800660f8  cmp     rcx, rax
0x1800660fb  jz      loc_180066315
0x180066101  test    byte ptr [rcx+1Ch], 1
0x180066105  jz      loc_180066315
0x18006610b  mov     edx, 0Bh
0x180066110  mov     rcx, [rcx+10h]
0x180066114  lea     r8, WPP_18864a23d0283f6b832131a6e90b37b9_Traceguids
0x18006611b  mov     r9d, ebx
0x18006611e  call    WPP_SF_D
0x180066123  jmp     loc_180066315
0x180066128  mov     rcx, [rbp+phProv]; hProv
0x18006612c  lea     rax, [rbp+phHash]
0x180066130  xor     r9d, r9d; dwFlags
0x180066133  mov     qword ptr [rsp+40h+dwFlags], rax; phHash
0x180066138  xor     r8d, r8d; hKey
0x18006613b  mov     edx, 8004h; Algid
0x180066140  call    cs:__imp_CryptCreateHash
0x180066146  test    eax, eax
0x180066148  jnz     short loc_180066187
0x18006614a  call    cs:__imp_GetLastError
0x180066150  mov     ebx, eax
0x180066152  test    eax, eax
0x180066154  jle     short loc_18006615F
0x180066156  movzx   ebx, ax
0x180066159  or      ebx, 80070000h
0x18006615f  mov     rcx, cs:WPP_GLOBAL_Control
0x180066166  lea     rax, WPP_GLOBAL_Control
0x18006616d  cmp     rcx, rax
0x180066170  jz      loc_180066315
0x180066176  test    byte ptr [rcx+1Ch], 1
0x18006617a  jz      loc_180066315
0x180066180  mov     edx, 0Ch
0x180066185  jmp     short loc_180066110
0x180066187  mov     rcx, [rbp+phHash]; hHash
0x18006618b  xor     r9d, r9d; dwFlags
0x18006618e  mov     r8d, esi; dwDataLen
0x180066191  mov     rdx, rdi; pbData
0x180066194  call    cs:__imp_CryptHashData
0x18006619a  test    eax, eax
0x18006619c  jnz     short loc_1800661DE
0x18006619e  call    cs:__imp_GetLastError
0x1800661a4  mov     ebx, eax
0x1800661a6  test    eax, eax
0x1800661a8  jle     short loc_1800661B3
0x1800661aa  movzx   ebx, ax
0x1800661ad  or      ebx, 80070000h
0x1800661b3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800661ba  lea     rax, WPP_GLOBAL_Control
0x1800661c1  cmp     rcx, rax
0x1800661c4  jz      loc_180066315
0x1800661ca  test    byte ptr [rcx+1Ch], 1
0x1800661ce  jz      loc_180066315
0x1800661d4  mov     edx, 0Dh
0x1800661d9  jmp     loc_180066110
0x1800661de  mov     rcx, [rbp+phHash]; hHash
0x1800661e2  lea     r9, [rbp+pdwDataLen]; pdwDataLen
0x1800661e6  xor     r8d, r8d; pbData
0x1800661e9  mov     [rsp+40h+dwFlags], 0; dwFlags
0x1800661f1  lea     edi, [r8+2]
0x1800661f5  mov     edx, edi; dwParam
0x1800661f7  call    cs:__imp_CryptGetHashParam
0x1800661fd  test    eax, eax
0x1800661ff  jnz     short loc_180066241
0x180066201  call    cs:__imp_GetLastError
0x180066207  mov     ebx, eax
0x180066209  test    eax, eax
0x18006620b  jle     short loc_180066216
0x18006620d  movzx   ebx, ax
0x180066210  or      ebx, 80070000h
0x180066216  mov     rcx, cs:WPP_GLOBAL_Control
0x18006621d  lea     rax, WPP_GLOBAL_Control
0x180066224  cmp     rcx, rax
0x180066227  jz      loc_180066315
0x18006622d  test    byte ptr [rcx+1Ch], 1
0x180066231  jz      loc_180066315
0x180066237  mov     edx, 0Eh
0x18006623c  jmp     loc_180066110
0x180066241  cmp     [rbp+pdwDataLen], 14h
0x180066245  jbe     short loc_180066287
0x180066247  mov     ebx, 8000FFFFh
0x18006624c  mov     rcx, cs:WPP_GLOBAL_Control
0x180066253  lea     rax, WPP_GLOBAL_Control
0x18006625a  cmp     rcx, rax
0x18006625d  jz      loc_180066315
0x180066263  test    byte ptr [rcx+1Ch], 1
0x180066267  jz      loc_180066315
0x18006626d  mov     rcx, [rcx+10h]
0x180066271  lea     r8, WPP_18864a23d0283f6b832131a6e90b37b9_Traceguids
0x180066278  mov     edx, 0Fh
0x18006627d  call    WPP_SF_
0x180066282  jmp     loc_180066315
0x180066287  mov     rcx, [rbp+phHash]; hHash
0x18006628b  lea     r9, [rbp+pdwDataLen]; pdwDataLen
0x18006628f  mov     r8, rbx; pbData
0x180066292  mov     [rsp+40h+dwFlags], 0; dwFlags
0x18006629a  mov     edx, edi; dwParam
0x18006629c  call    cs:__imp_CryptGetHashParam
0x1800662a2  test    eax, eax
0x1800662a4  jnz     short loc_1800662DE
0x1800662a6  call    cs:__imp_GetLastError
0x1800662ac  mov     ebx, eax
0x1800662ae  test    eax, eax
0x1800662b0  jle     short loc_1800662BB
0x1800662b2  movzx   ebx, ax
0x1800662b5  or      ebx, 80070000h
0x1800662bb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800662c2  lea     rax, WPP_GLOBAL_Control
0x1800662c9  cmp     rcx, rax
0x1800662cc  jz      short loc_180066315
0x1800662ce  test    byte ptr [rcx+1Ch], 1
0x1800662d2  jz      short loc_180066315
0x1800662d4  mov     edx, 10h
0x1800662d9  jmp     loc_180066110
0x1800662de  xor     ebx, ebx
0x1800662e0  jmp     short loc_180066315
0x1800662e2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800662e9  lea     rax, WPP_GLOBAL_Control
0x1800662f0  cmp     rcx, rax
0x1800662f3  jz      short loc_180066310
0x1800662f5  test    byte ptr [rcx+1Ch], 1
0x1800662f9  jz      short loc_180066310
0x1800662fb  mov     rcx, [rcx+10h]
0x1800662ff  lea     r8, WPP_18864a23d0283f6b832131a6e90b37b9_Traceguids
0x180066306  mov     edx, 0Ah
0x18006630b  call    WPP_SF_
0x180066310  mov     ebx, 80070057h
0x180066315  mov     rcx, [rbp+phHash]; hHash
0x180066319  test    rcx, rcx
0x18006631c  jz      short loc_18006632C
0x18006631e  call    cs:__imp_CryptDestroyHash
0x180066324  mov     [rbp+phHash], 0
0x18006632c  mov     rcx, [rbp+phProv]; hProv
0x180066330  test    rcx, rcx
0x180066333  jz      short loc_18006633D
0x180066335  xor     edx, edx; dwFlags
0x180066337  call    cs:__imp_CryptReleaseContext
0x18006633d  mov     eax, ebx
0x18006633f  mov     rbx, [rsp+40h+arg_8]
0x180066344  add     rsp, 40h
0x180066348  pop     rdi
0x180066349  pop     rsi
0x18006634a  pop     rbp
0x18006634b  retn
```
