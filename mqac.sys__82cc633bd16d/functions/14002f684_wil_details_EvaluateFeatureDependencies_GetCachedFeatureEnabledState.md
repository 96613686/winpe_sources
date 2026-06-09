# wil_details_EvaluateFeatureDependencies_GetCachedFeatureEnabledState

- ea: `0x14002f684`
- end: `0x14002f6b7`
- name: `wil_details_EvaluateFeatureDependencies_GetCachedFeatureEnabledState`
- size: `51`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x14002f5cc`
- `0x14002f6c0`

## callees

- `0x14002f684`
- `0x14002f6c0`

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
0x14002f684  sub     rsp, 28h
0x14002f688  mov     eax, [rcx]
0x14002f68a  mov     [rsp+28h+arg_0], 0
0x14002f693  mov     dword ptr [rsp+28h+arg_0], eax
0x14002f697  bt      eax, 9
0x14002f69b  jb      short loc_14002F6A4
0x14002f69d  mov     rax, [rsp+28h+arg_0]
0x14002f6a2  jmp     short loc_14002F6B1
0x14002f6a4  mov     r8, rdx
0x14002f6a7  mov     rdx, [rsp+28h+arg_0]
0x14002f6ac  call    wil_details_EvaluateFeatureDependencies_ReevaluateCachedFeatureEnabledState
0x14002f6b1  add     rsp, 28h
0x14002f6b5  retn
```
