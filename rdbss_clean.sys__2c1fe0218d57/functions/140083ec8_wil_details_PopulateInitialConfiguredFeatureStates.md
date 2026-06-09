# wil_details_PopulateInitialConfiguredFeatureStates

- ea: `0x140083ec8`
- end: `0x140083fad`
- name: `wil_details_PopulateInitialConfiguredFeatureStates`
- size: `229`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x140083e08`

## callees

- `0x14001ca94`
- `0x140025c20`
- `0x14004a09c`
- `0x140083ec8`

## import_xrefs

- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x140083f21`
- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x140083f21`

## pseudocode

```c
__int64 wil_details_PopulateInitialConfiguredFeatureStates()
{
  void *i; // rcx
  unsigned int v1; // eax
  __int64 v2; // rdx
  __int64 result; // rax
  _QWORD **v4; // rbx
  __int64 v5; // [rsp+20h] [rbp-38h] BYREF
  __int64 v6; // [rsp+28h] [rbp-30h] BYREF
  __int64 v7; // [rsp+30h] [rbp-28h] BYREF
  int v8; // [rsp+38h] [rbp-20h]

  for ( i = &wil_details_featureDescriptors_a; ; i = v4 + 7 )
  {
    result = wil_details_FeatureDescriptors_SkipPadding(i);
    v4 = (_QWORD **)result;
    if ( !result )
      break;
    v7 = 0;
    v8 = 0;
    v6 = 0;
    v5 = 0;
    if ( *(_BYTE *)(result + 29) || *(_BYTE *)(result + 30) )
    {
      v1 = -1073741275;
    }
    else
    {
      v1 = RtlQueryFeatureConfiguration(
             *(unsigned int *)(result + 24),
             (unsigned __int8)(*(_BYTE *)(result + 28) - 2) > 1u,
             &v6,
             &v7);
      if ( v1 == -2147483614 )
      {
        v5 = 518;
        v2 = 518;
        do
        {
          **v4 = v2;
          result = wil_details_FeatureDescriptors_SkipPadding(v4 + 7);
          v4 = (_QWORD **)result;
        }
        while ( result );
        return result;
      }
    }
    wil_details_BuildFeatureStateCacheFromQueryResults(v1, &v7, &v5);
    **v4 = v5;
  }
  return result;
}

```

## disassembly

```asm
0x140083ec8  push    rbx
0x140083eca  sub     rsp, 50h
0x140083ece  mov     rax, cs:__security_cookie
0x140083ed5  xor     rax, rsp
0x140083ed8  mov     [rsp+58h+var_18], rax
0x140083edd  lea     rcx, wil_details_featureDescriptors_a
0x140083ee4  jmp     loc_140083F9A
0x140083ee9  xor     eax, eax
0x140083eeb  mov     [rsp+58h+var_28], rax
0x140083ef0  mov     [rsp+58h+var_20], eax
0x140083ef4  mov     [rsp+58h+var_30], rax
0x140083ef9  mov     [rsp+58h+var_38], rax
0x140083efe  cmp     [rbx+1Dh], al
0x140083f01  jnz     short loc_140083F75
0x140083f03  cmp     [rbx+1Eh], al
0x140083f06  jnz     short loc_140083F75
0x140083f08  mov     al, [rbx+1Ch]
0x140083f0b  lea     r9, [rsp+58h+var_28]
0x140083f10  mov     ecx, [rbx+18h]
0x140083f13  lea     r8, [rsp+58h+var_30]
0x140083f18  xor     edx, edx
0x140083f1a  sub     al, 2
0x140083f1c  cmp     al, 1
0x140083f1e  setnbe  dl
0x140083f21  call    cs:__imp_RtlQueryFeatureConfiguration
0x140083f28  nop     dword ptr [rax+rax+00h]
0x140083f2d  cmp     eax, 80000022h
0x140083f32  jnz     short loc_140083F7A
0x140083f34  mov     [rsp+58h+var_38], 0
0x140083f3d  mov     dword ptr [rsp+58h+var_38], 206h
0x140083f45  mov     rdx, [rsp+58h+var_38]
0x140083f4a  mov     rax, [rbx]
0x140083f4d  lea     rcx, [rbx+38h]
0x140083f51  mov     [rax], rdx
0x140083f54  call    wil_details_FeatureDescriptors_SkipPadding
0x140083f59  mov     rbx, rax
0x140083f5c  test    rax, rax
0x140083f5f  jnz     short loc_140083F4A
0x140083f61  mov     rcx, [rsp+58h+var_18]
0x140083f66  xor     rcx, rsp; StackCookie
0x140083f69  call    __security_check_cookie
0x140083f6e  add     rsp, 50h
0x140083f72  pop     rbx
0x140083f73  retn
0x140083f75  mov     eax, 0C0000225h
0x140083f7a  lea     r8, [rsp+58h+var_38]
0x140083f7f  mov     ecx, eax
0x140083f81  lea     rdx, [rsp+58h+var_28]
0x140083f86  call    wil_details_BuildFeatureStateCacheFromQueryResults
0x140083f8b  mov     rcx, [rbx]
0x140083f8e  mov     rax, [rsp+58h+var_38]
0x140083f93  mov     [rcx], rax
0x140083f96  lea     rcx, [rbx+38h]
0x140083f9a  call    wil_details_FeatureDescriptors_SkipPadding
0x140083f9f  mov     rbx, rax
0x140083fa2  test    rax, rax
0x140083fa5  jnz     loc_140083EE9
0x140083fab  jmp     short loc_140083F61
```
