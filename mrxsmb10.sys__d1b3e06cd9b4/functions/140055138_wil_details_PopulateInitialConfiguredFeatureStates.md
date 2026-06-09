# wil_details_PopulateInitialConfiguredFeatureStates

- ea: `0x140055138`
- end: `0x140055217`
- name: `wil_details_PopulateInitialConfiguredFeatureStates`
- size: `223`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x140055078`

## callees

- `0x14000fb30`
- `0x140016560`
- `0x140033b6c`
- `0x140055138`

## import_xrefs

- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x140055199`
- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x140055199`

## pseudocode

```c
__int64 wil_details_PopulateInitialConfiguredFeatureStates()
{
  __int64 *i; // rcx
  __int64 result; // rax
  _QWORD **v2; // rbx
  unsigned int v3; // eax
  __int64 v4; // rdx
  __int64 v5; // [rsp+20h] [rbp-38h] BYREF
  __int64 v6; // [rsp+28h] [rbp-30h] BYREF
  __int64 v7; // [rsp+30h] [rbp-28h] BYREF
  int v8; // [rsp+38h] [rbp-20h]

  for ( i = wil_details_featureDescriptors_a; ; i = (__int64 *)(v2 + 7) )
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
0x140055138  push    rbx
0x14005513a  sub     rsp, 50h
0x14005513e  mov     rax, cs:__security_cookie
0x140055145  xor     rax, rsp
0x140055148  mov     [rsp+58h+var_18], rax
0x14005514d  lea     rcx, wil_details_featureDescriptors_a
0x140055154  call    wil_details_FeatureDescriptors_SkipPadding
0x140055159  mov     rbx, rax
0x14005515c  test    rax, rax
0x14005515f  jz      short loc_1400551D9
0x140055161  xor     eax, eax
0x140055163  mov     [rsp+58h+var_28], rax
0x140055168  mov     [rsp+58h+var_20], eax
0x14005516c  mov     [rsp+58h+var_30], rax
0x140055171  mov     [rsp+58h+var_38], rax
0x140055176  cmp     [rbx+1Dh], al
0x140055179  jnz     short loc_1400551ED
0x14005517b  cmp     [rbx+1Eh], al
0x14005517e  jnz     short loc_1400551ED
0x140055180  mov     al, [rbx+1Ch]
0x140055183  lea     r9, [rsp+58h+var_28]
0x140055188  mov     ecx, [rbx+18h]
0x14005518b  lea     r8, [rsp+58h+var_30]
0x140055190  xor     edx, edx
0x140055192  sub     al, 2
0x140055194  cmp     al, 1
0x140055196  setnbe  dl
0x140055199  call    cs:__imp_RtlQueryFeatureConfiguration
0x1400551a0  nop     dword ptr [rax+rax+00h]
0x1400551a5  cmp     eax, 80000022h
0x1400551aa  jnz     short loc_1400551F2
0x1400551ac  mov     [rsp+58h+var_38], 0
0x1400551b5  mov     dword ptr [rsp+58h+var_38], 206h
0x1400551bd  mov     rdx, [rsp+58h+var_38]
0x1400551c2  mov     rax, [rbx]
0x1400551c5  lea     rcx, [rbx+38h]
0x1400551c9  mov     [rax], rdx
0x1400551cc  call    wil_details_FeatureDescriptors_SkipPadding
0x1400551d1  mov     rbx, rax
0x1400551d4  test    rax, rax
0x1400551d7  jnz     short loc_1400551C2
0x1400551d9  mov     rcx, [rsp+58h+var_18]
0x1400551de  xor     rcx, rsp; StackCookie
0x1400551e1  call    __security_check_cookie
0x1400551e6  add     rsp, 50h
0x1400551ea  pop     rbx
0x1400551eb  retn
0x1400551ed  mov     eax, 0C0000225h
0x1400551f2  lea     r8, [rsp+58h+var_38]
0x1400551f7  mov     ecx, eax
0x1400551f9  lea     rdx, [rsp+58h+var_28]
0x1400551fe  call    wil_details_BuildFeatureStateCacheFromQueryResults
0x140055203  mov     rcx, [rbx]
0x140055206  mov     rax, [rsp+58h+var_38]
0x14005520b  mov     [rcx], rax
0x14005520e  lea     rcx, [rbx+38h]
0x140055212  jmp     loc_140055154
```
