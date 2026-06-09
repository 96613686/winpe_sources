# wil_details_ReevaluateOnFeatureConfigurationChange

- ea: `0x140033530`
- end: `0x140033654`
- name: `wil_details_ReevaluateOnFeatureConfigurationChange`
- size: `292`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x14001fc30`
- `0x140033244`
- `0x140033530`

## import_xrefs

- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x1400335af`
- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x1400335af`

## pseudocode

```c
__int64 wil_details_ReevaluateOnFeatureConfigurationChange()
{
  __int64 *i; // rbx
  __int64 v1; // rcx
  int v2; // eax
  __int16 v3; // dx
  __int16 v4; // dx
  __int64 v6; // [rsp+20h] [rbp-28h] BYREF
  __int64 v7; // [rsp+28h] [rbp-20h] BYREF
  int v8; // [rsp+30h] [rbp-18h]

  for ( i = wil_details_featureDescriptors_a; i < wil_details_featureDescriptors_a; ++i )
  {
    if ( *i )
    {
LABEL_23:
      if ( !i )
        return wil_details_EvaluateFeatureDependencies();
      if ( !*((_BYTE *)i + 29) && !*((_BYTE *)i + 30) && !*((_BYTE *)i + 28) )
      {
        v1 = *((unsigned int *)i + 6);
        v7 = 0;
        v8 = 0;
        v6 = 0;
        v2 = ((__int64 (__fastcall *)(__int64, __int64, __int64 *, __int64 *))RtlQueryFeatureConfiguration)(
               v1,
               1,
               &v6,
               &v7);
        if ( v2 == -2147483614 || v2 == -1073741275 )
          goto LABEL_16;
        if ( v2 )
        {
          if ( v2 == 279 )
          {
            v3 = BYTE4(v7) & 0x80;
            goto LABEL_15;
          }
LABEL_16:
          v4 = 518;
        }
        else
        {
          v3 = BYTE4(v7) & 0xB0 | (4 * (WORD2(v7) & 0xFFD0));
LABEL_15:
          v4 = (8 * v3) | 0x206;
        }
        _InterlockedXor((volatile signed __int32 *)*i, ((unsigned __int16)v4 ^ (unsigned __int16)*(_DWORD *)*i) & 0xF80);
      }
      for ( i += 7; i < wil_details_featureDescriptors_a; ++i )
      {
        if ( *i )
          goto LABEL_23;
      }
      return wil_details_EvaluateFeatureDependencies();
    }
  }
  return wil_details_EvaluateFeatureDependencies();
}

```

## disassembly

```asm
0x140033530  mov     [rsp+arg_0], rbx
0x140033535  push    rsi
0x140033536  sub     rsp, 40h
0x14003353a  mov     rax, cs:__security_cookie
0x140033541  xor     rax, rsp
0x140033544  mov     [rsp+48h+var_10], rax
0x140033549  lea     rbx, wil_details_featureDescriptors_a
0x140033550  lea     rsi, wil_details_featureDescriptors_a
0x140033557  jmp     short loc_140033567
0x140033559  cmp     qword ptr [rbx], 0
0x14003355d  jnz     loc_14003362D
0x140033563  add     rbx, 8
0x140033567  cmp     rbx, rsi
0x14003356a  jb      short loc_140033559
0x14003356c  jmp     loc_140033636
0x140033571  cmp     byte ptr [rbx+1Dh], 0
0x140033575  jnz     loc_140033616
0x14003357b  cmp     byte ptr [rbx+1Eh], 0
0x14003357f  jnz     loc_140033616
0x140033585  cmp     byte ptr [rbx+1Ch], 0
0x140033589  jnz     loc_140033616
0x14003358f  mov     ecx, [rbx+18h]
0x140033592  lea     r9, [rsp+48h+var_20]
0x140033597  xor     eax, eax
0x140033599  lea     r8, [rsp+48h+var_28]
0x14003359e  mov     [rsp+48h+var_20], rax
0x1400335a3  mov     [rsp+48h+var_18], eax
0x1400335a7  mov     [rsp+48h+var_28], rax
0x1400335ac  lea     edx, [rax+1]
0x1400335af  call    cs:__imp_RtlQueryFeatureConfiguration
0x1400335b6  nop     dword ptr [rax+rax+00h]
0x1400335bb  cmp     eax, 80000022h
0x1400335c0  jz      short loc_1400335FE
0x1400335c2  cmp     eax, 0C0000225h
0x1400335c7  jz      short loc_1400335FE
0x1400335c9  test    eax, eax
0x1400335cb  jz      short loc_1400335E0
0x1400335cd  cmp     eax, 117h
0x1400335d2  jnz     short loc_1400335FE
0x1400335d4  mov     edx, dword ptr [rsp+48h+var_20+4]
0x1400335d8  and     edx, 80h
0x1400335de  jmp     short loc_1400335F3
0x1400335e0  mov     eax, dword ptr [rsp+48h+var_20+4]
0x1400335e4  mov     edx, eax
0x1400335e6  and     edx, 0FFFFFFD0h
0x1400335e9  and     eax, 0B0h
0x1400335ee  shl     edx, 2
0x1400335f1  or      edx, eax
0x1400335f3  shl     edx, 3
0x1400335f6  or      edx, 206h
0x1400335fc  jmp     short loc_140033603
0x1400335fe  mov     edx, 206h
0x140033603  mov     rax, [rbx]
0x140033606  mov     ecx, [rax]
0x140033608  mov     rax, [rbx]
0x14003360b  xor     ecx, edx
0x14003360d  and     ecx, 0F80h
0x140033613  lock xor [rax], ecx
0x140033616  add     rbx, 38h ; '8'
0x14003361a  jmp     short loc_140033626
0x14003361c  cmp     qword ptr [rbx], 0
0x140033620  jnz     short loc_14003362D
0x140033622  add     rbx, 8
0x140033626  cmp     rbx, rsi
0x140033629  jb      short loc_14003361C
0x14003362b  jmp     short loc_140033636
0x14003362d  test    rbx, rbx
0x140033630  jnz     loc_140033571
0x140033636  call    wil_details_EvaluateFeatureDependencies
0x14003363b  mov     rcx, [rsp+48h+var_10]
0x140033640  xor     rcx, rsp; StackCookie
0x140033643  call    __security_check_cookie
0x140033648  mov     rbx, [rsp+48h+arg_0]
0x14003364d  add     rsp, 40h
0x140033651  pop     rsi
0x140033652  retn
```
