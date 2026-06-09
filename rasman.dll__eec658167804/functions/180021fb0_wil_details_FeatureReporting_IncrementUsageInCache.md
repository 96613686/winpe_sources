# wil_details_FeatureReporting_IncrementUsageInCache

- ea: `0x180021fb0`
- end: `0x180022085`
- name: `wil_details_FeatureReporting_IncrementUsageInCache`
- size: `213`
- prototype: `__int64 __fastcall(volatile signed __int32 *, int, __int64, _DWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18002208c`

## callees

- `0x180021fb0`

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
0x180021fb0  push    rbx
0x180021fb2  push    rsi
0x180021fb3  push    rdi
0x180021fb4  mov     r8d, [rcx]
0x180021fb7  lea     r10, [r9+8]
0x180021fbb  xor     edi, edi
0x180021fbd  mov     ebx, edx
0x180021fbf  cmp     edx, 4
0x180021fc2  mov     rsi, rcx
0x180021fc5  setz    dil
0x180021fc9  mov     eax, r8d
0x180021fcc  mov     dword ptr [r9+4], 0
0x180021fd4  or      eax, 1
0x180021fd7  mov     ecx, eax
0x180021fd9  shr     ecx, 0Eh
0x180021fdc  and     ecx, 1
0x180021fdf  cmp     ecx, edi
0x180021fe1  jz      short loc_180022025
0x180021fe3  mov     r11d, eax
0x180021fe6  shr     r11d, 5
0x180021fea  and     r11d, 1FFh
0x180021ff1  jbe     short loc_18002200E
0x180021ff3  mov     ecx, ebx
0x180021ff5  mov     [r9+4], r11d
0x180021ff9  neg     ecx
0x180021ffb  lea     r10, [r9+8]
0x180021fff  sbb     edx, edx
0x180022001  not     edx
0x180022003  and     edx, 4
0x180022006  mov     [r10], edx
0x180022009  and     eax, 0FFFFC01Fh
0x18002200e  xor     edx, edx
0x180022010  mov     ecx, 4000h
0x180022015  cmp     ebx, 4
0x180022018  cmovz   edx, ecx
0x18002201b  mov     ecx, eax
0x18002201d  btr     ecx, 0Eh
0x180022021  mov     eax, edx
0x180022023  or      eax, ecx
0x180022025  mov     ecx, eax
0x180022027  shr     ecx, 5
0x18002202a  and     ecx, 1FFh
0x180022030  lea     edx, [rcx+1]
0x180022033  cmp     edx, 1FFh
0x180022039  ja      short loc_180022045
0x18002203b  cmp     edx, ecx
0x18002203d  jb      short loc_180022045
0x18002203f  lea     r10, [r9+8]
0x180022043  jmp     short loc_180022051
0x180022045  mov     edx, 1
0x18002204a  mov     [r10], ebx
0x18002204d  mov     [r9+4], ecx
0x180022051  shl     edx, 5
0x180022054  xor     edx, eax
0x180022056  and     edx, 3FE0h
0x18002205c  xor     edx, eax
0x18002205e  mov     eax, r8d
0x180022061  lock cmpxchg [rsi], edx
0x180022065  jz      short loc_18002206F
0x180022067  mov     r8d, eax
0x18002206a  jmp     loc_180021FC9
0x18002206f  not     r8d
0x180022072  mov     dword ptr [r9+10h], 0
0x18002207a  and     r8d, 1
0x18002207e  mov     [r9], r8d
0x180022081  pop     rdi
0x180022082  pop     rsi
0x180022083  pop     rbx
0x180022084  retn
```
