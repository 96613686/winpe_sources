# sqlencrypt::SqlSecurityUtility::GetHMACWithSHA256(uchar const *,unsigned __int64,uchar const *,unsigned __int64,uchar *,unsigned __int64)

- ea: `0x10047dadc`
- end: `0x10047dcc5`
- name: `?GetHMACWithSHA256@SqlSecurityUtility@sqlencrypt@@SAJPEBE_K01PEAE1@Z`
- size: `489`
- prototype: `__int64 __usercall@<rax>(BYTE *pbData@<rcx>, unsigned __int64@<rdx>, const unsigned __int8 *@<r8>, unsigned __int64@<r9>, unsigned __int8 *, unsigned __int64)`
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x10047ad60`
- `0x10047dccc`

## callees

- `0x10047dadc`
- `0x10047dd74`
- `0x10047e63c`
- `0x100546a24`
- `0x100546aa8`
- `0x100548210`

## import_xrefs

- `ADVAPI32!CryptDestroyHash` at `0x10047dc7a`
- `ADVAPI32!CryptDestroyHash` at `0x10047dc7a`
- `ADVAPI32!CryptSetHashParam` at `0x10047dc16`
- `ADVAPI32!CryptSetHashParam` at `0x10047dc16`
- `ADVAPI32!CryptHashData` at `0x10047dc2a`
- `ADVAPI32!CryptHashData` at `0x10047dc2a`
- `ADVAPI32!CryptCreateHash` at `0x10047dbcf`
- `ADVAPI32!CryptCreateHash` at `0x10047dbcf`
- `ADVAPI32!CryptGetHashParam` at `0x10047dc57`
- `ADVAPI32!CryptGetHashParam` at `0x10047dc57`
- `ADVAPI32!CryptDestroyKey` at `0x10047dbdc`
- `ADVAPI32!CryptDestroyKey` at `0x10047dc83`
- `ADVAPI32!CryptDestroyKey` at `0x10047dbdc`
- `ADVAPI32!CryptDestroyKey` at `0x10047dc83`
- `api-ms-win-crt-string-l1-1-0!memcpy_s` at `0x10047dc70`
- `api-ms-win-crt-string-l1-1-0!memcpy_s` at `0x10047dc70`

## pseudocode

```c
__int64 __fastcall sqlencrypt::SqlSecurityUtility::GetHMACWithSHA256(
        BYTE *pbData,
        __int64 a2,
        const unsigned __int8 *a3,
        rsize_t a4,
        unsigned __int8 *a5,
        rsize_t DestinationSize)
{
  unsigned int v6; // ebx
  __int64 v10; // r9
  HCRYPTPROV WinCryptProvider; // r14
  __int64 v12; // rdx
  HCRYPTKEY inited; // rdi
  BYTE *v15; // r8
  DWORD v16; // eax
  __int64 v17; // r9
  HCRYPTHASH hHash; // [rsp+50h] [rbp-69h] BYREF
  DWORD pdwDataLen; // [rsp+58h] [rbp-61h] BYREF
  DWORD dwDataLen[2]; // [rsp+60h] [rbp-59h]
  BYTE pbDataa[8]; // [rsp+68h] [rbp-51h] BYREF
  __int64 v22; // [rsp+70h] [rbp-49h]
  int v23; // [rsp+78h] [rbp-41h]
  __int64 v24; // [rsp+80h] [rbp-39h]
  int v25; // [rsp+88h] [rbp-31h]
  _BYTE Source[32]; // [rsp+90h] [rbp-29h] BYREF

  v6 = 0;
  *(_QWORD *)dwDataLen = a2;
  if ( (bidGblFlags & 2) != 0 && off_1005E6EC8[0] )
    bidTraceW(0, 89088, off_1005E6EC8[0], pbData);
  WinCryptProvider = sqlencrypt::SqlSecurityUtility::GetWinCryptProvider();
  if ( !WinCryptProvider )
  {
    if ( (bidGblFlags & 2) != 0 )
    {
      v12 = 114697;
      return bidTraceHR(0, v12, 2147500037LL, v10);
    }
    return 2147500037LL;
  }
  inited = sqlencrypt::SqlSecurityUtility::InitHMACWithSHA256(a3, a4);
  if ( !inited )
  {
    if ( (bidGblFlags & 2) != 0 )
    {
      v12 = 119817;
      return bidTraceHR(0, v12, 2147500037LL, v10);
    }
    return 2147500037LL;
  }
  if ( !CryptCreateHash(WinCryptProvider, 0x8009u, inited, 0, &hHash) )
  {
    CryptDestroyKey(inited);
    if ( (bidGblFlags & 2) != 0 )
    {
      v12 = 125961;
      return bidTraceHR(0, v12, 2147500037LL, v10);
    }
    return 2147500037LL;
  }
  *(_DWORD *)pbDataa = 32780;
  v22 = 0;
  v23 = 0;
  v24 = 0;
  v25 = 0;
  CryptSetHashParam(hHash, 5u, pbDataa, 0);
  CryptHashData(hHash, pbData, dwDataLen[0], 0);
  v15 = Source;
  v16 = 32;
  if ( DestinationSize >= 0x20 )
  {
    v16 = DestinationSize;
    v15 = a5;
  }
  pdwDataLen = v16;
  CryptGetHashParam(hHash, 2u, v15, &pdwDataLen, 0);
  if ( DestinationSize < 0x20 )
    memcpy_s(a5, DestinationSize, Source, DestinationSize);
  CryptDestroyHash(hHash);
  CryptDestroyKey(inited);
  if ( (bidGblFlags & 2) != 0 )
    return (unsigned int)bidTraceHR(0, 140297, 0, v17);
  return v6;
}

