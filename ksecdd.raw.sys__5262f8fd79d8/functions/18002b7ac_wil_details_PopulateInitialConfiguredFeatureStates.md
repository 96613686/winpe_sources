# wil_details_PopulateInitialConfiguredFeatureStates

- ea: `0x18002b7ac`
- end: `0x18002b88b`
- name: `wil_details_PopulateInitialConfiguredFeatureStates`
- size: `223`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x18002b6ec`

## callees

- `0x18000b834`
- `0x1800108a0`
- `0x1800213c4`
- `0x18002b7ac`

## import_xrefs

- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x18002b80d`
- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x18002b80d`

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

  for ( i = &Feature_Schannel_SslCopyTlsExtensions__private_descriptor; ; i = (int **)(v2 + 7) )
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
0x18002b7ac  push    rbx
0x18002b7ae  sub     rsp, 50h
0x18002b7b2  mov     rax, cs:__security_cookie
0x18002b7b9  xor     rax, rsp
0x18002b7bc  mov     [rsp+58h+var_18], rax
0x18002b7c1  lea     rcx, Feature_Schannel_SslCopyTlsExtensions__private_descriptor
0x18002b7c8  call    wil_details_FeatureDescriptors_SkipPadding
0x18002b7cd  mov     rbx, rax
0x18002b7d0  test    rax, rax
0x18002b7d3  jz      short loc_18002B84D
0x18002b7d5  xor     eax, eax
0x18002b7d7  mov     [rsp+58h+var_28], rax
0x18002b7dc  mov     [rsp+58h+var_20], eax
0x18002b7e0  mov     [rsp+58h+var_30], rax
0x18002b7e5  mov     [rsp+58h+var_38], rax
0x18002b7ea  cmp     [rbx+1Dh], al
0x18002b7ed  jnz     short loc_18002B861
0x18002b7ef  cmp     [rbx+1Eh], al
0x18002b7f2  jnz     short loc_18002B861
0x18002b7f4  mov     al, [rbx+1Ch]
0x18002b7f7  lea     r9, [rsp+58h+var_28]
0x18002b7fc  mov     ecx, [rbx+18h]
0x18002b7ff  lea     r8, [rsp+58h+var_30]
0x18002b804  xor     edx, edx
0x18002b806  sub     al, 2
0x18002b808  cmp     al, 1
0x18002b80a  setnbe  dl
0x18002b80d  call    cs:__imp_RtlQueryFeatureConfiguration
0x18002b814  nop     dword ptr [rax+rax+00h]
0x18002b819  cmp     eax, 80000022h
0x18002b81e  jnz     short loc_18002B866
0x18002b820  mov     [rsp+58h+var_38], 0
0x18002b829  mov     dword ptr [rsp+58h+var_38], 206h
0x18002b831  mov     rdx, [rsp+58h+var_38]
0x18002b836  mov     rax, [rbx]
0x18002b839  lea     rcx, [rbx+38h]
0x18002b83d  mov     [rax], rdx
0x18002b840  call    wil_details_FeatureDescriptors_SkipPadding
0x18002b845  mov     rbx, rax
0x18002b848  test    rax, rax
0x18002b84b  jnz     short loc_18002B836
0x18002b84d  mov     rcx, [rsp+58h+var_18]
0x18002b852  xor     rcx, rsp; StackCookie
0x18002b855  call    __security_check_cookie
0x18002b85a  add     rsp, 50h
0x18002b85e  pop     rbx
0x18002b85f  retn
0x18002b861  mov     eax, 0C0000225h
0x18002b866  lea     r8, [rsp+58h+var_38]
0x18002b86b  mov     ecx, eax
0x18002b86d  lea     rdx, [rsp+58h+var_28]
0x18002b872  call    wil_details_BuildFeatureStateCacheFromQueryResults
0x18002b877  mov     rcx, [rbx]
0x18002b87a  mov     rax, [rsp+58h+var_38]
0x18002b87f  mov     [rcx], rax
0x18002b882  lea     rcx, [rbx+38h]
0x18002b886  jmp     loc_18002B7C8
```
