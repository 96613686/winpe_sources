# wil_details_UpdateFeatureConfiguredStates

- ea: `0x140016c00`
- end: `0x140016cb0`
- name: `wil_details_UpdateFeatureConfiguredStates`
- size: `176`
- prototype: `__int64 *()`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, installer_update`

## callers

- `0x140016b60`

## callees

- `0x1400033dc`
- `0x140005bb0`
- `0x1400168cc`
- `0x140016c00`

## import_xrefs

- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x140016c50`
- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x140016c50`

## pseudocode

```c
__int64 *wil_details_UpdateFeatureConfiguredStates()
{
  __int64 *i; // rcx
  __int64 v1; // rcx
  int v2; // eax
  __int64 *result; // rax
  volatile signed __int32 **v4; // rbx
  __int64 v5; // [rsp+20h] [rbp-38h] BYREF
  __int64 v6; // [rsp+28h] [rbp-30h] BYREF
  __int64 v7; // [rsp+30h] [rbp-28h] BYREF
  int v8; // [rsp+38h] [rbp-20h]

  for ( i = (__int64 *)wil_details_featureDescriptors_a; ; i = (__int64 *)(v4 + 7) )
  {
    result = wil_details_FeatureDescriptors_SkipPadding(i);
    v4 = (volatile signed __int32 **)result;
    if ( !result )
      break;
    if ( !*((_BYTE *)result + 29) && !*((_BYTE *)result + 30) && !*((_BYTE *)result + 28) )
    {
      v1 = *((unsigned int *)result + 6);
      v7 = 0;
      v8 = 0;
      v6 = 0;
      v2 = ((__int64 (__fastcall *)(__int64, __int64, __int64 *, __int64 *, __int64))RtlQueryFeatureConfiguration)(
             v1,
             1,
             &v6,
             &v7,
             v5);
      v5 = 0;
      wil_details_BuildFeatureStateCacheFromQueryResults(v2, (__int64)&v7, &v5);
      _InterlockedXor(*v4, ((unsigned __int16)v5 ^ (unsigned __int16)**v4) & 0xF80);
    }
  }
  return result;
}

```

## disassembly

```asm
0x140016c00  push    rbx
0x140016c02  sub     rsp, 50h
0x140016c06  mov     rax, cs:__security_cookie
0x140016c0d  xor     rax, rsp
0x140016c10  mov     [rsp+58h+var_18], rax
0x140016c15  lea     rcx, wil_details_featureDescriptors_a
0x140016c1c  jmp     short loc_140016C8F
0x140016c1e  cmp     byte ptr [rbx+1Dh], 0
0x140016c22  jnz     short loc_140016C8B
0x140016c24  cmp     byte ptr [rbx+1Eh], 0
0x140016c28  jnz     short loc_140016C8B
0x140016c2a  cmp     byte ptr [rbx+1Ch], 0
0x140016c2e  jnz     short loc_140016C8B
0x140016c30  mov     ecx, [rbx+18h]
0x140016c33  lea     r9, [rsp+58h+var_28]
0x140016c38  xor     eax, eax
0x140016c3a  lea     r8, [rsp+58h+var_30]
0x140016c3f  mov     [rsp+58h+var_28], rax
0x140016c44  mov     [rsp+58h+var_20], eax
0x140016c48  mov     [rsp+58h+var_30], rax
0x140016c4d  lea     edx, [rax+1]
0x140016c50  call    cs:__imp_RtlQueryFeatureConfiguration
0x140016c57  nop     dword ptr [rax+rax+00h]
0x140016c5c  lea     r8, [rsp+58h+var_38]
0x140016c61  mov     [rsp+58h+var_38], 0
0x140016c6a  mov     ecx, eax
0x140016c6c  lea     rdx, [rsp+58h+var_28]
0x140016c71  call    wil_details_BuildFeatureStateCacheFromQueryResults
0x140016c76  mov     rcx, [rbx]
0x140016c79  mov     edx, [rcx]
0x140016c7b  xor     edx, dword ptr [rsp+58h+var_38]
0x140016c7f  mov     rax, [rbx]
0x140016c82  and     edx, 0F80h
0x140016c88  lock xor [rax], edx
0x140016c8b  lea     rcx, [rbx+38h]
0x140016c8f  call    wil_details_FeatureDescriptors_SkipPadding
0x140016c94  mov     rbx, rax
0x140016c97  test    rax, rax
0x140016c9a  jnz     short loc_140016C1E
0x140016c9c  mov     rcx, [rsp+58h+var_18]
0x140016ca1  xor     rcx, rsp; StackCookie
0x140016ca4  call    __security_check_cookie
0x140016ca9  add     rsp, 50h
0x140016cad  pop     rbx
0x140016cae  retn
```
