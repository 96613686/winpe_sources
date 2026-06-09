# wil_details_FeatureReporting_IncrementOpportunityInCache

- ea: `0x180021ee0`
- end: `0x180021fa9`
- name: `wil_details_FeatureReporting_IncrementOpportunityInCache`
- size: `201`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18002208c`

## callees

- `0x180021ee0`

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
0x180021ee0  push    rbx
0x180021ee2  push    rsi
0x180021ee3  push    rdi
0x180021ee4  mov     r8d, [rcx]
0x180021ee7  lea     r10, [r9+8]
0x180021eeb  xor     ebx, ebx
0x180021eed  mov     r11d, edx
0x180021ef0  cmp     edx, 5
0x180021ef3  mov     rdi, rcx
0x180021ef6  mov     esi, 1
0x180021efb  setz    bl
0x180021efe  mov     eax, r8d
0x180021f01  mov     dword ptr [r9+4], 0
0x180021f09  or      eax, esi
0x180021f0b  mov     ecx, eax
0x180021f0d  shr     ecx, 16h
0x180021f10  and     ecx, esi
0x180021f12  cmp     ecx, ebx
0x180021f14  jz      short loc_180021F53
0x180021f16  mov     edx, eax
0x180021f18  shr     edx, 0Fh
0x180021f1b  and     edx, 7Fh
0x180021f1e  jbe     short loc_180021F3B
0x180021f20  cmp     r11d, esi
0x180021f23  mov     [r9+4], edx
0x180021f27  mov     ecx, 5
0x180021f2c  lea     r10, [r9+8]
0x180021f30  cmovnz  ecx, esi
0x180021f33  and     eax, 0FFC07FFFh
0x180021f38  mov     [r10], ecx
0x180021f3b  xor     edx, edx
0x180021f3d  mov     ecx, 400000h
0x180021f42  cmp     r11d, 5
0x180021f46  cmovz   edx, ecx
0x180021f49  mov     ecx, eax
0x180021f4b  btr     ecx, 16h
0x180021f4f  mov     eax, edx
0x180021f51  or      eax, ecx
0x180021f53  mov     ecx, eax
0x180021f55  shr     ecx, 0Fh
0x180021f58  and     ecx, 7Fh
0x180021f5b  lea     edx, [rcx+1]
0x180021f5e  cmp     edx, 7Fh
0x180021f61  ja      short loc_180021F6D
0x180021f63  cmp     edx, ecx
0x180021f65  jb      short loc_180021F6D
0x180021f67  lea     r10, [r9+8]
0x180021f6b  jmp     short loc_180021F76
0x180021f6d  mov     edx, esi
0x180021f6f  mov     [r10], r11d
0x180021f72  mov     [r9+4], ecx
0x180021f76  shl     edx, 0Fh
0x180021f79  xor     edx, eax
0x180021f7b  and     edx, 3F8000h
0x180021f81  xor     edx, eax
0x180021f83  mov     eax, r8d
0x180021f86  lock cmpxchg [rdi], edx
0x180021f8a  jz      short loc_180021F94
0x180021f8c  mov     r8d, eax
0x180021f8f  jmp     loc_180021EFE
0x180021f94  not     r8d
0x180021f97  mov     dword ptr [r9+10h], 0
0x180021f9f  and     r8d, esi
0x180021fa2  mov     [r9], r8d
0x180021fa5  pop     rdi
0x180021fa6  pop     rsi
0x180021fa7  pop     rbx
0x180021fa8  retn
```
