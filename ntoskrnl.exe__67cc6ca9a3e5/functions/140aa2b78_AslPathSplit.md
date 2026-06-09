# AslPathSplit

- ea: `0x140aa2b78`
- end: `0x140aa2d64`
- name: `AslPathSplit`
- size: `492`
- prototype: `__int64 __fastcall(STRSAFE_PCNZWCH pszSrc, NTSTRSAFE_PWSTR pszDest, size_t cchDest, NTSTRSAFE_PWSTR, int, NTSTRSAFE_PWSTR)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x140aecd48`

## callees

- `0x1402dc448`
- `0x1404495c4`
- `0x14053ecd0`
- `0x1406d9d70`
- `0x14097d158`
- `0x140aa2b78`

## string_xrefs

- `0x140aa2cfc`: `AslPathSplit`
- `0x140aa2cf1`: `RtlStringCchCopyNW failed [%x]`
- `0x140aa2d1b`: `RtlStringCchCopyW failed [%x]`
- `0x140aa2d32`: `RtlStringCchCopyW failed [%x]`
- `0x140aa2d55`: `RtlStringCchCopyW failed [%x]`

## pseudocode

```c
__int64 __fastcall AslPathSplit(
        STRSAFE_PCNZWCH pszSrc,
        NTSTRSAFE_PWSTR pszDest,
        size_t cchDest,
        NTSTRSAFE_PWSTR a4,
        int a5,
        NTSTRSAFE_PWSTR pszDesta)
{
  unsigned int v8; // ebp
  wchar_t *v10; // rax
  STRSAFE_PCNZWCH v11; // rdi
  NTSTATUS v12; // ebx
  _WORD *v13; // rcx
  wchar_t *v14; // r8
  __int64 v15; // r9
  __int64 v16; // rdx
  wchar_t *v17; // rcx
  wchar_t *v18; // rax
  const wchar_t *v19; // rbp
  size_t v20; // rdi
  int v22; // r8d
  const char *v23; // r9
  wchar_t Str[264]; // [rsp+30h] [rbp-258h] BYREF

  *pszDest = 0;
  v8 = cchDest;
  Str[0] = 0;
  *pszDesta = 0;
  *a4 = 0;
  v10 = wcsrchr(pszSrc, 0x5Cu);
  v11 = v10;
  if ( v10 )
  {
    v12 = RtlStringCchCopyNW(pszDest, v8, pszSrc, v10 - pszSrc + 1);
    if ( v12 < 0 )
    {
      v22 = 1231;
LABEL_17:
      v23 = "RtlStringCchCopyNW failed [%x]";
      goto LABEL_18;
    }
  }
  else
  {
    v11 = pszSrc;
  }
  v13 = v11 + 1;
  v14 = Str;
  v15 = 2147483646;
  v16 = 261;
  if ( *v11 != 92 )
    v13 = v11;
  do
  {
    if ( !v15 )
      break;
    if ( !*v13 )
      break;
    *v14++ = *v13++;
    --v15;
    --v16;
  }
  while ( v16 );
  v17 = v14 - 1;
  v12 = v16 == 0 ? 0x80000005 : 0;
  if ( v16 )
    v17 = v14;
  *v17 = 0;
  if ( !v16 )
  {
    v23 = "RtlStringCchCopyW failed [%x]";
    v22 = 1251;
    goto LABEL_18;
  }
  v18 = wcsrchr(Str, 0x2Eu);
  v19 = v18;
  if ( !v18 )
  {
    v12 = RtlStringCchCopyW(a4, 0x104u, Str);
    if ( v12 >= 0 )
      return 0;
    v23 = "RtlStringCchCopyW failed [%x]";
    v22 = 1278;
LABEL_18:
    AslLogCallPrintf(1, (unsigned int)"AslPathSplit", v22, (_DWORD)v23);
    return (unsigned int)v12;
  }
  v20 = v18 - Str;
  v12 = RtlStringCchCopyNW(a4, 0x104u, Str, v20);
  if ( v12 < 0 )
  {
    v22 = 1264;
    goto LABEL_17;
  }
  a4[v20] = 0;
  v12 = RtlStringCchCopyW(pszDesta, 0x104u, v19);
  if ( v12 < 0 )
  {
    v23 = "RtlStringCchCopyW failed [%x]";
    v22 = 1271;
    goto LABEL_18;
  }
  return 0;
}

```

