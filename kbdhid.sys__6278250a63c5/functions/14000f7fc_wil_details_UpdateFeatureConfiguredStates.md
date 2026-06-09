# wil_details_UpdateFeatureConfiguredStates

- ea: `0x14000f7fc`
- end: `0x14000f8ac`
- name: `wil_details_UpdateFeatureConfiguredStates`
- size: `176`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, installer_update`

## callers

- `0x14000f7e0`

## callees

- `0x1400057a0`
- `0x140007130`
- `0x14000f61c`
- `0x14000f7fc`

## import_xrefs

- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x14000f84c`
- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x14000f84c`

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
0x14000f7fc  push    rbx
0x14000f7fe  sub     rsp, 50h
0x14000f802  mov     rax, cs:__security_cookie
0x14000f809  xor     rax, rsp
0x14000f80c  mov     [rsp+58h+var_18], rax
0x14000f811  lea     rcx, wil_details_featureDescriptors_a
0x14000f818  jmp     short loc_14000F88B
0x14000f81a  cmp     byte ptr [rbx+1Dh], 0
0x14000f81e  jnz     short loc_14000F887
0x14000f820  cmp     byte ptr [rbx+1Eh], 0
0x14000f824  jnz     short loc_14000F887
0x14000f826  cmp     byte ptr [rbx+1Ch], 0
0x14000f82a  jnz     short loc_14000F887
0x14000f82c  mov     ecx, [rbx+18h]
0x14000f82f  lea     r9, [rsp+58h+var_28]
0x14000f834  xor     eax, eax
0x14000f836  lea     r8, [rsp+58h+var_30]
0x14000f83b  mov     [rsp+58h+var_28], rax
0x14000f840  mov     [rsp+58h+var_20], eax
0x14000f844  mov     [rsp+58h+var_30], rax
0x14000f849  lea     edx, [rax+1]
0x14000f84c  call    cs:__imp_RtlQueryFeatureConfiguration
0x14000f853  nop     dword ptr [rax+rax+00h]
0x14000f858  lea     r8, [rsp+58h+var_38]
0x14000f85d  mov     [rsp+58h+var_38], 0
0x14000f866  mov     ecx, eax
0x14000f868  lea     rdx, [rsp+58h+var_28]
0x14000f86d  call    wil_details_BuildFeatureStateCacheFromQueryResults
0x14000f872  mov     rcx, [rbx]
0x14000f875  mov     edx, [rcx]
0x14000f877  xor     edx, dword ptr [rsp+58h+var_38]
0x14000f87b  mov     rax, [rbx]
0x14000f87e  and     edx, 0F80h
0x14000f884  lock xor [rax], edx
0x14000f887  lea     rcx, [rbx+38h]
0x14000f88b  call    wil_details_FeatureDescriptors_SkipPadding
0x14000f890  mov     rbx, rax
0x14000f893  test    rax, rax
0x14000f896  jnz     short loc_14000F81A
0x14000f898  mov     rcx, [rsp+58h+var_18]
0x14000f89d  xor     rcx, rsp; StackCookie
0x14000f8a0  call    __security_check_cookie
0x14000f8a5  add     rsp, 50h
0x14000f8a9  pop     rbx
0x14000f8aa  retn
```
