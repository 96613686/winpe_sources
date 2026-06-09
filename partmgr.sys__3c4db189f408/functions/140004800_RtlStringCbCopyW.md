# RtlStringCbCopyW

- ea: `0x140004800`
- end: `0x14000486f`
- name: `RtlStringCbCopyW`
- size: `111`
- prototype: `NTSTATUS __stdcall(NTSTRSAFE_PWSTR pszDest, size_t cbDest, NTSTRSAFE_PCWSTR pszSrc)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x14001c3d8`
- `0x14002454c`
- `0x140024844`

## callees

- `0x140004800`

## pseudocode

```c
NTSTATUS __stdcall RtlStringCbCopyW(NTSTRSAFE_PWSTR pszDest, size_t cbDest, NTSTRSAFE_PCWSTR pszSrc)
{
  size_t v3; // rdx
  NTSTRSAFE_PWSTR v4; // r9
  __int64 v5; // rax
  NTSTRSAFE_PWSTR v6; // rax
  NTSTATUS result; // eax

  v3 = cbDest >> 1;
  v4 = pszDest;
  if ( !v3 )
    return -1073741811;
  if ( v3 > 0x7FFFFFFF )
  {
    result = -1073741811;
    *pszDest = 0;
  }
  else
  {
    v5 = 2147483646;
    do
    {
      if ( !v5 )
        break;
      if ( !*pszSrc )
        break;
      *v4++ = *pszSrc++;
      --v5;
      --v3;
    }
    while ( v3 );
    v6 = v4 - 1;
    if ( v3 )
      v6 = v4;
    *v6 = 0;
    result = -2147483643;
    if ( v3 )
      return 0;
  }
  return result;
}

```

## disassembly

```asm
0x140004800  shr     rdx, 1
0x140004803  mov     r9, rcx
0x140004806  jz      short loc_140004860
0x140004808  cmp     rdx, 7FFFFFFFh
0x14000480f  ja      short loc_140004856
0x140004811  mov     eax, 7FFFFFFEh
0x140004816  test    rax, rax
0x140004819  jz      short loc_140004839
0x14000481b  movzx   ecx, word ptr [r8]
0x14000481f  test    cx, cx
0x140004822  jz      short loc_140004839
0x140004824  mov     [r9], cx
0x140004828  add     r8, 2
0x14000482c  add     r9, 2
0x140004830  dec     rax
0x140004833  sub     rdx, 1
0x140004837  jnz     short loc_140004816
0x140004839  test    rdx, rdx
0x14000483c  lea     rax, [r9-2]
0x140004840  cmovnz  rax, r9
0x140004844  xor     ecx, ecx
0x140004846  test    rdx, rdx
0x140004849  mov     [rax], cx
0x14000484c  mov     eax, 80000005h
0x140004851  cmovnz  eax, ecx
0x140004854  retn
0x140004856  mov     eax, 0C000000Dh
0x14000485b  jmp     loc_140011D16
0x140004860  mov     eax, 0C000000Dh
0x140004865  test    rdx, rdx
0x140004868  jz      short locret_140004854
0x14000486a  jmp     loc_140011D16
0x140011d16  xor     ecx, ecx
0x140011d18  mov     [r9], cx
0x140011d1c  retn
```
