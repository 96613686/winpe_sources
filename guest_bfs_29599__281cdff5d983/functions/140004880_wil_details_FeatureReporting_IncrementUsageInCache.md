# wil_details_FeatureReporting_IncrementUsageInCache

- ea: `0x140004880`
- end: `0x140004956`
- name: `wil_details_FeatureReporting_IncrementUsageInCache`
- size: `214`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14000495c`

## callees

- `0x140004880`

## pseudocode

```c
__int64 __fastcall wil_details_FeatureReporting_IncrementUsageInCache(
        volatile signed __int32 *a1,
        int a2,
        __int64 a3,
        _DWORD *a4)
{
  signed __int32 v4; // r8d
  _DWORD *v5; // r10
  BOOL v8; // edi
  unsigned int v9; // eax
  int v10; // edx
  unsigned int v11; // ecx
  unsigned int v12; // edx
  __int64 result; // rax

  v4 = *a1;
  v5 = a4 + 2;
  v8 = a2 == 4;
  while ( 1 )
  {
    a4[1] = 0;
    v9 = v4 | 1;
    if ( (((v4 | 1u) >> 14) & 1) != v8 )
    {
      if ( ((v9 >> 5) & 0x1FF) != 0 )
      {
        a4[1] = (v9 >> 5) & 0x1FF;
        v5 = a4 + 2;
        a4[2] = a2 == 0 ? 4 : 0;
        v9 = v4 & 0xFFFFC01E | 1;
      }
      v10 = 0;
      if ( a2 == 4 )
        v10 = 0x4000;
      v9 = v9 & 0xFFFFBFFF | v10;
    }
    v11 = (v9 >> 5) & 0x1FF;
    v12 = v11 + 1;
    if ( v11 + 1 > 0x1FF || v12 < v11 )
    {
      LOWORD(v12) = 1;
      *v5 = a2;
      a4[1] = v11;
    }
    else
    {
      v5 = a4 + 2;
    }
    result = (unsigned int)_InterlockedCompareExchange(
                             a1,
                             v9 ^ ((unsigned __int16)v9 ^ (unsigned __int16)(32 * v12)) & 0x3FE0,
                             v4);
    if ( v4 == (_DWORD)result )
      break;
    v4 = result;
  }
  a4[4] = 0;
  *a4 = (v4 & 1) == 0;
  return result;
}

```

## disassembly

```asm
0x140004880  push    rbx
0x140004882  push    rsi
0x140004883  push    rdi
0x140004884  mov     r8d, [rcx]
0x140004887  lea     r10, [r9+8]
0x14000488b  xor     edi, edi
0x14000488d  mov     ebx, edx
0x14000488f  cmp     edx, 4
0x140004892  mov     rsi, rcx
0x140004895  setz    dil
0x140004899  mov     eax, r8d
0x14000489c  mov     dword ptr [r9+4], 0
0x1400048a4  or      eax, 1
0x1400048a7  mov     ecx, eax
0x1400048a9  shr     ecx, 0Eh
0x1400048ac  and     ecx, 1
0x1400048af  cmp     ecx, edi
0x1400048b1  jz      short loc_1400048F5
0x1400048b3  mov     r11d, eax
0x1400048b6  shr     r11d, 5
0x1400048ba  and     r11d, 1FFh
0x1400048c1  jbe     short loc_1400048DE
0x1400048c3  mov     ecx, ebx
0x1400048c5  mov     [r9+4], r11d
0x1400048c9  neg     ecx
0x1400048cb  lea     r10, [r9+8]
0x1400048cf  sbb     edx, edx
0x1400048d1  not     edx
0x1400048d3  and     edx, 4
0x1400048d6  mov     [r10], edx
0x1400048d9  and     eax, 0FFFFC01Fh
0x1400048de  xor     edx, edx
0x1400048e0  mov     ecx, 4000h
0x1400048e5  cmp     ebx, 4
0x1400048e8  cmovz   edx, ecx
0x1400048eb  mov     ecx, eax
0x1400048ed  btr     ecx, 0Eh
0x1400048f1  mov     eax, edx
0x1400048f3  or      eax, ecx
0x1400048f5  mov     ecx, eax
0x1400048f7  shr     ecx, 5
0x1400048fa  and     ecx, 1FFh
0x140004900  lea     edx, [rcx+1]
0x140004903  cmp     edx, 1FFh
0x140004909  ja      short loc_140004915
0x14000490b  cmp     edx, ecx
0x14000490d  jb      short loc_140004915
0x14000490f  lea     r10, [r9+8]
0x140004913  jmp     short loc_140004921
0x140004915  mov     edx, 1
0x14000491a  mov     [r10], ebx
0x14000491d  mov     [r9+4], ecx
0x140004921  shl     edx, 5
0x140004924  xor     edx, eax
0x140004926  and     edx, 3FE0h
0x14000492c  xor     edx, eax
0x14000492e  mov     eax, r8d
0x140004931  lock cmpxchg [rsi], edx
0x140004935  jz      short loc_14000493F
0x140004937  mov     r8d, eax
0x14000493a  jmp     loc_140004899
0x14000493f  not     r8d
0x140004942  mov     dword ptr [r9+10h], 0
0x14000494a  and     r8d, 1
0x14000494e  mov     [r9], r8d
0x140004951  pop     rdi
0x140004952  pop     rsi
0x140004953  pop     rbx
0x140004954  retn
```
