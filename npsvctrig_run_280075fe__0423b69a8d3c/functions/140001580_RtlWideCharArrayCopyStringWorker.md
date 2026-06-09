# RtlWideCharArrayCopyStringWorker

- ea: `0x140001580`
- end: `0x1400015e0`
- name: `RtlWideCharArrayCopyStringWorker`
- size: `96`
- prototype: `NTSTATUS __stdcall(wchar_t *pszDest, size_t cchDest, size_t *pcchNewDestLength, NTSTRSAFE_PCWSTR pszSrc, size_t cchToCopy)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140009410`

## callees

- `0x140001580`

## pseudocode

```c
NTSTATUS __stdcall RtlWideCharArrayCopyStringWorker(
        wchar_t *pszDest,
        size_t cchDest,
        size_t *pcchNewDestLength,
        NTSTRSAFE_PCWSTR pszSrc,
        size_t cchToCopy)
{
  NTSTATUS v5; // ebx
  size_t v6; // r11
  size_t v7; // r10
  __int64 v8; // rax
  NTSTATUS result; // eax

  v5 = 0;
  v6 = 0;
  v7 = cchDest;
  v8 = 0x7FFF;
  if ( cchDest )
  {
    while ( v8 )
    {
      if ( !*pszSrc )
      {
        if ( v7 )
          break;
LABEL_7:
        if ( !v8 )
          break;
        goto LABEL_8;
      }
      *pszDest++ = *pszSrc++;
      --v8;
      ++v6;
      if ( !--v7 )
        goto LABEL_7;
    }
  }
  else
  {
LABEL_8:
    if ( *pszSrc )
      v5 = -2147483643;
  }
  result = v5;
  *pcchNewDestLength = v6;
  return result;
}

```

## disassembly

```asm
0x140001580  mov     [rsp+arg_0], rbx
0x140001585  xor     ebx, ebx
0x140001587  xor     r11d, r11d
0x14000158a  mov     r10, rdx
0x14000158d  mov     eax, 7FFFh
0x140001592  test    rdx, rdx
0x140001595  jz      short loc_1400015C8
0x140001597  test    rax, rax
0x14000159a  jz      short loc_1400015D4
0x14000159c  movzx   edx, word ptr [r9]
0x1400015a0  test    dx, dx
0x1400015a3  jz      short loc_1400015BE
0x1400015a5  mov     [rcx], dx
0x1400015a8  add     r9, 2
0x1400015ac  add     rcx, 2
0x1400015b0  dec     rax
0x1400015b3  inc     r11
0x1400015b6  sub     r10, 1
0x1400015ba  jnz     short loc_140001597
0x1400015bc  jmp     short loc_1400015C3
0x1400015be  test    r10, r10
0x1400015c1  jnz     short loc_1400015D4
0x1400015c3  test    rax, rax
0x1400015c6  jz      short loc_1400015D4
0x1400015c8  cmp     [r9], bx
0x1400015cc  mov     eax, 80000005h
0x1400015d1  cmovnz  ebx, eax
0x1400015d4  mov     eax, ebx
0x1400015d6  mov     [r8], r11
0x1400015d9  mov     rbx, [rsp+arg_0]
0x1400015de  retn
```
