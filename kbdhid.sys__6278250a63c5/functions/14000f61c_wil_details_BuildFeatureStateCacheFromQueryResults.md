# wil_details_BuildFeatureStateCacheFromQueryResults

- ea: `0x14000f61c`
- end: `0x14000f673`
- name: `wil_details_BuildFeatureStateCacheFromQueryResults`
- size: `87`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x14000f7fc`
- `0x140011010`

## callees

- `0x14000f61c`

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
0x14000f61c  cmp     ecx, 80000022h
0x14000f622  jz      short loc_14000F665
0x14000f624  cmp     ecx, 0C0000225h
0x14000f62a  jz      short loc_14000F665
0x14000f62c  xor     eax, eax
0x14000f62e  mov     [r8], rax
0x14000f631  test    ecx, ecx
0x14000f633  jz      short loc_14000F648
0x14000f635  cmp     ecx, 117h
0x14000f63b  jnz     short loc_14000F66A
0x14000f63d  mov     edx, [rdx+4]
0x14000f640  and     edx, 80h
0x14000f646  jmp     short loc_14000F65A
0x14000f648  mov     eax, [rdx+4]
0x14000f64b  mov     edx, eax
0x14000f64d  and     edx, 40h
0x14000f650  and     eax, 0B0h
0x14000f655  shl     edx, 2
0x14000f658  or      edx, eax
0x14000f65a  shl     edx, 3
0x14000f65d  or      edx, 206h
0x14000f663  jmp     short loc_14000F66F
0x14000f665  xor     eax, eax
0x14000f667  mov     [r8], rax
0x14000f66a  mov     edx, 206h
0x14000f66f  mov     [r8], edx
0x14000f672  retn
```
