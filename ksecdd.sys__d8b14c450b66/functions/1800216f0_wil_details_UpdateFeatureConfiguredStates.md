# wil_details_UpdateFeatureConfiguredStates

- ea: `0x1800216f0`
- end: `0x1800217a0`
- name: `wil_details_UpdateFeatureConfiguredStates`
- size: `176`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x180021650`

## callees

- `0x18000b834`
- `0x180010840`
- `0x1800213c4`
- `0x1800216f0`

## import_xrefs

- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x180021740`
- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x180021740`

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

  for ( i = Feature_Schannel_SslCopyTlsExtensions__private_descriptor; ; i = (int **)(v4 + 7) )
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
0x1800216f0  push    rbx
0x1800216f2  sub     rsp, 50h
0x1800216f6  mov     rax, cs:__security_cookie
0x1800216fd  xor     rax, rsp
0x180021700  mov     [rsp+58h+var_18], rax
0x180021705  lea     rcx, Feature_Schannel_SslCopyTlsExtensions__private_descriptor
0x18002170c  jmp     short loc_18002177F
0x18002170e  cmp     byte ptr [rbx+1Dh], 0
0x180021712  jnz     short loc_18002177B
0x180021714  cmp     byte ptr [rbx+1Eh], 0
0x180021718  jnz     short loc_18002177B
0x18002171a  cmp     byte ptr [rbx+1Ch], 0
0x18002171e  jnz     short loc_18002177B
0x180021720  mov     ecx, [rbx+18h]
0x180021723  lea     r9, [rsp+58h+var_28]
0x180021728  xor     eax, eax
0x18002172a  lea     r8, [rsp+58h+var_30]
0x18002172f  mov     [rsp+58h+var_28], rax
0x180021734  mov     [rsp+58h+var_20], eax
0x180021738  mov     [rsp+58h+var_30], rax
0x18002173d  lea     edx, [rax+1]
0x180021740  call    cs:__imp_RtlQueryFeatureConfiguration
0x180021747  nop     dword ptr [rax+rax+00h]
0x18002174c  lea     r8, [rsp+58h+var_38]
0x180021751  mov     [rsp+58h+var_38], 0
0x18002175a  mov     ecx, eax
0x18002175c  lea     rdx, [rsp+58h+var_28]
0x180021761  call    wil_details_BuildFeatureStateCacheFromQueryResults
0x180021766  mov     rcx, [rbx]
0x180021769  mov     edx, [rcx]
0x18002176b  xor     edx, dword ptr [rsp+58h+var_38]
0x18002176f  mov     rax, [rbx]
0x180021772  and     edx, 0F80h
0x180021778  lock xor [rax], edx
0x18002177b  lea     rcx, [rbx+38h]
0x18002177f  call    wil_details_FeatureDescriptors_SkipPadding
0x180021784  mov     rbx, rax
0x180021787  test    rax, rax
0x18002178a  jnz     short loc_18002170E
0x18002178c  mov     rcx, [rsp+58h+var_18]
0x180021791  xor     rcx, rsp; StackCookie
0x180021794  call    __security_check_cookie
0x180021799  add     rsp, 50h
0x18002179d  pop     rbx
0x18002179e  retn
```
