# WriteFontToSpoolFile

- ea: `0x180084b3c`
- end: `0x180084ed5`
- name: `WriteFontToSpoolFile`
- size: `921`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18005c640`
- `0x1800850c8`

## callees

- `0x180045548`
- `0x180046018`
- `0x18007f800`
- `0x180080604`
- `0x180084b3c`
- `0x1800937e8`
- `0x1800a68d4`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180084c2a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180084dc9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180084c2a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180084dc9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180084ce2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180084e82`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180084ce2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180084e82`
- `win32u!NtGdiGetUFIPathname` at `0x180084bdd`
- `win32u!NtGdiGetUFIPathname` at `0x180084c6c`
- `win32u!NtGdiGetUFIPathname` at `0x180084bdd`
- `win32u!NtGdiGetUFIPathname` at `0x180084c6c`

## pseudocode

```c
_BOOL8 __fastcall WriteFontToSpoolFile(__int64 a1, __int64 a2, int a3)
{
  int v3; // r13d
  BOOL v7; // esi
  unsigned int v8; // eax
  void *v9; // rbx
  BOOL v10; // edi
  int v11; // eax
  WCHAR *v13; // rbx
  int v14; // ecx
  __int64 v15; // rdi
  unsigned int v17; // eax
  __int64 v18; // r14
  _DWORD *v19; // rax
  _DWORD *v20; // r15
  char *v21; // rsi
  char *v22; // r12
  __int64 v23; // rbx
  __int64 v24; // rcx
  SIZE_T *p_uBytes; // [rsp+30h] [rbp-D0h]
  HLOCAL v26; // [rsp+38h] [rbp-C8h]
  SIZE_T uBytes; // [rsp+50h] [rbp-B0h] BYREF
  int v28; // [rsp+58h] [rbp-A8h] BYREF
  int v29; // [rsp+5Ch] [rbp-A4h] BYREF
  unsigned int v30; // [rsp+60h] [rbp-A0h]
  __int64 v31; // [rsp+68h] [rbp-98h]
  void *FileHandle[2]; // [rsp+70h] [rbp-90h] BYREF
  __int128 v33; // [rsp+80h] [rbp-80h]
  _OWORD v34[2]; // [rsp+90h] [rbp-70h] BYREF
  void *Src[10]; // [rsp+B0h] [rbp-50h]
  WCHAR SourceString[784]; // [rsp+100h] [rbp+0h] BYREF

  v3 = 0;
  v31 = a1;
  p_uBytes = &uBytes;
  v29 = 0;
  uBytes = 0;
  v28 = 0;
  v7 = 0;
  *(_OWORD *)FileHandle = 0;
  v33 = 0;
  v34[0] = 0;
  if ( !(unsigned int)NtGdiGetUFIPathname(a2, &v29, SourceString, (char *)&uBytes + 4, a3, &v28) )
    return v7;
  v8 = HIDWORD(uBytes);
  if ( HIDWORD(uBytes) == 1 )
  {
    if ( v28 )
    {
      v26 = LocalAlloc(0, (unsigned int)uBytes);
      v10 = v26 != 0;
      LODWORD(p_uBytes) = 0;
      v9 = v26;
      if ( !(unsigned int)NtGdiGetUFIPathname(a2, 0, 0, 0, a3, 0) )
        goto LABEL_12;
    }
    else
    {
      v9 = 0;
      v10 = bMapFileUNICODEClideSide(SourceString, FileHandle, SHIDWORD(uBytes)) != 0;
    }
    if ( !v10 )
      return v7;
    DWORD1(v34[0]) = HIDWORD(uBytes);
    LODWORD(v34[0]) = 0;
    if ( v28 )
    {
      v11 = uBytes;
    }
    else
    {
      v11 = DWORD2(v33);
      v9 = (void *)v33;
      LODWORD(uBytes) = DWORD2(v33);
    }
    DWORD2(v34[0]) = v11;
    LOBYTE(v7) = (unsigned int)WriteFontDataAsEMFComment(a1, 2, v34, 16, v9, v11, (_DWORD)p_uBytes) != 0;
    if ( !v28 )
    {
      vUnmapFileClideSide(FileHandle);
      return v7;
    }
    if ( !v9 )
      return v7;
LABEL_12:
    LocalFree(v9);
    return v7;
  }
  if ( HIDWORD(uBytes) > 3 )
    return 0;
  v13 = SourceString;
  LODWORD(uBytes) = 0;
  v14 = 1;
  LODWORD(v15) = 0;
  while ( (unsigned int)v15 < v8 )
  {
    if ( !v14 )
      goto LABEL_36;
    if ( !(unsigned int)bMapFileUNICODEClideSide(v13, (PHANDLE)&v34[2 * (unsigned int)v15 + 1], 1) )
    {
      v8 = HIDWORD(uBytes);
      v14 = 0;
      break;
    }
    while ( *v13++ )
      ;
    v17 = (unsigned int)Src[4 * (unsigned int)v15 + 1];
    if ( v17 < 0xFFFFFFFC )
    {
      if ( (unsigned int)uBytes + ((v17 + 3) & 0xFFFFFFFC) >= (unsigned int)uBytes )
      {
        LODWORD(uBytes) = uBytes + ((v17 + 3) & 0xFFFFFFFC);
        v14 = 1;
        goto LABEL_26;
      }
      LODWORD(uBytes) = -1;
    }
    v14 = 0;
LABEL_26:
    v8 = HIDWORD(uBytes);
    LODWORD(v15) = v15 + 1;
  }
  if ( v14 )
  {
    v18 = (4 * v8 + 15) & 0xFFFFFFF8;
    v30 = (4 * v8 + 15) & 0xFFFFFFF8;
    if ( (int)v18 + (int)uBytes >= (unsigned int)v18 )
    {
      v19 = LocalAlloc(0, (unsigned int)(v18 + uBytes));
      v20 = v19;
      if ( v19 )
      {
        v21 = (char *)v19 + v18;
        v22 = (char *)v19 + v18;
        memset_0(v19, 0, (unsigned int)v18);
        v15 = 0;
        if ( HIDWORD(uBytes) )
        {
          do
          {
            v23 = 4LL * (unsigned int)v15;
            v3 += (LODWORD(Src[v23 + 1]) + 3) & 0xFFFFFFFC;
            v20[v15 + 2] = v3;
            memcpy_0(v22, Src[v23], LODWORD(Src[v23 + 1]));
            v15 = (unsigned int)(v15 + 1);
            v22 += (LODWORD(Src[v23 + 1]) + 3) & 0xFFFFFFFC;
          }
          while ( (unsigned int)v15 < HIDWORD(uBytes) );
          LODWORD(v18) = v30;
        }
        v24 = v31;
        *v20 = 0;
        v20[1] = HIDWORD(uBytes);
        v7 = WriteFontDataAsEMFComment(v24, 4, v20, (unsigned int)v18, v21, uBytes, (unsigned int)&uBytes) != 0;
        LocalFree(v20);
      }
    }
  }
LABEL_36:
  while ( (_DWORD)v15 )
  {
    LODWORD(v15) = v15 - 1;
    vUnmapFileClideSide(&v34[2 * (unsigned int)v15 + 1]);
  }
  return v7;
}

