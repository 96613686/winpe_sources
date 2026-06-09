# wil_details_PopulateInitialConfiguredFeatureStates

- ea: `0x14006515c`
- end: `0x14006523b`
- name: `wil_details_PopulateInitialConfiguredFeatureStates`
- size: `223`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x14006509c`

## callees

- `0x1400280e4`
- `0x14003e430`
- `0x14005ad60`
- `0x14006515c`

## import_xrefs

- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x1400651bd`
- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x1400651bd`

## pseudocode

```c
__int64 wil_details_PopulateInitialConfiguredFeatureStates()
{
  _UNKNOWN **i; // rcx
  __int64 result; // rax
  _QWORD **v2; // rbx
  unsigned int v3; // eax
  __int64 v4; // rdx
  __int64 v5; // [rsp+20h] [rbp-38h] BYREF
  __int64 v6; // [rsp+28h] [rbp-30h] BYREF
  __int64 v7; // [rsp+30h] [rbp-28h] BYREF
  int v8; // [rsp+38h] [rbp-20h]

  for ( i = &wil_details_featureDescriptors_a; ; i = (_UNKNOWN **)(v2 + 7) )
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
0x14006515c  push    rbx
0x14006515e  sub     rsp, 50h
0x140065162  mov     rax, cs:__security_cookie
0x140065169  xor     rax, rsp
0x14006516c  mov     [rsp+58h+var_18], rax
0x140065171  lea     rcx, wil_details_featureDescriptors_a
0x140065178  call    wil_details_FeatureDescriptors_SkipPadding
0x14006517d  mov     rbx, rax
0x140065180  test    rax, rax
0x140065183  jz      short loc_1400651FD
0x140065185  xor     eax, eax
0x140065187  mov     [rsp+58h+var_28], rax
0x14006518c  mov     [rsp+58h+var_20], eax
0x140065190  mov     [rsp+58h+var_30], rax
0x140065195  mov     [rsp+58h+var_38], rax
0x14006519a  cmp     [rbx+1Dh], al
0x14006519d  jnz     short loc_140065211
0x14006519f  cmp     [rbx+1Eh], al
0x1400651a2  jnz     short loc_140065211
0x1400651a4  mov     al, [rbx+1Ch]
0x1400651a7  lea     r9, [rsp+58h+var_28]
0x1400651ac  mov     ecx, [rbx+18h]
0x1400651af  lea     r8, [rsp+58h+var_30]
0x1400651b4  xor     edx, edx
0x1400651b6  sub     al, 2
0x1400651b8  cmp     al, 1
0x1400651ba  setnbe  dl
0x1400651bd  call    cs:__imp_RtlQueryFeatureConfiguration
0x1400651c4  nop     dword ptr [rax+rax+00h]
0x1400651c9  cmp     eax, 80000022h
0x1400651ce  jnz     short loc_140065216
0x1400651d0  mov     [rsp+58h+var_38], 0
0x1400651d9  mov     dword ptr [rsp+58h+var_38], 206h
0x1400651e1  mov     rdx, [rsp+58h+var_38]
0x1400651e6  mov     rax, [rbx]
0x1400651e9  lea     rcx, [rbx+38h]
0x1400651ed  mov     [rax], rdx
0x1400651f0  call    wil_details_FeatureDescriptors_SkipPadding
0x1400651f5  mov     rbx, rax
0x1400651f8  test    rax, rax
0x1400651fb  jnz     short loc_1400651E6
0x1400651fd  mov     rcx, [rsp+58h+var_18]
0x140065202  xor     rcx, rsp; StackCookie
0x140065205  call    __security_check_cookie
0x14006520a  add     rsp, 50h
0x14006520e  pop     rbx
0x14006520f  retn
0x140065211  mov     eax, 0C0000225h
0x140065216  lea     r8, [rsp+58h+var_38]
0x14006521b  mov     ecx, eax
0x14006521d  lea     rdx, [rsp+58h+var_28]
0x140065222  call    wil_details_BuildFeatureStateCacheFromQueryResults
0x140065227  mov     rcx, [rbx]
0x14006522a  mov     rax, [rsp+58h+var_38]
0x14006522f  mov     [rcx], rax
0x140065232  lea     rcx, [rbx+38h]
0x140065236  jmp     loc_140065178
```
