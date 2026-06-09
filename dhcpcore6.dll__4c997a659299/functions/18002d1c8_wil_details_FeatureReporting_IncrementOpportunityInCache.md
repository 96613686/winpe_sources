# wil_details_FeatureReporting_IncrementOpportunityInCache

- ea: `0x18002d1c8`
- end: `0x18002d292`
- name: `wil_details_FeatureReporting_IncrementOpportunityInCache`
- size: `202`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18002d374`

## callees

- `0x18002d1c8`

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
0x18002d1c8  push    rbx
0x18002d1ca  push    rsi
0x18002d1cb  push    rdi
0x18002d1cc  mov     r8d, [rcx]
0x18002d1cf  lea     r10, [r9+8]
0x18002d1d3  xor     ebx, ebx
0x18002d1d5  mov     r11d, edx
0x18002d1d8  cmp     edx, 5
0x18002d1db  mov     rdi, rcx
0x18002d1de  mov     esi, 1
0x18002d1e3  setz    bl
0x18002d1e6  mov     eax, r8d
0x18002d1e9  mov     dword ptr [r9+4], 0
0x18002d1f1  or      eax, esi
0x18002d1f3  mov     ecx, eax
0x18002d1f5  shr     ecx, 16h
0x18002d1f8  and     ecx, esi
0x18002d1fa  cmp     ecx, ebx
0x18002d1fc  jz      short loc_18002D23B
0x18002d1fe  mov     edx, eax
0x18002d200  shr     edx, 0Fh
0x18002d203  and     edx, 7Fh
0x18002d206  jbe     short loc_18002D223
0x18002d208  cmp     r11d, esi
0x18002d20b  mov     [r9+4], edx
0x18002d20f  mov     ecx, 5
0x18002d214  lea     r10, [r9+8]
0x18002d218  cmovnz  ecx, esi
0x18002d21b  and     eax, 0FFC07FFFh
0x18002d220  mov     [r10], ecx
0x18002d223  xor     edx, edx
0x18002d225  mov     ecx, 400000h
0x18002d22a  cmp     r11d, 5
0x18002d22e  cmovz   edx, ecx
0x18002d231  mov     ecx, eax
0x18002d233  btr     ecx, 16h
0x18002d237  mov     eax, edx
0x18002d239  or      eax, ecx
0x18002d23b  mov     ecx, eax
0x18002d23d  shr     ecx, 0Fh
0x18002d240  and     ecx, 7Fh
0x18002d243  lea     edx, [rcx+1]
0x18002d246  cmp     edx, 7Fh
0x18002d249  ja      short loc_18002D255
0x18002d24b  cmp     edx, ecx
0x18002d24d  jb      short loc_18002D255
0x18002d24f  lea     r10, [r9+8]
0x18002d253  jmp     short loc_18002D25E
0x18002d255  mov     edx, esi
0x18002d257  mov     [r10], r11d
0x18002d25a  mov     [r9+4], ecx
0x18002d25e  shl     edx, 0Fh
0x18002d261  xor     edx, eax
0x18002d263  and     edx, 3F8000h
0x18002d269  xor     edx, eax
0x18002d26b  mov     eax, r8d
0x18002d26e  lock cmpxchg [rdi], edx
0x18002d272  jz      short loc_18002D27C
0x18002d274  mov     r8d, eax
0x18002d277  jmp     loc_18002D1E6
0x18002d27c  not     r8d
0x18002d27f  mov     dword ptr [r9+10h], 0
0x18002d287  and     r8d, esi
0x18002d28a  mov     [r9], r8d
0x18002d28d  pop     rdi
0x18002d28e  pop     rsi
0x18002d28f  pop     rbx
0x18002d290  retn
```
