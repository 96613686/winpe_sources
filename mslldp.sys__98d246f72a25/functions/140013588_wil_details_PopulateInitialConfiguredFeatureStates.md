# wil_details_PopulateInitialConfiguredFeatureStates

- ea: `0x140013588`
- end: `0x14001366d`
- name: `wil_details_PopulateInitialConfiguredFeatureStates`
- size: `229`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1400134c8`

## callees

- `0x140004c24`
- `0x140006630`
- `0x14000e740`
- `0x140013588`

## import_xrefs

- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x1400135e1`
- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x1400135e1`

## pseudocode

```c
__int64 wil_details_PopulateInitialConfiguredFeatureStates()
{
  __int64 *i; // rcx
  unsigned int v1; // eax
  __int64 v2; // rdx
  __int64 result; // rax
  _QWORD **v4; // rbx
  __int64 v5; // [rsp+20h] [rbp-38h] BYREF
  __int64 v6; // [rsp+28h] [rbp-30h] BYREF
  __int64 v7; // [rsp+30h] [rbp-28h] BYREF
  int v8; // [rsp+38h] [rbp-20h]

  for ( i = wil_details_featureDescriptors_a; ; i = (__int64 *)(v4 + 7) )
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
0x140013588  push    rbx
0x14001358a  sub     rsp, 50h
0x14001358e  mov     rax, cs:__security_cookie
0x140013595  xor     rax, rsp
0x140013598  mov     [rsp+58h+var_18], rax
0x14001359d  lea     rcx, wil_details_featureDescriptors_a
0x1400135a4  jmp     loc_14001365A
0x1400135a9  xor     eax, eax
0x1400135ab  mov     [rsp+58h+var_28], rax
0x1400135b0  mov     [rsp+58h+var_20], eax
0x1400135b4  mov     [rsp+58h+var_30], rax
0x1400135b9  mov     [rsp+58h+var_38], rax
0x1400135be  cmp     [rbx+1Dh], al
0x1400135c1  jnz     short loc_140013635
0x1400135c3  cmp     [rbx+1Eh], al
0x1400135c6  jnz     short loc_140013635
0x1400135c8  mov     al, [rbx+1Ch]
0x1400135cb  lea     r9, [rsp+58h+var_28]
0x1400135d0  mov     ecx, [rbx+18h]
0x1400135d3  lea     r8, [rsp+58h+var_30]
0x1400135d8  xor     edx, edx
0x1400135da  sub     al, 2
0x1400135dc  cmp     al, 1
0x1400135de  setnbe  dl
0x1400135e1  call    cs:__imp_RtlQueryFeatureConfiguration
0x1400135e8  nop     dword ptr [rax+rax+00h]
0x1400135ed  cmp     eax, 80000022h
0x1400135f2  jnz     short loc_14001363A
0x1400135f4  mov     [rsp+58h+var_38], 0
0x1400135fd  mov     dword ptr [rsp+58h+var_38], 206h
0x140013605  mov     rdx, [rsp+58h+var_38]
0x14001360a  mov     rax, [rbx]
0x14001360d  lea     rcx, [rbx+38h]
0x140013611  mov     [rax], rdx
0x140013614  call    wil_details_FeatureDescriptors_SkipPadding
0x140013619  mov     rbx, rax
0x14001361c  test    rax, rax
0x14001361f  jnz     short loc_14001360A
0x140013621  mov     rcx, [rsp+58h+var_18]
0x140013626  xor     rcx, rsp; StackCookie
0x140013629  call    __security_check_cookie
0x14001362e  add     rsp, 50h
0x140013632  pop     rbx
0x140013633  retn
0x140013635  mov     eax, 0C0000225h
0x14001363a  lea     r8, [rsp+58h+var_38]
0x14001363f  mov     ecx, eax
0x140013641  lea     rdx, [rsp+58h+var_28]
0x140013646  call    wil_details_BuildFeatureStateCacheFromQueryResults
0x14001364b  mov     rcx, [rbx]
0x14001364e  mov     rax, [rsp+58h+var_38]
0x140013653  mov     [rcx], rax
0x140013656  lea     rcx, [rbx+38h]
0x14001365a  call    wil_details_FeatureDescriptors_SkipPadding
0x14001365f  mov     rbx, rax
0x140013662  test    rax, rax
0x140013665  jnz     loc_1400135A9
0x14001366b  jmp     short loc_140013621
```
