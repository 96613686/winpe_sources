# DwSetEapUserInfo

- ea: `0x1800c19ec`
- end: `0x1800c1c70`
- name: `DwSetEapUserInfo`
- size: `644`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x18007a430`

## callees

- `0x1800c13d4`
- `0x1800c17d4`
- `0x1800c18a0`
- `0x1800c19bc`
- `0x1800c19ec`
- `0x1800decee`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800c1b12`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800c1b12`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c1c4b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c1c4b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800c1a87`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800c1b65`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800c1a87`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800c1b65`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800c1ae3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800c1bd1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800c1c59`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800c1ae3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800c1bd1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800c1c59`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c1a95`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c1b73`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c1a95`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c1b73`

## pseudocode

```c
__int64 __fastcall DwSetEapUserInfo(int a1, __int128 *a2, const void *a3, unsigned int a4, int a5, int a6, int a7)
{
  unsigned int *v7; // rdi
  size_t v8; // r15
  const void *v9; // r12
  __int128 *v10; // r14
  DWORD EapInfo; // ebx
  unsigned int v12; // esi
  char *v13; // rax
  void *v14; // rsi
  DWORD LastError; // eax
  __int128 v16; // xmm0
  unsigned int v17; // r14d
  unsigned int *v18; // r15
  void *v19; // rbx
  char *i; // rcx
  unsigned int *v21; // rax
  unsigned int *v22; // r12
  unsigned int *j; // rsi
  __int64 v24; // rdx
  unsigned int v26; // [rsp+40h] [rbp-20h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-18h] BYREF
  void *Src; // [rsp+50h] [rbp-10h] BYREF

  v7 = 0;
  v8 = a4;
  Src = 0;
  v9 = a3;
  v26 = 0;
  v10 = a2;
  hKey = 0;
  if ( !a2 )
  {
    EapInfo = 0;
    goto LABEL_34;
  }
  EapInfo = DwGetEapInfo(a1, a6, (unsigned int)&Src, (unsigned int)&v26, (__int64)&hKey);
  if ( EapInfo )
  {
    v7 = (unsigned int *)Src;
    goto LABEL_34;
  }
  v7 = (unsigned int *)Src;
  v12 = v26;
  if ( a5 )
  {
    if ( v26 >= 4 )
    {
      if ( *(_DWORD *)Src == 827343173 )
      {
LABEL_15:
        v17 = 0;
        v18 = (unsigned int *)((char *)Src + v26);
        v19 = Src;
        for ( i = (char *)Src; i < (char *)v18; i += (unsigned int)(*((_DWORD *)i + 6) + 32) )
        {
          if ( *((_DWORD *)i + 6) >= 0xFFFFFFE0 || v17 + ((*((_DWORD *)i + 6) + 39) & 0xFFFFFFF8) < v17 )
          {
            EapInfo = -2147024362;
            goto LABEL_34;
          }
          v17 += (*((_DWORD *)i + 6) + 39) & 0xFFFFFFF8;
        }
        v21 = (unsigned int *)LocalAlloc(0x40u, v17);
        v22 = v21;
        if ( v21 )
        {
          for ( j = v21; v7 < v18; j = (unsigned int *)((char *)j + ((v24 + 39) & 0xFFFFFFFFFFFFFFF8uLL)) )
          {
            memcpy_0(j, v7, v7[6] + 32LL);
            *j = 844120389;
            v24 = v7[6];
            v7 = (unsigned int *)((char *)v7 + v24 + 32);
          }
          v26 = v17;
          v7 = v22;
          v12 = v17;
          if ( v19 )
            LocalFree(v19);
        }
        else
        {
          EapInfo = GetLastError();
          if ( EapInfo )
            goto LABEL_34;
        }
        v10 = a2;
        if ( !a5 )
        {
          LODWORD(v8) = a4;
          v9 = a3;
          goto LABEL_31;
        }
LABEL_29:
        LastError = DwRemoveEapUserInfo((_DWORD)v10, (_DWORD)v7, (unsigned int)&v26, (_DWORD)hKey, 1, a7);
        goto LABEL_9;
      }
      if ( *(_DWORD *)Src == 844120389 )
        goto LABEL_29;
    }
    LastError = RegDeleteValueW(hKey, L"EapInfo");
    goto LABEL_9;
  }
  if ( v26 >= 4 )
  {
    if ( *(_DWORD *)Src != 827343173 )
    {
      if ( *(_DWORD *)Src != 844120389 )
        goto LABEL_7;
LABEL_31:
      LastError = DwReplaceEapUserInfo(v10, v9, (unsigned int)v8, v7, v12, hKey, a7);
      goto LABEL_9;
    }
    goto LABEL_15;
  }
LABEL_7:
  v13 = (char *)LocalAlloc(0x40u, (v8 + 39) & 0xFFFFFFFFFFFFFFF8uLL);
  v14 = v13;
  if ( !v13 )
  {
    LastError = GetLastError();
LABEL_9:
    EapInfo = LastError;
    goto LABEL_34;
  }
  v16 = *v10;
  *((_DWORD *)v13 + 6) = v8;
  *(_DWORD *)v13 = 844120389;
  *(_OWORD *)(v13 + 8) = v16;
  *((_DWORD *)v13 + 1) = a7;
  memcpy_0(v13 + 28, v9, v8);
  EapInfo = DwSetEapInfo(hKey, v14, ((_DWORD)v8 + 39) & 0xFFFFFFF8);
  LocalFree(v14);
LABEL_34:
  if ( hKey )
    RegCloseKey(hKey);
  if ( v7 )
    LocalFree(v7);
  return EapInfo;
}

