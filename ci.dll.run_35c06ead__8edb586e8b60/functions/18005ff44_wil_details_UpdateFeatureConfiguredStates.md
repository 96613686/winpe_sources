# wil_details_UpdateFeatureConfiguredStates

- ea: `0x18005ff44`
- end: `0x18005fff4`
- name: `wil_details_UpdateFeatureConfiguredStates`
- size: `176`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, installer_update`

## callers

- `0x18005fe20`

## callees

- `0x180011e30`
- `0x18002c0d0`
- `0x18005fc04`
- `0x18005ff44`

## import_xrefs

- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x18005ff94`
- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x18005ff94`

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
0x18005ff44  push    rbx
0x18005ff46  sub     rsp, 50h
0x18005ff4a  mov     rax, cs:__security_cookie
0x18005ff51  xor     rax, rsp
0x18005ff54  mov     [rsp+58h+var_18], rax
0x18005ff59  lea     rcx, wil_details_featureDescriptors_a
0x18005ff60  jmp     short loc_18005FFD3
0x18005ff62  cmp     byte ptr [rbx+1Dh], 0
0x18005ff66  jnz     short loc_18005FFCF
0x18005ff68  cmp     byte ptr [rbx+1Eh], 0
0x18005ff6c  jnz     short loc_18005FFCF
0x18005ff6e  cmp     byte ptr [rbx+1Ch], 0
0x18005ff72  jnz     short loc_18005FFCF
0x18005ff74  mov     ecx, [rbx+18h]
0x18005ff77  lea     r9, [rsp+58h+var_28]
0x18005ff7c  xor     eax, eax
0x18005ff7e  lea     r8, [rsp+58h+var_30]
0x18005ff83  mov     [rsp+58h+var_28], rax
0x18005ff88  mov     [rsp+58h+var_20], eax
0x18005ff8c  mov     [rsp+58h+var_30], rax
0x18005ff91  lea     edx, [rax+1]
0x18005ff94  call    cs:__imp_RtlQueryFeatureConfiguration
0x18005ff9b  nop     dword ptr [rax+rax+00h]
0x18005ffa0  lea     r8, [rsp+58h+var_38]
0x18005ffa5  mov     [rsp+58h+var_38], 0
0x18005ffae  mov     ecx, eax
0x18005ffb0  lea     rdx, [rsp+58h+var_28]
0x18005ffb5  call    wil_details_BuildFeatureStateCacheFromQueryResults
0x18005ffba  mov     rcx, [rbx]
0x18005ffbd  mov     edx, [rcx]
0x18005ffbf  xor     edx, dword ptr [rsp+58h+var_38]
0x18005ffc3  mov     rax, [rbx]
0x18005ffc6  and     edx, 0F80h
0x18005ffcc  lock xor [rax], edx
0x18005ffcf  lea     rcx, [rbx+38h]
0x18005ffd3  call    wil_details_FeatureDescriptors_SkipPadding
0x18005ffd8  mov     rbx, rax
0x18005ffdb  test    rax, rax
0x18005ffde  jnz     short loc_18005FF62
0x18005ffe0  mov     rcx, [rsp+58h+var_18]
0x18005ffe5  xor     rcx, rsp; StackCookie
0x18005ffe8  call    __security_check_cookie
0x18005ffed  add     rsp, 50h
0x18005fff1  pop     rbx
0x18005fff2  retn
```
