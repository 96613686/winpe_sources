# wil_details_BuildFeatureStateCacheFromQueryResults

- ea: `0x140011cbc`
- end: `0x140011d13`
- name: `wil_details_BuildFeatureStateCacheFromQueryResults`
- size: `87`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140011ff0`
- `0x1400211b4`

## callees

- `0x140011cbc`

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
0x140011cbc  cmp     ecx, 80000022h
0x140011cc2  jz      short loc_140011D05
0x140011cc4  cmp     ecx, 0C0000225h
0x140011cca  jz      short loc_140011D05
0x140011ccc  xor     eax, eax
0x140011cce  mov     [r8], rax
0x140011cd1  test    ecx, ecx
0x140011cd3  jz      short loc_140011CE8
0x140011cd5  cmp     ecx, 117h
0x140011cdb  jnz     short loc_140011D0A
0x140011cdd  mov     edx, [rdx+4]
0x140011ce0  and     edx, 80h
0x140011ce6  jmp     short loc_140011CFA
0x140011ce8  mov     eax, [rdx+4]
0x140011ceb  mov     edx, eax
0x140011ced  and     edx, 40h
0x140011cf0  and     eax, 0B0h
0x140011cf5  shl     edx, 2
0x140011cf8  or      edx, eax
0x140011cfa  shl     edx, 3
0x140011cfd  or      edx, 206h
0x140011d03  jmp     short loc_140011D0F
0x140011d05  xor     eax, eax
0x140011d07  mov     [r8], rax
0x140011d0a  mov     edx, 206h
0x140011d0f  mov     [r8], edx
0x140011d12  retn
```
