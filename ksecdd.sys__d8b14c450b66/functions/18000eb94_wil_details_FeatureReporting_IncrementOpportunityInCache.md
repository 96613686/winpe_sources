# wil_details_FeatureReporting_IncrementOpportunityInCache

- ea: `0x18000eb94`
- end: `0x18000ec5e`
- name: `wil_details_FeatureReporting_IncrementOpportunityInCache`
- size: `202`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000ed40`

## callees

- `0x18000eb94`

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
0x18000eb94  push    rbx
0x18000eb96  push    rsi
0x18000eb97  push    rdi
0x18000eb98  mov     r8d, [rcx]
0x18000eb9b  lea     r10, [r9+8]
0x18000eb9f  xor     ebx, ebx
0x18000eba1  mov     r11d, edx
0x18000eba4  cmp     edx, 5
0x18000eba7  mov     rdi, rcx
0x18000ebaa  mov     esi, 1
0x18000ebaf  setz    bl
0x18000ebb2  mov     eax, r8d
0x18000ebb5  mov     dword ptr [r9+4], 0
0x18000ebbd  or      eax, esi
0x18000ebbf  mov     ecx, eax
0x18000ebc1  shr     ecx, 16h
0x18000ebc4  and     ecx, esi
0x18000ebc6  cmp     ecx, ebx
0x18000ebc8  jz      short loc_18000EC07
0x18000ebca  mov     edx, eax
0x18000ebcc  shr     edx, 0Fh
0x18000ebcf  and     edx, 7Fh
0x18000ebd2  jbe     short loc_18000EBEF
0x18000ebd4  cmp     r11d, esi
0x18000ebd7  mov     [r9+4], edx
0x18000ebdb  mov     ecx, 5
0x18000ebe0  lea     r10, [r9+8]
0x18000ebe4  cmovnz  ecx, esi
0x18000ebe7  and     eax, 0FFC07FFFh
0x18000ebec  mov     [r10], ecx
0x18000ebef  xor     edx, edx
0x18000ebf1  mov     ecx, 400000h
0x18000ebf6  cmp     r11d, 5
0x18000ebfa  cmovz   edx, ecx
0x18000ebfd  mov     ecx, eax
0x18000ebff  btr     ecx, 16h
0x18000ec03  mov     eax, edx
0x18000ec05  or      eax, ecx
0x18000ec07  mov     ecx, eax
0x18000ec09  shr     ecx, 0Fh
0x18000ec0c  and     ecx, 7Fh
0x18000ec0f  lea     edx, [rcx+1]
0x18000ec12  cmp     edx, 7Fh
0x18000ec15  ja      short loc_18000EC21
0x18000ec17  cmp     edx, ecx
0x18000ec19  jb      short loc_18000EC21
0x18000ec1b  lea     r10, [r9+8]
0x18000ec1f  jmp     short loc_18000EC2A
0x18000ec21  mov     edx, esi
0x18000ec23  mov     [r10], r11d
0x18000ec26  mov     [r9+4], ecx
0x18000ec2a  shl     edx, 0Fh
0x18000ec2d  xor     edx, eax
0x18000ec2f  and     edx, 3F8000h
0x18000ec35  xor     edx, eax
0x18000ec37  mov     eax, r8d
0x18000ec3a  lock cmpxchg [rdi], edx
0x18000ec3e  jz      short loc_18000EC48
0x18000ec40  mov     r8d, eax
0x18000ec43  jmp     loc_18000EBB2
0x18000ec48  not     r8d
0x18000ec4b  mov     dword ptr [r9+10h], 0
0x18000ec53  and     r8d, esi
0x18000ec56  mov     [r9], r8d
0x18000ec59  pop     rdi
0x18000ec5a  pop     rsi
0x18000ec5b  pop     rbx
0x18000ec5c  retn
```
