# DwGetEapUserInfo

- ea: `0x180024c10`
- end: `0x180024e98`
- name: `DwGetEapUserInfo`
- size: `648`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180019890`

## callees

- `0x180024a50`
- `0x180024c10`
- `0x180027386`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180024cd2`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180024cd2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180024e71`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180024e71`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180024e31`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180024e5b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180024e31`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180024e5b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180024d33`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180024d33`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024d4b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024d4b`

## pseudocode

```c
__int64 __fastcall DwGetEapUserInfo(int a1, void *a2, _DWORD *a3, _QWORD *a4, int a5, int a6)
{
  _QWORD *v6; // r15
  void *v8; // rbp
  DWORD EapInfo; // ebx
  unsigned int v10; // edi
  unsigned int *v11; // rsi
  unsigned int v12; // r15d
  unsigned int *v13; // r12
  char *v14; // rbp
  char *i; // rcx
  unsigned int *v16; // rax
  unsigned int *v17; // r13
  unsigned int v18; // ecx
  unsigned int *v19; // rdx
  __int64 v20; // rax
  _DWORD *v21; // rdi
  unsigned int *v22; // rdi
  unsigned int *v23; // rsi
  __int64 v24; // rdx
  void *Src; // [rsp+30h] [rbp-48h] BYREF
  HKEY hKey[8]; // [rsp+38h] [rbp-40h] BYREF
  unsigned int v29; // [rsp+90h] [rbp+18h] BYREF
  _QWORD *v30; // [rsp+98h] [rbp+20h]

  v30 = a4;
  Src = 0;
  v6 = a4;
  v29 = 0;
  hKey[0] = 0;
  v8 = a2;
  if ( !a3 )
    return (DWORD)-2147024809;
  if ( !a4 )
  {
    EapInfo = 0;
    *a3 = 0;
    return EapInfo;
  }
  EapInfo = DwGetEapInfo(a1, a5, (unsigned int)&Src, (unsigned int)&v29, (__int64)hKey);
  if ( EapInfo || (v10 = v29) == 0 )
  {
    v11 = (unsigned int *)Src;
    goto LABEL_39;
  }
  v11 = (unsigned int *)Src;
  if ( v29 < 4 )
    goto LABEL_10;
  if ( *(_DWORD *)Src == 827343173 )
  {
    v12 = 0;
    v13 = (unsigned int *)((char *)Src + v29);
    v14 = (char *)Src;
    for ( i = (char *)Src; i < (char *)v13; i += (unsigned int)(*((_DWORD *)i + 6) + 32) )
    {
      if ( *((_DWORD *)i + 6) >= 0xFFFFFFE0 || v12 + ((*((_DWORD *)i + 6) + 39) & 0xFFFFFFF8) < v12 )
      {
        EapInfo = -2147024362;
        goto LABEL_39;
      }
      v12 += (*((_DWORD *)i + 6) + 39) & 0xFFFFFFF8;
    }
    v16 = (unsigned int *)LocalAlloc(0x40u, v12);
    v17 = v16;
    if ( v16 )
    {
      EapInfo = 0;
      v22 = v11;
      v23 = v16;
      if ( v14 < (char *)v13 )
      {
        do
        {
          memcpy_0(v23, v22, v22[6] + 32LL);
          *v23 = 844120389;
          v24 = v22[6];
          v22 = (unsigned int *)((char *)v22 + v24 + 32);
          v23 = (unsigned int *)((char *)v23 + ((v24 + 39) & 0xFFFFFFFFFFFFFFF8uLL));
        }
        while ( v22 < v13 );
      }
      v11 = v17;
      v10 = v12;
      if ( v14 )
      {
        LocalFree(v14);
LABEL_21:
        v8 = a2;
        v6 = v30;
        goto LABEL_22;
      }
    }
    else
    {
      EapInfo = GetLastError();
    }
    if ( EapInfo )
      goto LABEL_39;
    goto LABEL_21;
  }
  if ( *(_DWORD *)Src != 844120389 )
  {
LABEL_10:
    RegDeleteValueW(hKey[0], L"EapInfo");
LABEL_11:
    *a3 = 0;
    goto LABEL_39;
  }
LABEL_22:
  v18 = 0;
  v19 = v11;
  if ( !v10 )
    goto LABEL_11;
  do
  {
    v20 = *v6 - *((_QWORD *)v19 + 1);
    if ( *v6 == *((_QWORD *)v19 + 1) )
      v20 = v6[1] - *((_QWORD *)v19 + 2);
    if ( !v20 && a6 == v19[1] )
      break;
    v18 += (v19[6] + 39) & 0xFFFFFFF8;
    v19 = (unsigned int *)((char *)v11 + v18);
  }
  while ( v18 < v10 );
  if ( v18 >= v10 )
    goto LABEL_11;
  v21 = v19 + 6;
  if ( v8 && *a3 >= *v21 )
    memcpy_0(v8, v19 + 7, (unsigned int)*v21);
  else
    EapInfo = 603;
  *a3 = *v21;
LABEL_39:
  if ( v11 )
    LocalFree(v11);
  if ( hKey[0] )
    RegCloseKey(hKey[0]);
  return EapInfo;
}

