# wil_details_FeatureReporting_IncrementUsageInCache

- ea: `0x180015f2c`
- end: `0x180016001`
- name: `wil_details_FeatureReporting_IncrementUsageInCache`
- size: `213`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180016008`

## callees

- `0x180015f2c`

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
0x180015f2c  push    rbx
0x180015f2e  push    rsi
0x180015f2f  push    rdi
0x180015f30  mov     r8d, [rcx]
0x180015f33  lea     r10, [r9+8]
0x180015f37  xor     edi, edi
0x180015f39  mov     ebx, edx
0x180015f3b  cmp     edx, 4
0x180015f3e  mov     rsi, rcx
0x180015f41  setz    dil
0x180015f45  mov     eax, r8d
0x180015f48  mov     dword ptr [r9+4], 0
0x180015f50  or      eax, 1
0x180015f53  mov     ecx, eax
0x180015f55  shr     ecx, 0Eh
0x180015f58  and     ecx, 1
0x180015f5b  cmp     ecx, edi
0x180015f5d  jz      short loc_180015FA1
0x180015f5f  mov     r11d, eax
0x180015f62  shr     r11d, 5
0x180015f66  and     r11d, 1FFh
0x180015f6d  jbe     short loc_180015F8A
0x180015f6f  mov     ecx, ebx
0x180015f71  mov     [r9+4], r11d
0x180015f75  neg     ecx
0x180015f77  lea     r10, [r9+8]
0x180015f7b  sbb     edx, edx
0x180015f7d  not     edx
0x180015f7f  and     edx, 4
0x180015f82  mov     [r10], edx
0x180015f85  and     eax, 0FFFFC01Fh
0x180015f8a  xor     edx, edx
0x180015f8c  mov     ecx, 4000h
0x180015f91  cmp     ebx, 4
0x180015f94  cmovz   edx, ecx
0x180015f97  mov     ecx, eax
0x180015f99  btr     ecx, 0Eh
0x180015f9d  mov     eax, edx
0x180015f9f  or      eax, ecx
0x180015fa1  mov     ecx, eax
0x180015fa3  shr     ecx, 5
0x180015fa6  and     ecx, 1FFh
0x180015fac  lea     edx, [rcx+1]
0x180015faf  cmp     edx, 1FFh
0x180015fb5  ja      short loc_180015FC1
0x180015fb7  cmp     edx, ecx
0x180015fb9  jb      short loc_180015FC1
0x180015fbb  lea     r10, [r9+8]
0x180015fbf  jmp     short loc_180015FCD
0x180015fc1  mov     edx, 1
0x180015fc6  mov     [r10], ebx
0x180015fc9  mov     [r9+4], ecx
0x180015fcd  shl     edx, 5
0x180015fd0  xor     edx, eax
0x180015fd2  and     edx, 3FE0h
0x180015fd8  xor     edx, eax
0x180015fda  mov     eax, r8d
0x180015fdd  lock cmpxchg [rsi], edx
0x180015fe1  jz      short loc_180015FEB
0x180015fe3  mov     r8d, eax
0x180015fe6  jmp     loc_180015F45
0x180015feb  not     r8d
0x180015fee  mov     dword ptr [r9+10h], 0
0x180015ff6  and     r8d, 1
0x180015ffa  mov     [r9], r8d
0x180015ffd  pop     rdi
0x180015ffe  pop     rsi
0x180015fff  pop     rbx
0x180016000  retn
```
