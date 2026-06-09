# wil_details_FeatureReporting_IncrementOpportunityInCache

- ea: `0x1800162ac`
- end: `0x180016375`
- name: `wil_details_FeatureReporting_IncrementOpportunityInCache`
- size: `201`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180016458`

## callees

- `0x1800162ac`

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
0x1800162ac  push    rbx
0x1800162ae  push    rsi
0x1800162af  push    rdi
0x1800162b0  mov     r8d, [rcx]
0x1800162b3  lea     r10, [r9+8]
0x1800162b7  xor     ebx, ebx
0x1800162b9  mov     r11d, edx
0x1800162bc  cmp     edx, 5
0x1800162bf  mov     rdi, rcx
0x1800162c2  mov     esi, 1
0x1800162c7  setz    bl
0x1800162ca  mov     eax, r8d
0x1800162cd  mov     dword ptr [r9+4], 0
0x1800162d5  or      eax, esi
0x1800162d7  mov     ecx, eax
0x1800162d9  shr     ecx, 16h
0x1800162dc  and     ecx, esi
0x1800162de  cmp     ecx, ebx
0x1800162e0  jz      short loc_18001631F
0x1800162e2  mov     edx, eax
0x1800162e4  shr     edx, 0Fh
0x1800162e7  and     edx, 7Fh
0x1800162ea  jbe     short loc_180016307
0x1800162ec  cmp     r11d, esi
0x1800162ef  mov     [r9+4], edx
0x1800162f3  mov     ecx, 5
0x1800162f8  lea     r10, [r9+8]
0x1800162fc  cmovnz  ecx, esi
0x1800162ff  and     eax, 0FFC07FFFh
0x180016304  mov     [r10], ecx
0x180016307  xor     edx, edx
0x180016309  mov     ecx, 400000h
0x18001630e  cmp     r11d, 5
0x180016312  cmovz   edx, ecx
0x180016315  mov     ecx, eax
0x180016317  btr     ecx, 16h
0x18001631b  mov     eax, edx
0x18001631d  or      eax, ecx
0x18001631f  mov     ecx, eax
0x180016321  shr     ecx, 0Fh
0x180016324  and     ecx, 7Fh
0x180016327  lea     edx, [rcx+1]
0x18001632a  cmp     edx, 7Fh
0x18001632d  ja      short loc_180016339
0x18001632f  cmp     edx, ecx
0x180016331  jb      short loc_180016339
0x180016333  lea     r10, [r9+8]
0x180016337  jmp     short loc_180016342
0x180016339  mov     edx, esi
0x18001633b  mov     [r10], r11d
0x18001633e  mov     [r9+4], ecx
0x180016342  shl     edx, 0Fh
0x180016345  xor     edx, eax
0x180016347  and     edx, 3F8000h
0x18001634d  xor     edx, eax
0x18001634f  mov     eax, r8d
0x180016352  lock cmpxchg [rdi], edx
0x180016356  jz      short loc_180016360
0x180016358  mov     r8d, eax
0x18001635b  jmp     loc_1800162CA
0x180016360  not     r8d
0x180016363  mov     dword ptr [r9+10h], 0
0x18001636b  and     r8d, esi
0x18001636e  mov     [r9], r8d
0x180016371  pop     rdi
0x180016372  pop     rsi
0x180016373  pop     rbx
0x180016374  retn
```
