# wil_details_EvaluateFeatureDependencies_UpdateFeatureDesiredStates

- ea: `0x180039374`
- end: `0x180039400`
- name: `wil_details_EvaluateFeatureDependencies_UpdateFeatureDesiredStates`
- size: `140`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x18003923c`

## callees

- `0x18001da84`
- `0x180039374`

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
0x180039374  sub     rsp, 28h
0x180039378  lea     rcx, wil_details_featureDescriptors_a
0x18003937f  mov     [rsp+28h+arg_0], 0
0x180039388  call    wil_details_FeatureDescriptors_SkipPadding
0x18003938d  mov     rdx, rax
0x180039390  test    rax, rax
0x180039393  jz      short loc_1800393FA
0x180039395  mov     r9d, dword ptr [rsp+28h+arg_0]
0x18003939a  mov     rcx, [rdx]
0x18003939d  mov     r8d, [rcx]
0x1800393a0  bt      r8d, 9
0x1800393a5  jnb     short loc_1800393E9
0x1800393a7  mov     ecx, r8d
0x1800393aa  and     ecx, 180h
0x1800393b0  jnz     short loc_1800393BC
0x1800393b2  xor     eax, eax
0x1800393b4  cmp     [rdx+1Fh], al
0x1800393b7  setnz   al
0x1800393ba  jmp     short loc_1800393C7
0x1800393bc  xor     eax, eax
0x1800393be  cmp     ecx, 100h
0x1800393c4  setz    al
0x1800393c7  shr     r8d, 6
0x1800393cb  and     r8d, 1
0x1800393cf  xor     r8d, eax
0x1800393d2  mov     eax, r9d
0x1800393d5  shl     r8d, 6
0x1800393d9  and     eax, 0FFFFFFBFh
0x1800393dc  mov     r9d, r8d
0x1800393df  or      r9d, eax
0x1800393e2  mov     rax, [rdx]
0x1800393e5  lock xor [rax], r9d
0x1800393e9  lea     rcx, [rdx+38h]
0x1800393ed  call    wil_details_FeatureDescriptors_SkipPadding
0x1800393f2  mov     rdx, rax
0x1800393f5  test    rax, rax
0x1800393f8  jnz     short loc_18003939A
0x1800393fa  add     rsp, 28h
0x1800393fe  retn
```
