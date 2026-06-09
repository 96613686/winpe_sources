# StringExHandleOtherFlagsA

- ea: `0x1800052f0`
- end: `0x180005386`
- name: `StringExHandleOtherFlagsA`
- size: `150`
- prototype: `static HRESULT __stdcall(STRSAFE_LPSTR pszDest, size_t cbDest, size_t cchOriginalDestLength, STRSAFE_LPSTR *ppszDestEnd, size_t *pcchRemaining, DWORD dwFlags)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000510c`

## callees

- `0x1800052f0`
- `0x180005486`

## pseudocode

```c
HRESULT __stdcall StringExHandleOtherFlagsA(
        STRSAFE_LPSTR pszDest,
        size_t cbDest,
        size_t cchOriginalDestLength,
        STRSAFE_LPSTR *ppszDestEnd,
        size_t *pcchRemaining,
        DWORD dwFlags)
{
  char *v10; // rax

  if ( cbDest && (dwFlags & 0x1000) != 0 )
  {
    *ppszDestEnd = pszDest;
    *pcchRemaining = cbDest;
    *pszDest = 0;
  }
  if ( (dwFlags & 0x400) == 0 )
  {
LABEL_7:
    if ( !cbDest )
      return 0;
    goto LABEL_8;
  }
  memset_0(pszDest, (unsigned __int8)dwFlags, cbDest);
  if ( !(_BYTE)dwFlags )
  {
    *ppszDestEnd = pszDest;
    *pcchRemaining = cbDest;
    goto LABEL_7;
  }
  if ( !cbDest )
    return 0;
  *pcchRemaining = 1;
  v10 = &pszDest[cbDest - 1];
  *ppszDestEnd = v10;
  *v10 = 0;
LABEL_8:
  if ( (dwFlags & 0x800) != 0 )
  {
    *ppszDestEnd = pszDest;
    *pcchRemaining = cbDest;
    *pszDest = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x1800052f0  push    rbx
0x1800052f2  push    rsi
0x1800052f3  push    rdi
0x1800052f4  push    r14
0x1800052f6  push    r15
0x1800052f8  sub     rsp, 20h
0x1800052fc  mov     r15, [rsp+48h+pcchRemaining]
0x180005301  mov     r14, r9
0x180005304  mov     rdi, rdx
0x180005307  mov     rsi, rcx
0x18000530a  test    rdx, rdx
0x18000530d  jz      short loc_180005322
0x18000530f  test    [rsp+48h+dwFlags], 1000h
0x180005317  jz      short loc_180005322
0x180005319  mov     [r9], rcx
0x18000531c  mov     [r15], rdx
0x18000531f  mov     byte ptr [rcx], 0
0x180005322  test    [rsp+48h+dwFlags], 400h
0x18000532a  jz      short loc_180005345
0x18000532c  movzx   ebx, byte ptr [rsp+48h+dwFlags]
0x180005331  mov     r8, rdi; Size
0x180005334  mov     edx, ebx; Val
0x180005336  call    memset_0
0x18000533b  test    ebx, ebx
0x18000533d  jnz     short loc_18000536B
0x18000533f  mov     [r14], rsi
0x180005342  mov     [r15], rdi
0x180005345  test    rdi, rdi
0x180005348  jz      short loc_18000535D
0x18000534a  test    [rsp+48h+dwFlags], 800h
0x180005352  jz      short loc_18000535D
0x180005354  mov     [r14], rsi
0x180005357  mov     [r15], rdi
0x18000535a  mov     byte ptr [rsi], 0
0x18000535d  xor     eax, eax
0x18000535f  add     rsp, 20h
0x180005363  pop     r15
0x180005365  pop     r14
0x180005367  pop     rdi
0x180005368  pop     rsi
0x180005369  pop     rbx
0x18000536a  retn
0x18000536b  test    rdi, rdi
0x18000536e  jz      short loc_18000535D
0x180005370  lea     rax, [rdi-1]
0x180005374  mov     qword ptr [r15], 1
0x18000537b  add     rax, rsi
0x18000537e  mov     [r14], rax
0x180005381  mov     byte ptr [rax], 0
0x180005384  jmp     short loc_18000534A
```
