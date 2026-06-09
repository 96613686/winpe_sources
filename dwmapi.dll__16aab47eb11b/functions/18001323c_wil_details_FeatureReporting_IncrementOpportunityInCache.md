# wil_details_FeatureReporting_IncrementOpportunityInCache

- ea: `0x18001323c`
- end: `0x180013305`
- name: `wil_details_FeatureReporting_IncrementOpportunityInCache`
- size: `201`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800133e8`

## callees

- `0x18001323c`

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
0x18001323c  push    rbx
0x18001323e  push    rsi
0x18001323f  push    rdi
0x180013240  mov     r8d, [rcx]
0x180013243  lea     r10, [r9+8]
0x180013247  xor     ebx, ebx
0x180013249  mov     r11d, edx
0x18001324c  cmp     edx, 5
0x18001324f  mov     rdi, rcx
0x180013252  mov     esi, 1
0x180013257  setz    bl
0x18001325a  mov     eax, r8d
0x18001325d  mov     dword ptr [r9+4], 0
0x180013265  or      eax, esi
0x180013267  mov     ecx, eax
0x180013269  shr     ecx, 16h
0x18001326c  and     ecx, esi
0x18001326e  cmp     ecx, ebx
0x180013270  jz      short loc_1800132AF
0x180013272  mov     edx, eax
0x180013274  shr     edx, 0Fh
0x180013277  and     edx, 7Fh
0x18001327a  jbe     short loc_180013297
0x18001327c  cmp     r11d, esi
0x18001327f  mov     [r9+4], edx
0x180013283  mov     ecx, 5
0x180013288  lea     r10, [r9+8]
0x18001328c  cmovnz  ecx, esi
0x18001328f  and     eax, 0FFC07FFFh
0x180013294  mov     [r10], ecx
0x180013297  xor     edx, edx
0x180013299  mov     ecx, 400000h
0x18001329e  cmp     r11d, 5
0x1800132a2  cmovz   edx, ecx
0x1800132a5  mov     ecx, eax
0x1800132a7  btr     ecx, 16h
0x1800132ab  mov     eax, edx
0x1800132ad  or      eax, ecx
0x1800132af  mov     ecx, eax
0x1800132b1  shr     ecx, 0Fh
0x1800132b4  and     ecx, 7Fh
0x1800132b7  lea     edx, [rcx+1]
0x1800132ba  cmp     edx, 7Fh
0x1800132bd  ja      short loc_1800132C9
0x1800132bf  cmp     edx, ecx
0x1800132c1  jb      short loc_1800132C9
0x1800132c3  lea     r10, [r9+8]
0x1800132c7  jmp     short loc_1800132D2
0x1800132c9  mov     edx, esi
0x1800132cb  mov     [r10], r11d
0x1800132ce  mov     [r9+4], ecx
0x1800132d2  shl     edx, 0Fh
0x1800132d5  xor     edx, eax
0x1800132d7  and     edx, 3F8000h
0x1800132dd  xor     edx, eax
0x1800132df  mov     eax, r8d
0x1800132e2  lock cmpxchg [rdi], edx
0x1800132e6  jz      short loc_1800132F0
0x1800132e8  mov     r8d, eax
0x1800132eb  jmp     loc_18001325A
0x1800132f0  not     r8d
0x1800132f3  mov     dword ptr [r9+10h], 0
0x1800132fb  and     r8d, esi
0x1800132fe  mov     [r9], r8d
0x180013301  pop     rdi
0x180013302  pop     rsi
0x180013303  pop     rbx
0x180013304  retn
```
