# sqlencrypt::AeadAes256cbcSha256::InitHMAC(uchar const *,ulong)

- ea: `0x10047b290`
- end: `0x10047b3e3`
- name: `?InitHMAC@AeadAes256cbcSha256@sqlencrypt@@AEAAJPEBEK@Z`
- size: `339`
- prototype: `int(sqlencrypt::AeadAes256cbcSha256 *__hidden this, const unsigned __int8 *, unsigned int)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1004796d0`
- `0x10047a800`

## callees

- `0x10047b290`
- `0x10047dd74`
- `0x10047e63c`
- `0x100546a24`
- `0x100546aa8`

## import_xrefs

- `ADVAPI32!CryptSetHashParam` at `0x10047b3a6`
- `ADVAPI32!CryptSetHashParam` at `0x10047b3a6`
- `ADVAPI32!CryptCreateHash` at `0x10047b355`
- `ADVAPI32!CryptCreateHash` at `0x10047b355`
- `ADVAPI32!CryptDestroyKey` at `0x10047b363`
- `ADVAPI32!CryptDestroyKey` at `0x10047b363`

## pseudocode

```c
__int64 __fastcall sqlencrypt::AeadAes256cbcSha256::InitHMAC(
        sqlencrypt::AeadAes256cbcSha256 *this,
        const unsigned __int8 *a2,
        unsigned int a3)
{
  unsigned int v3; // ebx
  rsize_t v4; // rbp
  HCRYPTPROV WinCryptProvider; // rsi
  __int64 v8; // r9
  __int64 v9; // rdx
  HCRYPTKEY inited; // rax
  HCRYPTHASH v12; // rcx
  __int64 v13; // r9
  BYTE pbData[8]; // [rsp+30h] [rbp-38h] BYREF
  __int64 v15; // [rsp+38h] [rbp-30h]
  int v16; // [rsp+40h] [rbp-28h]
  __int64 v17; // [rsp+48h] [rbp-20h]
  int v18; // [rsp+50h] [rbp-18h]

  v3 = 0;
  v4 = a3;
  if ( (bidGblFlags & 2) != 0 && off_1005E6DE0[0] )
    bidTraceW(0, 135168, off_1005E6DE0[0], a2);
  WinCryptProvider = sqlencrypt::SqlSecurityUtility::GetWinCryptProvider();
  if ( !WinCryptProvider )
  {
    if ( (bidGblFlags & 2) != 0 )
    {
      v9 = 144393;
      return bidTraceHR(0, v9, 2147500037LL, v8);
    }
    return 2147500037LL;
  }
  inited = sqlencrypt::SqlSecurityUtility::InitHMACWithSHA256(a2, v4);
  *((_QWORD *)this + 1) = inited;
  if ( !inited )
  {
    if ( (bidGblFlags & 2) != 0 )
    {
      v9 = 149513;
      return bidTraceHR(0, v9, 2147500037LL, v8);
    }
    return 2147500037LL;
  }
  if ( !CryptCreateHash(WinCryptProvider, 0x8009u, inited, 0, (HCRYPTHASH *)this + 2) )
  {
    CryptDestroyKey(*((_QWORD *)this + 1));
    *((_QWORD *)this + 1) = 0;
    if ( (bidGblFlags & 2) != 0 )
    {
      v9 = 155657;
      return bidTraceHR(0, v9, 2147500037LL, v8);
    }
    return 2147500037LL;
  }
  v12 = *((_QWORD *)this + 2);
  *(_DWORD *)pbData = 32780;
  v15 = 0;
  v16 = 0;
  v17 = 0;
  v18 = 0;
  CryptSetHashParam(v12, 5u, pbData, 0);
  if ( (bidGblFlags & 2) != 0 )
    return (unsigned int)bidTraceHR(0, 160777, 0, v13);
  return v3;
}

```

## disassembly

