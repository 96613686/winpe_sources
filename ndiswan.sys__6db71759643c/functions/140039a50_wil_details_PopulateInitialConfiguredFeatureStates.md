# wil_details_PopulateInitialConfiguredFeatureStates

- ea: `0x140039a50`
- end: `0x140039b2f`
- name: `wil_details_PopulateInitialConfiguredFeatureStates`
- size: `223`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1400396e8`

## callees

- `0x14000b5a4`
- `0x1400161f0`
- `0x14003752c`
- `0x140039a50`

## import_xrefs

- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x140039ab1`
- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x140039ab1`

## pseudocode

```c
__int64 wil_details_PopulateInitialConfiguredFeatureStates()
{
  __int64 **i; // rcx
  __int64 result; // rax
  _QWORD **v2; // rbx
  unsigned int v3; // eax
  __int64 v4; // rdx
  __int64 v5; // [rsp+20h] [rbp-38h] BYREF
  __int64 v6; // [rsp+28h] [rbp-30h] BYREF
  __int64 v7; // [rsp+30h] [rbp-28h] BYREF
  int v8; // [rsp+38h] [rbp-20h]

  for ( i = wil_details_featureDescriptors_a; ; i = v2 + 7 )
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
0x140039a50  push    rbx
0x140039a52  sub     rsp, 50h
0x140039a56  mov     rax, cs:__security_cookie
0x140039a5d  xor     rax, rsp
0x140039a60  mov     [rsp+58h+var_18], rax
0x140039a65  lea     rcx, wil_details_featureDescriptors_a
0x140039a6c  call    wil_details_FeatureDescriptors_SkipPadding
0x140039a71  mov     rbx, rax
0x140039a74  test    rax, rax
0x140039a77  jz      short loc_140039AF1
0x140039a79  xor     eax, eax
0x140039a7b  mov     [rsp+58h+var_28], rax
0x140039a80  mov     [rsp+58h+var_20], eax
0x140039a84  mov     [rsp+58h+var_30], rax
0x140039a89  mov     [rsp+58h+var_38], rax
0x140039a8e  cmp     [rbx+1Dh], al
0x140039a91  jnz     short loc_140039B05
0x140039a93  cmp     [rbx+1Eh], al
0x140039a96  jnz     short loc_140039B05
0x140039a98  mov     al, [rbx+1Ch]
0x140039a9b  lea     r9, [rsp+58h+var_28]
0x140039aa0  mov     ecx, [rbx+18h]
0x140039aa3  lea     r8, [rsp+58h+var_30]
0x140039aa8  xor     edx, edx
0x140039aaa  sub     al, 2
0x140039aac  cmp     al, 1
0x140039aae  setnbe  dl
0x140039ab1  call    cs:__imp_RtlQueryFeatureConfiguration
0x140039ab8  nop     dword ptr [rax+rax+00h]
0x140039abd  cmp     eax, 80000022h
0x140039ac2  jnz     short loc_140039B0A
0x140039ac4  mov     [rsp+58h+var_38], 0
0x140039acd  mov     dword ptr [rsp+58h+var_38], 206h
0x140039ad5  mov     rdx, [rsp+58h+var_38]
0x140039ada  mov     rax, [rbx]
0x140039add  lea     rcx, [rbx+38h]
0x140039ae1  mov     [rax], rdx
0x140039ae4  call    wil_details_FeatureDescriptors_SkipPadding
0x140039ae9  mov     rbx, rax
0x140039aec  test    rax, rax
0x140039aef  jnz     short loc_140039ADA
0x140039af1  mov     rcx, [rsp+58h+var_18]
0x140039af6  xor     rcx, rsp; StackCookie
0x140039af9  call    __security_check_cookie
0x140039afe  add     rsp, 50h
0x140039b02  pop     rbx
0x140039b03  retn
0x140039b05  mov     eax, 0C0000225h
0x140039b0a  lea     r8, [rsp+58h+var_38]
0x140039b0f  mov     ecx, eax
0x140039b11  lea     rdx, [rsp+58h+var_28]
0x140039b16  call    wil_details_BuildFeatureStateCacheFromQueryResults
0x140039b1b  mov     rcx, [rbx]
0x140039b1e  mov     rax, [rsp+58h+var_38]
0x140039b23  mov     [rcx], rax
0x140039b26  lea     rcx, [rbx+38h]
0x140039b2a  jmp     loc_140039A6C
```
