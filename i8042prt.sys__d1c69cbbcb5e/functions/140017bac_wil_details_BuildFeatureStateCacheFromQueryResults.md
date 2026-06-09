# wil_details_BuildFeatureStateCacheFromQueryResults

- ea: `0x140017bac`
- end: `0x140017c03`
- name: `wil_details_BuildFeatureStateCacheFromQueryResults`
- size: `87`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140017ee0`
- `0x140021a98`

## callees

- `0x140017bac`

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
0x140017bac  cmp     ecx, 80000022h
0x140017bb2  jz      short loc_140017BF5
0x140017bb4  cmp     ecx, 0C0000225h
0x140017bba  jz      short loc_140017BF5
0x140017bbc  xor     eax, eax
0x140017bbe  mov     [r8], rax
0x140017bc1  test    ecx, ecx
0x140017bc3  jz      short loc_140017BD8
0x140017bc5  cmp     ecx, 117h
0x140017bcb  jnz     short loc_140017BFA
0x140017bcd  mov     edx, [rdx+4]
0x140017bd0  and     edx, 80h
0x140017bd6  jmp     short loc_140017BEA
0x140017bd8  mov     eax, [rdx+4]
0x140017bdb  mov     edx, eax
0x140017bdd  and     edx, 40h
0x140017be0  and     eax, 0B0h
0x140017be5  shl     edx, 2
0x140017be8  or      edx, eax
0x140017bea  shl     edx, 3
0x140017bed  or      edx, 206h
0x140017bf3  jmp     short loc_140017BFF
0x140017bf5  xor     eax, eax
0x140017bf7  mov     [r8], rax
0x140017bfa  mov     edx, 206h
0x140017bff  mov     [r8], edx
0x140017c02  retn
```
