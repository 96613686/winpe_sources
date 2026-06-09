# MsvpWriteCredKeyEventLog(_MSV1_0_PRIMARY_CREDENTIAL *,void *,_MSV1_0_CREDENTIAL_KEY_TYPE)

- ea: `0x180012974`
- end: `0x180012bcf`
- name: `?MsvpWriteCredKeyEventLog@@YAXPEAU_MSV1_0_PRIMARY_CREDENTIAL@@PEAXW4_MSV1_0_CREDENTIAL_KEY_TYPE@@@Z`
- size: `603`
- prototype: `void(struct _MSV1_0_PRIMARY_CREDENTIAL *, void *, enum _MSV1_0_CREDENTIAL_KEY_TYPE)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800127c0`

## callees

- `0x180012974`
- `0x180012bd8`
- `0x180012cb8`
- `0x18002fb50`
- `0x18003aaac`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800129fd`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800129fd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180012b6c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180012b6c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180012ae9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180012ae9`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x180012a61`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x180012a61`
- `bcrypt!BCryptKeyDerivation` at `0x180012a90`
- `bcrypt!BCryptKeyDerivation` at `0x180012a90`
- `bcrypt!BCryptDestroyKey` at `0x180012b5e`
- `bcrypt!BCryptDestroyKey` at `0x180012b5e`

## pseudocode

```c
void __fastcall MsvpWriteCredKeyEventLog(UCHAR *a1, void *a2, enum _MSV1_0_CREDENTIAL_KEY_TYPE a3)
{
  unsigned __int16 *v6; // rdi
  __int64 v7; // rax
  __int64 v8; // r13
  int v9; // ecx
  int v10; // edx
  const unsigned __int16 *v11; // r15
  const unsigned __int16 *v12; // r14
  __int64 v13; // rax
  __int64 v14; // rcx
  unsigned __int64 v15; // rbx
  int v16; // r9d
  _BYTE *v17; // rax
  int v18; // [rsp+40h] [rbp-69h] BYREF
  BCRYPT_KEY_HANDLE phKey; // [rsp+48h] [rbp-61h] BYREF
  _DWORD v20[2]; // [rsp+50h] [rbp-59h] BYREF
  _DWORD *v21; // [rsp+58h] [rbp-51h]
  _DWORD v22[2]; // [rsp+60h] [rbp-49h] BYREF
  const char *v23; // [rsp+68h] [rbp-41h]
  DWORD LengthSid; // [rsp+70h] [rbp-39h]
  int v25; // [rsp+74h] [rbp-35h]
  void *v26; // [rsp+78h] [rbp-31h]
  __int64 v27; // [rsp+80h] [rbp-29h]
  const wchar_t *v28; // [rsp+88h] [rbp-21h]
  _BYTE v29[16]; // [rsp+90h] [rbp-19h] BYREF
  _OWORD v30[2]; // [rsp+A0h] [rbp-9h] BYREF

  if ( a1[42] && a3 == LocalUserCredKey || a1[43] && a3 == DomainUserCredKey )
  {
    phKey = 0;
    v18 = 0;
    v23 = "DPAPICredKeyLogging";
    v22[0] = 20;
    memset(v30, 0, sizeof(v30));
    v6 = 0;
    v22[1] = 13;
    LengthSid = GetLengthSid(a2);
    v25 = 14;
    v27 = 14;
    v28 = L"SHA256";
    v21 = v22;
    v7 = 102;
    v26 = a2;
    if ( a3 != LocalUserCredKey )
      v7 = 50;
    v20[0] = 0;
    v20[1] = 3;
    v8 = 32;
    if ( BCryptGenerateSymmetricKey((BCRYPT_ALG_HANDLE)0x341, &phKey, 0, 0, &a1[v7], 0x14u, 0) < 0
      || (int)BCryptKeyDerivation(phKey, v20, v30, 32, &v18, 0) < 0 )
    {
      goto LABEL_22;
    }
    v10 = 0;
    v11 = L"(null)";
    v12 = L"(null)";
    if ( *((_QWORD *)a1 + 3) )
      v12 = (const unsigned __int16 *)*((_QWORD *)a1 + 3);
    if ( a3 == DomainUserCredKey )
    {
      if ( *((_QWORD *)a1 + 1) )
        v11 = (const unsigned __int16 *)*((_QWORD *)a1 + 1);
      v13 = -1;
      v14 = -1;
      do
        ++v14;
      while ( v12[v14] );
      do
        ++v13;
      while ( v11[v13] );
      v15 = v14 + v13 + 2;
      v6 = (unsigned __int16 *)LocalAlloc(0, 2 * v15);
      *v6 = 0;
      StringCchCatW(v6, v15, v11);
      StringCchCatW(v6, v15, L"\\");
      StringCchCatW(v6, v15, v12);
      if ( (Microsoft_Windows_Crypto_DPAPIEnableBits & 8) == 0 )
        goto LABEL_22;
      v16 = (int)v6;
    }
    else
    {
      if ( (Microsoft_Windows_Crypto_DPAPIEnableBits & 8) == 0 )
      {
LABEL_22:
        if ( phKey )
          BCryptDestroyKey(phKey);
        if ( v6 )
          LocalFree(v6);
        v17 = v30;
        do
        {
          *v17++ = 0;
          --v8;
        }
        while ( v8 );
        return;
      }
      v16 = (int)v12;
    }
    McTemplateU0b32zk_EtwEventWriteTransfer(v9, v10, (unsigned int)v30, v16, (__int64)a2);
    goto LABEL_22;
  }
  if ( (Microsoft_Windows_Crypto_DPAPIEnableBits & 8) != 0 )
    McGenEventWrite_EtwEventWriteTransfer(
      (_DWORD)a1,
      (unsigned int)ETW_LOG_DPAPI_CRED_KEY_NOT_CREATED,
      a3,
      1,
      (__int64)v29);
}

```

