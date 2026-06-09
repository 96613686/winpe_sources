# wil_details_PopulateInitialConfiguredFeatureStates

- ea: `0x1400211b4`
- end: `0x140021293`
- name: `wil_details_PopulateInitialConfiguredFeatureStates`
- size: `223`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1400210f4`

## callees

- `0x140003964`
- `0x1400054a0`
- `0x140011cbc`
- `0x1400211b4`

## import_xrefs

- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x140021215`
- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x140021215`

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
0x1400211b4  push    rbx
0x1400211b6  sub     rsp, 50h
0x1400211ba  mov     rax, cs:__security_cookie
0x1400211c1  xor     rax, rsp
0x1400211c4  mov     [rsp+58h+var_18], rax
0x1400211c9  lea     rcx, wil_details_featureDescriptors_a
0x1400211d0  call    wil_details_FeatureDescriptors_SkipPadding
0x1400211d5  mov     rbx, rax
0x1400211d8  test    rax, rax
0x1400211db  jz      short loc_140021255
0x1400211dd  xor     eax, eax
0x1400211df  mov     [rsp+58h+var_28], rax
0x1400211e4  mov     [rsp+58h+var_20], eax
0x1400211e8  mov     [rsp+58h+var_30], rax
0x1400211ed  mov     [rsp+58h+var_38], rax
0x1400211f2  cmp     [rbx+1Dh], al
0x1400211f5  jnz     short loc_140021269
0x1400211f7  cmp     [rbx+1Eh], al
0x1400211fa  jnz     short loc_140021269
0x1400211fc  mov     al, [rbx+1Ch]
0x1400211ff  lea     r9, [rsp+58h+var_28]
0x140021204  mov     ecx, [rbx+18h]
0x140021207  lea     r8, [rsp+58h+var_30]
0x14002120c  xor     edx, edx
0x14002120e  sub     al, 2
0x140021210  cmp     al, 1
0x140021212  setnbe  dl
0x140021215  call    cs:__imp_RtlQueryFeatureConfiguration
0x14002121c  nop     dword ptr [rax+rax+00h]
0x140021221  cmp     eax, 80000022h
0x140021226  jnz     short loc_14002126E
0x140021228  mov     [rsp+58h+var_38], 0
0x140021231  mov     dword ptr [rsp+58h+var_38], 206h
0x140021239  mov     rdx, [rsp+58h+var_38]
0x14002123e  mov     rax, [rbx]
0x140021241  lea     rcx, [rbx+38h]
0x140021245  mov     [rax], rdx
0x140021248  call    wil_details_FeatureDescriptors_SkipPadding
0x14002124d  mov     rbx, rax
0x140021250  test    rax, rax
0x140021253  jnz     short loc_14002123E
0x140021255  mov     rcx, [rsp+58h+var_18]
0x14002125a  xor     rcx, rsp; StackCookie
0x14002125d  call    __security_check_cookie
0x140021262  add     rsp, 50h
0x140021266  pop     rbx
0x140021267  retn
0x140021269  mov     eax, 0C0000225h
0x14002126e  lea     r8, [rsp+58h+var_38]
0x140021273  mov     ecx, eax
0x140021275  lea     rdx, [rsp+58h+var_28]
0x14002127a  call    wil_details_BuildFeatureStateCacheFromQueryResults
0x14002127f  mov     rcx, [rbx]
0x140021282  mov     rax, [rsp+58h+var_38]
0x140021287  mov     [rcx], rax
0x14002128a  lea     rcx, [rbx+38h]
0x14002128e  jmp     loc_1400211D0
```
