# wil_details_BuildFeatureStateCacheFromQueryResults

- ea: `0x14002f56c`
- end: `0x14002f5c3`
- name: `wil_details_BuildFeatureStateCacheFromQueryResults`
- size: `87`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x14002f8f0`
- `0x140030138`

## callees

- `0x14002f56c`

## pseudocode

```c
__int64 __fastcall wil_details_BuildFeatureStateCacheFromQueryResults(int a1, __int64 a2, _QWORD *a3)
{
  __int64 result; // rax
  int v4; // edx
  int v5; // edx

  if ( a1 == -2147483614 || a1 == -1073741275 )
  {
    result = 0;
    *a3 = 0;
    goto LABEL_9;
  }
  result = 0;
  *a3 = 0;
  if ( !a1 )
  {
    result = *(_DWORD *)(a2 + 4) & 0xB0;
    v4 = result | (4 * (*(_DWORD *)(a2 + 4) & 0x40));
    goto LABEL_7;
  }
  if ( a1 != 279 )
  {
LABEL_9:
    v5 = 518;
    goto LABEL_10;
  }
  v4 = *(_DWORD *)(a2 + 4) & 0x80;
LABEL_7:
  v5 = (8 * v4) | 0x206;
LABEL_10:
  *(_DWORD *)a3 = v5;
  return result;
}

```

## disassembly

```asm
0x14002f56c  cmp     ecx, 80000022h
0x14002f572  jz      short loc_14002F5B5
0x14002f574  cmp     ecx, 0C0000225h
0x14002f57a  jz      short loc_14002F5B5
0x14002f57c  xor     eax, eax
0x14002f57e  mov     [r8], rax
0x14002f581  test    ecx, ecx
0x14002f583  jz      short loc_14002F598
0x14002f585  cmp     ecx, 117h
0x14002f58b  jnz     short loc_14002F5BA
0x14002f58d  mov     edx, [rdx+4]
0x14002f590  and     edx, 80h
0x14002f596  jmp     short loc_14002F5AA
0x14002f598  mov     eax, [rdx+4]
0x14002f59b  mov     edx, eax
0x14002f59d  and     edx, 40h
0x14002f5a0  and     eax, 0B0h
0x14002f5a5  shl     edx, 2
0x14002f5a8  or      edx, eax
0x14002f5aa  shl     edx, 3
0x14002f5ad  or      edx, 206h
0x14002f5b3  jmp     short loc_14002F5BF
0x14002f5b5  xor     eax, eax
0x14002f5b7  mov     [r8], rax
0x14002f5ba  mov     edx, 206h
0x14002f5bf  mov     [r8], edx
0x14002f5c2  retn
```
