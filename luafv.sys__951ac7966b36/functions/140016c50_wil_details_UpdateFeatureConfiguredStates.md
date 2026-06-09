# wil_details_UpdateFeatureConfiguredStates

- ea: `0x140016c50`
- end: `0x140016d00`
- name: `wil_details_UpdateFeatureConfiguredStates`
- size: `176`
- prototype: `__int64 *()`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, installer_update`

## callers

- `0x140016bb0`

## callees

- `0x1400031ac`
- `0x140005f30`
- `0x1400168cc`
- `0x140016c50`

## import_xrefs

- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x140016ca0`
- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x140016ca0`

## pseudocode

```c
__int64 *wil_details_UpdateFeatureConfiguredStates()
{
  __int64 *i; // rcx
  __int64 v1; // rcx
  int v2; // eax
  __int64 *result; // rax
  volatile signed __int32 **v4; // rbx
  __int64 v5; // [rsp+20h] [rbp-38h] BYREF
  __int64 v6; // [rsp+28h] [rbp-30h] BYREF
  __int64 v7; // [rsp+30h] [rbp-28h] BYREF
  int v8; // [rsp+38h] [rbp-20h]

  for ( i = (__int64 *)wil_details_featureDescriptors_a; ; i = (__int64 *)(v4 + 7) )
  {
    result = wil_details_FeatureDescriptors_SkipPadding(i);
    v4 = (volatile signed __int32 **)result;
    if ( !result )
      break;
    if ( !*((_BYTE *)result + 29) && !*((_BYTE *)result + 30) && !*((_BYTE *)result + 28) )
    {
      v1 = *((unsigned int *)result + 6);
      v7 = 0;
      v8 = 0;
      v6 = 0;
      v2 = RtlQueryFeatureConfiguration(v1, 1, &v6, &v7);
      v5 = 0;
      wil_details_BuildFeatureStateCacheFromQueryResults(v2, (__int64)&v7, &v5);
      _InterlockedXor(*v4, ((unsigned __int16)v5 ^ (unsigned __int16)**v4) & 0xF80);
    }
  }
  return result;
}

```

## disassembly

```asm
0x140016c50  push    rbx
0x140016c52  sub     rsp, 50h
0x140016c56  mov     rax, cs:__security_cookie
0x140016c5d  xor     rax, rsp
0x140016c60  mov     [rsp+58h+var_18], rax
0x140016c65  lea     rcx, wil_details_featureDescriptors_a
0x140016c6c  jmp     short loc_140016CDF
0x140016c6e  cmp     byte ptr [rbx+1Dh], 0
0x140016c72  jnz     short loc_140016CDB
0x140016c74  cmp     byte ptr [rbx+1Eh], 0
0x140016c78  jnz     short loc_140016CDB
0x140016c7a  cmp     byte ptr [rbx+1Ch], 0
0x140016c7e  jnz     short loc_140016CDB
0x140016c80  mov     ecx, [rbx+18h]
0x140016c83  lea     r9, [rsp+58h+var_28]
0x140016c88  xor     eax, eax
0x140016c8a  lea     r8, [rsp+58h+var_30]
0x140016c8f  mov     [rsp+58h+var_28], rax
0x140016c94  mov     [rsp+58h+var_20], eax
0x140016c98  mov     [rsp+58h+var_30], rax
0x140016c9d  lea     edx, [rax+1]
0x140016ca0  call    cs:__imp_RtlQueryFeatureConfiguration
0x140016ca7  nop     dword ptr [rax+rax+00h]
0x140016cac  lea     r8, [rsp+58h+var_38]
0x140016cb1  mov     [rsp+58h+var_38], 0
0x140016cba  mov     ecx, eax
0x140016cbc  lea     rdx, [rsp+58h+var_28]
0x140016cc1  call    wil_details_BuildFeatureStateCacheFromQueryResults
0x140016cc6  mov     rcx, [rbx]
0x140016cc9  mov     edx, [rcx]
0x140016ccb  xor     edx, dword ptr [rsp+58h+var_38]
0x140016ccf  mov     rax, [rbx]
0x140016cd2  and     edx, 0F80h
0x140016cd8  lock xor [rax], edx
0x140016cdb  lea     rcx, [rbx+38h]
0x140016cdf  call    wil_details_FeatureDescriptors_SkipPadding
0x140016ce4  mov     rbx, rax
0x140016ce7  test    rax, rax
0x140016cea  jnz     short loc_140016C6E
0x140016cec  mov     rcx, [rsp+58h+var_18]
0x140016cf1  xor     rcx, rsp; StackCookie
0x140016cf4  call    __security_check_cookie
0x140016cf9  add     rsp, 50h
0x140016cfd  pop     rbx
0x140016cfe  retn
```
