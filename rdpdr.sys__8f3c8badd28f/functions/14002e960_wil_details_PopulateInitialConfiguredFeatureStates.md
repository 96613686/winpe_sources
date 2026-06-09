# wil_details_PopulateInitialConfiguredFeatureStates

- ea: `0x14002e960`
- end: `0x14002ea3f`
- name: `wil_details_PopulateInitialConfiguredFeatureStates`
- size: `223`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x14002e8a0`

## callees

- `0x140003c24`
- `0x140006480`
- `0x14001857c`
- `0x14002e960`

## import_xrefs

- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x14002e9c1`
- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x14002e9c1`

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
0x14002e960  push    rbx
0x14002e962  sub     rsp, 50h
0x14002e966  mov     rax, cs:__security_cookie
0x14002e96d  xor     rax, rsp
0x14002e970  mov     [rsp+58h+var_18], rax
0x14002e975  lea     rcx, wil_details_featureDescriptors_a
0x14002e97c  call    wil_details_FeatureDescriptors_SkipPadding
0x14002e981  mov     rbx, rax
0x14002e984  test    rax, rax
0x14002e987  jz      short loc_14002EA01
0x14002e989  xor     eax, eax
0x14002e98b  mov     [rsp+58h+var_28], rax
0x14002e990  mov     [rsp+58h+var_20], eax
0x14002e994  mov     [rsp+58h+var_30], rax
0x14002e999  mov     [rsp+58h+var_38], rax
0x14002e99e  cmp     [rbx+1Dh], al
0x14002e9a1  jnz     short loc_14002EA15
0x14002e9a3  cmp     [rbx+1Eh], al
0x14002e9a6  jnz     short loc_14002EA15
0x14002e9a8  mov     al, [rbx+1Ch]
0x14002e9ab  lea     r9, [rsp+58h+var_28]
0x14002e9b0  mov     ecx, [rbx+18h]
0x14002e9b3  lea     r8, [rsp+58h+var_30]
0x14002e9b8  xor     edx, edx
0x14002e9ba  sub     al, 2
0x14002e9bc  cmp     al, 1
0x14002e9be  setnbe  dl
0x14002e9c1  call    cs:__imp_RtlQueryFeatureConfiguration
0x14002e9c8  nop     dword ptr [rax+rax+00h]
0x14002e9cd  cmp     eax, 80000022h
0x14002e9d2  jnz     short loc_14002EA1A
0x14002e9d4  mov     [rsp+58h+var_38], 0
0x14002e9dd  mov     dword ptr [rsp+58h+var_38], 206h
0x14002e9e5  mov     rdx, [rsp+58h+var_38]
0x14002e9ea  mov     rax, [rbx]
0x14002e9ed  lea     rcx, [rbx+38h]
0x14002e9f1  mov     [rax], rdx
0x14002e9f4  call    wil_details_FeatureDescriptors_SkipPadding
0x14002e9f9  mov     rbx, rax
0x14002e9fc  test    rax, rax
0x14002e9ff  jnz     short loc_14002E9EA
0x14002ea01  mov     rcx, [rsp+58h+var_18]
0x14002ea06  xor     rcx, rsp; StackCookie
0x14002ea09  call    __security_check_cookie
0x14002ea0e  add     rsp, 50h
0x14002ea12  pop     rbx
0x14002ea13  retn
0x14002ea15  mov     eax, 0C0000225h
0x14002ea1a  lea     r8, [rsp+58h+var_38]
0x14002ea1f  mov     ecx, eax
0x14002ea21  lea     rdx, [rsp+58h+var_28]
0x14002ea26  call    wil_details_BuildFeatureStateCacheFromQueryResults
0x14002ea2b  mov     rcx, [rbx]
0x14002ea2e  mov     rax, [rsp+58h+var_38]
0x14002ea33  mov     [rcx], rax
0x14002ea36  lea     rcx, [rbx+38h]
0x14002ea3a  jmp     loc_14002E97C
```
