# wil_details_EvaluateFeatureDependencies_ReevaluateCachedFeatureEnabledState

- ea: `0x140033398`
- end: `0x1400334a5`
- name: `wil_details_EvaluateFeatureDependencies_ReevaluateCachedFeatureEnabledState`
- size: `269`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140033244`
- `0x14003335c`

## callees

- `0x14003335c`
- `0x140033398`

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
0x140033398  mov     [rsp+arg_8], rbx
0x14003339d  mov     [rsp+arg_10], rbp
0x1400333a2  push    rsi
0x1400333a3  push    rdi
0x1400333a4  push    r13
0x1400333a6  push    r14
0x1400333a8  push    r15
0x1400333aa  sub     rsp, 20h
0x1400333ae  mov     r13d, 1
0x1400333b4  mov     [rsp+48h+arg_0], 0
0x1400333bd  mov     esi, edx
0x1400333bf  mov     r15, rcx
0x1400333c2  shr     esi, 6
0x1400333c5  mov     ecx, 0C00h
0x1400333ca  mov     eax, edx
0x1400333cc  and     esi, r13d
0x1400333cf  and     eax, ecx
0x1400333d1  mov     rbx, rdx
0x1400333d4  mov     edi, r13d
0x1400333d7  cmp     eax, ecx
0x1400333d9  jz      short loc_1400333E3
0x1400333db  test    esi, esi
0x1400333dd  jnz     short loc_1400333E3
0x1400333df  xor     ebp, ebp
0x1400333e1  jmp     short loc_140033451
0x1400333e3  mov     r14, [r8+20h]
0x1400333e7  xor     ebp, ebp
0x1400333e9  cmp     eax, ecx
0x1400333eb  setz    bpl
0x1400333ef  test    r14, r14
0x1400333f2  jz      short loc_140033451
0x1400333f4  mov     rax, [r14]
0x1400333f7  test    rax, rax
0x1400333fa  jz      short loc_140033442
0x1400333fc  cmp     byte ptr [rax+1Eh], 0
0x140033400  jnz     short loc_14003342D
0x140033402  cmp     byte ptr [rax+1Dh], 0
0x140033406  jnz     short loc_14003342D
0x140033408  mov     rcx, [rax]
0x14003340b  mov     rdx, rax
0x14003340e  call    wil_details_EvaluateFeatureDependencies_GetCachedFeatureEnabledState
0x140033413  test    edi, edi
0x140033415  jz      short loc_140033421
0x140033417  test    r13b, al
0x14003341a  jz      short loc_140033421
0x14003341c  mov     edi, r13d
0x14003341f  jmp     short loc_140033423
0x140033421  xor     edi, edi
0x140033423  add     r14, 8
0x140033427  test    edi, edi
0x140033429  jnz     short loc_1400333F4
0x14003342b  jmp     short loc_140033442
0x14003342d  test    edi, edi
0x14003342f  jz      short loc_140033440
0x140033431  cmp     byte ptr [rax+1Fh], 0
0x140033435  jz      short loc_140033440
0x140033437  mov     edi, r13d
0x14003343a  add     r14, 8
0x14003343e  jmp     short loc_1400333F4
0x140033440  xor     edi, edi
0x140033442  test    esi, esi
0x140033444  jz      short loc_14003344F
0x140033446  test    edi, edi
0x140033448  jz      short loc_14003344F
0x14003344a  mov     esi, r13d
0x14003344d  jmp     short loc_140033451
0x14003344f  xor     esi, esi
0x140033451  mov     edx, ebx
0x140033453  and     edx, 0FFFFFFFEh
0x140033456  or      edx, esi
0x140033458  test    ebp, ebp
0x14003345a  jz      short loc_140033464
0x14003345c  test    edi, edi
0x14003345e  jnz     short loc_140033464
0x140033460  btr     edx, 0Ah
0x140033464  mov     eax, ebx
0x140033466  mov     ecx, edx
0x140033468  and     eax, r13d
0x14003346b  and     ecx, 0FFFFFFCFh
0x14003346e  cmp     eax, esi
0x140033470  mov     eax, ebx
0x140033472  cmovz   ecx, edx
0x140033475  btr     ecx, 9
0x140033479  mov     dword ptr [rsp+48h+arg_0], ecx
0x14003347d  lock cmpxchg [r15], ecx
0x140033482  jz      short loc_140033488
0x140033484  mov     ebx, eax
0x140033486  jmp     short loc_140033451
0x140033488  mov     rax, [rsp+48h+arg_0]
0x14003348d  mov     rbx, [rsp+48h+arg_8]
0x140033492  mov     rbp, [rsp+48h+arg_10]
0x140033497  add     rsp, 20h
0x14003349b  pop     r15
0x14003349d  pop     r14
0x14003349f  pop     r13
0x1400334a1  pop     rdi
0x1400334a2  pop     rsi
0x1400334a3  retn
```
