# StringLengthWorkerA

- ea: `0x1000edb0`
- end: `0x1000eded`
- name: `StringLengthWorkerA`
- size: `61`
- prototype: `static HRESULT __stdcall(STRSAFE_PCNZCH psz, size_t cchMax, size_t *pcchLength)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x1000f076`
- `0x1000f240`
- `0x1000f4d0`

## callees

- `0x1000edb0`

## pseudocode

```c
HRESULT __stdcall StringLengthWorkerA(STRSAFE_PCNZCH psz, size_t cchMax, size_t *pcchLength)
{
  int v3; // edx
  _BYTE *v4; // ecx
  int v5; // esi
  HRESULT v6; // ecx

  v5 = v3;
  do
  {
    if ( !*v4 )
      break;
    ++v4;
    --v3;
  }
  while ( v3 );
  v6 = -2147024809;
  if ( v3 )
    v6 = 0;
  if ( psz )
  {
    if ( v3 )
      *(_DWORD *)psz = v5 - v3;
    else
      *(_DWORD *)psz = 0;
  }
  return v6;
}

```

## disassembly

```asm
0x1000edb0  mov     edi, edi
0x1000edb2  push    ebp
0x1000edb3  mov     ebp, esp
0x1000edb5  push    esi
0x1000edb6  mov     esi, edx
0x1000edb8  cmp     byte ptr [ecx], 0
0x1000edbb  jz      short loc_1000EDC3
0x1000edbd  inc     ecx
0x1000edbe  sub     edx, 1
0x1000edc1  jnz     short loc_1000EDB8
0x1000edc3  xor     eax, eax
0x1000edc5  mov     ecx, 80070057h
0x1000edca  test    edx, edx
0x1000edcc  cmovnz  ecx, eax
0x1000edcf  mov     eax, [ebp+psz]
0x1000edd2  test    eax, eax
0x1000edd4  jz      short loc_1000EDE6
0x1000edd6  test    edx, edx
0x1000edd8  jz      short loc_1000EDE0
0x1000edda  sub     esi, edx
0x1000eddc  mov     [eax], esi
0x1000edde  jmp     short loc_1000EDE6
0x1000ede0  mov     dword ptr [eax], 0
0x1000ede6  mov     eax, ecx
0x1000ede8  pop     esi
0x1000ede9  pop     ebp
0x1000edea  retn    4
```
