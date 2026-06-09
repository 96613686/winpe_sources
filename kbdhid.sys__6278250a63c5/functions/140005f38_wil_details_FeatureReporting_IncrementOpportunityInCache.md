# wil_details_FeatureReporting_IncrementOpportunityInCache

- ea: `0x140005f38`
- end: `0x140006002`
- name: `wil_details_FeatureReporting_IncrementOpportunityInCache`
- size: `202`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1400060e4`

## callees

- `0x140005f38`

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
0x140005f38  push    rbx
0x140005f3a  push    rsi
0x140005f3b  push    rdi
0x140005f3c  mov     r8d, [rcx]
0x140005f3f  lea     r10, [r9+8]
0x140005f43  xor     ebx, ebx
0x140005f45  mov     r11d, edx
0x140005f48  cmp     edx, 5
0x140005f4b  mov     rdi, rcx
0x140005f4e  mov     esi, 1
0x140005f53  setz    bl
0x140005f56  mov     eax, r8d
0x140005f59  mov     dword ptr [r9+4], 0
0x140005f61  or      eax, esi
0x140005f63  mov     ecx, eax
0x140005f65  shr     ecx, 16h
0x140005f68  and     ecx, esi
0x140005f6a  cmp     ecx, ebx
0x140005f6c  jz      short loc_140005FAB
0x140005f6e  mov     edx, eax
0x140005f70  shr     edx, 0Fh
0x140005f73  and     edx, 7Fh
0x140005f76  jbe     short loc_140005F93
0x140005f78  cmp     r11d, esi
0x140005f7b  mov     [r9+4], edx
0x140005f7f  mov     ecx, 5
0x140005f84  lea     r10, [r9+8]
0x140005f88  cmovnz  ecx, esi
0x140005f8b  and     eax, 0FFC07FFFh
0x140005f90  mov     [r10], ecx
0x140005f93  xor     edx, edx
0x140005f95  mov     ecx, 400000h
0x140005f9a  cmp     r11d, 5
0x140005f9e  cmovz   edx, ecx
0x140005fa1  mov     ecx, eax
0x140005fa3  btr     ecx, 16h
0x140005fa7  mov     eax, edx
0x140005fa9  or      eax, ecx
0x140005fab  mov     ecx, eax
0x140005fad  shr     ecx, 0Fh
0x140005fb0  and     ecx, 7Fh
0x140005fb3  lea     edx, [rcx+1]
0x140005fb6  cmp     edx, 7Fh
0x140005fb9  ja      short loc_140005FC5
0x140005fbb  cmp     edx, ecx
0x140005fbd  jb      short loc_140005FC5
0x140005fbf  lea     r10, [r9+8]
0x140005fc3  jmp     short loc_140005FCE
0x140005fc5  mov     edx, esi
0x140005fc7  mov     [r10], r11d
0x140005fca  mov     [r9+4], ecx
0x140005fce  shl     edx, 0Fh
0x140005fd1  xor     edx, eax
0x140005fd3  and     edx, 3F8000h
0x140005fd9  xor     edx, eax
0x140005fdb  mov     eax, r8d
0x140005fde  lock cmpxchg [rdi], edx
0x140005fe2  jz      short loc_140005FEC
0x140005fe4  mov     r8d, eax
0x140005fe7  jmp     loc_140005F56
0x140005fec  not     r8d
0x140005fef  mov     dword ptr [r9+10h], 0
0x140005ff7  and     r8d, esi
0x140005ffa  mov     [r9], r8d
0x140005ffd  pop     rdi
0x140005ffe  pop     rsi
0x140005fff  pop     rbx
0x140006000  retn
```
