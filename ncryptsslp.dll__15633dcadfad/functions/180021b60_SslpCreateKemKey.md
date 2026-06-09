# SslpCreateKemKey

- ea: `0x180021b60`
- end: `0x180021cb3`
- name: `SslpCreateKemKey`
- size: `339`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180011a40`

## callees

- `0x18000b654`
- `0x180021a74`
- `0x180021b60`
- `0x180022164`

## import_xrefs

- `ncrypt!NCryptSetProperty` at `0x180021c3e`
- `ncrypt!NCryptSetProperty` at `0x180021c3e`
- `ncrypt!NCryptFinalizeKey` at `0x180021c59`
- `ncrypt!NCryptFinalizeKey` at `0x180021c59`
- `ncrypt!NCryptCreatePersistedKey` at `0x180021bfb`
- `ncrypt!NCryptCreatePersistedKey` at `0x180021bfb`

## string_xrefs

- `0x180021c8b`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tlskem.c`

## pseudocode

```c
__int64 __fastcall SslpCreateKemKey(__int64 *a1, const WCHAR *a2, int a3, __int16 a4, PBYTE pbInput, char a6)
{
  __int64 v8; // rdi
  int v9; // eax
  unsigned int v10; // ebx
  __int64 v11; // rcx
  __int64 v12; // r9
  NCRYPT_HANDLE *v13; // r14
  SECURITY_STATUS PersistedKey; // eax
  __int64 v15; // r9
  SECURITY_STATUS v16; // eax
  SECURITY_STATUS v17; // eax
  __int64 v19; // [rsp+70h] [rbp+8h] BYREF

  v19 = 0;
  v8 = 0;
  if ( a1 && a3 == 458753 )
  {
    v9 = SslpCreateBaseKemKeyStruct(458753, a4, 458753, &v19);
    v10 = v9;
    if ( v9 >= 0 )
    {
      if ( (a6 & 2) != 0 )
      {
        v10 = 0;
        *a1 = v19;
        return v10;
      }
      v8 = v19;
      v13 = (NCRYPT_HANDLE *)(v19 + 24);
      PersistedKey = NCryptCreatePersistedKey(*(_QWORD *)(v19 + 16), (NCRYPT_KEY_HANDLE *)(v19 + 24), a2, 0, 0, 0);
      v10 = PersistedKey;
      if ( PersistedKey >= 0 )
      {
        v15 = -1;
        do
          ++v15;
        while ( *(_WORD *)&pbInput[2 * v15] );
        v16 = NCryptSetProperty(*v13, L"ParameterSetName", pbInput, 2 * v15 + 2, 0);
        v10 = v16;
        if ( v16 >= 0 )
        {
          v17 = NCryptFinalizeKey(*v13, 0);
          v10 = v17;
          if ( v17 >= 0 )
          {
            *a1 = v8;
            return v10;
          }
          v11 = (unsigned int)v17;
          v12 = 205;
        }
        else
        {
          v11 = (unsigned int)v16;
          v12 = 196;
        }
      }
      else
      {
        v11 = (unsigned int)PersistedKey;
        v12 = 184;
      }
    }
    else
    {
      v8 = v19;
      v11 = (unsigned int)v9;
      v12 = 158;
    }
  }
  else
  {
    v10 = -2146893785;
    v11 = 2148073511LL;
    v12 = 147;
  }
  DebugTraceError(v11, "status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tlskem.c", v12);
  if ( v8 )
    SslpFreeKemKey(v8);
  return v10;
}

```

## disassembly

