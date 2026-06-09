# wil_details_PopulateInitialConfiguredFeatureStates

- ea: `0x180045138`
- end: `0x180045217`
- name: `wil_details_PopulateInitialConfiguredFeatureStates`
- size: `223`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180045078`

## callees

- `0x18001da84`
- `0x180027ba0`
- `0x1800391dc`
- `0x180045138`

## import_xrefs

- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x180045199`
- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x180045199`

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
0x180045138  push    rbx
0x18004513a  sub     rsp, 50h
0x18004513e  mov     rax, cs:__security_cookie
0x180045145  xor     rax, rsp
0x180045148  mov     [rsp+58h+var_18], rax
0x18004514d  lea     rcx, wil_details_featureDescriptors_a
0x180045154  call    wil_details_FeatureDescriptors_SkipPadding
0x180045159  mov     rbx, rax
0x18004515c  test    rax, rax
0x18004515f  jz      short loc_1800451D9
0x180045161  xor     eax, eax
0x180045163  mov     [rsp+58h+var_28], rax
0x180045168  mov     [rsp+58h+var_20], eax
0x18004516c  mov     [rsp+58h+var_30], rax
0x180045171  mov     [rsp+58h+var_38], rax
0x180045176  cmp     [rbx+1Dh], al
0x180045179  jnz     short loc_1800451ED
0x18004517b  cmp     [rbx+1Eh], al
0x18004517e  jnz     short loc_1800451ED
0x180045180  mov     al, [rbx+1Ch]
0x180045183  lea     r9, [rsp+58h+var_28]
0x180045188  mov     ecx, [rbx+18h]
0x18004518b  lea     r8, [rsp+58h+var_30]
0x180045190  xor     edx, edx
0x180045192  sub     al, 2
0x180045194  cmp     al, 1
0x180045196  setnbe  dl
0x180045199  call    cs:__imp_RtlQueryFeatureConfiguration
0x1800451a0  nop     dword ptr [rax+rax+00h]
0x1800451a5  cmp     eax, 80000022h
0x1800451aa  jnz     short loc_1800451F2
0x1800451ac  mov     [rsp+58h+var_38], 0
0x1800451b5  mov     dword ptr [rsp+58h+var_38], 206h
0x1800451bd  mov     rdx, [rsp+58h+var_38]
0x1800451c2  mov     rax, [rbx]
0x1800451c5  lea     rcx, [rbx+38h]
0x1800451c9  mov     [rax], rdx
0x1800451cc  call    wil_details_FeatureDescriptors_SkipPadding
0x1800451d1  mov     rbx, rax
0x1800451d4  test    rax, rax
0x1800451d7  jnz     short loc_1800451C2
0x1800451d9  mov     rcx, [rsp+58h+var_18]
0x1800451de  xor     rcx, rsp; StackCookie
0x1800451e1  call    __security_check_cookie
0x1800451e6  add     rsp, 50h
0x1800451ea  pop     rbx
0x1800451eb  retn
0x1800451ed  mov     eax, 0C0000225h
0x1800451f2  lea     r8, [rsp+58h+var_38]
0x1800451f7  mov     ecx, eax
0x1800451f9  lea     rdx, [rsp+58h+var_28]
0x1800451fe  call    wil_details_BuildFeatureStateCacheFromQueryResults
0x180045203  mov     rcx, [rbx]
0x180045206  mov     rax, [rsp+58h+var_38]
0x18004520b  mov     [rcx], rax
0x18004520e  lea     rcx, [rbx+38h]
0x180045212  jmp     loc_180045154
```
