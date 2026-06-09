# wil_details_UpdateFeatureConfiguredStates

- ea: `0x18005f8b4`
- end: `0x18005f964`
- name: `wil_details_UpdateFeatureConfiguredStates`
- size: `176`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, installer_update`

## callers

- `0x18005f790`

## callees

- `0x180011f38`
- `0x18002bef0`
- `0x18005f5d8`
- `0x18005f8b4`

## import_xrefs

- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x18005f904`
- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x18005f904`

## pseudocode

```c
__int64 wil_details_UpdateFeatureConfiguredStates()
{
  __int64 **i; // rcx
  __int64 v1; // rcx
  unsigned int v2; // eax
  __int64 result; // rax
  volatile signed __int32 **v4; // rbx
  __int64 v5; // [rsp+20h] [rbp-38h] BYREF
  __int64 v6; // [rsp+28h] [rbp-30h] BYREF
  __int64 v7; // [rsp+30h] [rbp-28h] BYREF
  int v8; // [rsp+38h] [rbp-20h]

  for ( i = wil_details_featureDescriptors_a; ; i = (__int64 **)(v4 + 7) )
  {
    result = wil_details_FeatureDescriptors_SkipPadding(i);
    v4 = (volatile signed __int32 **)result;
    if ( !result )
      break;
    if ( !*(_BYTE *)(result + 29) && !*(_BYTE *)(result + 30) && !*(_BYTE *)(result + 28) )
    {
      v1 = *(unsigned int *)(result + 24);
      v7 = 0;
      v8 = 0;
      v6 = 0;
      v2 = RtlQueryFeatureConfiguration(v1, 1, &v6, &v7);
      v5 = 0;
      wil_details_BuildFeatureStateCacheFromQueryResults(v2, &v7, &v5);
      _InterlockedXor(*v4, ((unsigned __int16)v5 ^ (unsigned __int16)**v4) & 0xF80);
    }
  }
  return result;
}

```

## disassembly

```asm
0x18005f8b4  push    rbx
0x18005f8b6  sub     rsp, 50h
0x18005f8ba  mov     rax, cs:__security_cookie
0x18005f8c1  xor     rax, rsp
0x18005f8c4  mov     [rsp+58h+var_18], rax
0x18005f8c9  lea     rcx, wil_details_featureDescriptors_a
0x18005f8d0  jmp     short loc_18005F943
0x18005f8d2  cmp     byte ptr [rbx+1Dh], 0
0x18005f8d6  jnz     short loc_18005F93F
0x18005f8d8  cmp     byte ptr [rbx+1Eh], 0
0x18005f8dc  jnz     short loc_18005F93F
0x18005f8de  cmp     byte ptr [rbx+1Ch], 0
0x18005f8e2  jnz     short loc_18005F93F
0x18005f8e4  mov     ecx, [rbx+18h]
0x18005f8e7  lea     r9, [rsp+58h+var_28]
0x18005f8ec  xor     eax, eax
0x18005f8ee  lea     r8, [rsp+58h+var_30]
0x18005f8f3  mov     [rsp+58h+var_28], rax
0x18005f8f8  mov     [rsp+58h+var_20], eax
0x18005f8fc  mov     [rsp+58h+var_30], rax
0x18005f901  lea     edx, [rax+1]
0x18005f904  call    cs:__imp_RtlQueryFeatureConfiguration
0x18005f90b  nop     dword ptr [rax+rax+00h]
0x18005f910  lea     r8, [rsp+58h+var_38]
0x18005f915  mov     [rsp+58h+var_38], 0
0x18005f91e  mov     ecx, eax
0x18005f920  lea     rdx, [rsp+58h+var_28]
0x18005f925  call    wil_details_BuildFeatureStateCacheFromQueryResults
0x18005f92a  mov     rcx, [rbx]
0x18005f92d  mov     edx, [rcx]
0x18005f92f  xor     edx, dword ptr [rsp+58h+var_38]
0x18005f933  mov     rax, [rbx]
0x18005f936  and     edx, 0F80h
0x18005f93c  lock xor [rax], edx
0x18005f93f  lea     rcx, [rbx+38h]
0x18005f943  call    wil_details_FeatureDescriptors_SkipPadding
0x18005f948  mov     rbx, rax
0x18005f94b  test    rax, rax
0x18005f94e  jnz     short loc_18005F8D2
0x18005f950  mov     rcx, [rsp+58h+var_18]
0x18005f955  xor     rcx, rsp; StackCookie
0x18005f958  call    __security_check_cookie
0x18005f95d  add     rsp, 50h
0x18005f961  pop     rbx
0x18005f962  retn
```
