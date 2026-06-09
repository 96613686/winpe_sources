# wil_details_PopulateInitialConfiguredFeatureStates

- ea: `0x140087fe4`
- end: `0x1400880c3`
- name: `wil_details_PopulateInitialConfiguredFeatureStates`
- size: `223`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x140087f24`

## callees

- `0x140009ea8`
- `0x14001e140`
- `0x140042c34`
- `0x140087fe4`

## import_xrefs

- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x140088045`
- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x140088045`

## pseudocode

```c
__int64 wil_details_PopulateInitialConfiguredFeatureStates()
{
  _UNKNOWN **i; // rcx
  __int64 result; // rax
  _QWORD **v2; // rbx
  unsigned int v3; // eax
  __int64 v4; // rdx
  __int64 v5; // [rsp+20h] [rbp-38h] BYREF
  __int64 v6; // [rsp+28h] [rbp-30h] BYREF
  __int64 v7; // [rsp+30h] [rbp-28h] BYREF
  int v8; // [rsp+38h] [rbp-20h]

  for ( i = &Feature_CloudFileDisguisePlaceholders__private_descriptor; ; i = (_UNKNOWN **)(v2 + 7) )
  {
    result = wil_details_FeatureDescriptors_SkipPadding(i);
    v2 = (_QWORD **)result;
    if ( !result )
      break;
    v7 = 0;
    v8 = 0;
    v6 = 0;
    v5 = 0;
    if ( *(_BYTE *)(result + 29) || *(_BYTE *)(result + 30) )
    {
      v3 = -1073741275;
    }
    else
    {
      v3 = RtlQueryFeatureConfiguration(
             *(unsigned int *)(result + 24),
             (unsigned __int8)(*(_BYTE *)(result + 28) - 2) > 1u,
             &v6,
             &v7);
      if ( v3 == -2147483614 )
      {
        v5 = 518;
        v4 = 518;
        do
        {
          **v2 = v4;
          result = wil_details_FeatureDescriptors_SkipPadding(v2 + 7);
          v2 = (_QWORD **)result;
        }
        while ( result );
        return result;
      }
    }
    wil_details_BuildFeatureStateCacheFromQueryResults(v3, &v7, &v5);
    **v2 = v5;
  }
  return result;
}

```

## disassembly

```asm
0x140087fe4  push    rbx
0x140087fe6  sub     rsp, 50h
0x140087fea  mov     rax, cs:__security_cookie
0x140087ff1  xor     rax, rsp
0x140087ff4  mov     [rsp+58h+var_18], rax
0x140087ff9  lea     rcx, Feature_CloudFileDisguisePlaceholders__private_descriptor
0x140088000  call    wil_details_FeatureDescriptors_SkipPadding
0x140088005  mov     rbx, rax
0x140088008  test    rax, rax
0x14008800b  jz      short loc_140088085
0x14008800d  xor     eax, eax
0x14008800f  mov     [rsp+58h+var_28], rax
0x140088014  mov     [rsp+58h+var_20], eax
0x140088018  mov     [rsp+58h+var_30], rax
0x14008801d  mov     [rsp+58h+var_38], rax
0x140088022  cmp     [rbx+1Dh], al
0x140088025  jnz     short loc_140088099
0x140088027  cmp     [rbx+1Eh], al
0x14008802a  jnz     short loc_140088099
0x14008802c  mov     al, [rbx+1Ch]
0x14008802f  lea     r9, [rsp+58h+var_28]
0x140088034  mov     ecx, [rbx+18h]
0x140088037  lea     r8, [rsp+58h+var_30]
0x14008803c  xor     edx, edx
0x14008803e  sub     al, 2
0x140088040  cmp     al, 1
0x140088042  setnbe  dl
0x140088045  call    cs:__imp_RtlQueryFeatureConfiguration
0x14008804c  nop     dword ptr [rax+rax+00h]
0x140088051  cmp     eax, 80000022h
0x140088056  jnz     short loc_14008809E
0x140088058  mov     [rsp+58h+var_38], 0
0x140088061  mov     dword ptr [rsp+58h+var_38], 206h
0x140088069  mov     rdx, [rsp+58h+var_38]
0x14008806e  mov     rax, [rbx]
0x140088071  lea     rcx, [rbx+38h]
0x140088075  mov     [rax], rdx
0x140088078  call    wil_details_FeatureDescriptors_SkipPadding
0x14008807d  mov     rbx, rax
0x140088080  test    rax, rax
0x140088083  jnz     short loc_14008806E
0x140088085  mov     rcx, [rsp+58h+var_18]
0x14008808a  xor     rcx, rsp; StackCookie
0x14008808d  call    __security_check_cookie
0x140088092  add     rsp, 50h
0x140088096  pop     rbx
0x140088097  retn
0x140088099  mov     eax, 0C0000225h
0x14008809e  lea     r8, [rsp+58h+var_38]
0x1400880a3  mov     ecx, eax
0x1400880a5  lea     rdx, [rsp+58h+var_28]
0x1400880aa  call    wil_details_BuildFeatureStateCacheFromQueryResults
0x1400880af  mov     rcx, [rbx]
0x1400880b2  mov     rax, [rsp+58h+var_38]
0x1400880b7  mov     [rcx], rax
0x1400880ba  lea     rcx, [rbx+38h]
0x1400880be  jmp     loc_140088000
```
