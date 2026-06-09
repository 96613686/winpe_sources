# wil_details_FeatureReporting_IncrementOpportunityInCache

- ea: `0x1800106e0`
- end: `0x1800107a9`
- name: `wil_details_FeatureReporting_IncrementOpportunityInCache`
- size: `201`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180003964`

## callees

- `0x1800106e0`

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
0x1800106e0  push    rbx
0x1800106e2  push    rsi
0x1800106e3  push    rdi
0x1800106e4  mov     r8d, [rcx]
0x1800106e7  lea     r10, [r9+8]
0x1800106eb  xor     ebx, ebx
0x1800106ed  mov     r11d, edx
0x1800106f0  cmp     edx, 5
0x1800106f3  mov     rdi, rcx
0x1800106f6  mov     esi, 1
0x1800106fb  setz    bl
0x1800106fe  mov     eax, r8d
0x180010701  mov     dword ptr [r9+4], 0
0x180010709  or      eax, esi
0x18001070b  mov     ecx, eax
0x18001070d  shr     ecx, 16h
0x180010710  and     ecx, esi
0x180010712  cmp     ecx, ebx
0x180010714  jz      short loc_180010753
0x180010716  mov     edx, eax
0x180010718  shr     edx, 0Fh
0x18001071b  and     edx, 7Fh
0x18001071e  jbe     short loc_18001073B
0x180010720  cmp     r11d, esi
0x180010723  mov     [r9+4], edx
0x180010727  mov     ecx, 5
0x18001072c  lea     r10, [r9+8]
0x180010730  cmovnz  ecx, esi
0x180010733  and     eax, 0FFC07FFFh
0x180010738  mov     [r10], ecx
0x18001073b  xor     edx, edx
0x18001073d  mov     ecx, 400000h
0x180010742  cmp     r11d, 5
0x180010746  cmovz   edx, ecx
0x180010749  mov     ecx, eax
0x18001074b  btr     ecx, 16h
0x18001074f  mov     eax, edx
0x180010751  or      eax, ecx
0x180010753  mov     ecx, eax
0x180010755  shr     ecx, 0Fh
0x180010758  and     ecx, 7Fh
0x18001075b  lea     edx, [rcx+1]
0x18001075e  cmp     edx, 7Fh
0x180010761  ja      short loc_18001076D
0x180010763  cmp     edx, ecx
0x180010765  jb      short loc_18001076D
0x180010767  lea     r10, [r9+8]
0x18001076b  jmp     short loc_180010776
0x18001076d  mov     edx, esi
0x18001076f  mov     [r10], r11d
0x180010772  mov     [r9+4], ecx
0x180010776  shl     edx, 0Fh
0x180010779  xor     edx, eax
0x18001077b  and     edx, 3F8000h
0x180010781  xor     edx, eax
0x180010783  mov     eax, r8d
0x180010786  lock cmpxchg [rdi], edx
0x18001078a  jz      short loc_180010794
0x18001078c  mov     r8d, eax
0x18001078f  jmp     loc_1800106FE
0x180010794  not     r8d
0x180010797  mov     dword ptr [r9+10h], 0
0x18001079f  and     r8d, esi
0x1800107a2  mov     [r9], r8d
0x1800107a5  pop     rdi
0x1800107a6  pop     rsi
0x1800107a7  pop     rbx
0x1800107a8  retn
```
