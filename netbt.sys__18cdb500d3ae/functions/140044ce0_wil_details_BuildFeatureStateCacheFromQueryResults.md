# wil_details_BuildFeatureStateCacheFromQueryResults

- ea: `0x140044ce0`
- end: `0x140044d37`
- name: `wil_details_BuildFeatureStateCacheFromQueryResults`
- size: `87`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140045070`
- `0x1400532b8`

## callees

- `0x140044ce0`

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
0x140044ce0  cmp     ecx, 80000022h
0x140044ce6  jz      short loc_140044D29
0x140044ce8  cmp     ecx, 0C0000225h
0x140044cee  jz      short loc_140044D29
0x140044cf0  xor     eax, eax
0x140044cf2  mov     [r8], rax
0x140044cf5  test    ecx, ecx
0x140044cf7  jz      short loc_140044D0C
0x140044cf9  cmp     ecx, 117h
0x140044cff  jnz     short loc_140044D2E
0x140044d01  mov     edx, [rdx+4]
0x140044d04  and     edx, 80h
0x140044d0a  jmp     short loc_140044D1E
0x140044d0c  mov     eax, [rdx+4]
0x140044d0f  mov     edx, eax
0x140044d11  and     edx, 40h
0x140044d14  and     eax, 0B0h
0x140044d19  shl     edx, 2
0x140044d1c  or      edx, eax
0x140044d1e  shl     edx, 3
0x140044d21  or      edx, 206h
0x140044d27  jmp     short loc_140044D33
0x140044d29  xor     eax, eax
0x140044d2b  mov     [r8], rax
0x140044d2e  mov     edx, 206h
0x140044d33  mov     [r8], edx
0x140044d36  retn
```
