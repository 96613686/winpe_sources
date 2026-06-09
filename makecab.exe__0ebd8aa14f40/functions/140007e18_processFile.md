# processFile

- ea: `0x140007e18`
- end: `0x140008187`
- name: `processFile`
- size: `879`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x140006a6c`

## callees

- `0x140006030`
- `0x140006590`
- `0x140006e0c`
- `0x140007e18`
- `0x140008190`
- `0x1400084d8`
- `0x140008f70`
- `0x140009938`
- `0x140009aac`
- `0x14000e412`
- `0x14000e450`

## import_xrefs

- `Cabinet!__imp_FCICreate` at `0x14000800d`
- `Cabinet!__imp_FCICreate` at `0x14000800d`
- `Cabinet!__imp_FCIAddFile` at `0x1400080d1`
- `Cabinet!__imp_FCIAddFile` at `0x1400080d1`
- `Cabinet!__imp_FCIFlushCabinet` at `0x14000813c`
- `Cabinet!__imp_FCIFlushCabinet` at `0x14000813c`
- `Cabinet!__imp_FCIDestroy` at `0x140008163`
- `Cabinet!__imp_FCIDestroy` at `0x140008163`

## string_xrefs

- `0x14000801c`: `FCICreate`

## pseudocode

```c
__int64 __fastcall processFile(__int64 a1, __int64 a2)
{
  __int64 v4; // r8
  CHAR ***v5; // rax
  CHAR *v6; // r9
  CHAR *v7; // r12
  __int64 v8; // r14
  int FileSize; // eax
  CHAR *JustFileNameAndExt; // r13
  __int64 v11; // r15
  __int64 v12; // r8
  char *v13; // r9
  __int64 v14; // rdx
  char *szCab; // rcx
  char *v16; // rax
  HFCI v17; // rax
  const char *v18; // r8
  _BYTE *v19; // rcx
  CHAR *v20; // rdx
  _BYTE *v21; // rax
  TCOMP typeCompress; // [rsp+70h] [rbp-90h]
  CCAB pccab; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v25[256]; // [rsp+3B0h] [rbp+2B0h] BYREF
  char pszDest[256]; // [rsp+4B0h] [rbp+3B0h] BYREF

  memset_0(&pccab, 0, sizeof(pccab));
  v5 = *(CHAR ****)(a1 + 8);
  *(_QWORD *)(a1 + 3128) = a1;
  *(_QWORD *)(a1 + 3136) = a2;
  v6 = (*v5)[1];
  v7 = **v5;
  if ( (!v6 || !*v6) && !(unsigned int)getCompressedFileName(a1, v25, v4, **v5, a2) )
    return 0;
  v8 = 256;
  if ( !(unsigned int)catDirAndFile(pszDest, DirectoryName, a2) )
    return 0;
  FileSize = getFileSize(v7, a2);
  if ( FileSize == -1 )
    return 0;
  *(_DWORD *)(a1 + 120) = FileSize;
  JustFileNameAndExt = (CHAR *)getJustFileNameAndExt(v7);
  if ( !JustFileNameAndExt )
    return 0;
  v11 = 2147483646;
  pccab.szDisk[0] = 0;
  v12 = 2147483646;
  v13 = pszDest;
  v14 = 256;
  szCab = pccab.szCab;
  do
  {
    if ( !v12 )
      break;
    if ( !*v13 )
      break;
    *szCab++ = *v13++;
    --v12;
    --v14;
  }
  while ( v14 );
  v16 = szCab - 1;
  if ( v14 )
    v16 = szCab;
  *v16 = 0;
  pccab.szCabPath[0] = 0;
  *(_QWORD *)&pccab.cb = 0;
  pccab.setID = 0;
  pccab.fFailOnIncompressible = 0;
  if ( !(unsigned int)setCabinetReserve(&pccab, a1, a2, v13) )
    return 0;
  *(_DWORD *)(a1 + 160) = 0;
  v17 = FCICreate(
          (PERF)(a1 + 96),
          fciFilePlaced,
          fciAlloc,
          fciFree,
          (PFNFCIOPEN)fciOpen,
          fciRead,
          fciWrite,
          fciClose,
          fciSeek,
          fciDelete,
          fciTempFile,
          &pccab,
          (void *)(a1 + 3128));
  *(_QWORD *)(a1 + 88) = v17;
  if ( !v17 )
  {
    v18 = "FCICreate";
    goto LABEL_25;
  }
  typeCompress = tcompFromSession(a1, a2);
  v19 = (_BYTE *)(a1 + 228);
  v20 = JustFileNameAndExt;
  do
  {
    if ( !v11 )
      break;
    if ( !*v20 )
      break;
    *v19++ = *v20++;
    --v11;
    --v8;
  }
  while ( v8 );
  v21 = v19 - 1;
  if ( v8 )
    v21 = v19;
  *v21 = 0;
  *(_DWORD *)(a1 + 132) = 1;
  *(_DWORD *)(a1 + 136) = 1;
  fciStatus(0, 0, 0, (void *)(a1 + 3128));
  if ( !FCIAddFile(
          *(HFCI *)(a1 + 88),
          v7,
          JustFileNameAndExt,
          0,
          fciGetNextCabinet_NOT,
          fciStatus,
          fciOpenInfo,
          typeCompress) )
  {
    if ( *(_DWORD *)(*(_QWORD *)(a1 + 3136) + 512LL) )
      return 0;
    v18 = "FCIAddFile";
LABEL_25:
    mapFCIError(a2, a1, v18, (_DWORD *)(a1 + 96));
    return 0;
  }
  if ( !FCIFlushCabinet(*(HFCI *)(a1 + 88), 0, fciGetNextCabinet_NOT, fciStatus) )
  {
    if ( *(_DWORD *)(*(_QWORD *)(a1 + 3136) + 512LL) )
      return 0;
    v18 = "FCIFlushCabinet";
    goto LABEL_25;
  }
  if ( !FCIDestroy(*(HFCI *)(a1 + 88)) )
  {
    v18 = "FCIDestroy";
    goto LABEL_25;
  }
  *(_QWORD *)(a1 + 88) = 0;
  return 1;
}

