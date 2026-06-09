# wil_details_FeatureReporting_IncrementUsageInCache

- ea: `0x18000d82c`
- end: `0x18000d901`
- name: `wil_details_FeatureReporting_IncrementUsageInCache`
- size: `213`
- prototype: `__int64 __fastcall(volatile signed __int32 *, int, __int64, _DWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000d908`

## callees

- `0x18000d82c`

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
0x18000d82c  push    rbx
0x18000d82e  push    rsi
0x18000d82f  push    rdi
0x18000d830  mov     r8d, [rcx]
0x18000d833  lea     r10, [r9+8]
0x18000d837  xor     edi, edi
0x18000d839  mov     ebx, edx
0x18000d83b  cmp     edx, 4
0x18000d83e  mov     rsi, rcx
0x18000d841  setz    dil
0x18000d845  mov     eax, r8d
0x18000d848  mov     dword ptr [r9+4], 0
0x18000d850  or      eax, 1
0x18000d853  mov     ecx, eax
0x18000d855  shr     ecx, 0Eh
0x18000d858  and     ecx, 1
0x18000d85b  cmp     ecx, edi
0x18000d85d  jz      short loc_18000D8A1
0x18000d85f  mov     r11d, eax
0x18000d862  shr     r11d, 5
0x18000d866  and     r11d, 1FFh
0x18000d86d  jbe     short loc_18000D88A
0x18000d86f  mov     ecx, ebx
0x18000d871  mov     [r9+4], r11d
0x18000d875  neg     ecx
0x18000d877  lea     r10, [r9+8]
0x18000d87b  sbb     edx, edx
0x18000d87d  not     edx
0x18000d87f  and     edx, 4
0x18000d882  mov     [r10], edx
0x18000d885  and     eax, 0FFFFC01Fh
0x18000d88a  xor     edx, edx
0x18000d88c  mov     ecx, 4000h
0x18000d891  cmp     ebx, 4
0x18000d894  cmovz   edx, ecx
0x18000d897  mov     ecx, eax
0x18000d899  btr     ecx, 0Eh
0x18000d89d  mov     eax, edx
0x18000d89f  or      eax, ecx
0x18000d8a1  mov     ecx, eax
0x18000d8a3  shr     ecx, 5
0x18000d8a6  and     ecx, 1FFh
0x18000d8ac  lea     edx, [rcx+1]
0x18000d8af  cmp     edx, 1FFh
0x18000d8b5  ja      short loc_18000D8C1
0x18000d8b7  cmp     edx, ecx
0x18000d8b9  jb      short loc_18000D8C1
0x18000d8bb  lea     r10, [r9+8]
0x18000d8bf  jmp     short loc_18000D8CD
0x18000d8c1  mov     edx, 1
0x18000d8c6  mov     [r10], ebx
0x18000d8c9  mov     [r9+4], ecx
0x18000d8cd  shl     edx, 5
0x18000d8d0  xor     edx, eax
0x18000d8d2  and     edx, 3FE0h
0x18000d8d8  xor     edx, eax
0x18000d8da  mov     eax, r8d
0x18000d8dd  lock cmpxchg [rsi], edx
0x18000d8e1  jz      short loc_18000D8EB
0x18000d8e3  mov     r8d, eax
0x18000d8e6  jmp     loc_18000D845
0x18000d8eb  not     r8d
0x18000d8ee  mov     dword ptr [r9+10h], 0
0x18000d8f6  and     r8d, 1
0x18000d8fa  mov     [r9], r8d
0x18000d8fd  pop     rdi
0x18000d8fe  pop     rsi
0x18000d8ff  pop     rbx
0x18000d900  retn
```
