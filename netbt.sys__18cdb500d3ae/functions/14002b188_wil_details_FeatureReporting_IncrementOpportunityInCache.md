# wil_details_FeatureReporting_IncrementOpportunityInCache

- ea: `0x14002b188`
- end: `0x14002b252`
- name: `wil_details_FeatureReporting_IncrementOpportunityInCache`
- size: `202`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14002b334`

## callees

- `0x14002b188`

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
0x14002b188  push    rbx
0x14002b18a  push    rsi
0x14002b18b  push    rdi
0x14002b18c  mov     r8d, [rcx]
0x14002b18f  lea     r10, [r9+8]
0x14002b193  xor     ebx, ebx
0x14002b195  mov     r11d, edx
0x14002b198  cmp     edx, 5
0x14002b19b  mov     rdi, rcx
0x14002b19e  mov     esi, 1
0x14002b1a3  setz    bl
0x14002b1a6  mov     eax, r8d
0x14002b1a9  mov     dword ptr [r9+4], 0
0x14002b1b1  or      eax, esi
0x14002b1b3  mov     ecx, eax
0x14002b1b5  shr     ecx, 16h
0x14002b1b8  and     ecx, esi
0x14002b1ba  cmp     ecx, ebx
0x14002b1bc  jz      short loc_14002B1FB
0x14002b1be  mov     edx, eax
0x14002b1c0  shr     edx, 0Fh
0x14002b1c3  and     edx, 7Fh
0x14002b1c6  jbe     short loc_14002B1E3
0x14002b1c8  cmp     r11d, esi
0x14002b1cb  mov     [r9+4], edx
0x14002b1cf  mov     ecx, 5
0x14002b1d4  lea     r10, [r9+8]
0x14002b1d8  cmovnz  ecx, esi
0x14002b1db  and     eax, 0FFC07FFFh
0x14002b1e0  mov     [r10], ecx
0x14002b1e3  xor     edx, edx
0x14002b1e5  mov     ecx, 400000h
0x14002b1ea  cmp     r11d, 5
0x14002b1ee  cmovz   edx, ecx
0x14002b1f1  mov     ecx, eax
0x14002b1f3  btr     ecx, 16h
0x14002b1f7  mov     eax, edx
0x14002b1f9  or      eax, ecx
0x14002b1fb  mov     ecx, eax
0x14002b1fd  shr     ecx, 0Fh
0x14002b200  and     ecx, 7Fh
0x14002b203  lea     edx, [rcx+1]
0x14002b206  cmp     edx, 7Fh
0x14002b209  ja      short loc_14002B215
0x14002b20b  cmp     edx, ecx
0x14002b20d  jb      short loc_14002B215
0x14002b20f  lea     r10, [r9+8]
0x14002b213  jmp     short loc_14002B21E
0x14002b215  mov     edx, esi
0x14002b217  mov     [r10], r11d
0x14002b21a  mov     [r9+4], ecx
0x14002b21e  shl     edx, 0Fh
0x14002b221  xor     edx, eax
0x14002b223  and     edx, 3F8000h
0x14002b229  xor     edx, eax
0x14002b22b  mov     eax, r8d
0x14002b22e  lock cmpxchg [rdi], edx
0x14002b232  jz      short loc_14002B23C
0x14002b234  mov     r8d, eax
0x14002b237  jmp     loc_14002B1A6
0x14002b23c  not     r8d
0x14002b23f  mov     dword ptr [r9+10h], 0
0x14002b247  and     r8d, esi
0x14002b24a  mov     [r9], r8d
0x14002b24d  pop     rdi
0x14002b24e  pop     rsi
0x14002b24f  pop     rbx
0x14002b250  retn
```
