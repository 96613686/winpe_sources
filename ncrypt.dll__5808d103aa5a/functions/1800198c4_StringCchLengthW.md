# StringCchLengthW

- ea: `0x1800198c4`
- end: `0x1800198ee`
- name: `StringCchLengthW`
- size: `42`
- prototype: `HRESULT __stdcall(STRSAFE_PCNZWCH psz, size_t cchMax, size_t *pcchLength)`
- caller_count: `6`
- callee_count: `2`
- tags: ``

## callers

- `0x180014978`
- `0x180019770`
- `0x18001d0f0`
- `0x18001d280`
- `0x18001e50c`
- `0x18001e738`

## callees

- `0x1800198c4`
- `0x1800198f4`

## pseudocode

```c
HRESULT __stdcall StringCchLengthW(STRSAFE_PCNZWCH psz, size_t cchMax, size_t *pcchLength)
{
  HRESULT result; // eax

  if ( psz )
  {
    result = StringLengthWorkerW(psz, cchMax, pcchLength);
    if ( result >= 0 )
      return result;
  }
  else
  {
    result = -2147024809;
  }
  if ( pcchLength )
    *pcchLength = 0;
  return result;
}

```

## disassembly

```asm
0x1800198c4  sub     rsp, 28h
0x1800198c8  test    rcx, rcx
0x1800198cb  jz      short loc_1800198D8
0x1800198cd  call    StringLengthWorkerW
0x1800198d2  test    eax, eax
0x1800198d4  js      short loc_1800198DD
0x1800198d6  jmp     short loc_1800198E9
0x1800198d8  mov     eax, 80070057h
0x1800198dd  test    r8, r8
0x1800198e0  jz      short loc_1800198E9
0x1800198e2  mov     qword ptr [r8], 0
0x1800198e9  add     rsp, 28h
0x1800198ed  retn
```
