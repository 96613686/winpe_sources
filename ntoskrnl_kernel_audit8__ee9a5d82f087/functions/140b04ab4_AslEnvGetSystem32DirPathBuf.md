# AslEnvGetSystem32DirPathBuf

- ea: `0x140b04ab4`
- end: `0x140b04bfe`
- name: `AslEnvGetSystem32DirPathBuf`
- size: `330`
- prototype: `__int64 __usercall@<rax>(NTSTRSAFE_PWSTR pszDest@<rcx>, size_t cchDest@<rdx>, __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x14073b188`
- `0x140826ac0`

## callees

- `0x140438468`
- `0x1406dc8c0`
- `0x1406f7380`
- `0x140829038`
- `0x140829334`
- `0x1408c2f88`
- `0x140b04ab4`

## string_xrefs

- `0x140b04bc4`: `RtlStringCchCopyW failed [%x]`
- `0x140b04b57`: `AslPathToSystemPathBuf failed [%x]`
- `0x140b04b9f`: `AslPathCombine failed [%x]`
- `0x140b04b64`: `AslEnvGetSystem32DirPathBuf`

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
  NTSTATUS v11; // ebx
  const char *v12; // r9
  int v13; // r8d
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
  if ( v11 < 0 )
  {
    v12 = "AslPathToSystemPathBuf failed [%x]";
    v13 = 1575;
LABEL_11:
    AslLogCallPrintf(1, (unsigned int)"AslEnvGetSystem32DirPathBuf", v13, (_DWORD)v12);
    return (unsigned int)v11;
  }
  if ( a3 && *a3 )
  {
    v11 = AslPathCombine(pszSrc, a3, pszDest, cchDest);
    if ( v11 < 0 )
    {
      v12 = "AslPathCombine failed [%x]";
      v13 = 1585;
      goto LABEL_11;
    }
  }
  else
  {
    v11 = RtlStringCchCopyW(pszDest, cchDest, pszSrc);
    if ( v11 < 0 )
    {
      v12 = "RtlStringCchCopyW failed [%x]";
      v13 = 1593;
      goto LABEL_11;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x140b04ab4  push    rbx
0x140b04ab6  push    rbp
0x140b04ab7  push    rsi
0x140b04ab8  push    rdi
0x140b04ab9  push    r14
0x140b04abb  sub     rsp, 0C0h
0x140b04ac2  mov     rax, cs:__security_cookie
0x140b04ac9  xor     rax, rsp
0x140b04acc  mov     [rsp+0E8h+var_38], rax
0x140b04ad4  mov     rdi, r8
0x140b04ad7  mov     rbp, rdx
0x140b04ada  mov     rsi, rcx
0x140b04add  xor     edx, edx; Val
0x140b04adf  mov     r8d, 80h; Size
0x140b04ae5  lea     rcx, [rsp+0E8h+pszSrc]; void *
0x140b04aea  movzx   ebx, r9w
0x140b04aee  call    memset_0
0x140b04af3  mov     rcx, [rsp+0E8h+arg_20]
0x140b04afb  xor     r14d, r14d
0x140b04afe  mov     [rsi], r14w
0x140b04b02  test    rcx, rcx
0x140b04b05  jz      short loc_140B04B0C
0x140b04b07  movzx   ecx, word ptr [rcx]
0x140b04b0a  jmp     short loc_140B04B0F
0x140b04b0c  movzx   ecx, bx
0x140b04b0f  mov     rax, r14
0x140b04b12  lea     rdx, word_140E0D900
0x140b04b19  cmp     rax, 8
0x140b04b1d  jnb     loc_140B04BD8
0x140b04b23  mov     r8, rax
0x140b04b26  add     r8, r8
0x140b04b29  cmp     [rdx+r8*8], bx
0x140b04b2e  jnz     short loc_140B04B38
0x140b04b30  cmp     [rdx+r8*8+2], cx
0x140b04b36  jz      short loc_140B04B3D
0x140b04b38  inc     rax
0x140b04b3b  jmp     short loc_140B04B19
0x140b04b3d  mov     r8, [rdx+r8*8+8]; pszSrc
0x140b04b42  lea     rcx, [rsp+0E8h+pszSrc]; pszDest
0x140b04b47  mov     edx, 40h ; '@'; cchDest
0x140b04b4c  call    AslPathToSystemPathBuf
0x140b04b51  mov     ebx, eax
0x140b04b53  test    eax, eax
0x140b04b55  jns     short loc_140B04B7B
0x140b04b57  lea     r9, aAslpathtosyste; "AslPathToSystemPathBuf failed [%x]"
0x140b04b5e  mov     r8d, 627h
0x140b04b64  lea     rdx, aAslenvgetsyste; "AslEnvGetSystem32DirPathBuf"
0x140b04b6b  mov     [rsp+0E8h+var_C8], eax
0x140b04b6f  mov     ecx, 1
0x140b04b74  call    AslLogCallPrintf
0x140b04b79  jmp     short loc_140B04BDD
0x140b04b7b  test    rdi, rdi
0x140b04b7e  jz      short loc_140B04BAE
0x140b04b80  cmp     [rdi], r14w
0x140b04b84  jz      short loc_140B04BAE
0x140b04b86  mov     r9, rbp
0x140b04b89  lea     rcx, [rsp+0E8h+pszSrc]
0x140b04b8e  mov     r8, rsi
0x140b04b91  mov     rdx, rdi
0x140b04b94  call    AslPathCombine
0x140b04b99  mov     ebx, eax
0x140b04b9b  test    eax, eax
0x140b04b9d  jns     short loc_140B04BD3
0x140b04b9f  lea     r9, aAslpathcombine_0; "AslPathCombine failed [%x]"
0x140b04ba6  mov     r8d, 631h
0x140b04bac  jmp     short loc_140B04B64
0x140b04bae  lea     r8, [rsp+0E8h+pszSrc]; pszSrc
0x140b04bb3  mov     rdx, rbp; cchDest
0x140b04bb6  mov     rcx, rsi; pszDest
0x140b04bb9  call    RtlStringCchCopyW
0x140b04bbe  mov     ebx, eax
0x140b04bc0  test    eax, eax
0x140b04bc2  jns     short loc_140B04BD3
0x140b04bc4  lea     r9, aRtlstringcchco_0; "RtlStringCchCopyW failed [%x]"
0x140b04bcb  mov     r8d, 639h
0x140b04bd1  jmp     short loc_140B04B64
0x140b04bd3  mov     ebx, r14d
0x140b04bd6  jmp     short loc_140B04BDD
0x140b04bd8  mov     ebx, 0C00000BBh
0x140b04bdd  mov     eax, ebx
0x140b04bdf  mov     rcx, [rsp+0E8h+var_38]
0x140b04be7  xor     rcx, rsp; StackCookie
0x140b04bea  call    __security_check_cookie
0x140b04bef  add     rsp, 0C0h
0x140b04bf6  pop     r14
0x140b04bf8  pop     rdi
0x140b04bf9  pop     rsi
0x140b04bfa  pop     rbp
0x140b04bfb  pop     rbx
0x140b04bfc  retn
```
