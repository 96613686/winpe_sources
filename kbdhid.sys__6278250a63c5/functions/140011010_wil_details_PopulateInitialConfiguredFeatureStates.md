# wil_details_PopulateInitialConfiguredFeatureStates

- ea: `0x140011010`
- end: `0x1400110f0`
- name: `wil_details_PopulateInitialConfiguredFeatureStates`
- size: `224`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x140011940`

## callees

- `0x1400057a0`
- `0x140007130`
- `0x14000f61c`
- `0x140011010`

## import_xrefs

- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x140011072`
- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x140011072`

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

  for ( i = &wil_details_featureDescriptors_a; ; i = (_UNKNOWN **)(v2 + 7) )
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
0x140011010  push    rbx
0x140011012  sub     rsp, 50h
0x140011016  mov     rax, cs:__security_cookie
0x14001101d  xor     rax, rsp
0x140011020  mov     [rsp+58h+var_18], rax
0x140011025  lea     rcx, wil_details_featureDescriptors_a
0x14001102c  call    wil_details_FeatureDescriptors_SkipPadding
0x140011031  mov     rbx, rax
0x140011034  test    rax, rax
0x140011037  jz      short loc_1400110B2
0x140011039  xor     eax, eax
0x14001103b  mov     [rsp+58h+var_28], rax
0x140011040  mov     [rsp+58h+var_20], eax
0x140011044  mov     [rsp+58h+var_30], rax
0x140011049  mov     [rsp+58h+var_38], rax
0x14001104e  cmp     [rbx+1Dh], al
0x140011051  jnz     short loc_1400110C6
0x140011053  cmp     [rbx+1Eh], al
0x140011056  jnz     short loc_1400110C6
0x140011058  movzx   eax, byte ptr [rbx+1Ch]
0x14001105c  lea     r9, [rsp+58h+var_28]
0x140011061  mov     ecx, [rbx+18h]
0x140011064  lea     r8, [rsp+58h+var_30]
0x140011069  xor     edx, edx
0x14001106b  sub     al, 2
0x14001106d  cmp     al, 1
0x14001106f  setnbe  dl
0x140011072  call    cs:__imp_RtlQueryFeatureConfiguration
0x140011079  nop     dword ptr [rax+rax+00h]
0x14001107e  cmp     eax, 80000022h
0x140011083  jnz     short loc_1400110CB
0x140011085  mov     [rsp+58h+var_38], 0
0x14001108e  mov     dword ptr [rsp+58h+var_38], 206h
0x140011096  mov     rdx, [rsp+58h+var_38]
0x14001109b  mov     rax, [rbx]
0x14001109e  lea     rcx, [rbx+38h]
0x1400110a2  mov     [rax], rdx
0x1400110a5  call    wil_details_FeatureDescriptors_SkipPadding
0x1400110aa  mov     rbx, rax
0x1400110ad  test    rax, rax
0x1400110b0  jnz     short loc_14001109B
0x1400110b2  mov     rcx, [rsp+58h+var_18]
0x1400110b7  xor     rcx, rsp; StackCookie
0x1400110ba  call    __security_check_cookie
0x1400110bf  add     rsp, 50h
0x1400110c3  pop     rbx
0x1400110c4  retn
0x1400110c6  mov     eax, 0C0000225h
0x1400110cb  lea     r8, [rsp+58h+var_38]
0x1400110d0  mov     ecx, eax
0x1400110d2  lea     rdx, [rsp+58h+var_28]
0x1400110d7  call    wil_details_BuildFeatureStateCacheFromQueryResults
0x1400110dc  mov     rcx, [rbx]
0x1400110df  mov     rax, [rsp+58h+var_38]
0x1400110e4  mov     [rcx], rax
0x1400110e7  lea     rcx, [rbx+38h]
0x1400110eb  jmp     loc_14001102C
```
