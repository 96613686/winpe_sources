# wil_details_EvaluateFeatureDependencies_UpdateFeatureDesiredStates

- ea: `0x140044ed0`
- end: `0x140044f5c`
- name: `wil_details_EvaluateFeatureDependencies_UpdateFeatureDesiredStates`
- size: `140`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x140044d40`

## callees

- `0x14002d2b0`
- `0x140044ed0`

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
0x140044ed0  sub     rsp, 28h
0x140044ed4  lea     rcx, wil_details_featureDescriptors_a
0x140044edb  mov     [rsp+28h+arg_0], 0
0x140044ee4  call    wil_details_FeatureDescriptors_SkipPadding
0x140044ee9  mov     rdx, rax
0x140044eec  test    rax, rax
0x140044eef  jz      short loc_140044F56
0x140044ef1  mov     r9d, dword ptr [rsp+28h+arg_0]
0x140044ef6  mov     rcx, [rdx]
0x140044ef9  mov     r8d, [rcx]
0x140044efc  bt      r8d, 9
0x140044f01  jnb     short loc_140044F45
0x140044f03  mov     ecx, r8d
0x140044f06  and     ecx, 180h
0x140044f0c  jnz     short loc_140044F18
0x140044f0e  xor     eax, eax
0x140044f10  cmp     [rdx+1Fh], al
0x140044f13  setnz   al
0x140044f16  jmp     short loc_140044F23
0x140044f18  xor     eax, eax
0x140044f1a  cmp     ecx, 100h
0x140044f20  setz    al
0x140044f23  shr     r8d, 6
0x140044f27  and     r8d, 1
0x140044f2b  xor     r8d, eax
0x140044f2e  mov     eax, r9d
0x140044f31  shl     r8d, 6
0x140044f35  and     eax, 0FFFFFFBFh
0x140044f38  mov     r9d, r8d
0x140044f3b  or      r9d, eax
0x140044f3e  mov     rax, [rdx]
0x140044f41  lock xor [rax], r9d
0x140044f45  lea     rcx, [rdx+38h]
0x140044f49  call    wil_details_FeatureDescriptors_SkipPadding
0x140044f4e  mov     rdx, rax
0x140044f51  test    rax, rax
0x140044f54  jnz     short loc_140044EF6
0x140044f56  add     rsp, 28h
0x140044f5a  retn
```
