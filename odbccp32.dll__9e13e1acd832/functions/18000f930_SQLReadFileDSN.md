# SQLReadFileDSN

- ea: `0x18000f930`
- end: `0x18000faa9`
- name: `SQLReadFileDSN`
- size: `377`
- prototype: `BOOL __stdcall(LPCSTR lpszFileName, LPCSTR lpszAppName, LPCSTR lpszKeyName, LPSTR lpszString, WORD cchString, WORD *pcchString)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops`

## callees

- `0x180002940`
- `0x180009750`
- `0x18000f930`
- `0x1800138e4`
- `0x180013c2c`

## import_xrefs

- `msvcrt!calloc` at `0x18000f9a0`
- `msvcrt!calloc` at `0x18000f9a0`

## pseudocode

```c
BOOL __stdcall SQLReadFileDSN(
        LPCSTR lpszFileName,
        LPCSTR lpszAppName,
        LPCSTR lpszKeyName,
        LPSTR lpszString,
        WORD cchString,
        WORD *pcchString)
{
  unsigned __int16 v7; // r15
  WORD *v8; // rcx
  WCHAR *v10; // r14
  WCHAR *v11; // rsi
  WCHAR *v12; // rdi
  WCHAR *v13; // rbx
  int v14; // eax
  int v15; // eax
  int v16; // eax
  __int64 v17; // rcx
  char v19; // [rsp+40h] [rbp-30h] BYREF
  BOOL v20; // [rsp+44h] [rbp-2Ch]
  WCHAR *v21; // [rsp+48h] [rbp-28h] BYREF
  WCHAR *v22; // [rsp+50h] [rbp-20h] BYREF
  WCHAR *v23; // [rsp+58h] [rbp-18h] BYREF
  LPSTR v24; // [rsp+60h] [rbp-10h] BYREF
  WORD v26; // [rsp+C8h] [rbp+58h] BYREF

  v7 = cchString;
  v8 = (WORD *)&v19;
  v24 = lpszString;
  v21 = 0;
  v10 = 0;
  v22 = 0;
  if ( pcchString )
    v8 = pcchString;
  v23 = 0;
  pcchString = v8;
  v11 = 0;
  v26 = 0;
  v12 = 0;
  v20 = 0;
  v13 = 0;
  if ( !cchString || !lpszString || (v13 = (WCHAR *)calloc(2LL * cchString, 1u)) != 0 )
  {
    if ( !lpszFileName || (v14 = GWConvertToUnicode(lpszFileName, &v21, 0xFFFFFFFD), v10 = v21, v14) )
    {
      if ( !lpszAppName || (v15 = GWConvertToUnicode(lpszAppName, &v22, 0xFFFFFFFD), v11 = v22, v15) )
      {
        if ( !lpszKeyName || (v16 = GWConvertToUnicode(lpszKeyName, &v23, 0xFFFFFFFD), v12 = v23, v16) )
        {
          if ( (v20 = SQLReadFileDSNW(v10, v11, v12, v13, v7, &v26)) && v13 || v13 && v26 >= v7 )
            LConvertToAnsiWordLengths(v17, v13, v26, &v24, v7, pcchString);
        }
      }
    }
  }
  OFree(v10);
  OFree(v11);
  OFree(v12);
  OFree(v13);
  return v20;
}

```

## disassembly

