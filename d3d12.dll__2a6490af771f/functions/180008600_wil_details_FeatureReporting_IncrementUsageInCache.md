# wil_details_FeatureReporting_IncrementUsageInCache

- ea: `0x180008600`
- end: `0x1800086d5`
- name: `wil_details_FeatureReporting_IncrementUsageInCache`
- size: `213`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180008484`

## callees

- `0x180008600`

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
0x180008600  push    rbx
0x180008602  push    rsi
0x180008603  push    rdi
0x180008604  mov     r8d, [rcx]
0x180008607  lea     r10, [r9+8]
0x18000860b  xor     edi, edi
0x18000860d  mov     ebx, edx
0x18000860f  cmp     edx, 4
0x180008612  mov     rsi, rcx
0x180008615  setz    dil
0x180008619  mov     eax, r8d
0x18000861c  mov     dword ptr [r9+4], 0
0x180008624  or      eax, 1
0x180008627  mov     ecx, eax
0x180008629  shr     ecx, 0Eh
0x18000862c  and     ecx, 1
0x18000862f  cmp     ecx, edi
0x180008631  jz      short loc_180008675
0x180008633  mov     r11d, eax
0x180008636  shr     r11d, 5
0x18000863a  and     r11d, 1FFh
0x180008641  jbe     short loc_18000865E
0x180008643  mov     ecx, ebx
0x180008645  mov     [r9+4], r11d
0x180008649  neg     ecx
0x18000864b  lea     r10, [r9+8]
0x18000864f  sbb     edx, edx
0x180008651  not     edx
0x180008653  and     edx, 4
0x180008656  mov     [r10], edx
0x180008659  and     eax, 0FFFFC01Fh
0x18000865e  xor     edx, edx
0x180008660  mov     ecx, 4000h
0x180008665  cmp     ebx, 4
0x180008668  cmovz   edx, ecx
0x18000866b  mov     ecx, eax
0x18000866d  btr     ecx, 0Eh
0x180008671  mov     eax, edx
0x180008673  or      eax, ecx
0x180008675  mov     ecx, eax
0x180008677  shr     ecx, 5
0x18000867a  and     ecx, 1FFh
0x180008680  lea     edx, [rcx+1]
0x180008683  cmp     edx, 1FFh
0x180008689  ja      short loc_180008695
0x18000868b  cmp     edx, ecx
0x18000868d  jb      short loc_180008695
0x18000868f  lea     r10, [r9+8]
0x180008693  jmp     short loc_1800086A1
0x180008695  mov     edx, 1
0x18000869a  mov     [r10], ebx
0x18000869d  mov     [r9+4], ecx
0x1800086a1  shl     edx, 5
0x1800086a4  xor     edx, eax
0x1800086a6  and     edx, 3FE0h
0x1800086ac  xor     edx, eax
0x1800086ae  mov     eax, r8d
0x1800086b1  lock cmpxchg [rsi], edx
0x1800086b5  jz      short loc_1800086BF
0x1800086b7  mov     r8d, eax
0x1800086ba  jmp     loc_180008619
0x1800086bf  not     r8d
0x1800086c2  mov     dword ptr [r9+10h], 0
0x1800086ca  and     r8d, 1
0x1800086ce  mov     [r9], r8d
0x1800086d1  pop     rdi
0x1800086d2  pop     rsi
0x1800086d3  pop     rbx
0x1800086d4  retn
```
