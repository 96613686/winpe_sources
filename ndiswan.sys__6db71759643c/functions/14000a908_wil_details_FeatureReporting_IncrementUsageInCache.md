# wil_details_FeatureReporting_IncrementUsageInCache

- ea: `0x14000a908`
- end: `0x14000a9de`
- name: `wil_details_FeatureReporting_IncrementUsageInCache`
- size: `214`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14000a9e4`

## callees

- `0x14000a908`

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
0x14000a908  push    rbx
0x14000a90a  push    rsi
0x14000a90b  push    rdi
0x14000a90c  mov     r8d, [rcx]
0x14000a90f  lea     r10, [r9+8]
0x14000a913  xor     edi, edi
0x14000a915  mov     ebx, edx
0x14000a917  cmp     edx, 4
0x14000a91a  mov     rsi, rcx
0x14000a91d  setz    dil
0x14000a921  mov     eax, r8d
0x14000a924  mov     dword ptr [r9+4], 0
0x14000a92c  or      eax, 1
0x14000a92f  mov     ecx, eax
0x14000a931  shr     ecx, 0Eh
0x14000a934  and     ecx, 1
0x14000a937  cmp     ecx, edi
0x14000a939  jz      short loc_14000A97D
0x14000a93b  mov     r11d, eax
0x14000a93e  shr     r11d, 5
0x14000a942  and     r11d, 1FFh
0x14000a949  jbe     short loc_14000A966
0x14000a94b  mov     ecx, ebx
0x14000a94d  mov     [r9+4], r11d
0x14000a951  neg     ecx
0x14000a953  lea     r10, [r9+8]
0x14000a957  sbb     edx, edx
0x14000a959  not     edx
0x14000a95b  and     edx, 4
0x14000a95e  mov     [r10], edx
0x14000a961  and     eax, 0FFFFC01Fh
0x14000a966  xor     edx, edx
0x14000a968  mov     ecx, 4000h
0x14000a96d  cmp     ebx, 4
0x14000a970  cmovz   edx, ecx
0x14000a973  mov     ecx, eax
0x14000a975  btr     ecx, 0Eh
0x14000a979  mov     eax, edx
0x14000a97b  or      eax, ecx
0x14000a97d  mov     ecx, eax
0x14000a97f  shr     ecx, 5
0x14000a982  and     ecx, 1FFh
0x14000a988  lea     edx, [rcx+1]
0x14000a98b  cmp     edx, 1FFh
0x14000a991  ja      short loc_14000A99D
0x14000a993  cmp     edx, ecx
0x14000a995  jb      short loc_14000A99D
0x14000a997  lea     r10, [r9+8]
0x14000a99b  jmp     short loc_14000A9A9
0x14000a99d  mov     edx, 1
0x14000a9a2  mov     [r10], ebx
0x14000a9a5  mov     [r9+4], ecx
0x14000a9a9  shl     edx, 5
0x14000a9ac  xor     edx, eax
0x14000a9ae  and     edx, 3FE0h
0x14000a9b4  xor     edx, eax
0x14000a9b6  mov     eax, r8d
0x14000a9b9  lock cmpxchg [rsi], edx
0x14000a9bd  jz      short loc_14000A9C7
0x14000a9bf  mov     r8d, eax
0x14000a9c2  jmp     loc_14000A921
0x14000a9c7  not     r8d
0x14000a9ca  mov     dword ptr [r9+10h], 0
0x14000a9d2  and     r8d, 1
0x14000a9d6  mov     [r9], r8d
0x14000a9d9  pop     rdi
0x14000a9da  pop     rsi
0x14000a9db  pop     rbx
0x14000a9dc  retn
```
