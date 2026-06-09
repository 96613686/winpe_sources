# AslPathSplit

- ea: `0x140aa87a8`
- end: `0x140aa8994`
- name: `AslPathSplit`
- size: `492`
- prototype: `__int64 __fastcall(STRSAFE_PCNZWCH pszSrc, NTSTRSAFE_PWSTR pszDest, size_t cchDest, NTSTRSAFE_PWSTR, int, NTSTRSAFE_PWSTR)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x140af2e18`

## callees

- `0x140438468`
- `0x14045d774`
- `0x140546390`
- `0x1406dc8c0`
- `0x1408c2f88`
- `0x140aa87a8`

## string_xrefs

- `0x140aa892c`: `AslPathSplit`
- `0x140aa8921`: `RtlStringCchCopyNW failed [%x]`
- `0x140aa894b`: `RtlStringCchCopyW failed [%x]`
- `0x140aa8962`: `RtlStringCchCopyW failed [%x]`
- `0x140aa8985`: `RtlStringCchCopyW failed [%x]`

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
  NTSTATUS v12; // eax
  unsigned int v13; // ebx
  _WORD *v14; // rcx
  wchar_t *v15; // r8
  __int64 v16; // r9
  __int64 v17; // rdx
  wchar_t *v18; // rcx
  wchar_t *v19; // rax
  const wchar_t *v20; // rbp
  size_t v21; // rdi
  int v23; // r8d
  const char *v24; // r9
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
    v13 = v12;
    if ( v12 < 0 )
    {
      v23 = 1231;
LABEL_17:
      v24 = "RtlStringCchCopyNW failed [%x]";
      goto LABEL_18;
    }
  }
  else
  {
    v11 = pszSrc;
  }
  v14 = v11 + 1;
  v15 = Str;
  v16 = 2147483646;
  v17 = 261;
  if ( *v11 != 92 )
    v14 = v11;
  do
  {
    if ( !v16 )
      break;
    if ( !*v14 )
      break;
    *v15++ = *v14++;
    --v16;
    --v17;
  }
  while ( v17 );
  v18 = v15 - 1;
  v13 = v17 == 0 ? 0x80000005 : 0;
  if ( v17 )
    v18 = v15;
  *v18 = 0;
  if ( !v17 )
  {
    AslLogCallPrintf(1, (unsigned int)"AslPathSplit", 1251, (unsigned int)"RtlStringCchCopyW failed [%x]", -2147483643);
    return v13;
  }
  v19 = wcsrchr(Str, 0x2Eu);
  v20 = v19;
  if ( !v19 )
  {
    v12 = RtlStringCchCopyW(a4, 0x104u, Str);
    v13 = v12;
    if ( v12 >= 0 )
      return 0;
    v24 = "RtlStringCchCopyW failed [%x]";
    v23 = 1278;
LABEL_18:
    AslLogCallPrintf(1, (unsigned int)"AslPathSplit", v23, (_DWORD)v24, v12);
    return v13;
  }
  v21 = v19 - Str;
  v12 = RtlStringCchCopyNW(a4, 0x104u, Str, v21);
  v13 = v12;
  if ( v12 < 0 )
  {
    v23 = 1264;
    goto LABEL_17;
  }
  a4[v21] = 0;
  v12 = RtlStringCchCopyW(pszDesta, 0x104u, v20);
  v13 = v12;
  if ( v12 < 0 )
  {
    v24 = "RtlStringCchCopyW failed [%x]";
    v23 = 1271;
    goto LABEL_18;
  }
  return 0;
}

