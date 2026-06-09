# wil_details_ReevaluateOnFeatureConfigurationChange

- ea: `0x14000bac0`
- end: `0x14000bbe4`
- name: `wil_details_ReevaluateOnFeatureConfigurationChange`
- size: `292`
- prototype: `void()`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x140004110`
- `0x14000b858`
- `0x14000bac0`

## import_xrefs

- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x14000bb3f`
- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x14000bb3f`

## pseudocode

```c
void wil_details_ReevaluateOnFeatureConfigurationChange()
{
  __int64 **i; // rbx
  __int64 v1; // rcx
  int v2; // eax
  __int16 v3; // dx
  __int16 v4; // dx
  __int64 v5; // [rsp+20h] [rbp-28h] BYREF
  __int64 v6; // [rsp+28h] [rbp-20h] BYREF
  int v7; // [rsp+30h] [rbp-18h]

  for ( i = wil_details_featureDescriptors_a; i < (__int64 **)wil_details_featureDescriptors_z; ++i )
  {
    if ( *i )
    {
LABEL_23:
      if ( !i )
        break;
      if ( !*((_BYTE *)i + 29) && !*((_BYTE *)i + 30) && !*((_BYTE *)i + 28) )
      {
        v1 = *((unsigned int *)i + 6);
        v6 = 0;
        v7 = 0;
        v5 = 0;
        v2 = ((__int64 (__fastcall *)(__int64, __int64, __int64 *, __int64 *))RtlQueryFeatureConfiguration)(
               v1,
               1,
               &v5,
               &v6);
        if ( v2 == -2147483614 || v2 == -1073741275 )
          goto LABEL_16;
        if ( v2 )
        {
          if ( v2 == 279 )
          {
            v3 = BYTE4(v6) & 0x80;
            goto LABEL_15;
          }
LABEL_16:
          v4 = 518;
        }
        else
        {
          v3 = BYTE4(v6) & 0xB0 | (4 * (WORD2(v6) & 0xFFD0));
LABEL_15:
          v4 = (8 * v3) | 0x206;
        }
        _InterlockedXor((volatile signed __int32 *)*i, ((unsigned __int16)v4 ^ (unsigned __int16)*(_DWORD *)*i) & 0xF80);
      }
      for ( i += 7; i < (__int64 **)wil_details_featureDescriptors_z; ++i )
      {
        if ( *i )
          goto LABEL_23;
      }
      break;
    }
  }
  wil_details_EvaluateFeatureDependencies();
}

```

## disassembly

```asm
0x14000bac0  mov     [rsp+arg_0], rbx
0x14000bac5  push    rsi
0x14000bac6  sub     rsp, 40h
0x14000baca  mov     rax, cs:__security_cookie
0x14000bad1  xor     rax, rsp
0x14000bad4  mov     [rsp+48h+var_10], rax
0x14000bad9  lea     rbx, wil_details_featureDescriptors_a
0x14000bae0  lea     rsi, wil_details_featureDescriptors_z
0x14000bae7  jmp     short loc_14000BAF7
0x14000bae9  cmp     qword ptr [rbx], 0
0x14000baed  jnz     loc_14000BBBD
0x14000baf3  add     rbx, 8
0x14000baf7  cmp     rbx, rsi
0x14000bafa  jb      short loc_14000BAE9
0x14000bafc  jmp     loc_14000BBC6
0x14000bb01  cmp     byte ptr [rbx+1Dh], 0
0x14000bb05  jnz     loc_14000BBA6
0x14000bb0b  cmp     byte ptr [rbx+1Eh], 0
0x14000bb0f  jnz     loc_14000BBA6
0x14000bb15  cmp     byte ptr [rbx+1Ch], 0
0x14000bb19  jnz     loc_14000BBA6
0x14000bb1f  mov     ecx, [rbx+18h]
0x14000bb22  lea     r9, [rsp+48h+var_20]
0x14000bb27  xor     eax, eax
0x14000bb29  lea     r8, [rsp+48h+var_28]
0x14000bb2e  mov     [rsp+48h+var_20], rax
0x14000bb33  mov     [rsp+48h+var_18], eax
0x14000bb37  mov     [rsp+48h+var_28], rax
0x14000bb3c  lea     edx, [rax+1]
0x14000bb3f  call    cs:__imp_RtlQueryFeatureConfiguration
0x14000bb46  nop     dword ptr [rax+rax+00h]
0x14000bb4b  cmp     eax, 80000022h
0x14000bb50  jz      short loc_14000BB8E
0x14000bb52  cmp     eax, 0C0000225h
0x14000bb57  jz      short loc_14000BB8E
0x14000bb59  test    eax, eax
0x14000bb5b  jz      short loc_14000BB70
0x14000bb5d  cmp     eax, 117h
0x14000bb62  jnz     short loc_14000BB8E
0x14000bb64  mov     edx, dword ptr [rsp+48h+var_20+4]
0x14000bb68  and     edx, 80h
0x14000bb6e  jmp     short loc_14000BB83
0x14000bb70  mov     eax, dword ptr [rsp+48h+var_20+4]
0x14000bb74  mov     edx, eax
0x14000bb76  and     edx, 0FFFFFFD0h
0x14000bb79  and     eax, 0B0h
0x14000bb7e  shl     edx, 2
0x14000bb81  or      edx, eax
0x14000bb83  shl     edx, 3
0x14000bb86  or      edx, 206h
0x14000bb8c  jmp     short loc_14000BB93
0x14000bb8e  mov     edx, 206h
0x14000bb93  mov     rax, [rbx]
0x14000bb96  mov     ecx, [rax]
0x14000bb98  mov     rax, [rbx]
0x14000bb9b  xor     ecx, edx
0x14000bb9d  and     ecx, 0F80h
0x14000bba3  lock xor [rax], ecx
0x14000bba6  add     rbx, 38h ; '8'
0x14000bbaa  jmp     short loc_14000BBB6
0x14000bbac  cmp     qword ptr [rbx], 0
0x14000bbb0  jnz     short loc_14000BBBD
0x14000bbb2  add     rbx, 8
0x14000bbb6  cmp     rbx, rsi
0x14000bbb9  jb      short loc_14000BBAC
0x14000bbbb  jmp     short loc_14000BBC6
0x14000bbbd  test    rbx, rbx
0x14000bbc0  jnz     loc_14000BB01
0x14000bbc6  call    wil_details_EvaluateFeatureDependencies
0x14000bbcb  mov     rcx, [rsp+48h+var_10]
0x14000bbd0  xor     rcx, rsp; StackCookie
0x14000bbd3  call    __security_check_cookie
0x14000bbd8  mov     rbx, [rsp+48h+arg_0]
0x14000bbdd  add     rsp, 40h
0x14000bbe1  pop     rsi
0x14000bbe2  retn
```
