# wil_details_EvaluateFeatureDependencies_UpdateFeatureDesiredStates

- ea: `0x140016a64`
- end: `0x140016af0`
- name: `wil_details_EvaluateFeatureDependencies_UpdateFeatureDesiredStates`
- size: `140`
- prototype: `__int64 *()`
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x14001692c`

## callees

- `0x1400033dc`
- `0x140016a64`

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
0x140016a64  sub     rsp, 28h
0x140016a68  lea     rcx, wil_details_featureDescriptors_a
0x140016a6f  mov     [rsp+28h+arg_0], 0
0x140016a78  call    wil_details_FeatureDescriptors_SkipPadding
0x140016a7d  mov     rdx, rax
0x140016a80  test    rax, rax
0x140016a83  jz      short loc_140016AEA
0x140016a85  mov     r9d, dword ptr [rsp+28h+arg_0]
0x140016a8a  mov     rcx, [rdx]
0x140016a8d  mov     r8d, [rcx]
0x140016a90  bt      r8d, 9
0x140016a95  jnb     short loc_140016AD9
0x140016a97  mov     ecx, r8d
0x140016a9a  and     ecx, 180h
0x140016aa0  jnz     short loc_140016AAC
0x140016aa2  xor     eax, eax
0x140016aa4  cmp     [rdx+1Fh], al
0x140016aa7  setnz   al
0x140016aaa  jmp     short loc_140016AB7
0x140016aac  xor     eax, eax
0x140016aae  cmp     ecx, 100h
0x140016ab4  setz    al
0x140016ab7  shr     r8d, 6
0x140016abb  and     r8d, 1
0x140016abf  xor     r8d, eax
0x140016ac2  mov     eax, r9d
0x140016ac5  shl     r8d, 6
0x140016ac9  and     eax, 0FFFFFFBFh
0x140016acc  mov     r9d, r8d
0x140016acf  or      r9d, eax
0x140016ad2  mov     rax, [rdx]
0x140016ad5  lock xor [rax], r9d
0x140016ad9  lea     rcx, [rdx+38h]
0x140016add  call    wil_details_FeatureDescriptors_SkipPadding
0x140016ae2  mov     rdx, rax
0x140016ae5  test    rax, rax
0x140016ae8  jnz     short loc_140016A8A
0x140016aea  add     rsp, 28h
0x140016aee  retn
```
