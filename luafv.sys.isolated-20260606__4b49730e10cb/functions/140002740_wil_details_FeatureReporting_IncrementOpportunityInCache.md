# wil_details_FeatureReporting_IncrementOpportunityInCache

- ea: `0x140002740`
- end: `0x14000280a`
- name: `wil_details_FeatureReporting_IncrementOpportunityInCache`
- size: `202`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1400028ec`

## callees

- `0x140002740`

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
0x140002740  push    rbx
0x140002742  push    rsi
0x140002743  push    rdi
0x140002744  mov     r8d, [rcx]
0x140002747  lea     r10, [r9+8]
0x14000274b  xor     ebx, ebx
0x14000274d  mov     r11d, edx
0x140002750  cmp     edx, 5
0x140002753  mov     rdi, rcx
0x140002756  mov     esi, 1
0x14000275b  setz    bl
0x14000275e  mov     eax, r8d
0x140002761  mov     dword ptr [r9+4], 0
0x140002769  or      eax, esi
0x14000276b  mov     ecx, eax
0x14000276d  shr     ecx, 16h
0x140002770  and     ecx, esi
0x140002772  cmp     ecx, ebx
0x140002774  jz      short loc_1400027B3
0x140002776  mov     edx, eax
0x140002778  shr     edx, 0Fh
0x14000277b  and     edx, 7Fh
0x14000277e  jbe     short loc_14000279B
0x140002780  cmp     r11d, esi
0x140002783  mov     [r9+4], edx
0x140002787  mov     ecx, 5
0x14000278c  lea     r10, [r9+8]
0x140002790  cmovnz  ecx, esi
0x140002793  and     eax, 0FFC07FFFh
0x140002798  mov     [r10], ecx
0x14000279b  xor     edx, edx
0x14000279d  mov     ecx, 400000h
0x1400027a2  cmp     r11d, 5
0x1400027a6  cmovz   edx, ecx
0x1400027a9  mov     ecx, eax
0x1400027ab  btr     ecx, 16h
0x1400027af  mov     eax, edx
0x1400027b1  or      eax, ecx
0x1400027b3  mov     ecx, eax
0x1400027b5  shr     ecx, 0Fh
0x1400027b8  and     ecx, 7Fh
0x1400027bb  lea     edx, [rcx+1]
0x1400027be  cmp     edx, 7Fh
0x1400027c1  ja      short loc_1400027CD
0x1400027c3  cmp     edx, ecx
0x1400027c5  jb      short loc_1400027CD
0x1400027c7  lea     r10, [r9+8]
0x1400027cb  jmp     short loc_1400027D6
0x1400027cd  mov     edx, esi
0x1400027cf  mov     [r10], r11d
0x1400027d2  mov     [r9+4], ecx
0x1400027d6  shl     edx, 0Fh
0x1400027d9  xor     edx, eax
0x1400027db  and     edx, 3F8000h
0x1400027e1  xor     edx, eax
0x1400027e3  mov     eax, r8d
0x1400027e6  lock cmpxchg [rdi], edx
0x1400027ea  jz      short loc_1400027F4
0x1400027ec  mov     r8d, eax
0x1400027ef  jmp     loc_14000275E
0x1400027f4  not     r8d
0x1400027f7  mov     dword ptr [r9+10h], 0
0x1400027ff  and     r8d, esi
0x140002802  mov     [r9], r8d
0x140002805  pop     rdi
0x140002806  pop     rsi
0x140002807  pop     rbx
0x140002808  retn
```
