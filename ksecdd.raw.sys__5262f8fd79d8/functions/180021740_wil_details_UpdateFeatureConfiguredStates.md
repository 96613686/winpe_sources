# wil_details_UpdateFeatureConfiguredStates

- ea: `0x180021740`
- end: `0x1800217f0`
- name: `wil_details_UpdateFeatureConfiguredStates`
- size: `176`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x1800216a0`

## callees

- `0x18000b834`
- `0x1800108a0`
- `0x1800213c4`
- `0x180021740`

## import_xrefs

- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x180021790`
- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x180021790`

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

  for ( i = &Feature_Schannel_SslCopyTlsExtensions__private_descriptor; ; i = (int **)(v4 + 7) )
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
0x180021740  push    rbx
0x180021742  sub     rsp, 50h
0x180021746  mov     rax, cs:__security_cookie
0x18002174d  xor     rax, rsp
0x180021750  mov     [rsp+58h+var_18], rax
0x180021755  lea     rcx, Feature_Schannel_SslCopyTlsExtensions__private_descriptor
0x18002175c  jmp     short loc_1800217CF
0x18002175e  cmp     byte ptr [rbx+1Dh], 0
0x180021762  jnz     short loc_1800217CB
0x180021764  cmp     byte ptr [rbx+1Eh], 0
0x180021768  jnz     short loc_1800217CB
0x18002176a  cmp     byte ptr [rbx+1Ch], 0
0x18002176e  jnz     short loc_1800217CB
0x180021770  mov     ecx, [rbx+18h]
0x180021773  lea     r9, [rsp+58h+var_28]
0x180021778  xor     eax, eax
0x18002177a  lea     r8, [rsp+58h+var_30]
0x18002177f  mov     [rsp+58h+var_28], rax
0x180021784  mov     [rsp+58h+var_20], eax
0x180021788  mov     [rsp+58h+var_30], rax
0x18002178d  lea     edx, [rax+1]
0x180021790  call    cs:__imp_RtlQueryFeatureConfiguration
0x180021797  nop     dword ptr [rax+rax+00h]
0x18002179c  lea     r8, [rsp+58h+var_38]
0x1800217a1  mov     [rsp+58h+var_38], 0
0x1800217aa  mov     ecx, eax
0x1800217ac  lea     rdx, [rsp+58h+var_28]
0x1800217b1  call    wil_details_BuildFeatureStateCacheFromQueryResults
0x1800217b6  mov     rcx, [rbx]
0x1800217b9  mov     edx, [rcx]
0x1800217bb  xor     edx, dword ptr [rsp+58h+var_38]
0x1800217bf  mov     rax, [rbx]
0x1800217c2  and     edx, 0F80h
0x1800217c8  lock xor [rax], edx
0x1800217cb  lea     rcx, [rbx+38h]
0x1800217cf  call    wil_details_FeatureDescriptors_SkipPadding
0x1800217d4  mov     rbx, rax
0x1800217d7  test    rax, rax
0x1800217da  jnz     short loc_18002175E
0x1800217dc  mov     rcx, [rsp+58h+var_18]
0x1800217e1  xor     rcx, rsp; StackCookie
0x1800217e4  call    __security_check_cookie
0x1800217e9  add     rsp, 50h
0x1800217ed  pop     rbx
0x1800217ee  retn
```
