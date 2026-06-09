# wil_details_PopulateInitialConfiguredFeatureStates

- ea: `0x1400532b8`
- end: `0x14005339d`
- name: `wil_details_PopulateInitialConfiguredFeatureStates`
- size: `229`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1400531f8`

## callees

- `0x14002d2b0`
- `0x140030f40`
- `0x140044ce0`
- `0x1400532b8`

## import_xrefs

- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x140053311`
- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x140053311`

## pseudocode

```c
__int64 wil_details_PopulateInitialConfiguredFeatureStates()
{
  int **i; // rcx
  unsigned int v1; // eax
  __int64 v2; // rdx
  __int64 result; // rax
  _QWORD **v4; // rbx
  __int64 v5; // [rsp+20h] [rbp-38h] BYREF
  __int64 v6; // [rsp+28h] [rbp-30h] BYREF
  __int64 v7; // [rsp+30h] [rbp-28h] BYREF
  int v8; // [rsp+38h] [rbp-20h]

  for ( i = wil_details_featureDescriptors_a; ; i = (int **)(v4 + 7) )
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
0x1400532b8  push    rbx
0x1400532ba  sub     rsp, 50h
0x1400532be  mov     rax, cs:__security_cookie
0x1400532c5  xor     rax, rsp
0x1400532c8  mov     [rsp+58h+var_18], rax
0x1400532cd  lea     rcx, wil_details_featureDescriptors_a
0x1400532d4  jmp     loc_14005338A
0x1400532d9  xor     eax, eax
0x1400532db  mov     [rsp+58h+var_28], rax
0x1400532e0  mov     [rsp+58h+var_20], eax
0x1400532e4  mov     [rsp+58h+var_30], rax
0x1400532e9  mov     [rsp+58h+var_38], rax
0x1400532ee  cmp     [rbx+1Dh], al
0x1400532f1  jnz     short loc_140053365
0x1400532f3  cmp     [rbx+1Eh], al
0x1400532f6  jnz     short loc_140053365
0x1400532f8  mov     al, [rbx+1Ch]
0x1400532fb  lea     r9, [rsp+58h+var_28]
0x140053300  mov     ecx, [rbx+18h]
0x140053303  lea     r8, [rsp+58h+var_30]
0x140053308  xor     edx, edx
0x14005330a  sub     al, 2
0x14005330c  cmp     al, 1
0x14005330e  setnbe  dl
0x140053311  call    cs:__imp_RtlQueryFeatureConfiguration
0x140053318  nop     dword ptr [rax+rax+00h]
0x14005331d  cmp     eax, 80000022h
0x140053322  jnz     short loc_14005336A
0x140053324  mov     [rsp+58h+var_38], 0
0x14005332d  mov     dword ptr [rsp+58h+var_38], 206h
0x140053335  mov     rdx, [rsp+58h+var_38]
0x14005333a  mov     rax, [rbx]
0x14005333d  lea     rcx, [rbx+38h]
0x140053341  mov     [rax], rdx
0x140053344  call    wil_details_FeatureDescriptors_SkipPadding
0x140053349  mov     rbx, rax
0x14005334c  test    rax, rax
0x14005334f  jnz     short loc_14005333A
0x140053351  mov     rcx, [rsp+58h+var_18]
0x140053356  xor     rcx, rsp; StackCookie
0x140053359  call    __security_check_cookie
0x14005335e  add     rsp, 50h
0x140053362  pop     rbx
0x140053363  retn
0x140053365  mov     eax, 0C0000225h
0x14005336a  lea     r8, [rsp+58h+var_38]
0x14005336f  mov     ecx, eax
0x140053371  lea     rdx, [rsp+58h+var_28]
0x140053376  call    wil_details_BuildFeatureStateCacheFromQueryResults
0x14005337b  mov     rcx, [rbx]
0x14005337e  mov     rax, [rsp+58h+var_38]
0x140053383  mov     [rcx], rax
0x140053386  lea     rcx, [rbx+38h]
0x14005338a  call    wil_details_FeatureDescriptors_SkipPadding
0x14005338f  mov     rbx, rax
0x140053392  test    rax, rax
0x140053395  jnz     loc_1400532D9
0x14005339b  jmp     short loc_140053351
```
