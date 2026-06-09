# wil_details_EvaluateFeatureDependencies_ReevaluateCachedFeatureEnabledState

- ea: `0x1400248c4`
- end: `0x1400249d1`
- name: `wil_details_EvaluateFeatureDependencies_ReevaluateCachedFeatureEnabledState`
- size: `269`
- prototype: `__int64 __fastcall(volatile signed __int32 *, unsigned __int32, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140024770`
- `0x140024888`

## callees

- `0x140024888`
- `0x1400248c4`

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
  __int64 *v8; // r14
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
    v8 = *(__int64 **)(a3 + 32);
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
                                        *(_DWORD **)v9,
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
0x1400248c4  mov     [rsp+arg_8], rbx
0x1400248c9  mov     [rsp+arg_10], rbp
0x1400248ce  push    rsi
0x1400248cf  push    rdi
0x1400248d0  push    r13
0x1400248d2  push    r14
0x1400248d4  push    r15
0x1400248d6  sub     rsp, 20h
0x1400248da  mov     r13d, 1
0x1400248e0  mov     [rsp+48h+arg_0], 0
0x1400248e9  mov     esi, edx
0x1400248eb  mov     r15, rcx
0x1400248ee  shr     esi, 6
0x1400248f1  mov     ecx, 0C00h
0x1400248f6  mov     eax, edx
0x1400248f8  and     esi, r13d
0x1400248fb  and     eax, ecx
0x1400248fd  mov     rbx, rdx
0x140024900  mov     edi, r13d
0x140024903  cmp     eax, ecx
0x140024905  jz      short loc_14002490F
0x140024907  test    esi, esi
0x140024909  jnz     short loc_14002490F
0x14002490b  xor     ebp, ebp
0x14002490d  jmp     short loc_14002497D
0x14002490f  mov     r14, [r8+20h]
0x140024913  xor     ebp, ebp
0x140024915  cmp     eax, ecx
0x140024917  setz    bpl
0x14002491b  test    r14, r14
0x14002491e  jz      short loc_14002497D
0x140024920  mov     rax, [r14]
0x140024923  test    rax, rax
0x140024926  jz      short loc_14002496E
0x140024928  cmp     byte ptr [rax+1Eh], 0
0x14002492c  jnz     short loc_140024959
0x14002492e  cmp     byte ptr [rax+1Dh], 0
0x140024932  jnz     short loc_140024959
0x140024934  mov     rcx, [rax]
0x140024937  mov     rdx, rax
0x14002493a  call    wil_details_EvaluateFeatureDependencies_GetCachedFeatureEnabledState
0x14002493f  test    edi, edi
0x140024941  jz      short loc_14002494D
0x140024943  test    r13b, al
0x140024946  jz      short loc_14002494D
0x140024948  mov     edi, r13d
0x14002494b  jmp     short loc_14002494F
0x14002494d  xor     edi, edi
0x14002494f  add     r14, 8
0x140024953  test    edi, edi
0x140024955  jnz     short loc_140024920
0x140024957  jmp     short loc_14002496E
0x140024959  test    edi, edi
0x14002495b  jz      short loc_14002496C
0x14002495d  cmp     byte ptr [rax+1Fh], 0
0x140024961  jz      short loc_14002496C
0x140024963  mov     edi, r13d
0x140024966  add     r14, 8
0x14002496a  jmp     short loc_140024920
0x14002496c  xor     edi, edi
0x14002496e  test    esi, esi
0x140024970  jz      short loc_14002497B
0x140024972  test    edi, edi
0x140024974  jz      short loc_14002497B
0x140024976  mov     esi, r13d
0x140024979  jmp     short loc_14002497D
0x14002497b  xor     esi, esi
0x14002497d  mov     edx, ebx
0x14002497f  and     edx, 0FFFFFFFEh
0x140024982  or      edx, esi
0x140024984  test    ebp, ebp
0x140024986  jz      short loc_140024990
0x140024988  test    edi, edi
0x14002498a  jnz     short loc_140024990
0x14002498c  btr     edx, 0Ah
0x140024990  mov     eax, ebx
0x140024992  mov     ecx, edx
0x140024994  and     eax, r13d
0x140024997  and     ecx, 0FFFFFFCFh
0x14002499a  cmp     eax, esi
0x14002499c  mov     eax, ebx
0x14002499e  cmovz   ecx, edx
0x1400249a1  btr     ecx, 9
0x1400249a5  mov     dword ptr [rsp+48h+arg_0], ecx
0x1400249a9  lock cmpxchg [r15], ecx
0x1400249ae  jz      short loc_1400249B4
0x1400249b0  mov     ebx, eax
0x1400249b2  jmp     short loc_14002497D
0x1400249b4  mov     rax, [rsp+48h+arg_0]
0x1400249b9  mov     rbx, [rsp+48h+arg_8]
0x1400249be  mov     rbp, [rsp+48h+arg_10]
0x1400249c3  add     rsp, 20h
0x1400249c7  pop     r15
0x1400249c9  pop     r14
0x1400249cb  pop     r13
0x1400249cd  pop     rdi
0x1400249ce  pop     rsi
0x1400249cf  retn
```