```

## disassembly

```asm
0x10047dadc  push    rbp
0x10047dade  push    rbx
0x10047dadf  push    rsi
0x10047dae0  push    rdi
0x10047dae1  push    r12
0x10047dae3  push    r13
0x10047dae5  push    r14
0x10047dae7  push    r15
0x10047dae9  lea     rbp, [rsp-0Fh]
0x10047daee  sub     rsp, 0C8h
0x10047daf5  mov     rax, cs:__security_cookie
0x10047dafc  xor     rax, rsp
0x10047daff  mov     [rbp+47h+var_50], rax
0x10047db03  mov     r15, [rbp+47h+arg_20]
0x10047db07  xor     ebx, ebx
0x10047db09  test    byte ptr cs:_bidGblFlags, 2
0x10047db10  mov     r12, r9
0x10047db13  mov     rsi, [rbp+47h+DestinationSize]
0x10047db17  mov     rdi, r8
0x10047db1a  mov     qword ptr [rbp+47h+dwDataLen], rdx
0x10047db1e  mov     r13, rcx
0x10047db21  jz      short loc_10047DB5E
0x10047db23  mov     rax, cs:off_1005E6EC8; "<sqlencrypt::SqlSecurityUtility::GetHMA"...
0x10047db2a  test    rax, rax
0x10047db2d  jz      short loc_10047DB5E
0x10047db2f  mov     [rsp+100h+var_C0], rsi
0x10047db34  mov     [rsp+100h+var_C8], r15
0x10047db39  mov     [rsp+100h+var_D0], r9
0x10047db3e  mov     r9, rcx
0x10047db41  mov     [rsp+100h+var_D8], r8
0x10047db46  xor     ecx, ecx
0x10047db48  mov     r8, cs:off_1005E6EC8; "<sqlencrypt::SqlSecurityUtility::GetHMA"...
0x10047db4f  mov     [rsp+100h+phHash], rdx
0x10047db54  mov     edx, 15C00h
0x10047db59  call    _bidTraceW
0x10047db5e  call    ?GetWinCryptProvider@SqlSecurityUtility@sqlencrypt@@SA_KXZ; sqlencrypt::SqlSecurityUtility::GetWinCryptProvider(void)
0x10047db63  mov     r14, rax
0x10047db66  test    rax, rax
0x10047db69  jnz     short loc_10047DB95
0x10047db6b  test    byte ptr cs:_bidGblFlags, 2
0x10047db72  jz      short loc_10047DB8B
0x10047db74  mov     edx, 1C009h
0x10047db79  xor     ecx, ecx
0x10047db7b  mov     r8d, 80004005h
0x10047db81  call    _bidTraceHR
0x10047db86  jmp     loc_10047DCA5
0x10047db8b  mov     eax, 80004005h
0x10047db90  jmp     loc_10047DCA5
0x10047db95  mov     rdx, r12; SourceSize
0x10047db98  mov     rcx, rdi; Source
0x10047db9b  call    ?InitHMACWithSHA256@SqlSecurityUtility@sqlencrypt@@SA_KPEBE_K@Z; sqlencrypt::SqlSecurityUtility::InitHMACWithSHA256(uchar const *,unsigned __int64)
0x10047dba0  mov     rdi, rax
0x10047dba3  test    rax, rax
0x10047dba6  jnz     short loc_10047DBB8
0x10047dba8  test    byte ptr cs:_bidGblFlags, 2
0x10047dbaf  jz      short loc_10047DB8B
0x10047dbb1  mov     edx, 1D409h
0x10047dbb6  jmp     short loc_10047DB79
0x10047dbb8  lea     rax, [rbp+47h+hHash]
0x10047dbbc  xor     r9d, r9d; dwFlags
0x10047dbbf  mov     r8, rdi; hKey
0x10047dbc2  mov     [rsp+100h+phHash], rax; phHash
0x10047dbc7  mov     edx, 8009h; Algid
0x10047dbcc  mov     rcx, r14; hProv
0x10047dbcf  call    cs:__imp_CryptCreateHash
0x10047dbd5  test    eax, eax
0x10047dbd7  jnz     short loc_10047DBF2
0x10047dbd9  mov     rcx, rdi; hKey
0x10047dbdc  call    cs:__imp_CryptDestroyKey
0x10047dbe2  test    byte ptr cs:_bidGblFlags, 2
0x10047dbe9  jz      short loc_10047DB8B
0x10047dbeb  mov     edx, 1EC09h
0x10047dbf0  jmp     short loc_10047DB79
0x10047dbf2  mov     rcx, [rbp+47h+hHash]; hHash
0x10047dbf6  lea     r8, [rbp+47h+pbData]; pbData
0x10047dbfa  xor     r9d, r9d; dwFlags
0x10047dbfd  mov     dword ptr [rbp+47h+pbData], 800Ch
0x10047dc04  mov     [rbp+47h+var_90], rbx
0x10047dc08  mov     [rbp+47h+var_88], ebx
0x10047dc0b  mov     [rbp+47h+var_80], rbx
0x10047dc0f  lea     edx, [r9+5]; dwParam
0x10047dc13  mov     [rbp+47h+var_78], ebx
0x10047dc16  call    cs:__imp_CryptSetHashParam
0x10047dc1c  mov     r8d, [rbp+47h+dwDataLen]; dwDataLen
0x10047dc20  xor     r9d, r9d; dwFlags
0x10047dc23  mov     rcx, [rbp+47h+hHash]; hHash
0x10047dc27  mov     rdx, r13; pbData
0x10047dc2a  call    cs:__imp_CryptHashData
0x10047dc30  mov     rcx, [rbp+47h+hHash]; hHash
0x10047dc34  lea     r8, [rbp+47h+Source]
0x10047dc38  mov     eax, 20h ; ' '
0x10047dc3d  mov     dword ptr [rsp+100h+phHash], ebx; dwFlags
0x10047dc41  cmp     rsi, rax
0x10047dc44  lea     r9, [rbp+47h+pdwDataLen]; pdwDataLen
0x10047dc48  mov     edx, 2; dwParam
0x10047dc4d  cmovnb  eax, esi
0x10047dc50  cmovnb  r8, r15; pbData
0x10047dc54  mov     [rbp+47h+pdwDataLen], eax
0x10047dc57  call    cs:__imp_CryptGetHashParam
0x10047dc5d  cmp     rsi, 20h ; ' '
0x10047dc61  jnb     short loc_10047DC76
0x10047dc63  mov     r9, rsi; SourceSize
0x10047dc66  lea     r8, [rbp+47h+Source]; Source
0x10047dc6a  mov     rdx, rsi; DestinationSize
0x10047dc6d  mov     rcx, r15; Destination
0x10047dc70  call    cs:__imp_memcpy_s
0x10047dc76  mov     rcx, [rbp+47h+hHash]; hHash
0x10047dc7a  call    cs:__imp_CryptDestroyHash
0x10047dc80  mov     rcx, rdi; hKey
0x10047dc83  call    cs:__imp_CryptDestroyKey
0x10047dc89  test    byte ptr cs:_bidGblFlags, 2
0x10047dc90  jz      short loc_10047DCA3
0x10047dc92  xor     r8d, r8d
0x10047dc95  mov     edx, 22409h
0x10047dc9a  xor     ecx, ecx
0x10047dc9c  call    _bidTraceHR
0x10047dca1  mov     ebx, eax
0x10047dca3  mov     eax, ebx
0x10047dca5  mov     rcx, [rbp+47h+var_50]
0x10047dca9  xor     rcx, rsp; StackCookie
0x10047dcac  call    __security_check_cookie
0x10047dcb1  add     rsp, 0C8h
0x10047dcb8  pop     r15
0x10047dcba  pop     r14
0x10047dcbc  pop     r13
0x10047dcbe  pop     r12
0x10047dcc0  pop     rdi
0x10047dcc1  pop     rsi
0x10047dcc2  pop     rbx
0x10047dcc3  pop     rbp
0x10047dcc4  retn
```
