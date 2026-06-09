# wil_details_UpdateFeatureConfiguredStates

- ea: `0x14002f8f0`
- end: `0x14002f9a0`
- name: `wil_details_UpdateFeatureConfiguredStates`
- size: `176`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, installer_update`

## callers

- `0x14002f850`

## callees

- `0x1400118c4`
- `0x140024bb0`
- `0x14002f56c`
- `0x14002f8f0`

## import_xrefs

- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x14002f940`
- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x14002f940`

## pseudocode

```c
__int64 wil_details_UpdateFeatureConfiguredStates()
{
  __int64 *i; // rcx
  __int64 v1; // rcx
  unsigned int v2; // eax
  __int64 result; // rax
  volatile signed __int32 **v4; // rbx
  __int64 v5; // [rsp+20h] [rbp-38h] BYREF
  __int64 v6; // [rsp+28h] [rbp-30h] BYREF
  __int64 v7; // [rsp+30h] [rbp-28h] BYREF
  int v8; // [rsp+38h] [rbp-20h]

  for ( i = wil_details_featureDescriptors_a; ; i = (__int64 *)(v4 + 7) )
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
0x14002f8f0  push    rbx
0x14002f8f2  sub     rsp, 50h
0x14002f8f6  mov     rax, cs:__security_cookie
0x14002f8fd  xor     rax, rsp
0x14002f900  mov     [rsp+58h+var_18], rax
0x14002f905  lea     rcx, wil_details_featureDescriptors_a
0x14002f90c  jmp     short loc_14002F97F
0x14002f90e  cmp     byte ptr [rbx+1Dh], 0
0x14002f912  jnz     short loc_14002F97B
0x14002f914  cmp     byte ptr [rbx+1Eh], 0
0x14002f918  jnz     short loc_14002F97B
0x14002f91a  cmp     byte ptr [rbx+1Ch], 0
0x14002f91e  jnz     short loc_14002F97B
0x14002f920  mov     ecx, [rbx+18h]
0x14002f923  lea     r9, [rsp+58h+var_28]
0x14002f928  xor     eax, eax
0x14002f92a  lea     r8, [rsp+58h+var_30]
0x14002f92f  mov     [rsp+58h+var_28], rax
0x14002f934  mov     [rsp+58h+var_20], eax
0x14002f938  mov     [rsp+58h+var_30], rax
0x14002f93d  lea     edx, [rax+1]
0x14002f940  call    cs:__imp_RtlQueryFeatureConfiguration
0x14002f947  nop     dword ptr [rax+rax+00h]
0x14002f94c  lea     r8, [rsp+58h+var_38]
0x14002f951  mov     [rsp+58h+var_38], 0
0x14002f95a  mov     ecx, eax
0x14002f95c  lea     rdx, [rsp+58h+var_28]
0x14002f961  call    wil_details_BuildFeatureStateCacheFromQueryResults
0x14002f966  mov     rcx, [rbx]
0x14002f969  mov     edx, [rcx]
0x14002f96b  xor     edx, dword ptr [rsp+58h+var_38]
0x14002f96f  mov     rax, [rbx]
0x14002f972  and     edx, 0F80h
0x14002f978  lock xor [rax], edx
0x14002f97b  lea     rcx, [rbx+38h]
0x14002f97f  call    wil_details_FeatureDescriptors_SkipPadding
0x14002f984  mov     rbx, rax
0x14002f987  test    rax, rax
0x14002f98a  jnz     short loc_14002F90E
0x14002f98c  mov     rcx, [rsp+58h+var_18]
0x14002f991  xor     rcx, rsp; StackCookie
0x14002f994  call    __security_check_cookie
0x14002f999  add     rsp, 50h
0x14002f99d  pop     rbx
0x14002f99e  retn
```
