# wil_details_UpdateFeatureConfiguredStates

- ea: `0x140043480`
- end: `0x140043530`
- name: `wil_details_UpdateFeatureConfiguredStates`
- size: `176`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, installer_update`

## callers

- `0x1400433e0`

## callees

- `0x140029f9c`
- `0x1400371f0`
- `0x140043108`
- `0x140043480`

## import_xrefs

- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x1400434d0`
- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x1400434d0`

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

  for ( i = wil_details_featureDescriptors_a; ; i = (int **)(v4 + 7) )
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
0x140043480  push    rbx
0x140043482  sub     rsp, 50h
0x140043486  mov     rax, cs:__security_cookie
0x14004348d  xor     rax, rsp
0x140043490  mov     [rsp+58h+var_18], rax
0x140043495  lea     rcx, wil_details_featureDescriptors_a
0x14004349c  jmp     short loc_14004350F
0x14004349e  cmp     byte ptr [rbx+1Dh], 0
0x1400434a2  jnz     short loc_14004350B
0x1400434a4  cmp     byte ptr [rbx+1Eh], 0
0x1400434a8  jnz     short loc_14004350B
0x1400434aa  cmp     byte ptr [rbx+1Ch], 0
0x1400434ae  jnz     short loc_14004350B
0x1400434b0  mov     ecx, [rbx+18h]
0x1400434b3  lea     r9, [rsp+58h+var_28]
0x1400434b8  xor     eax, eax
0x1400434ba  lea     r8, [rsp+58h+var_30]
0x1400434bf  mov     [rsp+58h+var_28], rax
0x1400434c4  mov     [rsp+58h+var_20], eax
0x1400434c8  mov     [rsp+58h+var_30], rax
0x1400434cd  lea     edx, [rax+1]
0x1400434d0  call    cs:__imp_RtlQueryFeatureConfiguration
0x1400434d7  nop     dword ptr [rax+rax+00h]
0x1400434dc  lea     r8, [rsp+58h+var_38]
0x1400434e1  mov     [rsp+58h+var_38], 0
0x1400434ea  mov     ecx, eax
0x1400434ec  lea     rdx, [rsp+58h+var_28]
0x1400434f1  call    wil_details_BuildFeatureStateCacheFromQueryResults
0x1400434f6  mov     rcx, [rbx]
0x1400434f9  mov     edx, [rcx]
0x1400434fb  xor     edx, dword ptr [rsp+58h+var_38]
0x1400434ff  mov     rax, [rbx]
0x140043502  and     edx, 0F80h
0x140043508  lock xor [rax], edx
0x14004350b  lea     rcx, [rbx+38h]
0x14004350f  call    wil_details_FeatureDescriptors_SkipPadding
0x140043514  mov     rbx, rax
0x140043517  test    rax, rax
0x14004351a  jnz     short loc_14004349E
0x14004351c  mov     rcx, [rsp+58h+var_18]
0x140043521  xor     rcx, rsp; StackCookie
0x140043524  call    __security_check_cookie
0x140043529  add     rsp, 50h
0x14004352d  pop     rbx
0x14004352e  retn
```