```asm
0x180021b60  push    rbx
0x180021b62  push    rbp
0x180021b63  push    rsi
0x180021b64  push    rdi
0x180021b65  push    r14
0x180021b67  push    r15
0x180021b69  sub     rsp, 38h
0x180021b6d  xor     r15d, r15d
0x180021b70  movzx   eax, r9w
0x180021b74  mov     [rsp+68h+arg_0], r15
0x180021b79  mov     rbp, rdx
0x180021b7c  mov     rsi, rcx
0x180021b7f  mov     edi, r15d
0x180021b82  test    rcx, rcx
0x180021b85  jz      loc_180021C74
0x180021b8b  mov     ecx, 70001h
0x180021b90  cmp     r8d, ecx
0x180021b93  jnz     loc_180021C74
0x180021b99  lea     r9, [rsp+68h+arg_0]
0x180021b9e  mov     r8d, ecx
0x180021ba1  movzx   edx, ax
0x180021ba4  call    SslpCreateBaseKemKeyStruct
0x180021ba9  mov     ebx, eax
0x180021bab  test    eax, eax
0x180021bad  jns     short loc_180021BC1
0x180021baf  mov     rdi, [rsp+68h+arg_0]
0x180021bb4  mov     ecx, eax
0x180021bb6  mov     r9d, 9Eh
0x180021bbc  jmp     loc_180021C84
0x180021bc1  test    [rsp+68h+arg_28], 2
0x180021bc9  jz      short loc_180021BDB
0x180021bcb  mov     rax, [rsp+68h+arg_0]
0x180021bd0  mov     ebx, r15d
0x180021bd3  mov     [rsi], rax
0x180021bd6  jmp     loc_180021CA4
0x180021bdb  mov     rdi, [rsp+68h+arg_0]
0x180021be0  xor     r9d, r9d; pszKeyName
0x180021be3  mov     [rsp+68h+dwFlags], r15d; dwFlags
0x180021be8  mov     r8, rbp; pszAlgId
0x180021beb  mov     [rsp+68h+dwLegacyKeySpec], r15d; dwLegacyKeySpec
0x180021bf0  mov     rcx, [rdi+10h]; hProvider
0x180021bf4  lea     r14, [rdi+18h]
0x180021bf8  mov     rdx, r14; phKey
0x180021bfb  call    cs:__imp_NCryptCreatePersistedKey
0x180021c01  mov     ebx, eax
0x180021c03  test    eax, eax
0x180021c05  jns     short loc_180021C11
0x180021c07  mov     ecx, eax
0x180021c09  mov     r9d, 0B8h
0x180021c0f  jmp     short loc_180021C84
0x180021c11  mov     r8, [rsp+68h+pbInput]; pbInput
0x180021c19  or      r9, 0FFFFFFFFFFFFFFFFh
0x180021c1d  inc     r9
0x180021c20  cmp     [r8+r9*2], r15w
0x180021c25  jnz     short loc_180021C1D
0x180021c27  mov     rcx, [r14]; hObject
0x180021c2a  lea     r9d, ds:2[r9*2]; cbInput
0x180021c32  lea     rdx, aParametersetna; "ParameterSetName"
0x180021c39  mov     [rsp+68h+dwLegacyKeySpec], r15d; dwFlags
0x180021c3e  call    cs:__imp_NCryptSetProperty
0x180021c44  mov     ebx, eax
0x180021c46  test    eax, eax
0x180021c48  jns     short loc_180021C54
0x180021c4a  mov     ecx, eax
0x180021c4c  mov     r9d, 0C4h
0x180021c52  jmp     short loc_180021C84
0x180021c54  mov     rcx, [r14]; hKey
0x180021c57  xor     edx, edx; dwFlags
0x180021c59  call    cs:__imp_NCryptFinalizeKey
0x180021c5f  mov     ebx, eax
0x180021c61  test    eax, eax
0x180021c63  jns     short loc_180021C6F
0x180021c65  mov     ecx, eax
0x180021c67  mov     r9d, 0CDh
0x180021c6d  jmp     short loc_180021C84
0x180021c6f  mov     [rsi], rdi
0x180021c72  jmp     short loc_180021CA4
0x180021c74  mov     ebx, 80090027h
0x180021c79  mov     ecx, 80090027h
0x180021c7e  mov     r9d, 93h
0x180021c84  lea     rdx, aStatus_0; "status"
0x180021c8b  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180021c92  call    DebugTraceError
0x180021c97  test    rdi, rdi
0x180021c9a  jz      short loc_180021CA4
0x180021c9c  mov     rcx, rdi
0x180021c9f  call    SslpFreeKemKey
0x180021ca4  mov     eax, ebx
0x180021ca6  add     rsp, 38h
0x180021caa  pop     r15
0x180021cac  pop     r14
0x180021cae  pop     rdi
0x180021caf  pop     rsi
0x180021cb0  pop     rbp
0x180021cb1  pop     rbx
0x180021cb2  retn
```
