# wil_details_EvaluateFeatureDependencies_ReevaluateCachedFeatureEnabledState

- ea: `0x14000f6b8`
- end: `0x14000f76e`
- name: `wil_details_EvaluateFeatureDependencies_ReevaluateCachedFeatureEnabledState`
- size: `182`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14000f67c`

## callees

- `0x14000f67c`
- `0x14000f6b8`

## pseudocode

```c
__int64 __fastcall wil_details_EvaluateFeatureDependencies_ReevaluateCachedFeatureEnabledState(
        volatile signed __int32 *a1,
        unsigned __int32 a2,
        __int64 a3)
{
  signed __int32 v3; // ebx
  int v5; // edi
  __int64 *v6; // rsi
  __int64 v7; // rax
  unsigned int v8; // edx
  signed __int32 v9; // eax
  __int64 v11; // [rsp+50h] [rbp+8h]

  HIDWORD(v11) = 0;
  v3 = a2;
  v5 = (a2 >> 6) & 1;
  if ( v5 )
  {
    v6 = *(__int64 **)(a3 + 32);
    if ( v6 )
    {
      while ( 1 )
      {
        v7 = *v6;
        if ( !*v6 )
          break;
        if ( *(_BYTE *)(v7 + 30) || *(_BYTE *)(v7 + 29) )
        {
          if ( !*(_BYTE *)(v7 + 31) )
          {
            v5 = 0;
            goto LABEL_11;
          }
          v5 = 1;
          ++v6;
        }
        else
        {
          v5 = (wil_details_EvaluateFeatureDependencies_GetCachedFeatureEnabledState(*(_DWORD **)v7, *v6++) & 1) != 0;
          if ( !v5 )
            goto LABEL_11;
        }
      }
    }
  }
  while ( 1 )
  {
LABEL_11:
    v8 = v5 & 0xFFFFFFCF | v3 & 0xFFFFFFCE;
    if ( (v3 & 1) == v5 )
      v8 = v5 | v3 & 0xFFFFFFFE;
    v9 = _InterlockedCompareExchange(a1, v8 & 0xFFFFFDFF, v3);
    if ( v3 == v9 )
      break;
    v3 = v9;
  }
  LODWORD(v11) = v8 & 0xFFFFFDFF;
  return v11;
}

```

## disassembly

```asm
0x14000f6b8  push    rbx
0x14000f6ba  push    rbp
0x14000f6bb  push    rsi
0x14000f6bc  push    rdi
0x14000f6bd  sub     rsp, 28h
0x14000f6c1  mov     edi, edx
0x14000f6c3  mov     [rsp+48h+arg_0], 0
0x14000f6cc  shr     edi, 6
0x14000f6cf  mov     rbx, rdx
0x14000f6d2  mov     rbp, rcx
0x14000f6d5  and     edi, 1
0x14000f6d8  jz      short loc_14000F734
0x14000f6da  mov     rsi, [r8+20h]
0x14000f6de  test    rsi, rsi
0x14000f6e1  jz      short loc_14000F734
0x14000f6e3  mov     rax, [rsi]
0x14000f6e6  test    rax, rax
0x14000f6e9  jz      short loc_14000F734
0x14000f6eb  cmp     byte ptr [rax+1Eh], 0
0x14000f6ef  jnz     short loc_14000F71D
0x14000f6f1  cmp     byte ptr [rax+1Dh], 0
0x14000f6f5  jnz     short loc_14000F71D
0x14000f6f7  mov     rcx, [rax]
0x14000f6fa  mov     rdx, rax
0x14000f6fd  call    wil_details_EvaluateFeatureDependencies_GetCachedFeatureEnabledState
0x14000f702  test    edi, edi
0x14000f704  jz      short loc_14000F711
0x14000f706  test    al, 1
0x14000f708  jz      short loc_14000F711
0x14000f70a  mov     edi, 1
0x14000f70f  jmp     short loc_14000F713
0x14000f711  xor     edi, edi
0x14000f713  add     rsi, 8
0x14000f717  test    edi, edi
0x14000f719  jnz     short loc_14000F6E3
0x14000f71b  jmp     short loc_14000F734
0x14000f71d  test    edi, edi
0x14000f71f  jz      short loc_14000F732
0x14000f721  cmp     byte ptr [rax+1Fh], 0
0x14000f725  jz      short loc_14000F732
0x14000f727  mov     edi, 1
0x14000f72c  add     rsi, 8
0x14000f730  jmp     short loc_14000F6E3
0x14000f732  xor     edi, edi
0x14000f734  mov     ecx, ebx
0x14000f736  mov     eax, ebx
0x14000f738  and     ecx, 0FFFFFFFEh
0x14000f73b  and     eax, 1
0x14000f73e  or      ecx, edi
0x14000f740  mov     edx, ecx
0x14000f742  and     edx, 0FFFFFFCFh
0x14000f745  cmp     eax, edi
0x14000f747  mov     eax, ebx
0x14000f749  cmovz   edx, ecx
0x14000f74c  btr     edx, 9
0x14000f750  mov     dword ptr [rsp+48h+arg_0], edx
0x14000f754  lock cmpxchg [rbp+0], edx
0x14000f759  jz      short loc_14000F75F
0x14000f75b  mov     ebx, eax
0x14000f75d  jmp     short loc_14000F734
0x14000f75f  mov     rax, [rsp+48h+arg_0]
0x14000f764  add     rsp, 28h
0x14000f768  pop     rdi
0x14000f769  pop     rsi
0x14000f76a  pop     rbp
0x14000f76b  pop     rbx
0x14000f76c  retn
```
