# wil_details_EvaluateFeatureDependencies_GetCachedFeatureEnabledState

- ea: `0x1400375cc`
- end: `0x1400375ff`
- name: `wil_details_EvaluateFeatureDependencies_GetCachedFeatureEnabledState`
- size: `51`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x14003758c`
- `0x140037608`

## callees

- `0x1400375cc`
- `0x140037608`

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
0x1400375cc  sub     rsp, 28h
0x1400375d0  mov     eax, [rcx]
0x1400375d2  mov     [rsp+28h+arg_0], 0
0x1400375db  mov     dword ptr [rsp+28h+arg_0], eax
0x1400375df  bt      eax, 9
0x1400375e3  jb      short loc_1400375EC
0x1400375e5  mov     rax, [rsp+28h+arg_0]
0x1400375ea  jmp     short loc_1400375F9
0x1400375ec  mov     r8, rdx
0x1400375ef  mov     rdx, [rsp+28h+arg_0]
0x1400375f4  call    wil_details_EvaluateFeatureDependencies_ReevaluateCachedFeatureEnabledState
0x1400375f9  add     rsp, 28h
0x1400375fd  retn
```
