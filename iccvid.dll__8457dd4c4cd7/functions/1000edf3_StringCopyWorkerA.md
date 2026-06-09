# StringCopyWorkerA

- ea: `0x1000edf3`
- end: `0x1000ee37`
- name: `StringCopyWorkerA`
- size: `68`
- prototype: `static HRESULT __stdcall(STRSAFE_LPSTR pszDest, size_t cchDest, size_t *pcchNewDestLength, STRSAFE_PCNZCH pszSrc, size_t cchToCopy)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1000ed1b`
- `0x1000f076`

## callees

- `0x1000edf3`

## pseudocode

```c
HRESULT __stdcall StringCopyWorkerA(
        STRSAFE_LPSTR pszDest,
        size_t cchDest,
        size_t *pcchNewDestLength,
        STRSAFE_PCNZCH pszSrc,
        size_t cchToCopy)
{
  int v5; // edx
  _BYTE *v6; // ecx
  _BYTE *v7; // esi
  int i; // ecx
  HRESULT result; // eax
  _BYTE *v11; // ecx

  v7 = v6;
  for ( i = 2147483646; v5; --v5 )
  {
    if ( !i )
      break;
    if ( !*(_BYTE *)cchDest )
      break;
    *v7++ = *(_BYTE *)cchDest++;
    --i;
  }
  result = -2147024774;
  if ( v5 )
    result = 0;
  v11 = v7 - 1;
  if ( v5 )
    v11 = v7;
  *v11 = 0;
  return result;
}

```

## disassembly

```asm
0x1000edf3  mov     edi, edi
0x1000edf5  push    ebp
0x1000edf6  mov     ebp, esp
0x1000edf8  push    esi
0x1000edf9  mov     esi, ecx
0x1000edfb  mov     ecx, 7FFFFFFEh
0x1000ee00  test    edx, edx
0x1000ee02  jz      short loc_1000EE1D
0x1000ee04  mov     eax, [ebp+cchDest]
0x1000ee07  push    ebx
0x1000ee08  test    ecx, ecx
0x1000ee0a  jz      short loc_1000EE1C
0x1000ee0c  mov     bl, [eax]
0x1000ee0e  test    bl, bl
0x1000ee10  jz      short loc_1000EE1C
0x1000ee12  mov     [esi], bl
0x1000ee14  inc     esi
0x1000ee15  inc     eax
0x1000ee16  dec     ecx
0x1000ee17  sub     edx, 1
0x1000ee1a  jnz     short loc_1000EE08
0x1000ee1c  pop     ebx
0x1000ee1d  xor     ecx, ecx
0x1000ee1f  mov     eax, 8007007Ah
0x1000ee24  test    edx, edx
0x1000ee26  cmovnz  eax, ecx
0x1000ee29  lea     ecx, [esi-1]
0x1000ee2c  cmovnz  ecx, esi
0x1000ee2f  pop     esi
0x1000ee30  mov     byte ptr [ecx], 0
0x1000ee33  pop     ebp
0x1000ee34  retn    0Ch
```
