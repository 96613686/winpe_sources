# wil_details_FeatureReporting_IncrementOpportunityInCache

- ea: `0x1400183e0`
- end: `0x1400184a9`
- name: `wil_details_FeatureReporting_IncrementOpportunityInCache`
- size: `201`
- prototype: `__int64 __fastcall(volatile signed __int32 *, int, __int64, _DWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14001858c`

## callees

- `0x1400183e0`

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
0x1400183e0  push    rbx
0x1400183e2  push    rsi
0x1400183e3  push    rdi
0x1400183e4  mov     r8d, [rcx]
0x1400183e7  lea     r10, [r9+8]
0x1400183eb  xor     ebx, ebx
0x1400183ed  mov     r11d, edx
0x1400183f0  cmp     edx, 5
0x1400183f3  mov     rdi, rcx
0x1400183f6  mov     esi, 1
0x1400183fb  setz    bl
0x1400183fe  mov     eax, r8d
0x140018401  mov     dword ptr [r9+4], 0
0x140018409  or      eax, esi
0x14001840b  mov     ecx, eax
0x14001840d  shr     ecx, 16h
0x140018410  and     ecx, esi
0x140018412  cmp     ecx, ebx
0x140018414  jz      short loc_140018453
0x140018416  mov     edx, eax
0x140018418  shr     edx, 0Fh
0x14001841b  and     edx, 7Fh
0x14001841e  jbe     short loc_14001843B
0x140018420  cmp     r11d, esi
0x140018423  mov     [r9+4], edx
0x140018427  mov     ecx, 5
0x14001842c  lea     r10, [r9+8]
0x140018430  cmovnz  ecx, esi
0x140018433  and     eax, 0FFC07FFFh
0x140018438  mov     [r10], ecx
0x14001843b  xor     edx, edx
0x14001843d  mov     ecx, 400000h
0x140018442  cmp     r11d, 5
0x140018446  cmovz   edx, ecx
0x140018449  mov     ecx, eax
0x14001844b  btr     ecx, 16h
0x14001844f  mov     eax, edx
0x140018451  or      eax, ecx
0x140018453  mov     ecx, eax
0x140018455  shr     ecx, 0Fh
0x140018458  and     ecx, 7Fh
0x14001845b  lea     edx, [rcx+1]
0x14001845e  cmp     edx, 7Fh
0x140018461  ja      short loc_14001846D
0x140018463  cmp     edx, ecx
0x140018465  jb      short loc_14001846D
0x140018467  lea     r10, [r9+8]
0x14001846b  jmp     short loc_140018476
0x14001846d  mov     edx, esi
0x14001846f  mov     [r10], r11d
0x140018472  mov     [r9+4], ecx
0x140018476  shl     edx, 0Fh
0x140018479  xor     edx, eax
0x14001847b  and     edx, 3F8000h
0x140018481  xor     edx, eax
0x140018483  mov     eax, r8d
0x140018486  lock cmpxchg [rdi], edx
0x14001848a  jz      short loc_140018494
0x14001848c  mov     r8d, eax
0x14001848f  jmp     loc_1400183FE
0x140018494  not     r8d
0x140018497  mov     dword ptr [r9+10h], 0
0x14001849f  and     r8d, esi
0x1400184a2  mov     [r9], r8d
0x1400184a5  pop     rdi
0x1400184a6  pop     rsi
0x1400184a7  pop     rbx
0x1400184a8  retn
```
