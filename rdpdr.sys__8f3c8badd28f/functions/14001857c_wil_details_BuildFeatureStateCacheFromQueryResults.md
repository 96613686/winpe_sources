# wil_details_BuildFeatureStateCacheFromQueryResults

- ea: `0x14001857c`
- end: `0x1400185d3`
- name: `wil_details_BuildFeatureStateCacheFromQueryResults`
- size: `87`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140018900`
- `0x14002e960`

## callees

- `0x14001857c`

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
0x14001857c  cmp     ecx, 80000022h
0x140018582  jz      short loc_1400185C5
0x140018584  cmp     ecx, 0C0000225h
0x14001858a  jz      short loc_1400185C5
0x14001858c  xor     eax, eax
0x14001858e  mov     [r8], rax
0x140018591  test    ecx, ecx
0x140018593  jz      short loc_1400185A8
0x140018595  cmp     ecx, 117h
0x14001859b  jnz     short loc_1400185CA
0x14001859d  mov     edx, [rdx+4]
0x1400185a0  and     edx, 80h
0x1400185a6  jmp     short loc_1400185BA
0x1400185a8  mov     eax, [rdx+4]
0x1400185ab  mov     edx, eax
0x1400185ad  and     edx, 40h
0x1400185b0  and     eax, 0B0h
0x1400185b5  shl     edx, 2
0x1400185b8  or      edx, eax
0x1400185ba  shl     edx, 3
0x1400185bd  or      edx, 206h
0x1400185c3  jmp     short loc_1400185CF
0x1400185c5  xor     eax, eax
0x1400185c7  mov     [r8], rax
0x1400185ca  mov     edx, 206h
0x1400185cf  mov     [r8], edx
0x1400185d2  retn
```
