# wil_details_BuildFeatureStateCacheFromQueryResults

- ea: `0x14000e740`
- end: `0x14000e797`
- name: `wil_details_BuildFeatureStateCacheFromQueryResults`
- size: `87`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x14000ead0`
- `0x140013588`

## callees

- `0x14000e740`

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
0x14000e740  cmp     ecx, 80000022h
0x14000e746  jz      short loc_14000E789
0x14000e748  cmp     ecx, 0C0000225h
0x14000e74e  jz      short loc_14000E789
0x14000e750  xor     eax, eax
0x14000e752  mov     [r8], rax
0x14000e755  test    ecx, ecx
0x14000e757  jz      short loc_14000E76C
0x14000e759  cmp     ecx, 117h
0x14000e75f  jnz     short loc_14000E78E
0x14000e761  mov     edx, [rdx+4]
0x14000e764  and     edx, 80h
0x14000e76a  jmp     short loc_14000E77E
0x14000e76c  mov     eax, [rdx+4]
0x14000e76f  mov     edx, eax
0x14000e771  and     edx, 40h
0x14000e774  and     eax, 0B0h
0x14000e779  shl     edx, 2
0x14000e77c  or      edx, eax
0x14000e77e  shl     edx, 3
0x14000e781  or      edx, 206h
0x14000e787  jmp     short loc_14000E793
0x14000e789  xor     eax, eax
0x14000e78b  mov     [r8], rax
0x14000e78e  mov     edx, 206h
0x14000e793  mov     [r8], edx
0x14000e796  retn
```
