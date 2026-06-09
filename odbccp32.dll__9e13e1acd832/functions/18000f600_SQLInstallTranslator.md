# SQLInstallTranslator

- ea: `0x18000f600`
- end: `0x18000f773`
- name: `SQLInstallTranslator`
- size: `371`
- prototype: `BOOL __stdcall(LPCSTR lpszInfFile, LPCSTR lpszTranslator, LPCSTR lpszPathIn, LPSTR lpszPathOut, WORD cchPathOutMax, WORD *pcchPathOut, WORD fRequest, LPDWORD lpdwUsageCount)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x18000f780`

## callees

- `0x180002940`
- `0x180009660`
- `0x18000f600`
- `0x18000fea8`
- `0x1800138e4`
- `0x180013c2c`

## import_xrefs

- `msvcrt!calloc` at `0x18000f6c9`
- `msvcrt!calloc` at `0x18000f6c9`

## pseudocode

```c
BOOL __stdcall SQLInstallTranslator(
        LPCSTR lpszInfFile,
        LPCSTR lpszTranslator,
        LPCSTR lpszPathIn,
        LPSTR lpszPathOut,
        WORD cchPathOutMax,
        WORD *pcchPathOut,
        WORD fRequest,
        LPDWORD lpdwUsageCount)
{
  WORD *v8; // r14
  WCHAR *v11; // rsi
  WCHAR *v12; // rbx
  BOOL v13; // r15d
  const CHAR *v15; // rcx
  unsigned int v16; // r8d
  WORD v17; // di
  __int64 v18; // rcx
  LPCWSTR lpszTranslatora; // [rsp+40h] [rbp-20h] BYREF
  LPCWSTR lpszPathIna; // [rsp+48h] [rbp-18h] BYREF
  LPCWSTR lpszInfFilea; // [rsp+50h] [rbp-10h] BYREF
  LPSTR v23; // [rsp+58h] [rbp-8h] BYREF
  __int16 v25; // [rsp+B8h] [rbp+58h] BYREF

  v8 = (WORD *)&v25;
  v23 = lpszPathOut;
  lpszInfFilea = 0;
  lpszTranslatora = 0;
  v11 = 0;
  lpszPathIna = 0;
  v25 = 0;
  v12 = 0;
  v13 = 0;
  if ( pcchPathOut )
    v8 = pcchPathOut;
  if ( (unsigned int)GWConvertToUnicode(lpszInfFile, (WCHAR **)&lpszInfFilea, 0xFFFFFFFD) )
  {
    v15 = lpszTranslator;
    if ( lpszInfFile )
    {
      v16 = -3;
    }
    else
    {
      v16 = dnlen(lpszTranslator);
      v15 = lpszTranslator;
    }
    if ( (unsigned int)GWConvertToUnicode(v15, (WCHAR **)&lpszTranslatora, v16) )
    {
      if ( !(unsigned int)GWConvertToUnicode(lpszPathIn, (WCHAR **)&lpszPathIna, 0xFFFFFFFD)
        || (v17 = cchPathOutMax) != 0 && lpszPathOut && (v12 = (WCHAR *)calloc(2LL * cchPathOutMax, 1u)) == 0 )
      {
        v11 = (WCHAR *)lpszPathIna;
      }
      else
      {
        v11 = (WCHAR *)lpszPathIna;
        v13 = SQLInstallTranslatorW(lpszInfFilea, lpszTranslatora, lpszPathIna, v12, v17, v8, fRequest, lpdwUsageCount);
        if ( v13 && v12 )
          LConvertToAnsiWordLengths(v18, v12, *v8, &v23, v17, v8);
      }
    }
  }
  OFree((void *)lpszInfFilea);
  OFree((void *)lpszTranslatora);
  OFree(v11);
  OFree(v12);
  return v13;
}

```

## disassembly

