# wil_details_UpdateFeatureConfiguredStates

- ea: `0x140033ef0`
- end: `0x140033fa0`
- name: `wil_details_UpdateFeatureConfiguredStates`
- size: `176`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, installer_update`

## callers

- `0x140033e50`

## callees

- `0x14000fb30`
- `0x140016560`
- `0x140033b6c`
- `0x140033ef0`

## import_xrefs

- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x140033f40`
- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x140033f40`

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
0x140033ef0  push    rbx
0x140033ef2  sub     rsp, 50h
0x140033ef6  mov     rax, cs:__security_cookie
0x140033efd  xor     rax, rsp
0x140033f00  mov     [rsp+58h+var_18], rax
0x140033f05  lea     rcx, wil_details_featureDescriptors_a
0x140033f0c  jmp     short loc_140033F7F
0x140033f0e  cmp     byte ptr [rbx+1Dh], 0
0x140033f12  jnz     short loc_140033F7B
0x140033f14  cmp     byte ptr [rbx+1Eh], 0
0x140033f18  jnz     short loc_140033F7B
0x140033f1a  cmp     byte ptr [rbx+1Ch], 0
0x140033f1e  jnz     short loc_140033F7B
0x140033f20  mov     ecx, [rbx+18h]
0x140033f23  lea     r9, [rsp+58h+var_28]
0x140033f28  xor     eax, eax
0x140033f2a  lea     r8, [rsp+58h+var_30]
0x140033f2f  mov     [rsp+58h+var_28], rax
0x140033f34  mov     [rsp+58h+var_20], eax
0x140033f38  mov     [rsp+58h+var_30], rax
0x140033f3d  lea     edx, [rax+1]
0x140033f40  call    cs:__imp_RtlQueryFeatureConfiguration
0x140033f47  nop     dword ptr [rax+rax+00h]
0x140033f4c  lea     r8, [rsp+58h+var_38]
0x140033f51  mov     [rsp+58h+var_38], 0
0x140033f5a  mov     ecx, eax
0x140033f5c  lea     rdx, [rsp+58h+var_28]
0x140033f61  call    wil_details_BuildFeatureStateCacheFromQueryResults
0x140033f66  mov     rcx, [rbx]
0x140033f69  mov     edx, [rcx]
0x140033f6b  xor     edx, dword ptr [rsp+58h+var_38]
0x140033f6f  mov     rax, [rbx]
0x140033f72  and     edx, 0F80h
0x140033f78  lock xor [rax], edx
0x140033f7b  lea     rcx, [rbx+38h]
0x140033f7f  call    wil_details_FeatureDescriptors_SkipPadding
0x140033f84  mov     rbx, rax
0x140033f87  test    rax, rax
0x140033f8a  jnz     short loc_140033F0E
0x140033f8c  mov     rcx, [rsp+58h+var_18]
0x140033f91  xor     rcx, rsp; StackCookie
0x140033f94  call    __security_check_cookie
0x140033f99  add     rsp, 50h
0x140033f9d  pop     rbx
0x140033f9e  retn
```
