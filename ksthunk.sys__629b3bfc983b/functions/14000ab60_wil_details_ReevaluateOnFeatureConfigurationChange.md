# wil_details_ReevaluateOnFeatureConfigurationChange

- ea: `0x14000ab60`
- end: `0x14000ac84`
- name: `wil_details_ReevaluateOnFeatureConfigurationChange`
- size: `292`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x140003690`
- `0x14000a858`
- `0x14000ab60`

## import_xrefs

- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x14000abdf`
- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x14000abdf`

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
0x14000ab60  mov     [rsp+arg_0], rbx
0x14000ab65  push    rsi
0x14000ab66  sub     rsp, 40h
0x14000ab6a  mov     rax, cs:__security_cookie
0x14000ab71  xor     rax, rsp
0x14000ab74  mov     [rsp+48h+var_10], rax
0x14000ab79  lea     rbx, wil_details_featureDescriptors_a
0x14000ab80  lea     rsi, wil_details_featureDescriptors_a
0x14000ab87  jmp     short loc_14000AB97
0x14000ab89  cmp     qword ptr [rbx], 0
0x14000ab8d  jnz     loc_14000AC5D
0x14000ab93  add     rbx, 8
0x14000ab97  cmp     rbx, rsi
0x14000ab9a  jb      short loc_14000AB89
0x14000ab9c  jmp     loc_14000AC66
0x14000aba1  cmp     byte ptr [rbx+1Dh], 0
0x14000aba5  jnz     loc_14000AC46
0x14000abab  cmp     byte ptr [rbx+1Eh], 0
0x14000abaf  jnz     loc_14000AC46
0x14000abb5  cmp     byte ptr [rbx+1Ch], 0
0x14000abb9  jnz     loc_14000AC46
0x14000abbf  mov     ecx, [rbx+18h]
0x14000abc2  lea     r9, [rsp+48h+var_20]
0x14000abc7  xor     eax, eax
0x14000abc9  lea     r8, [rsp+48h+var_28]
0x14000abce  mov     [rsp+48h+var_20], rax
0x14000abd3  mov     [rsp+48h+var_18], eax
0x14000abd7  mov     [rsp+48h+var_28], rax
0x14000abdc  lea     edx, [rax+1]
0x14000abdf  call    cs:__imp_RtlQueryFeatureConfiguration
0x14000abe6  nop     dword ptr [rax+rax+00h]
0x14000abeb  cmp     eax, 80000022h
0x14000abf0  jz      short loc_14000AC2E
0x14000abf2  cmp     eax, 0C0000225h
0x14000abf7  jz      short loc_14000AC2E
0x14000abf9  test    eax, eax
0x14000abfb  jz      short loc_14000AC10
0x14000abfd  cmp     eax, 117h
0x14000ac02  jnz     short loc_14000AC2E
0x14000ac04  mov     edx, dword ptr [rsp+48h+var_20+4]
0x14000ac08  and     edx, 80h
0x14000ac0e  jmp     short loc_14000AC23
0x14000ac10  mov     eax, dword ptr [rsp+48h+var_20+4]
0x14000ac14  mov     edx, eax
0x14000ac16  and     edx, 0FFFFFFD0h
0x14000ac19  and     eax, 0B0h
0x14000ac1e  shl     edx, 2
0x14000ac21  or      edx, eax
0x14000ac23  shl     edx, 3
0x14000ac26  or      edx, 206h
0x14000ac2c  jmp     short loc_14000AC33
0x14000ac2e  mov     edx, 206h
0x14000ac33  mov     rax, [rbx]
0x14000ac36  mov     ecx, [rax]
0x14000ac38  mov     rax, [rbx]
0x14000ac3b  xor     ecx, edx
0x14000ac3d  and     ecx, 0F80h
0x14000ac43  lock xor [rax], ecx
0x14000ac46  add     rbx, 38h ; '8'
0x14000ac4a  jmp     short loc_14000AC56
0x14000ac4c  cmp     qword ptr [rbx], 0
0x14000ac50  jnz     short loc_14000AC5D
0x14000ac52  add     rbx, 8
0x14000ac56  cmp     rbx, rsi
0x14000ac59  jb      short loc_14000AC4C
0x14000ac5b  jmp     short loc_14000AC66
0x14000ac5d  test    rbx, rbx
0x14000ac60  jnz     loc_14000ABA1
0x14000ac66  call    wil_details_EvaluateFeatureDependencies
0x14000ac6b  mov     rcx, [rsp+48h+var_10]
0x14000ac70  xor     rcx, rsp; StackCookie
0x14000ac73  call    __security_check_cookie
0x14000ac78  mov     rbx, [rsp+48h+arg_0]
0x14000ac7d  add     rsp, 40h
0x14000ac81  pop     rsi
0x14000ac82  retn
```
