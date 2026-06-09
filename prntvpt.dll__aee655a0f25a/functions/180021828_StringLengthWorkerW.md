# StringLengthWorkerW

- ea: `0x180021828`
- end: `0x18002186d`
- name: `StringLengthWorkerW`
- size: `69`
- prototype: `static HRESULT __stdcall(STRSAFE_PCNZWCH psz, size_t cchMax, size_t *pcchLength)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001eb5c`

## callees

- `0x180021828`

## string_xrefs

- `0x18002182d`: `compstui.dll`

## pseudocode

```c
HRESULT __stdcall StringLengthWorkerW(STRSAFE_PCNZWCH psz, size_t cchMax, size_t *pcchLength)
{
  const unsigned __int16 *v3; // rax
  __int64 v4; // rcx
  HRESULT result; // eax

  v3 = L"compstui.dll";
  v4 = 259;
  do
  {
    if ( !*v3 )
      break;
    ++v3;
    --v4;
  }
  while ( v4 );
  result = v4 == 0 ? 0x80070057 : 0;
  if ( pcchLength )
  {
    if ( v4 )
      *pcchLength = 259 - v4;
    else
      *pcchLength = 0;
  }
  return result;
}

```

## disassembly

```asm
0x180021828  mov     edx, 103h
0x18002182d  lea     rax, aCompstuiDll; "compstui.dll"
0x180021834  mov     ecx, edx
0x180021836  xor     r9d, r9d
0x180021839  cmp     [rax], r9w
0x18002183d  jz      short loc_180021849
0x18002183f  add     rax, 2
0x180021843  sub     rcx, 1
0x180021847  jnz     short loc_180021839
0x180021849  mov     rax, rcx
0x18002184c  neg     rax
0x18002184f  sbb     eax, eax
0x180021851  not     eax
0x180021853  and     eax, 80070057h
0x180021858  test    r8, r8
0x18002185b  jz      short locret_18002186C
0x18002185d  test    rcx, rcx
0x180021860  jz      short loc_180021869
0x180021862  sub     rdx, rcx
0x180021865  mov     [r8], rdx
0x180021868  retn
0x180021869  mov     [r8], r9
0x18002186c  retn
```