## disassembly

```asm
0x180012974  mov     [rsp-8+arg_10], rbx
0x180012979  push    rbp
0x18001297a  push    rsi
0x18001297b  push    rdi
0x18001297c  push    r12
0x18001297e  push    r13
0x180012980  push    r14
0x180012982  push    r15
0x180012984  lea     rbp, [rsp-27h]
0x180012989  sub     rsp, 0D0h
0x180012990  mov     rax, cs:__security_cookie
0x180012997  xor     rax, rsp
0x18001299a  mov     [rbp+57h+var_40], rax
0x18001299e  xor     r15d, r15d
0x1800129a1  mov     ebx, r8d
0x1800129a4  mov     r12, rdx
0x1800129a7  mov     rsi, rcx
0x1800129aa  cmp     [rcx+2Ah], r15b
0x1800129ae  jz      short loc_1800129B5
0x1800129b0  cmp     ebx, 3
0x1800129b3  jz      short loc_1800129C8
0x1800129b5  cmp     [rcx+2Bh], r15b
0x1800129b9  jz      loc_180012B84
0x1800129bf  cmp     ebx, 2
0x1800129c2  jnz     loc_180012B84
0x1800129c8  xorps   xmm0, xmm0
0x1800129cb  mov     [rbp+57h+phKey], r15
0x1800129cf  lea     rax, aDpapicredkeylo; "DPAPICredKeyLogging"
0x1800129d6  mov     [rbp+57h+var_C0], r15d
0x1800129da  mov     r14d, 14h
0x1800129e0  mov     [rbp+57h+var_98], rax
0x1800129e4  mov     rcx, r12; pSid
0x1800129e7  mov     [rbp+57h+var_A0], r14d
0x1800129eb  movups  [rbp+57h+var_60], xmm0
0x1800129ef  mov     rdi, r15
0x1800129f2  mov     [rbp+57h+var_9C], 0Dh
0x1800129f9  movups  [rbp+57h+var_50], xmm0
0x1800129fd  call    cs:__imp_GetLengthSid
0x180012a03  mov     [rsp+100h+dwFlags], r15d; dwFlags
0x180012a08  lea     rdx, [rbp+57h+phKey]; phKey
0x180012a0c  mov     [rbp+57h+var_90], eax
0x180012a0f  cmp     ebx, 3
0x180012a12  lea     eax, [r14-6]
0x180012a16  mov     [rsp+100h+cbSecret], r14d; cbSecret
0x180012a1b  mov     [rbp+57h+var_8C], eax
0x180012a1e  mov     [rbp+57h+var_80], rax
0x180012a22  lea     rax, aSha256; "SHA256"
0x180012a29  mov     [rbp+57h+var_78], rax
0x180012a2d  lea     rax, [rbp+57h+var_A0]
0x180012a31  mov     [rbp+57h+var_A8], rax
0x180012a35  lea     eax, [r14+52h]
0x180012a39  lea     ecx, [rax-34h]
0x180012a3c  mov     [rbp+57h+var_88], r12
0x180012a40  cmovnz  eax, ecx
0x180012a43  mov     [rbp+57h+var_B0], r15d
0x180012a47  add     rax, rsi
0x180012a4a  mov     [rbp+57h+var_AC], 3
0x180012a51  xor     r9d, r9d; cbKeyObject
0x180012a54  mov     [rsp+100h+pbSecret], rax; pbSecret
0x180012a59  xor     r8d, r8d; pbKeyObject
0x180012a5c  mov     ecx, 341h; hAlgorithm
0x180012a61  call    cs:__imp_BCryptGenerateSymmetricKey
0x180012a67  lea     r13d, [r14+0Ch]
0x180012a6b  test    eax, eax
0x180012a6d  js      loc_180012B55
0x180012a73  mov     rcx, [rbp+57h+phKey]
0x180012a77  lea     rax, [rbp+57h+var_C0]
0x180012a7b  mov     [rsp+100h+cbSecret], r15d
0x180012a80  lea     r8, [rbp+57h+var_60]
0x180012a84  mov     r9d, r13d
0x180012a87  mov     [rsp+100h+pbSecret], rax
0x180012a8c  lea     rdx, [rbp+57h+var_B0]
0x180012a90  call    cs:__imp_BCryptKeyDerivation
0x180012a96  test    eax, eax
0x180012a98  js      loc_180012B55
0x180012a9e  xor     edx, edx
0x180012aa0  lea     r15, aNull_2; "(null)"
0x180012aa7  cmp     [rsi+18h], rdx
0x180012aab  mov     r14, r15
0x180012aae  cmovnz  r14, [rsi+18h]
0x180012ab3  cmp     ebx, 2
0x180012ab6  jnz     short loc_180012B33
0x180012ab8  cmp     [rsi+8], rdx
0x180012abc  cmovnz  r15, [rsi+8]
0x180012ac1  or      rax, 0FFFFFFFFFFFFFFFFh
0x180012ac5  mov     rcx, rax
0x180012ac8  inc     rcx
0x180012acb  cmp     [r14+rcx*2], dx
0x180012ad0  jnz     short loc_180012AC8
0x180012ad2  inc     rax
0x180012ad5  cmp     [r15+rax*2], dx
0x180012ada  jnz     short loc_180012AD2
0x180012adc  lea     rbx, [rax+2]
0x180012ae0  add     rbx, rcx
0x180012ae3  xor     ecx, ecx; uFlags
0x180012ae5  lea     rdx, [rbx+rbx]; uBytes
0x180012ae9  call    cs:__imp_LocalAlloc
0x180012aef  xor     ecx, ecx
0x180012af1  mov     r8, r15; unsigned __int16 *
0x180012af4  mov     rdx, rbx; unsigned __int64
0x180012af7  mov     rdi, rax
0x180012afa  mov     [rax], cx
0x180012afd  mov     rcx, rax; unsigned __int16 *
0x180012b00  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180012b05  lea     r8, asc_180072468; "\\"
0x180012b0c  mov     rdx, rbx; unsigned __int64
0x180012b0f  mov     rcx, rdi; unsigned __int16 *
0x180012b12  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180012b17  mov     r8, r14; unsigned __int16 *
0x180012b1a  mov     rdx, rbx; unsigned __int64
0x180012b1d  mov     rcx, rdi; unsigned __int16 *
0x180012b20  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180012b25  test    cs:Microsoft_Windows_Crypto_DPAPIEnableBits, 8
0x180012b2c  jz      short loc_180012B52
0x180012b2e  mov     r9, rdi
0x180012b31  jmp     short loc_180012B44
0x180012b33  cmp     ebx, 3
0x180012b36  jnz     short loc_180012B52
0x180012b38  test    cs:Microsoft_Windows_Crypto_DPAPIEnableBits, 8
0x180012b3f  jz      short loc_180012B52
0x180012b41  mov     r9, r14
0x180012b44  lea     r8, [rbp+57h+var_60]
0x180012b48  mov     [rsp+100h+pbSecret], r12
0x180012b4d  call    McTemplateU0b32zk_EtwEventWriteTransfer
0x180012b52  xor     r15d, r15d
0x180012b55  mov     rcx, [rbp+57h+phKey]; hKey
0x180012b59  test    rcx, rcx
0x180012b5c  jz      short loc_180012B64
0x180012b5e  call    cs:__imp_BCryptDestroyKey
0x180012b64  test    rdi, rdi
0x180012b67  jz      short loc_180012B72
0x180012b69  mov     rcx, rdi; hMem
0x180012b6c  call    cs:__imp_LocalFree
0x180012b72  lea     rax, [rbp+57h+var_60]
0x180012b76  mov     [rax], r15b
0x180012b79  inc     rax
0x180012b7c  sub     r13, 1
0x180012b80  jnz     short loc_180012B76
0x180012b82  jmp     short loc_180012BA8
0x180012b84  test    cs:Microsoft_Windows_Crypto_DPAPIEnableBits, 8
0x180012b8b  jz      short loc_180012BA8
0x180012b8d  lea     rax, [rbp+57h+var_70]
0x180012b91  mov     r9d, 1
0x180012b97  lea     rdx, ETW_LOG_DPAPI_CRED_KEY_NOT_CREATED
0x180012b9e  mov     [rsp+100h+pbSecret], rax
0x180012ba3  call    McGenEventWrite_EtwEventWriteTransfer
0x180012ba8  mov     rcx, [rbp+57h+var_40]
0x180012bac  xor     rcx, rsp; StackCookie
0x180012baf  call    __security_check_cookie
0x180012bb4  mov     rbx, [rsp+100h+arg_10]
0x180012bbc  add     rsp, 0D0h
0x180012bc3  pop     r15
0x180012bc5  pop     r14
0x180012bc7  pop     r13
0x180012bc9  pop     r12
0x180012bcb  pop     rdi
0x180012bcc  pop     rsi
0x180012bcd  pop     rbp
0x180012bce  retn
```
