# wil_details_FeatureReporting_IncrementOpportunityInCache

- ea: `0x18001bb18`
- end: `0x18001bbe1`
- name: `wil_details_FeatureReporting_IncrementOpportunityInCache`
- size: `201`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800169d8`

## callees

- `0x18001bb18`

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
0x18001bb18  push    rbx
0x18001bb1a  push    rsi
0x18001bb1b  push    rdi
0x18001bb1c  mov     r8d, [rcx]
0x18001bb1f  lea     r10, [r9+8]
0x18001bb23  xor     ebx, ebx
0x18001bb25  mov     r11d, edx
0x18001bb28  cmp     edx, 5
0x18001bb2b  mov     rdi, rcx
0x18001bb2e  mov     esi, 1
0x18001bb33  setz    bl
0x18001bb36  mov     eax, r8d
0x18001bb39  mov     dword ptr [r9+4], 0
0x18001bb41  or      eax, esi
0x18001bb43  mov     ecx, eax
0x18001bb45  shr     ecx, 16h
0x18001bb48  and     ecx, esi
0x18001bb4a  cmp     ecx, ebx
0x18001bb4c  jz      short loc_18001BB8B
0x18001bb4e  mov     edx, eax
0x18001bb50  shr     edx, 0Fh
0x18001bb53  and     edx, 7Fh
0x18001bb56  jbe     short loc_18001BB73
0x18001bb58  cmp     r11d, esi
0x18001bb5b  mov     [r9+4], edx
0x18001bb5f  mov     ecx, 5
0x18001bb64  lea     r10, [r9+8]
0x18001bb68  cmovnz  ecx, esi
0x18001bb6b  and     eax, 0FFC07FFFh
0x18001bb70  mov     [r10], ecx
0x18001bb73  xor     edx, edx
0x18001bb75  mov     ecx, 400000h
0x18001bb7a  cmp     r11d, 5
0x18001bb7e  cmovz   edx, ecx
0x18001bb81  mov     ecx, eax
0x18001bb83  btr     ecx, 16h
0x18001bb87  mov     eax, edx
0x18001bb89  or      eax, ecx
0x18001bb8b  mov     ecx, eax
0x18001bb8d  shr     ecx, 0Fh
0x18001bb90  and     ecx, 7Fh
0x18001bb93  lea     edx, [rcx+1]
0x18001bb96  cmp     edx, 7Fh
0x18001bb99  ja      short loc_18001BBA5
0x18001bb9b  cmp     edx, ecx
0x18001bb9d  jb      short loc_18001BBA5
0x18001bb9f  lea     r10, [r9+8]
0x18001bba3  jmp     short loc_18001BBAE
0x18001bba5  mov     edx, esi
0x18001bba7  mov     [r10], r11d
0x18001bbaa  mov     [r9+4], ecx
0x18001bbae  shl     edx, 0Fh
0x18001bbb1  xor     edx, eax
0x18001bbb3  and     edx, 3F8000h
0x18001bbb9  xor     edx, eax
0x18001bbbb  mov     eax, r8d
0x18001bbbe  lock cmpxchg [rdi], edx
0x18001bbc2  jz      short loc_18001BBCC
0x18001bbc4  mov     r8d, eax
0x18001bbc7  jmp     loc_18001BB36
0x18001bbcc  not     r8d
0x18001bbcf  mov     dword ptr [r9+10h], 0
0x18001bbd7  and     r8d, esi
0x18001bbda  mov     [r9], r8d
0x18001bbdd  pop     rdi
0x18001bbde  pop     rsi
0x18001bbdf  pop     rbx
0x18001bbe0  retn
```
