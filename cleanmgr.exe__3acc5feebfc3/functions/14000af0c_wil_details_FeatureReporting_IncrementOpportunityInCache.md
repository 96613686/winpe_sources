# wil_details_FeatureReporting_IncrementOpportunityInCache

- ea: `0x14000af0c`
- end: `0x14000afd5`
- name: `wil_details_FeatureReporting_IncrementOpportunityInCache`
- size: `201`
- prototype: `__int64 __fastcall(volatile signed __int32 *, int, __int64, _DWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14000b0b8`

## callees

- `0x14000af0c`

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
0x14000af0c  push    rbx
0x14000af0e  push    rsi
0x14000af0f  push    rdi
0x14000af10  mov     r8d, [rcx]
0x14000af13  lea     r10, [r9+8]
0x14000af17  xor     ebx, ebx
0x14000af19  mov     r11d, edx
0x14000af1c  cmp     edx, 5
0x14000af1f  mov     rdi, rcx
0x14000af22  mov     esi, 1
0x14000af27  setz    bl
0x14000af2a  mov     eax, r8d
0x14000af2d  mov     dword ptr [r9+4], 0
0x14000af35  or      eax, esi
0x14000af37  mov     ecx, eax
0x14000af39  shr     ecx, 16h
0x14000af3c  and     ecx, esi
0x14000af3e  cmp     ecx, ebx
0x14000af40  jz      short loc_14000AF7F
0x14000af42  mov     edx, eax
0x14000af44  shr     edx, 0Fh
0x14000af47  and     edx, 7Fh
0x14000af4a  jbe     short loc_14000AF67
0x14000af4c  cmp     r11d, esi
0x14000af4f  mov     [r9+4], edx
0x14000af53  mov     ecx, 5
0x14000af58  lea     r10, [r9+8]
0x14000af5c  cmovnz  ecx, esi
0x14000af5f  and     eax, 0FFC07FFFh
0x14000af64  mov     [r10], ecx
0x14000af67  xor     edx, edx
0x14000af69  mov     ecx, 400000h
0x14000af6e  cmp     r11d, 5
0x14000af72  cmovz   edx, ecx
0x14000af75  mov     ecx, eax
0x14000af77  btr     ecx, 16h
0x14000af7b  mov     eax, edx
0x14000af7d  or      eax, ecx
0x14000af7f  mov     ecx, eax
0x14000af81  shr     ecx, 0Fh
0x14000af84  and     ecx, 7Fh
0x14000af87  lea     edx, [rcx+1]
0x14000af8a  cmp     edx, 7Fh
0x14000af8d  ja      short loc_14000AF99
0x14000af8f  cmp     edx, ecx
0x14000af91  jb      short loc_14000AF99
0x14000af93  lea     r10, [r9+8]
0x14000af97  jmp     short loc_14000AFA2
0x14000af99  mov     edx, esi
0x14000af9b  mov     [r10], r11d
0x14000af9e  mov     [r9+4], ecx
0x14000afa2  shl     edx, 0Fh
0x14000afa5  xor     edx, eax
0x14000afa7  and     edx, 3F8000h
0x14000afad  xor     edx, eax
0x14000afaf  mov     eax, r8d
0x14000afb2  lock cmpxchg [rdi], edx
0x14000afb6  jz      short loc_14000AFC0
0x14000afb8  mov     r8d, eax
0x14000afbb  jmp     loc_14000AF2A
0x14000afc0  not     r8d
0x14000afc3  mov     dword ptr [r9+10h], 0
0x14000afcb  and     r8d, esi
0x14000afce  mov     [r9], r8d
0x14000afd1  pop     rdi
0x14000afd2  pop     rsi
0x14000afd3  pop     rbx
0x14000afd4  retn
```
