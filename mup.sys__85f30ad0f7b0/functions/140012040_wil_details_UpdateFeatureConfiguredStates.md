# wil_details_UpdateFeatureConfiguredStates

- ea: `0x140012040`
- end: `0x1400120f0`
- name: `wil_details_UpdateFeatureConfiguredStates`
- size: `176`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, installer_update`

## callers

- `0x140011fa0`

## callees

- `0x140003964`
- `0x1400054a0`
- `0x140011cbc`
- `0x140012040`

## import_xrefs

- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x140012090`
- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x140012090`

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
0x140012040  push    rbx
0x140012042  sub     rsp, 50h
0x140012046  mov     rax, cs:__security_cookie
0x14001204d  xor     rax, rsp
0x140012050  mov     [rsp+58h+var_18], rax
0x140012055  lea     rcx, wil_details_featureDescriptors_a
0x14001205c  jmp     short loc_1400120CF
0x14001205e  cmp     byte ptr [rbx+1Dh], 0
0x140012062  jnz     short loc_1400120CB
0x140012064  cmp     byte ptr [rbx+1Eh], 0
0x140012068  jnz     short loc_1400120CB
0x14001206a  cmp     byte ptr [rbx+1Ch], 0
0x14001206e  jnz     short loc_1400120CB
0x140012070  mov     ecx, [rbx+18h]
0x140012073  lea     r9, [rsp+58h+var_28]
0x140012078  xor     eax, eax
0x14001207a  lea     r8, [rsp+58h+var_30]
0x14001207f  mov     [rsp+58h+var_28], rax
0x140012084  mov     [rsp+58h+var_20], eax
0x140012088  mov     [rsp+58h+var_30], rax
0x14001208d  lea     edx, [rax+1]
0x140012090  call    cs:__imp_RtlQueryFeatureConfiguration
0x140012097  nop     dword ptr [rax+rax+00h]
0x14001209c  lea     r8, [rsp+58h+var_38]
0x1400120a1  mov     [rsp+58h+var_38], 0
0x1400120aa  mov     ecx, eax
0x1400120ac  lea     rdx, [rsp+58h+var_28]
0x1400120b1  call    wil_details_BuildFeatureStateCacheFromQueryResults
0x1400120b6  mov     rcx, [rbx]
0x1400120b9  mov     edx, [rcx]
0x1400120bb  xor     edx, dword ptr [rsp+58h+var_38]
0x1400120bf  mov     rax, [rbx]
0x1400120c2  and     edx, 0F80h
0x1400120c8  lock xor [rax], edx
0x1400120cb  lea     rcx, [rbx+38h]
0x1400120cf  call    wil_details_FeatureDescriptors_SkipPadding
0x1400120d4  mov     rbx, rax
0x1400120d7  test    rax, rax
0x1400120da  jnz     short loc_14001205E
0x1400120dc  mov     rcx, [rsp+58h+var_18]
0x1400120e1  xor     rcx, rsp; StackCookie
0x1400120e4  call    __security_check_cookie
0x1400120e9  add     rsp, 50h
0x1400120ed  pop     rbx
0x1400120ee  retn
```
