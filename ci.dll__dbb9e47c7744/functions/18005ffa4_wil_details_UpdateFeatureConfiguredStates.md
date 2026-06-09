# wil_details_UpdateFeatureConfiguredStates

- ea: `0x18005ffa4`
- end: `0x180060054`
- name: `wil_details_UpdateFeatureConfiguredStates`
- size: `176`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, installer_update`

## callers

- `0x18005fe80`

## callees

- `0x180011e20`
- `0x18002bf20`
- `0x18005fc64`
- `0x18005ffa4`

## import_xrefs

- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x18005fff4`
- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x18005fff4`

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
0x18005ffa4  push    rbx
0x18005ffa6  sub     rsp, 50h
0x18005ffaa  mov     rax, cs:__security_cookie
0x18005ffb1  xor     rax, rsp
0x18005ffb4  mov     [rsp+58h+var_18], rax
0x18005ffb9  lea     rcx, wil_details_featureDescriptors_a
0x18005ffc0  jmp     short loc_180060033
0x18005ffc2  cmp     byte ptr [rbx+1Dh], 0
0x18005ffc6  jnz     short loc_18006002F
0x18005ffc8  cmp     byte ptr [rbx+1Eh], 0
0x18005ffcc  jnz     short loc_18006002F
0x18005ffce  cmp     byte ptr [rbx+1Ch], 0
0x18005ffd2  jnz     short loc_18006002F
0x18005ffd4  mov     ecx, [rbx+18h]
0x18005ffd7  lea     r9, [rsp+58h+var_28]
0x18005ffdc  xor     eax, eax
0x18005ffde  lea     r8, [rsp+58h+var_30]
0x18005ffe3  mov     [rsp+58h+var_28], rax
0x18005ffe8  mov     [rsp+58h+var_20], eax
0x18005ffec  mov     [rsp+58h+var_30], rax
0x18005fff1  lea     edx, [rax+1]
0x18005fff4  call    cs:__imp_RtlQueryFeatureConfiguration
0x18005fffb  nop     dword ptr [rax+rax+00h]
0x180060000  lea     r8, [rsp+58h+var_38]
0x180060005  mov     [rsp+58h+var_38], 0
0x18006000e  mov     ecx, eax
0x180060010  lea     rdx, [rsp+58h+var_28]
0x180060015  call    wil_details_BuildFeatureStateCacheFromQueryResults
0x18006001a  mov     rcx, [rbx]
0x18006001d  mov     edx, [rcx]
0x18006001f  xor     edx, dword ptr [rsp+58h+var_38]
0x180060023  mov     rax, [rbx]
0x180060026  and     edx, 0F80h
0x18006002c  lock xor [rax], edx
0x18006002f  lea     rcx, [rbx+38h]
0x180060033  call    wil_details_FeatureDescriptors_SkipPadding
0x180060038  mov     rbx, rax
0x18006003b  test    rax, rax
0x18006003e  jnz     short loc_18005FFC2
0x180060040  mov     rcx, [rsp+58h+var_18]
0x180060045  xor     rcx, rsp; StackCookie
0x180060048  call    __security_check_cookie
0x18006004d  add     rsp, 50h
0x180060051  pop     rbx
0x180060052  retn
```
