# wil_details_BuildFeatureStateCacheFromQueryResults

- ea: `0x1800213c4`
- end: `0x18002141b`
- name: `wil_details_BuildFeatureStateCacheFromQueryResults`
- size: `87`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800216f0`
- `0x18002b7ac`

## callees

- `0x1800213c4`

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
0x1800213c4  cmp     ecx, 80000022h
0x1800213ca  jz      short loc_18002140D
0x1800213cc  cmp     ecx, 0C0000225h
0x1800213d2  jz      short loc_18002140D
0x1800213d4  xor     eax, eax
0x1800213d6  mov     [r8], rax
0x1800213d9  test    ecx, ecx
0x1800213db  jz      short loc_1800213F0
0x1800213dd  cmp     ecx, 117h
0x1800213e3  jnz     short loc_180021412
0x1800213e5  mov     edx, [rdx+4]
0x1800213e8  and     edx, 80h
0x1800213ee  jmp     short loc_180021402
0x1800213f0  mov     eax, [rdx+4]
0x1800213f3  mov     edx, eax
0x1800213f5  and     edx, 40h
0x1800213f8  and     eax, 0B0h
0x1800213fd  shl     edx, 2
0x180021400  or      edx, eax
0x180021402  shl     edx, 3
0x180021405  or      edx, 206h
0x18002140b  jmp     short loc_180021417
0x18002140d  xor     eax, eax
0x18002140f  mov     [r8], rax
0x180021412  mov     edx, 206h
0x180021417  mov     [r8], edx
0x18002141a  retn
```
