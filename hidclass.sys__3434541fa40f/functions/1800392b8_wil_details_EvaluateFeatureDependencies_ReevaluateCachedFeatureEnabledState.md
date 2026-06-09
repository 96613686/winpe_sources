# wil_details_EvaluateFeatureDependencies_ReevaluateCachedFeatureEnabledState

- ea: `0x1800392b8`
- end: `0x18003936e`
- name: `wil_details_EvaluateFeatureDependencies_ReevaluateCachedFeatureEnabledState`
- size: `182`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18003927c`

## callees

- `0x18003927c`
- `0x1800392b8`

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
0x1800392b8  push    rbx
0x1800392ba  push    rbp
0x1800392bb  push    rsi
0x1800392bc  push    rdi
0x1800392bd  sub     rsp, 28h
0x1800392c1  mov     edi, edx
0x1800392c3  mov     [rsp+48h+arg_0], 0
0x1800392cc  shr     edi, 6
0x1800392cf  mov     rbx, rdx
0x1800392d2  mov     rbp, rcx
0x1800392d5  and     edi, 1
0x1800392d8  jz      short loc_180039334
0x1800392da  mov     rsi, [r8+20h]
0x1800392de  test    rsi, rsi
0x1800392e1  jz      short loc_180039334
0x1800392e3  mov     rax, [rsi]
0x1800392e6  test    rax, rax
0x1800392e9  jz      short loc_180039334
0x1800392eb  cmp     byte ptr [rax+1Eh], 0
0x1800392ef  jnz     short loc_18003931D
0x1800392f1  cmp     byte ptr [rax+1Dh], 0
0x1800392f5  jnz     short loc_18003931D
0x1800392f7  mov     rcx, [rax]
0x1800392fa  mov     rdx, rax
0x1800392fd  call    wil_details_EvaluateFeatureDependencies_GetCachedFeatureEnabledState
0x180039302  test    edi, edi
0x180039304  jz      short loc_180039311
0x180039306  test    al, 1
0x180039308  jz      short loc_180039311
0x18003930a  mov     edi, 1
0x18003930f  jmp     short loc_180039313
0x180039311  xor     edi, edi
0x180039313  add     rsi, 8
0x180039317  test    edi, edi
0x180039319  jnz     short loc_1800392E3
0x18003931b  jmp     short loc_180039334
0x18003931d  test    edi, edi
0x18003931f  jz      short loc_180039332
0x180039321  cmp     byte ptr [rax+1Fh], 0
0x180039325  jz      short loc_180039332
0x180039327  mov     edi, 1
0x18003932c  add     rsi, 8
0x180039330  jmp     short loc_1800392E3
0x180039332  xor     edi, edi
0x180039334  mov     ecx, ebx
0x180039336  mov     eax, ebx
0x180039338  and     ecx, 0FFFFFFFEh
0x18003933b  and     eax, 1
0x18003933e  or      ecx, edi
0x180039340  mov     edx, ecx
0x180039342  and     edx, 0FFFFFFCFh
0x180039345  cmp     eax, edi
0x180039347  mov     eax, ebx
0x180039349  cmovz   edx, ecx
0x18003934c  btr     edx, 9
0x180039350  mov     dword ptr [rsp+48h+arg_0], edx
0x180039354  lock cmpxchg [rbp+0], edx
0x180039359  jz      short loc_18003935F
0x18003935b  mov     ebx, eax
0x18003935d  jmp     short loc_180039334
0x18003935f  mov     rax, [rsp+48h+arg_0]
0x180039364  add     rsp, 28h
0x180039368  pop     rdi
0x180039369  pop     rsi
0x18003936a  pop     rbp
0x18003936b  pop     rbx
0x18003936c  retn
```
