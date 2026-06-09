# wil_details_UpdateFeatureConfiguredStates

- ea: `0x140052480`
- end: `0x140052530`
- name: `wil_details_UpdateFeatureConfiguredStates`
- size: `176`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, installer_update`

## callers

- `0x1400523e0`

## callees

- `0x14002c690`
- `0x140037120`
- `0x1400520fc`
- `0x140052480`

## import_xrefs

- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x1400524d0`
- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x1400524d0`

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
0x140052480  push    rbx
0x140052482  sub     rsp, 50h
0x140052486  mov     rax, cs:__security_cookie
0x14005248d  xor     rax, rsp
0x140052490  mov     [rsp+58h+var_18], rax
0x140052495  lea     rcx, wil_details_featureDescriptors_a
0x14005249c  jmp     short loc_14005250F
0x14005249e  cmp     byte ptr [rbx+1Dh], 0
0x1400524a2  jnz     short loc_14005250B
0x1400524a4  cmp     byte ptr [rbx+1Eh], 0
0x1400524a8  jnz     short loc_14005250B
0x1400524aa  cmp     byte ptr [rbx+1Ch], 0
0x1400524ae  jnz     short loc_14005250B
0x1400524b0  mov     ecx, [rbx+18h]
0x1400524b3  lea     r9, [rsp+58h+var_28]
0x1400524b8  xor     eax, eax
0x1400524ba  lea     r8, [rsp+58h+var_30]
0x1400524bf  mov     [rsp+58h+var_28], rax
0x1400524c4  mov     [rsp+58h+var_20], eax
0x1400524c8  mov     [rsp+58h+var_30], rax
0x1400524cd  lea     edx, [rax+1]
0x1400524d0  call    cs:__imp_RtlQueryFeatureConfiguration
0x1400524d7  nop     dword ptr [rax+rax+00h]
0x1400524dc  lea     r8, [rsp+58h+var_38]
0x1400524e1  mov     [rsp+58h+var_38], 0
0x1400524ea  mov     ecx, eax
0x1400524ec  lea     rdx, [rsp+58h+var_28]
0x1400524f1  call    wil_details_BuildFeatureStateCacheFromQueryResults
0x1400524f6  mov     rcx, [rbx]
0x1400524f9  mov     edx, [rcx]
0x1400524fb  xor     edx, dword ptr [rsp+58h+var_38]
0x1400524ff  mov     rax, [rbx]
0x140052502  and     edx, 0F80h
0x140052508  lock xor [rax], edx
0x14005250b  lea     rcx, [rbx+38h]
0x14005250f  call    wil_details_FeatureDescriptors_SkipPadding
0x140052514  mov     rbx, rax
0x140052517  test    rax, rax
0x14005251a  jnz     short loc_14005249E
0x14005251c  mov     rcx, [rsp+58h+var_18]
0x140052521  xor     rcx, rsp; StackCookie
0x140052524  call    __security_check_cookie
0x140052529  add     rsp, 50h
0x14005252d  pop     rbx
0x14005252e  retn
```
