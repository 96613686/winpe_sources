# wil_details_ReevaluateOnFeatureConfigurationChange

- ea: `0x14000b280`
- end: `0x14000b3a4`
- name: `wil_details_ReevaluateOnFeatureConfigurationChange`
- size: `292`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x140001370`
- `0x14000ad9c`
- `0x14000b280`

## import_xrefs

- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x14000b2ff`
- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x14000b2ff`

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
0x14000b280  mov     [rsp+arg_0], rbx
0x14000b285  push    rsi
0x14000b286  sub     rsp, 40h
0x14000b28a  mov     rax, cs:__security_cookie
0x14000b291  xor     rax, rsp
0x14000b294  mov     [rsp+48h+var_10], rax
0x14000b299  lea     rbx, wil_details_featureDescriptors_a
0x14000b2a0  lea     rsi, wil_details_featureDescriptors_a
0x14000b2a7  jmp     short loc_14000B2B7
0x14000b2a9  cmp     qword ptr [rbx], 0
0x14000b2ad  jnz     loc_14000B37D
0x14000b2b3  add     rbx, 8
0x14000b2b7  cmp     rbx, rsi
0x14000b2ba  jb      short loc_14000B2A9
0x14000b2bc  jmp     loc_14000B386
0x14000b2c1  cmp     byte ptr [rbx+1Dh], 0
0x14000b2c5  jnz     loc_14000B366
0x14000b2cb  cmp     byte ptr [rbx+1Eh], 0
0x14000b2cf  jnz     loc_14000B366
0x14000b2d5  cmp     byte ptr [rbx+1Ch], 0
0x14000b2d9  jnz     loc_14000B366
0x14000b2df  mov     ecx, [rbx+18h]
0x14000b2e2  lea     r9, [rsp+48h+var_20]
0x14000b2e7  xor     eax, eax
0x14000b2e9  lea     r8, [rsp+48h+var_28]
0x14000b2ee  mov     [rsp+48h+var_20], rax
0x14000b2f3  mov     [rsp+48h+var_18], eax
0x14000b2f7  mov     [rsp+48h+var_28], rax
0x14000b2fc  lea     edx, [rax+1]
0x14000b2ff  call    cs:__imp_RtlQueryFeatureConfiguration
0x14000b306  nop     dword ptr [rax+rax+00h]
0x14000b30b  cmp     eax, 80000022h
0x14000b310  jz      short loc_14000B34E
0x14000b312  cmp     eax, 0C0000225h
0x14000b317  jz      short loc_14000B34E
0x14000b319  test    eax, eax
0x14000b31b  jz      short loc_14000B330
0x14000b31d  cmp     eax, 117h
0x14000b322  jnz     short loc_14000B34E
0x14000b324  mov     edx, dword ptr [rsp+48h+var_20+4]
0x14000b328  and     edx, 80h
0x14000b32e  jmp     short loc_14000B343
0x14000b330  mov     eax, dword ptr [rsp+48h+var_20+4]
0x14000b334  mov     edx, eax
0x14000b336  and     edx, 0FFFFFFD0h
0x14000b339  and     eax, 0B0h
0x14000b33e  shl     edx, 2
0x14000b341  or      edx, eax
0x14000b343  shl     edx, 3
0x14000b346  or      edx, 206h
0x14000b34c  jmp     short loc_14000B353
0x14000b34e  mov     edx, 206h
0x14000b353  mov     rax, [rbx]
0x14000b356  mov     ecx, [rax]
0x14000b358  mov     rax, [rbx]
0x14000b35b  xor     ecx, edx
0x14000b35d  and     ecx, 0F80h
0x14000b363  lock xor [rax], ecx
0x14000b366  add     rbx, 38h ; '8'
0x14000b36a  jmp     short loc_14000B376
0x14000b36c  cmp     qword ptr [rbx], 0
0x14000b370  jnz     short loc_14000B37D
0x14000b372  add     rbx, 8
0x14000b376  cmp     rbx, rsi
0x14000b379  jb      short loc_14000B36C
0x14000b37b  jmp     short loc_14000B386
0x14000b37d  test    rbx, rbx
0x14000b380  jnz     loc_14000B2C1
0x14000b386  call    wil_details_EvaluateFeatureDependencies
0x14000b38b  mov     rcx, [rsp+48h+var_10]
0x14000b390  xor     rcx, rsp; StackCookie
0x14000b393  call    __security_check_cookie
0x14000b398  mov     rbx, [rsp+48h+arg_0]
0x14000b39d  add     rsp, 40h
0x14000b3a1  pop     rsi
0x14000b3a2  retn
```
