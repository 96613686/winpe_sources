# wil_details_EvaluateFeatureDependencies_ReevaluateCachedFeatureEnabledState

- ea: `0x1400186d0`
- end: `0x1400187dd`
- name: `wil_details_EvaluateFeatureDependencies_ReevaluateCachedFeatureEnabledState`
- size: `269`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140018694`

## callees

- `0x140018694`
- `0x1400186d0`

## pseudocode

```c
__int64 __fastcall wil_details_EvaluateFeatureDependencies_ReevaluateCachedFeatureEnabledState(
        volatile signed __int32 *a1,
        unsigned __int32 a2,
        __int64 a3)
{
  int v4; // esi
  signed __int32 v5; // ebx
  BOOL v6; // edi
  BOOL v7; // ebp
  _QWORD *v8; // r14
  __int64 v9; // rax
  char CachedFeatureEnabledState; // al
  unsigned int v11; // edx
  unsigned int v12; // ecx
  signed __int32 v13; // eax
  __int64 v15; // [rsp+50h] [rbp+8h]

  HIDWORD(v15) = 0;
  v4 = (a2 >> 6) & 1;
  v5 = a2;
  v6 = 1;
  if ( (a2 & 0xC00) == 0xC00 || v4 )
  {
    v8 = *(_QWORD **)(a3 + 32);
    v7 = (a2 & 0xC00) == 3072;
    if ( v8 )
    {
      while ( 1 )
      {
        v9 = *v8;
        if ( !*v8 )
          break;
        if ( *(_BYTE *)(v9 + 30) || *(_BYTE *)(v9 + 29) )
        {
          if ( !*(_BYTE *)(v9 + 31) )
          {
            v6 = 0;
            break;
          }
          v6 = 1;
          ++v8;
        }
        else
        {
          CachedFeatureEnabledState = wil_details_EvaluateFeatureDependencies_GetCachedFeatureEnabledState(
                                        *(_QWORD *)v9,
                                        *v8);
          v6 = (CachedFeatureEnabledState & 1) != 0;
          ++v8;
          if ( (CachedFeatureEnabledState & 1) == 0 )
            break;
        }
      }
      v4 = v4 && v6;
    }
  }
  else
  {
    v7 = 0;
  }
  while ( 1 )
  {
    v11 = v4 | v5 & 0xFFFFFFFE;
    if ( v7 && !v6 )
      v11 = v4 & 0xFFFFFBFF | v5 & 0xFFFFFBFE;
    v12 = v11 & 0xFFFFFFCF;
    if ( (v5 & 1) == v4 )
      v12 = v11;
    v13 = _InterlockedCompareExchange(a1, v12 & 0xFFFFFDFF, v5);
    if ( v5 == v13 )
      break;
    v5 = v13;
  }
  LODWORD(v15) = v12 & 0xFFFFFDFF;
  return v15;
}

```

## disassembly

```asm
0x1400186d0  mov     [rsp+arg_8], rbx
0x1400186d5  mov     [rsp+arg_10], rbp
0x1400186da  push    rsi
0x1400186db  push    rdi
0x1400186dc  push    r13
0x1400186de  push    r14
0x1400186e0  push    r15
0x1400186e2  sub     rsp, 20h
0x1400186e6  mov     r13d, 1
0x1400186ec  mov     [rsp+48h+arg_0], 0
0x1400186f5  mov     esi, edx
0x1400186f7  mov     r15, rcx
0x1400186fa  shr     esi, 6
0x1400186fd  mov     ecx, 0C00h
0x140018702  mov     eax, edx
0x140018704  and     esi, r13d
0x140018707  and     eax, ecx
0x140018709  mov     rbx, rdx
0x14001870c  mov     edi, r13d
0x14001870f  cmp     eax, ecx
0x140018711  jz      short loc_14001871B
0x140018713  test    esi, esi
0x140018715  jnz     short loc_14001871B
0x140018717  xor     ebp, ebp
0x140018719  jmp     short loc_140018789
0x14001871b  mov     r14, [r8+20h]
0x14001871f  xor     ebp, ebp
0x140018721  cmp     eax, ecx
0x140018723  setz    bpl
0x140018727  test    r14, r14
0x14001872a  jz      short loc_140018789
0x14001872c  mov     rax, [r14]
0x14001872f  test    rax, rax
0x140018732  jz      short loc_14001877A
0x140018734  cmp     byte ptr [rax+1Eh], 0
0x140018738  jnz     short loc_140018765
0x14001873a  cmp     byte ptr [rax+1Dh], 0
0x14001873e  jnz     short loc_140018765
0x140018740  mov     rcx, [rax]
0x140018743  mov     rdx, rax
0x140018746  call    wil_details_EvaluateFeatureDependencies_GetCachedFeatureEnabledState
0x14001874b  test    edi, edi
0x14001874d  jz      short loc_140018759
0x14001874f  test    r13b, al
0x140018752  jz      short loc_140018759
0x140018754  mov     edi, r13d
0x140018757  jmp     short loc_14001875B
0x140018759  xor     edi, edi
0x14001875b  add     r14, 8
0x14001875f  test    edi, edi
0x140018761  jnz     short loc_14001872C
0x140018763  jmp     short loc_14001877A
0x140018765  test    edi, edi
0x140018767  jz      short loc_140018778
0x140018769  cmp     byte ptr [rax+1Fh], 0
0x14001876d  jz      short loc_140018778
0x14001876f  mov     edi, r13d
0x140018772  add     r14, 8
0x140018776  jmp     short loc_14001872C
0x140018778  xor     edi, edi
0x14001877a  test    esi, esi
0x14001877c  jz      short loc_140018787
0x14001877e  test    edi, edi
0x140018780  jz      short loc_140018787
0x140018782  mov     esi, r13d
0x140018785  jmp     short loc_140018789
0x140018787  xor     esi, esi
0x140018789  mov     edx, ebx
0x14001878b  and     edx, 0FFFFFFFEh
0x14001878e  or      edx, esi
0x140018790  test    ebp, ebp
0x140018792  jz      short loc_14001879C
0x140018794  test    edi, edi
0x140018796  jnz     short loc_14001879C
0x140018798  btr     edx, 0Ah
0x14001879c  mov     eax, ebx
0x14001879e  mov     ecx, edx
0x1400187a0  and     eax, r13d
0x1400187a3  and     ecx, 0FFFFFFCFh
0x1400187a6  cmp     eax, esi
0x1400187a8  mov     eax, ebx
0x1400187aa  cmovz   ecx, edx
0x1400187ad  btr     ecx, 9
0x1400187b1  mov     dword ptr [rsp+48h+arg_0], ecx
0x1400187b5  lock cmpxchg [r15], ecx
0x1400187ba  jz      short loc_1400187C0
0x1400187bc  mov     ebx, eax
0x1400187be  jmp     short loc_140018789
0x1400187c0  mov     rax, [rsp+48h+arg_0]
0x1400187c5  mov     rbx, [rsp+48h+arg_8]
0x1400187ca  mov     rbp, [rsp+48h+arg_10]
0x1400187cf  add     rsp, 20h
0x1400187d3  pop     r15
0x1400187d5  pop     r14
0x1400187d7  pop     r13
0x1400187d9  pop     rdi
0x1400187da  pop     rsi
0x1400187db  retn
```
