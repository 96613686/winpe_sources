# wil_details_BuildFeatureStateCacheFromQueryResults

- ea: `0x1400202bc`
- end: `0x140020313`
- name: `wil_details_BuildFeatureStateCacheFromQueryResults`
- size: `87`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140020640`
- `0x140032244`

## callees

- `0x1400202bc`

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
0x1400202bc  cmp     ecx, 80000022h
0x1400202c2  jz      short loc_140020305
0x1400202c4  cmp     ecx, 0C0000225h
0x1400202ca  jz      short loc_140020305
0x1400202cc  xor     eax, eax
0x1400202ce  mov     [r8], rax
0x1400202d1  test    ecx, ecx
0x1400202d3  jz      short loc_1400202E8
0x1400202d5  cmp     ecx, 117h
0x1400202db  jnz     short loc_14002030A
0x1400202dd  mov     edx, [rdx+4]
0x1400202e0  and     edx, 80h
0x1400202e6  jmp     short loc_1400202FA
0x1400202e8  mov     eax, [rdx+4]
0x1400202eb  mov     edx, eax
0x1400202ed  and     edx, 40h
0x1400202f0  and     eax, 0B0h
0x1400202f5  shl     edx, 2
0x1400202f8  or      edx, eax
0x1400202fa  shl     edx, 3
0x1400202fd  or      edx, 206h
0x140020303  jmp     short loc_14002030F
0x140020305  xor     eax, eax
0x140020307  mov     [r8], rax
0x14002030a  mov     edx, 206h
0x14002030f  mov     [r8], edx
0x140020312  retn
```