```asm
0x18000f930  mov     [rsp-38h+arg_0], rbx
0x18000f935  mov     [rsp-38h+lpMultiByteStr], r8
0x18000f93a  push    rbp
0x18000f93b  push    rsi
0x18000f93c  push    rdi
0x18000f93d  push    r12
0x18000f93f  push    r13
0x18000f941  push    r14
0x18000f943  push    r15
0x18000f945  mov     rbp, rsp
0x18000f948  sub     rsp, 70h
0x18000f94c  mov     rax, [rbp+pcchString]
0x18000f950  mov     r12, rcx
0x18000f953  movzx   r15d, [rbp+cchString]
0x18000f958  lea     rcx, [rbp+var_30]
0x18000f95c  mov     r13, rdx
0x18000f95f  mov     [rbp+var_10], r9
0x18000f963  xor     edx, edx
0x18000f965  test    rax, rax
0x18000f968  mov     [rbp+var_28], rdx
0x18000f96c  mov     r14d, edx
0x18000f96f  mov     [rbp+var_20], rdx
0x18000f973  cmovnz  rcx, rax
0x18000f977  mov     [rbp+var_18], rdx
0x18000f97b  mov     [rbp+pcchString], rcx
0x18000f97f  mov     esi, edx
0x18000f981  mov     [rbp+arg_18], dx
0x18000f985  mov     edi, edx
0x18000f987  mov     [rbp+var_2C], edx
0x18000f98a  mov     ebx, edx
0x18000f98c  test    r15w, r15w
0x18000f990  jz      short loc_18000F9B2
0x18000f992  test    r9, r9
0x18000f995  jz      short loc_18000F9B2
0x18000f997  mov     ecx, r15d
0x18000f99a  lea     edx, [rbx+1]; Size
0x18000f99d  add     rcx, rcx; Count
0x18000f9a0  call    cs:__imp_calloc
0x18000f9a6  mov     rbx, rax
0x18000f9a9  test    rax, rax
0x18000f9ac  jz      loc_18000FA6E
0x18000f9b2  test    r12, r12
0x18000f9b5  jz      short loc_18000F9D5
0x18000f9b7  mov     r8d, 0FFFFFFFDh
0x18000f9bd  lea     rdx, [rbp+var_28]
0x18000f9c1  mov     rcx, r12; lpMultiByteStr
0x18000f9c4  call    GWConvertToUnicode
0x18000f9c9  mov     r14, [rbp+var_28]
0x18000f9cd  test    eax, eax
0x18000f9cf  jz      loc_18000FA6E
0x18000f9d5  test    r13, r13
0x18000f9d8  jz      short loc_18000F9F4
0x18000f9da  mov     r8d, 0FFFFFFFDh
0x18000f9e0  lea     rdx, [rbp+var_20]
0x18000f9e4  mov     rcx, r13; lpMultiByteStr
0x18000f9e7  call    GWConvertToUnicode
0x18000f9ec  mov     rsi, [rbp+var_20]
0x18000f9f0  test    eax, eax
0x18000f9f2  jz      short loc_18000FA6E
0x18000f9f4  mov     rax, [rbp+lpMultiByteStr]
0x18000f9f8  test    rax, rax
0x18000f9fb  jz      short loc_18000FA17
0x18000f9fd  mov     r8d, 0FFFFFFFDh
0x18000fa03  lea     rdx, [rbp+var_18]
0x18000fa07  mov     rcx, rax; lpMultiByteStr
0x18000fa0a  call    GWConvertToUnicode
0x18000fa0f  mov     rdi, [rbp+var_18]
0x18000fa13  test    eax, eax
0x18000fa15  jz      short loc_18000FA6E
0x18000fa17  lea     rax, [rbp+arg_18]
0x18000fa1b  mov     r9, rbx; lpszString
0x18000fa1e  mov     [rsp+70h+var_48], rax; pcchString
0x18000fa23  mov     r8, rdi; lpszKeyName
0x18000fa26  mov     rdx, rsi; lpszAppName
0x18000fa29  mov     [rsp+70h+var_50], r15w; cchString
0x18000fa2f  mov     rcx, r14; lpszFileName
0x18000fa32  call    SQLReadFileDSNW
0x18000fa37  movzx   r8d, [rbp+arg_18]
0x18000fa3c  mov     [rbp+var_2C], eax
0x18000fa3f  test    eax, eax
0x18000fa41  jz      short loc_18000FA48
0x18000fa43  test    rbx, rbx
0x18000fa46  jnz     short loc_18000FA53
0x18000fa48  test    rbx, rbx
0x18000fa4b  jz      short loc_18000FA6E
0x18000fa4d  cmp     r8w, r15w
0x18000fa51  jb      short loc_18000FA6E
0x18000fa53  mov     rax, [rbp+pcchString]
0x18000fa57  lea     r9, [rbp+var_10]
0x18000fa5b  mov     [rsp+70h+var_48], rax
0x18000fa60  mov     rdx, rbx
0x18000fa63  mov     [rsp+70h+var_50], r15w
0x18000fa69  call    LConvertToAnsiWordLengths
0x18000fa6e  mov     rcx, r14
0x18000fa71  call    OFree
0x18000fa76  mov     rcx, rsi
0x18000fa79  call    OFree
0x18000fa7e  mov     rcx, rdi
0x18000fa81  call    OFree
0x18000fa86  mov     rcx, rbx
0x18000fa89  call    OFree
0x18000fa8e  mov     eax, [rbp+var_2C]
0x18000fa91  mov     rbx, [rsp+70h+arg_0]
0x18000fa99  add     rsp, 70h
0x18000fa9d  pop     r15
0x18000fa9f  pop     r14
0x18000faa1  pop     r13
0x18000faa3  pop     r12
0x18000faa5  pop     rdi
0x18000faa6  pop     rsi
0x18000faa7  pop     rbp
0x18000faa8  retn
```
