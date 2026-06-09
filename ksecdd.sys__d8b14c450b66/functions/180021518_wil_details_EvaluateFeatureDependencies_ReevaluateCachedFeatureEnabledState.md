# wil_details_EvaluateFeatureDependencies_ReevaluateCachedFeatureEnabledState

- ea: `0x180021518`
- end: `0x1800215ce`
- name: `wil_details_EvaluateFeatureDependencies_ReevaluateCachedFeatureEnabledState`
- size: `182`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800214dc`

## callees

- `0x1800214dc`
- `0x180021518`

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
0x180021518  push    rbx
0x18002151a  push    rbp
0x18002151b  push    rsi
0x18002151c  push    rdi
0x18002151d  sub     rsp, 28h
0x180021521  mov     edi, edx
0x180021523  mov     [rsp+48h+arg_0], 0
0x18002152c  shr     edi, 6
0x18002152f  mov     rbx, rdx
0x180021532  mov     rbp, rcx
0x180021535  and     edi, 1
0x180021538  jz      short loc_180021594
0x18002153a  mov     rsi, [r8+20h]
0x18002153e  test    rsi, rsi
0x180021541  jz      short loc_180021594
0x180021543  mov     rax, [rsi]
0x180021546  test    rax, rax
0x180021549  jz      short loc_180021594
0x18002154b  cmp     byte ptr [rax+1Eh], 0
0x18002154f  jnz     short loc_18002157D
0x180021551  cmp     byte ptr [rax+1Dh], 0
0x180021555  jnz     short loc_18002157D
0x180021557  mov     rcx, [rax]
0x18002155a  mov     rdx, rax
0x18002155d  call    wil_details_EvaluateFeatureDependencies_GetCachedFeatureEnabledState
0x180021562  test    edi, edi
0x180021564  jz      short loc_180021571
0x180021566  test    al, 1
0x180021568  jz      short loc_180021571
0x18002156a  mov     edi, 1
0x18002156f  jmp     short loc_180021573
0x180021571  xor     edi, edi
0x180021573  add     rsi, 8
0x180021577  test    edi, edi
0x180021579  jnz     short loc_180021543
0x18002157b  jmp     short loc_180021594
0x18002157d  test    edi, edi
0x18002157f  jz      short loc_180021592
0x180021581  cmp     byte ptr [rax+1Fh], 0
0x180021585  jz      short loc_180021592
0x180021587  mov     edi, 1
0x18002158c  add     rsi, 8
0x180021590  jmp     short loc_180021543
0x180021592  xor     edi, edi
0x180021594  mov     ecx, ebx
0x180021596  mov     eax, ebx
0x180021598  and     ecx, 0FFFFFFFEh
0x18002159b  and     eax, 1
0x18002159e  or      ecx, edi
0x1800215a0  mov     edx, ecx
0x1800215a2  and     edx, 0FFFFFFCFh
0x1800215a5  cmp     eax, edi
0x1800215a7  mov     eax, ebx
0x1800215a9  cmovz   edx, ecx
0x1800215ac  btr     edx, 9
0x1800215b0  mov     dword ptr [rsp+48h+arg_0], edx
0x1800215b4  lock cmpxchg [rbp+0], edx
0x1800215b9  jz      short loc_1800215BF
0x1800215bb  mov     ebx, eax
0x1800215bd  jmp     short loc_180021594
0x1800215bf  mov     rax, [rsp+48h+arg_0]
0x1800215c4  add     rsp, 28h
0x1800215c8  pop     rdi
0x1800215c9  pop     rsi
0x1800215ca  pop     rbp
0x1800215cb  pop     rbx
0x1800215cc  retn
```
