# myBlobToHashString(_CRYPTOAPI_BLOB const *,ushort * *)

- ea: `0x18001d6ec`
- end: `0x18001d8a2`
- name: `?myBlobToHashString@@YAJPEBU_CRYPTOAPI_BLOB@@PEAPEAG@Z`
- size: `438`
- prototype: `int(const struct _CRYPTOAPI_BLOB *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18001e4f4`

## callees

- `0x18001d6ec`
- `0x180020308`
- `0x180020a6c`
- `0x180021438`
- `0x180039740`

## import_xrefs

- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x18001d859`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x18001d859`
- `CRYPTSP!CryptGetHashParam` at `0x18001d7f6`
- `CRYPTSP!CryptGetHashParam` at `0x18001d7f6`
- `CRYPTSP!CryptHashData` at `0x18001d7bb`
- `CRYPTSP!CryptHashData` at `0x18001d7bb`
- `CRYPTSP!CryptCreateHash` at `0x18001d792`
- `CRYPTSP!CryptCreateHash` at `0x18001d792`
- `CRYPTSP!CryptAcquireContextW` at `0x18001d75f`
- `CRYPTSP!CryptAcquireContextW` at `0x18001d75f`
- `CRYPTSP!CryptReleaseContext` at `0x18001d879`
- `CRYPTSP!CryptReleaseContext` at `0x18001d879`
- `CRYPTSP!CryptDestroyHash` at `0x18001d868`
- `CRYPTSP!CryptDestroyHash` at `0x18001d868`

## pseudocode

```c
__int64 __fastcall myBlobToHashString(const struct _CRYPTOAPI_BLOB *a1, unsigned __int16 **a2)
{
  bool v2; // zf
  unsigned int v5; // ebx
  unsigned int v6; // ecx
  int v7; // edx
  int v8; // eax
  DWORD pdwDataLen; // [rsp+30h] [rbp-79h] BYREF
  HCRYPTHASH phHash; // [rsp+38h] [rbp-71h] BYREF
  unsigned int v12; // [rsp+40h] [rbp-69h] BYREF
  HCRYPTPROV phProv; // [rsp+48h] [rbp-61h] BYREF
  BYTE pbData[32]; // [rsp+50h] [rbp-59h] BYREF
  unsigned __int16 Src[64]; // [rsp+70h] [rbp-39h] BYREF

  v2 = a1->cbData == 0;
  phProv = 0;
  phHash = 0;
  pdwDataLen = 0;
  if ( v2 )
  {
    v5 = -2147024809;
    v6 = 199688602;
    v7 = -2147024809;
  }
  else
  {
    if ( CryptAcquireContextW(&phProv, 0, L"Microsoft Base Cryptographic Provider v1.0", 1u, 0xF0000000) )
    {
      if ( CryptCreateHash(phProv, 0x8004u, 0, 0, &phHash) )
      {
        if ( CryptHashData(phHash, a1->pbData, a1->cbData, 0) )
        {
          pdwDataLen = 20;
          if ( CryptGetHashParam(phHash, 2u, pbData, &pdwDataLen, 0) )
          {
            v12 = 120;
            v8 = MultiByteIntegerToWszBuf(3u, pdwDataLen, pbData, &v12, Src);
            v5 = v8;
            if ( v8 )
            {
              v6 = 202834330;
            }
            else
            {
              v8 = myDupString(Src, a2);
              v5 = v8;
              if ( !v8 )
                goto LABEL_17;
              v6 = 203030938;
            }
          }
          else
          {
            v8 = myHLastError();
            v5 = v8;
            v6 = 202178970;
          }
        }
        else
        {
          v8 = myHLastError();
          v5 = v8;
          v6 = 201720218;
        }
      }
      else
      {
        v8 = myHLastError();
        v5 = v8;
        v6 = 201195930;
      }
    }
    else
    {
      v8 = myHLastError();
      v5 = v8;
      v6 = 200671642;
    }
    v7 = v8;
  }
  CSPrintErrorLineFile(v6, v7);
LABEL_17:
  if ( phHash )
    CryptDestroyHash(phHash);
  if ( phProv )
    CryptReleaseContext(phProv, 0);
  return v5;
}

```

## disassembly

