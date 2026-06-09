# DwSetEapUserInfo

- ea: `0x180024358`
- end: `0x1800245dc`
- name: `DwSetEapUserInfo`
- size: `644`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x18001f670`

## callees

- `0x180023d40`
- `0x180024140`
- `0x18002420c`
- `0x180024328`
- `0x180024358`
- `0x1800263b6`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18002447e`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18002447e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800245b7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800245b7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002444f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002453d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800245c5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002444f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002453d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800245c5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800243f3`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800244d1`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800243f3`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800244d1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024401`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800244df`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024401`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800244df`

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
0x180024358  mov     r11, rsp
0x18002435b  mov     [r11+20h], r9d
0x18002435f  mov     [r11+18h], r8
0x180024363  mov     [r11+10h], rdx
0x180024367  push    rbp
0x180024368  push    rbx
0x180024369  push    rsi
0x18002436a  push    rdi
0x18002436b  push    r12
0x18002436d  push    r14
0x18002436f  push    r15
0x180024371  mov     rbp, rsp
0x180024374  sub     rsp, 60h
0x180024378  xor     edi, edi
0x18002437a  mov     r15d, r9d
0x18002437d  mov     [rbp+Src], rdi
0x180024381  mov     r12, r8
0x180024384  mov     [rbp+var_20], edi
0x180024387  mov     r14, rdx
0x18002438a  mov     [rbp+hKey], rdi
0x18002438e  test    rdx, rdx
0x180024391  jz      loc_1800245AC
0x180024397  mov     edx, [rbp+arg_28]
0x18002439a  lea     rax, [rbp+hKey]
0x18002439e  lea     r9, [rbp+var_20]
0x1800243a2  mov     [r11-78h], rax
0x1800243a6  lea     r8, [rbp+Src]
0x1800243aa  call    DwGetEapInfo
0x1800243af  mov     ebx, eax
0x1800243b1  test    eax, eax
0x1800243b3  jnz     loc_1800245A6
0x1800243b9  cmp     [rbp+arg_20], edi
0x1800243bc  mov     rdi, [rbp+Src]
0x1800243c0  mov     esi, [rbp+var_20]
0x1800243c3  jnz     loc_18002445A
0x1800243c9  cmp     esi, 4
0x1800243cc  jb      short loc_1800243E6
0x1800243ce  cmp     dword ptr [rdi], 31504145h
0x1800243d4  jz      loc_180024486
0x1800243da  cmp     dword ptr [rdi], 32504145h
0x1800243e0  jz      loc_18002457C
0x1800243e6  lea     rdx, [r15+27h]
0x1800243ea  mov     ecx, 40h ; '@'; uFlags
0x1800243ef  and     rdx, 0FFFFFFFFFFFFFFF8h; uBytes
0x1800243f3  call    cs:__imp_LocalAlloc
0x1800243f9  mov     rsi, rax
0x1800243fc  test    rax, rax
0x1800243ff  jnz     short loc_18002440E
0x180024401  call    cs:__imp_GetLastError
0x180024407  mov     ebx, eax
0x180024409  jmp     loc_1800245AE
0x18002440e  movups  xmm0, xmmword ptr [r14]
0x180024412  lea     rcx, [rsi+1Ch]; void *
0x180024416  mov     [rsi+18h], r15d
0x18002441a  mov     r8, r15; Size
0x18002441d  mov     dword ptr [rsi], 32504145h
0x180024423  movdqu  xmmword ptr [rax+8], xmm0
0x180024428  mov     eax, [rbp+arg_30]
0x18002442b  mov     rdx, r12; Src
0x18002442e  mov     [rsi+4], eax
0x180024431  call    memcpy_0
0x180024436  mov     rcx, [rbp+hKey]
0x18002443a  lea     r8d, [r15+27h]
0x18002443e  and     r8d, 0FFFFFFF8h
0x180024442  mov     rdx, rsi
0x180024445  call    DwSetEapInfo
0x18002444a  mov     rcx, rsi; hMem
0x18002444d  mov     ebx, eax
0x18002444f  call    cs:__imp_LocalFree
0x180024455  jmp     loc_1800245AE
0x18002445a  cmp     esi, 4
0x18002445d  jb      short loc_180024473
0x18002445f  cmp     dword ptr [rdi], 31504145h
0x180024465  jz      short loc_180024486
0x180024467  cmp     dword ptr [rdi], 32504145h
0x18002446d  jz      loc_18002454D
0x180024473  mov     rcx, [rbp+hKey]; hKey
0x180024477  lea     rdx, aEapinfo; "EapInfo"
0x18002447e  call    cs:__imp_RegDeleteValueW
0x180024484  jmp     short loc_180024407
0x180024486  xor     r14d, r14d
0x180024489  mov     r15d, esi
0x18002448c  add     r15, rdi
0x18002448f  mov     rbx, rdi
0x180024492  mov     rcx, rdi
0x180024495  cmp     rcx, r15
0x180024498  jnb     short loc_1800244C9
0x18002449a  mov     edx, [rcx+18h]
0x18002449d  add     edx, 20h ; ' '
0x1800244a0  cmp     edx, 20h ; ' '
0x1800244a3  jb      short loc_1800244BF
0x1800244a5  lea     r8d, [rdx+7]
0x1800244a9  and     r8d, 0FFFFFFF8h
0x1800244ad  add     r8d, r14d
0x1800244b0  cmp     r8d, r14d
0x1800244b3  jb      short loc_1800244BF
0x1800244b5  mov     eax, edx
0x1800244b7  mov     r14d, r8d
0x1800244ba  add     rcx, rax
0x1800244bd  jmp     short loc_180024495
0x1800244bf  mov     ebx, 80070216h
0x1800244c4  jmp     loc_1800245AE
0x1800244c9  mov     edx, r14d; uBytes
0x1800244cc  mov     ecx, 40h ; '@'; uFlags
0x1800244d1  call    cs:__imp_LocalAlloc
0x1800244d7  mov     r12, rax
0x1800244da  test    rax, rax
0x1800244dd  jnz     short loc_1800244F0
0x1800244df  call    cs:__imp_GetLastError
0x1800244e5  mov     ebx, eax
0x1800244e7  test    eax, eax
0x1800244e9  jz      short loc_180024543
0x1800244eb  jmp     loc_1800245AE
0x1800244f0  mov     rsi, r12
0x1800244f3  cmp     rbx, r15
0x1800244f6  jnb     short loc_18002452B
0x1800244f8  mov     r8d, [rdi+18h]
0x1800244fc  mov     rdx, rdi; Src
0x1800244ff  add     r8, 20h ; ' '; Size
0x180024503  mov     rcx, rsi; void *
0x180024506  call    memcpy_0
0x18002450b  mov     dword ptr [rsi], 32504145h
0x180024511  mov     edx, [rdi+18h]
0x180024514  add     rdi, 20h ; ' '
0x180024518  add     rdi, rdx
0x18002451b  lea     rax, [rdx+27h]
0x18002451f  and     rax, 0FFFFFFFFFFFFFFF8h
0x180024523  add     rsi, rax
0x180024526  cmp     rdi, r15
0x180024529  jb      short loc_1800244F8
0x18002452b  mov     [rbp+var_20], r14d
0x18002452f  mov     rdi, r12
0x180024532  mov     esi, r14d
0x180024535  test    rbx, rbx
0x180024538  jz      short loc_180024543
0x18002453a  mov     rcx, rbx; hMem
0x18002453d  call    cs:__imp_LocalFree
0x180024543  cmp     [rbp+arg_20], 0
0x180024547  mov     r14, [rbp+arg_8]
0x18002454b  jz      short loc_180024574
0x18002454d  mov     eax, [rbp+arg_30]
0x180024550  lea     r8, [rbp+var_20]
0x180024554  mov     r9, [rbp+hKey]
0x180024558  mov     rdx, rdi
0x18002455b  mov     dword ptr [rsp+60h+var_38], eax
0x18002455f  mov     rcx, r14
0x180024562  mov     [rsp+60h+var_40], 1
0x18002456a  call    DwRemoveEapUserInfo
0x18002456f  jmp     loc_180024407
0x180024574  mov     r15d, [rbp+arg_18]
0x180024578  mov     r12, [rbp+arg_10]
0x18002457c  mov     eax, [rbp+arg_30]
0x18002457f  mov     r9, rdi
0x180024582  mov     [rsp+60h+var_30], eax
0x180024586  mov     r8d, r15d
0x180024589  mov     rax, [rbp+hKey]
0x18002458d  mov     rdx, r12
0x180024590  mov     [rsp+60h+var_38], rax
0x180024595  mov     rcx, r14
0x180024598  mov     [rsp+60h+var_40], esi
0x18002459c  call    DwReplaceEapUserInfo
0x1800245a1  jmp     loc_180024407
0x1800245a6  mov     rdi, [rbp+Src]
0x1800245aa  jmp     short loc_1800245AE
0x1800245ac  xor     ebx, ebx
0x1800245ae  mov     rcx, [rbp+hKey]; hKey
0x1800245b2  test    rcx, rcx
0x1800245b5  jz      short loc_1800245BD
0x1800245b7  call    cs:__imp_RegCloseKey
0x1800245bd  test    rdi, rdi
0x1800245c0  jz      short loc_1800245CB
0x1800245c2  mov     rcx, rdi; hMem
0x1800245c5  call    cs:__imp_LocalFree
0x1800245cb  mov     eax, ebx
0x1800245cd  add     rsp, 60h
0x1800245d1  pop     r15
0x1800245d3  pop     r14
0x1800245d5  pop     r12
0x1800245d7  pop     rdi
0x1800245d8  pop     rsi
0x1800245d9  pop     rbx
0x1800245da  pop     rbp
0x1800245db  retn
```