```

## disassembly

```asm
0x140aa87a8  push    rbx
0x140aa87aa  push    rbp
0x140aa87ab  push    rsi
0x140aa87ac  push    rdi
0x140aa87ad  push    r12
0x140aa87af  push    r14
0x140aa87b1  push    r15
0x140aa87b3  sub     rsp, 250h
0x140aa87ba  mov     rax, cs:__security_cookie
0x140aa87c1  xor     rax, rsp
0x140aa87c4  mov     [rsp+288h+var_48], rax
0x140aa87cc  mov     r15, [rsp+288h+pszDest]
0x140aa87d4  xor     r12d, r12d
0x140aa87d7  mov     [rdx], r12w
0x140aa87db  mov     rsi, rdx
0x140aa87de  mov     r14, r9
0x140aa87e1  mov     ebp, r8d
0x140aa87e4  mov     rbx, rcx
0x140aa87e7  mov     [rsp+288h+Str], r12w
0x140aa87ed  mov     [r15], r12w
0x140aa87f1  lea     edx, [r12+5Ch]; Ch
0x140aa87f6  mov     [r9], r12w
0x140aa87fa  call    wcsrchr
0x140aa87ff  mov     rdi, rax
0x140aa8802  test    rax, rax
0x140aa8805  jz      loc_140AA893F
0x140aa880b  mov     r9, rax
0x140aa880e  mov     edx, ebp; cchDest
0x140aa8810  sub     r9, rbx
0x140aa8813  mov     r8, rbx; pszSrc
0x140aa8816  sar     r9, 1
0x140aa8819  mov     rcx, rsi; pszDest
0x140aa881c  inc     r9; cchToCopy
0x140aa881f  call    RtlStringCchCopyNW
0x140aa8824  mov     ebx, eax
0x140aa8826  test    eax, eax
0x140aa8828  js      loc_140AA891B
0x140aa882e  mov     edx, 5Ch ; '\'
0x140aa8833  lea     rcx, [rdi+2]
0x140aa8837  cmp     [rdi], dx
0x140aa883a  lea     r8, [rsp+288h+Str]
0x140aa883f  mov     r9d, 7FFFFFFEh
0x140aa8845  mov     edx, 105h
0x140aa884a  cmovnz  rcx, rdi
0x140aa884e  test    r9, r9
0x140aa8851  jz      short loc_140AA8870
0x140aa8853  movzx   eax, word ptr [rcx]
0x140aa8856  test    ax, ax
0x140aa8859  jz      short loc_140AA8870
0x140aa885b  mov     [r8], ax
0x140aa885f  add     rcx, 2
0x140aa8863  add     r8, 2
0x140aa8867  dec     r9
0x140aa886a  sub     rdx, 1
0x140aa886e  jnz     short loc_140AA884E
0x140aa8870  mov     rax, rdx
0x140aa8873  lea     rcx, [r8-2]
0x140aa8877  neg     rax
0x140aa887a  sbb     ebx, ebx
0x140aa887c  not     ebx
0x140aa887e  and     ebx, 80000005h
0x140aa8884  test    rdx, rdx
0x140aa8887  cmovnz  rcx, r8
0x140aa888b  mov     [rcx], r12w
0x140aa888f  jz      loc_140AA8947
0x140aa8895  mov     edx, 2Eh ; '.'; Ch
0x140aa889a  lea     rcx, [rsp+288h+Str]; Str
0x140aa889f  call    wcsrchr
0x140aa88a4  lea     r8, [rsp+288h+Str]; pszSrc
0x140aa88a9  mov     rbp, rax
0x140aa88ac  mov     rcx, r14; pszDest
0x140aa88af  test    rax, rax
0x140aa88b2  jz      loc_140AA8971
0x140aa88b8  lea     rax, [rsp+288h+Str]
0x140aa88bd  mov     rdi, rbp
0x140aa88c0  sub     rdi, rax
0x140aa88c3  mov     esi, 104h
0x140aa88c8  sar     rdi, 1
0x140aa88cb  mov     edx, esi; cchDest
0x140aa88cd  mov     r9, rdi; cchToCopy
0x140aa88d0  call    RtlStringCchCopyNW
0x140aa88d5  mov     ebx, eax
0x140aa88d7  test    eax, eax
0x140aa88d9  js      short loc_140AA895A
0x140aa88db  mov     r8, rbp; pszSrc
0x140aa88de  mov     [r14+rdi*2], r12w
0x140aa88e3  mov     edx, esi; cchDest
0x140aa88e5  mov     rcx, r15; pszDest
0x140aa88e8  call    RtlStringCchCopyW
0x140aa88ed  mov     ebx, eax
0x140aa88ef  test    eax, eax
0x140aa88f1  js      short loc_140AA8962
0x140aa88f3  mov     ebx, r12d
0x140aa88f6  mov     eax, ebx
0x140aa88f8  mov     rcx, [rsp+288h+var_48]
0x140aa8900  xor     rcx, rsp; StackCookie
0x140aa8903  call    __security_check_cookie
0x140aa8908  add     rsp, 250h
0x140aa890f  pop     r15
0x140aa8911  pop     r14
0x140aa8913  pop     r12
0x140aa8915  pop     rdi
0x140aa8916  pop     rsi
0x140aa8917  pop     rbp
0x140aa8918  pop     rbx
0x140aa8919  retn
0x140aa891b  mov     r8d, 4CFh
0x140aa8921  lea     r9, aRtlstringcchco_2; "RtlStringCchCopyNW failed [%x]"
0x140aa8928  mov     [rsp+288h+var_268], eax
0x140aa892c  lea     rdx, aAslpathsplit; "AslPathSplit"
0x140aa8933  mov     ecx, 1
0x140aa8938  call    AslLogCallPrintf
0x140aa893d  jmp     short loc_140AA88F6
0x140aa893f  mov     rdi, rbx
0x140aa8942  jmp     loc_140AA882E
0x140aa8947  mov     [rsp+288h+var_268], ebx
0x140aa894b  lea     r9, aRtlstringcchco_0; "RtlStringCchCopyW failed [%x]"
0x140aa8952  mov     r8d, 4E3h
0x140aa8958  jmp     short loc_140AA892C
0x140aa895a  mov     r8d, 4F0h
0x140aa8960  jmp     short loc_140AA8921
0x140aa8962  lea     r9, aRtlstringcchco_0; "RtlStringCchCopyW failed [%x]"
0x140aa8969  mov     r8d, 4F7h
0x140aa896f  jmp     short loc_140AA8928
0x140aa8971  mov     edx, 104h; cchDest
0x140aa8976  call    RtlStringCchCopyW
0x140aa897b  mov     ebx, eax
0x140aa897d  test    eax, eax
0x140aa897f  jns     loc_140AA88F3
0x140aa8985  lea     r9, aRtlstringcchco_0; "RtlStringCchCopyW failed [%x]"
0x140aa898c  mov     r8d, 4FEh
0x140aa8992  jmp     short loc_140AA8928
```
