# wil_details_FeatureReporting_IncrementOpportunityInCache

- ea: `0x14000ddf0`
- end: `0x14000deba`
- name: `wil_details_FeatureReporting_IncrementOpportunityInCache`
- size: `202`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14000df9c`

## callees

- `0x14000ddf0`

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
0x14000ddf0  push    rbx
0x14000ddf2  push    rsi
0x14000ddf3  push    rdi
0x14000ddf4  mov     r8d, [rcx]
0x14000ddf7  lea     r10, [r9+8]
0x14000ddfb  xor     ebx, ebx
0x14000ddfd  mov     r11d, edx
0x14000de00  cmp     edx, 5
0x14000de03  mov     rdi, rcx
0x14000de06  mov     esi, 1
0x14000de0b  setz    bl
0x14000de0e  mov     eax, r8d
0x14000de11  mov     dword ptr [r9+4], 0
0x14000de19  or      eax, esi
0x14000de1b  mov     ecx, eax
0x14000de1d  shr     ecx, 16h
0x14000de20  and     ecx, esi
0x14000de22  cmp     ecx, ebx
0x14000de24  jz      short loc_14000DE63
0x14000de26  mov     edx, eax
0x14000de28  shr     edx, 0Fh
0x14000de2b  and     edx, 7Fh
0x14000de2e  jbe     short loc_14000DE4B
0x14000de30  cmp     r11d, esi
0x14000de33  mov     [r9+4], edx
0x14000de37  mov     ecx, 5
0x14000de3c  lea     r10, [r9+8]
0x14000de40  cmovnz  ecx, esi
0x14000de43  and     eax, 0FFC07FFFh
0x14000de48  mov     [r10], ecx
0x14000de4b  xor     edx, edx
0x14000de4d  mov     ecx, 400000h
0x14000de52  cmp     r11d, 5
0x14000de56  cmovz   edx, ecx
0x14000de59  mov     ecx, eax
0x14000de5b  btr     ecx, 16h
0x14000de5f  mov     eax, edx
0x14000de61  or      eax, ecx
0x14000de63  mov     ecx, eax
0x14000de65  shr     ecx, 0Fh
0x14000de68  and     ecx, 7Fh
0x14000de6b  lea     edx, [rcx+1]
0x14000de6e  cmp     edx, 7Fh
0x14000de71  ja      short loc_14000DE7D
0x14000de73  cmp     edx, ecx
0x14000de75  jb      short loc_14000DE7D
0x14000de77  lea     r10, [r9+8]
0x14000de7b  jmp     short loc_14000DE86
0x14000de7d  mov     edx, esi
0x14000de7f  mov     [r10], r11d
0x14000de82  mov     [r9+4], ecx
0x14000de86  shl     edx, 0Fh
0x14000de89  xor     edx, eax
0x14000de8b  and     edx, 3F8000h
0x14000de91  xor     edx, eax
0x14000de93  mov     eax, r8d
0x14000de96  lock cmpxchg [rdi], edx
0x14000de9a  jz      short loc_14000DEA4
0x14000de9c  mov     r8d, eax
0x14000de9f  jmp     loc_14000DE0E
0x14000dea4  not     r8d
0x14000dea7  mov     dword ptr [r9+10h], 0
0x14000deaf  and     r8d, esi
0x14000deb2  mov     [r9], r8d
0x14000deb5  pop     rdi
0x14000deb6  pop     rsi
0x14000deb7  pop     rbx
0x14000deb8  retn
```