```asm
0x18001d6ec  mov     [rsp-8+arg_10], rbx
0x18001d6f1  mov     [rsp-8+arg_18], rdi
0x18001d6f6  push    rbp
0x18001d6f7  lea     rbp, [rsp-57h]
0x18001d6fc  sub     rsp, 100h
0x18001d703  mov     rax, cs:__security_cookie
0x18001d70a  xor     rax, rsp
0x18001d70d  mov     [rbp+57h+var_10], rax
0x18001d711  cmp     dword ptr [rcx], 0
0x18001d714  mov     rdi, rdx
0x18001d717  mov     rbx, rcx
0x18001d71a  mov     [rbp+57h+phProv], 0
0x18001d722  mov     [rbp+57h+phHash], 0
0x18001d72a  mov     [rbp+57h+pdwDataLen], 0
0x18001d731  jnz     short loc_18001D744
0x18001d733  mov     ebx, 80070057h
0x18001d738  mov     ecx, 0BE7019Ah
0x18001d73d  mov     edx, ebx
0x18001d73f  jmp     loc_18001D859
0x18001d744  mov     r9d, 1; dwProvType
0x18001d74a  mov     [rsp+100h+dwFlags], 0F0000000h; dwFlags
0x18001d752  lea     r8, szProvider; "Microsoft Base Cryptographic Provider v"...
0x18001d759  xor     edx, edx; szContainer
0x18001d75b  lea     rcx, [rbp+57h+phProv]; phProv
0x18001d75f  call    cs:__imp_CryptAcquireContextW
0x18001d765  test    eax, eax
0x18001d767  jnz     short loc_18001D77A
0x18001d769  call    ?myHLastError@@YAJXZ; myHLastError(void)
0x18001d76e  mov     ebx, eax
0x18001d770  mov     ecx, 0BF6019Ah
0x18001d775  jmp     loc_18001D857
0x18001d77a  mov     rcx, [rbp+57h+phProv]; hProv
0x18001d77e  lea     rax, [rbp+57h+phHash]
0x18001d782  xor     r9d, r9d; dwFlags
0x18001d785  mov     qword ptr [rsp+100h+dwFlags], rax; phHash
0x18001d78a  xor     r8d, r8d; hKey
0x18001d78d  mov     edx, 8004h; Algid
0x18001d792  call    cs:__imp_CryptCreateHash
0x18001d798  test    eax, eax
0x18001d79a  jnz     short loc_18001D7AD
0x18001d79c  call    ?myHLastError@@YAJXZ; myHLastError(void)
0x18001d7a1  mov     ebx, eax
0x18001d7a3  mov     ecx, 0BFE019Ah
0x18001d7a8  jmp     loc_18001D857
0x18001d7ad  mov     r8d, [rbx]; dwDataLen
0x18001d7b0  xor     r9d, r9d; dwFlags
0x18001d7b3  mov     rdx, [rbx+8]; pbData
0x18001d7b7  mov     rcx, [rbp+57h+phHash]; hHash
0x18001d7bb  call    cs:__imp_CryptHashData
0x18001d7c1  test    eax, eax
0x18001d7c3  jnz     short loc_18001D7D6
0x18001d7c5  call    ?myHLastError@@YAJXZ; myHLastError(void)
0x18001d7ca  mov     ebx, eax
0x18001d7cc  mov     ecx, 0C06019Ah
0x18001d7d1  jmp     loc_18001D857
0x18001d7d6  mov     rcx, [rbp+57h+phHash]; hHash
0x18001d7da  lea     r9, [rbp+57h+pdwDataLen]; pdwDataLen
0x18001d7de  lea     r8, [rbp+57h+pbData]; pbData
0x18001d7e2  mov     [rbp+57h+pdwDataLen], 14h
0x18001d7e9  mov     edx, 2; dwParam
0x18001d7ee  mov     [rsp+100h+dwFlags], 0; dwFlags
0x18001d7f6  call    cs:__imp_CryptGetHashParam
0x18001d7fc  test    eax, eax
0x18001d7fe  jnz     short loc_18001D80E
0x18001d800  call    ?myHLastError@@YAJXZ; myHLastError(void)
0x18001d805  mov     ebx, eax
0x18001d807  mov     ecx, 0C0D019Ah
0x18001d80c  jmp     short loc_18001D857
0x18001d80e  mov     edx, [rbp+57h+pdwDataLen]; unsigned int
0x18001d811  lea     rax, [rbp+57h+Src]
0x18001d815  lea     r9, [rbp+57h+var_C0]; unsigned int *
0x18001d819  mov     qword ptr [rsp+100h+dwFlags], rax; unsigned __int16 *
0x18001d81e  lea     r8, [rbp+57h+pbData]; unsigned __int8 *
0x18001d822  mov     [rbp+57h+var_C0], 78h ; 'x'
0x18001d829  mov     ecx, 3; unsigned int
0x18001d82e  call    ?MultiByteIntegerToWszBuf@@YAJKKPEBEPEAKPEAG@Z; MultiByteIntegerToWszBuf(ulong,ulong,uchar const *,ulong *,ushort *)
0x18001d833  mov     ebx, eax
0x18001d835  test    eax, eax
0x18001d837  jz      short loc_18001D840
0x18001d839  mov     ecx, 0C17019Ah
0x18001d83e  jmp     short loc_18001D857
0x18001d840  mov     rdx, rdi; unsigned __int16 **
0x18001d843  lea     rcx, [rbp+57h+Src]; Src
0x18001d847  call    ?myDupString@@YAJPEBGPEAPEAG@Z; myDupString(ushort const *,ushort * *)
0x18001d84c  mov     ebx, eax
0x18001d84e  test    eax, eax
0x18001d850  jz      short loc_18001D85F
0x18001d852  mov     ecx, 0C1A019Ah
0x18001d857  mov     edx, eax
0x18001d859  call    cs:__imp_?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x18001d85f  mov     rcx, [rbp+57h+phHash]; hHash
0x18001d863  test    rcx, rcx
0x18001d866  jz      short loc_18001D86E
0x18001d868  call    cs:__imp_CryptDestroyHash
0x18001d86e  mov     rcx, [rbp+57h+phProv]; hProv
0x18001d872  test    rcx, rcx
0x18001d875  jz      short loc_18001D87F
0x18001d877  xor     edx, edx; dwFlags
0x18001d879  call    cs:__imp_CryptReleaseContext
0x18001d87f  mov     eax, ebx
0x18001d881  mov     rcx, [rbp+57h+var_10]
0x18001d885  xor     rcx, rsp; StackCookie
0x18001d888  call    __security_check_cookie
0x18001d88d  lea     r11, [rsp+100h+var_s0]
0x18001d895  mov     rbx, [r11+20h]
0x18001d899  mov     rdi, [r11+28h]
0x18001d89d  mov     rsp, r11
0x18001d8a0  pop     rbp
0x18001d8a1  retn
```
