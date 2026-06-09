# wil_details_FeatureReporting_IncrementUsageInCache

- ea: `0x180016b5c`
- end: `0x180016c31`
- name: `wil_details_FeatureReporting_IncrementUsageInCache`
- size: `213`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800169d8`

## callees

- `0x180016b5c`

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
0x180016b5c  push    rbx
0x180016b5e  push    rsi
0x180016b5f  push    rdi
0x180016b60  mov     r8d, [rcx]
0x180016b63  lea     r10, [r9+8]
0x180016b67  xor     edi, edi
0x180016b69  mov     ebx, edx
0x180016b6b  cmp     edx, 4
0x180016b6e  mov     rsi, rcx
0x180016b71  setz    dil
0x180016b75  mov     eax, r8d
0x180016b78  mov     dword ptr [r9+4], 0
0x180016b80  or      eax, 1
0x180016b83  mov     ecx, eax
0x180016b85  shr     ecx, 0Eh
0x180016b88  and     ecx, 1
0x180016b8b  cmp     ecx, edi
0x180016b8d  jz      short loc_180016BD1
0x180016b8f  mov     r11d, eax
0x180016b92  shr     r11d, 5
0x180016b96  and     r11d, 1FFh
0x180016b9d  jbe     short loc_180016BBA
0x180016b9f  mov     ecx, ebx
0x180016ba1  mov     [r9+4], r11d
0x180016ba5  neg     ecx
0x180016ba7  lea     r10, [r9+8]
0x180016bab  sbb     edx, edx
0x180016bad  not     edx
0x180016baf  and     edx, 4
0x180016bb2  mov     [r10], edx
0x180016bb5  and     eax, 0FFFFC01Fh
0x180016bba  xor     edx, edx
0x180016bbc  mov     ecx, 4000h
0x180016bc1  cmp     ebx, 4
0x180016bc4  cmovz   edx, ecx
0x180016bc7  mov     ecx, eax
0x180016bc9  btr     ecx, 0Eh
0x180016bcd  mov     eax, edx
0x180016bcf  or      eax, ecx
0x180016bd1  mov     ecx, eax
0x180016bd3  shr     ecx, 5
0x180016bd6  and     ecx, 1FFh
0x180016bdc  lea     edx, [rcx+1]
0x180016bdf  cmp     edx, 1FFh
0x180016be5  ja      short loc_180016BF1
0x180016be7  cmp     edx, ecx
0x180016be9  jb      short loc_180016BF1
0x180016beb  lea     r10, [r9+8]
0x180016bef  jmp     short loc_180016BFD
0x180016bf1  mov     edx, 1
0x180016bf6  mov     [r10], ebx
0x180016bf9  mov     [r9+4], ecx
0x180016bfd  shl     edx, 5
0x180016c00  xor     edx, eax
0x180016c02  and     edx, 3FE0h
0x180016c08  xor     edx, eax
0x180016c0a  mov     eax, r8d
0x180016c0d  lock cmpxchg [rsi], edx
0x180016c11  jz      short loc_180016C1B
0x180016c13  mov     r8d, eax
0x180016c16  jmp     loc_180016B75
0x180016c1b  not     r8d
0x180016c1e  mov     dword ptr [r9+10h], 0
0x180016c26  and     r8d, 1
0x180016c2a  mov     [r9], r8d
0x180016c2d  pop     rdi
0x180016c2e  pop     rsi
0x180016c2f  pop     rbx
0x180016c30  retn
```
