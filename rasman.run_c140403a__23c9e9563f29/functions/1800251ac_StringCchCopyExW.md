# StringCchCopyExW

- ea: `0x1800251ac`
- end: `0x1800252c2`
- name: `StringCchCopyExW`
- size: `278`
- prototype: `HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cchDest, STRSAFE_LPCWSTR pszSrc, STRSAFE_LPWSTR *ppszDestEnd, size_t *pcchRemaining, DWORD dwFlags)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x180025040`
- `0x180025f98`

## callees

- `0x180014c0c`
- `0x1800251ac`
- `0x1800252c8`
- `0x1800252f4`
- `0x1800253a4`

## pseudocode

```c
HRESULT __stdcall StringCchCopyExW(
        STRSAFE_LPWSTR pszDest,
        size_t cchDest,
        STRSAFE_LPCWSTR pszSrc,
        STRSAFE_LPWSTR *ppszDestEnd,
        size_t *pcchRemaining,
        DWORD dwFlags)
{
  DWORD v6; // esi
  size_t v9; // rdx
  wchar_t *v10; // rcx
  int v11; // edi
  const wchar_t *v12; // r8
  __int64 *v13; // rax
  size_t v14; // rbx
  bool v15; // cf
  size_t *v17; // [rsp+20h] [rbp-28h]
  size_t pcchNewDestLength; // [rsp+68h] [rbp+20h] BYREF

  pcchNewDestLength = (size_t)ppszDestEnd;
  v6 = dwFlags;
  v11 = StringExValidateDestW(pszDest, cchDest, (const size_t)pszSrc, dwFlags);
  if ( v11 < 0 )
  {
    if ( cchDest )
      *v10 = 0;
  }
  else
  {
    if ( (v6 & 0x100) != 0 )
    {
      v13 = &qword_18002A860;
      if ( v12 )
        v13 = (__int64 *)v12;
      v12 = (const wchar_t *)v13;
    }
    if ( (v6 & 0xFFFFE000) != 0 )
    {
      v11 = -2147024809;
      if ( cchDest )
        *v10 = 0;
      goto LABEL_9;
    }
    if ( !cchDest )
    {
      v11 = 0;
      if ( !*v12 )
        return v11;
      v11 = pszDest != 0 ? -2147024774 : -2147024809;
      goto LABEL_9;
    }
    pcchNewDestLength = 0;
    v11 = StringCopyWorkerW(v10, v9, &pcchNewDestLength, v12, (size_t)v17);
    if ( v11 < 0 )
    {
LABEL_9:
      if ( (v6 & 0x1C00) != 0 && cchDest )
        StringExHandleOtherFlagsW(pszDest, 2 * cchDest, 0, (STRSAFE_LPWSTR *)&pcchRemaining, &pcchNewDestLength, v6);
      return v11;
    }
    if ( (v6 & 0x200) != 0 )
    {
      v15 = cchDest == pcchNewDestLength;
      v14 = cchDest - pcchNewDestLength;
      if ( !v15 && v14 != 1 )
        StringExHandleFillBehindNullW(&pszDest[pcchNewDestLength], 2 * v14, v6);
    }
  }
  return v11;
}

```

## disassembly

```asm
0x1800251ac  mov     [rsp+arg_0], rbx
0x1800251b1  mov     [rsp+arg_8], rbp
0x1800251b6  mov     [rsp+pcchNewDestLength], r9
0x1800251bb  push    rsi
0x1800251bc  push    rdi
0x1800251bd  push    r14
0x1800251bf  sub     rsp, 30h
0x1800251c3  mov     esi, [rsp+48h+dwFlags]
0x1800251c7  mov     rbx, rdx
0x1800251ca  mov     r9d, esi; dwFlags
0x1800251cd  mov     r14, rcx
0x1800251d0  call    StringExValidateDestW
0x1800251d5  xor     ebp, ebp
0x1800251d7  mov     edi, eax
0x1800251d9  test    eax, eax
0x1800251db  js      loc_1800252A5
0x1800251e1  bt      esi, 8
0x1800251e5  jnb     short loc_1800251F8
0x1800251e7  test    r8, r8
0x1800251ea  lea     rax, qword_18002A860
0x1800251f1  cmovnz  rax, r8
0x1800251f5  mov     r8, rax
0x1800251f8  test    esi, 0FFFFE000h
0x1800251fe  jz      short loc_180025246
0x180025200  mov     edi, 80070057h
0x180025205  test    rbx, rbx
0x180025208  jz      short loc_18002520D
0x18002520a  mov     [rcx], bp
0x18002520d  test    esi, 1C00h
0x180025213  jz      loc_1800252AD
0x180025219  test    rbx, rbx
0x18002521c  jz      loc_1800252AD
0x180025222  lea     rax, [rsp+48h+pcchNewDestLength]
0x180025227  mov     [rsp+48h+var_20], esi; dwFlags
0x18002522b  lea     rdx, [rbx+rbx]; cbDest
0x18002522f  mov     [rsp+48h+var_28], rax; pcchRemaining
0x180025234  lea     r9, [rsp+48h+pcchRemaining]; ppszDestEnd
0x180025239  xor     r8d, r8d; cchOriginalDestLength
0x18002523c  mov     rcx, r14; pszDest
0x18002523f  call    StringExHandleOtherFlagsW
0x180025244  jmp     short loc_1800252AD
0x180025246  test    rbx, rbx
0x180025249  jnz     short loc_180025267
0x18002524b  mov     edi, ebp
0x18002524d  cmp     [r8], bp
0x180025251  jz      short loc_1800252AD
0x180025253  mov     rax, r14
0x180025256  mov     edi, 80070057h
0x18002525b  neg     rax
0x18002525e  sbb     ecx, ecx
0x180025260  and     ecx, 23h
0x180025263  add     edi, ecx
0x180025265  jmp     short loc_18002520D
0x180025267  mov     r9, r8; pszSrc
0x18002526a  mov     [rsp+48h+pcchNewDestLength], rbp
0x18002526f  lea     r8, [rsp+48h+pcchNewDestLength]; pcchNewDestLength
0x180025274  call    StringCopyWorkerW
0x180025279  mov     edi, eax
0x18002527b  mov     rax, [rsp+48h+pcchNewDestLength]
0x180025280  lea     rcx, [r14+rax*2]; pszDestEnd
0x180025284  test    edi, edi
0x180025286  js      short loc_18002520D
0x180025288  bt      esi, 9
0x18002528c  jnb     short loc_1800252AD
0x18002528e  sub     rbx, rax
0x180025291  cmp     rbx, 1
0x180025295  jbe     short loc_1800252AD
0x180025297  lea     rdx, [rbx+rbx]; cbRemaining
0x18002529b  mov     r8d, esi; dwFlags
0x18002529e  call    StringExHandleFillBehindNullW
0x1800252a3  jmp     short loc_1800252AD
0x1800252a5  test    rbx, rbx
0x1800252a8  jz      short loc_1800252AD
0x1800252aa  mov     [rcx], bp
0x1800252ad  mov     rbx, [rsp+48h+arg_0]
0x1800252b2  mov     eax, edi
0x1800252b4  mov     rbp, [rsp+48h+arg_8]
0x1800252b9  add     rsp, 30h
0x1800252bd  pop     r14
0x1800252bf  pop     rdi
0x1800252c0  pop     rsi
0x1800252c1  retn
```
