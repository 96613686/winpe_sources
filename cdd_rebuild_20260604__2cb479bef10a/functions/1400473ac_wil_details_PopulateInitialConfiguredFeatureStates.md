# wil_details_PopulateInitialConfiguredFeatureStates

- ea: `0x1400473ac`
- end: `0x14004748b`
- name: `wil_details_PopulateInitialConfiguredFeatureStates`
- size: `223`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1400472ec`

## callees

- `0x140029f9c`
- `0x1400371f0`
- `0x140043108`
- `0x1400473ac`

## import_xrefs

- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x14004740d`
- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x14004740d`

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

  for ( i = wil_details_featureDescriptors_a; ; i = (int **)(v2 + 7) )
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
0x1400473ac  push    rbx
0x1400473ae  sub     rsp, 50h
0x1400473b2  mov     rax, cs:__security_cookie
0x1400473b9  xor     rax, rsp
0x1400473bc  mov     [rsp+58h+var_18], rax
0x1400473c1  lea     rcx, wil_details_featureDescriptors_a
0x1400473c8  call    wil_details_FeatureDescriptors_SkipPadding
0x1400473cd  mov     rbx, rax
0x1400473d0  test    rax, rax
0x1400473d3  jz      short loc_14004744D
0x1400473d5  xor     eax, eax
0x1400473d7  mov     [rsp+58h+var_28], rax
0x1400473dc  mov     [rsp+58h+var_20], eax
0x1400473e0  mov     [rsp+58h+var_30], rax
0x1400473e5  mov     [rsp+58h+var_38], rax
0x1400473ea  cmp     [rbx+1Dh], al
0x1400473ed  jnz     short loc_140047461
0x1400473ef  cmp     [rbx+1Eh], al
0x1400473f2  jnz     short loc_140047461
0x1400473f4  mov     al, [rbx+1Ch]
0x1400473f7  lea     r9, [rsp+58h+var_28]
0x1400473fc  mov     ecx, [rbx+18h]
0x1400473ff  lea     r8, [rsp+58h+var_30]
0x140047404  xor     edx, edx
0x140047406  sub     al, 2
0x140047408  cmp     al, 1
0x14004740a  setnbe  dl
0x14004740d  call    cs:__imp_RtlQueryFeatureConfiguration
0x140047414  nop     dword ptr [rax+rax+00h]
0x140047419  cmp     eax, 80000022h
0x14004741e  jnz     short loc_140047466
0x140047420  mov     [rsp+58h+var_38], 0
0x140047429  mov     dword ptr [rsp+58h+var_38], 206h
0x140047431  mov     rdx, [rsp+58h+var_38]
0x140047436  mov     rax, [rbx]
0x140047439  lea     rcx, [rbx+38h]
0x14004743d  mov     [rax], rdx
0x140047440  call    wil_details_FeatureDescriptors_SkipPadding
0x140047445  mov     rbx, rax
0x140047448  test    rax, rax
0x14004744b  jnz     short loc_140047436
0x14004744d  mov     rcx, [rsp+58h+var_18]
0x140047452  xor     rcx, rsp; StackCookie
0x140047455  call    __security_check_cookie
0x14004745a  add     rsp, 50h
0x14004745e  pop     rbx
0x14004745f  retn
0x140047461  mov     eax, 0C0000225h
0x140047466  lea     r8, [rsp+58h+var_38]
0x14004746b  mov     ecx, eax
0x14004746d  lea     rdx, [rsp+58h+var_28]
0x140047472  call    wil_details_BuildFeatureStateCacheFromQueryResults
0x140047477  mov     rcx, [rbx]
0x14004747a  mov     rax, [rsp+58h+var_38]
0x14004747f  mov     [rcx], rax
0x140047482  lea     rcx, [rbx+38h]
0x140047486  jmp     loc_1400473C8
```