```

## disassembly

```asm
0x180024c10  mov     rax, rsp
0x180024c13  mov     [rax+8], rbx
0x180024c17  mov     [rax+20h], r9
0x180024c1b  mov     [rax+10h], rdx
0x180024c1f  push    rbp
0x180024c20  push    rsi
0x180024c21  push    rdi
0x180024c22  push    r12
0x180024c24  push    r13
0x180024c26  push    r14
0x180024c28  push    r15
0x180024c2a  sub     rsp, 40h
0x180024c2e  mov     qword ptr [rax-48h], 0
0x180024c36  mov     r15, r9
0x180024c39  mov     dword ptr [rax+18h], 0
0x180024c40  mov     r14, r8
0x180024c43  mov     qword ptr [rax-40h], 0
0x180024c4b  mov     rbp, rdx
0x180024c4e  test    r8, r8
0x180024c51  jnz     short loc_180024C5D
0x180024c53  mov     ebx, 80070057h
0x180024c58  jmp     loc_180024E7D
0x180024c5d  test    r9, r9
0x180024c60  jnz     short loc_180024C6C
0x180024c62  xor     ebx, ebx
0x180024c64  mov     [r8], ebx
0x180024c67  jmp     loc_180024E7D
0x180024c6c  mov     edx, [rsp+78h+arg_20]
0x180024c73  lea     rax, [rsp+78h+hKey]
0x180024c78  lea     r9, [rsp+78h+arg_10]
0x180024c80  mov     [rsp+78h+var_58], rax
0x180024c85  lea     r8, [rsp+78h+Src]
0x180024c8a  call    DwGetEapInfo
0x180024c8f  mov     ebx, eax
0x180024c91  test    eax, eax
0x180024c93  jnz     loc_180024E4E
0x180024c99  mov     edi, [rsp+78h+arg_10]
0x180024ca0  test    edi, edi
0x180024ca2  jz      loc_180024E4E
0x180024ca8  mov     rsi, [rsp+78h+Src]
0x180024cad  cmp     edi, 4
0x180024cb0  jb      short loc_180024CC6
0x180024cb2  cmp     dword ptr [rsi], 31504145h
0x180024cb8  jz      short loc_180024CEA
0x180024cba  cmp     dword ptr [rsi], 32504145h
0x180024cc0  jz      loc_180024D71
0x180024cc6  mov     rcx, [rsp+78h+hKey]; hKey
0x180024ccb  lea     rdx, aEapinfo; "EapInfo"
0x180024cd2  call    cs:__imp_RegDeleteValueW
0x180024cd9  nop     dword ptr [rax+rax+00h]
0x180024cde  mov     dword ptr [r14], 0
0x180024ce5  jmp     loc_180024E53
0x180024cea  xor     r15d, r15d
0x180024ced  lea     r12, [rsi+rdi]
0x180024cf1  mov     rbp, rsi
0x180024cf4  mov     rcx, rsi
0x180024cf7  cmp     rcx, r12
0x180024cfa  jnb     short loc_180024D2B
0x180024cfc  mov     edx, [rcx+18h]
0x180024cff  add     edx, 20h ; ' '
0x180024d02  cmp     edx, 20h ; ' '
0x180024d05  jb      short loc_180024D21
0x180024d07  lea     r8d, [rdx+7]
0x180024d0b  and     r8d, 0FFFFFFF8h
0x180024d0f  add     r8d, r15d
0x180024d12  cmp     r8d, r15d
0x180024d15  jb      short loc_180024D21
0x180024d17  mov     eax, edx
0x180024d19  mov     r15d, r8d
0x180024d1c  add     rcx, rax
0x180024d1f  jmp     short loc_180024CF7
0x180024d21  mov     ebx, 80070216h
0x180024d26  jmp     loc_180024E53
0x180024d2b  mov     edx, r15d; uBytes
0x180024d2e  mov     ecx, 40h ; '@'; uFlags
0x180024d33  call    cs:__imp_LocalAlloc
0x180024d3a  nop     dword ptr [rax+rax+00h]
0x180024d3f  mov     r13, rax
0x180024d42  test    rax, rax
0x180024d45  jnz     loc_180024DDF
0x180024d4b  call    cs:__imp_GetLastError
0x180024d52  nop     dword ptr [rax+rax+00h]
0x180024d57  mov     ebx, eax
0x180024d59  test    ebx, ebx
0x180024d5b  jnz     loc_180024E53
0x180024d61  mov     rbp, [rsp+78h+arg_8]
0x180024d69  mov     r15, [rsp+78h+arg_18]
0x180024d71  xor     ecx, ecx
0x180024d73  mov     rdx, rsi
0x180024d76  test    edi, edi
0x180024d78  jz      loc_180024CDE
0x180024d7e  mov     r8d, [rsp+78h+arg_28]
0x180024d86  mov     rax, [r15]
0x180024d89  sub     rax, [rdx+8]
0x180024d8d  jnz     short loc_180024D97
0x180024d8f  mov     rax, [r15+8]
0x180024d93  sub     rax, [rdx+10h]
0x180024d97  test    rax, rax
0x180024d9a  jnz     short loc_180024DA2
0x180024d9c  cmp     r8d, [rdx+4]
0x180024da0  jz      short loc_180024DB6
0x180024da2  mov     eax, [rdx+18h]
0x180024da5  add     eax, 27h ; '''
0x180024da8  and     eax, 0FFFFFFF8h
0x180024dab  add     ecx, eax
0x180024dad  mov     edx, ecx
0x180024daf  add     rdx, rsi
0x180024db2  cmp     ecx, edi
0x180024db4  jb      short loc_180024D86
0x180024db6  cmp     ecx, edi
0x180024db8  jnb     loc_180024CDE
0x180024dbe  lea     rdi, [rdx+18h]
0x180024dc2  test    rbp, rbp
0x180024dc5  jz      short loc_180024E42
0x180024dc7  mov     eax, [rdi]
0x180024dc9  cmp     [r14], eax
0x180024dcc  jb      short loc_180024E42
0x180024dce  mov     r8d, eax; Size
0x180024dd1  add     rdx, 1Ch; Src
0x180024dd5  mov     rcx, rbp; void *
0x180024dd8  call    memcpy_0
0x180024ddd  jmp     short loc_180024E47
0x180024ddf  xor     ebx, ebx
0x180024de1  mov     rdi, rbp
0x180024de4  mov     rsi, r13
0x180024de7  cmp     rbp, r12
0x180024dea  jnb     short loc_180024E1F
0x180024dec  mov     r8d, [rdi+18h]
0x180024df0  mov     rdx, rdi; Src
0x180024df3  add     r8, 20h ; ' '; Size
0x180024df7  mov     rcx, rsi; void *
0x180024dfa  call    memcpy_0
0x180024dff  mov     dword ptr [rsi], 32504145h
0x180024e05  mov     edx, [rdi+18h]
0x180024e08  add     rdi, 20h ; ' '
0x180024e0c  add     rdi, rdx
0x180024e0f  lea     rax, [rdx+27h]
0x180024e13  and     rax, 0FFFFFFFFFFFFFFF8h
0x180024e17  add     rsi, rax
0x180024e1a  cmp     rdi, r12
0x180024e1d  jb      short loc_180024DEC
0x180024e1f  mov     rsi, r13
0x180024e22  mov     edi, r15d
0x180024e25  test    rbp, rbp
0x180024e28  jz      loc_180024D59
0x180024e2e  mov     rcx, rbp; hMem
0x180024e31  call    cs:__imp_LocalFree
0x180024e38  nop     dword ptr [rax+rax+00h]
0x180024e3d  jmp     loc_180024D61
0x180024e42  mov     ebx, 25Bh
0x180024e47  mov     eax, [rdi]
0x180024e49  mov     [r14], eax
0x180024e4c  jmp     short loc_180024E53
0x180024e4e  mov     rsi, [rsp+78h+Src]
0x180024e53  test    rsi, rsi
0x180024e56  jz      short loc_180024E67
0x180024e58  mov     rcx, rsi; hMem
0x180024e5b  call    cs:__imp_LocalFree
0x180024e62  nop     dword ptr [rax+rax+00h]
0x180024e67  mov     rcx, [rsp+78h+hKey]; hKey
0x180024e6c  test    rcx, rcx
0x180024e6f  jz      short loc_180024E7D
0x180024e71  call    cs:__imp_RegCloseKey
0x180024e78  nop     dword ptr [rax+rax+00h]
0x180024e7d  mov     eax, ebx
0x180024e7f  mov     rbx, [rsp+78h+arg_0]
0x180024e87  add     rsp, 40h
0x180024e8b  pop     r15
0x180024e8d  pop     r14
0x180024e8f  pop     r13
0x180024e91  pop     r12
0x180024e93  pop     rdi
0x180024e94  pop     rsi
0x180024e95  pop     rbp
0x180024e96  retn
```
