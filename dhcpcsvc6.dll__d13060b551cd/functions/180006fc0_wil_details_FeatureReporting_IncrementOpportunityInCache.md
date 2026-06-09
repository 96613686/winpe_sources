# wil_details_FeatureReporting_IncrementOpportunityInCache

- ea: `0x180006fc0`
- end: `0x180007089`
- name: `wil_details_FeatureReporting_IncrementOpportunityInCache`
- size: `201`
- prototype: `__int64 __fastcall(volatile signed __int32 *, int, __int64, _DWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180002ad0`

## callees

- `0x180006fc0`

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
0x180006fc0  push    rbx
0x180006fc2  push    rsi
0x180006fc3  push    rdi
0x180006fc4  mov     r8d, [rcx]
0x180006fc7  lea     r10, [r9+8]
0x180006fcb  xor     ebx, ebx
0x180006fcd  mov     r11d, edx
0x180006fd0  cmp     edx, 5
0x180006fd3  mov     rdi, rcx
0x180006fd6  mov     esi, 1
0x180006fdb  setz    bl
0x180006fde  mov     eax, r8d
0x180006fe1  mov     dword ptr [r9+4], 0
0x180006fe9  or      eax, esi
0x180006feb  mov     ecx, eax
0x180006fed  shr     ecx, 16h
0x180006ff0  and     ecx, esi
0x180006ff2  cmp     ecx, ebx
0x180006ff4  jz      short loc_180007033
0x180006ff6  mov     edx, eax
0x180006ff8  shr     edx, 0Fh
0x180006ffb  and     edx, 7Fh
0x180006ffe  jbe     short loc_18000701B
0x180007000  cmp     r11d, esi
0x180007003  mov     [r9+4], edx
0x180007007  mov     ecx, 5
0x18000700c  lea     r10, [r9+8]
0x180007010  cmovnz  ecx, esi
0x180007013  and     eax, 0FFC07FFFh
0x180007018  mov     [r10], ecx
0x18000701b  xor     edx, edx
0x18000701d  mov     ecx, 400000h
0x180007022  cmp     r11d, 5
0x180007026  cmovz   edx, ecx
0x180007029  mov     ecx, eax
0x18000702b  btr     ecx, 16h
0x18000702f  mov     eax, edx
0x180007031  or      eax, ecx
0x180007033  mov     ecx, eax
0x180007035  shr     ecx, 0Fh
0x180007038  and     ecx, 7Fh
0x18000703b  lea     edx, [rcx+1]
0x18000703e  cmp     edx, 7Fh
0x180007041  ja      short loc_18000704D
0x180007043  cmp     edx, ecx
0x180007045  jb      short loc_18000704D
0x180007047  lea     r10, [r9+8]
0x18000704b  jmp     short loc_180007056
0x18000704d  mov     edx, esi
0x18000704f  mov     [r10], r11d
0x180007052  mov     [r9+4], ecx
0x180007056  shl     edx, 0Fh
0x180007059  xor     edx, eax
0x18000705b  and     edx, 3F8000h
0x180007061  xor     edx, eax
0x180007063  mov     eax, r8d
0x180007066  lock cmpxchg [rdi], edx
0x18000706a  jz      short loc_180007074
0x18000706c  mov     r8d, eax
0x18000706f  jmp     loc_180006FDE
0x180007074  not     r8d
0x180007077  mov     dword ptr [r9+10h], 0
0x18000707f  and     r8d, esi
0x180007082  mov     [r9], r8d
0x180007085  pop     rdi
0x180007086  pop     rsi
0x180007087  pop     rbx
0x180007088  retn
```
