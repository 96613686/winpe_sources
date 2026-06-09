# DwSetEapUserInfo

- ea: `0x1800250d4`
- end: `0x180025392`
- name: `DwSetEapUserInfo`
- size: `702`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x180020100`

## callees

- `0x180024a50`
- `0x180024ea0`
- `0x180024f6c`
- `0x18002509c`
- `0x1800250d4`
- `0x180027386`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18002520c`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18002520c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180025360`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180025360`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800251d7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800252e0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180025374`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800251d7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800252e0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180025374`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002516f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180025268`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002516f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180025268`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025183`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002527c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025183`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002527c`

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
0x1800250d4  mov     r11, rsp
0x1800250d7  mov     [r11+20h], r9d
0x1800250db  mov     [r11+18h], r8
0x1800250df  mov     [r11+10h], rdx
0x1800250e3  push    rbp
0x1800250e4  push    rbx
0x1800250e5  push    rsi
0x1800250e6  push    rdi
0x1800250e7  push    r12
0x1800250e9  push    r14
0x1800250eb  push    r15
0x1800250ed  mov     rbp, rsp
0x1800250f0  sub     rsp, 60h
0x1800250f4  xor     edi, edi
0x1800250f6  mov     r15d, r9d
0x1800250f9  mov     [rbp+Src], rdi
0x1800250fd  mov     r12, r8
0x180025100  mov     [rbp+var_20], edi
0x180025103  mov     r14, rdx
0x180025106  mov     [rbp+hKey], rdi
0x18002510a  test    rdx, rdx
0x18002510d  jz      loc_180025355
0x180025113  mov     edx, [rbp+arg_28]
0x180025116  lea     rax, [rbp+hKey]
0x18002511a  lea     r9, [rbp+var_20]
0x18002511e  mov     [r11-78h], rax
0x180025122  lea     r8, [rbp+Src]
0x180025126  call    DwGetEapInfo
0x18002512b  mov     ebx, eax
0x18002512d  test    eax, eax
0x18002512f  jnz     loc_18002534F
0x180025135  cmp     [rbp+arg_20], edi
0x180025138  mov     rdi, [rbp+Src]
0x18002513c  mov     esi, [rbp+var_20]
0x18002513f  jnz     loc_1800251E8
0x180025145  cmp     esi, 4
0x180025148  jb      short loc_180025162
0x18002514a  cmp     dword ptr [rdi], 31504145h
0x180025150  jz      loc_18002521D
0x180025156  cmp     dword ptr [rdi], 32504145h
0x18002515c  jz      loc_180025325
0x180025162  lea     rdx, [r15+27h]
0x180025166  mov     ecx, 40h ; '@'; uFlags
0x18002516b  and     rdx, 0FFFFFFFFFFFFFFF8h; uBytes
0x18002516f  call    cs:__imp_LocalAlloc
0x180025176  nop     dword ptr [rax+rax+00h]
0x18002517b  mov     rsi, rax
0x18002517e  test    rax, rax
0x180025181  jnz     short loc_180025196
0x180025183  call    cs:__imp_GetLastError
0x18002518a  nop     dword ptr [rax+rax+00h]
0x18002518f  mov     ebx, eax
0x180025191  jmp     loc_180025357
0x180025196  movups  xmm0, xmmword ptr [r14]
0x18002519a  lea     rcx, [rsi+1Ch]; void *
0x18002519e  mov     [rsi+18h], r15d
0x1800251a2  mov     r8, r15; Size
0x1800251a5  mov     dword ptr [rsi], 32504145h
0x1800251ab  movdqu  xmmword ptr [rax+8], xmm0
0x1800251b0  mov     eax, [rbp+arg_30]
0x1800251b3  mov     rdx, r12; Src
0x1800251b6  mov     [rsi+4], eax
0x1800251b9  call    memcpy_0
0x1800251be  mov     rcx, [rbp+hKey]
0x1800251c2  lea     r8d, [r15+27h]
0x1800251c6  and     r8d, 0FFFFFFF8h
0x1800251ca  mov     rdx, rsi
0x1800251cd  call    DwSetEapInfo
0x1800251d2  mov     rcx, rsi; hMem
0x1800251d5  mov     ebx, eax
0x1800251d7  call    cs:__imp_LocalFree
0x1800251de  nop     dword ptr [rax+rax+00h]
0x1800251e3  jmp     loc_180025357
0x1800251e8  cmp     esi, 4
0x1800251eb  jb      short loc_180025201
0x1800251ed  cmp     dword ptr [rdi], 31504145h
0x1800251f3  jz      short loc_18002521D
0x1800251f5  cmp     dword ptr [rdi], 32504145h
0x1800251fb  jz      loc_1800252F6
0x180025201  mov     rcx, [rbp+hKey]; hKey
0x180025205  lea     rdx, aEapinfo; "EapInfo"
0x18002520c  call    cs:__imp_RegDeleteValueW
0x180025213  nop     dword ptr [rax+rax+00h]
0x180025218  jmp     loc_18002518F
0x18002521d  xor     r14d, r14d
0x180025220  mov     r15d, esi
0x180025223  add     r15, rdi
0x180025226  mov     rbx, rdi
0x180025229  mov     rcx, rdi
0x18002522c  cmp     rcx, r15
0x18002522f  jnb     short loc_180025260
0x180025231  mov     edx, [rcx+18h]
0x180025234  add     edx, 20h ; ' '
0x180025237  cmp     edx, 20h ; ' '
0x18002523a  jb      short loc_180025256
0x18002523c  lea     r8d, [rdx+7]
0x180025240  and     r8d, 0FFFFFFF8h
0x180025244  add     r8d, r14d
0x180025247  cmp     r8d, r14d
0x18002524a  jb      short loc_180025256
0x18002524c  mov     eax, edx
0x18002524e  mov     r14d, r8d
0x180025251  add     rcx, rax
0x180025254  jmp     short loc_18002522C
0x180025256  mov     ebx, 80070216h
0x18002525b  jmp     loc_180025357
0x180025260  mov     edx, r14d; uBytes
0x180025263  mov     ecx, 40h ; '@'; uFlags
0x180025268  call    cs:__imp_LocalAlloc
0x18002526f  nop     dword ptr [rax+rax+00h]
0x180025274  mov     r12, rax
0x180025277  test    rax, rax
0x18002527a  jnz     short loc_180025293
0x18002527c  call    cs:__imp_GetLastError
0x180025283  nop     dword ptr [rax+rax+00h]
0x180025288  mov     ebx, eax
0x18002528a  test    eax, eax
0x18002528c  jz      short loc_1800252EC
0x18002528e  jmp     loc_180025357
0x180025293  mov     rsi, r12
0x180025296  cmp     rbx, r15
0x180025299  jnb     short loc_1800252CE
0x18002529b  mov     r8d, [rdi+18h]
0x18002529f  mov     rdx, rdi; Src
0x1800252a2  add     r8, 20h ; ' '; Size
0x1800252a6  mov     rcx, rsi; void *
0x1800252a9  call    memcpy_0
0x1800252ae  mov     dword ptr [rsi], 32504145h
0x1800252b4  mov     edx, [rdi+18h]
0x1800252b7  add     rdi, 20h ; ' '
0x1800252bb  add     rdi, rdx
0x1800252be  lea     rax, [rdx+27h]
0x1800252c2  and     rax, 0FFFFFFFFFFFFFFF8h
0x1800252c6  add     rsi, rax
0x1800252c9  cmp     rdi, r15
0x1800252cc  jb      short loc_18002529B
0x1800252ce  mov     [rbp+var_20], r14d
0x1800252d2  mov     rdi, r12
0x1800252d5  mov     esi, r14d
0x1800252d8  test    rbx, rbx
0x1800252db  jz      short loc_1800252EC
0x1800252dd  mov     rcx, rbx; hMem
0x1800252e0  call    cs:__imp_LocalFree
0x1800252e7  nop     dword ptr [rax+rax+00h]
0x1800252ec  cmp     [rbp+arg_20], 0
0x1800252f0  mov     r14, [rbp+arg_8]
0x1800252f4  jz      short loc_18002531D
0x1800252f6  mov     eax, [rbp+arg_30]
0x1800252f9  lea     r8, [rbp+var_20]
0x1800252fd  mov     r9, [rbp+hKey]
0x180025301  mov     rdx, rdi
0x180025304  mov     dword ptr [rsp+60h+var_38], eax
0x180025308  mov     rcx, r14
0x18002530b  mov     [rsp+60h+var_40], 1
0x180025313  call    DwRemoveEapUserInfo
0x180025318  jmp     loc_18002518F
0x18002531d  mov     r15d, [rbp+arg_18]
0x180025321  mov     r12, [rbp+arg_10]
0x180025325  mov     eax, [rbp+arg_30]
0x180025328  mov     r9, rdi
0x18002532b  mov     [rsp+60h+var_30], eax
0x18002532f  mov     r8d, r15d
0x180025332  mov     rax, [rbp+hKey]
0x180025336  mov     rdx, r12
0x180025339  mov     [rsp+60h+var_38], rax
0x18002533e  mov     rcx, r14
0x180025341  mov     [rsp+60h+var_40], esi
0x180025345  call    DwReplaceEapUserInfo
0x18002534a  jmp     loc_18002518F
0x18002534f  mov     rdi, [rbp+Src]
0x180025353  jmp     short loc_180025357
0x180025355  xor     ebx, ebx
0x180025357  mov     rcx, [rbp+hKey]; hKey
0x18002535b  test    rcx, rcx
0x18002535e  jz      short loc_18002536C
0x180025360  call    cs:__imp_RegCloseKey
0x180025367  nop     dword ptr [rax+rax+00h]
0x18002536c  test    rdi, rdi
0x18002536f  jz      short loc_180025380
0x180025371  mov     rcx, rdi; hMem
0x180025374  call    cs:__imp_LocalFree
0x18002537b  nop     dword ptr [rax+rax+00h]
0x180025380  mov     eax, ebx
0x180025382  add     rsp, 60h
0x180025386  pop     r15
0x180025388  pop     r14
0x18002538a  pop     r12
0x18002538c  pop     rdi
0x18002538d  pop     rsi
0x18002538e  pop     rbx
0x18002538f  pop     rbp
0x180025390  retn
```
