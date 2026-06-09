# wil_details_EvaluateFeatureDependencies_UpdateFeatureDesiredStates

- ea: `0x140011eac`
- end: `0x140011f38`
- name: `wil_details_EvaluateFeatureDependencies_UpdateFeatureDesiredStates`
- size: `140`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x140011d1c`

## callees

- `0x140003964`
- `0x140011eac`

## pseudocode

```c
__int64 *wil_details_EvaluateFeatureDependencies_UpdateFeatureDesiredStates()
{
  __int64 *result; // rax
  __int64 *v1; // rdx
  int v2; // r9d
  unsigned int v3; // r8d
  BOOL v4; // eax

  result = wil_details_FeatureDescriptors_SkipPadding(wil_details_featureDescriptors_a);
  v1 = result;
  if ( result )
  {
    v2 = 0;
    do
    {
      v3 = *(_DWORD *)*v1;
      if ( (v3 & 0x200) != 0 )
      {
        if ( (v3 & 0x180) != 0 )
          v4 = (*(_DWORD *)*v1 & 0x180) == 256;
        else
          v4 = *((_BYTE *)v1 + 31) != 0;
        _InterlockedXor((volatile signed __int32 *)*v1, v2 & 0xFFFFFFBF | ((v4 ^ (v3 >> 6) & 1) << 6));
      }
      result = wil_details_FeatureDescriptors_SkipPadding(v1 + 7);
      v1 = result;
    }
    while ( result );
  }
  return result;
}

```

## disassembly

```asm
0x140011eac  sub     rsp, 28h
0x140011eb0  lea     rcx, wil_details_featureDescriptors_a
0x140011eb7  mov     [rsp+28h+arg_0], 0
0x140011ec0  call    wil_details_FeatureDescriptors_SkipPadding
0x140011ec5  mov     rdx, rax
0x140011ec8  test    rax, rax
0x140011ecb  jz      short loc_140011F32
0x140011ecd  mov     r9d, dword ptr [rsp+28h+arg_0]
0x140011ed2  mov     rcx, [rdx]
0x140011ed5  mov     r8d, [rcx]
0x140011ed8  bt      r8d, 9
0x140011edd  jnb     short loc_140011F21
0x140011edf  mov     ecx, r8d
0x140011ee2  and     ecx, 180h
0x140011ee8  jnz     short loc_140011EF4
0x140011eea  xor     eax, eax
0x140011eec  cmp     [rdx+1Fh], al
0x140011eef  setnz   al
0x140011ef2  jmp     short loc_140011EFF
0x140011ef4  xor     eax, eax
0x140011ef6  cmp     ecx, 100h
0x140011efc  setz    al
0x140011eff  shr     r8d, 6
0x140011f03  and     r8d, 1
0x140011f07  xor     r8d, eax
0x140011f0a  mov     eax, r9d
0x140011f0d  shl     r8d, 6
0x140011f11  and     eax, 0FFFFFFBFh
0x140011f14  mov     r9d, r8d
0x140011f17  or      r9d, eax
0x140011f1a  mov     rax, [rdx]
0x140011f1d  lock xor [rax], r9d
0x140011f21  lea     rcx, [rdx+38h]
0x140011f25  call    wil_details_FeatureDescriptors_SkipPadding
0x140011f2a  mov     rdx, rax
0x140011f2d  test    rax, rax
0x140011f30  jnz     short loc_140011ED2
0x140011f32  add     rsp, 28h
0x140011f36  retn
```