```asm
0x18000f600  mov     [rsp-38h+arg_0], rbx
0x18000f605  mov     [rsp-38h+lpMultiByteStr], r8
0x18000f60a  push    rbp
0x18000f60b  push    rsi
0x18000f60c  push    rdi
0x18000f60d  push    r12
0x18000f60f  push    r13
0x18000f611  push    r14
0x18000f613  push    r15
0x18000f615  mov     rbp, rsp
0x18000f618  sub     rsp, 60h
0x18000f61c  mov     rax, [rbp+pcchPathOut]
0x18000f620  lea     r14, [rbp+arg_18]
0x18000f624  mov     r12, rcx
0x18000f627  mov     [rbp+var_8], r9
0x18000f62b  xor     ecx, ecx
0x18000f62d  mov     rdi, rdx
0x18000f630  test    rax, rax
0x18000f633  mov     [rbp+lpszInfFile], rcx
0x18000f637  mov     [rbp+lpszTranslator], rcx
0x18000f63b  lea     rdx, [rbp+lpszInfFile]
0x18000f63f  mov     esi, ecx
0x18000f641  mov     [rbp+lpszPathIn], rcx
0x18000f645  lea     r8d, [rcx-3]
0x18000f649  mov     [rbp+arg_18], cx
0x18000f64d  mov     ebx, ecx
0x18000f64f  mov     r15d, ecx
0x18000f652  mov     rcx, r12; lpMultiByteStr
0x18000f655  mov     r13, r9
0x18000f658  cmovnz  r14, rax
0x18000f65c  call    GWConvertToUnicode
0x18000f661  test    eax, eax
0x18000f663  jz      loc_18000F736
0x18000f669  mov     rcx, rdi; lpMultiByteStr
0x18000f66c  test    r12, r12
0x18000f66f  jnz     short loc_18000F67F
0x18000f671  call    dnlen
0x18000f676  movsx   r8d, ax
0x18000f67a  mov     rcx, rdi
0x18000f67d  jmp     short loc_18000F685
0x18000f67f  mov     r8d, 0FFFFFFFDh
0x18000f685  lea     rdx, [rbp+lpszTranslator]
0x18000f689  call    GWConvertToUnicode
0x18000f68e  test    eax, eax
0x18000f690  jz      loc_18000F736
0x18000f696  mov     rcx, [rbp+lpMultiByteStr]; lpMultiByteStr
0x18000f69a  lea     rdx, [rbp+lpszPathIn]
0x18000f69e  mov     r8d, 0FFFFFFFDh
0x18000f6a4  call    GWConvertToUnicode
0x18000f6a9  test    eax, eax
0x18000f6ab  jz      loc_18000F732
0x18000f6b1  movzx   edi, [rbp+cchPathOutMax]
0x18000f6b5  test    di, di
0x18000f6b8  jz      short loc_18000F6D7
0x18000f6ba  test    r13, r13
0x18000f6bd  jz      short loc_18000F6D7
0x18000f6bf  mov     ecx, edi
0x18000f6c1  mov     edx, 1; Size
0x18000f6c6  add     rcx, rcx; Count
0x18000f6c9  call    cs:__imp_calloc
0x18000f6cf  mov     rbx, rax
0x18000f6d2  test    rax, rax
0x18000f6d5  jz      short loc_18000F732
0x18000f6d7  mov     rcx, [rbp+lpdwUsageCount]
0x18000f6db  mov     r9, rbx; lpszPathOut
0x18000f6de  mov     rsi, [rbp+lpszPathIn]
0x18000f6e2  mov     rdx, [rbp+lpszTranslator]; lpszTranslator
0x18000f6e6  mov     r8, rsi; lpszPathIn
0x18000f6e9  mov     [rsp+60h+var_28], rcx; lpdwUsageCount
0x18000f6ee  movzx   ecx, [rbp+fRequest]
0x18000f6f2  mov     [rsp+60h+var_30], cx; fRequest
0x18000f6f7  mov     rcx, [rbp+lpszInfFile]; lpszInfFile
0x18000f6fb  mov     [rsp+60h+var_38], r14; pcchPathOut
0x18000f700  mov     [rsp+60h+var_40], di; cchPathOutMax
0x18000f705  call    SQLInstallTranslatorW
0x18000f70a  mov     r15d, eax
0x18000f70d  test    eax, eax
0x18000f70f  jz      short loc_18000F736
0x18000f711  test    rbx, rbx
0x18000f714  jz      short loc_18000F736
0x18000f716  movzx   r8d, word ptr [r14]
0x18000f71a  lea     r9, [rbp+var_8]
0x18000f71e  mov     [rsp+60h+var_38], r14
0x18000f723  mov     rdx, rbx
0x18000f726  mov     [rsp+60h+var_40], di
0x18000f72b  call    LConvertToAnsiWordLengths
0x18000f730  jmp     short loc_18000F736
0x18000f732  mov     rsi, [rbp+lpszPathIn]
0x18000f736  mov     rcx, [rbp+lpszInfFile]
0x18000f73a  call    OFree
0x18000f73f  mov     rcx, [rbp+lpszTranslator]
0x18000f743  call    OFree
0x18000f748  mov     rcx, rsi
0x18000f74b  call    OFree
0x18000f750  mov     rcx, rbx
0x18000f753  call    OFree
0x18000f758  mov     rbx, [rsp+60h+arg_0]
0x18000f760  mov     eax, r15d
0x18000f763  add     rsp, 60h
0x18000f767  pop     r15
0x18000f769  pop     r14
0x18000f76b  pop     r13
0x18000f76d  pop     r12
0x18000f76f  pop     rdi
0x18000f770  pop     rsi
0x18000f771  pop     rbp
0x18000f772  retn
```
