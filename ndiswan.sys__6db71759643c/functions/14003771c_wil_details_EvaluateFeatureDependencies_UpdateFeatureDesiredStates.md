# wil_details_EvaluateFeatureDependencies_UpdateFeatureDesiredStates

- ea: `0x14003771c`
- end: `0x1400377a8`
- name: `wil_details_EvaluateFeatureDependencies_UpdateFeatureDesiredStates`
- size: `140`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x14003758c`

## callees

- `0x14000b5a4`
- `0x14003771c`

## pseudocode

```c
__int64 *wil_details_EvaluateFeatureDependencies_UpdateFeatureDesiredStates()
{
  __int64 *result; // rax
  __int64 *v1; // rdx
  int v2; // r9d
  unsigned int v3; // r8d
  BOOL v4; // eax

  result = wil_details_FeatureDescriptors_SkipPadding((__int64 *)wil_details_featureDescriptors_a);
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
0x14003771c  sub     rsp, 28h
0x140037720  lea     rcx, wil_details_featureDescriptors_a
0x140037727  mov     [rsp+28h+arg_0], 0
0x140037730  call    wil_details_FeatureDescriptors_SkipPadding
0x140037735  mov     rdx, rax
0x140037738  test    rax, rax
0x14003773b  jz      short loc_1400377A2
0x14003773d  mov     r9d, dword ptr [rsp+28h+arg_0]
0x140037742  mov     rcx, [rdx]
0x140037745  mov     r8d, [rcx]
0x140037748  bt      r8d, 9
0x14003774d  jnb     short loc_140037791
0x14003774f  mov     ecx, r8d
0x140037752  and     ecx, 180h
0x140037758  jnz     short loc_140037764
0x14003775a  xor     eax, eax
0x14003775c  cmp     [rdx+1Fh], al
0x14003775f  setnz   al
0x140037762  jmp     short loc_14003776F
0x140037764  xor     eax, eax
0x140037766  cmp     ecx, 100h
0x14003776c  setz    al
0x14003776f  shr     r8d, 6
0x140037773  and     r8d, 1
0x140037777  xor     r8d, eax
0x14003777a  mov     eax, r9d
0x14003777d  shl     r8d, 6
0x140037781  and     eax, 0FFFFFFBFh
0x140037784  mov     r9d, r8d
0x140037787  or      r9d, eax
0x14003778a  mov     rax, [rdx]
0x14003778d  lock xor [rax], r9d
0x140037791  lea     rcx, [rdx+38h]
0x140037795  call    wil_details_FeatureDescriptors_SkipPadding
0x14003779a  mov     rdx, rax
0x14003779d  test    rax, rax
0x1400377a0  jnz     short loc_140037742
0x1400377a2  add     rsp, 28h
0x1400377a6  retn
```
