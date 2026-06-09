# AslEnvGetSystem32DirPathBuf

- ea: `0x140afe014`
- end: `0x140afe15e`
- name: `AslEnvGetSystem32DirPathBuf`
- size: `330`
- prototype: `__int64 __usercall@<rax>(NTSTRSAFE_PWSTR pszDest@<rcx>, size_t cchDest@<rdx>, __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x1407369c8`
- `0x140824b50`

## callees

- `0x1402dc448`
- `0x1406d9d70`
- `0x1406f4880`
- `0x1408270c8`
- `0x1408273c4`
- `0x14097d158`
- `0x140afe014`

## string_xrefs

- `0x140afe124`: `RtlStringCchCopyW failed [%x]`
- `0x140afe0b7`: `AslPathToSystemPathBuf failed [%x]`
- `0x140afe0ff`: `AslPathCombine failed [%x]`
- `0x140afe0c4`: `AslEnvGetSystem32DirPathBuf`

## pseudocode

```c
__int64 __fastcall AslEnvGetSystem32DirPathBuf(
        NTSTRSAFE_PWSTR pszDest,
        size_t cchDest,
        _WORD *a3,
        __int16 a4,
        __int16 *a5)
{
  __int16 v9; // cx
  unsigned __int64 i; // rax
  NTSTATUS v11; // eax
  unsigned int v12; // ebx
  const char *v13; // r9
  int v14; // r8d
  wchar_t pszSrc[64]; // [rsp+30h] [rbp-B8h] BYREF

  memset_0(pszSrc, 0, sizeof(pszSrc));
  *pszDest = 0;
  if ( a5 )
    v9 = *a5;
  else
    v9 = a4;
  for ( i = 0; ; ++i )
  {
    if ( i >= 8 )
      return (unsigned int)-1073741637;
    if ( word_140E0D900[8 * i] == a4 && word_140E0D900[8 * i + 1] == v9 )
      break;
  }
  v11 = AslPathToSystemPathBuf(pszSrc, 0x40u, *(NTSTRSAFE_PCWSTR *)&word_140E0D900[8 * i + 4]);
  v12 = v11;
  if ( v11 < 0 )
  {
    v13 = "AslPathToSystemPathBuf failed [%x]";
    v14 = 1575;
LABEL_11:
    AslLogCallPrintf(1, (unsigned int)"AslEnvGetSystem32DirPathBuf", v14, (_DWORD)v13, v11);
    return v12;
  }
  if ( a3 && *a3 )
  {
    v11 = AslPathCombine(pszSrc, a3, pszDest, cchDest);
    v12 = v11;
    if ( v11 < 0 )
    {
      v13 = "AslPathCombine failed [%x]";
      v14 = 1585;
      goto LABEL_11;
    }
  }
  else
  {
    v11 = RtlStringCchCopyW(pszDest, cchDest, pszSrc);
    v12 = v11;
    if ( v11 < 0 )
    {
      v13 = "RtlStringCchCopyW failed [%x]";
      v14 = 1593;
      goto LABEL_11;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x140afe014  push    rbx
0x140afe016  push    rbp
0x140afe017  push    rsi
0x140afe018  push    rdi
0x140afe019  push    r14
0x140afe01b  sub     rsp, 0C0h
0x140afe022  mov     rax, cs:__security_cookie
0x140afe029  xor     rax, rsp
0x140afe02c  mov     [rsp+0E8h+var_38], rax
0x140afe034  mov     rdi, r8
0x140afe037  mov     rbp, rdx
0x140afe03a  mov     rsi, rcx
0x140afe03d  xor     edx, edx; Val
0x140afe03f  mov     r8d, 80h; Size
0x140afe045  lea     rcx, [rsp+0E8h+pszSrc]; void *
0x140afe04a  movzx   ebx, r9w
0x140afe04e  call    memset_0
0x140afe053  mov     rcx, [rsp+0E8h+arg_20]
0x140afe05b  xor     r14d, r14d
0x140afe05e  mov     [rsi], r14w
0x140afe062  test    rcx, rcx
0x140afe065  jz      short loc_140AFE06C
0x140afe067  movzx   ecx, word ptr [rcx]
0x140afe06a  jmp     short loc_140AFE06F
0x140afe06c  movzx   ecx, bx
0x140afe06f  mov     rax, r14
0x140afe072  lea     rdx, word_140E0D900
0x140afe079  cmp     rax, 8
0x140afe07d  jnb     loc_140AFE138
0x140afe083  mov     r8, rax
0x140afe086  add     r8, r8
0x140afe089  cmp     [rdx+r8*8], bx
0x140afe08e  jnz     short loc_140AFE098
0x140afe090  cmp     [rdx+r8*8+2], cx
0x140afe096  jz      short loc_140AFE09D
0x140afe098  inc     rax
0x140afe09b  jmp     short loc_140AFE079
0x140afe09d  mov     r8, [rdx+r8*8+8]; pszSrc
0x140afe0a2  lea     rcx, [rsp+0E8h+pszSrc]; pszDest
0x140afe0a7  mov     edx, 40h ; '@'; cchDest
0x140afe0ac  call    AslPathToSystemPathBuf
0x140afe0b1  mov     ebx, eax
0x140afe0b3  test    eax, eax
0x140afe0b5  jns     short loc_140AFE0DB
0x140afe0b7  lea     r9, aAslpathtosyste; "AslPathToSystemPathBuf failed [%x]"
0x140afe0be  mov     r8d, 627h
0x140afe0c4  lea     rdx, aAslenvgetsyste; "AslEnvGetSystem32DirPathBuf"
0x140afe0cb  mov     [rsp+0E8h+var_C8], eax
0x140afe0cf  mov     ecx, 1
0x140afe0d4  call    AslLogCallPrintf
0x140afe0d9  jmp     short loc_140AFE13D
0x140afe0db  test    rdi, rdi
0x140afe0de  jz      short loc_140AFE10E
0x140afe0e0  cmp     [rdi], r14w
0x140afe0e4  jz      short loc_140AFE10E
0x140afe0e6  mov     r9, rbp
0x140afe0e9  lea     rcx, [rsp+0E8h+pszSrc]
0x140afe0ee  mov     r8, rsi
0x140afe0f1  mov     rdx, rdi
0x140afe0f4  call    AslPathCombine
0x140afe0f9  mov     ebx, eax
0x140afe0fb  test    eax, eax
0x140afe0fd  jns     short loc_140AFE133
0x140afe0ff  lea     r9, aAslpathcombine_0; "AslPathCombine failed [%x]"
0x140afe106  mov     r8d, 631h
0x140afe10c  jmp     short loc_140AFE0C4
0x140afe10e  lea     r8, [rsp+0E8h+pszSrc]; pszSrc
0x140afe113  mov     rdx, rbp; cchDest
0x140afe116  mov     rcx, rsi; pszDest
0x140afe119  call    RtlStringCchCopyW
0x140afe11e  mov     ebx, eax
0x140afe120  test    eax, eax
0x140afe122  jns     short loc_140AFE133
0x140afe124  lea     r9, aRtlstringcchco_0; "RtlStringCchCopyW failed [%x]"
0x140afe12b  mov     r8d, 639h
0x140afe131  jmp     short loc_140AFE0C4
0x140afe133  mov     ebx, r14d
0x140afe136  jmp     short loc_140AFE13D
0x140afe138  mov     ebx, 0C00000BBh
0x140afe13d  mov     eax, ebx
0x140afe13f  mov     rcx, [rsp+0E8h+var_38]
0x140afe147  xor     rcx, rsp; StackCookie
0x140afe14a  call    __security_check_cookie
0x140afe14f  add     rsp, 0C0h
0x140afe156  pop     r14
0x140afe158  pop     rdi
0x140afe159  pop     rsi
0x140afe15a  pop     rbp
0x140afe15b  pop     rbx
0x140afe15c  retn
```
