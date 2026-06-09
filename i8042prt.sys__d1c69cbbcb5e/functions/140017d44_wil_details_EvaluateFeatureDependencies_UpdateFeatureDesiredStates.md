# wil_details_EvaluateFeatureDependencies_UpdateFeatureDesiredStates

- ea: `0x140017d44`
- end: `0x140017dd0`
- name: `wil_details_EvaluateFeatureDependencies_UpdateFeatureDesiredStates`
- size: `140`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x140017c0c`

## callees

- `0x14000a128`
- `0x140017d44`

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
0x140017d44  sub     rsp, 28h
0x140017d48  lea     rcx, wil_details_featureDescriptors_a
0x140017d4f  mov     [rsp+28h+arg_0], 0
0x140017d58  call    wil_details_FeatureDescriptors_SkipPadding
0x140017d5d  mov     rdx, rax
0x140017d60  test    rax, rax
0x140017d63  jz      short loc_140017DCA
0x140017d65  mov     r9d, dword ptr [rsp+28h+arg_0]
0x140017d6a  mov     rcx, [rdx]
0x140017d6d  mov     r8d, [rcx]
0x140017d70  bt      r8d, 9
0x140017d75  jnb     short loc_140017DB9
0x140017d77  mov     ecx, r8d
0x140017d7a  and     ecx, 180h
0x140017d80  jnz     short loc_140017D8C
0x140017d82  xor     eax, eax
0x140017d84  cmp     [rdx+1Fh], al
0x140017d87  setnz   al
0x140017d8a  jmp     short loc_140017D97
0x140017d8c  xor     eax, eax
0x140017d8e  cmp     ecx, 100h
0x140017d94  setz    al
0x140017d97  shr     r8d, 6
0x140017d9b  and     r8d, 1
0x140017d9f  xor     r8d, eax
0x140017da2  mov     eax, r9d
0x140017da5  shl     r8d, 6
0x140017da9  and     eax, 0FFFFFFBFh
0x140017dac  mov     r9d, r8d
0x140017daf  or      r9d, eax
0x140017db2  mov     rax, [rdx]
0x140017db5  lock xor [rax], r9d
0x140017db9  lea     rcx, [rdx+38h]
0x140017dbd  call    wil_details_FeatureDescriptors_SkipPadding
0x140017dc2  mov     rdx, rax
0x140017dc5  test    rax, rax
0x140017dc8  jnz     short loc_140017D6A
0x140017dca  add     rsp, 28h
0x140017dce  retn
```
