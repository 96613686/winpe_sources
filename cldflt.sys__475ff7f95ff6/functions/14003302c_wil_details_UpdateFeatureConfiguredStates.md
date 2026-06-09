# wil_details_UpdateFeatureConfiguredStates

- ea: `0x14003302c`
- end: `0x1400330dc`
- name: `wil_details_UpdateFeatureConfiguredStates`
- size: `176`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, installer_update`

## callers

- `0x140033010`

## callees

- `0x140009ea8`
- `0x14001e1c0`
- `0x14003302c`
- `0x140042d24`

## import_xrefs

- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x14003307c`
- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x14003307c`

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

  for ( i = &Feature_CloudFileDisguisePlaceholders__private_descriptor; ; i = (_UNKNOWN **)(v4 + 7) )
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
0x14003302c  push    rbx
0x14003302e  sub     rsp, 50h
0x140033032  mov     rax, cs:__security_cookie
0x140033039  xor     rax, rsp
0x14003303c  mov     [rsp+58h+var_18], rax
0x140033041  lea     rcx, Feature_CloudFileDisguisePlaceholders__private_descriptor
0x140033048  jmp     short loc_1400330BB
0x14003304a  cmp     byte ptr [rbx+1Dh], 0
0x14003304e  jnz     short loc_1400330B7
0x140033050  cmp     byte ptr [rbx+1Eh], 0
0x140033054  jnz     short loc_1400330B7
0x140033056  cmp     byte ptr [rbx+1Ch], 0
0x14003305a  jnz     short loc_1400330B7
0x14003305c  mov     ecx, [rbx+18h]
0x14003305f  lea     r9, [rsp+58h+var_28]
0x140033064  xor     eax, eax
0x140033066  lea     r8, [rsp+58h+var_30]
0x14003306b  mov     [rsp+58h+var_28], rax
0x140033070  mov     [rsp+58h+var_20], eax
0x140033074  mov     [rsp+58h+var_30], rax
0x140033079  lea     edx, [rax+1]
0x14003307c  call    cs:__imp_RtlQueryFeatureConfiguration
0x140033083  nop     dword ptr [rax+rax+00h]
0x140033088  lea     r8, [rsp+58h+var_38]
0x14003308d  mov     [rsp+58h+var_38], 0
0x140033096  mov     ecx, eax
0x140033098  lea     rdx, [rsp+58h+var_28]
0x14003309d  call    wil_details_BuildFeatureStateCacheFromQueryResults
0x1400330a2  mov     rcx, [rbx]
0x1400330a5  mov     edx, [rcx]
0x1400330a7  xor     edx, dword ptr [rsp+58h+var_38]
0x1400330ab  mov     rax, [rbx]
0x1400330ae  and     edx, 0F80h
0x1400330b4  lock xor [rax], edx
0x1400330b7  lea     rcx, [rbx+38h]
0x1400330bb  call    wil_details_FeatureDescriptors_SkipPadding
0x1400330c0  mov     rbx, rax
0x1400330c3  test    rax, rax
0x1400330c6  jnz     short loc_14003304A
0x1400330c8  mov     rcx, [rsp+58h+var_18]
0x1400330cd  xor     rcx, rsp; StackCookie
0x1400330d0  call    __security_check_cookie
0x1400330d5  add     rsp, 50h
0x1400330d9  pop     rbx
0x1400330da  retn
```
