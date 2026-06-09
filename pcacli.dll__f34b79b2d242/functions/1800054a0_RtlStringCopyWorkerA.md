# RtlStringCopyWorkerA

- ea: `0x1800054a0`
- end: `0x1800054e9`
- name: `RtlStringCopyWorkerA`
- size: `73`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800092ac`

## callees

- `0x1800054a0`

## pseudocode

```c
__int64 __fastcall RtlStringCopyWorkerA(_BYTE *a1, __int64 a2, __int64 a3, _BYTE *a4)
{
  __int64 i; // rax
  __int64 result; // rax
  _BYTE *v7; // rcx

  for ( i = 2147483646; a2; --a2 )
  {
    if ( !i )
      break;
    if ( !*a4 )
      break;
    *a1++ = *a4++;
    --i;
  }
  result = 2147483653LL;
  if ( a2 )
    result = 0;
  v7 = a1 - 1;
  if ( a2 )
    v7 = a1;
  *v7 = 0;
  return result;
}

```

## disassembly

```asm
0x1800054a0  mov     r10, rcx
0x1800054a3  mov     eax, 7FFFFFFEh
0x1800054a8  test    rdx, rdx
0x1800054ab  jz      short loc_1800054D0
0x1800054ad  nop     dword ptr [rax]
0x1800054b0  test    rax, rax
0x1800054b3  jz      short loc_1800054D0
0x1800054b5  movzx   r8d, byte ptr [r9]
0x1800054b9  test    r8b, r8b
0x1800054bc  jz      short loc_1800054D0
0x1800054be  mov     [r10], r8b
0x1800054c1  inc     r9
0x1800054c4  inc     r10
0x1800054c7  dec     rax
0x1800054ca  sub     rdx, 1
0x1800054ce  jnz     short loc_1800054B0
0x1800054d0  xor     ecx, ecx
0x1800054d2  mov     eax, 80000005h
0x1800054d7  test    rdx, rdx
0x1800054da  cmovnz  eax, ecx
0x1800054dd  lea     rcx, [r10-1]
0x1800054e1  cmovnz  rcx, r10
0x1800054e5  mov     byte ptr [rcx], 0
0x1800054e8  retn
```
