# wil_details_EvaluateFeatureDependencies_UpdateFeatureDesiredStates

- ea: `0x140011e54`
- end: `0x140011ee0`
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
- `0x140011e54`

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
0x140011e54  sub     rsp, 28h
0x140011e58  lea     rcx, wil_details_featureDescriptors_a
0x140011e5f  mov     [rsp+28h+arg_0], 0
0x140011e68  call    wil_details_FeatureDescriptors_SkipPadding
0x140011e6d  mov     rdx, rax
0x140011e70  test    rax, rax
0x140011e73  jz      short loc_140011EDA
0x140011e75  mov     r9d, dword ptr [rsp+28h+arg_0]
0x140011e7a  mov     rcx, [rdx]
0x140011e7d  mov     r8d, [rcx]
0x140011e80  bt      r8d, 9
0x140011e85  jnb     short loc_140011EC9
0x140011e87  mov     ecx, r8d
0x140011e8a  and     ecx, 180h
0x140011e90  jnz     short loc_140011E9C
0x140011e92  xor     eax, eax
0x140011e94  cmp     [rdx+1Fh], al
0x140011e97  setnz   al
0x140011e9a  jmp     short loc_140011EA7
0x140011e9c  xor     eax, eax
0x140011e9e  cmp     ecx, 100h
0x140011ea4  setz    al
0x140011ea7  shr     r8d, 6
0x140011eab  and     r8d, 1
0x140011eaf  xor     r8d, eax
0x140011eb2  mov     eax, r9d
0x140011eb5  shl     r8d, 6
0x140011eb9  and     eax, 0FFFFFFBFh
0x140011ebc  mov     r9d, r8d
0x140011ebf  or      r9d, eax
0x140011ec2  mov     rax, [rdx]
0x140011ec5  lock xor [rax], r9d
0x140011ec9  lea     rcx, [rdx+38h]
0x140011ecd  call    wil_details_FeatureDescriptors_SkipPadding
0x140011ed2  mov     rdx, rax
0x140011ed5  test    rax, rax
0x140011ed8  jnz     short loc_140011E7A
0x140011eda  add     rsp, 28h
0x140011ede  retn
```
