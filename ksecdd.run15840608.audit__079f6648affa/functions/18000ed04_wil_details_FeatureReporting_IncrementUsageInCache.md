# wil_details_FeatureReporting_IncrementUsageInCache

- ea: `0x18000ed04`
- end: `0x18000edda`
- name: `wil_details_FeatureReporting_IncrementUsageInCache`
- size: `214`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000ede0`

## callees

- `0x18000ed04`

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
0x18000ed04  push    rbx
0x18000ed06  push    rsi
0x18000ed07  push    rdi
0x18000ed08  mov     r8d, [rcx]
0x18000ed0b  lea     r10, [r9+8]
0x18000ed0f  xor     edi, edi
0x18000ed11  mov     ebx, edx
0x18000ed13  cmp     edx, 4
0x18000ed16  mov     rsi, rcx
0x18000ed19  setz    dil
0x18000ed1d  mov     eax, r8d
0x18000ed20  mov     dword ptr [r9+4], 0
0x18000ed28  or      eax, 1
0x18000ed2b  mov     ecx, eax
0x18000ed2d  shr     ecx, 0Eh
0x18000ed30  and     ecx, 1
0x18000ed33  cmp     ecx, edi
0x18000ed35  jz      short loc_18000ED79
0x18000ed37  mov     r11d, eax
0x18000ed3a  shr     r11d, 5
0x18000ed3e  and     r11d, 1FFh
0x18000ed45  jbe     short loc_18000ED62
0x18000ed47  mov     ecx, ebx
0x18000ed49  mov     [r9+4], r11d
0x18000ed4d  neg     ecx
0x18000ed4f  lea     r10, [r9+8]
0x18000ed53  sbb     edx, edx
0x18000ed55  not     edx
0x18000ed57  and     edx, 4
0x18000ed5a  mov     [r10], edx
0x18000ed5d  and     eax, 0FFFFC01Fh
0x18000ed62  xor     edx, edx
0x18000ed64  mov     ecx, 4000h
0x18000ed69  cmp     ebx, 4
0x18000ed6c  cmovz   edx, ecx
0x18000ed6f  mov     ecx, eax
0x18000ed71  btr     ecx, 0Eh
0x18000ed75  mov     eax, edx
0x18000ed77  or      eax, ecx
0x18000ed79  mov     ecx, eax
0x18000ed7b  shr     ecx, 5
0x18000ed7e  and     ecx, 1FFh
0x18000ed84  lea     edx, [rcx+1]
0x18000ed87  cmp     edx, 1FFh
0x18000ed8d  ja      short loc_18000ED99
0x18000ed8f  cmp     edx, ecx
0x18000ed91  jb      short loc_18000ED99
0x18000ed93  lea     r10, [r9+8]
0x18000ed97  jmp     short loc_18000EDA5
0x18000ed99  mov     edx, 1
0x18000ed9e  mov     [r10], ebx
0x18000eda1  mov     [r9+4], ecx
0x18000eda5  shl     edx, 5
0x18000eda8  xor     edx, eax
0x18000edaa  and     edx, 3FE0h
0x18000edb0  xor     edx, eax
0x18000edb2  mov     eax, r8d
0x18000edb5  lock cmpxchg [rsi], edx
0x18000edb9  jz      short loc_18000EDC3
0x18000edbb  mov     r8d, eax
0x18000edbe  jmp     loc_18000ED1D
0x18000edc3  not     r8d
0x18000edc6  mov     dword ptr [r9+10h], 0
0x18000edce  and     r8d, 1
0x18000edd2  mov     [r9], r8d
0x18000edd5  pop     rdi
0x18000edd6  pop     rsi
0x18000edd7  pop     rbx
0x18000edd8  retn
```
