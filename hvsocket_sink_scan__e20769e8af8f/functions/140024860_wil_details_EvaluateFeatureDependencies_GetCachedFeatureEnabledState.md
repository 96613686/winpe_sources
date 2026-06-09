# wil_details_EvaluateFeatureDependencies_GetCachedFeatureEnabledState

- ea: `0x140024860`
- end: `0x140024931`
- name: `wil_details_EvaluateFeatureDependencies_GetCachedFeatureEnabledState`
- size: `209`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140024770`
- `0x140024860`

## callees

- `0x140024860`

## pseudocode

```c
__int64 __fastcall wil_details_EvaluateFeatureDependencies_GetCachedFeatureEnabledState(
        volatile signed __int32 *a1,
        __int64 a2)
{
  unsigned __int32 v2; // esi
  int v4; // ebx
  __int64 *v5; // rdi
  __int64 v6; // rax
  unsigned __int32 v7; // eax
  unsigned int v8; // r8d
  __int64 v10; // [rsp+50h] [rbp+8h]

  v2 = *a1;
  v10 = *(unsigned int *)a1;
  if ( (*a1 & 0x200) != 0 )
  {
    HIDWORD(v10) = 0;
    v4 = (v2 >> 6) & 1;
    if ( v4 )
    {
      v5 = *(__int64 **)(a2 + 32);
      if ( v5 )
      {
        while ( 1 )
        {
          v6 = *v5;
          if ( !*v5 )
            break;
          if ( *(_BYTE *)(v6 + 30) || *(_BYTE *)(v6 + 29) )
          {
            if ( !*(_BYTE *)(v6 + 31) )
            {
              v4 = 0;
              goto LABEL_12;
            }
            v4 = 1;
            ++v5;
          }
          else
          {
            v4 = (wil_details_EvaluateFeatureDependencies_GetCachedFeatureEnabledState(*(_QWORD *)v6, *v5++) & 1) != 0;
            if ( !v4 )
              goto LABEL_12;
          }
        }
      }
    }
    do
    {
LABEL_12:
      v7 = v2;
      v8 = v4 & 0xFFFFFFCF | v2 & 0xFFFFFFCE;
      if ( (v2 & 1) == v4 )
        v8 = v4 | v2 & 0xFFFFFFFE;
      LODWORD(v10) = v8 & 0xFFFFFDFF;
      v2 = _InterlockedCompareExchange(a1, v8 & 0xFFFFFDFF, v2);
    }
    while ( v7 != v2 );
  }
  return v10;
}

```

## disassembly

```asm
0x140024860  push    rbx
0x140024862  push    rsi
0x140024863  push    rdi
0x140024864  push    r14
0x140024866  sub     rsp, 28h
0x14002486a  mov     esi, [rcx]
0x14002486c  mov     r14, rcx
0x14002486f  mov     [rsp+48h+arg_0], 0
0x140024878  mov     dword ptr [rsp+48h+arg_0], esi
0x14002487c  bt      esi, 9
0x140024880  jnb     loc_140024921
0x140024886  mov     ebx, esi
0x140024888  mov     [rsp+48h+arg_0], 0
0x140024891  shr     ebx, 6
0x140024894  and     ebx, 1
0x140024897  jz      short loc_1400248F3
0x140024899  mov     rdi, [rdx+20h]
0x14002489d  test    rdi, rdi
0x1400248a0  jz      short loc_1400248F3
0x1400248a2  mov     rax, [rdi]
0x1400248a5  test    rax, rax
0x1400248a8  jz      short loc_1400248F3
0x1400248aa  cmp     byte ptr [rax+1Eh], 0
0x1400248ae  jnz     short loc_1400248DC
0x1400248b0  cmp     byte ptr [rax+1Dh], 0
0x1400248b4  jnz     short loc_1400248DC
0x1400248b6  mov     rcx, [rax]
0x1400248b9  mov     rdx, rax
0x1400248bc  call    wil_details_EvaluateFeatureDependencies_GetCachedFeatureEnabledState
0x1400248c1  test    ebx, ebx
0x1400248c3  jz      short loc_1400248D0
0x1400248c5  test    al, 1
0x1400248c7  jz      short loc_1400248D0
0x1400248c9  mov     ebx, 1
0x1400248ce  jmp     short loc_1400248D2
0x1400248d0  xor     ebx, ebx
0x1400248d2  add     rdi, 8
0x1400248d6  test    ebx, ebx
0x1400248d8  jnz     short loc_1400248A2
0x1400248da  jmp     short loc_1400248F3
0x1400248dc  test    ebx, ebx
0x1400248de  jz      short loc_1400248F1
0x1400248e0  cmp     byte ptr [rax+1Fh], 0
0x1400248e4  jz      short loc_1400248F1
0x1400248e6  mov     ebx, 1
0x1400248eb  add     rdi, 8
0x1400248ef  jmp     short loc_1400248A2
0x1400248f1  xor     ebx, ebx
0x1400248f3  mov     edx, esi
0x1400248f5  mov     ecx, esi
0x1400248f7  and     edx, 0FFFFFFFEh
0x1400248fa  and     ecx, 1
0x1400248fd  or      edx, ebx
0x1400248ff  mov     eax, esi
0x140024901  mov     r8d, edx
0x140024904  and     r8d, 0FFFFFFCFh
0x140024908  cmp     ecx, ebx
0x14002490a  cmovz   r8d, edx
0x14002490e  btr     r8d, 9
0x140024913  mov     dword ptr [rsp+48h+arg_0], r8d
0x140024918  lock cmpxchg [r14], r8d
0x14002491d  mov     esi, eax
0x14002491f  jnz     short loc_1400248F3
0x140024921  mov     rax, [rsp+48h+arg_0]
0x140024926  add     rsp, 28h
0x14002492a  pop     r14
0x14002492c  pop     rdi
0x14002492d  pop     rsi
0x14002492e  pop     rbx
0x14002492f  retn
```
