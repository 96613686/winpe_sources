# wil_details_UpdateFeatureConfiguredStates

- ea: `0x140020640`
- end: `0x1400206f0`
- name: `wil_details_UpdateFeatureConfiguredStates`
- size: `176`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, installer_update`

## callers

- `0x1400205a0`

## callees

- `0x140007124`
- `0x140010160`
- `0x1400202bc`
- `0x140020640`

## import_xrefs

- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x140020690`
- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x140020690`

## pseudocode

```c
__int64 wil_details_UpdateFeatureConfiguredStates()
{
  int **i; // rcx
  __int64 v1; // rcx
  unsigned int v2; // eax
  __int64 result; // rax
  volatile signed __int32 **v4; // rbx
  __int64 v5; // [rsp+20h] [rbp-38h] BYREF
  __int64 v6; // [rsp+28h] [rbp-30h] BYREF
  __int64 v7; // [rsp+30h] [rbp-28h] BYREF
  int v8; // [rsp+38h] [rbp-20h]

  for ( i = &wil_details_featureDescriptors_a; ; i = (int **)(v4 + 7) )
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
0x140020640  push    rbx
0x140020642  sub     rsp, 50h
0x140020646  mov     rax, cs:__security_cookie
0x14002064d  xor     rax, rsp
0x140020650  mov     [rsp+58h+var_18], rax
0x140020655  lea     rcx, wil_details_featureDescriptors_a
0x14002065c  jmp     short loc_1400206CF
0x14002065e  cmp     byte ptr [rbx+1Dh], 0
0x140020662  jnz     short loc_1400206CB
0x140020664  cmp     byte ptr [rbx+1Eh], 0
0x140020668  jnz     short loc_1400206CB
0x14002066a  cmp     byte ptr [rbx+1Ch], 0
0x14002066e  jnz     short loc_1400206CB
0x140020670  mov     ecx, [rbx+18h]
0x140020673  lea     r9, [rsp+58h+var_28]
0x140020678  xor     eax, eax
0x14002067a  lea     r8, [rsp+58h+var_30]
0x14002067f  mov     [rsp+58h+var_28], rax
0x140020684  mov     [rsp+58h+var_20], eax
0x140020688  mov     [rsp+58h+var_30], rax
0x14002068d  lea     edx, [rax+1]
0x140020690  call    cs:__imp_RtlQueryFeatureConfiguration
0x140020697  nop     dword ptr [rax+rax+00h]
0x14002069c  lea     r8, [rsp+58h+var_38]
0x1400206a1  mov     [rsp+58h+var_38], 0
0x1400206aa  mov     ecx, eax
0x1400206ac  lea     rdx, [rsp+58h+var_28]
0x1400206b1  call    wil_details_BuildFeatureStateCacheFromQueryResults
0x1400206b6  mov     rcx, [rbx]
0x1400206b9  mov     edx, [rcx]
0x1400206bb  xor     edx, dword ptr [rsp+58h+var_38]
0x1400206bf  mov     rax, [rbx]
0x1400206c2  and     edx, 0F80h
0x1400206c8  lock xor [rax], edx
0x1400206cb  lea     rcx, [rbx+38h]
0x1400206cf  call    wil_details_FeatureDescriptors_SkipPadding
0x1400206d4  mov     rbx, rax
0x1400206d7  test    rax, rax
0x1400206da  jnz     short loc_14002065E
0x1400206dc  mov     rcx, [rsp+58h+var_18]
0x1400206e1  xor     rcx, rsp; StackCookie
0x1400206e4  call    __security_check_cookie
0x1400206e9  add     rsp, 50h
0x1400206ed  pop     rbx
0x1400206ee  retn
```
