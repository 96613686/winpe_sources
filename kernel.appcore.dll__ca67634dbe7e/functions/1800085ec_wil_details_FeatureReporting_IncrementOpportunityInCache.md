# wil_details_FeatureReporting_IncrementOpportunityInCache

- ea: `0x1800085ec`
- end: `0x1800086b5`
- name: `wil_details_FeatureReporting_IncrementOpportunityInCache`
- size: `201`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180008798`

## callees

- `0x1800085ec`

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
0x1800085ec  push    rbx
0x1800085ee  push    rsi
0x1800085ef  push    rdi
0x1800085f0  mov     r8d, [rcx]
0x1800085f3  lea     r10, [r9+8]
0x1800085f7  xor     ebx, ebx
0x1800085f9  mov     r11d, edx
0x1800085fc  cmp     edx, 5
0x1800085ff  mov     rdi, rcx
0x180008602  mov     esi, 1
0x180008607  setz    bl
0x18000860a  mov     eax, r8d
0x18000860d  mov     dword ptr [r9+4], 0
0x180008615  or      eax, esi
0x180008617  mov     ecx, eax
0x180008619  shr     ecx, 16h
0x18000861c  and     ecx, esi
0x18000861e  cmp     ecx, ebx
0x180008620  jz      short loc_18000865F
0x180008622  mov     edx, eax
0x180008624  shr     edx, 0Fh
0x180008627  and     edx, 7Fh
0x18000862a  jbe     short loc_180008647
0x18000862c  cmp     r11d, esi
0x18000862f  mov     [r9+4], edx
0x180008633  mov     ecx, 5
0x180008638  lea     r10, [r9+8]
0x18000863c  cmovnz  ecx, esi
0x18000863f  and     eax, 0FFC07FFFh
0x180008644  mov     [r10], ecx
0x180008647  xor     edx, edx
0x180008649  mov     ecx, 400000h
0x18000864e  cmp     r11d, 5
0x180008652  cmovz   edx, ecx
0x180008655  mov     ecx, eax
0x180008657  btr     ecx, 16h
0x18000865b  mov     eax, edx
0x18000865d  or      eax, ecx
0x18000865f  mov     ecx, eax
0x180008661  shr     ecx, 0Fh
0x180008664  and     ecx, 7Fh
0x180008667  lea     edx, [rcx+1]
0x18000866a  cmp     edx, 7Fh
0x18000866d  ja      short loc_180008679
0x18000866f  cmp     edx, ecx
0x180008671  jb      short loc_180008679
0x180008673  lea     r10, [r9+8]
0x180008677  jmp     short loc_180008682
0x180008679  mov     edx, esi
0x18000867b  mov     [r10], r11d
0x18000867e  mov     [r9+4], ecx
0x180008682  shl     edx, 0Fh
0x180008685  xor     edx, eax
0x180008687  and     edx, 3F8000h
0x18000868d  xor     edx, eax
0x18000868f  mov     eax, r8d
0x180008692  lock cmpxchg [rdi], edx
0x180008696  jz      short loc_1800086A0
0x180008698  mov     r8d, eax
0x18000869b  jmp     loc_18000860A
0x1800086a0  not     r8d
0x1800086a3  mov     dword ptr [r9+10h], 0
0x1800086ab  and     r8d, esi
0x1800086ae  mov     [r9], r8d
0x1800086b1  pop     rdi
0x1800086b2  pop     rsi
0x1800086b3  pop     rbx
0x1800086b4  retn
```
