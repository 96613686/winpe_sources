# wil_details_ReevaluateOnFeatureConfigurationChange

- ea: `0x1400249c0`
- end: `0x140024ae4`
- name: `wil_details_ReevaluateOnFeatureConfigurationChange`
- size: `292`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x14000bfa0`
- `0x140024770`
- `0x1400249c0`

## import_xrefs

- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x140024a3f`
- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x140024a3f`

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
0x1400249c0  mov     [rsp+arg_0], rbx
0x1400249c5  push    rsi
0x1400249c6  sub     rsp, 40h
0x1400249ca  mov     rax, cs:__security_cookie
0x1400249d1  xor     rax, rsp
0x1400249d4  mov     [rsp+48h+var_10], rax
0x1400249d9  lea     rbx, wil_details_featureDescriptors_a
0x1400249e0  lea     rsi, wil_details_featureDescriptors_a
0x1400249e7  jmp     short loc_1400249F7
0x1400249e9  cmp     qword ptr [rbx], 0
0x1400249ed  jnz     loc_140024ABD
0x1400249f3  add     rbx, 8
0x1400249f7  cmp     rbx, rsi
0x1400249fa  jb      short loc_1400249E9
0x1400249fc  jmp     loc_140024AC6
0x140024a01  cmp     byte ptr [rbx+1Dh], 0
0x140024a05  jnz     loc_140024AA6
0x140024a0b  cmp     byte ptr [rbx+1Eh], 0
0x140024a0f  jnz     loc_140024AA6
0x140024a15  cmp     byte ptr [rbx+1Ch], 0
0x140024a19  jnz     loc_140024AA6
0x140024a1f  mov     ecx, [rbx+18h]
0x140024a22  lea     r9, [rsp+48h+var_20]
0x140024a27  xor     eax, eax
0x140024a29  lea     r8, [rsp+48h+var_28]
0x140024a2e  mov     [rsp+48h+var_20], rax
0x140024a33  mov     [rsp+48h+var_18], eax
0x140024a37  mov     [rsp+48h+var_28], rax
0x140024a3c  lea     edx, [rax+1]
0x140024a3f  call    cs:__imp_RtlQueryFeatureConfiguration
0x140024a46  nop     dword ptr [rax+rax+00h]
0x140024a4b  cmp     eax, 80000022h
0x140024a50  jz      short loc_140024A8E
0x140024a52  cmp     eax, 0C0000225h
0x140024a57  jz      short loc_140024A8E
0x140024a59  test    eax, eax
0x140024a5b  jz      short loc_140024A70
0x140024a5d  cmp     eax, 117h
0x140024a62  jnz     short loc_140024A8E
0x140024a64  mov     edx, dword ptr [rsp+48h+var_20+4]
0x140024a68  and     edx, 80h
0x140024a6e  jmp     short loc_140024A83
0x140024a70  mov     eax, dword ptr [rsp+48h+var_20+4]
0x140024a74  mov     edx, eax
0x140024a76  and     edx, 0FFFFFFD0h
0x140024a79  and     eax, 0B0h
0x140024a7e  shl     edx, 2
0x140024a81  or      edx, eax
0x140024a83  shl     edx, 3
0x140024a86  or      edx, 206h
0x140024a8c  jmp     short loc_140024A93
0x140024a8e  mov     edx, 206h
0x140024a93  mov     rax, [rbx]
0x140024a96  mov     ecx, [rax]
0x140024a98  mov     rax, [rbx]
0x140024a9b  xor     ecx, edx
0x140024a9d  and     ecx, 0F80h
0x140024aa3  lock xor [rax], ecx
0x140024aa6  add     rbx, 38h ; '8'
0x140024aaa  jmp     short loc_140024AB6
0x140024aac  cmp     qword ptr [rbx], 0
0x140024ab0  jnz     short loc_140024ABD
0x140024ab2  add     rbx, 8
0x140024ab6  cmp     rbx, rsi
0x140024ab9  jb      short loc_140024AAC
0x140024abb  jmp     short loc_140024AC6
0x140024abd  test    rbx, rbx
0x140024ac0  jnz     loc_140024A01
0x140024ac6  call    wil_details_EvaluateFeatureDependencies
0x140024acb  mov     rcx, [rsp+48h+var_10]
0x140024ad0  xor     rcx, rsp; StackCookie
0x140024ad3  call    __security_check_cookie
0x140024ad8  mov     rbx, [rsp+48h+arg_0]
0x140024add  add     rsp, 40h
0x140024ae1  pop     rsi
0x140024ae2  retn
```
