# wil_details_UpdateFeatureConfiguredStates

- ea: `0x14005b0f0`
- end: `0x14005b1a0`
- name: `wil_details_UpdateFeatureConfiguredStates`
- size: `176`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, installer_update`

## callers

- `0x14005b050`

## callees

- `0x1400280e4`
- `0x14003e430`
- `0x14005ad60`
- `0x14005b0f0`

## import_xrefs

- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x14005b140`
- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x14005b140`

## pseudocode

```c
__int64 wil_details_UpdateFeatureConfiguredStates()
{
  _UNKNOWN **i; // rcx
  __int64 v1; // rcx
  unsigned int v2; // eax
  __int64 result; // rax
  volatile signed __int32 **v4; // rbx
  __int64 v5; // [rsp+20h] [rbp-38h] BYREF
  __int64 v6; // [rsp+28h] [rbp-30h] BYREF
  __int64 v7; // [rsp+30h] [rbp-28h] BYREF
  int v8; // [rsp+38h] [rbp-20h]

  for ( i = &wil_details_featureDescriptors_a; ; i = (_UNKNOWN **)(v4 + 7) )
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
0x14005b0f0  push    rbx
0x14005b0f2  sub     rsp, 50h
0x14005b0f6  mov     rax, cs:__security_cookie
0x14005b0fd  xor     rax, rsp
0x14005b100  mov     [rsp+58h+var_18], rax
0x14005b105  lea     rcx, wil_details_featureDescriptors_a
0x14005b10c  jmp     short loc_14005B17F
0x14005b10e  cmp     byte ptr [rbx+1Dh], 0
0x14005b112  jnz     short loc_14005B17B
0x14005b114  cmp     byte ptr [rbx+1Eh], 0
0x14005b118  jnz     short loc_14005B17B
0x14005b11a  cmp     byte ptr [rbx+1Ch], 0
0x14005b11e  jnz     short loc_14005B17B
0x14005b120  mov     ecx, [rbx+18h]
0x14005b123  lea     r9, [rsp+58h+var_28]
0x14005b128  xor     eax, eax
0x14005b12a  lea     r8, [rsp+58h+var_30]
0x14005b12f  mov     [rsp+58h+var_28], rax
0x14005b134  mov     [rsp+58h+var_20], eax
0x14005b138  mov     [rsp+58h+var_30], rax
0x14005b13d  lea     edx, [rax+1]
0x14005b140  call    cs:__imp_RtlQueryFeatureConfiguration
0x14005b147  nop     dword ptr [rax+rax+00h]
0x14005b14c  lea     r8, [rsp+58h+var_38]
0x14005b151  mov     [rsp+58h+var_38], 0
0x14005b15a  mov     ecx, eax
0x14005b15c  lea     rdx, [rsp+58h+var_28]
0x14005b161  call    wil_details_BuildFeatureStateCacheFromQueryResults
0x14005b166  mov     rcx, [rbx]
0x14005b169  mov     edx, [rcx]
0x14005b16b  xor     edx, dword ptr [rsp+58h+var_38]
0x14005b16f  mov     rax, [rbx]
0x14005b172  and     edx, 0F80h
0x14005b178  lock xor [rax], edx
0x14005b17b  lea     rcx, [rbx+38h]
0x14005b17f  call    wil_details_FeatureDescriptors_SkipPadding
0x14005b184  mov     rbx, rax
0x14005b187  test    rax, rax
0x14005b18a  jnz     short loc_14005B10E
0x14005b18c  mov     rcx, [rsp+58h+var_18]
0x14005b191  xor     rcx, rsp; StackCookie
0x14005b194  call    __security_check_cookie
0x14005b199  add     rsp, 50h
0x14005b19d  pop     rbx
0x14005b19e  retn
```
