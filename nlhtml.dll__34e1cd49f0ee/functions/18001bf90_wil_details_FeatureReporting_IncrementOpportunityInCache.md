# wil_details_FeatureReporting_IncrementOpportunityInCache

- ea: `0x18001bf90`
- end: `0x18001c059`
- name: `wil_details_FeatureReporting_IncrementOpportunityInCache`
- size: `201`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18001c13c`

## callees

- `0x18001bf90`

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
0x18001bf90  push    rbx
0x18001bf92  push    rsi
0x18001bf93  push    rdi
0x18001bf94  mov     r8d, [rcx]
0x18001bf97  lea     r10, [r9+8]
0x18001bf9b  xor     ebx, ebx
0x18001bf9d  mov     r11d, edx
0x18001bfa0  cmp     edx, 5
0x18001bfa3  mov     rdi, rcx
0x18001bfa6  mov     esi, 1
0x18001bfab  setz    bl
0x18001bfae  mov     eax, r8d
0x18001bfb1  mov     dword ptr [r9+4], 0
0x18001bfb9  or      eax, esi
0x18001bfbb  mov     ecx, eax
0x18001bfbd  shr     ecx, 16h
0x18001bfc0  and     ecx, esi
0x18001bfc2  cmp     ecx, ebx
0x18001bfc4  jz      short loc_18001C003
0x18001bfc6  mov     edx, eax
0x18001bfc8  shr     edx, 0Fh
0x18001bfcb  and     edx, 7Fh
0x18001bfce  jbe     short loc_18001BFEB
0x18001bfd0  cmp     r11d, esi
0x18001bfd3  mov     [r9+4], edx
0x18001bfd7  mov     ecx, 5
0x18001bfdc  lea     r10, [r9+8]
0x18001bfe0  cmovnz  ecx, esi
0x18001bfe3  and     eax, 0FFC07FFFh
0x18001bfe8  mov     [r10], ecx
0x18001bfeb  xor     edx, edx
0x18001bfed  mov     ecx, 400000h
0x18001bff2  cmp     r11d, 5
0x18001bff6  cmovz   edx, ecx
0x18001bff9  mov     ecx, eax
0x18001bffb  btr     ecx, 16h
0x18001bfff  mov     eax, edx
0x18001c001  or      eax, ecx
0x18001c003  mov     ecx, eax
0x18001c005  shr     ecx, 0Fh
0x18001c008  and     ecx, 7Fh
0x18001c00b  lea     edx, [rcx+1]
0x18001c00e  cmp     edx, 7Fh
0x18001c011  ja      short loc_18001C01D
0x18001c013  cmp     edx, ecx
0x18001c015  jb      short loc_18001C01D
0x18001c017  lea     r10, [r9+8]
0x18001c01b  jmp     short loc_18001C026
0x18001c01d  mov     edx, esi
0x18001c01f  mov     [r10], r11d
0x18001c022  mov     [r9+4], ecx
0x18001c026  shl     edx, 0Fh
0x18001c029  xor     edx, eax
0x18001c02b  and     edx, 3F8000h
0x18001c031  xor     edx, eax
0x18001c033  mov     eax, r8d
0x18001c036  lock cmpxchg [rdi], edx
0x18001c03a  jz      short loc_18001C044
0x18001c03c  mov     r8d, eax
0x18001c03f  jmp     loc_18001BFAE
0x18001c044  not     r8d
0x18001c047  mov     dword ptr [r9+10h], 0
0x18001c04f  and     r8d, esi
0x18001c052  mov     [r9], r8d
0x18001c055  pop     rdi
0x18001c056  pop     rsi
0x18001c057  pop     rbx
0x18001c058  retn
```