```

## disassembly

```asm
0x180084b3c  mov     [rsp-8+arg_18], rbx
0x180084b41  push    rbp
0x180084b42  push    rsi
0x180084b43  push    rdi
0x180084b44  push    r12
0x180084b46  push    r13
0x180084b48  push    r14
0x180084b4a  push    r15
0x180084b4c  lea     rbp, [rsp-630h]
0x180084b54  sub     rsp, 730h
0x180084b5b  mov     rax, cs:__security_cookie
0x180084b62  xor     rax, rsp
0x180084b65  mov     [rbp+660h+var_40], rax
0x180084b6c  xor     r13d, r13d
0x180084b6f  mov     [rsp+760h+var_6F8], rcx
0x180084b74  mov     [rsp+760h+var_718], r13
0x180084b79  lea     rax, [rsp+760h+uBytes]
0x180084b7e  mov     [rsp+760h+var_720], r13
0x180084b83  lea     r9, [rsp+760h+uBytes+4]
0x180084b88  xorps   xmm0, xmm0
0x180084b8b  mov     [rsp+760h+var_728], r13
0x180084b90  mov     [rsp+760h+var_730], rax
0x180084b95  mov     r14, rdx
0x180084b98  lea     rax, [rsp+760h+var_708]
0x180084b9d  mov     [rsp+760h+var_704], r13d
0x180084ba2  mov     [rsp+760h+var_738], rax
0x180084ba7  lea     rdx, [rsp+760h+var_704]
0x180084bac  mov     dword ptr [rsp+760h+var_740], r8d
0x180084bb1  mov     r15d, r8d
0x180084bb4  mov     r12, rcx
0x180084bb7  mov     dword ptr [rsp+760h+uBytes+4], r13d
0x180084bbc  lea     r8, [rbp+660h+SourceString]
0x180084bc0  mov     dword ptr [rsp+760h+uBytes], r13d
0x180084bc5  mov     rcx, r14
0x180084bc8  mov     [rsp+760h+var_708], r13d
0x180084bcd  mov     esi, r13d
0x180084bd0  movups  xmmword ptr [rsp+760h+FileHandle], xmm0
0x180084bd5  movups  [rbp+660h+var_6E0], xmm0
0x180084bd9  movups  [rbp+660h+var_6D0], xmm0
0x180084bdd  call    cs:__imp_NtGdiGetUFIPathname
0x180084be4  nop     dword ptr [rax+rax+00h]
0x180084be9  test    eax, eax
0x180084beb  jz      loc_180084EA8
0x180084bf1  mov     eax, dword ptr [rsp+760h+uBytes+4]
0x180084bf5  cmp     eax, 1
0x180084bf8  jnz     loc_180084D02
0x180084bfe  cmp     [rsp+760h+var_708], r13d
0x180084c03  jnz     short loc_180084C24
0x180084c05  mov     r8d, eax
0x180084c08  lea     rdx, [rsp+760h+FileHandle]; FileHandle
0x180084c0d  lea     rcx, [rbp+660h+SourceString]; SourceString
0x180084c11  mov     ebx, r13d
0x180084c14  call    bMapFileUNICODEClideSide
0x180084c19  test    eax, eax
0x180084c1b  mov     edi, r13d
0x180084c1e  setnz   dil
0x180084c22  jmp     short loc_180084C7C
0x180084c24  mov     edx, dword ptr [rsp+760h+uBytes]; uBytes
0x180084c28  xor     ecx, ecx; uFlags
0x180084c2a  call    cs:__imp_LocalAlloc
0x180084c31  nop     dword ptr [rax+rax+00h]
0x180084c36  mov     [rsp+760h+var_718], r13
0x180084c3b  mov     edi, r13d
0x180084c3e  mov     [rsp+760h+var_720], r13
0x180084c43  test    rax, rax
0x180084c46  mov     [rsp+760h+var_728], rax
0x180084c4b  mov     rcx, r14
0x180084c4e  setnz   dil
0x180084c52  mov     [rsp+760h+var_730], r13
0x180084c57  xor     r9d, r9d
0x180084c5a  mov     [rsp+760h+var_738], r13
0x180084c5f  xor     r8d, r8d
0x180084c62  mov     dword ptr [rsp+760h+var_740], r15d
0x180084c67  xor     edx, edx
0x180084c69  mov     rbx, rax
0x180084c6c  call    cs:__imp_NtGdiGetUFIPathname
0x180084c73  nop     dword ptr [rax+rax+00h]
0x180084c78  test    eax, eax
0x180084c7a  jz      short loc_180084CDF
0x180084c7c  test    edi, edi
0x180084c7e  jz      loc_180084EA8
0x180084c84  mov     eax, dword ptr [rsp+760h+uBytes+4]
0x180084c88  mov     dword ptr [rbp+660h+var_6D0+4], eax
0x180084c8b  mov     dword ptr [rbp+660h+var_6D0], r13d
0x180084c8f  cmp     [rsp+760h+var_708], r13d
0x180084c94  jnz     short loc_180084CA3
0x180084c96  mov     eax, dword ptr [rbp+660h+var_6E0+8]
0x180084c99  mov     rbx, qword ptr [rbp+660h+var_6E0]
0x180084c9d  mov     dword ptr [rsp+760h+uBytes], eax
0x180084ca1  jmp     short loc_180084CA7
0x180084ca3  mov     eax, dword ptr [rsp+760h+uBytes]
0x180084ca7  mov     r9d, 10h
0x180084cad  mov     dword ptr [rsp+760h+var_738], eax
0x180084cb1  lea     r8, [rbp+660h+var_6D0]
0x180084cb5  mov     dword ptr [rbp+660h+var_6D0+8], eax
0x180084cb8  mov     rcx, r12
0x180084cbb  mov     [rsp+760h+var_740], rbx
0x180084cc0  lea     edx, [r9-0Eh]
0x180084cc4  call    WriteFontDataAsEMFComment
0x180084cc9  test    eax, eax
0x180084ccb  setnz   sil
0x180084ccf  cmp     [rsp+760h+var_708], r13d
0x180084cd4  jz      short loc_180084CF3
0x180084cd6  test    rbx, rbx
0x180084cd9  jz      loc_180084EA8
0x180084cdf  mov     rcx, rbx; hMem
0x180084ce2  call    cs:__imp_LocalFree
0x180084ce9  nop     dword ptr [rax+rax+00h]
0x180084cee  jmp     loc_180084EA8
0x180084cf3  lea     rcx, [rsp+760h+FileHandle]
0x180084cf8  call    vUnmapFileClideSide
0x180084cfd  jmp     loc_180084EA8
0x180084d02  cmp     eax, 3
0x180084d05  jbe     short loc_180084D0E
0x180084d07  xor     eax, eax
0x180084d09  jmp     loc_180084EAA
0x180084d0e  lea     rbx, [rbp+660h+SourceString]
0x180084d12  mov     dword ptr [rsp+760h+uBytes], r13d
0x180084d17  mov     ecx, 1
0x180084d1c  mov     edi, r13d
0x180084d1f  mov     r15d, 0FFFFFFFCh
0x180084d25  cmp     edi, eax
0x180084d27  jnb     short loc_180084D9C
0x180084d29  test    ecx, ecx
0x180084d2b  jz      loc_180084EA4
0x180084d31  mov     r14d, edi
0x180084d34  lea     rdx, [rbp+660h+var_6C0]
0x180084d38  shl     r14, 5
0x180084d3c  mov     r8d, 1
0x180084d42  add     rdx, r14; FileHandle
0x180084d45  mov     rcx, rbx; SourceString
0x180084d48  call    bMapFileUNICODEClideSide
0x180084d4d  test    eax, eax
0x180084d4f  jz      short loc_180084D95
0x180084d51  movzx   eax, word ptr [rbx]
0x180084d54  add     rbx, 2
0x180084d58  test    ax, ax
0x180084d5b  jnz     short loc_180084D51
0x180084d5d  mov     eax, dword ptr [rbp+r14+660h+Size]
0x180084d62  cmp     eax, r15d
0x180084d65  jnb     short loc_180084D8A
0x180084d67  lea     edx, [rax+3]
0x180084d6a  and     edx, r15d
0x180084d6d  add     edx, dword ptr [rsp+760h+uBytes]
0x180084d71  cmp     edx, dword ptr [rsp+760h+uBytes]
0x180084d75  jb      short loc_180084D82
0x180084d77  mov     dword ptr [rsp+760h+uBytes], edx
0x180084d7b  mov     ecx, 1
0x180084d80  jmp     short loc_180084D8D
0x180084d82  mov     dword ptr [rsp+760h+uBytes], 0FFFFFFFFh
0x180084d8a  mov     ecx, r13d
0x180084d8d  mov     eax, dword ptr [rsp+760h+uBytes+4]
0x180084d91  inc     edi
0x180084d93  jmp     short loc_180084D25
0x180084d95  mov     eax, dword ptr [rsp+760h+uBytes+4]
0x180084d99  mov     ecx, r13d
0x180084d9c  test    ecx, ecx
0x180084d9e  jz      loc_180084EA4
0x180084da4  mov     ecx, dword ptr [rsp+760h+uBytes]
0x180084da8  lea     r14d, ds:0Fh[rax*4]
0x180084db0  and     r14d, 0FFFFFFF8h
0x180084db4  add     ecx, r14d
0x180084db7  mov     [rsp+760h+var_700], r14d
0x180084dbc  cmp     ecx, r14d
0x180084dbf  jb      loc_180084EA4
0x180084dc5  mov     edx, ecx; uBytes
0x180084dc7  xor     ecx, ecx; uFlags
0x180084dc9  call    cs:__imp_LocalAlloc
0x180084dd0  nop     dword ptr [rax+rax+00h]
0x180084dd5  mov     r15, rax
0x180084dd8  test    rax, rax
0x180084ddb  jz      loc_180084EA4
0x180084de1  lea     rsi, [r14+rax]
0x180084de5  mov     r8d, r14d; Size
0x180084de8  xor     edx, edx; Val
0x180084dea  mov     rcx, rax; void *
0x180084ded  mov     r12, rsi
0x180084df0  call    memset_0
0x180084df5  xor     edi, edi
0x180084df7  cmp     dword ptr [rsp+760h+uBytes+4], edi
0x180084dfb  jbe     short loc_180084E47
0x180084dfd  mov     r14d, 0FFFFFFFCh
0x180084e03  mov     ebx, edi
0x180084e05  mov     rcx, r12; void *
0x180084e08  shl     rbx, 5
0x180084e0c  mov     eax, dword ptr [rbp+rbx+660h+Size]
0x180084e10  add     eax, 3
0x180084e13  and     eax, r14d
0x180084e16  add     r13d, eax
0x180084e19  mov     [r15+rdi*4+8], r13d
0x180084e1e  mov     r8d, dword ptr [rbp+rbx+660h+Size]; Size
0x180084e23  mov     rdx, [rbp+rbx+660h+Src]; Src
0x180084e28  call    memcpy_0
0x180084e2d  mov     eax, dword ptr [rbp+rbx+660h+Size]
0x180084e31  inc     edi
0x180084e33  add     eax, 3
0x180084e36  and     rax, r14
0x180084e39  add     r12, rax
0x180084e3c  cmp     edi, dword ptr [rsp+760h+uBytes+4]
0x180084e40  jb      short loc_180084E03
0x180084e42  mov     r14d, [rsp+760h+var_700]
0x180084e47  mov     rcx, [rsp+760h+var_6F8]
0x180084e4c  xor     r13d, r13d
0x180084e4f  mov     [r15], r13d
0x180084e52  mov     r9d, r14d
0x180084e55  mov     eax, dword ptr [rsp+760h+uBytes+4]
0x180084e59  mov     r8, r15
0x180084e5c  mov     [r15+4], eax
0x180084e60  mov     eax, dword ptr [rsp+760h+uBytes]
0x180084e64  lea     edx, [r13+4]
0x180084e68  mov     dword ptr [rsp+760h+var_738], eax
0x180084e6c  mov     [rsp+760h+var_740], rsi
0x180084e71  call    WriteFontDataAsEMFComment
0x180084e76  test    eax, eax
0x180084e78  mov     esi, r13d
0x180084e7b  mov     rcx, r15; hMem
0x180084e7e  setnz   sil
0x180084e82  call    cs:__imp_LocalFree
0x180084e89  nop     dword ptr [rax+rax+00h]
0x180084e8e  jmp     short loc_180084EA4
0x180084e90  dec     edi
0x180084e92  lea     rax, [rbp+660h+var_6C0]
0x180084e96  mov     ecx, edi
0x180084e98  shl     rcx, 5
0x180084e9c  add     rcx, rax
0x180084e9f  call    vUnmapFileClideSide
0x180084ea4  test    edi, edi
0x180084ea6  jnz     short loc_180084E90
0x180084ea8  mov     eax, esi
0x180084eaa  mov     rcx, [rbp+660h+var_40]
0x180084eb1  xor     rcx, rsp; StackCookie
0x180084eb4  call    __security_check_cookie
0x180084eb9  mov     rbx, [rsp+760h+arg_18]
0x180084ec1  add     rsp, 730h
0x180084ec8  pop     r15
0x180084eca  pop     r14
0x180084ecc  pop     r13
0x180084ece  pop     r12
0x180084ed0  pop     rdi
0x180084ed1  pop     rsi
0x180084ed2  pop     rbp
0x180084ed3  retn
```
