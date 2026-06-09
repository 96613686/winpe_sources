# wil_details_UpdateFeatureConfiguredStates

- ea: `0x180039510`
- end: `0x1800395c0`
- name: `wil_details_UpdateFeatureConfiguredStates`
- size: `176`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, installer_update`

## callers

- `0x180039470`

## callees

- `0x18001da84`
- `0x180027ba0`
- `0x1800391dc`
- `0x180039510`

## import_xrefs

- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x180039560`
- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x180039560`

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
0x180039510  push    rbx
0x180039512  sub     rsp, 50h
0x180039516  mov     rax, cs:__security_cookie
0x18003951d  xor     rax, rsp
0x180039520  mov     [rsp+58h+var_18], rax
0x180039525  lea     rcx, wil_details_featureDescriptors_a
0x18003952c  jmp     short loc_18003959F
0x18003952e  cmp     byte ptr [rbx+1Dh], 0
0x180039532  jnz     short loc_18003959B
0x180039534  cmp     byte ptr [rbx+1Eh], 0
0x180039538  jnz     short loc_18003959B
0x18003953a  cmp     byte ptr [rbx+1Ch], 0
0x18003953e  jnz     short loc_18003959B
0x180039540  mov     ecx, [rbx+18h]
0x180039543  lea     r9, [rsp+58h+var_28]
0x180039548  xor     eax, eax
0x18003954a  lea     r8, [rsp+58h+var_30]
0x18003954f  mov     [rsp+58h+var_28], rax
0x180039554  mov     [rsp+58h+var_20], eax
0x180039558  mov     [rsp+58h+var_30], rax
0x18003955d  lea     edx, [rax+1]
0x180039560  call    cs:__imp_RtlQueryFeatureConfiguration
0x180039567  nop     dword ptr [rax+rax+00h]
0x18003956c  lea     r8, [rsp+58h+var_38]
0x180039571  mov     [rsp+58h+var_38], 0
0x18003957a  mov     ecx, eax
0x18003957c  lea     rdx, [rsp+58h+var_28]
0x180039581  call    wil_details_BuildFeatureStateCacheFromQueryResults
0x180039586  mov     rcx, [rbx]
0x180039589  mov     edx, [rcx]
0x18003958b  xor     edx, dword ptr [rsp+58h+var_38]
0x18003958f  mov     rax, [rbx]
0x180039592  and     edx, 0F80h
0x180039598  lock xor [rax], edx
0x18003959b  lea     rcx, [rbx+38h]
0x18003959f  call    wil_details_FeatureDescriptors_SkipPadding
0x1800395a4  mov     rbx, rax
0x1800395a7  test    rax, rax
0x1800395aa  jnz     short loc_18003952E
0x1800395ac  mov     rcx, [rsp+58h+var_18]
0x1800395b1  xor     rcx, rsp; StackCookie
0x1800395b4  call    __security_check_cookie
0x1800395b9  add     rsp, 50h
0x1800395bd  pop     rbx
0x1800395be  retn
```
