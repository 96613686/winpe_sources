# wil_details_PopulateInitialConfiguredFeatureStates

- ea: `0x140021a98`
- end: `0x140021b7d`
- name: `wil_details_PopulateInitialConfiguredFeatureStates`
- size: `229`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1400219d8`

## callees

- `0x14000a128`
- `0x14000da60`
- `0x140017bac`
- `0x140021a98`

## import_xrefs

- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x140021af1`
- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x140021af1`

## pseudocode

```c
__int64 wil_details_PopulateInitialConfiguredFeatureStates()
{
  int **i; // rcx
  unsigned int v1; // eax
  __int64 v2; // rdx
  __int64 result; // rax
  _QWORD **v4; // rbx
  __int64 v5; // [rsp+20h] [rbp-38h] BYREF
  __int64 v6; // [rsp+28h] [rbp-30h] BYREF
  __int64 v7; // [rsp+30h] [rbp-28h] BYREF
  int v8; // [rsp+38h] [rbp-20h]

  for ( i = wil_details_featureDescriptors_a; ; i = (int **)(v4 + 7) )
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
0x140021a98  push    rbx
0x140021a9a  sub     rsp, 50h
0x140021a9e  mov     rax, cs:__security_cookie
0x140021aa5  xor     rax, rsp
0x140021aa8  mov     [rsp+58h+var_18], rax
0x140021aad  lea     rcx, wil_details_featureDescriptors_a
0x140021ab4  jmp     loc_140021B6A
0x140021ab9  xor     eax, eax
0x140021abb  mov     [rsp+58h+var_28], rax
0x140021ac0  mov     [rsp+58h+var_20], eax
0x140021ac4  mov     [rsp+58h+var_30], rax
0x140021ac9  mov     [rsp+58h+var_38], rax
0x140021ace  cmp     [rbx+1Dh], al
0x140021ad1  jnz     short loc_140021B45
0x140021ad3  cmp     [rbx+1Eh], al
0x140021ad6  jnz     short loc_140021B45
0x140021ad8  mov     al, [rbx+1Ch]
0x140021adb  lea     r9, [rsp+58h+var_28]
0x140021ae0  mov     ecx, [rbx+18h]
0x140021ae3  lea     r8, [rsp+58h+var_30]
0x140021ae8  xor     edx, edx
0x140021aea  sub     al, 2
0x140021aec  cmp     al, 1
0x140021aee  setnbe  dl
0x140021af1  call    cs:__imp_RtlQueryFeatureConfiguration
0x140021af8  nop     dword ptr [rax+rax+00h]
0x140021afd  cmp     eax, 80000022h
0x140021b02  jnz     short loc_140021B4A
0x140021b04  mov     [rsp+58h+var_38], 0
0x140021b0d  mov     dword ptr [rsp+58h+var_38], 206h
0x140021b15  mov     rdx, [rsp+58h+var_38]
0x140021b1a  mov     rax, [rbx]
0x140021b1d  lea     rcx, [rbx+38h]
0x140021b21  mov     [rax], rdx
0x140021b24  call    wil_details_FeatureDescriptors_SkipPadding
0x140021b29  mov     rbx, rax
0x140021b2c  test    rax, rax
0x140021b2f  jnz     short loc_140021B1A
0x140021b31  mov     rcx, [rsp+58h+var_18]
0x140021b36  xor     rcx, rsp; StackCookie
0x140021b39  call    __security_check_cookie
0x140021b3e  add     rsp, 50h
0x140021b42  pop     rbx
0x140021b43  retn
0x140021b45  mov     eax, 0C0000225h
0x140021b4a  lea     r8, [rsp+58h+var_38]
0x140021b4f  mov     ecx, eax
0x140021b51  lea     rdx, [rsp+58h+var_28]
0x140021b56  call    wil_details_BuildFeatureStateCacheFromQueryResults
0x140021b5b  mov     rcx, [rbx]
0x140021b5e  mov     rax, [rsp+58h+var_38]
0x140021b63  mov     [rcx], rax
0x140021b66  lea     rcx, [rbx+38h]
0x140021b6a  call    wil_details_FeatureDescriptors_SkipPadding
0x140021b6f  mov     rbx, rax
0x140021b72  test    rax, rax
0x140021b75  jnz     loc_140021AB9
0x140021b7b  jmp     short loc_140021B31
```
