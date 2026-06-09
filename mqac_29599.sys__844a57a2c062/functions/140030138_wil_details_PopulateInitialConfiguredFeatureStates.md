# wil_details_PopulateInitialConfiguredFeatureStates

- ea: `0x140030138`
- end: `0x14003021d`
- name: `wil_details_PopulateInitialConfiguredFeatureStates`
- size: `229`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x140030078`

## callees

- `0x1400118c4`
- `0x140024bb0`
- `0x14002f56c`
- `0x140030138`

## import_xrefs

- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x140030191`
- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x140030191`

## pseudocode

```c
__int64 wil_details_PopulateInitialConfiguredFeatureStates()
{
  void *i; // rcx
  unsigned int v1; // eax
  __int64 v2; // rdx
  __int64 result; // rax
  _QWORD **v4; // rbx
  __int64 v5; // [rsp+20h] [rbp-38h] BYREF
  __int64 v6; // [rsp+28h] [rbp-30h] BYREF
  __int64 v7; // [rsp+30h] [rbp-28h] BYREF
  int v8; // [rsp+38h] [rbp-20h]

  for ( i = &wil_details_featureDescriptors_a; ; i = v4 + 7 )
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
0x140030138  push    rbx
0x14003013a  sub     rsp, 50h
0x14003013e  mov     rax, cs:__security_cookie
0x140030145  xor     rax, rsp
0x140030148  mov     [rsp+58h+var_18], rax
0x14003014d  lea     rcx, wil_details_featureDescriptors_a
0x140030154  jmp     loc_14003020A
0x140030159  xor     eax, eax
0x14003015b  mov     [rsp+58h+var_28], rax
0x140030160  mov     [rsp+58h+var_20], eax
0x140030164  mov     [rsp+58h+var_30], rax
0x140030169  mov     [rsp+58h+var_38], rax
0x14003016e  cmp     [rbx+1Dh], al
0x140030171  jnz     short loc_1400301E5
0x140030173  cmp     [rbx+1Eh], al
0x140030176  jnz     short loc_1400301E5
0x140030178  mov     al, [rbx+1Ch]
0x14003017b  lea     r9, [rsp+58h+var_28]
0x140030180  mov     ecx, [rbx+18h]
0x140030183  lea     r8, [rsp+58h+var_30]
0x140030188  xor     edx, edx
0x14003018a  sub     al, 2
0x14003018c  cmp     al, 1
0x14003018e  setnbe  dl
0x140030191  call    cs:__imp_RtlQueryFeatureConfiguration
0x140030198  nop     dword ptr [rax+rax+00h]
0x14003019d  cmp     eax, 80000022h
0x1400301a2  jnz     short loc_1400301EA
0x1400301a4  mov     [rsp+58h+var_38], 0
0x1400301ad  mov     dword ptr [rsp+58h+var_38], 206h
0x1400301b5  mov     rdx, [rsp+58h+var_38]
0x1400301ba  mov     rax, [rbx]
0x1400301bd  lea     rcx, [rbx+38h]
0x1400301c1  mov     [rax], rdx
0x1400301c4  call    wil_details_FeatureDescriptors_SkipPadding
0x1400301c9  mov     rbx, rax
0x1400301cc  test    rax, rax
0x1400301cf  jnz     short loc_1400301BA
0x1400301d1  mov     rcx, [rsp+58h+var_18]
0x1400301d6  xor     rcx, rsp; StackCookie
0x1400301d9  call    __security_check_cookie
0x1400301de  add     rsp, 50h
0x1400301e2  pop     rbx
0x1400301e3  retn
0x1400301e5  mov     eax, 0C0000225h
0x1400301ea  lea     r8, [rsp+58h+var_38]
0x1400301ef  mov     ecx, eax
0x1400301f1  lea     rdx, [rsp+58h+var_28]
0x1400301f6  call    wil_details_BuildFeatureStateCacheFromQueryResults
0x1400301fb  mov     rcx, [rbx]
0x1400301fe  mov     rax, [rsp+58h+var_38]
0x140030203  mov     [rcx], rax
0x140030206  lea     rcx, [rbx+38h]
0x14003020a  call    wil_details_FeatureDescriptors_SkipPadding
0x14003020f  mov     rbx, rax
0x140030212  test    rax, rax
0x140030215  jnz     loc_140030159
0x14003021b  jmp     short loc_1400301D1
```
