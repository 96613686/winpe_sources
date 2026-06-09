# wil_details_FeatureReporting_IncrementUsageInCache

- ea: `0x18000a6fc`
- end: `0x18000a7d1`
- name: `wil_details_FeatureReporting_IncrementUsageInCache`
- size: `213`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000a7d8`

## callees

- `0x18000a6fc`

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
0x18000a6fc  push    rbx
0x18000a6fe  push    rsi
0x18000a6ff  push    rdi
0x18000a700  mov     r8d, [rcx]
0x18000a703  lea     r10, [r9+8]
0x18000a707  xor     edi, edi
0x18000a709  mov     ebx, edx
0x18000a70b  cmp     edx, 4
0x18000a70e  mov     rsi, rcx
0x18000a711  setz    dil
0x18000a715  mov     eax, r8d
0x18000a718  mov     dword ptr [r9+4], 0
0x18000a720  or      eax, 1
0x18000a723  mov     ecx, eax
0x18000a725  shr     ecx, 0Eh
0x18000a728  and     ecx, 1
0x18000a72b  cmp     ecx, edi
0x18000a72d  jz      short loc_18000A771
0x18000a72f  mov     r11d, eax
0x18000a732  shr     r11d, 5
0x18000a736  and     r11d, 1FFh
0x18000a73d  jbe     short loc_18000A75A
0x18000a73f  mov     ecx, ebx
0x18000a741  mov     [r9+4], r11d
0x18000a745  neg     ecx
0x18000a747  lea     r10, [r9+8]
0x18000a74b  sbb     edx, edx
0x18000a74d  not     edx
0x18000a74f  and     edx, 4
0x18000a752  mov     [r10], edx
0x18000a755  and     eax, 0FFFFC01Fh
0x18000a75a  xor     edx, edx
0x18000a75c  mov     ecx, 4000h
0x18000a761  cmp     ebx, 4
0x18000a764  cmovz   edx, ecx
0x18000a767  mov     ecx, eax
0x18000a769  btr     ecx, 0Eh
0x18000a76d  mov     eax, edx
0x18000a76f  or      eax, ecx
0x18000a771  mov     ecx, eax
0x18000a773  shr     ecx, 5
0x18000a776  and     ecx, 1FFh
0x18000a77c  lea     edx, [rcx+1]
0x18000a77f  cmp     edx, 1FFh
0x18000a785  ja      short loc_18000A791
0x18000a787  cmp     edx, ecx
0x18000a789  jb      short loc_18000A791
0x18000a78b  lea     r10, [r9+8]
0x18000a78f  jmp     short loc_18000A79D
0x18000a791  mov     edx, 1
0x18000a796  mov     [r10], ebx
0x18000a799  mov     [r9+4], ecx
0x18000a79d  shl     edx, 5
0x18000a7a0  xor     edx, eax
0x18000a7a2  and     edx, 3FE0h
0x18000a7a8  xor     edx, eax
0x18000a7aa  mov     eax, r8d
0x18000a7ad  lock cmpxchg [rsi], edx
0x18000a7b1  jz      short loc_18000A7BB
0x18000a7b3  mov     r8d, eax
0x18000a7b6  jmp     loc_18000A715
0x18000a7bb  not     r8d
0x18000a7be  mov     dword ptr [r9+10h], 0
0x18000a7c6  and     r8d, 1
0x18000a7ca  mov     [r9], r8d
0x18000a7cd  pop     rdi
0x18000a7ce  pop     rsi
0x18000a7cf  pop     rbx
0x18000a7d0  retn
```
