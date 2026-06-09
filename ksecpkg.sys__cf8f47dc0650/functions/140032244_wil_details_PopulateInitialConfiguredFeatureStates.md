# wil_details_PopulateInitialConfiguredFeatureStates

- ea: `0x140032244`
- end: `0x140032323`
- name: `wil_details_PopulateInitialConfiguredFeatureStates`
- size: `223`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x140032184`

## callees

- `0x140007124`
- `0x140010160`
- `0x1400202bc`
- `0x140032244`

## import_xrefs

- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x1400322a5`
- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x1400322a5`

## pseudocode

```c
__int64 wil_details_PopulateInitialConfiguredFeatureStates()
{
  int **i; // rcx
  __int64 result; // rax
  _QWORD **v2; // rbx
  unsigned int v3; // eax
  __int64 v4; // rdx
  __int64 v5; // [rsp+20h] [rbp-38h] BYREF
  __int64 v6; // [rsp+28h] [rbp-30h] BYREF
  __int64 v7; // [rsp+30h] [rbp-28h] BYREF
  int v8; // [rsp+38h] [rbp-20h]

  for ( i = &wil_details_featureDescriptors_a; ; i = (int **)(v2 + 7) )
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
0x140032244  push    rbx
0x140032246  sub     rsp, 50h
0x14003224a  mov     rax, cs:__security_cookie
0x140032251  xor     rax, rsp
0x140032254  mov     [rsp+58h+var_18], rax
0x140032259  lea     rcx, wil_details_featureDescriptors_a
0x140032260  call    wil_details_FeatureDescriptors_SkipPadding
0x140032265  mov     rbx, rax
0x140032268  test    rax, rax
0x14003226b  jz      short loc_1400322E5
0x14003226d  xor     eax, eax
0x14003226f  mov     [rsp+58h+var_28], rax
0x140032274  mov     [rsp+58h+var_20], eax
0x140032278  mov     [rsp+58h+var_30], rax
0x14003227d  mov     [rsp+58h+var_38], rax
0x140032282  cmp     [rbx+1Dh], al
0x140032285  jnz     short loc_1400322F9
0x140032287  cmp     [rbx+1Eh], al
0x14003228a  jnz     short loc_1400322F9
0x14003228c  mov     al, [rbx+1Ch]
0x14003228f  lea     r9, [rsp+58h+var_28]
0x140032294  mov     ecx, [rbx+18h]
0x140032297  lea     r8, [rsp+58h+var_30]
0x14003229c  xor     edx, edx
0x14003229e  sub     al, 2
0x1400322a0  cmp     al, 1
0x1400322a2  setnbe  dl
0x1400322a5  call    cs:__imp_RtlQueryFeatureConfiguration
0x1400322ac  nop     dword ptr [rax+rax+00h]
0x1400322b1  cmp     eax, 80000022h
0x1400322b6  jnz     short loc_1400322FE
0x1400322b8  mov     [rsp+58h+var_38], 0
0x1400322c1  mov     dword ptr [rsp+58h+var_38], 206h
0x1400322c9  mov     rdx, [rsp+58h+var_38]
0x1400322ce  mov     rax, [rbx]
0x1400322d1  lea     rcx, [rbx+38h]
0x1400322d5  mov     [rax], rdx
0x1400322d8  call    wil_details_FeatureDescriptors_SkipPadding
0x1400322dd  mov     rbx, rax
0x1400322e0  test    rax, rax
0x1400322e3  jnz     short loc_1400322CE
0x1400322e5  mov     rcx, [rsp+58h+var_18]
0x1400322ea  xor     rcx, rsp; StackCookie
0x1400322ed  call    __security_check_cookie
0x1400322f2  add     rsp, 50h
0x1400322f6  pop     rbx
0x1400322f7  retn
0x1400322f9  mov     eax, 0C0000225h
0x1400322fe  lea     r8, [rsp+58h+var_38]
0x140032303  mov     ecx, eax
0x140032305  lea     rdx, [rsp+58h+var_28]
0x14003230a  call    wil_details_BuildFeatureStateCacheFromQueryResults
0x14003230f  mov     rcx, [rbx]
0x140032312  mov     rax, [rsp+58h+var_38]
0x140032317  mov     [rcx], rax
0x14003231a  lea     rcx, [rbx+38h]
0x14003231e  jmp     loc_140032260
```
