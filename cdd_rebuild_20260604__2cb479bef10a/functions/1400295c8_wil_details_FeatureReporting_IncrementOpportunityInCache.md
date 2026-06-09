# wil_details_FeatureReporting_IncrementOpportunityInCache

- ea: `0x1400295c8`
- end: `0x140029692`
- name: `wil_details_FeatureReporting_IncrementOpportunityInCache`
- size: `202`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140029774`

## callees

- `0x1400295c8`

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
0x1400295c8  push    rbx
0x1400295ca  push    rsi
0x1400295cb  push    rdi
0x1400295cc  mov     r8d, [rcx]
0x1400295cf  lea     r10, [r9+8]
0x1400295d3  xor     ebx, ebx
0x1400295d5  mov     r11d, edx
0x1400295d8  cmp     edx, 5
0x1400295db  mov     rdi, rcx
0x1400295de  mov     esi, 1
0x1400295e3  setz    bl
0x1400295e6  mov     eax, r8d
0x1400295e9  mov     dword ptr [r9+4], 0
0x1400295f1  or      eax, esi
0x1400295f3  mov     ecx, eax
0x1400295f5  shr     ecx, 16h
0x1400295f8  and     ecx, esi
0x1400295fa  cmp     ecx, ebx
0x1400295fc  jz      short loc_14002963B
0x1400295fe  mov     edx, eax
0x140029600  shr     edx, 0Fh
0x140029603  and     edx, 7Fh
0x140029606  jbe     short loc_140029623
0x140029608  cmp     r11d, esi
0x14002960b  mov     [r9+4], edx
0x14002960f  mov     ecx, 5
0x140029614  lea     r10, [r9+8]
0x140029618  cmovnz  ecx, esi
0x14002961b  and     eax, 0FFC07FFFh
0x140029620  mov     [r10], ecx
0x140029623  xor     edx, edx
0x140029625  mov     ecx, 400000h
0x14002962a  cmp     r11d, 5
0x14002962e  cmovz   edx, ecx
0x140029631  mov     ecx, eax
0x140029633  btr     ecx, 16h
0x140029637  mov     eax, edx
0x140029639  or      eax, ecx
0x14002963b  mov     ecx, eax
0x14002963d  shr     ecx, 0Fh
0x140029640  and     ecx, 7Fh
0x140029643  lea     edx, [rcx+1]
0x140029646  cmp     edx, 7Fh
0x140029649  ja      short loc_140029655
0x14002964b  cmp     edx, ecx
0x14002964d  jb      short loc_140029655
0x14002964f  lea     r10, [r9+8]
0x140029653  jmp     short loc_14002965E
0x140029655  mov     edx, esi
0x140029657  mov     [r10], r11d
0x14002965a  mov     [r9+4], ecx
0x14002965e  shl     edx, 0Fh
0x140029661  xor     edx, eax
0x140029663  and     edx, 3F8000h
0x140029669  xor     edx, eax
0x14002966b  mov     eax, r8d
0x14002966e  lock cmpxchg [rdi], edx
0x140029672  jz      short loc_14002967C
0x140029674  mov     r8d, eax
0x140029677  jmp     loc_1400295E6
0x14002967c  not     r8d
0x14002967f  mov     dword ptr [r9+10h], 0
0x140029687  and     r8d, esi
0x14002968a  mov     [r9], r8d
0x14002968d  pop     rdi
0x14002968e  pop     rsi
0x14002968f  pop     rbx
0x140029690  retn
```
