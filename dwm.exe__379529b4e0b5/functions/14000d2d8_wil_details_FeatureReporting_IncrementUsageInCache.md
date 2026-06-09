# wil_details_FeatureReporting_IncrementUsageInCache

- ea: `0x14000d2d8`
- end: `0x14000d3ad`
- name: `wil_details_FeatureReporting_IncrementUsageInCache`
- size: `213`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14000d3b4`

## callees

- `0x14000d2d8`

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
0x14000d2d8  push    rbx
0x14000d2da  push    rsi
0x14000d2db  push    rdi
0x14000d2dc  mov     r8d, [rcx]
0x14000d2df  lea     r10, [r9+8]
0x14000d2e3  xor     edi, edi
0x14000d2e5  mov     ebx, edx
0x14000d2e7  cmp     edx, 4
0x14000d2ea  mov     rsi, rcx
0x14000d2ed  setz    dil
0x14000d2f1  mov     eax, r8d
0x14000d2f4  mov     dword ptr [r9+4], 0
0x14000d2fc  or      eax, 1
0x14000d2ff  mov     ecx, eax
0x14000d301  shr     ecx, 0Eh
0x14000d304  and     ecx, 1
0x14000d307  cmp     ecx, edi
0x14000d309  jz      short loc_14000D34D
0x14000d30b  mov     r11d, eax
0x14000d30e  shr     r11d, 5
0x14000d312  and     r11d, 1FFh
0x14000d319  jbe     short loc_14000D336
0x14000d31b  mov     ecx, ebx
0x14000d31d  mov     [r9+4], r11d
0x14000d321  neg     ecx
0x14000d323  lea     r10, [r9+8]
0x14000d327  sbb     edx, edx
0x14000d329  not     edx
0x14000d32b  and     edx, 4
0x14000d32e  mov     [r10], edx
0x14000d331  and     eax, 0FFFFC01Fh
0x14000d336  xor     edx, edx
0x14000d338  mov     ecx, 4000h
0x14000d33d  cmp     ebx, 4
0x14000d340  cmovz   edx, ecx
0x14000d343  mov     ecx, eax
0x14000d345  btr     ecx, 0Eh
0x14000d349  mov     eax, edx
0x14000d34b  or      eax, ecx
0x14000d34d  mov     ecx, eax
0x14000d34f  shr     ecx, 5
0x14000d352  and     ecx, 1FFh
0x14000d358  lea     edx, [rcx+1]
0x14000d35b  cmp     edx, 1FFh
0x14000d361  ja      short loc_14000D36D
0x14000d363  cmp     edx, ecx
0x14000d365  jb      short loc_14000D36D
0x14000d367  lea     r10, [r9+8]
0x14000d36b  jmp     short loc_14000D379
0x14000d36d  mov     edx, 1
0x14000d372  mov     [r10], ebx
0x14000d375  mov     [r9+4], ecx
0x14000d379  shl     edx, 5
0x14000d37c  xor     edx, eax
0x14000d37e  and     edx, 3FE0h
0x14000d384  xor     edx, eax
0x14000d386  mov     eax, r8d
0x14000d389  lock cmpxchg [rsi], edx
0x14000d38d  jz      short loc_14000D397
0x14000d38f  mov     r8d, eax
0x14000d392  jmp     loc_14000D2F1
0x14000d397  not     r8d
0x14000d39a  mov     dword ptr [r9+10h], 0
0x14000d3a2  and     r8d, 1
0x14000d3a6  mov     [r9], r8d
0x14000d3a9  pop     rdi
0x14000d3aa  pop     rsi
0x14000d3ab  pop     rbx
0x14000d3ac  retn
```
