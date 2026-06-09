# StringCchCopyExW

- ea: `0x180026058`
- end: `0x18002616f`
- name: `StringCchCopyExW`
- size: `279`
- prototype: `HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cchDest, STRSAFE_LPCWSTR pszSrc, STRSAFE_LPWSTR *ppszDestEnd, size_t *pcchRemaining, DWORD dwFlags)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x180025ed0`
- `0x180026f3c`

## callees

- `0x1800155ac`
- `0x180026058`
- `0x180026178`
- `0x1800261a4`
- `0x180026258`

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
      v13 = &qword_18002B850;
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
0x180026058  mov     [rsp+arg_0], rbx
0x18002605d  mov     [rsp+arg_8], rbp
0x180026062  mov     [rsp+pcchNewDestLength], r9
0x180026067  push    rsi
0x180026068  push    rdi
0x180026069  push    r14
0x18002606b  sub     rsp, 30h
0x18002606f  mov     esi, [rsp+48h+dwFlags]
0x180026073  mov     rbx, rdx
0x180026076  mov     r9d, esi; dwFlags
0x180026079  mov     r14, rcx
0x18002607c  call    StringExValidateDestW
0x180026081  xor     ebp, ebp
0x180026083  mov     edi, eax
0x180026085  test    eax, eax
0x180026087  js      loc_180026151
0x18002608d  bt      esi, 8
0x180026091  jnb     short loc_1800260A4
0x180026093  test    r8, r8
0x180026096  lea     rax, qword_18002B850
0x18002609d  cmovnz  rax, r8
0x1800260a1  mov     r8, rax
0x1800260a4  test    esi, 0FFFFE000h
0x1800260aa  jz      short loc_1800260F2
0x1800260ac  mov     edi, 80070057h
0x1800260b1  test    rbx, rbx
0x1800260b4  jz      short loc_1800260B9
0x1800260b6  mov     [rcx], bp
0x1800260b9  test    esi, 1C00h
0x1800260bf  jz      loc_180026159
0x1800260c5  test    rbx, rbx
0x1800260c8  jz      loc_180026159
0x1800260ce  lea     rax, [rsp+48h+pcchNewDestLength]
0x1800260d3  mov     [rsp+48h+var_20], esi; dwFlags
0x1800260d7  lea     rdx, [rbx+rbx]; cbDest
0x1800260db  mov     [rsp+48h+var_28], rax; pcchRemaining
0x1800260e0  lea     r9, [rsp+48h+pcchRemaining]; ppszDestEnd
0x1800260e5  xor     r8d, r8d; cchOriginalDestLength
0x1800260e8  mov     rcx, r14; pszDest
0x1800260eb  call    StringExHandleOtherFlagsW
0x1800260f0  jmp     short loc_180026159
0x1800260f2  test    rbx, rbx
0x1800260f5  jnz     short loc_180026113
0x1800260f7  mov     edi, ebp
0x1800260f9  cmp     [r8], bp
0x1800260fd  jz      short loc_180026159
0x1800260ff  mov     rax, r14
0x180026102  mov     edi, 80070057h
0x180026107  neg     rax
0x18002610a  sbb     ecx, ecx
0x18002610c  and     ecx, 23h
0x18002610f  add     edi, ecx
0x180026111  jmp     short loc_1800260B9
0x180026113  mov     r9, r8; pszSrc
0x180026116  mov     [rsp+48h+pcchNewDestLength], rbp
0x18002611b  lea     r8, [rsp+48h+pcchNewDestLength]; pcchNewDestLength
0x180026120  call    StringCopyWorkerW
0x180026125  mov     edi, eax
0x180026127  mov     rax, [rsp+48h+pcchNewDestLength]
0x18002612c  lea     rcx, [r14+rax*2]; pszDestEnd
0x180026130  test    edi, edi
0x180026132  js      short loc_1800260B9
0x180026134  bt      esi, 9
0x180026138  jnb     short loc_180026159
0x18002613a  sub     rbx, rax
0x18002613d  cmp     rbx, 1
0x180026141  jbe     short loc_180026159
0x180026143  lea     rdx, [rbx+rbx]; cbRemaining
0x180026147  mov     r8d, esi; dwFlags
0x18002614a  call    StringExHandleFillBehindNullW
0x18002614f  jmp     short loc_180026159
0x180026151  test    rbx, rbx
0x180026154  jz      short loc_180026159
0x180026156  mov     [rcx], bp
0x180026159  mov     rbx, [rsp+48h+arg_0]
0x18002615e  mov     eax, edi
0x180026160  mov     rbp, [rsp+48h+arg_8]
0x180026165  add     rsp, 30h
0x180026169  pop     r14
0x18002616b  pop     rdi
0x18002616c  pop     rsi
0x18002616d  retn
```
