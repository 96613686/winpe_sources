# wil_details_ReevaluateOnFeatureConfigurationChange

- ea: `0x140041910`
- end: `0x140041a34`
- name: `wil_details_ReevaluateOnFeatureConfigurationChange`
- size: `292`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x14000ba20`
- `0x140041628`
- `0x140041910`

## import_xrefs

- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x14004198f`
- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x14004198f`

## pseudocode

```c
__int64 wil_details_ReevaluateOnFeatureConfigurationChange()
{
  _QWORD *i; // rbx
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
0x140041910  mov     [rsp+arg_0], rbx
0x140041915  push    rsi
0x140041916  sub     rsp, 40h
0x14004191a  mov     rax, cs:__security_cookie
0x140041921  xor     rax, rsp
0x140041924  mov     [rsp+48h+var_10], rax
0x140041929  lea     rbx, wil_details_featureDescriptors_a
0x140041930  lea     rsi, wil_details_featureDescriptors_a
0x140041937  jmp     short loc_140041947
0x140041939  cmp     qword ptr [rbx], 0
0x14004193d  jnz     loc_140041A0D
0x140041943  add     rbx, 8
0x140041947  cmp     rbx, rsi
0x14004194a  jb      short loc_140041939
0x14004194c  jmp     loc_140041A16
0x140041951  cmp     byte ptr [rbx+1Dh], 0
0x140041955  jnz     loc_1400419F6
0x14004195b  cmp     byte ptr [rbx+1Eh], 0
0x14004195f  jnz     loc_1400419F6
0x140041965  cmp     byte ptr [rbx+1Ch], 0
0x140041969  jnz     loc_1400419F6
0x14004196f  mov     ecx, [rbx+18h]
0x140041972  lea     r9, [rsp+48h+var_20]
0x140041977  xor     eax, eax
0x140041979  lea     r8, [rsp+48h+var_28]
0x14004197e  mov     [rsp+48h+var_20], rax
0x140041983  mov     [rsp+48h+var_18], eax
0x140041987  mov     [rsp+48h+var_28], rax
0x14004198c  lea     edx, [rax+1]
0x14004198f  call    cs:__imp_RtlQueryFeatureConfiguration
0x140041996  nop     dword ptr [rax+rax+00h]
0x14004199b  cmp     eax, 80000022h
0x1400419a0  jz      short loc_1400419DE
0x1400419a2  cmp     eax, 0C0000225h
0x1400419a7  jz      short loc_1400419DE
0x1400419a9  test    eax, eax
0x1400419ab  jz      short loc_1400419C0
0x1400419ad  cmp     eax, 117h
0x1400419b2  jnz     short loc_1400419DE
0x1400419b4  mov     edx, dword ptr [rsp+48h+var_20+4]
0x1400419b8  and     edx, 80h
0x1400419be  jmp     short loc_1400419D3
0x1400419c0  mov     eax, dword ptr [rsp+48h+var_20+4]
0x1400419c4  mov     edx, eax
0x1400419c6  and     edx, 0FFFFFFD0h
0x1400419c9  and     eax, 0B0h
0x1400419ce  shl     edx, 2
0x1400419d1  or      edx, eax
0x1400419d3  shl     edx, 3
0x1400419d6  or      edx, 206h
0x1400419dc  jmp     short loc_1400419E3
0x1400419de  mov     edx, 206h
0x1400419e3  mov     rax, [rbx]
0x1400419e6  mov     ecx, [rax]
0x1400419e8  mov     rax, [rbx]
0x1400419eb  xor     ecx, edx
0x1400419ed  and     ecx, 0F80h
0x1400419f3  lock xor [rax], ecx
0x1400419f6  add     rbx, 38h ; '8'
0x1400419fa  jmp     short loc_140041A06
0x1400419fc  cmp     qword ptr [rbx], 0
0x140041a00  jnz     short loc_140041A0D
0x140041a02  add     rbx, 8
0x140041a06  cmp     rbx, rsi
0x140041a09  jb      short loc_1400419FC
0x140041a0b  jmp     short loc_140041A16
0x140041a0d  test    rbx, rbx
0x140041a10  jnz     loc_140041951
0x140041a16  call    wil_details_EvaluateFeatureDependencies
0x140041a1b  mov     rcx, [rsp+48h+var_10]
0x140041a20  xor     rcx, rsp; StackCookie
0x140041a23  call    __security_check_cookie
0x140041a28  mov     rbx, [rsp+48h+arg_0]
0x140041a2d  add     rsp, 40h
0x140041a31  pop     rsi
0x140041a32  retn
```
