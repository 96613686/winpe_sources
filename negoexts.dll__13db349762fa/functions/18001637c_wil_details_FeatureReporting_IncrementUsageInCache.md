# wil_details_FeatureReporting_IncrementUsageInCache

- ea: `0x18001637c`
- end: `0x180016451`
- name: `wil_details_FeatureReporting_IncrementUsageInCache`
- size: `213`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180016458`

## callees

- `0x18001637c`

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
0x18001637c  push    rbx
0x18001637e  push    rsi
0x18001637f  push    rdi
0x180016380  mov     r8d, [rcx]
0x180016383  lea     r10, [r9+8]
0x180016387  xor     edi, edi
0x180016389  mov     ebx, edx
0x18001638b  cmp     edx, 4
0x18001638e  mov     rsi, rcx
0x180016391  setz    dil
0x180016395  mov     eax, r8d
0x180016398  mov     dword ptr [r9+4], 0
0x1800163a0  or      eax, 1
0x1800163a3  mov     ecx, eax
0x1800163a5  shr     ecx, 0Eh
0x1800163a8  and     ecx, 1
0x1800163ab  cmp     ecx, edi
0x1800163ad  jz      short loc_1800163F1
0x1800163af  mov     r11d, eax
0x1800163b2  shr     r11d, 5
0x1800163b6  and     r11d, 1FFh
0x1800163bd  jbe     short loc_1800163DA
0x1800163bf  mov     ecx, ebx
0x1800163c1  mov     [r9+4], r11d
0x1800163c5  neg     ecx
0x1800163c7  lea     r10, [r9+8]
0x1800163cb  sbb     edx, edx
0x1800163cd  not     edx
0x1800163cf  and     edx, 4
0x1800163d2  mov     [r10], edx
0x1800163d5  and     eax, 0FFFFC01Fh
0x1800163da  xor     edx, edx
0x1800163dc  mov     ecx, 4000h
0x1800163e1  cmp     ebx, 4
0x1800163e4  cmovz   edx, ecx
0x1800163e7  mov     ecx, eax
0x1800163e9  btr     ecx, 0Eh
0x1800163ed  mov     eax, edx
0x1800163ef  or      eax, ecx
0x1800163f1  mov     ecx, eax
0x1800163f3  shr     ecx, 5
0x1800163f6  and     ecx, 1FFh
0x1800163fc  lea     edx, [rcx+1]
0x1800163ff  cmp     edx, 1FFh
0x180016405  ja      short loc_180016411
0x180016407  cmp     edx, ecx
0x180016409  jb      short loc_180016411
0x18001640b  lea     r10, [r9+8]
0x18001640f  jmp     short loc_18001641D
0x180016411  mov     edx, 1
0x180016416  mov     [r10], ebx
0x180016419  mov     [r9+4], ecx
0x18001641d  shl     edx, 5
0x180016420  xor     edx, eax
0x180016422  and     edx, 3FE0h
0x180016428  xor     edx, eax
0x18001642a  mov     eax, r8d
0x18001642d  lock cmpxchg [rsi], edx
0x180016431  jz      short loc_18001643B
0x180016433  mov     r8d, eax
0x180016436  jmp     loc_180016395
0x18001643b  not     r8d
0x18001643e  mov     dword ptr [r9+10h], 0
0x180016446  and     r8d, 1
0x18001644a  mov     [r9], r8d
0x18001644d  pop     rdi
0x18001644e  pop     rsi
0x18001644f  pop     rbx
0x180016450  retn
```
