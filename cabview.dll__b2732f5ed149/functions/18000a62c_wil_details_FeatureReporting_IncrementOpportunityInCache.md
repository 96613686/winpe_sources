# wil_details_FeatureReporting_IncrementOpportunityInCache

- ea: `0x18000a62c`
- end: `0x18000a6f5`
- name: `wil_details_FeatureReporting_IncrementOpportunityInCache`
- size: `201`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000a7d8`

## callees

- `0x18000a62c`

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
0x18000a62c  push    rbx
0x18000a62e  push    rsi
0x18000a62f  push    rdi
0x18000a630  mov     r8d, [rcx]
0x18000a633  lea     r10, [r9+8]
0x18000a637  xor     ebx, ebx
0x18000a639  mov     r11d, edx
0x18000a63c  cmp     edx, 5
0x18000a63f  mov     rdi, rcx
0x18000a642  mov     esi, 1
0x18000a647  setz    bl
0x18000a64a  mov     eax, r8d
0x18000a64d  mov     dword ptr [r9+4], 0
0x18000a655  or      eax, esi
0x18000a657  mov     ecx, eax
0x18000a659  shr     ecx, 16h
0x18000a65c  and     ecx, esi
0x18000a65e  cmp     ecx, ebx
0x18000a660  jz      short loc_18000A69F
0x18000a662  mov     edx, eax
0x18000a664  shr     edx, 0Fh
0x18000a667  and     edx, 7Fh
0x18000a66a  jbe     short loc_18000A687
0x18000a66c  cmp     r11d, esi
0x18000a66f  mov     [r9+4], edx
0x18000a673  mov     ecx, 5
0x18000a678  lea     r10, [r9+8]
0x18000a67c  cmovnz  ecx, esi
0x18000a67f  and     eax, 0FFC07FFFh
0x18000a684  mov     [r10], ecx
0x18000a687  xor     edx, edx
0x18000a689  mov     ecx, 400000h
0x18000a68e  cmp     r11d, 5
0x18000a692  cmovz   edx, ecx
0x18000a695  mov     ecx, eax
0x18000a697  btr     ecx, 16h
0x18000a69b  mov     eax, edx
0x18000a69d  or      eax, ecx
0x18000a69f  mov     ecx, eax
0x18000a6a1  shr     ecx, 0Fh
0x18000a6a4  and     ecx, 7Fh
0x18000a6a7  lea     edx, [rcx+1]
0x18000a6aa  cmp     edx, 7Fh
0x18000a6ad  ja      short loc_18000A6B9
0x18000a6af  cmp     edx, ecx
0x18000a6b1  jb      short loc_18000A6B9
0x18000a6b3  lea     r10, [r9+8]
0x18000a6b7  jmp     short loc_18000A6C2
0x18000a6b9  mov     edx, esi
0x18000a6bb  mov     [r10], r11d
0x18000a6be  mov     [r9+4], ecx
0x18000a6c2  shl     edx, 0Fh
0x18000a6c5  xor     edx, eax
0x18000a6c7  and     edx, 3F8000h
0x18000a6cd  xor     edx, eax
0x18000a6cf  mov     eax, r8d
0x18000a6d2  lock cmpxchg [rdi], edx
0x18000a6d6  jz      short loc_18000A6E0
0x18000a6d8  mov     r8d, eax
0x18000a6db  jmp     loc_18000A64A
0x18000a6e0  not     r8d
0x18000a6e3  mov     dword ptr [r9+10h], 0
0x18000a6eb  and     r8d, esi
0x18000a6ee  mov     [r9], r8d
0x18000a6f1  pop     rdi
0x18000a6f2  pop     rsi
0x18000a6f3  pop     rbx
0x18000a6f4  retn
```
