# wil_details_BuildFeatureStateCacheFromQueryResults

- ea: `0x1400168cc`
- end: `0x140016923`
- name: `wil_details_BuildFeatureStateCacheFromQueryResults`
- size: `87`
- prototype: `__int64 __fastcall(int, __int64, _QWORD *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140016c50`
- `0x140029574`

## callees

- `0x1400168cc`

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
0x1400168cc  cmp     ecx, 80000022h
0x1400168d2  jz      short loc_140016915
0x1400168d4  cmp     ecx, 0C0000225h
0x1400168da  jz      short loc_140016915
0x1400168dc  xor     eax, eax
0x1400168de  mov     [r8], rax
0x1400168e1  test    ecx, ecx
0x1400168e3  jz      short loc_1400168F8
0x1400168e5  cmp     ecx, 117h
0x1400168eb  jnz     short loc_14001691A
0x1400168ed  mov     edx, [rdx+4]
0x1400168f0  and     edx, 80h
0x1400168f6  jmp     short loc_14001690A
0x1400168f8  mov     eax, [rdx+4]
0x1400168fb  mov     edx, eax
0x1400168fd  and     edx, 40h
0x140016900  and     eax, 0B0h
0x140016905  shl     edx, 2
0x140016908  or      edx, eax
0x14001690a  shl     edx, 3
0x14001690d  or      edx, 206h
0x140016913  jmp     short loc_14001691F
0x140016915  xor     eax, eax
0x140016917  mov     [r8], rax
0x14001691a  mov     edx, 206h
0x14001691f  mov     [r8], edx
0x140016922  retn
```
