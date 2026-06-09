# I_UrlCacheCreateCacheFile

- ea: `0x180007af0`
- end: `0x180007db9`
- name: `I_UrlCacheCreateCacheFile`
- size: `713`
- prototype: `HANDLE __fastcall(_WORD *Src, __int64, _WORD *, __int64, int)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x180004c90`

## callees

- `0x1800042e0`
- `0x1800068b0`
- `0x180007af0`
- `0x180008700`
- `0x180009030`
- `0x18000e2f0`
- `0x18000fb38`
- `0x18000fb7c`
- `0x18000fbc4`
- `0x1800174fc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007d6e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007d6e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007dab`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007dab`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180007cec`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180007cec`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180007d90`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180007d90`

## pseudocode

```c
HANDLE __fastcall I_UrlCacheCreateCacheFile(_WORD *Src, __int64 a2, _WORD *a3, __int64 a4, int a5)
{
  __int64 v8; // rbp
  __int64 v9; // r8
  __int64 v10; // rcx
  HANDLE FileW; // r15
  __int64 v12; // rbx
  WCHAR *v13; // rax
  WCHAR *v14; // r14
  size_t v16; // rdi
  __int128 v17; // xmm1
  WCHAR *v18; // rcx
  WCHAR v19; // ax
  __int128 v20; // xmm0
  __int128 v21; // xmm1
  __int64 v22; // r13
  DWORD dwFlagsAndAttributes; // edi
  DWORD v24; // esi
  DWORD LastError; // eax
  BCRYPT_HASH_HANDLE phHash[2]; // [rsp+48h] [rbp-B0h] BYREF
  __int64 v28; // [rsp+58h] [rbp-A0h]
  _OWORD v29[4]; // [rsp+60h] [rbp-98h] BYREF
  WCHAR v30; // [rsp+A0h] [rbp-58h]

  *(_OWORD *)phHash = 0;
  v28 = 0;
  CngRsa32Compat_MD5Init(phHash);
  v8 = -1;
  if ( a4 )
  {
    v9 = -1;
    do
      ++v9;
    while ( *(_WORD *)(a4 + 2 * v9) );
  }
  else
  {
    LODWORD(v9) = 0;
  }
  CngRsa32Compat_MD5Update(phHash, a4, (unsigned int)(2 * v9));
  CngRsa32Compat_MD5Final(phHash);
  I_UrlCacheBytesToWStr(v10, &phHash[1], v29);
  FileW = 0;
  if ( Src )
  {
    v12 = -1;
    do
      ++v12;
    while ( Src[v12] );
  }
  else
  {
    LODWORD(v12) = 0;
  }
  if ( a3 )
  {
    do
      ++v8;
    while ( a3[v8] );
  }
  else
  {
    LODWORD(v8) = 0;
  }
  v13 = (WCHAR *)PkiNonzeroAlloc(2LL * (unsigned int)(v12 + v8 + 42));
  v14 = v13;
  if ( v13 )
  {
    v16 = (unsigned int)v12;
    memcpy_0(v13, Src, v16 * 2);
    *(_OWORD *)&v14[v16] = *(_OWORD *)L"MetaData";
    v14[v16 + 8] = aMetadata[8];
    if ( !a5 || (unsigned int)I_CryptRecursiveCreateLowIntegrityDirectory(v14) )
    {
      v14[(unsigned int)(v12 + 8)] = 92;
      if ( (_DWORD)v8 )
        memcpy_0(&v14[(unsigned int)v12 + 9], a3, 2LL * (unsigned int)v8);
      v17 = v29[1];
      v18 = &v14[(unsigned int)v12 + (unsigned __int64)(unsigned int)v8];
      v19 = v30;
      *(_OWORD *)(v18 + 9) = v29[0];
      v20 = v29[2];
      *(_OWORD *)(v18 + 17) = v17;
      v21 = v29[3];
      *(_OWORD *)(v18 + 25) = v20;
      *(_OWORD *)(v18 + 33) = v21;
      v18[41] = v19;
      v22 = 0;
      dwFlagsAndAttributes = 4;
      v24 = -1073741824;
      if ( !a5 )
      {
        dwFlagsAndAttributes = 128;
        v24 = 0x80000000;
      }
      while ( 1 )
      {
        FileW = CreateFileW(v14, v24, a5 == 0, 0, (unsigned int)(a5 != 0) + 3, dwFlagsAndAttributes, 0);
        if ( FileW != (HANDLE)-1LL )
          break;
        LastError = GetLastError();
        if ( LastError == 32 )
        {
          if ( (unsigned int)v22 >= 6 )
            goto LABEL_32;
        }
        else
        {
          if ( LastError != 5 )
          {
            if ( LastError == 3 )
              LastError = 2;
LABEL_32:
            SetLastError(LastError);
            FileW = 0;
            break;
          }
          if ( (_DWORD)v22 )
            goto LABEL_32;
        }
        Sleep(*((_DWORD *)qword_18001B4D0 + v22));
        v22 = (unsigned int)(v22 + 1);
      }
    }
    else
    {
      PkiFree(v14);
      v14 = 0;
    }
  }
  PkiFree(v14);
  return FileW;
}

