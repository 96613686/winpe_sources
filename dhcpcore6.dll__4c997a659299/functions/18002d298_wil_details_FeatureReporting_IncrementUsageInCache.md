# wil_details_FeatureReporting_IncrementUsageInCache

- ea: `0x18002d298`
- end: `0x18002d36e`
- name: `wil_details_FeatureReporting_IncrementUsageInCache`
- size: `214`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18002d374`

## callees

- `0x18002d298`

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
0x18002d298  push    rbx
0x18002d29a  push    rsi
0x18002d29b  push    rdi
0x18002d29c  mov     r8d, [rcx]
0x18002d29f  lea     r10, [r9+8]
0x18002d2a3  xor     edi, edi
0x18002d2a5  mov     ebx, edx
0x18002d2a7  cmp     edx, 4
0x18002d2aa  mov     rsi, rcx
0x18002d2ad  setz    dil
0x18002d2b1  mov     eax, r8d
0x18002d2b4  mov     dword ptr [r9+4], 0
0x18002d2bc  or      eax, 1
0x18002d2bf  mov     ecx, eax
0x18002d2c1  shr     ecx, 0Eh
0x18002d2c4  and     ecx, 1
0x18002d2c7  cmp     ecx, edi
0x18002d2c9  jz      short loc_18002D30D
0x18002d2cb  mov     r11d, eax
0x18002d2ce  shr     r11d, 5
0x18002d2d2  and     r11d, 1FFh
0x18002d2d9  jbe     short loc_18002D2F6
0x18002d2db  mov     ecx, ebx
0x18002d2dd  mov     [r9+4], r11d
0x18002d2e1  neg     ecx
0x18002d2e3  lea     r10, [r9+8]
0x18002d2e7  sbb     edx, edx
0x18002d2e9  not     edx
0x18002d2eb  and     edx, 4
0x18002d2ee  mov     [r10], edx
0x18002d2f1  and     eax, 0FFFFC01Fh
0x18002d2f6  xor     edx, edx
0x18002d2f8  mov     ecx, 4000h
0x18002d2fd  cmp     ebx, 4
0x18002d300  cmovz   edx, ecx
0x18002d303  mov     ecx, eax
0x18002d305  btr     ecx, 0Eh
0x18002d309  mov     eax, edx
0x18002d30b  or      eax, ecx
0x18002d30d  mov     ecx, eax
0x18002d30f  shr     ecx, 5
0x18002d312  and     ecx, 1FFh
0x18002d318  lea     edx, [rcx+1]
0x18002d31b  cmp     edx, 1FFh
0x18002d321  ja      short loc_18002D32D
0x18002d323  cmp     edx, ecx
0x18002d325  jb      short loc_18002D32D
0x18002d327  lea     r10, [r9+8]
0x18002d32b  jmp     short loc_18002D339
0x18002d32d  mov     edx, 1
0x18002d332  mov     [r10], ebx
0x18002d335  mov     [r9+4], ecx
0x18002d339  shl     edx, 5
0x18002d33c  xor     edx, eax
0x18002d33e  and     edx, 3FE0h
0x18002d344  xor     edx, eax
0x18002d346  mov     eax, r8d
0x18002d349  lock cmpxchg [rsi], edx
0x18002d34d  jz      short loc_18002D357
0x18002d34f  mov     r8d, eax
0x18002d352  jmp     loc_18002D2B1
0x18002d357  not     r8d
0x18002d35a  mov     dword ptr [r9+10h], 0
0x18002d362  and     r8d, 1
0x18002d366  mov     [r9], r8d
0x18002d369  pop     rdi
0x18002d36a  pop     rsi
0x18002d36b  pop     rbx
0x18002d36c  retn
```
