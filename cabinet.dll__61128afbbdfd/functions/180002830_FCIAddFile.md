# FCIAddFile

- ea: `0x180002830`
- end: `0x180002972`
- name: `FCIAddFile`
- size: `322`
- prototype: `BOOL __cdecl(HFCI hfci, LPSTR pszSourceFile, LPSTR pszFileName, BOOL fExecute, PFNFCIGETNEXTCABINET pfnfcignc, PFNFCISTATUS pfnfcis, PFNFCIGETOPENINFO pfnfcigoi, TCOMP typeCompress)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180002830`
- `0x180003340`
- `0x1800039b8`
- `0x1800146f0`

## pseudocode

```c
BOOL __cdecl FCIAddFile(
        HFCI hfci,
        LPSTR pszSourceFile,
        LPSTR pszFileName,
        BOOL fExecute,
        PFNFCIGETNEXTCABINET pfnfcignc,
        PFNFCISTATUS pfnfcis,
        PFNFCIGETOPENINFO pfnfcigoi,
        TCOMP typeCompress)
{
  int v9; // esi
  int v10; // r15d
  _DWORD *v12; // rdx
  _DWORD *v13; // rcx
  int v14; // r8d
  int v15; // r9d

  v9 = (int)pszFileName;
  v10 = (int)pszSourceFile;
  if ( !hfci
    || !pszFileName
    || typeCompress != *(_WORD *)(*((_QWORD *)hfci + 1) + 676LL)
    && (!(unsigned int)AddFolderToCabinet(*(_QWORD *)hfci, (__int64)pfnfcis, *((_QWORD *)hfci + 4))
     || !(unsigned int)SetCompressionType(typeCompress, *((_QWORD *)hfci + 1)))
    || !(unsigned int)AddFileToFolder(
                        *((_QWORD *)hfci + 1),
                        v10,
                        v9,
                        fExecute,
                        (__int64)pfnfcis,
                        (__int64)pfnfcigoi,
                        typeCompress,
                        *((_QWORD *)hfci + 4)) )
  {
    return 0;
  }
  v12 = (_DWORD *)*((_QWORD *)hfci + 1);
  v13 = *(_DWORD **)hfci;
  v14 = v12[160];
  v15 = v12[24];
  if ( *(_DWORD *)(*(_QWORD *)hfci + 924LL) < (unsigned int)(v15 + v14)
    || v13[230] < (unsigned int)(v14 + v15 + v13[26] + v13[94] + v12[92] + v13[162] + v13[710] + v13[711]) )
  {
    return AddFolderToCabinet((int)v13, (__int64)pfnfcis, *((_QWORD *)hfci + 4));
  }
  else
  {
    return 1;
  }
}

```

## disassembly

```asm
0x180002830  push    rbx
0x180002832  push    rbp
0x180002833  push    rsi
0x180002834  push    rdi
0x180002835  push    r14
0x180002837  push    r15
0x180002839  sub     rsp, 48h
0x18000283d  mov     r14d, r9d
0x180002840  mov     rsi, r8
0x180002843  mov     r15, rdx
0x180002846  mov     rbx, rcx
0x180002849  test    rcx, rcx
0x18000284c  jz      loc_18000296E
0x180002852  test    r8, r8
0x180002855  jz      loc_18000296E
0x18000285b  mov     rdx, [rcx+8]
0x18000285f  movzx   edi, [rsp+78h+typeCompress]
0x180002867  mov     rbp, [rsp+78h+pfnfcis]
0x18000286f  cmp     di, [rdx+2A4h]
0x180002876  jnz     loc_180002935
0x18000287c  mov     rax, [rbx+20h]
0x180002880  mov     r9d, r14d
0x180002883  mov     rcx, [rbx+8]
0x180002887  mov     r8, rsi
0x18000288a  mov     [rsp+78h+var_40], rax
0x18000288f  mov     rdx, r15
0x180002892  mov     rax, [rsp+78h+pfnfcigoi]
0x18000289a  mov     [rsp+78h+var_48], di
0x18000289f  mov     [rsp+78h+var_50], rax
0x1800028a4  mov     [rsp+78h+var_58], rbp
0x1800028a9  call    AddFileToFolder
0x1800028ae  test    eax, eax
0x1800028b0  jz      loc_18000296E
0x1800028b6  mov     rdx, [rbx+8]
0x1800028ba  mov     rcx, [rbx]; int
0x1800028bd  mov     r8d, [rdx+280h]
0x1800028c4  mov     r9d, [rdx+60h]
0x1800028c8  lea     eax, [r9+r8]
0x1800028cc  cmp     [rcx+39Ch], eax
0x1800028d2  jnb     short loc_1800028FF
0x1800028d4  mov     rax, [rbx+20h]
0x1800028d8  xor     r8d, r8d
0x1800028db  mov     r9, [rsp+78h+pfnfcignc]
0x1800028e3  mov     [rsp+78h+var_50], rax; size_t
0x1800028e8  mov     [rsp+78h+var_58], rbp; __int64
0x1800028ed  call    AddFolderToCabinet
0x1800028f2  add     rsp, 48h
0x1800028f6  pop     r15
0x1800028f8  pop     r14
0x1800028fa  pop     rdi
0x1800028fb  pop     rsi
0x1800028fc  pop     rbp
0x1800028fd  pop     rbx
0x1800028fe  retn
0x1800028ff  mov     eax, [rcx+0B1Ch]
0x180002905  add     eax, [rcx+0B18h]
0x18000290b  add     eax, [rcx+288h]
0x180002911  add     eax, [rdx+170h]
0x180002917  add     eax, [rcx+178h]
0x18000291d  add     eax, [rcx+68h]
0x180002920  add     eax, r9d
0x180002923  add     eax, r8d
0x180002926  cmp     [rcx+398h], eax
0x18000292c  jb      short loc_1800028D4
0x18000292e  mov     eax, 1
0x180002933  jmp     short loc_1800028F2
0x180002935  mov     rax, [rcx+20h]
0x180002939  xor     r8d, r8d
0x18000293c  mov     r9, [rsp+78h+pfnfcignc]
0x180002944  mov     rcx, [rcx]; int
0x180002947  mov     [rsp+78h+var_50], rax; size_t
0x18000294c  mov     [rsp+78h+var_58], rbp; __int64
0x180002951  call    AddFolderToCabinet
0x180002956  test    eax, eax
0x180002958  jz      short loc_18000296E
0x18000295a  mov     rdx, [rbx+8]
0x18000295e  movzx   ecx, di
0x180002961  call    SetCompressionType
0x180002966  test    eax, eax
0x180002968  jnz     loc_18000287C
0x18000296e  xor     eax, eax
0x180002970  jmp     short loc_1800028F2
```
