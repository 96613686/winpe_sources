# wil_details_FeatureReporting_IncrementOpportunityInCache

- ea: `0x18000f44c`
- end: `0x18000f515`
- name: `wil_details_FeatureReporting_IncrementOpportunityInCache`
- size: `201`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180008484`

## callees

- `0x18000f44c`

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
0x18000f44c  push    rbx
0x18000f44e  push    rsi
0x18000f44f  push    rdi
0x18000f450  mov     r8d, [rcx]
0x18000f453  lea     r10, [r9+8]
0x18000f457  xor     ebx, ebx
0x18000f459  mov     r11d, edx
0x18000f45c  cmp     edx, 5
0x18000f45f  mov     rdi, rcx
0x18000f462  mov     esi, 1
0x18000f467  setz    bl
0x18000f46a  mov     eax, r8d
0x18000f46d  mov     dword ptr [r9+4], 0
0x18000f475  or      eax, esi
0x18000f477  mov     ecx, eax
0x18000f479  shr     ecx, 16h
0x18000f47c  and     ecx, esi
0x18000f47e  cmp     ecx, ebx
0x18000f480  jz      short loc_18000F4BF
0x18000f482  mov     edx, eax
0x18000f484  shr     edx, 0Fh
0x18000f487  and     edx, 7Fh
0x18000f48a  jbe     short loc_18000F4A7
0x18000f48c  cmp     r11d, esi
0x18000f48f  mov     [r9+4], edx
0x18000f493  mov     ecx, 5
0x18000f498  lea     r10, [r9+8]
0x18000f49c  cmovnz  ecx, esi
0x18000f49f  and     eax, 0FFC07FFFh
0x18000f4a4  mov     [r10], ecx
0x18000f4a7  xor     edx, edx
0x18000f4a9  mov     ecx, 400000h
0x18000f4ae  cmp     r11d, 5
0x18000f4b2  cmovz   edx, ecx
0x18000f4b5  mov     ecx, eax
0x18000f4b7  btr     ecx, 16h
0x18000f4bb  mov     eax, edx
0x18000f4bd  or      eax, ecx
0x18000f4bf  mov     ecx, eax
0x18000f4c1  shr     ecx, 0Fh
0x18000f4c4  and     ecx, 7Fh
0x18000f4c7  lea     edx, [rcx+1]
0x18000f4ca  cmp     edx, 7Fh
0x18000f4cd  ja      short loc_18000F4D9
0x18000f4cf  cmp     edx, ecx
0x18000f4d1  jb      short loc_18000F4D9
0x18000f4d3  lea     r10, [r9+8]
0x18000f4d7  jmp     short loc_18000F4E2
0x18000f4d9  mov     edx, esi
0x18000f4db  mov     [r10], r11d
0x18000f4de  mov     [r9+4], ecx
0x18000f4e2  shl     edx, 0Fh
0x18000f4e5  xor     edx, eax
0x18000f4e7  and     edx, 3F8000h
0x18000f4ed  xor     edx, eax
0x18000f4ef  mov     eax, r8d
0x18000f4f2  lock cmpxchg [rdi], edx
0x18000f4f6  jz      short loc_18000F500
0x18000f4f8  mov     r8d, eax
0x18000f4fb  jmp     loc_18000F46A
0x18000f500  not     r8d
0x18000f503  mov     dword ptr [r9+10h], 0
0x18000f50b  and     r8d, esi
0x18000f50e  mov     [r9], r8d
0x18000f511  pop     rdi
0x18000f512  pop     rsi
0x18000f513  pop     rbx
0x18000f514  retn
```
