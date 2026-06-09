# wil_details_EvaluateFeatureDependencies

- ea: `0x14000f010`
- end: `0x14000f0cf`
- name: `wil_details_EvaluateFeatureDependencies`
- size: `191`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x14000f7e0`
- `0x140011940`

## callees

- `0x1400057a0`
- `0x14000f010`
- `0x14000f67c`

## pseudocode

```c
__int64 *wil_details_EvaluateFeatureDependencies()
{
  __int64 *v0; // rdx
  int v1; // r9d
  unsigned int v2; // r8d
  BOOL v3; // eax
  __int64 *result; // rax
  __int64 i; // rbx

  v0 = wil_details_FeatureDescriptors_SkipPadding((__int64 *)&wil_details_featureDescriptors_a);
  if ( v0 )
  {
    v1 = 0;
    do
    {
      v2 = *(_DWORD *)*v0;
      if ( (v2 & 0x200) != 0 )
      {
        if ( (v2 & 0x180) != 0 )
          v3 = (*(_DWORD *)*v0 & 0x180) == 256;
        else
          v3 = *((_BYTE *)v0 + 31) != 0;
        _InterlockedXor((volatile signed __int32 *)*v0, v1 & 0xFFFFFFBF | ((v3 ^ (v2 >> 6) & 1) << 6));
      }
      v0 = wil_details_FeatureDescriptors_SkipPadding(v0 + 7);
    }
    while ( v0 );
  }
  result = wil_details_FeatureDescriptors_SkipPadding((__int64 *)&wil_details_featureDescriptors_a);
  for ( i = (__int64)result; result; i = (__int64)result )
  {
    wil_details_EvaluateFeatureDependencies_GetCachedFeatureEnabledState(*(_DWORD **)i, i);
    result = wil_details_FeatureDescriptors_SkipPadding((__int64 *)(i + 56));
  }
  return result;
}

```

## disassembly

```asm
0x14000f010  push    rbx
0x14000f012  sub     rsp, 20h
0x14000f016  lea     rcx, wil_details_featureDescriptors_a
0x14000f01d  mov     [rsp+28h+arg_0], 0
0x14000f026  call    wil_details_FeatureDescriptors_SkipPadding
0x14000f02b  mov     rdx, rax
0x14000f02e  test    rax, rax
0x14000f031  jz      short loc_14000F098
0x14000f033  mov     r9d, dword ptr [rsp+28h+arg_0]
0x14000f038  mov     rcx, [rdx]
0x14000f03b  mov     r8d, [rcx]
0x14000f03e  bt      r8d, 9
0x14000f043  jnb     short loc_14000F087
0x14000f045  mov     ecx, r8d
0x14000f048  and     ecx, 180h
0x14000f04e  jnz     short loc_14000F05A
0x14000f050  xor     eax, eax
0x14000f052  cmp     [rdx+1Fh], al
0x14000f055  setnz   al
0x14000f058  jmp     short loc_14000F065
0x14000f05a  xor     eax, eax
0x14000f05c  cmp     ecx, 100h
0x14000f062  setz    al
0x14000f065  shr     r8d, 6
0x14000f069  and     r8d, 1
0x14000f06d  xor     r8d, eax
0x14000f070  mov     eax, r9d
0x14000f073  shl     r8d, 6
0x14000f077  and     eax, 0FFFFFFBFh
0x14000f07a  mov     r9d, r8d
0x14000f07d  or      r9d, eax
0x14000f080  mov     rax, [rdx]
0x14000f083  lock xor [rax], r9d
0x14000f087  lea     rcx, [rdx+38h]
0x14000f08b  call    wil_details_FeatureDescriptors_SkipPadding
0x14000f090  mov     rdx, rax
0x14000f093  test    rax, rax
0x14000f096  jnz     short loc_14000F038
0x14000f098  lea     rcx, wil_details_featureDescriptors_a
0x14000f09f  call    wil_details_FeatureDescriptors_SkipPadding
0x14000f0a4  mov     rbx, rax
0x14000f0a7  test    rax, rax
0x14000f0aa  jz      short loc_14000F0C8
0x14000f0ac  mov     rcx, [rbx]
0x14000f0af  mov     rdx, rbx
0x14000f0b2  call    wil_details_EvaluateFeatureDependencies_GetCachedFeatureEnabledState
0x14000f0b7  lea     rcx, [rbx+38h]
0x14000f0bb  call    wil_details_FeatureDescriptors_SkipPadding
0x14000f0c0  mov     rbx, rax
0x14000f0c3  test    rax, rax
0x14000f0c6  jnz     short loc_14000F0AC
0x14000f0c8  add     rsp, 20h
0x14000f0cc  pop     rbx
0x14000f0cd  retn
```
