# wil_details_EvaluateFeatureDependencies_UpdateFeatureDesiredStates

- ea: `0x14000e930`
- end: `0x14000e9bc`
- name: `wil_details_EvaluateFeatureDependencies_UpdateFeatureDesiredStates`
- size: `140`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x14000e7a0`

## callees

- `0x140004c24`
- `0x14000e930`

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
0x14000e930  sub     rsp, 28h
0x14000e934  lea     rcx, wil_details_featureDescriptors_a
0x14000e93b  mov     [rsp+28h+arg_0], 0
0x14000e944  call    wil_details_FeatureDescriptors_SkipPadding
0x14000e949  mov     rdx, rax
0x14000e94c  test    rax, rax
0x14000e94f  jz      short loc_14000E9B6
0x14000e951  mov     r9d, dword ptr [rsp+28h+arg_0]
0x14000e956  mov     rcx, [rdx]
0x14000e959  mov     r8d, [rcx]
0x14000e95c  bt      r8d, 9
0x14000e961  jnb     short loc_14000E9A5
0x14000e963  mov     ecx, r8d
0x14000e966  and     ecx, 180h
0x14000e96c  jnz     short loc_14000E978
0x14000e96e  xor     eax, eax
0x14000e970  cmp     [rdx+1Fh], al
0x14000e973  setnz   al
0x14000e976  jmp     short loc_14000E983
0x14000e978  xor     eax, eax
0x14000e97a  cmp     ecx, 100h
0x14000e980  setz    al
0x14000e983  shr     r8d, 6
0x14000e987  and     r8d, 1
0x14000e98b  xor     r8d, eax
0x14000e98e  mov     eax, r9d
0x14000e991  shl     r8d, 6
0x14000e995  and     eax, 0FFFFFFBFh
0x14000e998  mov     r9d, r8d
0x14000e99b  or      r9d, eax
0x14000e99e  mov     rax, [rdx]
0x14000e9a1  lock xor [rax], r9d
0x14000e9a5  lea     rcx, [rdx+38h]
0x14000e9a9  call    wil_details_FeatureDescriptors_SkipPadding
0x14000e9ae  mov     rdx, rax
0x14000e9b1  test    rax, rax
0x14000e9b4  jnz     short loc_14000E956
0x14000e9b6  add     rsp, 28h
0x14000e9ba  retn
```
