# StringCchCatW

- ea: `0x180004afc`
- end: `0x180004b3f`
- name: `StringCchCatW`
- size: `67`
- prototype: `HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cchDest, STRSAFE_LPCWSTR pszSrc)`
- caller_count: `7`
- callee_count: `3`
- tags: ``

## callers

- `0x180004260`
- `0x18000844c`
- `0x18000dc70`
- `0x180010a4c`
- `0x180012b14`
- `0x180012c98`
- `0x1800134d4`

## callees

- `0x180002ea0`
- `0x180004afc`
- `0x180004b50`

## pseudocode

```c
HRESULT __stdcall StringCchCatW(STRSAFE_LPWSTR pszDest, size_t cchDest, STRSAFE_LPCWSTR pszSrc)
{
  size_t v3; // r9
  HRESULT result; // eax
  size_t *v6; // r8
  __int64 v7; // r10
  __int64 v8; // r11
  size_t v9; // [rsp+20h] [rbp-18h]
  size_t pcchDestLength; // [rsp+58h] [rbp+20h] BYREF

  pcchDestLength = 0;
  result = StringValidateDestAndLengthW(pszDest, cchDest, &pcchDestLength, v3);
  if ( result >= 0 )
    return StringCopyWorkerW((STRSAFE_LPWSTR)(v8 + 2 * pcchDestLength), v7 - pcchDestLength, v6, pszSrc, v9);
  return result;
}

```

## disassembly

```asm
0x180004afc  push    rbx
0x180004afe  sub     rsp, 30h
0x180004b02  mov     rbx, r8
0x180004b05  mov     [rsp+38h+pcchDestLength], 0
0x180004b0e  lea     r8, [rsp+38h+pcchDestLength]; pcchDestLength
0x180004b13  mov     r10, rdx
0x180004b16  mov     r11, rcx
0x180004b19  call    StringValidateDestAndLengthW
0x180004b1e  test    eax, eax
0x180004b20  js      short loc_180004B39
0x180004b22  mov     rax, [rsp+38h+pcchDestLength]
0x180004b27  mov     r9, rbx; pszSrc
0x180004b2a  sub     r10, rax
0x180004b2d  mov     rdx, r10; cchDest
0x180004b30  lea     rcx, [r11+rax*2]; pszDest
0x180004b34  call    StringCopyWorkerW
0x180004b39  add     rsp, 30h
0x180004b3d  pop     rbx
0x180004b3e  retn
```
