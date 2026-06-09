# wil_details_EvaluateFeatureDependencies_UpdateFeatureDesiredStates

- ea: `0x140016abc`
- end: `0x140016b48`
- name: `wil_details_EvaluateFeatureDependencies_UpdateFeatureDesiredStates`
- size: `140`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x14001692c`

## callees

- `0x1400031ac`
- `0x140016abc`

## pseudocode

```c
__int64 wil_details_EvaluateFeatureDependencies_UpdateFeatureDesiredStates()
{
  __int64 result; // rax
  volatile signed __int32 **v1; // rdx
  int v2; // r9d
  volatile unsigned __int32 v3; // r8d
  BOOL v4; // eax

  result = wil_details_FeatureDescriptors_SkipPadding(wil_details_featureDescriptors_a);
  v1 = (volatile signed __int32 **)result;
  if ( result )
  {
    v2 = 0;
    do
    {
      v3 = **v1;
      if ( (v3 & 0x200) != 0 )
      {
        if ( (v3 & 0x180) != 0 )
          v4 = (**v1 & 0x180) == 256;
        else
          v4 = *((_BYTE *)v1 + 31) != 0;
        _InterlockedXor(*v1, v2 & 0xFFFFFFBF | ((v4 ^ (v3 >> 6) & 1) << 6));
      }
      result = wil_details_FeatureDescriptors_SkipPadding(v1 + 7);
      v1 = (volatile signed __int32 **)result;
    }
    while ( result );
  }
  return result;
}

```

## disassembly

```asm
0x140016abc  sub     rsp, 28h
0x140016ac0  lea     rcx, wil_details_featureDescriptors_a
0x140016ac7  mov     [rsp+28h+arg_0], 0
0x140016ad0  call    wil_details_FeatureDescriptors_SkipPadding
0x140016ad5  mov     rdx, rax
0x140016ad8  test    rax, rax
0x140016adb  jz      short loc_140016B42
0x140016add  mov     r9d, dword ptr [rsp+28h+arg_0]
0x140016ae2  mov     rcx, [rdx]
0x140016ae5  mov     r8d, [rcx]
0x140016ae8  bt      r8d, 9
0x140016aed  jnb     short loc_140016B31
0x140016aef  mov     ecx, r8d
0x140016af2  and     ecx, 180h
0x140016af8  jnz     short loc_140016B04
0x140016afa  xor     eax, eax
0x140016afc  cmp     [rdx+1Fh], al
0x140016aff  setnz   al
0x140016b02  jmp     short loc_140016B0F
0x140016b04  xor     eax, eax
0x140016b06  cmp     ecx, 100h
0x140016b0c  setz    al
0x140016b0f  shr     r8d, 6
0x140016b13  and     r8d, 1
0x140016b17  xor     r8d, eax
0x140016b1a  mov     eax, r9d
0x140016b1d  shl     r8d, 6
0x140016b21  and     eax, 0FFFFFFBFh
0x140016b24  mov     r9d, r8d
0x140016b27  or      r9d, eax
0x140016b2a  mov     rax, [rdx]
0x140016b2d  lock xor [rax], r9d
0x140016b31  lea     rcx, [rdx+38h]
0x140016b35  call    wil_details_FeatureDescriptors_SkipPadding
0x140016b3a  mov     rdx, rax
0x140016b3d  test    rax, rax
0x140016b40  jnz     short loc_140016AE2
0x140016b42  add     rsp, 28h
0x140016b46  retn
```
