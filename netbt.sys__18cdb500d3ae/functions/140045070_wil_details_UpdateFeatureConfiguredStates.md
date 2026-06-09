# wil_details_UpdateFeatureConfiguredStates

- ea: `0x140045070`
- end: `0x140045120`
- name: `wil_details_UpdateFeatureConfiguredStates`
- size: `176`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, installer_update`

## callers

- `0x140044fd0`

## callees

- `0x14002d2b0`
- `0x140030f40`
- `0x140044ce0`
- `0x140045070`

## import_xrefs

- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x1400450c0`
- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x1400450c0`

## pseudocode

```c
__int64 wil_details_UpdateFeatureConfiguredStates()
{
  int **i; // rcx
  __int64 v1; // rcx
  unsigned int v2; // eax
  __int64 result; // rax
  volatile signed __int32 **v4; // rbx
  __int64 v5; // [rsp+20h] [rbp-38h] BYREF
  __int64 v6; // [rsp+28h] [rbp-30h] BYREF
  __int64 v7; // [rsp+30h] [rbp-28h] BYREF
  int v8; // [rsp+38h] [rbp-20h]

  for ( i = wil_details_featureDescriptors_a; ; i = (int **)(v4 + 7) )
  {
    result = wil_details_FeatureDescriptors_SkipPadding(i);
    v4 = (volatile signed __int32 **)result;
    if ( !result )
      break;
    if ( !*(_BYTE *)(result + 29) && !*(_BYTE *)(result + 30) && !*(_BYTE *)(result + 28) )
    {
      v1 = *(unsigned int *)(result + 24);
      v7 = 0;
      v8 = 0;
      v6 = 0;
      v2 = RtlQueryFeatureConfiguration(v1, 1, &v6, &v7);
      v5 = 0;
      wil_details_BuildFeatureStateCacheFromQueryResults(v2, &v7, &v5);
      _InterlockedXor(*v4, ((unsigned __int16)v5 ^ (unsigned __int16)**v4) & 0xF80);
    }
  }
  return result;
}

```

## disassembly

```asm
0x140045070  push    rbx
0x140045072  sub     rsp, 50h
0x140045076  mov     rax, cs:__security_cookie
0x14004507d  xor     rax, rsp
0x140045080  mov     [rsp+58h+var_18], rax
0x140045085  lea     rcx, wil_details_featureDescriptors_a
0x14004508c  jmp     short loc_1400450FF
0x14004508e  cmp     byte ptr [rbx+1Dh], 0
0x140045092  jnz     short loc_1400450FB
0x140045094  cmp     byte ptr [rbx+1Eh], 0
0x140045098  jnz     short loc_1400450FB
0x14004509a  cmp     byte ptr [rbx+1Ch], 0
0x14004509e  jnz     short loc_1400450FB
0x1400450a0  mov     ecx, [rbx+18h]
0x1400450a3  lea     r9, [rsp+58h+var_28]
0x1400450a8  xor     eax, eax
0x1400450aa  lea     r8, [rsp+58h+var_30]
0x1400450af  mov     [rsp+58h+var_28], rax
0x1400450b4  mov     [rsp+58h+var_20], eax
0x1400450b8  mov     [rsp+58h+var_30], rax
0x1400450bd  lea     edx, [rax+1]
0x1400450c0  call    cs:__imp_RtlQueryFeatureConfiguration
0x1400450c7  nop     dword ptr [rax+rax+00h]
0x1400450cc  lea     r8, [rsp+58h+var_38]
0x1400450d1  mov     [rsp+58h+var_38], 0
0x1400450da  mov     ecx, eax
0x1400450dc  lea     rdx, [rsp+58h+var_28]
0x1400450e1  call    wil_details_BuildFeatureStateCacheFromQueryResults
0x1400450e6  mov     rcx, [rbx]
0x1400450e9  mov     edx, [rcx]
0x1400450eb  xor     edx, dword ptr [rsp+58h+var_38]
0x1400450ef  mov     rax, [rbx]
0x1400450f2  and     edx, 0F80h
0x1400450f8  lock xor [rax], edx
0x1400450fb  lea     rcx, [rbx+38h]
0x1400450ff  call    wil_details_FeatureDescriptors_SkipPadding
0x140045104  mov     rbx, rax
0x140045107  test    rax, rax
0x14004510a  jnz     short loc_14004508E
0x14004510c  mov     rcx, [rsp+58h+var_18]
0x140045111  xor     rcx, rsp; StackCookie
0x140045114  call    __security_check_cookie
0x140045119  add     rsp, 50h
0x14004511d  pop     rbx
0x14004511e  retn
```