```

## disassembly

```asm
0x140007e18  mov     [rsp-8+arg_10], rbx
0x140007e1d  push    rbp
0x140007e1e  push    rsi
0x140007e1f  push    rdi
0x140007e20  push    r12
0x140007e22  push    r13
0x140007e24  push    r14
0x140007e26  push    r15
0x140007e28  lea     rbp, [rsp-4C0h]
0x140007e30  sub     rsp, 5C0h
0x140007e37  mov     rax, cs:__security_cookie
0x140007e3e  xor     rax, rsp
0x140007e41  mov     [rbp+4F0h+var_40], rax
0x140007e48  mov     rdi, rdx
0x140007e4b  mov     rbx, rcx
0x140007e4e  xor     edx, edx; Val
0x140007e50  lea     rcx, [rbp+4F0h+var_570]; void *
0x140007e54  mov     r8d, 324h; Size
0x140007e5a  call    memset_0
0x140007e5f  mov     rax, [rbx+8]
0x140007e63  xor     esi, esi
0x140007e65  mov     [rbx+0C38h], rbx
0x140007e6c  mov     [rbx+0C40h], rdi
0x140007e73  mov     rcx, [rax]
0x140007e76  mov     r9, [rcx+8]
0x140007e7a  mov     r12, [rcx]
0x140007e7d  test    r9, r9
0x140007e80  jz      short loc_140007E87
0x140007e82  cmp     [r9], sil
0x140007e85  jnz     short loc_140007EAD
0x140007e87  mov     r9, r12
0x140007e8a  mov     [rsp+5F0h+pfnopen], rdi
0x140007e8f  lea     rdx, [rbp+4F0h+var_240]
0x140007e96  mov     rcx, rbx
0x140007e99  call    getCompressedFileName
0x140007e9e  test    eax, eax
0x140007ea0  jz      loc_140008100
0x140007ea6  lea     r9, [rbp+4F0h+var_240]
0x140007ead  lea     rax, DirectoryName
0x140007eb4  mov     [rsp+5F0h+pfnread], rdi; __int64
0x140007eb9  mov     r14d, 100h
0x140007ebf  mov     [rsp+5F0h+pfnopen], rax; lpCurrentChar
0x140007ec4  mov     edx, r14d
0x140007ec7  lea     r8, [rbx+0B34h]
0x140007ece  lea     rcx, [rbp+4F0h+pszDest]; pszDest
0x140007ed5  call    catDirAndFile
0x140007eda  test    eax, eax
0x140007edc  jz      loc_140008100
0x140007ee2  mov     rdx, rdi
0x140007ee5  mov     rcx, r12
0x140007ee8  call    getFileSize
0x140007eed  cmp     eax, 0FFFFFFFFh
0x140007ef0  jz      loc_140008100
0x140007ef6  mov     rdx, rdi
0x140007ef9  mov     [rbx+78h], eax
0x140007efc  mov     rcx, r12; lpCurrentChar
0x140007eff  call    getJustFileNameAndExt
0x140007f04  mov     r13, rax
0x140007f07  test    rax, rax
0x140007f0a  jz      loc_140008100
0x140007f10  mov     r15d, 7FFFFFFEh
0x140007f16  mov     [rbp+4F0h+var_570.szDisk], sil
0x140007f1a  mov     r8d, r15d
0x140007f1d  lea     r9, [rbp+4F0h+pszDest]
0x140007f24  mov     edx, r14d
0x140007f27  lea     rcx, [rbp+4F0h+var_570.szCab]
0x140007f2e  test    r8, r8
0x140007f31  jz      short loc_140007F4B
0x140007f33  mov     al, [r9]
0x140007f36  test    al, al
0x140007f38  jz      short loc_140007F4B
0x140007f3a  mov     [rcx], al
0x140007f3c  inc     r9
0x140007f3f  inc     rcx
0x140007f42  dec     r8
0x140007f45  sub     rdx, 1
0x140007f49  jnz     short loc_140007F2E
0x140007f4b  test    rdx, rdx
0x140007f4e  lea     rax, [rcx-1]
0x140007f52  mov     r8, rdi
0x140007f55  mov     rdx, rbx
0x140007f58  cmovnz  rax, rcx
0x140007f5c  lea     rcx, [rbp+4F0h+var_570]
0x140007f60  mov     [rax], sil
0x140007f63  mov     [rbp+4F0h+var_570.szCabPath], sil
0x140007f6a  mov     qword ptr [rbp+4F0h+var_570.cb], rsi
0x140007f6e  mov     [rbp+4F0h+var_570.setID], si
0x140007f72  mov     [rbp+4F0h+var_570.fFailOnIncompressible], esi
0x140007f75  call    setCabinetReserve
0x140007f7a  test    eax, eax
0x140007f7c  jz      loc_140008100
0x140007f82  lea     rax, [rbx+0C38h]
0x140007f89  mov     [rbx+0A0h], esi
0x140007f8f  mov     [rsp+5F0h+pv], rax; pv
0x140007f94  lea     rsi, [rbx+60h]
0x140007f98  lea     rax, [rbp+4F0h+var_570]
0x140007f9c  mov     rcx, rsi; perf
0x140007f9f  mov     [rsp+5F0h+pccab], rax; pccab
0x140007fa4  lea     r9, fciFree; pfnf
0x140007fab  lea     rax, fciTempFile
0x140007fb2  mov     [rsp+5F0h+pfnfcigtf], rax; pfnfcigtf
0x140007fb7  lea     r8, fciAlloc; pfna
0x140007fbe  lea     rax, fciDelete
0x140007fc5  mov     [rsp+5F0h+pfndelete], rax; pfndelete
0x140007fca  lea     rdx, fciFilePlaced; pfnfcifp
0x140007fd1  lea     rax, fciSeek
0x140007fd8  mov     [rsp+5F0h+pfnseek], rax; pfnseek
0x140007fdd  lea     rax, fciClose
0x140007fe4  mov     [rsp+5F0h+pfnclose], rax; pfnclose
0x140007fe9  lea     rax, fciWrite
0x140007ff0  mov     [rsp+5F0h+pfnwrite], rax; pfnwrite
0x140007ff5  lea     rax, fciRead
0x140007ffc  mov     [rsp+5F0h+pfnread], rax; pfnread
0x140008001  lea     rax, fciOpen
0x140008008  mov     [rsp+5F0h+pfnopen], rax; pfnopen
0x14000800d  call    cs:__imp_FCICreate
0x140008013  mov     [rbx+58h], rax
0x140008017  test    rax, rax
0x14000801a  jnz     short loc_140008028
0x14000801c  lea     r8, aFcicreate; "FCICreate"
0x140008023  jmp     loc_1400080F2
0x140008028  mov     rdx, rdi
0x14000802b  mov     rcx, rbx
0x14000802e  call    tcompFromSession
0x140008033  mov     dword ptr [rsp+5F0h+typeCompress], eax
0x140008037  lea     rcx, [rbx+0E4h]
0x14000803e  mov     rdx, r13
0x140008041  mov     r9d, 1
0x140008047  test    r15, r15
0x14000804a  jz      short loc_140008065
0x14000804c  mov     r8b, [rdx]
0x14000804f  test    r8b, r8b
0x140008052  jz      short loc_140008065
0x140008054  mov     [rcx], r8b
0x140008057  add     rdx, r9
0x14000805a  add     rcx, r9
0x14000805d  sub     r15, r9
0x140008060  sub     r14, r9
0x140008063  jnz     short loc_140008047
0x140008065  lea     rax, [rcx-1]
0x140008069  xor     r15d, r15d
0x14000806c  test    r14, r14
0x14000806f  cmovnz  rax, rcx
0x140008073  xor     r8d, r8d; cb2
0x140008076  xor     edx, edx; cb1
0x140008078  xor     ecx, ecx; typeStatus
0x14000807a  mov     [rax], r15b
0x14000807d  mov     [rbx+84h], r9d
0x140008084  mov     [rbx+88h], r9d
0x14000808b  lea     r9, [rbx+0C38h]; pv
0x140008092  call    fciStatus
0x140008097  mov     eax, dword ptr [rsp+5F0h+typeCompress]
0x14000809b  lea     r14, fciStatus
0x1400080a2  mov     rcx, [rbx+58h]; hfci
0x1400080a6  xor     r9d, r9d; fExecute
0x1400080a9  mov     word ptr [rsp+5F0h+pfnclose], ax; typeCompress
0x1400080ae  mov     r8, r13; pszFileName
0x1400080b1  lea     rax, fciOpenInfo
0x1400080b8  mov     rdx, r12; pszSourceFile
0x1400080bb  mov     [rsp+5F0h+pfnwrite], rax; pfnfcigoi
0x1400080c0  lea     rax, fciGetNextCabinet_NOT
0x1400080c7  mov     [rsp+5F0h+pfnread], r14; pfnfcis
0x1400080cc  mov     [rsp+5F0h+pfnopen], rax; pfnfcignc
0x1400080d1  call    cs:__imp_FCIAddFile
0x1400080d7  test    eax, eax
0x1400080d9  jnz     short loc_14000812C
0x1400080db  mov     rax, [rbx+0C40h]
0x1400080e2  cmp     [rax+200h], r15d
0x1400080e9  jnz     short loc_140008100
0x1400080eb  lea     r8, aFciaddfile; "FCIAddFile"
0x1400080f2  mov     r9, rsi
0x1400080f5  mov     rdx, rbx
0x1400080f8  mov     rcx, rdi
0x1400080fb  call    mapFCIError
0x140008100  xor     eax, eax
0x140008102  mov     rcx, [rbp+4F0h+var_40]
0x140008109  xor     rcx, rsp; StackCookie
0x14000810c  call    __security_check_cookie
0x140008111  mov     rbx, [rsp+5F0h+arg_10]
0x140008119  add     rsp, 5C0h
0x140008120  pop     r15
0x140008122  pop     r14
0x140008124  pop     r13
0x140008126  pop     r12
0x140008128  pop     rdi
0x140008129  pop     rsi
0x14000812a  pop     rbp
0x14000812b  retn
0x14000812c  mov     rcx, [rbx+58h]; hfci
0x140008130  lea     r8, fciGetNextCabinet_NOT; pfnfcignc
0x140008137  mov     r9, r14; pfnfcis
0x14000813a  xor     edx, edx; fGetNextCab
0x14000813c  call    cs:__imp_FCIFlushCabinet
0x140008142  test    eax, eax
0x140008144  jnz     short loc_14000815F
0x140008146  mov     rax, [rbx+0C40h]
0x14000814d  cmp     [rax+200h], r15d
0x140008154  jnz     short loc_140008100
0x140008156  lea     r8, aFciflushcabine; "FCIFlushCabinet"
0x14000815d  jmp     short loc_1400080F2
0x14000815f  mov     rcx, [rbx+58h]; hfci
0x140008163  call    cs:__imp_FCIDestroy
0x140008169  test    eax, eax
0x14000816b  jnz     short loc_140008179
0x14000816d  lea     r8, aFcidestroy; "FCIDestroy"
0x140008174  jmp     loc_1400080F2
0x140008179  mov     [rbx+58h], r15
0x14000817d  mov     eax, 1
0x140008182  jmp     loc_140008102
```
