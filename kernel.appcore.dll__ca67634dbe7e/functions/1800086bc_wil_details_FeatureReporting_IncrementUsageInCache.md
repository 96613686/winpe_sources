# wil_details_FeatureReporting_IncrementUsageInCache

- ea: `0x1800086bc`
- end: `0x180008791`
- name: `wil_details_FeatureReporting_IncrementUsageInCache`
- size: `213`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180008798`

## callees

- `0x1800086bc`

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
0x1800086bc  push    rbx
0x1800086be  push    rsi
0x1800086bf  push    rdi
0x1800086c0  mov     r8d, [rcx]
0x1800086c3  lea     r10, [r9+8]
0x1800086c7  xor     edi, edi
0x1800086c9  mov     ebx, edx
0x1800086cb  cmp     edx, 4
0x1800086ce  mov     rsi, rcx
0x1800086d1  setz    dil
0x1800086d5  mov     eax, r8d
0x1800086d8  mov     dword ptr [r9+4], 0
0x1800086e0  or      eax, 1
0x1800086e3  mov     ecx, eax
0x1800086e5  shr     ecx, 0Eh
0x1800086e8  and     ecx, 1
0x1800086eb  cmp     ecx, edi
0x1800086ed  jz      short loc_180008731
0x1800086ef  mov     r11d, eax
0x1800086f2  shr     r11d, 5
0x1800086f6  and     r11d, 1FFh
0x1800086fd  jbe     short loc_18000871A
0x1800086ff  mov     ecx, ebx
0x180008701  mov     [r9+4], r11d
0x180008705  neg     ecx
0x180008707  lea     r10, [r9+8]
0x18000870b  sbb     edx, edx
0x18000870d  not     edx
0x18000870f  and     edx, 4
0x180008712  mov     [r10], edx
0x180008715  and     eax, 0FFFFC01Fh
0x18000871a  xor     edx, edx
0x18000871c  mov     ecx, 4000h
0x180008721  cmp     ebx, 4
0x180008724  cmovz   edx, ecx
0x180008727  mov     ecx, eax
0x180008729  btr     ecx, 0Eh
0x18000872d  mov     eax, edx
0x18000872f  or      eax, ecx
0x180008731  mov     ecx, eax
0x180008733  shr     ecx, 5
0x180008736  and     ecx, 1FFh
0x18000873c  lea     edx, [rcx+1]
0x18000873f  cmp     edx, 1FFh
0x180008745  ja      short loc_180008751
0x180008747  cmp     edx, ecx
0x180008749  jb      short loc_180008751
0x18000874b  lea     r10, [r9+8]
0x18000874f  jmp     short loc_18000875D
0x180008751  mov     edx, 1
0x180008756  mov     [r10], ebx
0x180008759  mov     [r9+4], ecx
0x18000875d  shl     edx, 5
0x180008760  xor     edx, eax
0x180008762  and     edx, 3FE0h
0x180008768  xor     edx, eax
0x18000876a  mov     eax, r8d
0x18000876d  lock cmpxchg [rsi], edx
0x180008771  jz      short loc_18000877B
0x180008773  mov     r8d, eax
0x180008776  jmp     loc_1800086D5
0x18000877b  not     r8d
0x18000877e  mov     dword ptr [r9+10h], 0
0x180008786  and     r8d, 1
0x18000878a  mov     [r9], r8d
0x18000878d  pop     rdi
0x18000878e  pop     rsi
0x18000878f  pop     rbx
0x180008790  retn
```