## disassembly

```asm
0x140aa2b78  push    rbx
0x140aa2b7a  push    rbp
0x140aa2b7b  push    rsi
0x140aa2b7c  push    rdi
0x140aa2b7d  push    r12
0x140aa2b7f  push    r14
0x140aa2b81  push    r15
0x140aa2b83  sub     rsp, 250h
0x140aa2b8a  mov     rax, cs:__security_cookie
0x140aa2b91  xor     rax, rsp
0x140aa2b94  mov     [rsp+288h+var_48], rax
0x140aa2b9c  mov     r15, [rsp+288h+pszDest]
0x140aa2ba4  xor     r12d, r12d
0x140aa2ba7  mov     [rdx], r12w
0x140aa2bab  mov     rsi, rdx
0x140aa2bae  mov     r14, r9
0x140aa2bb1  mov     ebp, r8d
0x140aa2bb4  mov     rbx, rcx
0x140aa2bb7  mov     [rsp+288h+Str], r12w
0x140aa2bbd  mov     [r15], r12w
0x140aa2bc1  lea     edx, [r12+5Ch]; Ch
0x140aa2bc6  mov     [r9], r12w
0x140aa2bca  call    wcsrchr
0x140aa2bcf  mov     rdi, rax
0x140aa2bd2  test    rax, rax
0x140aa2bd5  jz      loc_140AA2D0F
0x140aa2bdb  mov     r9, rax
0x140aa2bde  mov     edx, ebp; cchDest
0x140aa2be0  sub     r9, rbx
0x140aa2be3  mov     r8, rbx; pszSrc
0x140aa2be6  sar     r9, 1
0x140aa2be9  mov     rcx, rsi; pszDest
0x140aa2bec  inc     r9; cchToCopy
0x140aa2bef  call    RtlStringCchCopyNW
0x140aa2bf4  mov     ebx, eax
0x140aa2bf6  test    eax, eax
0x140aa2bf8  js      loc_140AA2CEB
0x140aa2bfe  mov     edx, 5Ch ; '\'
0x140aa2c03  lea     rcx, [rdi+2]
0x140aa2c07  cmp     [rdi], dx
0x140aa2c0a  lea     r8, [rsp+288h+Str]
0x140aa2c0f  mov     r9d, 7FFFFFFEh
0x140aa2c15  mov     edx, 105h
0x140aa2c1a  cmovnz  rcx, rdi
0x140aa2c1e  test    r9, r9
0x140aa2c21  jz      short loc_140AA2C40
0x140aa2c23  movzx   eax, word ptr [rcx]
0x140aa2c26  test    ax, ax
0x140aa2c29  jz      short loc_140AA2C40
0x140aa2c2b  mov     [r8], ax
0x140aa2c2f  add     rcx, 2
0x140aa2c33  add     r8, 2
0x140aa2c37  dec     r9
0x140aa2c3a  sub     rdx, 1
0x140aa2c3e  jnz     short loc_140AA2C1E
0x140aa2c40  mov     rax, rdx
0x140aa2c43  lea     rcx, [r8-2]
0x140aa2c47  neg     rax
0x140aa2c4a  sbb     ebx, ebx
0x140aa2c4c  not     ebx
0x140aa2c4e  and     ebx, 80000005h
0x140aa2c54  test    rdx, rdx
0x140aa2c57  cmovnz  rcx, r8
0x140aa2c5b  mov     [rcx], r12w
0x140aa2c5f  jz      loc_140AA2D17
0x140aa2c65  mov     edx, 2Eh ; '.'; Ch
0x140aa2c6a  lea     rcx, [rsp+288h+Str]; Str
0x140aa2c6f  call    wcsrchr
0x140aa2c74  lea     r8, [rsp+288h+Str]; pszSrc
0x140aa2c79  mov     rbp, rax
0x140aa2c7c  mov     rcx, r14; pszDest
0x140aa2c7f  test    rax, rax
0x140aa2c82  jz      loc_140AA2D41
0x140aa2c88  lea     rax, [rsp+288h+Str]
0x140aa2c8d  mov     rdi, rbp
0x140aa2c90  sub     rdi, rax
0x140aa2c93  mov     esi, 104h
0x140aa2c98  sar     rdi, 1
0x140aa2c9b  mov     edx, esi; cchDest
0x140aa2c9d  mov     r9, rdi; cchToCopy
0x140aa2ca0  call    RtlStringCchCopyNW
0x140aa2ca5  mov     ebx, eax
0x140aa2ca7  test    eax, eax
0x140aa2ca9  js      short loc_140AA2D2A
0x140aa2cab  mov     r8, rbp; pszSrc
0x140aa2cae  mov     [r14+rdi*2], r12w
0x140aa2cb3  mov     edx, esi; cchDest
0x140aa2cb5  mov     rcx, r15; pszDest
0x140aa2cb8  call    RtlStringCchCopyW
0x140aa2cbd  mov     ebx, eax
0x140aa2cbf  test    eax, eax
0x140aa2cc1  js      short loc_140AA2D32
0x140aa2cc3  mov     ebx, r12d
0x140aa2cc6  mov     eax, ebx
0x140aa2cc8  mov     rcx, [rsp+288h+var_48]
0x140aa2cd0  xor     rcx, rsp; StackCookie
0x140aa2cd3  call    __security_check_cookie
0x140aa2cd8  add     rsp, 250h
0x140aa2cdf  pop     r15
0x140aa2ce1  pop     r14
0x140aa2ce3  pop     r12
0x140aa2ce5  pop     rdi
0x140aa2ce6  pop     rsi
0x140aa2ce7  pop     rbp
0x140aa2ce8  pop     rbx
0x140aa2ce9  retn
0x140aa2ceb  mov     r8d, 4CFh
0x140aa2cf1  lea     r9, aRtlstringcchco_2; "RtlStringCchCopyNW failed [%x]"
0x140aa2cf8  mov     [rsp+288h+var_268], eax
0x140aa2cfc  lea     rdx, aAslpathsplit; "AslPathSplit"
0x140aa2d03  mov     ecx, 1
0x140aa2d08  call    AslLogCallPrintf
0x140aa2d0d  jmp     short loc_140AA2CC6
0x140aa2d0f  mov     rdi, rbx
0x140aa2d12  jmp     loc_140AA2BFE
0x140aa2d17  mov     [rsp+288h+var_268], ebx
0x140aa2d1b  lea     r9, aRtlstringcchco_0; "RtlStringCchCopyW failed [%x]"
0x140aa2d22  mov     r8d, 4E3h
0x140aa2d28  jmp     short loc_140AA2CFC
0x140aa2d2a  mov     r8d, 4F0h
0x140aa2d30  jmp     short loc_140AA2CF1
0x140aa2d32  lea     r9, aRtlstringcchco_0; "RtlStringCchCopyW failed [%x]"
0x140aa2d39  mov     r8d, 4F7h
0x140aa2d3f  jmp     short loc_140AA2CF8
0x140aa2d41  mov     edx, 104h; cchDest
0x140aa2d46  call    RtlStringCchCopyW
0x140aa2d4b  mov     ebx, eax
0x140aa2d4d  test    eax, eax
0x140aa2d4f  jns     loc_140AA2CC3
0x140aa2d55  lea     r9, aRtlstringcchco_0; "RtlStringCchCopyW failed [%x]"
0x140aa2d5c  mov     r8d, 4FEh
0x140aa2d62  jmp     short loc_140AA2CF8
```
