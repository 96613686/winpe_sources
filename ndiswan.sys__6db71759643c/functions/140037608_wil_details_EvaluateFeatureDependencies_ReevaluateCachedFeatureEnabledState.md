# wil_details_EvaluateFeatureDependencies_ReevaluateCachedFeatureEnabledState

- ea: `0x140037608`
- end: `0x140037715`
- name: `wil_details_EvaluateFeatureDependencies_ReevaluateCachedFeatureEnabledState`
- size: `269`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400375cc`

## callees

- `0x1400375cc`
- `0x140037608`

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
0x140037608  mov     [rsp+arg_8], rbx
0x14003760d  mov     [rsp+arg_10], rbp
0x140037612  push    rsi
0x140037613  push    rdi
0x140037614  push    r13
0x140037616  push    r14
0x140037618  push    r15
0x14003761a  sub     rsp, 20h
0x14003761e  mov     r13d, 1
0x140037624  mov     [rsp+48h+arg_0], 0
0x14003762d  mov     esi, edx
0x14003762f  mov     r15, rcx
0x140037632  shr     esi, 6
0x140037635  mov     ecx, 0C00h
0x14003763a  mov     eax, edx
0x14003763c  and     esi, r13d
0x14003763f  and     eax, ecx
0x140037641  mov     rbx, rdx
0x140037644  mov     edi, r13d
0x140037647  cmp     eax, ecx
0x140037649  jz      short loc_140037653
0x14003764b  test    esi, esi
0x14003764d  jnz     short loc_140037653
0x14003764f  xor     ebp, ebp
0x140037651  jmp     short loc_1400376C1
0x140037653  mov     r14, [r8+20h]
0x140037657  xor     ebp, ebp
0x140037659  cmp     eax, ecx
0x14003765b  setz    bpl
0x14003765f  test    r14, r14
0x140037662  jz      short loc_1400376C1
0x140037664  mov     rax, [r14]
0x140037667  test    rax, rax
0x14003766a  jz      short loc_1400376B2
0x14003766c  cmp     byte ptr [rax+1Eh], 0
0x140037670  jnz     short loc_14003769D
0x140037672  cmp     byte ptr [rax+1Dh], 0
0x140037676  jnz     short loc_14003769D
0x140037678  mov     rcx, [rax]
0x14003767b  mov     rdx, rax
0x14003767e  call    wil_details_EvaluateFeatureDependencies_GetCachedFeatureEnabledState
0x140037683  test    edi, edi
0x140037685  jz      short loc_140037691
0x140037687  test    r13b, al
0x14003768a  jz      short loc_140037691
0x14003768c  mov     edi, r13d
0x14003768f  jmp     short loc_140037693
0x140037691  xor     edi, edi
0x140037693  add     r14, 8
0x140037697  test    edi, edi
0x140037699  jnz     short loc_140037664
0x14003769b  jmp     short loc_1400376B2
0x14003769d  test    edi, edi
0x14003769f  jz      short loc_1400376B0
0x1400376a1  cmp     byte ptr [rax+1Fh], 0
0x1400376a5  jz      short loc_1400376B0
0x1400376a7  mov     edi, r13d
0x1400376aa  add     r14, 8
0x1400376ae  jmp     short loc_140037664
0x1400376b0  xor     edi, edi
0x1400376b2  test    esi, esi
0x1400376b4  jz      short loc_1400376BF
0x1400376b6  test    edi, edi
0x1400376b8  jz      short loc_1400376BF
0x1400376ba  mov     esi, r13d
0x1400376bd  jmp     short loc_1400376C1
0x1400376bf  xor     esi, esi
0x1400376c1  mov     edx, ebx
0x1400376c3  and     edx, 0FFFFFFFEh
0x1400376c6  or      edx, esi
0x1400376c8  test    ebp, ebp
0x1400376ca  jz      short loc_1400376D4
0x1400376cc  test    edi, edi
0x1400376ce  jnz     short loc_1400376D4
0x1400376d0  btr     edx, 0Ah
0x1400376d4  mov     eax, ebx
0x1400376d6  mov     ecx, edx
0x1400376d8  and     eax, r13d
0x1400376db  and     ecx, 0FFFFFFCFh
0x1400376de  cmp     eax, esi
0x1400376e0  mov     eax, ebx
0x1400376e2  cmovz   ecx, edx
0x1400376e5  btr     ecx, 9
0x1400376e9  mov     dword ptr [rsp+48h+arg_0], ecx
0x1400376ed  lock cmpxchg [r15], ecx
0x1400376f2  jz      short loc_1400376F8
0x1400376f4  mov     ebx, eax
0x1400376f6  jmp     short loc_1400376C1
0x1400376f8  mov     rax, [rsp+48h+arg_0]
0x1400376fd  mov     rbx, [rsp+48h+arg_8]
0x140037702  mov     rbp, [rsp+48h+arg_10]
0x140037707  add     rsp, 20h
0x14003770b  pop     r15
0x14003770d  pop     r14
0x14003770f  pop     r13
0x140037711  pop     rdi
0x140037712  pop     rsi
0x140037713  retn
```
