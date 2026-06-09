# wil_details_EvaluateFeatureDependencies_GetCachedFeatureEnabledState

- ea: `0x140043220`
- end: `0x140043253`
- name: `wil_details_EvaluateFeatureDependencies_GetCachedFeatureEnabledState`
- size: `51`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140043168`
- `0x14004325c`

## callees

- `0x140043220`
- `0x14004325c`

## pseudocode

```c
__int64 __fastcall wil_details_EvaluateFeatureDependencies_GetCachedFeatureEnabledState(
        volatile signed __int32 *a1,
        __int64 a2)
{
  if ( (*a1 & 0x200) != 0 )
    return wil_details_EvaluateFeatureDependencies_ReevaluateCachedFeatureEnabledState(a1, *a1, a2);
  else
    return *(unsigned int *)a1;
}

```

## disassembly

```asm
0x140043220  sub     rsp, 28h
0x140043224  mov     eax, [rcx]
0x140043226  mov     [rsp+28h+arg_0], 0
0x14004322f  mov     dword ptr [rsp+28h+arg_0], eax
0x140043233  bt      eax, 9
0x140043237  jb      short loc_140043240
0x140043239  mov     rax, [rsp+28h+arg_0]
0x14004323e  jmp     short loc_14004324D
0x140043240  mov     r8, rdx
0x140043243  mov     rdx, [rsp+28h+arg_0]
0x140043248  call    wil_details_EvaluateFeatureDependencies_ReevaluateCachedFeatureEnabledState
0x14004324d  add     rsp, 28h
0x140043251  retn
```
