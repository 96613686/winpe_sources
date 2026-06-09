# wil_details_UpdateFeatureConfiguredStates

- ea: `0x140018900`
- end: `0x1400189b0`
- name: `wil_details_UpdateFeatureConfiguredStates`
- size: `176`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, installer_update`

## callers

- `0x140018860`

## callees

- `0x140003c24`
- `0x140006480`
- `0x14001857c`
- `0x140018900`

## import_xrefs

- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x140018950`
- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x140018950`

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
0x140018900  push    rbx
0x140018902  sub     rsp, 50h
0x140018906  mov     rax, cs:__security_cookie
0x14001890d  xor     rax, rsp
0x140018910  mov     [rsp+58h+var_18], rax
0x140018915  lea     rcx, wil_details_featureDescriptors_a
0x14001891c  jmp     short loc_14001898F
0x14001891e  cmp     byte ptr [rbx+1Dh], 0
0x140018922  jnz     short loc_14001898B
0x140018924  cmp     byte ptr [rbx+1Eh], 0
0x140018928  jnz     short loc_14001898B
0x14001892a  cmp     byte ptr [rbx+1Ch], 0
0x14001892e  jnz     short loc_14001898B
0x140018930  mov     ecx, [rbx+18h]
0x140018933  lea     r9, [rsp+58h+var_28]
0x140018938  xor     eax, eax
0x14001893a  lea     r8, [rsp+58h+var_30]
0x14001893f  mov     [rsp+58h+var_28], rax
0x140018944  mov     [rsp+58h+var_20], eax
0x140018948  mov     [rsp+58h+var_30], rax
0x14001894d  lea     edx, [rax+1]
0x140018950  call    cs:__imp_RtlQueryFeatureConfiguration
0x140018957  nop     dword ptr [rax+rax+00h]
0x14001895c  lea     r8, [rsp+58h+var_38]
0x140018961  mov     [rsp+58h+var_38], 0
0x14001896a  mov     ecx, eax
0x14001896c  lea     rdx, [rsp+58h+var_28]
0x140018971  call    wil_details_BuildFeatureStateCacheFromQueryResults
0x140018976  mov     rcx, [rbx]
0x140018979  mov     edx, [rcx]
0x14001897b  xor     edx, dword ptr [rsp+58h+var_38]
0x14001897f  mov     rax, [rbx]
0x140018982  and     edx, 0F80h
0x140018988  lock xor [rax], edx
0x14001898b  lea     rcx, [rbx+38h]
0x14001898f  call    wil_details_FeatureDescriptors_SkipPadding
0x140018994  mov     rbx, rax
0x140018997  test    rax, rax
0x14001899a  jnz     short loc_14001891E
0x14001899c  mov     rcx, [rsp+58h+var_18]
0x1400189a1  xor     rcx, rsp; StackCookie
0x1400189a4  call    __security_check_cookie
0x1400189a9  add     rsp, 50h
0x1400189ad  pop     rbx
0x1400189ae  retn
```
