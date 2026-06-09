# wil_details_BuildFeatureStateCacheFromQueryResults

- ea: `0x140043108`
- end: `0x14004315f`
- name: `wil_details_BuildFeatureStateCacheFromQueryResults`
- size: `87`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140043480`
- `0x1400473ac`

## callees

- `0x140043108`

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
0x140043108  cmp     ecx, 80000022h
0x14004310e  jz      short loc_140043151
0x140043110  cmp     ecx, 0C0000225h
0x140043116  jz      short loc_140043151
0x140043118  xor     eax, eax
0x14004311a  mov     [r8], rax
0x14004311d  test    ecx, ecx
0x14004311f  jz      short loc_140043134
0x140043121  cmp     ecx, 117h
0x140043127  jnz     short loc_140043156
0x140043129  mov     edx, [rdx+4]
0x14004312c  and     edx, 80h
0x140043132  jmp     short loc_140043146
0x140043134  mov     eax, [rdx+4]
0x140043137  mov     edx, eax
0x140043139  and     edx, 40h
0x14004313c  and     eax, 0B0h
0x140043141  shl     edx, 2
0x140043144  or      edx, eax
0x140043146  shl     edx, 3
0x140043149  or      edx, 206h
0x14004314f  jmp     short loc_14004315B
0x140043151  xor     eax, eax
0x140043153  mov     [r8], rax
0x140043156  mov     edx, 206h
0x14004315b  mov     [r8], edx
0x14004315e  retn
```
