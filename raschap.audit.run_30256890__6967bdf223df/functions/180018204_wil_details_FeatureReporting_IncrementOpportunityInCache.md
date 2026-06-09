# wil_details_FeatureReporting_IncrementOpportunityInCache

- ea: `0x180018204`
- end: `0x1800182cd`
- name: `wil_details_FeatureReporting_IncrementOpportunityInCache`
- size: `201`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800183b0`

## callees

- `0x180018204`

## pseudocode

```c
__int64 __fastcall wil_details_FeatureReporting_IncrementOpportunityInCache(
        volatile signed __int32 *a1,
        int a2,
        __int64 a3,
        _DWORD *a4)
{
  signed __int32 v4; // r8d
  int *v5; // r10
  BOOL v8; // ebx
  unsigned int v9; // eax
  int v10; // ecx
  int v11; // edx
  unsigned int v12; // ecx
  unsigned int v13; // edx
  __int64 result; // rax

  v4 = *a1;
  v5 = a4 + 2;
  v8 = a2 == 5;
  while ( 1 )
  {
    a4[1] = 0;
    v9 = v4 | 1;
    if ( (((v4 | 1u) >> 22) & 1) != v8 )
    {
      if ( ((v9 >> 15) & 0x7F) != 0 )
      {
        a4[1] = (v9 >> 15) & 0x7F;
        v10 = 5;
        v5 = a4 + 2;
        if ( a2 != 1 )
          v10 = 1;
        v9 = v4 & 0xFFC07FFE | 1;
        *v5 = v10;
      }
      v11 = 0;
      if ( a2 == 5 )
        v11 = 0x400000;
      v9 = v9 & 0xFFBFFFFF | v11;
    }
    v12 = (v9 >> 15) & 0x7F;
    v13 = v12 + 1;
    if ( v12 + 1 > 0x7F || v13 < v12 )
    {
      v13 = 1;
      *v5 = a2;
      a4[1] = v12;
    }
    else
    {
      v5 = a4 + 2;
    }
    result = (unsigned int)_InterlockedCompareExchange(a1, v9 ^ (v9 ^ (v13 << 15)) & 0x3F8000, v4);
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
0x180018204  push    rbx
0x180018206  push    rsi
0x180018207  push    rdi
0x180018208  mov     r8d, [rcx]
0x18001820b  lea     r10, [r9+8]
0x18001820f  xor     ebx, ebx
0x180018211  mov     r11d, edx
0x180018214  cmp     edx, 5
0x180018217  mov     rdi, rcx
0x18001821a  mov     esi, 1
0x18001821f  setz    bl
0x180018222  mov     eax, r8d
0x180018225  mov     dword ptr [r9+4], 0
0x18001822d  or      eax, esi
0x18001822f  mov     ecx, eax
0x180018231  shr     ecx, 16h
0x180018234  and     ecx, esi
0x180018236  cmp     ecx, ebx
0x180018238  jz      short loc_180018277
0x18001823a  mov     edx, eax
0x18001823c  shr     edx, 0Fh
0x18001823f  and     edx, 7Fh
0x180018242  jbe     short loc_18001825F
0x180018244  cmp     r11d, esi
0x180018247  mov     [r9+4], edx
0x18001824b  mov     ecx, 5
0x180018250  lea     r10, [r9+8]
0x180018254  cmovnz  ecx, esi
0x180018257  and     eax, 0FFC07FFFh
0x18001825c  mov     [r10], ecx
0x18001825f  xor     edx, edx
0x180018261  mov     ecx, 400000h
0x180018266  cmp     r11d, 5
0x18001826a  cmovz   edx, ecx
0x18001826d  mov     ecx, eax
0x18001826f  btr     ecx, 16h
0x180018273  mov     eax, edx
0x180018275  or      eax, ecx
0x180018277  mov     ecx, eax
0x180018279  shr     ecx, 0Fh
0x18001827c  and     ecx, 7Fh
0x18001827f  lea     edx, [rcx+1]
0x180018282  cmp     edx, 7Fh
0x180018285  ja      short loc_180018291
0x180018287  cmp     edx, ecx
0x180018289  jb      short loc_180018291
0x18001828b  lea     r10, [r9+8]
0x18001828f  jmp     short loc_18001829A
0x180018291  mov     edx, esi
0x180018293  mov     [r10], r11d
0x180018296  mov     [r9+4], ecx
0x18001829a  shl     edx, 0Fh
0x18001829d  xor     edx, eax
0x18001829f  and     edx, 3F8000h
0x1800182a5  xor     edx, eax
0x1800182a7  mov     eax, r8d
0x1800182aa  lock cmpxchg [rdi], edx
0x1800182ae  jz      short loc_1800182B8
0x1800182b0  mov     r8d, eax
0x1800182b3  jmp     loc_180018222
0x1800182b8  not     r8d
0x1800182bb  mov     dword ptr [r9+10h], 0
0x1800182c3  and     r8d, esi
0x1800182c6  mov     [r9], r8d
0x1800182c9  pop     rdi
0x1800182ca  pop     rsi
0x1800182cb  pop     rbx
0x1800182cc  retn
```