```asm
0x10047b290  mov     rax, rsp
0x10047b293  mov     [rax+8], rbx
0x10047b297  mov     [rax+10h], rbp
0x10047b29b  mov     [rax+18h], rsi
0x10047b29f  mov     [rax+20h], rdi
0x10047b2a3  push    r14
0x10047b2a5  sub     rsp, 60h
0x10047b2a9  xor     ebx, ebx
0x10047b2ab  mov     ebp, r8d
0x10047b2ae  test    byte ptr cs:_bidGblFlags, 2
0x10047b2b5  mov     r14, rdx
0x10047b2b8  mov     rdi, rcx
0x10047b2bb  jz      short loc_10047B2E3
0x10047b2bd  mov     rax, cs:off_1005E6DE0; "<sqlencrypt::AeadAes256cbcSha256::InitH"...
0x10047b2c4  test    rax, rax
0x10047b2c7  jz      short loc_10047B2E3
0x10047b2c9  mov     r8, cs:off_1005E6DE0; "<sqlencrypt::AeadAes256cbcSha256::InitH"...
0x10047b2d0  mov     r9, rdx
0x10047b2d3  mov     edx, 21000h
0x10047b2d8  mov     dword ptr [rsp+68h+phHash], ebp
0x10047b2dc  xor     ecx, ecx
0x10047b2de  call    _bidTraceW
0x10047b2e3  call    ?GetWinCryptProvider@SqlSecurityUtility@sqlencrypt@@SA_KXZ; sqlencrypt::SqlSecurityUtility::GetWinCryptProvider(void)
0x10047b2e8  mov     rsi, rax
0x10047b2eb  test    rax, rax
0x10047b2ee  jnz     short loc_10047B31A
0x10047b2f0  test    byte ptr cs:_bidGblFlags, 2
0x10047b2f7  jz      short loc_10047B310
0x10047b2f9  mov     edx, 23409h
0x10047b2fe  xor     ecx, ecx
0x10047b300  mov     r8d, 80004005h
0x10047b306  call    _bidTraceHR
0x10047b30b  jmp     loc_10047B3C8
0x10047b310  mov     eax, 80004005h
0x10047b315  jmp     loc_10047B3C8
0x10047b31a  mov     rdx, rbp; SourceSize
0x10047b31d  mov     rcx, r14; Source
0x10047b320  call    ?InitHMACWithSHA256@SqlSecurityUtility@sqlencrypt@@SA_KPEBE_K@Z; sqlencrypt::SqlSecurityUtility::InitHMACWithSHA256(uchar const *,unsigned __int64)
0x10047b325  mov     [rdi+8], rax
0x10047b329  test    rax, rax
0x10047b32c  jnz     short loc_10047B33E
0x10047b32e  test    byte ptr cs:_bidGblFlags, 2
0x10047b335  jz      short loc_10047B310
0x10047b337  mov     edx, 24809h
0x10047b33c  jmp     short loc_10047B2FE
0x10047b33e  lea     r14, [rdi+10h]
0x10047b342  xor     r9d, r9d; dwFlags
0x10047b345  mov     r8, rax; hKey
0x10047b348  mov     [rsp+68h+phHash], r14; phHash
0x10047b34d  mov     edx, 8009h; Algid
0x10047b352  mov     rcx, rsi; hProv
0x10047b355  call    cs:__imp_CryptCreateHash
0x10047b35b  test    eax, eax
0x10047b35d  jnz     short loc_10047B37D
0x10047b35f  mov     rcx, [rdi+8]; hKey
0x10047b363  call    cs:__imp_CryptDestroyKey
0x10047b369  mov     [rdi+8], rbx
0x10047b36d  test    byte ptr cs:_bidGblFlags, 2
0x10047b374  jz      short loc_10047B310
0x10047b376  mov     edx, 26009h
0x10047b37b  jmp     short loc_10047B2FE
0x10047b37d  mov     rcx, [r14]; hHash
0x10047b380  lea     r8, [rsp+68h+pbData]; pbData
0x10047b385  xor     r9d, r9d; dwFlags
0x10047b388  mov     dword ptr [rsp+68h+pbData], 800Ch
0x10047b390  mov     [rsp+68h+var_30], rbx
0x10047b395  mov     [rsp+68h+var_28], ebx
0x10047b399  mov     [rsp+68h+var_20], rbx
0x10047b39e  lea     edx, [r9+5]; dwParam
0x10047b3a2  mov     [rsp+68h+var_18], ebx
0x10047b3a6  call    cs:__imp_CryptSetHashParam
0x10047b3ac  test    byte ptr cs:_bidGblFlags, 2
0x10047b3b3  jz      short loc_10047B3C6
0x10047b3b5  xor     r8d, r8d
0x10047b3b8  mov     edx, 27409h
0x10047b3bd  xor     ecx, ecx
0x10047b3bf  call    _bidTraceHR
0x10047b3c4  mov     ebx, eax
0x10047b3c6  mov     eax, ebx
0x10047b3c8  lea     r11, [rsp+68h+var_8]
0x10047b3cd  mov     rbx, [r11+10h]
0x10047b3d1  mov     rbp, [r11+18h]
0x10047b3d5  mov     rsi, [r11+20h]
0x10047b3d9  mov     rdi, [r11+28h]
0x10047b3dd  mov     rsp, r11
0x10047b3e0  pop     r14
0x10047b3e2  retn
```
