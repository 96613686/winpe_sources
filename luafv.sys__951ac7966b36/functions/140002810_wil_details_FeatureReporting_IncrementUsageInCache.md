# wil_details_FeatureReporting_IncrementUsageInCache

- ea: `0x140002810`
- end: `0x1400028e6`
- name: `wil_details_FeatureReporting_IncrementUsageInCache`
- size: `214`
- prototype: `__int64 __fastcall(volatile signed __int32 *, int, __int64, _DWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1400028ec`

## callees

- `0x140002810`

## pseudocode

```c
__int64 __fastcall wil_details_FeatureReporting_IncrementUsageInCache(
        volatile signed __int32 *a1,
        int a2,
        __int64 a3,
        _DWORD *a4)
{
  signed __int32 v4; // r8d
  _DWORD *v5; // r10
  BOOL v8; // edi
  unsigned int v9; // eax
  int v10; // edx
  unsigned int v11; // ecx
  unsigned int v12; // edx
  __int64 result; // rax

  v4 = *a1;
  v5 = a4 + 2;
  v8 = a2 == 4;
  while ( 1 )
  {
    a4[1] = 0;
    v9 = v4 | 1;
    if ( (((v4 | 1u) >> 14) & 1) != v8 )
    {
      if ( ((v9 >> 5) & 0x1FF) != 0 )
      {
        a4[1] = (v9 >> 5) & 0x1FF;
        v5 = a4 + 2;
        a4[2] = a2 == 0 ? 4 : 0;
        v9 = v4 & 0xFFFFC01E | 1;
      }
      v10 = 0;
      if ( a2 == 4 )
        v10 = 0x4000;
      v9 = v9 & 0xFFFFBFFF | v10;
    }
    v11 = (v9 >> 5) & 0x1FF;
    v12 = v11 + 1;
    if ( v11 + 1 > 0x1FF || v12 < v11 )
    {
      LOWORD(v12) = 1;
      *v5 = a2;
      a4[1] = v11;
    }
    else
    {
      v5 = a4 + 2;
    }
    result = (unsigned int)_InterlockedCompareExchange(
                             a1,
                             v9 ^ ((unsigned __int16)v9 ^ (unsigned __int16)(32 * v12)) & 0x3FE0,
                             v4);
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
0x140002810  push    rbx
0x140002812  push    rsi
0x140002813  push    rdi
0x140002814  mov     r8d, [rcx]
0x140002817  lea     r10, [r9+8]
0x14000281b  xor     edi, edi
0x14000281d  mov     ebx, edx
0x14000281f  cmp     edx, 4
0x140002822  mov     rsi, rcx
0x140002825  setz    dil
0x140002829  mov     eax, r8d
0x14000282c  mov     dword ptr [r9+4], 0
0x140002834  or      eax, 1
0x140002837  mov     ecx, eax
0x140002839  shr     ecx, 0Eh
0x14000283c  and     ecx, 1
0x14000283f  cmp     ecx, edi
0x140002841  jz      short loc_140002885
0x140002843  mov     r11d, eax
0x140002846  shr     r11d, 5
0x14000284a  and     r11d, 1FFh
0x140002851  jbe     short loc_14000286E
0x140002853  mov     ecx, ebx
0x140002855  mov     [r9+4], r11d
0x140002859  neg     ecx
0x14000285b  lea     r10, [r9+8]
0x14000285f  sbb     edx, edx
0x140002861  not     edx
0x140002863  and     edx, 4
0x140002866  mov     [r10], edx
0x140002869  and     eax, 0FFFFC01Fh
0x14000286e  xor     edx, edx
0x140002870  mov     ecx, 4000h
0x140002875  cmp     ebx, 4
0x140002878  cmovz   edx, ecx
0x14000287b  mov     ecx, eax
0x14000287d  btr     ecx, 0Eh
0x140002881  mov     eax, edx
0x140002883  or      eax, ecx
0x140002885  mov     ecx, eax
0x140002887  shr     ecx, 5
0x14000288a  and     ecx, 1FFh
0x140002890  lea     edx, [rcx+1]
0x140002893  cmp     edx, 1FFh
0x140002899  ja      short loc_1400028A5
0x14000289b  cmp     edx, ecx
0x14000289d  jb      short loc_1400028A5
0x14000289f  lea     r10, [r9+8]
0x1400028a3  jmp     short loc_1400028B1
0x1400028a5  mov     edx, 1
0x1400028aa  mov     [r10], ebx
0x1400028ad  mov     [r9+4], ecx
0x1400028b1  shl     edx, 5
0x1400028b4  xor     edx, eax
0x1400028b6  and     edx, 3FE0h
0x1400028bc  xor     edx, eax
0x1400028be  mov     eax, r8d
0x1400028c1  lock cmpxchg [rsi], edx
0x1400028c5  jz      short loc_1400028CF
0x1400028c7  mov     r8d, eax
0x1400028ca  jmp     loc_140002829
0x1400028cf  not     r8d
0x1400028d2  mov     dword ptr [r9+10h], 0
0x1400028da  and     r8d, 1
0x1400028de  mov     [r9], r8d
0x1400028e1  pop     rdi
0x1400028e2  pop     rsi
0x1400028e3  pop     rbx
0x1400028e4  retn
```
