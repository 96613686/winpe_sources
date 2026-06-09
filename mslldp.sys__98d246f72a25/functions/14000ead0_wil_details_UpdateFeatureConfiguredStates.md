# wil_details_UpdateFeatureConfiguredStates

- ea: `0x14000ead0`
- end: `0x14000eb80`
- name: `wil_details_UpdateFeatureConfiguredStates`
- size: `176`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, installer_update`

## callers

- `0x14000ea30`

## callees

- `0x140004c24`
- `0x140006630`
- `0x14000e740`
- `0x14000ead0`

## import_xrefs

- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x14000eb20`
- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x14000eb20`

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
0x14000ead0  push    rbx
0x14000ead2  sub     rsp, 50h
0x14000ead6  mov     rax, cs:__security_cookie
0x14000eadd  xor     rax, rsp
0x14000eae0  mov     [rsp+58h+var_18], rax
0x14000eae5  lea     rcx, wil_details_featureDescriptors_a
0x14000eaec  jmp     short loc_14000EB5F
0x14000eaee  cmp     byte ptr [rbx+1Dh], 0
0x14000eaf2  jnz     short loc_14000EB5B
0x14000eaf4  cmp     byte ptr [rbx+1Eh], 0
0x14000eaf8  jnz     short loc_14000EB5B
0x14000eafa  cmp     byte ptr [rbx+1Ch], 0
0x14000eafe  jnz     short loc_14000EB5B
0x14000eb00  mov     ecx, [rbx+18h]
0x14000eb03  lea     r9, [rsp+58h+var_28]
0x14000eb08  xor     eax, eax
0x14000eb0a  lea     r8, [rsp+58h+var_30]
0x14000eb0f  mov     [rsp+58h+var_28], rax
0x14000eb14  mov     [rsp+58h+var_20], eax
0x14000eb18  mov     [rsp+58h+var_30], rax
0x14000eb1d  lea     edx, [rax+1]
0x14000eb20  call    cs:__imp_RtlQueryFeatureConfiguration
0x14000eb27  nop     dword ptr [rax+rax+00h]
0x14000eb2c  lea     r8, [rsp+58h+var_38]
0x14000eb31  mov     [rsp+58h+var_38], 0
0x14000eb3a  mov     ecx, eax
0x14000eb3c  lea     rdx, [rsp+58h+var_28]
0x14000eb41  call    wil_details_BuildFeatureStateCacheFromQueryResults
0x14000eb46  mov     rcx, [rbx]
0x14000eb49  mov     edx, [rcx]
0x14000eb4b  xor     edx, dword ptr [rsp+58h+var_38]
0x14000eb4f  mov     rax, [rbx]
0x14000eb52  and     edx, 0F80h
0x14000eb58  lock xor [rax], edx
0x14000eb5b  lea     rcx, [rbx+38h]
0x14000eb5f  call    wil_details_FeatureDescriptors_SkipPadding
0x14000eb64  mov     rbx, rax
0x14000eb67  test    rax, rax
0x14000eb6a  jnz     short loc_14000EAEE
0x14000eb6c  mov     rcx, [rsp+58h+var_18]
0x14000eb71  xor     rcx, rsp; StackCookie
0x14000eb74  call    __security_check_cookie
0x14000eb79  add     rsp, 50h
0x14000eb7d  pop     rbx
0x14000eb7e  retn
```
