# wil_details_PopulateInitialConfiguredFeatureStates

- ea: `0x140029574`
- end: `0x140029653`
- name: `wil_details_PopulateInitialConfiguredFeatureStates`
- size: `223`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1400294b4`

## callees

- `0x1400031ac`
- `0x140005f30`
- `0x1400168cc`
- `0x140029574`

## import_xrefs

- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x1400295d5`
- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x1400295d5`

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
0x140029574  push    rbx
0x140029576  sub     rsp, 50h
0x14002957a  mov     rax, cs:__security_cookie
0x140029581  xor     rax, rsp
0x140029584  mov     [rsp+58h+var_18], rax
0x140029589  lea     rcx, wil_details_featureDescriptors_a
0x140029590  call    wil_details_FeatureDescriptors_SkipPadding
0x140029595  mov     rbx, rax
0x140029598  test    rax, rax
0x14002959b  jz      short loc_140029615
0x14002959d  xor     eax, eax
0x14002959f  mov     [rsp+58h+var_28], rax
0x1400295a4  mov     [rsp+58h+var_20], eax
0x1400295a8  mov     [rsp+58h+var_30], rax
0x1400295ad  mov     [rsp+58h+var_38], rax
0x1400295b2  cmp     [rbx+1Dh], al
0x1400295b5  jnz     short loc_140029629
0x1400295b7  cmp     [rbx+1Eh], al
0x1400295ba  jnz     short loc_140029629
0x1400295bc  mov     al, [rbx+1Ch]
0x1400295bf  lea     r9, [rsp+58h+var_28]
0x1400295c4  mov     ecx, [rbx+18h]
0x1400295c7  lea     r8, [rsp+58h+var_30]
0x1400295cc  xor     edx, edx
0x1400295ce  sub     al, 2
0x1400295d0  cmp     al, 1
0x1400295d2  setnbe  dl
0x1400295d5  call    cs:__imp_RtlQueryFeatureConfiguration
0x1400295dc  nop     dword ptr [rax+rax+00h]
0x1400295e1  cmp     eax, 80000022h
0x1400295e6  jnz     short loc_14002962E
0x1400295e8  mov     [rsp+58h+var_38], 0
0x1400295f1  mov     dword ptr [rsp+58h+var_38], 206h
0x1400295f9  mov     rdx, [rsp+58h+var_38]
0x1400295fe  mov     rax, [rbx]
0x140029601  lea     rcx, [rbx+38h]
0x140029605  mov     [rax], rdx
0x140029608  call    wil_details_FeatureDescriptors_SkipPadding
0x14002960d  mov     rbx, rax
0x140029610  test    rax, rax
0x140029613  jnz     short loc_1400295FE
0x140029615  mov     rcx, [rsp+58h+var_18]
0x14002961a  xor     rcx, rsp; StackCookie
0x14002961d  call    __security_check_cookie
0x140029622  add     rsp, 50h
0x140029626  pop     rbx
0x140029627  retn
0x140029629  mov     eax, 0C0000225h
0x14002962e  lea     r8, [rsp+58h+var_38]
0x140029633  mov     ecx, eax
0x140029635  lea     rdx, [rsp+58h+var_28]
0x14002963a  call    wil_details_BuildFeatureStateCacheFromQueryResults
0x14002963f  mov     rcx, [rbx]
0x140029642  mov     rax, [rsp+58h+var_38]
0x140029647  mov     [rcx], rax
0x14002964a  lea     rcx, [rbx+38h]
0x14002964e  jmp     loc_140029590
```
