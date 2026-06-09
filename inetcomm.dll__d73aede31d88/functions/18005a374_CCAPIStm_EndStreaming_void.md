# CCAPIStm::EndStreaming(void)

- ea: `0x18005a374`
- end: `0x18005a5e9`
- name: `?EndStreaming@CCAPIStm@@QEAAJXZ`
- size: `629`
- prototype: `__int64 __fastcall(CCAPIStm *__hidden this)`
- caller_count: `6`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x18003a2fc`
- `0x18003a588`
- `0x18003a690`
- `0x18003bf10`
- `0x18003c1e8`
- `0x18005a374`

## callees

- `0x180023b48`
- `0x1800247c8`
- `0x18005a374`
- `0x18005be40`
- `0x18005d1d8`
- `0x1800cd010`

## import_xrefs

- `CRYPT32!CryptMsgGetParam` at `0x18005a4ae`
- `CRYPT32!CryptMsgGetParam` at `0x18005a510`
- `CRYPT32!CryptMsgGetParam` at `0x18005a4ae`
- `CRYPT32!CryptMsgGetParam` at `0x18005a510`
- `CRYPT32!CryptMsgUpdate` at `0x18005a3e4`
- `CRYPT32!CryptMsgUpdate` at `0x18005a425`
- `CRYPT32!CryptMsgUpdate` at `0x18005a3e4`
- `CRYPT32!CryptMsgUpdate` at `0x18005a425`
- `CRYPT32!CryptEncodeObjectEx` at `0x18005a557`
- `CRYPT32!CryptEncodeObjectEx` at `0x18005a557`

## pseudocode

```c
__int64 __fastcall CCAPIStm::EndStreaming(CCAPIStm *this)
{
  void *v1; // rsi
  int v3; // ecx
  int LastError; // ebx
  __int64 v5; // rax
  int v6; // r14d
  bool v7; // zf
  void *v8; // rcx
  DWORD v9; // edx
  int v10; // eax
  int v11; // eax
  CCAPIStm *v12; // rcx
  DWORD pcbData; // [rsp+70h] [rbp+30h] BYREF
  void *pvData; // [rsp+78h] [rbp+38h] BYREF
  __int64 pvEncoded; // [rsp+80h] [rbp+40h] BYREF

  v1 = 0;
  v3 = *((_DWORD *)this + 3);
  LastError = 0;
  pvData = 0;
  if ( (unsigned int)(v3 - 6) <= 1 )
    return (unsigned int)LastError;
  v5 = *((_QWORD *)this + 12);
  if ( (*((_DWORD *)this + 16) & 0x10000) != 0 && v3 == 4 )
  {
    *((_DWORD *)this + 3) = 5;
    *((_DWORD *)this + 4) = 34;
    *(_DWORD *)(v5 + 12) = 1;
    if ( !CryptMsgUpdate(*((HCRYPTMSG *)this + 3), *((const BYTE **)this + 18), *((_DWORD *)this + 38), 1) )
    {
      LastError = HrGetLastError();
      if ( LastError == -2147024896 )
        LastError = -2147024891;
    }
    *((_DWORD *)this + 38) = 0;
    goto LABEL_37;
  }
  v6 = *(_DWORD *)(v5 + 12);
  if ( !CryptMsgUpdate(*((HCRYPTMSG *)this + 3), *((const BYTE **)this + 18), *((_DWORD *)this + 38), 1) )
  {
    LastError = HrGetLastError();
    if ( LastError == -2147024896 )
      return (unsigned int)-2147024891;
    goto LABEL_37;
  }
  v7 = (*((_BYTE *)this + 64) & 2) == 0;
  *((_DWORD *)this + 38) = 0;
  if ( !v7 )
    *((_DWORD *)this + 3) = 5;
  if ( (*((_DWORD *)this + 16) & 0x10000) == 0 )
    goto LABEL_29;
  if ( (v6 & 1) == 0 )
  {
    v7 = (v6 & 2) == 0;
    if ( (v6 & 2) == 0 )
    {
LABEL_30:
      if ( !v7 && (*((_DWORD *)this + 16) & 0x10000) != 0 )
        SMimeCapsFromHMsg(*((HCRYPTMSG *)this + 3));
      v12 = (CCAPIStm *)*((_QWORD *)this + 5);
      if ( !v12 )
        goto LABEL_35;
      v11 = CCAPIStm::EndStreaming(v12);
      goto LABEL_34;
    }
    v8 = (void *)*((_QWORD *)this + 3);
    pcbData = 0;
    pvEncoded = 0;
    if ( CryptMsgGetParam(v8, 0x25u, 0, 0, &pcbData) )
    {
      v9 = pcbData;
    }
    else
    {
      LastError = HrGetLastError();
      if ( LastError != -2146889713 )
        goto LABEL_37;
      v9 = 0;
      pcbData = 0;
    }
    LastError = 0;
    if ( v9 )
    {
      v10 = MemAlloc(&pvData, v9);
      v1 = pvData;
      if ( !v10 )
      {
        LastError = -2147024882;
        goto LABEL_35;
      }
      if ( !CryptMsgGetParam(*((HCRYPTMSG *)this + 3), 0x25u, 0, pvData, &pcbData)
        || !CryptEncodeObjectEx(1u, "1.3.6.1.4.1.311.16.1.1", v1, 0x8000u, &CryptEncodeAlloc, &pvEncoded, &pcbData) )
      {
        v11 = HrGetLastError();
LABEL_34:
        LastError = v11;
LABEL_35:
        if ( v1 )
          ((void (__fastcall *)(LPMALLOC, void *))g_pMalloc->lpVtbl->Free)(g_pMalloc, v1);
        goto LABEL_37;
      }
      *(_DWORD *)(*((_QWORD *)this + 12) + 80LL) = pcbData;
      *(_QWORD *)(*((_QWORD *)this + 12) + 88LL) = pvEncoded;
    }
    goto LABEL_29;
  }
  LastError = CCAPIStm::VerifySignedMessage(this);
  if ( LastError >= 0 )
  {
LABEL_29:
    v7 = (v6 & 2) == 0;
    goto LABEL_30;
  }
LABEL_37:
  if ( LastError == 5 )
    return (unsigned int)-2147024891;
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x18005a374  mov     [rsp-28h+arg_18], rbx
0x18005a379  push    rbp
0x18005a37a  push    rsi
0x18005a37b  push    rdi
0x18005a37c  push    r13
0x18005a37e  push    r14
0x18005a380  mov     rbp, rsp
0x18005a383  sub     rsp, 40h
0x18005a387  xor     esi, esi
0x18005a389  mov     rdi, rcx
0x18005a38c  mov     ecx, [rcx+0Ch]
0x18005a38f  xor     ebx, ebx
0x18005a391  mov     [rbp+pvData], rsi
0x18005a395  lea     eax, [rcx-6]
0x18005a398  cmp     eax, 1
0x18005a39b  jbe     loc_18005A5D3
0x18005a3a1  test    dword ptr [rdi+40h], 10000h
0x18005a3a8  mov     r13d, 80070005h
0x18005a3ae  mov     rax, [rdi+60h]
0x18005a3b2  jz      short loc_18005A409
0x18005a3b4  cmp     ecx, 4
0x18005a3b7  jnz     short loc_18005A409
0x18005a3b9  mov     dword ptr [rdi+0Ch], 5
0x18005a3c0  lea     r9d, [rbx+1]; fFinal
0x18005a3c4  mov     dword ptr [rdi+10h], 22h ; '"'
0x18005a3cb  mov     dword ptr [rax+0Ch], 1
0x18005a3d2  mov     r8d, [rdi+98h]; cbData
0x18005a3d9  mov     rdx, [rdi+90h]; pbData
0x18005a3e0  mov     rcx, [rdi+18h]; hCryptMsg
0x18005a3e4  call    cs:__imp_CryptMsgUpdate
0x18005a3ea  test    eax, eax
0x18005a3ec  jnz     short loc_18005A3FE
0x18005a3ee  call    ?HrGetLastError@@YAJXZ; HrGetLastError(void)
0x18005a3f3  cmp     eax, 80070000h
0x18005a3f8  mov     ebx, eax
0x18005a3fa  cmovz   ebx, r13d
0x18005a3fe  mov     [rdi+98h], esi
0x18005a404  jmp     loc_18005A5CC
0x18005a409  mov     r8d, [rdi+98h]; cbData
0x18005a410  mov     r9d, 1; fFinal
0x18005a416  mov     rdx, [rdi+90h]; pbData
0x18005a41d  mov     rcx, [rdi+18h]; hCryptMsg
0x18005a421  mov     r14d, [rax+0Ch]
0x18005a425  call    cs:__imp_CryptMsgUpdate
0x18005a42b  test    eax, eax
0x18005a42d  jnz     short loc_18005A449
0x18005a42f  call    ?HrGetLastError@@YAJXZ; HrGetLastError(void)
0x18005a434  mov     ebx, eax
0x18005a436  cmp     eax, 80070000h
0x18005a43b  jnz     loc_18005A5CC
0x18005a441  mov     ebx, r13d
0x18005a444  jmp     loc_18005A5D3
0x18005a449  test    byte ptr [rdi+40h], 2
0x18005a44d  mov     [rdi+98h], ebx
0x18005a453  jz      short loc_18005A45C
0x18005a455  mov     dword ptr [rdi+0Ch], 5
0x18005a45c  test    dword ptr [rdi+40h], 10000h
0x18005a463  jz      loc_18005A577
0x18005a469  test    r14b, 1
0x18005a46d  jz      short loc_18005A486
0x18005a46f  mov     rcx, rdi; this
0x18005a472  call    ?VerifySignedMessage@CCAPIStm@@AEAAJXZ; CCAPIStm::VerifySignedMessage(void)
0x18005a477  mov     ebx, eax
0x18005a479  test    eax, eax
0x18005a47b  js      loc_18005A5CC
0x18005a481  jmp     loc_18005A577
0x18005a486  test    r14b, 2
0x18005a48a  jz      loc_18005A57B
0x18005a490  mov     rcx, [rdi+18h]; hCryptMsg
0x18005a494  lea     rax, [rbp+arg_0]
0x18005a498  xor     r9d, r9d; pvData
0x18005a49b  mov     [rbp+arg_0], ebx
0x18005a49e  xor     r8d, r8d; dwIndex
0x18005a4a1  mov     [rbp+arg_10], rbx
0x18005a4a5  mov     [rsp+40h+pcbData], rax; pcbData
0x18005a4aa  lea     edx, [r9+25h]; dwParamType
0x18005a4ae  call    cs:__imp_CryptMsgGetParam
0x18005a4b4  test    eax, eax
0x18005a4b6  jnz     short loc_18005A4D1
0x18005a4b8  call    ?HrGetLastError@@YAJXZ; HrGetLastError(void)
0x18005a4bd  mov     ebx, eax
0x18005a4bf  cmp     eax, 8009100Fh
0x18005a4c4  jnz     loc_18005A5CC
0x18005a4ca  xor     edx, edx
0x18005a4cc  mov     [rbp+arg_0], edx
0x18005a4cf  jmp     short loc_18005A4D4
0x18005a4d1  mov     edx, [rbp+arg_0]; unsigned int
0x18005a4d4  xor     ebx, ebx
0x18005a4d6  test    edx, edx
0x18005a4d8  jz      loc_18005A577
0x18005a4de  lea     rcx, [rbp+pvData]; void **
0x18005a4e2  call    ?MemAlloc@@YAHPEAPEAXK@Z; MemAlloc(void * *,ulong)
0x18005a4e7  mov     rsi, [rbp+pvData]
0x18005a4eb  test    eax, eax
0x18005a4ed  jnz     short loc_18005A4F9
0x18005a4ef  mov     ebx, 8007000Eh
0x18005a4f4  jmp     loc_18005A5B1
0x18005a4f9  mov     rcx, [rdi+18h]; hCryptMsg
0x18005a4fd  lea     rax, [rbp+arg_0]
0x18005a501  xor     r8d, r8d; dwIndex
0x18005a504  mov     [rsp+40h+pcbData], rax; pcbData
0x18005a509  mov     r9, rsi; pvData
0x18005a50c  lea     edx, [r8+25h]; dwParamType
0x18005a510  call    cs:__imp_CryptMsgGetParam
0x18005a516  test    eax, eax
0x18005a518  jnz     short loc_18005A524
0x18005a51a  call    ?HrGetLastError@@YAJXZ; HrGetLastError(void)
0x18005a51f  jmp     loc_18005A5AF
0x18005a524  lea     rax, [rbp+arg_0]
0x18005a528  mov     r9d, 8000h; dwFlags
0x18005a52e  mov     [rsp+40h+pcbEncoded], rax; pcbEncoded
0x18005a533  lea     rdx, szStructType; "1.3.6.1.4.1.311.16.1.1"
0x18005a53a  lea     rax, [rbp+arg_10]
0x18005a53e  mov     r8, rsi; pvStructInfo
0x18005a541  mov     [rsp+40h+pvEncoded], rax; pvEncoded
0x18005a546  mov     ecx, 1; dwCertEncodingType
0x18005a54b  lea     rax, ?CryptEncodeAlloc@@3U_CRYPT_ENCODE_PARA@@A; _CRYPT_ENCODE_PARA CryptEncodeAlloc
0x18005a552  mov     [rsp+40h+pcbData], rax; pEncodePara
0x18005a557  call    cs:__imp_CryptEncodeObjectEx
0x18005a55d  test    eax, eax
0x18005a55f  jz      short loc_18005A51A
0x18005a561  mov     rcx, [rdi+60h]
0x18005a565  mov     eax, [rbp+arg_0]
0x18005a568  mov     [rcx+50h], eax
0x18005a56b  mov     rcx, [rdi+60h]
0x18005a56f  mov     rax, [rbp+arg_10]
0x18005a573  mov     [rcx+58h], rax
0x18005a577  test    r14b, 2
0x18005a57b  setnz   cl
0x18005a57e  test    dword ptr [rdi+40h], 10000h
0x18005a585  setnz   al
0x18005a588  test    al, cl
0x18005a58a  jz      short loc_18005A5A1
0x18005a58c  mov     r9, [rdi+60h]
0x18005a590  mov     rcx, [rdi+18h]; hCryptMsg
0x18005a594  add     r9, 70h ; 'p'
0x18005a598  lea     r8, [r9+8]
0x18005a59c  call    _SMimeCapsFromHMsg
0x18005a5a1  mov     rcx, [rdi+28h]; this
0x18005a5a5  test    rcx, rcx
0x18005a5a8  jz      short loc_18005A5B1
0x18005a5aa  call    ?EndStreaming@CCAPIStm@@QEAAJXZ; CCAPIStm::EndStreaming(void)
0x18005a5af  mov     ebx, eax
0x18005a5b1  test    rsi, rsi
0x18005a5b4  jz      short loc_18005A5CC
0x18005a5b6  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x18005a5bd  mov     rdx, rsi
0x18005a5c0  mov     rax, [rcx]
0x18005a5c3  mov     rax, [rax+28h]
0x18005a5c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a5cc  cmp     ebx, 5
0x18005a5cf  cmovz   ebx, r13d
0x18005a5d3  mov     eax, ebx
0x18005a5d5  mov     rbx, [rsp+40h+arg_18]
0x18005a5dd  add     rsp, 40h
0x18005a5e1  pop     r14
0x18005a5e3  pop     r13
0x18005a5e5  pop     rdi
0x18005a5e6  pop     rsi
0x18005a5e7  pop     rbp
0x18005a5e8  retn
```