```

## disassembly

```asm
0x1800c19ec  mov     r11, rsp
0x1800c19ef  mov     [r11+20h], r9d
0x1800c19f3  mov     [r11+18h], r8
0x1800c19f7  mov     [r11+10h], rdx
0x1800c19fb  push    rbp
0x1800c19fc  push    rbx
0x1800c19fd  push    rsi
0x1800c19fe  push    rdi
0x1800c19ff  push    r12
0x1800c1a01  push    r14
0x1800c1a03  push    r15
0x1800c1a05  mov     rbp, rsp
0x1800c1a08  sub     rsp, 60h
0x1800c1a0c  xor     edi, edi
0x1800c1a0e  mov     r15d, r9d
0x1800c1a11  mov     [rbp+Src], rdi
0x1800c1a15  mov     r12, r8
0x1800c1a18  mov     [rbp+var_20], edi
0x1800c1a1b  mov     r14, rdx
0x1800c1a1e  mov     [rbp+hKey], rdi
0x1800c1a22  test    rdx, rdx
0x1800c1a25  jz      loc_1800C1C40
0x1800c1a2b  mov     edx, [rbp+arg_28]
0x1800c1a2e  lea     rax, [rbp+hKey]
0x1800c1a32  lea     r9, [rbp+var_20]
0x1800c1a36  mov     [r11-78h], rax
0x1800c1a3a  lea     r8, [rbp+Src]
0x1800c1a3e  call    DwGetEapInfo
0x1800c1a43  mov     ebx, eax
0x1800c1a45  test    eax, eax
0x1800c1a47  jnz     loc_1800C1C3A
0x1800c1a4d  cmp     [rbp+arg_20], edi
0x1800c1a50  mov     rdi, [rbp+Src]
0x1800c1a54  mov     esi, [rbp+var_20]
0x1800c1a57  jnz     loc_1800C1AEE
0x1800c1a5d  cmp     esi, 4
0x1800c1a60  jb      short loc_1800C1A7A
0x1800c1a62  cmp     dword ptr [rdi], 31504145h
0x1800c1a68  jz      loc_1800C1B1A
0x1800c1a6e  cmp     dword ptr [rdi], 32504145h
0x1800c1a74  jz      loc_1800C1C10
0x1800c1a7a  lea     rdx, [r15+27h]
0x1800c1a7e  mov     ecx, 40h ; '@'; uFlags
0x1800c1a83  and     rdx, 0FFFFFFFFFFFFFFF8h; uBytes
0x1800c1a87  call    cs:__imp_LocalAlloc
0x1800c1a8d  mov     rsi, rax
0x1800c1a90  test    rax, rax
0x1800c1a93  jnz     short loc_1800C1AA2
0x1800c1a95  call    cs:__imp_GetLastError
0x1800c1a9b  mov     ebx, eax
0x1800c1a9d  jmp     loc_1800C1C42
0x1800c1aa2  movups  xmm0, xmmword ptr [r14]
0x1800c1aa6  lea     rcx, [rsi+1Ch]; void *
0x1800c1aaa  mov     [rsi+18h], r15d
0x1800c1aae  mov     r8, r15; Size
0x1800c1ab1  mov     dword ptr [rsi], 32504145h
0x1800c1ab7  movdqu  xmmword ptr [rax+8], xmm0
0x1800c1abc  mov     eax, [rbp+arg_30]
0x1800c1abf  mov     rdx, r12; Src
0x1800c1ac2  mov     [rsi+4], eax
0x1800c1ac5  call    memcpy_0
0x1800c1aca  mov     rcx, [rbp+hKey]
0x1800c1ace  lea     r8d, [r15+27h]
0x1800c1ad2  and     r8d, 0FFFFFFF8h
0x1800c1ad6  mov     rdx, rsi
0x1800c1ad9  call    DwSetEapInfo
0x1800c1ade  mov     rcx, rsi; hMem
0x1800c1ae1  mov     ebx, eax
0x1800c1ae3  call    cs:__imp_LocalFree
0x1800c1ae9  jmp     loc_1800C1C42
0x1800c1aee  cmp     esi, 4
0x1800c1af1  jb      short loc_1800C1B07
0x1800c1af3  cmp     dword ptr [rdi], 31504145h
0x1800c1af9  jz      short loc_1800C1B1A
0x1800c1afb  cmp     dword ptr [rdi], 32504145h
0x1800c1b01  jz      loc_1800C1BE1
0x1800c1b07  mov     rcx, [rbp+hKey]; hKey
0x1800c1b0b  lea     rdx, aEapinfo; "EapInfo"
0x1800c1b12  call    cs:__imp_RegDeleteValueW
0x1800c1b18  jmp     short loc_1800C1A9B
0x1800c1b1a  xor     r14d, r14d
0x1800c1b1d  mov     r15d, esi
0x1800c1b20  add     r15, rdi
0x1800c1b23  mov     rbx, rdi
0x1800c1b26  mov     rcx, rdi
0x1800c1b29  cmp     rcx, r15
0x1800c1b2c  jnb     short loc_1800C1B5D
0x1800c1b2e  mov     edx, [rcx+18h]
0x1800c1b31  add     edx, 20h ; ' '
0x1800c1b34  cmp     edx, 20h ; ' '
0x1800c1b37  jb      short loc_1800C1B53
0x1800c1b39  lea     r8d, [rdx+7]
0x1800c1b3d  and     r8d, 0FFFFFFF8h
0x1800c1b41  add     r8d, r14d
0x1800c1b44  cmp     r8d, r14d
0x1800c1b47  jb      short loc_1800C1B53
0x1800c1b49  mov     eax, edx
0x1800c1b4b  mov     r14d, r8d
0x1800c1b4e  add     rcx, rax
0x1800c1b51  jmp     short loc_1800C1B29
0x1800c1b53  mov     ebx, 80070216h
0x1800c1b58  jmp     loc_1800C1C42
0x1800c1b5d  mov     edx, r14d; uBytes
0x1800c1b60  mov     ecx, 40h ; '@'; uFlags
0x1800c1b65  call    cs:__imp_LocalAlloc
0x1800c1b6b  mov     r12, rax
0x1800c1b6e  test    rax, rax
0x1800c1b71  jnz     short loc_1800C1B84
0x1800c1b73  call    cs:__imp_GetLastError
0x1800c1b79  mov     ebx, eax
0x1800c1b7b  test    eax, eax
0x1800c1b7d  jz      short loc_1800C1BD7
0x1800c1b7f  jmp     loc_1800C1C42
0x1800c1b84  mov     rsi, r12
0x1800c1b87  cmp     rbx, r15
0x1800c1b8a  jnb     short loc_1800C1BBF
0x1800c1b8c  mov     r8d, [rdi+18h]
0x1800c1b90  mov     rdx, rdi; Src
0x1800c1b93  add     r8, 20h ; ' '; Size
0x1800c1b97  mov     rcx, rsi; void *
0x1800c1b9a  call    memcpy_0
0x1800c1b9f  mov     dword ptr [rsi], 32504145h
0x1800c1ba5  mov     edx, [rdi+18h]
0x1800c1ba8  add     rdi, 20h ; ' '
0x1800c1bac  add     rdi, rdx
0x1800c1baf  lea     rax, [rdx+27h]
0x1800c1bb3  and     rax, 0FFFFFFFFFFFFFFF8h
0x1800c1bb7  add     rsi, rax
0x1800c1bba  cmp     rdi, r15
0x1800c1bbd  jb      short loc_1800C1B8C
0x1800c1bbf  mov     [rbp+var_20], r14d
0x1800c1bc3  mov     rdi, r12
0x1800c1bc6  mov     esi, r14d
0x1800c1bc9  test    rbx, rbx
0x1800c1bcc  jz      short loc_1800C1BD7
0x1800c1bce  mov     rcx, rbx; hMem
0x1800c1bd1  call    cs:__imp_LocalFree
0x1800c1bd7  cmp     [rbp+arg_20], 0
0x1800c1bdb  mov     r14, [rbp+arg_8]
0x1800c1bdf  jz      short loc_1800C1C08
0x1800c1be1  mov     eax, [rbp+arg_30]
0x1800c1be4  lea     r8, [rbp+var_20]
0x1800c1be8  mov     r9, [rbp+hKey]
0x1800c1bec  mov     rdx, rdi
0x1800c1bef  mov     dword ptr [rsp+60h+var_38], eax
0x1800c1bf3  mov     rcx, r14
0x1800c1bf6  mov     [rsp+60h+var_40], 1
0x1800c1bfe  call    DwRemoveEapUserInfo
0x1800c1c03  jmp     loc_1800C1A9B
0x1800c1c08  mov     r15d, [rbp+arg_18]
0x1800c1c0c  mov     r12, [rbp+arg_10]
0x1800c1c10  mov     eax, [rbp+arg_30]
0x1800c1c13  mov     r9, rdi
0x1800c1c16  mov     [rsp+60h+var_30], eax
0x1800c1c1a  mov     r8d, r15d
0x1800c1c1d  mov     rax, [rbp+hKey]
0x1800c1c21  mov     rdx, r12
0x1800c1c24  mov     [rsp+60h+var_38], rax
0x1800c1c29  mov     rcx, r14
0x1800c1c2c  mov     [rsp+60h+var_40], esi
0x1800c1c30  call    DwReplaceEapUserInfo
0x1800c1c35  jmp     loc_1800C1A9B
0x1800c1c3a  mov     rdi, [rbp+Src]
0x1800c1c3e  jmp     short loc_1800C1C42
0x1800c1c40  xor     ebx, ebx
0x1800c1c42  mov     rcx, [rbp+hKey]; hKey
0x1800c1c46  test    rcx, rcx
0x1800c1c49  jz      short loc_1800C1C51
0x1800c1c4b  call    cs:__imp_RegCloseKey
0x1800c1c51  test    rdi, rdi
0x1800c1c54  jz      short loc_1800C1C5F
0x1800c1c56  mov     rcx, rdi; hMem
0x1800c1c59  call    cs:__imp_LocalFree
0x1800c1c5f  mov     eax, ebx
0x1800c1c61  add     rsp, 60h
0x1800c1c65  pop     r15
0x1800c1c67  pop     r14
0x1800c1c69  pop     r12
0x1800c1c6b  pop     rdi
0x1800c1c6c  pop     rsi
0x1800c1c6d  pop     rbx
0x1800c1c6e  pop     rbp
0x1800c1c6f  retn
```