```

## disassembly

```asm
0x180007af0  push    rbx
0x180007af2  push    rbp
0x180007af3  push    rsi
0x180007af4  push    rdi
0x180007af5  push    r14
0x180007af7  push    r15
0x180007af9  sub     rsp, 0C8h
0x180007b00  mov     rax, cs:__security_cookie
0x180007b07  xor     rax, rsp
0x180007b0a  mov     [rsp+0F8h+var_48], rax
0x180007b12  mov     rsi, rcx
0x180007b15  mov     [rsp+0F8h+Src], r8
0x180007b1a  xorps   xmm0, xmm0
0x180007b1d  lea     rcx, [rsp+0F8h+phHash]; phHash
0x180007b22  xor     eax, eax
0x180007b24  mov     rbx, r9
0x180007b27  movups  xmmword ptr [rsp+0F8h+phHash], xmm0
0x180007b2c  mov     [rsp+0F8h+var_A0], rax
0x180007b31  mov     rdi, r8
0x180007b34  call    CngRsa32Compat_MD5Init
0x180007b39  mov     rbp, 0FFFFFFFFFFFFFFFFh
0x180007b40  test    rbx, rbx
0x180007b43  jz      loc_180007D5F
0x180007b49  mov     r8, rbp
0x180007b4c  nop     dword ptr [rax+00h]
0x180007b50  inc     r8
0x180007b53  cmp     word ptr [rbx+r8*2], 0
0x180007b59  jnz     short loc_180007B50
0x180007b5b  add     r8d, r8d
0x180007b5e  lea     rcx, [rsp+0F8h+phHash]
0x180007b63  mov     rdx, rbx
0x180007b66  call    CngRsa32Compat_MD5Update
0x180007b6b  lea     rcx, [rsp+0F8h+phHash]
0x180007b70  call    CngRsa32Compat_MD5Final
0x180007b75  lea     r8, [rsp+0F8h+var_98]
0x180007b7a  lea     rdx, [rsp+0F8h+phHash+8]
0x180007b7f  call    I_UrlCacheBytesToWStr
0x180007b84  xor     r15d, r15d
0x180007b87  test    rsi, rsi
0x180007b8a  jz      loc_180007D67
0x180007b90  mov     rbx, rbp
0x180007b93  inc     rbx
0x180007b96  cmp     [rsi+rbx*2], r15w
0x180007b9b  jnz     short loc_180007B93
0x180007b9d  test    rdi, rdi
0x180007ba0  jnz     loc_180007D50
0x180007ba6  xor     ebp, ebp
0x180007ba8  lea     ecx, [rbp+2Ah]
0x180007bab  add     ecx, ebx
0x180007bad  add     rcx, rcx; uBytes
0x180007bb0  call    PkiNonzeroAlloc
0x180007bb5  mov     r14, rax
0x180007bb8  test    rax, rax
0x180007bbb  jnz     short loc_180007BE8
0x180007bbd  mov     rcx, r14; hMem
0x180007bc0  call    PkiFree
0x180007bc5  mov     rax, r15
0x180007bc8  mov     rcx, [rsp+0F8h+var_48]
0x180007bd0  xor     rcx, rsp; StackCookie
0x180007bd3  call    __security_check_cookie
0x180007bd8  add     rsp, 0C8h
0x180007bdf  pop     r15
0x180007be1  pop     r14
0x180007be3  pop     rdi
0x180007be4  pop     rsi
0x180007be5  pop     rbp
0x180007be6  pop     rbx
0x180007be7  retn
0x180007be8  mov     [rsp+0F8h+arg_8], r12
0x180007bf0  mov     [rsp+0F8h+var_38], r13
0x180007bf8  mov     r13d, ebx
0x180007bfb  mov     rdx, rsi; Src
0x180007bfe  mov     rcx, r14; void *
0x180007c01  lea     rdi, ds:0[r13*2]
0x180007c09  mov     r8, rdi; Size
0x180007c0c  call    memcpy_0
0x180007c11  movups  xmm0, xmmword ptr cs:aMetadata; "MetaData"
0x180007c18  mov     r12d, [rsp+0F8h+arg_20]
0x180007c20  movups  xmmword ptr [rdi+r14], xmm0
0x180007c25  movzx   eax, word ptr cs:aMetadata+10h; ""
0x180007c2c  mov     [rdi+r14+10h], ax
0x180007c32  test    r12d, r12d
0x180007c35  jnz     loc_180007D2D
0x180007c3b  add     ebx, 8
0x180007c3e  mov     word ptr [r14+rbx*2], 5Ch ; '\'
0x180007c45  test    ebp, ebp
0x180007c47  jnz     loc_180007D10
0x180007c4d  movaps  xmm0, [rsp+0F8h+var_98]
0x180007c52  movaps  xmm1, [rsp+0F8h+var_88]
0x180007c57  mov     eax, ebp
0x180007c59  add     rax, r13
0x180007c5c  lea     rcx, [r14+rax*2]
0x180007c60  movzx   eax, [rsp+0F8h+var_58]
0x180007c68  movups  xmmword ptr [rcx+12h], xmm0
0x180007c6c  movaps  xmm0, [rsp+0F8h+var_78]
0x180007c74  movups  xmmword ptr [rcx+22h], xmm1
0x180007c78  movaps  xmm1, [rsp+0F8h+var_68]
0x180007c80  movups  xmmword ptr [rcx+32h], xmm0
0x180007c84  movups  xmmword ptr [rcx+42h], xmm1
0x180007c88  mov     [rcx+52h], ax
0x180007c8c  xor     r13d, r13d
0x180007c8f  mov     eax, 80h
0x180007c94  test    r12d, r12d
0x180007c97  mov     edi, 4
0x180007c9c  mov     esi, 0C0000000h
0x180007ca1  cmovz   edi, eax
0x180007ca4  xor     ebx, ebx
0x180007ca6  test    r12d, r12d
0x180007ca9  mov     eax, 80000000h
0x180007cae  setnz   bl
0x180007cb1  xor     ebp, ebp
0x180007cb3  add     ebx, 3
0x180007cb6  test    r12d, r12d
0x180007cb9  setz    bpl
0x180007cbd  test    r12d, r12d
0x180007cc0  lea     r12, qword_18001B4D0
0x180007cc7  cmovz   esi, eax
0x180007cca  nop     word ptr [rax+rax+00h]
0x180007cd0  mov     [rsp+0F8h+hTemplateFile], 0; hTemplateFile
0x180007cd9  xor     r9d, r9d; lpSecurityAttributes
0x180007cdc  mov     [rsp+0F8h+dwFlagsAndAttributes], edi; dwFlagsAndAttributes
0x180007ce0  mov     r8d, ebp; dwShareMode
0x180007ce3  mov     edx, esi; dwDesiredAccess
0x180007ce5  mov     [rsp+0F8h+dwCreationDisposition], ebx; dwCreationDisposition
0x180007ce9  mov     rcx, r14; lpFileName
0x180007cec  call    cs:__imp_CreateFileW
0x180007cf2  mov     r15, rax
0x180007cf5  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180007cf9  jz      short loc_180007D6E
0x180007cfb  mov     r12, [rsp+0F8h+arg_8]
0x180007d03  mov     r13, [rsp+0F8h+var_38]
0x180007d0b  jmp     loc_180007BBD
0x180007d10  mov     rdx, [rsp+0F8h+Src]; Src
0x180007d15  lea     rcx, [r13+9]
0x180007d19  mov     r8d, ebp
0x180007d1c  lea     rcx, [r14+rcx*2]; void *
0x180007d20  add     r8, r8; Size
0x180007d23  call    memcpy_0
0x180007d28  jmp     loc_180007C4D
0x180007d2d  mov     rcx, r14; lpFileName
0x180007d30  call    I_CryptRecursiveCreateLowIntegrityDirectory
0x180007d35  test    eax, eax
0x180007d37  jnz     loc_180007C3B
0x180007d3d  mov     rcx, r14; hMem
0x180007d40  call    PkiFree
0x180007d45  xor     r14d, r14d
0x180007d48  jmp     short loc_180007CFB
0x180007d50  inc     rbp
0x180007d53  cmp     [rdi+rbp*2], r15w
0x180007d58  jnz     short loc_180007D50
0x180007d5a  jmp     loc_180007BA8
0x180007d5f  xor     r8d, r8d
0x180007d62  jmp     loc_180007B5B
0x180007d67  xor     ebx, ebx
0x180007d69  jmp     loc_180007B9D
0x180007d6e  call    cs:__imp_GetLastError
0x180007d74  cmp     eax, 20h ; ' '
0x180007d77  jnz     short loc_180007D81
0x180007d79  cmp     r13d, 6
0x180007d7d  jb      short loc_180007D8C
0x180007d7f  jmp     short loc_180007DA9
0x180007d81  cmp     eax, 5
0x180007d84  jnz     short loc_180007D9E
0x180007d86  cmp     r13d, 1
0x180007d8a  jnb     short loc_180007DA9
0x180007d8c  mov     ecx, [r12+r13*4]; dwMilliseconds
0x180007d90  call    cs:__imp_Sleep
0x180007d96  inc     r13d
0x180007d99  jmp     loc_180007CD0
0x180007d9e  cmp     eax, 3
0x180007da1  mov     ecx, 2
0x180007da6  cmovz   eax, ecx
0x180007da9  mov     ecx, eax; dwErrCode
0x180007dab  call    cs:__imp_SetLastError
0x180007db1  xor     r15d, r15d
0x180007db4  jmp     loc_180007CFB
```
