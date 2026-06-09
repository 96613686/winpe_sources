# wil_details_ReevaluateOnFeatureConfigurationChange

- ea: `0x140024a60`
- end: `0x140024b84`
- name: `wil_details_ReevaluateOnFeatureConfigurationChange`
- size: `292`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x14000bfa0`
- `0x140024770`
- `0x140024a60`

## import_xrefs

- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x140024adf`
- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x140024adf`

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
0x140024a60  mov     [rsp+arg_0], rbx
0x140024a65  push    rsi
0x140024a66  sub     rsp, 40h
0x140024a6a  mov     rax, cs:__security_cookie
0x140024a71  xor     rax, rsp
0x140024a74  mov     [rsp+48h+var_10], rax
0x140024a79  lea     rbx, wil_details_featureDescriptors_a
0x140024a80  lea     rsi, wil_details_featureDescriptors_a
0x140024a87  jmp     short loc_140024A97
0x140024a89  cmp     qword ptr [rbx], 0
0x140024a8d  jnz     loc_140024B5D
0x140024a93  add     rbx, 8
0x140024a97  cmp     rbx, rsi
0x140024a9a  jb      short loc_140024A89
0x140024a9c  jmp     loc_140024B66
0x140024aa1  cmp     byte ptr [rbx+1Dh], 0
0x140024aa5  jnz     loc_140024B46
0x140024aab  cmp     byte ptr [rbx+1Eh], 0
0x140024aaf  jnz     loc_140024B46
0x140024ab5  cmp     byte ptr [rbx+1Ch], 0
0x140024ab9  jnz     loc_140024B46
0x140024abf  mov     ecx, [rbx+18h]
0x140024ac2  lea     r9, [rsp+48h+var_20]
0x140024ac7  xor     eax, eax
0x140024ac9  lea     r8, [rsp+48h+var_28]
0x140024ace  mov     [rsp+48h+var_20], rax
0x140024ad3  mov     [rsp+48h+var_18], eax
0x140024ad7  mov     [rsp+48h+var_28], rax
0x140024adc  lea     edx, [rax+1]
0x140024adf  call    cs:__imp_RtlQueryFeatureConfiguration
0x140024ae6  nop     dword ptr [rax+rax+00h]
0x140024aeb  cmp     eax, 80000022h
0x140024af0  jz      short loc_140024B2E
0x140024af2  cmp     eax, 0C0000225h
0x140024af7  jz      short loc_140024B2E
0x140024af9  test    eax, eax
0x140024afb  jz      short loc_140024B10
0x140024afd  cmp     eax, 117h
0x140024b02  jnz     short loc_140024B2E
0x140024b04  mov     edx, dword ptr [rsp+48h+var_20+4]
0x140024b08  and     edx, 80h
0x140024b0e  jmp     short loc_140024B23
0x140024b10  mov     eax, dword ptr [rsp+48h+var_20+4]
0x140024b14  mov     edx, eax
0x140024b16  and     edx, 0FFFFFFD0h
0x140024b19  and     eax, 0B0h
0x140024b1e  shl     edx, 2
0x140024b21  or      edx, eax
0x140024b23  shl     edx, 3
0x140024b26  or      edx, 206h
0x140024b2c  jmp     short loc_140024B33
0x140024b2e  mov     edx, 206h
0x140024b33  mov     rax, [rbx]
0x140024b36  mov     ecx, [rax]
0x140024b38  mov     rax, [rbx]
0x140024b3b  xor     ecx, edx
0x140024b3d  and     ecx, 0F80h
0x140024b43  lock xor [rax], ecx
0x140024b46  add     rbx, 38h ; '8'
0x140024b4a  jmp     short loc_140024B56
0x140024b4c  cmp     qword ptr [rbx], 0
0x140024b50  jnz     short loc_140024B5D
0x140024b52  add     rbx, 8
0x140024b56  cmp     rbx, rsi
0x140024b59  jb      short loc_140024B4C
0x140024b5b  jmp     short loc_140024B66
0x140024b5d  test    rbx, rbx
0x140024b60  jnz     loc_140024AA1
0x140024b66  call    wil_details_EvaluateFeatureDependencies
0x140024b6b  mov     rcx, [rsp+48h+var_10]
0x140024b70  xor     rcx, rsp; StackCookie
0x140024b73  call    __security_check_cookie
0x140024b78  mov     rbx, [rsp+48h+arg_0]
0x140024b7d  add     rsp, 40h
0x140024b81  pop     rsi
0x140024b82  retn
```
