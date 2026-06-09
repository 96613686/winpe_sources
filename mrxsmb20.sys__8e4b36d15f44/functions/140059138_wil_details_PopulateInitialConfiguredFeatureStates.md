# wil_details_PopulateInitialConfiguredFeatureStates

- ea: `0x140059138`
- end: `0x140059217`
- name: `wil_details_PopulateInitialConfiguredFeatureStates`
- size: `223`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x140059078`

## callees

- `0x14002c690`
- `0x140037120`
- `0x1400520fc`
- `0x140059138`

## import_xrefs

- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x140059199`
- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x140059199`

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
0x140059138  push    rbx
0x14005913a  sub     rsp, 50h
0x14005913e  mov     rax, cs:__security_cookie
0x140059145  xor     rax, rsp
0x140059148  mov     [rsp+58h+var_18], rax
0x14005914d  lea     rcx, wil_details_featureDescriptors_a
0x140059154  call    wil_details_FeatureDescriptors_SkipPadding
0x140059159  mov     rbx, rax
0x14005915c  test    rax, rax
0x14005915f  jz      short loc_1400591D9
0x140059161  xor     eax, eax
0x140059163  mov     [rsp+58h+var_28], rax
0x140059168  mov     [rsp+58h+var_20], eax
0x14005916c  mov     [rsp+58h+var_30], rax
0x140059171  mov     [rsp+58h+var_38], rax
0x140059176  cmp     [rbx+1Dh], al
0x140059179  jnz     short loc_1400591ED
0x14005917b  cmp     [rbx+1Eh], al
0x14005917e  jnz     short loc_1400591ED
0x140059180  mov     al, [rbx+1Ch]
0x140059183  lea     r9, [rsp+58h+var_28]
0x140059188  mov     ecx, [rbx+18h]
0x14005918b  lea     r8, [rsp+58h+var_30]
0x140059190  xor     edx, edx
0x140059192  sub     al, 2
0x140059194  cmp     al, 1
0x140059196  setnbe  dl
0x140059199  call    cs:__imp_RtlQueryFeatureConfiguration
0x1400591a0  nop     dword ptr [rax+rax+00h]
0x1400591a5  cmp     eax, 80000022h
0x1400591aa  jnz     short loc_1400591F2
0x1400591ac  mov     [rsp+58h+var_38], 0
0x1400591b5  mov     dword ptr [rsp+58h+var_38], 206h
0x1400591bd  mov     rdx, [rsp+58h+var_38]
0x1400591c2  mov     rax, [rbx]
0x1400591c5  lea     rcx, [rbx+38h]
0x1400591c9  mov     [rax], rdx
0x1400591cc  call    wil_details_FeatureDescriptors_SkipPadding
0x1400591d1  mov     rbx, rax
0x1400591d4  test    rax, rax
0x1400591d7  jnz     short loc_1400591C2
0x1400591d9  mov     rcx, [rsp+58h+var_18]
0x1400591de  xor     rcx, rsp; StackCookie
0x1400591e1  call    __security_check_cookie
0x1400591e6  add     rsp, 50h
0x1400591ea  pop     rbx
0x1400591eb  retn
0x1400591ed  mov     eax, 0C0000225h
0x1400591f2  lea     r8, [rsp+58h+var_38]
0x1400591f7  mov     ecx, eax
0x1400591f9  lea     rdx, [rsp+58h+var_28]
0x1400591fe  call    wil_details_BuildFeatureStateCacheFromQueryResults
0x140059203  mov     rcx, [rbx]
0x140059206  mov     rax, [rsp+58h+var_38]
0x14005920b  mov     [rcx], rax
0x14005920e  lea     rcx, [rbx+38h]
0x140059212  jmp     loc_140059154
```
