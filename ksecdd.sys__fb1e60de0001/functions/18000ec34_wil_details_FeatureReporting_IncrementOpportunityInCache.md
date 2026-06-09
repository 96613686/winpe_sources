# wil_details_FeatureReporting_IncrementOpportunityInCache

- ea: `0x18000ec34`
- end: `0x18000ecfe`
- name: `wil_details_FeatureReporting_IncrementOpportunityInCache`
- size: `202`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000ede0`

## callees

- `0x18000ec34`

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
0x18000ec34  push    rbx
0x18000ec36  push    rsi
0x18000ec37  push    rdi
0x18000ec38  mov     r8d, [rcx]
0x18000ec3b  lea     r10, [r9+8]
0x18000ec3f  xor     ebx, ebx
0x18000ec41  mov     r11d, edx
0x18000ec44  cmp     edx, 5
0x18000ec47  mov     rdi, rcx
0x18000ec4a  mov     esi, 1
0x18000ec4f  setz    bl
0x18000ec52  mov     eax, r8d
0x18000ec55  mov     dword ptr [r9+4], 0
0x18000ec5d  or      eax, esi
0x18000ec5f  mov     ecx, eax
0x18000ec61  shr     ecx, 16h
0x18000ec64  and     ecx, esi
0x18000ec66  cmp     ecx, ebx
0x18000ec68  jz      short loc_18000ECA7
0x18000ec6a  mov     edx, eax
0x18000ec6c  shr     edx, 0Fh
0x18000ec6f  and     edx, 7Fh
0x18000ec72  jbe     short loc_18000EC8F
0x18000ec74  cmp     r11d, esi
0x18000ec77  mov     [r9+4], edx
0x18000ec7b  mov     ecx, 5
0x18000ec80  lea     r10, [r9+8]
0x18000ec84  cmovnz  ecx, esi
0x18000ec87  and     eax, 0FFC07FFFh
0x18000ec8c  mov     [r10], ecx
0x18000ec8f  xor     edx, edx
0x18000ec91  mov     ecx, 400000h
0x18000ec96  cmp     r11d, 5
0x18000ec9a  cmovz   edx, ecx
0x18000ec9d  mov     ecx, eax
0x18000ec9f  btr     ecx, 16h
0x18000eca3  mov     eax, edx
0x18000eca5  or      eax, ecx
0x18000eca7  mov     ecx, eax
0x18000eca9  shr     ecx, 0Fh
0x18000ecac  and     ecx, 7Fh
0x18000ecaf  lea     edx, [rcx+1]
0x18000ecb2  cmp     edx, 7Fh
0x18000ecb5  ja      short loc_18000ECC1
0x18000ecb7  cmp     edx, ecx
0x18000ecb9  jb      short loc_18000ECC1
0x18000ecbb  lea     r10, [r9+8]
0x18000ecbf  jmp     short loc_18000ECCA
0x18000ecc1  mov     edx, esi
0x18000ecc3  mov     [r10], r11d
0x18000ecc6  mov     [r9+4], ecx
0x18000ecca  shl     edx, 0Fh
0x18000eccd  xor     edx, eax
0x18000eccf  and     edx, 3F8000h
0x18000ecd5  xor     edx, eax
0x18000ecd7  mov     eax, r8d
0x18000ecda  lock cmpxchg [rdi], edx
0x18000ecde  jz      short loc_18000ECE8
0x18000ece0  mov     r8d, eax
0x18000ece3  jmp     loc_18000EC52
0x18000ece8  not     r8d
0x18000eceb  mov     dword ptr [r9+10h], 0
0x18000ecf3  and     r8d, esi
0x18000ecf6  mov     [r9], r8d
0x18000ecf9  pop     rdi
0x18000ecfa  pop     rsi
0x18000ecfb  pop     rbx
0x18000ecfc  retn
```
