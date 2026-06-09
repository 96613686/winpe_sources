# wil_details_FeatureReporting_IncrementOpportunityInCache

- ea: `0x18001dab0`
- end: `0x18001db7a`
- name: `wil_details_FeatureReporting_IncrementOpportunityInCache`
- size: `202`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18001dc5c`

## callees

- `0x18001dab0`

## pseudocode

```c
__int64 __fastcall wil_details_FeatureReporting_IncrementOpportunityInCache(
        volatile signed __int32 *a1,
        int a2,
        __int64 a3,
        _DWORD *a4)
{
  signed __int32 v4; // r8d
  int *v5; // r10
  BOOL v8; // ebx
  unsigned int v9; // eax
  int v10; // ecx
  int v11; // edx
  unsigned int v12; // ecx
  unsigned int v13; // edx
  __int64 result; // rax

  v4 = *a1;
  v5 = a4 + 2;
  v8 = a2 == 5;
  while ( 1 )
  {
    a4[1] = 0;
    v9 = v4 | 1;
    if ( (((v4 | 1u) >> 22) & 1) != v8 )
    {
      if ( ((v9 >> 15) & 0x7F) != 0 )
      {
        a4[1] = (v9 >> 15) & 0x7F;
        v10 = 5;
        v5 = a4 + 2;
        if ( a2 != 1 )
          v10 = 1;
        v9 = v4 & 0xFFC07FFE | 1;
        *v5 = v10;
      }
      v11 = 0;
      if ( a2 == 5 )
        v11 = 0x400000;
      v9 = v9 & 0xFFBFFFFF | v11;
    }
    v12 = (v9 >> 15) & 0x7F;
    v13 = v12 + 1;
    if ( v12 + 1 > 0x7F || v13 < v12 )
    {
      v13 = 1;
      *v5 = a2;
      a4[1] = v12;
    }
    else
    {
      v5 = a4 + 2;
    }
    result = (unsigned int)_InterlockedCompareExchange(a1, v9 ^ (v9 ^ (v13 << 15)) & 0x3F8000, v4);
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
0x18001dab0  push    rbx
0x18001dab2  push    rsi
0x18001dab3  push    rdi
0x18001dab4  mov     r8d, [rcx]
0x18001dab7  lea     r10, [r9+8]
0x18001dabb  xor     ebx, ebx
0x18001dabd  mov     r11d, edx
0x18001dac0  cmp     edx, 5
0x18001dac3  mov     rdi, rcx
0x18001dac6  mov     esi, 1
0x18001dacb  setz    bl
0x18001dace  mov     eax, r8d
0x18001dad1  mov     dword ptr [r9+4], 0
0x18001dad9  or      eax, esi
0x18001dadb  mov     ecx, eax
0x18001dadd  shr     ecx, 16h
0x18001dae0  and     ecx, esi
0x18001dae2  cmp     ecx, ebx
0x18001dae4  jz      short loc_18001DB23
0x18001dae6  mov     edx, eax
0x18001dae8  shr     edx, 0Fh
0x18001daeb  and     edx, 7Fh
0x18001daee  jbe     short loc_18001DB0B
0x18001daf0  cmp     r11d, esi
0x18001daf3  mov     [r9+4], edx
0x18001daf7  mov     ecx, 5
0x18001dafc  lea     r10, [r9+8]
0x18001db00  cmovnz  ecx, esi
0x18001db03  and     eax, 0FFC07FFFh
0x18001db08  mov     [r10], ecx
0x18001db0b  xor     edx, edx
0x18001db0d  mov     ecx, 400000h
0x18001db12  cmp     r11d, 5
0x18001db16  cmovz   edx, ecx
0x18001db19  mov     ecx, eax
0x18001db1b  btr     ecx, 16h
0x18001db1f  mov     eax, edx
0x18001db21  or      eax, ecx
0x18001db23  mov     ecx, eax
0x18001db25  shr     ecx, 0Fh
0x18001db28  and     ecx, 7Fh
0x18001db2b  lea     edx, [rcx+1]
0x18001db2e  cmp     edx, 7Fh
0x18001db31  ja      short loc_18001DB3D
0x18001db33  cmp     edx, ecx
0x18001db35  jb      short loc_18001DB3D
0x18001db37  lea     r10, [r9+8]
0x18001db3b  jmp     short loc_18001DB46
0x18001db3d  mov     edx, esi
0x18001db3f  mov     [r10], r11d
0x18001db42  mov     [r9+4], ecx
0x18001db46  shl     edx, 0Fh
0x18001db49  xor     edx, eax
0x18001db4b  and     edx, 3F8000h
0x18001db51  xor     edx, eax
0x18001db53  mov     eax, r8d
0x18001db56  lock cmpxchg [rdi], edx
0x18001db5a  jz      short loc_18001DB64
0x18001db5c  mov     r8d, eax
0x18001db5f  jmp     loc_18001DACE
0x18001db64  not     r8d
0x18001db67  mov     dword ptr [r9+10h], 0
0x18001db6f  and     r8d, esi
0x18001db72  mov     [r9], r8d
0x18001db75  pop     rdi
0x18001db76  pop     rsi
0x18001db77  pop     rbx
0x18001db78  retn
```
