# wil_details_FeatureReporting_IncrementUsageInCache

- ea: `0x14002b258`
- end: `0x14002b32e`
- name: `wil_details_FeatureReporting_IncrementUsageInCache`
- size: `214`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14002b334`

## callees

- `0x14002b258`

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
0x14002b258  push    rbx
0x14002b25a  push    rsi
0x14002b25b  push    rdi
0x14002b25c  mov     r8d, [rcx]
0x14002b25f  lea     r10, [r9+8]
0x14002b263  xor     edi, edi
0x14002b265  mov     ebx, edx
0x14002b267  cmp     edx, 4
0x14002b26a  mov     rsi, rcx
0x14002b26d  setz    dil
0x14002b271  mov     eax, r8d
0x14002b274  mov     dword ptr [r9+4], 0
0x14002b27c  or      eax, 1
0x14002b27f  mov     ecx, eax
0x14002b281  shr     ecx, 0Eh
0x14002b284  and     ecx, 1
0x14002b287  cmp     ecx, edi
0x14002b289  jz      short loc_14002B2CD
0x14002b28b  mov     r11d, eax
0x14002b28e  shr     r11d, 5
0x14002b292  and     r11d, 1FFh
0x14002b299  jbe     short loc_14002B2B6
0x14002b29b  mov     ecx, ebx
0x14002b29d  mov     [r9+4], r11d
0x14002b2a1  neg     ecx
0x14002b2a3  lea     r10, [r9+8]
0x14002b2a7  sbb     edx, edx
0x14002b2a9  not     edx
0x14002b2ab  and     edx, 4
0x14002b2ae  mov     [r10], edx
0x14002b2b1  and     eax, 0FFFFC01Fh
0x14002b2b6  xor     edx, edx
0x14002b2b8  mov     ecx, 4000h
0x14002b2bd  cmp     ebx, 4
0x14002b2c0  cmovz   edx, ecx
0x14002b2c3  mov     ecx, eax
0x14002b2c5  btr     ecx, 0Eh
0x14002b2c9  mov     eax, edx
0x14002b2cb  or      eax, ecx
0x14002b2cd  mov     ecx, eax
0x14002b2cf  shr     ecx, 5
0x14002b2d2  and     ecx, 1FFh
0x14002b2d8  lea     edx, [rcx+1]
0x14002b2db  cmp     edx, 1FFh
0x14002b2e1  ja      short loc_14002B2ED
0x14002b2e3  cmp     edx, ecx
0x14002b2e5  jb      short loc_14002B2ED
0x14002b2e7  lea     r10, [r9+8]
0x14002b2eb  jmp     short loc_14002B2F9
0x14002b2ed  mov     edx, 1
0x14002b2f2  mov     [r10], ebx
0x14002b2f5  mov     [r9+4], ecx
0x14002b2f9  shl     edx, 5
0x14002b2fc  xor     edx, eax
0x14002b2fe  and     edx, 3FE0h
0x14002b304  xor     edx, eax
0x14002b306  mov     eax, r8d
0x14002b309  lock cmpxchg [rsi], edx
0x14002b30d  jz      short loc_14002B317
0x14002b30f  mov     r8d, eax
0x14002b312  jmp     loc_14002B271
0x14002b317  not     r8d
0x14002b31a  mov     dword ptr [r9+10h], 0
0x14002b322  and     r8d, 1
0x14002b326  mov     [r9], r8d
0x14002b329  pop     rdi
0x14002b32a  pop     rsi
0x14002b32b  pop     rbx
0x14002b32c  retn
```
